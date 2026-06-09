# LoadTraceFiles(unsigned __int64,unsigned __int64,TraceFileSource,TraceFileType,ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,uchar)

- ea: `0x18003053c`
- end: `0x180030977`
- name: `?LoadTraceFiles@@YAJ_K0W4TraceFileSource@@W4TraceFileType@@PEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@E@Z`
- size: `1083`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 *, __int64, char)`
- caller_count: `3`
- callee_count: `18`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180041060`
- `0x1800424e0`
- `0x1800778f0`

## callees

- `0x180008740`
- `0x180008d2c`
- `0x18001c8cc`
- `0x18001cbe8`
- `0x18001ce44`
- `0x18003053c`
- `0x180030bec`
- `0x180039648`
- `0x18003bb60`
- `0x18003bf74`
- `0x180041c5c`
- `0x180045d70`
- `0x180045da8`
- `0x180045e00`
- `0x18004ca90`
- `0x18004d8fc`
- `0x1800776c0`
- `0x180077f30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180030772`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180030772`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800307df`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800307df`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180030910`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180030910`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800308ff`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800308ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030792`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800306d8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180030752`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800306d8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180030752`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall LoadTraceFiles(__int64 a1, __int64 a2, int a3, int a4, unsigned __int16 *a5, __int64 a6, char a7)
{
  unsigned __int64 v11; // rdx
  int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rcx
  FILETIME v15; // rdi
  int SleepStudyTraceDirectory; // eax
  const wchar_t *v17; // rcx
  size_t v18; // r8
  size_t v19; // rdx
  size_t *v20; // r8
  const WCHAR *v21; // r8
  size_t v22; // rdx
  HANDLE FirstFileW; // r14
  signed int LastError; // eax
  size_t v25; // rdi
  size_t v26; // rdx
  size_t v27; // rax
  __int64 v28; // r8
  unsigned __int64 v29; // rbx
  size_t v30; // rcx
  unsigned __int16 **v31; // rcx
  unsigned __int64 v32; // rdx
  unsigned __int16 **v33; // r8
  _WORD *v34; // rdi
  unsigned __int64 i; // rcx
  unsigned __int16 *v36; // rcx
  size_t v38; // [rsp+20h] [rbp-708h]
  FILETIME FileTime2; // [rsp+38h] [rbp-6F0h] BYREF
  unsigned __int16 *v40[2]; // [rsp+40h] [rbp-6E8h] BYREF
  size_t v41; // [rsp+50h] [rbp-6D8h]
  unsigned __int64 v42; // [rsp+58h] [rbp-6D0h]
  __int128 v43; // [rsp+60h] [rbp-6C8h] BYREF
  __int128 v44; // [rsp+70h] [rbp-6B8h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-6A8h] BYREF
  WCHAR pszPath[264]; // [rsp+2D0h] [rbp-458h] BYREF
  wchar_t pszDest[264]; // [rsp+4E0h] [rbp-248h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FileTime2 = 0;
  *(_OWORD *)v40 = 0;
  v41 = 0;
  v42 = 0;
  std::wstring::_Construct_empty(v40);
  if ( a3 == 1 )
  {
    v12 = v11;
    if ( a2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      LOWORD(v11) = 0;
    }
    v43 = 0;
    v44 = 0;
    v13 = -1;
    do
      ++v13;
    while ( a5[v13] != (_WORD)v11 );
    std::wstring::_Construct<1,unsigned short const *>(&v43, a5, v13);
    v14 = *(_QWORD *)(a6 + 8);
    if ( v14 == *(_QWORD *)(a6 + 16) )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a6, *(_QWORD *)(a6 + 8), &v43);
    }
    else
    {
      std::wstring::wstring(v14, (__int64)&v43);
      *(_QWORD *)(a6 + 8) += 32LL;
    }
    if ( *((_QWORD *)&v44 + 1) > 7u )
      std::_Deallocate<16>((void *)v43, 2LL * *((_QWORD *)&v44 + 1) + 2);
    goto LABEL_65;
  }
  v15 = (FILETIME)(a1 - a2);
  FileTime2 = v15;
  if ( a7 == (_BYTE)v11 && !a2 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v15 = FileTime2;
  }
  if ( !*(_QWORD *)&v15 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 )
  {
    SleepStudyTraceDirectory = GetSleepStudyTraceDirectory(pszPath);
    goto LABEL_20;
  }
  if ( a3 == 2 )
  {
    SleepStudyTraceDirectory = StringCchCopyW(pszPath, v11, a5);
LABEL_20:
    v12 = SleepStudyTraceDirectory;
    if ( SleepStudyTraceDirectory < 0 )
      goto LABEL_65;
    goto LABEL_23;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_23:
  if ( a4 != 2 || (v12 = PathCchAppend(pszPath, 0x104u, L"ScreenOn"), v12 >= 0) )
  {
    v12 = StringValidateDestW(v17, 0x104u, v18);
    if ( v12 < 0 )
    {
      pszDest[0] = 0;
      goto LABEL_65;
    }
    v12 = StringCopyWorkerW(pszDest, v19, v20, pszPath, v38);
    if ( v12 < 0 )
      goto LABEL_65;
    if ( a4 )
    {
      if ( a4 == 1 )
      {
        v21 = L"user-not-present-*.etl";
      }
      else
      {
        if ( a4 != 2 )
          goto LABEL_65;
        v21 = L"ScreenOn*.etl";
      }
    }
    else
    {
      v21 = L"sleepstudy-trace-*.etl";
    }
    v12 = PathCchAppend(pszDest, 0x104u, v21);
    if ( v12 >= 0 )
    {
      FirstFileW = FindFirstFileW(pszDest, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        if ( GetLastError() - 2 <= 1 )
        {
          v12 = -2147220989;
          goto LABEL_65;
        }
        goto LABEL_36;
      }
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0
          && (a7 || CompareFileTime(&FindFileData.ftCreationTime, &FileTime2) >= 0) )
        {
          v25 = wcsnlen_s(FindFileData.cFileName, v22);
          v27 = wcsnlen_s(pszPath, v26);
          v29 = v25 + v27 + 2;
          v30 = v41;
          if ( v29 > v41 )
          {
            v32 = v29 - v41;
            if ( v29 - v41 > v42 - v41 )
            {
              std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(
                v40,
                v32,
                v28,
                v29 - v41);
            }
            else
            {
              v41 = v25 + v27 + 2;
              v33 = v40;
              if ( v42 > 7 )
                v33 = (unsigned __int16 **)v40[0];
              v34 = (_WORD *)v33 + v30;
              if ( v32 )
              {
                for ( i = v29 - v30; i; --i )
                  *v34++ = 0;
              }
              *((_WORD *)v33 + v29) = 0;
            }
          }
          else
          {
            v41 = v25 + v27 + 2;
            v31 = v40;
            if ( v42 > 7 )
              v31 = (unsigned __int16 **)v40[0];
            *((_WORD *)v31 + v29) = 0;
          }
          v36 = (unsigned __int16 *)v40;
          if ( v42 > 7 )
            v36 = v40[0];
          v12 = StringCchPrintfW(v36, v29, L"%s\\%s", pszPath, FindFileData.cFileName);
          if ( v12 < 0 )
            goto LABEL_65;
          if ( *(_QWORD *)(a6 + 8) == *(_QWORD *)(a6 + 16) )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a6, *(_QWORD *)(a6 + 8), v40);
          }
          else
          {
            std::wstring::wstring(*(_QWORD *)(a6 + 8), v40);
            *(_QWORD *)(a6 + 8) += 32LL;
          }
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      if ( !FindClose(FirstFileW) )
      {
LABEL_36:
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
LABEL_65:
  if ( v42 > 7 )
    std::_Deallocate<16>(v40[0], 2 * v42 + 2);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003053c  mov     [rsp+arg_10], rbx
0x180030541  push    rsi
0x180030542  push    rdi
0x180030543  push    r12
0x180030545  push    r14
0x180030547  push    r15
0x180030549  sub     rsp, 700h
0x180030550  mov     rax, cs:__security_cookie
0x180030557  xor     rax, rsp
0x18003055a  mov     [rsp+728h+var_38], rax
0x180030562  mov     r14d, r9d
0x180030565  mov     r15d, r8d
0x180030568  mov     rbx, rdx
0x18003056b  mov     rdi, rcx
0x18003056e  mov     r12, [rsp+728h+arg_20]
0x180030576  mov     rsi, [rsp+728h+arg_28]
0x18003057e  xor     edx, edx; Val
0x180030580  mov     r8d, 250h; Size
0x180030586  lea     rcx, [rsp+728h+FindFileData]; void *
0x18003058e  call    memset_0
0x180030593  xor     edx, edx
0x180030595  mov     qword ptr [rsp+728h+FileTime2.dwLowDateTime], rdx
0x18003059a  xorps   xmm0, xmm0
0x18003059d  movups  xmmword ptr [rsp+728h+var_6E8], xmm0
0x1800305a2  mov     [rsp+728h+var_6D8], rdx
0x1800305a7  mov     [rsp+728h+var_6D0], rdx
0x1800305ac  lea     rcx, [rsp+728h+var_6E8]
0x1800305b1  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800305b6  nop
0x1800305b7  cmp     r15d, 1
0x1800305bb  jnz     loc_180030651
0x1800305c1  mov     edi, edx
0x1800305c3  test    rbx, rbx
0x1800305c6  jz      short loc_1800305CF
0x1800305c8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800305cd  xor     edx, edx
0x1800305cf  xorps   xmm0, xmm0
0x1800305d2  movups  [rsp+728h+var_6C8], xmm0
0x1800305d7  xorps   xmm1, xmm1
0x1800305da  movdqu  [rsp+728h+var_6B8], xmm1
0x1800305e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800305e4  inc     rax
0x1800305e7  cmp     [r12+rax*2], dx
0x1800305ec  jnz     short loc_1800305E4
0x1800305ee  mov     r8, rax
0x1800305f1  mov     rdx, r12
0x1800305f4  lea     rcx, [rsp+728h+var_6C8]
0x1800305f9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800305fe  nop
0x1800305ff  mov     rcx, [rsi+8]
0x180030603  cmp     rcx, [rsi+10h]
0x180030607  jz      short loc_18003061A
0x180030609  lea     rdx, [rsp+728h+var_6C8]
0x18003060e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180030613  add     qword ptr [rsi+8], 20h ; ' '
0x180030618  jmp     short loc_18003062B
0x18003061a  lea     r8, [rsp+728h+var_6C8]
0x18003061f  mov     rdx, rcx
0x180030622  mov     rcx, rsi
0x180030625  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18003062a  nop
0x18003062b  mov     rdx, qword ptr [rsp+728h+var_6B8+8]
0x180030630  cmp     rdx, 7
0x180030634  jbe     loc_180030930
0x18003063a  lea     rdx, ds:2[rdx*2]
0x180030642  mov     rcx, qword ptr [rsp+728h+var_6C8]
0x180030647  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003064c  jmp     loc_180030930
0x180030651  sub     rdi, rbx
0x180030654  mov     qword ptr [rsp+728h+FileTime2.dwLowDateTime], rdi
0x180030659  cmp     [rsp+728h+arg_30], dl
0x180030660  jnz     short loc_180030671
0x180030662  test    rbx, rbx
0x180030665  jnz     short loc_180030671
0x180030667  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003066c  mov     rdi, qword ptr [rsp+728h+FileTime2.dwLowDateTime]
0x180030671  test    rdi, rdi
0x180030674  jnz     short loc_18003067B
0x180030676  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003067b  test    r15d, r15d
0x18003067e  jnz     short loc_18003068F
0x180030680  lea     rcx, [rsp+728h+pszPath]; unsigned __int16 *
0x180030688  call    GetSleepStudyTraceDirectory
0x18003068d  jmp     short loc_1800306A5
0x18003068f  cmp     r15d, 2
0x180030693  jnz     short loc_1800306B4
0x180030695  mov     r8, r12; unsigned __int16 *
0x180030698  lea     rcx, [rsp+728h+pszPath]; unsigned __int16 *
0x1800306a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800306a5  mov     edi, eax
0x1800306a7  xor     r15d, r15d
0x1800306aa  test    eax, eax
0x1800306ac  js      loc_180030930
0x1800306b2  jmp     short loc_1800306BC
0x1800306b4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800306b9  xor     r15d, r15d
0x1800306bc  mov     ebx, 104h
0x1800306c1  cmp     r14d, 2
0x1800306c5  jnz     short loc_1800306E8
0x1800306c7  lea     r8, pszMore; "ScreenOn"
0x1800306ce  mov     edx, ebx; cchPath
0x1800306d0  lea     rcx, [rsp+728h+pszPath]; pszPath
0x1800306d8  call    cs:__imp_PathCchAppend
0x1800306de  mov     edi, eax
0x1800306e0  test    eax, eax
0x1800306e2  js      loc_180030930
0x1800306e8  mov     rdx, rbx; cchDest
0x1800306eb  call    StringValidateDestW
0x1800306f0  mov     edi, eax
0x1800306f2  test    eax, eax
0x1800306f4  js      loc_180030927
0x1800306fa  lea     r9, [rsp+728h+pszPath]; pszSrc
0x180030702  lea     rcx, [rsp+728h+pszDest]; pszDest
0x18003070a  call    StringCopyWorkerW
0x18003070f  mov     edi, eax
0x180030711  test    eax, eax
0x180030713  js      loc_180030930
0x180030719  test    r14d, r14d
0x18003071c  jnz     short loc_180030727
0x18003071e  lea     r8, aSleepstudyTrac; "sleepstudy-trace-*.etl"
0x180030725  jmp     short loc_180030747
0x180030727  cmp     r14d, 1
0x18003072b  jnz     short loc_180030736
0x18003072d  lea     r8, aUserNotPresent; "user-not-present-*.etl"
0x180030734  jmp     short loc_180030747
0x180030736  cmp     r14d, 2
0x18003073a  jnz     loc_180030930
0x180030740  lea     r8, aScreenonEtl; "ScreenOn*.etl"
0x180030747  mov     rdx, rbx; cchPath
0x18003074a  lea     rcx, [rsp+728h+pszDest]; pszPath
0x180030752  call    cs:__imp_PathCchAppend
0x180030758  mov     edi, eax
0x18003075a  test    eax, eax
0x18003075c  js      loc_180030930
0x180030762  lea     rdx, [rsp+728h+FindFileData]; lpFindFileData
0x18003076a  lea     rcx, [rsp+728h+pszDest]; lpFileName
0x180030772  call    cs:__imp_FindFirstFileW
0x180030778  mov     r14, rax
0x18003077b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003077f  cmp     r14, rax
0x180030782  jnz     short loc_1800307BA
0x180030784  call    cs:__imp_GetLastError
0x18003078a  add     eax, 0FFFFFFFEh
0x18003078d  cmp     eax, 1
0x180030790  jbe     short loc_1800307B0
0x180030792  call    cs:__imp_GetLastError
0x180030798  mov     edi, eax
0x18003079a  test    eax, eax
0x18003079c  jle     loc_180030930
0x1800307a2  movzx   edi, ax
0x1800307a5  or      edi, 80070000h
0x1800307ab  jmp     loc_180030930
0x1800307b0  mov     edi, 80040203h
0x1800307b5  jmp     loc_180030930
0x1800307ba  test    byte ptr [rsp+728h+FindFileData.dwFileAttributes], 10h
0x1800307c2  jnz     loc_1800308F4
0x1800307c8  cmp     [rsp+728h+arg_30], r15b
0x1800307d0  jnz     short loc_1800307ED
0x1800307d2  lea     rdx, [rsp+728h+FileTime2]; lpFileTime2
0x1800307d7  lea     rcx, [rsp+728h+FindFileData.ftCreationTime]; lpFileTime1
0x1800307df  call    cs:__imp_CompareFileTime
0x1800307e5  test    eax, eax
0x1800307e7  js      loc_1800308F4
0x1800307ed  lea     rcx, [rsp+728h+FindFileData.cFileName]; Source
0x1800307f5  call    wcsnlen_s
0x1800307fa  mov     rdi, rax
0x1800307fd  lea     rcx, [rsp+728h+pszPath]; Source
0x180030805  call    wcsnlen_s
0x18003080a  lea     rbx, [rax+2]
0x18003080e  add     rbx, rdi
0x180030811  mov     rcx, [rsp+728h+var_6D8]
0x180030816  cmp     rbx, rcx
0x180030819  ja      short loc_180030838
0x18003081b  mov     [rsp+728h+var_6D8], rbx
0x180030820  lea     rcx, [rsp+728h+var_6E8]
0x180030825  cmp     [rsp+728h+var_6D0], 7
0x18003082b  cmova   rcx, [rsp+728h+var_6E8]
0x180030831  mov     [rcx+rbx*2], r15w
0x180030836  jmp     short loc_180030888
0x180030838  mov     rdx, rbx
0x18003083b  sub     rdx, rcx
0x18003083e  mov     rax, [rsp+728h+var_6D0]
0x180030843  sub     rax, rcx
0x180030846  cmp     rdx, rax
0x180030849  ja      short loc_18003087B
0x18003084b  mov     [rsp+728h+var_6D8], rbx
0x180030850  lea     r8, [rsp+728h+var_6E8]
0x180030855  cmp     [rsp+728h+var_6D0], 7
0x18003085b  cmova   r8, [rsp+728h+var_6E8]
0x180030861  lea     rdi, [r8+rcx*2]
0x180030865  test    rdx, rdx
0x180030868  jz      short loc_180030874
0x18003086a  movzx   eax, r15w
0x18003086e  mov     rcx, rdx
0x180030871  rep stosw
0x180030874  mov     [r8+rbx*2], r15w
0x180030879  jmp     short loc_180030888
0x18003087b  mov     r9, rdx
0x18003087e  lea     rcx, [rsp+728h+var_6E8]
0x180030883  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180030888  lea     rcx, [rsp+728h+var_6E8]
0x18003088d  cmp     [rsp+728h+var_6D0], 7
0x180030893  cmova   rcx, [rsp+728h+var_6E8]; unsigned __int16 *
0x180030899  lea     rax, [rsp+728h+FindFileData.cFileName]
0x1800308a1  mov     [rsp+728h+var_708], rax
0x1800308a6  lea     r9, [rsp+728h+pszPath]
0x1800308ae  lea     r8, aSS; "%s\\%s"
0x1800308b5  mov     rdx, rbx; unsigned __int64
0x1800308b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800308bd  mov     edi, eax
0x1800308bf  test    eax, eax
0x1800308c1  jns     short loc_1800308C5
0x1800308c3  jmp     short loc_180030930
0x1800308c5  mov     rax, [rsi+8]
0x1800308c9  cmp     rax, [rsi+10h]
0x1800308cd  jz      short loc_1800308E3
0x1800308cf  lea     rdx, [rsp+728h+var_6E8]
0x1800308d4  mov     rcx, rax
0x1800308d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800308dc  add     qword ptr [rsi+8], 20h ; ' '
0x1800308e1  jmp     short loc_1800308F4
0x1800308e3  lea     r8, [rsp+728h+var_6E8]
0x1800308e8  mov     rdx, rax
0x1800308eb  mov     rcx, rsi
0x1800308ee  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1800308f3  nop
0x1800308f4  lea     rdx, [rsp+728h+FindFileData]; lpFindFileData
0x1800308fc  mov     rcx, r14; hFindFile
0x1800308ff  call    cs:__imp_FindNextFileW
0x180030905  test    eax, eax
0x180030907  jnz     loc_1800307BA
0x18003090d  mov     rcx, r14; hFindFile
0x180030910  call    cs:__imp_FindClose
0x180030916  test    eax, eax
0x180030918  jnz     short loc_180030930
0x18003091a  jmp     loc_180030792
0x18003091f  mov     edi, [rsp+728h+var_6F8]
0x180030923  jmp     short loc_180030930
0x180030925  jmp     short loc_18003091F
0x180030927  mov     [rsp+728h+pszDest], r15w
0x180030930  mov     rdx, [rsp+728h+var_6D0]
0x180030935  cmp     rdx, 7
0x180030939  jbe     short loc_18003094D
0x18003093b  lea     rdx, ds:2[rdx*2]
0x180030943  mov     rcx, [rsp+728h+var_6E8]
0x180030948  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003094d  mov     eax, edi
0x18003094f  mov     rcx, [rsp+728h+var_38]
0x180030957  xor     rcx, rsp; StackCookie
0x18003095a  call    __security_check_cookie
0x18003095f  mov     rbx, [rsp+728h+arg_10]
0x180030967  add     rsp, 700h
0x18003096e  pop     r15
0x180030970  pop     r14
0x180030972  pop     r12
0x180030974  pop     rdi
0x180030975  pop     rsi
0x180030976  retn
```
