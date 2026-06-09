# AicpStartAIS(ulong)

- ea: `0x180042eac`
- end: `0x180042ff3`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `327`
- prototype: `unsigned int __fastcall(unsigned int dwTimeout)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180039e7c`

## callees

- `0x180042eac`
- `0x180046460`
- `0x1800475c4`
- `0x1800475e8`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180042eeb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180042eeb`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180042f43`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180042f43`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180042f1b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180042f1b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042fb3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042fc2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042fb3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042fc2`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180042f6e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180042f6e`

## pseudocode

```c
__int64 __fastcall AicpStartAIS(unsigned int dwTimeout)
{
  int v1; // esi
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbp
  unsigned int dwWin32ExitCode; // ebx
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  _SERVICE_STATUS ssService; // [rsp+20h] [rbp-38h] BYREF

  memset(&ssService, 0, sizeof(ssService));
  v1 = 0;
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v5 = OpenServiceW(v2, L"AppInfo", 0x14u);
    v6 = v5;
    if ( v5 )
    {
      if ( StartServiceW(v5, 0, 0) || (dwWin32ExitCode = GetLastError_0(), dwWin32ExitCode == 1056) )
      {
        dwWin32ExitCode = 1460;
        while ( QueryServiceStatus(v6, &ssService) )
        {
          if ( ssService.dwCurrentState == 4 )
          {
            dwWin32ExitCode = 0;
            goto $CleanExit_0;
          }
          if ( ssService.dwCurrentState == 1 )
          {
            dwWin32ExitCode = ssService.dwWin32ExitCode;
            goto $CleanExit_0;
          }
          Sleep_0(0x1F4u);
          if ( (unsigned int)++v1 > 0xA )
            goto $CleanExit_0;
        }
        dwWin32ExitCode = GetLastError_0();
      }
$CleanExit_0:
      CloseServiceHandle(v6);
    }
    else
    {
      dwWin32ExitCode = GetLastError_0();
    }
    CloseServiceHandle(v3);
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
0x180042eac  mov     r11, rsp
0x180042eaf  mov     [r11+8], rbx
0x180042eb3  mov     [r11+10h], rbp
0x180042eb7  mov     [r11+18h], rsi
0x180042ebb  push    rdi
0x180042ebc  sub     rsp, 50h
0x180042ec0  mov     rax, cs:__security_cookie
0x180042ec7  xor     rax, rsp
0x180042eca  mov     [rsp+58h+var_18], rax
0x180042ecf  xor     eax, eax
0x180042ed1  xorps   xmm0, xmm0
0x180042ed4  movups  xmmword ptr [rsp+58h+ssService.dwServiceType], xmm0
0x180042ed9  mov     [r11-28h], rax
0x180042edd  xor     esi, esi
0x180042edf  xor     edx, edx; lpDatabaseName
0x180042ee1  mov     [rsp+58h+ssService.dwWaitHint], eax
0x180042ee5  xor     ecx, ecx; lpMachineName
0x180042ee7  lea     r8d, [rsi+1]; dwDesiredAccess
0x180042eeb  call    cs:__imp_OpenSCManagerW
0x180042ef2  nop     dword ptr [rax+rax+00h]
0x180042ef7  mov     rbp, rax
0x180042efa  test    rax, rax
0x180042efd  jnz     short loc_180042F0B
0x180042eff  call    GetLastError_0
0x180042f04  mov     ebx, eax
0x180042f06  jmp     loc_180042FCE
0x180042f0b  mov     r8d, 14h; dwDesiredAccess
0x180042f11  lea     rdx, aAppinfo; "AppInfo"
0x180042f18  mov     rcx, rbp; hSCManager
0x180042f1b  call    cs:__imp_OpenServiceW
0x180042f22  nop     dword ptr [rax+rax+00h]
0x180042f27  mov     rdi, rax
0x180042f2a  test    rax, rax
0x180042f2d  jnz     short loc_180042F3B
0x180042f2f  call    GetLastError_0
0x180042f34  mov     ebx, eax
0x180042f36  jmp     loc_180042FBF
0x180042f3b  xor     r8d, r8d; lpServiceArgVectors
0x180042f3e  xor     edx, edx; dwNumServiceArgs
0x180042f40  mov     rcx, rdi; hService
0x180042f43  call    cs:__imp_StartServiceW
0x180042f4a  nop     dword ptr [rax+rax+00h]
0x180042f4f  test    eax, eax
0x180042f51  jnz     short loc_180042F61
0x180042f53  call    GetLastError_0
0x180042f58  mov     ebx, eax
0x180042f5a  cmp     eax, 420h
0x180042f5f  jnz     short $CleanExit_0
0x180042f61  mov     ebx, 5B4h
0x180042f66  lea     rdx, [rsp+58h+ssService]; lpServiceStatus
0x180042f6b  mov     rcx, rdi; hService
0x180042f6e  call    cs:__imp_QueryServiceStatus
0x180042f75  nop     dword ptr [rax+rax+00h]
0x180042f7a  test    eax, eax
0x180042f7c  jz      short loc_180042FA9
0x180042f7e  cmp     [rsp+58h+ssService.dwCurrentState], 4
0x180042f83  jz      short loc_180042FA5
0x180042f85  cmp     [rsp+58h+ssService.dwCurrentState], 1
0x180042f8a  jz      short loc_180042F9F
0x180042f8c  mov     ecx, 1F4h; dwMilliseconds
0x180042f91  call    Sleep_0
0x180042f96  inc     esi
0x180042f98  cmp     esi, 0Ah
0x180042f9b  jbe     short loc_180042F66
0x180042f9d  jmp     short $CleanExit_0
0x180042f9f  mov     ebx, [rsp+58h+ssService.dwWin32ExitCode]
0x180042fa3  jmp     short $CleanExit_0
0x180042fa5  xor     ebx, ebx
0x180042fa7  jmp     short $CleanExit_0
0x180042fa9  call    GetLastError_0
0x180042fae  mov     ebx, eax
0x180042fb0  mov     rcx, rdi; hSCObject
0x180042fb3  call    cs:__imp_CloseServiceHandle
0x180042fba  nop     dword ptr [rax+rax+00h]
0x180042fbf  mov     rcx, rbp; hSCObject
0x180042fc2  call    cs:__imp_CloseServiceHandle
0x180042fc9  nop     dword ptr [rax+rax+00h]
0x180042fce  mov     eax, ebx
0x180042fd0  mov     rcx, [rsp+58h+var_18]
0x180042fd5  xor     rcx, rsp; StackCookie
0x180042fd8  call    __security_check_cookie
0x180042fdd  mov     rbx, [rsp+58h+arg_0]
0x180042fe2  mov     rbp, [rsp+58h+arg_8]
0x180042fe7  mov     rsi, [rsp+58h+arg_10]
0x180042fec  add     rsp, 50h
0x180042ff0  pop     rdi
0x180042ff1  retn
```
