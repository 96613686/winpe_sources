# CFirewallCplInitializer::GetExistingCodeBehind(IUnknown *,IUnknown * *)

- ea: `0x18000f034`
- end: `0x18000f0bf`
- name: `?GetExistingCodeBehind@CFirewallCplInitializer@@SAJPEAUIUnknown@@PEAPEAU2@@Z`
- size: `139`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IUnknown **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000f130`
- `0x180010060`
- `0x180010d20`

## callees

- `0x18000f034`
- `0x180032010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18000f05d`
- `SHCORE!IUnknown_QueryService` at `0x18000f05d`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18000f08d`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18000f08d`

## pseudocode

```c
__int64 __fastcall CFirewallCplInitializer::GetExistingCodeBehind(struct IUnknown *a1, struct IUnknown **a2)
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
    v3 = PSPropertyBag_ReadType((IPropertyBag *)ppvOut, L"FirewallCplCore", &var, 0xDu);
    if ( v3 >= 0 )
      *a2 = var.punkVal;
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000f034  mov     [rsp+arg_0], rbx
0x18000f039  push    rdi
0x18000f03a  sub     rsp, 40h
0x18000f03e  mov     rdi, rdx
0x18000f041  mov     [rsp+48h+ppvOut], 0
0x18000f04a  lea     rdx, SID_PerNamespaceIDPropertyBag; guidService
0x18000f051  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x18000f056  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18000f05d  call    cs:__imp_IUnknown_QueryService
0x18000f063  mov     ebx, eax
0x18000f065  test    eax, eax
0x18000f067  js      short loc_18000F0B2
0x18000f069  mov     rcx, [rsp+48h+ppvOut]; propBag
0x18000f06e  lea     r8, [rsp+48h+var]; var
0x18000f073  xor     eax, eax
0x18000f075  lea     rdx, aFirewallcplcor; "FirewallCplCore"
0x18000f07c  xorps   xmm0, xmm0
0x18000f07f  mov     qword ptr [rsp+48h+var+10h], rax
0x18000f084  movups  xmmword ptr [rsp+48h+var], xmm0
0x18000f089  lea     r9d, [rax+0Dh]; type
0x18000f08d  call    cs:__imp_PSPropertyBag_ReadType
0x18000f093  mov     ebx, eax
0x18000f095  test    eax, eax
0x18000f097  js      short loc_18000F0A1
0x18000f099  mov     rax, qword ptr [rsp+48h+var+8]
0x18000f09e  mov     [rdi], rax
0x18000f0a1  mov     rcx, [rsp+48h+ppvOut]
0x18000f0a6  mov     rax, [rcx]
0x18000f0a9  mov     rax, [rax+10h]
0x18000f0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0b2  mov     eax, ebx
0x18000f0b4  mov     rbx, [rsp+48h+arg_0]
0x18000f0b9  add     rsp, 40h
0x18000f0bd  pop     rdi
0x18000f0be  retn
```
