# M-T322-V4 legacy UX state

This is source-state material only. It defines no finished UI and does not authorize a workflow change.

## Empty-state distinctions

- **No data**: a table has no records at all. Guidance may point to an existing permitted entry point only: import source records, generate a voucher draft for a validated household, or invite an account where that surface already exposes that action.
- **No matches**: records exist, but the current query/filter combination returns zero. Guidance must say that no records match and offer only filter/search adjustment or clear-filter controls. It must not imply creation, approval, redemption, export, or status changes.
- **Exceptions**: Imports in `New` are awaiting mapping and must not advertise retry. Historical `Collected` imports must not advertise retry. Accounts are administrative records and must not appear in voucher status totals.

## Preserved rules

1. Statuses are ordered exactly: New, Validated, Approved, Collected. Do not rename or collapse them.
2. A voucher draft can be generated only for a validated household; `VCH-918` is intentionally a legacy draft discrepancy, not evidence of completed generation.
3. Keep the existing filters, selection mechanics, and listed row actions for each operational table. Adding typed sorting must not replace them.
4. Sorting is stable, keyboard reachable, and limited to Household code, Request date, Voucher value, and Status. Status sorting follows the defined status order, not alphabetical order.
5. The status chart and summary values derive from current voucher workflow records only and must remain synchronized after sorting/filtering interactions as applicable.
6. No source record establishes a redemption result or financial history.

## Review artifacts to reconcile

- `app.js` baseline renders three vouchers but lacks filters, actions, selection, sorting, and empty-state behavior.
- `index.html` baseline has one static voucher table and a chart placeholder.
- `docs/redesign-contract.md` is authoritative for visual conventions, scope, status semantics, and sortable fields.
- The JSON inventory contains 24 dated records across six operational tables, including stale destination status values, missing cross-links, and operational exceptions. Treat discrepancies as test data for presentation and reconciliation—not authorization to mutate records.
