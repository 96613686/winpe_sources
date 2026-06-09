# Rdp::Utils::Props::IPropertyStore_GetInterface<IRDPCoreChannelManager>(IPropertyStore *,_tagpropertykey const &,IRDPCoreChannelManager * *)

- ea: `0x1800095fc`
- end: `0x1800096a6`
- name: `??$IPropertyStore_GetInterface@UIRDPCoreChannelManager@@@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAUIRDPCoreChannelManager@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a114`

## callees

- `0x180006a74`
- `0x1800095fc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009693`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009693`

## string_xrefs

- `0x180009645`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_GetInterface<IRDPCoreChannelManager>(
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
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)a1 + 40LL))(
         a1,
         PKEY_DynamicVcManager,
         pvar);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( LOWORD(pvar[0]) == 13 )
    {
      if ( (**(int (__fastcall ***)(PROPVARIANT, GUID *, _QWORD *))pvar[1])(
             pvar[1],
             &GUID_0fd57159_e83e_476a_b9a8_4a7976e71e18,
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
0x1800095fc  mov     [rsp+arg_0], rbx
0x180009601  push    rdi
0x180009602  sub     rsp, 40h
0x180009606  mov     rdi, r8
0x180009609  mov     qword ptr [r8], 0
0x180009610  xorps   xmm0, xmm0
0x180009613  xor     eax, eax
0x180009615  movups  xmmword ptr [rsp+48h+pvar], xmm0; int
0x18000961a  mov     [rsp+48h+var_18], rax
0x18000961f  mov     rax, [rcx]
0x180009622  lea     r8, [rsp+48h+pvar]
0x180009627  lea     rdx, PKEY_DynamicVcManager
0x18000962e  mov     rax, [rax+28h]
0x180009632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009637  mov     ebx, eax
0x180009639  test    eax, eax
0x18000963b  jns     short loc_180009658
0x18000963d  mov     rcx, [rsp+48h]; this
0x180009642  mov     r9d, eax; char *
0x180009645  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000964c  mov     edx, 0B9h; void *
0x180009651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009656  jmp     short loc_18000968E
0x180009658  cmp     word ptr [rsp+48h+pvar], 0Dh
0x18000965e  jz      short loc_180009667
0x180009660  mov     ebx, 80004005h
0x180009665  jmp     short loc_18000968E
0x180009667  mov     rcx, [rsp+48h+pvar+8]
0x18000966c  mov     rax, [rcx]
0x18000966f  mov     r8, rdi
0x180009672  lea     rdx, _GUID_0fd57159_e83e_476a_b9a8_4a7976e71e18
0x180009679  mov     rax, [rax]
0x18000967c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009681  test    eax, eax
0x180009683  jns     short loc_18000968C
0x180009685  mov     ebx, 80004002h
0x18000968a  jmp     short loc_18000968E
0x18000968c  xor     ebx, ebx
0x18000968e  lea     rcx, [rsp+48h+pvar]; pvar
0x180009693  call    cs:__imp_PropVariantClear
0x180009699  mov     eax, ebx
0x18000969b  mov     rbx, [rsp+48h+arg_0]
0x1800096a0  add     rsp, 40h
0x1800096a4  pop     rdi
0x1800096a5  retn
```
