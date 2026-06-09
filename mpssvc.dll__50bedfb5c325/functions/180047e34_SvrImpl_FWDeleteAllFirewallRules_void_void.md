# SvrImpl_FWDeleteAllFirewallRules(void *,void *)

- ea: `0x180047e34`
- end: `0x1800481a4`
- name: `?SvrImpl_FWDeleteAllFirewallRules@@YAKPEAX0@Z`
- size: `880`
- prototype: `unsigned int __fastcall(void *, void *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800a9dc8`
- `0x1800c7790`

## callees

- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x1800192e0`
- `0x18003ec48`
- `0x180047e34`
- `0x1800481ac`
- `0x180059714`
- `0x180060ef8`
- `0x18006e578`
- `0x1800729c0`
- `0x1800a700c`
- `0x1800a7b68`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800480b8`
- `fwbase!FwHResultToWindowsError` at `0x18004811b`
- `fwbase!FwHResultToWindowsError` at `0x180048171`
- `fwbase!FwHResultToWindowsError` at `0x1800480b8`
- `fwbase!FwHResultToWindowsError` at `0x18004811b`
- `fwbase!FwHResultToWindowsError` at `0x180048171`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180047f25`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180047f25`
- `fwbase!FwChangeSourceSignal` at `0x1800480aa`
- `fwbase!FwChangeSourceSignal` at `0x1800480aa`
- `fwbase!FwFree` at `0x18004814d`
- `fwbase!FwFree` at `0x180048163`
- `fwbase!FwFree` at `0x18004814d`
- `fwbase!FwFree` at `0x180048163`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x180047fbd`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x180047fbd`

## string_xrefs

- `0x180047ea1`: `SvrImpl_FWDeleteAllFirewallRules`
- `0x180047ec0`: `SvrImpl_FWDeleteAllFirewallRules`
- `0x18004808b`: `SvrImpl_FWDeleteAllFirewallRules`
- `0x18004809a`: `SvrImpl_FWDeleteAllFirewallRules`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWDeleteAllFirewallRules(void *a1, _DWORD *a2)
{
  __int64 result; // rax
  unsigned int v5; // ebx
  unsigned int v6; // ebp
  int RPCClientSID; // eax
  const wchar_t *v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // eax
  __int64 v13; // rax
  const unsigned __int16 *v14; // rdi
  const unsigned __int16 *v15; // r8
  const wchar_t *v16; // rdx
  int v17; // eax
  int v18; // r8d
  int v19; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v20; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t **v21; // [rsp+38h] [rbp-40h] BYREF

  v21 = 0;
  v20 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 103, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWDeleteAllFirewallRules");
  if ( (int)result >= 0 )
  {
    v5 = FwLock();
    if ( (v5 & 0x80000000) != 0 )
    {
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllFirewallRules");
      return v5;
    }
    v6 = 0;
    if ( a1 )
    {
      RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v21);
      v5 = RPCClientSID;
      if ( RPCClientSID < 0 )
      {
        v8 = 0;
        v9 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_40;
        v10 = 104;
LABEL_12:
        v11 = (unsigned int)RPCClientSID;
LABEL_39:
        WPP_SF_d(*(_QWORD *)(v9 + 16), v10, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v11);
        goto LABEL_40;
      }
      v8 = *v21;
      FwGetRpcCallersProcessImageName(a1, &v20);
    }
    else
    {
      v8 = (const wchar_t *)qword_180134200;
      v20 = qword_180134208;
    }
    if ( a2[6] == 2 )
    {
      v6 = a2[4];
      if ( v6 <= 0xC )
      {
        v12 = 4148;
        if ( _bittest(&v12, v6) )
        {
          if ( *(_QWORD *)a2 && (RPCClientSID = FwDeleteAllRules(*(_QWORD *)a2, 0), v5 = RPCClientSID, RPCClientSID < 0) )
          {
            v9 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_40;
            }
            v10 = 108;
          }
          else
          {
            if ( v6 == 4
              || (RPCClientSID = FwIncrmDeleteAllRules(*((_QWORD *)a2 + 1), (unsigned int)a2[4], 0),
                  v5 = RPCClientSID,
                  RPCClientSID >= 0) )
            {
              v13 = FwStringTableFind(&dword_1801341D0, 23173);
              FwAuditLogRuleChange((_DWORD)v8, 0x7FFFFFFF, 0, 1, v13, 0);
LABEL_40:
              FwUnlockInternal(a1, "SvrImpl_FWDeleteAllFirewallRules");
              FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllFirewallRules");
              if ( (v5 & 0x80000000) == 0 )
                FwChangeSourceSignal();
              v14 = &qword_1800FBFF0;
              v19 = FwHResultToWindowsError(v5);
              v15 = &qword_1800FBFF0;
              v16 = L"S-1-0-0";
              if ( v20 )
                v15 = v20;
              if ( v8 )
                v16 = v8;
              FwLogBatchUpdate("\v\b", v16, v15, v6, v19);
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
              {
                if ( v20 )
                  v14 = v20;
                v17 = FwHResultToWindowsError(v5);
                WPP_SF_DSD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 110, v18, v17, (__int64)v14, v6);
              }
              FwFree(v21);
              if ( a1 )
                FwFree(v20);
              return FwHResultToWindowsError(v5);
            }
            v9 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_40;
            }
            v10 = 109;
          }
          goto LABEL_12;
        }
      }
      v5 = -2147024846;
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_40;
      v10 = 107;
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 105);
        v9 = WPP_GLOBAL_Control;
      }
      v5 = -2147024891;
      if ( (_UNKNOWN *)v9 == &WPP_GLOBAL_Control || (*(_BYTE *)(v9 + 28) & 1) == 0 )
        goto LABEL_40;
      v10 = 106;
    }
    v11 = v5;
    goto LABEL_39;
  }
  return result;
}

```

## disassembly

```asm
0x180047e34  mov     r11, rsp
0x180047e37  mov     [r11+18h], rbx
0x180047e3b  mov     [r11+20h], rbp
0x180047e3f  push    rsi
0x180047e40  push    rdi
0x180047e41  push    r12
0x180047e43  push    r13
0x180047e45  push    r14
0x180047e47  sub     rsp, 50h
0x180047e4b  mov     rax, cs:__security_cookie
0x180047e52  xor     rax, rsp
0x180047e55  mov     [rsp+78h+var_38], rax
0x180047e5a  mov     rdi, rdx
0x180047e5d  mov     qword ptr [r11-40h], 0
0x180047e65  mov     rsi, rcx
0x180047e68  mov     qword ptr [r11-48h], 0
0x180047e70  mov     rcx, cs:WPP_GLOBAL_Control
0x180047e77  lea     r12, WPP_GLOBAL_Control
0x180047e7e  lea     r13, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180047e85  cmp     rcx, r12
0x180047e88  jz      short loc_180047EA1
0x180047e8a  test    byte ptr [rcx+1Ch], 8
0x180047e8e  jz      short loc_180047EA1
0x180047e90  mov     rcx, [rcx+10h]
0x180047e94  mov     edx, 67h ; 'g'
0x180047e99  mov     r8, r13
0x180047e9c  call    WPP_SF_
0x180047ea1  lea     rcx, aSvrimplFwdelet_1; "SvrImpl_FWDeleteAllFirewallRules"
0x180047ea8  call    FwAcquireRPCSharedLock
0x180047ead  test    eax, eax
0x180047eaf  js      loc_18004817D
0x180047eb5  call    FwLock
0x180047eba  mov     ebx, eax
0x180047ebc  test    eax, eax
0x180047ebe  jns     short loc_180047ED3
0x180047ec0  lea     rcx, aSvrimplFwdelet_1; "SvrImpl_FWDeleteAllFirewallRules"
0x180047ec7  call    FwReleaseRPCSharedLock
0x180047ecc  mov     eax, ebx
0x180047ece  jmp     loc_18004817D
0x180047ed3  xor     ebp, ebp
0x180047ed5  test    rsi, rsi
0x180047ed8  jz      short loc_180047F33
0x180047eda  lea     rdx, [rsp+78h+var_40]
0x180047edf  mov     rcx, rsi
0x180047ee2  call    ExtractRPCClientSID
0x180047ee7  mov     ebx, eax
0x180047ee9  test    eax, eax
0x180047eeb  jns     short loc_180047F15
0x180047eed  xor     r14d, r14d
0x180047ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x180047ef7  cmp     rcx, r12
0x180047efa  jz      loc_18004808B
0x180047f00  test    byte ptr [rcx+1Ch], 1
0x180047f04  jz      loc_18004808B
0x180047f0a  lea     edx, [rbp+68h]
0x180047f0d  mov     r9d, eax
0x180047f10  jmp     loc_18004807F
0x180047f15  mov     rax, [rsp+78h+var_40]
0x180047f1a  lea     rdx, [rsp+78h+var_48]
0x180047f1f  mov     rcx, rsi
0x180047f22  mov     r14, [rax]
0x180047f25  call    cs:__imp_FwGetRpcCallersProcessImageName
0x180047f2c  nop     dword ptr [rax+rax+00h]
0x180047f31  jmp     short loc_180047F46
0x180047f33  mov     rax, cs:qword_180134208
0x180047f3a  mov     r14, cs:qword_180134200
0x180047f41  mov     [rsp+78h+var_48], rax
0x180047f46  mov     r9d, [rdi+18h]
0x180047f4a  cmp     r9d, 2
0x180047f4e  jz      short loc_180047F99
0x180047f50  mov     rcx, cs:WPP_GLOBAL_Control
0x180047f57  cmp     rcx, r12
0x180047f5a  jz      short loc_180047F77
0x180047f5c  test    byte ptr [rcx+1Ch], 1
0x180047f60  jz      short loc_180047F77
0x180047f62  mov     rcx, [rcx+10h]
0x180047f66  mov     edx, 69h ; 'i'
0x180047f6b  call    WPP_SF_l
0x180047f70  mov     rcx, cs:WPP_GLOBAL_Control
0x180047f77  mov     ebx, 80070005h
0x180047f7c  cmp     rcx, r12
0x180047f7f  jz      loc_18004808B
0x180047f85  test    byte ptr [rcx+1Ch], 1
0x180047f89  jz      loc_18004808B
0x180047f8f  mov     edx, 6Ah ; 'j'
0x180047f94  jmp     loc_18004807C
0x180047f99  mov     ebp, [rdi+10h]
0x180047f9c  cmp     ebp, 0Ch
0x180047f9f  ja      loc_180048060
0x180047fa5  mov     eax, 1034h
0x180047faa  bt      eax, ebp
0x180047fad  jnb     loc_180048060
0x180047fb3  mov     rcx, [rdi]
0x180047fb6  test    rcx, rcx
0x180047fb9  jz      short loc_180047FF3
0x180047fbb  xor     edx, edx
0x180047fbd  call    cs:__imp_FwDeleteAllRules
0x180047fc4  nop     dword ptr [rax+rax+00h]
0x180047fc9  mov     ebx, eax
0x180047fcb  test    eax, eax
0x180047fcd  jns     short loc_180047FF3
0x180047fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180047fd6  cmp     rcx, r12
0x180047fd9  jz      loc_18004808B
0x180047fdf  test    byte ptr [rcx+1Ch], 1
0x180047fe3  jz      loc_18004808B
0x180047fe9  mov     edx, 6Ch ; 'l'
0x180047fee  jmp     loc_180047F0D
0x180047ff3  cmp     ebp, 4
0x180047ff6  jz      short loc_180048029
0x180047ff8  mov     edx, [rdi+10h]
0x180047ffb  xor     r8d, r8d
0x180047ffe  mov     rcx, [rdi+8]
0x180048002  call    FwIncrmDeleteAllRules
0x180048007  mov     ebx, eax
0x180048009  test    eax, eax
0x18004800b  jns     short loc_180048029
0x18004800d  mov     rcx, cs:WPP_GLOBAL_Control
0x180048014  cmp     rcx, r12
0x180048017  jz      short loc_18004808B
0x180048019  test    byte ptr [rcx+1Ch], 1
0x18004801d  jz      short loc_18004808B
0x18004801f  mov     edx, 6Dh ; 'm'
0x180048024  jmp     loc_180047F0D
0x180048029  mov     edx, 5A85h
0x18004802e  lea     rcx, dword_1801341D0
0x180048035  call    FwStringTableFind
0x18004803a  mov     r9d, 1
0x180048040  mov     [rsp+78h+var_50], 0
0x180048049  xor     r8d, r8d
0x18004804c  mov     [rsp+78h+var_58], rax
0x180048051  mov     edx, 7FFFFFFFh
0x180048056  mov     rcx, r14
0x180048059  call    FwAuditLogRuleChange
0x18004805e  jmp     short loc_18004808B
0x180048060  mov     ebx, 80070032h
0x180048065  mov     rcx, cs:WPP_GLOBAL_Control
0x18004806c  cmp     rcx, r12
0x18004806f  jz      short loc_18004808B
0x180048071  test    byte ptr [rcx+1Ch], 1
0x180048075  jz      short loc_18004808B
0x180048077  mov     edx, 6Bh ; 'k'
0x18004807c  mov     r9d, ebx
0x18004807f  mov     rcx, [rcx+10h]
0x180048083  mov     r8, r13
0x180048086  call    WPP_SF_d
0x18004808b  lea     rdx, aSvrimplFwdelet_1; "SvrImpl_FWDeleteAllFirewallRules"
0x180048092  mov     rcx, rsi; void *
0x180048095  call    FwUnlockInternal
0x18004809a  lea     rcx, aSvrimplFwdelet_1; "SvrImpl_FWDeleteAllFirewallRules"
0x1800480a1  call    FwReleaseRPCSharedLock
0x1800480a6  test    ebx, ebx
0x1800480a8  js      short loc_1800480B6
0x1800480aa  call    cs:__imp_FwChangeSourceSignal
0x1800480b1  nop     dword ptr [rax+rax+00h]
0x1800480b6  mov     ecx, ebx
0x1800480b8  call    cs:__imp_FwHResultToWindowsError
0x1800480bf  nop     dword ptr [rax+rax+00h]
0x1800480c4  mov     rcx, [rsp+78h+var_48]
0x1800480c9  lea     rdi, qword_1800FBFF0
0x1800480d0  test    rcx, rcx
0x1800480d3  mov     dword ptr [rsp+78h+var_58], eax
0x1800480d7  mov     r8, rdi
0x1800480da  lea     rdx, aS100; "S-1-0-0"
0x1800480e1  cmovnz  r8, rcx
0x1800480e5  mov     r9d, ebp
0x1800480e8  test    r14, r14
0x1800480eb  lea     rcx, WFAllFirewallRulesDeletedEvent0; "\v\b"
0x1800480f2  cmovnz  rdx, r14
0x1800480f6  call    ?FwLogBatchUpdate@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGW4_tag_FW_STORE_TYPE@@K@Z; FwLogBatchUpdate(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_STORE_TYPE,ulong)
0x1800480fb  mov     rax, cs:WPP_GLOBAL_Control
0x180048102  cmp     rax, r12
0x180048105  jz      short loc_180048148
0x180048107  test    byte ptr [rax+1Ch], 4
0x18004810b  jz      short loc_180048148
0x18004810d  mov     rax, [rsp+78h+var_48]
0x180048112  mov     ecx, ebx
0x180048114  test    rax, rax
0x180048117  cmovnz  rdi, rax
0x18004811b  call    cs:__imp_FwHResultToWindowsError
0x180048122  nop     dword ptr [rax+rax+00h]
0x180048127  mov     rcx, cs:WPP_GLOBAL_Control
0x18004812e  mov     edx, 6Eh ; 'n'
0x180048133  mov     dword ptr [rsp+78h+var_50], ebp
0x180048137  mov     r9d, eax
0x18004813a  mov     [rsp+78h+var_58], rdi
0x18004813f  mov     rcx, [rcx+10h]
0x180048143  call    WPP_SF_DSD
0x180048148  mov     rcx, [rsp+78h+var_40]
0x18004814d  call    cs:__imp_FwFree
0x180048154  nop     dword ptr [rax+rax+00h]
0x180048159  test    rsi, rsi
0x18004815c  jz      short loc_18004816F
0x18004815e  mov     rcx, [rsp+78h+var_48]
0x180048163  call    cs:__imp_FwFree
0x18004816a  nop     dword ptr [rax+rax+00h]
0x18004816f  mov     ecx, ebx
0x180048171  call    cs:__imp_FwHResultToWindowsError
0x180048178  nop     dword ptr [rax+rax+00h]
0x18004817d  mov     rcx, [rsp+78h+var_38]
0x180048182  xor     rcx, rsp; StackCookie
0x180048185  call    __security_check_cookie
0x18004818a  lea     r11, [rsp+78h+var_28]
0x18004818f  mov     rbx, [r11+40h]
0x180048193  mov     rbp, [r11+48h]
0x180048197  mov     rsp, r11
0x18004819a  pop     r14
0x18004819c  pop     r13
0x18004819e  pop     r12
0x1800481a0  pop     rdi
0x1800481a1  pop     rsi
0x1800481a2  retn
```
