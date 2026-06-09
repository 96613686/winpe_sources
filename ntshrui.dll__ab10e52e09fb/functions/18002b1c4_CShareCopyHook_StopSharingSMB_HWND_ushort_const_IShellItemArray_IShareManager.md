# CShareCopyHook::_StopSharingSMB(HWND__ *,ushort const *,IShellItemArray *,IShareManager *)

- ea: `0x18002b1c4`
- end: `0x18002b4d0`
- name: `?_StopSharingSMB@CShareCopyHook@@AEAAJPEAUHWND__@@PEBGPEAUIShellItemArray@@PEAUIShareManager@@@Z`
- size: `780`
- prototype: `__int64 __fastcall(CShareCopyHook *__hidden this, HWND, const unsigned __int16 *, struct IShellItemArray *, struct IShareManager *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016770`

## callees

- `0x18001a1a4`
- `0x18001c4a8`
- `0x18002b1c4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b20e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b20e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002b29c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002b331`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002b471`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002b29c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002b331`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002b471`

## pseudocode

```c

```
