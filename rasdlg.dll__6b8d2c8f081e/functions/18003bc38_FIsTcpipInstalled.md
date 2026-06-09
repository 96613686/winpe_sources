# FIsTcpipInstalled

- ea: `0x18003bc38`
- end: `0x18003bcee`
- name: `FIsTcpipInstalled`
- size: `182`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18001c2cc`

## callees

- `0x18003bc38`
- `0x18004d110`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003bc82`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003bc82`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003bcc0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003bcc9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003bcc0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003bcc9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003bc60`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003bc60`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003bca9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003bca9`

## pseudocode

```c
__int64 FIsTcpipInstalled()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  unsigned int v2; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v0 = OpenSCManagerW(0, 0, 0x80000000);
  v1 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"Tcpip", 4u);
    v4 = v3;
    if ( v3 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      v2 = 0;
      if ( QueryServiceStatus(v3, &ServiceStatus) )
        LOBYTE(v2) = ServiceStatus.dwCurrentState == 4;
      CloseServiceHandle(v4);
    }
    else
    {
      v2 = 0;
    }
    CloseServiceHandle(v1);
  }
  else
  {
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18003bc38  mov     [rsp+arg_0], rbx
0x18003bc3d  mov     [rsp+arg_8], rsi
0x18003bc42  push    rdi
0x18003bc43  sub     rsp, 50h
0x18003bc47  mov     rax, cs:__security_cookie
0x18003bc4e  xor     rax, rsp
0x18003bc51  mov     [rsp+58h+var_18], rax
0x18003bc56  xor     edx, edx; lpDatabaseName
0x18003bc58  xor     ecx, ecx; lpMachineName
0x18003bc5a  mov     r8d, 80000000h; dwDesiredAccess
0x18003bc60  call    cs:__imp_OpenSCManagerW
0x18003bc66  mov     rdi, rax
0x18003bc69  test    rax, rax
0x18003bc6c  jnz     short loc_18003BC72
0x18003bc6e  xor     ebx, ebx
0x18003bc70  jmp     short loc_18003BCCF
0x18003bc72  mov     r8d, 4; dwDesiredAccess
0x18003bc78  lea     rdx, aTcpip; "Tcpip"
0x18003bc7f  mov     rcx, rdi; hSCManager
0x18003bc82  call    cs:__imp_OpenServiceW
0x18003bc88  mov     rsi, rax
0x18003bc8b  test    rax, rax
0x18003bc8e  jnz     short loc_18003BC94
0x18003bc90  xor     ebx, ebx
0x18003bc92  jmp     short loc_18003BCC6
0x18003bc94  xorps   xmm0, xmm0
0x18003bc97  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18003bc9c  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18003bca1  mov     rcx, rsi; hService
0x18003bca4  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18003bca9  call    cs:__imp_QueryServiceStatus
0x18003bcaf  xor     ebx, ebx
0x18003bcb1  test    eax, eax
0x18003bcb3  jz      short loc_18003BCBD
0x18003bcb5  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x18003bcba  setz    bl
0x18003bcbd  mov     rcx, rsi; hSCObject
0x18003bcc0  call    cs:__imp_CloseServiceHandle
0x18003bcc6  mov     rcx, rdi; hSCObject
0x18003bcc9  call    cs:__imp_CloseServiceHandle
0x18003bccf  mov     eax, ebx
0x18003bcd1  mov     rcx, [rsp+58h+var_18]
0x18003bcd6  xor     rcx, rsp; StackCookie
0x18003bcd9  call    __security_check_cookie
0x18003bcde  mov     rbx, [rsp+58h+arg_0]
0x18003bce3  mov     rsi, [rsp+58h+arg_8]
0x18003bce8  add     rsp, 50h
0x18003bcec  pop     rdi
0x18003bced  retn
```
