# CupShup BD Command Centre (Streamlit)

This app reads the uploaded CupShup Excel workbook and provides:
- Executive overview of BD closed revenue, target achievement and realised revenue
- Team performance by rep
- Named pipeline view (clearly labelled as a 2 Nov 2026 snapshot in the source)
- Outbound activity and meetings
- LMS overview
- Full explorer for every worksheet in the uploaded workbook
- Workbook coverage and data-quality inventory

## Run locally
1. Install Python 3.10+.
2. Run `pip install -r requirements.txt`.
3. Run `streamlit run app.py`.
4. Upload `CupShup_BD_Pipeline_Review.xlsx` in the sidebar.

## Deploy free on Streamlit Community Cloud
1. Create a GitHub repository and upload `app.py` and `requirements.txt` (do not upload sensitive workbook data to a public repository).
2. Sign in to Streamlit Community Cloud with GitHub.
3. Choose **New app**, select the repository, branch and `app.py`.
4. Deploy. Open the generated app URL and upload the workbook using the sidebar.
5. Upload a fresh Excel export when the source tracker changes.

## Important data notes
- All worksheets are shown in the All 22 Sheets explorer; no sheet is intentionally omitted.
- The app uses the raw `BD Log` and `Targets` sheets for closed-revenue and target calculations, rather than adding pre-calculated summary tabs to avoid double counting.
- `Closed (L)` follows the source definition: signed agreement, advance or PO.
- `Realised Revenue` is shown separately from BD closed revenue.
- The source labels `Named Pipeline` as a 2 Nov 2026 snapshot; it should be refreshed before relying on current pipeline values.
- The source note on `Realised Revenue` says Elixiir Q3 billing of ₹24.6 L is not credited in Shweta's tab.
- Excel formulas are displayed as stored in the workbook in the Sheet Explorer; this app does not recalculate Excel formulas.
- This is a workbook-snapshot dashboard, not a live Google Sheets connection. Refresh by uploading a new workbook export.
