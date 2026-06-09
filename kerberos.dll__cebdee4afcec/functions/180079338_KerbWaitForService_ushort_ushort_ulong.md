# KerbWaitForService(ushort *,ushort *,ulong)

- ea: `0x180079338`
- end: `0x1800796e0`
- name: `?KerbWaitForService@@YAJPEAG0K@Z`
- size: `936`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, PCWSTR SourceString, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180037ea8`
- `0x1800389b8`

## callees

- `0x180007e80`
- `0x180070680`
- `0x18007108c`
- `0x180078eb0`
- `0x180079338`
- `0x18008b70c`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800793ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007946c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007953d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800795ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800793ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007946c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007953d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800795ea`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800795cd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800795cd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18007940a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18007940a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800793c0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800793c0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180079617`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180079625`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180079617`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180079625`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180079459`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180079533`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180079459`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180079533`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180079563`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800795e0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180079563`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800795e0`

## string_xrefs

- `0x1800796b8`: `         Service specific error code: %lu %lx`
- `0x1800793d4`: ` KerbWaitForService: OpenSCManager failed: %lu`
- `0x1800793e1`: `KerbWaitForService`
- `0x18007942b`: `KerbWaitForService`
- `0x180079601`: `KerbWaitForService`
- `0x180079686`: `KerbWaitForService`
- `0x1800796c3`: `KerbWaitForService`
- `0x18007941e`: `KerbWaitForService: OpenService failed: %lu`
- `0x180079477`: `KerbWaitForService: QueryServiceConfig failed: %lu`
- `0x180079543`: `KerbWaitForService: QueryServiceConfig failed again: %lu`
- `0x1800795f4`: `KerbWaitForService: QueryServiceStatus failed: %lu`
- `0x18007967b`: `KerbWaitForService: %ws service couldn't start: %lu %lx`
- `0x18007958c`: `KerbWaitForService: Invalid service state: %lu`

## pseudocode

```c
__int64 __fastcall KerbWaitForService(LPCWSTR lpServiceName, PCWSTR SourceString)
{
  unsigned int v4; // ebx
  __int64 result; // rax
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // r13
  DWORD LastError; // eax
  struct _QUERY_SERVICE_CONFIGW *p_pcbBytesNeeded; // rdi
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // r14
  DWORD v12; // eax
  const char *v13; // r9
  __int64 v14; // r8
  struct _QUERY_SERVICE_CONFIGW *p_ServiceConfig; // rax
  unsigned __int64 v16; // rsi
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  _DWORD *v21; // rax
  DWORD dwStartType; // r15d
  BOOL i; // eax
  __int64 v24; // [rsp+0h] [rbp-40h] BYREF
  __int64 v25; // [rsp+20h] [rbp-20h]
  __int64 v26; // [rsp+28h] [rbp-18h]
  __int64 v27; // [rsp+30h] [rbp-10h]
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp+0h] BYREF
  unsigned int v29; // [rsp+44h] [rbp+4h]
  _QWORD v30[3]; // [rsp+48h] [rbp+8h] BYREF
  struct _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+60h] [rbp+20h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+A0h] [rbp+60h] BYREF

  v30[0] = lpServiceName;
  v29 = KerbGlobalKdcWaitTime;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v4 = 0;
  memset_0(&ServiceConfig, 0, sizeof(ServiceConfig));
  pcbBytesNeeded = 0;
  if ( SourceString )
  {
    result = KerbWaitForEvent(SourceString, 0);
    v4 = result;
    if ( (int)result >= 0 )
      return result;
  }
  v6 = OpenSCManagerW(0, 0, 1u);
  v7 = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    KerbTracerT::Log(1, "KerbWaitForService", 752, " KerbWaitForService: OpenSCManager failed: %lu", LastError);
    return (unsigned int)-1073741422;
  }
  p_pcbBytesNeeded = 0;
  v10 = OpenServiceW(v6, lpServiceName, 5u);
  v11 = v10;
  if ( !v10 )
  {
    v12 = GetLastError();
    v13 = "KerbWaitForService: OpenService failed: %lu";
    v14 = 763;
LABEL_7:
    LODWORD(v25) = v12;
    KerbTracerT::Log(1, "KerbWaitForService", v14, v13, v25);
    v4 = -1073741422;
    goto LABEL_44;
  }
  if ( QueryServiceConfigW(v10, &ServiceConfig, 0x40u, &pcbBytesNeeded) )
  {
    p_ServiceConfig = &ServiceConfig;
  }
  else
  {
    v12 = GetLastError();
    if ( v12 != 122 )
    {
      v13 = "KerbWaitForService: QueryServiceConfig failed: %lu";
      v14 = 789;
      goto LABEL_7;
    }
    v16 = pcbBytesNeeded;
    if ( !pcbBytesNeeded
      || pcbBytesNeeded > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)pcbBytesNeeded + g_ulAdditionalProbeSize + 8 < pcbBytesNeeded
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_56;
    }
    v17 = v16 + 23;
    if ( v16 + 23 <= v16 + 8 )
      v17 = 0xFFFFFFFFFFFFFF0LL;
    v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
    v19 = alloca(v18);
    v20 = alloca(v18);
    p_pcbBytesNeeded = (struct _QUERY_SERVICE_CONFIGW *)&pcbBytesNeeded;
    if ( &v24 == (__int64 *)-64LL
      || (pcbBytesNeeded = 1801679955, (p_pcbBytesNeeded = (struct _QUERY_SERVICE_CONFIGW *)v30) == 0) )
    {
LABEL_56:
      if ( v16 + 8 >= v16 )
      {
        v21 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        p_pcbBytesNeeded = (struct _QUERY_SERVICE_CONFIGW *)v21;
        if ( v21 )
        {
          *v21 = 1885431112;
          p_pcbBytesNeeded = (struct _QUERY_SERVICE_CONFIGW *)(v21 + 2);
        }
      }
    }
    if ( !p_pcbBytesNeeded )
    {
      v4 = -1073741801;
      goto LABEL_44;
    }
    if ( !QueryServiceConfigW(v11, p_pcbBytesNeeded, pcbBytesNeeded, &pcbBytesNeeded) )
    {
      v12 = GetLastError();
      v13 = "KerbWaitForService: QueryServiceConfig failed again: %lu";
      v14 = 809;
      goto LABEL_7;
    }
    p_ServiceConfig = p_pcbBytesNeeded;
  }
  dwStartType = p_ServiceConfig->dwStartType;
  for ( i = QueryServiceStatus(v11, &ServiceStatus); ; i = QueryServiceStatus(v11, &ServiceStatus) )
  {
    if ( !i )
    {
      LODWORD(v25) = GetLastError();
      KerbTracerT::Log(1, "KerbWaitForService", 835, "KerbWaitForService: QueryServiceStatus failed: %lu", v25);
      goto LABEL_43;
    }
    if ( ServiceStatus.dwCurrentState != 1 )
      break;
    if ( ServiceStatus.dwWin32ExitCode != 1077 )
    {
      LODWORD(v27) = ServiceStatus.dwWin32ExitCode;
      LODWORD(v26) = ServiceStatus.dwWin32ExitCode;
      KerbTracerT::Log(
        1,
        "KerbWaitForService",
        863,
        "KerbWaitForService: %ws service couldn't start: %lu %lx",
        v30[0],
        v26,
        v27);
      if ( ServiceStatus.dwWin32ExitCode == 1066 )
        KerbTracerT::Log(
          1,
          "KerbWaitForService",
          870,
          "         Service specific error code: %lu %lx",
          ServiceStatus.dwServiceSpecificExitCode,
          ServiceStatus.dwServiceSpecificExitCode);
      goto LABEL_43;
    }
LABEL_34:
    if ( dwStartType != 2 )
      goto LABEL_44;
    if ( SourceString )
    {
      v4 = KerbWaitForEvent(SourceString, 1u);
      if ( v4 != -1073741422 )
        goto LABEL_44;
    }
    else
    {
      Sleep(0x3E8u);
    }
    if ( !--v29 )
      goto LABEL_43;
  }
  if ( ServiceStatus.dwCurrentState == 2 )
    goto LABEL_34;
  if ( ServiceStatus.dwCurrentState != 4 )
  {
    LODWORD(v25) = ServiceStatus.dwCurrentState;
    KerbTracerT::Log(1, "KerbWaitForService", 896, "KerbWaitForService: Invalid service state: %lu", v25);
LABEL_43:
    v4 = -1073741422;
    goto LABEL_44;
  }
  v4 = 0;
LABEL_44:
  CloseServiceHandle(v7);
  if ( v11 )
    CloseServiceHandle(v11);
  if ( p_pcbBytesNeeded )
  {
    if ( LODWORD(p_pcbBytesNeeded[-1].lpDisplayName) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return v4;
}

```

## disassembly

```asm
0x180079338  push    rbp
0x18007933a  push    rsi
0x18007933b  push    rdi
0x18007933c  push    r12
0x18007933e  push    r13
0x180079340  push    r14
0x180079342  push    r15
0x180079344  sub     rsp, 0D0h
0x18007934b  lea     rbp, [rsp+40h]
0x180079350  mov     [rbp+0C0h+arg_10], rbx
0x180079357  mov     rax, cs:__security_cookie
0x18007935e  xor     rax, rbp
0x180079361  mov     [rbp+0C0h+var_40], rax
0x180079368  mov     eax, cs:?KerbGlobalKdcWaitTime@@3KA; ulong KerbGlobalKdcWaitTime
0x18007936e  xorps   xmm0, xmm0
0x180079371  mov     r12, rdx
0x180079374  mov     [rbp+0C0h+var_B8], rcx
0x180079378  mov     rsi, rcx
0x18007937b  mov     [rbp+0C0h+var_BC], eax
0x18007937e  movups  xmmword ptr [rbp+0C0h+ServiceStatus.dwServiceType], xmm0
0x180079382  xor     ebx, ebx
0x180079384  lea     rcx, [rbp+0C0h+ServiceConfig]; void *
0x180079388  xor     edx, edx; Val
0x18007938a  movups  xmmword ptr [rbp+0C0h+ServiceStatus.dwWin32ExitCode], xmm0
0x18007938e  lea     r8d, [rbx+40h]; Size
0x180079392  call    memset_0
0x180079397  mov     [rbp+0C0h+pcbBytesNeeded], ebx
0x18007939a  test    r12, r12
0x18007939d  jz      short loc_1800793B3
0x18007939f  xor     edx, edx; unsigned int
0x1800793a1  mov     rcx, r12; SourceString
0x1800793a4  call    ?KerbWaitForEvent@@YAJPEAGK@Z; KerbWaitForEvent(ushort *,ulong)
0x1800793a9  mov     ebx, eax
0x1800793ab  test    eax, eax
0x1800793ad  jns     loc_18007964A
0x1800793b3  mov     r15d, 1
0x1800793b9  xor     edx, edx; lpDatabaseName
0x1800793bb  mov     r8d, r15d; dwDesiredAccess
0x1800793be  xor     ecx, ecx; lpMachineName
0x1800793c0  call    cs:__imp_OpenSCManagerW
0x1800793c6  mov     r13, rax
0x1800793c9  test    rax, rax
0x1800793cc  jnz     short loc_1800793FE
0x1800793ce  call    cs:__imp_GetLastError
0x1800793d4  lea     r9, aKerbwaitforser_1; " KerbWaitForService: OpenSCManager fail"...
0x1800793db  mov     r8d, 2F0h
0x1800793e1  lea     rdx, aKerbwaitforser_2; "KerbWaitForService"
0x1800793e8  mov     dword ptr [rsp+100h+var_E0], eax
0x1800793ec  mov     ecx, r15d
0x1800793ef  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800793f4  mov     ebx, 0C0000192h
0x1800793f9  jmp     loc_180079648
0x1800793fe  xor     edi, edi
0x180079400  mov     rdx, rsi; lpServiceName
0x180079403  mov     rcx, r13; hSCManager
0x180079406  lea     r8d, [rdi+5]; dwDesiredAccess
0x18007940a  call    cs:__imp_OpenServiceW
0x180079410  mov     r14, rax
0x180079413  test    rax, rax
0x180079416  jnz     short loc_180079448
0x180079418  call    cs:__imp_GetLastError
0x18007941e  lea     r9, aKerbwaitforser_5; "KerbWaitForService: OpenService failed:"...
0x180079425  mov     r8d, 2FBh
0x18007942b  lea     rdx, aKerbwaitforser_2; "KerbWaitForService"
0x180079432  mov     dword ptr [rsp+100h+var_E0], eax
0x180079436  mov     ecx, r15d
0x180079439  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007943e  mov     ebx, 0C0000192h
0x180079443  jmp     loc_180079614
0x180079448  lea     r9, [rbp+0C0h+pcbBytesNeeded]; pcbBytesNeeded
0x18007944c  mov     r8d, 40h ; '@'; cbBufSize
0x180079452  lea     rdx, [rbp+0C0h+ServiceConfig]; lpServiceConfig
0x180079456  mov     rcx, r14; hService
0x180079459  call    cs:__imp_QueryServiceConfigW
0x18007945f  test    eax, eax
0x180079461  jz      short loc_18007946C
0x180079463  lea     rax, [rbp+0C0h+ServiceConfig]
0x180079467  jmp     loc_180079558
0x18007946c  call    cs:__imp_GetLastError
0x180079472  cmp     eax, 7Ah ; 'z'
0x180079475  jz      short loc_180079486
0x180079477  lea     r9, aKerbwaitforser_0; "KerbWaitForService: QueryServiceConfig "...
0x18007947e  mov     r8d, 315h
0x180079484  jmp     short loc_18007942B
0x180079486  mov     esi, [rbp+0C0h+pcbBytesNeeded]
0x180079489  test    rsi, rsi
0x18007948c  jz      short loc_1800794EF
0x18007948e  cmp     rsi, cs:g_ulMaxStackAllocSize
0x180079495  ja      short loc_1800794EF
0x180079497  mov     rcx, cs:g_ulAdditionalProbeSize
0x18007949e  add     rcx, 8
0x1800794a2  add     rcx, rsi
0x1800794a5  cmp     rcx, rsi
0x1800794a8  jb      short loc_1800794EF
0x1800794aa  call    VerifyStackAvailable
0x1800794af  test    eax, eax
0x1800794b1  jz      short loc_1800794EF
0x1800794b3  lea     rax, [rsi+8]
0x1800794b7  lea     rcx, [rax+0Fh]
0x1800794bb  cmp     rcx, rax
0x1800794be  ja      short loc_1800794CA
0x1800794c0  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800794ca  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800794ce  mov     rax, rcx
0x1800794d1  call    _alloca_probe
0x1800794d6  sub     rsp, rcx
0x1800794d9  lea     rdi, [rsp+100h+pcbBytesNeeded]
0x1800794de  test    rdi, rdi
0x1800794e1  jz      short loc_1800794EF
0x1800794e3  mov     dword ptr [rdi], 6B637453h
0x1800794e9  add     rdi, 8
0x1800794ed  jnz     short loc_180079516
0x1800794ef  lea     rcx, [rsi+8]
0x1800794f3  cmp     rcx, rsi
0x1800794f6  jb      short loc_180079516
0x1800794f8  mov     rax, cs:g_pfnAllocate
0x1800794ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079504  mov     rdi, rax
0x180079507  test    rax, rax
0x18007950a  jz      short loc_180079516
0x18007950c  mov     dword ptr [rax], 70616548h
0x180079512  add     rdi, 8
0x180079516  test    rdi, rdi
0x180079519  jnz     short loc_180079525
0x18007951b  mov     ebx, 0C0000017h
0x180079520  jmp     loc_180079614
0x180079525  mov     r8d, [rbp+0C0h+pcbBytesNeeded]; cbBufSize
0x180079529  lea     r9, [rbp+0C0h+pcbBytesNeeded]; pcbBytesNeeded
0x18007952d  mov     rdx, rdi; lpServiceConfig
0x180079530  mov     rcx, r14; hService
0x180079533  call    cs:__imp_QueryServiceConfigW
0x180079539  test    eax, eax
0x18007953b  jnz     short loc_180079555
0x18007953d  call    cs:__imp_GetLastError
0x180079543  lea     r9, aKerbwaitforser_4; "KerbWaitForService: QueryServiceConfig "...
0x18007954a  mov     r8d, 329h
0x180079550  jmp     loc_18007942B
0x180079555  mov     rax, rdi
0x180079558  mov     r15d, [rax+4]
0x18007955c  lea     rdx, [rbp+0C0h+ServiceStatus]; lpServiceStatus
0x180079560  mov     rcx, r14; hService
0x180079563  call    cs:__imp_QueryServiceStatus
0x180079569  mov     esi, 0C0000192h
0x18007956e  jmp     short loc_1800795E6
0x180079570  mov     ecx, [rbp+0C0h+ServiceStatus.dwCurrentState]
0x180079573  mov     eax, ecx
0x180079575  sub     eax, 1
0x180079578  jz      short loc_18007959B
0x18007957a  sub     eax, 1
0x18007957d  jz      short loc_1800795A9
0x18007957f  cmp     eax, 2
0x180079582  jz      loc_180079673
0x180079588  mov     dword ptr [rsp+100h+var_E0], ecx
0x18007958c  lea     r9, aKerbwaitforser_6; "KerbWaitForService: Invalid service sta"...
0x180079593  mov     r8d, 380h
0x180079599  jmp     short loc_180079601
0x18007959b  mov     eax, [rbp+0C0h+ServiceStatus.dwWin32ExitCode]
0x18007959e  cmp     eax, 435h
0x1800795a3  jnz     loc_180079677
0x1800795a9  cmp     r15d, 2
0x1800795ad  jnz     short loc_180079614
0x1800795af  test    r12, r12
0x1800795b2  jz      short loc_1800795C8
0x1800795b4  lea     edx, [r15-1]; unsigned int
0x1800795b8  mov     rcx, r12; SourceString
0x1800795bb  call    ?KerbWaitForEvent@@YAJPEAGK@Z; KerbWaitForEvent(ushort *,ulong)
0x1800795c0  mov     ebx, eax
0x1800795c2  cmp     eax, esi
0x1800795c4  jnz     short loc_180079614
0x1800795c6  jmp     short loc_1800795D3
0x1800795c8  mov     ecx, 3E8h; dwMilliseconds
0x1800795cd  call    cs:__imp_Sleep
0x1800795d3  add     [rbp+0C0h+var_BC], 0FFFFFFFFh
0x1800795d7  jz      short loc_180079612
0x1800795d9  lea     rdx, [rbp+0C0h+ServiceStatus]; lpServiceStatus
0x1800795dd  mov     rcx, r14; hService
0x1800795e0  call    cs:__imp_QueryServiceStatus
0x1800795e6  test    eax, eax
0x1800795e8  jnz     short loc_180079570
0x1800795ea  call    cs:__imp_GetLastError
0x1800795f0  mov     dword ptr [rsp+100h+var_E0], eax
0x1800795f4  lea     r9, aKerbwaitforser_3; "KerbWaitForService: QueryServiceStatus "...
0x1800795fb  mov     r8d, 343h
0x180079601  lea     rdx, aKerbwaitforser_2; "KerbWaitForService"
0x180079608  mov     ecx, 1
0x18007960d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180079612  mov     ebx, esi
0x180079614  mov     rcx, r13; hSCObject
0x180079617  call    cs:__imp_CloseServiceHandle
0x18007961d  test    r14, r14
0x180079620  jz      short loc_18007962B
0x180079622  mov     rcx, r14; hSCObject
0x180079625  call    cs:__imp_CloseServiceHandle
0x18007962b  test    rdi, rdi
0x18007962e  jz      short loc_180079648
0x180079630  lea     rcx, [rdi-8]
0x180079634  cmp     dword ptr [rcx], 70616548h
0x18007963a  jnz     short loc_180079648
0x18007963c  mov     rax, cs:g_pfnFree
0x180079643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079648  mov     eax, ebx
0x18007964a  mov     rcx, [rbp+0C0h+var_40]
0x180079651  xor     rcx, rbp; StackCookie
0x180079654  call    __security_check_cookie
0x180079659  mov     rbx, [rbp+0C0h+arg_10]
0x180079660  lea     rsp, [rbp+90h]
0x180079667  pop     r15
0x180079669  pop     r14
0x18007966b  pop     r13
0x18007966d  pop     r12
0x18007966f  pop     rdi
0x180079670  pop     rsi
0x180079671  pop     rbp
0x180079672  retn
0x180079673  xor     ebx, ebx
0x180079675  jmp     short loc_180079614
0x180079677  mov     dword ptr [rsp+100h+var_D0], eax
0x18007967b  lea     r9, aKerbwaitforser; "KerbWaitForService: %ws service couldn'"...
0x180079682  mov     dword ptr [rsp+100h+var_D8], eax
0x180079686  lea     rdx, aKerbwaitforser_2; "KerbWaitForService"
0x18007968d  mov     rax, [rbp+0C0h+var_B8]
0x180079691  mov     ebx, 1
0x180079696  mov     r8d, 35Fh
0x18007969c  mov     [rsp+100h+var_E0], rax
0x1800796a1  mov     ecx, ebx
0x1800796a3  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800796a8  cmp     [rbp+0C0h+ServiceStatus.dwWin32ExitCode], 42Ah
0x1800796af  jnz     loc_180079612
0x1800796b5  mov     eax, [rbp+0C0h+ServiceStatus.dwServiceSpecificExitCode]
0x1800796b8  lea     r9, aServiceSpecifi; "         Service specific error code: %"...
0x1800796bf  mov     dword ptr [rsp+100h+var_D8], eax
0x1800796c3  lea     rdx, aKerbwaitforser_2; "KerbWaitForService"
0x1800796ca  mov     r8d, 366h
0x1800796d0  mov     dword ptr [rsp+100h+var_E0], eax
0x1800796d4  mov     ecx, ebx
0x1800796d6  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800796db  jmp     loc_180079612
```
