# Rdp::Utils::Props::IPropertyStore_GetLuid(IPropertyStore *,_tagpropertykey const &,_LUID *)

- ea: `0x180013da4`
- end: `0x180013e36`
- name: `?IPropertyStore_GetLuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_LUID@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(Rdp::Utils::Props *__hidden this, struct IPropertyStore *, const struct _tagpropertykey *, struct _LUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014570`

## callees

- `0x180006a74`
- `0x180013da4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013e23`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013e23`

## string_xrefs

- `0x180013ded`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_GetLuid(
        Rdp::Utils::Props *this,
        struct IPropertyStore *a2,
        const struct _tagpropertykey *a3,
        struct _LUID *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)&a3->fmtid.Data1 = 0;
  *(_OWORD *)pvar = 0;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(Rdp::Utils::Props *, __int64 *, PROPVARIANT *, struct _LUID *))(*(_QWORD *)this + 40LL))(
         this,
         PKEY_PreferredRenderAdapter,
         pvar,
         a4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( LOWORD(pvar[0]) == 20 )
    {
      *(PROPVARIANT *)&a3->fmtid.Data1 = pvar[1];
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
      (void *)0xE7,
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
0x180013da4  mov     [rsp+arg_0], rbx
0x180013da9  push    rdi
0x180013daa  sub     rsp, 40h
0x180013dae  mov     rdi, r8
0x180013db1  mov     qword ptr [r8], 0
0x180013db8  xorps   xmm0, xmm0
0x180013dbb  xor     eax, eax
0x180013dbd  movups  xmmword ptr [rsp+48h+pvar], xmm0; int
0x180013dc2  mov     [rsp+48h+var_18], rax
0x180013dc7  mov     rax, [rcx]
0x180013dca  lea     r8, [rsp+48h+pvar]
0x180013dcf  lea     rdx, PKEY_PreferredRenderAdapter
0x180013dd6  mov     rax, [rax+28h]
0x180013dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ddf  mov     ebx, eax
0x180013de1  test    eax, eax
0x180013de3  jns     short loc_180013E00
0x180013de5  mov     rcx, [rsp+48h]; this
0x180013dea  mov     r9d, eax; char *
0x180013ded  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180013df4  mov     edx, 0E7h; void *
0x180013df9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013dfe  jmp     short loc_180013E1E
0x180013e00  cmp     word ptr [rsp+48h+pvar], 14h
0x180013e06  jz      short loc_180013E0F
0x180013e08  mov     ebx, 80004005h
0x180013e0d  jmp     short loc_180013E1E
0x180013e0f  mov     eax, dword ptr [rsp+48h+pvar+8]
0x180013e13  mov     [rdi], eax
0x180013e15  mov     eax, dword ptr [rsp+48h+pvar+0Ch]
0x180013e19  mov     [rdi+4], eax
0x180013e1c  xor     ebx, ebx
0x180013e1e  lea     rcx, [rsp+48h+pvar]; pvar
0x180013e23  call    cs:__imp_PropVariantClear
0x180013e29  mov     eax, ebx
0x180013e2b  mov     rbx, [rsp+48h+arg_0]
0x180013e30  add     rsp, 40h
0x180013e34  pop     rdi
0x180013e35  retn
```
