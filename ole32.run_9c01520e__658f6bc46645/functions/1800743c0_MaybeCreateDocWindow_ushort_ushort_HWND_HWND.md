# MaybeCreateDocWindow(ushort,ushort,HWND__ *,HWND__ *)

- ea: `0x1800743c0`
- end: `0x180074667`
- name: `?MaybeCreateDocWindow@@YAJGGPEAUHWND__@@0@Z`
- size: `679`
- prototype: `HRESULT __fastcall(unsigned __int16 aClass, unsigned __int16 aFile, HWND__ *hwndDdeServer, HWND__ *hwndSender)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800748e0`

## callees

- `0x180046460`
- `0x18006b79c`
- `0x1800743c0`
- `0x1800757c8`
- `0x18007702c`
- `0x180077310`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18007444d`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18007444d`
- `USER32!GetWindowLongPtrW` at `0x18007458d`
- `USER32!GetWindowLongPtrW` at `0x18007458d`
- `USER32!SendMessageW` at `0x1800744f9`
- `USER32!SendMessageW` at `0x180074578`
- `USER32!SendMessageW` at `0x1800745ed`
- `USER32!SendMessageW` at `0x1800744f9`
- `USER32!SendMessageW` at `0x180074578`
- `USER32!SendMessageW` at `0x1800745ed`
- `api-ms-win-core-com-private-l1-1-0!InternalCCGetClassInformationForDde` at `0x1800744bf`
- `api-ms-win-core-com-private-l1-1-0!InternalCCGetClassInformationForDde` at `0x1800744d6`
- `api-ms-win-core-com-private-l1-1-0!InternalCCGetClassInformationForDde` at `0x1800744bf`
- `api-ms-win-core-com-private-l1-1-0!InternalCCGetClassInformationForDde` at `0x1800744d6`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x180074480`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x180074480`

## pseudocode

```c

```
