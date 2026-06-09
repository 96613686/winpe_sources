# TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)

- ea: `0x180032180`
- end: `0x1800323af`
- name: `?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(TOKEN_KEY *this, const BYTE *, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180031dd4`

## callees

- `0x180032180`
- `0x180032ea4`
- `0x1800343f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032331`
- `CRYPTSP!CryptDestroyHash` at `0x18003236d`
- `CRYPTSP!CryptDestroyHash` at `0x18003236d`
- `CRYPTSP!CryptGetHashParam` at `0x1800322d8`
- `CRYPTSP!CryptGetHashParam` at `0x180032327`
- `CRYPTSP!CryptGetHashParam` at `0x1800322d8`
- `CRYPTSP!CryptGetHashParam` at `0x180032327`
- `CRYPTSP!CryptCreateHash` at `0x1800321fb`
- `CRYPTSP!CryptCreateHash` at `0x1800321fb`
- `CRYPTSP!CryptHashData` at `0x180032278`
- `CRYPTSP!CryptHashData` at `0x180032278`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180032377`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180032385`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180032377`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180032385`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800322be`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18003230d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18003234f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800322be`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18003230d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18003234f`
- `iisutil!PuDbgPrint` at `0x180032252`
- `iisutil!PuDbgPrint` at `0x180032252`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800322f8`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800322f8`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800321c8`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800321c8`

## string_xrefs

- `0x180032246`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180032227`: `CryptCreateHash() failed : hr = 0x%x\n`
- `0x18003223b`: `TOKEN_KEY::GeneratePasswordHash`

## pseudocode

```c
__int64 __fastcall TOKEN_KEY::GeneratePasswordHash(TOKEN_KEY *this, const BYTE *a2, struct STRU *a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r8
  signed int v10; // eax
  BYTE *Ptr; // rax
  signed int v12; // eax
  BYTE *v13; // rax
  unsigned int v14; // ebx
  unsigned __int8 *v15; // rax
  __int64 pdwDataLen; // [rsp+30h] [rbp-29h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v19[48]; // [rsp+40h] [rbp-19h] BYREF
  _OWORD v20[2]; // [rsp+70h] [rbp+17h] BYREF

  hHash = 0;
  LODWORD(pdwDataLen) = 0;
  memset(v20, 0, sizeof(v20));
  BUFFER::BUFFER((BUFFER *)v19, (unsigned __int8 *)v20, 0x20u);
  if ( !a2 || !a3 )
  {
    BUFFER::~BUFFER((BUFFER *)v19);
    return 2147942487LL;
  }
  if ( !CryptCreateHash(TOKEN_KEY::sm_hCryptProv, 0x800Cu, 0, 0, &hHash) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_25;
    v7 = "CryptCreateHash() failed : hr = 0x%x\n";
    v8 = 774;
    goto LABEL_8;
  }
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)&a2[2 * v9] );
  if ( CryptHashData(hHash, a2, 2 * v9, 0) )
  {
    LODWORD(pdwDataLen) = 32;
    Ptr = (BYTE *)BUFFER::QueryPtr((BUFFER *)v19);
    if ( !CryptGetHashParam(hHash, 2u, Ptr, (DWORD *)&pdwDataLen, 0) )
    {
      v12 = GetLastError();
      v6 = v12;
      if ( v12 != 234 )
        goto LABEL_22;
      if ( !BUFFER::Resize((BUFFER *)v19, pdwDataLen) )
      {
        v6 = -2147024882;
        goto LABEL_25;
      }
      v13 = (BYTE *)BUFFER::QueryPtr((BUFFER *)v19);
      if ( !CryptGetHashParam(hHash, 2u, v13, (DWORD *)&pdwDataLen, 0) )
      {
        v12 = GetLastError();
        v6 = v12;
LABEL_22:
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
        goto LABEL_25;
      }
    }
    v14 = pdwDataLen;
    v15 = (unsigned __int8 *)BUFFER::QueryPtr((BUFFER *)v19);
    v6 = TOKEN_KEY::ToHex(v15, v14, a3);
    goto LABEL_25;
  }
  v10 = GetLastError();
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( (g_dwDebugFlags & 3) == 0 )
    goto LABEL_25;
  v7 = "CryptHashData() failed : hr = 0x%x\n";
  v8 = 788;
LABEL_8:
  PuDbgPrint(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
    v8,
    "TOKEN_KEY::GeneratePasswordHash",
    v7,
    v6,
    pdwDataLen);
LABEL_25:
  if ( hHash )
    CryptDestroyHash(hHash);
  BUFFER::~BUFFER((BUFFER *)v19);
  return v6;
}

```

## disassembly

```asm
0x180032180  mov     [rsp-8+arg_0], rbx
0x180032185  push    rbp
0x180032186  push    rsi
0x180032187  push    rdi
0x180032188  lea     rbp, [rsp-47h]
0x18003218d  sub     rsp, 0A0h
0x180032194  mov     rax, cs:__security_cookie
0x18003219b  xor     rax, rsp
0x18003219e  mov     [rbp+57h+var_20], rax
0x1800321a2  xor     esi, esi
0x1800321a4  lea     rcx, [rbp+57h+var_70]
0x1800321a8  xorps   xmm0, xmm0
0x1800321ab  mov     [rbp+57h+hHash], rsi
0x1800321af  mov     rdi, r8
0x1800321b2  mov     dword ptr [rbp+57h+pdwDataLen], esi
0x1800321b5  mov     rbx, rdx
0x1800321b8  lea     rdx, [rbp+57h+var_40]
0x1800321bc  lea     r8d, [rsi+20h]
0x1800321c0  movups  [rbp+57h+var_40], xmm0
0x1800321c4  movups  [rbp+57h+var_30], xmm0
0x1800321c8  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800321ce  test    rbx, rbx
0x1800321d1  jz      loc_180032381
0x1800321d7  test    rdi, rdi
0x1800321da  jz      loc_180032381
0x1800321e0  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x1800321e7  lea     rax, [rbp+57h+hHash]
0x1800321eb  xor     r9d, r9d; dwFlags
0x1800321ee  mov     [rsp+0B0h+phHash], rax; phHash
0x1800321f3  xor     r8d, r8d; hKey
0x1800321f6  mov     edx, 800Ch; Algid
0x1800321fb  call    cs:__imp_CryptCreateHash
0x180032201  test    eax, eax
0x180032203  jnz     short loc_18003225D
0x180032205  call    cs:__imp_GetLastError
0x18003220b  mov     ebx, eax
0x18003220d  test    eax, eax
0x18003220f  jle     short loc_18003221A
0x180032211  movzx   ebx, ax
0x180032214  or      ebx, 80070000h
0x18003221a  test    byte ptr cs:g_dwDebugFlags, 3
0x180032221  jz      loc_180032364
0x180032227  lea     rax, aCryptcreatehas; "CryptCreateHash() failed : hr = 0x%x\n"
0x18003222e  mov     r8d, 306h
0x180032234  mov     rcx, cs:g_pDebug
0x18003223b  lea     r9, aTokenKeyGenera; "TOKEN_KEY::GeneratePasswordHash"
0x180032242  mov     [rsp+0B0h+var_88], ebx
0x180032246  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18003224d  mov     [rsp+0B0h+phHash], rax
0x180032252  call    cs:__imp_PuDbgPrint
0x180032258  jmp     loc_180032364
0x18003225d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180032261  inc     r8
0x180032264  cmp     [rbx+r8*2], si
0x180032269  jnz     short loc_180032261
0x18003226b  mov     rcx, [rbp+57h+hHash]; hHash
0x18003226f  add     r8d, r8d; dwDataLen
0x180032272  xor     r9d, r9d; dwFlags
0x180032275  mov     rdx, rbx; pbData
0x180032278  call    cs:__imp_CryptHashData
0x18003227e  test    eax, eax
0x180032280  jnz     short loc_1800322B3
0x180032282  call    cs:__imp_GetLastError
0x180032288  mov     ebx, eax
0x18003228a  test    eax, eax
0x18003228c  jle     short loc_180032297
0x18003228e  movzx   ebx, ax
0x180032291  or      ebx, 80070000h
0x180032297  test    byte ptr cs:g_dwDebugFlags, 3
0x18003229e  jz      loc_180032364
0x1800322a4  lea     rax, aCrypthashdataF; "CryptHashData() failed : hr = 0x%x\n"
0x1800322ab  mov     r8d, 314h
0x1800322b1  jmp     short loc_180032234
0x1800322b3  lea     rcx, [rbp+57h+var_70]
0x1800322b7  mov     dword ptr [rbp+57h+pdwDataLen], 20h ; ' '
0x1800322be  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800322c4  mov     rcx, [rbp+57h+hHash]; hHash
0x1800322c8  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x1800322cc  mov     r8, rax; pbData
0x1800322cf  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x1800322d3  mov     edx, 2; dwParam
0x1800322d8  call    cs:__imp_CryptGetHashParam
0x1800322de  test    eax, eax
0x1800322e0  jnz     short loc_180032348
0x1800322e2  call    cs:__imp_GetLastError
0x1800322e8  mov     ebx, eax
0x1800322ea  cmp     eax, 0EAh
0x1800322ef  jnz     short loc_180032339
0x1800322f1  mov     edx, dword ptr [rbp+57h+pdwDataLen]
0x1800322f4  lea     rcx, [rbp+57h+var_70]
0x1800322f8  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800322fe  test    al, al
0x180032300  jnz     short loc_180032309
0x180032302  mov     ebx, 8007000Eh
0x180032307  jmp     short loc_180032364
0x180032309  lea     rcx, [rbp+57h+var_70]
0x18003230d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180032313  mov     rcx, [rbp+57h+hHash]; hHash
0x180032317  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18003231b  mov     r8, rax; pbData
0x18003231e  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x180032322  mov     edx, 2; dwParam
0x180032327  call    cs:__imp_CryptGetHashParam
0x18003232d  test    eax, eax
0x18003232f  jnz     short loc_180032348
0x180032331  call    cs:__imp_GetLastError
0x180032337  mov     ebx, eax
0x180032339  test    eax, eax
0x18003233b  jle     short loc_180032364
0x18003233d  movzx   ebx, ax
0x180032340  or      ebx, 80070000h
0x180032346  jmp     short loc_180032364
0x180032348  mov     ebx, dword ptr [rbp+57h+pdwDataLen]
0x18003234b  lea     rcx, [rbp+57h+var_70]
0x18003234f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180032355  mov     r8, rdi; struct STRU *
0x180032358  mov     edx, ebx; unsigned int
0x18003235a  mov     rcx, rax; unsigned __int8 *
0x18003235d  call    ?ToHex@TOKEN_KEY@@SAJPEAEKPEAVSTRU@@@Z; TOKEN_KEY::ToHex(uchar *,ulong,STRU *)
0x180032362  mov     ebx, eax
0x180032364  mov     rcx, [rbp+57h+hHash]; hHash
0x180032368  test    rcx, rcx
0x18003236b  jz      short loc_180032373
0x18003236d  call    cs:__imp_CryptDestroyHash
0x180032373  lea     rcx, [rbp+57h+var_70]
0x180032377  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18003237d  mov     eax, ebx
0x18003237f  jmp     short loc_180032390
0x180032381  lea     rcx, [rbp+57h+var_70]
0x180032385  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18003238b  mov     eax, 80070057h
0x180032390  mov     rcx, [rbp+57h+var_20]
0x180032394  xor     rcx, rsp; StackCookie
0x180032397  call    __security_check_cookie
0x18003239c  mov     rbx, [rsp+0B0h+arg_0]
0x1800323a4  add     rsp, 0A0h
0x1800323ab  pop     rdi
0x1800323ac  pop     rsi
0x1800323ad  pop     rbp
0x1800323ae  retn
```
