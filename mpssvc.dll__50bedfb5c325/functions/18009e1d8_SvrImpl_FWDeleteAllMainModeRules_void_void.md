# SvrImpl_FWDeleteAllMainModeRules(void *,void *)

- ea: `0x18009e1d8`
- end: `0x18009e515`
- name: `?SvrImpl_FWDeleteAllMainModeRules@@YAKPEAX0@Z`
- size: `829`
- prototype: `unsigned int __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800c7870`

## callees

- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x1800192e0`
- `0x18003ec48`
- `0x1800481ac`
- `0x180059714`
- `0x180060ef8`
- `0x18006e578`
- `0x1800729c0`
- `0x18009e1d8`
- `0x1800a700c`
- `0x1800a7b68`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18009e42b`
- `fwbase!FwHResultToWindowsError` at `0x18009e496`
- `fwbase!FwHResultToWindowsError` at `0x18009e4e7`
- `fwbase!FwHResultToWindowsError` at `0x18009e42b`
- `fwbase!FwHResultToWindowsError` at `0x18009e496`
- `fwbase!FwHResultToWindowsError` at `0x18009e4e7`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009e2c2`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009e2c2`
- `fwbase!FwChangeSourceSignal` at `0x18009e41d`
- `fwbase!FwChangeSourceSignal` at `0x18009e41d`
- `fwbase!FwFree` at `0x18009e4c8`
- `fwbase!FwFree` at `0x18009e4d9`
- `fwbase!FwFree` at `0x18009e4c8`
- `fwbase!FwFree` at `0x18009e4d9`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x18009e361`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x18009e361`

## string_xrefs

- `0x18009e240`: `SvrImpl_FWDeleteAllMainModeRules`
- `0x18009e25f`: `SvrImpl_FWDeleteAllMainModeRules`
- `0x18009e3fe`: `SvrImpl_FWDeleteAllMainModeRules`
- `0x18009e40d`: `SvrImpl_FWDeleteAllMainModeRules`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWDeleteAllMainModeRules(void *a1, _DWORD *a2)
{
  __int64 result; // rax
  int v5; // ebx
  unsigned int v6; // esi
  int RPCClientSID; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rdi
  const unsigned __int16 *v15; // r8
  const wchar_t *v16; // rdx
  int v17; // eax
  int v18; // r8d
  const wchar_t **v19; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v20; // [rsp+38h] [rbp-40h] BYREF

  v19 = 0;
  v20 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 427, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWDeleteAllMainModeRules");
  if ( (int)result >= 0 )
  {
    v5 = FwLock();
    if ( v5 < 0 )
    {
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllMainModeRules");
      return (unsigned int)v5;
    }
    v6 = 0;
    RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v19);
    v8 = RPCClientSID;
    if ( RPCClientSID < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_36;
      v10 = 428;
LABEL_11:
      v11 = (unsigned int)RPCClientSID;
LABEL_12:
      WPP_SF_d(*(_QWORD *)(v9 + 16), v10, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v11);
LABEL_36:
      FwUnlockInternal(a1, "SvrImpl_FWDeleteAllMainModeRules");
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllMainModeRules");
      if ( (v8 & 0x80000000) == 0 )
        FwChangeSourceSignal();
      v13 = FwHResultToWindowsError(v8);
      v14 = &qword_1800FBFF0;
      v15 = &qword_1800FBFF0;
      if ( v20 )
        v15 = v20;
      if ( v19 )
        v16 = *v19;
      else
        v16 = L"S-1-0-0";
      FwLogBatchUpdate(WFAllMMRulesDeletedEvent0, v16, v15, v6, v13);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        if ( v20 )
          v14 = v20;
        v17 = FwHResultToWindowsError(v8);
        WPP_SF_DSD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 434, v18, v17, (__int64)v14, v6);
      }
      FwFree(v19);
      FwFree(v20);
      return FwHResultToWindowsError(v8);
    }
    FwGetRpcCallersProcessImageName(a1, &v20);
    if ( a2[6] == 2 )
    {
      v6 = a2[4];
      if ( v6 == 2 || v6 == 5 )
      {
        if ( *(_QWORD *)a2 && (RPCClientSID = FwDeleteAllRules(*(_QWORD *)a2, 2), v8 = RPCClientSID, RPCClientSID < 0) )
        {
          v9 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_36;
          v10 = 432;
        }
        else
        {
          RPCClientSID = FwIncrmDeleteAllRules(*((_QWORD *)a2 + 1), (unsigned int)a2[4], 2);
          v8 = RPCClientSID;
          if ( RPCClientSID >= 0 )
          {
            v12 = FwStringTableFind(&dword_1801341D0, 23173);
            FwAuditLogRuleChange((unsigned int)*v19, 0x7FFFFFFF, 2, 1, v12, 0);
            goto LABEL_36;
          }
          v9 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_36;
          v10 = 433;
        }
        goto LABEL_11;
      }
      v8 = -2147024846;
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_36;
      v10 = 431;
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 429);
        v9 = WPP_GLOBAL_Control;
      }
      v8 = -2147024891;
      if ( (_UNKNOWN *)v9 == &WPP_GLOBAL_Control || (*(_BYTE *)(v9 + 28) & 1) == 0 )
        goto LABEL_36;
      v10 = 430;
    }
    v11 = v8;
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x18009e1d8  mov     [rsp+arg_10], rbx
0x18009e1dd  push    rbp
0x18009e1de  push    rsi
0x18009e1df  push    rdi
0x18009e1e0  push    r13
0x18009e1e2  push    r15
0x18009e1e4  sub     rsp, 50h
0x18009e1e8  mov     rax, cs:__security_cookie
0x18009e1ef  xor     rax, rsp
0x18009e1f2  mov     [rsp+78h+var_38], rax
0x18009e1f7  mov     rdi, rdx
0x18009e1fa  mov     [rsp+78h+var_48], 0
0x18009e203  mov     rbp, rcx
0x18009e206  mov     [rsp+78h+var_40], 0
0x18009e20f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e216  lea     r15, WPP_GLOBAL_Control
0x18009e21d  lea     r13, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009e224  cmp     rcx, r15
0x18009e227  jz      short loc_18009E240
0x18009e229  test    byte ptr [rcx+1Ch], 8
0x18009e22d  jz      short loc_18009E240
0x18009e22f  mov     rcx, [rcx+10h]
0x18009e233  mov     edx, 1ABh
0x18009e238  mov     r8, r13
0x18009e23b  call    WPP_SF_
0x18009e240  lea     rcx, aSvrimplFwdelet_4; "SvrImpl_FWDeleteAllMainModeRules"
0x18009e247  call    FwAcquireRPCSharedLock
0x18009e24c  test    eax, eax
0x18009e24e  js      loc_18009E4F3
0x18009e254  call    FwLock
0x18009e259  mov     ebx, eax
0x18009e25b  test    eax, eax
0x18009e25d  jns     short loc_18009E272
0x18009e25f  lea     rcx, aSvrimplFwdelet_4; "SvrImpl_FWDeleteAllMainModeRules"
0x18009e266  call    FwReleaseRPCSharedLock
0x18009e26b  mov     eax, ebx
0x18009e26d  jmp     loc_18009E4F3
0x18009e272  lea     rdx, [rsp+78h+var_48]
0x18009e277  mov     rcx, rbp
0x18009e27a  xor     esi, esi
0x18009e27c  call    ExtractRPCClientSID
0x18009e281  mov     ebx, eax
0x18009e283  test    eax, eax
0x18009e285  jns     short loc_18009E2BA
0x18009e287  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e28e  cmp     rcx, r15
0x18009e291  jz      loc_18009E3FE
0x18009e297  test    byte ptr [rcx+1Ch], 1
0x18009e29b  jz      loc_18009E3FE
0x18009e2a1  mov     edx, 1ACh
0x18009e2a6  mov     r9d, eax
0x18009e2a9  mov     rcx, [rcx+10h]
0x18009e2ad  mov     r8, r13
0x18009e2b0  call    WPP_SF_d
0x18009e2b5  jmp     loc_18009E3FE
0x18009e2ba  lea     rdx, [rsp+78h+var_40]
0x18009e2bf  mov     rcx, rbp
0x18009e2c2  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009e2c9  nop     dword ptr [rax+rax+00h]
0x18009e2ce  mov     r9d, [rdi+18h]
0x18009e2d2  cmp     r9d, 2
0x18009e2d6  jz      short loc_18009E321
0x18009e2d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e2df  cmp     rcx, r15
0x18009e2e2  jz      short loc_18009E2FF
0x18009e2e4  test    byte ptr [rcx+1Ch], 1
0x18009e2e8  jz      short loc_18009E2FF
0x18009e2ea  mov     rcx, [rcx+10h]
0x18009e2ee  mov     edx, 1ADh
0x18009e2f3  call    WPP_SF_l
0x18009e2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e2ff  mov     ebx, 80070005h
0x18009e304  cmp     rcx, r15
0x18009e307  jz      loc_18009E3FE
0x18009e30d  test    byte ptr [rcx+1Ch], 1
0x18009e311  jz      loc_18009E3FE
0x18009e317  mov     edx, 1AEh
0x18009e31c  mov     r9d, ebx
0x18009e31f  jmp     short loc_18009E2A9
0x18009e321  mov     esi, [rdi+10h]
0x18009e324  cmp     esi, 2
0x18009e327  jz      short loc_18009E354
0x18009e329  cmp     esi, 5
0x18009e32c  jz      short loc_18009E354
0x18009e32e  mov     ebx, 80070032h
0x18009e333  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e33a  cmp     rcx, r15
0x18009e33d  jz      loc_18009E3FE
0x18009e343  test    byte ptr [rcx+1Ch], 1
0x18009e347  jz      loc_18009E3FE
0x18009e34d  mov     edx, 1AFh
0x18009e352  jmp     short loc_18009E31C
0x18009e354  mov     rcx, [rdi]
0x18009e357  test    rcx, rcx
0x18009e35a  jz      short loc_18009E38F
0x18009e35c  mov     edx, 2
0x18009e361  call    cs:__imp_FwDeleteAllRules
0x18009e368  nop     dword ptr [rax+rax+00h]
0x18009e36d  mov     ebx, eax
0x18009e36f  test    eax, eax
0x18009e371  jns     short loc_18009E38F
0x18009e373  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e37a  cmp     rcx, r15
0x18009e37d  jz      short loc_18009E3FE
0x18009e37f  test    byte ptr [rcx+1Ch], 1
0x18009e383  jz      short loc_18009E3FE
0x18009e385  mov     edx, 1B0h
0x18009e38a  jmp     loc_18009E2A6
0x18009e38f  mov     edx, [rdi+10h]
0x18009e392  mov     r8d, 2
0x18009e398  mov     rcx, [rdi+8]
0x18009e39c  call    FwIncrmDeleteAllRules
0x18009e3a1  mov     ebx, eax
0x18009e3a3  test    eax, eax
0x18009e3a5  jns     short loc_18009E3C3
0x18009e3a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e3ae  cmp     rcx, r15
0x18009e3b1  jz      short loc_18009E3FE
0x18009e3b3  test    byte ptr [rcx+1Ch], 1
0x18009e3b7  jz      short loc_18009E3FE
0x18009e3b9  mov     edx, 1B1h
0x18009e3be  jmp     loc_18009E2A6
0x18009e3c3  mov     edx, 5A85h
0x18009e3c8  lea     rcx, dword_1801341D0
0x18009e3cf  call    FwStringTableFind
0x18009e3d4  mov     rcx, [rsp+78h+var_48]
0x18009e3d9  mov     r9d, 1
0x18009e3df  mov     [rsp+78h+var_50], 0
0x18009e3e8  mov     edx, 7FFFFFFFh
0x18009e3ed  mov     [rsp+78h+var_58], rax
0x18009e3f2  mov     rcx, [rcx]
0x18009e3f5  lea     r8d, [r9+1]
0x18009e3f9  call    FwAuditLogRuleChange
0x18009e3fe  lea     rdx, aSvrimplFwdelet_4; "SvrImpl_FWDeleteAllMainModeRules"
0x18009e405  mov     rcx, rbp; void *
0x18009e408  call    FwUnlockInternal
0x18009e40d  lea     rcx, aSvrimplFwdelet_4; "SvrImpl_FWDeleteAllMainModeRules"
0x18009e414  call    FwReleaseRPCSharedLock
0x18009e419  test    ebx, ebx
0x18009e41b  js      short loc_18009E429
0x18009e41d  call    cs:__imp_FwChangeSourceSignal
0x18009e424  nop     dword ptr [rax+rax+00h]
0x18009e429  mov     ecx, ebx
0x18009e42b  call    cs:__imp_FwHResultToWindowsError
0x18009e432  nop     dword ptr [rax+rax+00h]
0x18009e437  mov     rcx, [rsp+78h+var_40]
0x18009e43c  lea     rdi, qword_1800FBFF0
0x18009e443  mov     rdx, [rsp+78h+var_48]
0x18009e448  test    rcx, rcx
0x18009e44b  mov     r8, rdi
0x18009e44e  cmovnz  r8, rcx
0x18009e452  test    rdx, rdx
0x18009e455  jz      short loc_18009E45C
0x18009e457  mov     rdx, [rdx]
0x18009e45a  jmp     short loc_18009E463
0x18009e45c  lea     rdx, aS100; "S-1-0-0"
0x18009e463  mov     r9d, esi
0x18009e466  mov     dword ptr [rsp+78h+var_58], eax
0x18009e46a  lea     rcx, WFAllMMRulesDeletedEvent0
0x18009e471  call    ?FwLogBatchUpdate@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGW4_tag_FW_STORE_TYPE@@K@Z; FwLogBatchUpdate(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_STORE_TYPE,ulong)
0x18009e476  mov     rax, cs:WPP_GLOBAL_Control
0x18009e47d  cmp     rax, r15
0x18009e480  jz      short loc_18009E4C3
0x18009e482  test    byte ptr [rax+1Ch], 4
0x18009e486  jz      short loc_18009E4C3
0x18009e488  mov     rax, [rsp+78h+var_40]
0x18009e48d  mov     ecx, ebx
0x18009e48f  test    rax, rax
0x18009e492  cmovnz  rdi, rax
0x18009e496  call    cs:__imp_FwHResultToWindowsError
0x18009e49d  nop     dword ptr [rax+rax+00h]
0x18009e4a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e4a9  mov     edx, 1B2h
0x18009e4ae  mov     dword ptr [rsp+78h+var_50], esi
0x18009e4b2  mov     r9d, eax
0x18009e4b5  mov     [rsp+78h+var_58], rdi
0x18009e4ba  mov     rcx, [rcx+10h]
0x18009e4be  call    WPP_SF_DSD
0x18009e4c3  mov     rcx, [rsp+78h+var_48]
0x18009e4c8  call    cs:__imp_FwFree
0x18009e4cf  nop     dword ptr [rax+rax+00h]
0x18009e4d4  mov     rcx, [rsp+78h+var_40]
0x18009e4d9  call    cs:__imp_FwFree
0x18009e4e0  nop     dword ptr [rax+rax+00h]
0x18009e4e5  mov     ecx, ebx
0x18009e4e7  call    cs:__imp_FwHResultToWindowsError
0x18009e4ee  nop     dword ptr [rax+rax+00h]
0x18009e4f3  mov     rcx, [rsp+78h+var_38]
0x18009e4f8  xor     rcx, rsp; StackCookie
0x18009e4fb  call    __security_check_cookie
0x18009e500  mov     rbx, [rsp+78h+arg_10]
0x18009e508  add     rsp, 50h
0x18009e50c  pop     r15
0x18009e50e  pop     r13
0x18009e510  pop     rdi
0x18009e511  pop     rsi
0x18009e512  pop     rbp
0x18009e513  retn
```
