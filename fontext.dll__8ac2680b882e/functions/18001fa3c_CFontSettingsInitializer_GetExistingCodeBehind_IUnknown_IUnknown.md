# CFontSettingsInitializer::GetExistingCodeBehind(IUnknown *,IUnknown * *)

- ea: `0x18001fa3c`
- end: `0x18001fac7`
- name: `?GetExistingCodeBehind@CFontSettingsInitializer@@SAJPEAUIUnknown@@PEAPEAU2@@Z`
- size: `139`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18001fad0`
- `0x180020640`

## callees

- `0x18001fa3c`
- `0x180032010`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadType` at `0x18001fa95`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18001fa95`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001fa65`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001fa65`

## pseudocode

```c
__int64 __fastcall CFontSettingsInitializer::GetExistingCodeBehind(struct IUnknown *a1, struct IUnknown **a2)
{
  HRESULT v3; // ebx
  VARIANT var; // [rsp+20h] [rbp-28h] BYREF
  void *ppvOut; // [rsp+60h] [rbp+18h] BYREF

  ppvOut = 0;
  v3 = IUnknown_QueryService(
         a1,
         (const GUID *const)&SID_PerNamespaceIDPropertyBag,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &ppvOut);
  if ( v3 >= 0 )
  {
    memset(&var, 0, sizeof(var));
    v3 = PSPropertyBag_ReadType((IPropertyBag *)ppvOut, L"FontSettingsCore", &var, 0xDu);
    if ( v3 >= 0 )
      *a2 = var.punkVal;
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001fa3c  mov     [rsp+arg_0], rbx
0x18001fa41  push    rdi
0x18001fa42  sub     rsp, 40h
0x18001fa46  mov     rdi, rdx
0x18001fa49  mov     [rsp+48h+ppvOut], 0
0x18001fa52  lea     rdx, SID_PerNamespaceIDPropertyBag; guidService
0x18001fa59  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x18001fa5e  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18001fa65  call    cs:__imp_IUnknown_QueryService
0x18001fa6b  mov     ebx, eax
0x18001fa6d  test    eax, eax
0x18001fa6f  js      short loc_18001FABA
0x18001fa71  mov     rcx, [rsp+48h+ppvOut]; propBag
0x18001fa76  lea     r8, [rsp+48h+var]; var
0x18001fa7b  xor     eax, eax
0x18001fa7d  lea     rdx, propName; "FontSettingsCore"
0x18001fa84  xorps   xmm0, xmm0
0x18001fa87  mov     qword ptr [rsp+48h+var+10h], rax
0x18001fa8c  movups  xmmword ptr [rsp+48h+var], xmm0
0x18001fa91  lea     r9d, [rax+0Dh]; type
0x18001fa95  call    cs:__imp_PSPropertyBag_ReadType
0x18001fa9b  mov     ebx, eax
0x18001fa9d  test    eax, eax
0x18001fa9f  js      short loc_18001FAA9
0x18001faa1  mov     rax, qword ptr [rsp+48h+var+8]
0x18001faa6  mov     [rdi], rax
0x18001faa9  mov     rcx, [rsp+48h+ppvOut]
0x18001faae  mov     rax, [rcx]
0x18001fab1  mov     rax, [rax+10h]
0x18001fab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faba  mov     eax, ebx
0x18001fabc  mov     rbx, [rsp+48h+arg_0]
0x18001fac1  add     rsp, 40h
0x18001fac5  pop     rdi
0x18001fac6  retn
```
