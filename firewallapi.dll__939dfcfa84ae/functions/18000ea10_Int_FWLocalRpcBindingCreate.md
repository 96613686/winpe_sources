# Int_FWLocalRpcBindingCreate

- ea: `0x18000ea10`
- end: `0x18000eca9`
- name: `Int_FWLocalRpcBindingCreate`
- size: `665`
- prototype: ``
- caller_count: `45`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000e750`
- `0x180010180`
- `0x18001c170`
- `0x18001d130`
- `0x18001db50`
- `0x18001dfb0`
- `0x18001e4a0`
- `0x180020bd0`
- `0x1800232b0`
- `0x180027240`
- `0x18004e730`
- `0x18004eab0`
- `0x18004ec30`
- `0x18004f710`
- `0x18004ffd0`
- `0x180050150`
- `0x180050550`
- `0x1800519f0`
- `0x180051b40`
- `0x180051ce0`
- `0x180051e80`
- `0x180052220`
- `0x1800524a0`
- `0x180052610`
- `0x180052780`
- `0x180053060`
- `0x1800539e0`
- `0x180053b60`
- `0x180054310`
- `0x180055a20`
- `0x180055ba0`
- `0x180055ea0`
- `0x180056270`
- `0x1800566a0`
- `0x1800569d0`
- `0x180056c50`
- `0x180056fd0`
- `0x180057360`
- `0x180057480`
- `0x180057630`
- `0x180057a50`
- `0x180057d70`
- `0x180057ef0`
- `0x1800580b0`
- `0x180058570`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x180026798`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x18000eab0`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000eab0`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000eace`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000eace`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000eb49`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000eb49`
- `RPCRT4!RpcStringFreeW` at `0x18000eb70`
- `RPCRT4!RpcStringFreeW` at `0x18000eb70`
- `RPCRT4!RpcBindingFree` at `0x18000ec7d`
- `RPCRT4!RpcBindingFree` at `0x18000ec7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec0b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000eb09`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000eb09`

## pseudocode

```c
__int64 __fastcall Int_FWLocalRpcBindingCreate(RPC_BINDING_HANDLE *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  __int64 v5; // rcx
  FwPolicy2 *v7; // rcx
  __int64 v8; // rdx
  DWORD LastError; // eax
  unsigned int v10; // eax
  __int64 v11; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-59h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp-51h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+50h] [rbp-49h] BYREF
  __int128 v15; // [rsp+60h] [rbp-39h]
  _OWORD *v16; // [rsp+70h] [rbp-29h]
  DWORD cbSid; // [rsp+78h] [rbp-21h] BYREF
  _OWORD pSid[4]; // [rsp+80h] [rbp-19h] BYREF
  int v19; // [rsp+C0h] [rbp+27h]

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 356, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  cbSid = 68;
  v16 = 0;
  v19 = 0;
  String = 0;
  Binding = 0;
  SecurityQOS = 0;
  *a1 = 0;
  v15 = 0;
  memset(pSid, 0, sizeof(pSid));
  v2 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  v3 = v2;
  if ( v2 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 357;
LABEL_27:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v2);
    }
LABEL_28:
    if ( Binding )
    {
      v10 = RpcBindingFree(&Binding);
      if ( v10 )
        MicrosoftTelemetryAssertTriggeredArgs(v11, v10);
    }
    goto LABEL_9;
  }
  v2 = RpcBindingFromStringBindingW(String, &Binding);
  v3 = v2;
  if ( v2 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 358;
      goto LABEL_27;
    }
    goto LABEL_28;
  }
  SecurityQOS.Version = 3;
  *(_QWORD *)&SecurityQOS.Capabilities = 1;
  SecurityQOS.ImpersonationType = 3;
  if ( CreateWellKnownSid(WinLocalServiceSid, 0, pSid, &cbSid) )
  {
    v16 = pSid;
    v2 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xFFFFFFFF, 0, 0, &SecurityQOS);
    v3 = v2;
    if ( !v2 )
    {
      *a1 = Binding;
      goto LABEL_9;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_28;
    v8 = 360;
    goto LABEL_27;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 359, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, LastError);
  if ( v3 )
    goto LABEL_28;
LABEL_9:
  if ( String )
  {
    v4 = RpcStringFreeW(&String);
    if ( v4 )
      MicrosoftTelemetryAssertTriggeredArgs(v5, v4);
  }
  return v3;
}

```

## disassembly

```asm
0x18000ea10  mov     [rsp-8+arg_8], rbx
0x18000ea15  mov     [rsp-8+arg_10], rsi
0x18000ea1a  push    rbp
0x18000ea1b  push    rdi
0x18000ea1c  push    r14
0x18000ea1e  lea     rbp, [rsp-47h]
0x18000ea23  sub     rsp, 0E0h
0x18000ea2a  mov     rax, cs:__security_cookie
0x18000ea31  xor     rax, rsp
0x18000ea34  mov     [rbp+57h+var_20], rax
0x18000ea38  mov     rdi, rcx
0x18000ea3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea42  lea     r14, WPP_GLOBAL_Control
0x18000ea49  cmp     rcx, r14
0x18000ea4c  jz      short loc_18000EA58
0x18000ea4e  test    byte ptr [rcx+1Ch], 8
0x18000ea52  jnz     loc_18000EBD8
0x18000ea58  xorps   xmm1, xmm1
0x18000ea5b  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18000ea62  xor     eax, eax
0x18000ea64  lea     rdx, ProtSeq; "ncalrpc"
0x18000ea6b  xor     esi, esi
0x18000ea6d  mov     [rbp+57h+var_80], rax
0x18000ea71  xorps   xmm0, xmm0
0x18000ea74  mov     [rbp+57h+var_30], eax
0x18000ea77  lea     rax, [rbp+57h+String]
0x18000ea7b  mov     [rbp+57h+String], rsi
0x18000ea7f  mov     [rsp+0F0h+StringBinding], rax; StringBinding
0x18000ea84  xor     r9d, r9d; Endpoint
0x18000ea87  xor     r8d, r8d; NetworkAddr
0x18000ea8a  mov     [rsp+0F0h+Options], rsi; Options
0x18000ea8f  xor     ecx, ecx; ObjUuid
0x18000ea91  mov     [rbp+57h+Binding], rsi
0x18000ea95  movups  xmmword ptr [rbp+57h+var_A0.Version], xmm0
0x18000ea99  mov     [rdi], rsi
0x18000ea9c  movups  [rbp+57h+var_90], xmm0
0x18000eaa0  movups  [rbp+57h+pSid], xmm1
0x18000eaa4  movups  [rbp+57h+var_60], xmm1
0x18000eaa8  movups  [rbp+57h+var_50], xmm1
0x18000eaac  movups  [rbp+57h+var_40], xmm1
0x18000eab0  call    cs:__imp_RpcStringBindingComposeW
0x18000eab7  nop     dword ptr [rax+rax+00h]
0x18000eabc  mov     ebx, eax
0x18000eabe  test    eax, eax
0x18000eac0  jnz     loc_18000EBAB
0x18000eac6  mov     rcx, [rbp+57h+String]; StringBinding
0x18000eaca  lea     rdx, [rbp+57h+Binding]; Binding
0x18000eace  call    cs:__imp_RpcBindingFromStringBindingW
0x18000ead5  nop     dword ptr [rax+rax+00h]
0x18000eada  mov     ebx, eax
0x18000eadc  test    eax, eax
0x18000eade  jnz     loc_18000EBF2
0x18000eae4  lea     r9, [rbp+57h+cbSid]; cbSid
0x18000eae8  mov     [rbp+57h+var_A0.Version], 3
0x18000eaef  lea     r8, [rbp+57h+pSid]; pSid
0x18000eaf3  mov     qword ptr [rbp+57h+var_A0.Capabilities], 1
0x18000eafb  xor     edx, edx; DomainSid
0x18000eafd  mov     [rbp+57h+var_A0.ImpersonationType], 3
0x18000eb04  mov     ecx, 17h; WellKnownSidType
0x18000eb09  call    cs:__imp_CreateWellKnownSid
0x18000eb10  nop     dword ptr [rax+rax+00h]
0x18000eb15  test    eax, eax
0x18000eb17  jz      loc_18000EC0B
0x18000eb1d  mov     rcx, [rbp+57h+Binding]; Binding
0x18000eb21  lea     rax, [rbp+57h+pSid]
0x18000eb25  mov     [rbp+57h+var_80], rax
0x18000eb29  xor     edx, edx; ServerPrincName
0x18000eb2b  lea     rax, [rbp+57h+var_A0]
0x18000eb2f  mov     r9d, 0FFFFFFFFh; AuthnSvc
0x18000eb35  mov     [rsp+0F0h+SecurityQOS], rax; SecurityQOS
0x18000eb3a  mov     r8d, 6; AuthnLevel
0x18000eb40  mov     dword ptr [rsp+0F0h+StringBinding], esi; AuthzSvc
0x18000eb44  mov     [rsp+0F0h+Options], rsi; AuthIdentity
0x18000eb49  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000eb50  nop     dword ptr [rax+rax+00h]
0x18000eb55  mov     ebx, eax
0x18000eb57  test    eax, eax
0x18000eb59  jnz     loc_18000EC45
0x18000eb5f  mov     rax, [rbp+57h+Binding]
0x18000eb63  mov     [rdi], rax
0x18000eb66  cmp     [rbp+57h+String], rsi
0x18000eb6a  jz      short loc_18000EB84
0x18000eb6c  lea     rcx, [rbp+57h+String]; String
0x18000eb70  call    cs:__imp_RpcStringFreeW
0x18000eb77  nop     dword ptr [rax+rax+00h]
0x18000eb7c  test    eax, eax
0x18000eb7e  jnz     loc_18000EC9D
0x18000eb84  mov     eax, ebx
0x18000eb86  mov     rcx, [rbp+57h+var_20]
0x18000eb8a  xor     rcx, rsp; StackCookie
0x18000eb8d  call    __security_check_cookie
0x18000eb92  lea     r11, [rsp+0F0h+var_10]
0x18000eb9a  mov     rbx, [r11+28h]
0x18000eb9e  mov     rsi, [r11+30h]
0x18000eba2  mov     rsp, r11
0x18000eba5  pop     r14
0x18000eba7  pop     rdi
0x18000eba8  pop     rbp
0x18000eba9  retn
0x18000ebab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebb2  cmp     rcx, r14
0x18000ebb5  jz      loc_18000EC6F
0x18000ebbb  test    byte ptr [rcx+1Ch], 1
0x18000ebbf  jz      loc_18000EC6F
0x18000ebc5  mov     edx, 165h
0x18000ebca  jmp     loc_18000EC5C
0x18000ebcf  test    ebx, ebx
0x18000ebd1  jz      short loc_18000EB66
0x18000ebd3  jmp     loc_18000EC6F
0x18000ebd8  mov     rcx, [rcx+10h]
0x18000ebdc  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000ebe3  mov     edx, 164h
0x18000ebe8  call    WPP_SF_
0x18000ebed  jmp     loc_18000EA58
0x18000ebf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebf9  cmp     rcx, r14
0x18000ebfc  jz      short loc_18000EC6F
0x18000ebfe  test    byte ptr [rcx+1Ch], 1
0x18000ec02  jz      short loc_18000EC6F
0x18000ec04  mov     edx, 166h
0x18000ec09  jmp     short loc_18000EC5C
0x18000ec0b  call    cs:__imp_GetLastError
0x18000ec12  nop     dword ptr [rax+rax+00h]
0x18000ec17  mov     ebx, eax
0x18000ec19  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec20  cmp     rcx, r14
0x18000ec23  jz      short loc_18000EBCF
0x18000ec25  test    byte ptr [rcx+1Ch], 1
0x18000ec29  jz      short loc_18000EBCF
0x18000ec2b  mov     rcx, [rcx+10h]
0x18000ec2f  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000ec36  mov     edx, 167h
0x18000ec3b  mov     r9d, eax
0x18000ec3e  call    WPP_SF_d
0x18000ec43  jmp     short loc_18000EBCF
0x18000ec45  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec4c  cmp     rcx, r14
0x18000ec4f  jz      short loc_18000EC6F
0x18000ec51  test    byte ptr [rcx+1Ch], 1
0x18000ec55  jz      short loc_18000EC6F
0x18000ec57  mov     edx, 168h
0x18000ec5c  mov     rcx, [rcx+10h]
0x18000ec60  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000ec67  mov     r9d, eax
0x18000ec6a  call    WPP_SF_d
0x18000ec6f  cmp     [rbp+57h+Binding], rsi
0x18000ec73  jz      loc_18000EB66
0x18000ec79  lea     rcx, [rbp+57h+Binding]; Binding
0x18000ec7d  call    cs:__imp_RpcBindingFree
0x18000ec84  nop     dword ptr [rax+rax+00h]
0x18000ec89  test    eax, eax
0x18000ec8b  jz      loc_18000EB66
0x18000ec91  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree for binding")
0x18000ec93  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000ec98  jmp     loc_18000EB66
0x18000ec9d  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcStringFreeW for stringBinding")
0x18000ec9f  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000eca4  jmp     loc_18000EB84
```
