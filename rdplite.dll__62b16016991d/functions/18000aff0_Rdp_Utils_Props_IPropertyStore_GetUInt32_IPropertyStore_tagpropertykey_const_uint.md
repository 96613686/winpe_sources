# Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)

- ea: `0x18000aff0`
- end: `0x18000b074`
- name: `?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z`
- size: `132`
- prototype: `__int64 __fastcall(Rdp::Utils::Props *__hidden this, struct IPropertyStore *, const struct _tagpropertykey *, unsigned int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b578`
- `0x18000c410`
- `0x180011db0`
- `0x180015550`
- `0x180015dcc`
- `0x1800183b4`

## callees

- `0x180006a74`
- `0x18000aff0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b061`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b061`

## string_xrefs

- `0x18000b032`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_GetUInt32(
        Rdp::Utils::Props *this,
        struct IPropertyStore *a2,
        const struct _tagpropertykey *a3,
        unsigned int *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  a3->fmtid.Data1 = 0;
  *(_OWORD *)pvar = 0;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(Rdp::Utils::Props *, struct IPropertyStore *, PROPVARIANT *, unsigned int *))(*(_QWORD *)this + 40LL))(
         this,
         a2,
         pvar,
         a4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( LOWORD(pvar[0]) == 19 )
    {
      a3->fmtid.Data1 = (unsigned int)pvar[1];
      v6 = 0;
    }
    else
    {
      v6 = -2147467259;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PropsHelpers.h",
      (const char *)(unsigned int)v5,
      (int)pvar[0]);
  }
  PropVariantClear(pvar);
  return v6;
}

```

## disassembly

```asm
0x18000aff0  mov     [rsp+arg_0], rbx
0x18000aff5  push    rdi
0x18000aff6  sub     rsp, 40h
0x18000affa  mov     rdi, r8
0x18000affd  mov     dword ptr [r8], 0
0x18000b004  xorps   xmm0, xmm0
0x18000b007  xor     eax, eax
0x18000b009  movups  xmmword ptr [rsp+48h+pvar], xmm0; int
0x18000b00e  mov     [rsp+48h+var_18], rax
0x18000b013  mov     rax, [rcx]
0x18000b016  lea     r8, [rsp+48h+pvar]
0x18000b01b  mov     rax, [rax+28h]
0x18000b01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b024  mov     ebx, eax
0x18000b026  test    eax, eax
0x18000b028  jns     short loc_18000B045
0x18000b02a  mov     rcx, [rsp+48h]; this
0x18000b02f  mov     r9d, eax; char *
0x18000b032  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000b039  mov     edx, 47h ; 'G'; void *
0x18000b03e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b043  jmp     short loc_18000B05C
0x18000b045  cmp     word ptr [rsp+48h+pvar], 13h
0x18000b04b  jz      short loc_18000B054
0x18000b04d  mov     ebx, 80004005h
0x18000b052  jmp     short loc_18000B05C
0x18000b054  mov     eax, dword ptr [rsp+48h+pvar+8]
0x18000b058  mov     [rdi], eax
0x18000b05a  xor     ebx, ebx
0x18000b05c  lea     rcx, [rsp+48h+pvar]; pvar
0x18000b061  call    cs:__imp_PropVariantClear
0x18000b067  mov     eax, ebx
0x18000b069  mov     rbx, [rsp+48h+arg_0]
0x18000b06e  add     rsp, 40h
0x18000b072  pop     rdi
0x18000b073  retn
```
