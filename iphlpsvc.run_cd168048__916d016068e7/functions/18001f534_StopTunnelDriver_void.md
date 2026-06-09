# StopTunnelDriver(void)

- ea: `0x18001f534`
- end: `0x18001f6bf`
- name: `?StopTunnelDriver@@YAKXZ`
- size: `395`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001e9bc`
- `0x18001f3f4`

## callees

- `0x18000d7b0`
- `0x18001f534`
- `0x18004b630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f568`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f568`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f693`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f60b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f64c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f60b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f64c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f588`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f588`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001f5f7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001f5f7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f671`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f680`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f671`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f680`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001f5ac`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001f5ac`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001f63c`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001f63c`

## string_xrefs

- `0x18001f5a3`: `ServicesActive`
- `0x18001f5cc`: `Failed to open handle to SCM 0x%x`
- `0x18001f617`: `Failed to open handle to tunnel service 0x%x`
- `0x18001f658`: `Failed to stop tunnel service 0x%x`

## pseudocode

```c
__int64 StopTunnelDriver(void)
{
  __int64 LastError; // rbx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-30h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  LODWORD(LastError) = 0;
  AcquireSRWLockExclusive(&ServiceControlLock);
  if ( !--gTunnelsStarted )
  {
    CloseHandle(gTunnelFile);
    gTunnelFile = (HANDLE)-1LL;
    v1 = OpenSCManagerW(0, L"ServicesActive", 1u);
    v2 = v1;
    if ( v1 )
    {
      v3 = OpenServiceW(v1, L"tunnel", 0x20u);
      v4 = v3;
      if ( v3 )
      {
        if ( !ControlService(v3, 1u, &ServiceStatus) )
        {
          LastError = GetLastError();
          EventWrite0(0x800000, L"Failed to stop tunnel service 0x%x", LastError);
        }
        CloseServiceHandle(v4);
      }
      else
      {
        LastError = GetLastError();
        EventWrite0(0x800000, L"Failed to open handle to tunnel service 0x%x", LastError);
      }
      CloseServiceHandle(v2);
    }
    else
    {
      LastError = GetLastError();
      EventWrite0(0x800000, L"Failed to open handle to SCM 0x%x", LastError);
    }
  }
  ReleaseSRWLockExclusive(&ServiceControlLock);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001f534  mov     [rsp+arg_0], rbx
0x18001f539  mov     [rsp+arg_8], rsi
0x18001f53e  push    rdi
0x18001f53f  sub     rsp, 50h
0x18001f543  mov     rax, cs:__security_cookie
0x18001f54a  xor     rax, rsp
0x18001f54d  mov     [rsp+58h+var_10], rax
0x18001f552  xorps   xmm0, xmm0
0x18001f555  lea     rcx, ?ServiceControlLock@@3Vsrwlock@wil@@A; SRWLock
0x18001f55c  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001f561  xor     ebx, ebx
0x18001f563  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001f568  call    cs:__imp_AcquireSRWLockExclusive
0x18001f56f  nop     dword ptr [rax+rax+00h]
0x18001f574  add     cs:?gTunnelsStarted@@3KA, 0FFFFFFFFh; ulong gTunnelsStarted
0x18001f57b  jnz     loc_18001F68C
0x18001f581  mov     rcx, cs:?gTunnelFile@@3PEAXEA; hObject
0x18001f588  call    cs:__imp_CloseHandle
0x18001f58f  nop     dword ptr [rax+rax+00h]
0x18001f594  lea     r8d, [rbx+1]; dwDesiredAccess
0x18001f598  mov     cs:?gTunnelFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * gTunnelFile
0x18001f5a3  lea     rdx, DatabaseName; "ServicesActive"
0x18001f5aa  xor     ecx, ecx; lpMachineName
0x18001f5ac  call    cs:__imp_OpenSCManagerW
0x18001f5b3  nop     dword ptr [rax+rax+00h]
0x18001f5b8  mov     rsi, rax
0x18001f5bb  test    rax, rax
0x18001f5be  jnz     short loc_18001F5E7
0x18001f5c0  call    cs:__imp_GetLastError
0x18001f5c7  nop     dword ptr [rax+rax+00h]
0x18001f5cc  lea     rdx, aFailedToOpenHa; "Failed to open handle to SCM 0x%x"
0x18001f5d3  mov     ecx, 800000h
0x18001f5d8  mov     r8d, eax
0x18001f5db  mov     ebx, eax
0x18001f5dd  call    EventWrite0
0x18001f5e2  jmp     loc_18001F68C
0x18001f5e7  mov     r8d, 20h ; ' '; dwDesiredAccess
0x18001f5ed  lea     rdx, aTunnel; "tunnel"
0x18001f5f4  mov     rcx, rsi; hSCManager
0x18001f5f7  call    cs:__imp_OpenServiceW
0x18001f5fe  nop     dword ptr [rax+rax+00h]
0x18001f603  mov     rdi, rax
0x18001f606  test    rax, rax
0x18001f609  jnz     short loc_18001F62F
0x18001f60b  call    cs:__imp_GetLastError
0x18001f612  nop     dword ptr [rax+rax+00h]
0x18001f617  lea     rdx, aFailedToOpenHa_0; "Failed to open handle to tunnel service"...
0x18001f61e  mov     ecx, 800000h
0x18001f623  mov     r8d, eax
0x18001f626  mov     ebx, eax
0x18001f628  call    EventWrite0
0x18001f62d  jmp     short loc_18001F67D
0x18001f62f  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001f634  mov     edx, 1; dwControl
0x18001f639  mov     rcx, rdi; hService
0x18001f63c  call    cs:__imp_ControlService
0x18001f643  nop     dword ptr [rax+rax+00h]
0x18001f648  test    eax, eax
0x18001f64a  jnz     short loc_18001F66E
0x18001f64c  call    cs:__imp_GetLastError
0x18001f653  nop     dword ptr [rax+rax+00h]
0x18001f658  lea     rdx, aFailedToStopTu; "Failed to stop tunnel service 0x%x"
0x18001f65f  mov     ecx, 800000h
0x18001f664  mov     r8d, eax
0x18001f667  mov     ebx, eax
0x18001f669  call    EventWrite0
0x18001f66e  mov     rcx, rdi; hSCObject
0x18001f671  call    cs:__imp_CloseServiceHandle
0x18001f678  nop     dword ptr [rax+rax+00h]
0x18001f67d  mov     rcx, rsi; hSCObject
0x18001f680  call    cs:__imp_CloseServiceHandle
0x18001f687  nop     dword ptr [rax+rax+00h]
0x18001f68c  lea     rcx, ?ServiceControlLock@@3Vsrwlock@wil@@A; SRWLock
0x18001f693  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f69a  nop     dword ptr [rax+rax+00h]
0x18001f69f  mov     eax, ebx
0x18001f6a1  mov     rcx, [rsp+58h+var_10]
0x18001f6a6  xor     rcx, rsp; StackCookie
0x18001f6a9  call    __security_check_cookie
0x18001f6ae  mov     rbx, [rsp+58h+arg_0]
0x18001f6b3  mov     rsi, [rsp+58h+arg_8]
0x18001f6b8  add     rsp, 50h
0x18001f6bc  pop     rdi
0x18001f6bd  retn
```
