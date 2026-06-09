# CHgCplInitializer::GetExistingCodeBehind(IUnknown *,IUnknown * *)

- ea: `0x18000ec00`
- end: `0x18000ec8b`
- name: `?GetExistingCodeBehind@CHgCplInitializer@@SAJPEAUIUnknown@@PEAPEAU2@@Z`
- size: `139`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000eca0`
- `0x18000f410`

## callees

- `0x18000ec00`
- `0x18001a010`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadType` at `0x18000ec59`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18000ec59`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000ec29`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000ec29`

## pseudocode

```c
__int64 __fastcall CHgCplInitializer::GetExistingCodeBehind(struct IUnknown *a1, struct IUnknown **a2)
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
    v3 = PSPropertyBag_ReadType((IPropertyBag *)ppvOut, L"HgCplCore", &var, 0xDu);
    if ( v3 >= 0 )
      *a2 = var.punkVal;
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ec00  mov     [rsp+arg_0], rbx
0x18000ec05  push    rdi
0x18000ec06  sub     rsp, 40h
0x18000ec0a  mov     rdi, rdx
0x18000ec0d  mov     [rsp+48h+ppvOut], 0
0x18000ec16  lea     rdx, SID_PerNamespaceIDPropertyBag; guidService
0x18000ec1d  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x18000ec22  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18000ec29  call    cs:__imp_IUnknown_QueryService
0x18000ec2f  mov     ebx, eax
0x18000ec31  test    eax, eax
0x18000ec33  js      short loc_18000EC7E
0x18000ec35  mov     rcx, [rsp+48h+ppvOut]; propBag
0x18000ec3a  lea     r8, [rsp+48h+var]; var
0x18000ec3f  xor     eax, eax
0x18000ec41  lea     rdx, propName; "HgCplCore"
0x18000ec48  xorps   xmm0, xmm0
0x18000ec4b  mov     qword ptr [rsp+48h+var+10h], rax
0x18000ec50  movups  xmmword ptr [rsp+48h+var], xmm0
0x18000ec55  lea     r9d, [rax+0Dh]; type
0x18000ec59  call    cs:__imp_PSPropertyBag_ReadType
0x18000ec5f  mov     ebx, eax
0x18000ec61  test    eax, eax
0x18000ec63  js      short loc_18000EC6D
0x18000ec65  mov     rax, qword ptr [rsp+48h+var+8]
0x18000ec6a  mov     [rdi], rax
0x18000ec6d  mov     rcx, [rsp+48h+ppvOut]
0x18000ec72  mov     rax, [rcx]
0x18000ec75  mov     rax, [rax+10h]
0x18000ec79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec7e  mov     eax, ebx
0x18000ec80  mov     rbx, [rsp+48h+arg_0]
0x18000ec85  add     rsp, 40h
0x18000ec89  pop     rdi
0x18000ec8a  retn
```
