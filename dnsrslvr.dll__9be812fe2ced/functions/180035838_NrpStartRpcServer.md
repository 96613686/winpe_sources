# NrpStartRpcServer

- ea: `0x180035838`
- end: `0x180035a2d`
- name: `NrpStartRpcServer`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800494f8`

## callees

- `0x180035838`
- `0x180046ec0`
- `0x180047818`
- `0x180051c5c`
- `0x180086b1c`

## import_xrefs

- `RPCRT4!RpcServerRegisterIfEx` at `0x180035922`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180035922`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800358cc`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800358cc`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800359ca`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800359ca`
- `RPCRT4!RpcBindingVectorFree` at `0x180035998`
- `RPCRT4!RpcBindingVectorFree` at `0x180035998`
- `RPCRT4!RpcServerInqBindings` at `0x18003594e`
- `RPCRT4!RpcServerInqBindings` at `0x18003594e`
- `RPCRT4!RpcEpRegisterW` at `0x180035983`
- `RPCRT4!RpcEpRegisterW` at `0x180035983`
- `WS2_32!__imp_WSAStartup` at `0x1800358ab`
- `WS2_32!__imp_WSAStartup` at `0x1800358ab`
- `WS2_32!__imp_WSACleanup` at `0x1800359d0`
- `WS2_32!__imp_WSACleanup` at `0x1800359d0`

## pseudocode

```c
int __fastcall NrpStartRpcServer(unsigned __int8 a1)
{
  unsigned int v1; // ebx
  int result; // eax
  unsigned int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r9
  RPC_BINDING_VECTOR *BindingVector[2]; // [rsp+30h] [rbp-1C8h] BYREF
  WSAData WSAData; // [rsp+40h] [rbp-1B8h] BYREF

  v1 = a1;
  BindingVector[0] = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 16, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids, v1);
  result = WSAStartup(0x202u, &WSAData);
  if ( !result )
  {
    RpcAllowUserMode = v1;
    v3 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, 0);
    v4 = v3;
    if ( v3 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      {
LABEL_22:
        WSACleanup();
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_d(1035, 21, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids, v4);
        return v4;
      }
      v5 = 17;
LABEL_7:
      WPP_SF_d(1035, v5, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids, v3);
      goto LABEL_22;
    }
    v3 = RpcServerRegisterIfEx(qword_180091050, 0, 0, 0x29u, 0x4D2u, NrpSecurityCallBack);
    v4 = v3;
    if ( v3 && v3 != 1713 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_22;
      v5 = 18;
      goto LABEL_7;
    }
    v6 = RpcServerInqBindings(BindingVector);
    v4 = v6;
    if ( v6 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      {
LABEL_21:
        RpcServerUnregisterIfEx(qword_180091050, 0, 1);
        goto LABEL_22;
      }
      v7 = 19;
      v8 = v6;
    }
    else
    {
      v4 = RpcEpRegisterW(qword_180091050, BindingVector[0], 0, (RPC_WSTR)L"NRP server endpoint");
      if ( BindingVector[0] )
        RpcBindingVectorFree(BindingVector);
      if ( !v4 )
      {
        RpcServerInitialized = 1;
        NrpNotifyAfd(1u);
        return 0;
      }
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_21;
      v7 = 20;
      v8 = v4;
    }
    WPP_SF_d(1035, v7, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids, v8);
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x180035838  mov     [rsp+arg_8], rbx
0x18003583d  mov     [rsp+arg_10], rbp
0x180035842  push    rsi
0x180035843  sub     rsp, 1F0h
0x18003584a  mov     rax, cs:__security_cookie
0x180035851  xor     rax, rsp
0x180035854  mov     [rsp+1F8h+var_18], rax
0x18003585c  movzx   ebx, cl
0x18003585f  xor     edx, edx; Val
0x180035861  lea     rcx, [rsp+1F8h+WSAData]; void *
0x180035866  mov     [rsp+1F8h+BindingVector], 0
0x18003586f  mov     r8d, 198h; Size
0x180035875  call    memset_0
0x18003587a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180035881  lea     rbp, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids
0x180035888  mov     esi, 40Bh
0x18003588d  jz      short loc_1800358A1
0x18003588f  mov     r9d, ebx
0x180035892  mov     edx, 10h
0x180035897  mov     ecx, esi
0x180035899  mov     r8, rbp
0x18003589c  call    WPP_SF_d
0x1800358a1  mov     ecx, 202h; wVersionRequested
0x1800358a6  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x1800358ab  call    cs:__imp_WSAStartup
0x1800358b1  test    eax, eax
0x1800358b3  jnz     loc_180035A08
0x1800358b9  xor     r8d, r8d; SecurityDescriptor
0x1800358bc  mov     cs:RpcAllowUserMode, bl
0x1800358c2  lea     edx, [rax+0Ah]; MaxCalls
0x1800358c5  lea     rcx, Protseq; "ncalrpc"
0x1800358cc  call    cs:__imp_RpcServerUseProtseqW
0x1800358d2  mov     ebx, eax
0x1800358d4  test    eax, eax
0x1800358d6  jz      short loc_1800358FC
0x1800358d8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800358df  jz      loc_1800359D0
0x1800358e5  mov     edx, 11h
0x1800358ea  mov     ecx, esi
0x1800358ec  mov     r9d, eax
0x1800358ef  mov     r8, rbp
0x1800358f2  call    WPP_SF_d
0x1800358f7  jmp     loc_1800359D0
0x1800358fc  lea     rax, NrpSecurityCallBack
0x180035903  mov     r9d, 29h ; ')'; Flags
0x180035909  mov     [rsp+1F8h+IfCallback], rax; IfCallback
0x18003590e  lea     rcx, qword_180091050; IfSpec
0x180035915  xor     r8d, r8d; MgrEpv
0x180035918  mov     [rsp+1F8h+MaxCalls], 4D2h; MaxCalls
0x180035920  xor     edx, edx; MgrTypeUuid
0x180035922  call    cs:__imp_RpcServerRegisterIfEx
0x180035928  mov     ebx, eax
0x18003592a  test    eax, eax
0x18003592c  jz      short loc_180035949
0x18003592e  cmp     eax, 6B1h
0x180035933  jz      short loc_180035949
0x180035935  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003593c  jz      loc_1800359D0
0x180035942  mov     edx, 12h
0x180035947  jmp     short loc_1800358EA
0x180035949  lea     rcx, [rsp+1F8h+BindingVector]; BindingVector
0x18003594e  call    cs:__imp_RpcServerInqBindings
0x180035954  mov     ebx, eax
0x180035956  test    eax, eax
0x180035958  jz      short loc_18003596D
0x18003595a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180035961  jz      short loc_1800359BD
0x180035963  mov     edx, 13h
0x180035968  mov     r9d, eax
0x18003596b  jmp     short loc_1800359B3
0x18003596d  mov     rdx, [rsp+1F8h+BindingVector]; BindingVector
0x180035972  lea     r9, Annotation; "NRP server endpoint"
0x180035979  xor     r8d, r8d; UuidVector
0x18003597c  lea     rcx, qword_180091050; IfSpec
0x180035983  call    cs:__imp_RpcEpRegisterW
0x180035989  cmp     [rsp+1F8h+BindingVector], 0
0x18003598f  mov     ebx, eax
0x180035991  jz      short loc_18003599E
0x180035993  lea     rcx, [rsp+1F8h+BindingVector]; BindingVector
0x180035998  call    cs:__imp_RpcBindingVectorFree
0x18003599e  test    ebx, ebx
0x1800359a0  jz      short loc_1800359F5
0x1800359a2  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800359a9  jz      short loc_1800359BD
0x1800359ab  mov     edx, 14h
0x1800359b0  mov     r9d, ebx
0x1800359b3  mov     r8, rbp
0x1800359b6  mov     ecx, esi
0x1800359b8  call    WPP_SF_d
0x1800359bd  xor     edx, edx; MgrTypeUuid
0x1800359bf  lea     rcx, qword_180091050; IfSpec
0x1800359c6  lea     r8d, [rdx+1]; RundownContextHandles
0x1800359ca  call    cs:__imp_RpcServerUnregisterIfEx
0x1800359d0  call    cs:__imp_WSACleanup
0x1800359d6  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800359dd  jz      short loc_1800359F1
0x1800359df  mov     edx, 15h
0x1800359e4  mov     ecx, esi
0x1800359e6  mov     r9d, ebx
0x1800359e9  mov     r8, rbp
0x1800359ec  call    WPP_SF_d
0x1800359f1  mov     eax, ebx
0x1800359f3  jmp     short loc_180035A08
0x1800359f5  mov     ecx, 1
0x1800359fa  mov     cs:RpcServerInitialized, 1
0x180035a01  call    NrpNotifyAfd
0x180035a06  xor     eax, eax
0x180035a08  mov     rcx, [rsp+1F8h+var_18]
0x180035a10  xor     rcx, rsp; StackCookie
0x180035a13  call    __security_check_cookie
0x180035a18  lea     r11, [rsp+1F8h+var_8]
0x180035a20  mov     rbx, [r11+18h]
0x180035a24  mov     rbp, [r11+20h]
0x180035a28  mov     rsp, r11
0x180035a2b  pop     rsi
0x180035a2c  retn
```
