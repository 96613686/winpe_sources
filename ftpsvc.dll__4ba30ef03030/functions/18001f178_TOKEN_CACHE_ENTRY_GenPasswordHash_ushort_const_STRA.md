# TOKEN_CACHE_ENTRY::GenPasswordHash(ushort const *,STRA *)

- ea: `0x18001f178`
- end: `0x18001f38d`
- name: `?GenPasswordHash@TOKEN_CACHE_ENTRY@@QEAAJPEBGPEAVSTRA@@@Z`
- size: `533`
- prototype: `__int64 __fastcall(TOKEN_CACHE_ENTRY *this, const BYTE *, struct STRA *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001f04c`
- `0x18001f394`

## callees

- `0x18001f178`
- `0x18002020c`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001f200`
- `KERNEL32!GetLastError` at `0x18001f27d`
- `KERNEL32!GetLastError` at `0x18001f2d3`
- `KERNEL32!GetLastError` at `0x18001f319`
- `KERNEL32!GetLastError` at `0x18001f200`
- `KERNEL32!GetLastError` at `0x18001f27d`
- `KERNEL32!GetLastError` at `0x18001f2d3`
- `KERNEL32!GetLastError` at `0x18001f319`
- `ADVAPI32!CryptDestroyHash` at `0x18001f34a`
- `ADVAPI32!CryptDestroyHash` at `0x18001f34a`
- `ADVAPI32!CryptGetHashParam` at `0x18001f2c9`
- `ADVAPI32!CryptGetHashParam` at `0x18001f30f`
- `ADVAPI32!CryptGetHashParam` at `0x18001f2c9`
- `ADVAPI32!CryptGetHashParam` at `0x18001f30f`
- `ADVAPI32!CryptHashData` at `0x18001f273`
- `ADVAPI32!CryptHashData` at `0x18001f273`
- `ADVAPI32!CryptCreateHash` at `0x18001f1f6`
- `ADVAPI32!CryptCreateHash` at `0x18001f1f6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001f355`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001f363`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001f355`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001f363`
- `iisutil!PuDbgPrint` at `0x18001f24d`
- `iisutil!PuDbgPrint` at `0x18001f24d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001f2e9`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001f2e9`

## string_xrefs

- `0x18001f23f`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18001f222`: `CryptCreateHash() failed : hr = 0x%x\n`
- `0x18001f233`: `TOKEN_CACHE_ENTRY::GenPasswordHash`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TOKEN_CACHE_ENTRY::GenPasswordHash(TOKEN_CACHE_ENTRY *this, const BYTE *a2, struct STRA *a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r8
  signed int v10; // eax
  signed int v11; // eax
  __int64 pdwDataLen; // [rsp+30h] [rbp-29h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-19h] BYREF
  BYTE *pbData; // [rsp+60h] [rbp+7h]
  int v17; // [rsp+68h] [rbp+Fh]
  __int16 v18; // [rsp+6Ch] [rbp+13h]
  _OWORD v19[2]; // [rsp+70h] [rbp+17h] BYREF

  hHash = 0;
  LODWORD(pdwDataLen) = 0;
  memset(v19, 0, sizeof(v19));
  pbData = (BYTE *)v19;
  v17 = 32;
  v18 = 256;
  if ( !a2 || !a3 )
  {
    BUFFER::~BUFFER((BUFFER *)v15);
    return 2147942487LL;
  }
  if ( !CryptCreateHash(TOKEN_CACHE_ENTRY::sm_hCryptProv, 0x800Cu, 0, 0, &hHash) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_25;
    v7 = "CryptCreateHash() failed : hr = 0x%x\n";
    v8 = 499;
    goto LABEL_8;
  }
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)&a2[2 * v9] );
  if ( CryptHashData(hHash, a2, 2 * v9, 0) )
  {
    LODWORD(pdwDataLen) = v17;
    if ( !CryptGetHashParam(hHash, 2u, pbData, (DWORD *)&pdwDataLen, 0) )
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 != 234 )
        goto LABEL_22;
      if ( !BUFFER::Resize((BUFFER *)v15, pdwDataLen) )
      {
        v6 = -2147024882;
        goto LABEL_25;
      }
      if ( !CryptGetHashParam(hHash, 2u, pbData, (DWORD *)&pdwDataLen, 0) )
      {
        v11 = GetLastError();
        v6 = v11;
LABEL_22:
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        goto LABEL_25;
      }
    }
    v6 = ToHex(pbData, pdwDataLen, a3);
    goto LABEL_25;
  }
  v10 = GetLastError();
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( (g_dwDebugFlags & 3) == 0 )
    goto LABEL_25;
  v7 = "CryptHashData() failed : hr = 0x%x\n";
  v8 = 513;
LABEL_8:
  PuDbgPrint(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
    v8,
    "TOKEN_CACHE_ENTRY::GenPasswordHash",
    v7,
    v6,
    pdwDataLen);
LABEL_25:
  if ( hHash )
    CryptDestroyHash(hHash);
  BUFFER::~BUFFER((BUFFER *)v15);
  return v6;
}

```

## disassembly

```asm
0x18001f178  mov     [rsp-8+arg_0], rbx
0x18001f17d  push    rbp
0x18001f17e  push    rsi
0x18001f17f  push    rdi
0x18001f180  lea     rbp, [rsp-47h]
0x18001f185  sub     rsp, 0A0h
0x18001f18c  mov     rax, cs:__security_cookie
0x18001f193  xor     rax, rsp
0x18001f196  mov     [rbp+57h+var_20], rax
0x18001f19a  mov     rdi, r8
0x18001f19d  mov     rbx, rdx
0x18001f1a0  xor     esi, esi
0x18001f1a2  mov     [rbp+57h+hHash], rsi
0x18001f1a6  mov     dword ptr [rbp+57h+pdwDataLen], esi
0x18001f1a9  xorps   xmm0, xmm0
0x18001f1ac  movups  [rbp+57h+var_40], xmm0
0x18001f1b0  movups  [rbp+57h+var_30], xmm0
0x18001f1b4  lea     rax, [rbp+57h+var_40]
0x18001f1b8  mov     [rbp+57h+pbData], rax
0x18001f1bc  mov     [rbp+57h+var_48], 20h ; ' '
0x18001f1c3  mov     [rbp+57h+var_44], 100h
0x18001f1c9  test    rdx, rdx
0x18001f1cc  jz      loc_18001F35F
0x18001f1d2  test    r8, r8
0x18001f1d5  jz      loc_18001F35F
0x18001f1db  lea     rax, [rbp+57h+hHash]
0x18001f1df  mov     [rsp+0B0h+phHash], rax; phHash
0x18001f1e4  xor     r9d, r9d; dwFlags
0x18001f1e7  xor     r8d, r8d; hKey
0x18001f1ea  mov     edx, 800Ch; Algid
0x18001f1ef  mov     rcx, cs:?sm_hCryptProv@TOKEN_CACHE_ENTRY@@0_KA; hProv
0x18001f1f6  call    cs:__imp_CryptCreateHash
0x18001f1fc  test    eax, eax
0x18001f1fe  jnz     short loc_18001F258
0x18001f200  call    cs:__imp_GetLastError
0x18001f206  mov     ebx, eax
0x18001f208  test    eax, eax
0x18001f20a  jle     short loc_18001F215
0x18001f20c  movzx   ebx, ax
0x18001f20f  or      ebx, 80070000h
0x18001f215  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f21c  jz      loc_18001F341
0x18001f222  lea     rax, aCryptcreatehas; "CryptCreateHash() failed : hr = 0x%x\n"
0x18001f229  mov     r8d, 1F3h
0x18001f22f  mov     [rsp+0B0h+var_88], ebx
0x18001f233  lea     r9, aTokenCacheEntr_3; "TOKEN_CACHE_ENTRY::GenPasswordHash"
0x18001f23a  mov     [rsp+0B0h+phHash], rax
0x18001f23f  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001f246  mov     rcx, cs:g_pDebug
0x18001f24d  call    cs:__imp_PuDbgPrint
0x18001f253  jmp     loc_18001F341
0x18001f258  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f25c  inc     r8
0x18001f25f  cmp     [rbx+r8*2], si
0x18001f264  jnz     short loc_18001F25C
0x18001f266  add     r8d, r8d; dwDataLen
0x18001f269  xor     r9d, r9d; dwFlags
0x18001f26c  mov     rdx, rbx; pbData
0x18001f26f  mov     rcx, [rbp+57h+hHash]; hHash
0x18001f273  call    cs:__imp_CryptHashData
0x18001f279  test    eax, eax
0x18001f27b  jnz     short loc_18001F2AE
0x18001f27d  call    cs:__imp_GetLastError
0x18001f283  mov     ebx, eax
0x18001f285  test    eax, eax
0x18001f287  jle     short loc_18001F292
0x18001f289  movzx   ebx, ax
0x18001f28c  or      ebx, 80070000h
0x18001f292  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f299  jz      loc_18001F341
0x18001f29f  lea     rax, aCrypthashdataF_0; "CryptHashData() failed : hr = 0x%x\n"
0x18001f2a6  mov     r8d, 201h
0x18001f2ac  jmp     short loc_18001F22F
0x18001f2ae  mov     eax, [rbp+57h+var_48]
0x18001f2b1  mov     dword ptr [rbp+57h+pdwDataLen], eax
0x18001f2b4  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x18001f2b8  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18001f2bc  mov     r8, [rbp+57h+pbData]; pbData
0x18001f2c0  mov     edx, 2; dwParam
0x18001f2c5  mov     rcx, [rbp+57h+hHash]; hHash
0x18001f2c9  call    cs:__imp_CryptGetHashParam
0x18001f2cf  test    eax, eax
0x18001f2d1  jnz     short loc_18001F330
0x18001f2d3  call    cs:__imp_GetLastError
0x18001f2d9  mov     ebx, eax
0x18001f2db  cmp     eax, 0EAh
0x18001f2e0  jnz     short loc_18001F321
0x18001f2e2  mov     edx, dword ptr [rbp+57h+pdwDataLen]
0x18001f2e5  lea     rcx, [rbp+57h+var_70]
0x18001f2e9  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001f2ef  test    al, al
0x18001f2f1  jnz     short loc_18001F2FA
0x18001f2f3  mov     ebx, 8007000Eh
0x18001f2f8  jmp     short loc_18001F341
0x18001f2fa  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x18001f2fe  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18001f302  mov     r8, [rbp+57h+pbData]; pbData
0x18001f306  mov     edx, 2; dwParam
0x18001f30b  mov     rcx, [rbp+57h+hHash]; hHash
0x18001f30f  call    cs:__imp_CryptGetHashParam
0x18001f315  test    eax, eax
0x18001f317  jnz     short loc_18001F330
0x18001f319  call    cs:__imp_GetLastError
0x18001f31f  mov     ebx, eax
0x18001f321  test    eax, eax
0x18001f323  jle     short loc_18001F341
0x18001f325  movzx   ebx, ax
0x18001f328  or      ebx, 80070000h
0x18001f32e  jmp     short loc_18001F341
0x18001f330  mov     r8, rdi; struct STRA *
0x18001f333  mov     edx, dword ptr [rbp+57h+pdwDataLen]; unsigned int
0x18001f336  mov     rcx, [rbp+57h+pbData]; unsigned __int8 *
0x18001f33a  call    ?ToHex@@YAJPEAEKAEAVSTRA@@@Z; ToHex(uchar *,ulong,STRA &)
0x18001f33f  mov     ebx, eax
0x18001f341  mov     rcx, [rbp+57h+hHash]; hHash
0x18001f345  test    rcx, rcx
0x18001f348  jz      short loc_18001F351
0x18001f34a  call    cs:__imp_CryptDestroyHash
0x18001f350  nop
0x18001f351  lea     rcx, [rbp+57h+var_70]
0x18001f355  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001f35b  mov     eax, ebx
0x18001f35d  jmp     short loc_18001F36E
0x18001f35f  lea     rcx, [rbp+57h+var_70]
0x18001f363  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001f369  mov     eax, 80070057h
0x18001f36e  mov     rcx, [rbp+57h+var_20]
0x18001f372  xor     rcx, rsp; StackCookie
0x18001f375  call    __security_check_cookie
0x18001f37a  mov     rbx, [rsp+0B0h+arg_0]
0x18001f382  add     rsp, 0A0h
0x18001f389  pop     rdi
0x18001f38a  pop     rsi
0x18001f38b  pop     rbp
0x18001f38c  retn
```
