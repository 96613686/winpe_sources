# SvrImpl_FWDeleteFirewallRule(void *,void *,ushort const *)

- ea: `0x1800355c0`
- end: `0x180035aa3`
- name: `?SvrImpl_FWDeleteFirewallRule@@YAKPEAX0PEBG@Z`
- size: `1251`
- prototype: `unsigned int __fastcall(void *, void *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180034660`
- `0x180035ab0`

## callees

- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x1800192e0`
- `0x180028474`
- `0x1800355c0`
- `0x18003ec48`
- `0x18004394c`
- `0x180047d80`
- `0x18004c604`
- `0x18004f864`
- `0x180059714`
- `0x180060168`
- `0x1800729c0`
- `0x1800a71c8`
- `0x1800a7b68`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180035784`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180035824`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180035784`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180035824`
- `fwbase!FwHResultToWindowsError` at `0x18003591b`
- `fwbase!FwHResultToWindowsError` at `0x180035a0a`
- `fwbase!FwHResultToWindowsError` at `0x180035a6f`
- `fwbase!FwHResultToWindowsError` at `0x18003591b`
- `fwbase!FwHResultToWindowsError` at `0x180035a0a`
- `fwbase!FwHResultToWindowsError` at `0x180035a6f`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180035875`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180035875`
- `fwbase!FwChangeSourceSignal` at `0x18003590d`
- `fwbase!FwChangeSourceSignal` at `0x18003590d`
- `fwbase!FwReportReturnError` at `0x1800359a5`
- `fwbase!FwReportReturnError` at `0x1800359a5`
- `fwbase!FwFree` at `0x180035a41`
- `fwbase!FwFree` at `0x180035a51`
- `fwbase!FwFree` at `0x180035a61`
- `fwbase!FwFree` at `0x180035a41`
- `fwbase!FwFree` at `0x180035a51`
- `fwbase!FwFree` at `0x180035a61`
- `FWPolicyIOMgr!FwDeleteRule` at `0x18003574e`
- `FWPolicyIOMgr!FwDeleteRule` at `0x18003574e`

## string_xrefs

- `0x18003599e`: `FwEventRuleDeleted`
- `0x180035649`: `SvrImpl_FWDeleteFirewallRule`
- `0x180035668`: `SvrImpl_FWDeleteFirewallRule`
- `0x1800358ee`: `SvrImpl_FWDeleteFirewallRule`
- `0x1800358fd`: `SvrImpl_FWDeleteFirewallRule`
- `0x1800358db`: `FwTimeToDeleteRuleFeatureEnabled`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWDeleteFirewallRule(void *a1, struct _tag_FW_STORE **a2, const unsigned __int16 *a3)
{
  struct _tlgProvider_t *v5; // rdx
  __int64 result; // rax
  int v8; // edi
  unsigned __int16 *v9; // r15
  int RPCClientSID; // eax
  int v11; // edi
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  void *v15; // r12
  unsigned int v16; // r9d
  unsigned int v17; // eax
  int v18; // ecx
  int TickCount64; // r13d
  int v20; // eax
  const unsigned __int16 *v21; // rsi
  wchar_t *v22; // r13
  unsigned __int16 *v23; // rbx
  const unsigned __int16 *v24; // r12
  signed int IsEventEnbled; // eax
  signed int v26; // ecx
  unsigned __int16 *v27; // rbx
  int v28; // eax
  int v29; // r8d
  __int64 v30; // [rsp+40h] [rbp-40h] BYREF
  struct _tlgProvider_t *v31; // [rsp+48h] [rbp-38h]
  void *v32; // [rsp+50h] [rbp-30h]
  unsigned __int16 *v33; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int16 *v34; // [rsp+60h] [rbp-20h] BYREF
  void **v35; // [rsp+68h] [rbp-18h] BYREF

  v35 = 0;
  v5 = (struct _tlgProvider_t *)&dword_18012C458;
  LODWORD(v30) = 0;
  v34 = 0;
  if ( !dword_18012C458 )
    v5 = 0;
  v33 = 0;
  v31 = v5;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 94, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWDeleteFirewallRule");
  if ( (int)result >= 0 )
  {
    v8 = FwLock();
    if ( v8 < 0 )
    {
      FwReleaseRPCSharedLock("SvrImpl_FWDeleteFirewallRule");
      return (unsigned int)v8;
    }
    v9 = 0;
    if ( a1 )
    {
      RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v35);
      v11 = RPCClientSID;
      if ( RPCClientSID < 0 )
      {
        v32 = 0;
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_47;
        v13 = 95;
        goto LABEL_14;
      }
      v15 = *v35;
    }
    else
    {
      v15 = qword_180134200;
    }
    v16 = *((_DWORD *)a2 + 6);
    v32 = v15;
    if ( v16 == 2 )
    {
      v17 = *((_DWORD *)a2 + 4);
      if ( v17 <= 0xC && (v18 = 7988, _bittest(&v18, v17)) )
      {
        if ( *a2 )
        {
          RPCClientSID = FwDeleteRule(*a2, 0, a3);
          v11 = RPCClientSID;
          if ( RPCClientSID < 0 )
          {
            v12 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_47;
            }
            v13 = 99;
LABEL_14:
            v14 = (unsigned int)RPCClientSID;
LABEL_46:
            WPP_SF_d(*(_QWORD *)(v12 + 16), v13, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v14);
            goto LABEL_47;
          }
        }
        TickCount64 = GetTickCount64();
        v11 = FwIncrmDeleteRule(a2[1], &v33, (__int64)&v30);
        if ( v11 >= 0 )
        {
          v11 = FwHyperVMgrDeleteHostFirewallRule(*((unsigned int *)a2 + 4), a3);
          if ( v11 >= 0 )
          {
            v20 = GetTickCount64();
            NetioHistogramLog((struct _HISTOGRAM *)g_timeDeleteRuleHistogram, v20 - TickCount64);
            ++m_DeleteRuleLoggedToHistogramCount;
            FwAuditLogRuleChange((_DWORD)v15, v30, 0, 1, (__int64)a3, (__int64)v33);
            if ( a1 )
            {
              FwGetRpcCallersProcessImageName(a1, &v34);
              v9 = v34;
            }
            else
            {
              v9 = qword_180134208;
            }
            goto LABEL_47;
          }
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          {
LABEL_47:
            if ( v31 )
              FwUploadHistogramIfNotEmpty(
                (struct _HISTOGRAM *)g_timeDeleteRuleHistogram,
                "FwTimeToDeleteRuleFeatureEnabled",
                &m_DeleteRuleLoggedToHistogramCount,
                m_HistogramThresholdDeleteRule,
                v31);
            FwUnlockInternal(a1, "SvrImpl_FWDeleteFirewallRule");
            FwReleaseRPCSharedLock("SvrImpl_FWDeleteFirewallRule");
            if ( v11 >= 0 )
              FwChangeSourceSignal();
            v21 = &qword_1800FBFF0;
            LODWORD(v31) = FwHResultToWindowsError((unsigned int)v11);
            v22 = L"S-1-0-0";
            v23 = (unsigned __int16 *)&qword_1800FBFF0;
            LODWORD(v30) = 0;
            if ( v33 )
              v23 = v33;
            v24 = &qword_1800FBFF0;
            if ( !a3 )
              a3 = &qword_1800FBFF0;
            if ( v9 )
              v24 = v9;
            if ( v32 )
              v22 = (wchar_t *)v32;
            IsEventEnbled = FwIsEventEnbled(&WFRuleDeleteEvent0, &v30);
            if ( IsEventEnbled > 0 )
              v26 = (unsigned __int16)IsEventEnbled | 0x80070000;
            else
              v26 = IsEventEnbled;
            if ( v26 >= 0 )
            {
              if ( (_DWORD)v30 )
                FwEventObjectDeleted(&WFRuleDeleteEvent0, v22, v24, a3, v23, (char)v31);
            }
            else
            {
              if ( IsEventEnbled > 0 )
                IsEventEnbled = (unsigned __int16)IsEventEnbled | 0x80070000;
              FwReportReturnError("FwEventRuleDeleted", (unsigned int)IsEventEnbled);
            }
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              v27 = (unsigned __int16 *)&qword_1800FBFF0;
              if ( v33 )
                v27 = v33;
              if ( v9 )
                v21 = v9;
              v28 = FwHResultToWindowsError((unsigned int)v11);
              WPP_SF_DSSS(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                102,
                v29,
                v28,
                (__int64)v21,
                (__int64)a3,
                (__int64)v27);
            }
            FwFree(v34);
            FwFree(v35);
            FwFree(v33);
            return FwHResultToWindowsError((unsigned int)v11);
          }
          v13 = 101;
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_47;
          v13 = 100;
        }
      }
      else
      {
        v11 = -2147024846;
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_47;
        v13 = 98;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 96);
        v12 = WPP_GLOBAL_Control;
      }
      v11 = -2147024891;
      if ( (_UNKNOWN *)v12 == &WPP_GLOBAL_Control || (*(_BYTE *)(v12 + 28) & 1) == 0 )
        goto LABEL_47;
      v13 = 97;
    }
    v14 = (unsigned int)v11;
    goto LABEL_46;
  }
  return result;
}

```

## disassembly

```asm
0x1800355c0  mov     [rsp-38h+arg_18], rbx
0x1800355c5  push    rbp
0x1800355c6  push    rsi
0x1800355c7  push    rdi
0x1800355c8  push    r12
0x1800355ca  push    r13
0x1800355cc  push    r14
0x1800355ce  push    r15
0x1800355d0  mov     rbp, rsp
0x1800355d3  sub     rsp, 80h
0x1800355da  mov     rax, cs:__security_cookie
0x1800355e1  xor     rax, rsp
0x1800355e4  mov     [rbp+var_10], rax
0x1800355e8  xor     r12d, r12d
0x1800355eb  mov     rbx, rdx
0x1800355ee  mov     rsi, rcx
0x1800355f1  mov     [rbp+var_18], r12
0x1800355f5  mov     ecx, cs:dword_18012C458
0x1800355fb  lea     rdx, dword_18012C458
0x180035602  test    ecx, ecx
0x180035604  mov     dword ptr [rbp+var_40], r12d
0x180035608  mov     r14, r8
0x18003560b  mov     [rbp+var_20], r12
0x18003560f  cmovz   rdx, r12
0x180035613  mov     [rbp+var_28], r12
0x180035617  mov     [rbp+var_38], rdx
0x18003561b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035622  lea     r13, WPP_GLOBAL_Control
0x180035629  cmp     rcx, r13
0x18003562c  jz      short loc_180035649
0x18003562e  test    byte ptr [rcx+1Ch], 8
0x180035632  jz      short loc_180035649
0x180035634  mov     rcx, [rcx+10h]
0x180035638  lea     edx, [r12+5Eh]
0x18003563d  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180035644  call    WPP_SF_
0x180035649  lea     rcx, aSvrimplFwdelet_7
0x180035650  call    FwAcquireRPCSharedLock
0x180035655  test    eax, eax
0x180035657  js      loc_180035A7B
0x18003565d  call    FwLock
0x180035662  mov     edi, eax
0x180035664  test    eax, eax
0x180035666  jns     short loc_18003567B
0x180035668  lea     rcx, aSvrimplFwdelet_7
0x18003566f  call    FwReleaseRPCSharedLock
0x180035674  mov     eax, edi
0x180035676  jmp     loc_180035A7B
0x18003567b  mov     r15, r12
0x18003567e  test    rsi, rsi
0x180035681  jz      short loc_1800356C9
0x180035683  lea     rdx, [rbp+var_18]
0x180035687  mov     rcx, rsi
0x18003568a  call    ExtractRPCClientSID
0x18003568f  mov     edi, eax
0x180035691  test    eax, eax
0x180035693  jns     short loc_1800356C0
0x180035695  mov     [rbp+var_30], r12
0x180035699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800356a0  cmp     rcx, r13
0x1800356a3  jz      loc_1800358BF
0x1800356a9  test    byte ptr [rcx+1Ch], 1
0x1800356ad  jz      loc_1800358BF
0x1800356b3  mov     edx, 5Fh ; '_'
0x1800356b8  mov     r9d, eax
0x1800356bb  jmp     loc_1800358AF
0x1800356c0  mov     rax, [rbp+var_18]
0x1800356c4  mov     r12, [rax]
0x1800356c7  jmp     short loc_1800356D0
0x1800356c9  mov     r12, cs:qword_180134200
0x1800356d0  mov     r9d, [rbx+18h]
0x1800356d4  mov     [rbp+var_30], r12
0x1800356d8  cmp     r9d, 2
0x1800356dc  jz      short loc_180035727
0x1800356de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800356e5  cmp     rcx, r13
0x1800356e8  jz      short loc_180035705
0x1800356ea  test    byte ptr [rcx+1Ch], 1
0x1800356ee  jz      short loc_180035705
0x1800356f0  mov     rcx, [rcx+10h]
0x1800356f4  mov     edx, 60h ; '`'
0x1800356f9  call    WPP_SF_l
0x1800356fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180035705  mov     edi, 80070005h
0x18003570a  cmp     rcx, r13
0x18003570d  jz      loc_1800358BF
0x180035713  test    byte ptr [rcx+1Ch], 1
0x180035717  jz      loc_1800358BF
0x18003571d  mov     edx, 61h ; 'a'
0x180035722  jmp     loc_1800358AC
0x180035727  mov     eax, [rbx+10h]
0x18003572a  cmp     eax, 0Ch
0x18003572d  ja      loc_180035890
0x180035733  mov     ecx, 1F34h
0x180035738  bt      ecx, eax
0x18003573b  jnb     loc_180035890
0x180035741  mov     rcx, [rbx]
0x180035744  test    rcx, rcx
0x180035747  jz      short loc_180035784
0x180035749  mov     r8, r14
0x18003574c  xor     edx, edx
0x18003574e  call    cs:__imp_FwDeleteRule
0x180035755  nop     dword ptr [rax+rax+00h]
0x18003575a  mov     edi, eax
0x18003575c  test    eax, eax
0x18003575e  jns     short loc_180035784
0x180035760  mov     rcx, cs:WPP_GLOBAL_Control
0x180035767  cmp     rcx, r13
0x18003576a  jz      loc_1800358BF
0x180035770  test    byte ptr [rcx+1Ch], 1
0x180035774  jz      loc_1800358BF
0x18003577a  mov     edx, 63h ; 'c'
0x18003577f  jmp     loc_1800356B8
0x180035784  call    cs:__imp_GetTickCount64
0x18003578b  nop     dword ptr [rax+rax+00h]
0x180035790  mov     edx, [rbx+10h]
0x180035793  mov     r9, r14
0x180035796  mov     rcx, [rbx+8]; struct _tag_FW_STORE *
0x18003579a  mov     r13, rax
0x18003579d  lea     rax, [rbp+var_40]
0x1800357a1  xor     r8d, r8d
0x1800357a4  mov     qword ptr [rsp+80h+var_58], rax; __int64
0x1800357a9  lea     rax, [rbp+var_28]
0x1800357ad  mov     [rsp+80h+var_60], rax; unsigned __int16 **
0x1800357b2  call    FwIncrmDeleteRule
0x1800357b7  mov     edi, eax
0x1800357b9  test    eax, eax
0x1800357bb  jns     short loc_1800357E8
0x1800357bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800357c4  lea     rax, WPP_GLOBAL_Control
0x1800357cb  cmp     rcx, rax
0x1800357ce  jz      loc_1800358BF
0x1800357d4  test    byte ptr [rcx+1Ch], 1
0x1800357d8  jz      loc_1800358BF
0x1800357de  mov     edx, 64h ; 'd'
0x1800357e3  jmp     loc_1800358AC
0x1800357e8  mov     ecx, [rbx+10h]
0x1800357eb  mov     rdx, r14
0x1800357ee  call    FwHyperVMgrDeleteHostFirewallRule
0x1800357f3  mov     edi, eax
0x1800357f5  test    eax, eax
0x1800357f7  jns     short loc_180035824
0x1800357f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180035800  lea     rax, WPP_GLOBAL_Control
0x180035807  cmp     rcx, rax
0x18003580a  jz      loc_1800358BF
0x180035810  test    byte ptr [rcx+1Ch], 1
0x180035814  jz      loc_1800358BF
0x18003581a  mov     edx, 65h ; 'e'
0x18003581f  jmp     loc_1800358AC
0x180035824  call    cs:__imp_GetTickCount64
0x18003582b  nop     dword ptr [rax+rax+00h]
0x180035830  sub     eax, r13d
0x180035833  lea     rcx, g_timeDeleteRuleHistogram; struct _HISTOGRAM *
0x18003583a  mov     edx, eax; unsigned int
0x18003583c  call    ?NetioHistogramLog@@YAXPEAU_HISTOGRAM@@K@Z
0x180035841  mov     rax, [rbp+var_28]
0x180035845  mov     r9d, 1
0x18003584b  mov     edx, dword ptr [rbp+var_40]
0x18003584e  xor     r8d, r8d
0x180035851  inc     cs:?m_DeleteRuleLoggedToHistogramCount@@3KA
0x180035857  mov     rcx, r12
0x18003585a  mov     qword ptr [rsp+80h+var_58], rax
0x18003585f  mov     [rsp+80h+var_60], r14
0x180035864  call    FwAuditLogRuleChange
0x180035869  test    rsi, rsi
0x18003586c  jz      short loc_180035887
0x18003586e  lea     rdx, [rbp+var_20]
0x180035872  mov     rcx, rsi
0x180035875  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18003587c  nop     dword ptr [rax+rax+00h]
0x180035881  mov     r15, [rbp+var_20]
0x180035885  jmp     short loc_1800358BF
0x180035887  mov     r15, cs:qword_180134208
0x18003588e  jmp     short loc_1800358BF
0x180035890  mov     edi, 80070032h
0x180035895  mov     rcx, cs:WPP_GLOBAL_Control
0x18003589c  cmp     rcx, r13
0x18003589f  jz      short loc_1800358BF
0x1800358a1  test    byte ptr [rcx+1Ch], 1
0x1800358a5  jz      short loc_1800358BF
0x1800358a7  mov     edx, 62h ; 'b'
0x1800358ac  mov     r9d, edi
0x1800358af  mov     rcx, [rcx+10h]
0x1800358b3  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800358ba  call    WPP_SF_d
0x1800358bf  mov     rax, [rbp+var_38]
0x1800358c3  test    rax, rax
0x1800358c6  jz      short loc_1800358EE
0x1800358c8  lea     r9, ?m_HistogramThresholdDeleteRule@@3KA
0x1800358cf  mov     [rsp+80h+var_60], rax; struct _tlgProvider_t *
0x1800358d4  lea     r8, ?m_DeleteRuleLoggedToHistogramCount@@3KA; unsigned int *
0x1800358db  lea     rdx, aFwtimetodelete
0x1800358e2  lea     rcx, g_timeDeleteRuleHistogram; struct _HISTOGRAM *
0x1800358e9  call    ?FwUploadHistogramIfNotEmpty@@YAXPEAU_HISTOGRAM@@PEADPEAK2PEBU_tlgProvider_t@@@Z
0x1800358ee  lea     rdx, aSvrimplFwdelet_7
0x1800358f5  mov     rcx, rsi; void *
0x1800358f8  call    FwUnlockInternal
0x1800358fd  lea     rcx, aSvrimplFwdelet_7
0x180035904  call    FwReleaseRPCSharedLock
0x180035909  test    edi, edi
0x18003590b  js      short loc_180035919
0x18003590d  call    cs:__imp_FwChangeSourceSignal
0x180035914  nop     dword ptr [rax+rax+00h]
0x180035919  mov     ecx, edi
0x18003591b  call    cs:__imp_FwHResultToWindowsError
0x180035922  nop     dword ptr [rax+rax+00h]
0x180035927  mov     rcx, [rbp+var_28]
0x18003592b  lea     rsi, qword_1800FBFF0
0x180035932  test    rcx, rcx
0x180035935  mov     dword ptr [rbp+var_38], eax
0x180035938  mov     rax, [rbp+var_30]
0x18003593c  lea     r13, aS100
0x180035943  mov     rbx, rsi
0x180035946  mov     dword ptr [rbp+var_40], 0
0x18003594d  cmovnz  rbx, rcx
0x180035951  lea     rdx, [rbp+var_40]
0x180035955  test    r14, r14
0x180035958  lea     rcx, WFRuleDeleteEvent0
0x18003595f  mov     r12, rsi
0x180035962  cmovz   r14, rsi
0x180035966  test    r15, r15
0x180035969  cmovnz  r12, r15
0x18003596d  test    rax, rax
0x180035970  cmovnz  r13, rax
0x180035974  call    FwIsEventEnbled
0x180035979  movzx   edx, ax
0x18003597c  mov     r8d, 80070000h
0x180035982  test    eax, eax
0x180035984  jg      short loc_18003598A
0x180035986  mov     ecx, eax
0x180035988  jmp     short loc_18003598F
0x18003598a  mov     ecx, edx
0x18003598c  or      ecx, r8d
0x18003598f  test    ecx, ecx
0x180035991  jns     short loc_1800359B3
0x180035993  test    eax, eax
0x180035995  jle     short loc_18003599C
0x180035997  mov     eax, edx
0x180035999  or      eax, r8d
0x18003599c  mov     edx, eax
0x18003599e  lea     rcx, aFweventruledel
0x1800359a5  call    cs:__imp_FwReportReturnError
0x1800359ac  nop     dword ptr [rax+rax+00h]
0x1800359b1  jmp     short loc_1800359DA
0x1800359b3  cmp     dword ptr [rbp+var_40], 0
0x1800359b7  jz      short loc_1800359DA
0x1800359b9  mov     eax, dword ptr [rbp+var_38]
0x1800359bc  lea     rcx, WFRuleDeleteEvent0; struct _EVENT_DESCRIPTOR *
0x1800359c3  mov     dword ptr [rsp+80h+var_58], eax; char
0x1800359c7  mov     r9, r14; unsigned __int16 *
0x1800359ca  mov     r8, r12; unsigned __int16 *
0x1800359cd  mov     [rsp+80h+var_60], rbx; unsigned __int16 *
0x1800359d2  mov     rdx, r13; void *
0x1800359d5  call    ?FwEventObjectDeleted@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBG22K@Z
0x1800359da  mov     rax, cs:WPP_GLOBAL_Control
0x1800359e1  lea     rcx, WPP_GLOBAL_Control
0x1800359e8  cmp     rax, rcx
0x1800359eb  jz      short loc_180035A3D
0x1800359ed  test    byte ptr [rax+1Ch], 4
0x1800359f1  jz      short loc_180035A3D
0x1800359f3  mov     rax, [rbp+var_28]
0x1800359f7  mov     rbx, rsi
0x1800359fa  test    rax, rax
0x1800359fd  mov     ecx, edi
0x1800359ff  cmovnz  rbx, rax
0x180035a03  test    r15, r15
0x180035a06  cmovnz  rsi, r15
0x180035a0a  call    cs:__imp_FwHResultToWindowsError
0x180035a11  nop     dword ptr [rax+rax+00h]
0x180035a16  mov     rcx, cs:WPP_GLOBAL_Control
0x180035a1d  mov     edx, 66h ; 'f'
0x180035a22  mov     [rsp+80h+var_50], rbx
0x180035a27  mov     r9d, eax
0x180035a2a  mov     qword ptr [rsp+80h+var_58], r14
0x180035a2f  mov     [rsp+80h+var_60], rsi
0x180035a34  mov     rcx, [rcx+10h]
0x180035a38  call    WPP_SF_DSSS
0x180035a3d  mov     rcx, [rbp+var_20]
0x180035a41  call    cs:__imp_FwFree
0x180035a48  nop     dword ptr [rax+rax+00h]
0x180035a4d  mov     rcx, [rbp+var_18]
0x180035a51  call    cs:__imp_FwFree
0x180035a58  nop     dword ptr [rax+rax+00h]
0x180035a5d  mov     rcx, [rbp+var_28]
0x180035a61  call    cs:__imp_FwFree
0x180035a68  nop     dword ptr [rax+rax+00h]
0x180035a6d  mov     ecx, edi
0x180035a6f  call    cs:__imp_FwHResultToWindowsError
0x180035a76  nop     dword ptr [rax+rax+00h]
0x180035a7b  mov     rcx, [rbp+var_10]
0x180035a7f  xor     rcx, rsp; StackCookie
0x180035a82  call    __security_check_cookie
0x180035a87  mov     rbx, [rsp+80h+arg_18]
0x180035a8f  add     rsp, 80h
0x180035a96  pop     r15
0x180035a98  pop     r14
0x180035a9a  pop     r13
0x180035a9c  pop     r12
0x180035a9e  pop     rdi
  ... truncated ...
```
