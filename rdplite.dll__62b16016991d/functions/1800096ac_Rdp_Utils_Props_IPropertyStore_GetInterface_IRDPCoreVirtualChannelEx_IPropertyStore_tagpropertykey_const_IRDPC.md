# Rdp::Utils::Props::IPropertyStore_GetInterface<IRDPCoreVirtualChannelEx>(IPropertyStore *,_tagpropertykey const &,IRDPCoreVirtualChannelEx * *)

- ea: `0x1800096ac`
- end: `0x18000974f`
- name: `??$IPropertyStore_GetInterface@UIRDPCoreVirtualChannelEx@@@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAUIRDPCoreVirtualChannelEx@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a114`

## callees

- `0x180006a74`
- `0x1800096ac`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000973c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000973c`

## string_xrefs

- `0x1800096ee`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_GetInterface<IRDPCoreVirtualChannelEx>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a3 = 0;
  *(_OWORD *)pvar = 0;
  v8 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, PROPVARIANT *))(*(_QWORD *)a1 + 40LL))(a1, a2, pvar);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( LOWORD(pvar[0]) == 13 )
    {
      if ( (**(int (__fastcall ***)(PROPVARIANT, GUID *, _QWORD *))pvar[1])(
             pvar[1],
             &GUID_5c45d603_ff63_46ec_885f_7f9c366ae117,
             a3) >= 0 )
        v5 = 0;
      else
        v5 = -2147467262;
    }
    else
    {
      v5 = -2147467259;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PropsHelpers.h",
      (const char *)(unsigned int)v4,
      (int)pvar[0]);
  }
  PropVariantClear(pvar);
  return v5;
}

```

## disassembly

```asm
0x1800096ac  mov     [rsp+arg_0], rbx
0x1800096b1  push    rdi
0x1800096b2  sub     rsp, 40h
0x1800096b6  mov     rdi, r8
0x1800096b9  mov     qword ptr [r8], 0
0x1800096c0  xorps   xmm0, xmm0
0x1800096c3  xor     eax, eax
0x1800096c5  movups  xmmword ptr [rsp+48h+pvar], xmm0; int
0x1800096ca  mov     [rsp+48h+var_18], rax
0x1800096cf  mov     rax, [rcx]
0x1800096d2  lea     r8, [rsp+48h+pvar]
0x1800096d7  mov     rax, [rax+28h]
0x1800096db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096e0  mov     ebx, eax
0x1800096e2  test    eax, eax
0x1800096e4  jns     short loc_180009701
0x1800096e6  mov     rcx, [rsp+48h]; this
0x1800096eb  mov     r9d, eax; char *
0x1800096ee  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800096f5  mov     edx, 0B9h; void *
0x1800096fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096ff  jmp     short loc_180009737
0x180009701  cmp     word ptr [rsp+48h+pvar], 0Dh
0x180009707  jz      short loc_180009710
0x180009709  mov     ebx, 80004005h
0x18000970e  jmp     short loc_180009737
0x180009710  mov     rcx, [rsp+48h+pvar+8]
0x180009715  mov     rax, [rcx]
0x180009718  mov     r8, rdi
0x18000971b  lea     rdx, _GUID_5c45d603_ff63_46ec_885f_7f9c366ae117
0x180009722  mov     rax, [rax]
0x180009725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000972a  test    eax, eax
0x18000972c  jns     short loc_180009735
0x18000972e  mov     ebx, 80004002h
0x180009733  jmp     short loc_180009737
0x180009735  xor     ebx, ebx
0x180009737  lea     rcx, [rsp+48h+pvar]; pvar
0x18000973c  call    cs:__imp_PropVariantClear
0x180009742  mov     eax, ebx
0x180009744  mov     rbx, [rsp+48h+arg_0]
0x180009749  add     rsp, 40h
0x18000974d  pop     rdi
0x18000974e  retn
```
