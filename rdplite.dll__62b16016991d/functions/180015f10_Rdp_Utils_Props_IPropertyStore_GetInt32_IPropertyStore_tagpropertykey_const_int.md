# Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)

- ea: `0x180015f10`
- end: `0x180015f94`
- name: `?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z`
- size: `132`
- prototype: `__int64 __fastcall(Rdp::Utils::Props *__hidden this, struct IPropertyStore *, const struct _tagpropertykey *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015dcc`

## callees

- `0x180006a74`
- `0x180015f10`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015f81`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015f81`

## string_xrefs

- `0x180015f52`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_GetInt32(
        Rdp::Utils::Props *this,
        struct IPropertyStore *a2,
        const struct _tagpropertykey *a3,
        int *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  a3->fmtid.Data1 = 0;
  *(_OWORD *)pvar = 0;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(Rdp::Utils::Props *, struct IPropertyStore *, PROPVARIANT *, int *))(*(_QWORD *)this + 40LL))(
         this,
         a2,
         pvar,
         a4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( LOWORD(pvar[0]) == 3 )
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
      (void *)0x5D,
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
0x180015f10  mov     [rsp+arg_0], rbx
0x180015f15  push    rdi
0x180015f16  sub     rsp, 40h
0x180015f1a  mov     rdi, r8
0x180015f1d  mov     dword ptr [r8], 0
0x180015f24  xorps   xmm0, xmm0
0x180015f27  xor     eax, eax
0x180015f29  movups  xmmword ptr [rsp+48h+pvar], xmm0; int
0x180015f2e  mov     [rsp+48h+var_18], rax
0x180015f33  mov     rax, [rcx]
0x180015f36  lea     r8, [rsp+48h+pvar]
0x180015f3b  mov     rax, [rax+28h]
0x180015f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f44  mov     ebx, eax
0x180015f46  test    eax, eax
0x180015f48  jns     short loc_180015F65
0x180015f4a  mov     rcx, [rsp+48h]; this
0x180015f4f  mov     r9d, eax; char *
0x180015f52  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180015f59  mov     edx, 5Dh ; ']'; void *
0x180015f5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f63  jmp     short loc_180015F7C
0x180015f65  cmp     word ptr [rsp+48h+pvar], 3
0x180015f6b  jz      short loc_180015F74
0x180015f6d  mov     ebx, 80004005h
0x180015f72  jmp     short loc_180015F7C
0x180015f74  mov     eax, dword ptr [rsp+48h+pvar+8]
0x180015f78  mov     [rdi], eax
0x180015f7a  xor     ebx, ebx
0x180015f7c  lea     rcx, [rsp+48h+pvar]; pvar
0x180015f81  call    cs:__imp_PropVariantClear
0x180015f87  mov     eax, ebx
0x180015f89  mov     rbx, [rsp+48h+arg_0]
0x180015f8e  add     rsp, 40h
0x180015f92  pop     rdi
0x180015f93  retn
```
