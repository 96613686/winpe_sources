# GetCodePageForFont

- ea: `0x180018ab8`
- end: `0x180018cac`
- name: `GetCodePageForFont`
- size: `500`
- prototype: `__int64 __fastcall(HANDLE h)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021dc4`
- `0x180038c54`
- `0x180040730`
- `0x180043fe4`
- `0x18004e980`
- `0x180058390`
- `0x18005fca4`
- `0x180065bf0`
- `0x18006a770`

## callees

- `0x1800115f0`
- `0x180018ab8`
- `0x18003a6b8`
- `0x18008ea60`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180018b87`
- `ADVAPI32!RegOpenKeyExW` at `0x180018b87`
- `ADVAPI32!RegQueryValueExW` at `0x180018bbe`
- `ADVAPI32!RegQueryValueExW` at `0x180018bbe`
- `ADVAPI32!RegCloseKey` at `0x180018bc9`
- `ADVAPI32!RegCloseKey` at `0x180018bc9`
- `GDI32!GetObjectW` at `0x180018b15`
- `GDI32!GetObjectW` at `0x180018b15`
- `GDI32!TranslateCharsetInfo` at `0x180018c7a`
- `GDI32!TranslateCharsetInfo` at `0x180018c7a`

## pseudocode

```c
__int64 __fastcall GetCodePageForFont(HANDLE h)
{
  __int64 v2; // rcx
  WCHAR *v3; // r8
  __int64 v4; // rdx
  BYTE *v5; // rax
  BYTE *v6; // rcx
  DWORD *v7; // rbx
  const WCHAR *v8; // rdx
  const WCHAR *v9; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pv[48]; // [rsp+40h] [rbp-C0h] BYREF
  tagCHARSETINFO v15; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Data[32]; // [rsp+C0h] [rbp-40h] BYREF

  memset(pv, 0, 0x5Cu);
  cbData = 0;
  Type = 0;
  memset(&v15, 0, sizeof(v15));
  hKey = 0;
  if ( !GetObjectW(h, 92, pv) )
    return 0;
  v2 = 2147483646;
  v3 = &pv[14];
  v4 = 32;
  v5 = (BYTE *)Data;
  do
  {
    if ( !v2 )
      break;
    if ( !*v3 )
      break;
    *(_WORD *)v5 = *v3++;
    v5 += 2;
    --v2;
    --v4;
  }
  while ( v4 );
  v6 = v5 - 2;
  if ( v4 )
    v6 = v5;
  *(_WORD *)v6 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\FontSubstitutes",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 64;
    RegQueryValueExW(hKey, &pv[14], 0, &Type, (LPBYTE)Data, &cbData);
    RegCloseKey(hKey);
  }
  v7 = (DWORD *)HIBYTE(pv[11]);
  if ( !HIBYTE(pv[11]) )
  {
    if ( !StrCmpICW(L"Helv", Data) || !StrCmpICW(L"Ms Sans Serif", Data) || !StrCmpICW(L"Ms Serif", Data) )
      return 0;
    v8 = Data;
    v9 = L"Tahoma";
LABEL_17:
    if ( !StrCmpICW(v9, v8) )
      return 0;
    goto LABEL_18;
  }
  if ( HIBYTE(pv[11]) == 0x80 )
  {
    v8 = &pv[14];
    v9 = &word_18009A478;
    goto LABEL_17;
  }
LABEL_18:
  if ( StrCmpICW(&word_18009A480, &pv[14]) && StrCmpICW(&word_18009A48C, &pv[14]) && TranslateCharsetInfo(v7, &v15, 1u) )
    return v15.ciACP;
  return 0;
}

```

## disassembly

```asm
0x180018ab8  mov     [rsp-8+arg_8], rbx
0x180018abd  mov     [rsp-8+arg_10], rsi
0x180018ac2  push    rbp
0x180018ac3  lea     rbp, [rsp-10h]
0x180018ac8  sub     rsp, 110h
0x180018acf  mov     rax, cs:__security_cookie
0x180018ad6  xor     rax, rsp
0x180018ad9  mov     [rbp+10h+var_10], rax
0x180018add  xor     edx, edx; Val
0x180018adf  mov     rbx, rcx
0x180018ae2  lea     rcx, [rsp+110h+pv]; void *
0x180018ae7  lea     r8d, [rdx+5Ch]; Size
0x180018aeb  call    memset
0x180018af0  xor     esi, esi
0x180018af2  lea     r8, [rsp+110h+pv]; pv
0x180018af7  xorps   xmm0, xmm0
0x180018afa  mov     [rsp+110h+cbData], esi
0x180018afe  mov     rcx, rbx; h
0x180018b01  mov     [rsp+110h+Type], esi
0x180018b05  movups  xmmword ptr [rbp+10h+var_70.ciCharset], xmm0
0x180018b09  lea     edx, [rsi+5Ch]; c
0x180018b0c  mov     [rsp+110h+hKey], rsi
0x180018b11  movups  xmmword ptr [rbp+10h+var_70.fs.fsUsb+8], xmm0
0x180018b15  call    cs:__imp_GetObjectW
0x180018b1b  test    eax, eax
0x180018b1d  jz      loc_180018C89
0x180018b23  mov     ecx, 7FFFFFFEh
0x180018b28  lea     r8, [rsp+110h+ValueName]
0x180018b2d  lea     edx, [rsi+20h]
0x180018b30  lea     rax, [rbp+10h+Data]
0x180018b34  test    rcx, rcx
0x180018b37  jz      short loc_180018B58
0x180018b39  movzx   r9d, word ptr [r8]
0x180018b3d  test    r9w, r9w
0x180018b41  jz      short loc_180018B58
0x180018b43  mov     [rax], r9w
0x180018b47  add     r8, 2
0x180018b4b  add     rax, 2
0x180018b4f  dec     rcx
0x180018b52  sub     rdx, 1
0x180018b56  jnz     short loc_180018B34
0x180018b58  test    rdx, rdx
0x180018b5b  lea     rcx, [rax-2]
0x180018b5f  mov     r9d, 20019h; samDesired
0x180018b65  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180018b6c  cmovnz  rcx, rax
0x180018b70  lea     rax, [rsp+110h+hKey]
0x180018b75  xor     r8d, r8d; ulOptions
0x180018b78  mov     [rsp+110h+phkResult], rax; phkResult
0x180018b7d  mov     [rcx], si
0x180018b80  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018b87  call    cs:__imp_RegOpenKeyExW
0x180018b8d  test    eax, eax
0x180018b8f  jnz     short loc_180018BCF
0x180018b91  mov     rcx, [rsp+110h+hKey]; hKey
0x180018b96  lea     rax, [rsp+110h+cbData]
0x180018b9b  mov     [rsp+110h+lpcbData], rax; lpcbData
0x180018ba0  lea     r9, [rsp+110h+Type]; lpType
0x180018ba5  lea     rax, [rbp+10h+Data]
0x180018ba9  mov     [rsp+110h+cbData], 40h ; '@'
0x180018bb1  xor     r8d, r8d; lpReserved
0x180018bb4  mov     [rsp+110h+phkResult], rax; lpData
0x180018bb9  lea     rdx, [rsp+110h+ValueName]; lpValueName
0x180018bbe  call    cs:__imp_RegQueryValueExW
0x180018bc4  mov     rcx, [rsp+110h+hKey]; hKey
0x180018bc9  call    cs:__imp_RegCloseKey
0x180018bcf  movzx   ebx, [rsp+110h+var_B9]
0x180018bd4  test    bl, bl
0x180018bd6  jnz     short loc_180018C29
0x180018bd8  lea     rdx, [rbp+10h+Data]; pszStr2
0x180018bdc  lea     rcx, pszStr1; "Helv"
0x180018be3  call    StrCmpICW
0x180018be8  test    eax, eax
0x180018bea  jz      loc_180018C89
0x180018bf0  lea     rdx, [rbp+10h+Data]; pszStr2
0x180018bf4  lea     rcx, aMsSansSerif; "Ms Sans Serif"
0x180018bfb  call    StrCmpICW
0x180018c00  test    eax, eax
0x180018c02  jz      loc_180018C89
0x180018c08  lea     rdx, [rbp+10h+Data]; pszStr2
0x180018c0c  lea     rcx, aMsSerif; "Ms Serif"
0x180018c13  call    StrCmpICW
0x180018c18  test    eax, eax
0x180018c1a  jz      short loc_180018C89
0x180018c1c  lea     rdx, [rbp+10h+Data]
0x180018c20  lea     rcx, aTahoma; "Tahoma"
0x180018c27  jmp     short loc_180018C3A
0x180018c29  cmp     bl, 80h
0x180018c2c  jnz     short loc_180018C43
0x180018c2e  lea     rdx, [rsp+110h+ValueName]; pszStr2
0x180018c33  lea     rcx, word_18009A478; pszStr1
0x180018c3a  call    StrCmpICW
0x180018c3f  test    eax, eax
0x180018c41  jz      short loc_180018C89
0x180018c43  lea     rdx, [rsp+110h+ValueName]; pszStr2
0x180018c48  lea     rcx, word_18009A480; pszStr1
0x180018c4f  call    StrCmpICW
0x180018c54  test    eax, eax
0x180018c56  jz      short loc_180018C89
0x180018c58  lea     rdx, [rsp+110h+ValueName]; pszStr2
0x180018c5d  lea     rcx, word_18009A48C; pszStr1
0x180018c64  call    StrCmpICW
0x180018c69  test    eax, eax
0x180018c6b  jz      short loc_180018C89
0x180018c6d  mov     rcx, rbx; lpSrc
0x180018c70  lea     rdx, [rbp+10h+var_70]; lpCs
0x180018c74  mov     r8d, 1; dwFlags
0x180018c7a  call    cs:__imp_TranslateCharsetInfo
0x180018c80  test    eax, eax
0x180018c82  jz      short loc_180018C89
0x180018c84  mov     eax, [rbp+10h+var_70.ciACP]
0x180018c87  jmp     short loc_180018C8B
0x180018c89  xor     eax, eax
0x180018c8b  mov     rcx, [rbp+10h+var_10]
0x180018c8f  xor     rcx, rsp; StackCookie
0x180018c92  call    __security_check_cookie
0x180018c97  lea     r11, [rsp+110h+var_s0]
0x180018c9f  mov     rbx, [r11+18h]
0x180018ca3  mov     rsi, [r11+20h]
0x180018ca7  mov     rsp, r11
0x180018caa  pop     rbp
0x180018cab  retn
```
