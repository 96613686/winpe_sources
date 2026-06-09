# SvrImpl_FWDeleteAllMainModeRules(void *,void *)

- ea: `0x180099038`
- end: `0x180099344`
- name: `?SvrImpl_FWDeleteAllMainModeRules@@YAKPEAX0@Z`
- size: `780`
- prototype: `unsigned int __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800c0a00`

## callees

- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180017110`
- `0x18003e798`
- `0x18005441c`
- `0x180054a90`
- `0x18005c294`
- `0x18006b5d8`
- `0x18006f520`
- `0x180099038`
- `0x1800a1868`
- `0x1800a2378`

## import_xrefs

- `fwbase!FwGetRpcCallersProcessImageName` at `0x180099122`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180099122`
- `fwbase!FwChangeSourceSignal` at `0x180099271`
- `fwbase!FwChangeSourceSignal` at `0x180099271`
- `fwbase!FwHResultToWindowsError` at `0x180099279`
- `fwbase!FwHResultToWindowsError` at `0x1800992de`
- `fwbase!FwHResultToWindowsError` at `0x18009931d`
- `fwbase!FwHResultToWindowsError` at `0x180099279`
- `fwbase!FwHResultToWindowsError` at `0x1800992de`
- `fwbase!FwHResultToWindowsError` at `0x18009931d`
- `fwbase!FwFree` at `0x18009930a`
- `fwbase!FwFree` at `0x180099315`
- `fwbase!FwFree` at `0x18009930a`
- `fwbase!FwFree` at `0x180099315`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x1800991bb`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x1800991bb`

## string_xrefs

- `0x1800990a0`: `SvrImpl_FWDeleteAllMainModeRules`
- `0x1800990bf`: `SvrImpl_FWDeleteAllMainModeRules`
- `0x180099252`: `SvrImpl_FWDeleteAllMainModeRules`
- `0x180099261`: `SvrImpl_FWDeleteAllMainModeRules`

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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 427, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
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
      WPP_SF_d(*(_QWORD *)(v9 + 16), v10, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v11);
LABEL_36:
      FwUnlockInternal(a1, "SvrImpl_FWDeleteAllMainModeRules");
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllMainModeRules");
      if ( (v8 & 0x80000000) == 0 )
        FwChangeSourceSignal();
      v13 = FwHResultToWindowsError(v8);
      v14 = &qword_1800F5F90;
      v15 = &qword_1800F5F90;
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
            v12 = FwStringTableFind(&dword_18012E020, 23173);
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
0x180099038  mov     [rsp+arg_10], rbx
0x18009903d  push    rbp
0x18009903e  push    rsi
0x18009903f  push    rdi
0x180099040  push    r13
0x180099042  push    r15
0x180099044  sub     rsp, 50h
0x180099048  mov     rax, cs:__security_cookie
0x18009904f  xor     rax, rsp
0x180099052  mov     [rsp+78h+var_38], rax
0x180099057  mov     rdi, rdx
0x18009905a  mov     [rsp+78h+var_48], 0
0x180099063  mov     rbp, rcx
0x180099066  mov     [rsp+78h+var_40], 0
0x18009906f  mov     rcx, cs:WPP_GLOBAL_Control
0x180099076  lea     r15, WPP_GLOBAL_Control
0x18009907d  lea     r13, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180099084  cmp     rcx, r15
0x180099087  jz      short loc_1800990A0
0x180099089  test    byte ptr [rcx+1Ch], 8
0x18009908d  jz      short loc_1800990A0
0x18009908f  mov     rcx, [rcx+10h]
0x180099093  mov     edx, 1ABh
0x180099098  mov     r8, r13
0x18009909b  call    WPP_SF_
0x1800990a0  lea     rcx, aSvrimplFwdelet_4; "SvrImpl_FWDeleteAllMainModeRules"
0x1800990a7  call    FwAcquireRPCSharedLock
0x1800990ac  test    eax, eax
0x1800990ae  js      loc_180099323
0x1800990b4  call    FwLock
0x1800990b9  mov     ebx, eax
0x1800990bb  test    eax, eax
0x1800990bd  jns     short loc_1800990D2
0x1800990bf  lea     rcx, aSvrimplFwdelet_4; "SvrImpl_FWDeleteAllMainModeRules"
0x1800990c6  call    FwReleaseRPCSharedLock
0x1800990cb  mov     eax, ebx
0x1800990cd  jmp     loc_180099323
0x1800990d2  lea     rdx, [rsp+78h+var_48]
0x1800990d7  mov     rcx, rbp
0x1800990da  xor     esi, esi
0x1800990dc  call    ExtractRPCClientSID
0x1800990e1  mov     ebx, eax
0x1800990e3  test    eax, eax
0x1800990e5  jns     short loc_18009911A
0x1800990e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800990ee  cmp     rcx, r15
0x1800990f1  jz      loc_180099252
0x1800990f7  test    byte ptr [rcx+1Ch], 1
0x1800990fb  jz      loc_180099252
0x180099101  mov     edx, 1ACh
0x180099106  mov     r9d, eax
0x180099109  mov     rcx, [rcx+10h]
0x18009910d  mov     r8, r13
0x180099110  call    WPP_SF_d
0x180099115  jmp     loc_180099252
0x18009911a  lea     rdx, [rsp+78h+var_40]
0x18009911f  mov     rcx, rbp
0x180099122  call    cs:__imp_FwGetRpcCallersProcessImageName
0x180099128  mov     r9d, [rdi+18h]
0x18009912c  cmp     r9d, 2
0x180099130  jz      short loc_18009917B
0x180099132  mov     rcx, cs:WPP_GLOBAL_Control
0x180099139  cmp     rcx, r15
0x18009913c  jz      short loc_180099159
0x18009913e  test    byte ptr [rcx+1Ch], 1
0x180099142  jz      short loc_180099159
0x180099144  mov     rcx, [rcx+10h]
0x180099148  mov     edx, 1ADh
0x18009914d  call    WPP_SF_l
0x180099152  mov     rcx, cs:WPP_GLOBAL_Control
0x180099159  mov     ebx, 80070005h
0x18009915e  cmp     rcx, r15
0x180099161  jz      loc_180099252
0x180099167  test    byte ptr [rcx+1Ch], 1
0x18009916b  jz      loc_180099252
0x180099171  mov     edx, 1AEh
0x180099176  mov     r9d, ebx
0x180099179  jmp     short loc_180099109
0x18009917b  mov     esi, [rdi+10h]
0x18009917e  cmp     esi, 2
0x180099181  jz      short loc_1800991AE
0x180099183  cmp     esi, 5
0x180099186  jz      short loc_1800991AE
0x180099188  mov     ebx, 80070032h
0x18009918d  mov     rcx, cs:WPP_GLOBAL_Control
0x180099194  cmp     rcx, r15
0x180099197  jz      loc_180099252
0x18009919d  test    byte ptr [rcx+1Ch], 1
0x1800991a1  jz      loc_180099252
0x1800991a7  mov     edx, 1AFh
0x1800991ac  jmp     short loc_180099176
0x1800991ae  mov     rcx, [rdi]
0x1800991b1  test    rcx, rcx
0x1800991b4  jz      short loc_1800991E3
0x1800991b6  mov     edx, 2
0x1800991bb  call    cs:__imp_FwDeleteAllRules
0x1800991c1  mov     ebx, eax
0x1800991c3  test    eax, eax
0x1800991c5  jns     short loc_1800991E3
0x1800991c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800991ce  cmp     rcx, r15
0x1800991d1  jz      short loc_180099252
0x1800991d3  test    byte ptr [rcx+1Ch], 1
0x1800991d7  jz      short loc_180099252
0x1800991d9  mov     edx, 1B0h
0x1800991de  jmp     loc_180099106
0x1800991e3  mov     edx, [rdi+10h]
0x1800991e6  mov     r8d, 2
0x1800991ec  mov     rcx, [rdi+8]
0x1800991f0  call    FwIncrmDeleteAllRules
0x1800991f5  mov     ebx, eax
0x1800991f7  test    eax, eax
0x1800991f9  jns     short loc_180099217
0x1800991fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180099202  cmp     rcx, r15
0x180099205  jz      short loc_180099252
0x180099207  test    byte ptr [rcx+1Ch], 1
0x18009920b  jz      short loc_180099252
0x18009920d  mov     edx, 1B1h
0x180099212  jmp     loc_180099106
0x180099217  mov     edx, 5A85h
0x18009921c  lea     rcx, dword_18012E020
0x180099223  call    FwStringTableFind
0x180099228  mov     rcx, [rsp+78h+var_48]
0x18009922d  mov     r9d, 1
0x180099233  mov     [rsp+78h+var_50], 0
0x18009923c  mov     edx, 7FFFFFFFh
0x180099241  mov     [rsp+78h+var_58], rax
0x180099246  mov     rcx, [rcx]
0x180099249  lea     r8d, [r9+1]
0x18009924d  call    FwAuditLogRuleChange
0x180099252  lea     rdx, aSvrimplFwdelet_4; "SvrImpl_FWDeleteAllMainModeRules"
0x180099259  mov     rcx, rbp; void *
0x18009925c  call    FwUnlockInternal
0x180099261  lea     rcx, aSvrimplFwdelet_4; "SvrImpl_FWDeleteAllMainModeRules"
0x180099268  call    FwReleaseRPCSharedLock
0x18009926d  test    ebx, ebx
0x18009926f  js      short loc_180099277
0x180099271  call    cs:__imp_FwChangeSourceSignal
0x180099277  mov     ecx, ebx
0x180099279  call    cs:__imp_FwHResultToWindowsError
0x18009927f  mov     rcx, [rsp+78h+var_40]
0x180099284  lea     rdi, qword_1800F5F90
0x18009928b  mov     rdx, [rsp+78h+var_48]
0x180099290  test    rcx, rcx
0x180099293  mov     r8, rdi
0x180099296  cmovnz  r8, rcx
0x18009929a  test    rdx, rdx
0x18009929d  jz      short loc_1800992A4
0x18009929f  mov     rdx, [rdx]
0x1800992a2  jmp     short loc_1800992AB
0x1800992a4  lea     rdx, aS100; "S-1-0-0"
0x1800992ab  mov     r9d, esi
0x1800992ae  mov     dword ptr [rsp+78h+var_58], eax
0x1800992b2  lea     rcx, WFAllMMRulesDeletedEvent0
0x1800992b9  call    ?FwLogBatchUpdate@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGW4_tag_FW_STORE_TYPE@@K@Z; FwLogBatchUpdate(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_STORE_TYPE,ulong)
0x1800992be  mov     rax, cs:WPP_GLOBAL_Control
0x1800992c5  cmp     rax, r15
0x1800992c8  jz      short loc_180099305
0x1800992ca  test    byte ptr [rax+1Ch], 4
0x1800992ce  jz      short loc_180099305
0x1800992d0  mov     rax, [rsp+78h+var_40]
0x1800992d5  mov     ecx, ebx
0x1800992d7  test    rax, rax
0x1800992da  cmovnz  rdi, rax
0x1800992de  call    cs:__imp_FwHResultToWindowsError
0x1800992e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800992eb  mov     edx, 1B2h
0x1800992f0  mov     dword ptr [rsp+78h+var_50], esi
0x1800992f4  mov     r9d, eax
0x1800992f7  mov     [rsp+78h+var_58], rdi
0x1800992fc  mov     rcx, [rcx+10h]
0x180099300  call    WPP_SF_DSD
0x180099305  mov     rcx, [rsp+78h+var_48]
0x18009930a  call    cs:__imp_FwFree
0x180099310  mov     rcx, [rsp+78h+var_40]
0x180099315  call    cs:__imp_FwFree
0x18009931b  mov     ecx, ebx
0x18009931d  call    cs:__imp_FwHResultToWindowsError
0x180099323  mov     rcx, [rsp+78h+var_38]
0x180099328  xor     rcx, rsp; StackCookie
0x18009932b  call    __security_check_cookie
0x180099330  mov     rbx, [rsp+78h+arg_10]
0x180099338  add     rsp, 50h
0x18009933c  pop     r15
0x18009933e  pop     r13
0x180099340  pop     rdi
0x180099341  pop     rsi
0x180099342  pop     rbp
0x180099343  retn
```
