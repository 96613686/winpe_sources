# FetchReportBegin(_TLSReport *,ulong,_iobuf * *)

- ea: `0x180052984`
- end: `0x180052ac3`
- name: `?FetchReportBegin@@YAKPEAU_TLSReport@@KPEAPEAU_iobuf@@@Z`
- size: `319`
- prototype: `unsigned int __fastcall(struct _TLSReport *, unsigned int, struct _iobuf **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011470`

## callees

- `0x18000d060`
- `0x180052984`
- `0x1800547dc`
- `0x18005650c`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!feof` at `0x180052a4c`
- `msvcrt!feof` at `0x180052a4c`
- `msvcrt!ferror` at `0x180052a86`
- `msvcrt!ferror` at `0x180052a86`
- `msvcrt!fgetws` at `0x180052a6c`
- `msvcrt!fgetws` at `0x180052a6c`
- `msvcrt!_errno` at `0x180052a32`
- `msvcrt!_errno` at `0x180052a32`
- `msvcrt!_wfopen` at `0x180052a1e`
- `msvcrt!_wfopen` at `0x180052a1e`

## pseudocode

```c
__int64 __fastcall FetchReportBegin(struct _TLSReport *a1, int a2, struct _iobuf **a3)
{
  unsigned int v3; // ebx
  char *v6; // rcx
  FILE *v7; // rax
  FILE *i; // r8
  wchar_t FileName[264]; // [rsp+30h] [rbp-428h] BYREF
  wchar_t Buffer[256]; // [rsp+240h] [rbp-218h] BYREF

  v3 = 0;
  if ( !a3 )
    return 87;
  if ( !a1 )
    return 87;
  v6 = (char *)a1 + 1544;
  if ( !v6 )
    return 87;
  StringCchPrintfW(FileName, 0x104u, L"%s%s", &g_szReportDir, v6);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88234>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MSRC88234>::GetImpl'::`2'::impl) )
  {
    if ( !IsValidReportPath(FileName) )
      return 87;
  }
  v7 = _wfopen(FileName, L"rt");
  *a3 = v7;
  if ( !v7 )
    return (unsigned int)*_errno();
  for ( i = v7; fgetws(Buffer, 255, i); i = *a3 )
  {
    if ( !a2 )
      return v3;
    --a2;
    if ( feof(*a3) )
      return v3;
  }
  return (unsigned int)ferror(*a3);
}

```

## disassembly

```asm
0x180052984  mov     [rsp+arg_8], rbx
0x180052989  mov     [rsp+arg_18], rsi
0x18005298e  push    rdi
0x18005298f  sub     rsp, 450h
0x180052996  mov     rax, cs:__security_cookie
0x18005299d  xor     rax, rsp
0x1800529a0  mov     [rsp+458h+var_18], rax
0x1800529a8  xor     ebx, ebx
0x1800529aa  mov     rdi, r8
0x1800529ad  mov     esi, edx
0x1800529af  test    r8, r8
0x1800529b2  jz      loc_180052A98
0x1800529b8  test    rcx, rcx
0x1800529bb  jz      loc_180052A98
0x1800529c1  add     rcx, 608h
0x1800529c8  jz      loc_180052A98
0x1800529ce  mov     [rsp+458h+var_438], rcx
0x1800529d3  lea     r9, ?g_szReportDir@@3PAGA; ushort near * g_szReportDir
0x1800529da  lea     rcx, [rsp+458h+FileName]; unsigned __int16 *
0x1800529df  mov     edx, 104h; unsigned __int64
0x1800529e4  lea     r8, aSS_1; "%s%s"
0x1800529eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800529f0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MSRC88234@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MSRC88234@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88234> `wil::Feature<__WilFeatureTraits_Feature_MSRC88234>::GetImpl(void)'::`2'::impl
0x1800529f7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MSRC88234@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88234>::__private_IsEnabled(void)
0x1800529fc  test    al, al
0x1800529fe  jz      short loc_180052A12
0x180052a00  lea     rcx, [rsp+458h+FileName]; unsigned __int16 *
0x180052a05  call    IsValidReportPath
0x180052a0a  test    al, al
0x180052a0c  jz      loc_180052A98
0x180052a12  lea     rdx, aRt; "rt"
0x180052a19  lea     rcx, [rsp+458h+FileName]; FileName
0x180052a1e  call    cs:__imp__wfopen
0x180052a25  nop     dword ptr [rax+rax+00h]
0x180052a2a  mov     [rdi], rax
0x180052a2d  test    rax, rax
0x180052a30  jnz     short loc_180052A42
0x180052a32  call    cs:__imp__errno
0x180052a39  nop     dword ptr [rax+rax+00h]
0x180052a3e  mov     eax, [rax]
0x180052a40  jmp     short loc_180052A9D
0x180052a42  mov     r8, rax
0x180052a45  jmp     short loc_180052A5F
0x180052a47  mov     rcx, [rdi]; Stream
0x180052a4a  dec     esi
0x180052a4c  call    cs:__imp_feof
0x180052a53  nop     dword ptr [rax+rax+00h]
0x180052a58  test    eax, eax
0x180052a5a  jnz     short loc_180052A94
0x180052a5c  mov     r8, [rdi]; Stream
0x180052a5f  mov     edx, 0FFh; BufferCount
0x180052a64  lea     rcx, [rsp+458h+Buffer]; Buffer
0x180052a6c  call    cs:__imp_fgetws
0x180052a73  nop     dword ptr [rax+rax+00h]
0x180052a78  test    rax, rax
0x180052a7b  jz      short loc_180052A83
0x180052a7d  test    esi, esi
0x180052a7f  jnz     short loc_180052A47
0x180052a81  jmp     short loc_180052A94
0x180052a83  mov     rcx, [rdi]; Stream
0x180052a86  call    cs:__imp_ferror
0x180052a8d  nop     dword ptr [rax+rax+00h]
0x180052a92  mov     ebx, eax
0x180052a94  mov     eax, ebx
0x180052a96  jmp     short loc_180052A9D
0x180052a98  mov     eax, 57h ; 'W'
0x180052a9d  mov     rcx, [rsp+458h+var_18]
0x180052aa5  xor     rcx, rsp; StackCookie
0x180052aa8  call    __security_check_cookie
0x180052aad  lea     r11, [rsp+458h+var_8]
0x180052ab5  mov     rbx, [r11+18h]
0x180052ab9  mov     rsi, [r11+28h]
0x180052abd  mov     rsp, r11
0x180052ac0  pop     rdi
0x180052ac1  retn
```
