# CLogger::Write(LogLevel,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)

- ea: `0x1800354f8`
- end: `0x1800358c6`
- name: `?Write@CLogger@@QEAAXW4LogLevel@@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z`
- size: `974`
- prototype: `__int64 __fastcall(CLogger *this, int, _QWORD *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1800358cc`

## callees

- `0x1800031c0`
- `0x180004850`
- `0x1800048c0`
- `0x180004d40`
- `0x1800059ec`
- `0x180006270`
- `0x180006640`
- `0x180006dcc`
- `0x1800070ec`
- `0x180019084`
- `0x18002a36c`
- `0x18002afa8`
- `0x180034954`
- `0x180034a0c`
- `0x18003505c`
- `0x18003533c`
- `0x180035478`
- `0x1800354f8`
- `0x18003d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wctomb` at `0x18003582a`
- `api-ms-win-crt-private-l1-1-0!_o_wctomb` at `0x18003582a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800356d3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800356d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035699`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035699`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035703`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003571d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003571d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035725`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035725`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800356a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800356a7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180035663`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180035681`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180035663`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180035681`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18003587a`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18003587a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035864`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035864`

## string_xrefs

- `0x18003565c`: `api-ms-win-core-psapi-obsolete-l1-1-0.dll`
- `0x18003567a`: `psapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLogger::Write(CLogger *this, int a2, _QWORD *a3)
{
  __int64 v6; // r15
  __int64 v7; // rdx
  int *v8; // r14
  __int64 v9; // rbx
  int v10; // edi
  int v11; // edi
  const char *v12; // rdx
  HMODULE LibraryW; // rax
  HMODULE v14; // rbx
  const CHAR *v15; // rdx
  FARPROC ProcAddress; // rdi
  HANDLE CurrentProcess; // rax
  char *v18; // rax
  char *v19; // rdx
  __int64 v20; // r8
  DWORD CurrentProcessId; // edi
  DWORD CurrentThreadId; // ebx
  wchar_t *v23; // r14
  int v24; // ebx
  void *v25; // rax
  void *v26; // r15
  char *i; // rdi
  __int64 v28; // rax
  const struct std::nothrow_t *v29; // rdx
  unsigned __int8 v31[8]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v32; // [rsp+38h] [rbp-C8h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+48h] [rbp-B8h] BYREF
  char v35[16]; // [rsp+50h] [rbp-B0h] BYREF
  char Str[272]; // [rsp+60h] [rbp-A0h] BYREF
  char v37[1024]; // [rsp+170h] [rbp+70h] BYREF

  *(_QWORD *)NumberOfBytesWritten = a3;
  v6 = -1;
  if ( *((_QWORD *)this + 6) == -1
    || *((_DWORD *)this + 14) > a2
    || (unsigned int)(*((_DWORD *)this + 16) + *((_DWORD *)this + 15) + *(_DWORD *)(*a3 - 16LL)) > 0x80000
    && !(unsigned int)CLogger::RollOver(this) )
  {
    return ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(a3);
  }
  ATL::CTime::GetTickCount(v35);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v32);
  v7 = *(_QWORD *)ATL::CTime::Format(v35, &v34, L"%m/%d/%Y %H:%M:%S");
  v8 = (int *)(v32 - 12);
  if ( (wchar_t *)(v7 - 24) != v32 - 12 )
  {
    if ( v8[4] >= 0 && *(_QWORD *)(v7 - 24) == *(_QWORD *)v8 )
    {
      v9 = ATL::CSimpleStringT<wchar_t,0>::CloneData();
      ATL::CStringData::Release((ATL::CStringData *)v8);
      v32 = (wchar_t *)(v9 + 24);
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString(&v32, v7, *(unsigned int *)(v7 - 16));
    }
  }
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v34);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&v32, "\t");
  v10 = a2 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 != 1 )
        goto LABEL_17;
      v12 = "error";
    }
    else
    {
      v12 = "warning";
    }
  }
  else
  {
    v12 = "info";
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&v32, v12);
LABEL_17:
  if ( !*(_DWORD *)(*((_QWORD *)this + 2) - 16LL) )
  {
    memset_0(Str, 0, 0x104u);
    LibraryW = LoadLibraryW(L"api-ms-win-core-psapi-obsolete-l1-1-0.dll");
    v14 = LibraryW;
    if ( LibraryW )
    {
      v15 = "K32GetModuleFileNameExA";
    }
    else
    {
      LibraryW = LoadLibraryW(L"psapi.dll");
      v14 = LibraryW;
      if ( !LibraryW )
        goto LABEL_30;
      v15 = "GetModuleFileNameExA";
    }
    ProcAddress = GetProcAddress(LibraryW, v15);
    if ( ProcAddress )
    {
      CurrentProcess = GetCurrentProcess();
      if ( ((unsigned int (__fastcall *)(HANDLE, _QWORD, char *, __int64))ProcAddress)(CurrentProcess, 0, Str, 260) )
      {
        v18 = strrchr(Str, 92);
        v19 = v18 + 1;
        if ( v18 == (char *)-1LL )
        {
          v20 = 0;
LABEL_29:
          ATL::CSimpleStringT<char,0>::SetString((char *)this + 16, v19, v20);
          FreeLibrary(v14);
          goto LABEL_30;
        }
      }
      else
      {
        v19 = Str;
      }
      v20 = -1;
      do
        ++v20;
      while ( v19[v20] );
      goto LABEL_29;
    }
  }
LABEL_30:
  memset_0(v37, 0, sizeof(v37));
  CurrentProcessId = GetCurrentProcessId();
  CurrentThreadId = GetCurrentThreadId();
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&v32, "\t");
  if ( (int)StringCbPrintfA(
              v37,
              0x400u,
              "\t%s (PID:%d TID:%d)\t",
              *((const char **)this + 2),
              CurrentProcessId,
              CurrentThreadId) >= 0 )
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&v32, v37);
  ATL::CSimpleStringT<wchar_t,0>::Append(&v32, *a3, *(unsigned int *)(*a3 - 16LL));
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&v32, "\r\n");
  v23 = v32;
  do
    ++v6;
  while ( v32[v6] );
  v24 = 2 * v6;
  v25 = operator new[](2 * (int)v6 + 1, (const struct std::nothrow_t *)std::nothrow);
  v26 = v25;
  if ( v25 )
  {
    for ( i = (char *)v25; *v23; ++v23 )
    {
      if ( !v24 )
        break;
      if ( (unsigned __int16)(*v23 + 21504) > 0xFFu )
      {
        LODWORD(v28) = wctomb(i, *v23);
        if ( (int)v28 <= 0 )
          v28 = 2;
        v24 -= v28;
        i += v28;
      }
      else if ( v24 >= 2 )
      {
        v31[0] = *(_BYTE *)v23;
        v34 = v24;
        if ( (unsigned int)ATL::AtlHexEncode(v31, 1, i, &v34) )
        {
          i += 2;
          v24 -= 2;
        }
      }
    }
    NumberOfBytesWritten[0] = 0;
    if ( WriteFile(*((HANDLE *)this + 6), v26, (_DWORD)i - (_DWORD)v26, NumberOfBytesWritten, 0) )
    {
      *((_DWORD *)this + 16) += NumberOfBytesWritten[0];
      FlushFileBuffers(*((HANDLE *)this + 6));
    }
    operator delete(v26, v29);
  }
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v32);
  return ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(a3);
}

```

## disassembly

```asm
0x1800354f8  mov     [rsp-8+arg_8], rbx
0x1800354fd  push    rbp
0x1800354fe  push    rsi
0x1800354ff  push    rdi
0x180035500  push    r12
0x180035502  push    r13
0x180035504  push    r14
0x180035506  push    r15
0x180035508  lea     rbp, [rsp-480h]
0x180035510  sub     rsp, 580h
0x180035517  mov     rax, cs:__security_cookie
0x18003551e  xor     rax, rsp
0x180035521  mov     [rbp+4B0h+var_40], rax
0x180035528  mov     r12, r8
0x18003552b  mov     edi, edx
0x18003552d  mov     rsi, rcx
0x180035530  mov     qword ptr [rsp+5B0h+NumberOfBytesWritten], r8
0x180035535  or      r15, 0FFFFFFFFFFFFFFFFh
0x180035539  cmp     [rcx+30h], r15
0x18003553d  jz      loc_180035894
0x180035543  cmp     [rcx+38h], edx
0x180035546  jg      loc_180035894
0x18003554c  mov     rax, [r8]
0x18003554f  mov     ecx, [rax-10h]
0x180035552  add     ecx, [rsi+3Ch]
0x180035555  add     ecx, [rsi+40h]
0x180035558  xor     r13d, r13d
0x18003555b  cmp     ecx, 80000h
0x180035561  jbe     short loc_180035573
0x180035563  mov     rcx, rsi; this
0x180035566  call    ?RollOver@CLogger@@AEAAHXZ; CLogger::RollOver(void)
0x18003556b  test    eax, eax
0x18003556d  jz      loc_180035894
0x180035573  lea     rcx, [rsp+5B0h+var_560]
0x180035578  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x18003557d  lea     rcx, [rsp+5B0h+var_578]
0x180035582  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180035587  nop
0x180035588  lea     r8, aMDYHMS; "%m/%d/%Y %H:%M:%S"
0x18003558f  lea     rdx, [rsp+5B0h+var_568]
0x180035594  lea     rcx, [rsp+5B0h+var_560]
0x180035599  call    ?Format@CTime@ATL@@QEBA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@2@PEB_W@Z; ATL::CTime::Format(wchar_t const *)
0x18003559e  nop
0x18003559f  mov     rdx, [rax]
0x1800355a2  lea     rcx, [rdx-18h]
0x1800355a6  mov     r14, [rsp+5B0h+var_578]
0x1800355ab  add     r14, 0FFFFFFFFFFFFFFE8h
0x1800355af  cmp     rcx, r14
0x1800355b2  jz      short loc_1800355EC
0x1800355b4  cmp     [r14+10h], r13d
0x1800355b8  jl      short loc_1800355DD
0x1800355ba  mov     rax, [r14]
0x1800355bd  cmp     [rcx], rax
0x1800355c0  jnz     short loc_1800355DD
0x1800355c2  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x1800355c7  mov     rbx, rax
0x1800355ca  mov     rcx, r14; this
0x1800355cd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800355d2  lea     rax, [rbx+18h]
0x1800355d6  mov     [rsp+5B0h+var_578], rax
0x1800355db  jmp     short loc_1800355EC
0x1800355dd  mov     r8d, [rdx-10h]
0x1800355e1  lea     rcx, [rsp+5B0h+var_578]
0x1800355e6  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800355eb  nop
0x1800355ec  lea     rcx, [rsp+5B0h+var_568]
0x1800355f1  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x1800355f6  lea     rdx, asc_180048060; "\t"
0x1800355fd  lea     rcx, [rsp+5B0h+var_578]
0x180035602  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180035607  sub     edi, 1
0x18003560a  jz      short loc_180035628
0x18003560c  sub     edi, 1
0x18003560f  jz      short loc_18003561F
0x180035611  cmp     edi, 1
0x180035614  jnz     short loc_180035639
0x180035616  lea     rdx, aError; "error"
0x18003561d  jmp     short loc_18003562F
0x18003561f  lea     rdx, aWarning; "warning"
0x180035626  jmp     short loc_18003562F
0x180035628  lea     rdx, aInfo; "info"
0x18003562f  lea     rcx, [rsp+5B0h+var_578]
0x180035634  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180035639  lea     r14, [rsi+10h]
0x18003563d  mov     rax, [r14]
0x180035640  cmp     [rax-10h], r13d
0x180035644  jnz     loc_180035709
0x18003564a  xor     edx, edx; Val
0x18003564c  mov     r8d, 104h; Size
0x180035652  lea     rcx, [rsp+5B0h+Str]; void *
0x180035657  call    memset_0
0x18003565c  lea     rcx, aApiMsWinCorePs; "api-ms-win-core-psapi-obsolete-l1-1-0.d"...
0x180035663  call    cs:__imp_LoadLibraryW
0x180035669  mov     rbx, rax
0x18003566c  test    rax, rax
0x18003566f  jz      short loc_18003567A
0x180035671  lea     rdx, aK32getmodulefi; "K32GetModuleFileNameExA"
0x180035678  jmp     short loc_180035696
0x18003567a  lea     rcx, aPsapiDll; "psapi.dll"
0x180035681  call    cs:__imp_LoadLibraryW
0x180035687  mov     rbx, rax
0x18003568a  test    rax, rax
0x18003568d  jz      short loc_180035709
0x18003568f  lea     rdx, aGetmodulefilen; "GetModuleFileNameExA"
0x180035696  mov     rcx, rax; hModule
0x180035699  call    cs:__imp_GetProcAddress
0x18003569f  mov     rdi, rax
0x1800356a2  test    rax, rax
0x1800356a5  jz      short loc_180035709
0x1800356a7  call    cs:__imp_GetCurrentProcess
0x1800356ad  mov     rcx, rax
0x1800356b0  mov     r9d, 104h
0x1800356b6  lea     r8, [rsp+5B0h+Str]
0x1800356bb  xor     edx, edx
0x1800356bd  mov     rax, rdi
0x1800356c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356c5  test    eax, eax
0x1800356c7  jz      short loc_1800356E7
0x1800356c9  mov     edx, 5Ch ; '\'; Ch
0x1800356ce  lea     rcx, [rsp+5B0h+Str]; Str
0x1800356d3  call    cs:__imp_strrchr
0x1800356d9  lea     rdx, [rax+1]
0x1800356dd  test    rdx, rdx
0x1800356e0  jnz     short loc_1800356EC
0x1800356e2  mov     r8d, r13d
0x1800356e5  jmp     short loc_1800356F8
0x1800356e7  lea     rdx, [rsp+5B0h+Str]
0x1800356ec  mov     r8, r15
0x1800356ef  inc     r8
0x1800356f2  cmp     [rdx+r8], r13b
0x1800356f6  jnz     short loc_1800356EF
0x1800356f8  mov     rcx, r14
0x1800356fb  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::SetString(char const *,int)
0x180035700  mov     rcx, rbx; hLibModule
0x180035703  call    cs:__imp_FreeLibrary
0x180035709  mov     r13d, 400h
0x18003570f  mov     r8d, r13d; Size
0x180035712  xor     edx, edx; Val
0x180035714  lea     rcx, [rbp+4B0h+var_440]; void *
0x180035718  call    memset_0
0x18003571d  call    cs:__imp_GetCurrentProcessId
0x180035723  mov     edi, eax
0x180035725  call    cs:__imp_GetCurrentThreadId
0x18003572b  mov     ebx, eax
0x18003572d  lea     rdx, asc_180048060; "\t"
0x180035734  lea     rcx, [rsp+5B0h+var_578]
0x180035739  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x18003573e  mov     [rsp+5B0h+var_588], ebx
0x180035742  mov     dword ptr [rsp+5B0h+lpOverlapped], edi
0x180035746  mov     r9, [r14]
0x180035749  lea     r8, aSPidDTidD; "\t%s (PID:%d TID:%d)\t"
0x180035750  mov     edx, r13d; unsigned __int64
0x180035753  lea     rcx, [rbp+4B0h+var_440]; char *
0x180035757  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18003575c  xor     r13d, r13d
0x18003575f  test    eax, eax
0x180035761  js      short loc_180035771
0x180035763  lea     rdx, [rbp+4B0h+var_440]
0x180035767  lea     rcx, [rsp+5B0h+var_578]
0x18003576c  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180035771  mov     rdx, [r12]
0x180035775  mov     r8d, [rdx-10h]
0x180035779  lea     rcx, [rsp+5B0h+var_578]
0x18003577e  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x180035783  lea     rdx, asc_18004812C; "\r\n"
0x18003578a  lea     rcx, [rsp+5B0h+var_578]
0x18003578f  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180035794  mov     r14, [rsp+5B0h+var_578]
0x180035799  inc     r15
0x18003579c  cmp     [r14+r15*2], r13w
0x1800357a1  jnz     short loc_180035799
0x1800357a3  lea     ebx, [r15+r15]
0x1800357a7  lea     eax, [rbx+1]
0x1800357aa  movsxd  rcx, eax; unsigned __int64
0x1800357ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800357b4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800357b9  mov     r15, rax
0x1800357bc  test    rax, rax
0x1800357bf  jz      loc_180035889
0x1800357c5  mov     rdi, rax
0x1800357c8  cmp     [r14], r13w
0x1800357cc  jz      short loc_180035848
0x1800357ce  mov     edx, 2
0x1800357d3  test    ebx, ebx
0x1800357d5  jz      short loc_180035848
0x1800357d7  mov     ecx, 5400h
0x1800357dc  movzx   eax, word ptr [r14]
0x1800357e0  add     ax, cx
0x1800357e3  mov     ecx, 0FFh
0x1800357e8  cmp     ax, cx
0x1800357eb  ja      short loc_180035823
0x1800357ed  cmp     ebx, edx
0x1800357ef  jl      short loc_18003583F
0x1800357f1  mov     al, [r14]
0x1800357f4  mov     [rsp+5B0h+var_580], al
0x1800357f8  mov     [rsp+5B0h+var_568], ebx
0x1800357fc  lea     r9, [rsp+5B0h+var_568]; int *
0x180035801  mov     r8, rdi; char *
0x180035804  mov     edx, 1; int
0x180035809  lea     rcx, [rsp+5B0h+var_580]; unsigned __int8 *
0x18003580e  call    ?AtlHexEncode@ATL@@YAHPEBEHPEADPEAH@Z; ATL::AtlHexEncode(uchar const *,int,char *,int *)
0x180035813  mov     edx, 2
0x180035818  test    eax, eax
0x18003581a  jz      short loc_18003583F
0x18003581c  add     rdi, rdx
0x18003581f  sub     ebx, edx
0x180035821  jmp     short loc_18003583F
0x180035823  movzx   edx, word ptr [r14]; WCh
0x180035827  mov     rcx, rdi; MbCh
0x18003582a  call    cs:__imp_wctomb
0x180035830  test    eax, eax
0x180035832  mov     edx, 2
0x180035837  cmovle  eax, edx
0x18003583a  sub     ebx, eax
0x18003583c  add     rdi, rax
0x18003583f  add     r14, rdx
0x180035842  cmp     [r14], r13w
0x180035846  jnz     short loc_1800357D3
0x180035848  mov     [rsp+5B0h+NumberOfBytesWritten], r13d
0x18003584d  sub     edi, r15d
0x180035850  mov     [rsp+5B0h+lpOverlapped], r13; lpOverlapped
0x180035855  lea     r9, [rsp+5B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003585a  mov     r8d, edi; nNumberOfBytesToWrite
0x18003585d  mov     rdx, r15; lpBuffer
0x180035860  mov     rcx, [rsi+30h]; hFile
0x180035864  call    cs:__imp_WriteFile
0x18003586a  cmp     eax, 1
0x18003586d  jnz     short loc_180035880
0x18003586f  mov     eax, [rsp+5B0h+NumberOfBytesWritten]
0x180035873  add     [rsi+40h], eax
0x180035876  mov     rcx, [rsi+30h]; hFile
0x18003587a  call    cs:__imp_FlushFileBuffers
0x180035880  mov     rcx, r15; void *
0x180035883  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180035888  nop
0x180035889  lea     rcx, [rsp+5B0h+var_578]
0x18003588e  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180035893  nop
0x180035894  mov     rcx, r12
0x180035897  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18003589c  mov     rcx, [rbp+4B0h+var_40]
0x1800358a3  xor     rcx, rsp; StackCookie
0x1800358a6  call    __security_check_cookie
0x1800358ab  mov     rbx, [rsp+5B0h+arg_8]
0x1800358b3  add     rsp, 580h
0x1800358ba  pop     r15
0x1800358bc  pop     r14
0x1800358be  pop     r13
0x1800358c0  pop     r12
0x1800358c2  pop     rdi
0x1800358c3  pop     rsi
0x1800358c4  pop     rbp
0x1800358c5  retn
```
