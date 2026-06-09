# GetNodeServiceState

- ea: `0x180024650`
- end: `0x180024902`
- name: `GetNodeServiceState`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002e7d0`

## callees

- `0x180002f50`
- `0x180024650`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002470f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002474e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002477a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024875`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002470f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002474e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002477a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024875`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800248d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800248d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002476c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002476c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180024701`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180024701`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002469e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002469e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800248ba`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800248c8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800248ba`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800248c8`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180024744`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180024797`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180024744`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180024797`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800247fe`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800247fe`

## string_xrefs

- `0x1800246d5`: `Error in opening handle of Service Control Manager for node %ws. Error %d`
- `0x1800246b5`: `GetNodeServiceState`
- `0x1800247c4`: `GetNodeServiceState`
- `0x180024844`: `GetNodeServiceState`
- `0x1800248a3`: `GetNodeServiceState`
- `0x18002472b`: `Error in opening handle for cluster service for node %ws. Error %d`
- `0x180024891`: `Querying for cluster service config failed for node %ws. Error %d`
- `0x180024824`: `Querying for cluster service status failed for node %ws. Error %d`
- `0x180024851`: `Cluster service is running on node %ws.`

## pseudocode

```c
__int64 __fastcall GetNodeServiceState(const WCHAR *a1, _DWORD *a2)
{
  const WCHAR *v3; // rbx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // r15
  DWORD LastError; // edi
  struct _QUERY_SERVICE_CONFIGW *v7; // rsi
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rbp
  DWORD v10; // eax
  __int64 v11; // r9
  const wchar_t *v12; // rax
  struct _QUERY_SERVICE_CONFIGW *v13; // rax
  DWORD v14; // eax
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp-68h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-60h] BYREF
  WCHAR ServiceName[8]; // [rsp+68h] [rbp-40h] BYREF

  pcbBytesNeeded = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v3 = a1;
  wcscpy(ServiceName, L"ClusSvc");
  v4 = OpenSCManagerW(a1, 0, 1u);
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( !v3 )
      v3 = &base;
    TraceMsg(
      2,
      0,
      L"GetNodeServiceState",
      645,
      L"Error in opening handle of Service Control Manager for node %ws. Error %d",
      v3,
      LastError);
    return LastError;
  }
  v7 = 0;
  v8 = OpenServiceW(v4, ServiceName, 5u);
  v9 = v8;
  if ( !v8 )
  {
    v10 = GetLastError();
    v11 = 654;
    LastError = v10;
    if ( !v3 )
      v3 = &base;
    v12 = L"Error in opening handle for cluster service for node %ws. Error %d";
LABEL_32:
    TraceMsg(2, 0, L"GetNodeServiceState", v11, v12, v3, LastError);
    goto LABEL_33;
  }
  if ( !QueryServiceConfigW(v8, 0, 0, &pcbBytesNeeded) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      v11 = 665;
LABEL_29:
      if ( !v3 )
        v3 = &base;
      v12 = L"Querying for cluster service config failed for node %ws. Error %d";
      goto LABEL_32;
    }
  }
  v13 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0, pcbBytesNeeded);
  v7 = v13;
  if ( v13 )
  {
    if ( QueryServiceConfigW(v9, v13, pcbBytesNeeded, &pcbBytesNeeded) )
    {
      if ( v7->dwStartType == 4 )
      {
        LastError = 0;
        *a2 = 1;
        if ( !v3 )
          v3 = &base;
        TraceMsg(4, 0, L"GetNodeServiceState", 685, L"Cluster node %ws is available to be added to the cluster.", v3);
        goto LABEL_33;
      }
      *a2 = 3;
      if ( QueryServiceStatus(v9, &ServiceStatus) )
      {
        if ( ServiceStatus.dwCurrentState == 4 )
        {
          if ( !v3 )
            v3 = &base;
          TraceMsg(4, 0, L"GetNodeServiceState", 707, L"Cluster service is running on node %ws.", v3);
          *a2 = 19;
        }
        LastError = 0;
        goto LABEL_33;
      }
      v14 = GetLastError();
      v11 = 701;
      LastError = v14;
      if ( !v3 )
        v3 = &base;
      v12 = L"Querying for cluster service status failed for node %ws. Error %d";
      goto LABEL_32;
    }
    LastError = GetLastError();
    v11 = 692;
    goto LABEL_29;
  }
  LastError = GetLastError();
LABEL_33:
  CloseServiceHandle(v5);
  if ( v9 )
    CloseServiceHandle(v9);
  if ( v7 )
    LocalFree(v7);
  return LastError;
}

```

## disassembly

```asm
0x180024650  mov     [rsp+arg_10], rbx
0x180024655  push    rbp
0x180024656  push    rsi
0x180024657  push    rdi
0x180024658  push    r14
0x18002465a  push    r15
0x18002465c  sub     rsp, 80h
0x180024663  mov     rax, cs:__security_cookie
0x18002466a  xor     rax, rsp
0x18002466d  mov     [rsp+0A8h+var_30], rax
0x180024672  movups  xmm0, xmmword ptr cs:aClussvc; "ClusSvc"
0x180024679  xor     eax, eax
0x18002467b  mov     r14, rdx
0x18002467e  xorps   xmm1, xmm1
0x180024681  mov     [rsp+0A8h+pcbBytesNeeded], eax
0x180024685  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm1
0x18002468a  xor     edx, edx; lpDatabaseName
0x18002468c  mov     rbx, rcx
0x18002468f  lea     r8d, [rax+1]; dwDesiredAccess
0x180024693  movdqu  xmmword ptr [rsp+0A8h+ServiceName], xmm0
0x180024699  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm1
0x18002469e  call    cs:__imp_OpenSCManagerW
0x1800246a4  mov     r15, rax
0x1800246a7  test    rax, rax
0x1800246aa  jnz     short loc_1800246F3
0x1800246ac  call    cs:__imp_GetLastError
0x1800246b2  test    rbx, rbx
0x1800246b5  lea     r8, aGetnodeservice; "GetNodeServiceState"
0x1800246bc  mov     edi, eax
0x1800246be  mov     r9d, 285h
0x1800246c4  lea     rax, base
0x1800246cb  mov     [rsp+0A8h+var_78], edi
0x1800246cf  cmovz   rbx, rax
0x1800246d3  xor     edx, edx
0x1800246d5  lea     rax, aErrorInOpening_0; "Error in opening handle of Service Cont"...
0x1800246dc  mov     [rsp+0A8h+var_80], rbx
0x1800246e1  mov     [rsp+0A8h+var_88], rax
0x1800246e6  lea     ecx, [rdx+2]
0x1800246e9  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800246ee  jmp     loc_1800248DC
0x1800246f3  xor     esi, esi
0x1800246f5  lea     rdx, [rsp+0A8h+ServiceName]; lpServiceName
0x1800246fa  mov     rcx, r15; hSCManager
0x1800246fd  lea     r8d, [rsi+5]; dwDesiredAccess
0x180024701  call    cs:__imp_OpenServiceW
0x180024707  mov     rbp, rax
0x18002470a  test    rax, rax
0x18002470d  jnz     short loc_180024737
0x18002470f  call    cs:__imp_GetLastError
0x180024715  test    rbx, rbx
0x180024718  mov     r9d, 28Eh
0x18002471e  mov     edi, eax
0x180024720  lea     rax, base
0x180024727  cmovz   rbx, rax
0x18002472b  lea     rax, aErrorInOpening; "Error in opening handle for cluster ser"...
0x180024732  jmp     loc_180024898
0x180024737  lea     r9, [rsp+0A8h+pcbBytesNeeded]; pcbBytesNeeded
0x18002473c  xor     r8d, r8d; cbBufSize
0x18002473f  xor     edx, edx; lpServiceConfig
0x180024741  mov     rcx, rbp; hService
0x180024744  call    cs:__imp_QueryServiceConfigW
0x18002474a  test    eax, eax
0x18002474c  jnz     short loc_180024766
0x18002474e  call    cs:__imp_GetLastError
0x180024754  mov     edi, eax
0x180024756  cmp     eax, 7Ah ; 'z'
0x180024759  jz      short loc_180024766
0x18002475b  mov     r9d, 299h
0x180024761  jmp     loc_180024883
0x180024766  mov     edx, [rsp+0A8h+pcbBytesNeeded]; uBytes
0x18002476a  xor     ecx, ecx; uFlags
0x18002476c  call    cs:__imp_LocalAlloc
0x180024772  mov     rsi, rax
0x180024775  test    rax, rax
0x180024778  jnz     short loc_180024787
0x18002477a  call    cs:__imp_GetLastError
0x180024780  mov     edi, eax
0x180024782  jmp     loc_1800248B7
0x180024787  mov     r8d, [rsp+0A8h+pcbBytesNeeded]; cbBufSize
0x18002478c  lea     r9, [rsp+0A8h+pcbBytesNeeded]; pcbBytesNeeded
0x180024791  mov     rdx, rsi; lpServiceConfig
0x180024794  mov     rcx, rbp; hService
0x180024797  call    cs:__imp_QueryServiceConfigW
0x18002479d  test    eax, eax
0x18002479f  jz      loc_180024875
0x1800247a5  cmp     dword ptr [rsi+4], 4
0x1800247a9  jnz     short loc_1800247EF
0x1800247ab  xor     edi, edi
0x1800247ad  mov     dword ptr [r14], 1
0x1800247b4  test    rbx, rbx
0x1800247b7  lea     rax, base
0x1800247be  mov     r9d, 2ADh
0x1800247c4  lea     r8, aGetnodeservice; "GetNodeServiceState"
0x1800247cb  cmovz   rbx, rax
0x1800247cf  lea     rax, aClusterNodeWsI; "Cluster node %ws is available to be add"...
0x1800247d6  mov     [rsp+0A8h+var_80], rbx
0x1800247db  lea     ecx, [rdi+4]
0x1800247de  xor     edx, edx
0x1800247e0  mov     [rsp+0A8h+var_88], rax
0x1800247e5  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800247ea  jmp     loc_1800248B7
0x1800247ef  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x1800247f4  mov     dword ptr [r14], 3
0x1800247fb  mov     rcx, rbp; hService
0x1800247fe  call    cs:__imp_QueryServiceStatus
0x180024804  test    eax, eax
0x180024806  jnz     short loc_18002482D
0x180024808  call    cs:__imp_GetLastError
0x18002480e  test    rbx, rbx
0x180024811  mov     r9d, 2BDh
0x180024817  mov     edi, eax
0x180024819  lea     rax, base
0x180024820  cmovz   rbx, rax
0x180024824  lea     rax, aQueryingForClu_0; "Querying for cluster service status fai"...
0x18002482b  jmp     short loc_180024898
0x18002482d  cmp     [rsp+0A8h+ServiceStatus.dwCurrentState], 4
0x180024832  jnz     short loc_180024871
0x180024834  test    rbx, rbx
0x180024837  lea     rax, base
0x18002483e  mov     r9d, 2C3h
0x180024844  lea     r8, aGetnodeservice; "GetNodeServiceState"
0x18002484b  cmovz   rbx, rax
0x18002484f  xor     edx, edx
0x180024851  lea     rax, aClusterService; "Cluster service is running on node %ws."
0x180024858  mov     [rsp+0A8h+var_80], rbx
0x18002485d  mov     [rsp+0A8h+var_88], rax
0x180024862  lea     ecx, [rdx+4]
0x180024865  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18002486a  mov     dword ptr [r14], 13h
0x180024871  xor     edi, edi
0x180024873  jmp     short loc_1800248B7
0x180024875  call    cs:__imp_GetLastError
0x18002487b  mov     edi, eax
0x18002487d  mov     r9d, 2B4h
0x180024883  lea     rax, base
0x18002488a  test    rbx, rbx
0x18002488d  cmovz   rbx, rax
0x180024891  lea     rax, aQueryingForClu; "Querying for cluster service config fai"...
0x180024898  xor     edx, edx
0x18002489a  mov     [rsp+0A8h+var_78], edi
0x18002489e  mov     [rsp+0A8h+var_80], rbx
0x1800248a3  lea     r8, aGetnodeservice; "GetNodeServiceState"
0x1800248aa  mov     [rsp+0A8h+var_88], rax
0x1800248af  lea     ecx, [rdx+2]
0x1800248b2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800248b7  mov     rcx, r15; hSCObject
0x1800248ba  call    cs:__imp_CloseServiceHandle
0x1800248c0  test    rbp, rbp
0x1800248c3  jz      short loc_1800248CE
0x1800248c5  mov     rcx, rbp; hSCObject
0x1800248c8  call    cs:__imp_CloseServiceHandle
0x1800248ce  test    rsi, rsi
0x1800248d1  jz      short loc_1800248DC
0x1800248d3  mov     rcx, rsi; hMem
0x1800248d6  call    cs:__imp_LocalFree
0x1800248dc  mov     eax, edi
0x1800248de  mov     rcx, [rsp+0A8h+var_30]
0x1800248e3  xor     rcx, rsp; StackCookie
0x1800248e6  call    __security_check_cookie
0x1800248eb  mov     rbx, [rsp+0A8h+arg_10]
0x1800248f3  add     rsp, 80h
0x1800248fa  pop     r15
0x1800248fc  pop     r14
0x1800248fe  pop     rdi
0x1800248ff  pop     rsi
0x180024900  pop     rbp
0x180024901  retn
```
