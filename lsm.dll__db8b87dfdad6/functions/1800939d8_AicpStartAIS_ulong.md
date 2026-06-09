# AicpStartAIS(ulong)

- ea: `0x1800939d8`
- end: `0x180093adb`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `259`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800935b8`

## callees

- `0x18004b460`
- `0x18004c123`
- `0x18004c232`
- `0x1800939d8`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180093a2f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180093a2f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180093a05`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180093a05`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093ab4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093abd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093ab4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093abd`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180093a4e`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180093a4e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180093a75`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180093a75`

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
0x1800939d8  push    rbx
0x1800939da  push    rbp
0x1800939db  push    rsi
0x1800939dc  push    rdi
0x1800939dd  sub     rsp, 58h
0x1800939e1  mov     rax, cs:__security_cookie
0x1800939e8  xor     rax, rsp
0x1800939eb  mov     [rsp+78h+var_38], rax
0x1800939f0  xorps   xmm0, xmm0
0x1800939f3  xor     edx, edx; lpDatabaseName
0x1800939f5  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800939fa  xor     ecx, ecx; lpMachineName
0x1800939fc  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180093a01  lea     r8d, [rdx+1]; dwDesiredAccess
0x180093a05  call    cs:__imp_OpenSCManagerW
0x180093a0b  mov     rbp, rax
0x180093a0e  test    rax, rax
0x180093a11  jnz     short loc_180093A1F
0x180093a13  call    GetLastError_0
0x180093a18  mov     ebx, eax
0x180093a1a  jmp     loc_180093AC3
0x180093a1f  mov     r8d, 14h; dwDesiredAccess
0x180093a25  lea     rdx, aAppinfo; "AppInfo"
0x180093a2c  mov     rcx, rbp; hSCManager
0x180093a2f  call    cs:__imp_OpenServiceW
0x180093a35  mov     rsi, rax
0x180093a38  test    rax, rax
0x180093a3b  jnz     short loc_180093A46
0x180093a3d  call    GetLastError_0
0x180093a42  mov     ebx, eax
0x180093a44  jmp     short loc_180093ABA
0x180093a46  xor     r8d, r8d; lpServiceArgVectors
0x180093a49  xor     edx, edx; dwNumServiceArgs
0x180093a4b  mov     rcx, rsi; hService
0x180093a4e  call    cs:__imp_StartServiceW
0x180093a54  test    eax, eax
0x180093a56  jnz     short loc_180093A66
0x180093a58  call    GetLastError_0
0x180093a5d  mov     ebx, eax
0x180093a5f  cmp     eax, 420h
0x180093a64  jnz     short loc_180093AB1
0x180093a66  xor     edi, edi
0x180093a68  mov     ebx, 5B4h
0x180093a6d  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180093a72  mov     rcx, rsi; hService
0x180093a75  call    cs:__imp_QueryServiceStatus
0x180093a7b  test    eax, eax
0x180093a7d  jz      short loc_180093AAA
0x180093a7f  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x180093a84  jz      short loc_180093AA6
0x180093a86  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x180093a8b  jz      short loc_180093AA0
0x180093a8d  mov     ecx, 1F4h; dwMilliseconds
0x180093a92  call    Sleep_0
0x180093a97  inc     edi
0x180093a99  cmp     edi, 0Ah
0x180093a9c  jbe     short loc_180093A6D
0x180093a9e  jmp     short loc_180093AB1
0x180093aa0  mov     ebx, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x180093aa4  jmp     short loc_180093AB1
0x180093aa6  xor     ebx, ebx
0x180093aa8  jmp     short loc_180093AB1
0x180093aaa  call    GetLastError_0
0x180093aaf  mov     ebx, eax
0x180093ab1  mov     rcx, rsi; hSCObject
0x180093ab4  call    cs:__imp_CloseServiceHandle
0x180093aba  mov     rcx, rbp; hSCObject
0x180093abd  call    cs:__imp_CloseServiceHandle
0x180093ac3  mov     eax, ebx
0x180093ac5  mov     rcx, [rsp+78h+var_38]
0x180093aca  xor     rcx, rsp; StackCookie
0x180093acd  call    __security_check_cookie
0x180093ad2  add     rsp, 58h
0x180093ad6  pop     rdi
0x180093ad7  pop     rsi
0x180093ad8  pop     rbp
0x180093ad9  pop     rbx
0x180093ada  retn
```
