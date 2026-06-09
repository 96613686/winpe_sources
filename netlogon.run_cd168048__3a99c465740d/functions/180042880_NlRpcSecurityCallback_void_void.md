# NlRpcSecurityCallback(void *,void *)

- ea: `0x180042880`
- end: `0x180042b80`
- name: `?NlRpcSecurityCallback@@YAJPEAX0@Z`
- size: `768`
- prototype: `int(void *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003890`
- `0x180007518`
- `0x18000e910`
- `0x18000f3e4`
- `0x1800421bc`
- `0x180042880`

## import_xrefs

- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800428d3`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800428d3`
- `RPCRT4!RpcBindingServerFromClient` at `0x180042a28`
- `RPCRT4!RpcBindingServerFromClient` at `0x180042a28`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180042a43`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180042a43`
- `RPCRT4!RpcStringFreeW` at `0x180042b07`
- `RPCRT4!RpcStringFreeW` at `0x180042b07`
- `RPCRT4!RpcBindingFree` at `0x180042aec`
- `RPCRT4!RpcBindingFree` at `0x180042aec`
- `ntdll!RtlAcquireResourceShared` at `0x180042990`
- `ntdll!RtlAcquireResourceShared` at `0x180042990`
- `ntdll!RtlReleaseResource` at `0x1800429af`
- `ntdll!RtlReleaseResource` at `0x1800429ef`
- `ntdll!RtlReleaseResource` at `0x1800429af`
- `ntdll!RtlReleaseResource` at `0x1800429ef`

## string_xrefs

- `0x1800428e8`: `NlRpcSecurityCallback: RpcServerInqCallAttributesW failed RpcStatus:0x%x\n`
- `0x18004290c`: `NlRpcSecurityCallback: client called non-existent method OpNum:%d\n`
- `0x180042955`: `NlRpcSecurityCallback: remote client called local-only method OpNum:%d Method:%S\n`
- `0x180042ab9`: `Allowing a denied DC-locator RPC call due to Netlogon DCLocatorRPCSecurityPolicy policy setting: OpNum:%d Method:%S\n`
- `0x180042a68`: `NlRpcSecurityCallback: rejecting an unauthorized RPC call. Client info could not be retrieved due to %#x. OpNum:%d Method:%S\n`
- `0x180042ad8`: `NlRpcSecurityCallback: rejecting an unauthorized RPC call from %ws OpNum:%d Method:%S\n`
- `0x180042b1d`: `Rejecting an RPC call due to error from AccessCheck: %#x OpNum:%d Method:%S\n`

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
0x180042880  mov     [rsp-8+arg_0], rbx
0x180042885  mov     [rsp-8+arg_10], rsi
0x18004288a  push    rbp
0x18004288b  push    rdi
0x18004288c  push    r13
0x18004288e  push    r14
0x180042890  push    r15
0x180042892  lea     rbp, [rsp-37h]
0x180042897  sub     rsp, 0C0h
0x18004289e  mov     rax, cs:__security_cookie
0x1800428a5  xor     rax, rsp
0x1800428a8  mov     [rbp+57h+var_30], rax
0x1800428ac  mov     r15, rdx
0x1800428af  lea     rcx, [rbp+57h+var_98]; void *
0x1800428b3  xor     edx, edx; Val
0x1800428b5  lea     r8d, [rdx+68h]; Size
0x1800428b9  call    memset_0
0x1800428be  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x1800428c2  mov     [rbp+57h+RpcCallAttributes], 2
0x1800428c9  mov     rcx, r15; ClientBinding
0x1800428cc  mov     [rbp+57h+var_9C], 60h ; '`'
0x1800428d3  call    cs:__imp_RpcServerInqCallAttributesW
0x1800428da  nop     dword ptr [rax+rax+00h]
0x1800428df  mov     ebx, eax
0x1800428e1  test    eax, eax
0x1800428e3  jz      short loc_180042900
0x1800428e5  mov     r8d, eax
0x1800428e8  lea     rdx, aNlrpcsecurityc_2; "NlRpcSecurityCallback: RpcServerInqCall"...
0x1800428ef  mov     ecx, 100h; unsigned int
0x1800428f4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800428f9  mov     eax, ebx
0x1800428fb  jmp     loc_180042B57
0x180042900  movzx   ebx, [rbp+57h+var_48]
0x180042904  cmp     ebx, 3Ch ; '<'
0x180042907  jb      short loc_180042924
0x180042909  mov     r8d, ebx
0x18004290c  lea     rdx, aNlrpcsecurityc_1; "NlRpcSecurityCallback: client called no"...
0x180042913  mov     ecx, 100h; unsigned int
0x180042918  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004291d  xor     eax, eax
0x18004291f  jmp     loc_180042B57
0x180042924  lea     eax, [rbx-9]
0x180042927  mov     r14d, 1
0x18004292d  cmp     ax, r14w
0x180042931  jbe     loc_180042B3E
0x180042937  lea     rdi, [rbx+rbx*2]
0x18004293b  lea     r13, ?NlRPCFunctionProperties@@3PAU_NETLOGON_RPC_FUNCTION_PROPERTIES@@A; _NETLOGON_RPC_FUNCTION_PROPERTIES near * NlRPCFunctionProperties
0x180042942  cmp     dword ptr [r13+rdi*8+0], 0
0x180042948  jnz     short loc_18004296E
0x18004294a  cmp     [rbp+57h+var_64], r14d
0x18004294e  jz      short loc_18004296E
0x180042950  mov     r9, [r13+rdi*8+10h]
0x180042955  lea     rdx, aNlrpcsecurityc_0; "NlRpcSecurityCallback: remote client ca"...
0x18004295c  mov     r8d, ebx
0x18004295f  mov     ecx, 100h; unsigned int
0x180042964  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042969  jmp     loc_180042B52
0x18004296e  xor     esi, esi
0x180042970  cmp     [r13+rdi*8+4], esi
0x180042975  setz    sil
0x180042979  cmp     cs:?NlGlobalMemberWorkstation@@3HA, 0; int NlGlobalMemberWorkstation
0x180042980  jz      loc_180042A76
0x180042986  mov     dl, r14b; Wait
0x180042989  lea     rcx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x180042990  call    cs:__imp_RtlAcquireResourceShared
0x180042997  nop     dword ptr [rax+rax+00h]
0x18004299c  mov     rcx, cs:?NlGlobalRpcSecurityDescriptor@@3PEAXEA; pSecurityDescriptor
0x1800429a3  test    rcx, rcx
0x1800429a6  jnz     short loc_1800429DB
0x1800429a8  lea     rcx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x1800429af  call    cs:__imp_RtlReleaseResource
0x1800429b6  nop     dword ptr [rax+rax+00h]
0x1800429bb  mov     edx, [r13+rdi*8+8]; DesiredAccess
0x1800429c0  test    edx, edx
0x1800429c2  jz      loc_180042ACD
0x1800429c8  mov     rcx, cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA; pSecurityDescriptor
0x1800429cf  mov     r9d, esi
0x1800429d2  call    NetpAccessCheck2
0x1800429d7  mov     esi, eax
0x1800429d9  jmp     short loc_1800429FB
0x1800429db  mov     r9d, esi
0x1800429de  mov     edx, r14d; DesiredAccess
0x1800429e1  call    NetpAccessCheck2
0x1800429e6  lea     rcx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x1800429ed  mov     esi, eax
0x1800429ef  call    cs:__imp_RtlReleaseResource
0x1800429f6  nop     dword ptr [rax+rax+00h]
0x1800429fb  test    esi, esi
0x1800429fd  jz      loc_180042ACD
0x180042a03  mov     r14d, ebx
0x180042a06  mov     ebx, 5
0x180042a0b  cmp     esi, ebx
0x180042a0d  jnz     loc_180042B18
0x180042a13  xor     esi, esi
0x180042a15  mov     [rbp+57h+ServerBinding], 0
0x180042a1d  lea     rdx, [rbp+57h+ServerBinding]; ServerBinding
0x180042a21  mov     [rbp+57h+StringBinding], rsi
0x180042a25  mov     rcx, r15; ClientBinding
0x180042a28  call    cs:__imp_RpcBindingServerFromClient
0x180042a2f  nop     dword ptr [rax+rax+00h]
0x180042a34  test    eax, eax
0x180042a36  jnz     short loc_180042A4F
0x180042a38  mov     rcx, [rbp+57h+ServerBinding]; Binding
0x180042a3c  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x180042a40  lea     esi, [rbx-4]
0x180042a43  call    cs:__imp_RpcBindingToStringBindingW
0x180042a4a  nop     dword ptr [rax+rax+00h]
0x180042a4f  mov     rcx, [r13+rdi*8+10h]
0x180042a54  mov     r9d, r14d
0x180042a57  mov     [rsp+0E0h+var_C0], rcx
0x180042a5c  mov     ecx, 100h; unsigned int
0x180042a61  test    eax, eax
0x180042a63  jz      short loc_180042AD4
0x180042a65  mov     r8d, eax
0x180042a68  lea     rdx, aNlrpcsecurityc_3; "NlRpcSecurityCallback: rejecting an una"...
0x180042a6f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042a74  jmp     short loc_180042AE4
0x180042a76  mov     edx, [r13+rdi*8+0Ch]; DesiredAccess
0x180042a7b  test    edx, edx
0x180042a7d  jz      short loc_180042ACD
0x180042a7f  cmp     [rbp+57h+var_64], r14d
0x180042a83  jz      short loc_180042ACD
0x180042a85  mov     rcx, cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA; pSecurityDescriptor
0x180042a8c  mov     r9d, esi
0x180042a8f  call    NetpAccessCheck2
0x180042a94  mov     esi, eax
0x180042a96  test    eax, eax
0x180042a98  jz      short loc_180042ACD
0x180042a9a  mov     r8, [r13+rdi*8+10h]; char *
0x180042a9f  mov     edx, ebx; unsigned int
0x180042aa1  mov     rcx, r15; void *
0x180042aa4  mov     r14d, ebx
0x180042aa7  call    ?CheckDCLocatorRPCSecurityPolicyBypass@@YAHPEAXKPEAD@Z; CheckDCLocatorRPCSecurityPolicyBypass(void *,ulong,char *)
0x180042aac  test    eax, eax
0x180042aae  jz      loc_180042A06
0x180042ab4  mov     r9, [r13+rdi*8+10h]
0x180042ab9  lea     rdx, aAllowingADenie; "Allowing a denied DC-locator RPC call d"...
0x180042ac0  mov     r8d, ebx
0x180042ac3  mov     ecx, 100h; unsigned int
0x180042ac8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042acd  xor     ebx, ebx
0x180042acf  jmp     loc_1800428F9
0x180042ad4  mov     r8, [rbp+57h+StringBinding]
0x180042ad8  lea     rdx, aNlrpcsecurityc; "NlRpcSecurityCallback: rejecting an una"...
0x180042adf  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042ae4  test    esi, esi
0x180042ae6  jz      short loc_180042AF8
0x180042ae8  lea     rcx, [rbp+57h+ServerBinding]; Binding
0x180042aec  call    cs:__imp_RpcBindingFree
0x180042af3  nop     dword ptr [rax+rax+00h]
0x180042af8  cmp     [rbp+57h+StringBinding], 0
0x180042afd  jz      loc_1800428F9
0x180042b03  lea     rcx, [rbp+57h+StringBinding]; String
0x180042b07  call    cs:__imp_RpcStringFreeW
0x180042b0e  nop     dword ptr [rax+rax+00h]
0x180042b13  jmp     loc_1800428F9
0x180042b18  mov     rax, [r13+rdi*8+10h]
0x180042b1d  lea     rdx, aRejectingAnRpc; "Rejecting an RPC call due to error from"...
0x180042b24  mov     r9d, r14d
0x180042b27  mov     [rsp+0E0h+var_C0], rax
0x180042b2c  mov     r8d, esi
0x180042b2f  mov     ecx, 100h; unsigned int
0x180042b34  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042b39  jmp     loc_1800428F9
0x180042b3e  mov     r8d, ebx
0x180042b41  lea     rdx, aRejectingDepre; "Rejecting deprecated function opcode:%d"...
0x180042b48  mov     ecx, 800h; unsigned int
0x180042b4d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042b52  mov     eax, 5
0x180042b57  mov     rcx, [rbp+57h+var_30]
0x180042b5b  xor     rcx, rsp; StackCookie
0x180042b5e  call    __security_check_cookie
0x180042b63  lea     r11, [rsp+0E0h+var_20]
0x180042b6b  mov     rbx, [r11+30h]
0x180042b6f  mov     rsi, [r11+40h]
0x180042b73  mov     rsp, r11
0x180042b76  pop     r15
0x180042b78  pop     r14
0x180042b7a  pop     r13
0x180042b7c  pop     rdi
0x180042b7d  pop     rbp
0x180042b7e  retn
```
