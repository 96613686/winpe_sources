# WerpLaunchAeDebug

- ea: `0x18003b9a0`
- end: `0x18003c2ed`
- name: `WerpLaunchAeDebug`
- size: `2381`
- prototype: `__int64 __usercall@<rax>(HANDLE Process@<rcx>, HANDLE Thread@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18003b9a0`
- `0x18003c2f4`
- `0x18004ed48`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlDetermineDosPathNameType_U` at `0x18003bd59`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18003bd59`
- `ntdll!DbgPrintEx` at `0x18003bdb7`
- `ntdll!DbgPrintEx` at `0x18003beee`
- `ntdll!DbgPrintEx` at `0x18003bf22`
- `ntdll!DbgPrintEx` at `0x18003bfa1`
- `ntdll!DbgPrintEx` at `0x18003c013`
- `ntdll!DbgPrintEx` at `0x18003bdb7`
- `ntdll!DbgPrintEx` at `0x18003beee`
- `ntdll!DbgPrintEx` at `0x18003bf22`
- `ntdll!DbgPrintEx` at `0x18003bfa1`
- `ntdll!DbgPrintEx` at `0x18003c013`
- `ntdll!RtlGetCurrentTransaction` at `0x18003be01`
- `ntdll!RtlGetCurrentTransaction` at `0x18003be01`
- `ntdll!NtQueryInformationProcess` at `0x18003bec0`
- `ntdll!NtQueryInformationProcess` at `0x18003bec0`
- `ntdll!RtlSetCurrentTransaction` at `0x18003be0c`
- `ntdll!RtlSetCurrentTransaction` at `0x18003c24a`
- `ntdll!RtlSetCurrentTransaction` at `0x18003be0c`
- `ntdll!RtlSetCurrentTransaction` at `0x18003c24a`
- `ntdll!RtlGetNtSystemRoot` at `0x18003bd6b`
- `ntdll!RtlGetNtSystemRoot` at `0x18003bd6b`
- `ntdll!NtWaitForMultipleObjects` at `0x18003c1c6`
- `ntdll!NtWaitForMultipleObjects` at `0x18003c1c6`
- `ntdll!NtQuerySystemInformation` at `0x18003bb4a`
- `ntdll!NtQuerySystemInformation` at `0x18003bb4a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003ba59`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003ba59`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003c149`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003c149`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18003bfcb`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18003c056`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18003bfcb`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18003c056`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18003c0aa`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18003c0aa`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18003bb60`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18003bb60`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18003c23c`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18003c23c`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18003bd1a`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18003bd1a`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x18003bbb1`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x18003bbb1`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003c260`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003c276`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003c260`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003c276`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003baa9`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003c034`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003baa9`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003c034`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x18003c1f5`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x18003c1f5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003bb0a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003bb0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c0eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c0fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c22a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c285`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c294`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c2b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c0eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c0fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c22a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c285`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c294`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c2b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003bb1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003bb1c`

## string_xrefs

- `0x18003bdf0`: `WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printng the debugger commandline with 0x%x\n`
- `0x18003bd98`: `WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printing the debugger path with 0x%x\n`
- `0x18003bd71`: `%s\system32\%s`
- `0x18003bffb`: `WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n`
- `0x18003c0c5`: `WER/CrashAPI/%u:%u: ERROR UpdateProcThreadAttribute failed: 0x%x\n`

## pseudocode

```c
__int64 __fastcall WerpLaunchAeDebug(HANDLE Process, HANDLE Thread, __int64 a3, _OWORD *a4, __int64 a5)
{
  _DWORD *CurrentTransaction; // r13
  struct _PROC_THREAD_ATTRIBUTE_LIST *v10; // rbx
  int v11; // esi
  signed int LastErrorValue; // r14d
  unsigned __int16 *v13; // rdi
  HANDLE v14; // rcx
  char *v15; // rax
  char *v16; // rsi
  DWORD v17; // r12d
  _BYTE *v18; // rdx
  __int128 v19; // xmm0
  __int64 v20; // rcx
  __int128 v21; // xmm1
  char *v22; // rax
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  const unsigned __int16 *v41; // r14
  const unsigned __int16 *v42; // r15
  __int64 NtSystemRoot; // rax
  int v44; // eax
  const CHAR *v45; // r8
  int v46; // eax
  _DWORD *v47; // r12
  DWORD v48; // r14d
  unsigned int v49; // r8d
  NTSTATUS InformationProcess; // eax
  HANDLE v51; // r9
  int v52; // eax
  signed int v53; // eax
  const CHAR *v54; // r8
  struct _PROC_THREAD_ATTRIBUTE_LIST *v55; // rax
  NTSTATUS v56; // eax
  HANDLE v57; // rcx
  DWORD dwDesiredAccess[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwDesiredAccessa[2]; // [rsp+20h] [rbp-E0h]
  BOOL bInheritHandle[2]; // [rsp+28h] [rbp-D8h]
  BOOL bInheritHandlea[2]; // [rsp+28h] [rbp-D8h]
  char ProcessInformation[4]; // [rsp+50h] [rbp-B0h] BYREF
  int Value; // [rsp+54h] [rbp-ACh] BYREF
  DWORD ProcessId; // [rsp+58h] [rbp-A8h]
  int v66; // [rsp+5Ch] [rbp-A4h]
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hProcess; // [rsp+68h] [rbp-98h]
  SIZE_T NumberOfBytesWritten; // [rsp+70h] [rbp-90h] BYREF
  ULONG_PTR Size; // [rsp+78h] [rbp-88h] BYREF
  LPVOID lpAddress; // [rsp+80h] [rbp-80h]
  struct _PROCESS_INFORMATION lpProcessInformation; // [rsp+88h] [rbp-78h] BYREF
  __int64 v73; // [rsp+A8h] [rbp-58h]
  HANDLE UniqueProcess; // [rsp+B0h] [rbp-50h]
  HANDLE Object[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+C8h] [rbp-38h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+E0h] [rbp-20h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v78; // [rsp+148h] [rbp+48h]
  __int64 SystemInformation; // [rsp+150h] [rbp+50h] BYREF
  int v80; // [rsp+158h] [rbp+58h]
  _DWORD Buffer[2]; // [rsp+160h] [rbp+60h] BYREF
  DWORD ThreadId; // [rsp+168h] [rbp+68h]
  int v83; // [rsp+16Ch] [rbp+6Ch]
  __int64 v84; // [rsp+170h] [rbp+70h]
  __int64 v85; // [rsp+178h] [rbp+78h]
  __int64 v86; // [rsp+180h] [rbp+80h]
  __int128 v87; // [rsp+188h] [rbp+88h]
  __int128 v88; // [rsp+198h] [rbp+98h]
  __int128 v89; // [rsp+1A8h] [rbp+A8h]
  __int128 v90; // [rsp+1B8h] [rbp+B8h]
  __int128 v91; // [rsp+1C8h] [rbp+C8h]
  __int128 v92; // [rsp+1D8h] [rbp+D8h]
  __int128 v93; // [rsp+1E8h] [rbp+E8h]
  __int128 v94; // [rsp+1F8h] [rbp+F8h]
  __int128 v95; // [rsp+208h] [rbp+108h]
  __int64 v96; // [rsp+218h] [rbp+118h]
  char v97; // [rsp+220h] [rbp+120h] BYREF

  CurrentTransaction = 0;
  hProcess = Process;
  v73 = a5;
  hObject = 0;
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  Size = 0;
  SystemInformation = 0;
  v80 = 0;
  memset(&lpProcessInformation, 0, sizeof(lpProcessInformation));
  v10 = 0;
  v11 = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v66 = 0;
  *(_OWORD *)Object = 0;
  memset_0(Buffer, 0, 0x590u);
  NumberOfBytesWritten = 0;
  Value = -1;
  ProcessInformation[0] = 0;
  ProcessId = GetProcessId(Process);
  if ( !ProcessId )
  {
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    v13 = 0;
    if ( LastErrorValue > 0 )
      LastErrorValue = (unsigned __int16)LastErrorValue | 0x80070000;
    goto LABEL_75;
  }
  UniqueProcess = NtCurrentTeb()->ClientId.UniqueProcess;
  v13 = (unsigned __int16 *)VirtualAlloc(0, 0x4D0u, 0x1000u, 4u);
  if ( !v13 )
  {
    LastErrorValue = -2147024882;
    goto LABEL_75;
  }
  v14 = hObject;
  lpAddress = 0;
  EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  v15 = (char *)hObject + 1;
  EventAttributes.bInheritHandle = 1;
  hObject = 0;
  if ( (unsigned __int64)v15 > 1 )
    CloseHandle(v14);
  DuplicateHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL, Thread, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &hObject, 0, 1, 2u);
  v16 = (char *)CreateEventW(&EventAttributes, 1, 0, 0);
  if ( v16 == (char *)-1LL
    || v16 + 1 == (char *)1
    || !a3
    || NtQuerySystemInformation(SystemProcessorInformation, &SystemInformation, 0xCu, 0) < 0 )
  {
    v17 = ProcessId;
  }
  else
  {
    if ( Thread )
      ThreadId = GetThreadId(Thread);
    else
      ThreadId = 0;
    v17 = ProcessId;
    Buffer[1] = (unsigned __int16)SystemInformation;
    v84 = *(_QWORD *)(a3 + 16);
    Buffer[0] = 40;
    v83 = 0;
    if ( ProcessId == (_DWORD)UniqueProcess )
    {
      v85 = a3;
      CurrentTransaction = Buffer;
      v86 = (__int64)a4;
    }
    else
    {
      lpAddress = VirtualAllocEx(hProcess, 0, 0x590u, 0x1000u, 4u);
      v18 = lpAddress;
      if ( lpAddress )
      {
        v19 = *(_OWORD *)a3;
        v20 = 9;
        v21 = *(_OWORD *)(a3 + 16);
        v96 = *(_QWORD *)(a3 + 144);
        v22 = &v97;
        v87 = v19;
        v23 = *(_OWORD *)(a3 + 32);
        v88 = v21;
        v24 = *(_OWORD *)(a3 + 48);
        v89 = v23;
        v25 = *(_OWORD *)(a3 + 64);
        v90 = v24;
        v26 = *(_OWORD *)(a3 + 80);
        v91 = v25;
        v27 = *(_OWORD *)(a3 + 96);
        v92 = v26;
        v28 = *(_OWORD *)(a3 + 112);
        v93 = v27;
        v29 = *(_OWORD *)(a3 + 128);
        v94 = v28;
        v95 = v29;
        do
        {
          v30 = a4[1];
          *(_OWORD *)v22 = *a4;
          v31 = a4[2];
          *((_OWORD *)v22 + 1) = v30;
          v32 = a4[3];
          *((_OWORD *)v22 + 2) = v31;
          v33 = a4[4];
          *((_OWORD *)v22 + 3) = v32;
          v34 = a4[5];
          *((_OWORD *)v22 + 4) = v33;
          v35 = a4[6];
          *((_OWORD *)v22 + 5) = v34;
          v36 = a4[7];
          a4 += 8;
          *((_OWORD *)v22 + 6) = v35;
          *((_OWORD *)v22 + 7) = v36;
          v22 += 128;
          --v20;
        }
        while ( v20 );
        v37 = a4[1];
        *(_OWORD *)v22 = *a4;
        v38 = a4[2];
        *((_OWORD *)v22 + 1) = v37;
        v39 = a4[3];
        *((_OWORD *)v22 + 2) = v38;
        v40 = a4[4];
        *((_OWORD *)v22 + 3) = v39;
        *((_OWORD *)v22 + 4) = v40;
        NumberOfBytesWritten = v18 - (_BYTE *)Buffer;
        v85 = (__int64)(v18 + 40);
        v86 = (__int64)(v18 + 192);
        if ( WriteProcessMemory(hProcess, v18, Buffer, 0x590u, &NumberOfBytesWritten) )
        {
          if ( NumberOfBytesWritten == 1424 )
            CurrentTransaction = lpAddress;
        }
      }
    }
  }
  v41 = (const unsigned __int16 *)(v73 + 4);
  if ( *(_WORD *)(v73 + 4) == 34 || RtlDetermineDosPathNameType_U((PCWSTR)(v73 + 4)) != RtlPathTypeRelative )
  {
    v42 = v41;
LABEL_28:
    v46 = StringCchPrintfW(v13, 0x143u, v42, v17, v16, CurrentTransaction);
    LastErrorValue = v46;
    if ( v46 < 0 )
    {
      bInheritHandle[0] = v46;
      v45 = "WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printng the debugger commandline with 0x%x\n";
      dwDesiredAccess[0] = 4855;
      goto LABEL_26;
    }
    CurrentTransaction = (_DWORD *)RtlGetCurrentTransaction();
    RtlSetCurrentTransaction(0);
    v47 = (_DWORD *)v73;
    StartupInfo.cb = 112;
    StartupInfo.lpDesktop = (LPWSTR)&word_180086D5C;
    v48 = (*(_DWORD *)v73 & 4) != 0 ? 0x40000 : 0;
    if ( (*(_DWORD *)v73 & 4) != 0 )
    {
      v49 = (*(_DWORD *)v73 >> 3) & 0xF;
      if ( v49 < 4 || v49 == 5 || v49 == 6 || v49 == 7 )
      {
        Value = (*(_DWORD *)v73 >> 3) & 0xF;
      }
      else
      {
        Value = -1;
        if ( v49 == 14 )
        {
          ProcessInformation[0] = 0;
          InformationProcess = NtQueryInformationProcess(
                                 hProcess,
                                 ProcessAffinityUpdateMode|ProcessUserModeIOPL,
                                 ProcessInformation,
                                 1u,
                                 0);
          v51 = NtCurrentTeb()->ClientId.UniqueProcess;
          if ( InformationProcess >= 0 )
          {
            DbgPrintEx(
              0x96u,
              2u,
              "WER/CrashAPI/%u:%u: TRACE Faulting process protection/signer: %02x/%02x\n",
              (_DWORD)v51,
              4908,
              ProcessInformation[0] & 7,
              (unsigned __int8)ProcessInformation[0] >> 4);
            if ( (ProcessInformation[0] & 7u) >= 3 || (ProcessInformation[0] & 0xF0u) >= 0x90 )
              v52 = -1;
            else
              v52 = *((_DWORD *)qword_18008D850
                    + 9 * (ProcessInformation[0] & 7)
                    + ((unsigned __int64)(unsigned __int8)ProcessInformation[0] >> 4));
            Value = v52;
          }
          else
          {
            DbgPrintEx(
              0x96u,
              1u,
              "WER/CrashAPI/%u:%u: WARNING NtQueryInformationProcess/ProcessProtectionInformation failed: NTSTATUS %08X\n",
              (_DWORD)v51,
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
      (*v47 >> 3) & 0xF,
      Value);
    if ( (*(_BYTE *)v47 & 4) != 0 && Value != -1 )
    {
      if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) && NtCurrentTeb()->LastErrorValue != 122 )
      {
        v53 = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
        bInheritHandlea[0] = v53;
        dwDesiredAccessa[0] = 4937;
LABEL_49:
        v54 = "WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n";
LABEL_50:
        LastErrorValue = v53;
LABEL_51:
        DbgPrintEx(
          0x96u,
          0,
          v54,
          NtCurrentTeb()->ClientId.UniqueProcess,
          *(_QWORD *)dwDesiredAccessa,
          *(_QWORD *)bInheritHandlea);
        goto LABEL_70;
      }
      v55 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)VirtualAlloc(0, Size, 0x1000u, 4u);
      v10 = v55;
      if ( !v55 )
      {
        LastErrorValue = -2147024882;
        v54 = "WER/CrashAPI/%u:%u: ERROR Failed to allocate attribute list: 0x%x\n";
        bInheritHandlea[0] = -2147024882;
        dwDesiredAccessa[0] = 4950;
        goto LABEL_51;
      }
      if ( !InitializeProcThreadAttributeList(v55, 1u, 0, &Size) )
      {
        v53 = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
        bInheritHandlea[0] = v53;
        dwDesiredAccessa[0] = 4962;
        goto LABEL_49;
      }
      v66 = 1;
      if ( !UpdateProcThreadAttribute(v10, 0, 0x2000Bu, &Value, 4u, 0, 0) )
      {
        v53 = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
        bInheritHandlea[0] = v53;
        v54 = "WER/CrashAPI/%u:%u: ERROR UpdateProcThreadAttribute failed: 0x%x\n";
        dwDesiredAccessa[0] = 4978;
        goto LABEL_50;
      }
      v78 = v10;
      v48 |= 0x80000u;
    }
    if ( lpProcessInformation.hProcess )
      CloseHandle(lpProcessInformation.hProcess);
    if ( lpProcessInformation.hThread )
      CloseHandle(lpProcessInformation.hThread);
    memset(&lpProcessInformation, 0, sizeof(lpProcessInformation));
    if ( CreateProcessW(0, v13, 0, 0, 1, v48, 0, 0, &StartupInfo, &lpProcessInformation) )
    {
      LastErrorValue = 0;
      if ( (unsigned __int64)(v16 + 1) > 1 )
      {
        Object[1] = lpProcessInformation.hProcess;
        Object[0] = v16;
        while ( 1 )
        {
          v56 = NtWaitForMultipleObjects(2u, Object, WaitAny, 1u, 0);
          if ( !v56 )
            break;
          if ( v56 == 1 )
          {
            LastErrorValue = -2147023829;
            goto LABEL_70;
          }
        }
      }
      goto LABEL_70;
    }
    v53 = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
    bInheritHandlea[0] = v53;
    v54 = "WER/CrashAPI/%u:%u: ERROR Debugger spawn failed: 0x%x\n";
    dwDesiredAccessa[0] = 5003;
    goto LABEL_50;
  }
  v42 = v13 + 323;
  NtSystemRoot = RtlGetNtSystemRoot();
  v44 = StringCchPrintfW(v13 + 323, 0x125u, L"%s\\system32\\%s", NtSystemRoot, v41);
  LastErrorValue = v44;
  if ( v44 >= 0 )
    goto LABEL_28;
  bInheritHandle[0] = v44;
  v45 = "WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printing the debugger path with 0x%x\n";
  dwDesiredAccess[0] = 4834;
LABEL_26:
  DbgPrintEx(
    0x96u,
    0,
    v45,
    NtCurrentTeb()->ClientId.UniqueProcess,
    *(_QWORD *)dwDesiredAccess,
    *(_QWORD *)bInheritHandle);
  CurrentTransaction = 0;
LABEL_70:
  if ( lpAddress )
    VirtualFreeEx(hProcess, lpAddress, 0, 0x8000u);
  if ( (unsigned __int64)(v16 + 1) > 1 )
    CloseHandle(v16);
  v11 = v66;
LABEL_75:
  v57 = hObject;
  hObject = 0;
  if ( (unsigned __int64)v57 + 1 > 1 )
    CloseHandle(v57);
  if ( v11 && v10 )
    DeleteProcThreadAttributeList(v10);
  if ( CurrentTransaction )
    RtlSetCurrentTransaction(CurrentTransaction);
  if ( v13 )
    VirtualFree(v13, 0, 0x8000u);
  if ( v10 )
    VirtualFree(v10, 0, 0x8000u);
  if ( lpProcessInformation.hProcess )
    CloseHandle(lpProcessInformation.hProcess);
  if ( lpProcessInformation.hThread )
    CloseHandle(lpProcessInformation.hThread);
  memset(&lpProcessInformation, 0, sizeof(lpProcessInformation));
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return (unsigned int)LastErrorValue;
}

```

## disassembly

```asm
0x18003b9a0  push    rbp
0x18003b9a2  push    rbx
0x18003b9a3  push    rsi
0x18003b9a4  push    rdi
0x18003b9a5  push    r12
0x18003b9a7  push    r13
0x18003b9a9  push    r14
0x18003b9ab  push    r15
0x18003b9ad  lea     rbp, [rsp-608h]
0x18003b9b5  sub     rsp, 708h
0x18003b9bc  mov     rax, cs:__security_cookie
0x18003b9c3  xor     rax, rsp
0x18003b9c6  mov     [rbp+640h+var_50], rax
0x18003b9cd  mov     rax, [rbp+640h+arg_20]
0x18003b9d4  xor     r13d, r13d
0x18003b9d7  mov     r15, r8
0x18003b9da  mov     [rsp+740h+hProcess], rcx
0x18003b9df  mov     r12, rdx
0x18003b9e2  mov     [rbp+640h+var_698], rax
0x18003b9e6  mov     rdi, rcx
0x18003b9e9  mov     [rsp+740h+hObject], r13
0x18003b9ee  lea     r8d, [r13+68h]; Size
0x18003b9f2  mov     qword ptr [rbp+640h+StartupInfo.cb], r13
0x18003b9f6  xor     edx, edx; Val
0x18003b9f8  lea     rcx, [rbp+640h+StartupInfo.lpReserved]; void *
0x18003b9fc  mov     r14, r9
0x18003b9ff  call    memset_0
0x18003ba04  xor     eax, eax
0x18003ba06  mov     [rsp+740h+Size], r13
0x18003ba0b  xorps   xmm0, xmm0
0x18003ba0e  mov     [rbp+640h+var_6A8], rax
0x18003ba12  xor     edx, edx; Val
0x18003ba14  mov     qword ptr [rbp+640h+EventAttributes.bInheritHandle], rax
0x18003ba18  mov     r8d, 590h; Size
0x18003ba1e  mov     [rbp+640h+SystemInformation], rax
0x18003ba22  lea     rcx, [rbp+640h+Buffer]; void *
0x18003ba26  mov     [rbp+640h+var_5E8], eax
0x18003ba29  movups  xmmword ptr [rbp+640h+var_6B8], xmm0
0x18003ba2d  mov     ebx, r13d
0x18003ba30  mov     esi, r13d
0x18003ba33  movups  xmmword ptr [rbp+640h+EventAttributes.nLength], xmm0
0x18003ba37  mov     [rsp+740h+var_6E4], r13d
0x18003ba3c  movups  xmmword ptr [rbp+640h+Object], xmm0
0x18003ba40  call    memset_0
0x18003ba45  mov     rcx, rdi; Process
0x18003ba48  mov     [rsp+740h+NumberOfBytesWritten], rbx
0x18003ba4d  mov     [rsp+740h+Value], 0FFFFFFFFh
0x18003ba55  mov     [rsp+740h+ProcessInformation], bl
0x18003ba59  call    cs:__imp_GetProcessId
0x18003ba5f  mov     [rsp+740h+var_6E8], eax
0x18003ba63  test    eax, eax
0x18003ba65  jnz     short loc_18003BA8B
0x18003ba67  mov     r14d, gs:68h
0x18003ba70  xor     edi, edi
0x18003ba72  test    r14d, r14d
0x18003ba75  jle     loc_18003C212
0x18003ba7b  movzx   r14d, r14w
0x18003ba7f  or      r14d, 80070000h
0x18003ba86  jmp     loc_18003C212
0x18003ba8b  mov     rax, gs:40h
0x18003ba94  xor     ecx, ecx; lpAddress
0x18003ba96  mov     edx, 4D0h; dwSize
0x18003ba9b  mov     [rbp+640h+var_690], rax
0x18003ba9f  mov     r8d, 1000h; flAllocationType
0x18003baa5  lea     r9d, [rcx+4]; flProtect
0x18003baa9  call    cs:__imp_VirtualAlloc
0x18003baaf  mov     rdi, rax
0x18003bab2  test    rax, rax
0x18003bab5  jz      loc_18003C2E2
0x18003babb  mov     rcx, [rsp+740h+hObject]; hObject
0x18003bac0  mov     esi, 1
0x18003bac5  mov     [rbp+640h+lpAddress], r13
0x18003bac9  mov     [rbp+640h+EventAttributes.nLength], 18h
0x18003bad0  mov     [rbp+640h+EventAttributes.lpSecurityDescriptor], rbx
0x18003bad4  lea     rax, [rcx+1]
0x18003bad8  mov     [rbp+640h+EventAttributes.bInheritHandle], esi
0x18003badb  mov     [rsp+740h+hObject], rbx
0x18003bae0  cmp     rax, rsi
0x18003bae3  jbe     short loc_18003BAEB
0x18003bae5  call    cs:__imp_CloseHandle
0x18003baeb  or      rcx, 0FFFFFFFFFFFFFFFFh; hSourceProcessHandle
0x18003baef  mov     [rsp+740h+dwOptions], 2; dwOptions
0x18003baf7  mov     r8, rcx; hTargetProcessHandle
0x18003bafa  mov     [rsp+740h+bInheritHandle], esi; bInheritHandle
0x18003bafe  lea     r9, [rsp+740h+hObject]; lpTargetHandle
0x18003bb03  mov     [rsp+740h+dwDesiredAccess], ebx; dwDesiredAccess
0x18003bb07  mov     rdx, r12; hSourceHandle
0x18003bb0a  call    cs:__imp_DuplicateHandle
0x18003bb10  xor     r9d, r9d; lpName
0x18003bb13  lea     rcx, [rbp+640h+EventAttributes]; lpEventAttributes
0x18003bb17  xor     r8d, r8d; bInitialState
0x18003bb1a  mov     edx, esi; bManualReset
0x18003bb1c  call    cs:__imp_CreateEventW
0x18003bb22  mov     rsi, rax
0x18003bb25  inc     rax
0x18003bb28  cmp     rax, 1
0x18003bb2c  jbe     loc_18003BD42
0x18003bb32  test    r15, r15
0x18003bb35  jz      loc_18003BD42
0x18003bb3b  xor     r9d, r9d; ReturnLength
0x18003bb3e  lea     rdx, [rbp+640h+SystemInformation]; SystemInformation
0x18003bb42  lea     r8d, [r9+0Ch]; SystemInformationLength
0x18003bb46  lea     ecx, [r9+1]; SystemInformationClass
0x18003bb4a  call    cs:__imp_NtQuerySystemInformation
0x18003bb50  test    eax, eax
0x18003bb52  js      loc_18003BD42
0x18003bb58  test    r12, r12
0x18003bb5b  jz      short loc_18003BB6B
0x18003bb5d  mov     rcx, r12; Thread
0x18003bb60  call    cs:__imp_GetThreadId
0x18003bb66  mov     [rbp+640h+var_5D8], eax
0x18003bb69  jmp     short loc_18003BB6E
0x18003bb6b  mov     [rbp+640h+var_5D8], ebx
0x18003bb6e  movzx   eax, word ptr [rbp+640h+SystemInformation]
0x18003bb72  mov     r12d, [rsp+740h+var_6E8]
0x18003bb77  mov     [rbp+640h+var_5DC], eax
0x18003bb7a  mov     rax, [r15+10h]
0x18003bb7e  mov     [rbp+640h+var_5D0], rax
0x18003bb82  mov     [rbp+640h+Buffer], 28h ; '('
0x18003bb89  mov     [rbp+640h+var_5D4], ebx
0x18003bb8c  cmp     r12d, dword ptr [rbp+640h+var_690]
0x18003bb90  jz      loc_18003BD31
0x18003bb96  mov     rcx, [rsp+740h+hProcess]; hProcess
0x18003bb9b  xor     edx, edx; lpAddress
0x18003bb9d  mov     r9d, 1000h; flAllocationType
0x18003bba3  mov     [rsp+740h+dwDesiredAccess], 4; flProtect
0x18003bbab  mov     r8d, 590h; dwSize
0x18003bbb1  call    cs:__imp_VirtualAllocEx
0x18003bbb7  mov     [rbp+640h+lpAddress], rax
0x18003bbbb  mov     rdx, rax; lpBaseAddress
0x18003bbbe  test    rax, rax
0x18003bbc1  jz      loc_18003BD47
0x18003bbc7  movups  xmm0, xmmword ptr [r15]
0x18003bbcb  mov     rax, [r15+90h]
0x18003bbd2  mov     ecx, 9
0x18003bbd7  movups  xmm1, xmmword ptr [r15+10h]
0x18003bbdc  mov     [rbp+640h+var_528], rax
0x18003bbe3  lea     rax, [rbp+640h+var_520]
0x18003bbea  movups  [rbp+640h+var_5B8], xmm0
0x18003bbf1  lea     r8d, [rcx+77h]
0x18003bbf5  movups  xmm0, xmmword ptr [r15+20h]
0x18003bbfa  movups  [rbp+640h+var_5A8], xmm1
0x18003bc01  movups  xmm1, xmmword ptr [r15+30h]
0x18003bc06  movups  [rbp+640h+var_598], xmm0
0x18003bc0d  movups  xmm0, xmmword ptr [r15+40h]
0x18003bc12  movups  [rbp+640h+var_588], xmm1
0x18003bc19  movups  xmm1, xmmword ptr [r15+50h]
0x18003bc1e  movups  [rbp+640h+var_578], xmm0
0x18003bc25  movups  xmm0, xmmword ptr [r15+60h]
0x18003bc2a  movups  [rbp+640h+var_568], xmm1
0x18003bc31  movups  xmm1, xmmword ptr [r15+70h]
0x18003bc36  movups  [rbp+640h+var_558], xmm0
0x18003bc3d  movups  xmm0, xmmword ptr [r15+80h]
0x18003bc45  movups  [rbp+640h+var_548], xmm1
0x18003bc4c  movups  [rbp+640h+var_538], xmm0
0x18003bc53  movups  xmm0, xmmword ptr [r14]
0x18003bc57  movups  xmm1, xmmword ptr [r14+10h]
0x18003bc5c  movups  xmmword ptr [rax], xmm0
0x18003bc5f  movups  xmm0, xmmword ptr [r14+20h]
0x18003bc64  movups  xmmword ptr [rax+10h], xmm1
0x18003bc68  movups  xmm1, xmmword ptr [r14+30h]
0x18003bc6d  movups  xmmword ptr [rax+20h], xmm0
0x18003bc71  movups  xmm0, xmmword ptr [r14+40h]
0x18003bc76  movups  xmmword ptr [rax+30h], xmm1
0x18003bc7a  movups  xmm1, xmmword ptr [r14+50h]
0x18003bc7f  movups  xmmword ptr [rax+40h], xmm0
0x18003bc83  movups  xmm0, xmmword ptr [r14+60h]
0x18003bc88  movups  xmmword ptr [rax+50h], xmm1
0x18003bc8c  movups  xmm1, xmmword ptr [r14+70h]
0x18003bc91  add     r14, r8
0x18003bc94  movups  xmmword ptr [rax+60h], xmm0
0x18003bc98  movups  xmmword ptr [rax+70h], xmm1
0x18003bc9c  add     rax, r8
0x18003bc9f  sub     rcx, 1
0x18003bca3  jnz     short loc_18003BC53
0x18003bca5  movups  xmm0, xmmword ptr [r14]
0x18003bca9  mov     rcx, rdx
0x18003bcac  lea     r8, [rbp+640h+Buffer]; lpBuffer
0x18003bcb0  movups  xmm1, xmmword ptr [r14+10h]
0x18003bcb5  movups  xmmword ptr [rax], xmm0
0x18003bcb8  movups  xmm0, xmmword ptr [r14+20h]
0x18003bcbd  movups  xmmword ptr [rax+10h], xmm1
0x18003bcc1  movups  xmm1, xmmword ptr [r14+30h]
0x18003bcc6  movups  xmmword ptr [rax+20h], xmm0
0x18003bcca  movups  xmm0, xmmword ptr [r14+40h]
0x18003bccf  mov     r14d, 590h
0x18003bcd5  movups  xmmword ptr [rax+30h], xmm1
0x18003bcd9  mov     r9d, r14d; nSize
0x18003bcdc  movups  xmmword ptr [rax+40h], xmm0
0x18003bce0  lea     rax, [rbp+640h+Buffer]
0x18003bce4  sub     rcx, rax
0x18003bce7  lea     rax, [rbp+640h+var_5B8]
0x18003bcee  add     rax, rcx
0x18003bcf1  mov     [rsp+740h+NumberOfBytesWritten], rcx
0x18003bcf6  mov     [rbp+640h+var_5C8], rax
0x18003bcfa  lea     rax, [rbp+640h+var_520]
0x18003bd01  add     rax, rcx
0x18003bd04  mov     rcx, [rsp+740h+hProcess]; hProcess
0x18003bd09  mov     [rbp+640h+var_5C0], rax
0x18003bd10  lea     rax, [rsp+740h+NumberOfBytesWritten]
0x18003bd15  mov     qword ptr [rsp+740h+dwDesiredAccess], rax; lpNumberOfBytesWritten
0x18003bd1a  call    cs:__imp_WriteProcessMemory
0x18003bd20  test    eax, eax
0x18003bd22  jz      short loc_18003BD47
0x18003bd24  cmp     [rsp+740h+NumberOfBytesWritten], r14
0x18003bd29  jnz     short loc_18003BD47
0x18003bd2b  mov     r13, [rbp+640h+lpAddress]
0x18003bd2f  jmp     short loc_18003BD47
0x18003bd31  mov     [rbp+640h+var_5C8], r15
0x18003bd35  lea     r13, [rbp+640h+Buffer]
0x18003bd39  mov     [rbp+640h+var_5C0], r14
0x18003bd40  jmp     short loc_18003BD47
0x18003bd42  mov     r12d, [rsp+740h+var_6E8]
0x18003bd47  mov     r14, [rbp+640h+var_698]
0x18003bd4b  add     r14, 4
0x18003bd4f  cmp     word ptr [r14], 22h ; '"'
0x18003bd54  jz      short loc_18003BDC5
0x18003bd56  mov     rcx, r14; Path
0x18003bd59  call    cs:__imp_RtlDetermineDosPathNameType_U
0x18003bd5f  cmp     eax, 5
0x18003bd62  jnz     short loc_18003BDC5
0x18003bd64  lea     r15, [rdi+286h]
0x18003bd6b  call    cs:__imp_RtlGetNtSystemRoot
0x18003bd71  lea     r8, aSSystem32S; "%s\\system32\\%s"
0x18003bd78  mov     qword ptr [rsp+740h+dwDesiredAccess], r14
0x18003bd7d  mov     r9, rax
0x18003bd80  mov     edx, 125h; unsigned __int64
0x18003bd85  mov     rcx, r15; unsigned __int16 *
0x18003bd88  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003bd8d  mov     r14d, eax
0x18003bd90  test    eax, eax
0x18003bd92  jns     short loc_18003BDC8
0x18003bd94  mov     [rsp+740h+bInheritHandle], eax
0x18003bd98  lea     r8, aWerCrashapiUUE_10; "WER/CrashAPI/%u:%u: ERROR StringCchPrin"...
0x18003bd9f  mov     [rsp+740h+dwDesiredAccess], 12E2h
0x18003bda7  mov     r9, gs:40h
0x18003bdb0  xor     edx, edx; Level
0x18003bdb2  mov     ecx, 96h; ComponentId
0x18003bdb7  call    cs:__imp_DbgPrintEx
0x18003bdbd  mov     r13, rbx
0x18003bdc0  jmp     loc_18003C1DB
0x18003bdc5  mov     r15, r14
0x18003bdc8  mov     qword ptr [rsp+740h+bInheritHandle], r13
0x18003bdcd  mov     r9d, r12d
0x18003bdd0  mov     r8, r15; unsigned __int16 *
0x18003bdd3  mov     qword ptr [rsp+740h+dwDesiredAccess], rsi
0x18003bdd8  mov     edx, 143h; unsigned __int64
0x18003bddd  mov     rcx, rdi; unsigned __int16 *
0x18003bde0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003bde5  mov     r14d, eax
0x18003bde8  test    eax, eax
0x18003bdea  jns     short loc_18003BE01
0x18003bdec  mov     [rsp+740h+bInheritHandle], eax
0x18003bdf0  lea     r8, aWerCrashapiUUE_31; "WER/CrashAPI/%u:%u: ERROR StringCchPrin"...
0x18003bdf7  mov     [rsp+740h+dwDesiredAccess], 12F7h
0x18003bdff  jmp     short loc_18003BDA7
0x18003be01  call    cs:__imp_RtlGetCurrentTransaction
0x18003be07  xor     ecx, ecx
0x18003be09  mov     r13, rax
0x18003be0c  call    cs:__imp_RtlSetCurrentTransaction
0x18003be12  mov     r12, [rbp+640h+var_698]
0x18003be16  lea     rax, word_180086D5C
0x18003be1d  mov     [rbp+640h+StartupInfo.cb], 70h ; 'p'
0x18003be24  mov     r15d, 96h
0x18003be2a  mov     [rbp+640h+StartupInfo.lpDesktop], rax
0x18003be2e  mov     r8d, [r12]
0x18003be32  mov     edx, r8d
0x18003be35  and     edx, 4
0x18003be38  mov     ecx, edx
0x18003be3a  neg     ecx
0x18003be3c  sbb     r14d, r14d
0x18003be3f  and     r14d, 40000h
0x18003be46  test    edx, edx
0x18003be48  jz      loc_18003BF6B
0x18003be4e  shr     r8d, 3
0x18003be52  and     r8d, 0Fh
0x18003be56  mov     eax, r8d
0x18003be59  jz      loc_18003BF66
0x18003be5f  sub     eax, 1
0x18003be62  jz      loc_18003BF66
0x18003be68  sub     eax, 1
0x18003be6b  jz      loc_18003BF66
0x18003be71  sub     eax, 1
0x18003be74  jz      loc_18003BF66
0x18003be7a  sub     eax, 2
0x18003be7d  jz      loc_18003BF66
0x18003be83  sub     eax, 1
0x18003be86  jz      loc_18003BF66
0x18003be8c  sub     eax, 1
0x18003be8f  jz      loc_18003BF66
0x18003be95  mov     [rsp+740h+Value], 0FFFFFFFFh
0x18003be9d  cmp     eax, 7
0x18003bea0  jnz     loc_18003BF6B
0x18003bea6  mov     rcx, [rsp+740h+hProcess]; ProcessHandle
0x18003beab  lea     r9d, [rax-6]; ProcessInformationLength
0x18003beaf  lea     r8, [rsp+740h+ProcessInformation]; ProcessInformation
0x18003beb4  mov     [rsp+740h+ProcessInformation], bl
0x18003beb8  lea     edx, [rax+36h]; ProcessInformationClass
0x18003bebb  mov     qword ptr [rsp+740h+dwDesiredAccess], rbx; ReturnLength
0x18003bec0  call    cs:__imp_NtQueryInformationProcess
  ... truncated ...
```
