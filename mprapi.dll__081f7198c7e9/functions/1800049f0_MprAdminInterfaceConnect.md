# MprAdminInterfaceConnect

- ea: `0x1800049f0`
- end: `0x180004a57`
- name: `MprAdminInterfaceConnect`
- size: `103`
- prototype: `DWORD __stdcall(MPR_SERVER_HANDLE hMprServer, HANDLE hInterface, HANDLE hEvent, BOOL fSynchronous)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800049f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004a06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004a06`
- `RPCRT4!NdrClientCall3` at `0x180004a38`
- `RPCRT4!NdrClientCall3` at `0x180004a38`

## pseudocode

```c
DWORD __stdcall MprAdminInterfaceConnect(
        MPR_SERVER_HANDLE hMprServer,
        HANDLE hInterface,
        HANDLE hEvent,
        BOOL fSynchronous)
{
  int v6; // esi
  int v9; // [rsp+20h] [rbp-58h]
  BOOL v10; // [rsp+30h] [rbp-48h]
  DWORD CurrentProcessId; // [rsp+38h] [rbp-40h]

  v6 = (int)hInterface;
  CurrentProcessId = GetCurrentProcessId();
  v10 = fSynchronous;
  v9 = v6;
  return (unsigned int)NdrClientCall3(
                         (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                         0x15u,
                         0,
                         hMprServer,
                         v9,
                         hEvent,
                         v10,
                         CurrentProcessId).Pointer;
}

```

## disassembly

```asm
0x1800049f0  push    rbx
0x1800049f2  push    rsi
0x1800049f3  push    rdi
0x1800049f4  push    r14
0x1800049f6  sub     rsp, 58h
0x1800049fa  mov     ebx, r9d
0x1800049fd  mov     rdi, r8
0x180004a00  mov     rsi, rdx
0x180004a03  mov     r14, rcx
0x180004a06  call    cs:__imp_GetCurrentProcessId
0x180004a0c  nop
0x180004a0d  mov     [rsp+78h+var_30], 0
0x180004a16  mov     [rsp+78h+var_40], eax
0x180004a1a  mov     [rsp+78h+var_48], ebx
0x180004a1e  mov     [rsp+78h+var_50], rdi
0x180004a23  mov     [rsp+78h+var_58], esi
0x180004a27  mov     r9, r14
0x180004a2a  xor     r8d, r8d; pReturnValue
0x180004a2d  lea     edx, [r8+15h]; nProcNum
0x180004a31  lea     rcx, pProxyInfo; pProxyInfo
0x180004a38  call    cs:__imp_NdrClientCall3
0x180004a3e  mov     [rsp+78h+var_30], rax
0x180004a43  mov     [rsp+78h+var_38], eax
0x180004a47  jmp     short loc_180004A4D
0x180004a49  mov     [rsp+78h+var_38], eax
0x180004a4d  add     rsp, 58h
0x180004a51  pop     r14
0x180004a53  pop     rdi
0x180004a54  pop     rsi
0x180004a55  pop     rbx
0x180004a56  retn
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
