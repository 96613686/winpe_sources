# CDumpCollection::CollectDump(_MINIDUMP_TYPE,void *,ulong,ulong)

- ea: `0x18003ea08`
- end: `0x18003f13b`
- name: `?CollectDump@CDumpCollection@@QEAAJW4_MINIDUMP_TYPE@@PEAXKK@Z`
- size: `1843`
- prototype: `__int64 __fastcall(CDumpCollection *this, enum _MINIDUMP_TYPE, void *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180007db8`

## callees

- `0x18000113c`
- `0x180001758`
- `0x180002890`
- `0x1800028b4`
- `0x180003474`
- `0x180007704`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f40`
- `0x18000af40`
- `0x18003dfd4`
- `0x18003e5a8`
- `0x18003ea08`
- `0x180040cb4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003efd6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003f0fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003efd6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003f0fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ecfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ed0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ecfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ed0b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003ed92`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003ed92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003ed89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003eda1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003ef31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003ed89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003eda1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003ef31`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003edad`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003ef3c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003edad`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003ef3c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003eb46`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003eb46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003edf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003edf1`
- `ntdll!RtlCompareMemory` at `0x18003ec48`
- `ntdll!RtlCompareMemory` at `0x18003ec48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ea53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ef73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ea53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ef73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ed83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003efb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ed83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003efb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003efb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f110`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003efb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f110`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003ed2f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003ed2f`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x18003eb9d`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x18003eb9d`
- `dbghelp!MiniDumpWriteDump` at `0x18003ede0`
- `dbghelp!MiniDumpWriteDump` at `0x18003ede0`

## pseudocode

```c
__int64 __fastcall CDumpCollection::CollectDump(CDumpCollection *this, enum _MINIDUMP_TYPE a2, void *a3, int a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  DWORD v12; // edi
  __int64 v13; // rax
  unsigned int v14; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  int v18; // r15d
  HANDLE v19; // rax
  signed int LastError; // eax
  signed int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  HANDLE *v28; // rsi
  HANDLE CurrentProcess; // rbx
  void *v30; // rdi
  HANDLE v31; // rax
  signed int v32; // eax
  MINIDUMP_TYPE v33; // r12d
  HANDLE CurrentThread; // rax
  int ThreadPriority; // esi
  HANDLE v36; // rax
  BOOL v37; // r13d
  int FinalPathByHandle; // eax
  int v39; // r8d
  int v40; // r9d
  _QWORD *v41; // rcx
  HANDLE v42; // rax
  HANDLE v43; // rcx
  HMODULE v44; // rcx
  unsigned __int32 v46; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hProcess; // [rsp+60h] [rbp-A0h] BYREF
  HMODULE hLibModule; // [rsp+68h] [rbp-98h]
  __int128 v50; // [rsp+70h] [rbp-90h] BYREF
  struct _MINIDUMP_EXCEPTION_INFORMATION ExceptionParam; // [rsp+80h] [rbp-80h] BYREF
  void *v52; // [rsp+90h] [rbp-70h]
  _WORD *v53; // [rsp+98h] [rbp-68h]
  _WORD v54[8]; // [rsp+A0h] [rbp-60h] BYREF
  void *v55; // [rsp+B0h] [rbp-50h] BYREF
  int *v56; // [rsp+B8h] [rbp-48h] BYREF
  const wchar_t *v57; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v58; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v59[2]; // [rsp+D8h] [rbp-28h] BYREF
  struct _MINIDUMP_CALLBACK_INFORMATION CallbackParam; // [rsp+E8h] [rbp-18h] BYREF
  CDumpCollection *v61; // [rsp+F8h] [rbp-8h]
  char v62; // [rsp+100h] [rbp+0h]
  _BYTE v63[80]; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v64[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v65; // [rsp+168h] [rbp+68h]
  __int64 v66; // [rsp+170h] [rbp+70h]
  int v67; // [rsp+178h] [rbp+78h]
  char v68[128]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE Source2[48]; // [rsp+200h] [rbp+100h] BYREF
  int v70; // [rsp+230h] [rbp+130h]
  char v71[32]; // [rsp+6D0h] [rbp+5D0h] BYREF
  __int128 *v72; // [rsp+6F0h] [rbp+5F0h]
  __int64 v73; // [rsp+6F8h] [rbp+5F8h]
  unsigned __int32 *v74; // [rsp+700h] [rbp+600h]
  __int64 v75; // [rsp+708h] [rbp+608h]
  HANDLE *p_hFile; // [rsp+710h] [rbp+610h]
  __int64 v77; // [rsp+718h] [rbp+618h]

  hFile = a3;
  hProcess = 0;
  v61 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v62 = 1;
  if ( *((_QWORD *)this + 136) != -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8, v10, v11);
  *((_QWORD *)this + 136) = a3;
  ExceptionParam = 0;
  memset_0(v64, 0, 0x98u);
  v58 = 0;
  v12 = *((_DWORD *)this + 279);
  hLibModule = 0;
  memset_0(v63, 0, sizeof(v63));
  v52 = v54;
  v53 = v54;
  v54[0] = 0;
  if ( v12 )
  {
    v14 = -2147467259;
  }
  else
  {
    CDumpCollection::_SnapAllThreads(this);
    v13 = *((_QWORD *)this + 301);
    if ( *((_QWORD *)this + 300) == v13 || (v12 = *(_DWORD *)(v13 - 4)) == 0 )
    {
      v14 = -2147467259;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_10;
      v16 = 43;
      v17 = 2147500037LL;
LABEL_9:
      WPP_SF_d(v15[2], v16, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v17);
LABEL_10:
      v18 = 2;
      goto LABEL_61;
    }
    v14 = 0;
  }
  v19 = OpenThread(0x48u, 0, v12);
  if ( !v19 )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_10;
    v16 = 44;
    v17 = v14;
    goto LABEL_9;
  }
  *((_DWORD *)this + 304) = 1048607;
  if ( !GetThreadContext(v19, (LPCONTEXT)((char *)this + 1168)) )
  {
    v21 = GetLastError();
    v14 = v21;
    if ( v21 > 0 )
      v14 = (unsigned __int16)v21 | 0x80070000;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_26;
    v23 = 45;
LABEL_25:
    WPP_SF_d(v22[2], v23, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v14);
LABEL_26:
    v18 = 2;
    goto LABEL_61;
  }
  v18 = -1;
  v64[0] = a4;
  v64[1] = 1;
  v65 = 0;
  v66 = *((_QWORD *)this + 177);
  memset_0(Source2, 0, 0x4D0u);
  v70 = 1048607;
  if ( RtlCompareMemory((char *)this + 1168, Source2, 0x4D0u) == 1232 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v25, v24, v26, v27);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
  }
  else
  {
    v67 = 0;
    memset_0(v68, 0, 0x78u);
    *(_QWORD *)&v58 = v64;
    *((_QWORD *)&v58 + 1) = (char *)this + 1168;
    ExceptionParam.ThreadId = v12;
    ExceptionParam.ExceptionPointers = (PEXCEPTION_POINTERS)&v58;
    ExceptionParam.ClientPointers = 0;
    v59[0] = this;
    v59[1] = 0;
    v50 = 0;
    CallbackParam.CallbackRoutine = (MINIDUMP_CALLBACK_ROUTINE)CDumpCollection::StaticMinidumpCallback;
    CallbackParam.CallbackParam = v59;
    v28 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&hProcess);
    CurrentProcess = GetCurrentProcess();
    v30 = (void *)*((_QWORD *)this + 137);
    v31 = GetCurrentProcess();
    if ( !DuplicateHandle(v31, v30, CurrentProcess, v28, 0, 0, 2u) )
    {
      v32 = GetLastError();
      v14 = v32;
      if ( v32 > 0 )
        v14 = (unsigned __int16)v32 | 0x80070000;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_26;
      v23 = 52;
      goto LABEL_25;
    }
    v33 = a2 | 0x820000;
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    if ( ThreadPriority != 0x7FFFFFFF )
    {
      v36 = GetCurrentThread();
      SetThreadPriority(v36, -1);
    }
    v37 = MiniDumpWriteDump(
            hProcess,
            *((_DWORD *)this + 278),
            *((HANDLE *)this + 136),
            v33,
            &ExceptionParam,
            0,
            &CallbackParam);
    if ( v37 )
      v14 = 0;
    else
      v14 = GetLastError();
    FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(hFile);
    if ( FinalPathByHandle < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids,
        (unsigned int)FinalPathByHandle);
    }
    if ( (unsigned int)dword_180062000 > 5
      && (qword_180062010 & 0x400000000000LL) != 0
      && (qword_180062018 & 0x400000000000LL) == qword_180062018 )
    {
      v55 = v52;
      v46 = v33;
      v56 = &dword_18004FE4C;
      v57 = L"DumpCollection";
      LODWORD(hFile) = v14;
      *(_QWORD *)&v50 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        (unsigned int)&dword_180062000,
        (unsigned int)byte_1800585DD,
        v39,
        v40,
        (__int64)&v50,
        (__int64)&hFile,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)&v46,
        (__int64)&v55);
    }
    v41 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v14, v33);
      v41 = WPP_GLOBAL_Control;
    }
    if ( ThreadPriority != 0x7FFFFFFF )
    {
      v42 = GetCurrentThread();
      SetThreadPriority(v42, ThreadPriority);
      v41 = WPP_GLOBAL_Control;
    }
    if ( !v37 && v41 != &WPP_GLOBAL_Control && (*((_BYTE *)v41 + 28) & 1) != 0 )
      WPP_SF_d(v41[2], 55, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v14);
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    if ( v37 )
    {
      v14 = 0;
      v18 = 0;
    }
  }
LABEL_61:
  *((_QWORD *)this + 136) = -1;
  v43 = hProcess;
  hProcess = 0;
  if ( (unsigned __int64)v43 + 1 > 1 )
    CloseHandle(v43);
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  v62 = 0;
  v44 = hLibModule;
  hLibModule = 0;
  if ( v44 )
    FreeLibrary(v44);
  MmsFree(v63);
  if ( v14 )
  {
    if ( (unsigned int)dword_180062000 > 5
      && (qword_180062010 & 0x400000000000LL) != 0
      && (qword_180062018 & 0x400000000000LL) == qword_180062018 )
    {
      LODWORD(hFile) = v18;
      v46 = v14;
      *(_QWORD *)&v50 = 0x1000000;
      p_hFile = &hFile;
      v77 = 4;
      v74 = &v46;
      v75 = 4;
      v72 = &v50;
      v73 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_180062000, byte_18005858B, 0, 0, 5, v71);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v14, v18);
  }
  if ( v52 != v54 )
    operator delete(v52, (const struct std::nothrow_t *)&std::nothrow);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( (unsigned __int64)hProcess + 1 > 1 )
    CloseHandle(hProcess);
  return v14;
}

```

## disassembly

```asm
0x18003ea08  push    rbp
0x18003ea0a  push    rbx
0x18003ea0b  push    rsi
0x18003ea0c  push    rdi
0x18003ea0d  push    r12
0x18003ea0f  push    r13
0x18003ea11  push    r14
0x18003ea13  push    r15
0x18003ea15  lea     rbp, [rsp-638h]
0x18003ea1d  sub     rsp, 738h
0x18003ea24  mov     rax, cs:__security_cookie
0x18003ea2b  xor     rax, rsp
0x18003ea2e  mov     [rbp+670h+var_50], rax
0x18003ea35  mov     r13d, r9d
0x18003ea38  mov     rbx, r8
0x18003ea3b  mov     [rsp+770h+hFile], rbx
0x18003ea40  mov     r12d, edx
0x18003ea43  mov     r14, rcx
0x18003ea46  mov     [rsp+770h+hProcess], 0
0x18003ea4f  mov     [rbp+670h+var_678], rcx
0x18003ea53  call    cs:__imp_EnterCriticalSection
0x18003ea59  mov     [rbp+670h+var_670], 1
0x18003ea5d  cmp     qword ptr [r14+440h], 0FFFFFFFFFFFFFFFFh
0x18003ea65  jz      short loc_18003EA6C
0x18003ea67  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003ea6c  mov     [r14+440h], rbx
0x18003ea73  xorps   xmm0, xmm0
0x18003ea76  movups  xmmword ptr [rbp+670h+ExceptionParam.ThreadId], xmm0
0x18003ea7a  xor     edx, edx; Val
0x18003ea7c  mov     r8d, 98h; Size
0x18003ea82  lea     rcx, [rbp+670h+var_610]; void *
0x18003ea86  call    memset_0
0x18003ea8b  xorps   xmm0, xmm0
0x18003ea8e  movups  [rbp+670h+var_6A8], xmm0
0x18003ea92  mov     edi, [r14+45Ch]
0x18003ea99  mov     [rsp+770h+hLibModule], 0
0x18003eaa2  xor     edx, edx; Val
0x18003eaa4  lea     r8d, [rdx+50h]; Size
0x18003eaa8  lea     rcx, [rbp+670h+var_660]; void *
0x18003eaac  call    memset_0
0x18003eab1  lea     rax, [rbp+670h+var_6D0]
0x18003eab5  mov     [rbp+670h+var_6E0], rax
0x18003eab9  lea     rax, [rbp+670h+var_6D0]
0x18003eabd  mov     [rbp+670h+var_6D8], rax
0x18003eac1  xor     eax, eax
0x18003eac3  mov     [rbp+670h+var_6D0], ax
0x18003eac7  mov     rsi, 400000000000h
0x18003ead1  test    edi, edi
0x18003ead3  jnz     short loc_18003EB39
0x18003ead5  mov     rcx, r14; this
0x18003ead8  call    ?_SnapAllThreads@CDumpCollection@@AEAAJXZ; CDumpCollection::_SnapAllThreads(void)
0x18003eadd  mov     rax, [r14+968h]
0x18003eae4  cmp     [r14+960h], rax
0x18003eaeb  jz      short loc_18003EAF4
0x18003eaed  mov     edi, [rax-4]
0x18003eaf0  test    edi, edi
0x18003eaf2  jnz     short loc_18003EB35
0x18003eaf4  mov     ebx, 80004005h
0x18003eaf9  lea     rdi, WPP_GLOBAL_Control
0x18003eb00  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eb07  cmp     rcx, rdi
0x18003eb0a  jz      short loc_18003EB2A
0x18003eb0c  test    byte ptr [rcx+1Ch], 1
0x18003eb10  jz      short loc_18003EB2A
0x18003eb12  mov     edx, 2Bh ; '+'
0x18003eb17  mov     r9d, ebx
0x18003eb1a  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003eb21  mov     rcx, [rcx+10h]
0x18003eb25  call    WPP_SF_d
0x18003eb2a  mov     r15d, 2
0x18003eb30  jmp     loc_18003EF8D
0x18003eb35  xor     ebx, ebx
0x18003eb37  jmp     short loc_18003EB3E
0x18003eb39  mov     ebx, 80004005h
0x18003eb3e  mov     r8d, edi; dwThreadId
0x18003eb41  xor     edx, edx; bInheritHandle
0x18003eb43  lea     ecx, [rdx+48h]; dwDesiredAccess
0x18003eb46  call    cs:__imp_OpenThread
0x18003eb4c  test    rax, rax
0x18003eb4f  jnz     short loc_18003EB89
0x18003eb51  call    cs:__imp_GetLastError
0x18003eb57  mov     ebx, eax
0x18003eb59  test    eax, eax
0x18003eb5b  jle     short loc_18003EB66
0x18003eb5d  movzx   ebx, ax
0x18003eb60  or      ebx, 80070000h
0x18003eb66  lea     rdi, WPP_GLOBAL_Control
0x18003eb6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eb74  cmp     rcx, rdi
0x18003eb77  jz      short loc_18003EB2A
0x18003eb79  test    byte ptr [rcx+1Ch], 1
0x18003eb7d  jz      short loc_18003EB2A
0x18003eb7f  mov     edx, 2Ch ; ','
0x18003eb84  mov     r9d, ebx
0x18003eb87  jmp     short loc_18003EB1A
0x18003eb89  lea     rsi, [r14+490h]
0x18003eb90  mov     dword ptr [rsi+30h], 10001Fh
0x18003eb97  mov     rdx, rsi; lpContext
0x18003eb9a  mov     rcx, rax; hThread
0x18003eb9d  call    cs:__imp_GetThreadContext
0x18003eba3  test    eax, eax
0x18003eba5  jnz     short loc_18003EBF8
0x18003eba7  call    cs:__imp_GetLastError
0x18003ebad  mov     ebx, eax
0x18003ebaf  test    eax, eax
0x18003ebb1  jle     short loc_18003EBBC
0x18003ebb3  movzx   ebx, ax
0x18003ebb6  or      ebx, 80070000h
0x18003ebbc  lea     rdi, WPP_GLOBAL_Control
0x18003ebc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ebca  cmp     rcx, rdi
0x18003ebcd  jz      short loc_18003EBED
0x18003ebcf  test    byte ptr [rcx+1Ch], 1
0x18003ebd3  jz      short loc_18003EBED
0x18003ebd5  mov     edx, 2Dh ; '-'
0x18003ebda  mov     r9d, ebx
0x18003ebdd  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003ebe4  mov     rcx, [rcx+10h]
0x18003ebe8  call    WPP_SF_d
0x18003ebed  mov     r15d, 2
0x18003ebf3  jmp     loc_18003EF83
0x18003ebf8  or      r15d, 0FFFFFFFFh
0x18003ebfc  mov     [rbp+670h+var_610], r13d
0x18003ec00  mov     [rbp+670h+var_60C], 1
0x18003ec07  mov     [rbp+670h+var_608], 0
0x18003ec0f  mov     rax, [r14+588h]
0x18003ec16  mov     [rbp+670h+var_600], rax
0x18003ec1a  mov     r13d, 4D0h
0x18003ec20  mov     r8d, r13d; Size
0x18003ec23  xor     edx, edx; Val
0x18003ec25  lea     rcx, [rbp+670h+Source2]; void *
0x18003ec2c  call    memset_0
0x18003ec31  mov     [rbp+670h+var_540], 10001Fh
0x18003ec3b  mov     r8d, r13d; Length
0x18003ec3e  lea     rdx, [rbp+670h+Source2]; Source2
0x18003ec45  mov     rcx, rsi; Source1
0x18003ec48  call    cs:__imp_RtlCompareMemory
0x18003ec4e  cmp     rax, r13
0x18003ec51  jnz     short loc_18003EC92
0x18003ec53  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003ec58  lea     rdi, WPP_GLOBAL_Control
0x18003ec5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ec66  cmp     rcx, rdi
0x18003ec69  jz      loc_18003EF83
0x18003ec6f  test    byte ptr [rcx+1Ch], 1
0x18003ec73  jz      loc_18003EF83
0x18003ec79  lea     edx, [r15+2Fh]
0x18003ec7d  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003ec84  mov     rcx, [rcx+10h]
0x18003ec88  call    WPP_SF_
0x18003ec8d  jmp     loc_18003EF83
0x18003ec92  xor     r13d, r13d
0x18003ec95  mov     [rbp+670h+var_5F8], r13d
0x18003ec99  xor     edx, edx; Val
0x18003ec9b  lea     r8d, [r13+78h]; Size
0x18003ec9f  lea     rcx, [rbp+670h+var_5F0]; void *
0x18003eca6  call    memset_0
0x18003ecab  lea     rax, [rbp+670h+var_610]
0x18003ecaf  mov     qword ptr [rbp+670h+var_6A8], rax
0x18003ecb3  mov     qword ptr [rbp+670h+var_6A8+8], rsi
0x18003ecb7  mov     [rbp+670h+ExceptionParam.ThreadId], edi
0x18003ecba  lea     rax, [rbp+670h+var_6A8]
0x18003ecbe  mov     [rbp+670h+ExceptionParam.ExceptionPointers], rax
0x18003ecc2  mov     [rbp+670h+ExceptionParam.ClientPointers], r13d
0x18003ecc6  xorps   xmm0, xmm0
0x18003ecc9  movups  [rsp+770h+var_700], xmm0
0x18003ecce  mov     [rbp+670h+var_698], r14
0x18003ecd2  mov     [rbp+670h+var_690], r13
0x18003ecd6  movups  [rsp+770h+var_700], xmm0
0x18003ecdb  lea     rax, ?StaticMinidumpCallback@CDumpCollection@@CAHPEAXQEAU_MINIDUMP_CALLBACK_INPUT@@PEAU_MINIDUMP_CALLBACK_OUTPUT@@@Z; CDumpCollection::StaticMinidumpCallback(void *,_MINIDUMP_CALLBACK_INPUT * const,_MINIDUMP_CALLBACK_OUTPUT *)
0x18003ece2  mov     [rbp+670h+CallbackParam.CallbackRoutine], rax
0x18003ece6  lea     rax, [rbp+670h+var_698]
0x18003ecea  mov     [rbp+670h+CallbackParam.CallbackParam], rax
0x18003ecee  lea     rcx, [rsp+770h+hProcess]
0x18003ecf3  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18003ecf8  mov     rsi, rax
0x18003ecfb  call    cs:__imp_GetCurrentProcess
0x18003ed01  mov     rbx, rax
0x18003ed04  mov     rdi, [r14+448h]
0x18003ed0b  call    cs:__imp_GetCurrentProcess
0x18003ed11  mov     [rsp+770h+dwOptions], 2; dwOptions
0x18003ed19  mov     [rsp+770h+bInheritHandle], r13d; bInheritHandle
0x18003ed1e  mov     [rsp+770h+dwDesiredAccess], r13d; dwDesiredAccess
0x18003ed23  mov     r9, rsi; lpTargetHandle
0x18003ed26  mov     r8, rbx; hTargetProcessHandle
0x18003ed29  mov     rdx, rdi; hSourceHandle
0x18003ed2c  mov     rcx, rax; hSourceProcessHandle
0x18003ed2f  call    cs:__imp_DuplicateHandle
0x18003ed35  test    eax, eax
0x18003ed37  jnz     short loc_18003ED79
0x18003ed39  call    cs:__imp_GetLastError
0x18003ed3f  mov     ebx, eax
0x18003ed41  test    eax, eax
0x18003ed43  jle     short loc_18003ED4E
0x18003ed45  movzx   ebx, ax
0x18003ed48  or      ebx, 80070000h
0x18003ed4e  lea     rdi, WPP_GLOBAL_Control
0x18003ed55  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ed5c  cmp     rcx, rdi
0x18003ed5f  jz      loc_18003EBED
0x18003ed65  test    byte ptr [rcx+1Ch], 1
0x18003ed69  jz      loc_18003EBED
0x18003ed6f  mov     edx, 34h ; '4'
0x18003ed74  jmp     loc_18003EBDA
0x18003ed79  or      r12d, 820000h
0x18003ed80  mov     rcx, r14; lpCriticalSection
0x18003ed83  call    cs:__imp_LeaveCriticalSection
0x18003ed89  call    cs:__imp_GetCurrentThread
0x18003ed8f  mov     rcx, rax; hThread
0x18003ed92  call    cs:__imp_GetThreadPriority
0x18003ed98  mov     esi, eax
0x18003ed9a  cmp     eax, 7FFFFFFFh
0x18003ed9f  jz      short loc_18003EDB3
0x18003eda1  call    cs:__imp_GetCurrentThread
0x18003eda7  mov     rcx, rax; hThread
0x18003edaa  or      edx, 0FFFFFFFFh; nPriority
0x18003edad  call    cs:__imp_SetThreadPriority
0x18003edb3  lea     rax, [rbp+670h+CallbackParam]
0x18003edb7  mov     qword ptr [rsp+770h+dwOptions], rax; CallbackParam
0x18003edbc  mov     qword ptr [rsp+770h+bInheritHandle], r13; UserStreamParam
0x18003edc1  lea     rax, [rbp+670h+ExceptionParam]
0x18003edc5  mov     qword ptr [rsp+770h+dwDesiredAccess], rax; ExceptionParam
0x18003edca  mov     r9d, r12d; DumpType
0x18003edcd  mov     r8, [r14+440h]; hFile
0x18003edd4  mov     edx, [r14+458h]; ProcessId
0x18003eddb  mov     rcx, [rsp+770h+hProcess]; hProcess
0x18003ede0  call    cs:__imp_MiniDumpWriteDump
0x18003ede6  mov     r13d, eax
0x18003ede9  test    eax, eax
0x18003edeb  jz      short loc_18003EDF1
0x18003eded  xor     ebx, ebx
0x18003edef  jmp     short loc_18003EDF9
0x18003edf1  call    cs:__imp_GetLastError
0x18003edf7  mov     ebx, eax
0x18003edf9  lea     rdx, [rbp+670h+var_6E0]
0x18003edfd  mov     rcx, [rsp+770h+hFile]; hFile
0x18003ee02  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18003ee07  lea     rdi, WPP_GLOBAL_Control
0x18003ee0e  test    eax, eax
0x18003ee10  jns     short loc_18003EE3C
0x18003ee12  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ee19  cmp     rcx, rdi
0x18003ee1c  jz      short loc_18003EE3C
0x18003ee1e  test    byte ptr [rcx+1Ch], 1
0x18003ee22  jz      short loc_18003EE3C
0x18003ee24  mov     edx, 35h ; '5'
0x18003ee29  mov     r9d, eax
0x18003ee2c  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003ee33  mov     rcx, [rcx+10h]
0x18003ee37  call    WPP_SF_d
0x18003ee3c  mov     eax, cs:dword_180062000
0x18003ee42  cmp     eax, 5
0x18003ee45  jbe     loc_18003EEF3
0x18003ee4b  mov     rcx, cs:qword_180062018
0x18003ee52  mov     rax, cs:qword_180062010
0x18003ee59  mov     rdx, 400000000000h
0x18003ee63  test    rdx, rax
0x18003ee66  jz      loc_18003EEF3
0x18003ee6c  mov     rax, rcx
0x18003ee6f  and     rax, rdx
0x18003ee72  cmp     rax, rcx
0x18003ee75  jnz     short loc_18003EEF3
0x18003ee77  mov     rax, [rbp+670h+var_6E0]
0x18003ee7b  mov     [rbp+670h+var_6C0], rax
0x18003ee7f  mov     [rsp+770h+var_720], r12d
0x18003ee84  lea     rax, dword_18004FE4C
0x18003ee8b  mov     [rbp+670h+var_6B8], rax
0x18003ee8f  lea     rax, aDumpcollection; "DumpCollection"
0x18003ee96  mov     [rbp+670h+var_6B0], rax
0x18003ee9a  mov     dword ptr [rsp+770h+hFile], ebx
0x18003ee9e  mov     qword ptr [rsp+770h+var_700], 1000000h
0x18003eea7  lea     rax, [rbp+670h+var_6C0]
0x18003eeab  mov     [rsp+770h+var_728], rax
0x18003eeb0  lea     rax, [rsp+770h+var_720]
0x18003eeb5  mov     [rsp+770h+var_730], rax
0x18003eeba  lea     rax, [rbp+670h+var_6B8]
0x18003eebe  mov     [rsp+770h+var_738], rax
0x18003eec3  lea     rax, [rbp+670h+var_6B0]
0x18003eec7  mov     qword ptr [rsp+770h+dwOptions], rax
0x18003eecc  lea     rax, [rsp+770h+hFile]
0x18003eed1  mov     qword ptr [rsp+770h+bInheritHandle], rax
0x18003eed6  lea     rax, [rsp+770h+var_700]
0x18003eedb  mov     qword ptr [rsp+770h+dwDesiredAccess], rax
0x18003eee0  lea     rdx, byte_1800585DD
0x18003eee7  lea     rcx, dword_180062000
0x18003eeee  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@545@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18003eef3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eefa  cmp     rcx, rdi
0x18003eefd  jz      short loc_18003EF29
0x18003eeff  test    byte ptr [rcx+1Ch], 4
0x18003ef03  jz      short loc_18003EF29
0x18003ef05  mov     edx, 36h ; '6'
0x18003ef0a  mov     [rsp+770h+dwDesiredAccess], r12d
0x18003ef0f  mov     r9d, ebx
0x18003ef12  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003ef19  mov     rcx, [rcx+10h]
0x18003ef1d  call    WPP_SF_Dd
0x18003ef22  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ef29  cmp     esi, 7FFFFFFFh
0x18003ef2f  jz      short loc_18003EF49
  ... truncated ...
```
