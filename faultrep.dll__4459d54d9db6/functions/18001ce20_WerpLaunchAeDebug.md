# WerpLaunchAeDebug

- ea: `0x18001ce20`
- end: `0x18001d7f9`
- name: `WerpLaunchAeDebug`
- size: `2521`
- prototype: `__int64 __fastcall(HANDLE Process, HANDLE Thread, __int64, _OWORD *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ff8c`
- `0x180014c34`

## callees

- `0x180002890`
- `0x180003474`
- `0x180003617`
- `0x180006684`
- `0x180007704`
- `0x18001ce20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001d478`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001d501`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001d478`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001d501`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001cedc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001cedc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001cf5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001cf65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001cf5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001cf65`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001d572`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001d572`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001d748`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001d748`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001cfe3`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001cfe3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001d62e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001d62e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ceec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d48d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d50b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ceec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d48d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d50b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d638`
- `ntdll!NtWaitForMultipleObjects` at `0x18001d6d3`
- `ntdll!NtWaitForMultipleObjects` at `0x18001d6d3`
- `ntdll!RtlSetCurrentTransaction` at `0x18001d29d`
- `ntdll!RtlSetCurrentTransaction` at `0x18001d756`
- `ntdll!RtlSetCurrentTransaction` at `0x18001d29d`
- `ntdll!RtlSetCurrentTransaction` at `0x18001d756`
- `ntdll!RtlGetCurrentTransaction` at `0x18001d291`
- `ntdll!RtlGetCurrentTransaction` at `0x18001d291`
- `ntdll!RtlGetNtSystemRoot` at `0x18001d1f6`
- `ntdll!RtlGetNtSystemRoot` at `0x18001d1f6`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18001d1e4`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18001d1e4`
- `ntdll!NtQueryInformationProcess` at `0x18001d34f`
- `ntdll!NtQueryInformationProcess` at `0x18001d34f`
- `ntdll!DbgPrintEx` at `0x18001d242`
- `ntdll!DbgPrintEx` at `0x18001d380`
- `ntdll!DbgPrintEx` at `0x18001d3c3`
- `ntdll!DbgPrintEx` at `0x18001d449`
- `ntdll!DbgPrintEx` at `0x18001d242`
- `ntdll!DbgPrintEx` at `0x18001d380`
- `ntdll!DbgPrintEx` at `0x18001d3c3`
- `ntdll!DbgPrintEx` at `0x18001d449`
- `ntdll!NtQuerySystemInformation` at `0x18001cfcd`
- `ntdll!NtQuerySystemInformation` at `0x18001cfcd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cf9f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cf9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d5d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d5df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d733`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d791`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d7a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d7c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d5d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d5df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d733`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d791`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d7a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d7c2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001cf8b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001cf8b`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x18001d6fe`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x18001d6fe`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x18001d038`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x18001d038`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001cf27`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001d4e1`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001cf27`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001d4e1`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18001d1a5`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18001d1a5`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001d76c`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001d782`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001d76c`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001d782`

## string_xrefs

- `0x18001d1fc`: `%s\system32\%s`
- `0x18001d229`: `WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printing the debugger path with 0x%x\n`
- `0x18001d280`: `WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printng the debugger commandline with 0x%x\n`
- `0x18001d4c3`: `WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n`
- `0x18001d5aa`: `WER/CrashAPI/%u:%u: ERROR UpdateProcThreadAttribute failed: 0x%x\n`

## pseudocode

```c
__int64 __fastcall WerpLaunchAeDebug(HANDLE Process, HANDLE Thread, __int64 a3, _OWORD *a4, __int64 a5)
{
  struct _PROC_THREAD_ATTRIBUTE_LIST *v9; // rbx
  __int64 v10; // rsi
  wchar_t *v11; // rdi
  signed int LastError; // eax
  signed int v13; // r14d
  HANDLE *v14; // r14
  HANDLE CurrentProcess; // rsi
  HANDLE v16; // rax
  char *v17; // rsi
  HANDLE v18; // r12
  _BYTE *v19; // r14
  __int128 v20; // xmm0
  __int64 v21; // rcx
  __int128 v22; // xmm1
  char *v23; // rax
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  _DWORD *v42; // r12
  const wchar_t *v43; // r14
  const wchar_t *v44; // r15
  __int64 NtSystemRoot; // rax
  DWORD v46; // eax
  const CHAR *v47; // r8
  _DWORD *v48; // r15
  DWORD v49; // r13d
  unsigned int v50; // r8d
  NTSTATUS InformationProcess; // r14d
  DWORD v52; // eax
  unsigned int v53; // r14d
  DWORD v54; // eax
  int v55; // eax
  int v56; // r14d
  int v57; // r15d
  DWORD v58; // eax
  signed int v59; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v60; // rax
  signed int v61; // eax
  signed int v62; // eax
  signed int v63; // eax
  NTSTATUS v64; // eax
  HANDLE v65; // rcx
  DWORD dwDesiredAccess[2]; // [rsp+20h] [rbp-E0h]
  BOOL bInheritHandle[2]; // [rsp+28h] [rbp-D8h]
  char ProcessInformation[4]; // [rsp+50h] [rbp-B0h] BYREF
  int Value[3]; // [rsp+54h] [rbp-ACh] BYREF
  DWORD ProcessId; // [rsp+60h] [rbp-A0h]
  int v72; // [rsp+64h] [rbp-9Ch]
  HANDLE v73; // [rsp+68h] [rbp-98h] BYREF
  DWORD CurrentProcessId_0; // [rsp+70h] [rbp-90h]
  SIZE_T NumberOfBytesWritten; // [rsp+78h] [rbp-88h] BYREF
  __int64 v76; // [rsp+80h] [rbp-80h]
  ULONG_PTR Size; // [rsp+88h] [rbp-78h] BYREF
  HANDLE hProcess; // [rsp+90h] [rbp-70h]
  __int64 CurrentTransaction; // [rsp+98h] [rbp-68h]
  struct _PROCESS_INFORMATION hObject; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID lpAddress; // [rsp+B8h] [rbp-48h]
  HANDLE Object[2]; // [rsp+C0h] [rbp-40h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+F0h] [rbp-10h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v85; // [rsp+158h] [rbp+58h]
  __int64 SystemInformation; // [rsp+160h] [rbp+60h] BYREF
  int v87; // [rsp+168h] [rbp+68h]
  _DWORD Buffer[2]; // [rsp+170h] [rbp+70h] BYREF
  DWORD ThreadId; // [rsp+178h] [rbp+78h]
  int v90; // [rsp+17Ch] [rbp+7Ch]
  __int64 v91; // [rsp+180h] [rbp+80h]
  __int64 v92; // [rsp+188h] [rbp+88h]
  __int64 v93; // [rsp+190h] [rbp+90h]
  __int128 v94; // [rsp+198h] [rbp+98h]
  __int128 v95; // [rsp+1A8h] [rbp+A8h]
  __int128 v96; // [rsp+1B8h] [rbp+B8h]
  __int128 v97; // [rsp+1C8h] [rbp+C8h]
  __int128 v98; // [rsp+1D8h] [rbp+D8h]
  __int128 v99; // [rsp+1E8h] [rbp+E8h]
  __int128 v100; // [rsp+1F8h] [rbp+F8h]
  __int128 v101; // [rsp+208h] [rbp+108h]
  __int128 v102; // [rsp+218h] [rbp+118h]
  __int64 v103; // [rsp+228h] [rbp+128h]
  char v104; // [rsp+230h] [rbp+130h] BYREF

  hProcess = Process;
  v76 = a5;
  v73 = 0;
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  Size = 0;
  SystemInformation = 0;
  v87 = 0;
  memset(&hObject, 0, sizeof(hObject));
  v9 = 0;
  v72 = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v10 = 0;
  CurrentTransaction = 0;
  *(_OWORD *)Object = 0;
  memset_0(Buffer, 0, 0x590u);
  NumberOfBytesWritten = 0;
  Value[0] = -1;
  ProcessInformation[0] = 0;
  ProcessId = GetProcessId(Process);
  if ( !ProcessId )
  {
    v11 = 0;
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_88;
  }
  CurrentProcessId_0 = GetCurrentProcessId_0();
  v11 = (wchar_t *)VirtualAlloc(0, 0x4D0u, 0x1000u, 4u);
  if ( !v11 )
  {
    v13 = -2147024882;
    goto LABEL_88;
  }
  lpAddress = 0;
  EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  EventAttributes.bInheritHandle = 1;
  v14 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&v73);
  CurrentProcess = GetCurrentProcess();
  v16 = GetCurrentProcess();
  DuplicateHandle(v16, Thread, CurrentProcess, v14, 0, 1, 2u);
  v17 = (char *)CreateEventW(&EventAttributes, 1, 0, 0);
  if ( v17 == (char *)-1LL
    || v17 + 1 == (char *)1
    || !a3
    || NtQuerySystemInformation(SystemProcessorInformation, &SystemInformation, 0xCu, 0) < 0 )
  {
    goto LABEL_19;
  }
  if ( Thread )
    ThreadId = GetThreadId(Thread);
  else
    ThreadId = 0;
  Buffer[1] = (unsigned __int16)SystemInformation;
  v91 = *(_QWORD *)(a3 + 16);
  Buffer[0] = 40;
  v90 = 0;
  if ( ProcessId == CurrentProcessId_0 )
  {
    v92 = a3;
    v42 = Buffer;
    v93 = (__int64)a4;
    goto LABEL_20;
  }
  v18 = hProcess;
  lpAddress = VirtualAllocEx(hProcess, 0, 0x590u, 0x1000u, 4u);
  v19 = lpAddress;
  if ( !lpAddress )
    goto LABEL_19;
  v20 = *(_OWORD *)a3;
  v21 = 9;
  v22 = *(_OWORD *)(a3 + 16);
  v103 = *(_QWORD *)(a3 + 144);
  v23 = &v104;
  v94 = v20;
  v24 = *(_OWORD *)(a3 + 32);
  v95 = v22;
  v25 = *(_OWORD *)(a3 + 48);
  v96 = v24;
  v26 = *(_OWORD *)(a3 + 64);
  v97 = v25;
  v27 = *(_OWORD *)(a3 + 80);
  v98 = v26;
  v28 = *(_OWORD *)(a3 + 96);
  v99 = v27;
  v29 = *(_OWORD *)(a3 + 112);
  v100 = v28;
  v30 = *(_OWORD *)(a3 + 128);
  v101 = v29;
  v102 = v30;
  do
  {
    v31 = a4[1];
    *(_OWORD *)v23 = *a4;
    v32 = a4[2];
    *((_OWORD *)v23 + 1) = v31;
    v33 = a4[3];
    *((_OWORD *)v23 + 2) = v32;
    v34 = a4[4];
    *((_OWORD *)v23 + 3) = v33;
    v35 = a4[5];
    *((_OWORD *)v23 + 4) = v34;
    v36 = a4[6];
    *((_OWORD *)v23 + 5) = v35;
    v37 = a4[7];
    a4 += 8;
    *((_OWORD *)v23 + 6) = v36;
    *((_OWORD *)v23 + 7) = v37;
    v23 += 128;
    --v21;
  }
  while ( v21 );
  v38 = a4[1];
  *(_OWORD *)v23 = *a4;
  v39 = a4[2];
  *((_OWORD *)v23 + 1) = v38;
  v40 = a4[3];
  *((_OWORD *)v23 + 2) = v39;
  v41 = a4[4];
  *((_OWORD *)v23 + 3) = v40;
  *((_OWORD *)v23 + 4) = v41;
  NumberOfBytesWritten = v19 - (_BYTE *)Buffer;
  v92 = (__int64)(v19 + 40);
  v93 = (__int64)(v19 + 192);
  if ( !WriteProcessMemory(v18, v19, Buffer, 0x590u, &NumberOfBytesWritten) || NumberOfBytesWritten != 1424 )
  {
LABEL_19:
    v42 = 0;
    goto LABEL_20;
  }
  v42 = v19;
LABEL_20:
  v43 = (const wchar_t *)(v76 + 4);
  if ( *(_WORD *)(v76 + 4) == 34 || RtlDetermineDosPathNameType_U((PCWSTR)(v76 + 4)) != RtlPathTypeRelative )
  {
    v44 = v43;
  }
  else
  {
    v44 = v11 + 323;
    NtSystemRoot = RtlGetNtSystemRoot();
    v13 = StringCchPrintfW(v11 + 323, 0x125u, L"%s\\system32\\%s", NtSystemRoot, v43);
    if ( v13 < 0 )
    {
      v46 = GetCurrentProcessId_0();
      bInheritHandle[0] = v13;
      v47 = "WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printing the debugger path with 0x%x\n";
      dwDesiredAccess[0] = 4834;
      goto LABEL_24;
    }
  }
  v13 = StringCchPrintfW(v11, 0x143u, v44, ProcessId, v17, v42);
  if ( v13 < 0 )
  {
    v46 = GetCurrentProcessId_0();
    bInheritHandle[0] = v13;
    v47 = "WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printng the debugger commandline with 0x%x\n";
    dwDesiredAccess[0] = 4855;
    goto LABEL_24;
  }
  CurrentTransaction = RtlGetCurrentTransaction();
  RtlSetCurrentTransaction(0);
  v48 = (_DWORD *)v76;
  StartupInfo.cb = 112;
  StartupInfo.lpDesktop = (LPWSTR)&dword_18004FE4C;
  v49 = (*(_DWORD *)v76 & 4) != 0 ? 0x40000 : 0;
  if ( (*(_DWORD *)v76 & 4) != 0 )
  {
    v50 = (*(_DWORD *)v76 >> 3) & 0xF;
    if ( v50 < 4 || v50 == 5 || v50 == 6 || v50 == 7 )
    {
      Value[0] = (*(_DWORD *)v76 >> 3) & 0xF;
    }
    else
    {
      Value[0] = -1;
      if ( v50 == 14 )
      {
        ProcessInformation[0] = 0;
        InformationProcess = NtQueryInformationProcess(
                               hProcess,
                               ProcessAffinityUpdateMode|ProcessUserModeIOPL,
                               ProcessInformation,
                               1u,
                               0);
        if ( InformationProcess >= 0 )
        {
          v53 = (unsigned __int8)ProcessInformation[0];
          v54 = GetCurrentProcessId_0();
          DbgPrintEx(
            0x96u,
            2u,
            "WER/CrashAPI/%u:%u: TRACE Faulting process protection/signer: %02x/%02x\n",
            v54,
            4908,
            v53 & 7,
            v53 >> 4);
          if ( (ProcessInformation[0] & 7u) >= 3 || (ProcessInformation[0] & 0xF0u) >= 0x90 )
            v55 = -1;
          else
            v55 = *((_DWORD *)qword_1800531A0
                  + 9 * (ProcessInformation[0] & 7)
                  + ((unsigned __int64)(unsigned __int8)ProcessInformation[0] >> 4));
          Value[0] = v55;
        }
        else
        {
          v52 = GetCurrentProcessId_0();
          DbgPrintEx(
            0x96u,
            1u,
            "WER/CrashAPI/%u:%u: WARNING NtQueryInformationProcess/ProcessProtectionInformation failed: NTSTATUS %08X\n",
            v52,
            4903,
            InformationProcess);
        }
      }
    }
  }
  v56 = Value[0];
  v57 = (*v48 >> 3) & 0xF;
  v58 = GetCurrentProcessId_0();
  DbgPrintEx(0x96u, 2u, "WER/CrashAPI/%u:%u: TRACE Mapped protection level %02X -> %08X\n", v58, 4922, v57, v56);
  if ( (*(_BYTE *)v76 & 4) != 0 && Value[0] != -1 )
  {
    if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) && GetLastError() != 122 )
    {
      v59 = GetLastError();
      v13 = v59;
      if ( v59 > 0 )
        v13 = (unsigned __int16)v59 | 0x80070000;
      if ( v13 >= 0 )
        v13 = -2147467259;
      v46 = GetCurrentProcessId_0();
      bInheritHandle[0] = v13;
      dwDesiredAccess[0] = 4937;
LABEL_51:
      v47 = "WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n";
      goto LABEL_24;
    }
    v60 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)VirtualAlloc(0, Size, 0x1000u, 4u);
    v9 = v60;
    if ( !v60 )
    {
      v13 = -2147024882;
      v46 = GetCurrentProcessId_0();
      bInheritHandle[0] = -2147024882;
      v47 = "WER/CrashAPI/%u:%u: ERROR Failed to allocate attribute list: 0x%x\n";
      dwDesiredAccess[0] = 4950;
      goto LABEL_24;
    }
    if ( !InitializeProcThreadAttributeList(v60, 1u, 0, &Size) )
    {
      v61 = GetLastError();
      v13 = v61;
      if ( v61 > 0 )
        v13 = (unsigned __int16)v61 | 0x80070000;
      if ( v13 >= 0 )
        v13 = -2147467259;
      v46 = GetCurrentProcessId_0();
      bInheritHandle[0] = v13;
      dwDesiredAccess[0] = 4962;
      goto LABEL_51;
    }
    v72 = 1;
    if ( !UpdateProcThreadAttribute(v9, 0, 0x2000Bu, Value, 4u, 0, 0) )
    {
      v62 = GetLastError();
      v13 = v62;
      if ( v62 > 0 )
        v13 = (unsigned __int16)v62 | 0x80070000;
      if ( v13 >= 0 )
        v13 = -2147467259;
      v46 = GetCurrentProcessId_0();
      bInheritHandle[0] = v13;
      v47 = "WER/CrashAPI/%u:%u: ERROR UpdateProcThreadAttribute failed: 0x%x\n";
      dwDesiredAccess[0] = 4978;
      goto LABEL_24;
    }
    v85 = v9;
    v49 |= 0x80000u;
  }
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  memset(&hObject, 0, sizeof(hObject));
  if ( CreateProcessW(0, v11, 0, 0, 1, v49, 0, 0, &StartupInfo, &hObject) )
  {
    v13 = 0;
    if ( (unsigned __int64)(v17 + 1) > 1 )
    {
      Object[1] = hObject.hProcess;
      Object[0] = v17;
      while ( 1 )
      {
        v64 = NtWaitForMultipleObjects(2u, Object, WaitAny, 1u, 0);
        if ( !v64 )
          break;
        if ( v64 == 1 )
        {
          v13 = -2147023829;
          goto LABEL_83;
        }
      }
    }
    goto LABEL_83;
  }
  v63 = GetLastError();
  v13 = v63;
  if ( v63 > 0 )
    v13 = (unsigned __int16)v63 | 0x80070000;
  if ( v13 >= 0 )
    v13 = -2147467259;
  v46 = GetCurrentProcessId_0();
  bInheritHandle[0] = v13;
  v47 = "WER/CrashAPI/%u:%u: ERROR Debugger spawn failed: 0x%x\n";
  dwDesiredAccess[0] = 5003;
LABEL_24:
  DbgPrintEx(0x96u, 0, v47, v46, *(_QWORD *)dwDesiredAccess, *(_QWORD *)bInheritHandle);
LABEL_83:
  if ( lpAddress )
    VirtualFreeEx(hProcess, lpAddress, 0, 0x8000u);
  if ( (unsigned __int64)(v17 + 1) > 1 )
    CloseHandle(v17);
  v10 = CurrentTransaction;
LABEL_88:
  v65 = v73;
  v73 = 0;
  if ( (unsigned __int64)v65 + 1 > 1 )
    CloseHandle(v65);
  if ( v72 && v9 )
    DeleteProcThreadAttributeList(v9);
  if ( v10 )
    RtlSetCurrentTransaction(v10);
  if ( v11 )
    VirtualFree(v11, 0, 0x8000u);
  if ( v9 )
    VirtualFree(v9, 0, 0x8000u);
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  memset(&hObject, 0, sizeof(hObject));
  if ( (unsigned __int64)v73 + 1 > 1 )
    CloseHandle(v73);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001ce20  push    rbp
0x18001ce22  push    rbx
0x18001ce23  push    rsi
0x18001ce24  push    rdi
0x18001ce25  push    r12
0x18001ce27  push    r13
0x18001ce29  push    r14
0x18001ce2b  push    r15
0x18001ce2d  lea     rbp, [rsp-618h]
0x18001ce35  sub     rsp, 718h
0x18001ce3c  mov     rax, cs:__security_cookie
0x18001ce43  xor     rax, rsp
0x18001ce46  mov     [rbp+650h+var_50], rax
0x18001ce4d  mov     rax, [rbp+650h+arg_20]
0x18001ce54  xor     r14d, r14d
0x18001ce57  mov     r13, r8
0x18001ce5a  mov     [rbp+650h+hProcess], rcx
0x18001ce5e  mov     r12, rdx
0x18001ce61  mov     [rbp+650h+var_6D0], rax
0x18001ce65  mov     rdi, rcx
0x18001ce68  mov     [rsp+750h+var_6E8], r14
0x18001ce6d  lea     r8d, [r14+68h]; Size
0x18001ce71  mov     qword ptr [rbp+650h+StartupInfo.cb], r14
0x18001ce75  xor     edx, edx; Val
0x18001ce77  lea     rcx, [rbp+650h+StartupInfo.lpReserved]; void *
0x18001ce7b  mov     r15, r9
0x18001ce7e  call    memset_0
0x18001ce83  xor     eax, eax
0x18001ce85  mov     [rbp+650h+Size], r14
0x18001ce89  xorps   xmm0, xmm0
0x18001ce8c  mov     [rbp+650h+var_6A0], rax
0x18001ce90  xor     edx, edx; Val
0x18001ce92  mov     qword ptr [rbp+650h+EventAttributes.bInheritHandle], rax
0x18001ce96  mov     r8d, 590h; Size
0x18001ce9c  mov     [rbp+650h+SystemInformation], rax
0x18001cea0  lea     rcx, [rbp+650h+Buffer]; void *
0x18001cea4  mov     [rbp+650h+var_5E8], eax
0x18001cea7  movups  xmmword ptr [rbp+650h+hObject], xmm0
0x18001ceab  mov     ebx, r14d
0x18001ceae  mov     [rsp+750h+var_6EC], r14d
0x18001ceb3  movups  xmmword ptr [rbp+650h+EventAttributes.nLength], xmm0
0x18001ceb7  mov     esi, r14d
0x18001ceba  mov     [rbp+650h+var_6B8], r14
0x18001cebe  movups  xmmword ptr [rbp+650h+Object], xmm0
0x18001cec2  call    memset_0
0x18001cec7  mov     rcx, rdi; Process
0x18001ceca  mov     [rsp+750h+NumberOfBytesWritten], r14
0x18001cecf  mov     [rsp+750h+Value], 0FFFFFFFFh
0x18001ced7  mov     [rsp+750h+ProcessInformation], r14b
0x18001cedc  call    cs:__imp_GetProcessId
0x18001cee2  mov     [rsp+750h+var_6F0], eax
0x18001cee6  test    eax, eax
0x18001cee8  jnz     short loc_18001CF0D
0x18001ceea  xor     edi, edi
0x18001ceec  call    cs:__imp_GetLastError
0x18001cef2  mov     r14d, eax
0x18001cef5  test    eax, eax
0x18001cef7  jle     loc_18001D71B
0x18001cefd  movzx   r14d, ax
0x18001cf01  or      r14d, 80070000h
0x18001cf08  jmp     loc_18001D71B
0x18001cf0d  call    GetCurrentProcessId_0
0x18001cf12  xor     ecx, ecx; lpAddress
0x18001cf14  mov     [rsp+750h+var_6E0], eax
0x18001cf18  mov     edx, 4D0h; dwSize
0x18001cf1d  mov     r8d, 1000h; flAllocationType
0x18001cf23  lea     r9d, [rcx+4]; flProtect
0x18001cf27  call    cs:__imp_VirtualAlloc
0x18001cf2d  mov     rdi, rax
0x18001cf30  test    rax, rax
0x18001cf33  jz      loc_18001D7EE
0x18001cf39  lea     rcx, [rsp+750h+var_6E8]
0x18001cf3e  mov     [rbp+650h+lpAddress], r14
0x18001cf42  mov     [rbp+650h+EventAttributes.nLength], 18h
0x18001cf49  mov     [rbp+650h+EventAttributes.lpSecurityDescriptor], r14
0x18001cf4d  mov     [rbp+650h+EventAttributes.bInheritHandle], 1
0x18001cf54  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001cf59  mov     r14, rax
0x18001cf5c  call    cs:__imp_GetCurrentProcess
0x18001cf62  mov     rsi, rax
0x18001cf65  call    cs:__imp_GetCurrentProcess
0x18001cf6b  mov     [rsp+750h+dwOptions], 2; dwOptions
0x18001cf73  mov     r9, r14; lpTargetHandle
0x18001cf76  mov     rcx, rax; hSourceProcessHandle
0x18001cf79  mov     [rsp+750h+bInheritHandle], 1; bInheritHandle
0x18001cf81  mov     r8, rsi; hTargetProcessHandle
0x18001cf84  mov     [rsp+750h+dwDesiredAccess], ebx; dwDesiredAccess
0x18001cf88  mov     rdx, r12; hSourceHandle
0x18001cf8b  call    cs:__imp_DuplicateHandle
0x18001cf91  xor     r9d, r9d; lpName
0x18001cf94  lea     rcx, [rbp+650h+EventAttributes]; lpEventAttributes
0x18001cf98  xor     r8d, r8d; bInitialState
0x18001cf9b  lea     edx, [r9+1]; bManualReset
0x18001cf9f  call    cs:__imp_CreateEventW
0x18001cfa5  mov     rsi, rax
0x18001cfa8  inc     rax
0x18001cfab  cmp     rax, 1
0x18001cfaf  jbe     loc_18001D1CF
0x18001cfb5  test    r13, r13
0x18001cfb8  jz      loc_18001D1CF
0x18001cfbe  xor     r9d, r9d; ReturnLength
0x18001cfc1  lea     rdx, [rbp+650h+SystemInformation]; SystemInformation
0x18001cfc5  lea     r8d, [r9+0Ch]; SystemInformationLength
0x18001cfc9  lea     ecx, [r9+1]; SystemInformationClass
0x18001cfcd  call    cs:__imp_NtQuerySystemInformation
0x18001cfd3  test    eax, eax
0x18001cfd5  js      loc_18001D1CF
0x18001cfdb  test    r12, r12
0x18001cfde  jz      short loc_18001CFEE
0x18001cfe0  mov     rcx, r12; Thread
0x18001cfe3  call    cs:__imp_GetThreadId
0x18001cfe9  mov     [rbp+650h+var_5D8], eax
0x18001cfec  jmp     short loc_18001CFF1
0x18001cfee  mov     [rbp+650h+var_5D8], ebx
0x18001cff1  movzx   eax, word ptr [rbp+650h+SystemInformation]
0x18001cff5  mov     [rbp+650h+var_5DC], eax
0x18001cff8  mov     rax, [r13+10h]
0x18001cffc  mov     [rbp+650h+var_5D0], rax
0x18001d003  mov     eax, [rsp+750h+var_6F0]
0x18001d007  mov     [rbp+650h+Buffer], 28h ; '('
0x18001d00e  mov     [rbp+650h+var_5D4], ebx
0x18001d011  cmp     eax, [rsp+750h+var_6E0]
0x18001d015  jz      loc_18001D1BB
0x18001d01b  mov     r12, [rbp+650h+hProcess]
0x18001d01f  xor     edx, edx; lpAddress
0x18001d021  mov     rcx, r12; hProcess
0x18001d024  mov     [rsp+750h+dwDesiredAccess], 4; flProtect
0x18001d02c  mov     r9d, 1000h; flAllocationType
0x18001d032  mov     r8d, 590h; dwSize
0x18001d038  call    cs:__imp_VirtualAllocEx
0x18001d03e  mov     [rbp+650h+lpAddress], rax
0x18001d042  mov     r14, rax
0x18001d045  test    rax, rax
0x18001d048  jz      loc_18001D1CF
0x18001d04e  movups  xmm0, xmmword ptr [r13+0]
0x18001d053  mov     rax, [r13+90h]
0x18001d05a  mov     ecx, 9
0x18001d05f  movups  xmm1, xmmword ptr [r13+10h]
0x18001d064  mov     [rbp+650h+var_528], rax
0x18001d06b  lea     rax, [rbp+650h+var_520]
0x18001d072  movups  [rbp+650h+var_5B8], xmm0
0x18001d079  lea     edx, [rcx+77h]
0x18001d07c  movups  xmm0, xmmword ptr [r13+20h]
0x18001d081  movups  [rbp+650h+var_5A8], xmm1
0x18001d088  movups  xmm1, xmmword ptr [r13+30h]
0x18001d08d  movups  [rbp+650h+var_598], xmm0
0x18001d094  movups  xmm0, xmmword ptr [r13+40h]
0x18001d099  movups  [rbp+650h+var_588], xmm1
0x18001d0a0  movups  xmm1, xmmword ptr [r13+50h]
0x18001d0a5  movups  [rbp+650h+var_578], xmm0
0x18001d0ac  movups  xmm0, xmmword ptr [r13+60h]
0x18001d0b1  movups  [rbp+650h+var_568], xmm1
0x18001d0b8  movups  xmm1, xmmword ptr [r13+70h]
0x18001d0bd  movups  [rbp+650h+var_558], xmm0
0x18001d0c4  movups  xmm0, xmmword ptr [r13+80h]
0x18001d0cc  movups  [rbp+650h+var_548], xmm1
0x18001d0d3  movups  [rbp+650h+var_538], xmm0
0x18001d0da  movups  xmm0, xmmword ptr [r15]
0x18001d0de  movups  xmm1, xmmword ptr [r15+10h]
0x18001d0e3  movups  xmmword ptr [rax], xmm0
0x18001d0e6  movups  xmm0, xmmword ptr [r15+20h]
0x18001d0eb  movups  xmmword ptr [rax+10h], xmm1
0x18001d0ef  movups  xmm1, xmmword ptr [r15+30h]
0x18001d0f4  movups  xmmword ptr [rax+20h], xmm0
0x18001d0f8  movups  xmm0, xmmword ptr [r15+40h]
0x18001d0fd  movups  xmmword ptr [rax+30h], xmm1
0x18001d101  movups  xmm1, xmmword ptr [r15+50h]
0x18001d106  movups  xmmword ptr [rax+40h], xmm0
0x18001d10a  movups  xmm0, xmmword ptr [r15+60h]
0x18001d10f  movups  xmmword ptr [rax+50h], xmm1
0x18001d113  movups  xmm1, xmmword ptr [r15+70h]
0x18001d118  add     r15, rdx
0x18001d11b  movups  xmmword ptr [rax+60h], xmm0
0x18001d11f  movups  xmmword ptr [rax+70h], xmm1
0x18001d123  add     rax, rdx
0x18001d126  sub     rcx, 1
0x18001d12a  jnz     short loc_18001D0DA
0x18001d12c  movups  xmm0, xmmword ptr [r15]
0x18001d130  mov     rcx, r14
0x18001d133  lea     r8, [rbp+650h+Buffer]; lpBuffer
0x18001d137  movups  xmm1, xmmword ptr [r15+10h]
0x18001d13c  mov     rdx, r14; lpBaseAddress
0x18001d13f  movups  xmmword ptr [rax], xmm0
0x18001d142  movups  xmm0, xmmword ptr [r15+20h]
0x18001d147  movups  xmmword ptr [rax+10h], xmm1
0x18001d14b  movups  xmm1, xmmword ptr [r15+30h]
0x18001d150  movups  xmmword ptr [rax+20h], xmm0
0x18001d154  movups  xmm0, xmmword ptr [r15+40h]
0x18001d159  mov     r15d, 590h
0x18001d15f  movups  xmmword ptr [rax+30h], xmm1
0x18001d163  mov     r9d, r15d; nSize
0x18001d166  movups  xmmword ptr [rax+40h], xmm0
0x18001d16a  lea     rax, [rbp+650h+Buffer]
0x18001d16e  sub     rcx, rax
0x18001d171  lea     rax, [rbp+650h+var_5B8]
0x18001d178  add     rax, rcx
0x18001d17b  mov     [rsp+750h+NumberOfBytesWritten], rcx
0x18001d180  mov     [rbp+650h+var_5C8], rax
0x18001d187  lea     rax, [rbp+650h+var_520]
0x18001d18e  add     rax, rcx
0x18001d191  mov     rcx, r12; hProcess
0x18001d194  mov     [rbp+650h+var_5C0], rax
0x18001d19b  lea     rax, [rsp+750h+NumberOfBytesWritten]
0x18001d1a0  mov     qword ptr [rsp+750h+dwDesiredAccess], rax; lpNumberOfBytesWritten
0x18001d1a5  call    cs:__imp_WriteProcessMemory
0x18001d1ab  test    eax, eax
0x18001d1ad  jz      short loc_18001D1CF
0x18001d1af  cmp     [rsp+750h+NumberOfBytesWritten], r15
0x18001d1b4  jnz     short loc_18001D1CF
0x18001d1b6  mov     r12, r14
0x18001d1b9  jmp     short loc_18001D1D2
0x18001d1bb  mov     [rbp+650h+var_5C8], r13
0x18001d1c2  lea     r12, [rbp+650h+Buffer]
0x18001d1c6  mov     [rbp+650h+var_5C0], r15
0x18001d1cd  jmp     short loc_18001D1D2
0x18001d1cf  mov     r12, rbx
0x18001d1d2  mov     r14, [rbp+650h+var_6D0]
0x18001d1d6  add     r14, 4
0x18001d1da  cmp     word ptr [r14], 22h ; '"'
0x18001d1df  jz      short loc_18001D24D
0x18001d1e1  mov     rcx, r14; Path
0x18001d1e4  call    cs:__imp_RtlDetermineDosPathNameType_U
0x18001d1ea  cmp     eax, 5
0x18001d1ed  jnz     short loc_18001D24D
0x18001d1ef  lea     r15, [rdi+286h]
0x18001d1f6  call    cs:__imp_RtlGetNtSystemRoot
0x18001d1fc  lea     r8, aSSystem32S; "%s\\system32\\%s"
0x18001d203  mov     qword ptr [rsp+750h+dwDesiredAccess], r14
0x18001d208  mov     r9, rax
0x18001d20b  mov     edx, 125h; unsigned __int64
0x18001d210  mov     rcx, r15; wchar_t *
0x18001d213  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001d218  mov     r14d, eax
0x18001d21b  test    eax, eax
0x18001d21d  jns     short loc_18001D250
0x18001d21f  call    GetCurrentProcessId_0
0x18001d224  mov     [rsp+750h+bInheritHandle], r14d
0x18001d229  lea     r8, aWerCrashapiUUE_4; "WER/CrashAPI/%u:%u: ERROR StringCchPrin"...
0x18001d230  mov     [rsp+750h+dwDesiredAccess], 12E2h
0x18001d238  mov     ecx, 96h; ComponentId
0x18001d23d  mov     r9d, eax
0x18001d240  xor     edx, edx; Level
0x18001d242  call    cs:__imp_DbgPrintEx
0x18001d248  jmp     loc_18001D6E5
0x18001d24d  mov     r15, r14
0x18001d250  mov     r9d, [rsp+750h+var_6F0]
0x18001d255  mov     r8, r15; wchar_t *
0x18001d258  mov     qword ptr [rsp+750h+bInheritHandle], r12
0x18001d25d  mov     edx, 143h; unsigned __int64
0x18001d262  mov     rcx, rdi; wchar_t *
0x18001d265  mov     qword ptr [rsp+750h+dwDesiredAccess], rsi
0x18001d26a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001d26f  mov     r14d, eax
0x18001d272  test    eax, eax
0x18001d274  jns     short loc_18001D291
0x18001d276  call    GetCurrentProcessId_0
0x18001d27b  mov     [rsp+750h+bInheritHandle], r14d
0x18001d280  lea     r8, aWerCrashapiUUE_15; "WER/CrashAPI/%u:%u: ERROR StringCchPrin"...
0x18001d287  mov     [rsp+750h+dwDesiredAccess], 12F7h
0x18001d28f  jmp     short loc_18001D238
0x18001d291  call    cs:__imp_RtlGetCurrentTransaction
0x18001d297  xor     ecx, ecx
0x18001d299  mov     [rbp+650h+var_6B8], rax
0x18001d29d  call    cs:__imp_RtlSetCurrentTransaction
0x18001d2a3  mov     r15, [rbp+650h+var_6D0]
0x18001d2a7  lea     rax, dword_18004FE4C
0x18001d2ae  mov     [rbp+650h+StartupInfo.cb], 70h ; 'p'
0x18001d2b5  mov     r12d, 96h
0x18001d2bb  mov     [rbp+650h+StartupInfo.lpDesktop], rax
0x18001d2bf  mov     r8d, [r15]
0x18001d2c2  mov     edx, r8d
0x18001d2c5  and     edx, 4
0x18001d2c8  mov     ecx, edx
0x18001d2ca  neg     ecx
0x18001d2cc  sbb     r13d, r13d
0x18001d2cf  and     r13d, 40000h
0x18001d2d6  test    edx, edx
0x18001d2d8  jz      loc_18001D40C
0x18001d2de  shr     r8d, 3
0x18001d2e2  and     r8d, 0Fh
0x18001d2e6  mov     eax, r8d
0x18001d2e9  jz      loc_18001D407
0x18001d2ef  sub     eax, 1
0x18001d2f2  jz      loc_18001D407
0x18001d2f8  sub     eax, 1
0x18001d2fb  jz      loc_18001D407
0x18001d301  sub     eax, 1
0x18001d304  jz      loc_18001D407
0x18001d30a  sub     eax, 2
0x18001d30d  jz      loc_18001D407
0x18001d313  sub     eax, 1
0x18001d316  jz      loc_18001D407
0x18001d31c  sub     eax, 1
0x18001d31f  jz      loc_18001D407
0x18001d325  mov     [rsp+750h+Value], 0FFFFFFFFh
0x18001d32d  cmp     eax, 7
0x18001d330  jnz     loc_18001D40C
0x18001d336  mov     rcx, [rbp+650h+hProcess]; ProcessHandle
0x18001d33a  lea     r9d, [rax-6]; ProcessInformationLength
0x18001d33e  lea     r8, [rsp+750h+ProcessInformation]; ProcessInformation
  ... truncated ...
```
