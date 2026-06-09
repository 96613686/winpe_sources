# SvrImpl_FWDeleteAllFirewallRules(void *,void *)

- ea: `0x180054748`
- end: `0x180054a87`
- name: `?SvrImpl_FWDeleteAllFirewallRules@@YAKPEAX0@Z`
- size: `831`
- prototype: `unsigned int __fastcall(void *, void *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800a4444`
- `0x1800c0930`

## callees

- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180017110`
- `0x18003e798`
- `0x18005441c`
- `0x180054748`
- `0x180054a90`
- `0x18005c294`
- `0x18006b5d8`
- `0x18006f520`
- `0x1800a1868`
- `0x1800a2378`

## import_xrefs

- `fwbase!FwGetRpcCallersProcessImageName` at `0x180054839`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180054839`
- `fwbase!FwChangeSourceSignal` at `0x1800549b2`
- `fwbase!FwChangeSourceSignal` at `0x1800549b2`
- `fwbase!FwHResultToWindowsError` at `0x1800549ba`
- `fwbase!FwHResultToWindowsError` at `0x180054a17`
- `fwbase!FwHResultToWindowsError` at `0x180054a5b`
- `fwbase!FwHResultToWindowsError` at `0x1800549ba`
- `fwbase!FwHResultToWindowsError` at `0x180054a17`
- `fwbase!FwHResultToWindowsError` at `0x180054a5b`
- `fwbase!FwFree` at `0x180054a43`
- `fwbase!FwFree` at `0x180054a53`
- `fwbase!FwFree` at `0x180054a43`
- `fwbase!FwFree` at `0x180054a53`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x1800548cb`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x1800548cb`

## string_xrefs

- `0x1800547b5`: `SvrImpl_FWDeleteAllFirewallRules`
- `0x1800547d4`: `SvrImpl_FWDeleteAllFirewallRules`
- `0x180054993`: `SvrImpl_FWDeleteAllFirewallRules`
- `0x1800549a2`: `SvrImpl_FWDeleteAllFirewallRules`

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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 103, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
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
        WPP_SF_d(*(_QWORD *)(v9 + 16), v10, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v11);
        goto LABEL_40;
      }
      v8 = *v21;
      FwGetRpcCallersProcessImageName(a1, &v20);
    }
    else
    {
      v8 = (const wchar_t *)qword_18012E050;
      v20 = qword_18012E058;
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
              v13 = FwStringTableFind(&dword_18012E020, 23173);
              FwAuditLogRuleChange((_DWORD)v8, 0x7FFFFFFF, 0, 1, v13, 0);
LABEL_40:
              FwUnlockInternal(a1, "SvrImpl_FWDeleteAllFirewallRules");
              FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllFirewallRules");
              if ( (v5 & 0x80000000) == 0 )
                FwChangeSourceSignal();
              v14 = &qword_1800F5F90;
              v19 = FwHResultToWindowsError(v5);
              v15 = &qword_1800F5F90;
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
0x180054748  mov     r11, rsp
0x18005474b  mov     [r11+18h], rbx
0x18005474f  mov     [r11+20h], rbp
0x180054753  push    rsi
0x180054754  push    rdi
0x180054755  push    r12
0x180054757  push    r13
0x180054759  push    r14
0x18005475b  sub     rsp, 50h
0x18005475f  mov     rax, cs:__security_cookie
0x180054766  xor     rax, rsp
0x180054769  mov     [rsp+78h+var_38], rax
0x18005476e  mov     rdi, rdx
0x180054771  mov     qword ptr [r11-40h], 0
0x180054779  mov     rsi, rcx
0x18005477c  mov     qword ptr [r11-48h], 0
0x180054784  mov     rcx, cs:WPP_GLOBAL_Control
0x18005478b  lea     r12, WPP_GLOBAL_Control
0x180054792  lea     r13, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180054799  cmp     rcx, r12
0x18005479c  jz      short loc_1800547B5
0x18005479e  test    byte ptr [rcx+1Ch], 8
0x1800547a2  jz      short loc_1800547B5
0x1800547a4  mov     rcx, [rcx+10h]
0x1800547a8  mov     edx, 67h ; 'g'
0x1800547ad  mov     r8, r13
0x1800547b0  call    WPP_SF_
0x1800547b5  lea     rcx, aSvrimplFwdelet_1; "SvrImpl_FWDeleteAllFirewallRules"
0x1800547bc  call    FwAcquireRPCSharedLock
0x1800547c1  test    eax, eax
0x1800547c3  js      loc_180054A61
0x1800547c9  call    FwLock
0x1800547ce  mov     ebx, eax
0x1800547d0  test    eax, eax
0x1800547d2  jns     short loc_1800547E7
0x1800547d4  lea     rcx, aSvrimplFwdelet_1; "SvrImpl_FWDeleteAllFirewallRules"
0x1800547db  call    FwReleaseRPCSharedLock
0x1800547e0  mov     eax, ebx
0x1800547e2  jmp     loc_180054A61
0x1800547e7  xor     ebp, ebp
0x1800547e9  test    rsi, rsi
0x1800547ec  jz      short loc_180054841
0x1800547ee  lea     rdx, [rsp+78h+var_40]
0x1800547f3  mov     rcx, rsi
0x1800547f6  call    ExtractRPCClientSID
0x1800547fb  mov     ebx, eax
0x1800547fd  test    eax, eax
0x1800547ff  jns     short loc_180054829
0x180054801  xor     r14d, r14d
0x180054804  mov     rcx, cs:WPP_GLOBAL_Control
0x18005480b  cmp     rcx, r12
0x18005480e  jz      loc_180054993
0x180054814  test    byte ptr [rcx+1Ch], 1
0x180054818  jz      loc_180054993
0x18005481e  lea     edx, [rbp+68h]
0x180054821  mov     r9d, eax
0x180054824  jmp     loc_180054987
0x180054829  mov     rax, [rsp+78h+var_40]
0x18005482e  lea     rdx, [rsp+78h+var_48]
0x180054833  mov     rcx, rsi
0x180054836  mov     r14, [rax]
0x180054839  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18005483f  jmp     short loc_180054854
0x180054841  mov     rax, cs:qword_18012E058
0x180054848  mov     r14, cs:qword_18012E050
0x18005484f  mov     [rsp+78h+var_48], rax
0x180054854  mov     r9d, [rdi+18h]
0x180054858  cmp     r9d, 2
0x18005485c  jz      short loc_1800548A7
0x18005485e  mov     rcx, cs:WPP_GLOBAL_Control
0x180054865  cmp     rcx, r12
0x180054868  jz      short loc_180054885
0x18005486a  test    byte ptr [rcx+1Ch], 1
0x18005486e  jz      short loc_180054885
0x180054870  mov     rcx, [rcx+10h]
0x180054874  mov     edx, 69h ; 'i'
0x180054879  call    WPP_SF_l
0x18005487e  mov     rcx, cs:WPP_GLOBAL_Control
0x180054885  mov     ebx, 80070005h
0x18005488a  cmp     rcx, r12
0x18005488d  jz      loc_180054993
0x180054893  test    byte ptr [rcx+1Ch], 1
0x180054897  jz      loc_180054993
0x18005489d  mov     edx, 6Ah ; 'j'
0x1800548a2  jmp     loc_180054984
0x1800548a7  mov     ebp, [rdi+10h]
0x1800548aa  cmp     ebp, 0Ch
0x1800548ad  ja      loc_180054968
0x1800548b3  mov     eax, 1034h
0x1800548b8  bt      eax, ebp
0x1800548bb  jnb     loc_180054968
0x1800548c1  mov     rcx, [rdi]
0x1800548c4  test    rcx, rcx
0x1800548c7  jz      short loc_1800548FB
0x1800548c9  xor     edx, edx
0x1800548cb  call    cs:__imp_FwDeleteAllRules
0x1800548d1  mov     ebx, eax
0x1800548d3  test    eax, eax
0x1800548d5  jns     short loc_1800548FB
0x1800548d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800548de  cmp     rcx, r12
0x1800548e1  jz      loc_180054993
0x1800548e7  test    byte ptr [rcx+1Ch], 1
0x1800548eb  jz      loc_180054993
0x1800548f1  mov     edx, 6Ch ; 'l'
0x1800548f6  jmp     loc_180054821
0x1800548fb  cmp     ebp, 4
0x1800548fe  jz      short loc_180054931
0x180054900  mov     edx, [rdi+10h]
0x180054903  xor     r8d, r8d
0x180054906  mov     rcx, [rdi+8]
0x18005490a  call    FwIncrmDeleteAllRules
0x18005490f  mov     ebx, eax
0x180054911  test    eax, eax
0x180054913  jns     short loc_180054931
0x180054915  mov     rcx, cs:WPP_GLOBAL_Control
0x18005491c  cmp     rcx, r12
0x18005491f  jz      short loc_180054993
0x180054921  test    byte ptr [rcx+1Ch], 1
0x180054925  jz      short loc_180054993
0x180054927  mov     edx, 6Dh ; 'm'
0x18005492c  jmp     loc_180054821
0x180054931  mov     edx, 5A85h
0x180054936  lea     rcx, dword_18012E020
0x18005493d  call    FwStringTableFind
0x180054942  mov     r9d, 1
0x180054948  mov     [rsp+78h+var_50], 0
0x180054951  xor     r8d, r8d
0x180054954  mov     [rsp+78h+var_58], rax
0x180054959  mov     edx, 7FFFFFFFh
0x18005495e  mov     rcx, r14
0x180054961  call    FwAuditLogRuleChange
0x180054966  jmp     short loc_180054993
0x180054968  mov     ebx, 80070032h
0x18005496d  mov     rcx, cs:WPP_GLOBAL_Control
0x180054974  cmp     rcx, r12
0x180054977  jz      short loc_180054993
0x180054979  test    byte ptr [rcx+1Ch], 1
0x18005497d  jz      short loc_180054993
0x18005497f  mov     edx, 6Bh ; 'k'
0x180054984  mov     r9d, ebx
0x180054987  mov     rcx, [rcx+10h]
0x18005498b  mov     r8, r13
0x18005498e  call    WPP_SF_d
0x180054993  lea     rdx, aSvrimplFwdelet_1; "SvrImpl_FWDeleteAllFirewallRules"
0x18005499a  mov     rcx, rsi; void *
0x18005499d  call    FwUnlockInternal
0x1800549a2  lea     rcx, aSvrimplFwdelet_1; "SvrImpl_FWDeleteAllFirewallRules"
0x1800549a9  call    FwReleaseRPCSharedLock
0x1800549ae  test    ebx, ebx
0x1800549b0  js      short loc_1800549B8
0x1800549b2  call    cs:__imp_FwChangeSourceSignal
0x1800549b8  mov     ecx, ebx
0x1800549ba  call    cs:__imp_FwHResultToWindowsError
0x1800549c0  mov     rcx, [rsp+78h+var_48]
0x1800549c5  lea     rdi, qword_1800F5F90
0x1800549cc  test    rcx, rcx
0x1800549cf  mov     dword ptr [rsp+78h+var_58], eax
0x1800549d3  mov     r8, rdi
0x1800549d6  lea     rdx, aS100; "S-1-0-0"
0x1800549dd  cmovnz  r8, rcx
0x1800549e1  mov     r9d, ebp
0x1800549e4  test    r14, r14
0x1800549e7  lea     rcx, WFAllFirewallRulesDeletedEvent0; "\v\b"
0x1800549ee  cmovnz  rdx, r14
0x1800549f2  call    ?FwLogBatchUpdate@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGW4_tag_FW_STORE_TYPE@@K@Z; FwLogBatchUpdate(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_STORE_TYPE,ulong)
0x1800549f7  mov     rax, cs:WPP_GLOBAL_Control
0x1800549fe  cmp     rax, r12
0x180054a01  jz      short loc_180054A3E
0x180054a03  test    byte ptr [rax+1Ch], 4
0x180054a07  jz      short loc_180054A3E
0x180054a09  mov     rax, [rsp+78h+var_48]
0x180054a0e  mov     ecx, ebx
0x180054a10  test    rax, rax
0x180054a13  cmovnz  rdi, rax
0x180054a17  call    cs:__imp_FwHResultToWindowsError
0x180054a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180054a24  mov     edx, 6Eh ; 'n'
0x180054a29  mov     dword ptr [rsp+78h+var_50], ebp
0x180054a2d  mov     r9d, eax
0x180054a30  mov     [rsp+78h+var_58], rdi
0x180054a35  mov     rcx, [rcx+10h]
0x180054a39  call    WPP_SF_DSD
0x180054a3e  mov     rcx, [rsp+78h+var_40]
0x180054a43  call    cs:__imp_FwFree
0x180054a49  test    rsi, rsi
0x180054a4c  jz      short loc_180054A59
0x180054a4e  mov     rcx, [rsp+78h+var_48]
0x180054a53  call    cs:__imp_FwFree
0x180054a59  mov     ecx, ebx
0x180054a5b  call    cs:__imp_FwHResultToWindowsError
0x180054a61  mov     rcx, [rsp+78h+var_38]
0x180054a66  xor     rcx, rsp; StackCookie
0x180054a69  call    __security_check_cookie
0x180054a6e  lea     r11, [rsp+78h+var_28]
0x180054a73  mov     rbx, [r11+40h]
0x180054a77  mov     rbp, [r11+48h]
0x180054a7b  mov     rsp, r11
0x180054a7e  pop     r14
0x180054a80  pop     r13
0x180054a82  pop     r12
0x180054a84  pop     rdi
0x180054a85  pop     rsi
0x180054a86  retn
```
