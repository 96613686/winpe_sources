# Csl::StringToULongLongCommon(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,int,unsigned __int64 &)

- ea: `0x14000d9bc`
- end: `0x14000daf6`
- name: `?StringToULongLongCommon@Csl@@YAJAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@HAEA_K@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64, int, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14000dafc`
- `0x14001dd28`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x14000cd84`
- `0x14000d9bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x14000da36`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x14000da36`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x14000da51`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x14000da51`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000da71`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000da71`

## pseudocode

```c
__int64 __fastcall Csl::StringToULongLongCommon(__int64 a1, int a2, __int64 *a3)
{
  unsigned __int64 v4; // r8
  const void *v6; // rdx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  wchar_t *String[2]; // [rsp+20h] [rbp-28h] BYREF
  _WORD v13[12]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  wchar_t *EndPtr; // [rsp+70h] [rbp+28h] BYREF

  v4 = *(_QWORD *)(a1 + 8);
  v6 = *(const void **)a1;
  String[0] = v13;
  v13[0] = 0;
  String[1] = v13;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)String,
          v6,
          v4) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x133,
      (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
      (const char *)0x8007000ELL);
    if ( String[0] != v13 )
      operator delete(String[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  _o__set_errno(0);
  EndPtr = 0;
  v8 = _wcstoi64(String[0], &EndPtr, a2);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 314;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
      (const char *)0x8007000DLL);
    if ( String[0] != v13 )
      operator delete(String[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942413LL;
  }
  if ( v8 )
  {
    v11 = String[0];
  }
  else if ( *(_DWORD *)_o__errno() || (v11 = String[0], EndPtr == String[0]) || *EndPtr )
  {
    v10 = 325;
    goto LABEL_12;
  }
  *a3 = v9;
  if ( v11 != v13 )
    operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x14000d9bc  push    rbp
0x14000d9be  push    rbx
0x14000d9bf  push    rsi
0x14000d9c0  push    rdi
0x14000d9c1  mov     rbp, rsp
0x14000d9c4  sub     rsp, 48h
0x14000d9c8  lea     rax, [rbp+var_18]
0x14000d9cc  mov     rdi, r8
0x14000d9cf  mov     r8, [rcx+8]
0x14000d9d3  mov     ebx, edx
0x14000d9d5  mov     rdx, [rcx]
0x14000d9d8  xor     esi, esi
0x14000d9da  mov     [rbp+String], rax
0x14000d9de  lea     rcx, [rbp+String]
0x14000d9e2  lea     rax, [rbp+var_18]
0x14000d9e6  mov     [rbp+var_18], si
0x14000d9ea  mov     [rbp+var_20], rax
0x14000d9ee  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14000d9f3  test    al, al
0x14000d9f5  jnz     short loc_14000DA34
0x14000d9f7  mov     rcx, [rbp+20h]; this
0x14000d9fb  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000da02  mov     ebx, 8007000Eh
0x14000da07  mov     edx, 133h; void *
0x14000da0c  mov     r9d, ebx; char *
0x14000da0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000da14  mov     rcx, [rbp+String]; void *
0x14000da18  lea     rdx, [rbp+var_18]
0x14000da1c  cmp     rcx, rdx
0x14000da1f  jz      short loc_14000DA2D
0x14000da21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000da28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000da2d  mov     eax, ebx
0x14000da2f  jmp     loc_14000DAEC
0x14000da34  xor     ecx, ecx
0x14000da36  call    cs:__imp__o__set_errno
0x14000da3d  nop     dword ptr [rax+rax+00h]
0x14000da42  mov     rcx, [rbp+String]; String
0x14000da46  lea     rdx, [rbp+EndPtr]; EndPtr
0x14000da4a  mov     r8d, ebx; Radix
0x14000da4d  mov     [rbp+EndPtr], rsi
0x14000da51  call    cs:__imp__wcstoi64
0x14000da58  nop     dword ptr [rax+rax+00h]
0x14000da5d  mov     rbx, rax
0x14000da60  test    rax, rax
0x14000da63  jns     short loc_14000DA6C
0x14000da65  mov     edx, 13Ah
0x14000da6a  jmp     short loc_14000DA98
0x14000da6c  test    rbx, rbx
0x14000da6f  jnz     short loc_14000DACE
0x14000da71  call    cs:__imp__o__errno
0x14000da78  nop     dword ptr [rax+rax+00h]
0x14000da7d  cmp     [rax], esi
0x14000da7f  jnz     short loc_14000DA93
0x14000da81  mov     rax, [rbp+EndPtr]
0x14000da85  mov     rcx, [rbp+String]
0x14000da89  cmp     rax, rcx
0x14000da8c  jz      short loc_14000DA93
0x14000da8e  cmp     [rax], si
0x14000da91  jz      short loc_14000DAD2
0x14000da93  mov     edx, 145h; void *
0x14000da98  mov     rcx, [rbp+20h]; this
0x14000da9c  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000daa3  mov     r9d, 8007000Dh; char *
0x14000daa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000daae  mov     rcx, [rbp+String]; void *
0x14000dab2  lea     rax, [rbp+var_18]
0x14000dab6  cmp     rcx, rax
0x14000dab9  jz      short loc_14000DAC7
0x14000dabb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000dac2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dac7  mov     eax, 8007000Dh
0x14000dacc  jmp     short loc_14000DAEC
0x14000dace  mov     rcx, [rbp+String]; void *
0x14000dad2  lea     rax, [rbp+var_18]
0x14000dad6  mov     [rdi], rbx
0x14000dad9  cmp     rcx, rax
0x14000dadc  jz      short loc_14000DAEA
0x14000dade  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000dae5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000daea  xor     eax, eax
0x14000daec  add     rsp, 48h
0x14000daf0  pop     rdi
0x14000daf1  pop     rsi
0x14000daf2  pop     rbx
0x14000daf3  pop     rbp
0x14000daf4  retn
```
