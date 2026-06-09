# StartIkeextService

- ea: `0x18008040c`
- end: `0x1800804d3`
- name: `StartIkeextService`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18007fbcc`

## callees

- `0x1800803a8`
- `0x18008040c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180080431`
- `KERNEL32!GetLastError` at `0x180080467`
- `KERNEL32!GetLastError` at `0x18008048e`
- `KERNEL32!GetLastError` at `0x180080431`
- `KERNEL32!GetLastError` at `0x180080467`
- `KERNEL32!GetLastError` at `0x18008048e`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180080459`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180080459`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180080423`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180080423`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180080484`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180080484`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800804ad`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800804bb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800804ad`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800804bb`

## string_xrefs

- `0x180080439`: `OpenSCManager failed with error: %d`
- `0x18008046f`: `OpenService failed with error: %d`
- `0x180080499`: `StartService failed with error: %d`

## pseudocode

```c
__int64 StartIkeextService()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  DWORD LastError; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  const CHAR *v5; // rcx
  DWORD v6; // eax

  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( !v0 )
  {
    LastError = GetLastError();
    RasIpsecTrace("OpenSCManager failed with error: %d");
    return LastError;
  }
  v3 = OpenServiceA(v0, "ikeext", 0x14u);
  v4 = v3;
  if ( v3 )
  {
    LastError = 0;
    if ( StartServiceW(v3, 0, 0) )
      goto LABEL_9;
    v6 = GetLastError();
    v5 = "StartService failed with error: %d";
    if ( v6 != 1056 )
      LastError = v6;
  }
  else
  {
    LastError = GetLastError();
    v5 = "OpenService failed with error: %d";
  }
  RasIpsecTrace(v5);
LABEL_9:
  CloseServiceHandle(v1);
  if ( v4 )
    CloseServiceHandle(v4);
  return LastError;
}

```

## disassembly

```asm
0x18008040c  mov     [rsp+arg_0], rbx
0x180080411  mov     [rsp+arg_8], rsi
0x180080416  push    rdi
0x180080417  sub     rsp, 20h
0x18008041b  xor     edx, edx; lpDatabaseName
0x18008041d  xor     ecx, ecx; lpMachineName
0x18008041f  lea     r8d, [rdx+1]; dwDesiredAccess
0x180080423  call    cs:__imp_OpenSCManagerW
0x180080429  mov     rsi, rax
0x18008042c  test    rax, rax
0x18008042f  jnz     short loc_180080449
0x180080431  call    cs:__imp_GetLastError
0x180080437  mov     edx, eax
0x180080439  lea     rcx, aOpenscmanagerF; "OpenSCManager failed with error: %d"
0x180080440  mov     ebx, eax
0x180080442  call    RasIpsecTrace
0x180080447  jmp     short loc_1800804C1
0x180080449  mov     r8d, 14h; dwDesiredAccess
0x18008044f  lea     rdx, ServiceName; "ikeext"
0x180080456  mov     rcx, rsi; hSCManager
0x180080459  call    cs:__imp_OpenServiceA
0x18008045f  mov     rdi, rax
0x180080462  test    rax, rax
0x180080465  jnz     short loc_18008047A
0x180080467  call    cs:__imp_GetLastError
0x18008046d  mov     ebx, eax
0x18008046f  lea     rcx, aOpenserviceFai; "OpenService failed with error: %d"
0x180080476  mov     edx, eax
0x180080478  jmp     short loc_1800804A5
0x18008047a  xor     r8d, r8d; lpServiceArgVectors
0x18008047d  xor     edx, edx; dwNumServiceArgs
0x18008047f  mov     rcx, rdi; hService
0x180080482  xor     ebx, ebx
0x180080484  call    cs:__imp_StartServiceW
0x18008048a  test    eax, eax
0x18008048c  jnz     short loc_1800804AA
0x18008048e  call    cs:__imp_GetLastError
0x180080494  cmp     eax, 420h
0x180080499  lea     rcx, aStartserviceFa; "StartService failed with error: %d"
0x1800804a0  cmovnz  ebx, eax
0x1800804a3  mov     edx, ebx
0x1800804a5  call    RasIpsecTrace
0x1800804aa  mov     rcx, rsi; hSCObject
0x1800804ad  call    cs:__imp_CloseServiceHandle
0x1800804b3  test    rdi, rdi
0x1800804b6  jz      short loc_1800804C1
0x1800804b8  mov     rcx, rdi; hSCObject
0x1800804bb  call    cs:__imp_CloseServiceHandle
0x1800804c1  mov     rsi, [rsp+28h+arg_8]
0x1800804c6  mov     eax, ebx
0x1800804c8  mov     rbx, [rsp+28h+arg_0]
0x1800804cd  add     rsp, 20h
0x1800804d1  pop     rdi
0x1800804d2  retn
```
