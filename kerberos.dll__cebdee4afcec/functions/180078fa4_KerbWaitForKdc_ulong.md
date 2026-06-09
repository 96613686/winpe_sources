# KerbWaitForKdc(ulong)

- ea: `0x180078fa4`
- end: `0x180079330`
- name: `?KerbWaitForKdc@@YAJK@Z`
- size: `908`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025680`
- `0x180037ea8`
- `0x1800389b8`

## callees

- `0x180007e80`
- `0x180070680`
- `0x18007108c`
- `0x180078eb0`
- `0x180078fa4`
- `0x18008b70c`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800790d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800791a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800790d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800791a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079242`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180079074`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180079074`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180079025`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180079025`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007926e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007927c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007926e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007927c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800790c0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18007919a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800790c0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18007919a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800791ca`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180079238`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800791ca`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180079238`

## string_xrefs

- `0x180078ffc`: `\Security\KdcStartEvent`
- `0x180079219`: `\Security\KdcStartEvent`
- `0x18007903a`: ` KerbWaitForKdc: OpenSCManager failed: %lu`
- `0x180079088`: `KerbWaitForKdc: OpenService failed: %lu`
- `0x1800790de`: `KerbWaitForKdc: QueryServiceConfig failed: %lu`
- `0x1800791aa`: `KerbWaitForKdc: QueryServiceConfig failed again: %lu`
- `0x18007924c`: `KerbWaitForKdc: QueryServiceStatus failed: %lu`
- `0x1800792d7`: `KerbWaitForKdc: KDC service couldn't start: %lu %lx`
- `0x180079307`: `         Service specific error code: %lu %lx`
- `0x1800791f3`: `KerbWaitForKdc: Invalid service state: %lu`

## pseudocode

```c
__int64 __fastcall KerbWaitForKdc()
{
  unsigned int v0; // r13d
  __int64 result; // rax
  int v2; // ebx
  SC_HANDLE v3; // rax
  DWORD LastError; // eax
  struct _QUERY_SERVICE_CONFIGW *p_pcbBytesNeeded; // rdi
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // r15
  DWORD v8; // eax
  const char *v9; // r9
  __int64 v10; // r8
  _QUERY_SERVICE_CONFIGW *p_ServiceConfig; // rax
  unsigned __int64 v12; // rsi
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  _DWORD *v17; // rax
  DWORD dwStartType; // r12d
  BOOL i; // eax
  __int64 v20; // [rsp+0h] [rbp-30h] BYREF
  __int64 v21; // [rsp+20h] [rbp-10h]
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp+0h] BYREF
  SC_HANDLE hSCObject[3]; // [rsp+38h] [rbp+8h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+50h] [rbp+20h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+90h] [rbp+60h] BYREF

  v0 = KerbGlobalKdcWaitTime;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  memset_0(&ServiceConfig, 0, sizeof(ServiceConfig));
  pcbBytesNeeded = 0;
  result = KerbWaitForEvent(L"\\Security\\KdcStartEvent", 0);
  v2 = result;
  if ( (int)result >= 0 )
  {
    KerbKdcStarted = 1;
    return result;
  }
  v3 = OpenSCManagerW(0, 0, 1u);
  hSCObject[0] = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    KerbTracerT::Log(1, "KerbWaitForKdc", 478, " KerbWaitForKdc: OpenSCManager failed: %lu", LastError);
    return (unsigned int)-1073741422;
  }
  p_pcbBytesNeeded = 0;
  v6 = OpenServiceW(v3, L"kdc", 5u);
  v7 = v6;
  if ( !v6 )
  {
    v8 = GetLastError();
    v9 = "KerbWaitForKdc: OpenService failed: %lu";
    v10 = 489;
LABEL_7:
    LODWORD(v21) = v8;
    KerbTracerT::Log(1, "KerbWaitForKdc", v10, v9, v21);
    v2 = -1073741422;
    goto LABEL_41;
  }
  if ( QueryServiceConfigW(v6, &ServiceConfig, 0x40u, &pcbBytesNeeded) )
  {
    p_ServiceConfig = &ServiceConfig;
  }
  else
  {
    v8 = GetLastError();
    if ( v8 != 122 )
    {
      v9 = "KerbWaitForKdc: QueryServiceConfig failed: %lu";
      v10 = 515;
      goto LABEL_7;
    }
    v12 = pcbBytesNeeded;
    if ( !pcbBytesNeeded
      || pcbBytesNeeded > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)pcbBytesNeeded + g_ulAdditionalProbeSize + 8 < pcbBytesNeeded
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_54;
    }
    v13 = v12 + 23;
    if ( v12 + 23 <= v12 + 8 )
      v13 = 0xFFFFFFFFFFFFFF0LL;
    v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
    v15 = alloca(v14);
    v16 = alloca(v14);
    p_pcbBytesNeeded = (struct _QUERY_SERVICE_CONFIGW *)&pcbBytesNeeded;
    if ( &v20 == (__int64 *)-48LL
      || (pcbBytesNeeded = 1801679955, (p_pcbBytesNeeded = (struct _QUERY_SERVICE_CONFIGW *)hSCObject) == 0) )
    {
LABEL_54:
      if ( v12 + 8 >= v12 )
      {
        v17 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        p_pcbBytesNeeded = (struct _QUERY_SERVICE_CONFIGW *)v17;
        if ( v17 )
        {
          *v17 = 1885431112;
          p_pcbBytesNeeded = (struct _QUERY_SERVICE_CONFIGW *)(v17 + 2);
        }
      }
    }
    if ( !p_pcbBytesNeeded )
    {
      v2 = -1073741801;
      goto LABEL_41;
    }
    if ( !QueryServiceConfigW(v7, p_pcbBytesNeeded, pcbBytesNeeded, &pcbBytesNeeded) )
    {
      v8 = GetLastError();
      v9 = "KerbWaitForKdc: QueryServiceConfig failed again: %lu";
      v10 = 535;
      goto LABEL_7;
    }
    p_ServiceConfig = p_pcbBytesNeeded;
  }
  dwStartType = p_ServiceConfig->dwStartType;
  for ( i = QueryServiceStatus(v7, &ServiceStatus); ; i = QueryServiceStatus(v7, &ServiceStatus) )
  {
    if ( !i )
    {
      LODWORD(v21) = GetLastError();
      KerbTracerT::Log(1, "KerbWaitForKdc", 561, "KerbWaitForKdc: QueryServiceStatus failed: %lu", v21);
      goto LABEL_40;
    }
    if ( ServiceStatus.dwCurrentState != 1 )
      break;
    if ( ServiceStatus.dwWin32ExitCode != 1077 )
    {
      KerbTracerT::Log(
        1,
        "KerbWaitForKdc",
        588,
        "KerbWaitForKdc: KDC service couldn't start: %lu %lx",
        ServiceStatus.dwWin32ExitCode,
        ServiceStatus.dwWin32ExitCode);
      if ( ServiceStatus.dwWin32ExitCode == 1066 )
        KerbTracerT::Log(
          1,
          "KerbWaitForKdc",
          595,
          "         Service specific error code: %lu %lx",
          ServiceStatus.dwServiceSpecificExitCode,
          ServiceStatus.dwServiceSpecificExitCode);
      goto LABEL_40;
    }
    if ( dwStartType != 2 )
      goto LABEL_41;
LABEL_35:
    v2 = KerbWaitForEvent(L"\\Security\\KdcStartEvent", 1u);
    if ( v2 != -1073741422 )
      goto LABEL_41;
    if ( !--v0 )
      goto LABEL_40;
  }
  if ( ServiceStatus.dwCurrentState == 2 )
    goto LABEL_35;
  if ( ServiceStatus.dwCurrentState != 4 )
  {
    LODWORD(v21) = ServiceStatus.dwCurrentState;
    KerbTracerT::Log(1, "KerbWaitForKdc", 621, "KerbWaitForKdc: Invalid service state: %lu", v21);
LABEL_40:
    v2 = -1073741422;
    goto LABEL_41;
  }
  v2 = 0;
LABEL_41:
  CloseServiceHandle(hSCObject[0]);
  if ( v7 )
    CloseServiceHandle(v7);
  if ( p_pcbBytesNeeded && LODWORD(p_pcbBytesNeeded[-1].lpDisplayName) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v2 >= 0 )
    KerbKdcStarted = 1;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180078fa4  push    rbp
0x180078fa6  push    rbx
0x180078fa7  push    rsi
0x180078fa8  push    rdi
0x180078fa9  push    r12
0x180078fab  push    r13
0x180078fad  push    r14
0x180078faf  push    r15
0x180078fb1  sub     rsp, 0C8h
0x180078fb8  lea     rbp, [rsp+30h]
0x180078fbd  mov     rax, cs:__security_cookie
0x180078fc4  xor     rax, rbp
0x180078fc7  mov     [rbp+0D0h+var_50], rax
0x180078fce  mov     r13d, cs:?KerbGlobalKdcWaitTime@@3KA; ulong KerbGlobalKdcWaitTime
0x180078fd5  lea     rcx, [rbp+0D0h+ServiceConfig]; void *
0x180078fd9  xorps   xmm0, xmm0
0x180078fdc  mov     esi, 40h ; '@'
0x180078fe1  movups  xmmword ptr [rbp+0D0h+ServiceStatus.dwServiceType], xmm0
0x180078fe5  mov     r8d, esi; Size
0x180078fe8  xor     edx, edx; Val
0x180078fea  movups  xmmword ptr [rbp+0D0h+ServiceStatus.dwWin32ExitCode], xmm0
0x180078fee  call    memset_0
0x180078ff3  xor     edx, edx; unsigned int
0x180078ff5  mov     [rbp+0D0h+pcbBytesNeeded], 0
0x180078ffc  lea     rcx, aSecurityKdcsta; "\\Security\\KdcStartEvent"
0x180079003  call    ?KerbWaitForEvent@@YAJPEAGK@Z; KerbWaitForEvent(ushort *,ulong)
0x180079008  lea     r14d, [rsi-3Fh]
0x18007900c  mov     ebx, eax
0x18007900e  test    eax, eax
0x180079010  js      short loc_18007901E
0x180079012  mov     cs:?KerbKdcStarted@@3EA, r14b; uchar KerbKdcStarted
0x180079019  jmp     loc_1800792AC
0x18007901e  mov     r8d, r14d; dwDesiredAccess
0x180079021  xor     edx, edx; lpDatabaseName
0x180079023  xor     ecx, ecx; lpMachineName
0x180079025  call    cs:__imp_OpenSCManagerW
0x18007902b  mov     [rbp+0D0h+hSCObject], rax
0x18007902f  test    rax, rax
0x180079032  jnz     short loc_180079064
0x180079034  call    cs:__imp_GetLastError
0x18007903a  lea     r9, aKerbwaitforkdc_6; " KerbWaitForKdc: OpenSCManager failed: "...
0x180079041  mov     r8d, 1DEh
0x180079047  lea     rdx, aKerbwaitforkdc_2; "KerbWaitForKdc"
0x18007904e  mov     dword ptr [rsp+100h+var_E0], eax
0x180079052  mov     ecx, r14d
0x180079055  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007905a  mov     ebx, 0C0000192h
0x18007905f  jmp     loc_1800792AA
0x180079064  xor     edi, edi
0x180079066  lea     rdx, ServiceName; "kdc"
0x18007906d  mov     rcx, rax; hSCManager
0x180079070  lea     r8d, [rdi+5]; dwDesiredAccess
0x180079074  call    cs:__imp_OpenServiceW
0x18007907a  mov     r15, rax
0x18007907d  test    rax, rax
0x180079080  jnz     short loc_1800790B2
0x180079082  call    cs:__imp_GetLastError
0x180079088  lea     r9, aKerbwaitforkdc_4; "KerbWaitForKdc: OpenService failed: %lu"
0x18007908f  mov     r8d, 1E9h
0x180079095  lea     rdx, aKerbwaitforkdc_2; "KerbWaitForKdc"
0x18007909c  mov     dword ptr [rsp+100h+var_E0], eax
0x1800790a0  mov     ecx, r14d
0x1800790a3  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800790a8  mov     ebx, 0C0000192h
0x1800790ad  jmp     loc_18007926A
0x1800790b2  lea     r9, [rbp+0D0h+pcbBytesNeeded]; pcbBytesNeeded
0x1800790b6  mov     r8d, esi; cbBufSize
0x1800790b9  lea     rdx, [rbp+0D0h+ServiceConfig]; lpServiceConfig
0x1800790bd  mov     rcx, r15; hService
0x1800790c0  call    cs:__imp_QueryServiceConfigW
0x1800790c6  test    eax, eax
0x1800790c8  jz      short loc_1800790D3
0x1800790ca  lea     rax, [rbp+0D0h+ServiceConfig]
0x1800790ce  jmp     loc_1800791BF
0x1800790d3  call    cs:__imp_GetLastError
0x1800790d9  cmp     eax, 7Ah ; 'z'
0x1800790dc  jz      short loc_1800790ED
0x1800790de  lea     r9, aKerbwaitforkdc_5; "KerbWaitForKdc: QueryServiceConfig fail"...
0x1800790e5  mov     r8d, 203h
0x1800790eb  jmp     short loc_180079095
0x1800790ed  mov     esi, [rbp+0D0h+pcbBytesNeeded]
0x1800790f0  test    rsi, rsi
0x1800790f3  jz      short loc_180079156
0x1800790f5  cmp     rsi, cs:g_ulMaxStackAllocSize
0x1800790fc  ja      short loc_180079156
0x1800790fe  mov     rcx, cs:g_ulAdditionalProbeSize
0x180079105  add     rcx, 8
0x180079109  add     rcx, rsi
0x18007910c  cmp     rcx, rsi
0x18007910f  jb      short loc_180079156
0x180079111  call    VerifyStackAvailable
0x180079116  test    eax, eax
0x180079118  jz      short loc_180079156
0x18007911a  lea     rax, [rsi+8]
0x18007911e  lea     rcx, [rax+0Fh]
0x180079122  cmp     rcx, rax
0x180079125  ja      short loc_180079131
0x180079127  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180079131  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180079135  mov     rax, rcx
0x180079138  call    _alloca_probe
0x18007913d  sub     rsp, rcx
0x180079140  lea     rdi, [rsp+100h+pcbBytesNeeded]
0x180079145  test    rdi, rdi
0x180079148  jz      short loc_180079156
0x18007914a  mov     dword ptr [rdi], 6B637453h
0x180079150  add     rdi, 8
0x180079154  jnz     short loc_18007917D
0x180079156  lea     rcx, [rsi+8]
0x18007915a  cmp     rcx, rsi
0x18007915d  jb      short loc_18007917D
0x18007915f  mov     rax, cs:g_pfnAllocate
0x180079166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007916b  mov     rdi, rax
0x18007916e  test    rax, rax
0x180079171  jz      short loc_18007917D
0x180079173  mov     dword ptr [rax], 70616548h
0x180079179  add     rdi, 8
0x18007917d  test    rdi, rdi
0x180079180  jnz     short loc_18007918C
0x180079182  mov     ebx, 0C0000017h
0x180079187  jmp     loc_18007926A
0x18007918c  mov     r8d, [rbp+0D0h+pcbBytesNeeded]; cbBufSize
0x180079190  lea     r9, [rbp+0D0h+pcbBytesNeeded]; pcbBytesNeeded
0x180079194  mov     rdx, rdi; lpServiceConfig
0x180079197  mov     rcx, r15; hService
0x18007919a  call    cs:__imp_QueryServiceConfigW
0x1800791a0  test    eax, eax
0x1800791a2  jnz     short loc_1800791BC
0x1800791a4  call    cs:__imp_GetLastError
0x1800791aa  lea     r9, aKerbwaitforkdc_0; "KerbWaitForKdc: QueryServiceConfig fail"...
0x1800791b1  mov     r8d, 217h
0x1800791b7  jmp     loc_180079095
0x1800791bc  mov     rax, rdi
0x1800791bf  mov     r12d, [rax+4]
0x1800791c3  lea     rdx, [rbp+0D0h+ServiceStatus]; lpServiceStatus
0x1800791c7  mov     rcx, r15; hService
0x1800791ca  call    cs:__imp_QueryServiceStatus
0x1800791d0  mov     esi, 0C0000192h
0x1800791d5  jmp     short loc_18007923E
0x1800791d7  mov     ecx, [rbp+0D0h+ServiceStatus.dwCurrentState]
0x1800791da  mov     eax, ecx
0x1800791dc  sub     eax, r14d
0x1800791df  jz      short loc_180079202
0x1800791e1  sub     eax, r14d
0x1800791e4  jz      short loc_180079216
0x1800791e6  cmp     eax, 2
0x1800791e9  jz      loc_1800792CF
0x1800791ef  mov     dword ptr [rsp+100h+var_E0], ecx
0x1800791f3  lea     r9, aKerbwaitforkdc_1; "KerbWaitForKdc: Invalid service state: "...
0x1800791fa  mov     r8d, 26Dh
0x180079200  jmp     short loc_180079259
0x180079202  mov     eax, [rbp+0D0h+ServiceStatus.dwWin32ExitCode]
0x180079205  cmp     eax, 435h
0x18007920a  jnz     loc_1800792D3
0x180079210  cmp     r12d, 2
0x180079214  jnz     short loc_18007926A
0x180079216  mov     edx, r14d; unsigned int
0x180079219  lea     rcx, aSecurityKdcsta; "\\Security\\KdcStartEvent"
0x180079220  call    ?KerbWaitForEvent@@YAJPEAGK@Z; KerbWaitForEvent(ushort *,ulong)
0x180079225  mov     ebx, eax
0x180079227  cmp     eax, esi
0x180079229  jnz     short loc_18007926A
0x18007922b  add     r13d, 0FFFFFFFFh
0x18007922f  jz      short loc_180079268
0x180079231  lea     rdx, [rbp+0D0h+ServiceStatus]; lpServiceStatus
0x180079235  mov     rcx, r15; hService
0x180079238  call    cs:__imp_QueryServiceStatus
0x18007923e  test    eax, eax
0x180079240  jnz     short loc_1800791D7
0x180079242  call    cs:__imp_GetLastError
0x180079248  mov     dword ptr [rsp+100h+var_E0], eax
0x18007924c  lea     r9, aKerbwaitforkdc_3; "KerbWaitForKdc: QueryServiceStatus fail"...
0x180079253  mov     r8d, 231h
0x180079259  lea     rdx, aKerbwaitforkdc_2; "KerbWaitForKdc"
0x180079260  mov     ecx, r14d
0x180079263  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180079268  mov     ebx, esi
0x18007926a  mov     rcx, [rbp+0D0h+hSCObject]; hSCObject
0x18007926e  call    cs:__imp_CloseServiceHandle
0x180079274  test    r15, r15
0x180079277  jz      short loc_180079282
0x180079279  mov     rcx, r15; hSCObject
0x18007927c  call    cs:__imp_CloseServiceHandle
0x180079282  test    rdi, rdi
0x180079285  jz      short loc_18007929F
0x180079287  lea     rcx, [rdi-8]
0x18007928b  cmp     dword ptr [rcx], 70616548h
0x180079291  jnz     short loc_18007929F
0x180079293  mov     rax, cs:g_pfnFree
0x18007929a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007929f  test    ebx, ebx
0x1800792a1  js      short loc_1800792AA
0x1800792a3  mov     cs:?KerbKdcStarted@@3EA, r14b; uchar KerbKdcStarted
0x1800792aa  mov     eax, ebx
0x1800792ac  mov     rcx, [rbp+0D0h+var_50]
0x1800792b3  xor     rcx, rbp; StackCookie
0x1800792b6  call    __security_check_cookie
0x1800792bb  lea     rsp, [rbp+98h]
0x1800792c2  pop     r15
0x1800792c4  pop     r14
0x1800792c6  pop     r13
0x1800792c8  pop     r12
0x1800792ca  pop     rdi
0x1800792cb  pop     rsi
0x1800792cc  pop     rbx
0x1800792cd  pop     rbp
0x1800792ce  retn
0x1800792cf  xor     ebx, ebx
0x1800792d1  jmp     short loc_18007926A
0x1800792d3  mov     [rsp+100h+var_D8], eax
0x1800792d7  lea     r9, aKerbwaitforkdc; "KerbWaitForKdc: KDC service couldn't st"...
0x1800792de  mov     r8d, 24Ch
0x1800792e4  mov     dword ptr [rsp+100h+var_E0], eax
0x1800792e8  lea     rdx, aKerbwaitforkdc_2; "KerbWaitForKdc"
0x1800792ef  mov     ecx, r14d
0x1800792f2  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800792f7  cmp     [rbp+0D0h+ServiceStatus.dwWin32ExitCode], 42Ah
0x1800792fe  jnz     loc_180079268
0x180079304  mov     eax, [rbp+0D0h+ServiceStatus.dwServiceSpecificExitCode]
0x180079307  lea     r9, aServiceSpecifi; "         Service specific error code: %"...
0x18007930e  mov     [rsp+100h+var_D8], eax
0x180079312  lea     rdx, aKerbwaitforkdc_2; "KerbWaitForKdc"
0x180079319  mov     r8d, 253h
0x18007931f  mov     dword ptr [rsp+100h+var_E0], eax
0x180079323  mov     ecx, r14d
0x180079326  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007932b  jmp     loc_180079268
```
