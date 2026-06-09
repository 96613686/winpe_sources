# TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)

- ea: `0x180010fa0`
- end: `0x1800111cf`
- name: `?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z`
- size: `559`
- prototype: `int(TOKEN_KEY *__hidden this, const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010bf4`

## callees

- `0x180010fa0`
- `0x180011ca4`
- `0x1800124c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011151`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800110de`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001112d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001116f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800110de`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001112d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001116f`
- `iisutil!PuDbgPrint` at `0x180011072`
- `iisutil!PuDbgPrint` at `0x180011072`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180011197`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800111a5`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180011197`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800111a5`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180011118`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180011118`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180010fe8`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180010fe8`
- `CRYPTSP!CryptDestroyHash` at `0x18001118d`
- `CRYPTSP!CryptDestroyHash` at `0x18001118d`
- `CRYPTSP!CryptHashData` at `0x180011098`
- `CRYPTSP!CryptHashData` at `0x180011098`
- `CRYPTSP!CryptGetHashParam` at `0x1800110f8`
- `CRYPTSP!CryptGetHashParam` at `0x180011147`
- `CRYPTSP!CryptGetHashParam` at `0x1800110f8`
- `CRYPTSP!CryptGetHashParam` at `0x180011147`
- `CRYPTSP!CryptCreateHash` at `0x18001101b`
- `CRYPTSP!CryptCreateHash` at `0x18001101b`

## string_xrefs

- `0x180011066`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180011047`: `CryptCreateHash() failed : hr = 0x%x\n`
- `0x18001105b`: `TOKEN_KEY::GeneratePasswordHash`

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
0x180010fa0  mov     [rsp-8+arg_0], rbx
0x180010fa5  push    rbp
0x180010fa6  push    rsi
0x180010fa7  push    rdi
0x180010fa8  lea     rbp, [rsp-47h]
0x180010fad  sub     rsp, 0A0h
0x180010fb4  mov     rax, cs:__security_cookie
0x180010fbb  xor     rax, rsp
0x180010fbe  mov     [rbp+57h+var_20], rax
0x180010fc2  xor     esi, esi
0x180010fc4  lea     rcx, [rbp+57h+var_70]
0x180010fc8  xorps   xmm0, xmm0
0x180010fcb  mov     [rbp+57h+hHash], rsi
0x180010fcf  mov     rdi, r8
0x180010fd2  mov     dword ptr [rbp+57h+pdwDataLen], esi
0x180010fd5  mov     rbx, rdx
0x180010fd8  lea     rdx, [rbp+57h+var_40]
0x180010fdc  lea     r8d, [rsi+20h]
0x180010fe0  movups  [rbp+57h+var_40], xmm0
0x180010fe4  movups  [rbp+57h+var_30], xmm0
0x180010fe8  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180010fee  test    rbx, rbx
0x180010ff1  jz      loc_1800111A1
0x180010ff7  test    rdi, rdi
0x180010ffa  jz      loc_1800111A1
0x180011000  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x180011007  lea     rax, [rbp+57h+hHash]
0x18001100b  xor     r9d, r9d; dwFlags
0x18001100e  mov     [rsp+0B0h+phHash], rax; phHash
0x180011013  xor     r8d, r8d; hKey
0x180011016  mov     edx, 800Ch; Algid
0x18001101b  call    cs:__imp_CryptCreateHash
0x180011021  test    eax, eax
0x180011023  jnz     short loc_18001107D
0x180011025  call    cs:__imp_GetLastError
0x18001102b  mov     ebx, eax
0x18001102d  test    eax, eax
0x18001102f  jle     short loc_18001103A
0x180011031  movzx   ebx, ax
0x180011034  or      ebx, 80070000h
0x18001103a  test    byte ptr cs:g_dwDebugFlags, 3
0x180011041  jz      loc_180011184
0x180011047  lea     rax, aCryptcreatehas; "CryptCreateHash() failed : hr = 0x%x\n"
0x18001104e  mov     r8d, 306h
0x180011054  mov     rcx, cs:g_pDebug
0x18001105b  lea     r9, aTokenKeyGenera; "TOKEN_KEY::GeneratePasswordHash"
0x180011062  mov     [rsp+0B0h+var_88], ebx
0x180011066  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001106d  mov     [rsp+0B0h+phHash], rax
0x180011072  call    cs:__imp_PuDbgPrint
0x180011078  jmp     loc_180011184
0x18001107d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180011081  inc     r8
0x180011084  cmp     [rbx+r8*2], si
0x180011089  jnz     short loc_180011081
0x18001108b  mov     rcx, [rbp+57h+hHash]; hHash
0x18001108f  add     r8d, r8d; dwDataLen
0x180011092  xor     r9d, r9d; dwFlags
0x180011095  mov     rdx, rbx; pbData
0x180011098  call    cs:__imp_CryptHashData
0x18001109e  test    eax, eax
0x1800110a0  jnz     short loc_1800110D3
0x1800110a2  call    cs:__imp_GetLastError
0x1800110a8  mov     ebx, eax
0x1800110aa  test    eax, eax
0x1800110ac  jle     short loc_1800110B7
0x1800110ae  movzx   ebx, ax
0x1800110b1  or      ebx, 80070000h
0x1800110b7  test    byte ptr cs:g_dwDebugFlags, 3
0x1800110be  jz      loc_180011184
0x1800110c4  lea     rax, aCrypthashdataF; "CryptHashData() failed : hr = 0x%x\n"
0x1800110cb  mov     r8d, 314h
0x1800110d1  jmp     short loc_180011054
0x1800110d3  lea     rcx, [rbp+57h+var_70]
0x1800110d7  mov     dword ptr [rbp+57h+pdwDataLen], 20h ; ' '
0x1800110de  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800110e4  mov     rcx, [rbp+57h+hHash]; hHash
0x1800110e8  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x1800110ec  mov     r8, rax; pbData
0x1800110ef  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x1800110f3  mov     edx, 2; dwParam
0x1800110f8  call    cs:__imp_CryptGetHashParam
0x1800110fe  test    eax, eax
0x180011100  jnz     short loc_180011168
0x180011102  call    cs:__imp_GetLastError
0x180011108  mov     ebx, eax
0x18001110a  cmp     eax, 0EAh
0x18001110f  jnz     short loc_180011159
0x180011111  mov     edx, dword ptr [rbp+57h+pdwDataLen]
0x180011114  lea     rcx, [rbp+57h+var_70]
0x180011118  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001111e  test    al, al
0x180011120  jnz     short loc_180011129
0x180011122  mov     ebx, 8007000Eh
0x180011127  jmp     short loc_180011184
0x180011129  lea     rcx, [rbp+57h+var_70]
0x18001112d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180011133  mov     rcx, [rbp+57h+hHash]; hHash
0x180011137  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18001113b  mov     r8, rax; pbData
0x18001113e  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x180011142  mov     edx, 2; dwParam
0x180011147  call    cs:__imp_CryptGetHashParam
0x18001114d  test    eax, eax
0x18001114f  jnz     short loc_180011168
0x180011151  call    cs:__imp_GetLastError
0x180011157  mov     ebx, eax
0x180011159  test    eax, eax
0x18001115b  jle     short loc_180011184
0x18001115d  movzx   ebx, ax
0x180011160  or      ebx, 80070000h
0x180011166  jmp     short loc_180011184
0x180011168  mov     ebx, dword ptr [rbp+57h+pdwDataLen]
0x18001116b  lea     rcx, [rbp+57h+var_70]
0x18001116f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180011175  mov     r8, rdi; struct STRU *
0x180011178  mov     edx, ebx; unsigned int
0x18001117a  mov     rcx, rax; unsigned __int8 *
0x18001117d  call    ?ToHex@TOKEN_KEY@@SAJPEAEKPEAVSTRU@@@Z; TOKEN_KEY::ToHex(uchar *,ulong,STRU *)
0x180011182  mov     ebx, eax
0x180011184  mov     rcx, [rbp+57h+hHash]; hHash
0x180011188  test    rcx, rcx
0x18001118b  jz      short loc_180011193
0x18001118d  call    cs:__imp_CryptDestroyHash
0x180011193  lea     rcx, [rbp+57h+var_70]
0x180011197  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001119d  mov     eax, ebx
0x18001119f  jmp     short loc_1800111B0
0x1800111a1  lea     rcx, [rbp+57h+var_70]
0x1800111a5  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800111ab  mov     eax, 80070057h
0x1800111b0  mov     rcx, [rbp+57h+var_20]
0x1800111b4  xor     rcx, rsp; StackCookie
0x1800111b7  call    __security_check_cookie
0x1800111bc  mov     rbx, [rsp+0B0h+arg_0]
0x1800111c4  add     rsp, 0A0h
0x1800111cb  pop     rdi
0x1800111cc  pop     rsi
0x1800111cd  pop     rbp
0x1800111ce  retn
```
