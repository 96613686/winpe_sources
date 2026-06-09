# StartIkeextService

- ea: `0x180085d20`
- end: `0x180085e1b`
- name: `StartIkeextService`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180084f24`

## callees

- `0x180085cb4`
- `0x180085d20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180085d4d`
- `KERNEL32!GetLastError` at `0x180085d92`
- `KERNEL32!GetLastError` at `0x180085dc3`
- `KERNEL32!GetLastError` at `0x180085d4d`
- `KERNEL32!GetLastError` at `0x180085d92`
- `KERNEL32!GetLastError` at `0x180085dc3`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180085d7e`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180085d7e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180085d39`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180085d39`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180085db3`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180085db3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085de8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085dfc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085de8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085dfc`

## string_xrefs

- `0x180085d5b`: `OpenSCManager failed with error: %d`
- `0x180085da0`: `OpenService failed with error: %d`
- `0x180085dd4`: `StartService failed with error: %d`

## pseudocode

```c
__int64 StartIkeextService()
{
  DWORD LastError; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  const CHAR *v5; // rcx
  DWORD v6; // eax

  LastError = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( !v1 )
  {
    LastError = GetLastError();
    RasIpsecTrace("OpenSCManager failed with error: %d");
    return LastError;
  }
  v3 = OpenServiceA(v1, "ikeext", 0x14u);
  v4 = v3;
  if ( v3 )
  {
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
  CloseServiceHandle(v2);
  if ( v4 )
    CloseServiceHandle(v4);
  return LastError;
}

```

## disassembly

```asm
0x180085d20  mov     [rsp+arg_0], rbx
0x180085d25  mov     [rsp+arg_8], rsi
0x180085d2a  push    rdi
0x180085d2b  sub     rsp, 20h
0x180085d2f  xor     ebx, ebx
0x180085d31  xor     edx, edx; lpDatabaseName
0x180085d33  xor     ecx, ecx; lpMachineName
0x180085d35  lea     r8d, [rbx+1]; dwDesiredAccess
0x180085d39  call    cs:__imp_OpenSCManagerW
0x180085d40  nop     dword ptr [rax+rax+00h]
0x180085d45  mov     rsi, rax
0x180085d48  test    rax, rax
0x180085d4b  jnz     short loc_180085D6E
0x180085d4d  call    cs:__imp_GetLastError
0x180085d54  nop     dword ptr [rax+rax+00h]
0x180085d59  mov     edx, eax
0x180085d5b  lea     rcx, aOpenscmanagerF; "OpenSCManager failed with error: %d"
0x180085d62  mov     ebx, eax
0x180085d64  call    RasIpsecTrace
0x180085d69  jmp     loc_180085E08
0x180085d6e  mov     r8d, 14h; dwDesiredAccess
0x180085d74  lea     rdx, ServiceName; "ikeext"
0x180085d7b  mov     rcx, rsi; hSCManager
0x180085d7e  call    cs:__imp_OpenServiceA
0x180085d85  nop     dword ptr [rax+rax+00h]
0x180085d8a  mov     rdi, rax
0x180085d8d  test    rax, rax
0x180085d90  jnz     short loc_180085DAB
0x180085d92  call    cs:__imp_GetLastError
0x180085d99  nop     dword ptr [rax+rax+00h]
0x180085d9e  mov     ebx, eax
0x180085da0  lea     rcx, aOpenserviceFai; "OpenService failed with error: %d"
0x180085da7  mov     edx, eax
0x180085da9  jmp     short loc_180085DE0
0x180085dab  xor     r8d, r8d; lpServiceArgVectors
0x180085dae  xor     edx, edx; dwNumServiceArgs
0x180085db0  mov     rcx, rdi; hService
0x180085db3  call    cs:__imp_StartServiceW
0x180085dba  nop     dword ptr [rax+rax+00h]
0x180085dbf  test    eax, eax
0x180085dc1  jnz     short loc_180085DE5
0x180085dc3  call    cs:__imp_GetLastError
0x180085dca  nop     dword ptr [rax+rax+00h]
0x180085dcf  cmp     eax, 420h
0x180085dd4  lea     rcx, aStartserviceFa; "StartService failed with error: %d"
0x180085ddb  cmovnz  ebx, eax
0x180085dde  mov     edx, ebx
0x180085de0  call    RasIpsecTrace
0x180085de5  mov     rcx, rsi; hSCObject
0x180085de8  call    cs:__imp_CloseServiceHandle
0x180085def  nop     dword ptr [rax+rax+00h]
0x180085df4  test    rdi, rdi
0x180085df7  jz      short loc_180085E08
0x180085df9  mov     rcx, rdi; hSCObject
0x180085dfc  call    cs:__imp_CloseServiceHandle
0x180085e03  nop     dword ptr [rax+rax+00h]
0x180085e08  mov     rsi, [rsp+28h+arg_8]
0x180085e0d  mov     eax, ebx
0x180085e0f  mov     rbx, [rsp+28h+arg_0]
0x180085e14  add     rsp, 20h
0x180085e18  pop     rdi
0x180085e19  retn
```
