# NlWaitForService(ushort *,ulong,uchar)

- ea: `0x180078fd8`
- end: `0x1800792cd`
- name: `?NlWaitForService@@YAJPEAGKE@Z`
- size: `757`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int, unsigned __int8)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180045570`
- `0x18004a450`
- `0x18004b258`
- `0x180075570`

## callees

- `0x180007518`
- `0x18000e910`
- `0x18000f3e4`
- `0x180029c68`
- `0x180078fd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800791d6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800791d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007903e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007908b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800790cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007912e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007903e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007908b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800790cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007912e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079246`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800790f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800790f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800792a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800792a2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18007902a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18007902a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180079077`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180079077`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007927a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007928e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007927a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007928e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800790b7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18007911e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800790b7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18007911e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180079173`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180079173`

## string_xrefs

- `0x18007904d`: `NlWaitForService: %ws: OpenSCManager failed: %lu\n`
- `0x18007909a`: `NlWaitForService: %ws: OpenService failed: %lu\n`
- `0x1800790e1`: `NlWaitForService: %ws: QueryServiceConfig failed: %lu\n`
- `0x18007913d`: `NlWaitForService: %ws: QueryServiceConfig failed again: %lu\n`
- `0x18007925e`: `NlWaitForService: %ws Service start type invalid: %lu\n`
- `0x180079255`: `NlWaitForService: %ws: QueryServiceStatus failed: %lu\n`
- `0x180079212`: `NlWaitForService: %ws: service couldn't start: %lu %lx\n`
- `0x180079230`: `         Service specific error code: %lu %lx\n`
- `0x18007919d`: `NlWaitForService: %ws: Invalid service state: %lu\n`
- `0x1800791b9`: `NlWaitForService: %ws: wait for service to start\n`

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
0x180078fd8  push    rbp
0x180078fda  push    rbx
0x180078fdb  push    rsi
0x180078fdc  push    rdi
0x180078fdd  push    r14
0x180078fdf  push    r15
0x180078fe1  lea     rbp, [rsp-2Fh]
0x180078fe6  sub     rsp, 0B8h
0x180078fed  mov     rax, cs:__security_cookie
0x180078ff4  xor     rax, rsp
0x180078ff7  mov     [rbp+57h+var_40], rax
0x180078ffb  xorps   xmm0, xmm0
0x180078ffe  mov     r14d, edx
0x180079001  xor     edx, edx; Val
0x180079003  mov     rbx, rcx
0x180079006  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x18007900a  lea     rcx, [rbp+57h+ServiceConfig]; void *
0x18007900e  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x180079012  lea     r8d, [rdx+40h]; Size
0x180079016  call    memset_0
0x18007901b  xor     edx, edx; lpDatabaseName
0x18007901d  mov     [rbp+57h+pcbBytesNeeded], 0
0x180079024  xor     ecx, ecx; lpMachineName
0x180079026  lea     r8d, [rdx+1]; dwDesiredAccess
0x18007902a  call    cs:__imp_OpenSCManagerW
0x180079031  nop     dword ptr [rax+rax+00h]
0x180079036  mov     r15, rax
0x180079039  test    rax, rax
0x18007903c  jnz     short loc_18007906B
0x18007903e  call    cs:__imp_GetLastError
0x180079045  nop     dword ptr [rax+rax+00h]
0x18007904a  mov     r8, rbx
0x18007904d  lea     rdx, aNlwaitforservi_0; "NlWaitForService: %ws: OpenSCManager fa"...
0x180079054  mov     r9d, eax
0x180079057  mov     ecx, 100h; unsigned int
0x18007905c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180079061  mov     ebx, 102h
0x180079066  jmp     loc_1800792AE
0x18007906b  xor     edi, edi
0x18007906d  mov     rdx, rbx; lpServiceName
0x180079070  mov     rcx, r15; hSCManager
0x180079073  lea     r8d, [rdi+5]; dwDesiredAccess
0x180079077  call    cs:__imp_OpenServiceW
0x18007907e  nop     dword ptr [rax+rax+00h]
0x180079083  mov     rsi, rax
0x180079086  test    rax, rax
0x180079089  jnz     short loc_1800790A6
0x18007908b  call    cs:__imp_GetLastError
0x180079092  nop     dword ptr [rax+rax+00h]
0x180079097  mov     r9d, eax
0x18007909a  lea     rdx, aNlwaitforservi_3; "NlWaitForService: %ws: OpenService fail"...
0x1800790a1  jmp     loc_180079265
0x1800790a6  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x1800790aa  mov     r8d, 40h ; '@'; cbBufSize
0x1800790b0  lea     rdx, [rbp+57h+ServiceConfig]; lpServiceConfig
0x1800790b4  mov     rcx, rsi; hService
0x1800790b7  call    cs:__imp_QueryServiceConfigW
0x1800790be  nop     dword ptr [rax+rax+00h]
0x1800790c3  test    eax, eax
0x1800790c5  jz      short loc_1800790CD
0x1800790c7  lea     rax, [rbp+57h+ServiceConfig]
0x1800790cb  jmp     short loc_18007914C
0x1800790cd  call    cs:__imp_GetLastError
0x1800790d4  nop     dword ptr [rax+rax+00h]
0x1800790d9  cmp     eax, 7Ah ; 'z'
0x1800790dc  jz      short loc_1800790ED
0x1800790de  mov     r9d, eax
0x1800790e1  lea     rdx, aNlwaitforservi_7; "NlWaitForService: %ws: QueryServiceConf"...
0x1800790e8  jmp     loc_180079265
0x1800790ed  mov     edx, [rbp+57h+pcbBytesNeeded]; uBytes
0x1800790f0  xor     ecx, ecx; uFlags
0x1800790f2  call    cs:__imp_LocalAlloc
0x1800790f9  nop     dword ptr [rax+rax+00h]
0x1800790fe  mov     rdi, rax
0x180079101  test    rax, rax
0x180079104  jnz     short loc_180079110
0x180079106  mov     ebx, 0C0000017h
0x18007910b  jmp     loc_180079277
0x180079110  mov     r8d, [rbp+57h+pcbBytesNeeded]; cbBufSize
0x180079114  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x180079118  mov     rdx, rdi; lpServiceConfig
0x18007911b  mov     rcx, rsi; hService
0x18007911e  call    cs:__imp_QueryServiceConfigW
0x180079125  nop     dword ptr [rax+rax+00h]
0x18007912a  test    eax, eax
0x18007912c  jnz     short loc_180079149
0x18007912e  call    cs:__imp_GetLastError
0x180079135  nop     dword ptr [rax+rax+00h]
0x18007913a  mov     r9d, eax
0x18007913d  lea     rdx, aNlwaitforservi_6; "NlWaitForService: %ws: QueryServiceConf"...
0x180079144  jmp     loc_180079265
0x180079149  mov     rax, rdi
0x18007914c  mov     r9d, [rax+4]
0x180079150  cmp     r9d, 2
0x180079154  jnz     loc_18007925E
0x18007915a  lea     ecx, [r14+5]
0x18007915e  mov     eax, 0CCCCCCCDh
0x180079163  mul     ecx
0x180079165  mov     r14d, edx
0x180079168  shr     r14d, 2
0x18007916c  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180079170  mov     rcx, rsi; hService
0x180079173  call    cs:__imp_QueryServiceStatus
0x18007917a  nop     dword ptr [rax+rax+00h]
0x18007917f  test    eax, eax
0x180079181  jz      loc_180079246
0x180079187  mov     r9d, [rbp+57h+ServiceStatus.dwCurrentState]
0x18007918b  mov     eax, r9d
0x18007918e  sub     eax, 1
0x180079191  jz      short loc_1800791A9
0x180079193  sub     eax, 1
0x180079196  jz      short loc_1800791B6
0x180079198  cmp     eax, 2
0x18007919b  jz      short loc_180079206
0x18007919d  lea     rdx, aNlwaitforservi_4; "NlWaitForService: %ws: Invalid service "...
0x1800791a4  jmp     loc_180079265
0x1800791a9  mov     r9d, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x1800791ad  cmp     r9d, 435h
0x1800791b4  jnz     short loc_18007920A
0x1800791b6  mov     r8, rbx
0x1800791b9  lea     rdx, aNlwaitforservi_5; "NlWaitForService: %ws: wait for service"...
0x1800791c0  mov     ecx, 1; unsigned int
0x1800791c5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800791ca  mov     rcx, cs:?NlGlobalTerminateEvent@@3PEAXEA; hHandle
0x1800791d1  mov     edx, 1388h; dwMilliseconds
0x1800791d6  call    cs:__imp_WaitForSingleObject
0x1800791dd  nop     dword ptr [rax+rax+00h]
0x1800791e2  cmp     cs:?NlGlobalTerminate@@3HA, 0; int NlGlobalTerminate
0x1800791e9  jnz     loc_180079272
0x1800791ef  xor     ecx, ecx; int
0x1800791f1  call    ?GiveInstallHints@@YAHH@Z; GiveInstallHints(int)
0x1800791f6  test    eax, eax
0x1800791f8  jz      short loc_180079272
0x1800791fa  add     r14d, 0FFFFFFFFh
0x1800791fe  jnz     loc_18007916C
0x180079204  jmp     short loc_180079272
0x180079206  xor     ebx, ebx
0x180079208  jmp     short loc_180079277
0x18007920a  mov     r8, rbx
0x18007920d  mov     [rsp+0E0h+var_C0], r9d
0x180079212  lea     rdx, aNlwaitforservi_1; "NlWaitForService: %ws: service couldn't"...
0x180079219  mov     ecx, 100h; unsigned int
0x18007921e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180079223  cmp     [rbp+57h+ServiceStatus.dwWin32ExitCode], 42Ah
0x18007922a  jnz     short loc_180079272
0x18007922c  mov     r8d, [rbp+57h+ServiceStatus.dwServiceSpecificExitCode]
0x180079230  lea     rdx, aServiceSpecifi; "         Service specific error code: %"...
0x180079237  mov     r9d, r8d
0x18007923a  mov     ecx, 100h; unsigned int
0x18007923f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180079244  jmp     short loc_180079272
0x180079246  call    cs:__imp_GetLastError
0x18007924d  nop     dword ptr [rax+rax+00h]
0x180079252  mov     r9d, eax
0x180079255  lea     rdx, aNlwaitforservi_2; "NlWaitForService: %ws: QueryServiceStat"...
0x18007925c  jmp     short loc_180079265
0x18007925e  lea     rdx, aNlwaitforservi; "NlWaitForService: %ws Service start typ"...
0x180079265  mov     r8, rbx
0x180079268  mov     ecx, 100h; unsigned int
0x18007926d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180079272  mov     ebx, 102h
0x180079277  mov     rcx, r15; hSCObject
0x18007927a  call    cs:__imp_CloseServiceHandle
0x180079281  nop     dword ptr [rax+rax+00h]
0x180079286  test    rsi, rsi
0x180079289  jz      short loc_18007929A
0x18007928b  mov     rcx, rsi; hSCObject
0x18007928e  call    cs:__imp_CloseServiceHandle
0x180079295  nop     dword ptr [rax+rax+00h]
0x18007929a  test    rdi, rdi
0x18007929d  jz      short loc_1800792AE
0x18007929f  mov     rcx, rdi; hMem
0x1800792a2  call    cs:__imp_LocalFree
0x1800792a9  nop     dword ptr [rax+rax+00h]
0x1800792ae  mov     eax, ebx
0x1800792b0  mov     rcx, [rbp+57h+var_40]
0x1800792b4  xor     rcx, rsp; StackCookie
0x1800792b7  call    __security_check_cookie
0x1800792bc  add     rsp, 0B8h
0x1800792c3  pop     r15
0x1800792c5  pop     r14
0x1800792c7  pop     rdi
0x1800792c8  pop     rsi
0x1800792c9  pop     rbx
0x1800792ca  pop     rbp
0x1800792cb  retn
```
