# AicpStartAIS(ulong)

- ea: `0x1401beecc`
- end: `0x1401beffa`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `302`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140021780`

## callees

- `0x14010e160`
- `0x14010f88b`
- `0x14010f927`
- `0x1401beecc`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1401bef51`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1401bef51`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1401befc6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1401befd5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1401befc6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1401befd5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1401bef29`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1401bef29`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1401beef9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1401beef9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1401bef7e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1401bef7e`

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
0x1401beecc  push    rbx
0x1401beece  push    rbp
0x1401beecf  push    rsi
0x1401beed0  push    rdi
0x1401beed1  sub     rsp, 58h
0x1401beed5  mov     rax, cs:__security_cookie
0x1401beedc  xor     rax, rsp
0x1401beedf  mov     [rsp+78h+var_38], rax
0x1401beee4  xorps   xmm0, xmm0
0x1401beee7  xor     edx, edx; lpDatabaseName
0x1401beee9  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1401beeee  xor     ecx, ecx; lpMachineName
0x1401beef0  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1401beef5  lea     r8d, [rdx+1]; dwDesiredAccess
0x1401beef9  call    cs:__imp_OpenSCManagerW
0x1401bef00  nop     dword ptr [rax+rax+00h]
0x1401bef05  mov     rbp, rax
0x1401bef08  test    rax, rax
0x1401bef0b  jnz     short loc_1401BEF19
0x1401bef0d  call    GetLastError_0
0x1401bef12  mov     ebx, eax
0x1401bef14  jmp     loc_1401BEFE1
0x1401bef19  mov     r8d, 14h; dwDesiredAccess
0x1401bef1f  lea     rdx, aAppinfo; "AppInfo"
0x1401bef26  mov     rcx, rbp; hSCManager
0x1401bef29  call    cs:__imp_OpenServiceW
0x1401bef30  nop     dword ptr [rax+rax+00h]
0x1401bef35  mov     rsi, rax
0x1401bef38  test    rax, rax
0x1401bef3b  jnz     short loc_1401BEF49
0x1401bef3d  call    GetLastError_0
0x1401bef42  mov     ebx, eax
0x1401bef44  jmp     loc_1401BEFD2
0x1401bef49  xor     r8d, r8d; lpServiceArgVectors
0x1401bef4c  xor     edx, edx; dwNumServiceArgs
0x1401bef4e  mov     rcx, rsi; hService
0x1401bef51  call    cs:__imp_StartServiceW
0x1401bef58  nop     dword ptr [rax+rax+00h]
0x1401bef5d  test    eax, eax
0x1401bef5f  jnz     short loc_1401BEF6F
0x1401bef61  call    GetLastError_0
0x1401bef66  mov     ebx, eax
0x1401bef68  cmp     eax, 420h
0x1401bef6d  jnz     short loc_1401BEFC3
0x1401bef6f  xor     edi, edi
0x1401bef71  mov     ebx, 5B4h
0x1401bef76  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1401bef7b  mov     rcx, rsi; hService
0x1401bef7e  call    cs:__imp_QueryServiceStatus
0x1401bef85  nop     dword ptr [rax+rax+00h]
0x1401bef8a  test    eax, eax
0x1401bef8c  jz      short loc_1401BEFBC
0x1401bef8e  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x1401bef93  jz      short loc_1401BEFB8
0x1401bef95  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x1401bef9a  jz      short loc_1401BEFB2
0x1401bef9c  mov     ecx, 1F4h; dwMilliseconds
0x1401befa1  call    Sleep_0
0x1401befa6  inc     edi
0x1401befa8  cmp     edi, 258h
0x1401befae  jbe     short loc_1401BEF76
0x1401befb0  jmp     short loc_1401BEFC3
0x1401befb2  mov     ebx, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x1401befb6  jmp     short loc_1401BEFC3
0x1401befb8  xor     ebx, ebx
0x1401befba  jmp     short loc_1401BEFC3
0x1401befbc  call    GetLastError_0
0x1401befc1  mov     ebx, eax
0x1401befc3  mov     rcx, rsi; hSCObject
0x1401befc6  call    cs:__imp_CloseServiceHandle
0x1401befcd  nop     dword ptr [rax+rax+00h]
0x1401befd2  mov     rcx, rbp; hSCObject
0x1401befd5  call    cs:__imp_CloseServiceHandle
0x1401befdc  nop     dword ptr [rax+rax+00h]
0x1401befe1  mov     eax, ebx
0x1401befe3  mov     rcx, [rsp+78h+var_38]
0x1401befe8  xor     rcx, rsp; StackCookie
0x1401befeb  call    __security_check_cookie
0x1401beff0  add     rsp, 58h
0x1401beff4  pop     rdi
0x1401beff5  pop     rsi
0x1401beff6  pop     rbp
0x1401beff7  pop     rbx
0x1401beff8  retn
```
