# LipsBfeTunnelAdd

- ea: `0x1800487ac`
- end: `0x180048980`
- name: `LipsBfeTunnelAdd`
- size: `468`
- prototype: `__int64 __fastcall(FWPM_PROVIDER_CONTEXT0 *mainModePolicy, FWPM_PROVIDER_CONTEXT0 *tunnelPolicy, FWP_CONDITION_VALUE0 *, __int128 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180049560`

## callees

- `0x180009d44`
- `0x18000c4d0`
- `0x18000e510`
- `0x18004713c`
- `0x1800487ac`
- `0x180048bd0`
- `0x180048d8c`
- `0x18004d05e`
- `0x18004d090`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18004887a`
- `ntdll!EtwEventWrite` at `0x1800488cb`
- `ntdll!EtwEventWrite` at `0x18004887a`
- `ntdll!EtwEventWrite` at `0x1800488cb`
- `fwpuclnt!FwpmIPsecTunnelAdd0` at `0x1800488aa`
- `fwpuclnt!FwpmIPsecTunnelAdd0` at `0x1800488aa`

## pseudocode

```c
__int64 __fastcall LipsBfeTunnelAdd(
        FWPM_PROVIDER_CONTEXT0 *mainModePolicy,
        FWPM_PROVIDER_CONTEXT0 *tunnelPolicy,
        FWP_CONDITION_VALUE0 *a3,
        __int128 *a4)
{
  FWP_CONDITION_VALUE0 v8; // xmm0
  DWORD v9; // eax
  DWORD v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  FWPM_FILTER_CONDITION0 filterConditions; // [rsp+40h] [rbp-78h] BYREF
  GUID v17; // [rsp+68h] [rbp-50h]
  int v18; // [rsp+78h] [rbp-40h]
  __int128 v19; // [rsp+80h] [rbp-38h]

  memset_0(&filterConditions, 0, 0x50u);
  filterConditions.matchType = FWP_MATCH_EQUAL;
  v18 = 0;
  filterConditions.fieldKey = FWPM_CONDITION_IP_LOCAL_ADDRESS;
  v8 = *a3;
  v17 = FWPM_CONDITION_IP_REMOTE_ADDRESS;
  filterConditions.conditionValue = v8;
  v19 = *a4;
  v9 = LipsBfeBind();
  v10 = v9;
  if ( v9 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_19;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_14;
    v12 = 41;
    v13 = v9;
LABEL_13:
    WPP_SF_d(v11[2], v12, WPP_47af9f0627fa340f85c21449576885fa_Traceguids, v13);
    v11 = WPP_GLOBAL_Control;
LABEL_14:
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x10) != 0 )
      WPP_SF_sd(v11[2]);
    goto LABEL_19;
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_IPsecTunnelAdd_Begin, 0, 0);
  v10 = FwpmIPsecTunnelAdd0(gLipsBfeEngineHandle, 0, mainModePolicy, tunnelPolicy, 2u, &filterConditions, 0);
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_IPsecTunnelAdd_End, 0, 0);
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_19;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_14;
    v12 = 42;
    v13 = v10;
    goto LABEL_13;
  }
  if ( !gLipsNumExemptionCount++ )
    LipsBfeAddIpv6NbrDiscExemptions();
LABEL_19:
  LipsBfeUnbindOnFailure(v10);
  if ( v10 )
    return LipsReportError(v10, "LipsBfeTunnelAdd");
  else
    return 0;
}

```

## disassembly

```asm
0x1800487ac  mov     [rsp+arg_10], rbx
0x1800487b1  push    rbp
0x1800487b2  push    rsi
0x1800487b3  push    rdi
0x1800487b4  sub     rsp, 0A0h
0x1800487bb  mov     rax, cs:__security_cookie
0x1800487c2  xor     rax, rsp
0x1800487c5  mov     [rsp+0B8h+var_28], rax
0x1800487cd  mov     rbp, rdx
0x1800487d0  mov     rbx, r8
0x1800487d3  xor     edx, edx; Val
0x1800487d5  mov     rsi, rcx
0x1800487d8  lea     rcx, [rsp+0B8h+var_78]; void *
0x1800487dd  mov     rdi, r9
0x1800487e0  lea     r8d, [rdx+50h]; Size
0x1800487e4  call    memset_0
0x1800487e9  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x1800487f0  mov     [rsp+0B8h+var_78.matchType], 0
0x1800487f8  movups  xmm1, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_ADDRESS.Data1
0x1800487ff  mov     [rsp+0B8h+var_40], 0
0x180048807  movdqu  xmmword ptr [rsp+0B8h+var_78.fieldKey.Data1], xmm0
0x18004880d  movups  xmm0, xmmword ptr [rbx]
0x180048810  movdqu  [rsp+0B8h+var_50], xmm1
0x180048816  movdqu  xmmword ptr [rsp+0B8h+var_78.conditionValue.type], xmm0
0x18004881c  movups  xmm0, xmmword ptr [rdi]
0x18004881f  movdqu  [rsp+0B8h+var_38], xmm0
0x180048828  call    LipsBfeBind
0x18004882d  mov     ebx, eax
0x18004882f  test    eax, eax
0x180048831  jz      short loc_180048861
0x180048833  mov     rcx, cs:WPP_GLOBAL_Control
0x18004883a  lea     rdi, WPP_GLOBAL_Control
0x180048841  cmp     rcx, rdi
0x180048844  jz      loc_180048940
0x18004884a  test    byte ptr [rcx+1Ch], 10h
0x18004884e  jz      loc_18004890D
0x180048854  mov     edx, 29h ; ')'
0x180048859  mov     r9d, eax
0x18004885c  jmp     loc_1800488F6
0x180048861  mov     rcx, cs:g_Provider
0x180048868  test    rcx, rcx
0x18004886b  jz      short loc_180048880
0x18004886d  xor     r9d, r9d
0x180048870  lea     rdx, IPSEC_BFE_IPsecTunnelAdd_Begin
0x180048877  xor     r8d, r8d
0x18004887a  call    cs:__imp_EtwEventWrite
0x180048880  mov     rcx, cs:gLipsBfeEngineHandle; engineHandle
0x180048887  lea     rax, [rsp+0B8h+var_78]
0x18004888c  mov     [rsp+0B8h+sd], 0; sd
0x180048895  mov     r9, rbp; tunnelPolicy
0x180048898  mov     [rsp+0B8h+filterConditions], rax; filterConditions
0x18004889d  mov     r8, rsi; mainModePolicy
0x1800488a0  xor     edx, edx; flags
0x1800488a2  mov     [rsp+0B8h+numFilterConditions], 2; numFilterConditions
0x1800488aa  call    cs:__imp_FwpmIPsecTunnelAdd0
0x1800488b0  mov     rcx, cs:g_Provider
0x1800488b7  mov     ebx, eax
0x1800488b9  test    rcx, rcx
0x1800488bc  jz      short loc_1800488D1
0x1800488be  xor     r9d, r9d
0x1800488c1  lea     rdx, IPSEC_BFE_IPsecTunnelAdd_End
0x1800488c8  xor     r8d, r8d
0x1800488cb  call    cs:__imp_EtwEventWrite
0x1800488d1  test    ebx, ebx
0x1800488d3  jz      short loc_180048927
0x1800488d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800488dc  lea     rdi, WPP_GLOBAL_Control
0x1800488e3  cmp     rcx, rdi
0x1800488e6  jz      short loc_180048940
0x1800488e8  test    byte ptr [rcx+1Ch], 10h
0x1800488ec  jz      short loc_18004890D
0x1800488ee  mov     edx, 2Ah ; '*'
0x1800488f3  mov     r9d, ebx
0x1800488f6  mov     rcx, [rcx+10h]
0x1800488fa  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x180048901  call    WPP_SF_d
0x180048906  mov     rcx, cs:WPP_GLOBAL_Control
0x18004890d  cmp     rcx, rdi
0x180048910  jz      short loc_180048940
0x180048912  test    byte ptr [rcx+1Ch], 10h
0x180048916  jz      short loc_180048940
0x180048918  mov     rcx, [rcx+10h]
0x18004891c  mov     [rsp+0B8h+numFilterConditions], ebx
0x180048920  call    WPP_SF_sd
0x180048925  jmp     short loc_180048940
0x180048927  mov     eax, cs:gLipsNumExemptionCount
0x18004892d  mov     ecx, eax
0x18004892f  inc     eax
0x180048931  mov     cs:gLipsNumExemptionCount, eax
0x180048937  test    ecx, ecx
0x180048939  jnz     short loc_180048940
0x18004893b  call    LipsBfeAddIpv6NbrDiscExemptions
0x180048940  mov     ecx, ebx
0x180048942  call    LipsBfeUnbindOnFailure
0x180048947  test    ebx, ebx
0x180048949  jnz     short loc_18004894F
0x18004894b  xor     eax, eax
0x18004894d  jmp     short loc_18004895D
0x18004894f  lea     rdx, aLipsbfetunnela; "LipsBfeTunnelAdd"
0x180048956  mov     ecx, ebx
0x180048958  call    LipsReportError
0x18004895d  mov     rcx, [rsp+0B8h+var_28]
0x180048965  xor     rcx, rsp; StackCookie
0x180048968  call    __security_check_cookie
0x18004896d  mov     rbx, [rsp+0B8h+arg_10]
0x180048975  add     rsp, 0A0h
0x18004897c  pop     rdi
0x18004897d  pop     rsi
0x18004897e  pop     rbp
0x18004897f  retn
```
