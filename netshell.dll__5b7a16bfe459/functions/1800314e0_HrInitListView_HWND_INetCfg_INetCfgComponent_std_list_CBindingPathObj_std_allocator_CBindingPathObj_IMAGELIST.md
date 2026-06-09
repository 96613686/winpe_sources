# HrInitListView(HWND__ *,INetCfg *,INetCfgComponent *,std::list<CBindingPathObj *,std::allocator<CBindingPathObj *>> *,_IMAGELIST * *)

- ea: `0x1800314e0`
- end: `0x180031577`
- name: `?HrInitListView@@YAJPEAUHWND__@@PEAUINetCfg@@PEAUINetCfgComponent@@PEAV?$list@PEAVCBindingPathObj@@V?$allocator@PEAVCBindingPathObj@@@std@@@std@@PEAPEAU_IMAGELIST@@@Z`
- size: `151`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, struct _IMAGELIST **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002c9a0`
- `0x18002ca40`

## callees

- `0x18001eb7c`
- `0x18003133c`
- `0x1800314e0`
- `0x18003191c`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x180031506`
- `USER32!GetWindowLongPtrW` at `0x180031506`
- `USER32!SendMessageW` at `0x180031563`
- `USER32!SendMessageW` at `0x180031563`
- `USER32!GetParent` at `0x1800314f8`
- `USER32!GetParent` at `0x1800314f8`

## pseudocode

```c

```
