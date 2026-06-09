# InetCreateResponseInfo(void *)

- ea: `0x18000335c`
- end: `0x18000357c`
- name: `?InetCreateResponseInfo@@YAPEAU_CRYPTNET_URL_CACHE_RESPONSE_INFO@@PEAX@Z`
- size: `544`
- prototype: `struct _CRYPTNET_URL_CACHE_RESPONSE_INFO *__fastcall(void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180002d8c`
- `0x18000335c`
- `0x180003584`
- `0x18001fa58`
- `0x18001fa9c`
- `0x18001fae4`
- `0x180026552`
- `0x18002656a`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000355a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000355a`
- `CRYPT32!CryptMemAlloc` at `0x1800033dc`
- `CRYPT32!CryptMemAlloc` at `0x1800033dc`
- `CRYPT32!CryptMemFree` at `0x1800033ed`
- `CRYPT32!CryptMemFree` at `0x1800033f6`
- `CRYPT32!CryptMemFree` at `0x1800033ff`
- `CRYPT32!CryptMemFree` at `0x1800033ed`
- `CRYPT32!CryptMemFree` at `0x1800033f6`
- `CRYPT32!CryptMemFree` at `0x1800033ff`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000353a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000353a`
- `WINHTTP!WinHttpQueryHeaders` at `0x18000348b`
- `WINHTTP!WinHttpQueryHeaders` at `0x18000348b`

## pseudocode

```c
struct _CRYPTNET_URL_CACHE_RESPONSE_INFO *__fastcall InetCreateResponseInfo(void *a1)
{
  _WORD *v1; // rbx
  unsigned int v2; // edi
  unsigned __int16 *v3; // r13
  unsigned __int16 *v4; // rsi
  __int64 v5; // r15
  unsigned __int16 *StringHeader; // r14
  __int64 v7; // rax
  _WORD *v8; // rax
  void *v10; // rsi
  const unsigned __int16 *v11; // rax
  DWORD dwIndex; // [rsp+30h] [rbp-48h] BYREF
  DWORD dwBufferLength; // [rsp+34h] [rbp-44h] BYREF
  HINTERNET hRequest; // [rsp+38h] [rbp-40h] BYREF
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+50h] [rbp-28h]
  SYSTEMTIME Buffer; // [rsp+58h] [rbp-20h] BYREF

  v1 = 0;
  hRequest = a1;
  dwBufferLength = 0;
  v2 = 0;
  dwIndex = 0;
  v3 = 0;
  v4 = 0;
  Buffer = 0;
  v5 = -1;
  StringHeader = InetHttpQueryAndAllocateStringHeader(a1, 0x36u);
  if ( !StringHeader )
    goto LABEL_6;
  if ( *StringHeader != 34 )
    goto LABEL_6;
  v7 = -1;
  do
    ++v7;
  while ( StringHeader[v7] );
  v2 = v7 + 1;
  if ( (unsigned int)(v7 + 1) > 0xFFFF )
  {
    SetLastError(0x216u);
  }
  else
  {
LABEL_6:
    v8 = CryptMemAlloc(2 * v2 + 40);
    v1 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, 2 * v2 + 40);
      *(_DWORD *)v1 = 40;
      v1[2] = 1;
      if ( v2 )
      {
        *((_QWORD *)v1 + 3) = v1 + 20;
        memcpy_0(v1 + 20, StringHeader, 2LL * v2);
      }
      v10 = hRequest;
      dwBufferLength = 16;
      dwIndex = 0;
      if ( WinHttpQueryHeaders(hRequest, 0x4000000Bu, 0, &Buffer, &dwBufferLength, &dwIndex) )
      {
        hRequest = 0;
        if ( SystemTimeToFileTime(&Buffer, (LPFILETIME)&hRequest) )
          *((_QWORD *)v1 + 1) = hRequest;
      }
      v11 = InetHttpQueryAndAllocateStringHeader(v10, 0x31u);
      v3 = (unsigned __int16 *)v11;
      if ( v11 )
        *((_DWORD *)v1 + 4) = InetGetMaxAgeFromCacheControlHeader(v11);
      v4 = InetHttpQueryAndAllocateStringHeader(v10, 0x42u);
      if ( v4 )
      {
        *(_OWORD *)phHash = 0;
        v16 = 0;
        CngRsa32Compat_MD5Init(phHash);
        do
          ++v5;
        while ( v4[v5] );
        CngRsa32Compat_MD5Update(phHash, v4, (unsigned int)(2 * v5));
        if ( v2 > 1 )
          CngRsa32Compat_MD5Update(phHash, *((_QWORD *)v1 + 3), 2 * v2 - 2);
        CngRsa32Compat_MD5Update(phHash, v1 + 4, 8);
        CngRsa32Compat_MD5Final(phHash);
        *((_DWORD *)v1 + 8) = phHash[1];
      }
    }
  }
  CryptMemFree(StringHeader);
  CryptMemFree(v3);
  CryptMemFree(v4);
  return (struct _CRYPTNET_URL_CACHE_RESPONSE_INFO *)v1;
}

```

## disassembly

```asm
0x18000335c  push    rbp
0x18000335e  push    rbx
0x18000335f  push    rsi
0x180003360  push    rdi
0x180003361  push    r12
0x180003363  push    r13
0x180003365  push    r14
0x180003367  push    r15
0x180003369  mov     rbp, rsp
0x18000336c  sub     rsp, 78h
0x180003370  mov     rax, cs:__security_cookie
0x180003377  xor     rax, rsp
0x18000337a  mov     [rbp+var_10], rax
0x18000337e  xor     ebx, ebx
0x180003380  mov     [rbp+hRequest], rcx
0x180003384  xorps   xmm0, xmm0
0x180003387  mov     [rbp+dwBufferLength], ebx
0x18000338a  mov     edi, ebx
0x18000338c  mov     [rbp+dwIndex], ebx
0x18000338f  mov     r13d, ebx
0x180003392  mov     esi, ebx
0x180003394  lea     edx, [rbx+36h]; dwInfoLevel
0x180003397  movups  [rbp+Buffer], xmm0
0x18000339b  call    ?InetHttpQueryAndAllocateStringHeader@@YAPEAGPEAXK@Z; InetHttpQueryAndAllocateStringHeader(void *,ulong)
0x1800033a0  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800033a4  mov     r14, rax
0x1800033a7  test    rax, rax
0x1800033aa  jz      short loc_1800033D1
0x1800033ac  lea     eax, [rbx+22h]
0x1800033af  cmp     ax, [r14]
0x1800033b3  jnz     short loc_1800033D1
0x1800033b5  mov     rax, r15
0x1800033b8  inc     rax
0x1800033bb  cmp     [r14+rax*2], bx
0x1800033c0  jnz     short loc_1800033B8
0x1800033c2  lea     edi, [rax+1]
0x1800033c5  cmp     edi, 0FFFFh
0x1800033cb  ja      loc_180003555
0x1800033d1  lea     r12d, ds:28h[rdi*2]
0x1800033d9  mov     ecx, r12d; cbSize
0x1800033dc  call    cs:__imp_CryptMemAlloc
0x1800033e2  mov     rbx, rax
0x1800033e5  test    rax, rax
0x1800033e8  jnz     short loc_180003425
0x1800033ea  mov     rcx, r14; pv
0x1800033ed  call    cs:__imp_CryptMemFree
0x1800033f3  mov     rcx, r13; pv
0x1800033f6  call    cs:__imp_CryptMemFree
0x1800033fc  mov     rcx, rsi; pv
0x1800033ff  call    cs:__imp_CryptMemFree
0x180003405  mov     rax, rbx
0x180003408  mov     rcx, [rbp+var_10]
0x18000340c  xor     rcx, rsp; StackCookie
0x18000340f  call    __security_check_cookie
0x180003414  add     rsp, 78h
0x180003418  pop     r15
0x18000341a  pop     r14
0x18000341c  pop     r13
0x18000341e  pop     r12
0x180003420  pop     rdi
0x180003421  pop     rsi
0x180003422  pop     rbx
0x180003423  pop     rbp
0x180003424  retn
0x180003425  mov     r8d, r12d; Size
0x180003428  xor     edx, edx; Val
0x18000342a  mov     rcx, rbx; void *
0x18000342d  call    memset_0
0x180003432  xor     r12d, r12d
0x180003435  mov     dword ptr [rbx], 28h ; '('
0x18000343b  mov     word ptr [rbx+4], 1
0x180003441  test    edi, edi
0x180003443  jz      short loc_18000345B
0x180003445  lea     rcx, [rbx+28h]; void *
0x180003449  mov     r8d, edi
0x18000344c  add     r8, r8; Size
0x18000344f  mov     [rbx+18h], rcx
0x180003453  mov     rdx, r14; Src
0x180003456  call    memcpy_0
0x18000345b  mov     rsi, [rbp+hRequest]
0x18000345f  lea     rax, [rbp+dwIndex]
0x180003463  mov     [rsp+78h+lpdwIndex], rax; lpdwIndex
0x180003468  lea     r9, [rbp+Buffer]; lpBuffer
0x18000346c  lea     rax, [rbp+dwBufferLength]
0x180003470  mov     [rbp+dwBufferLength], 10h
0x180003477  xor     r8d, r8d; pwszName
0x18000347a  mov     [rsp+78h+lpdwBufferLength], rax; lpdwBufferLength
0x18000347f  mov     edx, 4000000Bh; dwInfoLevel
0x180003484  mov     [rbp+dwIndex], r12d
0x180003488  mov     rcx, rsi; hRequest
0x18000348b  call    cs:__imp_WinHttpQueryHeaders
0x180003491  test    eax, eax
0x180003493  jnz     loc_18000352E
0x180003499  mov     edx, 31h ; '1'; dwInfoLevel
0x18000349e  mov     rcx, rsi; hRequest
0x1800034a1  call    ?InetHttpQueryAndAllocateStringHeader@@YAPEAGPEAXK@Z; InetHttpQueryAndAllocateStringHeader(void *,ulong)
0x1800034a6  mov     r13, rax
0x1800034a9  test    rax, rax
0x1800034ac  jz      short loc_1800034B9
0x1800034ae  mov     rcx, rax; unsigned __int16 *
0x1800034b1  call    ?InetGetMaxAgeFromCacheControlHeader@@YAKPEBG@Z; InetGetMaxAgeFromCacheControlHeader(ushort const *)
0x1800034b6  mov     [rbx+10h], eax
0x1800034b9  mov     edx, 42h ; 'B'; dwInfoLevel
0x1800034be  mov     rcx, rsi; hRequest
0x1800034c1  call    ?InetHttpQueryAndAllocateStringHeader@@YAPEAGPEAXK@Z; InetHttpQueryAndAllocateStringHeader(void *,ulong)
0x1800034c6  mov     rsi, rax
0x1800034c9  test    rax, rax
0x1800034cc  jz      loc_1800033EA
0x1800034d2  xorps   xmm0, xmm0
0x1800034d5  lea     rcx, [rbp+phHash]; phHash
0x1800034d9  xor     eax, eax
0x1800034db  movups  xmmword ptr [rbp+phHash], xmm0
0x1800034df  mov     [rbp+var_28], rax
0x1800034e3  call    CngRsa32Compat_MD5Init
0x1800034e8  inc     r15
0x1800034eb  cmp     [rsi+r15*2], r12w
0x1800034f0  jnz     short loc_1800034E8
0x1800034f2  lea     r8d, [r15+r15]
0x1800034f6  mov     rdx, rsi
0x1800034f9  lea     rcx, [rbp+phHash]
0x1800034fd  call    CngRsa32Compat_MD5Update
0x180003502  cmp     edi, 1
0x180003505  ja      short loc_180003565
0x180003507  lea     rdx, [rbx+8]
0x18000350b  mov     r8d, 8
0x180003511  lea     rcx, [rbp+phHash]
0x180003515  call    CngRsa32Compat_MD5Update
0x18000351a  lea     rcx, [rbp+phHash]
0x18000351e  call    CngRsa32Compat_MD5Final
0x180003523  mov     ecx, dword ptr [rbp+phHash+8]
0x180003526  mov     [rbx+20h], ecx
0x180003529  jmp     loc_1800033EA
0x18000352e  lea     rdx, [rbp+hRequest]; lpFileTime
0x180003532  mov     [rbp+hRequest], r12
0x180003536  lea     rcx, [rbp+Buffer]; lpSystemTime
0x18000353a  call    cs:__imp_SystemTimeToFileTime
0x180003540  test    eax, eax
0x180003542  jz      loc_180003499
0x180003548  mov     rax, [rbp+hRequest]
0x18000354c  mov     [rbx+8], rax
0x180003550  jmp     loc_180003499
0x180003555  mov     ecx, 216h; dwErrCode
0x18000355a  call    cs:__imp_SetLastError
0x180003560  jmp     loc_1800033EA
0x180003565  mov     rdx, [rbx+18h]
0x180003569  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[rdi*2]
0x180003571  lea     rcx, [rbp+phHash]
0x180003575  call    CngRsa32Compat_MD5Update
0x18000357a  jmp     short loc_180003507
```
