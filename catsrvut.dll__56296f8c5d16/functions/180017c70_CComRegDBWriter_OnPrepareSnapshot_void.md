# CComRegDBWriter::OnPrepareSnapshot(void)

- ea: `0x180017c70`
- end: `0x180017d0a`
- name: `?OnPrepareSnapshot@CComRegDBWriter@@UEAA_NXZ`
- size: `154`
- prototype: `bool __fastcall(CComRegDBWriter *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180017c70`
- `0x180055880`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180017c97`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180017c97`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180017cbc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180017cea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180017cbc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180017cea`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180017cb0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180017cb0`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180017ce1`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180017ce1`

## string_xrefs

- `0x180017ca3`: `COMSysApp`

## pseudocode

```c
char __fastcall CComRegDBWriter::OnPrepareSnapshot(CComRegDBWriter *this)
{
  SC_HANDLE v1; // rbx
  SC_HANDLE v2; // rdi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  if ( *((_DWORD *)this + 4) )
  {
    v1 = OpenSCManagerW(0, 0, 1u);
    v2 = OpenServiceW(v1, L"COMSysApp", 0xF003Fu);
    CloseServiceHandle(v1);
    if ( v2 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      ControlService(v2, 1u, &ServiceStatus);
      CloseServiceHandle(v2);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180017c70  mov     [rsp+arg_0], rbx
0x180017c75  push    rdi
0x180017c76  sub     rsp, 50h
0x180017c7a  mov     rax, cs:__security_cookie
0x180017c81  xor     rax, rsp
0x180017c84  mov     [rsp+58h+var_18], rax
0x180017c89  cmp     dword ptr [rcx+10h], 0
0x180017c8d  jz      short loc_180017CF0
0x180017c8f  xor     edx, edx; lpDatabaseName
0x180017c91  xor     ecx, ecx; lpMachineName
0x180017c93  lea     r8d, [rdx+1]; dwDesiredAccess
0x180017c97  call    cs:__imp_OpenSCManagerW
0x180017c9d  mov     r8d, 0F003Fh; dwDesiredAccess
0x180017ca3  lea     rdx, ServiceName; "COMSysApp"
0x180017caa  mov     rcx, rax; hSCManager
0x180017cad  mov     rbx, rax
0x180017cb0  call    cs:__imp_OpenServiceW
0x180017cb6  mov     rcx, rbx; hSCObject
0x180017cb9  mov     rdi, rax
0x180017cbc  call    cs:__imp_CloseServiceHandle
0x180017cc2  test    rdi, rdi
0x180017cc5  jz      short loc_180017CF0
0x180017cc7  xorps   xmm0, xmm0
0x180017cca  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180017ccf  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180017cd4  mov     edx, 1; dwControl
0x180017cd9  mov     rcx, rdi; hService
0x180017cdc  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180017ce1  call    cs:__imp_ControlService
0x180017ce7  mov     rcx, rdi; hSCObject
0x180017cea  call    cs:__imp_CloseServiceHandle
0x180017cf0  mov     al, 1
0x180017cf2  mov     rcx, [rsp+58h+var_18]
0x180017cf7  xor     rcx, rsp; StackCookie
0x180017cfa  call    __security_check_cookie
0x180017cff  mov     rbx, [rsp+58h+arg_0]
0x180017d04  add     rsp, 50h
0x180017d08  pop     rdi
0x180017d09  retn
```
