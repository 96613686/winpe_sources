# CHttpBase::GetResponse(void)

- ea: `0x1800454ec`
- end: `0x1800458cb`
- name: `?GetResponse@CHttpBase@@IEAAJXZ`
- size: `991`
- prototype: `__int64 __fastcall(CHttpBase *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180043bc0`
- `0x180045c78`
- `0x180046c7c`

## callees

- `0x180001284`
- `0x180001290`
- `0x180003416`
- `0x180004654`
- `0x1800046c8`
- `0x1800454ec`
- `0x18005bd72`
- `0x18005bdc0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180045801`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180045801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800455a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800456a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800455a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800456a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045860`
- `WINHTTP!WinHttpReadData` at `0x1800457bd`
- `WINHTTP!WinHttpReadData` at `0x1800457bd`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800456eb`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800456eb`
- `WINHTTP!WinHttpQueryOption` at `0x18004558c`
- `WINHTTP!WinHttpQueryOption` at `0x180045621`
- `WINHTTP!WinHttpQueryOption` at `0x18004558c`
- `WINHTTP!WinHttpQueryOption` at `0x180045621`
- `WINHTTP!WinHttpQueryHeaders` at `0x18004567f`
- `WINHTTP!WinHttpQueryHeaders` at `0x18004567f`
- `WININET!InternetQueryOptionW` at `0x180045594`
- `WININET!InternetQueryOptionW` at `0x180045629`
- `WININET!InternetQueryOptionW` at `0x180045594`
- `WININET!InternetQueryOptionW` at `0x180045629`
- `WININET!InternetQueryDataAvailable` at `0x1800456f9`
- `WININET!InternetQueryDataAvailable` at `0x1800456f9`
- `WININET!InternetReadFile` at `0x1800457c5`
- `WININET!InternetReadFile` at `0x1800457c5`
- `WININET!HttpQueryInfoW` at `0x180045698`
- `WININET!HttpQueryInfoW` at `0x180045698`

## pseudocode

```c
__int64 __fastcall CHttpBase::GetResponse(CHttpBase *this)
{
  DWORD v1; // r14d
  void *v3; // r13
  char *v4; // r15
  signed int v5; // ebx
  DWORD v6; // r11d
  void *v7; // rcx
  signed int LastError; // eax
  unsigned __int64 v9; // kr00_8
  void *v10; // rax
  void *v11; // rcx
  BOOL v12; // eax
  DWORD v13; // r12d
  void *v14; // rcx
  BOOL v15; // eax
  DWORD v16; // eax
  void *v17; // rcx
  BOOL v18; // eax
  DWORD v19; // r8d
  DWORD v20; // edi
  char *v21; // rax
  void *v22; // rcx
  char *v23; // rdx
  DWORD v25; // edi
  void *v26; // rcx
  int (__fastcall *v27)(_QWORD, __int64, unsigned int *, _QWORD); // rax
  signed int v28; // eax
  DWORD Buffer; // [rsp+30h] [rbp-39h] BYREF
  DWORD dwNumberOfBytesAvailable; // [rsp+34h] [rbp-35h] BYREF
  DWORD dwBufferLength; // [rsp+38h] [rbp-31h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+3Ch] [rbp-2Dh] BYREF
  unsigned int v34; // [rsp+40h] [rbp-29h] BYREF
  DWORD lpdwBufferLength; // [rsp+44h] [rbp-25h] BYREF
  DWORD dwIndex; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int16 v37[20]; // [rsp+50h] [rbp-19h] BYREF

  v1 = 0;
  lpdwBufferLength = 4;
  dwNumberOfBytesRead = 0;
  dwNumberOfBytesAvailable = 0;
  Buffer = 0;
  dwIndex = 0;
  v34 = 0;
  v3 = 0;
  dwBufferLength = 0;
  v4 = 0;
  v5 = StringCchCopyW(v37, 0x14u, &Src);
  if ( v5 < 0 )
    goto LABEL_65;
  v7 = (void *)*((_QWORD *)this + 13);
  Buffer = v6;
  if ( !v7 )
  {
LABEL_3:
    v5 = -2147024809;
    goto LABEL_65;
  }
  if ( g_fGlobalOptionUseWinhttp )
    WinHttpQueryOption(v7, 0x22u, 0, &dwBufferLength);
  else
    InternetQueryOptionW(v7, 0x22u, 0, &dwBufferLength);
  if ( !dwBufferLength )
    goto LABEL_8;
  operator delete(*((void **)this + 20));
  v9 = dwBufferLength;
  *((_QWORD *)this + 20) = 0;
  v10 = operator new[](saturated_mul(v9, 2u));
  *((_QWORD *)this + 20) = v10;
  if ( !v10 )
  {
LABEL_14:
    v5 = -2147024882;
    goto LABEL_65;
  }
  v11 = (void *)*((_QWORD *)this + 13);
  if ( g_fGlobalOptionUseWinhttp )
    v12 = WinHttpQueryOption(v11, 0x22u, v10, &dwBufferLength);
  else
    v12 = InternetQueryOptionW(v11, 0x22u, v10, &dwBufferLength);
  if ( !v12 )
  {
LABEL_8:
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    goto LABEL_65;
  }
  v13 = 0;
  _RTLTRACE("[msdrm]:Response Url=%S\n", *((const wchar_t **)this + 20));
  v14 = (void *)*((_QWORD *)this + 13);
  if ( g_fGlobalOptionUseWinhttp )
    v15 = WinHttpQueryHeaders(
            v14,
            0x20000005u,
            g_wszWINHTTP_HEADER_NAME_BY_INDEX,
            &Buffer,
            &lpdwBufferLength,
            lpdwWINHTTP_NO_HEADER_INDEX);
  else
    v15 = HttpQueryInfoW(v14, 0x20000005u, &Buffer, &lpdwBufferLength, &dwIndex);
  if ( v15 )
  {
    v16 = Buffer;
  }
  else
  {
    GetLastError();
    v16 = 0;
    Buffer = 0;
  }
  if ( v16 )
  {
    if ( v16 == -1 )
      goto LABEL_3;
    v4 = (char *)operator new[](v16);
    if ( v4 )
    {
      v13 = Buffer;
      v5 = 0;
      goto LABEL_29;
    }
    goto LABEL_14;
  }
  while ( 1 )
  {
LABEL_29:
    v17 = (void *)*((_QWORD *)this + 13);
    if ( g_fGlobalOptionUseWinhttp )
      v18 = WinHttpQueryDataAvailable(v17, &dwNumberOfBytesAvailable);
    else
      v18 = InternetQueryDataAvailable(v17, &dwNumberOfBytesAvailable, 0, 0);
    if ( !v18 || (v19 = dwNumberOfBytesAvailable) == 0 )
    {
      *((_DWORD *)this + 30) = GetLastError();
LABEL_61:
      if ( Buffer && v1 < Buffer )
      {
        v5 = -2147168444;
      }
      else
      {
        operator delete(*((void **)this + 16));
        *((_QWORD *)this + 16) = v4;
        v4 = 0;
        *((_DWORD *)this + 34) = v1;
      }
      goto LABEL_65;
    }
    v20 = v1 + dwNumberOfBytesAvailable;
    if ( v1 + dwNumberOfBytesAvailable < v1 || v20 < dwNumberOfBytesAvailable )
      goto LABEL_3;
    v5 = 0;
    v34 = 0;
    if ( Buffer )
    {
      if ( v20 > 0x28F5C28 )
      {
        v5 = v20 > 0x28F5C28 ? 0x80070057 : 0;
        goto LABEL_65;
      }
      v34 = 100 * v20 / Buffer;
    }
    if ( v13 < v20 )
    {
      v3 = v4;
      v21 = (char *)operator new[](v20);
      v4 = v21;
      if ( !v21 )
        goto LABEL_14;
      memset_0(v21, 0, v20);
      memcpy_0(v4, v3, v20 - dwNumberOfBytesAvailable);
      if ( v3 )
      {
        operator delete(v3);
        v3 = 0;
      }
      v19 = dwNumberOfBytesAvailable;
      v13 = v20;
    }
    v22 = (void *)*((_QWORD *)this + 13);
    v23 = &v4[v20 - (unsigned __int64)v19];
    if ( !(g_fGlobalOptionUseWinhttp
         ? WinHttpReadData(v22, v23, v19, &dwNumberOfBytesRead)
         : InternetReadFile(v22, v23, v19, &dwNumberOfBytesRead)) )
      break;
    v1 = v20;
    if ( !dwNumberOfBytesRead )
      goto LABEL_61;
    v25 = v20 - dwNumberOfBytesAvailable;
    v1 = v25 + dwNumberOfBytesRead;
    if ( v25 + dwNumberOfBytesRead < v25 || v1 < dwNumberOfBytesRead )
      goto LABEL_3;
    v26 = (void *)*((_QWORD *)this + 10);
    if ( v26 && !WaitForSingleObject(v26, 0)
      || (v27 = (int (__fastcall *)(_QWORD, __int64, unsigned int *, _QWORD))*((_QWORD *)this + 1)) != 0
      && v27(*((unsigned int *)this + 4), 315141, &v34, *((_QWORD *)this + 3)) < 0 )
    {
      v5 = -2147168447;
      goto LABEL_65;
    }
    v5 = 0;
  }
  v28 = GetLastError();
  *((_DWORD *)this + 30) = v28;
  v5 = v28;
  if ( v28 > 0 )
    v5 = (unsigned __int16)v28 | 0x80070000;
LABEL_65:
  operator delete(v3);
  operator delete(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800454ec  push    rbp
0x1800454ee  push    rbx
0x1800454ef  push    rsi
0x1800454f0  push    rdi
0x1800454f1  push    r12
0x1800454f3  push    r13
0x1800454f5  push    r14
0x1800454f7  push    r15
0x1800454f9  lea     rbp, [rsp-1Fh]
0x1800454fe  sub     rsp, 88h
0x180045505  mov     rax, cs:__security_cookie
0x18004550c  xor     rax, rsp
0x18004550f  mov     [rbp+57h+var_48], rax
0x180045513  xor     r14d, r14d
0x180045516  mov     [rbp+57h+var_7C], 4
0x18004551d  mov     rsi, rcx
0x180045520  mov     [rbp+57h+dwNumberOfBytesRead], r14d
0x180045524  lea     r8, Src; unsigned __int16 *
0x18004552b  mov     [rbp+57h+dwNumberOfBytesAvailable], r14d
0x18004552f  lea     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180045533  mov     [rbp+57h+Buffer], r14d
0x180045537  lea     r11d, [r14+14h]
0x18004553b  mov     [rbp+57h+dwIndex], r14d
0x18004553f  mov     edx, r11d; unsigned __int64
0x180045542  mov     [rbp+57h+var_80], r14d
0x180045546  mov     r13d, r14d
0x180045549  mov     [rbp+57h+dwBufferLength], r14d
0x18004554d  mov     r15d, r14d
0x180045550  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180045555  mov     ebx, eax
0x180045557  test    eax, eax
0x180045559  js      loc_180045899
0x18004555f  mov     rcx, [rsi+68h]; hInternet
0x180045563  mov     [rbp+57h+Buffer], r11d
0x180045567  test    rcx, rcx
0x18004556a  jnz     short loc_180045576
0x18004556c  mov     ebx, 80070057h
0x180045571  jmp     loc_180045899
0x180045576  xor     r8d, r8d; lpBuffer
0x180045579  lea     r9, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x18004557d  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r14d; int g_fGlobalOptionUseWinhttp
0x180045584  lea     edi, [r8+22h]
0x180045588  mov     edx, edi; dwOption
0x18004558a  jz      short loc_180045594
0x18004558c  call    cs:__imp_WinHttpQueryOption
0x180045592  jmp     short loc_18004559A
0x180045594  call    cs:__imp_InternetQueryOptionW
0x18004559a  cmp     [rbp+57h+dwBufferLength], r14d
0x18004559e  ja      short loc_1800455C4
0x1800455a0  call    cs:__imp_GetLastError
0x1800455a6  mov     ebx, eax
0x1800455a8  test    eax, eax
0x1800455aa  jle     short loc_1800455B5
0x1800455ac  movzx   ebx, ax
0x1800455af  or      ebx, 80070000h
0x1800455b5  test    ebx, ebx
0x1800455b7  mov     eax, 80004005h
0x1800455bc  cmovns  ebx, eax
0x1800455bf  jmp     loc_180045899
0x1800455c4  mov     rcx, [rsi+0A0h]; Block
0x1800455cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800455d0  mov     ecx, [rbp+57h+dwBufferLength]
0x1800455d3  mov     eax, 2
0x1800455d8  mul     rcx
0x1800455db  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800455e2  mov     [rsi+0A0h], r14
0x1800455e9  cmovb   rax, rcx
0x1800455ed  mov     rcx, rax; unsigned __int64
0x1800455f0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800455f5  mov     [rsi+0A0h], rax
0x1800455fc  test    rax, rax
0x1800455ff  jnz     short loc_18004560B
0x180045601  mov     ebx, 8007000Eh
0x180045606  jmp     loc_180045899
0x18004560b  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r14d; int g_fGlobalOptionUseWinhttp
0x180045612  lea     r9, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x180045616  mov     rcx, [rsi+68h]; hInternet
0x18004561a  mov     r8, rax; lpBuffer
0x18004561d  mov     edx, edi; dwOption
0x18004561f  jz      short loc_180045629
0x180045621  call    cs:__imp_WinHttpQueryOption
0x180045627  jmp     short loc_18004562F
0x180045629  call    cs:__imp_InternetQueryOptionW
0x18004562f  test    eax, eax
0x180045631  jz      loc_1800455A0
0x180045637  mov     rdx, [rsi+0A0h]
0x18004563e  lea     rcx, aMsdrmResponseU; "[msdrm]:Response Url=%S\n"
0x180045645  mov     r12d, r14d
0x180045648  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004564d  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r14d; int g_fGlobalOptionUseWinhttp
0x180045654  mov     edx, 20000005h; dwInfoLevel
0x180045659  mov     rcx, [rsi+68h]; hRequest
0x18004565d  jz      short loc_180045687
0x18004565f  mov     rax, cs:?lpdwWINHTTP_NO_HEADER_INDEX@@3PEAKEA; ulong * lpdwWINHTTP_NO_HEADER_INDEX
0x180045666  lea     r9, [rbp+57h+Buffer]; lpBuffer
0x18004566a  mov     r8, cs:?g_wszWINHTTP_HEADER_NAME_BY_INDEX@@3PEAGEA; pwszName
0x180045671  mov     [rsp+0C0h+lpdwIndex], rax; lpdwIndex
0x180045676  lea     rax, [rbp+57h+var_7C]
0x18004567a  mov     [rsp+0C0h+lpdwBufferLength], rax; lpdwBufferLength
0x18004567f  call    cs:__imp_WinHttpQueryHeaders
0x180045685  jmp     short loc_18004569E
0x180045687  lea     rax, [rbp+57h+dwIndex]
0x18004568b  lea     r9, [rbp+57h+var_7C]; lpdwBufferLength
0x18004568f  mov     [rsp+0C0h+lpdwBufferLength], rax; lpdwIndex
0x180045694  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180045698  call    cs:__imp_HttpQueryInfoW
0x18004569e  test    eax, eax
0x1800456a0  jnz     short loc_1800456B0
0x1800456a2  call    cs:__imp_GetLastError
0x1800456a8  mov     eax, r14d
0x1800456ab  mov     [rbp+57h+Buffer], eax
0x1800456ae  jmp     short loc_1800456B3
0x1800456b0  mov     eax, [rbp+57h+Buffer]
0x1800456b3  test    eax, eax
0x1800456b5  jz      short loc_1800456DA
0x1800456b7  cmp     eax, 0FFFFFFFFh
0x1800456ba  jz      loc_18004556C
0x1800456c0  mov     ecx, eax; unsigned __int64
0x1800456c2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800456c7  mov     r15, rax
0x1800456ca  test    rax, rax
0x1800456cd  jz      loc_180045601
0x1800456d3  mov     r12d, [rbp+57h+Buffer]
0x1800456d7  mov     ebx, r14d
0x1800456da  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, 0; int g_fGlobalOptionUseWinhttp
0x1800456e1  lea     rdx, [rbp+57h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1800456e5  mov     rcx, [rsi+68h]; hFile
0x1800456e9  jz      short loc_1800456F3
0x1800456eb  call    cs:__imp_WinHttpQueryDataAvailable
0x1800456f1  jmp     short loc_1800456FF
0x1800456f3  xor     r9d, r9d; dwContext
0x1800456f6  xor     r8d, r8d; dwFlags
0x1800456f9  call    cs:__imp_InternetQueryDataAvailable
0x1800456ff  test    eax, eax
0x180045701  jz      loc_180045860
0x180045707  mov     r8d, [rbp+57h+dwNumberOfBytesAvailable]
0x18004570b  test    r8d, r8d
0x18004570e  jz      loc_180045860
0x180045714  lea     edi, [r14+r8]
0x180045718  cmp     edi, r14d
0x18004571b  jb      loc_18004556C
0x180045721  cmp     edi, r8d
0x180045724  jb      loc_18004556C
0x18004572a  mov     ecx, [rbp+57h+Buffer]
0x18004572d  xor     ebx, ebx
0x18004572f  mov     [rbp+57h+var_80], ebx
0x180045732  test    ecx, ecx
0x180045734  jz      short loc_18004574D
0x180045736  mov     eax, 28F5C28h
0x18004573b  cmp     eax, edi
0x18004573d  jb      loc_180045834
0x180045743  imul    eax, edi, 64h ; 'd'
0x180045746  xor     edx, edx
0x180045748  div     ecx
0x18004574a  mov     [rbp+57h+var_80], eax
0x18004574d  cmp     r12d, edi
0x180045750  jnb     short loc_1800457A1
0x180045752  mov     ecx, edi; unsigned __int64
0x180045754  mov     r13, r15
0x180045757  mov     r14d, edi
0x18004575a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004575f  mov     r15, rax
0x180045762  test    rax, rax
0x180045765  jz      loc_180045601
0x18004576b  mov     r8d, r14d; Size
0x18004576e  xor     edx, edx; Val
0x180045770  mov     rcx, rax; void *
0x180045773  call    memset_0
0x180045778  mov     r8d, edi
0x18004577b  mov     rdx, r13; Src
0x18004577e  sub     r8d, [rbp+57h+dwNumberOfBytesAvailable]; Size
0x180045782  mov     rcx, r15; void *
0x180045785  call    memcpy_0
0x18004578a  test    r13, r13
0x18004578d  jz      short loc_18004579A
0x18004578f  mov     rcx, r13; Block
0x180045792  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180045797  xor     r13d, r13d
0x18004579a  mov     r8d, [rbp+57h+dwNumberOfBytesAvailable]; dwNumberOfBytesToRead
0x18004579e  mov     r12d, edi
0x1800457a1  mov     rcx, [rsi+68h]; hFile
0x1800457a5  lea     r9, [rbp+57h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1800457a9  mov     edx, edi
0x1800457ab  mov     eax, r8d
0x1800457ae  sub     rdx, rax
0x1800457b1  add     rdx, r15; lpBuffer
0x1800457b4  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, 0; int g_fGlobalOptionUseWinhttp
0x1800457bb  jz      short loc_1800457C5
0x1800457bd  call    cs:__imp_WinHttpReadData
0x1800457c3  jmp     short loc_1800457CB
0x1800457c5  call    cs:__imp_InternetReadFile
0x1800457cb  test    eax, eax
0x1800457cd  jz      short loc_180045846
0x1800457cf  mov     eax, [rbp+57h+dwNumberOfBytesRead]
0x1800457d2  mov     r14d, edi
0x1800457d5  test    eax, eax
0x1800457d7  jz      loc_180045869
0x1800457dd  sub     edi, [rbp+57h+dwNumberOfBytesAvailable]
0x1800457e0  lea     r14d, [rdi+rax]
0x1800457e4  cmp     r14d, edi
0x1800457e7  jb      loc_18004556C
0x1800457ed  cmp     r14d, eax
0x1800457f0  jb      loc_18004556C
0x1800457f6  mov     rcx, [rsi+50h]; hHandle
0x1800457fa  test    rcx, rcx
0x1800457fd  jz      short loc_18004580B
0x1800457ff  xor     edx, edx; dwMilliseconds
0x180045801  call    cs:__imp_WaitForSingleObject
0x180045807  test    eax, eax
0x180045809  jz      short loc_18004583F
0x18004580b  mov     rax, [rsi+8]
0x18004580f  test    rax, rax
0x180045812  jz      short loc_18004582D
0x180045814  mov     r9, [rsi+18h]
0x180045818  lea     r8, [rbp+57h+var_80]
0x18004581c  mov     ecx, [rsi+10h]
0x18004581f  mov     edx, 4CF05h
0x180045824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045829  test    eax, eax
0x18004582b  js      short loc_18004583F
0x18004582d  xor     ebx, ebx
0x18004582f  jmp     loc_1800456DA
0x180045834  sbb     eax, eax
0x180045836  mov     ebx, 80070057h
0x18004583b  and     ebx, eax
0x18004583d  jmp     short loc_180045899
0x18004583f  mov     ebx, 8004CF41h
0x180045844  jmp     short loc_180045899
0x180045846  call    cs:__imp_GetLastError
0x18004584c  mov     [rsi+78h], eax
0x18004584f  mov     ebx, eax
0x180045851  test    eax, eax
0x180045853  jle     short loc_180045899
0x180045855  movzx   ebx, ax
0x180045858  or      ebx, 80070000h
0x18004585e  jmp     short loc_180045899
0x180045860  call    cs:__imp_GetLastError
0x180045866  mov     [rsi+78h], eax
0x180045869  mov     eax, [rbp+57h+Buffer]
0x18004586c  test    eax, eax
0x18004586e  jz      short loc_18004587C
0x180045870  cmp     r14d, eax
0x180045873  jnb     short loc_18004587C
0x180045875  mov     ebx, 8004CF44h
0x18004587a  jmp     short loc_180045899
0x18004587c  mov     rcx, [rsi+80h]; Block
0x180045883  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180045888  mov     [rsi+80h], r15
0x18004588f  xor     r15d, r15d
0x180045892  mov     [rsi+88h], r14d
0x180045899  mov     rcx, r13; Block
0x18004589c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800458a1  mov     rcx, r15; Block
0x1800458a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800458a9  mov     eax, ebx
0x1800458ab  mov     rcx, [rbp+57h+var_48]
0x1800458af  xor     rcx, rsp; StackCookie
0x1800458b2  call    __security_check_cookie
0x1800458b7  add     rsp, 88h
0x1800458be  pop     r15
0x1800458c0  pop     r14
0x1800458c2  pop     r13
0x1800458c4  pop     r12
0x1800458c6  pop     rdi
0x1800458c7  pop     rsi
0x1800458c8  pop     rbx
0x1800458c9  pop     rbp
0x1800458ca  retn
```
