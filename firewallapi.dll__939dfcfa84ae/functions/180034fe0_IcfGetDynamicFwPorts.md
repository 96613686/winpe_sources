# IcfGetDynamicFwPorts

- ea: `0x180034fe0`
- end: `0x18003532f`
- name: `IcfGetDynamicFwPorts`
- size: `847`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009780`
- `0x18000c3f0`
- `0x18000cc80`
- `0x18000d0f0`
- `0x180019b34`
- `0x1800294b0`
- `0x18003336c`
- `0x180033488`
- `0x1800348ec`
- `0x180034aa0`
- `0x180034fe0`

## import_xrefs

- `fwbase!FwBaseAlloc` at `0x1800350dc`
- `fwbase!FwBaseAlloc` at `0x180035183`
- `fwbase!FwBaseAlloc` at `0x1800350dc`
- `fwbase!FwBaseAlloc` at `0x180035183`
- `fwbase!FwSizeTMultiply` at `0x180035168`
- `fwbase!FwSizeTMultiply` at `0x180035168`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180035125`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x1800351d2`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180035125`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x1800351d2`
- `fwbase!FwHResultToWindowsError` at `0x180035309`
- `fwbase!FwHResultToWindowsError` at `0x180035309`
- `fwbase!FwReportErrorAsWinError` at `0x18003508b`
- `fwbase!FwReportErrorAsWinError` at `0x18003508b`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180035109`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x1800351ae`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180035109`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x1800351ae`
- `fwbase!FwStringCopy` at `0x180035213`
- `fwbase!FwStringCopy` at `0x180035213`

## string_xrefs

- `0x18003507a`: `FWOpenPolicyStore`
- `0x1800352bc`: `CopySubnetRestrictions`
- `0x1800352b0`: `CopyAddrRanges`

## pseudocode

```c
__int64 __fastcall IcfGetDynamicFwPorts(__int64 a1, _QWORD *a2)
{
  unsigned int v3; // eax
  const char *v4; // rdx
  __int64 v5; // r8
  int v6; // ebx
  unsigned int *v7; // rdi
  struct _tag_FW_RULE *i; // rbx
  __int64 v9; // rdx
  __int64 v11; // rax
  struct _tag_FW_RULE *v12; // rbx
  unsigned int v13; // esi
  __int64 v14; // rcx
  int v15; // eax
  unsigned __int64 v16; // r14
  __int64 v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-38h] BYREF
  struct _tag_FW_RULE *v19; // [rsp+38h] [rbp-30h] BYREF
  __int64 v20; // [rsp+40h] [rbp-28h] BYREF
  __int64 v21; // [rsp+48h] [rbp-20h] BYREF
  int v22; // [rsp+50h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  v20 = 0;
  v19 = 0;
  v22 = 0;
  v18 = 0;
  v3 = FWOpenPolicyStore(0x221u, 0, 5u, 1u, 0, &v20);
  if ( v3 )
  {
    v4 = "FWOpenPolicyStore";
LABEL_6:
    v5 = v3;
LABEL_7:
    v6 = FwReportErrorAsWinError("IcfGetDynamicFwPorts", v4, v5);
    goto LABEL_42;
  }
  v3 = FWEnumFirewallRules(v20, 0x10000, 0x80000000, 9, (__int64)&v22, (__int64)&v19);
  if ( v3 )
  {
    v4 = "FWEnumFirewallRules";
    goto LABEL_6;
  }
  v18 = FwBaseAlloc(16);
  v7 = (unsigned int *)v18;
  if ( !v18 )
  {
LABEL_11:
    v5 = 8;
    v4 = "FwAlloc";
    goto LABEL_7;
  }
  for ( i = v19; i; i = *(struct _tag_FW_RULE **)i )
  {
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(i)
      && (*((_BYTE *)i + 292) & 1) != 0
      && (unsigned int)IsRuleOldGlobalOpenPort(i)
      && *((_DWORD *)i + 85) == 3
      && *((_DWORD *)i + 72) == 3 )
    {
      ++*v7;
    }
  }
  if ( *v7 )
  {
    v9 = *v7;
    v21 = 0;
    if ( (int)FwSizeTMultiply(128, v9, &v21) < 0 )
      return 8;
    v11 = FwBaseAlloc(v21);
    *((_QWORD *)v7 + 1) = v11;
    if ( !v11 )
      goto LABEL_11;
    v12 = v19;
    v13 = 0;
    while ( v12 )
    {
      if ( (unsigned int)IsRuleOpenPortOrAuthApp(v12)
        && (*((_BYTE *)v12 + 292) & 1) != 0
        && (unsigned int)IsRuleOldGlobalOpenPort(v12)
        && *((_DWORD *)v12 + 85) == 3
        && *((_DWORD *)v12 + 72) == 3 )
      {
        v14 = *((_QWORD *)v12 + 3);
        if ( v14 )
        {
          v15 = FwStringCopy(v14, *((_QWORD *)v7 + 1) + ((unsigned __int64)v13 << 7));
          if ( v15 < 0 )
          {
            v17 = (unsigned int)v15;
            return FwHResultToWindowsError(v17);
          }
        }
        v16 = (unsigned __int64)v13 << 7;
        *(_DWORD *)(*((_QWORD *)v7 + 1) + v16 + 28) = 2;
        *(_WORD *)(*((_QWORD *)v7 + 1) + v16 + 32) = **((_WORD **)v12 + 9);
        *(_DWORD *)(*((_QWORD *)v7 + 1) + v16 + 36) = *((unsigned __int16 *)v12 + 24);
        *(_DWORD *)(*((_QWORD *)v7 + 1) + v16 + 40) = 1;
        v3 = CopySubnetRestrictions(
               v12,
               (struct ICF_SUBNETS_ *)(v16 + *((_QWORD *)v7 + 1) + 48LL),
               (struct ICF_SUBNETS6_ *)(v16 + *((_QWORD *)v7 + 1) + 72LL));
        if ( v3 )
        {
          v4 = "CopySubnetRestrictions";
          goto LABEL_6;
        }
        v3 = CopyAddrRanges(
               v12,
               (struct ICF_RANGES_ *)(v16 + *((_QWORD *)v7 + 1) + 96LL),
               (struct ICF_RANGES6_ *)(v16 + *((_QWORD *)v7 + 1) + 112LL));
        if ( v3 )
        {
          v4 = "CopyAddrRanges";
          goto LABEL_6;
        }
        ++v13;
      }
      v12 = *(struct _tag_FW_RULE **)v12;
    }
  }
  v6 = 0;
  *a2 = v7;
LABEL_42:
  if ( v20 )
    FWClosePolicyStore();
  if ( v19 )
    FWFreeFirewallRules(v19);
  if ( v6 < 0 )
    IcfFreeDynamicFwPorts(&v18);
  if ( (unsigned int)IsRpcError(v6) )
    v6 = -2147023174;
  v17 = (unsigned int)v6;
  return FwHResultToWindowsError(v17);
}

```

## disassembly

```asm
0x180034fe0  push    rbp
0x180034fe2  push    rbx
0x180034fe3  push    rsi
0x180034fe4  push    rdi
0x180034fe5  push    r14
0x180034fe7  push    r15
0x180034fe9  mov     rbp, rsp
0x180034fec  sub     rsp, 68h
0x180034ff0  mov     rax, cs:__security_cookie
0x180034ff7  xor     rax, rsp
0x180034ffa  mov     [rbp+var_10], rax
0x180034ffe  mov     r15, rdx
0x180035001  mov     rcx, cs:WPP_GLOBAL_Control
0x180035008  lea     rax, WPP_GLOBAL_Control
0x18003500f  mov     esi, 8
0x180035014  cmp     rcx, rax
0x180035017  jz      short loc_180035032
0x180035019  test    [rcx+1Ch], sil
0x18003501d  jz      short loc_180035032
0x18003501f  mov     rcx, [rcx+10h]
0x180035023  lea     edx, [rsi+1Fh]
0x180035026  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18003502d  call    WPP_SF_
0x180035032  xor     edx, edx
0x180035034  mov     [rbp+var_28], 0
0x18003503c  lea     rax, [rbp+var_28]
0x180035040  mov     [rbp+var_30], 0
0x180035048  mov     [rsp+68h+var_40], rax
0x18003504d  mov     ecx, 221h
0x180035052  mov     [rbp+var_18], 0
0x180035059  lea     r9d, [rdx+1]
0x18003505d  mov     [rbp+var_38], 0
0x180035065  lea     r8d, [rdx+5]
0x180035069  mov     dword ptr [rsp+68h+var_48], 0
0x180035071  call    FWOpenPolicyStore
0x180035076  test    eax, eax
0x180035078  jz      short loc_18003509E
0x18003507a  lea     rdx, aFwopenpolicyst_1; "FWOpenPolicyStore"
0x180035081  mov     r8d, eax
0x180035084  lea     rcx, aIcfgetdynamicf_0; "IcfGetDynamicFwPorts"
0x18003508b  call    cs:__imp_FwReportErrorAsWinError
0x180035092  nop     dword ptr [rax+rax+00h]
0x180035097  mov     ebx, eax
0x180035099  jmp     loc_1800352CD
0x18003509e  mov     rcx, [rbp+var_28]
0x1800350a2  lea     rax, [rbp+var_30]
0x1800350a6  mov     [rsp+68h+var_40], rax
0x1800350ab  mov     r9d, 9
0x1800350b1  lea     rax, [rbp+var_18]
0x1800350b5  mov     edx, 10000h
0x1800350ba  mov     r8d, 80000000h
0x1800350c0  mov     [rsp+68h+var_48], rax
0x1800350c5  call    FWEnumFirewallRules
0x1800350ca  test    eax, eax
0x1800350cc  jz      short loc_1800350D7
0x1800350ce  lea     rdx, aFwenumfirewall_0; "FWEnumFirewallRules"
0x1800350d5  jmp     short loc_180035081
0x1800350d7  mov     ecx, 10h
0x1800350dc  call    cs:__imp_FwBaseAlloc
0x1800350e3  nop     dword ptr [rax+rax+00h]
0x1800350e8  mov     [rbp+var_38], rax
0x1800350ec  mov     rdi, rax
0x1800350ef  test    rax, rax
0x1800350f2  jnz     short loc_180035100
0x1800350f4  mov     r8d, esi
0x1800350f7  lea     rdx, aFwalloc_0; "FwAlloc"
0x1800350fe  jmp     short loc_180035084
0x180035100  mov     rbx, [rbp+var_30]
0x180035104  jmp     short loc_18003514C
0x180035106  mov     rcx, rbx
0x180035109  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180035110  nop     dword ptr [rax+rax+00h]
0x180035115  test    eax, eax
0x180035117  jz      short loc_180035149
0x180035119  test    byte ptr [rbx+124h], 1
0x180035120  jz      short loc_180035149
0x180035122  mov     rcx, rbx
0x180035125  call    cs:__imp_IsRuleOldGlobalOpenPort
0x18003512c  nop     dword ptr [rax+rax+00h]
0x180035131  test    eax, eax
0x180035133  jz      short loc_180035149
0x180035135  cmp     dword ptr [rbx+154h], 3
0x18003513c  jnz     short loc_180035149
0x18003513e  cmp     dword ptr [rbx+120h], 3
0x180035145  jnz     short loc_180035149
0x180035147  inc     dword ptr [rdi]
0x180035149  mov     rbx, [rbx]
0x18003514c  test    rbx, rbx
0x18003514f  jnz     short loc_180035106
0x180035151  cmp     [rdi], ebx
0x180035153  jz      loc_1800352C8
0x180035159  mov     edx, [rdi]
0x18003515b  lea     r8, [rbp+var_20]
0x18003515f  mov     ecx, 80h
0x180035164  mov     [rbp+var_20], rbx
0x180035168  call    cs:__imp_FwSizeTMultiply
0x18003516f  nop     dword ptr [rax+rax+00h]
0x180035174  test    eax, eax
0x180035176  jns     short loc_18003517F
0x180035178  mov     eax, esi
0x18003517a  jmp     loc_180035315
0x18003517f  mov     rcx, [rbp+var_20]
0x180035183  call    cs:__imp_FwBaseAlloc
0x18003518a  nop     dword ptr [rax+rax+00h]
0x18003518f  mov     [rdi+8], rax
0x180035193  test    rax, rax
0x180035196  jz      loc_1800350F4
0x18003519c  mov     rbx, [rbp+var_30]
0x1800351a0  xor     esi, esi
0x1800351a2  test    rbx, rbx
0x1800351a5  jz      loc_1800352C8
0x1800351ab  mov     rcx, rbx
0x1800351ae  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x1800351b5  nop     dword ptr [rax+rax+00h]
0x1800351ba  test    eax, eax
0x1800351bc  jz      loc_1800352A4
0x1800351c2  test    byte ptr [rbx+124h], 1
0x1800351c9  jz      loc_1800352A4
0x1800351cf  mov     rcx, rbx
0x1800351d2  call    cs:__imp_IsRuleOldGlobalOpenPort
0x1800351d9  nop     dword ptr [rax+rax+00h]
0x1800351de  test    eax, eax
0x1800351e0  jz      loc_1800352A4
0x1800351e6  cmp     dword ptr [rbx+154h], 3
0x1800351ed  jnz     loc_1800352A4
0x1800351f3  cmp     dword ptr [rbx+120h], 3
0x1800351fa  jnz     loc_1800352A4
0x180035200  mov     rcx, [rbx+18h]
0x180035204  test    rcx, rcx
0x180035207  jz      short loc_180035227
0x180035209  mov     edx, esi
0x18003520b  shl     rdx, 7
0x18003520f  add     rdx, [rdi+8]
0x180035213  call    cs:__imp_FwStringCopy
0x18003521a  nop     dword ptr [rax+rax+00h]
0x18003521f  test    eax, eax
0x180035221  js      loc_1800352AC
0x180035227  mov     rax, [rdi+8]
0x18003522b  mov     r14d, esi
0x18003522e  shl     r14, 7
0x180035232  mov     dword ptr [rax+r14+1Ch], 2
0x18003523b  mov     rax, [rbx+48h]
0x18003523f  mov     rcx, [rdi+8]
0x180035243  movzx   eax, word ptr [rax]
0x180035246  mov     [rcx+r14+20h], ax
0x18003524c  mov     rax, [rdi+8]
0x180035250  movzx   ecx, word ptr [rbx+30h]
0x180035254  mov     [rax+r14+24h], ecx
0x180035259  mov     rcx, rbx; struct _tag_FW_RULE *
0x18003525c  mov     rax, [rdi+8]
0x180035260  mov     dword ptr [rax+r14+28h], 1
0x180035269  mov     rax, [rdi+8]
0x18003526d  lea     r8, [rax+48h]
0x180035271  lea     rdx, [rax+30h]
0x180035275  add     r8, r14; struct ICF_SUBNETS6_ *
0x180035278  add     rdx, r14; struct ICF_SUBNETS_ *
0x18003527b  call    ?CopySubnetRestrictions@@YAKPEBU_tag_FW_RULE@@PEAUICF_SUBNETS_@@PEAUICF_SUBNETS6_@@@Z; CopySubnetRestrictions(_tag_FW_RULE const *,ICF_SUBNETS_ *,ICF_SUBNETS6_ *)
0x180035280  test    eax, eax
0x180035282  jnz     short loc_1800352BC
0x180035284  mov     rax, [rdi+8]
0x180035288  mov     rcx, rbx; struct _tag_FW_RULE *
0x18003528b  lea     r8, [rax+70h]
0x18003528f  lea     rdx, [rax+60h]
0x180035293  add     r8, r14; struct ICF_RANGES6_ *
0x180035296  add     rdx, r14; struct ICF_RANGES_ *
0x180035299  call    ?CopyAddrRanges@@YAKPEBU_tag_FW_RULE@@PEAUICF_RANGES_@@PEAUICF_RANGES6_@@@Z; CopyAddrRanges(_tag_FW_RULE const *,ICF_RANGES_ *,ICF_RANGES6_ *)
0x18003529e  test    eax, eax
0x1800352a0  jnz     short loc_1800352B0
0x1800352a2  inc     esi
0x1800352a4  mov     rbx, [rbx]
0x1800352a7  jmp     loc_1800351A2
0x1800352ac  mov     ecx, eax
0x1800352ae  jmp     short loc_180035309
0x1800352b0  lea     rdx, aCopyaddrranges; "CopyAddrRanges"
0x1800352b7  jmp     loc_180035081
0x1800352bc  lea     rdx, aCopysubnetrest; "CopySubnetRestrictions"
0x1800352c3  jmp     loc_180035081
0x1800352c8  xor     ebx, ebx
0x1800352ca  mov     [r15], rdi
0x1800352cd  mov     rcx, [rbp+var_28]
0x1800352d1  test    rcx, rcx
0x1800352d4  jz      short loc_1800352DB
0x1800352d6  call    FWClosePolicyStore
0x1800352db  mov     rcx, [rbp+var_30]
0x1800352df  test    rcx, rcx
0x1800352e2  jz      short loc_1800352E9
0x1800352e4  call    FWFreeFirewallRules
0x1800352e9  test    ebx, ebx
0x1800352eb  jns     short loc_1800352F6
0x1800352ed  lea     rcx, [rbp+var_38]
0x1800352f1  call    IcfFreeDynamicFwPorts
0x1800352f6  mov     ecx, ebx; int
0x1800352f8  call    ?IsRpcError@@YAHJ@Z; IsRpcError(long)
0x1800352fd  mov     ecx, 800706BAh
0x180035302  test    eax, eax
0x180035304  cmovnz  ebx, ecx
0x180035307  mov     ecx, ebx
0x180035309  call    cs:__imp_FwHResultToWindowsError
0x180035310  nop     dword ptr [rax+rax+00h]
0x180035315  mov     rcx, [rbp+var_10]
0x180035319  xor     rcx, rsp; StackCookie
0x18003531c  call    __security_check_cookie
0x180035321  add     rsp, 68h
0x180035325  pop     r15
0x180035327  pop     r14
0x180035329  pop     rdi
0x18003532a  pop     rsi
0x18003532b  pop     rbx
0x18003532c  pop     rbp
0x18003532d  retn
```
