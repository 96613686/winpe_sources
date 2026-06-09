# AicpStartAIS(ulong)

- ea: `0x1401c0588`
- end: `0x1401c068e`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `262`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140012138`

## callees

- `0x1401040e0`
- `0x14010582f`
- `0x1401058cb`
- `0x1401c0588`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1401c05fe`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1401c05fe`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1401c0667`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1401c0670`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1401c0667`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1401c0670`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1401c05df`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1401c05df`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1401c05b5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1401c05b5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1401c0625`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1401c0625`

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
          if ( (unsigned int)++v5 > 0x258 )
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
0x1401c0588  push    rbx
0x1401c058a  push    rbp
0x1401c058b  push    rsi
0x1401c058c  push    rdi
0x1401c058d  sub     rsp, 58h
0x1401c0591  mov     rax, cs:__security_cookie
0x1401c0598  xor     rax, rsp
0x1401c059b  mov     [rsp+78h+var_38], rax
0x1401c05a0  xorps   xmm0, xmm0
0x1401c05a3  xor     edx, edx; lpDatabaseName
0x1401c05a5  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1401c05aa  xor     ecx, ecx; lpMachineName
0x1401c05ac  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1401c05b1  lea     r8d, [rdx+1]; dwDesiredAccess
0x1401c05b5  call    cs:__imp_OpenSCManagerW
0x1401c05bb  mov     rbp, rax
0x1401c05be  test    rax, rax
0x1401c05c1  jnz     short loc_1401C05CF
0x1401c05c3  call    GetLastError_0
0x1401c05c8  mov     ebx, eax
0x1401c05ca  jmp     loc_1401C0676
0x1401c05cf  mov     r8d, 14h; dwDesiredAccess
0x1401c05d5  lea     rdx, aAppinfo; "AppInfo"
0x1401c05dc  mov     rcx, rbp; hSCManager
0x1401c05df  call    cs:__imp_OpenServiceW
0x1401c05e5  mov     rsi, rax
0x1401c05e8  test    rax, rax
0x1401c05eb  jnz     short loc_1401C05F6
0x1401c05ed  call    GetLastError_0
0x1401c05f2  mov     ebx, eax
0x1401c05f4  jmp     short loc_1401C066D
0x1401c05f6  xor     r8d, r8d; lpServiceArgVectors
0x1401c05f9  xor     edx, edx; dwNumServiceArgs
0x1401c05fb  mov     rcx, rsi; hService
0x1401c05fe  call    cs:__imp_StartServiceW
0x1401c0604  test    eax, eax
0x1401c0606  jnz     short loc_1401C0616
0x1401c0608  call    GetLastError_0
0x1401c060d  mov     ebx, eax
0x1401c060f  cmp     eax, 420h
0x1401c0614  jnz     short loc_1401C0664
0x1401c0616  xor     edi, edi
0x1401c0618  mov     ebx, 5B4h
0x1401c061d  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1401c0622  mov     rcx, rsi; hService
0x1401c0625  call    cs:__imp_QueryServiceStatus
0x1401c062b  test    eax, eax
0x1401c062d  jz      short loc_1401C065D
0x1401c062f  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x1401c0634  jz      short loc_1401C0659
0x1401c0636  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x1401c063b  jz      short loc_1401C0653
0x1401c063d  mov     ecx, 1F4h; dwMilliseconds
0x1401c0642  call    Sleep_0
0x1401c0647  inc     edi
0x1401c0649  cmp     edi, 258h
0x1401c064f  jbe     short loc_1401C061D
0x1401c0651  jmp     short loc_1401C0664
0x1401c0653  mov     ebx, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x1401c0657  jmp     short loc_1401C0664
0x1401c0659  xor     ebx, ebx
0x1401c065b  jmp     short loc_1401C0664
0x1401c065d  call    GetLastError_0
0x1401c0662  mov     ebx, eax
0x1401c0664  mov     rcx, rsi; hSCObject
0x1401c0667  call    cs:__imp_CloseServiceHandle
0x1401c066d  mov     rcx, rbp; hSCObject
0x1401c0670  call    cs:__imp_CloseServiceHandle
0x1401c0676  mov     eax, ebx
0x1401c0678  mov     rcx, [rsp+78h+var_38]
0x1401c067d  xor     rcx, rsp; StackCookie
0x1401c0680  call    __security_check_cookie
0x1401c0685  add     rsp, 58h
0x1401c0689  pop     rdi
0x1401c068a  pop     rsi
0x1401c068b  pop     rbp
0x1401c068c  pop     rbx
0x1401c068d  retn
```
