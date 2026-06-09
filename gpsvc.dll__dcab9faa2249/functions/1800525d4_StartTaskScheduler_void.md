# StartTaskScheduler(void)

- ea: `0x1800525d4`
- end: `0x1800526d7`
- name: `?StartTaskScheduler@@YAJXZ`
- size: `259`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800517f0`
- `0x18006d498`

## callees

- `0x1800525d4`
- `0x18007d320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005262a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005262a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052694`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180052613`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180052613`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18005268a`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18005268a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800525f5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800525f5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005261f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800526b7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005261f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800526b7`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18005265a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18005265a`

## pseudocode

```c
__int64 StartTaskScheduler(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbx
  SC_HANDLE v2; // rdi
  signed int v3; // eax
  unsigned int v4; // ebx
  signed int v5; // eax
  signed int LastError; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 && (v2 = OpenServiceW(v0, L"Schedule", 0x14u), CloseServiceHandle(v1), v2) )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(v2, &ServiceStatus) )
    {
      if ( ServiceStatus.dwCurrentState == 4 || StartServiceW(v2, 0, 0) )
      {
        v4 = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v4 = 0;
        if ( LastError != -2147023840 )
          v4 = LastError;
      }
    }
    else
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
    }
    CloseServiceHandle(v2);
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x1800525d4  mov     [rsp+arg_0], rbx
0x1800525d9  push    rdi
0x1800525da  sub     rsp, 50h
0x1800525de  mov     rax, cs:__security_cookie
0x1800525e5  xor     rax, rsp
0x1800525e8  mov     [rsp+58h+var_18], rax
0x1800525ed  xor     edx, edx; lpDatabaseName
0x1800525ef  xor     ecx, ecx; lpMachineName
0x1800525f1  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800525f5  call    cs:__imp_OpenSCManagerW
0x1800525fb  mov     rbx, rax
0x1800525fe  test    rax, rax
0x180052601  jz      short loc_18005262A
0x180052603  mov     r8d, 14h; dwDesiredAccess
0x180052609  lea     rdx, aSchedule; "Schedule"
0x180052610  mov     rcx, rax; hSCManager
0x180052613  call    cs:__imp_OpenServiceW
0x180052619  mov     rcx, rbx; hSCObject
0x18005261c  mov     rdi, rax
0x18005261f  call    cs:__imp_CloseServiceHandle
0x180052625  test    rdi, rdi
0x180052628  jnz     short loc_180052645
0x18005262a  call    cs:__imp_GetLastError
0x180052630  mov     ebx, eax
0x180052632  test    eax, eax
0x180052634  jle     loc_1800526BD
0x18005263a  movzx   ebx, ax
0x18005263d  or      ebx, 80070000h
0x180052643  jmp     short loc_1800526BD
0x180052645  xorps   xmm0, xmm0
0x180052648  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18005264d  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180052652  mov     rcx, rdi; hService
0x180052655  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18005265a  call    cs:__imp_QueryServiceStatus
0x180052660  test    eax, eax
0x180052662  jnz     short loc_18005267B
0x180052664  call    cs:__imp_GetLastError
0x18005266a  mov     ebx, eax
0x18005266c  test    eax, eax
0x18005266e  jle     short loc_1800526B4
0x180052670  movzx   ebx, ax
0x180052673  or      ebx, 80070000h
0x180052679  jmp     short loc_1800526B4
0x18005267b  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x180052680  jz      short loc_1800526B2
0x180052682  xor     r8d, r8d; lpServiceArgVectors
0x180052685  xor     edx, edx; dwNumServiceArgs
0x180052687  mov     rcx, rdi; hService
0x18005268a  call    cs:__imp_StartServiceW
0x180052690  test    eax, eax
0x180052692  jnz     short loc_1800526B2
0x180052694  call    cs:__imp_GetLastError
0x18005269a  test    eax, eax
0x18005269c  jle     short loc_1800526A6
0x18005269e  movzx   eax, ax
0x1800526a1  or      eax, 80070000h
0x1800526a6  xor     ebx, ebx
0x1800526a8  cmp     eax, 80070420h
0x1800526ad  cmovnz  ebx, eax
0x1800526b0  jmp     short loc_1800526B4
0x1800526b2  xor     ebx, ebx
0x1800526b4  mov     rcx, rdi; hSCObject
0x1800526b7  call    cs:__imp_CloseServiceHandle
0x1800526bd  mov     eax, ebx
0x1800526bf  mov     rcx, [rsp+58h+var_18]
0x1800526c4  xor     rcx, rsp; StackCookie
0x1800526c7  call    __security_check_cookie
0x1800526cc  mov     rbx, [rsp+58h+arg_0]
0x1800526d1  add     rsp, 50h
0x1800526d5  pop     rdi
0x1800526d6  retn
```
