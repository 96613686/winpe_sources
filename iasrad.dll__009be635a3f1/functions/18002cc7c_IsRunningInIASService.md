# IsRunningInIASService

- ea: `0x18002cc7c`
- end: `0x18002cd5a`
- name: `IsRunningInIASService`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18002ca80`

## callees

- `0x18002cc7c`
- `0x18002e230`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18002cd47`
- `KERNEL32!GetCurrentProcessId` at `0x18002cd47`
- `ADVAPI32!CloseServiceHandle` at `0x18002cce8`
- `ADVAPI32!CloseServiceHandle` at `0x18002cd34`
- `ADVAPI32!CloseServiceHandle` at `0x18002cd3d`
- `ADVAPI32!CloseServiceHandle` at `0x18002cce8`
- `ADVAPI32!CloseServiceHandle` at `0x18002cd34`
- `ADVAPI32!CloseServiceHandle` at `0x18002cd3d`
- `ADVAPI32!OpenSCManagerA` at `0x18002ccb9`
- `ADVAPI32!OpenSCManagerA` at `0x18002ccb9`
- `ADVAPI32!QueryServiceStatusEx` at `0x18002cd29`
- `ADVAPI32!QueryServiceStatusEx` at `0x18002cd29`
- `ADVAPI32!OpenServiceA` at `0x18002ccd7`
- `ADVAPI32!OpenServiceA` at `0x18002ccd7`

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
0x18002cc7c  mov     [rsp+arg_0], rbx
0x18002cc81  mov     [rsp+arg_8], rsi
0x18002cc86  push    rdi
0x18002cc87  sub     rsp, 70h
0x18002cc8b  mov     rax, cs:__security_cookie
0x18002cc92  xor     rax, rsp
0x18002cc95  mov     [rsp+78h+var_18], rax
0x18002cc9a  xor     eax, eax
0x18002cc9c  xorps   xmm0, xmm0
0x18002cc9f  xor     edx, edx; lpDatabaseName
0x18002cca1  mov     [rsp+78h+var_20], eax
0x18002cca5  xor     ecx, ecx; lpMachineName
0x18002cca7  mov     [rsp+78h+var_48], eax
0x18002ccab  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x18002ccb0  lea     r8d, [rax+1Dh]; dwDesiredAccess
0x18002ccb4  movups  [rsp+78h+var_30], xmm0
0x18002ccb9  call    cs:__imp_OpenSCManagerA
0x18002ccbf  mov     rdi, rax
0x18002ccc2  test    rax, rax
0x18002ccc5  jz      short loc_18002CCEE
0x18002ccc7  mov     r8d, 4; dwDesiredAccess
0x18002cccd  lea     rdx, ServiceName; "IAS"
0x18002ccd4  mov     rcx, rax; hSCManager
0x18002ccd7  call    cs:__imp_OpenServiceA
0x18002ccdd  mov     rsi, rax
0x18002cce0  test    rax, rax
0x18002cce3  jnz     short loc_18002CD0F
0x18002cce5  mov     rcx, rdi; hSCObject
0x18002cce8  call    cs:__imp_CloseServiceHandle
0x18002ccee  xor     eax, eax
0x18002ccf0  mov     rcx, [rsp+78h+var_18]
0x18002ccf5  xor     rcx, rsp; StackCookie
0x18002ccf8  call    __security_check_cookie
0x18002ccfd  lea     r11, [rsp+78h+var_8]
0x18002cd02  mov     rbx, [r11+10h]
0x18002cd06  mov     rsi, [r11+18h]
0x18002cd0a  mov     rsp, r11
0x18002cd0d  pop     rdi
0x18002cd0e  retn
0x18002cd0f  lea     rax, [rsp+78h+var_48]
0x18002cd14  mov     r9d, 24h ; '$'; cbBufSize
0x18002cd1a  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x18002cd1f  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18002cd24  xor     edx, edx; InfoLevel
0x18002cd26  mov     rcx, rsi; hService
0x18002cd29  call    cs:__imp_QueryServiceStatusEx
0x18002cd2f  mov     rcx, rsi; hSCObject
0x18002cd32  mov     ebx, eax
0x18002cd34  call    cs:__imp_CloseServiceHandle
0x18002cd3a  mov     rcx, rdi; hSCObject
0x18002cd3d  call    cs:__imp_CloseServiceHandle
0x18002cd43  test    ebx, ebx
0x18002cd45  jz      short loc_18002CCEE
0x18002cd47  call    cs:__imp_GetCurrentProcessId
0x18002cd4d  xor     ecx, ecx
0x18002cd4f  cmp     dword ptr [rsp+78h+var_30+0Ch], eax
0x18002cd53  setz    cl
0x18002cd56  mov     eax, ecx
0x18002cd58  jmp     short loc_18002CCF0
```
