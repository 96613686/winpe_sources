# CCorSvcMgr::CreateWorkerRestrictedToken(_TOKEN_PRIVILEGES *)

- ea: `0x1800280bc`
- end: `0x18002830f`
- name: `?CreateWorkerRestrictedToken@CCorSvcMgr@@CAPEAXPEAU_TOKEN_PRIVILEGES@@@Z`
- size: `595`
- prototype: `void *__fastcall(struct _TOKEN_PRIVILEGES *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180027ea8`

## callees

- `0x180007f20`
- `0x180007fd4`
- `0x180008200`
- `0x1800280bc`
- `0x1800304ec`
- `0x1800351e8`
- `0x18003dc50`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180028100`
- `KERNEL32!GetCurrentProcess` at `0x180028100`
- `KERNEL32!CloseHandle` at `0x1800282d5`
- `KERNEL32!CloseHandle` at `0x1800282d5`
- `KERNEL32!GetLastError` at `0x180028152`
- `KERNEL32!GetLastError` at `0x180028152`

## pseudocode

```c

```
