# CsControlService

- ea: `0x1800b08f0`
- end: `0x1800b0989`
- name: `CsControlService`
- size: `153`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800b0800`

## callees

- `0x1800b08f0`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b093e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b093e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b0962`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b096b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b0962`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b096b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b0920`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b0920`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800b0959`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800b0959`

## string_xrefs

- `0x1800b0934`: `SharedAccess`

## pseudocode

```c
int CsControlService()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbx
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rdi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerW(0, 0, 0xF003Fu);
  v1 = v0;
  if ( v0 )
  {
    v2 = OpenServiceW(v0, L"SharedAccess", 0xF01FFu);
    v3 = v2;
    if ( v2 )
    {
      ControlService(v2, 0x82u, &ServiceStatus);
      CloseServiceHandle(v3);
    }
    LODWORD(v0) = CloseServiceHandle(v1);
  }
  return (int)v0;
}

```

## disassembly

```asm
0x1800b08f0  mov     [rsp+arg_0], rbx
0x1800b08f5  push    rdi
0x1800b08f6  sub     rsp, 50h
0x1800b08fa  mov     rax, cs:__security_cookie
0x1800b0901  xor     rax, rsp
0x1800b0904  mov     [rsp+58h+var_18], rax
0x1800b0909  xorps   xmm0, xmm0
0x1800b090c  xor     edx, edx; lpDatabaseName
0x1800b090e  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1800b0913  xor     ecx, ecx; lpMachineName
0x1800b0915  mov     r8d, 0F003Fh; dwDesiredAccess
0x1800b091b  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800b0920  call    cs:__imp_OpenSCManagerW
0x1800b0926  mov     rbx, rax
0x1800b0929  test    rax, rax
0x1800b092c  jz      short loc_1800B0971
0x1800b092e  mov     r8d, 0F01FFh; dwDesiredAccess
0x1800b0934  lea     rdx, c_szSharedAccess; "SharedAccess"
0x1800b093b  mov     rcx, rax; hSCManager
0x1800b093e  call    cs:__imp_OpenServiceW
0x1800b0944  mov     rdi, rax
0x1800b0947  test    rax, rax
0x1800b094a  jz      short loc_1800B0968
0x1800b094c  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800b0951  mov     edx, 82h; dwControl
0x1800b0956  mov     rcx, rax; hService
0x1800b0959  call    cs:__imp_ControlService
0x1800b095f  mov     rcx, rdi; hSCObject
0x1800b0962  call    cs:__imp_CloseServiceHandle
0x1800b0968  mov     rcx, rbx; hSCObject
0x1800b096b  call    cs:__imp_CloseServiceHandle
0x1800b0971  mov     rcx, [rsp+58h+var_18]
0x1800b0976  xor     rcx, rsp; StackCookie
0x1800b0979  call    __security_check_cookie
0x1800b097e  mov     rbx, [rsp+58h+arg_0]
0x1800b0983  add     rsp, 50h
0x1800b0987  pop     rdi
0x1800b0988  retn
```
