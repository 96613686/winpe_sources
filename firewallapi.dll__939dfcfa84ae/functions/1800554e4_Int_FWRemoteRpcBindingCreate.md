# Int_FWRemoteRpcBindingCreate

- ea: `0x1800554e4`
- end: `0x1800557b4`
- name: `Int_FWRemoteRpcBindingCreate`
- size: `720`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e750`

## callees

- `0x180005e0c`
- `0x180026798`
- `0x1800294b0`
- `0x18003336c`
- `0x1800554e4`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180055583`
- `RPCRT4!RpcStringBindingComposeW` at `0x180055583`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800555c1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800555c1`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800556f7`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800556f7`
- `RPCRT4!RpcBindingSetOption` at `0x180055645`
- `RPCRT4!RpcBindingSetOption` at `0x180055645`
- `RPCRT4!RpcEpResolveBinding` at `0x180055602`
- `RPCRT4!RpcEpResolveBinding` at `0x180055602`
- `RPCRT4!RpcStringFreeW` at `0x180055765`
- `RPCRT4!RpcStringFreeW` at `0x180055765`
- `RPCRT4!RpcBindingFree` at `0x18005573a`
- `RPCRT4!RpcBindingFree` at `0x18005573a`
- `fwbase!FwConstructRemoteMachineSPN` at `0x180055682`
- `fwbase!FwConstructRemoteMachineSPN` at `0x180055682`
- `fwbase!FwBaseFree` at `0x180055785`
- `fwbase!FwBaseFree` at `0x180055785`

## pseudocode

```c
__int64 __fastcall Int_FWRemoteRpcBindingCreate(RPC_WSTR NetworkAddr, RPC_BINDING_HANDLE *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  FwPolicy2 *v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-30h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp-28h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+50h] [rbp-20h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+58h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 361, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  String = 0;
  Binding = 0;
  ServerPrincName = 0;
  *a2 = 0;
  SecurityQOS = 0;
  v4 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_ip_tcp", NetworkAddr, 0, 0, &String);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 362;
LABEL_28:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v4);
    }
  }
  else
  {
    v4 = RpcBindingFromStringBindingW(String, &Binding);
    v5 = v4;
    if ( v4 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 363;
        goto LABEL_28;
      }
    }
    else
    {
      v4 = RpcEpResolveBinding(Binding, qword_18007B4B0);
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 364;
          goto LABEL_28;
        }
      }
      else
      {
        v4 = RpcBindingSetOption(Binding, 0xBu, 1u);
        v5 = v4;
        if ( v4 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v7 = 365;
            goto LABEL_28;
          }
        }
        else
        {
          v4 = FwConstructRemoteMachineSPN(NetworkAddr, &ServerPrincName);
          v5 = v4;
          if ( v4 )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v7 = 366;
              goto LABEL_28;
            }
          }
          else
          {
            SecurityQOS.Version = 1;
            *(_QWORD *)&SecurityQOS.Capabilities = 1;
            SecurityQOS.ImpersonationType = 3;
            v4 = RpcBindingSetAuthInfoExW(Binding, ServerPrincName, 6u, 9u, 0, 0, &SecurityQOS);
            v5 = v4;
            if ( !v4 )
            {
              *a2 = Binding;
              goto LABEL_33;
            }
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v7 = 367;
              goto LABEL_28;
            }
          }
        }
      }
    }
  }
  if ( Binding )
  {
    v8 = RpcBindingFree(&Binding);
    if ( v8 )
      MicrosoftTelemetryAssertTriggeredArgs(v9, v8);
  }
LABEL_33:
  if ( String )
  {
    v10 = RpcStringFreeW(&String);
    if ( v10 )
      MicrosoftTelemetryAssertTriggeredArgs(v11, v10);
  }
  if ( ServerPrincName )
    FwBaseFree(ServerPrincName);
  return v5;
}

```

## disassembly

```asm
0x1800554e4  mov     [rsp-28h+arg_10], rbx
0x1800554e9  push    rbp
0x1800554ea  push    rsi
0x1800554eb  push    rdi
0x1800554ec  push    r12
0x1800554ee  push    r15
0x1800554f0  mov     rbp, rsp
0x1800554f3  sub     rsp, 70h
0x1800554f7  mov     rax, cs:__security_cookie
0x1800554fe  xor     rax, rsp
0x180055501  mov     [rbp+var_8], rax
0x180055505  mov     rdi, rdx
0x180055508  mov     rsi, rcx
0x18005550b  mov     rcx, cs:WPP_GLOBAL_Control
0x180055512  lea     r15, WPP_GLOBAL_Control
0x180055519  lea     r12, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180055520  cmp     rcx, r15
0x180055523  jz      short loc_18005553C
0x180055525  test    byte ptr [rcx+1Ch], 8
0x180055529  jz      short loc_18005553C
0x18005552b  mov     rcx, [rcx+10h]
0x18005552f  mov     edx, 169h
0x180055534  mov     r8, r12
0x180055537  call    WPP_SF_
0x18005553c  lea     rax, [rbp+String]
0x180055540  mov     [rbp+String], 0
0x180055548  xorps   xmm0, xmm0
0x18005554b  mov     [rsp+70h+StringBinding], rax; StringBinding
0x180055550  xor     r9d, r9d; Endpoint
0x180055553  mov     [rsp+70h+Options], 0; Options
0x18005555c  mov     r8, rsi; NetworkAddr
0x18005555f  mov     [rbp+Binding], 0
0x180055567  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x18005556e  mov     [rbp+ServerPrincName], 0
0x180055576  xor     ecx, ecx; ObjUuid
0x180055578  mov     qword ptr [rdi], 0
0x18005557f  movups  xmmword ptr [rbp+var_18.Version], xmm0
0x180055583  call    cs:__imp_RpcStringBindingComposeW
0x18005558a  nop     dword ptr [rax+rax+00h]
0x18005558f  mov     ebx, eax
0x180055591  test    eax, eax
0x180055593  jz      short loc_1800555B9
0x180055595  mov     rcx, cs:WPP_GLOBAL_Control
0x18005559c  cmp     rcx, r15
0x18005559f  jz      loc_18005572F
0x1800555a5  test    byte ptr [rcx+1Ch], 1
0x1800555a9  jz      loc_18005572F
0x1800555af  mov     edx, 16Ah
0x1800555b4  jmp     loc_180055720
0x1800555b9  mov     rcx, [rbp+String]; StringBinding
0x1800555bd  lea     rdx, [rbp+Binding]; Binding
0x1800555c1  call    cs:__imp_RpcBindingFromStringBindingW
0x1800555c8  nop     dword ptr [rax+rax+00h]
0x1800555cd  mov     ebx, eax
0x1800555cf  test    eax, eax
0x1800555d1  jz      short loc_1800555F7
0x1800555d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800555da  cmp     rcx, r15
0x1800555dd  jz      loc_18005572F
0x1800555e3  test    byte ptr [rcx+1Ch], 1
0x1800555e7  jz      loc_18005572F
0x1800555ed  mov     edx, 16Bh
0x1800555f2  jmp     loc_180055720
0x1800555f7  mov     rcx, [rbp+Binding]; Binding
0x1800555fb  lea     rdx, qword_18007B4B0; IfSpec
0x180055602  call    cs:__imp_RpcEpResolveBinding
0x180055609  nop     dword ptr [rax+rax+00h]
0x18005560e  mov     ebx, eax
0x180055610  test    eax, eax
0x180055612  jz      short loc_180055638
0x180055614  mov     rcx, cs:WPP_GLOBAL_Control
0x18005561b  cmp     rcx, r15
0x18005561e  jz      loc_18005572F
0x180055624  test    byte ptr [rcx+1Ch], 1
0x180055628  jz      loc_18005572F
0x18005562e  mov     edx, 16Ch
0x180055633  jmp     loc_180055720
0x180055638  mov     rcx, [rbp+Binding]; hBinding
0x18005563c  mov     edx, 0Bh; option
0x180055641  lea     r8d, [rdx-0Ah]; optionValue
0x180055645  call    cs:__imp_RpcBindingSetOption
0x18005564c  nop     dword ptr [rax+rax+00h]
0x180055651  mov     ebx, eax
0x180055653  test    eax, eax
0x180055655  jz      short loc_18005567B
0x180055657  mov     rcx, cs:WPP_GLOBAL_Control
0x18005565e  cmp     rcx, r15
0x180055661  jz      loc_18005572F
0x180055667  test    byte ptr [rcx+1Ch], 1
0x18005566b  jz      loc_18005572F
0x180055671  mov     edx, 16Dh
0x180055676  jmp     loc_180055720
0x18005567b  lea     rdx, [rbp+ServerPrincName]
0x18005567f  mov     rcx, rsi
0x180055682  call    cs:__imp_FwConstructRemoteMachineSPN
0x180055689  nop     dword ptr [rax+rax+00h]
0x18005568e  mov     ebx, eax
0x180055690  test    eax, eax
0x180055692  jz      short loc_1800556B5
0x180055694  mov     rcx, cs:WPP_GLOBAL_Control
0x18005569b  cmp     rcx, r15
0x18005569e  jz      loc_18005572F
0x1800556a4  test    byte ptr [rcx+1Ch], 1
0x1800556a8  jz      loc_18005572F
0x1800556ae  mov     edx, 16Eh
0x1800556b3  jmp     short loc_180055720
0x1800556b5  mov     rdx, [rbp+ServerPrincName]; ServerPrincName
0x1800556b9  lea     rax, [rbp+var_18]
0x1800556bd  mov     rcx, [rbp+Binding]; Binding
0x1800556c1  mov     r9d, 9; AuthnSvc
0x1800556c7  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x1800556cc  mov     dword ptr [rsp+70h+StringBinding], 0; AuthzSvc
0x1800556d4  mov     [rbp+var_18.Version], 1
0x1800556db  lea     r8d, [r9-3]; AuthnLevel
0x1800556df  mov     qword ptr [rbp+var_18.Capabilities], 1
0x1800556e7  mov     [rbp+var_18.ImpersonationType], 3
0x1800556ee  mov     [rsp+70h+Options], 0; AuthIdentity
0x1800556f7  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800556fe  nop     dword ptr [rax+rax+00h]
0x180055703  mov     ebx, eax
0x180055705  test    eax, eax
0x180055707  jz      short loc_180055753
0x180055709  mov     rcx, cs:WPP_GLOBAL_Control
0x180055710  cmp     rcx, r15
0x180055713  jz      short loc_18005572F
0x180055715  test    byte ptr [rcx+1Ch], 1
0x180055719  jz      short loc_18005572F
0x18005571b  mov     edx, 16Fh
0x180055720  mov     rcx, [rcx+10h]
0x180055724  mov     r9d, eax
0x180055727  mov     r8, r12
0x18005572a  call    WPP_SF_d
0x18005572f  cmp     [rbp+Binding], 0
0x180055734  jz      short loc_18005575A
0x180055736  lea     rcx, [rbp+Binding]; Binding
0x18005573a  call    cs:__imp_RpcBindingFree
0x180055741  nop     dword ptr [rax+rax+00h]
0x180055746  test    eax, eax
0x180055748  jz      short loc_18005575A
0x18005574a  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree for binding")
0x18005574c  call    MicrosoftTelemetryAssertTriggeredArgs
0x180055751  jmp     short loc_18005575A
0x180055753  mov     rax, [rbp+Binding]
0x180055757  mov     [rdi], rax
0x18005575a  cmp     [rbp+String], 0
0x18005575f  jz      short loc_18005577C
0x180055761  lea     rcx, [rbp+String]; String
0x180055765  call    cs:__imp_RpcStringFreeW
0x18005576c  nop     dword ptr [rax+rax+00h]
0x180055771  test    eax, eax
0x180055773  jz      short loc_18005577C
0x180055775  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcStringFreeW for stringBinding")
0x180055777  call    MicrosoftTelemetryAssertTriggeredArgs
0x18005577c  mov     rcx, [rbp+ServerPrincName]
0x180055780  test    rcx, rcx
0x180055783  jz      short loc_180055791
0x180055785  call    cs:__imp_FwBaseFree
0x18005578c  nop     dword ptr [rax+rax+00h]
0x180055791  mov     eax, ebx
0x180055793  mov     rcx, [rbp+var_8]
0x180055797  xor     rcx, rsp; StackCookie
0x18005579a  call    __security_check_cookie
0x18005579f  mov     rbx, [rsp+70h+arg_10]
0x1800557a7  add     rsp, 70h
0x1800557ab  pop     r15
0x1800557ad  pop     r12
0x1800557af  pop     rdi
0x1800557b0  pop     rsi
0x1800557b1  pop     rbp
0x1800557b2  retn
```
