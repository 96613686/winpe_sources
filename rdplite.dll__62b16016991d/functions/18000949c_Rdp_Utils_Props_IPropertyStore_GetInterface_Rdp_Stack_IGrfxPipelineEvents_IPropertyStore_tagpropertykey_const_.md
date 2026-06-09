# Rdp::Utils::Props::IPropertyStore_GetInterface<Rdp::Stack::IGrfxPipelineEvents>(IPropertyStore *,_tagpropertykey const &,Rdp::Stack::IGrfxPipelineEvents * *)

- ea: `0x18000949c`
- end: `0x180009546`
- name: `??$IPropertyStore_GetInterface@UIGrfxPipelineEvents@Stack@Rdp@@@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAUIGrfxPipelineEvents@Stack@2@@Z`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a114`

## callees

- `0x180006a74`
- `0x18000949c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009533`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009533`

## string_xrefs

- `0x1800094e5`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_GetInterface<Rdp::Stack::IGrfxPipelineEvents>(
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
         PKEY_GrfxPipelineEvents,
         pvar);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( LOWORD(pvar[0]) == 13 )
    {
      if ( (**(int (__fastcall ***)(PROPVARIANT, GUID *, _QWORD *))pvar[1])(
             pvar[1],
             &GUID_f3de9982_9b56_48ec_9279_812e4560ddc8,
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
0x18000949c  mov     [rsp+arg_0], rbx
0x1800094a1  push    rdi
0x1800094a2  sub     rsp, 40h
0x1800094a6  mov     rdi, r8
0x1800094a9  mov     qword ptr [r8], 0
0x1800094b0  xorps   xmm0, xmm0
0x1800094b3  xor     eax, eax
0x1800094b5  movups  xmmword ptr [rsp+48h+pvar], xmm0; int
0x1800094ba  mov     [rsp+48h+var_18], rax
0x1800094bf  mov     rax, [rcx]
0x1800094c2  lea     r8, [rsp+48h+pvar]
0x1800094c7  lea     rdx, PKEY_GrfxPipelineEvents
0x1800094ce  mov     rax, [rax+28h]
0x1800094d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094d7  mov     ebx, eax
0x1800094d9  test    eax, eax
0x1800094db  jns     short loc_1800094F8
0x1800094dd  mov     rcx, [rsp+48h]; this
0x1800094e2  mov     r9d, eax; char *
0x1800094e5  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800094ec  mov     edx, 0B9h; void *
0x1800094f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094f6  jmp     short loc_18000952E
0x1800094f8  cmp     word ptr [rsp+48h+pvar], 0Dh
0x1800094fe  jz      short loc_180009507
0x180009500  mov     ebx, 80004005h
0x180009505  jmp     short loc_18000952E
0x180009507  mov     rcx, [rsp+48h+pvar+8]
0x18000950c  mov     rax, [rcx]
0x18000950f  mov     r8, rdi
0x180009512  lea     rdx, _GUID_f3de9982_9b56_48ec_9279_812e4560ddc8
0x180009519  mov     rax, [rax]
0x18000951c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009521  test    eax, eax
0x180009523  jns     short loc_18000952C
0x180009525  mov     ebx, 80004002h
0x18000952a  jmp     short loc_18000952E
0x18000952c  xor     ebx, ebx
0x18000952e  lea     rcx, [rsp+48h+pvar]; pvar
0x180009533  call    cs:__imp_PropVariantClear
0x180009539  mov     eax, ebx
0x18000953b  mov     rbx, [rsp+48h+arg_0]
0x180009540  add     rsp, 40h
0x180009544  pop     rdi
0x180009545  retn
```
