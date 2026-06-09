# CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)

- ea: `0x18003691c`
- end: `0x180036b4d`
- name: `?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z`
- size: `561`
- prototype: `__int64 __fastcall(const struct CLRConfig::ConfigStringInfo *, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180005fc4`
- `0x180006d60`
- `0x18001dcb0`
- `0x18002cfd4`
- `0x1800368fc`
- `0x1800375ac`
- `0x180037c10`

## callees

- `0x180030530`
- `0x180030568`
- `0x180036598`
- `0x18003691c`
- `0x180036b50`
- `0x180036fd0`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `ucrtbase_clr0400!wcscpy_s` at `0x1800369d0`
- `ucrtbase_clr0400!wcscpy_s` at `0x180036ac0`
- `ucrtbase_clr0400!wcscpy_s` at `0x1800369d0`
- `ucrtbase_clr0400!wcscpy_s` at `0x180036ac0`

## pseudocode

```c
__int64 __fastcall CLRConfig::GetConfigValue(wchar_t **a1, unsigned __int16 **a2)
{
  unsigned __int16 *ConfigString_DontUse; // rbx
  wchar_t *v5; // rcx
  __int64 v6; // rdi
  unsigned __int64 v7; // rdi
  unsigned __int128 v8; // rax
  wchar_t *v9; // rax
  int v10; // r8d
  char v11; // dl
  char v12; // r14
  BOOL v13; // edi
  unsigned int v14; // r8d
  __int64 v15; // rdi
  unsigned __int64 v16; // rdi
  unsigned __int128 v17; // rax
  wchar_t *v18; // rax
  unsigned __int16 *v20; // rdi
  wchar_t *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v22; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v23[264]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Source[132]; // [rsp+148h] [rbp+48h] BYREF

  ConfigString_DontUse = 0;
  if ( ((_DWORD)a1[1] & 0x400) == 0 )
  {
    if ( CLRConfig::s_IsQuirkEnabledCallback )
    {
      v5 = *a1;
      LODWORD(v21) = 0;
      if ( (int)CLRConfig::getQuirkEnabledAndValueFromWinDB(v5, (int *)&v21, (struct _CPT_QUIRK_DATA *)v23) >= 0 )
      {
        if ( (_DWORD)v21 )
        {
          v6 = -1;
          do
            ++v6;
          while ( Source[v6] );
          v7 = v6 + 1;
          v8 = v7 * (unsigned __int128)2uLL;
          if ( !is_mul_ok(v7, 2u) )
            *(_QWORD *)&v8 = -1;
          v9 = (wchar_t *)operator new(v8, *((const struct NoThrow **)&v8 + 1));
          ConfigString_DontUse = v9;
          if ( !v9 )
            return 2147942414LL;
          wcscpy_s(v9, v7, Source);
        }
      }
    }
  }
  v10 = *((_DWORD *)a1 + 2);
  v11 = ((v10 & 1) == 0) | 2;
  if ( (v10 & 8) != 0 )
    v11 = ((_DWORD)a1[1] & 1) == 0;
  v12 = v11 | 4;
  if ( (v10 & 4) != 0 )
    v12 = v11;
  v13 = (v10 & 2) == 0;
  if ( ConfigString_DontUse )
    goto LABEL_31;
  if ( (v10 & 0x20) == 0 )
  {
    ConfigString_DontUse = REGUTIL::GetConfigString_DontUse_(*a1, v13, v12, 1);
    if ( ConfigString_DontUse )
      goto LABEL_31;
  }
  v14 = *((_DWORD *)a1 + 2);
  if ( (v14 & 0x10) == 0
    && CLRConfig::s_GetConfigValueCallback
    && (int)CLRConfig::s_GetConfigValueCallback(*a1, &v21, (v14 >> 6) & 1, (v14 >> 7) & 1) >= 0
    && v21 )
  {
    v15 = -1;
    do
      ++v15;
    while ( v21[v15] );
    v16 = v15 + 1;
    v17 = v16 * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v16, 2u) )
      *(_QWORD *)&v17 = -1;
    v18 = (wchar_t *)operator new(v17, *((const struct NoThrow **)&v17 + 1));
    ConfigString_DontUse = v18;
    if ( !v18 )
      return 2147942414LL;
    wcscpy_s(v18, v16, v21);
    goto LABEL_31;
  }
  if ( ((_BYTE)a1[1] & 0x20) != 0 )
  {
    ConfigString_DontUse = REGUTIL::GetConfigString_DontUse_(*a1, v13, v12, 1);
    if ( ConfigString_DontUse )
    {
LABEL_31:
      if ( ((_DWORD)a1[1] & 0x100) != 0 )
      {
        v22 = 0;
        if ( (int)CLRConfig::TrimWhiteSpace(ConfigString_DontUse, &v22) >= 0 )
        {
          v20 = v22;
          if ( v22 )
          {
            operator delete(ConfigString_DontUse);
            ConfigString_DontUse = v20;
          }
        }
      }
    }
  }
  *a2 = ConfigString_DontUse;
  return 0;
}

```

## disassembly

```asm
0x18003691c  mov     [rsp-8+arg_10], rbx
0x180036921  mov     [rsp-8+arg_18], rsi
0x180036926  push    rbp
0x180036927  push    rdi
0x180036928  push    r12
0x18003692a  push    r14
0x18003692c  push    r15
0x18003692e  lea     rbp, [rsp-160h]
0x180036936  sub     rsp, 260h
0x18003693d  mov     rax, cs:__security_cookie
0x180036944  xor     rax, rsp
0x180036947  mov     [rbp+180h+var_30], rax
0x18003694e  xor     r12d, r12d
0x180036951  or      r14, 0FFFFFFFFFFFFFFFFh
0x180036955  test    dword ptr [rcx+8], 400h
0x18003695c  mov     r15, rdx
0x18003695f  mov     rsi, rcx
0x180036962  mov     ebx, r12d
0x180036965  jnz     short loc_1800369D6
0x180036967  cmp     cs:?s_IsQuirkEnabledCallback@CLRConfig@@0P6A_NPEBGK@ZEA, r12; bool (*CLRConfig::s_IsQuirkEnabledCallback)(ushort const *,ulong)
0x18003696e  jz      short loc_1800369D6
0x180036970  mov     rcx, [rcx]; Source
0x180036973  lea     r8, [rsp+280h+var_240]; struct _CPT_QUIRK_DATA *
0x180036978  lea     rdx, [rsp+280h+var_250]; int *
0x18003697d  mov     dword ptr [rsp+280h+var_250], r12d
0x180036982  call    ?getQuirkEnabledAndValueFromWinDB@CLRConfig@@SAJPEBGPEAHPEAU_CPT_QUIRK_DATA@@@Z; CLRConfig::getQuirkEnabledAndValueFromWinDB(ushort const *,int *,_CPT_QUIRK_DATA *)
0x180036987  test    eax, eax
0x180036989  js      short loc_1800369D6
0x18003698b  cmp     dword ptr [rsp+280h+var_250], r12d
0x180036990  jz      short loc_1800369D6
0x180036992  lea     rax, [rbp+180h+Source]
0x180036996  mov     rdi, r14
0x180036999  inc     rdi
0x18003699c  cmp     [rax+rdi*2], r12w
0x1800369a1  jnz     short loc_180036999
0x1800369a3  inc     rdi
0x1800369a6  mov     eax, 2
0x1800369ab  mul     rdi
0x1800369ae  cmovo   rax, r14
0x1800369b2  mov     rcx, rax; dwBytes
0x1800369b5  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x1800369ba  mov     rbx, rax
0x1800369bd  test    rax, rax
0x1800369c0  jz      loc_180036AAE
0x1800369c6  lea     r8, [rbp+180h+Source]; Source
0x1800369ca  mov     rdx, rdi; SizeInWords
0x1800369cd  mov     rcx, rax; Destination
0x1800369d0  call    cs:__imp_wcscpy_s
0x1800369d6  mov     r8d, [rsi+8]
0x1800369da  mov     eax, r8d
0x1800369dd  mov     ecx, r8d
0x1800369e0  mov     edi, r8d
0x1800369e3  not     ecx
0x1800369e5  and     ecx, 1
0x1800369e8  mov     edx, ecx
0x1800369ea  or      edx, 2
0x1800369ed  and     al, 8
0x1800369ef  mov     eax, r8d
0x1800369f2  cmovnz  edx, ecx
0x1800369f5  mov     r14d, edx
0x1800369f8  or      r14d, 4
0x1800369fc  and     al, 4
0x1800369fe  cmovnz  r14d, edx
0x180036a02  shr     edi, 1
0x180036a04  not     edi
0x180036a06  and     edi, 1
0x180036a09  test    rbx, rbx
0x180036a0c  jnz     loc_180036AE9
0x180036a12  test    r8b, 20h
0x180036a16  jnz     short loc_180036A35
0x180036a18  mov     rcx, [rsi]
0x180036a1b  lea     r9d, [rbx+1]
0x180036a1f  mov     r8d, r14d
0x180036a22  mov     edx, edi
0x180036a24  call    ?GetConfigString_DontUse_@REGUTIL@@SAPEAGPEBGHW4CORConfigLevel@1@H@Z; REGUTIL::GetConfigString_DontUse_(ushort const *,int,REGUTIL::CORConfigLevel,int)
0x180036a29  mov     rbx, rax
0x180036a2c  test    rax, rax
0x180036a2f  jnz     loc_180036AE9
0x180036a35  mov     r8d, [rsi+8]
0x180036a39  test    r8b, 10h
0x180036a3d  jnz     loc_180036AC8
0x180036a43  mov     rax, cs:?s_GetConfigValueCallback@CLRConfig@@0P6AJPEBGPEAPEBGHH@ZEA; long (*CLRConfig::s_GetConfigValueCallback)(ushort const *,ushort const * *,int,int)
0x180036a4a  test    rax, rax
0x180036a4d  jz      short loc_180036AC8
0x180036a4f  mov     rcx, [rsi]
0x180036a52  lea     rdx, [rsp+280h+var_250]
0x180036a57  mov     r9d, r8d
0x180036a5a  shr     r8d, 6
0x180036a5e  shr     r9d, 7
0x180036a62  and     r8d, 1
0x180036a66  and     r9d, 1
0x180036a6a  call    cs:__guard_dispatch_icall_fptr
0x180036a70  test    eax, eax
0x180036a72  js      short loc_180036AC8
0x180036a74  mov     rcx, [rsp+280h+var_250]
0x180036a79  test    rcx, rcx
0x180036a7c  jz      short loc_180036AC8
0x180036a7e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180036a82  mov     rdi, r8
0x180036a85  inc     rdi
0x180036a88  cmp     [rcx+rdi*2], r12w
0x180036a8d  jnz     short loc_180036A85
0x180036a8f  inc     rdi
0x180036a92  mov     eax, 2
0x180036a97  mul     rdi
0x180036a9a  cmovo   rax, r8
0x180036a9e  mov     rcx, rax; dwBytes
0x180036aa1  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180036aa6  mov     rbx, rax
0x180036aa9  test    rax, rax
0x180036aac  jnz     short loc_180036AB5
0x180036aae  mov     eax, 8007000Eh
0x180036ab3  jmp     short loc_180036B22
0x180036ab5  mov     r8, [rsp+280h+var_250]; Source
0x180036aba  mov     rdx, rdi; SizeInWords
0x180036abd  mov     rcx, rax; Destination
0x180036ac0  call    cs:__imp_wcscpy_s
0x180036ac6  jmp     short loc_180036AE9
0x180036ac8  test    byte ptr [rsi+8], 20h
0x180036acc  jz      short loc_180036B1D
0x180036ace  mov     rcx, [rsi]
0x180036ad1  mov     r9d, 1
0x180036ad7  mov     r8d, r14d
0x180036ada  mov     edx, edi
0x180036adc  call    ?GetConfigString_DontUse_@REGUTIL@@SAPEAGPEBGHW4CORConfigLevel@1@H@Z; REGUTIL::GetConfigString_DontUse_(ushort const *,int,REGUTIL::CORConfigLevel,int)
0x180036ae1  mov     rbx, rax
0x180036ae4  test    rax, rax
0x180036ae7  jz      short loc_180036B1D
0x180036ae9  test    dword ptr [rsi+8], 100h
0x180036af0  jz      short loc_180036B1D
0x180036af2  lea     rdx, [rsp+280h+var_248]; unsigned __int16 **
0x180036af7  mov     [rsp+280h+var_248], r12
0x180036afc  mov     rcx, rbx; unsigned __int16 *
0x180036aff  call    ?TrimWhiteSpace@CLRConfig@@CAJPEBGPEAPEAG@Z; CLRConfig::TrimWhiteSpace(ushort const *,ushort * *)
0x180036b04  test    eax, eax
0x180036b06  js      short loc_180036B1D
0x180036b08  mov     rdi, [rsp+280h+var_248]
0x180036b0d  test    rdi, rdi
0x180036b10  jz      short loc_180036B1D
0x180036b12  mov     rcx, rbx; lpMem
0x180036b15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036b1a  mov     rbx, rdi
0x180036b1d  mov     [r15], rbx
0x180036b20  xor     eax, eax
0x180036b22  mov     rcx, [rbp+180h+var_30]
0x180036b29  xor     rcx, rsp; StackCookie
0x180036b2c  call    __security_check_cookie
0x180036b31  lea     r11, [rsp+280h+var_20]
0x180036b39  mov     rbx, [r11+40h]
0x180036b3d  mov     rsi, [r11+48h]
0x180036b41  mov     rsp, r11
0x180036b44  pop     r15
0x180036b46  pop     r14
0x180036b48  pop     r12
0x180036b4a  pop     rdi
0x180036b4b  pop     rbp
0x180036b4c  retn
```
