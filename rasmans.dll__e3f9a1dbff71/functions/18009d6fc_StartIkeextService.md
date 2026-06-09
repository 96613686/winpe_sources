# StartIkeextService

- ea: `0x18009d6fc`
- end: `0x18009d7c3`
- name: `StartIkeextService`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18009cec0`

## callees

- `0x18009d698`
- `0x18009d6fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d77e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d77e`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18009d749`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18009d749`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d79d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d7ab`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d79d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d7ab`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009d713`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009d713`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18009d774`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18009d774`

## string_xrefs

- `0x18009d729`: `OpenSCManager failed with error: %d`
- `0x18009d789`: `StartService failed with error: %d`
- `0x18009d75f`: `OpenService failed with error: %d`

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
0x18009d6fc  mov     [rsp+arg_0], rbx
0x18009d701  mov     [rsp+arg_8], rsi
0x18009d706  push    rdi
0x18009d707  sub     rsp, 20h
0x18009d70b  xor     edx, edx; lpDatabaseName
0x18009d70d  xor     ecx, ecx; lpMachineName
0x18009d70f  lea     r8d, [rdx+1]; dwDesiredAccess
0x18009d713  call    cs:__imp_OpenSCManagerW
0x18009d719  mov     rsi, rax
0x18009d71c  test    rax, rax
0x18009d71f  jnz     short loc_18009D739
0x18009d721  call    cs:__imp_GetLastError
0x18009d727  mov     edx, eax
0x18009d729  lea     rcx, aOpenscmanagerF; "OpenSCManager failed with error: %d"
0x18009d730  mov     ebx, eax
0x18009d732  call    RasIpsecTrace
0x18009d737  jmp     short loc_18009D7B1
0x18009d739  mov     r8d, 14h; dwDesiredAccess
0x18009d73f  lea     rdx, aIkeext; "ikeext"
0x18009d746  mov     rcx, rsi; hSCManager
0x18009d749  call    cs:__imp_OpenServiceA
0x18009d74f  mov     rdi, rax
0x18009d752  test    rax, rax
0x18009d755  jnz     short loc_18009D76A
0x18009d757  call    cs:__imp_GetLastError
0x18009d75d  mov     ebx, eax
0x18009d75f  lea     rcx, aOpenserviceFai; "OpenService failed with error: %d"
0x18009d766  mov     edx, eax
0x18009d768  jmp     short loc_18009D795
0x18009d76a  xor     r8d, r8d; lpServiceArgVectors
0x18009d76d  xor     edx, edx; dwNumServiceArgs
0x18009d76f  mov     rcx, rdi; hService
0x18009d772  xor     ebx, ebx
0x18009d774  call    cs:__imp_StartServiceW
0x18009d77a  test    eax, eax
0x18009d77c  jnz     short loc_18009D79A
0x18009d77e  call    cs:__imp_GetLastError
0x18009d784  cmp     eax, 420h
0x18009d789  lea     rcx, aStartserviceFa; "StartService failed with error: %d"
0x18009d790  cmovnz  ebx, eax
0x18009d793  mov     edx, ebx
0x18009d795  call    RasIpsecTrace
0x18009d79a  mov     rcx, rsi; hSCObject
0x18009d79d  call    cs:__imp_CloseServiceHandle
0x18009d7a3  test    rdi, rdi
0x18009d7a6  jz      short loc_18009D7B1
0x18009d7a8  mov     rcx, rdi; hSCObject
0x18009d7ab  call    cs:__imp_CloseServiceHandle
0x18009d7b1  mov     rsi, [rsp+28h+arg_8]
0x18009d7b6  mov     eax, ebx
0x18009d7b8  mov     rbx, [rsp+28h+arg_0]
0x18009d7bd  add     rsp, 20h
0x18009d7c1  pop     rdi
0x18009d7c2  retn
```
