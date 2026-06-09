# MprAdminInterfaceUpdateRoutes

- ea: `0x1800065e0`
- end: `0x180006647`
- name: `MprAdminInterfaceUpdateRoutes`
- size: `103`
- prototype: `DWORD __stdcall(MPR_SERVER_HANDLE hMprServer, HANDLE hInterface, DWORD dwProtocolId, HANDLE hEvent)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800065e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800065f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800065f6`
- `RPCRT4!NdrClientCall3` at `0x180006628`
- `RPCRT4!NdrClientCall3` at `0x180006628`

## pseudocode

```c
DWORD __stdcall MprAdminInterfaceUpdateRoutes(
        MPR_SERVER_HANDLE hMprServer,
        HANDLE hInterface,
        DWORD dwProtocolId,
        HANDLE hEvent)
{
  int v6; // esi
  int v9; // [rsp+20h] [rbp-58h]
  DWORD v10; // [rsp+28h] [rbp-50h]
  DWORD CurrentProcessId; // [rsp+38h] [rbp-40h]

  v6 = (int)hInterface;
  CurrentProcessId = GetCurrentProcessId();
  v10 = dwProtocolId;
  v9 = v6;
  return (unsigned int)NdrClientCall3(
                         (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                         0x17u,
                         0,
                         hMprServer,
                         v9,
                         v10,
                         hEvent,
                         CurrentProcessId).Pointer;
}

```

## disassembly

```asm
0x1800065e0  push    rbx
0x1800065e2  push    rsi
0x1800065e3  push    rdi
0x1800065e4  push    r14
0x1800065e6  sub     rsp, 58h
0x1800065ea  mov     rbx, r9
0x1800065ed  mov     edi, r8d
0x1800065f0  mov     rsi, rdx
0x1800065f3  mov     r14, rcx
0x1800065f6  call    cs:__imp_GetCurrentProcessId
0x1800065fc  nop
0x1800065fd  mov     [rsp+78h+var_30], 0
0x180006606  mov     [rsp+78h+var_40], eax
0x18000660a  mov     [rsp+78h+var_48], rbx
0x18000660f  mov     [rsp+78h+var_50], edi
0x180006613  mov     [rsp+78h+var_58], esi
0x180006617  mov     r9, r14
0x18000661a  xor     r8d, r8d; pReturnValue
0x18000661d  lea     edx, [r8+17h]; nProcNum
0x180006621  lea     rcx, pProxyInfo; pProxyInfo
0x180006628  call    cs:__imp_NdrClientCall3
0x18000662e  mov     [rsp+78h+var_30], rax
0x180006633  mov     [rsp+78h+var_38], eax
0x180006637  jmp     short loc_18000663D
0x180006639  mov     [rsp+78h+var_38], eax
0x18000663d  add     rsp, 58h
0x180006641  pop     r14
0x180006643  pop     rdi
0x180006644  pop     rsi
0x180006645  pop     rbx
0x180006646  retn
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
