# NlWaitForService(ushort *,ulong,uchar)

- ea: `0x1800738d0`
- end: `0x180073b66`
- name: `?NlWaitForService@@YAJPEAGKE@Z`
- size: `662`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int, unsigned __int8)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18004284c`
- `0x1800472e8`
- `0x180048078`
- `0x180070110`

## callees

- `0x180007278`
- `0x18000e270`
- `0x18000ed34`
- `0x180028750`
- `0x1800738d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180073a92`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180073a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800739a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800739f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800739a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800739f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073af8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800739c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800739c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073b42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073b42`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180073922`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180073922`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180073963`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180073963`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180073b26`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180073b34`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180073b26`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180073b34`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180073997`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800739ec`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180073997`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800739ec`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180073a35`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180073a35`

## string_xrefs

- `0x180073939`: `NlWaitForService: %ws: OpenSCManager failed: %lu\n`
- `0x18007397a`: `NlWaitForService: %ws: OpenService failed: %lu\n`
- `0x1800739b5`: `NlWaitForService: %ws: QueryServiceConfig failed: %lu\n`
- `0x1800739ff`: `NlWaitForService: %ws: QueryServiceConfig failed again: %lu\n`
- `0x180073b0a`: `NlWaitForService: %ws Service start type invalid: %lu\n`
- `0x180073b01`: `NlWaitForService: %ws: QueryServiceStatus failed: %lu\n`
- `0x180073ac4`: `NlWaitForService: %ws: service couldn't start: %lu %lx\n`
- `0x180073ae2`: `         Service specific error code: %lu %lx\n`
- `0x180073a59`: `NlWaitForService: %ws: Invalid service state: %lu\n`
- `0x180073a75`: `NlWaitForService: %ws: wait for service to start\n`

## pseudocode

```c
__int64 __fastcall NlWaitForService(LPCWSTR lpServiceName, int a2)
{
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // r15
  DWORD LastError; // eax
  unsigned int v7; // ebx
  _QUERY_SERVICE_CONFIGW *v8; // rdi
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rsi
  __int64 v11; // r9
  _QUERY_SERVICE_CONFIGW *p_ServiceConfig; // rax
  DWORD v13; // eax
  struct _QUERY_SERVICE_CONFIGW *v14; // rax
  __int64 v15; // r9
  __int64 dwStartType; // r9
  unsigned int v17; // r14d
  __int64 v18; // r9
  DWORD pcbBytesNeeded[4]; // [rsp+30h] [rbp-59h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+40h] [rbp-49h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+80h] [rbp-9h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  memset_0(&ServiceConfig, 0, sizeof(ServiceConfig));
  pcbBytesNeeded[0] = 0;
  v4 = OpenSCManagerW(0, 0, 1u);
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    NlPrintRoutine(0x100u, L"NlWaitForService: %ws: OpenSCManager failed: %lu\n", lpServiceName, LastError);
    return 258;
  }
  v8 = 0;
  v9 = OpenServiceW(v4, lpServiceName, 5u);
  v10 = v9;
  if ( !v9 )
  {
    v11 = GetLastError();
    NlPrintRoutine(0x100u, L"NlWaitForService: %ws: OpenService failed: %lu\n", lpServiceName, v11);
LABEL_31:
    v7 = 258;
    goto LABEL_32;
  }
  if ( QueryServiceConfigW(v9, &ServiceConfig, 0x40u, pcbBytesNeeded) )
  {
    p_ServiceConfig = &ServiceConfig;
  }
  else
  {
    v13 = GetLastError();
    if ( v13 != 122 )
    {
      NlPrintRoutine(0x100u, L"NlWaitForService: %ws: QueryServiceConfig failed: %lu\n", lpServiceName, v13);
      goto LABEL_31;
    }
    v14 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0, pcbBytesNeeded[0]);
    v8 = v14;
    if ( !v14 )
    {
      v7 = -1073741801;
      goto LABEL_32;
    }
    if ( !QueryServiceConfigW(v10, v14, pcbBytesNeeded[0], pcbBytesNeeded) )
    {
      v15 = GetLastError();
      NlPrintRoutine(0x100u, L"NlWaitForService: %ws: QueryServiceConfig failed again: %lu\n", lpServiceName, v15);
      goto LABEL_31;
    }
    p_ServiceConfig = v8;
  }
  dwStartType = p_ServiceConfig->dwStartType;
  if ( (_DWORD)dwStartType != 2 )
  {
    NlPrintRoutine(0x100u, L"NlWaitForService: %ws Service start type invalid: %lu\n", lpServiceName, dwStartType);
    goto LABEL_31;
  }
  v17 = (a2 + 5) / 5u;
  while ( 1 )
  {
    if ( !QueryServiceStatus(v10, &ServiceStatus) )
    {
      v18 = GetLastError();
      NlPrintRoutine(0x100u, L"NlWaitForService: %ws: QueryServiceStatus failed: %lu\n", lpServiceName, v18);
      goto LABEL_31;
    }
    if ( ServiceStatus.dwCurrentState != 1 )
      break;
    if ( ServiceStatus.dwWin32ExitCode != 1077 )
    {
      NlPrintRoutine(0x100u, L"NlWaitForService: %ws: service couldn't start: %lu %lx\n", lpServiceName);
      if ( ServiceStatus.dwWin32ExitCode == 1066 )
        NlPrintRoutine(
          0x100u,
          L"         Service specific error code: %lu %lx\n",
          ServiceStatus.dwServiceSpecificExitCode,
          ServiceStatus.dwServiceSpecificExitCode);
      goto LABEL_31;
    }
LABEL_22:
    NlPrintRoutine(1u, L"NlWaitForService: %ws: wait for service to start\n", lpServiceName);
    WaitForSingleObject(NlGlobalTerminateEvent, 0x1388u);
    if ( !NlGlobalTerminate )
    {
      if ( (unsigned int)GiveInstallHints(0) )
      {
        if ( --v17 )
          continue;
      }
    }
    goto LABEL_31;
  }
  if ( ServiceStatus.dwCurrentState == 2 )
    goto LABEL_22;
  if ( ServiceStatus.dwCurrentState != 4 )
  {
    NlPrintRoutine(
      0x100u,
      L"NlWaitForService: %ws: Invalid service state: %lu\n",
      lpServiceName,
      ServiceStatus.dwCurrentState);
    goto LABEL_31;
  }
  v7 = 0;
LABEL_32:
  CloseServiceHandle(v5);
  if ( v10 )
    CloseServiceHandle(v10);
  if ( v8 )
    LocalFree(v8);
  return v7;
}

```

## disassembly

```asm
0x1800738d0  push    rbp
0x1800738d2  push    rbx
0x1800738d3  push    rsi
0x1800738d4  push    rdi
0x1800738d5  push    r14
0x1800738d7  push    r15
0x1800738d9  lea     rbp, [rsp-2Fh]
0x1800738de  sub     rsp, 0B8h
0x1800738e5  mov     rax, cs:__security_cookie
0x1800738ec  xor     rax, rsp
0x1800738ef  mov     [rbp+57h+var_40], rax
0x1800738f3  xorps   xmm0, xmm0
0x1800738f6  mov     r14d, edx
0x1800738f9  xor     edx, edx; Val
0x1800738fb  mov     rbx, rcx
0x1800738fe  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180073902  lea     rcx, [rbp+57h+ServiceConfig]; void *
0x180073906  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x18007390a  lea     r8d, [rdx+40h]; Size
0x18007390e  call    memset_0
0x180073913  xor     edx, edx; lpDatabaseName
0x180073915  mov     [rbp+57h+pcbBytesNeeded], 0
0x18007391c  xor     ecx, ecx; lpMachineName
0x18007391e  lea     r8d, [rdx+1]; dwDesiredAccess
0x180073922  call    cs:__imp_OpenSCManagerW
0x180073928  mov     r15, rax
0x18007392b  test    rax, rax
0x18007392e  jnz     short loc_180073957
0x180073930  call    cs:__imp_GetLastError
0x180073936  mov     r8, rbx
0x180073939  lea     rdx, aNlwaitforservi_0; "NlWaitForService: %ws: OpenSCManager fa"...
0x180073940  mov     r9d, eax
0x180073943  mov     ecx, 100h; unsigned int
0x180073948  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007394d  mov     ebx, 102h
0x180073952  jmp     loc_180073B48
0x180073957  xor     edi, edi
0x180073959  mov     rdx, rbx; lpServiceName
0x18007395c  mov     rcx, r15; hSCManager
0x18007395f  lea     r8d, [rdi+5]; dwDesiredAccess
0x180073963  call    cs:__imp_OpenServiceW
0x180073969  mov     rsi, rax
0x18007396c  test    rax, rax
0x18007396f  jnz     short loc_180073986
0x180073971  call    cs:__imp_GetLastError
0x180073977  mov     r9d, eax
0x18007397a  lea     rdx, aNlwaitforservi_3; "NlWaitForService: %ws: OpenService fail"...
0x180073981  jmp     loc_180073B11
0x180073986  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x18007398a  mov     r8d, 40h ; '@'; cbBufSize
0x180073990  lea     rdx, [rbp+57h+ServiceConfig]; lpServiceConfig
0x180073994  mov     rcx, rsi; hService
0x180073997  call    cs:__imp_QueryServiceConfigW
0x18007399d  test    eax, eax
0x18007399f  jz      short loc_1800739A7
0x1800739a1  lea     rax, [rbp+57h+ServiceConfig]
0x1800739a5  jmp     short loc_180073A0E
0x1800739a7  call    cs:__imp_GetLastError
0x1800739ad  cmp     eax, 7Ah ; 'z'
0x1800739b0  jz      short loc_1800739C1
0x1800739b2  mov     r9d, eax
0x1800739b5  lea     rdx, aNlwaitforservi_7; "NlWaitForService: %ws: QueryServiceConf"...
0x1800739bc  jmp     loc_180073B11
0x1800739c1  mov     edx, [rbp+57h+pcbBytesNeeded]; uBytes
0x1800739c4  xor     ecx, ecx; uFlags
0x1800739c6  call    cs:__imp_LocalAlloc
0x1800739cc  mov     rdi, rax
0x1800739cf  test    rax, rax
0x1800739d2  jnz     short loc_1800739DE
0x1800739d4  mov     ebx, 0C0000017h
0x1800739d9  jmp     loc_180073B23
0x1800739de  mov     r8d, [rbp+57h+pcbBytesNeeded]; cbBufSize
0x1800739e2  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x1800739e6  mov     rdx, rdi; lpServiceConfig
0x1800739e9  mov     rcx, rsi; hService
0x1800739ec  call    cs:__imp_QueryServiceConfigW
0x1800739f2  test    eax, eax
0x1800739f4  jnz     short loc_180073A0B
0x1800739f6  call    cs:__imp_GetLastError
0x1800739fc  mov     r9d, eax
0x1800739ff  lea     rdx, aNlwaitforservi_6; "NlWaitForService: %ws: QueryServiceConf"...
0x180073a06  jmp     loc_180073B11
0x180073a0b  mov     rax, rdi
0x180073a0e  mov     r9d, [rax+4]
0x180073a12  cmp     r9d, 2
0x180073a16  jnz     loc_180073B0A
0x180073a1c  lea     ecx, [r14+5]
0x180073a20  mov     eax, 0CCCCCCCDh
0x180073a25  mul     ecx
0x180073a27  mov     r14d, edx
0x180073a2a  shr     r14d, 2
0x180073a2e  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180073a32  mov     rcx, rsi; hService
0x180073a35  call    cs:__imp_QueryServiceStatus
0x180073a3b  test    eax, eax
0x180073a3d  jz      loc_180073AF8
0x180073a43  mov     r9d, [rbp+57h+ServiceStatus.dwCurrentState]
0x180073a47  mov     eax, r9d
0x180073a4a  sub     eax, 1
0x180073a4d  jz      short loc_180073A65
0x180073a4f  sub     eax, 1
0x180073a52  jz      short loc_180073A72
0x180073a54  cmp     eax, 2
0x180073a57  jz      short loc_180073AB8
0x180073a59  lea     rdx, aNlwaitforservi_4; "NlWaitForService: %ws: Invalid service "...
0x180073a60  jmp     loc_180073B11
0x180073a65  mov     r9d, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x180073a69  cmp     r9d, 435h
0x180073a70  jnz     short loc_180073ABC
0x180073a72  mov     r8, rbx
0x180073a75  lea     rdx, aNlwaitforservi_5; "NlWaitForService: %ws: wait for service"...
0x180073a7c  mov     ecx, 1; unsigned int
0x180073a81  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180073a86  mov     rcx, cs:?NlGlobalTerminateEvent@@3PEAXEA; hHandle
0x180073a8d  mov     edx, 1388h; dwMilliseconds
0x180073a92  call    cs:__imp_WaitForSingleObject
0x180073a98  cmp     cs:?NlGlobalTerminate@@3HA, 0; int NlGlobalTerminate
0x180073a9f  jnz     short loc_180073B1E
0x180073aa1  xor     ecx, ecx; int
0x180073aa3  call    ?GiveInstallHints@@YAHH@Z; GiveInstallHints(int)
0x180073aa8  test    eax, eax
0x180073aaa  jz      short loc_180073B1E
0x180073aac  add     r14d, 0FFFFFFFFh
0x180073ab0  jnz     loc_180073A2E
0x180073ab6  jmp     short loc_180073B1E
0x180073ab8  xor     ebx, ebx
0x180073aba  jmp     short loc_180073B23
0x180073abc  mov     r8, rbx
0x180073abf  mov     [rsp+0E0h+var_C0], r9d
0x180073ac4  lea     rdx, aNlwaitforservi_1; "NlWaitForService: %ws: service couldn't"...
0x180073acb  mov     ecx, 100h; unsigned int
0x180073ad0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180073ad5  cmp     [rbp+57h+ServiceStatus.dwWin32ExitCode], 42Ah
0x180073adc  jnz     short loc_180073B1E
0x180073ade  mov     r8d, [rbp+57h+ServiceStatus.dwServiceSpecificExitCode]
0x180073ae2  lea     rdx, aServiceSpecifi; "         Service specific error code: %"...
0x180073ae9  mov     r9d, r8d
0x180073aec  mov     ecx, 100h; unsigned int
0x180073af1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180073af6  jmp     short loc_180073B1E
0x180073af8  call    cs:__imp_GetLastError
0x180073afe  mov     r9d, eax
0x180073b01  lea     rdx, aNlwaitforservi_2; "NlWaitForService: %ws: QueryServiceStat"...
0x180073b08  jmp     short loc_180073B11
0x180073b0a  lea     rdx, aNlwaitforservi; "NlWaitForService: %ws Service start typ"...
0x180073b11  mov     r8, rbx
0x180073b14  mov     ecx, 100h; unsigned int
0x180073b19  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180073b1e  mov     ebx, 102h
0x180073b23  mov     rcx, r15; hSCObject
0x180073b26  call    cs:__imp_CloseServiceHandle
0x180073b2c  test    rsi, rsi
0x180073b2f  jz      short loc_180073B3A
0x180073b31  mov     rcx, rsi; hSCObject
0x180073b34  call    cs:__imp_CloseServiceHandle
0x180073b3a  test    rdi, rdi
0x180073b3d  jz      short loc_180073B48
0x180073b3f  mov     rcx, rdi; hMem
0x180073b42  call    cs:__imp_LocalFree
0x180073b48  mov     eax, ebx
0x180073b4a  mov     rcx, [rbp+57h+var_40]
0x180073b4e  xor     rcx, rsp; StackCookie
0x180073b51  call    __security_check_cookie
0x180073b56  add     rsp, 0B8h
0x180073b5d  pop     r15
0x180073b5f  pop     r14
0x180073b61  pop     rdi
0x180073b62  pop     rsi
0x180073b63  pop     rbx
0x180073b64  pop     rbp
0x180073b65  retn
```
