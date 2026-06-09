# MprAdminRegisterConnectionNotification

- ea: `0x180006e00`
- end: `0x180006e73`
- name: `MprAdminRegisterConnectionNotification`
- size: `115`
- prototype: `DWORD __stdcall(MPR_SERVER_HANDLE hMprServer, HANDLE hEventNotification)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180006e00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006e10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006e10`
- `RPCRT4!NdrClientCall3` at `0x180006e4c`
- `RPCRT4!NdrClientCall3` at `0x180006e4c`

## pseudocode

```c
DWORD __stdcall MprAdminRegisterConnectionNotification(MPR_SERVER_HANDLE hMprServer, HANDLE hEventNotification)
{
  DWORD CurrentProcessId; // eax
  int v6; // [rsp+20h] [rbp-38h]
  DWORD v7; // [rsp+28h] [rbp-30h]

  CurrentProcessId = GetCurrentProcessId();
  if ( hEventNotification == (HANDLE)-1LL || !hEventNotification )
    return 87;
  v7 = CurrentProcessId;
  v6 = 1;
  return (unsigned int)NdrClientCall3(
                         (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                         0x22u,
                         0,
                         hMprServer,
                         v6,
                         v7,
                         hEventNotification).Pointer;
}

```

## disassembly

```asm
0x180006e00  mov     [rsp+arg_0], rbx
0x180006e05  push    rdi
0x180006e06  sub     rsp, 50h
0x180006e0a  mov     rbx, rdx
0x180006e0d  mov     rdi, rcx
0x180006e10  call    cs:__imp_GetCurrentProcessId
0x180006e16  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180006e1a  jz      short loc_180006E63
0x180006e1c  test    rbx, rbx
0x180006e1f  jz      short loc_180006E63
0x180006e21  mov     [rsp+58h+arg_8], 0
0x180006e2a  mov     [rsp+58h+var_28], rbx
0x180006e2f  mov     [rsp+58h+var_30], eax
0x180006e33  mov     [rsp+58h+var_38], 1
0x180006e3b  mov     r9, rdi
0x180006e3e  xor     r8d, r8d; pReturnValue
0x180006e41  lea     edx, [r8+22h]; nProcNum
0x180006e45  lea     rcx, pProxyInfo; pProxyInfo
0x180006e4c  call    cs:__imp_NdrClientCall3
0x180006e52  mov     [rsp+58h+arg_8], rax
0x180006e57  mov     [rsp+58h+var_18], eax
0x180006e5b  jmp     short loc_180006E61
0x180006e5d  mov     [rsp+58h+var_18], eax
0x180006e61  jmp     short loc_180006E68
0x180006e63  mov     eax, 57h ; 'W'
0x180006e68  mov     rbx, [rsp+58h+arg_0]
0x180006e6d  add     rsp, 50h
0x180006e71  pop     rdi
0x180006e72  retn
0x18005158b  push    rbp
0x18005158d  sub     rsp, 40h
0x180051591  mov     rbp, rdx
0x180051594  mov     rcx, [rcx]
0x180051597  mov     ecx, [rcx]; ExceptionCode
0x180051599  call    cs:__imp_I_RpcExceptionFilter
0x18005159f  nop
0x1800515a0  add     rsp, 40h
0x1800515a4  pop     rbp
0x1800515a5  retn
```
