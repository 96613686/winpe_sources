# IUnknown_QueryShellBrowser(IUnknown *,_GUID const &,void * *)

- ea: `0x180028920`
- end: `0x180028a17`
- name: `?IUnknown_QueryShellBrowser@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `247`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180028680`
- `0x180028760`

## callees

- `0x18002883c`
- `0x180028920`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180028966`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800289ae`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180028a00`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180028966`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800289ae`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180028a00`

## pseudocode

```c
__int64 __fastcall IUnknown_QueryShellBrowser(struct IUnknown *a1, const struct _GUID *a2, void **a3)
{
  HRESULT ServiceObject; // ebx
  const struct _GUID *v7; // rdx
  const struct _GUID *v8; // r8
  IUnknown *punk; // [rsp+50h] [rbp+8h] BYREF
  void *ppvOut; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  ServiceObject = -2147467259;
  if ( a1 )
  {
    ppvOut = 0;
    if ( IUnknown_QueryService(
           a1,
           &GUID_3dec5f26_8322_497c_b1a9_d76f2646b3cc,
           &GUID_76542021_fff8_43f3_acbd_bb46a60a94ca,
           &ppvOut) < 0 )
    {
      ServiceObject = IUnknown_QueryServiceObject(a1, v7, v8, a2, a3);
      if ( ServiceObject < 0 )
        return (unsigned int)IUnknown_QueryService(a1, (const GUID *const)&SID_STopLevelBrowser, a2, a3);
    }
    else
    {
      punk = 0;
      ServiceObject = (*(__int64 (__fastcall **)(void *, GUID *, IUnknown **))(*(_QWORD *)ppvOut + 104LL))(
                        ppvOut,
                        &GUID_00020400_0000_0000_c000_000000000046,
                        &punk);
      if ( ServiceObject >= 0 )
      {
        ServiceObject = IUnknown_QueryService(punk, &IID_IShellBrowser, a2, a3);
        ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
  }
  return (unsigned int)ServiceObject;
}

```

## disassembly

```asm
0x180028920  mov     [rsp+arg_8], rbx
0x180028925  push    rbp
0x180028926  push    rsi
0x180028927  push    rdi
0x180028928  sub     rsp, 30h
0x18002892c  mov     qword ptr [r8], 0
0x180028933  mov     rsi, r8
0x180028936  mov     rbp, rdx
0x180028939  mov     rdi, rcx
0x18002893c  mov     ebx, 80004005h
0x180028941  test    rcx, rcx
0x180028944  jz      loc_180028A08
0x18002894a  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x18002894f  mov     [rsp+48h+ppvOut], 0
0x180028958  lea     r8, _GUID_76542021_fff8_43f3_acbd_bb46a60a94ca; riid
0x18002895f  lea     rdx, _GUID_3dec5f26_8322_497c_b1a9_d76f2646b3cc; guidService
0x180028966  call    cs:__imp_IUnknown_QueryService
0x18002896c  test    eax, eax
0x18002896e  js      short loc_1800289DA
0x180028970  mov     rcx, [rsp+48h+ppvOut]
0x180028975  lea     r8, [rsp+48h+punk]
0x18002897a  mov     [rsp+48h+punk], 0
0x180028983  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x18002898a  mov     rax, [rcx]
0x18002898d  mov     rax, [rax+68h]
0x180028991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028996  mov     ebx, eax
0x180028998  test    eax, eax
0x18002899a  js      short loc_1800289C7
0x18002899c  mov     rcx, [rsp+48h+punk]; punk
0x1800289a1  lea     rdx, IID_IShellBrowser; guidService
0x1800289a8  mov     r9, rsi; ppvOut
0x1800289ab  mov     r8, rbp; riid
0x1800289ae  call    cs:__imp_IUnknown_QueryService
0x1800289b4  mov     rcx, [rsp+48h+punk]
0x1800289b9  mov     ebx, eax
0x1800289bb  mov     rax, [rcx]
0x1800289be  mov     rax, [rax+10h]
0x1800289c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289c7  mov     rcx, [rsp+48h+ppvOut]
0x1800289cc  mov     rax, [rcx]
0x1800289cf  mov     rax, [rax+10h]
0x1800289d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289d8  jmp     short loc_180028A08
0x1800289da  mov     r9, rbp; struct _GUID *
0x1800289dd  mov     [rsp+48h+var_28], rsi; void **
0x1800289e2  mov     rcx, rdi; struct IUnknown *
0x1800289e5  call    ?IUnknown_QueryServiceObject@@YAJPEAUIUnknown@@AEBU_GUID@@11PEAPEAX@Z; IUnknown_QueryServiceObject(IUnknown *,_GUID const &,_GUID const &,_GUID const &,void * *)
0x1800289ea  mov     ebx, eax
0x1800289ec  test    eax, eax
0x1800289ee  jns     short loc_180028A08
0x1800289f0  mov     r9, rsi; ppvOut
0x1800289f3  lea     rdx, SID_STopLevelBrowser; guidService
0x1800289fa  mov     r8, rbp; riid
0x1800289fd  mov     rcx, rdi; punk
0x180028a00  call    cs:__imp_IUnknown_QueryService
0x180028a06  mov     ebx, eax
0x180028a08  mov     eax, ebx
0x180028a0a  mov     rbx, [rsp+48h+arg_8]
0x180028a0f  add     rsp, 30h
0x180028a13  pop     rdi
0x180028a14  pop     rsi
0x180028a15  pop     rbp
0x180028a16  retn
```
