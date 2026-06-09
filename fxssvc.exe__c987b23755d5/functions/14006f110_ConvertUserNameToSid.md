# ConvertUserNameToSid

- ea: `0x14006f110`
- end: `0x14006f34a`
- name: `ConvertUserNameToSid`
- size: `570`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000cf58`
- `0x14000d244`
- `0x14000e9ec`
- `0x14000f2f0`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140065d14`
- `0x140065dbc`
- `0x14006f110`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x14006f1b5`
- `ADVAPI32!LookupAccountNameW` at `0x14006f2d2`
- `ADVAPI32!LookupAccountNameW` at `0x14006f1b5`
- `ADVAPI32!LookupAccountNameW` at `0x14006f2d2`
- `KERNEL32!GetLastError` at `0x14006f1bf`
- `KERNEL32!GetLastError` at `0x14006f21f`
- `KERNEL32!GetLastError` at `0x14006f2dc`
- `KERNEL32!GetLastError` at `0x14006f1bf`
- `KERNEL32!GetLastError` at `0x14006f21f`
- `KERNEL32!GetLastError` at `0x14006f2dc`

## pseudocode

```c

```
