# NetpIsServiceStarted

- ea: `0x18008eb78`
- end: `0x18008ec70`
- name: `NetpIsServiceStarted`
- size: `248`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800747cc`
- `0x180075514`

## callees

- `0x18000e910`
- `0x18008eb78`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008eba9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008eba9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008ebd0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008ebd0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008ebe7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008ec10`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008ec21`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008ec30`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008ebe7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008ec10`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008ec21`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008ec30`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18008ebfd`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18008ebfd`

## pseudocode

```c
_BOOL8 __fastcall NetpIsServiceStarted(LPCWSTR lpServiceName)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  SC_HANDLE v7; // rcx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( !v2 )
    return 0;
  v5 = OpenServiceW(v2, lpServiceName, 4u);
  v6 = v5;
  if ( !v5 )
  {
    v7 = v3;
LABEL_5:
    CloseServiceHandle(v7);
    return 0;
  }
  if ( !QueryServiceStatus(v5, &ServiceStatus) )
  {
    CloseServiceHandle(v3);
    v7 = v6;
    goto LABEL_5;
  }
  CloseServiceHandle(v3);
  CloseServiceHandle(v6);
  return ServiceStatus.dwCurrentState - 4 <= 2 || ServiceStatus.dwCurrentState == 7;
}

```

## disassembly

```asm
0x18008eb78  mov     [rsp+arg_8], rbx
0x18008eb7d  push    rdi
0x18008eb7e  sub     rsp, 50h
0x18008eb82  mov     rax, cs:__security_cookie
0x18008eb89  xor     rax, rsp
0x18008eb8c  mov     [rsp+58h+var_18], rax
0x18008eb91  xorps   xmm0, xmm0
0x18008eb94  xor     edx, edx; lpDatabaseName
0x18008eb96  mov     rdi, rcx
0x18008eb99  xor     ecx, ecx; lpMachineName
0x18008eb9b  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18008eba0  lea     r8d, [rdx+1]; dwDesiredAccess
0x18008eba4  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18008eba9  call    cs:__imp_OpenSCManagerW
0x18008ebb0  nop     dword ptr [rax+rax+00h]
0x18008ebb5  mov     rbx, rax
0x18008ebb8  test    rax, rax
0x18008ebbb  jnz     short loc_18008EBC4
0x18008ebbd  xor     eax, eax
0x18008ebbf  jmp     loc_18008EC57
0x18008ebc4  mov     r8d, 4; dwDesiredAccess
0x18008ebca  mov     rdx, rdi; lpServiceName
0x18008ebcd  mov     rcx, rbx; hSCManager
0x18008ebd0  call    cs:__imp_OpenServiceW
0x18008ebd7  nop     dword ptr [rax+rax+00h]
0x18008ebdc  mov     rdi, rax
0x18008ebdf  test    rax, rax
0x18008ebe2  jnz     short loc_18008EBF5
0x18008ebe4  mov     rcx, rbx; hSCObject
0x18008ebe7  call    cs:__imp_CloseServiceHandle
0x18008ebee  nop     dword ptr [rax+rax+00h]
0x18008ebf3  jmp     short loc_18008EBBD
0x18008ebf5  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18008ebfa  mov     rcx, rdi; hService
0x18008ebfd  call    cs:__imp_QueryServiceStatus
0x18008ec04  nop     dword ptr [rax+rax+00h]
0x18008ec09  mov     rcx, rbx; hSCObject
0x18008ec0c  test    eax, eax
0x18008ec0e  jnz     short loc_18008EC21
0x18008ec10  call    cs:__imp_CloseServiceHandle
0x18008ec17  nop     dword ptr [rax+rax+00h]
0x18008ec1c  mov     rcx, rdi
0x18008ec1f  jmp     short loc_18008EBE7
0x18008ec21  call    cs:__imp_CloseServiceHandle
0x18008ec28  nop     dword ptr [rax+rax+00h]
0x18008ec2d  mov     rcx, rdi; hSCObject
0x18008ec30  call    cs:__imp_CloseServiceHandle
0x18008ec37  nop     dword ptr [rax+rax+00h]
0x18008ec3c  mov     ecx, [rsp+58h+ServiceStatus.dwCurrentState]
0x18008ec40  lea     eax, [rcx-4]
0x18008ec43  cmp     eax, 2
0x18008ec46  jbe     short loc_18008EC52
0x18008ec48  xor     eax, eax
0x18008ec4a  cmp     ecx, 7
0x18008ec4d  setz    al
0x18008ec50  jmp     short loc_18008EC57
0x18008ec52  mov     eax, 1
0x18008ec57  mov     rcx, [rsp+58h+var_18]
0x18008ec5c  xor     rcx, rsp; StackCookie
0x18008ec5f  call    __security_check_cookie
0x18008ec64  mov     rbx, [rsp+58h+arg_8]
0x18008ec69  add     rsp, 50h
0x18008ec6d  pop     rdi
0x18008ec6e  retn
```
