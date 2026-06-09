# IsRunningInIASService

- ea: `0x18000cdac`
- end: `0x18000ce8a`
- name: `IsRunningInIASService`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000cbb0`

## callees

- `0x18000cdac`
- `0x18000dd10`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x18000ce18`
- `ADVAPI32!CloseServiceHandle` at `0x18000ce64`
- `ADVAPI32!CloseServiceHandle` at `0x18000ce6d`
- `ADVAPI32!CloseServiceHandle` at `0x18000ce18`
- `ADVAPI32!CloseServiceHandle` at `0x18000ce64`
- `ADVAPI32!CloseServiceHandle` at `0x18000ce6d`
- `ADVAPI32!OpenSCManagerA` at `0x18000cde9`
- `ADVAPI32!OpenSCManagerA` at `0x18000cde9`
- `ADVAPI32!QueryServiceStatusEx` at `0x18000ce59`
- `ADVAPI32!QueryServiceStatusEx` at `0x18000ce59`
- `ADVAPI32!OpenServiceA` at `0x18000ce07`
- `ADVAPI32!OpenServiceA` at `0x18000ce07`
- `KERNEL32!GetCurrentProcessId` at `0x18000ce77`
- `KERNEL32!GetCurrentProcessId` at `0x18000ce77`

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
0x18000cdac  mov     [rsp+arg_0], rbx
0x18000cdb1  mov     [rsp+arg_8], rsi
0x18000cdb6  push    rdi
0x18000cdb7  sub     rsp, 70h
0x18000cdbb  mov     rax, cs:__security_cookie
0x18000cdc2  xor     rax, rsp
0x18000cdc5  mov     [rsp+78h+var_18], rax
0x18000cdca  xor     eax, eax
0x18000cdcc  xorps   xmm0, xmm0
0x18000cdcf  xor     edx, edx; lpDatabaseName
0x18000cdd1  mov     [rsp+78h+var_20], eax
0x18000cdd5  xor     ecx, ecx; lpMachineName
0x18000cdd7  mov     [rsp+78h+var_48], eax
0x18000cddb  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x18000cde0  lea     r8d, [rax+1Dh]; dwDesiredAccess
0x18000cde4  movups  [rsp+78h+var_30], xmm0
0x18000cde9  call    cs:__imp_OpenSCManagerA
0x18000cdef  mov     rdi, rax
0x18000cdf2  test    rax, rax
0x18000cdf5  jz      short loc_18000CE1E
0x18000cdf7  mov     r8d, 4; dwDesiredAccess
0x18000cdfd  lea     rdx, ServiceName; "IAS"
0x18000ce04  mov     rcx, rax; hSCManager
0x18000ce07  call    cs:__imp_OpenServiceA
0x18000ce0d  mov     rsi, rax
0x18000ce10  test    rax, rax
0x18000ce13  jnz     short loc_18000CE3F
0x18000ce15  mov     rcx, rdi; hSCObject
0x18000ce18  call    cs:__imp_CloseServiceHandle
0x18000ce1e  xor     eax, eax
0x18000ce20  mov     rcx, [rsp+78h+var_18]
0x18000ce25  xor     rcx, rsp; StackCookie
0x18000ce28  call    __security_check_cookie
0x18000ce2d  lea     r11, [rsp+78h+var_8]
0x18000ce32  mov     rbx, [r11+10h]
0x18000ce36  mov     rsi, [r11+18h]
0x18000ce3a  mov     rsp, r11
0x18000ce3d  pop     rdi
0x18000ce3e  retn
0x18000ce3f  lea     rax, [rsp+78h+var_48]
0x18000ce44  mov     r9d, 24h ; '$'; cbBufSize
0x18000ce4a  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x18000ce4f  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18000ce54  xor     edx, edx; InfoLevel
0x18000ce56  mov     rcx, rsi; hService
0x18000ce59  call    cs:__imp_QueryServiceStatusEx
0x18000ce5f  mov     rcx, rsi; hSCObject
0x18000ce62  mov     ebx, eax
0x18000ce64  call    cs:__imp_CloseServiceHandle
0x18000ce6a  mov     rcx, rdi; hSCObject
0x18000ce6d  call    cs:__imp_CloseServiceHandle
0x18000ce73  test    ebx, ebx
0x18000ce75  jz      short loc_18000CE1E
0x18000ce77  call    cs:__imp_GetCurrentProcessId
0x18000ce7d  xor     ecx, ecx
0x18000ce7f  cmp     dword ptr [rsp+78h+var_30+0Ch], eax
0x18000ce83  setz    cl
0x18000ce86  mov     eax, ecx
0x18000ce88  jmp     short loc_18000CE20
```
