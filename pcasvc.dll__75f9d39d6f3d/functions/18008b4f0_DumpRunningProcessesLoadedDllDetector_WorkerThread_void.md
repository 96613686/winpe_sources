# DumpRunningProcessesLoadedDllDetector_WorkerThread(void *)

- ea: `0x18008b4f0`
- end: `0x18008b77b`
- name: `?DumpRunningProcessesLoadedDllDetector_WorkerThread@@YAKPEAX@Z`
- size: `651`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007020`
- `0x180012920`
- `0x18003c26c`
- `0x180089f80`
- `0x18008a4c4`
- `0x18008ad74`
- `0x18008b010`
- `0x18008b4f0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18008b62e`
- `ntdll!RtlFreeHeap` at `0x18008b62e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008b6a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008b6a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b757`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b757`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008b664`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008b664`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008b5d8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008b5d8`

## string_xrefs

- `0x18008b503`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18008b5c7`: `ProcessLoadedDllDetectorLastRun`
- `0x18008b646`: `ProcessLoadedDllDetectorLastRun`
- `0x18008b53d`: `ProcessLoadedDllDetectorInterval`
- `0x18008b56e`: `DumpRunningProcessesLoadedDllDetector worker thread started, initial enabled state: %d`
- `0x18008b54c`: `ProcessLoadedDllDetectorEnabled`
- `0x18008b6bd`: `ProcessLoadedDllDetectorEnabled`
- `0x18008b5e2`: `RegSetKeyValueW failed to set last run timestamp [%d]`
- `0x18008b560`: `DumpRunningProcessesLoadedDllDetector_WorkerThread`
- `0x18008b707`: `Feature enabled, creating scheduled task`
- `0x18008b6e1`: `DumpRunningProcessesLoadedDllDetector enabled state changed from %d to %d`
- `0x18008b72a`: `Feature disabled, deleting scheduled task`

## pseudocode

```c
__int64 __fastcall DumpRunningProcessesLoadedDllDetector_WorkerThread(PVOID Parameter)
{
  DWORD RegistryDWORD; // esi
  unsigned int v2; // ebx
  unsigned int v3; // edi
  unsigned __int64 v4; // rax
  WCHAR *v5; // rbx
  __int64 result; // rax
  unsigned __int64 Data; // [rsp+78h] [rbp+38h] BYREF
  PVOID P; // [rsp+80h] [rbp+40h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp+48h] BYREF

  Data = 0;
  SystemTimeAsFileTime = 0;
  P = 0;
  RegistryDWORD = PcaUtilityGetRegistryDWORD(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                    L"ProcessLoadedDllDetectorInterval",
                    0xDBBA00u);
  v2 = PcaUtilityGetRegistryDWORD(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
         L"ProcessLoadedDllDetectorEnabled",
         0);
  v3 = v2;
  AslLogCallPrintf(
    3,
    (unsigned int)"DumpRunningProcessesLoadedDllDetector_WorkerThread",
    2156,
    (unsigned int)"DumpRunningProcessesLoadedDllDetector worker thread started, initial enabled state: %d");
  if ( v2 )
    goto LABEL_4;
  DumpRunningProcessesLoadedDllDetector_DeleteTask();
  while ( 1 )
  {
    if ( !v2 )
      goto LABEL_16;
LABEL_4:
    v4 = DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult((unsigned __int16 **)&P);
    v5 = (WCHAR *)P;
    Data = v4;
    if ( !v4 )
      goto LABEL_9;
    if ( RegSetKeyValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
           L"ProcessLoadedDllDetectorLastRun",
           0xBu,
           &Data,
           8u) )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"DumpRunningProcessesLoadedDllDetector_WorkerThread",
        2182,
        (unsigned int)"RegSetKeyValueW failed to set last run timestamp [%d]");
      Data = 0;
      goto LABEL_9;
    }
    if ( v5 )
    {
      DumpRunningProcessesLoadedDllDetector_SaveAppData(v5);
LABEL_9:
      if ( v5 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
        P = 0;
      }
    }
    if ( !Data )
      Data = PcaUtilityGetRegistryQWORD(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
               L"ProcessLoadedDllDetectorLastRun",
               0);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( !Data || Data + 20000 * RegistryDWORD < *(_QWORD *)&SystemTimeAsFileTime )
      DumpRunningProcessesLoadedDllDetector_ScheduleTask();
LABEL_16:
    if ( (g_DllDetectorState & 2) != 0 || WaitForSingleObject(g_DllDetectorWaitEvent, RegistryDWORD) != 258 )
      break;
    v2 = PcaUtilityGetRegistryDWORD(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
           L"ProcessLoadedDllDetectorEnabled",
           0);
    if ( v2 != v3 )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"DumpRunningProcessesLoadedDllDetector_WorkerThread",
        2258,
        (unsigned int)"DumpRunningProcessesLoadedDllDetector enabled state changed from %d to %d");
      if ( v2 )
      {
        if ( !v3 )
        {
          AslLogCallPrintf(
            3,
            (unsigned int)"DumpRunningProcessesLoadedDllDetector_WorkerThread",
            2263,
            (unsigned int)"Feature enabled, creating scheduled task");
          DumpRunningProcessesLoadedDllDetector_ScheduleTask();
        }
      }
      else if ( v3 )
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"DumpRunningProcessesLoadedDllDetector_WorkerThread",
          2269,
          (unsigned int)"Feature disabled, deleting scheduled task");
        DumpRunningProcessesLoadedDllDetector_DeleteTask();
      }
      v3 = v2;
    }
  }
  CloseHandle(g_DllDetectorWaitEvent);
  result = 0;
  g_DllDetectorWaitEvent = 0;
  return result;
}

```

## disassembly

```asm
0x18008b4f0  mov     [rsp-28h+arg_0], rbx
0x18008b4f5  push    rbp
0x18008b4f6  push    rsi
0x18008b4f7  push    rdi
0x18008b4f8  push    r13
0x18008b4fa  push    r15
0x18008b4fc  mov     rbp, rsp
0x18008b4ff  sub     rsp, 40h
0x18008b503  lea     r13, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18008b50a  mov     [rbp+Data], 0
0x18008b512  mov     rbx, 0FFFFFFFF80000002h
0x18008b519  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18008b521  mov     rdx, r13; unsigned __int16 *
0x18008b524  mov     [rbp+var_10], 0
0x18008b52c  mov     rcx, rbx; HKEY
0x18008b52f  mov     [rbp+P], 0
0x18008b537  mov     r9d, 0DBBA00h; unsigned int
0x18008b53d  lea     r8, aProcessloadedd_0; "ProcessLoadedDllDetectorInterval"
0x18008b544  call    ?PcaUtilityGetRegistryDWORD@@YAKPEAUHKEY__@@PEBG1K@Z; PcaUtilityGetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18008b549  xor     r9d, r9d; unsigned int
0x18008b54c  lea     r8, aProcessloadedd_2; "ProcessLoadedDllDetectorEnabled"
0x18008b553  mov     rdx, r13; unsigned __int16 *
0x18008b556  mov     rcx, rbx; HKEY
0x18008b559  mov     esi, eax
0x18008b55b  call    ?PcaUtilityGetRegistryDWORD@@YAKPEAUHKEY__@@PEBG1K@Z; PcaUtilityGetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18008b560  lea     r15, aDumprunningpro_11; "DumpRunningProcessesLoadedDllDetector_W"...
0x18008b567  mov     dword ptr [rsp+40h+lpData], eax
0x18008b56b  mov     rdx, r15
0x18008b56e  lea     r9, aDumprunningpro_7; "DumpRunningProcessesLoadedDllDetector w"...
0x18008b575  mov     r8d, 86Ch
0x18008b57b  mov     ecx, 3
0x18008b580  mov     ebx, eax
0x18008b582  mov     edi, eax
0x18008b584  call    AslLogCallPrintf
0x18008b589  test    ebx, ebx
0x18008b58b  jnz     short loc_18008B59A
0x18008b58d  call    ?DumpRunningProcessesLoadedDllDetector_DeleteTask@@YAKXZ; DumpRunningProcessesLoadedDllDetector_DeleteTask(void)
0x18008b592  test    ebx, ebx
0x18008b594  jz      loc_18008B693
0x18008b59a  lea     rcx, [rbp+P]; unsigned __int16 **
0x18008b59e  call    ?DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult@@YA_KPEAPEAG@Z; DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult(ushort * *)
0x18008b5a3  mov     rbx, [rbp+P]
0x18008b5a7  mov     [rbp+Data], rax
0x18008b5ab  test    rax, rax
0x18008b5ae  jz      short loc_18008B617
0x18008b5b0  lea     rax, [rbp+Data]
0x18008b5b4  mov     [rsp+40h+cbData], 8; cbData
0x18008b5bc  mov     r9d, 0Bh; dwType
0x18008b5c2  mov     [rsp+40h+lpData], rax; lpData
0x18008b5c7  lea     r8, aProcessloadedd_1; "ProcessLoadedDllDetectorLastRun"
0x18008b5ce  mov     rdx, r13; lpSubKey
0x18008b5d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008b5d8  call    cs:__imp_RegSetKeyValueW
0x18008b5de  test    eax, eax
0x18008b5e0  jz      short loc_18008B60A
0x18008b5e2  lea     r9, aRegsetkeyvalue_0; "RegSetKeyValueW failed to set last run "...
0x18008b5e9  mov     dword ptr [rsp+40h+lpData], eax
0x18008b5ed  mov     r8d, 886h
0x18008b5f3  mov     rdx, r15
0x18008b5f6  mov     ecx, 1
0x18008b5fb  call    AslLogCallPrintf
0x18008b600  mov     [rbp+Data], 0
0x18008b608  jmp     short loc_18008B617
0x18008b60a  test    rbx, rbx
0x18008b60d  jz      short loc_18008B63C
0x18008b60f  mov     rcx, rbx; lpWideCharStr
0x18008b612  call    ?DumpRunningProcessesLoadedDllDetector_SaveAppData@@YAXPEAG@Z; DumpRunningProcessesLoadedDllDetector_SaveAppData(ushort *)
0x18008b617  test    rbx, rbx
0x18008b61a  jz      short loc_18008B63C
0x18008b61c  mov     rcx, gs:60h
0x18008b625  mov     r8, rbx; P
0x18008b628  xor     edx, edx; Flags
0x18008b62a  mov     rcx, [rcx+30h]; HeapHandle
0x18008b62e  call    cs:__imp_RtlFreeHeap
0x18008b634  mov     [rbp+P], 0
0x18008b63c  cmp     [rbp+Data], 0
0x18008b641  jnz     short loc_18008B660
0x18008b643  xor     r9d, r9d; unsigned __int64
0x18008b646  lea     r8, aProcessloadedd_1; "ProcessLoadedDllDetectorLastRun"
0x18008b64d  mov     rdx, r13; unsigned __int16 *
0x18008b650  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18008b657  call    ?PcaUtilityGetRegistryQWORD@@YA_KPEAUHKEY__@@PEBG1_K@Z; PcaUtilityGetRegistryQWORD(HKEY__ *,ushort const *,ushort const *,unsigned __int64)
0x18008b65c  mov     [rbp+Data], rax
0x18008b660  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18008b664  call    cs:__imp_GetSystemTimeAsFileTime
0x18008b66a  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18008b66d  mov     rdx, [rbp+Data]
0x18008b671  mov     dword ptr [rbp+var_10+4], eax
0x18008b674  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18008b677  mov     dword ptr [rbp+var_10], eax
0x18008b67a  test    rdx, rdx
0x18008b67d  jz      short loc_18008B68E
0x18008b67f  imul    ecx, esi, 4E20h
0x18008b685  add     rcx, rdx
0x18008b688  cmp     rcx, [rbp+var_10]
0x18008b68c  jnb     short loc_18008B693
0x18008b68e  call    ?DumpRunningProcessesLoadedDllDetector_ScheduleTask@@YAKXZ; DumpRunningProcessesLoadedDllDetector_ScheduleTask(void)
0x18008b693  test    byte ptr cs:?g_DllDetectorState@@3KA, 2; ulong g_DllDetectorState
0x18008b69a  jnz     loc_18008B750
0x18008b6a0  mov     rcx, cs:?g_DllDetectorWaitEvent@@3PEAXEA; hHandle
0x18008b6a7  mov     edx, esi; dwMilliseconds
0x18008b6a9  call    cs:__imp_WaitForSingleObject
0x18008b6af  cmp     eax, 102h
0x18008b6b4  jnz     loc_18008B750
0x18008b6ba  xor     r9d, r9d; unsigned int
0x18008b6bd  lea     r8, aProcessloadedd_2; "ProcessLoadedDllDetectorEnabled"
0x18008b6c4  mov     rdx, r13; unsigned __int16 *
0x18008b6c7  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18008b6ce  call    ?PcaUtilityGetRegistryDWORD@@YAKPEAUHKEY__@@PEBG1K@Z; PcaUtilityGetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18008b6d3  mov     ebx, eax
0x18008b6d5  cmp     eax, edi
0x18008b6d7  jz      loc_18008B592
0x18008b6dd  mov     [rsp+40h+cbData], eax
0x18008b6e1  lea     r9, aDumprunningpro_4; "DumpRunningProcessesLoadedDllDetector e"...
0x18008b6e8  mov     r8d, 8D2h
0x18008b6ee  mov     dword ptr [rsp+40h+lpData], edi
0x18008b6f2  mov     rdx, r15
0x18008b6f5  mov     ecx, 3
0x18008b6fa  call    AslLogCallPrintf
0x18008b6ff  test    ebx, ebx
0x18008b701  jz      short loc_18008B726
0x18008b703  test    edi, edi
0x18008b705  jnz     short loc_18008B749
0x18008b707  lea     r9, aFeatureEnabled; "Feature enabled, creating scheduled tas"...
0x18008b70e  mov     r8d, 8D7h
0x18008b714  mov     rdx, r15
0x18008b717  lea     ecx, [rdi+3]
0x18008b71a  call    AslLogCallPrintf
0x18008b71f  call    ?DumpRunningProcessesLoadedDllDetector_ScheduleTask@@YAKXZ; DumpRunningProcessesLoadedDllDetector_ScheduleTask(void)
0x18008b724  jmp     short loc_18008B749
0x18008b726  test    edi, edi
0x18008b728  jz      short loc_18008B749
0x18008b72a  lea     r9, aFeatureDisable; "Feature disabled, deleting scheduled ta"...
0x18008b731  mov     r8d, 8DDh
0x18008b737  mov     rdx, r15
0x18008b73a  mov     ecx, 3
0x18008b73f  call    AslLogCallPrintf
0x18008b744  call    ?DumpRunningProcessesLoadedDllDetector_DeleteTask@@YAKXZ; DumpRunningProcessesLoadedDllDetector_DeleteTask(void)
0x18008b749  mov     edi, ebx
0x18008b74b  jmp     loc_18008B592
0x18008b750  mov     rcx, cs:?g_DllDetectorWaitEvent@@3PEAXEA; hObject
0x18008b757  call    cs:__imp_CloseHandle
0x18008b75d  mov     rbx, [rsp+40h+arg_0]
0x18008b762  xor     eax, eax
0x18008b764  mov     cs:?g_DllDetectorWaitEvent@@3PEAXEA, 0; void * g_DllDetectorWaitEvent
0x18008b76f  add     rsp, 40h
0x18008b773  pop     r15
0x18008b775  pop     r13
0x18008b777  pop     rdi
0x18008b778  pop     rsi
0x18008b779  pop     rbp
0x18008b77a  retn
```
