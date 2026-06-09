# TOKEN_CACHE_ENTRY::GenPasswordHash(ushort const *,STRA *)

- ea: `0x180058ff8`
- end: `0x180059227`
- name: `?GenPasswordHash@TOKEN_CACHE_ENTRY@@QEAAJPEBGPEAVSTRA@@@Z`
- size: `559`
- prototype: `int(TOKEN_CACHE_ENTRY *__hidden this, const unsigned __int16 *, struct STRA *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058f60`
- `0x180059230`

## callees

- `0x180058ff8`
- `0x180059958`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005907d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800590fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005915a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800591a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005907d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800590fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005915a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800591a9`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800591ef`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800591fd`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800591ef`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800591fd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180059136`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180059185`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800591c7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180059136`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180059185`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800591c7`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180059040`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180059040`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180059170`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180059170`
- `iisutil!PuDbgPrint` at `0x1800590ca`
- `iisutil!PuDbgPrint` at `0x1800590ca`
- `CRYPTSP!CryptHashData` at `0x1800590f0`
- `CRYPTSP!CryptHashData` at `0x1800590f0`
- `CRYPTSP!CryptCreateHash` at `0x180059073`
- `CRYPTSP!CryptCreateHash` at `0x180059073`
- `CRYPTSP!CryptGetHashParam` at `0x180059150`
- `CRYPTSP!CryptGetHashParam` at `0x18005919f`
- `CRYPTSP!CryptGetHashParam` at `0x180059150`
- `CRYPTSP!CryptGetHashParam` at `0x18005919f`
- `CRYPTSP!CryptDestroyHash` at `0x1800591e5`
- `CRYPTSP!CryptDestroyHash` at `0x1800591e5`

## string_xrefs

- `0x1800590be`: `servercommon\inetsrv\iis\iisrearc\core\nativereader\dll\tokencache.cxx`
- `0x18005909f`: `CryptCreateHash() failed : hr = 0x%x\n`
- `0x1800590b3`: `TOKEN_CACHE_ENTRY::GenPasswordHash`

## pseudocode

```c
__int64 __fastcall TOKEN_CACHE_ENTRY::GenPasswordHash(TOKEN_CACHE_ENTRY *this, const BYTE *a2, struct STRA *a3)
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
  if ( !CryptCreateHash(TOKEN_CACHE_ENTRY::sm_hCryptProv, 0x800Cu, 0, 0, &hHash) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_25;
    v7 = "CryptCreateHash() failed : hr = 0x%x\n";
    v8 = 221;
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
    v6 = ToHex(v15, v14, a3);
    goto LABEL_25;
  }
  v10 = GetLastError();
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( (g_dwDebugFlags & 3) == 0 )
    goto LABEL_25;
  v7 = "CryptHashData() failed : hr = 0x%x\n";
  v8 = 235;
LABEL_8:
  PuDbgPrint(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\core\\nativereader\\dll\\tokencache.cxx",
    v8,
    "TOKEN_CACHE_ENTRY::GenPasswordHash",
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
0x180058ff8  mov     [rsp-8+arg_0], rbx
0x180058ffd  push    rbp
0x180058ffe  push    rsi
0x180058fff  push    rdi
0x180059000  lea     rbp, [rsp-47h]
0x180059005  sub     rsp, 0A0h
0x18005900c  mov     rax, cs:__security_cookie
0x180059013  xor     rax, rsp
0x180059016  mov     [rbp+57h+var_20], rax
0x18005901a  xor     esi, esi
0x18005901c  lea     rcx, [rbp+57h+var_70]
0x180059020  xorps   xmm0, xmm0
0x180059023  mov     [rbp+57h+hHash], rsi
0x180059027  mov     rdi, r8
0x18005902a  mov     dword ptr [rbp+57h+pdwDataLen], esi
0x18005902d  mov     rbx, rdx
0x180059030  lea     rdx, [rbp+57h+var_40]
0x180059034  lea     r8d, [rsi+20h]
0x180059038  movups  [rbp+57h+var_40], xmm0
0x18005903c  movups  [rbp+57h+var_30], xmm0
0x180059040  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180059046  test    rbx, rbx
0x180059049  jz      loc_1800591F9
0x18005904f  test    rdi, rdi
0x180059052  jz      loc_1800591F9
0x180059058  mov     rcx, cs:?sm_hCryptProv@TOKEN_CACHE_ENTRY@@0_KA; hProv
0x18005905f  lea     rax, [rbp+57h+hHash]
0x180059063  xor     r9d, r9d; dwFlags
0x180059066  mov     [rsp+0B0h+phHash], rax; phHash
0x18005906b  xor     r8d, r8d; hKey
0x18005906e  mov     edx, 800Ch; Algid
0x180059073  call    cs:__imp_CryptCreateHash
0x180059079  test    eax, eax
0x18005907b  jnz     short loc_1800590D5
0x18005907d  call    cs:__imp_GetLastError
0x180059083  mov     ebx, eax
0x180059085  test    eax, eax
0x180059087  jle     short loc_180059092
0x180059089  movzx   ebx, ax
0x18005908c  or      ebx, 80070000h
0x180059092  test    byte ptr cs:g_dwDebugFlags, 3
0x180059099  jz      loc_1800591DC
0x18005909f  lea     rax, aCryptcreatehas_0; "CryptCreateHash() failed : hr = 0x%x\n"
0x1800590a6  mov     r8d, 0DDh
0x1800590ac  mov     rcx, cs:g_pDebug
0x1800590b3  lea     r9, aTokenCacheEntr_2; "TOKEN_CACHE_ENTRY::GenPasswordHash"
0x1800590ba  mov     [rsp+0B0h+var_88], ebx
0x1800590be  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800590c5  mov     [rsp+0B0h+phHash], rax
0x1800590ca  call    cs:__imp_PuDbgPrint
0x1800590d0  jmp     loc_1800591DC
0x1800590d5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800590d9  inc     r8
0x1800590dc  cmp     [rbx+r8*2], si
0x1800590e1  jnz     short loc_1800590D9
0x1800590e3  mov     rcx, [rbp+57h+hHash]; hHash
0x1800590e7  add     r8d, r8d; dwDataLen
0x1800590ea  xor     r9d, r9d; dwFlags
0x1800590ed  mov     rdx, rbx; pbData
0x1800590f0  call    cs:__imp_CryptHashData
0x1800590f6  test    eax, eax
0x1800590f8  jnz     short loc_18005912B
0x1800590fa  call    cs:__imp_GetLastError
0x180059100  mov     ebx, eax
0x180059102  test    eax, eax
0x180059104  jle     short loc_18005910F
0x180059106  movzx   ebx, ax
0x180059109  or      ebx, 80070000h
0x18005910f  test    byte ptr cs:g_dwDebugFlags, 3
0x180059116  jz      loc_1800591DC
0x18005911c  lea     rax, aCrypthashdataF; "CryptHashData() failed : hr = 0x%x\n"
0x180059123  mov     r8d, 0EBh
0x180059129  jmp     short loc_1800590AC
0x18005912b  lea     rcx, [rbp+57h+var_70]
0x18005912f  mov     dword ptr [rbp+57h+pdwDataLen], 20h ; ' '
0x180059136  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18005913c  mov     rcx, [rbp+57h+hHash]; hHash
0x180059140  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x180059144  mov     r8, rax; pbData
0x180059147  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x18005914b  mov     edx, 2; dwParam
0x180059150  call    cs:__imp_CryptGetHashParam
0x180059156  test    eax, eax
0x180059158  jnz     short loc_1800591C0
0x18005915a  call    cs:__imp_GetLastError
0x180059160  mov     ebx, eax
0x180059162  cmp     eax, 0EAh
0x180059167  jnz     short loc_1800591B1
0x180059169  mov     edx, dword ptr [rbp+57h+pdwDataLen]
0x18005916c  lea     rcx, [rbp+57h+var_70]
0x180059170  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180059176  test    al, al
0x180059178  jnz     short loc_180059181
0x18005917a  mov     ebx, 8007000Eh
0x18005917f  jmp     short loc_1800591DC
0x180059181  lea     rcx, [rbp+57h+var_70]
0x180059185  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18005918b  mov     rcx, [rbp+57h+hHash]; hHash
0x18005918f  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x180059193  mov     r8, rax; pbData
0x180059196  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x18005919a  mov     edx, 2; dwParam
0x18005919f  call    cs:__imp_CryptGetHashParam
0x1800591a5  test    eax, eax
0x1800591a7  jnz     short loc_1800591C0
0x1800591a9  call    cs:__imp_GetLastError
0x1800591af  mov     ebx, eax
0x1800591b1  test    eax, eax
0x1800591b3  jle     short loc_1800591DC
0x1800591b5  movzx   ebx, ax
0x1800591b8  or      ebx, 80070000h
0x1800591be  jmp     short loc_1800591DC
0x1800591c0  mov     ebx, dword ptr [rbp+57h+pdwDataLen]
0x1800591c3  lea     rcx, [rbp+57h+var_70]
0x1800591c7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800591cd  mov     r8, rdi; struct STRA *
0x1800591d0  mov     edx, ebx; unsigned int
0x1800591d2  mov     rcx, rax; unsigned __int8 *
0x1800591d5  call    ?ToHex@@YAJPEAEKAEAVSTRA@@@Z; ToHex(uchar *,ulong,STRA &)
0x1800591da  mov     ebx, eax
0x1800591dc  mov     rcx, [rbp+57h+hHash]; hHash
0x1800591e0  test    rcx, rcx
0x1800591e3  jz      short loc_1800591EB
0x1800591e5  call    cs:__imp_CryptDestroyHash
0x1800591eb  lea     rcx, [rbp+57h+var_70]
0x1800591ef  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800591f5  mov     eax, ebx
0x1800591f7  jmp     short loc_180059208
0x1800591f9  lea     rcx, [rbp+57h+var_70]
0x1800591fd  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180059203  mov     eax, 80070057h
0x180059208  mov     rcx, [rbp+57h+var_20]
0x18005920c  xor     rcx, rsp; StackCookie
0x18005920f  call    __security_check_cookie
0x180059214  mov     rbx, [rsp+0B0h+arg_0]
0x18005921c  add     rsp, 0A0h
0x180059223  pop     rdi
0x180059224  pop     rsi
0x180059225  pop     rbp
0x180059226  retn
```
