# WerpLaunchAeDebug

- ea: `0x18003f330`
- end: `0x18003fcb4`
- name: `WerpLaunchAeDebug`
- size: `2436`
- prototype: `__int64 __usercall@<rax>(HANDLE Process@<rcx>, HANDLE Thread@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18003f330`
- `0x18003fcbc`
- `0x180052114`
- `0x180052b38`
- `0x180056b74`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlDetermineDosPathNameType_U` at `0x18003f717`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18003f717`
- `ntdll!DbgPrintEx` at `0x18003f781`
- `ntdll!DbgPrintEx` at `0x18003f8d0`
- `ntdll!DbgPrintEx` at `0x18003f90a`
- `ntdll!DbgPrintEx` at `0x18003f98f`
- `ntdll!DbgPrintEx` at `0x18003f781`
- `ntdll!DbgPrintEx` at `0x18003f8d0`
- `ntdll!DbgPrintEx` at `0x18003f90a`
- `ntdll!DbgPrintEx` at `0x18003f98f`
- `ntdll!RtlGetCurrentTransaction` at `0x18003f7d0`
- `ntdll!RtlGetCurrentTransaction` at `0x18003f7d0`
- `ntdll!NtQueryInformationProcess` at `0x18003f89c`
- `ntdll!NtQueryInformationProcess` at `0x18003f89c`
- `ntdll!RtlSetCurrentTransaction` at `0x18003f7e3`
- `ntdll!RtlSetCurrentTransaction` at `0x18003fc21`
- `ntdll!RtlSetCurrentTransaction` at `0x18003f7e3`
- `ntdll!RtlSetCurrentTransaction` at `0x18003fc21`
- `ntdll!RtlGetNtSystemRoot` at `0x18003f72f`
- `ntdll!RtlGetNtSystemRoot` at `0x18003f72f`
- `ntdll!NtWaitForMultipleObjects` at `0x18003fba2`
- `ntdll!NtWaitForMultipleObjects` at `0x18003fba2`
- `ntdll!NtQuerySystemInformation` at `0x18003f4f1`
- `ntdll!NtQuerySystemInformation` at `0x18003f4f1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003f3eb`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003f3eb`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003fb1f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003fb1f`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18003f9be`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18003fa42`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18003f9be`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18003fa42`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18003fa9c`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18003fa9c`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18003f50d`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18003f50d`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18003fc0d`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18003fc0d`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18003f6cb`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18003f6cb`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x18003f562`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x18003f562`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003fc3d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003fc60`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003fc3d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003fc60`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003f43d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003fa1b`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003f43d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003fa1b`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x18003fbd2`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x18003fbd2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003f49b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003f49b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f4b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f4b5`

## string_xrefs

- `0x18003f7bf`: `WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printng the debugger commandline with 0x%x\n`
- `0x18003f762`: `WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printing the debugger path with 0x%x\n`
- `0x18003f73b`: `%s\system32\%s`
- `0x18003f9f4`: `WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n`
- `0x18003fabd`: `WER/CrashAPI/%u:%u: ERROR UpdateProcThreadAttribute failed: 0x%x\n`

## pseudocode

```c
__int64 __fastcall WerpLaunchAeDebug(HANDLE Process, HANDLE Thread, __int64 a3, _OWORD *a4, __int64 a5)
{
  __int64 v5; // r13
  struct _PROC_THREAD_ATTRIBUTE_LIST *v10; // rbx
  HANDLE v11; // rsi
  __int64 v12; // rcx
  signed int LastErrorValue; // r14d
  unsigned __int16 *v14; // rdi
  HANDLE UniqueProcess; // r13
  HANDLE v16; // rdx
  __int64 v17; // rcx
  HANDLE v18; // r12
  _BYTE *v19; // r13
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
  const unsigned __int16 *v43; // r14
  const unsigned __int16 *v44; // r15
  __int64 NtSystemRoot; // rax
  int v46; // eax
  const CHAR *v47; // r8
  int v48; // eax
  _DWORD *v49; // r12
  DWORD v50; // r14d
  unsigned int v51; // r8d
  NTSTATUS InformationProcess; // eax
  HANDLE v53; // r9
  int v54; // eax
  signed int v55; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v56; // rax
  NTSTATUS v57; // eax
  HANDLE v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  DWORD dwDesiredAccess[2]; // [rsp+20h] [rbp-E0h]
  BOOL bInheritHandle[2]; // [rsp+28h] [rbp-D8h]
  _BYTE ProcessInformation[4]; // [rsp+50h] [rbp-B0h] BYREF
  int Value[3]; // [rsp+54h] [rbp-ACh] BYREF
  HANDLE TargetHandle; // [rsp+60h] [rbp-A0h] BYREF
  DWORD ProcessId; // [rsp+68h] [rbp-98h]
  int v69; // [rsp+6Ch] [rbp-94h]
  __int64 CurrentTransaction; // [rsp+78h] [rbp-88h]
  SIZE_T NumberOfBytesWritten; // [rsp+80h] [rbp-80h] BYREF
  ULONG_PTR Size; // [rsp+88h] [rbp-78h] BYREF
  HANDLE hProcess; // [rsp+90h] [rbp-70h]
  __int64 v74; // [rsp+98h] [rbp-68h]
  HANDLE Object[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+B0h] [rbp-50h] BYREF
  struct _PROCESS_INFORMATION lpProcessInformation; // [rsp+C8h] [rbp-38h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+E0h] [rbp-20h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v79; // [rsp+148h] [rbp+48h]
  __int64 SystemInformation; // [rsp+150h] [rbp+50h] BYREF
  int v81; // [rsp+158h] [rbp+58h]
  _DWORD Buffer[2]; // [rsp+160h] [rbp+60h] BYREF
  DWORD ThreadId; // [rsp+168h] [rbp+68h]
  int v84; // [rsp+16Ch] [rbp+6Ch]
  __int64 v85; // [rsp+170h] [rbp+70h]
  __int64 v86; // [rsp+178h] [rbp+78h]
  __int64 v87; // [rsp+180h] [rbp+80h]
  __int128 v88; // [rsp+188h] [rbp+88h]
  __int128 v89; // [rsp+198h] [rbp+98h]
  __int128 v90; // [rsp+1A8h] [rbp+A8h]
  __int128 v91; // [rsp+1B8h] [rbp+B8h]
  __int128 v92; // [rsp+1C8h] [rbp+C8h]
  __int128 v93; // [rsp+1D8h] [rbp+D8h]
  __int128 v94; // [rsp+1E8h] [rbp+E8h]
  __int128 v95; // [rsp+1F8h] [rbp+F8h]
  __int128 v96; // [rsp+208h] [rbp+108h]
  __int64 v97; // [rsp+218h] [rbp+118h]
  char v98; // [rsp+220h] [rbp+120h] BYREF

  v5 = 0;
  hProcess = Process;
  v74 = a5;
  TargetHandle = 0;
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  Size = 0;
  SystemInformation = 0;
  v81 = 0;
  memset(&lpProcessInformation, 0, sizeof(lpProcessInformation));
  v10 = 0;
  v69 = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v11 = 0;
  CurrentTransaction = 0;
  *(_OWORD *)Object = 0;
  memset_0(Buffer, 0, 0x590u);
  NumberOfBytesWritten = 0;
  Value[0] = -1;
  ProcessInformation[0] = 0;
  ProcessId = GetProcessId(Process);
  if ( !ProcessId )
  {
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    v14 = 0;
    if ( LastErrorValue > 0 )
      LastErrorValue = (unsigned __int16)LastErrorValue | 0x80070000;
    goto LABEL_69;
  }
  UniqueProcess = NtCurrentTeb()->ClientId.UniqueProcess;
  v14 = (unsigned __int16 *)VirtualAlloc(0, 0x4D0u, 0x1000u, 4u);
  if ( !v14 )
  {
    LastErrorValue = -2147024882;
    v5 = 0;
    goto LABEL_69;
  }
  v16 = TargetHandle;
  TargetHandle = 0;
  EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  EventAttributes.bInheritHandle = 1;
  tlx::file_handle_traits::operator()(v12, v16);
  DuplicateHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL, Thread, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &TargetHandle, 0, 1, 2u);
  v11 = CreateEventW(&EventAttributes, 1, 0, 0);
  tlx::file_handle_traits::operator()(v17, 0);
  if ( (unsigned __int64)v11 + 1 <= 1 )
    goto LABEL_21;
  if ( !a3 )
  {
    v19 = 0;
LABEL_20:
    v42 = 0;
    goto LABEL_23;
  }
  if ( NtQuerySystemInformation(SystemProcessorInformation, &SystemInformation, 0xCu, 0) < 0 )
  {
LABEL_21:
    v42 = 0;
    goto LABEL_22;
  }
  if ( Thread )
    ThreadId = GetThreadId(Thread);
  else
    ThreadId = 0;
  Buffer[1] = (unsigned __int16)SystemInformation;
  v85 = *(_QWORD *)(a3 + 16);
  Buffer[0] = 40;
  v84 = 0;
  if ( ProcessId == (_DWORD)UniqueProcess )
  {
    v86 = a3;
    v42 = Buffer;
    v87 = (__int64)a4;
LABEL_22:
    v19 = 0;
    goto LABEL_23;
  }
  v18 = hProcess;
  v19 = VirtualAllocEx(hProcess, 0, 0x590u, 0x1000u, 4u);
  if ( !v19 )
    goto LABEL_20;
  v20 = *(_OWORD *)a3;
  v21 = 9;
  v22 = *(_OWORD *)(a3 + 16);
  v97 = *(_QWORD *)(a3 + 144);
  v23 = &v98;
  v88 = v20;
  v24 = *(_OWORD *)(a3 + 32);
  v89 = v22;
  v25 = *(_OWORD *)(a3 + 48);
  v90 = v24;
  v26 = *(_OWORD *)(a3 + 64);
  v91 = v25;
  v27 = *(_OWORD *)(a3 + 80);
  v92 = v26;
  v28 = *(_OWORD *)(a3 + 96);
  v93 = v27;
  v29 = *(_OWORD *)(a3 + 112);
  v94 = v28;
  v30 = *(_OWORD *)(a3 + 128);
  v95 = v29;
  v96 = v30;
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
  v86 = (__int64)(v19 + 40);
  v87 = (__int64)(v19 + 192);
  if ( !WriteProcessMemory(v18, v19, Buffer, 0x590u, &NumberOfBytesWritten) || NumberOfBytesWritten != 1424 )
    goto LABEL_20;
  v42 = v19;
LABEL_23:
  v43 = (const unsigned __int16 *)(v74 + 4);
  if ( *(_WORD *)(v74 + 4) == 34 || RtlDetermineDosPathNameType_U((PCWSTR)(v74 + 4)) != RtlPathTypeRelative )
  {
    v44 = v43;
LABEL_29:
    v48 = StringCchPrintfW(v14, 0x143u, v44, ProcessId, v11, v42);
    LastErrorValue = v48;
    if ( v48 < 0 )
    {
      bInheritHandle[0] = v48;
      v47 = "WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printng the debugger commandline with 0x%x\n";
      dwDesiredAccess[0] = 4855;
      goto LABEL_27;
    }
    CurrentTransaction = RtlGetCurrentTransaction();
    RtlSetCurrentTransaction(0);
    v49 = (_DWORD *)v74;
    StartupInfo.cb = 112;
    StartupInfo.lpDesktop = (LPWSTR)&word_18008EBAC;
    v50 = (*(_DWORD *)v74 & 4) != 0 ? 0x40000 : 0;
    if ( (*(_DWORD *)v74 & 4) != 0 )
    {
      v51 = (*(_DWORD *)v74 >> 3) & 0xF;
      if ( v51 < 4 || v51 == 5 || v51 == 6 || v51 == 7 )
      {
        Value[0] = (*(_DWORD *)v74 >> 3) & 0xF;
      }
      else
      {
        Value[0] = -1;
        if ( v51 == 14 )
        {
          ProcessInformation[0] = 0;
          InformationProcess = NtQueryInformationProcess(
                                 hProcess,
                                 ProcessAffinityUpdateMode|ProcessUserModeIOPL,
                                 ProcessInformation,
                                 1u,
                                 0);
          v53 = NtCurrentTeb()->ClientId.UniqueProcess;
          if ( InformationProcess >= 0 )
          {
            DbgPrintEx(
              0x96u,
              2u,
              "WER/CrashAPI/%u:%u: TRACE Faulting process protection/signer: %02x/%02x\n",
              (_DWORD)v53,
              4908,
              ProcessInformation[0] & 7,
              ProcessInformation[0] >> 4);
            if ( (ProcessInformation[0] & 7u) >= 3 || (ProcessInformation[0] & 0xF0u) >= 0x90 )
              v54 = -1;
            else
              v54 = *((_DWORD *)qword_180095810
                    + 9 * (ProcessInformation[0] & 7)
                    + ((unsigned __int64)ProcessInformation[0] >> 4));
            Value[0] = v54;
          }
          else
          {
            DbgPrintEx(
              0x96u,
              1u,
              "WER/CrashAPI/%u:%u: WARNING NtQueryInformationProcess/ProcessProtectionInformation failed: NTSTATUS %08X\n",
              (_DWORD)v53,
              4903,
              InformationProcess);
          }
        }
      }
    }
    DbgPrintEx(
      0x96u,
      2u,
      "WER/CrashAPI/%u:%u: TRACE Mapped protection level %02X -> %08X\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      4922,
      (*v49 >> 3) & 0xF,
      Value[0]);
    if ( (*(_BYTE *)v49 & 4) != 0 && Value[0] != -1 )
    {
      if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) && NtCurrentTeb()->LastErrorValue != 122 )
      {
        v55 = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
        bInheritHandle[0] = v55;
        dwDesiredAccess[0] = 4937;
LABEL_50:
        v47 = "WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n";
LABEL_51:
        LastErrorValue = v55;
        goto LABEL_27;
      }
      v56 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)VirtualAlloc(0, Size, 0x1000u, 4u);
      v10 = v56;
      if ( !v56 )
      {
        LastErrorValue = -2147024882;
        v47 = "WER/CrashAPI/%u:%u: ERROR Failed to allocate attribute list: 0x%x\n";
        bInheritHandle[0] = -2147024882;
        dwDesiredAccess[0] = 4950;
        goto LABEL_27;
      }
      if ( !InitializeProcThreadAttributeList(v56, 1u, 0, &Size) )
      {
        v55 = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
        bInheritHandle[0] = v55;
        dwDesiredAccess[0] = 4962;
        goto LABEL_50;
      }
      v69 = 1;
      if ( !UpdateProcThreadAttribute(v10, 0, 0x2000Bu, Value, 4u, 0, 0) )
      {
        v55 = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
        bInheritHandle[0] = v55;
        v47 = "WER/CrashAPI/%u:%u: ERROR UpdateProcThreadAttribute failed: 0x%x\n";
        dwDesiredAccess[0] = 4978;
        goto LABEL_51;
      }
      v79 = v10;
      v50 |= 0x80000u;
    }
    wer::ProcessInformation::Clear((wer::ProcessInformation *)&lpProcessInformation);
    if ( CreateProcessW(0, v14, 0, 0, 1, v50, 0, 0, &StartupInfo, &lpProcessInformation) )
    {
      LastErrorValue = 0;
      if ( (unsigned __int64)v11 + 1 > 1 )
      {
        Object[1] = lpProcessInformation.hProcess;
        Object[0] = v11;
        while ( 1 )
        {
          v57 = NtWaitForMultipleObjects(2u, Object, WaitAny, 1u, 0);
          if ( !v57 )
            break;
          if ( v57 == 1 )
          {
            LastErrorValue = -2147023829;
            goto LABEL_66;
          }
        }
      }
      goto LABEL_66;
    }
    v55 = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
    bInheritHandle[0] = v55;
    v47 = "WER/CrashAPI/%u:%u: ERROR Debugger spawn failed: 0x%x\n";
    dwDesiredAccess[0] = 5003;
    goto LABEL_51;
  }
  v44 = v14 + 323;
  NtSystemRoot = RtlGetNtSystemRoot();
  v46 = StringCchPrintfW(v14 + 323, 0x125u, L"%s\\system32\\%s", NtSystemRoot, v43);
  LastErrorValue = v46;
  if ( v46 >= 0 )
    goto LABEL_29;
  bInheritHandle[0] = v46;
  v47 = "WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printing the debugger path with 0x%x\n";
  dwDesiredAccess[0] = 4834;
LABEL_27:
  DbgPrintEx(
    0x96u,
    0,
    v47,
    NtCurrentTeb()->ClientId.UniqueProcess,
    *(_QWORD *)dwDesiredAccess,
    *(_QWORD *)bInheritHandle);
LABEL_66:
  if ( v19 )
    VirtualFreeEx(hProcess, v19, 0, 0x8000u);
  v5 = CurrentTransaction;
LABEL_69:
  tlx::file_handle_traits::operator()(v12, v11);
  v58 = TargetHandle;
  TargetHandle = 0;
  tlx::file_handle_traits::operator()(v59, v58);
  if ( v69 && v10 )
    DeleteProcThreadAttributeList(v10);
  if ( v5 )
    RtlSetCurrentTransaction(v5);
  if ( v14 )
    VirtualFree(v14, 0, 0x8000u);
  tlx::file_handle_traits::operator()(v60, 0);
  if ( v10 )
    VirtualFree(v10, 0, 0x8000u);
  wer::ProcessInformation::Clear((wer::ProcessInformation *)&lpProcessInformation);
  tlx::file_handle_traits::operator()(v61, TargetHandle);
  return (unsigned int)LastErrorValue;
}

```

## disassembly

```asm
0x18003f330  push    rbp
0x18003f332  push    rbx
0x18003f333  push    rsi
0x18003f334  push    rdi
0x18003f335  push    r12
0x18003f337  push    r13
0x18003f339  push    r14
0x18003f33b  push    r15
0x18003f33d  lea     rbp, [rsp-608h]
0x18003f345  sub     rsp, 708h
0x18003f34c  mov     rax, cs:__security_cookie
0x18003f353  xor     rax, rsp
0x18003f356  mov     [rbp+640h+var_50], rax
0x18003f35d  mov     rax, [rbp+640h+arg_20]
0x18003f364  xor     r13d, r13d
0x18003f367  mov     r15, r8
0x18003f36a  mov     [rbp+640h+hProcess], rcx
0x18003f36e  mov     r12, rdx
0x18003f371  mov     [rbp+640h+var_6A8], rax
0x18003f375  mov     rdi, rcx
0x18003f378  mov     [rsp+740h+TargetHandle], r13
0x18003f37d  lea     r8d, [r13+68h]; Size
0x18003f381  mov     qword ptr [rbp+640h+StartupInfo.cb], r13
0x18003f385  xor     edx, edx; Val
0x18003f387  lea     rcx, [rbp+640h+StartupInfo.lpReserved]; void *
0x18003f38b  mov     r14, r9
0x18003f38e  call    memset_0
0x18003f393  xor     eax, eax
0x18003f395  mov     [rbp+640h+Size], r13
0x18003f399  xorps   xmm0, xmm0
0x18003f39c  mov     qword ptr [rbp+640h+var_678.dwProcessId], rax
0x18003f3a0  xor     edx, edx; Val
0x18003f3a2  mov     qword ptr [rbp+640h+EventAttributes.bInheritHandle], rax
0x18003f3a6  mov     r8d, 590h; Size
0x18003f3ac  mov     [rbp+640h+SystemInformation], rax
0x18003f3b0  lea     rcx, [rbp+640h+Buffer]; void *
0x18003f3b4  mov     [rbp+640h+var_5E8], eax
0x18003f3b7  movups  xmmword ptr [rbp+640h+var_678.hProcess], xmm0
0x18003f3bb  mov     ebx, r13d
0x18003f3be  mov     [rsp+740h+var_6D4], r13d
0x18003f3c3  movups  xmmword ptr [rbp+640h+EventAttributes.nLength], xmm0
0x18003f3c7  mov     esi, r13d
0x18003f3ca  mov     [rsp+740h+var_6C8], r13
0x18003f3cf  movups  xmmword ptr [rbp+640h+Object], xmm0
0x18003f3d3  call    memset_0
0x18003f3d8  mov     rcx, rdi; Process
0x18003f3db  mov     [rbp+640h+NumberOfBytesWritten], rbx
0x18003f3df  mov     [rsp+740h+Value], 0FFFFFFFFh
0x18003f3e7  mov     [rsp+740h+ProcessInformation], bl
0x18003f3eb  call    cs:__imp_GetProcessId
0x18003f3f2  nop     dword ptr [rax+rax+00h]
0x18003f3f7  mov     [rsp+740h+var_6D8], eax
0x18003f3fb  test    eax, eax
0x18003f3fd  jnz     short loc_18003F423
0x18003f3ff  mov     r14d, gs:68h
0x18003f408  xor     edi, edi
0x18003f40a  test    r14d, r14d
0x18003f40d  jle     loc_18003FBE3
0x18003f413  movzx   r14d, r14w
0x18003f417  or      r14d, 80070000h
0x18003f41e  jmp     loc_18003FBE3
0x18003f423  mov     r13, gs:40h
0x18003f42c  xor     ecx, ecx; lpAddress
0x18003f42e  mov     edx, 4D0h; dwSize
0x18003f433  mov     r8d, 1000h; flAllocationType
0x18003f439  lea     r9d, [rcx+4]; flProtect
0x18003f43d  call    cs:__imp_VirtualAlloc
0x18003f444  nop     dword ptr [rax+rax+00h]
0x18003f449  mov     rdi, rax
0x18003f44c  xor     eax, eax
0x18003f44e  test    rdi, rdi
0x18003f451  jz      loc_18003FCA6
0x18003f457  mov     rdx, [rsp+740h+TargetHandle]
0x18003f45c  mov     [rsp+740h+TargetHandle], rax
0x18003f461  mov     [rbp+640h+EventAttributes.nLength], 18h
0x18003f468  mov     [rbp+640h+EventAttributes.lpSecurityDescriptor], rax
0x18003f46c  mov     [rbp+640h+EventAttributes.bInheritHandle], 1
0x18003f473  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f478  or      rcx, 0FFFFFFFFFFFFFFFFh; hSourceProcessHandle
0x18003f47c  mov     [rsp+740h+dwOptions], 2; dwOptions
0x18003f484  mov     r8, rcx; hTargetProcessHandle
0x18003f487  mov     [rsp+740h+bInheritHandle], 1; bInheritHandle
0x18003f48f  lea     r9, [rsp+740h+TargetHandle]; lpTargetHandle
0x18003f494  mov     [rsp+740h+dwDesiredAccess], ebx; dwDesiredAccess
0x18003f498  mov     rdx, r12; hSourceHandle
0x18003f49b  call    cs:__imp_DuplicateHandle
0x18003f4a2  nop     dword ptr [rax+rax+00h]
0x18003f4a7  xor     r9d, r9d; lpName
0x18003f4aa  lea     rcx, [rbp+640h+EventAttributes]; lpEventAttributes
0x18003f4ae  xor     r8d, r8d; bInitialState
0x18003f4b1  lea     edx, [r9+1]; bManualReset
0x18003f4b5  call    cs:__imp_CreateEventW
0x18003f4bc  nop     dword ptr [rax+rax+00h]
0x18003f4c1  xor     edx, edx
0x18003f4c3  mov     rsi, rax
0x18003f4c6  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f4cb  lea     rax, [rsi+1]
0x18003f4cf  cmp     rax, 1
0x18003f4d3  jbe     loc_18003F6FF
0x18003f4d9  test    r15, r15
0x18003f4dc  jz      loc_18003F6F7
0x18003f4e2  xor     r9d, r9d; ReturnLength
0x18003f4e5  lea     rdx, [rbp+640h+SystemInformation]; SystemInformation
0x18003f4e9  lea     r8d, [r9+0Ch]; SystemInformationLength
0x18003f4ed  lea     ecx, [r9+1]; SystemInformationClass
0x18003f4f1  call    cs:__imp_NtQuerySystemInformation
0x18003f4f8  nop     dword ptr [rax+rax+00h]
0x18003f4fd  test    eax, eax
0x18003f4ff  js      loc_18003F6FF
0x18003f505  test    r12, r12
0x18003f508  jz      short loc_18003F51E
0x18003f50a  mov     rcx, r12; Thread
0x18003f50d  call    cs:__imp_GetThreadId
0x18003f514  nop     dword ptr [rax+rax+00h]
0x18003f519  mov     [rbp+640h+var_5D8], eax
0x18003f51c  jmp     short loc_18003F521
0x18003f51e  mov     [rbp+640h+var_5D8], ebx
0x18003f521  movzx   eax, word ptr [rbp+640h+SystemInformation]
0x18003f525  mov     [rbp+640h+var_5DC], eax
0x18003f528  mov     rax, [r15+10h]
0x18003f52c  mov     [rbp+640h+var_5D0], rax
0x18003f530  mov     [rbp+640h+Buffer], 28h ; '('
0x18003f537  mov     [rbp+640h+var_5D4], ebx
0x18003f53a  cmp     [rsp+740h+var_6D8], r13d
0x18003f53f  jz      loc_18003F6E6
0x18003f545  mov     r12, [rbp+640h+hProcess]
0x18003f549  xor     edx, edx; lpAddress
0x18003f54b  mov     rcx, r12; hProcess
0x18003f54e  mov     [rsp+740h+dwDesiredAccess], 4; flProtect
0x18003f556  mov     r9d, 1000h; flAllocationType
0x18003f55c  mov     r8d, 590h; dwSize
0x18003f562  call    cs:__imp_VirtualAllocEx
0x18003f569  nop     dword ptr [rax+rax+00h]
0x18003f56e  mov     r13, rax
0x18003f571  test    rax, rax
0x18003f574  jz      loc_18003F6FA
0x18003f57a  movups  xmm0, xmmword ptr [r15]
0x18003f57e  mov     rax, [r15+90h]
0x18003f585  mov     ecx, 9
0x18003f58a  movups  xmm1, xmmword ptr [r15+10h]
0x18003f58f  mov     [rbp+640h+var_528], rax
0x18003f596  lea     rax, [rbp+640h+var_520]
0x18003f59d  movups  [rbp+640h+var_5B8], xmm0
0x18003f5a4  lea     edx, [rcx+77h]
0x18003f5a7  movups  xmm0, xmmword ptr [r15+20h]
0x18003f5ac  movups  [rbp+640h+var_5A8], xmm1
0x18003f5b3  movups  xmm1, xmmword ptr [r15+30h]
0x18003f5b8  movups  [rbp+640h+var_598], xmm0
0x18003f5bf  movups  xmm0, xmmword ptr [r15+40h]
0x18003f5c4  movups  [rbp+640h+var_588], xmm1
0x18003f5cb  movups  xmm1, xmmword ptr [r15+50h]
0x18003f5d0  movups  [rbp+640h+var_578], xmm0
0x18003f5d7  movups  xmm0, xmmword ptr [r15+60h]
0x18003f5dc  movups  [rbp+640h+var_568], xmm1
0x18003f5e3  movups  xmm1, xmmword ptr [r15+70h]
0x18003f5e8  movups  [rbp+640h+var_558], xmm0
0x18003f5ef  movups  xmm0, xmmword ptr [r15+80h]
0x18003f5f7  movups  [rbp+640h+var_548], xmm1
0x18003f5fe  movups  [rbp+640h+var_538], xmm0
0x18003f605  movups  xmm0, xmmword ptr [r14]
0x18003f609  movups  xmm1, xmmword ptr [r14+10h]
0x18003f60e  movups  xmmword ptr [rax], xmm0
0x18003f611  movups  xmm0, xmmword ptr [r14+20h]
0x18003f616  movups  xmmword ptr [rax+10h], xmm1
0x18003f61a  movups  xmm1, xmmword ptr [r14+30h]
0x18003f61f  movups  xmmword ptr [rax+20h], xmm0
0x18003f623  movups  xmm0, xmmword ptr [r14+40h]
0x18003f628  movups  xmmword ptr [rax+30h], xmm1
0x18003f62c  movups  xmm1, xmmword ptr [r14+50h]
0x18003f631  movups  xmmword ptr [rax+40h], xmm0
0x18003f635  movups  xmm0, xmmword ptr [r14+60h]
0x18003f63a  movups  xmmword ptr [rax+50h], xmm1
0x18003f63e  movups  xmm1, xmmword ptr [r14+70h]
0x18003f643  add     r14, rdx
0x18003f646  movups  xmmword ptr [rax+60h], xmm0
0x18003f64a  movups  xmmword ptr [rax+70h], xmm1
0x18003f64e  add     rax, rdx
0x18003f651  sub     rcx, 1
0x18003f655  jnz     short loc_18003F605
0x18003f657  movups  xmm0, xmmword ptr [r14]
0x18003f65b  mov     rcx, r13
0x18003f65e  lea     r8, [rbp+640h+Buffer]; lpBuffer
0x18003f662  movups  xmm1, xmmword ptr [r14+10h]
0x18003f667  mov     rdx, r13; lpBaseAddress
0x18003f66a  movups  xmmword ptr [rax], xmm0
0x18003f66d  movups  xmm0, xmmword ptr [r14+20h]
0x18003f672  movups  xmmword ptr [rax+10h], xmm1
0x18003f676  movups  xmm1, xmmword ptr [r14+30h]
0x18003f67b  movups  xmmword ptr [rax+20h], xmm0
0x18003f67f  movups  xmm0, xmmword ptr [r14+40h]
0x18003f684  mov     r14d, 590h
0x18003f68a  movups  xmmword ptr [rax+30h], xmm1
0x18003f68e  mov     r9d, r14d; nSize
0x18003f691  movups  xmmword ptr [rax+40h], xmm0
0x18003f695  lea     rax, [rbp+640h+Buffer]
0x18003f699  sub     rcx, rax
0x18003f69c  lea     rax, [rbp+640h+var_5B8]
0x18003f6a3  add     rax, rcx
0x18003f6a6  mov     [rbp+640h+NumberOfBytesWritten], rcx
0x18003f6aa  mov     [rbp+640h+var_5C8], rax
0x18003f6ae  lea     rax, [rbp+640h+var_520]
0x18003f6b5  add     rax, rcx
0x18003f6b8  mov     rcx, r12; hProcess
0x18003f6bb  mov     [rbp+640h+var_5C0], rax
0x18003f6c2  lea     rax, [rbp+640h+NumberOfBytesWritten]
0x18003f6c6  mov     qword ptr [rsp+740h+dwDesiredAccess], rax; lpNumberOfBytesWritten
0x18003f6cb  call    cs:__imp_WriteProcessMemory
0x18003f6d2  nop     dword ptr [rax+rax+00h]
0x18003f6d7  test    eax, eax
0x18003f6d9  jz      short loc_18003F6FA
0x18003f6db  cmp     [rbp+640h+NumberOfBytesWritten], r14
0x18003f6df  jnz     short loc_18003F6FA
0x18003f6e1  mov     r12, r13
0x18003f6e4  jmp     short loc_18003F705
0x18003f6e6  mov     [rbp+640h+var_5C8], r15
0x18003f6ea  lea     r12, [rbp+640h+Buffer]
0x18003f6ee  mov     [rbp+640h+var_5C0], r14
0x18003f6f5  jmp     short loc_18003F702
0x18003f6f7  mov     r13, rbx
0x18003f6fa  mov     r12, rbx
0x18003f6fd  jmp     short loc_18003F705
0x18003f6ff  mov     r12, rbx
0x18003f702  mov     r13, rbx
0x18003f705  mov     r14, [rbp+640h+var_6A8]
0x18003f709  add     r14, 4
0x18003f70d  cmp     word ptr [r14], 22h ; '"'
0x18003f712  jz      short loc_18003F792
0x18003f714  mov     rcx, r14; Path
0x18003f717  call    cs:__imp_RtlDetermineDosPathNameType_U
0x18003f71e  nop     dword ptr [rax+rax+00h]
0x18003f723  cmp     eax, 5
0x18003f726  jnz     short loc_18003F792
0x18003f728  lea     r15, [rdi+286h]
0x18003f72f  call    cs:__imp_RtlGetNtSystemRoot
0x18003f736  nop     dword ptr [rax+rax+00h]
0x18003f73b  lea     r8, aSSystem32S; "%s\\system32\\%s"
0x18003f742  mov     qword ptr [rsp+740h+dwDesiredAccess], r14
0x18003f747  mov     r9, rax
0x18003f74a  mov     edx, 125h; unsigned __int64
0x18003f74f  mov     rcx, r15; unsigned __int16 *
0x18003f752  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003f757  mov     r14d, eax
0x18003f75a  test    eax, eax
0x18003f75c  jns     short loc_18003F795
0x18003f75e  mov     [rsp+740h+bInheritHandle], eax
0x18003f762  lea     r8, aWerCrashapiUUE_10; "WER/CrashAPI/%u:%u: ERROR StringCchPrin"...
0x18003f769  mov     [rsp+740h+dwDesiredAccess], 12E2h
0x18003f771  mov     ecx, 96h; ComponentId
0x18003f776  mov     r9, gs:40h
0x18003f77f  xor     edx, edx; Level
0x18003f781  call    cs:__imp_DbgPrintEx
0x18003f788  nop     dword ptr [rax+rax+00h]
0x18003f78d  jmp     loc_18003FBBD
0x18003f792  mov     r15, r14
0x18003f795  mov     r9d, [rsp+740h+var_6D8]
0x18003f79a  mov     r8, r15; unsigned __int16 *
0x18003f79d  mov     qword ptr [rsp+740h+bInheritHandle], r12
0x18003f7a2  mov     edx, 143h; unsigned __int64
0x18003f7a7  mov     rcx, rdi; unsigned __int16 *
0x18003f7aa  mov     qword ptr [rsp+740h+dwDesiredAccess], rsi
0x18003f7af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003f7b4  mov     r14d, eax
0x18003f7b7  test    eax, eax
0x18003f7b9  jns     short loc_18003F7D0
0x18003f7bb  mov     [rsp+740h+bInheritHandle], eax
0x18003f7bf  lea     r8, aWerCrashapiUUE_31; "WER/CrashAPI/%u:%u: ERROR StringCchPrin"...
0x18003f7c6  mov     [rsp+740h+dwDesiredAccess], 12F7h
0x18003f7ce  jmp     short loc_18003F771
0x18003f7d0  call    cs:__imp_RtlGetCurrentTransaction
0x18003f7d7  nop     dword ptr [rax+rax+00h]
0x18003f7dc  xor     ecx, ecx
0x18003f7de  mov     [rsp+740h+var_6C8], rax
0x18003f7e3  call    cs:__imp_RtlSetCurrentTransaction
0x18003f7ea  nop     dword ptr [rax+rax+00h]
0x18003f7ef  mov     r12, [rbp+640h+var_6A8]
0x18003f7f3  lea     rax, word_18008EBAC
0x18003f7fa  mov     [rbp+640h+StartupInfo.cb], 70h ; 'p'
0x18003f801  mov     r15d, 96h
0x18003f807  mov     [rbp+640h+StartupInfo.lpDesktop], rax
0x18003f80b  mov     r8d, [r12]
0x18003f80f  mov     edx, r8d
0x18003f812  and     edx, 4
0x18003f815  mov     ecx, edx
0x18003f817  neg     ecx
0x18003f819  sbb     r14d, r14d
0x18003f81c  and     r14d, 40000h
0x18003f823  test    edx, edx
0x18003f825  jz      loc_18003F959
0x18003f82b  shr     r8d, 3
0x18003f82f  and     r8d, 0Fh
0x18003f833  mov     eax, r8d
0x18003f836  jz      loc_18003F954
0x18003f83c  sub     eax, 1
0x18003f83f  jz      loc_18003F954
0x18003f845  sub     eax, 1
0x18003f848  jz      loc_18003F954
0x18003f84e  sub     eax, 1
0x18003f851  jz      loc_18003F954
0x18003f857  sub     eax, 2
0x18003f85a  jz      loc_18003F954
  ... truncated ...
```
