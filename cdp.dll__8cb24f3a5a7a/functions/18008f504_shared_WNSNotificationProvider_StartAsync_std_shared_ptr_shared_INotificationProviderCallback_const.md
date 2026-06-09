# shared::WNSNotificationProvider::StartAsync(std::shared_ptr<shared::INotificationProviderCallback> const &)

- ea: `0x18008f504`
- end: `0x18008f6e3`
- name: `?StartAsync@WNSNotificationProvider@shared@@QEAAXAEBV?$shared_ptr@VINotificationProviderCallback@shared@@@std@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(shared::WNSNotificationProvider *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18004ddb8`

## callees

- `0x1800110f8`
- `0x180013da0`
- `0x180059714`
- `0x18005a14c`
- `0x18008dbc0`
- `0x18008f504`
- `0x1800ddd6c`
- `0x1800ef5f8`
- `0x180133350`
- `0x1801333f0`
- `0x18016c080`
- `0x18016fbd4`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f5ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f5ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008f5e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008f5e0`
- `msvcp_win!_Mtx_unlock` at `0x18008f6dc`

## string_xrefs

- `0x18008f5b1`: `{"text":"Obtaining notification URI"}`
- `0x18008f62d`: `{"text":"WPN is ready! registering for notifications"}`
- `0x18008f670`: `{"text":"WPN is not currently ready! waiting for WNF to fire"}`
- `0x18008f65d`: `{"text":"Skipping QueueRegisterForNotifications as one is already queued."}`
- `0x18008f688`: `{"text":"WNSNotificationProvider - No persisted channel URI"}`

## pseudocode

```c

```
