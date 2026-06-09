# CCatalogServer::IsServiceRunning(__MIDL___MIDL_itf_catsrv_0000_0004_0001,__MIDL___MIDL_itf_catsrv_0000_0004_0002 *)

- ea: `0x18001e5d0`
- end: `0x18001e73b`
- name: `?IsServiceRunning@CCatalogServer@@UEAAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@PEAW4__MIDL___MIDL_itf_catsrv_0000_0004_0002@@@Z`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18001e5d0`
- `0x18001e744`
- `0x18001efbc`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6a0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e704`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e712`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e704`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e712`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001e646`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001e646`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001e66a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001e66a`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001e689`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001e689`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001e6e5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001e6e5`

## pseudocode

```c
__int64 __fastcall CCatalogServer::IsServiceRunning(__int64 a1, unsigned int a2, _DWORD *a3)
{
  __int64 v3; // rsi
  int LoadBalancingIfNeeded; // ebx
  const WCHAR *v6; // rsi
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rbp
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rsi
  DWORD LastError; // eax
  DWORD v12; // eax
  DWORD v13; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-48h] BYREF

  v3 = (int)a2;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( a2 == 1 )
  {
    LoadBalancingIfNeeded = LoadLoadBalancingIfNeeded(a2);
    if ( LoadBalancingIfNeeded < 0 )
      return (unsigned int)LoadBalancingIfNeeded;
    if ( a3 )
    {
      v6 = (&csServices)[10 * v3 - 5];
      *a3 = 7;
      v7 = OpenSCManagerW(0, 0, 0x80000001);
      v8 = v7;
      if ( !v7 )
        return (unsigned int)-2147418113;
      v9 = OpenServiceW(v7, v6, 0x84u);
      v10 = v9;
      if ( v9 )
      {
        if ( ControlService(v9, 4u, &ServiceStatus) )
        {
          *a3 = utConvertToServiceState(ServiceStatus.dwCurrentState);
          goto LABEL_21;
        }
        LastError = GetLastError();
        *a3 = 7;
        v12 = LastError - 5;
        if ( v12 )
        {
          v13 = v12 - 1046;
          if ( !v13 )
            goto LABEL_15;
          v14 = v13 - 1;
          if ( !v14 )
            goto LABEL_15;
          v15 = v14 - 1;
          if ( v15 && (v16 = v15 - 8) != 0 )
          {
            if ( v16 != 1 )
            {
LABEL_15:
              LoadBalancingIfNeeded = -2147418113;
              goto LABEL_21;
            }
            *a3 = 0;
          }
          else
          {
            if ( !QueryServiceStatus(v10, &ServiceStatus) )
              goto LABEL_15;
            *a3 = utConvertToServiceState(ServiceStatus.dwCurrentState);
          }
          LoadBalancingIfNeeded = 0;
        }
        else
        {
          LoadBalancingIfNeeded = -2147024891;
        }
      }
LABEL_21:
      CloseServiceHandle(v8);
      if ( v10 )
        CloseServiceHandle(v10);
      return (unsigned int)LoadBalancingIfNeeded;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001e5d0  mov     [rsp+arg_0], rbx
0x18001e5d5  push    rbp
0x18001e5d6  push    rsi
0x18001e5d7  push    rdi
0x18001e5d8  sub     rsp, 50h
0x18001e5dc  mov     rax, cs:__security_cookie
0x18001e5e3  xor     rax, rsp
0x18001e5e6  mov     [rsp+68h+var_28], rax
0x18001e5eb  xorps   xmm0, xmm0
0x18001e5ee  movsxd  rsi, edx
0x18001e5f1  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x18001e5f6  mov     rdi, r8
0x18001e5f9  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001e5fe  lea     eax, [rsi-1]
0x18001e601  test    eax, eax
0x18001e603  jnz     loc_18001E71C
0x18001e609  mov     ecx, esi
0x18001e60b  call    ?LoadLoadBalancingIfNeeded@@YAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@@Z; LoadLoadBalancingIfNeeded(__MIDL___MIDL_itf_catsrv_0000_0004_0001)
0x18001e610  mov     ebx, eax
0x18001e612  test    eax, eax
0x18001e614  js      loc_18001E718
0x18001e61a  test    rdi, rdi
0x18001e61d  jz      loc_18001E71C
0x18001e623  lea     rdx, [rsi+rsi*4]
0x18001e627  xor     ecx, ecx; lpMachineName
0x18001e629  add     rdx, rdx
0x18001e62c  lea     rsi, ?csServices@@3PAUcsServiceInfo@@A; csServiceInfo near * csServices
0x18001e633  mov     r8d, 80000001h; dwDesiredAccess
0x18001e639  mov     rsi, [rsi+rdx*8-50h]
0x18001e63e  xor     edx, edx; lpDatabaseName
0x18001e640  mov     dword ptr [rdi], 7
0x18001e646  call    cs:__imp_OpenSCManagerW
0x18001e64c  mov     rbp, rax
0x18001e64f  test    rax, rax
0x18001e652  jnz     short loc_18001E65E
0x18001e654  mov     ebx, 8000FFFFh
0x18001e659  jmp     loc_18001E718
0x18001e65e  mov     r8d, 84h; dwDesiredAccess
0x18001e664  mov     rdx, rsi; lpServiceName
0x18001e667  mov     rcx, rbp; hSCManager
0x18001e66a  call    cs:__imp_OpenServiceW
0x18001e670  mov     rsi, rax
0x18001e673  test    rax, rax
0x18001e676  jz      loc_18001E701
0x18001e67c  lea     r8, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18001e681  mov     edx, 4; dwControl
0x18001e686  mov     rcx, rax; hService
0x18001e689  call    cs:__imp_ControlService
0x18001e68f  test    eax, eax
0x18001e691  jz      short loc_18001E6A0
0x18001e693  mov     ecx, [rsp+68h+ServiceStatus.dwCurrentState]
0x18001e697  call    ?utConvertToServiceState@@YA?AW4__MIDL___MIDL_itf_catsrv_0000_0004_0002@@K@Z; utConvertToServiceState(ulong)
0x18001e69c  mov     [rdi], eax
0x18001e69e  jmp     short loc_18001E701
0x18001e6a0  call    cs:__imp_GetLastError
0x18001e6a6  mov     dword ptr [rdi], 7
0x18001e6ac  sub     eax, 5
0x18001e6af  jz      short loc_18001E6FC
0x18001e6b1  sub     eax, 416h
0x18001e6b6  jz      short loc_18001E6CC
0x18001e6b8  sub     eax, 1
0x18001e6bb  jz      short loc_18001E6CC
0x18001e6bd  sub     eax, 1
0x18001e6c0  jz      short loc_18001E6DD
0x18001e6c2  sub     eax, 8
0x18001e6c5  jz      short loc_18001E6DD
0x18001e6c7  cmp     eax, 1
0x18001e6ca  jz      short loc_18001E6D3
0x18001e6cc  mov     ebx, 8000FFFFh
0x18001e6d1  jmp     short loc_18001E701
0x18001e6d3  mov     dword ptr [rdi], 0
0x18001e6d9  xor     ebx, ebx
0x18001e6db  jmp     short loc_18001E701
0x18001e6dd  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18001e6e2  mov     rcx, rsi; hService
0x18001e6e5  call    cs:__imp_QueryServiceStatus
0x18001e6eb  test    eax, eax
0x18001e6ed  jz      short loc_18001E6CC
0x18001e6ef  mov     ecx, [rsp+68h+ServiceStatus.dwCurrentState]
0x18001e6f3  call    ?utConvertToServiceState@@YA?AW4__MIDL___MIDL_itf_catsrv_0000_0004_0002@@K@Z; utConvertToServiceState(ulong)
0x18001e6f8  mov     [rdi], eax
0x18001e6fa  jmp     short loc_18001E6D9
0x18001e6fc  mov     ebx, 80070005h
0x18001e701  mov     rcx, rbp; hSCObject
0x18001e704  call    cs:__imp_CloseServiceHandle
0x18001e70a  test    rsi, rsi
0x18001e70d  jz      short loc_18001E718
0x18001e70f  mov     rcx, rsi; hSCObject
0x18001e712  call    cs:__imp_CloseServiceHandle
0x18001e718  mov     eax, ebx
0x18001e71a  jmp     short loc_18001E721
0x18001e71c  mov     eax, 80070057h
0x18001e721  mov     rcx, [rsp+68h+var_28]
0x18001e726  xor     rcx, rsp; StackCookie
0x18001e729  call    __security_check_cookie
0x18001e72e  mov     rbx, [rsp+68h+arg_0]
0x18001e733  add     rsp, 50h
0x18001e737  pop     rdi
0x18001e738  pop     rsi
0x18001e739  pop     rbp
0x18001e73a  retn
```
