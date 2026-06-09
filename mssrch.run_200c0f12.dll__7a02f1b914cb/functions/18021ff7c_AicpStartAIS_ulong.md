# AicpStartAIS(ulong)

- ea: `0x18021ff7c`
- end: `0x18022007f`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `259`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800baffc`

## callees

- `0x1801244c0`
- `0x18012581f`
- `0x180125feb`
- `0x18021ff7c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18021ffd3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18021ffd3`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18021fff2`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18021fff2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18021ffa9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18021ffa9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180220058`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180220061`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180220058`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180220061`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180220019`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180220019`

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
0x18021ff7c  push    rbx
0x18021ff7e  push    rbp
0x18021ff7f  push    rsi
0x18021ff80  push    rdi
0x18021ff81  sub     rsp, 58h
0x18021ff85  mov     rax, cs:__security_cookie
0x18021ff8c  xor     rax, rsp
0x18021ff8f  mov     [rsp+78h+var_38], rax
0x18021ff94  xorps   xmm0, xmm0
0x18021ff97  xor     edx, edx; lpDatabaseName
0x18021ff99  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18021ff9e  xor     ecx, ecx; lpMachineName
0x18021ffa0  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18021ffa5  lea     r8d, [rdx+1]; dwDesiredAccess
0x18021ffa9  call    cs:__imp_OpenSCManagerW
0x18021ffaf  mov     rbp, rax
0x18021ffb2  test    rax, rax
0x18021ffb5  jnz     short loc_18021FFC3
0x18021ffb7  call    GetLastError_0
0x18021ffbc  mov     ebx, eax
0x18021ffbe  jmp     loc_180220067
0x18021ffc3  mov     r8d, 14h; dwDesiredAccess
0x18021ffc9  lea     rdx, aAppinfo; "AppInfo"
0x18021ffd0  mov     rcx, rbp; hSCManager
0x18021ffd3  call    cs:__imp_OpenServiceW
0x18021ffd9  mov     rsi, rax
0x18021ffdc  test    rax, rax
0x18021ffdf  jnz     short loc_18021FFEA
0x18021ffe1  call    GetLastError_0
0x18021ffe6  mov     ebx, eax
0x18021ffe8  jmp     short loc_18022005E
0x18021ffea  xor     r8d, r8d; lpServiceArgVectors
0x18021ffed  xor     edx, edx; dwNumServiceArgs
0x18021ffef  mov     rcx, rsi; hService
0x18021fff2  call    cs:__imp_StartServiceW
0x18021fff8  test    eax, eax
0x18021fffa  jnz     short loc_18022000A
0x18021fffc  call    GetLastError_0
0x180220001  mov     ebx, eax
0x180220003  cmp     eax, 420h
0x180220008  jnz     short loc_180220055
0x18022000a  xor     edi, edi
0x18022000c  mov     ebx, 5B4h
0x180220011  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180220016  mov     rcx, rsi; hService
0x180220019  call    cs:__imp_QueryServiceStatus
0x18022001f  test    eax, eax
0x180220021  jz      short loc_18022004E
0x180220023  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x180220028  jz      short loc_18022004A
0x18022002a  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x18022002f  jz      short loc_180220044
0x180220031  mov     ecx, 1F4h; dwMilliseconds
0x180220036  call    Sleep_0
0x18022003b  inc     edi
0x18022003d  cmp     edi, 0Ah
0x180220040  jbe     short loc_180220011
0x180220042  jmp     short loc_180220055
0x180220044  mov     ebx, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x180220048  jmp     short loc_180220055
0x18022004a  xor     ebx, ebx
0x18022004c  jmp     short loc_180220055
0x18022004e  call    GetLastError_0
0x180220053  mov     ebx, eax
0x180220055  mov     rcx, rsi; hSCObject
0x180220058  call    cs:__imp_CloseServiceHandle
0x18022005e  mov     rcx, rbp; hSCObject
0x180220061  call    cs:__imp_CloseServiceHandle
0x180220067  mov     eax, ebx
0x180220069  mov     rcx, [rsp+78h+var_38]
0x18022006e  xor     rcx, rsp; StackCookie
0x180220071  call    __security_check_cookie
0x180220076  add     rsp, 58h
0x18022007a  pop     rdi
0x18022007b  pop     rsi
0x18022007c  pop     rbp
0x18022007d  pop     rbx
0x18022007e  retn
```
