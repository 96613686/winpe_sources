# DsaPauseNetlogon

- ea: `0x1800341d4`
- end: `0x1800342ce`
- name: `DsaPauseNetlogon`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18003c270`
- `0x18003c4bc`

## callees

- `0x18001e090`
- `0x1800341d4`
- `0x180172774`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003422e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003427f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003422e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003427f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342a5`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18003424a`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18003424a`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180034220`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180034220`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180034275`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180034275`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003428f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003429d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003428f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003429d`

## pseudocode

```c
__int64 __fastcall DsaPauseNetlogon(int a1, __int64 a2)
{
  DWORD LastError; // ebx
  SC_HANDLE v4; // rdi
  SC_HANDLE v5; // rsi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( DsaWaitUntilServiceIsRunningEx("netlogon", a2, 1) )
  {
    LastError = 0;
    v4 = OpenSCManagerA(0, 0, 1u);
    if ( v4 || (LastError = GetLastError()) == 0 )
    {
      v5 = OpenServiceA(v4, "netlogon", 0x48u);
      if ( v5 || (LastError = GetLastError()) == 0 )
      {
        if ( !ControlService(v5, (a1 != 0) + 2, &ServiceStatus) )
          LastError = GetLastError();
        if ( v5 )
          CloseServiceHandle(v5);
      }
      if ( v4 )
        CloseServiceHandle(v4);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      return 8341;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800341d4  push    rbx
0x1800341d6  push    rbp
0x1800341d7  push    rsi
0x1800341d8  push    rdi
0x1800341d9  sub     rsp, 58h
0x1800341dd  mov     rax, cs:__security_cookie
0x1800341e4  xor     rax, rsp
0x1800341e7  mov     [rsp+78h+var_38], rax
0x1800341ec  xorps   xmm0, xmm0
0x1800341ef  mov     ebp, ecx
0x1800341f1  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800341f6  mov     edi, 1
0x1800341fb  lea     rcx, ServiceName; "netlogon"
0x180034202  mov     r8d, edi
0x180034205  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18003420a  call    DsaWaitUntilServiceIsRunningEx
0x18003420f  test    al, al
0x180034211  jz      loc_1800342A5
0x180034217  mov     r8d, edi; dwDesiredAccess
0x18003421a  xor     edx, edx; lpDatabaseName
0x18003421c  xor     ecx, ecx; lpMachineName
0x18003421e  xor     ebx, ebx
0x180034220  call    cs:__imp_OpenSCManagerA
0x180034226  mov     rdi, rax
0x180034229  test    rax, rax
0x18003422c  jnz     short loc_18003423A
0x18003422e  call    cs:__imp_GetLastError
0x180034234  mov     ebx, eax
0x180034236  test    eax, eax
0x180034238  jnz     short loc_1800342B6
0x18003423a  mov     r8d, 48h ; 'H'; dwDesiredAccess
0x180034240  lea     rdx, ServiceName; "netlogon"
0x180034247  mov     rcx, rdi; hSCManager
0x18003424a  call    cs:__imp_OpenServiceA
0x180034250  mov     rsi, rax
0x180034253  test    rax, rax
0x180034256  jnz     short loc_180034264
0x180034258  call    cs:__imp_GetLastError
0x18003425e  mov     ebx, eax
0x180034260  test    eax, eax
0x180034262  jnz     short loc_180034295
0x180034264  neg     ebp
0x180034266  lea     r8, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18003426b  mov     rcx, rsi; hService
0x18003426e  sbb     edx, edx
0x180034270  neg     edx
0x180034272  add     edx, 2; dwControl
0x180034275  call    cs:__imp_ControlService
0x18003427b  test    eax, eax
0x18003427d  jnz     short loc_180034287
0x18003427f  call    cs:__imp_GetLastError
0x180034285  mov     ebx, eax
0x180034287  test    rsi, rsi
0x18003428a  jz      short loc_180034295
0x18003428c  mov     rcx, rsi; hSCObject
0x18003428f  call    cs:__imp_CloseServiceHandle
0x180034295  test    rdi, rdi
0x180034298  jz      short loc_1800342B6
0x18003429a  mov     rcx, rdi; hSCObject
0x18003429d  call    cs:__imp_CloseServiceHandle
0x1800342a3  jmp     short loc_1800342B6
0x1800342a5  call    cs:__imp_GetLastError
0x1800342ab  mov     ebx, eax
0x1800342ad  test    eax, eax
0x1800342af  jnz     short loc_1800342B6
0x1800342b1  mov     ebx, 2095h
0x1800342b6  mov     eax, ebx
0x1800342b8  mov     rcx, [rsp+78h+var_38]
0x1800342bd  xor     rcx, rsp; StackCookie
0x1800342c0  call    __security_check_cookie
0x1800342c5  add     rsp, 58h
0x1800342c9  pop     rdi
0x1800342ca  pop     rsi
0x1800342cb  pop     rbp
0x1800342cc  pop     rbx
0x1800342cd  retn
```
