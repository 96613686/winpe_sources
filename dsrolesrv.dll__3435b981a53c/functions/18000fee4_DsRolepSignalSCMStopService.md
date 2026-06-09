# DsRolepSignalSCMStopService

- ea: `0x18000fee4`
- end: `0x18000ffa2`
- name: `DsRolepSignalSCMStopService`
- size: `190`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000f510`

## callees

- `0x18000fee4`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff64`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000ff3f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000ff3f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000ff17`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000ff17`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000ff6f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000ff7d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000ff6f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000ff7d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000ff5a`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000ff5a`

## pseudocode

```c
__int64 DsRolepSignalSCMStopService()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  DWORD LastError; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"DsRoleSvc", 0x20u);
    v4 = v3;
    if ( !v3 || (LastError = 0, !ControlService(v3, 1u, &ServiceStatus)) )
      LastError = GetLastError();
    CloseServiceHandle(v1);
    if ( v4 )
      CloseServiceHandle(v4);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x18000fee4  mov     [rsp+arg_0], rbx
0x18000fee9  mov     [rsp+arg_8], rsi
0x18000feee  push    rdi
0x18000feef  sub     rsp, 50h
0x18000fef3  mov     rax, cs:__security_cookie
0x18000fefa  xor     rax, rsp
0x18000fefd  mov     [rsp+58h+var_18], rax
0x18000ff02  xorps   xmm0, xmm0
0x18000ff05  xor     edx, edx; lpDatabaseName
0x18000ff07  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18000ff0c  xor     ecx, ecx; lpMachineName
0x18000ff0e  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000ff13  lea     r8d, [rdx+1]; dwDesiredAccess
0x18000ff17  call    cs:__imp_OpenSCManagerW
0x18000ff1d  mov     rsi, rax
0x18000ff20  test    rax, rax
0x18000ff23  jnz     short loc_18000FF2F
0x18000ff25  call    cs:__imp_GetLastError
0x18000ff2b  mov     ebx, eax
0x18000ff2d  jmp     short loc_18000FF83
0x18000ff2f  mov     r8d, 20h ; ' '; dwDesiredAccess
0x18000ff35  lea     rdx, ServiceName; "DsRoleSvc"
0x18000ff3c  mov     rcx, rsi; hSCManager
0x18000ff3f  call    cs:__imp_OpenServiceW
0x18000ff45  mov     rdi, rax
0x18000ff48  test    rax, rax
0x18000ff4b  jz      short loc_18000FF64
0x18000ff4d  xor     ebx, ebx
0x18000ff4f  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18000ff54  mov     rcx, rax; hService
0x18000ff57  lea     edx, [rbx+1]; dwControl
0x18000ff5a  call    cs:__imp_ControlService
0x18000ff60  test    eax, eax
0x18000ff62  jnz     short loc_18000FF6C
0x18000ff64  call    cs:__imp_GetLastError
0x18000ff6a  mov     ebx, eax
0x18000ff6c  mov     rcx, rsi; hSCObject
0x18000ff6f  call    cs:__imp_CloseServiceHandle
0x18000ff75  test    rdi, rdi
0x18000ff78  jz      short loc_18000FF83
0x18000ff7a  mov     rcx, rdi; hSCObject
0x18000ff7d  call    cs:__imp_CloseServiceHandle
0x18000ff83  mov     eax, ebx
0x18000ff85  mov     rcx, [rsp+58h+var_18]
0x18000ff8a  xor     rcx, rsp; StackCookie
0x18000ff8d  call    __security_check_cookie
0x18000ff92  mov     rbx, [rsp+58h+arg_0]
0x18000ff97  mov     rsi, [rsp+58h+arg_8]
0x18000ff9c  add     rsp, 50h
0x18000ffa0  pop     rdi
0x18000ffa1  retn
```
