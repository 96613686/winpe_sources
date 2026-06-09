# StopTunnelDriver(void)

- ea: `0x18001f544`
- end: `0x18001f6cf`
- name: `?StopTunnelDriver@@YAKXZ`
- size: `395`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001e9cc`
- `0x18001f404`

## callees

- `0x18000d7c0`
- `0x18001f544`
- `0x18004b5f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f578`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f578`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f6a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f6a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f61b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f65c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f61b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f65c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f598`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f598`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001f607`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001f607`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f681`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f690`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f681`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f690`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001f5bc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001f5bc`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001f64c`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001f64c`

## string_xrefs

- `0x18001f5b3`: `ServicesActive`
- `0x18001f5dc`: `Failed to open handle to SCM 0x%x`
- `0x18001f627`: `Failed to open handle to tunnel service 0x%x`
- `0x18001f668`: `Failed to stop tunnel service 0x%x`

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
0x18001f544  mov     [rsp+arg_0], rbx
0x18001f549  mov     [rsp+arg_8], rsi
0x18001f54e  push    rdi
0x18001f54f  sub     rsp, 50h
0x18001f553  mov     rax, cs:__security_cookie
0x18001f55a  xor     rax, rsp
0x18001f55d  mov     [rsp+58h+var_10], rax
0x18001f562  xorps   xmm0, xmm0
0x18001f565  lea     rcx, ?ServiceControlLock@@3Vsrwlock@wil@@A; SRWLock
0x18001f56c  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001f571  xor     ebx, ebx
0x18001f573  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001f578  call    cs:__imp_AcquireSRWLockExclusive
0x18001f57f  nop     dword ptr [rax+rax+00h]
0x18001f584  add     cs:?gTunnelsStarted@@3KA, 0FFFFFFFFh; ulong gTunnelsStarted
0x18001f58b  jnz     loc_18001F69C
0x18001f591  mov     rcx, cs:?gTunnelFile@@3PEAXEA; hObject
0x18001f598  call    cs:__imp_CloseHandle
0x18001f59f  nop     dword ptr [rax+rax+00h]
0x18001f5a4  lea     r8d, [rbx+1]; dwDesiredAccess
0x18001f5a8  mov     cs:?gTunnelFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * gTunnelFile
0x18001f5b3  lea     rdx, DatabaseName; "ServicesActive"
0x18001f5ba  xor     ecx, ecx; lpMachineName
0x18001f5bc  call    cs:__imp_OpenSCManagerW
0x18001f5c3  nop     dword ptr [rax+rax+00h]
0x18001f5c8  mov     rsi, rax
0x18001f5cb  test    rax, rax
0x18001f5ce  jnz     short loc_18001F5F7
0x18001f5d0  call    cs:__imp_GetLastError
0x18001f5d7  nop     dword ptr [rax+rax+00h]
0x18001f5dc  lea     rdx, aFailedToOpenHa; "Failed to open handle to SCM 0x%x"
0x18001f5e3  mov     ecx, 800000h
0x18001f5e8  mov     r8d, eax
0x18001f5eb  mov     ebx, eax
0x18001f5ed  call    EventWrite0
0x18001f5f2  jmp     loc_18001F69C
0x18001f5f7  mov     r8d, 20h ; ' '; dwDesiredAccess
0x18001f5fd  lea     rdx, aTunnel; "tunnel"
0x18001f604  mov     rcx, rsi; hSCManager
0x18001f607  call    cs:__imp_OpenServiceW
0x18001f60e  nop     dword ptr [rax+rax+00h]
0x18001f613  mov     rdi, rax
0x18001f616  test    rax, rax
0x18001f619  jnz     short loc_18001F63F
0x18001f61b  call    cs:__imp_GetLastError
0x18001f622  nop     dword ptr [rax+rax+00h]
0x18001f627  lea     rdx, aFailedToOpenHa_0; "Failed to open handle to tunnel service"...
0x18001f62e  mov     ecx, 800000h
0x18001f633  mov     r8d, eax
0x18001f636  mov     ebx, eax
0x18001f638  call    EventWrite0
0x18001f63d  jmp     short loc_18001F68D
0x18001f63f  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001f644  mov     edx, 1; dwControl
0x18001f649  mov     rcx, rdi; hService
0x18001f64c  call    cs:__imp_ControlService
0x18001f653  nop     dword ptr [rax+rax+00h]
0x18001f658  test    eax, eax
0x18001f65a  jnz     short loc_18001F67E
0x18001f65c  call    cs:__imp_GetLastError
0x18001f663  nop     dword ptr [rax+rax+00h]
0x18001f668  lea     rdx, aFailedToStopTu; "Failed to stop tunnel service 0x%x"
0x18001f66f  mov     ecx, 800000h
0x18001f674  mov     r8d, eax
0x18001f677  mov     ebx, eax
0x18001f679  call    EventWrite0
0x18001f67e  mov     rcx, rdi; hSCObject
0x18001f681  call    cs:__imp_CloseServiceHandle
0x18001f688  nop     dword ptr [rax+rax+00h]
0x18001f68d  mov     rcx, rsi; hSCObject
0x18001f690  call    cs:__imp_CloseServiceHandle
0x18001f697  nop     dword ptr [rax+rax+00h]
0x18001f69c  lea     rcx, ?ServiceControlLock@@3Vsrwlock@wil@@A; SRWLock
0x18001f6a3  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f6aa  nop     dword ptr [rax+rax+00h]
0x18001f6af  mov     eax, ebx
0x18001f6b1  mov     rcx, [rsp+58h+var_10]
0x18001f6b6  xor     rcx, rsp; StackCookie
0x18001f6b9  call    __security_check_cookie
0x18001f6be  mov     rbx, [rsp+58h+arg_0]
0x18001f6c3  mov     rsi, [rsp+58h+arg_8]
0x18001f6c8  add     rsp, 50h
0x18001f6cc  pop     rdi
0x18001f6cd  retn
```
