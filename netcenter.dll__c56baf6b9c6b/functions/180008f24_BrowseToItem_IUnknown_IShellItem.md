# BrowseToItem(IUnknown *,IShellItem *)

- ea: `0x180008f24`
- end: `0x180008fbd`
- name: `?BrowseToItem@@YAJPEAUIUnknown@@PEAUIShellItem@@@Z`
- size: `153`
- prototype: `int(struct IUnknown *, struct IShellItem *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000d2e4`

## callees

- `0x180008f24`
- `0x180023010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180008f4d`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180008f4d`
- `SHELL32!SHGetIDListFromObject` at `0x180008f6a`
- `SHELL32!SHGetIDListFromObject` at `0x180008f6a`
- `SHELL32!__imp_ILFree` at `0x180008f99`
- `SHELL32!__imp_ILFree` at `0x180008f99`

## pseudocode

```c
__int64 __fastcall BrowseToItem(struct IUnknown *a1, IUnknown *a2)
{
  HRESULT v3; // ebx
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp+18h] BYREF
  void *ppvOut; // [rsp+48h] [rbp+20h] BYREF

  ppvOut = 0;
  v3 = IUnknown_QueryService(
         a1,
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_000214e2_0000_0000_c000_000000000046,
         &ppvOut);
  if ( v3 >= 0 )
  {
    ppidl = 0;
    v3 = SHGetIDListFromObject(a2, &ppidl);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(void *, LPITEMIDLIST, __int64))(*(_QWORD *)ppvOut + 88LL))(ppvOut, ppidl, 1);
      ILFree(ppidl);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008f24  mov     [rsp+arg_0], rbx
0x180008f29  push    rdi
0x180008f2a  sub     rsp, 20h
0x180008f2e  mov     rdi, rdx
0x180008f31  mov     [rsp+28h+ppvOut], 0
0x180008f3a  lea     rdx, SID_STopLevelBrowser; guidService
0x180008f41  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x180008f46  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x180008f4d  call    cs:__imp_IUnknown_QueryService
0x180008f53  mov     ebx, eax
0x180008f55  test    eax, eax
0x180008f57  js      short loc_180008FB0
0x180008f59  lea     rdx, [rsp+28h+ppidl]; ppidl
0x180008f5e  mov     [rsp+28h+ppidl], 0
0x180008f67  mov     rcx, rdi; punk
0x180008f6a  call    cs:__imp_SHGetIDListFromObject
0x180008f70  mov     ebx, eax
0x180008f72  test    eax, eax
0x180008f74  js      short loc_180008F9F
0x180008f76  mov     rcx, [rsp+28h+ppvOut]
0x180008f7b  mov     r8d, 1
0x180008f81  mov     rdx, [rsp+28h+ppidl]
0x180008f86  mov     rax, [rcx]
0x180008f89  mov     rax, [rax+58h]
0x180008f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f92  mov     rcx, [rsp+28h+ppidl]; pidl
0x180008f97  mov     ebx, eax
0x180008f99  call    cs:__imp_ILFree
0x180008f9f  mov     rcx, [rsp+28h+ppvOut]
0x180008fa4  mov     rax, [rcx]
0x180008fa7  mov     rax, [rax+10h]
0x180008fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fb0  mov     eax, ebx
0x180008fb2  mov     rbx, [rsp+28h+arg_0]
0x180008fb7  add     rsp, 20h
0x180008fbb  pop     rdi
0x180008fbc  retn
```
