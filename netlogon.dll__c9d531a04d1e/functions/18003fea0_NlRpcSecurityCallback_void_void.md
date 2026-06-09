# NlRpcSecurityCallback(void *,void *)

- ea: `0x18003fea0`
- end: `0x18004016f`
- name: `?NlRpcSecurityCallback@@YAJPEAX0@Z`
- size: `719`
- prototype: `int(void *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003700`
- `0x180007278`
- `0x18000e270`
- `0x18000ed34`
- `0x18003f85c`
- `0x18003fea0`

## import_xrefs

- `RPCRT4!RpcServerInqCallAttributesW` at `0x18003fef3`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18003fef3`
- `RPCRT4!RpcBindingServerFromClient` at `0x180040030`
- `RPCRT4!RpcBindingServerFromClient` at `0x180040030`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180040045`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180040045`
- `RPCRT4!RpcStringFreeW` at `0x1800400fd`
- `RPCRT4!RpcStringFreeW` at `0x1800400fd`
- `RPCRT4!RpcBindingFree` at `0x1800400e8`
- `RPCRT4!RpcBindingFree` at `0x1800400e8`
- `ntdll!RtlAcquireResourceShared` at `0x18003ffaa`
- `ntdll!RtlAcquireResourceShared` at `0x18003ffaa`
- `ntdll!RtlReleaseResource` at `0x18003ffc3`
- `ntdll!RtlReleaseResource` at `0x18003fffd`
- `ntdll!RtlReleaseResource` at `0x18003ffc3`
- `ntdll!RtlReleaseResource` at `0x18003fffd`

## string_xrefs

- `0x18003ff02`: `NlRpcSecurityCallback: RpcServerInqCallAttributesW failed RpcStatus:0x%x\n`
- `0x18003ff26`: `NlRpcSecurityCallback: client called non-existent method OpNum:%d\n`
- `0x18003ff6f`: `NlRpcSecurityCallback: remote client called local-only method OpNum:%d Method:%S\n`
- `0x1800400b5`: `Allowing a denied DC-locator RPC call due to Netlogon DCLocatorRPCSecurityPolicy policy setting: OpNum:%d Method:%S\n`
- `0x180040064`: `NlRpcSecurityCallback: rejecting an unauthorized RPC call. Client info could not be retrieved due to %#x. OpNum:%d Method:%S\n`
- `0x1800400d4`: `NlRpcSecurityCallback: rejecting an unauthorized RPC call from %ws OpNum:%d Method:%S\n`
- `0x18004010d`: `Rejecting an RPC call due to error from AccessCheck: %#x OpNum:%d Method:%S\n`

## pseudocode

```c
__int64 __fastcall NlRpcSecurityCallback(void *a1, void *a2)
{
  unsigned int v3; // eax
  __int64 v4; // r8
  unsigned int v5; // ebx
  __int64 v7; // rbx
  __int64 v8; // rdi
  BOOL v9; // esi
  __int64 v10; // r8
  __int64 v11; // r8
  DWORD v12; // edx
  unsigned int v13; // esi
  unsigned int v14; // r14d
  int v15; // esi
  unsigned int v16; // eax
  DWORD v17; // edx
  __int64 v18; // [rsp+20h] [rbp-69h]
  RPC_WSTR StringBinding; // [rsp+30h] [rbp-59h] BYREF
  RPC_BINDING_HANDLE ServerBinding; // [rsp+38h] [rbp-51h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v22[52]; // [rsp+48h] [rbp-41h] BYREF
  int v23; // [rsp+7Ch] [rbp-Dh]
  unsigned __int16 v24; // [rsp+98h] [rbp+Fh]

  memset_0(v22, 0, 0x68u);
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 96;
  v3 = RpcServerInqCallAttributesW(a2, RpcCallAttributes);
  v5 = v3;
  if ( v3 )
  {
    NlPrintRoutine(0x100u, L"NlRpcSecurityCallback: RpcServerInqCallAttributesW failed RpcStatus:0x%x\n", v3);
    return v5;
  }
  v7 = v24;
  if ( v24 >= 0x3Cu )
  {
    NlPrintRoutine(0x100u, L"NlRpcSecurityCallback: client called non-existent method OpNum:%d\n", v24);
    return 0;
  }
  if ( (unsigned __int16)(v24 - 9) <= 1u )
  {
    NlPrintRoutine(0x800u, L"Rejecting deprecated function opcode:%d.\n", v24);
    return 5;
  }
  v8 = 3LL * v24;
  if ( *((_DWORD *)&NlRPCFunctionProperties + 6 * v24) || v23 == 1 )
  {
    v9 = *((_DWORD *)&NlRPCFunctionProperties + 6 * v24 + 1) == 0;
    if ( NlGlobalMemberWorkstation )
    {
      RtlAcquireResourceShared(&NlGlobalRpcSecurityDescriptorLock, 1u);
      if ( NlGlobalRpcSecurityDescriptor )
      {
        v13 = NetpAccessCheck2(NlGlobalRpcSecurityDescriptor, 1u, v10, v9);
        RtlReleaseResource(&NlGlobalRpcSecurityDescriptorLock);
      }
      else
      {
        RtlReleaseResource(&NlGlobalRpcSecurityDescriptorLock);
        v12 = *((_DWORD *)&NlRPCFunctionProperties + 6 * v7 + 2);
        if ( !v12 )
          return 0;
        v13 = NetpAccessCheck2(NlGlobalNetlogonSecurityDescriptor, v12, v11, v9);
      }
      if ( v13 )
      {
        v14 = v7;
        goto LABEL_17;
      }
    }
    else
    {
      v17 = *((_DWORD *)&NlRPCFunctionProperties + 6 * v24 + 3);
      if ( v17 )
      {
        if ( v23 != 1 )
        {
          v13 = NetpAccessCheck2(
                  NlGlobalNetlogonSecurityDescriptor,
                  v17,
                  v4,
                  *((_DWORD *)&NlRPCFunctionProperties + 6 * v24 + 1) == 0);
          if ( v13 )
          {
            v14 = v7;
            if ( !(unsigned int)CheckDCLocatorRPCSecurityPolicyBypass(
                                  a2,
                                  v7,
                                  (char *)*(&NlRPCFunctionProperties + 3 * v7 + 2)) )
            {
LABEL_17:
              v5 = 5;
              if ( v13 == 5 )
              {
                v15 = 0;
                ServerBinding = 0;
                StringBinding = 0;
                v16 = RpcBindingServerFromClient(a2, &ServerBinding);
                if ( !v16 )
                {
                  v15 = 1;
                  v16 = RpcBindingToStringBindingW(ServerBinding, &StringBinding);
                }
                v18 = (__int64)*(&NlRPCFunctionProperties + v8 + 2);
                if ( v16 )
                  NlPrintRoutine(
                    0x100u,
                    L"NlRpcSecurityCallback: rejecting an unauthorized RPC call. Client info could not be retrieved due to"
                     " %#x. OpNum:%d Method:%S\n",
                    v16,
                    v14,
                    v18);
                else
                  NlPrintRoutine(
                    0x100u,
                    L"NlRpcSecurityCallback: rejecting an unauthorized RPC call from %ws OpNum:%d Method:%S\n",
                    StringBinding,
                    v14,
                    v18);
                if ( v15 )
                  RpcBindingFree(&ServerBinding);
                if ( StringBinding )
                  RpcStringFreeW(&StringBinding);
              }
              else
              {
                NlPrintRoutine(
                  0x100u,
                  L"Rejecting an RPC call due to error from AccessCheck: %#x OpNum:%d Method:%S\n",
                  v13,
                  v14,
                  *(&NlRPCFunctionProperties + v8 + 2));
              }
              return v5;
            }
            NlPrintRoutine(
              0x100u,
              L"Allowing a denied DC-locator RPC call due to Netlogon DCLocatorRPCSecurityPolicy policy setting: OpNum:%d Method:%S\n",
              (unsigned int)v7,
              *(&NlRPCFunctionProperties + 3 * v7 + 2));
          }
        }
      }
    }
    return 0;
  }
  NlPrintRoutine(
    0x100u,
    L"NlRpcSecurityCallback: remote client called local-only method OpNum:%d Method:%S\n",
    v24,
    *(&NlRPCFunctionProperties + 3 * v24 + 2));
  return 5;
}

```

## disassembly

```asm
0x18003fea0  mov     [rsp-8+arg_0], rbx
0x18003fea5  mov     [rsp-8+arg_10], rsi
0x18003feaa  push    rbp
0x18003feab  push    rdi
0x18003feac  push    r13
0x18003feae  push    r14
0x18003feb0  push    r15
0x18003feb2  lea     rbp, [rsp-37h]
0x18003feb7  sub     rsp, 0C0h
0x18003febe  mov     rax, cs:__security_cookie
0x18003fec5  xor     rax, rsp
0x18003fec8  mov     [rbp+57h+var_30], rax
0x18003fecc  mov     r15, rdx
0x18003fecf  lea     rcx, [rbp+57h+var_98]; void *
0x18003fed3  xor     edx, edx; Val
0x18003fed5  lea     r8d, [rdx+68h]; Size
0x18003fed9  call    memset_0
0x18003fede  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18003fee2  mov     [rbp+57h+RpcCallAttributes], 2
0x18003fee9  mov     rcx, r15; ClientBinding
0x18003feec  mov     [rbp+57h+var_9C], 60h ; '`'
0x18003fef3  call    cs:__imp_RpcServerInqCallAttributesW
0x18003fef9  mov     ebx, eax
0x18003fefb  test    eax, eax
0x18003fefd  jz      short loc_18003FF1A
0x18003feff  mov     r8d, eax
0x18003ff02  lea     rdx, aNlrpcsecurityc_2; "NlRpcSecurityCallback: RpcServerInqCall"...
0x18003ff09  mov     ecx, 100h; unsigned int
0x18003ff0e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ff13  mov     eax, ebx
0x18003ff15  jmp     loc_180040147
0x18003ff1a  movzx   ebx, [rbp+57h+var_48]
0x18003ff1e  cmp     ebx, 3Ch ; '<'
0x18003ff21  jb      short loc_18003FF3E
0x18003ff23  mov     r8d, ebx
0x18003ff26  lea     rdx, aNlrpcsecurityc_1; "NlRpcSecurityCallback: client called no"...
0x18003ff2d  mov     ecx, 100h; unsigned int
0x18003ff32  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ff37  xor     eax, eax
0x18003ff39  jmp     loc_180040147
0x18003ff3e  lea     eax, [rbx-9]
0x18003ff41  mov     r14d, 1
0x18003ff47  cmp     ax, r14w
0x18003ff4b  jbe     loc_18004012E
0x18003ff51  lea     rdi, [rbx+rbx*2]
0x18003ff55  lea     r13, ?NlRPCFunctionProperties@@3PAU_NETLOGON_RPC_FUNCTION_PROPERTIES@@A; _NETLOGON_RPC_FUNCTION_PROPERTIES near * NlRPCFunctionProperties
0x18003ff5c  cmp     dword ptr [r13+rdi*8+0], 0
0x18003ff62  jnz     short loc_18003FF88
0x18003ff64  cmp     [rbp+57h+var_64], r14d
0x18003ff68  jz      short loc_18003FF88
0x18003ff6a  mov     r9, [r13+rdi*8+10h]
0x18003ff6f  lea     rdx, aNlrpcsecurityc_0; "NlRpcSecurityCallback: remote client ca"...
0x18003ff76  mov     r8d, ebx
0x18003ff79  mov     ecx, 100h; unsigned int
0x18003ff7e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ff83  jmp     loc_180040142
0x18003ff88  xor     esi, esi
0x18003ff8a  cmp     [r13+rdi*8+4], esi
0x18003ff8f  setz    sil
0x18003ff93  cmp     cs:?NlGlobalMemberWorkstation@@3HA, 0; int NlGlobalMemberWorkstation
0x18003ff9a  jz      loc_180040072
0x18003ffa0  mov     dl, r14b; Wait
0x18003ffa3  lea     rcx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x18003ffaa  call    cs:__imp_RtlAcquireResourceShared
0x18003ffb0  mov     rcx, cs:?NlGlobalRpcSecurityDescriptor@@3PEAXEA; pSecurityDescriptor
0x18003ffb7  test    rcx, rcx
0x18003ffba  jnz     short loc_18003FFE9
0x18003ffbc  lea     rcx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x18003ffc3  call    cs:__imp_RtlReleaseResource
0x18003ffc9  mov     edx, [r13+rdi*8+8]; DesiredAccess
0x18003ffce  test    edx, edx
0x18003ffd0  jz      loc_1800400C9
0x18003ffd6  mov     rcx, cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA; pSecurityDescriptor
0x18003ffdd  mov     r9d, esi
0x18003ffe0  call    NetpAccessCheck2
0x18003ffe5  mov     esi, eax
0x18003ffe7  jmp     short loc_180040003
0x18003ffe9  mov     r9d, esi
0x18003ffec  mov     edx, r14d; DesiredAccess
0x18003ffef  call    NetpAccessCheck2
0x18003fff4  lea     rcx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x18003fffb  mov     esi, eax
0x18003fffd  call    cs:__imp_RtlReleaseResource
0x180040003  test    esi, esi
0x180040005  jz      loc_1800400C9
0x18004000b  mov     r14d, ebx
0x18004000e  mov     ebx, 5
0x180040013  cmp     esi, ebx
0x180040015  jnz     loc_180040108
0x18004001b  xor     esi, esi
0x18004001d  mov     [rbp+57h+ServerBinding], 0
0x180040025  lea     rdx, [rbp+57h+ServerBinding]; ServerBinding
0x180040029  mov     [rbp+57h+StringBinding], rsi
0x18004002d  mov     rcx, r15; ClientBinding
0x180040030  call    cs:__imp_RpcBindingServerFromClient
0x180040036  test    eax, eax
0x180040038  jnz     short loc_18004004B
0x18004003a  mov     rcx, [rbp+57h+ServerBinding]; Binding
0x18004003e  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x180040042  lea     esi, [rbx-4]
0x180040045  call    cs:__imp_RpcBindingToStringBindingW
0x18004004b  mov     rcx, [r13+rdi*8+10h]
0x180040050  mov     r9d, r14d
0x180040053  mov     [rsp+0E0h+var_C0], rcx
0x180040058  mov     ecx, 100h; unsigned int
0x18004005d  test    eax, eax
0x18004005f  jz      short loc_1800400D0
0x180040061  mov     r8d, eax
0x180040064  lea     rdx, aNlrpcsecurityc_3; "NlRpcSecurityCallback: rejecting an una"...
0x18004006b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040070  jmp     short loc_1800400E0
0x180040072  mov     edx, [r13+rdi*8+0Ch]; DesiredAccess
0x180040077  test    edx, edx
0x180040079  jz      short loc_1800400C9
0x18004007b  cmp     [rbp+57h+var_64], r14d
0x18004007f  jz      short loc_1800400C9
0x180040081  mov     rcx, cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA; pSecurityDescriptor
0x180040088  mov     r9d, esi
0x18004008b  call    NetpAccessCheck2
0x180040090  mov     esi, eax
0x180040092  test    eax, eax
0x180040094  jz      short loc_1800400C9
0x180040096  mov     r8, [r13+rdi*8+10h]; char *
0x18004009b  mov     edx, ebx; unsigned int
0x18004009d  mov     rcx, r15; void *
0x1800400a0  mov     r14d, ebx
0x1800400a3  call    ?CheckDCLocatorRPCSecurityPolicyBypass@@YAHPEAXKPEAD@Z; CheckDCLocatorRPCSecurityPolicyBypass(void *,ulong,char *)
0x1800400a8  test    eax, eax
0x1800400aa  jz      loc_18004000E
0x1800400b0  mov     r9, [r13+rdi*8+10h]
0x1800400b5  lea     rdx, aAllowingADenie; "Allowing a denied DC-locator RPC call d"...
0x1800400bc  mov     r8d, ebx
0x1800400bf  mov     ecx, 100h; unsigned int
0x1800400c4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800400c9  xor     ebx, ebx
0x1800400cb  jmp     loc_18003FF13
0x1800400d0  mov     r8, [rbp+57h+StringBinding]
0x1800400d4  lea     rdx, aNlrpcsecurityc; "NlRpcSecurityCallback: rejecting an una"...
0x1800400db  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800400e0  test    esi, esi
0x1800400e2  jz      short loc_1800400EE
0x1800400e4  lea     rcx, [rbp+57h+ServerBinding]; Binding
0x1800400e8  call    cs:__imp_RpcBindingFree
0x1800400ee  cmp     [rbp+57h+StringBinding], 0
0x1800400f3  jz      loc_18003FF13
0x1800400f9  lea     rcx, [rbp+57h+StringBinding]; String
0x1800400fd  call    cs:__imp_RpcStringFreeW
0x180040103  jmp     loc_18003FF13
0x180040108  mov     rax, [r13+rdi*8+10h]
0x18004010d  lea     rdx, aRejectingAnRpc; "Rejecting an RPC call due to error from"...
0x180040114  mov     r9d, r14d
0x180040117  mov     [rsp+0E0h+var_C0], rax
0x18004011c  mov     r8d, esi
0x18004011f  mov     ecx, 100h; unsigned int
0x180040124  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040129  jmp     loc_18003FF13
0x18004012e  mov     r8d, ebx
0x180040131  lea     rdx, aRejectingDepre; "Rejecting deprecated function opcode:%d"...
0x180040138  mov     ecx, 800h; unsigned int
0x18004013d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040142  mov     eax, 5
0x180040147  mov     rcx, [rbp+57h+var_30]
0x18004014b  xor     rcx, rsp; StackCookie
0x18004014e  call    __security_check_cookie
0x180040153  lea     r11, [rsp+0E0h+var_20]
0x18004015b  mov     rbx, [r11+30h]
0x18004015f  mov     rsi, [r11+40h]
0x180040163  mov     rsp, r11
0x180040166  pop     r15
0x180040168  pop     r14
0x18004016a  pop     r13
0x18004016c  pop     rdi
0x18004016d  pop     rbp
0x18004016e  retn
```
