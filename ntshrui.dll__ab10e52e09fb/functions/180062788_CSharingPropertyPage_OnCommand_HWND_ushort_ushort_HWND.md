# CSharingPropertyPage::_OnCommand(HWND__ *,ushort,ushort,HWND__ *)

- ea: `0x180062788`
- end: `0x1800628f1`
- name: `?_OnCommand@CSharingPropertyPage@@IEAAHPEAUHWND__@@GG0@Z`
- size: `361`
- prototype: `__int64 __usercall@<rax>(CSharingPropertyPage *__hidden this@<rcx>, HWND hwndOwner@<rdx>, unsigned __int16@<r8w>, unsigned __int16@<r9w>, HWND)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001dd40`

## callees

- `0x18000323c`
- `0x18001c4a8`
- `0x1800620b4`
- `0x180062788`
- `0x180062f84`
- `0x180072844`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800627d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800627d5`
- `USER32!PostMessageW` at `0x180062866`
- `USER32!PostMessageW` at `0x1800628cf`
- `USER32!PostMessageW` at `0x180062866`
- `USER32!PostMessageW` at `0x1800628cf`
- `USER32!GetParent` at `0x180062852`
- `USER32!GetParent` at `0x1800628bb`
- `USER32!GetParent` at `0x180062852`
- `USER32!GetParent` at `0x1800628bb`

## pseudocode

```c

```
