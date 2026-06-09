# AicpStartAIS(ulong)

- ea: `0x180098eac`
- end: `0x180098fd7`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `299`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180098a44`

## callees

- `0x18004e850`
- `0x18004f533`
- `0x18004f642`
- `0x180098eac`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180098f09`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180098f09`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180098ed9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180098ed9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180098fa3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180098fb2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180098fa3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180098fb2`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180098f31`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180098f31`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180098f5e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180098f5e`

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
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"AppInfo", 0x14u);
    v4 = v3;
    if ( v3 )
    {
      if ( StartServiceW(v3, 0, 0) || (dwWin32ExitCode = GetLastError_0(), dwWin32ExitCode == 1056) )
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
          Sleep_0(0x1F4u);
          if ( (unsigned int)++v5 > 0xA )
            goto LABEL_16;
        }
        dwWin32ExitCode = GetLastError_0();
      }
LABEL_16:
      CloseServiceHandle(v4);
    }
    else
    {
      dwWin32ExitCode = GetLastError_0();
    }
    CloseServiceHandle(v1);
  }
  else
  {
    return GetLastError_0();
  }
  return dwWin32ExitCode;
}

```

## disassembly

```asm
0x180098eac  push    rbx
0x180098eae  push    rbp
0x180098eaf  push    rsi
0x180098eb0  push    rdi
0x180098eb1  sub     rsp, 58h
0x180098eb5  mov     rax, cs:__security_cookie
0x180098ebc  xor     rax, rsp
0x180098ebf  mov     [rsp+78h+var_38], rax
0x180098ec4  xorps   xmm0, xmm0
0x180098ec7  xor     edx, edx; lpDatabaseName
0x180098ec9  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180098ece  xor     ecx, ecx; lpMachineName
0x180098ed0  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180098ed5  lea     r8d, [rdx+1]; dwDesiredAccess
0x180098ed9  call    cs:__imp_OpenSCManagerW
0x180098ee0  nop     dword ptr [rax+rax+00h]
0x180098ee5  mov     rbp, rax
0x180098ee8  test    rax, rax
0x180098eeb  jnz     short loc_180098EF9
0x180098eed  call    GetLastError_0
0x180098ef2  mov     ebx, eax
0x180098ef4  jmp     loc_180098FBE
0x180098ef9  mov     r8d, 14h; dwDesiredAccess
0x180098eff  lea     rdx, aAppinfo; "AppInfo"
0x180098f06  mov     rcx, rbp; hSCManager
0x180098f09  call    cs:__imp_OpenServiceW
0x180098f10  nop     dword ptr [rax+rax+00h]
0x180098f15  mov     rsi, rax
0x180098f18  test    rax, rax
0x180098f1b  jnz     short loc_180098F29
0x180098f1d  call    GetLastError_0
0x180098f22  mov     ebx, eax
0x180098f24  jmp     loc_180098FAF
0x180098f29  xor     r8d, r8d; lpServiceArgVectors
0x180098f2c  xor     edx, edx; dwNumServiceArgs
0x180098f2e  mov     rcx, rsi; hService
0x180098f31  call    cs:__imp_StartServiceW
0x180098f38  nop     dword ptr [rax+rax+00h]
0x180098f3d  test    eax, eax
0x180098f3f  jnz     short loc_180098F4F
0x180098f41  call    GetLastError_0
0x180098f46  mov     ebx, eax
0x180098f48  cmp     eax, 420h
0x180098f4d  jnz     short loc_180098FA0
0x180098f4f  xor     edi, edi
0x180098f51  mov     ebx, 5B4h
0x180098f56  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180098f5b  mov     rcx, rsi; hService
0x180098f5e  call    cs:__imp_QueryServiceStatus
0x180098f65  nop     dword ptr [rax+rax+00h]
0x180098f6a  test    eax, eax
0x180098f6c  jz      short loc_180098F99
0x180098f6e  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x180098f73  jz      short loc_180098F95
0x180098f75  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x180098f7a  jz      short loc_180098F8F
0x180098f7c  mov     ecx, 1F4h; dwMilliseconds
0x180098f81  call    Sleep_0
0x180098f86  inc     edi
0x180098f88  cmp     edi, 0Ah
0x180098f8b  jbe     short loc_180098F56
0x180098f8d  jmp     short loc_180098FA0
0x180098f8f  mov     ebx, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x180098f93  jmp     short loc_180098FA0
0x180098f95  xor     ebx, ebx
0x180098f97  jmp     short loc_180098FA0
0x180098f99  call    GetLastError_0
0x180098f9e  mov     ebx, eax
0x180098fa0  mov     rcx, rsi; hSCObject
0x180098fa3  call    cs:__imp_CloseServiceHandle
0x180098faa  nop     dword ptr [rax+rax+00h]
0x180098faf  mov     rcx, rbp; hSCObject
0x180098fb2  call    cs:__imp_CloseServiceHandle
0x180098fb9  nop     dword ptr [rax+rax+00h]
0x180098fbe  mov     eax, ebx
0x180098fc0  mov     rcx, [rsp+78h+var_38]
0x180098fc5  xor     rcx, rsp; StackCookie
0x180098fc8  call    __security_check_cookie
0x180098fcd  add     rsp, 58h
0x180098fd1  pop     rdi
0x180098fd2  pop     rsi
0x180098fd3  pop     rbp
0x180098fd4  pop     rbx
0x180098fd5  retn
```
