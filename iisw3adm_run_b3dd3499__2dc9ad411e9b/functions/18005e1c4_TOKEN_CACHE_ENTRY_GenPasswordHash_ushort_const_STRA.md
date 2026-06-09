# TOKEN_CACHE_ENTRY::GenPasswordHash(ushort const *,STRA *)

- ea: `0x18005e1c4`
- end: `0x18005e460`
- name: `?GenPasswordHash@TOKEN_CACHE_ENTRY@@QEAAJPEBGPEAVSTRA@@@Z`
- size: `668`
- prototype: `int(TOKEN_CACHE_ENTRY *__hidden this, const unsigned __int16 *, struct STRA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005e468`

## callees

- `0x18005e1c4`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e2cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e36f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e2cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e36f`
- `iisutil!PuDbgPrint` at `0x18005e29f`
- `iisutil!PuDbgPrint` at `0x18005e29f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18005e424`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18005e432`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18005e424`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18005e432`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18005e33e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18005e33e`
- `iisutil!?Resize@STRA@@QEAAJK@Z` at `0x18005e39e`
- `iisutil!?Resize@STRA@@QEAAJK@Z` at `0x18005e39e`
- `CRYPTSP!CryptGetHashParam` at `0x18005e31e`
- `CRYPTSP!CryptGetHashParam` at `0x18005e365`
- `CRYPTSP!CryptGetHashParam` at `0x18005e31e`
- `CRYPTSP!CryptGetHashParam` at `0x18005e365`
- `CRYPTSP!CryptHashData` at `0x18005e2c5`
- `CRYPTSP!CryptHashData` at `0x18005e2c5`
- `CRYPTSP!CryptCreateHash` at `0x18005e248`
- `CRYPTSP!CryptCreateHash` at `0x18005e248`
- `CRYPTSP!CryptDestroyHash` at `0x18005e419`
- `CRYPTSP!CryptDestroyHash` at `0x18005e419`

## string_xrefs

- `0x18005e291`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18005e274`: `CryptCreateHash() failed : hr = 0x%x\n`
- `0x18005e285`: `TOKEN_CACHE_ENTRY::GenPasswordHash`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TOKEN_CACHE_ENTRY::GenPasswordHash(TOKEN_CACHE_ENTRY *this, const BYTE *a2, struct STRA *a3)
{
  signed int LastError; // eax
  signed int v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r8
  signed int v10; // eax
  signed int v11; // eax
  unsigned int v12; // esi
  BYTE *v13; // r14
  __int64 v14; // r11
  unsigned int v15; // r9d
  unsigned int i; // r10d
  unsigned int v17; // eax
  __int64 v18; // r9
  unsigned int v19; // ecx
  __int64 pdwDataLen; // [rsp+30h] [rbp-39h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v23[32]; // [rsp+40h] [rbp-29h] BYREF
  BYTE *pbData; // [rsp+60h] [rbp-9h]
  int v25; // [rsp+68h] [rbp-1h]
  __int16 v26; // [rsp+6Ch] [rbp+3h]
  _OWORD v27[2]; // [rsp+70h] [rbp+7h] BYREF

  hHash = 0;
  LODWORD(pdwDataLen) = 0;
  memset(v27, 0, sizeof(v27));
  pbData = (BYTE *)v27;
  v25 = 32;
  v26 = 256;
  if ( !a2 || !a3 )
  {
    BUFFER::~BUFFER((BUFFER *)v23);
    return 2147942487LL;
  }
  if ( !CryptCreateHash(TOKEN_CACHE_ENTRY::sm_hCryptProv, 0x800Cu, 0, 0, &hHash) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_29;
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
    LODWORD(pdwDataLen) = v25;
    if ( !CryptGetHashParam(hHash, 2u, pbData, (DWORD *)&pdwDataLen, 0) )
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 != 234 )
        goto LABEL_22;
      if ( !BUFFER::Resize((BUFFER *)v23, pdwDataLen) )
      {
        v6 = -2147024882;
        goto LABEL_29;
      }
      if ( !CryptGetHashParam(hHash, 2u, pbData, (DWORD *)&pdwDataLen, 0) )
      {
        v11 = GetLastError();
        v6 = v11;
LABEL_22:
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        goto LABEL_29;
      }
    }
    v12 = pdwDataLen;
    v13 = pbData;
    v6 = STRA::Resize(a3, 2 * pdwDataLen + 1);
    if ( v6 >= 0 )
    {
      v14 = *((_QWORD *)a3 + 4);
      v15 = 0;
      for ( i = 0; i < v12; ++i )
      {
        v17 = v13[i] >> 4;
        *(_BYTE *)(v15 + v14) = v17 + 87 + (v17 < 0xA ? 0xD9 : 0);
        v18 = v15 + 1;
        v19 = v13[i] & 0xF;
        *(_BYTE *)(v18 + v14) = v19 + (v19 < 0xA ? 48 : 87);
        v15 = v18 + 1;
      }
      if ( v15 < *((_DWORD *)a3 + 10) )
      {
        *(_BYTE *)(v15 + *((_QWORD *)a3 + 4)) = 0;
        *((_DWORD *)a3 + 12) = v15;
      }
    }
    goto LABEL_29;
  }
  v10 = GetLastError();
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( (g_dwDebugFlags & 3) == 0 )
    goto LABEL_29;
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
LABEL_29:
  if ( hHash )
    CryptDestroyHash(hHash);
  BUFFER::~BUFFER((BUFFER *)v23);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005e1c4  mov     [rsp-8+arg_0], rbx
0x18005e1c9  push    rbp
0x18005e1ca  push    rsi
0x18005e1cb  push    rdi
0x18005e1cc  push    r14
0x18005e1ce  push    r15
0x18005e1d0  lea     rbp, [rsp-37h]
0x18005e1d5  sub     rsp, 0A0h
0x18005e1dc  mov     rax, cs:__security_cookie
0x18005e1e3  xor     rax, rsp
0x18005e1e6  mov     [rbp+57h+var_30], rax
0x18005e1ea  mov     rdi, r8
0x18005e1ed  mov     rbx, rdx
0x18005e1f0  xor     r15d, r15d
0x18005e1f3  mov     [rbp+57h+hHash], r15
0x18005e1f7  mov     dword ptr [rbp+57h+pdwDataLen], r15d
0x18005e1fb  xorps   xmm0, xmm0
0x18005e1fe  movups  [rbp+57h+var_50], xmm0
0x18005e202  movups  [rbp+57h+var_40], xmm0
0x18005e206  lea     rax, [rbp+57h+var_50]
0x18005e20a  mov     [rbp+57h+pbData], rax
0x18005e20e  mov     [rbp+57h+var_58], 20h ; ' '
0x18005e215  mov     [rbp+57h+var_54], 100h
0x18005e21b  test    rdx, rdx
0x18005e21e  jz      loc_18005E42E
0x18005e224  test    r8, r8
0x18005e227  jz      loc_18005E42E
0x18005e22d  lea     rax, [rbp+57h+hHash]
0x18005e231  mov     [rsp+0C0h+phHash], rax; phHash
0x18005e236  xor     r9d, r9d; dwFlags
0x18005e239  xor     r8d, r8d; hKey
0x18005e23c  mov     edx, 800Ch; Algid
0x18005e241  mov     rcx, cs:?sm_hCryptProv@TOKEN_CACHE_ENTRY@@0_KA; hProv
0x18005e248  call    cs:__imp_CryptCreateHash
0x18005e24e  test    eax, eax
0x18005e250  jnz     short loc_18005E2AA
0x18005e252  call    cs:__imp_GetLastError
0x18005e258  mov     ebx, eax
0x18005e25a  test    eax, eax
0x18005e25c  jle     short loc_18005E267
0x18005e25e  movzx   ebx, ax
0x18005e261  or      ebx, 80070000h
0x18005e267  test    byte ptr cs:g_dwDebugFlags, 3
0x18005e26e  jz      loc_18005E410
0x18005e274  lea     rax, aCryptcreatehas_0; "CryptCreateHash() failed : hr = 0x%x\n"
0x18005e27b  mov     r8d, 1F3h
0x18005e281  mov     [rsp+0C0h+var_98], ebx
0x18005e285  lea     r9, aTokenCacheEntr_3; "TOKEN_CACHE_ENTRY::GenPasswordHash"
0x18005e28c  mov     [rsp+0C0h+phHash], rax
0x18005e291  lea     rdx, aServercommonIn_45; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18005e298  mov     rcx, cs:g_pDebug
0x18005e29f  call    cs:__imp_PuDbgPrint
0x18005e2a5  jmp     loc_18005E410
0x18005e2aa  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005e2ae  inc     r8
0x18005e2b1  cmp     [rbx+r8*2], r15w
0x18005e2b6  jnz     short loc_18005E2AE
0x18005e2b8  add     r8d, r8d; dwDataLen
0x18005e2bb  xor     r9d, r9d; dwFlags
0x18005e2be  mov     rdx, rbx; pbData
0x18005e2c1  mov     rcx, [rbp+57h+hHash]; hHash
0x18005e2c5  call    cs:__imp_CryptHashData
0x18005e2cb  test    eax, eax
0x18005e2cd  jnz     short loc_18005E300
0x18005e2cf  call    cs:__imp_GetLastError
0x18005e2d5  mov     ebx, eax
0x18005e2d7  test    eax, eax
0x18005e2d9  jle     short loc_18005E2E4
0x18005e2db  movzx   ebx, ax
0x18005e2de  or      ebx, 80070000h
0x18005e2e4  test    byte ptr cs:g_dwDebugFlags, 3
0x18005e2eb  jz      loc_18005E410
0x18005e2f1  lea     rax, aCrypthashdataF; "CryptHashData() failed : hr = 0x%x\n"
0x18005e2f8  mov     r8d, 201h
0x18005e2fe  jmp     short loc_18005E281
0x18005e300  mov     eax, [rbp+57h+var_58]
0x18005e303  mov     dword ptr [rbp+57h+pdwDataLen], eax
0x18005e306  mov     dword ptr [rsp+0C0h+phHash], r15d; dwFlags
0x18005e30b  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18005e30f  mov     r8, [rbp+57h+pbData]; pbData
0x18005e313  mov     esi, 2
0x18005e318  mov     edx, esi; dwParam
0x18005e31a  mov     rcx, [rbp+57h+hHash]; hHash
0x18005e31e  call    cs:__imp_CryptGetHashParam
0x18005e324  test    eax, eax
0x18005e326  jnz     short loc_18005E38D
0x18005e328  call    cs:__imp_GetLastError
0x18005e32e  mov     ebx, eax
0x18005e330  cmp     eax, 0EAh
0x18005e335  jnz     short loc_18005E377
0x18005e337  mov     edx, dword ptr [rbp+57h+pdwDataLen]
0x18005e33a  lea     rcx, [rbp+57h+var_80]
0x18005e33e  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18005e344  test    al, al
0x18005e346  jnz     short loc_18005E352
0x18005e348  mov     ebx, 8007000Eh
0x18005e34d  jmp     loc_18005E410
0x18005e352  mov     dword ptr [rsp+0C0h+phHash], r15d; dwFlags
0x18005e357  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18005e35b  mov     r8, [rbp+57h+pbData]; pbData
0x18005e35f  mov     edx, esi; dwParam
0x18005e361  mov     rcx, [rbp+57h+hHash]; hHash
0x18005e365  call    cs:__imp_CryptGetHashParam
0x18005e36b  test    eax, eax
0x18005e36d  jnz     short loc_18005E38D
0x18005e36f  call    cs:__imp_GetLastError
0x18005e375  mov     ebx, eax
0x18005e377  test    eax, eax
0x18005e379  jle     loc_18005E410
0x18005e37f  movzx   ebx, ax
0x18005e382  or      ebx, 80070000h
0x18005e388  jmp     loc_18005E410
0x18005e38d  mov     esi, dword ptr [rbp+57h+pdwDataLen]
0x18005e390  mov     r14, [rbp+57h+pbData]
0x18005e394  lea     edx, ds:1[rsi*2]
0x18005e39b  mov     rcx, rdi
0x18005e39e  call    cs:__imp_?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x18005e3a4  mov     ebx, eax
0x18005e3a6  test    eax, eax
0x18005e3a8  js      short loc_18005E410
0x18005e3aa  mov     r11, [rdi+20h]
0x18005e3ae  mov     r9d, r15d
0x18005e3b1  mov     r10d, r15d
0x18005e3b4  test    esi, esi
0x18005e3b6  jz      short loc_18005E3FB
0x18005e3b8  mov     r8d, r10d
0x18005e3bb  movzx   eax, byte ptr [r8+r14]
0x18005e3c0  shr     eax, 4
0x18005e3c3  cmp     eax, 0Ah
0x18005e3c6  sbb     cl, cl
0x18005e3c8  and     cl, 0D9h
0x18005e3cb  add     al, 57h ; 'W'
0x18005e3cd  add     cl, al
0x18005e3cf  mov     eax, r9d
0x18005e3d2  mov     [rax+r11], cl
0x18005e3d6  inc     r9d
0x18005e3d9  movzx   ecx, byte ptr [r8+r14]
0x18005e3de  and     ecx, 0Fh
0x18005e3e1  cmp     ecx, 0Ah
0x18005e3e4  sbb     al, al
0x18005e3e6  and     al, 0D9h
0x18005e3e8  add     al, 57h ; 'W'
0x18005e3ea  add     al, cl
0x18005e3ec  mov     [r9+r11], al
0x18005e3f0  inc     r9d
0x18005e3f3  inc     r10d
0x18005e3f6  cmp     r10d, esi
0x18005e3f9  jb      short loc_18005E3B8
0x18005e3fb  cmp     r9d, [rdi+28h]
0x18005e3ff  jnb     short loc_18005E410
0x18005e401  mov     ecx, r9d
0x18005e404  mov     rax, [rdi+20h]
0x18005e408  mov     [rcx+rax], r15b
0x18005e40c  mov     [rdi+30h], r9d
0x18005e410  mov     rcx, [rbp+57h+hHash]; hHash
0x18005e414  test    rcx, rcx
0x18005e417  jz      short loc_18005E420
0x18005e419  call    cs:__imp_CryptDestroyHash
0x18005e41f  nop
0x18005e420  lea     rcx, [rbp+57h+var_80]
0x18005e424  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18005e42a  mov     eax, ebx
0x18005e42c  jmp     short loc_18005E43D
0x18005e42e  lea     rcx, [rbp+57h+var_80]
0x18005e432  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18005e438  mov     eax, 80070057h
0x18005e43d  mov     rcx, [rbp+57h+var_30]
0x18005e441  xor     rcx, rsp; StackCookie
0x18005e444  call    __security_check_cookie
0x18005e449  mov     rbx, [rsp+0C0h+arg_0]
0x18005e451  add     rsp, 0A0h
0x18005e458  pop     r15
0x18005e45a  pop     r14
0x18005e45c  pop     rdi
0x18005e45d  pop     rsi
0x18005e45e  pop     rbp
0x18005e45f  retn
```
