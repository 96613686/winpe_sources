# IsServiceRunningOrStartPending(ushort const *)

- ea: `0x1800143ec`
- end: `0x1800144a2`
- name: `?IsServiceRunningOrStartPending@@YA_NPEBG@Z`
- size: `182`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001376c`
- `0x180013c80`
- `0x1800143d4`

## callees

- `0x1800143ec`
- `0x1800254e0`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180014433`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180014433`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180014415`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180014415`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014473`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001447c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014473`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001447c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180014456`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180014456`

## pseudocode

```c
bool __fastcall IsServiceRunningOrStartPending(const unsigned __int16 *a1)
{
  bool v1; // si
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v1 = 0;
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v4 = OpenServiceW(v2, L"LanmanServer", 4u);
    v5 = v4;
    if ( v4 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( QueryServiceStatus(v4, &ServiceStatus) )
        v1 = ((ServiceStatus.dwCurrentState - 2) & 0xFFFFFFFD) == 0;
      CloseServiceHandle(v5);
    }
    CloseServiceHandle(v3);
  }
  return v1;
}

```

## disassembly

```asm
0x1800143ec  mov     [rsp+arg_0], rbx
0x1800143f1  mov     [rsp+arg_8], rsi
0x1800143f6  push    rdi
0x1800143f7  sub     rsp, 50h
0x1800143fb  mov     rax, cs:__security_cookie
0x180014402  xor     rax, rsp
0x180014405  mov     [rsp+58h+var_18], rax
0x18001440a  xor     edx, edx; lpDatabaseName
0x18001440c  xor     ecx, ecx; lpMachineName
0x18001440e  xor     sil, sil
0x180014411  lea     r8d, [rdx+1]; dwDesiredAccess
0x180014415  call    cs:__imp_OpenSCManagerW
0x18001441b  mov     rbx, rax
0x18001441e  test    rax, rax
0x180014421  jz      short loc_180014482
0x180014423  mov     r8d, 4; dwDesiredAccess
0x180014429  lea     rdx, ServiceName; "LanmanServer"
0x180014430  mov     rcx, rax; hSCManager
0x180014433  call    cs:__imp_OpenServiceW
0x180014439  mov     rdi, rax
0x18001443c  test    rax, rax
0x18001443f  jz      short loc_180014479
0x180014441  xorps   xmm0, xmm0
0x180014444  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180014449  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001444e  mov     rcx, rax; hService
0x180014451  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180014456  call    cs:__imp_QueryServiceStatus
0x18001445c  test    eax, eax
0x18001445e  jz      short loc_180014470
0x180014460  mov     eax, [rsp+58h+ServiceStatus.dwCurrentState]
0x180014464  add     eax, 0FFFFFFFEh
0x180014467  test    eax, 0FFFFFFFDh
0x18001446c  setz    sil
0x180014470  mov     rcx, rdi; hSCObject
0x180014473  call    cs:__imp_CloseServiceHandle
0x180014479  mov     rcx, rbx; hSCObject
0x18001447c  call    cs:__imp_CloseServiceHandle
0x180014482  mov     al, sil
0x180014485  mov     rcx, [rsp+58h+var_18]
0x18001448a  xor     rcx, rsp; StackCookie
0x18001448d  call    __security_check_cookie
0x180014492  mov     rbx, [rsp+58h+arg_0]
0x180014497  mov     rsi, [rsp+58h+arg_8]
0x18001449c  add     rsp, 50h
0x1800144a0  pop     rdi
0x1800144a1  retn
```
