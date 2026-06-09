# StopService(void)

- ea: `0x18002a898`
- end: `0x18002aa10`
- name: `?StopService@@YAXXZ`
- size: `376`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002aa18`

## callees

- `0x180029fb0`
- `0x18002a898`
- `0x18002d200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a931`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a9af`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a9af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a8c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a9ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a8c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a9ce`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002a8d3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002a8d3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a9e5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a9ee`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a9e5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a9ee`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a8fa`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a923`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a8fa`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a923`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18002a9a1`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18002a9a1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002a9bd`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002a9bd`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18002a98e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18002a98e`

## string_xrefs

- `0x18002a8eb`: `SharedAccess`
- `0x18002a917`: `SharedAccess`

## pseudocode

```c
void StopService(void)
{
  DWORD TickCount; // ebp
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rdi
  int v3; // esi
  SC_HANDLE v4; // rbx
  _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  TickCount = GetTickCount();
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = 1;
    v4 = OpenServiceW(v1, L"SharedAccess", 0x1A7u);
    if ( v4 || (unsigned int)IsWcmsvc() && (v3 = 0, (v4 = OpenServiceW(v2, L"SharedAccess", 0x1A5u)) != 0) )
    {
      if ( v3 )
        ChangeServiceConfigW(v4, 0xFFFFFFFF, 3u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0);
      do
      {
        if ( !ControlService(v4, 1u, &ServiceStatus) )
          break;
        Sleep(ServiceStatus.dwWaitHint);
        if ( !QueryServiceStatus(v4, &ServiceStatus) )
          break;
      }
      while ( ServiceStatus.dwCurrentState != 1 && GetTickCount() - TickCount < 0xBB8 );
      if ( v4 )
        CloseServiceHandle(v4);
    }
    else
    {
      GetLastError();
    }
    CloseServiceHandle(v2);
  }
}

```

## disassembly

```asm
0x18002a898  push    rbx
0x18002a89a  push    rbp
0x18002a89b  push    rsi
0x18002a89c  push    rdi
0x18002a89d  sub     rsp, 98h
0x18002a8a4  mov     rax, cs:__security_cookie
0x18002a8ab  xor     rax, rsp
0x18002a8ae  mov     [rsp+0B8h+var_38], rax
0x18002a8b6  xorps   xmm0, xmm0
0x18002a8b9  movups  xmmword ptr [rsp+0B8h+ServiceStatus.dwServiceType], xmm0
0x18002a8be  movups  xmmword ptr [rsp+0B8h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002a8c3  call    cs:__imp_GetTickCount
0x18002a8c9  xor     edx, edx; lpDatabaseName
0x18002a8cb  xor     ecx, ecx; lpMachineName
0x18002a8cd  mov     ebp, eax
0x18002a8cf  lea     r8d, [rdx+1]; dwDesiredAccess
0x18002a8d3  call    cs:__imp_OpenSCManagerW
0x18002a8d9  mov     rdi, rax
0x18002a8dc  test    rax, rax
0x18002a8df  jz      loc_18002A9F4
0x18002a8e5  mov     r8d, 1A7h; dwDesiredAccess
0x18002a8eb  lea     rdx, ?c_wszSharedAccess@@3QBGB; "SharedAccess"
0x18002a8f2  mov     rcx, rax; hSCManager
0x18002a8f5  mov     esi, 1
0x18002a8fa  call    cs:__imp_OpenServiceW
0x18002a900  mov     rbx, rax
0x18002a903  test    rax, rax
0x18002a906  jnz     short loc_18002A93C
0x18002a908  call    ?IsWcmsvc@@YAHXZ; IsWcmsvc(void)
0x18002a90d  test    eax, eax
0x18002a90f  jz      short loc_18002A931
0x18002a911  mov     r8d, 1A5h; dwDesiredAccess
0x18002a917  lea     rdx, ?c_wszSharedAccess@@3QBGB; "SharedAccess"
0x18002a91e  mov     rcx, rdi; hSCManager
0x18002a921  xor     esi, esi
0x18002a923  call    cs:__imp_OpenServiceW
0x18002a929  mov     rbx, rax
0x18002a92c  test    rax, rax
0x18002a92f  jnz     short loc_18002A93C
0x18002a931  call    cs:__imp_GetLastError
0x18002a937  jmp     loc_18002A9EB
0x18002a93c  test    esi, esi
0x18002a93e  jz      short loc_18002A994
0x18002a940  mov     [rsp+0B8h+lpDisplayName], 0; lpDisplayName
0x18002a949  or      edx, 0FFFFFFFFh; dwServiceType
0x18002a94c  mov     [rsp+0B8h+lpPassword], 0; lpPassword
0x18002a955  mov     r9d, edx; dwErrorControl
0x18002a958  mov     [rsp+0B8h+lpServiceStartName], 0; lpServiceStartName
0x18002a961  mov     r8d, 3; dwStartType
0x18002a967  mov     [rsp+0B8h+lpDependencies], 0; lpDependencies
0x18002a970  mov     rcx, rbx; hService
0x18002a973  mov     [rsp+0B8h+lpdwTagId], 0; lpdwTagId
0x18002a97c  mov     [rsp+0B8h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18002a985  mov     [rsp+0B8h+lpBinaryPathName], 0; lpBinaryPathName
0x18002a98e  call    cs:__imp_ChangeServiceConfigW
0x18002a994  lea     r8, [rsp+0B8h+ServiceStatus]; lpServiceStatus
0x18002a999  mov     edx, 1; dwControl
0x18002a99e  mov     rcx, rbx; hService
0x18002a9a1  call    cs:__imp_ControlService
0x18002a9a7  test    eax, eax
0x18002a9a9  jz      short loc_18002A9DD
0x18002a9ab  mov     ecx, [rsp+0B8h+ServiceStatus.dwWaitHint]; dwMilliseconds
0x18002a9af  call    cs:__imp_Sleep
0x18002a9b5  lea     rdx, [rsp+0B8h+ServiceStatus]; lpServiceStatus
0x18002a9ba  mov     rcx, rbx; hService
0x18002a9bd  call    cs:__imp_QueryServiceStatus
0x18002a9c3  test    eax, eax
0x18002a9c5  jz      short loc_18002A9DD
0x18002a9c7  cmp     [rsp+0B8h+ServiceStatus.dwCurrentState], 1
0x18002a9cc  jz      short loc_18002A9DD
0x18002a9ce  call    cs:__imp_GetTickCount
0x18002a9d4  sub     eax, ebp
0x18002a9d6  cmp     eax, 0BB8h
0x18002a9db  jb      short loc_18002A994
0x18002a9dd  test    rbx, rbx
0x18002a9e0  jz      short loc_18002A9EB
0x18002a9e2  mov     rcx, rbx; hSCObject
0x18002a9e5  call    cs:__imp_CloseServiceHandle
0x18002a9eb  mov     rcx, rdi; hSCObject
0x18002a9ee  call    cs:__imp_CloseServiceHandle
0x18002a9f4  mov     rcx, [rsp+0B8h+var_38]
0x18002a9fc  xor     rcx, rsp; StackCookie
0x18002a9ff  call    __security_check_cookie
0x18002aa04  add     rsp, 98h
0x18002aa0b  pop     rdi
0x18002aa0c  pop     rsi
0x18002aa0d  pop     rbp
0x18002aa0e  pop     rbx
0x18002aa0f  retn
```
