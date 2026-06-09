# GetHwndOfFrame(IUnknown *,HWND__ * *)

- ea: `0x18000f0c8`
- end: `0x18000f129`
- name: `?GetHwndOfFrame@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z`
- size: `97`
- prototype: `int(struct IUnknown *, HWND *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800098bc`
- `0x18000f438`

## callees

- `0x18000f0c8`
- `0x180032010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18000f0f1`
- `SHCORE!IUnknown_QueryService` at `0x18000f0f1`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000f105`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000f105`

## pseudocode

```c
__int64 __fastcall GetHwndOfFrame(struct IUnknown *a1, HWND *a2)
{
  HRESULT v3; // ebx
  void *ppvOut; // [rsp+40h] [rbp+18h] BYREF

  ppvOut = 0;
  v3 = IUnknown_QueryService(
         a1,
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_00000000_0000_0000_c000_000000000046,
         &ppvOut);
  if ( v3 >= 0 )
  {
    IUnknown_GetWindow((IUnknown *)ppvOut, a2);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000f0c8  mov     [rsp+arg_0], rbx
0x18000f0cd  push    rdi
0x18000f0ce  sub     rsp, 20h
0x18000f0d2  mov     rdi, rdx
0x18000f0d5  mov     [rsp+28h+ppvOut], 0
0x18000f0de  lea     rdx, SID_STopLevelBrowser; guidService
0x18000f0e5  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x18000f0ea  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000f0f1  call    cs:__imp_IUnknown_QueryService
0x18000f0f7  mov     ebx, eax
0x18000f0f9  test    eax, eax
0x18000f0fb  js      short loc_18000F11C
0x18000f0fd  mov     rcx, [rsp+28h+ppvOut]; punk
0x18000f102  mov     rdx, rdi; phwnd
0x18000f105  call    cs:__imp_IUnknown_GetWindow
0x18000f10b  mov     rcx, [rsp+28h+ppvOut]
0x18000f110  mov     rdx, [rcx]
0x18000f113  mov     rax, [rdx+10h]
0x18000f117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f11c  mov     eax, ebx
0x18000f11e  mov     rbx, [rsp+28h+arg_0]
0x18000f123  add     rsp, 20h
0x18000f127  pop     rdi
0x18000f128  retn
```
