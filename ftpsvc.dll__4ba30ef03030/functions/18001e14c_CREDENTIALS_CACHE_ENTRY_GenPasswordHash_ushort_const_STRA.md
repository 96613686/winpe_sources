# CREDENTIALS_CACHE_ENTRY::GenPasswordHash(ushort const *,STRA *)

- ea: `0x18001e14c`
- end: `0x18001e362`
- name: `?GenPasswordHash@CREDENTIALS_CACHE_ENTRY@@QEAAJPEBGPEAVSTRA@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(CREDENTIALS_CACHE_ENTRY *this, const BYTE *, struct STRA *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e368`
- `0x18001e7e4`

## callees

- `0x18001e14c`
- `0x18002020c`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e1d4`
- `KERNEL32!GetLastError` at `0x18001e251`
- `KERNEL32!GetLastError` at `0x18001e2a8`
- `KERNEL32!GetLastError` at `0x18001e2ee`
- `KERNEL32!GetLastError` at `0x18001e1d4`
- `KERNEL32!GetLastError` at `0x18001e251`
- `KERNEL32!GetLastError` at `0x18001e2a8`
- `KERNEL32!GetLastError` at `0x18001e2ee`
- `ADVAPI32!CryptDestroyHash` at `0x18001e31f`
- `ADVAPI32!CryptDestroyHash` at `0x18001e31f`
- `ADVAPI32!CryptGetHashParam` at `0x18001e29e`
- `ADVAPI32!CryptGetHashParam` at `0x18001e2e4`
- `ADVAPI32!CryptGetHashParam` at `0x18001e29e`
- `ADVAPI32!CryptGetHashParam` at `0x18001e2e4`
- `ADVAPI32!CryptHashData` at `0x18001e247`
- `ADVAPI32!CryptHashData` at `0x18001e247`
- `ADVAPI32!CryptCreateHash` at `0x18001e1ca`
- `ADVAPI32!CryptCreateHash` at `0x18001e1ca`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001e32a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001e338`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001e32a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001e338`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001e2be`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001e2be`
- `iisutil!PuDbgPrintError` at `0x18001e221`
- `iisutil!PuDbgPrintError` at `0x18001e221`

## string_xrefs

- `0x18001e213`: `inetsrv\iis\iisrearc\ftp\server\core\credentials_cache.cxx`
- `0x18001e1f6`: `CryptCreateHash() failed\n`
- `0x18001e208`: `CREDENTIALS_CACHE_ENTRY::GenPasswordHash`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CREDENTIALS_CACHE_ENTRY::GenPasswordHash(
        CREDENTIALS_CACHE_ENTRY *this,
        const BYTE *a2,
        struct STRA *a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  __int64 v7; // r8
  signed int v8; // eax
  signed int v9; // eax
  __int64 pdwDataLen; // [rsp+30h] [rbp-29h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v13[32]; // [rsp+40h] [rbp-19h] BYREF
  BYTE *pbData; // [rsp+60h] [rbp+7h]
  int v15; // [rsp+68h] [rbp+Fh]
  __int16 v16; // [rsp+6Ch] [rbp+13h]
  _OWORD v17[2]; // [rsp+70h] [rbp+17h] BYREF

  hHash = 0;
  LODWORD(pdwDataLen) = 0;
  memset(v17, 0, sizeof(v17));
  pbData = (BYTE *)v17;
  v15 = 32;
  v16 = 256;
  if ( !a2 || !a3 )
  {
    BUFFER::~BUFFER((BUFFER *)v13);
    return 2147942487LL;
  }
  if ( !CryptCreateHash(CREDENTIALS_CACHE_ENTRY::sm_hCryptProv, 0x800Cu, 0, 0, &hHash) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\credentials_cache.cxx",
        260,
        "CREDENTIALS_CACHE_ENTRY::GenPasswordHash",
        v6,
        "CryptCreateHash() failed\n",
        pdwDataLen);
    goto LABEL_25;
  }
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&a2[2 * v7] );
  if ( !CryptHashData(hHash, a2, 2 * v7, 0) )
  {
    v8 = GetLastError();
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\credentials_cache.cxx",
        274,
        "CREDENTIALS_CACHE_ENTRY::GenPasswordHash",
        v6,
        "CryptHashData() failed\n",
        pdwDataLen);
    goto LABEL_25;
  }
  LODWORD(pdwDataLen) = 32;
  if ( CryptGetHashParam(hHash, 2u, pbData, (DWORD *)&pdwDataLen, 0) )
    goto LABEL_24;
  v9 = GetLastError();
  v6 = v9;
  if ( v9 != 234 )
    goto LABEL_22;
  if ( BUFFER::Resize((BUFFER *)v13, pdwDataLen) )
  {
    if ( !CryptGetHashParam(hHash, 2u, pbData, (DWORD *)&pdwDataLen, 0) )
    {
      v9 = GetLastError();
      v6 = v9;
LABEL_22:
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      goto LABEL_25;
    }
LABEL_24:
    v6 = ToHex(pbData, pdwDataLen, a3);
    goto LABEL_25;
  }
  v6 = -2147024882;
LABEL_25:
  if ( hHash )
    CryptDestroyHash(hHash);
  BUFFER::~BUFFER((BUFFER *)v13);
  return v6;
}

```

## disassembly

```asm
0x18001e14c  mov     [rsp-8+arg_0], rbx
0x18001e151  push    rbp
0x18001e152  push    rsi
0x18001e153  push    rdi
0x18001e154  lea     rbp, [rsp-47h]
0x18001e159  sub     rsp, 0A0h
0x18001e160  mov     rax, cs:__security_cookie
0x18001e167  xor     rax, rsp
0x18001e16a  mov     [rbp+57h+var_20], rax
0x18001e16e  mov     rdi, r8
0x18001e171  mov     rbx, rdx
0x18001e174  xor     esi, esi
0x18001e176  mov     [rbp+57h+hHash], rsi
0x18001e17a  mov     dword ptr [rbp+57h+pdwDataLen], esi
0x18001e17d  xorps   xmm0, xmm0
0x18001e180  movups  [rbp+57h+var_40], xmm0
0x18001e184  movups  [rbp+57h+var_30], xmm0
0x18001e188  lea     rax, [rbp+57h+var_40]
0x18001e18c  mov     [rbp+57h+pbData], rax
0x18001e190  mov     [rbp+57h+var_48], 20h ; ' '
0x18001e197  mov     [rbp+57h+var_44], 100h
0x18001e19d  test    rdx, rdx
0x18001e1a0  jz      loc_18001E334
0x18001e1a6  test    r8, r8
0x18001e1a9  jz      loc_18001E334
0x18001e1af  lea     rax, [rbp+57h+hHash]
0x18001e1b3  mov     [rsp+0B0h+phHash], rax; phHash
0x18001e1b8  xor     r9d, r9d; dwFlags
0x18001e1bb  xor     r8d, r8d; hKey
0x18001e1be  mov     edx, 800Ch; Algid
0x18001e1c3  mov     rcx, cs:?sm_hCryptProv@CREDENTIALS_CACHE_ENTRY@@0_KA; hProv
0x18001e1ca  call    cs:__imp_CryptCreateHash
0x18001e1d0  test    eax, eax
0x18001e1d2  jnz     short loc_18001E22C
0x18001e1d4  call    cs:__imp_GetLastError
0x18001e1da  mov     ebx, eax
0x18001e1dc  test    eax, eax
0x18001e1de  jle     short loc_18001E1E9
0x18001e1e0  movzx   ebx, ax
0x18001e1e3  or      ebx, 80070000h
0x18001e1e9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001e1f0  jz      loc_18001E316
0x18001e1f6  lea     rax, aCryptcreatehas_0; "CryptCreateHash() failed\n"
0x18001e1fd  mov     r8d, 104h
0x18001e203  mov     [rsp+0B0h+var_88], rax
0x18001e208  lea     r9, aCredentialsCac; "CREDENTIALS_CACHE_ENTRY::GenPasswordHas"...
0x18001e20f  mov     dword ptr [rsp+0B0h+phHash], ebx
0x18001e213  lea     rdx, aInetsrvIisIisr_21; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001e21a  mov     rcx, cs:g_pDebug
0x18001e221  call    cs:__imp_PuDbgPrintError
0x18001e227  jmp     loc_18001E316
0x18001e22c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e230  inc     r8
0x18001e233  cmp     [rbx+r8*2], si
0x18001e238  jnz     short loc_18001E230
0x18001e23a  add     r8d, r8d; dwDataLen
0x18001e23d  xor     r9d, r9d; dwFlags
0x18001e240  mov     rdx, rbx; pbData
0x18001e243  mov     rcx, [rbp+57h+hHash]; hHash
0x18001e247  call    cs:__imp_CryptHashData
0x18001e24d  test    eax, eax
0x18001e24f  jnz     short loc_18001E282
0x18001e251  call    cs:__imp_GetLastError
0x18001e257  mov     ebx, eax
0x18001e259  test    eax, eax
0x18001e25b  jle     short loc_18001E266
0x18001e25d  movzx   ebx, ax
0x18001e260  or      ebx, 80070000h
0x18001e266  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001e26d  jz      loc_18001E316
0x18001e273  lea     rax, aCrypthashdataF; "CryptHashData() failed\n"
0x18001e27a  mov     r8d, 112h
0x18001e280  jmp     short loc_18001E203
0x18001e282  mov     dword ptr [rbp+57h+pdwDataLen], 20h ; ' '
0x18001e289  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x18001e28d  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18001e291  mov     r8, [rbp+57h+pbData]; pbData
0x18001e295  mov     edx, 2; dwParam
0x18001e29a  mov     rcx, [rbp+57h+hHash]; hHash
0x18001e29e  call    cs:__imp_CryptGetHashParam
0x18001e2a4  test    eax, eax
0x18001e2a6  jnz     short loc_18001E305
0x18001e2a8  call    cs:__imp_GetLastError
0x18001e2ae  mov     ebx, eax
0x18001e2b0  cmp     eax, 0EAh
0x18001e2b5  jnz     short loc_18001E2F6
0x18001e2b7  mov     edx, dword ptr [rbp+57h+pdwDataLen]
0x18001e2ba  lea     rcx, [rbp+57h+var_70]
0x18001e2be  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001e2c4  test    al, al
0x18001e2c6  jnz     short loc_18001E2CF
0x18001e2c8  mov     ebx, 8007000Eh
0x18001e2cd  jmp     short loc_18001E316
0x18001e2cf  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x18001e2d3  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18001e2d7  mov     r8, [rbp+57h+pbData]; pbData
0x18001e2db  mov     edx, 2; dwParam
0x18001e2e0  mov     rcx, [rbp+57h+hHash]; hHash
0x18001e2e4  call    cs:__imp_CryptGetHashParam
0x18001e2ea  test    eax, eax
0x18001e2ec  jnz     short loc_18001E305
0x18001e2ee  call    cs:__imp_GetLastError
0x18001e2f4  mov     ebx, eax
0x18001e2f6  test    eax, eax
0x18001e2f8  jle     short loc_18001E316
0x18001e2fa  movzx   ebx, ax
0x18001e2fd  or      ebx, 80070000h
0x18001e303  jmp     short loc_18001E316
0x18001e305  mov     r8, rdi; struct STRA *
0x18001e308  mov     edx, dword ptr [rbp+57h+pdwDataLen]; unsigned int
0x18001e30b  mov     rcx, [rbp+57h+pbData]; unsigned __int8 *
0x18001e30f  call    ?ToHex@@YAJPEAEKAEAVSTRA@@@Z; ToHex(uchar *,ulong,STRA &)
0x18001e314  mov     ebx, eax
0x18001e316  mov     rcx, [rbp+57h+hHash]; hHash
0x18001e31a  test    rcx, rcx
0x18001e31d  jz      short loc_18001E326
0x18001e31f  call    cs:__imp_CryptDestroyHash
0x18001e325  nop
0x18001e326  lea     rcx, [rbp+57h+var_70]
0x18001e32a  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001e330  mov     eax, ebx
0x18001e332  jmp     short loc_18001E343
0x18001e334  lea     rcx, [rbp+57h+var_70]
0x18001e338  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001e33e  mov     eax, 80070057h
0x18001e343  mov     rcx, [rbp+57h+var_20]
0x18001e347  xor     rcx, rsp; StackCookie
0x18001e34a  call    __security_check_cookie
0x18001e34f  mov     rbx, [rsp+0B0h+arg_0]
0x18001e357  add     rsp, 0A0h
0x18001e35e  pop     rdi
0x18001e35f  pop     rsi
0x18001e360  pop     rbp
0x18001e361  retn
```
