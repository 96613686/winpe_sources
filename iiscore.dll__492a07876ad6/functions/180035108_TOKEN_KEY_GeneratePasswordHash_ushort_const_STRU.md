# TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)

- ea: `0x180035108`
- end: `0x1800353a5`
- name: `?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(TOKEN_KEY *this, const BYTE *, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180034c90`

## callees

- `0x180035108`
- `0x180036034`
- `0x180037790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035308`
- `CRYPTSP!CryptDestroyHash` at `0x180035350`
- `CRYPTSP!CryptDestroyHash` at `0x180035350`
- `CRYPTSP!CryptGetHashParam` at `0x18003528d`
- `CRYPTSP!CryptGetHashParam` at `0x1800352f8`
- `CRYPTSP!CryptGetHashParam` at `0x18003528d`
- `CRYPTSP!CryptGetHashParam` at `0x1800352f8`
- `CRYPTSP!CryptCreateHash` at `0x180035189`
- `CRYPTSP!CryptCreateHash` at `0x180035189`
- `CRYPTSP!CryptHashData` at `0x180035218`
- `CRYPTSP!CryptHashData` at `0x180035218`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180035360`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180035374`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180035360`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180035374`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18003526d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800352d8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18003532c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18003526d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800352d8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18003532c`
- `iisutil!PuDbgPrint` at `0x1800351ec`
- `iisutil!PuDbgPrint` at `0x1800351ec`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800352bd`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800352bd`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180035150`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180035150`

## string_xrefs

- `0x1800351e0`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x1800351c1`: `CryptCreateHash() failed : hr = 0x%x\n`
- `0x1800351d5`: `TOKEN_KEY::GeneratePasswordHash`

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
0x180035108  mov     [rsp-8+arg_0], rbx
0x18003510d  push    rbp
0x18003510e  push    rsi
0x18003510f  push    rdi
0x180035110  lea     rbp, [rsp-47h]
0x180035115  sub     rsp, 0A0h
0x18003511c  mov     rax, cs:__security_cookie
0x180035123  xor     rax, rsp
0x180035126  mov     [rbp+57h+var_20], rax
0x18003512a  xor     esi, esi
0x18003512c  lea     rcx, [rbp+57h+var_70]
0x180035130  xorps   xmm0, xmm0
0x180035133  mov     [rbp+57h+hHash], rsi
0x180035137  mov     rdi, r8
0x18003513a  mov     dword ptr [rbp+57h+pdwDataLen], esi
0x18003513d  mov     rbx, rdx
0x180035140  lea     rdx, [rbp+57h+var_40]
0x180035144  lea     r8d, [rsi+20h]
0x180035148  movups  [rbp+57h+var_40], xmm0
0x18003514c  movups  [rbp+57h+var_30], xmm0
0x180035150  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180035157  nop     dword ptr [rax+rax+00h]
0x18003515c  test    rbx, rbx
0x18003515f  jz      loc_180035370
0x180035165  test    rdi, rdi
0x180035168  jz      loc_180035370
0x18003516e  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x180035175  lea     rax, [rbp+57h+hHash]
0x180035179  xor     r9d, r9d; dwFlags
0x18003517c  mov     [rsp+0B0h+phHash], rax; phHash
0x180035181  xor     r8d, r8d; hKey
0x180035184  mov     edx, 800Ch; Algid
0x180035189  call    cs:__imp_CryptCreateHash
0x180035190  nop     dword ptr [rax+rax+00h]
0x180035195  test    eax, eax
0x180035197  jnz     short loc_1800351FD
0x180035199  call    cs:__imp_GetLastError
0x1800351a0  nop     dword ptr [rax+rax+00h]
0x1800351a5  mov     ebx, eax
0x1800351a7  test    eax, eax
0x1800351a9  jle     short loc_1800351B4
0x1800351ab  movzx   ebx, ax
0x1800351ae  or      ebx, 80070000h
0x1800351b4  test    byte ptr cs:g_dwDebugFlags, 3
0x1800351bb  jz      loc_180035347
0x1800351c1  lea     rax, aCryptcreatehas; "CryptCreateHash() failed : hr = 0x%x\n"
0x1800351c8  mov     r8d, 306h
0x1800351ce  mov     rcx, cs:g_pDebug
0x1800351d5  lea     r9, aTokenKeyGenera; "TOKEN_KEY::GeneratePasswordHash"
0x1800351dc  mov     [rsp+0B0h+var_88], ebx
0x1800351e0  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800351e7  mov     [rsp+0B0h+phHash], rax
0x1800351ec  call    cs:__imp_PuDbgPrint
0x1800351f3  nop     dword ptr [rax+rax+00h]
0x1800351f8  jmp     loc_180035347
0x1800351fd  or      r8, 0FFFFFFFFFFFFFFFFh
0x180035201  inc     r8
0x180035204  cmp     [rbx+r8*2], si
0x180035209  jnz     short loc_180035201
0x18003520b  mov     rcx, [rbp+57h+hHash]; hHash
0x18003520f  add     r8d, r8d; dwDataLen
0x180035212  xor     r9d, r9d; dwFlags
0x180035215  mov     rdx, rbx; pbData
0x180035218  call    cs:__imp_CryptHashData
0x18003521f  nop     dword ptr [rax+rax+00h]
0x180035224  test    eax, eax
0x180035226  jnz     short loc_180035262
0x180035228  call    cs:__imp_GetLastError
0x18003522f  nop     dword ptr [rax+rax+00h]
0x180035234  mov     ebx, eax
0x180035236  test    eax, eax
0x180035238  jle     short loc_180035243
0x18003523a  movzx   ebx, ax
0x18003523d  or      ebx, 80070000h
0x180035243  test    byte ptr cs:g_dwDebugFlags, 3
0x18003524a  jz      loc_180035347
0x180035250  lea     rax, aCrypthashdataF; "CryptHashData() failed : hr = 0x%x\n"
0x180035257  mov     r8d, 314h
0x18003525d  jmp     loc_1800351CE
0x180035262  lea     rcx, [rbp+57h+var_70]
0x180035266  mov     dword ptr [rbp+57h+pdwDataLen], 20h ; ' '
0x18003526d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180035274  nop     dword ptr [rax+rax+00h]
0x180035279  mov     rcx, [rbp+57h+hHash]; hHash
0x18003527d  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x180035281  mov     r8, rax; pbData
0x180035284  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x180035288  mov     edx, 2; dwParam
0x18003528d  call    cs:__imp_CryptGetHashParam
0x180035294  nop     dword ptr [rax+rax+00h]
0x180035299  test    eax, eax
0x18003529b  jnz     loc_180035325
0x1800352a1  call    cs:__imp_GetLastError
0x1800352a8  nop     dword ptr [rax+rax+00h]
0x1800352ad  mov     ebx, eax
0x1800352af  cmp     eax, 0EAh
0x1800352b4  jnz     short loc_180035316
0x1800352b6  mov     edx, dword ptr [rbp+57h+pdwDataLen]
0x1800352b9  lea     rcx, [rbp+57h+var_70]
0x1800352bd  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800352c4  nop     dword ptr [rax+rax+00h]
0x1800352c9  test    al, al
0x1800352cb  jnz     short loc_1800352D4
0x1800352cd  mov     ebx, 8007000Eh
0x1800352d2  jmp     short loc_180035347
0x1800352d4  lea     rcx, [rbp+57h+var_70]
0x1800352d8  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800352df  nop     dword ptr [rax+rax+00h]
0x1800352e4  mov     rcx, [rbp+57h+hHash]; hHash
0x1800352e8  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x1800352ec  mov     r8, rax; pbData
0x1800352ef  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x1800352f3  mov     edx, 2; dwParam
0x1800352f8  call    cs:__imp_CryptGetHashParam
0x1800352ff  nop     dword ptr [rax+rax+00h]
0x180035304  test    eax, eax
0x180035306  jnz     short loc_180035325
0x180035308  call    cs:__imp_GetLastError
0x18003530f  nop     dword ptr [rax+rax+00h]
0x180035314  mov     ebx, eax
0x180035316  test    eax, eax
0x180035318  jle     short loc_180035347
0x18003531a  movzx   ebx, ax
0x18003531d  or      ebx, 80070000h
0x180035323  jmp     short loc_180035347
0x180035325  mov     ebx, dword ptr [rbp+57h+pdwDataLen]
0x180035328  lea     rcx, [rbp+57h+var_70]
0x18003532c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180035333  nop     dword ptr [rax+rax+00h]
0x180035338  mov     r8, rdi; struct STRU *
0x18003533b  mov     edx, ebx; unsigned int
0x18003533d  mov     rcx, rax; unsigned __int8 *
0x180035340  call    ?ToHex@TOKEN_KEY@@SAJPEAEKPEAVSTRU@@@Z; TOKEN_KEY::ToHex(uchar *,ulong,STRU *)
0x180035345  mov     ebx, eax
0x180035347  mov     rcx, [rbp+57h+hHash]; hHash
0x18003534b  test    rcx, rcx
0x18003534e  jz      short loc_18003535C
0x180035350  call    cs:__imp_CryptDestroyHash
0x180035357  nop     dword ptr [rax+rax+00h]
0x18003535c  lea     rcx, [rbp+57h+var_70]
0x180035360  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180035367  nop     dword ptr [rax+rax+00h]
0x18003536c  mov     eax, ebx
0x18003536e  jmp     short loc_180035385
0x180035370  lea     rcx, [rbp+57h+var_70]
0x180035374  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18003537b  nop     dword ptr [rax+rax+00h]
0x180035380  mov     eax, 80070057h
0x180035385  mov     rcx, [rbp+57h+var_20]
0x180035389  xor     rcx, rsp; StackCookie
0x18003538c  call    __security_check_cookie
0x180035391  mov     rbx, [rsp+0B0h+arg_0]
0x180035399  add     rsp, 0A0h
0x1800353a0  pop     rdi
0x1800353a1  pop     rsi
0x1800353a2  pop     rbp
0x1800353a3  retn
```
