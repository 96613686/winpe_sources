# AicpStartAIS(ulong)

- ea: `0x1800b0f20`
- end: `0x1800b106e`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `334`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800b137c`

## callees

- `0x180004f70`
- `0x1800b0f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0f98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0fc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0f98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0fc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1029`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b100a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b100a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b0f84`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b0f84`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b0f4d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b0f4d`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800b0fb3`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800b0fb3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b103a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b1049`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b103a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b1049`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800b0fe7`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800b0fe7`

## pseudocode

```c
__int64 __fastcall AicpStartAIS()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbp
  DWORD dwWin32ExitCode; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  int v5; // edi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"AppInfo", 0x14u);
    v4 = v3;
    if ( v3 )
    {
      if ( StartServiceW(v3, 0, 0) || (dwWin32ExitCode = GetLastError(), dwWin32ExitCode == 1056) )
      {
        v5 = 0;
        dwWin32ExitCode = 1460;
        while ( QueryServiceStatus(v4, &ServiceStatus) )
        {
          if ( ServiceStatus.dwCurrentState == 4 )
          {
            dwWin32ExitCode = 0;
            goto LABEL_16;
          }
          if ( ServiceStatus.dwCurrentState == 1 )
          {
            dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
            goto LABEL_16;
          }
          Sleep(0x1F4u);
          if ( (unsigned int)++v5 > 0xA )
            goto LABEL_16;
        }
        dwWin32ExitCode = GetLastError();
      }
LABEL_16:
      CloseServiceHandle(v4);
    }
    else
    {
      dwWin32ExitCode = GetLastError();
    }
    CloseServiceHandle(v1);
  }
  else
  {
    return GetLastError();
  }
  return dwWin32ExitCode;
}

```

## disassembly

```asm
0x1800b0f20  push    rbx
0x1800b0f22  push    rbp
0x1800b0f23  push    rsi
0x1800b0f24  push    rdi
0x1800b0f25  sub     rsp, 58h
0x1800b0f29  mov     rax, cs:__security_cookie
0x1800b0f30  xor     rax, rsp
0x1800b0f33  mov     [rsp+78h+var_38], rax
0x1800b0f38  xorps   xmm0, xmm0
0x1800b0f3b  xor     edx, edx; lpDatabaseName
0x1800b0f3d  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800b0f42  xor     ecx, ecx; lpMachineName
0x1800b0f44  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800b0f49  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800b0f4d  call    cs:__imp_OpenSCManagerW
0x1800b0f54  nop     dword ptr [rax+rax+00h]
0x1800b0f59  mov     rbp, rax
0x1800b0f5c  test    rax, rax
0x1800b0f5f  jnz     short loc_1800B0F74
0x1800b0f61  call    cs:__imp_GetLastError
0x1800b0f68  nop     dword ptr [rax+rax+00h]
0x1800b0f6d  mov     ebx, eax
0x1800b0f6f  jmp     loc_1800B1055
0x1800b0f74  mov     r8d, 14h; dwDesiredAccess
0x1800b0f7a  lea     rdx, ServiceName; "AppInfo"
0x1800b0f81  mov     rcx, rbp; hSCManager
0x1800b0f84  call    cs:__imp_OpenServiceW
0x1800b0f8b  nop     dword ptr [rax+rax+00h]
0x1800b0f90  mov     rsi, rax
0x1800b0f93  test    rax, rax
0x1800b0f96  jnz     short loc_1800B0FAB
0x1800b0f98  call    cs:__imp_GetLastError
0x1800b0f9f  nop     dword ptr [rax+rax+00h]
0x1800b0fa4  mov     ebx, eax
0x1800b0fa6  jmp     loc_1800B1046
0x1800b0fab  xor     r8d, r8d; lpServiceArgVectors
0x1800b0fae  xor     edx, edx; dwNumServiceArgs
0x1800b0fb0  mov     rcx, rsi; hService
0x1800b0fb3  call    cs:__imp_StartServiceW
0x1800b0fba  nop     dword ptr [rax+rax+00h]
0x1800b0fbf  test    eax, eax
0x1800b0fc1  jnz     short loc_1800B0FD8
0x1800b0fc3  call    cs:__imp_GetLastError
0x1800b0fca  nop     dword ptr [rax+rax+00h]
0x1800b0fcf  mov     ebx, eax
0x1800b0fd1  cmp     eax, 420h
0x1800b0fd6  jnz     short loc_1800B1037
0x1800b0fd8  xor     edi, edi
0x1800b0fda  mov     ebx, 5B4h
0x1800b0fdf  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800b0fe4  mov     rcx, rsi; hService
0x1800b0fe7  call    cs:__imp_QueryServiceStatus
0x1800b0fee  nop     dword ptr [rax+rax+00h]
0x1800b0ff3  test    eax, eax
0x1800b0ff5  jz      short loc_1800B1029
0x1800b0ff7  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x1800b0ffc  jz      short loc_1800B1025
0x1800b0ffe  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x1800b1003  jz      short loc_1800B101F
0x1800b1005  mov     ecx, 1F4h; dwMilliseconds
0x1800b100a  call    cs:__imp_Sleep
0x1800b1011  nop     dword ptr [rax+rax+00h]
0x1800b1016  inc     edi
0x1800b1018  cmp     edi, 0Ah
0x1800b101b  jbe     short loc_1800B0FDF
0x1800b101d  jmp     short loc_1800B1037
0x1800b101f  mov     ebx, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x1800b1023  jmp     short loc_1800B1037
0x1800b1025  xor     ebx, ebx
0x1800b1027  jmp     short loc_1800B1037
0x1800b1029  call    cs:__imp_GetLastError
0x1800b1030  nop     dword ptr [rax+rax+00h]
0x1800b1035  mov     ebx, eax
0x1800b1037  mov     rcx, rsi; hSCObject
0x1800b103a  call    cs:__imp_CloseServiceHandle
0x1800b1041  nop     dword ptr [rax+rax+00h]
0x1800b1046  mov     rcx, rbp; hSCObject
0x1800b1049  call    cs:__imp_CloseServiceHandle
0x1800b1050  nop     dword ptr [rax+rax+00h]
0x1800b1055  mov     eax, ebx
0x1800b1057  mov     rcx, [rsp+78h+var_38]
0x1800b105c  xor     rcx, rsp; StackCookie
0x1800b105f  call    __security_check_cookie
0x1800b1064  add     rsp, 58h
0x1800b1068  pop     rdi
0x1800b1069  pop     rsi
0x1800b106a  pop     rbp
0x1800b106b  pop     rbx
0x1800b106c  retn
```
