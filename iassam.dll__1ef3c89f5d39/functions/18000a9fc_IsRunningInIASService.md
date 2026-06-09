# IsRunningInIASService

- ea: `0x18000a9fc`
- end: `0x18000aada`
- name: `IsRunningInIASService`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000a800`

## callees

- `0x18000a9fc`
- `0x18002b4a0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18000aac7`
- `KERNEL32!GetCurrentProcessId` at `0x18000aac7`
- `ADVAPI32!OpenServiceA` at `0x18000aa57`
- `ADVAPI32!OpenServiceA` at `0x18000aa57`
- `ADVAPI32!CloseServiceHandle` at `0x18000aa68`
- `ADVAPI32!CloseServiceHandle` at `0x18000aab4`
- `ADVAPI32!CloseServiceHandle` at `0x18000aabd`
- `ADVAPI32!CloseServiceHandle` at `0x18000aa68`
- `ADVAPI32!CloseServiceHandle` at `0x18000aab4`
- `ADVAPI32!CloseServiceHandle` at `0x18000aabd`
- `ADVAPI32!OpenSCManagerA` at `0x18000aa39`
- `ADVAPI32!OpenSCManagerA` at `0x18000aa39`
- `ADVAPI32!QueryServiceStatusEx` at `0x18000aaa9`
- `ADVAPI32!QueryServiceStatusEx` at `0x18000aaa9`

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
0x18000a9fc  mov     [rsp+arg_0], rbx
0x18000aa01  mov     [rsp+arg_8], rsi
0x18000aa06  push    rdi
0x18000aa07  sub     rsp, 70h
0x18000aa0b  mov     rax, cs:__security_cookie
0x18000aa12  xor     rax, rsp
0x18000aa15  mov     [rsp+78h+var_18], rax
0x18000aa1a  xor     eax, eax
0x18000aa1c  xorps   xmm0, xmm0
0x18000aa1f  xor     edx, edx; lpDatabaseName
0x18000aa21  mov     [rsp+78h+var_20], eax
0x18000aa25  xor     ecx, ecx; lpMachineName
0x18000aa27  mov     [rsp+78h+var_48], eax
0x18000aa2b  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x18000aa30  lea     r8d, [rax+1Dh]; dwDesiredAccess
0x18000aa34  movups  [rsp+78h+var_30], xmm0
0x18000aa39  call    cs:__imp_OpenSCManagerA
0x18000aa3f  mov     rdi, rax
0x18000aa42  test    rax, rax
0x18000aa45  jz      short loc_18000AA6E
0x18000aa47  mov     r8d, 4; dwDesiredAccess
0x18000aa4d  lea     rdx, ServiceName; "IAS"
0x18000aa54  mov     rcx, rax; hSCManager
0x18000aa57  call    cs:__imp_OpenServiceA
0x18000aa5d  mov     rsi, rax
0x18000aa60  test    rax, rax
0x18000aa63  jnz     short loc_18000AA8F
0x18000aa65  mov     rcx, rdi; hSCObject
0x18000aa68  call    cs:__imp_CloseServiceHandle
0x18000aa6e  xor     eax, eax
0x18000aa70  mov     rcx, [rsp+78h+var_18]
0x18000aa75  xor     rcx, rsp; StackCookie
0x18000aa78  call    __security_check_cookie
0x18000aa7d  lea     r11, [rsp+78h+var_8]
0x18000aa82  mov     rbx, [r11+10h]
0x18000aa86  mov     rsi, [r11+18h]
0x18000aa8a  mov     rsp, r11
0x18000aa8d  pop     rdi
0x18000aa8e  retn
0x18000aa8f  lea     rax, [rsp+78h+var_48]
0x18000aa94  mov     r9d, 24h ; '$'; cbBufSize
0x18000aa9a  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x18000aa9f  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18000aaa4  xor     edx, edx; InfoLevel
0x18000aaa6  mov     rcx, rsi; hService
0x18000aaa9  call    cs:__imp_QueryServiceStatusEx
0x18000aaaf  mov     rcx, rsi; hSCObject
0x18000aab2  mov     ebx, eax
0x18000aab4  call    cs:__imp_CloseServiceHandle
0x18000aaba  mov     rcx, rdi; hSCObject
0x18000aabd  call    cs:__imp_CloseServiceHandle
0x18000aac3  test    ebx, ebx
0x18000aac5  jz      short loc_18000AA6E
0x18000aac7  call    cs:__imp_GetCurrentProcessId
0x18000aacd  xor     ecx, ecx
0x18000aacf  cmp     dword ptr [rsp+78h+var_30+0Ch], eax
0x18000aad3  setz    cl
0x18000aad6  mov     eax, ecx
0x18000aad8  jmp     short loc_18000AA70
```
