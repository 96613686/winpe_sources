# StartIkeextService

- ea: `0x1800a2bac`
- end: `0x1800a2ca7`
- name: `StartIkeextService`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800a2288`

## callees

- `0x1800a2b38`
- `0x1800a2bac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2bd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2c4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2bd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2c4f`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800a2c08`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800a2c08`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a2c74`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a2c88`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a2c74`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a2c88`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800a2bc3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800a2bc3`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800a2c3f`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800a2c3f`

## string_xrefs

- `0x1800a2c2a`: `OpenService failed with error: %d`
- `0x1800a2be5`: `OpenSCManager failed with error: %d`
- `0x1800a2c60`: `StartService failed with error: %d`

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
0x1800a2bac  mov     [rsp+arg_0], rbx
0x1800a2bb1  mov     [rsp+arg_8], rsi
0x1800a2bb6  push    rdi
0x1800a2bb7  sub     rsp, 20h
0x1800a2bbb  xor     edx, edx; lpDatabaseName
0x1800a2bbd  xor     ecx, ecx; lpMachineName
0x1800a2bbf  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800a2bc3  call    cs:__imp_OpenSCManagerW
0x1800a2bca  nop     dword ptr [rax+rax+00h]
0x1800a2bcf  mov     rsi, rax
0x1800a2bd2  test    rax, rax
0x1800a2bd5  jnz     short loc_1800A2BF8
0x1800a2bd7  call    cs:__imp_GetLastError
0x1800a2bde  nop     dword ptr [rax+rax+00h]
0x1800a2be3  mov     edx, eax
0x1800a2be5  lea     rcx, aOpenscmanagerF; "OpenSCManager failed with error: %d"
0x1800a2bec  mov     ebx, eax
0x1800a2bee  call    RasIpsecTrace
0x1800a2bf3  jmp     loc_1800A2C94
0x1800a2bf8  mov     r8d, 14h; dwDesiredAccess
0x1800a2bfe  lea     rdx, aIkeext; "ikeext"
0x1800a2c05  mov     rcx, rsi; hSCManager
0x1800a2c08  call    cs:__imp_OpenServiceA
0x1800a2c0f  nop     dword ptr [rax+rax+00h]
0x1800a2c14  mov     rdi, rax
0x1800a2c17  test    rax, rax
0x1800a2c1a  jnz     short loc_1800A2C35
0x1800a2c1c  call    cs:__imp_GetLastError
0x1800a2c23  nop     dword ptr [rax+rax+00h]
0x1800a2c28  mov     ebx, eax
0x1800a2c2a  lea     rcx, aOpenserviceFai; "OpenService failed with error: %d"
0x1800a2c31  mov     edx, eax
0x1800a2c33  jmp     short loc_1800A2C6C
0x1800a2c35  xor     r8d, r8d; lpServiceArgVectors
0x1800a2c38  xor     edx, edx; dwNumServiceArgs
0x1800a2c3a  mov     rcx, rdi; hService
0x1800a2c3d  xor     ebx, ebx
0x1800a2c3f  call    cs:__imp_StartServiceW
0x1800a2c46  nop     dword ptr [rax+rax+00h]
0x1800a2c4b  test    eax, eax
0x1800a2c4d  jnz     short loc_1800A2C71
0x1800a2c4f  call    cs:__imp_GetLastError
0x1800a2c56  nop     dword ptr [rax+rax+00h]
0x1800a2c5b  cmp     eax, 420h
0x1800a2c60  lea     rcx, aStartserviceFa; "StartService failed with error: %d"
0x1800a2c67  cmovnz  ebx, eax
0x1800a2c6a  mov     edx, ebx
0x1800a2c6c  call    RasIpsecTrace
0x1800a2c71  mov     rcx, rsi; hSCObject
0x1800a2c74  call    cs:__imp_CloseServiceHandle
0x1800a2c7b  nop     dword ptr [rax+rax+00h]
0x1800a2c80  test    rdi, rdi
0x1800a2c83  jz      short loc_1800A2C94
0x1800a2c85  mov     rcx, rdi; hSCObject
0x1800a2c88  call    cs:__imp_CloseServiceHandle
0x1800a2c8f  nop     dword ptr [rax+rax+00h]
0x1800a2c94  mov     rsi, [rsp+28h+arg_8]
0x1800a2c99  mov     eax, ebx
0x1800a2c9b  mov     rbx, [rsp+28h+arg_0]
0x1800a2ca0  add     rsp, 20h
0x1800a2ca4  pop     rdi
0x1800a2ca5  retn
```
