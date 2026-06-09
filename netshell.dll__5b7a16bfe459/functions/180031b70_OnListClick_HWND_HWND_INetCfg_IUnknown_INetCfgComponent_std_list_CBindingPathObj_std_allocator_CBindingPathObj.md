# OnListClick(HWND__ *,HWND__ *,INetCfg *,IUnknown *,INetCfgComponent *,std::list<CBindingPathObj *,std::allocator<CBindingPathObj *>> *,int,int)

- ea: `0x180031b70`
- end: `0x180031d67`
- name: `?OnListClick@@YAHPEAUHWND__@@0PEAUINetCfg@@PEAUIUnknown@@PEAUINetCfgComponent@@PEAV?$list@PEAVCBindingPathObj@@V?$allocator@PEAVCBindingPathObj@@@std@@@std@@HH@Z`
- size: `503`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, __int64, __int64, int, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800087a0`
- `0x18002daa0`
- `0x18002fe40`

## callees

- `0x180007de0`
- `0x18001c34c`
- `0x18001e1e0`
- `0x18001eb7c`
- `0x180031864`
- `0x180031b70`
- `0x180065010`

## import_xrefs

- `USER32!SendMessageW` at `0x180031bf4`
- `USER32!SendMessageW` at `0x180031c31`
- `USER32!SendMessageW` at `0x180031c97`
- `USER32!SendMessageW` at `0x180031bf4`
- `USER32!SendMessageW` at `0x180031c31`
- `USER32!SendMessageW` at `0x180031c97`
- `USER32!MapWindowPoints` at `0x180031bdf`
- `USER32!MapWindowPoints` at `0x180031bdf`
- `USER32!GetMessagePos` at `0x180031bbd`
- `USER32!GetMessagePos` at `0x180031bbd`

## pseudocode

```c

```
