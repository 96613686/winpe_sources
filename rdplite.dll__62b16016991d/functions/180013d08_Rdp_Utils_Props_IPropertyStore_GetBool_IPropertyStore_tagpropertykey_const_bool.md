# Rdp::Utils::Props::IPropertyStore_GetBool(IPropertyStore *,_tagpropertykey const &,bool *)

- ea: `0x180013d08`
- end: `0x180013d9c`
- name: `?IPropertyStore_GetBool@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEA_N@Z`
- size: `148`
- prototype: `__int64 __fastcall(Rdp::Utils::Props *__hidden this, struct IPropertyStore *, const struct _tagpropertykey *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001367c`

## callees

- `0x180006a74`
- `0x180013d08`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013d84`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013d84`

## string_xrefs

- `0x180013d53`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_GetBool(
        Rdp::Utils::Props *this,
        struct IPropertyStore *a2,
        const struct _tagpropertykey *a3,
        bool *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  LOBYTE(a3->fmtid.Data1) = 0;
  *(_OWORD *)pvar = 0;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(Rdp::Utils::Props *, __int64 *, PROPVARIANT *, bool *))(*(_QWORD *)this + 40LL))(
         this,
         PKEY_Caps_Enable_Sw_Mouse,
         pvar,
         a4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( LOWORD(pvar[0]) == 11 )
    {
      LOBYTE(a3->fmtid.Data1) = LOWORD(pvar[1]) != 0;
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
      (void *)0x32,
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
0x180013d08  mov     r11, rsp
0x180013d0b  mov     [r11+8], rbx
0x180013d0f  mov     [r11+10h], rsi
0x180013d13  push    rdi
0x180013d14  sub     rsp, 40h
0x180013d18  mov     rdi, r8
0x180013d1b  xor     esi, esi
0x180013d1d  mov     [r8], sil
0x180013d20  xorps   xmm0, xmm0
0x180013d23  xor     eax, eax
0x180013d25  movups  xmmword ptr [rsp+48h+pvar], xmm0; int
0x180013d2a  mov     [r11-18h], rax
0x180013d2e  mov     rax, [rcx]
0x180013d31  lea     r8, [r11-28h]
0x180013d35  lea     rdx, PKEY_Caps_Enable_Sw_Mouse
0x180013d3c  mov     rax, [rax+28h]
0x180013d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d45  mov     ebx, eax
0x180013d47  test    eax, eax
0x180013d49  jns     short loc_180013D64
0x180013d4b  mov     rcx, [rsp+48h]; this
0x180013d50  mov     r9d, eax; char *
0x180013d53  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180013d5a  lea     edx, [rsi+32h]; void *
0x180013d5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013d62  jmp     short loc_180013D7F
0x180013d64  cmp     word ptr [rsp+48h+pvar], 0Bh
0x180013d6a  jz      short loc_180013D73
0x180013d6c  mov     ebx, 80004005h
0x180013d71  jmp     short loc_180013D7F
0x180013d73  cmp     word ptr [rsp+48h+pvar+8], si
0x180013d78  setnz   al
0x180013d7b  mov     [rdi], al
0x180013d7d  mov     ebx, esi
0x180013d7f  lea     rcx, [rsp+48h+pvar]; pvar
0x180013d84  call    cs:__imp_PropVariantClear
0x180013d8a  mov     eax, ebx
0x180013d8c  mov     rbx, [rsp+48h+arg_0]
0x180013d91  mov     rsi, [rsp+48h+arg_8]
0x180013d96  add     rsp, 40h
0x180013d9a  pop     rdi
0x180013d9b  retn
```
