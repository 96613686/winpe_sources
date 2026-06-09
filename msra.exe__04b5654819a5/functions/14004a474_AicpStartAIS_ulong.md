# AicpStartAIS(ulong)

- ea: `0x14004a474`
- end: `0x14004a59f`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `299`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14004a218`

## callees

- `0x140001402`
- `0x14000141a`
- `0x14004a474`
- `0x14004ad80`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14004a4a1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14004a4a1`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x14004a4f9`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x14004a4f9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14004a56b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14004a57a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14004a56b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14004a57a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14004a4d1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14004a4d1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x14004a526`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x14004a526`

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
0x14004a474  push    rbx
0x14004a476  push    rbp
0x14004a477  push    rsi
0x14004a478  push    rdi
0x14004a479  sub     rsp, 58h
0x14004a47d  mov     rax, cs:__security_cookie
0x14004a484  xor     rax, rsp
0x14004a487  mov     [rsp+78h+var_38], rax
0x14004a48c  xorps   xmm0, xmm0
0x14004a48f  xor     edx, edx; lpDatabaseName
0x14004a491  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x14004a496  xor     ecx, ecx; lpMachineName
0x14004a498  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x14004a49d  lea     r8d, [rdx+1]; dwDesiredAccess
0x14004a4a1  call    cs:__imp_OpenSCManagerW
0x14004a4a8  nop     dword ptr [rax+rax+00h]
0x14004a4ad  mov     rbp, rax
0x14004a4b0  test    rax, rax
0x14004a4b3  jnz     short loc_14004A4C1
0x14004a4b5  call    GetLastError_0
0x14004a4ba  mov     ebx, eax
0x14004a4bc  jmp     loc_14004A586
0x14004a4c1  mov     r8d, 14h; dwDesiredAccess
0x14004a4c7  lea     rdx, ServiceName; "AppInfo"
0x14004a4ce  mov     rcx, rbp; hSCManager
0x14004a4d1  call    cs:__imp_OpenServiceW
0x14004a4d8  nop     dword ptr [rax+rax+00h]
0x14004a4dd  mov     rsi, rax
0x14004a4e0  test    rax, rax
0x14004a4e3  jnz     short loc_14004A4F1
0x14004a4e5  call    GetLastError_0
0x14004a4ea  mov     ebx, eax
0x14004a4ec  jmp     loc_14004A577
0x14004a4f1  xor     r8d, r8d; lpServiceArgVectors
0x14004a4f4  xor     edx, edx; dwNumServiceArgs
0x14004a4f6  mov     rcx, rsi; hService
0x14004a4f9  call    cs:__imp_StartServiceW
0x14004a500  nop     dword ptr [rax+rax+00h]
0x14004a505  test    eax, eax
0x14004a507  jnz     short loc_14004A517
0x14004a509  call    GetLastError_0
0x14004a50e  mov     ebx, eax
0x14004a510  cmp     eax, 420h
0x14004a515  jnz     short loc_14004A568
0x14004a517  xor     edi, edi
0x14004a519  mov     ebx, 5B4h
0x14004a51e  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x14004a523  mov     rcx, rsi; hService
0x14004a526  call    cs:__imp_QueryServiceStatus
0x14004a52d  nop     dword ptr [rax+rax+00h]
0x14004a532  test    eax, eax
0x14004a534  jz      short loc_14004A561
0x14004a536  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x14004a53b  jz      short loc_14004A55D
0x14004a53d  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x14004a542  jz      short loc_14004A557
0x14004a544  mov     ecx, 1F4h; dwMilliseconds
0x14004a549  call    Sleep_0
0x14004a54e  inc     edi
0x14004a550  cmp     edi, 0Ah
0x14004a553  jbe     short loc_14004A51E
0x14004a555  jmp     short loc_14004A568
0x14004a557  mov     ebx, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x14004a55b  jmp     short loc_14004A568
0x14004a55d  xor     ebx, ebx
0x14004a55f  jmp     short loc_14004A568
0x14004a561  call    GetLastError_0
0x14004a566  mov     ebx, eax
0x14004a568  mov     rcx, rsi; hSCObject
0x14004a56b  call    cs:__imp_CloseServiceHandle
0x14004a572  nop     dword ptr [rax+rax+00h]
0x14004a577  mov     rcx, rbp; hSCObject
0x14004a57a  call    cs:__imp_CloseServiceHandle
0x14004a581  nop     dword ptr [rax+rax+00h]
0x14004a586  mov     eax, ebx
0x14004a588  mov     rcx, [rsp+78h+var_38]
0x14004a58d  xor     rcx, rsp; StackCookie
0x14004a590  call    __security_check_cookie
0x14004a595  add     rsp, 58h
0x14004a599  pop     rdi
0x14004a59a  pop     rsi
0x14004a59b  pop     rbp
0x14004a59c  pop     rbx
0x14004a59d  retn
```
