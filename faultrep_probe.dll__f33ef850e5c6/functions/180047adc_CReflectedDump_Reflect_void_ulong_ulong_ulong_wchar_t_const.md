# CReflectedDump::Reflect(void *,ulong,ulong,ulong,wchar_t const *)

- ea: `0x180047adc`
- end: `0x18004833b`
- name: `?Reflect@CReflectedDump@@IEAAJPEAXKKKPEB_W@Z`
- size: `2143`
- prototype: `__int64 __usercall@<rax>(CReflectedDump *__hidden this@<rcx>, HANDLE ProcessHandle@<rdx>, DWORD dwThreadId@<r8d>, unsigned int@<r9d>, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180048350`

## callees

- `0x180001758`
- `0x180002890`
- `0x180003474`
- `0x180007704`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f40`
- `0x18000a9a4`
- `0x18003cc4c`
- `0x180046e14`
- `0x18004704c`
- `0x180047314`
- `0x180047adc`
- `0x180048ab0`
- `0x180048c4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180048005`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180048099`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180048005`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180048099`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047f0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047f15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047f1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047f0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047f15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047f1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004808d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180048210`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180048220`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800482c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004808d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180048210`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180048220`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800482c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800480d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800480d6`
- `ntdll!NtResumeProcess` at `0x180047cd7`
- `ntdll!NtResumeProcess` at `0x180048204`
- `ntdll!NtResumeProcess` at `0x180047cd7`
- `ntdll!NtResumeProcess` at `0x180048204`
- `ntdll!NtSuspendProcess` at `0x180047fc3`
- `ntdll!NtSuspendProcess` at `0x180047fc3`
- `ntdll!RtlCreateProcessReflection` at `0x180048248`
- `ntdll!RtlCreateProcessReflection` at `0x180048248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047c8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047ca4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047cb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047cec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800482f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047c8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047ca4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047cb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047cec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800482f4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180047f48`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180047f48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047cfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047cfb`
- `dbghelp!MiniDumpWriteDump` at `0x1800480c7`
- `dbghelp!MiniDumpWriteDump` at `0x1800480c7`
- `wer!WerpGetStorePath` at `0x180047d47`
- `wer!WerpGetStorePath` at `0x180047d47`
- `wer!WerpValidateReportKey` at `0x180047c33`
- `wer!WerpValidateReportKey` at `0x180047c33`

## pseudocode

```c
__int64 __fastcall CReflectedDump::Reflect(
        CReflectedDump *this,
        HANDLE ProcessHandle,
        DWORD dwThreadId,
        unsigned int a4,
        char a5,
        wchar_t *a6)
{
  DWORD v6; // r13d
  int v9; // edi
  int DumpSecurityDescriptor; // eax
  int v11; // r14d
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  const wchar_t *v14; // rdi
  int StorePath; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  HANDLE v19; // rcx
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rdx
  HANDLE *v24; // rsi
  HANDLE CurrentProcess; // rdi
  HANDLE v26; // rbx
  HANDLE v27; // rax
  signed int LastError; // eax
  HANDLE v29; // rsi
  DWORD ProcessId; // eax
  MINIDUMP_TYPE v31; // edi
  DWORD TickCount; // r12d
  DWORD v33; // eax
  int v34; // r8d
  int v35; // r9d
  _BYTE *v36; // rcx
  __int64 v37; // rdx
  DWORD v38; // edi
  int ProcessReflection; // r14d
  void *v40; // rcx
  int v41; // [rsp+50h] [rbp-B0h]
  unsigned int v42; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v43; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+64h] [rbp-9Ch] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hFile; // [rsp+70h] [rbp-90h] BYREF
  HANDLE ProcessHandlea; // [rsp+78h] [rbp-88h]
  HLOCAL hMem; // [rsp+80h] [rbp-80h] BYREF
  __int128 v49; // [rsp+88h] [rbp-78h]
  __int64 v50; // [rsp+98h] [rbp-68h]
  char *v51; // [rsp+A0h] [rbp-60h] BYREF
  void *v52; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v53; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v55; // [rsp+C0h] [rbp-40h] BYREF
  struct _MINIDUMP_EXCEPTION_INFORMATION ExceptionParam; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE v57[2]; // [rsp+E0h] [rbp-20h]
  __int128 v58; // [rsp+F0h] [rbp-10h]
  struct _MINIDUMP_CALLBACK_INFORMATION CallbackParam; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v60[160]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v61[1232]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t v62[264]; // [rsp+680h] [rbp+580h] BYREF

  ProcessHandlea = ProcessHandle;
  v6 = dwThreadId;
  v42 = dwThreadId;
  v41 = 0;
  hFile = 0;
  v43 = a4;
  *(_OWORD *)v57 = 0;
  v9 = 0;
  v58 = 0;
  ExceptionParam = 0;
  memset_0(v60, 0, 0x98u);
  v55 = 0;
  memset_0(v61, 0, sizeof(v61));
  hMem = 0;
  hObject = 0;
  v44 = 0;
  v49 = 0;
  CallbackParam.CallbackRoutine = (MINIDUMP_CALLBACK_ROUTINE)CReflectedDump::static_MiniDumpCallback;
  CallbackParam.CallbackParam = this;
  LODWORD(v49) = 24;
  v50 = 0;
  DumpSecurityDescriptor = GetDumpSecurityDescriptor(ProcessHandle, &hMem);
  v11 = DumpSecurityDescriptor;
  if ( DumpSecurityDescriptor >= 0 )
  {
    v14 = L".mdref";
    *((_QWORD *)&v49 + 1) = hMem;
    if ( (a5 & 2) == 0 )
      v14 = L".tdref";
    if ( a6 && *a6 )
    {
      StorePath = WerpValidateReportKey(a6);
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_16;
        v17 = 31;
        goto LABEL_14;
      }
      v44 = 260;
      StorePath = WerpGetStorePath(3, v62, &v44);
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_16;
        v17 = 32;
        goto LABEL_14;
      }
      StorePath = StringCchCatW(v62, v21, L"\\");
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_16;
        v17 = 33;
        goto LABEL_14;
      }
      StorePath = StringCchCatW(v62, v22, a6);
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_16;
        v17 = 34;
        goto LABEL_14;
      }
      StorePath = StringCchCatW(v62, v23, L"\\");
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_16;
        v17 = 35;
        goto LABEL_14;
      }
      StorePath = UtilGetTempFile(&hFile, v62, v14, (char *)this + 8);
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 36;
LABEL_14:
          v18 = (unsigned int)StorePath;
LABEL_15:
          WPP_SF_d(v16[2], v17, &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, v18);
LABEL_16:
          v9 = 0;
          goto LABEL_17;
        }
        goto LABEL_92;
      }
    }
    else
    {
      StorePath = UtilGetTempFile(&hFile, 0, v14, (char *)this + 8);
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 37;
          goto LABEL_14;
        }
        goto LABEL_92;
      }
    }
    v24 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&hObject);
    CurrentProcess = GetCurrentProcess();
    v26 = GetCurrentProcess();
    v27 = GetCurrentProcess();
    if ( !DuplicateHandle(v27, v26, CurrentProcess, v24, 0x100000u, 0, 0) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v17 = 38;
        v18 = (unsigned int)v11;
        goto LABEL_15;
      }
      goto LABEL_92;
    }
    v29 = ProcessHandlea;
    if ( (a5 & 1) == 0 )
    {
      if ( (NtSuspendProcess(ProcessHandlea) & 0xC0000000) != 0xC0000000 )
      {
        v9 = 1;
        v41 = 1;
        goto LABEL_70;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
          (unsigned int)v11);
    }
    v9 = 0;
LABEL_70:
    if ( !v6 )
    {
      ProcessId = GetProcessId(v29);
      DumpSecurityDescriptor = GetFirstThreadInProcess(ProcessId, &v42);
      v11 = DumpSecurityDescriptor;
      if ( DumpSecurityDescriptor < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 40;
          goto LABEL_5;
        }
        goto LABEL_92;
      }
      v6 = v42;
    }
    ExceptionParam.ExceptionPointers = (PEXCEPTION_POINTERS)&v55;
    *((_QWORD *)&v55 + 1) = v61;
    *(_QWORD *)&v55 = v60;
    SetExceptionInformation(v6, v43, &ExceptionParam);
    v31 = (a5 & 2) != 0
        ? MiniDumpWithThreadInfo|MiniDumpWithProcessThreadData|MiniDumpWithUnloadedModules|MiniDumpWithHandleData
        : MiniDumpFilterTriage|MiniDumpWithProcessThreadData|MiniDumpFilterModulePaths|MiniDumpWithUnloadedModules|MiniDumpWithHandleData;
    TickCount = GetTickCount();
    v33 = GetProcessId(v29);
    if ( MiniDumpWriteDump(v29, v33, hFile, v31, &ExceptionParam, 0, &CallbackParam) )
      v11 = 0;
    else
      v11 = GetLastError();
    if ( (unsigned int)dword_180062070 > 5
      && (qword_180062080 & 0x400000000000LL) != 0
      && (qword_180062088 & 0x400000000000LL) == qword_180062088 )
    {
      v43 = (a5 & 2) != 0 ? 4388 : 1048996;
      v51 = (char *)this + 8;
      v42 = v11;
      v52 = &unk_18004FE4C;
      v54 = 0x1000000;
      v53 = L"Reflection";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        (unsigned int)&dword_180062070,
        (unsigned int)&unk_180058646,
        v34,
        v35,
        (__int64)&v54,
        (__int64)&v42,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v43,
        (__int64)&v51);
    }
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
        (unsigned int)v11,
        v31);
      v36 = WPP_GLOBAL_Control;
    }
    if ( v11 < 0 )
    {
      if ( v36 == (_BYTE *)&WPP_GLOBAL_Control || (v36[28] & 1) == 0 )
        goto LABEL_92;
      v37 = 42;
      goto LABEL_91;
    }
    if ( v41 )
    {
      NtResumeProcess(v29);
      v41 = 0;
    }
    *((_DWORD *)this + 136) = GetTickCount() - TickCount;
    v38 = GetTickCount();
    ProcessReflection = RtlCreateProcessReflection(v29, 12, 0);
    if ( (ProcessReflection & 0xC0000000) != 0xC0000000 )
    {
      if ( (unsigned int)VerifyReflectedProcessHandle(v29, v57[0]) )
      {
        *((_DWORD *)this + 137) = GetTickCount() - v38;
        v40 = (void *)*((_QWORD *)this + 66);
        *((HANDLE *)this + 66) = v57[0];
        if ( (unsigned __int64)v40 + 1 > 1 )
          CloseHandle(v40);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
            *((unsigned int *)this + 136),
            *((_DWORD *)this + 137));
        v11 = 0;
      }
      else
      {
        v11 = 6;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
      }
      goto LABEL_92;
    }
    v11 = ProcessReflection | 0x10000000;
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v37 = 43;
LABEL_91:
      WPP_SF_d(*((_QWORD *)v36 + 2), v37, &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, (unsigned int)v11);
    }
LABEL_92:
    v9 = v41;
    goto LABEL_17;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 30;
LABEL_5:
    WPP_SF_d(v12[2], v13, &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, (unsigned int)DumpSecurityDescriptor);
  }
LABEL_17:
  v19 = hObject;
  hObject = 0;
  if ( (unsigned __int64)v19 + 1 > 1 )
    CloseHandle(v19);
  if ( (unsigned __int64)hFile + 1 > 1 )
    CloseHandle(hFile);
  if ( v57[1] )
  {
    CloseHandle(v57[1]);
    v57[1] = 0;
  }
  if ( v11 < 0 )
    CReflectedDump::Cleanup(this);
  if ( v9 )
    NtResumeProcess(ProcessHandlea);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180047adc  mov     [rsp-8+arg_18], rbx
0x180047ae1  push    rbp
0x180047ae2  push    rsi
0x180047ae3  push    rdi
0x180047ae4  push    r12
0x180047ae6  push    r13
0x180047ae8  push    r14
0x180047aea  push    r15
0x180047aec  lea     rbp, [rsp-7A0h]
0x180047af4  sub     rsp, 8A0h
0x180047afb  mov     rax, cs:__security_cookie
0x180047b02  xor     rax, rsp
0x180047b05  mov     [rbp+7D0h+var_40], rax
0x180047b0c  mov     rbx, [rbp+7D0h+arg_28]
0x180047b13  xorps   xmm0, xmm0
0x180047b16  xor     r14d, r14d
0x180047b19  mov     [rsp+8D0h+ProcessHandle], rdx
0x180047b1e  mov     r13d, r8d
0x180047b21  mov     [rsp+8D0h+var_878], r8d
0x180047b26  mov     rsi, rdx
0x180047b29  mov     [rsp+8D0h+var_880], r14d
0x180047b2e  mov     r15, rcx
0x180047b31  mov     [rsp+8D0h+hFile], r14
0x180047b36  xor     edx, edx; Val
0x180047b38  mov     [rsp+8D0h+var_870], r9d
0x180047b3d  mov     r8d, 98h; Size
0x180047b43  lea     rcx, [rbp+7D0h+var_7C0]; void *
0x180047b47  movups  xmmword ptr [rbp+7D0h+var_7F0], xmm0
0x180047b4b  mov     edi, r14d
0x180047b4e  movups  [rbp+7D0h+var_7E0], xmm0
0x180047b52  movups  xmmword ptr [rbp+7D0h+ExceptionParam.ThreadId], xmm0
0x180047b56  call    memset_0
0x180047b5b  xorps   xmm0, xmm0
0x180047b5e  lea     rcx, [rbp+7D0h+var_720]; void *
0x180047b65  xor     edx, edx; Val
0x180047b67  mov     r8d, 4D0h; Size
0x180047b6d  movups  [rbp+7D0h+var_810], xmm0
0x180047b71  call    memset_0
0x180047b76  xor     eax, eax
0x180047b78  mov     [rbp+7D0h+hMem], r14
0x180047b7c  mov     [rbp+7D0h+var_838], rax
0x180047b80  lea     rdx, [rbp+7D0h+hMem]; SecurityDescriptor
0x180047b84  xorps   xmm0, xmm0
0x180047b87  mov     [rsp+8D0h+hObject], r14
0x180047b8c  lea     rax, ?static_MiniDumpCallback@CReflectedDump@@KAHPEAXQEAU_MINIDUMP_CALLBACK_INPUT@@PEAU_MINIDUMP_CALLBACK_OUTPUT@@@Z; CReflectedDump::static_MiniDumpCallback(void *,_MINIDUMP_CALLBACK_INPUT * const,_MINIDUMP_CALLBACK_OUTPUT *)
0x180047b93  mov     [rsp+8D0h+var_86C], r14d
0x180047b98  movups  [rbp+7D0h+var_848], xmm0
0x180047b9c  mov     rcx, rsi; ProcessHandle
0x180047b9f  mov     [rbp+7D0h+CallbackParam.CallbackRoutine], rax
0x180047ba3  mov     [rbp+7D0h+CallbackParam.CallbackParam], r15
0x180047ba7  mov     dword ptr [rbp+7D0h+var_848], 18h
0x180047bae  mov     dword ptr [rbp+7D0h+var_838], r14d
0x180047bb2  call    GetDumpSecurityDescriptor
0x180047bb7  xor     esi, esi
0x180047bb9  mov     r14d, eax
0x180047bbc  test    eax, eax
0x180047bbe  jns     short loc_180047BF9
0x180047bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180047bc7  lea     rbx, WPP_GLOBAL_Control
0x180047bce  cmp     rcx, rbx
0x180047bd1  jz      loc_180047C77
0x180047bd7  test    byte ptr [rcx+1Ch], 1
0x180047bdb  jz      loc_180047C77
0x180047be1  lea     edx, [rsi+1Eh]
0x180047be4  mov     rcx, [rcx+10h]
0x180047be8  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x180047bef  mov     r9d, eax
0x180047bf2  call    WPP_SF_d
0x180047bf7  jmp     short loc_180047C77
0x180047bf9  mov     rax, [rbp+7D0h+hMem]
0x180047bfd  lea     rdi, aMdref; ".mdref"
0x180047c04  mov     r12d, dword ptr [rbp+7D0h+arg_20]
0x180047c0b  and     r12d, 2
0x180047c0f  mov     qword ptr [rbp+7D0h+var_848+8], rax
0x180047c13  lea     rax, aTdref; ".tdref"
0x180047c1a  cmovz   rdi, rax
0x180047c1e  test    rbx, rbx
0x180047c21  jz      loc_180047EA9
0x180047c27  cmp     [rbx], si
0x180047c2a  jz      loc_180047EA9
0x180047c30  mov     rcx, rbx
0x180047c33  call    cs:__imp_WerpValidateReportKey
0x180047c39  mov     r14d, eax
0x180047c3c  test    eax, eax
0x180047c3e  jns     loc_180047D2E
0x180047c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180047c4b  lea     rbx, WPP_GLOBAL_Control
0x180047c52  cmp     rcx, rbx
0x180047c55  jz      short loc_180047C75
0x180047c57  test    byte ptr [rcx+1Ch], 1
0x180047c5b  jz      short loc_180047C75
0x180047c5d  mov     edx, 1Fh
0x180047c62  mov     r9d, eax
0x180047c65  mov     rcx, [rcx+10h]
0x180047c69  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x180047c70  call    WPP_SF_d
0x180047c75  mov     edi, esi
0x180047c77  mov     rcx, [rsp+8D0h+hObject]; hObject
0x180047c7c  mov     [rsp+8D0h+hObject], 0
0x180047c85  lea     rax, [rcx+1]
0x180047c89  cmp     rax, 1
0x180047c8d  jbe     short loc_180047C95
0x180047c8f  call    cs:__imp_CloseHandle
0x180047c95  mov     rcx, [rsp+8D0h+hFile]; hObject
0x180047c9a  lea     rax, [rcx+1]
0x180047c9e  cmp     rax, 1
0x180047ca2  jbe     short loc_180047CAA
0x180047ca4  call    cs:__imp_CloseHandle
0x180047caa  mov     rcx, [rbp+7D0h+var_7F0+8]; hObject
0x180047cae  test    rcx, rcx
0x180047cb1  jz      short loc_180047CC1
0x180047cb3  call    cs:__imp_CloseHandle
0x180047cb9  mov     [rbp+7D0h+var_7F0+8], 0
0x180047cc1  test    r14d, r14d
0x180047cc4  jns     short loc_180047CCE
0x180047cc6  mov     rcx, r15; this
0x180047cc9  call    ?Cleanup@CReflectedDump@@QEAAXXZ; CReflectedDump::Cleanup(void)
0x180047cce  test    edi, edi
0x180047cd0  jz      short loc_180047CDD
0x180047cd2  mov     rcx, [rsp+8D0h+ProcessHandle]; ProcessHandle
0x180047cd7  call    cs:__imp_NtResumeProcess
0x180047cdd  mov     rcx, [rsp+8D0h+hObject]; hObject
0x180047ce2  lea     rax, [rcx+1]
0x180047ce6  cmp     rax, 1
0x180047cea  jbe     short loc_180047CF2
0x180047cec  call    cs:__imp_CloseHandle
0x180047cf2  mov     rcx, [rbp+7D0h+hMem]; hMem
0x180047cf6  test    rcx, rcx
0x180047cf9  jz      short loc_180047D01
0x180047cfb  call    cs:__imp_LocalFree
0x180047d01  mov     eax, r14d
0x180047d04  mov     rcx, [rbp+7D0h+var_40]
0x180047d0b  xor     rcx, rsp; StackCookie
0x180047d0e  call    __security_check_cookie
0x180047d13  mov     rbx, [rsp+8D0h+arg_18]
0x180047d1b  add     rsp, 8A0h
0x180047d22  pop     r15
0x180047d24  pop     r14
0x180047d26  pop     r13
0x180047d28  pop     r12
0x180047d2a  pop     rdi
0x180047d2b  pop     rsi
0x180047d2c  pop     rbp
0x180047d2d  retn
0x180047d2e  lea     r8, [rsp+8D0h+var_86C]
0x180047d33  mov     [rsp+8D0h+var_86C], 104h
0x180047d3b  lea     rdx, [rbp+7D0h+var_250]
0x180047d42  mov     ecx, 3
0x180047d47  call    cs:__imp_WerpGetStorePath
0x180047d4d  mov     r14d, eax
0x180047d50  test    eax, eax
0x180047d52  jns     short loc_180047D7F
0x180047d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180047d5b  lea     rbx, WPP_GLOBAL_Control
0x180047d62  cmp     rcx, rbx
0x180047d65  jz      loc_180047C75
0x180047d6b  test    byte ptr [rcx+1Ch], 1
0x180047d6f  jz      loc_180047C75
0x180047d75  mov     edx, 20h ; ' '
0x180047d7a  jmp     loc_180047C62
0x180047d7f  lea     r8, SubBlock; "\\"
0x180047d86  lea     rcx, [rbp+7D0h+var_250]; wchar_t *
0x180047d8d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180047d92  mov     r14d, eax
0x180047d95  test    eax, eax
0x180047d97  jns     short loc_180047DC4
0x180047d99  mov     rcx, cs:WPP_GLOBAL_Control
0x180047da0  lea     rbx, WPP_GLOBAL_Control
0x180047da7  cmp     rcx, rbx
0x180047daa  jz      loc_180047C75
0x180047db0  test    byte ptr [rcx+1Ch], 1
0x180047db4  jz      loc_180047C75
0x180047dba  mov     edx, 21h ; '!'
0x180047dbf  jmp     loc_180047C62
0x180047dc4  mov     r8, rbx; wchar_t *
0x180047dc7  lea     rcx, [rbp+7D0h+var_250]; wchar_t *
0x180047dce  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180047dd3  mov     r14d, eax
0x180047dd6  test    eax, eax
0x180047dd8  jns     short loc_180047E05
0x180047dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180047de1  lea     rbx, WPP_GLOBAL_Control
0x180047de8  cmp     rcx, rbx
0x180047deb  jz      loc_180047C75
0x180047df1  test    byte ptr [rcx+1Ch], 1
0x180047df5  jz      loc_180047C75
0x180047dfb  mov     edx, 22h ; '"'
0x180047e00  jmp     loc_180047C62
0x180047e05  lea     r8, SubBlock; "\\"
0x180047e0c  lea     rcx, [rbp+7D0h+var_250]; wchar_t *
0x180047e13  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180047e18  mov     r14d, eax
0x180047e1b  test    eax, eax
0x180047e1d  jns     short loc_180047E4A
0x180047e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180047e26  lea     rbx, WPP_GLOBAL_Control
0x180047e2d  cmp     rcx, rbx
0x180047e30  jz      loc_180047C75
0x180047e36  test    byte ptr [rcx+1Ch], 1
0x180047e3a  jz      loc_180047C75
0x180047e40  mov     edx, 23h ; '#'
0x180047e45  jmp     loc_180047C62
0x180047e4a  mov     dword ptr [rsp+8D0h+var_898], esi
0x180047e4e  lea     rax, [rbp+7D0h+var_848]
0x180047e52  mov     [rsp+8D0h+dwOptions], esi
0x180047e56  lea     r9, [r15+8]
0x180047e5a  mov     r8, rdi
0x180047e5d  mov     qword ptr [rsp+8D0h+bInheritHandle], rax
0x180047e62  lea     rdx, [rbp+7D0h+var_250]
0x180047e69  lea     rcx, [rsp+8D0h+hFile]
0x180047e6e  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180047e73  mov     r14d, eax
0x180047e76  test    eax, eax
0x180047e78  jns     loc_180047EFF
0x180047e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180047e85  lea     rbx, WPP_GLOBAL_Control
0x180047e8c  cmp     rcx, rbx
0x180047e8f  jz      loc_1800481F1
0x180047e95  test    byte ptr [rcx+1Ch], 1
0x180047e99  jz      loc_1800481F1
0x180047e9f  mov     edx, 24h ; '$'
0x180047ea4  jmp     loc_180047C62
0x180047ea9  mov     dword ptr [rsp+8D0h+var_898], esi
0x180047ead  lea     rax, [rbp+7D0h+var_848]
0x180047eb1  mov     [rsp+8D0h+dwOptions], esi
0x180047eb5  lea     r9, [r15+8]
0x180047eb9  mov     r8, rdi
0x180047ebc  mov     qword ptr [rsp+8D0h+bInheritHandle], rax
0x180047ec1  xor     edx, edx
0x180047ec3  lea     rcx, [rsp+8D0h+hFile]
0x180047ec8  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180047ecd  mov     r14d, eax
0x180047ed0  test    eax, eax
0x180047ed2  jns     short loc_180047EFF
0x180047ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180047edb  lea     rbx, WPP_GLOBAL_Control
0x180047ee2  cmp     rcx, rbx
0x180047ee5  jz      loc_1800481F1
0x180047eeb  test    byte ptr [rcx+1Ch], 1
0x180047eef  jz      loc_1800481F1
0x180047ef5  mov     edx, 25h ; '%'
0x180047efa  jmp     loc_180047C62
0x180047eff  lea     rcx, [rsp+8D0h+hObject]
0x180047f04  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180047f09  mov     rsi, rax
0x180047f0c  call    cs:__imp_GetCurrentProcess
0x180047f12  mov     rdi, rax
0x180047f15  call    cs:__imp_GetCurrentProcess
0x180047f1b  mov     rbx, rax
0x180047f1e  call    cs:__imp_GetCurrentProcess
0x180047f24  mov     [rsp+8D0h+dwOptions], 0; dwOptions
0x180047f2c  mov     r9, rsi; lpTargetHandle
0x180047f2f  mov     rcx, rax; hSourceProcessHandle
0x180047f32  mov     [rsp+8D0h+bInheritHandle], 0; bInheritHandle
0x180047f3a  mov     r8, rdi; hTargetProcessHandle
0x180047f3d  mov     [rsp+8D0h+dwDesiredAccess], 100000h; dwDesiredAccess
0x180047f45  mov     rdx, rbx; hSourceHandle
0x180047f48  call    cs:__imp_DuplicateHandle
0x180047f4e  xor     esi, esi
0x180047f50  test    eax, eax
0x180047f52  jnz     short loc_180047FA6
0x180047f54  call    cs:__imp_GetLastError
0x180047f5a  mov     r14d, eax
0x180047f5d  test    eax, eax
0x180047f5f  jle     short loc_180047F6C
0x180047f61  movzx   r14d, ax
0x180047f65  or      r14d, 80070000h
0x180047f6c  test    r14d, r14d
0x180047f6f  mov     eax, 80004005h
0x180047f74  cmovns  r14d, eax
0x180047f78  mov     rcx, cs:WPP_GLOBAL_Control
0x180047f7f  lea     rbx, WPP_GLOBAL_Control
0x180047f86  cmp     rcx, rbx
0x180047f89  jz      loc_1800481F1
0x180047f8f  test    byte ptr [rcx+1Ch], 1
0x180047f93  jz      loc_1800481F1
0x180047f99  mov     edx, 26h ; '&'
0x180047f9e  mov     r9d, r14d
0x180047fa1  jmp     loc_180047C65
0x180047fa6  test    [rbp+7D0h+arg_20], 1
0x180047fad  lea     rbx, WPP_GLOBAL_Control
0x180047fb4  mov     rsi, [rsp+8D0h+ProcessHandle]
0x180047fb9  mov     edi, 0C0000000h
0x180047fbe  jnz     short loc_180047FF9
0x180047fc0  mov     rcx, rsi; ProcessHandle
0x180047fc3  call    cs:__imp_NtSuspendProcess
0x180047fc9  and     eax, edi
0x180047fcb  cmp     eax, edi
0x180047fcd  jnz     short loc_180048041
0x180047fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180047fd6  cmp     rcx, rbx
0x180047fd9  jz      short loc_180047FF9
0x180047fdb  test    byte ptr [rcx+1Ch], 1
0x180047fdf  jz      short loc_180047FF9
0x180047fe1  mov     rcx, [rcx+10h]
0x180047fe5  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x180047fec  mov     edx, 27h ; '''
0x180047ff1  mov     r9d, r14d
0x180047ff4  call    WPP_SF_d
0x180047ff9  mov     edi, [rsp+8D0h+var_880]
  ... truncated ...
```
