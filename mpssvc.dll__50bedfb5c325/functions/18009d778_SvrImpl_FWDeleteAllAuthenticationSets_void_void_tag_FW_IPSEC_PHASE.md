# SvrImpl_FWDeleteAllAuthenticationSets(void *,void *,_tag_FW_IPSEC_PHASE)

- ea: `0x18009d778`
- end: `0x18009daf3`
- name: `?SvrImpl_FWDeleteAllAuthenticationSets@@YAKPEAX0W4_tag_FW_IPSEC_PHASE@@@Z`
- size: `891`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800c7510`

## callees

- `0x180005b70`
- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x1800192e0`
- `0x18003ec48`
- `0x180059714`
- `0x18006e578`
- `0x1800729c0`
- `0x18008bc14`
- `0x18008c4b8`
- `0x18008f870`
- `0x18009d778`
- `0x1800a7b68`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18009da05`
- `fwbase!FwHResultToWindowsError` at `0x18009da74`
- `fwbase!FwHResultToWindowsError` at `0x18009daca`
- `fwbase!FwHResultToWindowsError` at `0x18009da05`
- `fwbase!FwHResultToWindowsError` at `0x18009da74`
- `fwbase!FwHResultToWindowsError` at `0x18009daca`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009d864`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009d864`
- `fwbase!FwChangeSourceSignal` at `0x18009d9f7`
- `fwbase!FwChangeSourceSignal` at `0x18009d9f7`
- `fwbase!FwFree` at `0x18009daab`
- `fwbase!FwFree` at `0x18009dabc`
- `fwbase!FwFree` at `0x18009daab`
- `fwbase!FwFree` at `0x18009dabc`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18009d93b`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18009d93b`

## string_xrefs

- `0x18009d7e2`: `SvrImpl_FWDeleteAllAuthenticationSets`
- `0x18009d801`: `SvrImpl_FWDeleteAllAuthenticationSets`
- `0x18009d9d8`: `SvrImpl_FWDeleteAllAuthenticationSets`
- `0x18009d9e7`: `SvrImpl_FWDeleteAllAuthenticationSets`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWDeleteAllAuthenticationSets(void *a1, __int64 a2, unsigned int a3)
{
  __int64 result; // rax
  int v7; // ebx
  int v8; // esi
  int RPCClientSID; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rdi
  const unsigned __int16 *v17; // r8
  const wchar_t *v18; // rdx
  int v19; // eax
  int v20; // r8d
  const wchar_t **v21; // [rsp+40h] [rbp-58h] BYREF
  const unsigned __int16 *v22; // [rsp+48h] [rbp-50h] BYREF

  v21 = 0;
  v22 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 315, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWDeleteAllAuthenticationSets");
  if ( (int)result >= 0 )
  {
    v7 = FwLock();
    if ( v7 < 0 )
    {
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllAuthenticationSets");
      return (unsigned int)v7;
    }
    v8 = 0;
    RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v21);
    v10 = RPCClientSID;
    if ( RPCClientSID < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_40;
      v12 = 316;
LABEL_11:
      v13 = (unsigned int)RPCClientSID;
LABEL_12:
      WPP_SF_d(*(_QWORD *)(v11 + 16), v12, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v13);
LABEL_40:
      FwUnlockInternal(a1, "SvrImpl_FWDeleteAllAuthenticationSets");
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllAuthenticationSets");
      if ( (v10 & 0x80000000) == 0 )
        FwChangeSourceSignal();
      v15 = FwHResultToWindowsError(v10);
      v16 = &qword_1800FBFF0;
      v17 = &qword_1800FBFF0;
      if ( v22 )
        v17 = v22;
      if ( v21 )
        v18 = *v21;
      else
        v18 = L"S-1-0-0";
      FwLogBatchUpdateCSObjects(WFAllAuthenticationSetsDeletedEvent0, v18, v17, a3, v8, v15);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        if ( v22 )
          v16 = v22;
        v19 = FwHResultToWindowsError(v10);
        WPP_SF_DSDD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 323, v20, v19, (__int64)v16, a3, v8);
      }
      FwFree(v21);
      FwFree(v22);
      return FwHResultToWindowsError(v10);
    }
    FwGetRpcCallersProcessImageName(a1, &v22);
    if ( *(_DWORD *)(a2 + 24) == 2 )
    {
      v8 = *(_DWORD *)(a2 + 16);
      if ( v8 == 2 || v8 == 5 )
      {
        if ( !(unsigned int)FwAnyNonDefaultSetsAreInUse(*(_QWORD *)(a2 + 8), 0, a3) )
        {
          if ( *(_QWORD *)a2
            && (RPCClientSID = FwDeleteAllSets(*(_QWORD *)a2, 0, a3), v10 = RPCClientSID, RPCClientSID < 0) )
          {
            v11 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_40;
            }
            v12 = 321;
          }
          else
          {
            RPCClientSID = FwIncrmDeleteAllSets(*(_QWORD *)(a2 + 8), *(unsigned int *)(a2 + 16), 0, a3);
            v10 = RPCClientSID;
            if ( RPCClientSID >= 0 )
            {
              v14 = FwStringTableFind(&dword_1801341D0, 23173);
              FwAuditLogRuleChange((unsigned int)*v21, 0x7FFFFFFF, 4, 1, v14, 0);
              goto LABEL_40;
            }
            v11 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_40;
            }
            v12 = 322;
          }
          goto LABEL_11;
        }
        v10 = -2147022494;
        v11 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_40;
        v12 = 320;
      }
      else
      {
        v10 = -2147024846;
        v11 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_40;
        v12 = 319;
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 317);
        v11 = WPP_GLOBAL_Control;
      }
      v10 = -2147024891;
      if ( (_UNKNOWN *)v11 == &WPP_GLOBAL_Control || (*(_BYTE *)(v11 + 28) & 1) == 0 )
        goto LABEL_40;
      v12 = 318;
    }
    v13 = v10;
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x18009d778  push    rbx
0x18009d77a  push    rbp
0x18009d77b  push    rsi
0x18009d77c  push    rdi
0x18009d77d  push    r12
0x18009d77f  push    r13
0x18009d781  push    r14
0x18009d783  sub     rsp, 60h
0x18009d787  mov     rax, cs:__security_cookie
0x18009d78e  xor     rax, rsp
0x18009d791  mov     [rsp+98h+var_48], rax
0x18009d796  mov     r14d, r8d
0x18009d799  mov     [rsp+98h+var_58], 0
0x18009d7a2  mov     rdi, rdx
0x18009d7a5  mov     [rsp+98h+var_50], 0
0x18009d7ae  mov     rbp, rcx
0x18009d7b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d7b8  lea     r12, WPP_GLOBAL_Control
0x18009d7bf  lea     r13, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009d7c6  cmp     rcx, r12
0x18009d7c9  jz      short loc_18009D7E2
0x18009d7cb  test    byte ptr [rcx+1Ch], 8
0x18009d7cf  jz      short loc_18009D7E2
0x18009d7d1  mov     rcx, [rcx+10h]
0x18009d7d5  mov     edx, 13Bh
0x18009d7da  mov     r8, r13
0x18009d7dd  call    WPP_SF_
0x18009d7e2  lea     rcx, aSvrimplFwdelet_2; "SvrImpl_FWDeleteAllAuthenticationSets"
0x18009d7e9  call    FwAcquireRPCSharedLock
0x18009d7ee  test    eax, eax
0x18009d7f0  js      loc_18009DAD6
0x18009d7f6  call    FwLock
0x18009d7fb  mov     ebx, eax
0x18009d7fd  test    eax, eax
0x18009d7ff  jns     short loc_18009D814
0x18009d801  lea     rcx, aSvrimplFwdelet_2; "SvrImpl_FWDeleteAllAuthenticationSets"
0x18009d808  call    FwReleaseRPCSharedLock
0x18009d80d  mov     eax, ebx
0x18009d80f  jmp     loc_18009DAD6
0x18009d814  lea     rdx, [rsp+98h+var_58]
0x18009d819  mov     rcx, rbp
0x18009d81c  xor     esi, esi
0x18009d81e  call    ExtractRPCClientSID
0x18009d823  mov     ebx, eax
0x18009d825  test    eax, eax
0x18009d827  jns     short loc_18009D85C
0x18009d829  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d830  cmp     rcx, r12
0x18009d833  jz      loc_18009D9D8
0x18009d839  test    byte ptr [rcx+1Ch], 1
0x18009d83d  jz      loc_18009D9D8
0x18009d843  mov     edx, 13Ch
0x18009d848  mov     r9d, eax
0x18009d84b  mov     rcx, [rcx+10h]
0x18009d84f  mov     r8, r13
0x18009d852  call    WPP_SF_d
0x18009d857  jmp     loc_18009D9D8
0x18009d85c  lea     rdx, [rsp+98h+var_50]
0x18009d861  mov     rcx, rbp
0x18009d864  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009d86b  nop     dword ptr [rax+rax+00h]
0x18009d870  mov     r9d, [rdi+18h]
0x18009d874  cmp     r9d, 2
0x18009d878  jz      short loc_18009D8C3
0x18009d87a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d881  cmp     rcx, r12
0x18009d884  jz      short loc_18009D8A1
0x18009d886  test    byte ptr [rcx+1Ch], 1
0x18009d88a  jz      short loc_18009D8A1
0x18009d88c  mov     rcx, [rcx+10h]
0x18009d890  mov     edx, 13Dh
0x18009d895  call    WPP_SF_l
0x18009d89a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d8a1  mov     ebx, 80070005h
0x18009d8a6  cmp     rcx, r12
0x18009d8a9  jz      loc_18009D9D8
0x18009d8af  test    byte ptr [rcx+1Ch], 1
0x18009d8b3  jz      loc_18009D9D8
0x18009d8b9  mov     edx, 13Eh
0x18009d8be  mov     r9d, ebx
0x18009d8c1  jmp     short loc_18009D84B
0x18009d8c3  mov     esi, [rdi+10h]
0x18009d8c6  cmp     esi, 2
0x18009d8c9  jz      short loc_18009D8F6
0x18009d8cb  cmp     esi, 5
0x18009d8ce  jz      short loc_18009D8F6
0x18009d8d0  mov     ebx, 80070032h
0x18009d8d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d8dc  cmp     rcx, r12
0x18009d8df  jz      loc_18009D9D8
0x18009d8e5  test    byte ptr [rcx+1Ch], 1
0x18009d8e9  jz      loc_18009D9D8
0x18009d8ef  mov     edx, 13Fh
0x18009d8f4  jmp     short loc_18009D8BE
0x18009d8f6  mov     rcx, [rdi+8]
0x18009d8fa  mov     r8d, r14d
0x18009d8fd  xor     edx, edx
0x18009d8ff  call    FwAnyNonDefaultSetsAreInUse
0x18009d904  test    eax, eax
0x18009d906  jz      short loc_18009D92E
0x18009d908  mov     ebx, 80070962h
0x18009d90d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d914  cmp     rcx, r12
0x18009d917  jz      loc_18009D9D8
0x18009d91d  test    byte ptr [rcx+1Ch], 1
0x18009d921  jz      loc_18009D9D8
0x18009d927  mov     edx, 140h
0x18009d92c  jmp     short loc_18009D8BE
0x18009d92e  mov     rcx, [rdi]
0x18009d931  test    rcx, rcx
0x18009d934  jz      short loc_18009D969
0x18009d936  mov     r8d, r14d
0x18009d939  xor     edx, edx
0x18009d93b  call    cs:__imp_FwDeleteAllSets
0x18009d942  nop     dword ptr [rax+rax+00h]
0x18009d947  mov     ebx, eax
0x18009d949  test    eax, eax
0x18009d94b  jns     short loc_18009D969
0x18009d94d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d954  cmp     rcx, r12
0x18009d957  jz      short loc_18009D9D8
0x18009d959  test    byte ptr [rcx+1Ch], 1
0x18009d95d  jz      short loc_18009D9D8
0x18009d95f  mov     edx, 141h
0x18009d964  jmp     loc_18009D848
0x18009d969  mov     edx, [rdi+10h]
0x18009d96c  mov     r9d, r14d
0x18009d96f  mov     rcx, [rdi+8]
0x18009d973  xor     r8d, r8d
0x18009d976  call    FwIncrmDeleteAllSets
0x18009d97b  mov     ebx, eax
0x18009d97d  test    eax, eax
0x18009d97f  jns     short loc_18009D99D
0x18009d981  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d988  cmp     rcx, r12
0x18009d98b  jz      short loc_18009D9D8
0x18009d98d  test    byte ptr [rcx+1Ch], 1
0x18009d991  jz      short loc_18009D9D8
0x18009d993  mov     edx, 142h
0x18009d998  jmp     loc_18009D848
0x18009d99d  mov     edx, 5A85h
0x18009d9a2  lea     rcx, dword_1801341D0
0x18009d9a9  call    FwStringTableFind
0x18009d9ae  mov     rcx, [rsp+98h+var_58]
0x18009d9b3  mov     r9d, 1
0x18009d9b9  mov     [rsp+98h+var_70], 0
0x18009d9c2  mov     edx, 7FFFFFFFh
0x18009d9c7  mov     [rsp+98h+var_78], rax
0x18009d9cc  mov     rcx, [rcx]
0x18009d9cf  lea     r8d, [r9+3]
0x18009d9d3  call    FwAuditLogRuleChange
0x18009d9d8  lea     rdx, aSvrimplFwdelet_2; "SvrImpl_FWDeleteAllAuthenticationSets"
0x18009d9df  mov     rcx, rbp; void *
0x18009d9e2  call    FwUnlockInternal
0x18009d9e7  lea     rcx, aSvrimplFwdelet_2; "SvrImpl_FWDeleteAllAuthenticationSets"
0x18009d9ee  call    FwReleaseRPCSharedLock
0x18009d9f3  test    ebx, ebx
0x18009d9f5  js      short loc_18009DA03
0x18009d9f7  call    cs:__imp_FwChangeSourceSignal
0x18009d9fe  nop     dword ptr [rax+rax+00h]
0x18009da03  mov     ecx, ebx
0x18009da05  call    cs:__imp_FwHResultToWindowsError
0x18009da0c  nop     dword ptr [rax+rax+00h]
0x18009da11  mov     rcx, [rsp+98h+var_50]
0x18009da16  lea     rdi, qword_1800FBFF0
0x18009da1d  mov     rdx, [rsp+98h+var_58]
0x18009da22  test    rcx, rcx
0x18009da25  mov     r8, rdi
0x18009da28  cmovnz  r8, rcx
0x18009da2c  test    rdx, rdx
0x18009da2f  jz      short loc_18009DA36
0x18009da31  mov     rdx, [rdx]
0x18009da34  jmp     short loc_18009DA3D
0x18009da36  lea     rdx, aS100; "S-1-0-0"
0x18009da3d  mov     dword ptr [rsp+98h+var_70], eax
0x18009da41  lea     rcx, WFAllAuthenticationSetsDeletedEvent0
0x18009da48  mov     r9d, r14d
0x18009da4b  mov     dword ptr [rsp+98h+var_78], esi
0x18009da4f  call    ?FwLogBatchUpdateCSObjects@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGW4_tag_FW_IPSEC_PHASE@@W4_tag_FW_STORE_TYPE@@K@Z; FwLogBatchUpdateCSObjects(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_IPSEC_PHASE,_tag_FW_STORE_TYPE,ulong)
0x18009da54  mov     rax, cs:WPP_GLOBAL_Control
0x18009da5b  cmp     rax, r12
0x18009da5e  jz      short loc_18009DAA6
0x18009da60  test    byte ptr [rax+1Ch], 4
0x18009da64  jz      short loc_18009DAA6
0x18009da66  mov     rax, [rsp+98h+var_50]
0x18009da6b  mov     ecx, ebx
0x18009da6d  test    rax, rax
0x18009da70  cmovnz  rdi, rax
0x18009da74  call    cs:__imp_FwHResultToWindowsError
0x18009da7b  nop     dword ptr [rax+rax+00h]
0x18009da80  mov     rcx, cs:WPP_GLOBAL_Control
0x18009da87  mov     edx, 143h
0x18009da8c  mov     [rsp+98h+var_68], esi
0x18009da90  mov     r9d, eax
0x18009da93  mov     dword ptr [rsp+98h+var_70], r14d
0x18009da98  mov     [rsp+98h+var_78], rdi
0x18009da9d  mov     rcx, [rcx+10h]
0x18009daa1  call    WPP_SF_DSDD
0x18009daa6  mov     rcx, [rsp+98h+var_58]
0x18009daab  call    cs:__imp_FwFree
0x18009dab2  nop     dword ptr [rax+rax+00h]
0x18009dab7  mov     rcx, [rsp+98h+var_50]
0x18009dabc  call    cs:__imp_FwFree
0x18009dac3  nop     dword ptr [rax+rax+00h]
0x18009dac8  mov     ecx, ebx
0x18009daca  call    cs:__imp_FwHResultToWindowsError
0x18009dad1  nop     dword ptr [rax+rax+00h]
0x18009dad6  mov     rcx, [rsp+98h+var_48]
0x18009dadb  xor     rcx, rsp; StackCookie
0x18009dade  call    __security_check_cookie
0x18009dae3  add     rsp, 60h
0x18009dae7  pop     r14
0x18009dae9  pop     r13
0x18009daeb  pop     r12
0x18009daed  pop     rdi
0x18009daee  pop     rsi
0x18009daef  pop     rbp
0x18009daf0  pop     rbx
0x18009daf1  retn
```
