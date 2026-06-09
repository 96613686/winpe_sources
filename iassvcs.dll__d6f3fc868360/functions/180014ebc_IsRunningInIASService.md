# IsRunningInIASService

- ea: `0x180014ebc`
- end: `0x180014f9a`
- name: `IsRunningInIASService`
- size: `222`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180014cc0`

## callees

- `0x180014ebc`
- `0x1800181e0`

## import_xrefs

- `ADVAPI32!OpenSCManagerA` at `0x180014ef9`
- `ADVAPI32!OpenSCManagerA` at `0x180014ef9`
- `ADVAPI32!QueryServiceStatusEx` at `0x180014f69`
- `ADVAPI32!QueryServiceStatusEx` at `0x180014f69`
- `ADVAPI32!OpenServiceA` at `0x180014f17`
- `ADVAPI32!OpenServiceA` at `0x180014f17`
- `ADVAPI32!CloseServiceHandle` at `0x180014f28`
- `ADVAPI32!CloseServiceHandle` at `0x180014f74`
- `ADVAPI32!CloseServiceHandle` at `0x180014f7d`
- `ADVAPI32!CloseServiceHandle` at `0x180014f28`
- `ADVAPI32!CloseServiceHandle` at `0x180014f74`
- `ADVAPI32!CloseServiceHandle` at `0x180014f7d`
- `KERNEL32!GetCurrentProcessId` at `0x180014f87`
- `KERNEL32!GetCurrentProcessId` at `0x180014f87`

## pseudocode

```c
_BOOL8 IsRunningInIASService()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  SC_HANDLE v2; // rsi
  BOOL v4; // ebx
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v7; // [rsp+48h] [rbp-30h]
  int v8; // [rsp+58h] [rbp-20h]

  v8 = 0;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  v7 = 0;
  v0 = OpenSCManagerA(0, 0, 0x1Du);
  v1 = v0;
  if ( !v0 )
    return 0;
  v2 = OpenServiceA(v0, "IAS", 4u);
  if ( !v2 )
  {
    CloseServiceHandle(v1);
    return 0;
  }
  v4 = QueryServiceStatusEx(v2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded);
  CloseServiceHandle(v2);
  CloseServiceHandle(v1);
  if ( !v4 )
    return 0;
  return HIDWORD(v7) == GetCurrentProcessId();
}

```

## disassembly

```asm
0x180014ebc  mov     [rsp+arg_0], rbx
0x180014ec1  mov     [rsp+arg_8], rsi
0x180014ec6  push    rdi
0x180014ec7  sub     rsp, 70h
0x180014ecb  mov     rax, cs:__security_cookie
0x180014ed2  xor     rax, rsp
0x180014ed5  mov     [rsp+78h+var_18], rax
0x180014eda  xor     eax, eax
0x180014edc  xorps   xmm0, xmm0
0x180014edf  xor     edx, edx; lpDatabaseName
0x180014ee1  mov     [rsp+78h+var_20], eax
0x180014ee5  xor     ecx, ecx; lpMachineName
0x180014ee7  mov     [rsp+78h+var_48], eax
0x180014eeb  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x180014ef0  lea     r8d, [rax+1Dh]; dwDesiredAccess
0x180014ef4  movups  [rsp+78h+var_30], xmm0
0x180014ef9  call    cs:__imp_OpenSCManagerA
0x180014eff  mov     rdi, rax
0x180014f02  test    rax, rax
0x180014f05  jz      short loc_180014F2E
0x180014f07  mov     r8d, 4; dwDesiredAccess
0x180014f0d  lea     rdx, aIas_1; "IAS"
0x180014f14  mov     rcx, rax; hSCManager
0x180014f17  call    cs:__imp_OpenServiceA
0x180014f1d  mov     rsi, rax
0x180014f20  test    rax, rax
0x180014f23  jnz     short loc_180014F4F
0x180014f25  mov     rcx, rdi; hSCObject
0x180014f28  call    cs:__imp_CloseServiceHandle
0x180014f2e  xor     eax, eax
0x180014f30  mov     rcx, [rsp+78h+var_18]
0x180014f35  xor     rcx, rsp; StackCookie
0x180014f38  call    __security_check_cookie
0x180014f3d  lea     r11, [rsp+78h+var_8]
0x180014f42  mov     rbx, [r11+10h]
0x180014f46  mov     rsi, [r11+18h]
0x180014f4a  mov     rsp, r11
0x180014f4d  pop     rdi
0x180014f4e  retn
0x180014f4f  lea     rax, [rsp+78h+var_48]
0x180014f54  mov     r9d, 24h ; '$'; cbBufSize
0x180014f5a  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x180014f5f  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180014f64  xor     edx, edx; InfoLevel
0x180014f66  mov     rcx, rsi; hService
0x180014f69  call    cs:__imp_QueryServiceStatusEx
0x180014f6f  mov     rcx, rsi; hSCObject
0x180014f72  mov     ebx, eax
0x180014f74  call    cs:__imp_CloseServiceHandle
0x180014f7a  mov     rcx, rdi; hSCObject
0x180014f7d  call    cs:__imp_CloseServiceHandle
0x180014f83  test    ebx, ebx
0x180014f85  jz      short loc_180014F2E
0x180014f87  call    cs:__imp_GetCurrentProcessId
0x180014f8d  xor     ecx, ecx
0x180014f8f  cmp     dword ptr [rsp+78h+var_30+0Ch], eax
0x180014f93  setz    cl
0x180014f96  mov     eax, ecx
0x180014f98  jmp     short loc_180014F30
```
