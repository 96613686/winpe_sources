# Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)

- ea: `0x18000af58`
- end: `0x18000afe7`
- name: `?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(Rdp::Utils::Props *__hidden this, struct IPropertyStore *, const struct _tagpropertykey *, struct _GUID *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a114`
- `0x18000c410`
- `0x180014e40`
- `0x18001a2a0`

## callees

- `0x180006a74`
- `0x18000af58`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000afd4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000afd4`

## string_xrefs

- `0x18000af9f`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_GetGuid(
        Rdp::Utils::Props *this,
        struct IPropertyStore *a2,
        const struct _tagpropertykey *a3,
        struct _GUID *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  a3->fmtid = GUID_00000000_0000_0000_0000_000000000000;
  *(_OWORD *)pvar = 0;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(Rdp::Utils::Props *, struct IPropertyStore *, PROPVARIANT *, struct _GUID *))(*(_QWORD *)this + 40LL))(
         this,
         a2,
         pvar,
         a4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( LOWORD(pvar[0]) == 72 )
    {
      a3->fmtid = *(GUID *)pvar[1];
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
      (void *)0xD2,
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
0x18000af58  mov     [rsp+arg_0], rbx
0x18000af5d  push    rdi
0x18000af5e  sub     rsp, 40h
0x18000af62  mov     rdi, r8
0x18000af65  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000af6c  movdqu  xmmword ptr [r8], xmm0
0x18000af71  xorps   xmm1, xmm1
0x18000af74  xor     eax, eax
0x18000af76  movups  xmmword ptr [rsp+48h+pvar], xmm1; int
0x18000af7b  mov     [rsp+48h+var_18], rax
0x18000af80  mov     rax, [rcx]
0x18000af83  lea     r8, [rsp+48h+pvar]
0x18000af88  mov     rax, [rax+28h]
0x18000af8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af91  mov     ebx, eax
0x18000af93  test    eax, eax
0x18000af95  jns     short loc_18000AFB2
0x18000af97  mov     rcx, [rsp+48h]; this
0x18000af9c  mov     r9d, eax; char *
0x18000af9f  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000afa6  mov     edx, 0D2h; void *
0x18000afab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000afb0  jmp     short loc_18000AFCF
0x18000afb2  cmp     word ptr [rsp+48h+pvar], 48h ; 'H'
0x18000afb8  jz      short loc_18000AFC1
0x18000afba  mov     ebx, 80004005h
0x18000afbf  jmp     short loc_18000AFCF
0x18000afc1  mov     rax, [rsp+48h+pvar+8]
0x18000afc6  movups  xmm0, xmmword ptr [rax]
0x18000afc9  movdqu  xmmword ptr [rdi], xmm0
0x18000afcd  xor     ebx, ebx
0x18000afcf  lea     rcx, [rsp+48h+pvar]; pvar
0x18000afd4  call    cs:__imp_PropVariantClear
0x18000afda  mov     eax, ebx
0x18000afdc  mov     rbx, [rsp+48h+arg_0]
0x18000afe1  add     rsp, 40h
0x18000afe5  pop     rdi
0x18000afe6  retn
```
