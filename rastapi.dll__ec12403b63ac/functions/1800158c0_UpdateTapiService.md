# UpdateTapiService

- ea: `0x1800158c0`
- end: `0x180015a8b`
- name: `UpdateTapiService`
- size: `459`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800033d0`
- `0x18000d92c`
- `0x180012340`
- `0x180015280`
- `0x180015768`
- `0x1800158c0`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a66`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015a5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015a5c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800159cc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800159cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800159d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800159e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800159d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800159e2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x1800159a4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x1800159a4`

## string_xrefs

- `0x1800158f0`: `rundll32.exe streamci,StreamingDeviceSetup {eeab7790-c514-11d1-b42b-00805fc1270e},asyncmac,{ad498944-762f-11d0-8dcb-00c04fc3358c}`
- `0x1800159b6`: `UpdateTapiService: CreateProcess failed with error 0x%x`
- `0x180015a14`: `UpdateTapiService: StartTapiService failed (0x%x)`
- `0x180015a47`: `UpdateTapiService: GetPortsFromTapi failed (0x%x)`

## pseudocode

```c
__int64 UpdateTapiService()
{
  unsigned int LastError; // ebx
  const CHAR *v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOA StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  CHAR CommandLine[144]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  strcpy(
    CommandLine,
    "rundll32.exe streamci,StreamingDeviceSetup {eeab7790-c514-11d1-b42b-00805fc1270e},asyncmac,{ad498944-762f-11d0-8dcb-00c04fc3358c}");
  if ( !CreateProcessA(0, CommandLine, 0, 0, 0, 0x28u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    LastError = GetLastError();
    v1 = "UpdateTapiService: CreateProcess failed with error 0x%x";
LABEL_10:
    RasTapiTrace(v1);
    goto LABEL_11;
  }
  LastError = 0;
  WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  GetMutex(v3, v2, v4, v5);
  if ( g_fTapiSrvRunning )
    goto LABEL_11;
  g_fTapiSrvRunning = 1;
  LastError = StartTapiService();
  if ( LastError )
  {
    g_fTapiSrvRunning = 0;
    v1 = "UpdateTapiService: StartTapiService failed (0x%x)";
    goto LABEL_10;
  }
  UpdateRasmanDependency(1);
  if ( !TapiThreadId && !RasLine && (unsigned int)GetPortsFromTapi(1) )
  {
    v1 = "UpdateTapiService: GetPortsFromTapi failed (0x%x)";
    goto LABEL_10;
  }
LABEL_11:
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  return LastError;
}

```

## disassembly

```asm
0x1800158c0  mov     [rsp-8+arg_0], rbx
0x1800158c5  push    rbp
0x1800158c6  lea     rbp, [rsp-80h]
0x1800158cb  sub     rsp, 180h
0x1800158d2  mov     rax, cs:__security_cookie
0x1800158d9  xor     rax, rsp
0x1800158dc  mov     [rbp+80h+var_10], rax
0x1800158e0  xor     edx, edx; Val
0x1800158e2  lea     rcx, [rsp+180h+StartupInfo]; void *
0x1800158e7  lea     r8d, [rdx+68h]; Size
0x1800158eb  call    memset_0
0x1800158f0  movaps  xmm1, xmmword ptr cs:aRundll32ExeStr; "rundll32.exe streamci,StreamingDeviceSe"...
0x1800158f7  lea     rdx, [rbp+80h+CommandLine]; lpCommandLine
0x1800158fb  xorps   xmm0, xmm0
0x1800158fe  xor     eax, eax
0x180015900  movups  xmmword ptr [rsp+180h+ProcessInformation.hProcess], xmm0
0x180015905  xor     r9d, r9d; lpThreadAttributes
0x180015908  mov     qword ptr [rsp+180h+ProcessInformation.dwProcessId], rax
0x18001590d  movaps  xmm0, xmmword ptr cs:aRundll32ExeStr+10h; "eamci,StreamingDeviceSetup {eeab7790-c5"...
0x180015914  xor     r8d, r8d; lpProcessAttributes
0x180015917  movzx   eax, word ptr cs:aRundll32ExeStr+80h; "}"
0x18001591e  xor     ecx, ecx; lpApplicationName
0x180015920  movups  xmmword ptr [rbp+80h+CommandLine], xmm1
0x180015924  mov     [rbp+80h+var_20], ax
0x180015928  lea     rax, [rsp+180h+ProcessInformation]
0x18001592d  movaps  xmm1, xmmword ptr cs:aRundll32ExeStr+20h; "eviceSetup {eeab7790-c514-11d1-b42b-008"...
0x180015934  mov     [rsp+180h+lpProcessInformation], rax; lpProcessInformation
0x180015939  lea     rax, [rsp+180h+StartupInfo]
0x18001593e  mov     [rsp+180h+lpStartupInfo], rax; lpStartupInfo
0x180015943  movups  [rbp+80h+var_90], xmm0
0x180015947  mov     [rsp+180h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180015950  movaps  xmm0, xmmword ptr cs:aRundll32ExeStr+30h; "7790-c514-11d1-b42b-00805fc1270e},async"...
0x180015957  movups  [rbp+80h+var_80], xmm1
0x18001595b  mov     [rsp+180h+lpEnvironment], 0; lpEnvironment
0x180015964  movaps  xmm1, xmmword ptr cs:aRundll32ExeStr+40h; "42b-00805fc1270e},asyncmac,{ad498944-76"...
0x18001596b  movups  [rbp+80h+var_70], xmm0
0x18001596f  mov     [rsp+180h+dwCreationFlags], 28h ; '('; dwCreationFlags
0x180015977  movaps  xmm0, xmmword ptr cs:aRundll32ExeStr+50h; "},asyncmac,{ad498944-762f-11d0-8dcb-00c"...
0x18001597e  movups  [rbp+80h+var_60], xmm1
0x180015982  mov     [rsp+180h+bInheritHandles], 0; bInheritHandles
0x18001598a  movaps  xmm1, xmmword ptr cs:aRundll32ExeStr+60h; "8944-762f-11d0-8dcb-00c04fc3358c}"
0x180015991  movups  [rbp+80h+var_50], xmm0
0x180015995  movaps  xmm0, xmmword ptr cs:aRundll32ExeStr+70h; "dcb-00c04fc3358c}"
0x18001599c  movups  [rbp+80h+var_40], xmm1
0x1800159a0  movups  [rbp+80h+var_30], xmm0
0x1800159a4  call    cs:__imp_CreateProcessA
0x1800159aa  test    eax, eax
0x1800159ac  jnz     short loc_1800159C2
0x1800159ae  call    cs:__imp_GetLastError
0x1800159b4  mov     ebx, eax
0x1800159b6  lea     rcx, aUpdatetapiserv_2; "UpdateTapiService: CreateProcess failed"...
0x1800159bd  jmp     loc_180015A4E
0x1800159c2  mov     rcx, [rsp+180h+ProcessInformation.hProcess]; hHandle
0x1800159c7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800159ca  xor     ebx, ebx
0x1800159cc  call    cs:__imp_WaitForSingleObject
0x1800159d2  mov     rcx, [rsp+180h+ProcessInformation.hProcess]; hObject
0x1800159d7  call    cs:__imp_CloseHandle
0x1800159dd  mov     rcx, [rsp+180h+ProcessInformation.hThread]; hObject
0x1800159e2  call    cs:__imp_CloseHandle
0x1800159e8  call    GetMutex
0x1800159ed  cmp     cs:g_fTapiSrvRunning, ebx
0x1800159f3  jnz     short loc_180015A55
0x1800159f5  mov     cs:g_fTapiSrvRunning, 1
0x1800159ff  call    StartTapiService
0x180015a04  mov     ebx, eax
0x180015a06  test    eax, eax
0x180015a08  jz      short loc_180015A1D
0x180015a0a  mov     cs:g_fTapiSrvRunning, 0
0x180015a14  lea     rcx, aUpdatetapiserv_0; "UpdateTapiService: StartTapiService fai"...
0x180015a1b  jmp     short loc_180015A4E
0x180015a1d  mov     ecx, 1
0x180015a22  call    UpdateRasmanDependency
0x180015a27  cmp     cs:TapiThreadId, 0
0x180015a2e  jnz     short loc_180015A55
0x180015a30  cmp     cs:RasLine, 0
0x180015a37  jnz     short loc_180015A55
0x180015a39  mov     ecx, 1
0x180015a3e  call    GetPortsFromTapi
0x180015a43  test    eax, eax
0x180015a45  jz      short loc_180015A55
0x180015a47  lea     rcx, aUpdatetapiserv_1; "UpdateTapiService: GetPortsFromTapi fai"...
0x180015a4e  mov     edx, eax
0x180015a50  call    RasTapiTrace
0x180015a55  mov     rcx, cs:RasTapiMutex; hMutex
0x180015a5c  call    cs:__imp_ReleaseMutex
0x180015a62  test    eax, eax
0x180015a64  jnz     short loc_180015A6C
0x180015a66  call    cs:__imp_GetLastError
0x180015a6c  mov     eax, ebx
0x180015a6e  mov     rcx, [rbp+80h+var_10]
0x180015a72  xor     rcx, rsp; StackCookie
0x180015a75  call    __security_check_cookie
0x180015a7a  mov     rbx, [rsp+180h+arg_0]
0x180015a82  add     rsp, 180h
0x180015a89  pop     rbp
0x180015a8a  retn
```
