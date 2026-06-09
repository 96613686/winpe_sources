# SvrImpl_FWDeleteFirewallRule(void *,void *,ushort const *)

- ea: `0x1800314c4`
- end: `0x18003195b`
- name: `?SvrImpl_FWDeleteFirewallRule@@YAKPEAX0PEBG@Z`
- size: `1175`
- prototype: `__int64 __fastcall(void *, struct _tag_FW_STORE **, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002f478`
- `0x180031970`

## callees

- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180017110`
- `0x180025ed0`
- `0x1800314c4`
- `0x18003e798`
- `0x180043234`
- `0x180049928`
- `0x18004c870`
- `0x18005441c`
- `0x180054568`
- `0x18005b0ac`
- `0x18006f520`
- `0x1800a1a18`
- `0x1800a2378`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180031682`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180031719`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180031682`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180031719`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180031764`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180031764`
- `fwbase!FwChangeSourceSignal` at `0x1800317f6`
- `fwbase!FwChangeSourceSignal` at `0x1800317f6`
- `fwbase!FwHResultToWindowsError` at `0x1800317fe`
- `fwbase!FwHResultToWindowsError` at `0x1800318e1`
- `fwbase!FwHResultToWindowsError` at `0x18003192e`
- `fwbase!FwHResultToWindowsError` at `0x1800317fe`
- `fwbase!FwHResultToWindowsError` at `0x1800318e1`
- `fwbase!FwHResultToWindowsError` at `0x18003192e`
- `fwbase!FwReportReturnError` at `0x180031882`
- `fwbase!FwReportReturnError` at `0x180031882`
- `fwbase!FwFree` at `0x180031912`
- `fwbase!FwFree` at `0x18003191c`
- `fwbase!FwFree` at `0x180031926`
- `fwbase!FwFree` at `0x180031912`
- `fwbase!FwFree` at `0x18003191c`
- `fwbase!FwFree` at `0x180031926`
- `FWPolicyIOMgr!FwDeleteRule` at `0x180031652`
- `FWPolicyIOMgr!FwDeleteRule` at `0x180031652`

## string_xrefs

- `0x18003187b`: `FwEventRuleDeleted`
- `0x1800317c4`: `FwTimeToDeleteRuleFeatureEnabled`
- `0x18003154d`: `SvrImpl_FWDeleteFirewallRule`
- `0x18003156c`: `SvrImpl_FWDeleteFirewallRule`
- `0x1800317d7`: `SvrImpl_FWDeleteFirewallRule`
- `0x1800317e6`: `SvrImpl_FWDeleteFirewallRule`

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
  v5 = (struct _tlgProvider_t *)&dword_180126458;
  LODWORD(v30) = 0;
  v34 = 0;
  if ( !dword_180126458 )
    v5 = 0;
  v33 = 0;
  v31 = v5;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 94, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
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
      v15 = qword_18012E050;
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
            WPP_SF_d(*(_QWORD *)(v12 + 16), v13, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v14);
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
              v9 = qword_18012E058;
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
                &m_HistogramThresholdDeleteRule,
                v31);
            FwUnlockInternal(a1, "SvrImpl_FWDeleteFirewallRule");
            FwReleaseRPCSharedLock("SvrImpl_FWDeleteFirewallRule");
            if ( v11 >= 0 )
              FwChangeSourceSignal();
            v21 = &qword_1800F5F90;
            LODWORD(v31) = FwHResultToWindowsError((unsigned int)v11);
            v22 = L"S-1-0-0";
            v23 = (unsigned __int16 *)&qword_1800F5F90;
            LODWORD(v30) = 0;
            if ( v33 )
              v23 = v33;
            v24 = &qword_1800F5F90;
            if ( !a3 )
              a3 = &qword_1800F5F90;
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
                FwEventObjectDeleted(&WFRuleDeleteEvent0, v22, v24, a3, v23, (unsigned int)v31);
            }
            else
            {
              if ( IsEventEnbled > 0 )
                IsEventEnbled = (unsigned __int16)IsEventEnbled | 0x80070000;
              FwReportReturnError("FwEventRuleDeleted", (unsigned int)IsEventEnbled, 2147942400LL);
            }
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              v27 = (unsigned __int16 *)&qword_1800F5F90;
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
0x1800314c4  mov     [rsp-38h+arg_18], rbx
0x1800314c9  push    rbp
0x1800314ca  push    rsi
0x1800314cb  push    rdi
0x1800314cc  push    r12
0x1800314ce  push    r13
0x1800314d0  push    r14
0x1800314d2  push    r15
0x1800314d4  mov     rbp, rsp
0x1800314d7  sub     rsp, 80h
0x1800314de  mov     rax, cs:__security_cookie
0x1800314e5  xor     rax, rsp
0x1800314e8  mov     [rbp+var_10], rax
0x1800314ec  xor     r12d, r12d
0x1800314ef  mov     rbx, rdx
0x1800314f2  mov     rsi, rcx
0x1800314f5  mov     [rbp+var_18], r12
0x1800314f9  mov     ecx, cs:dword_180126458
0x1800314ff  lea     rdx, dword_180126458
0x180031506  test    ecx, ecx
0x180031508  mov     dword ptr [rbp+var_40], r12d
0x18003150c  mov     r14, r8
0x18003150f  mov     [rbp+var_20], r12
0x180031513  cmovz   rdx, r12
0x180031517  mov     [rbp+var_28], r12
0x18003151b  mov     [rbp+var_38], rdx
0x18003151f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031526  lea     r13, WPP_GLOBAL_Control
0x18003152d  cmp     rcx, r13
0x180031530  jz      short loc_18003154D
0x180031532  test    byte ptr [rcx+1Ch], 8
0x180031536  jz      short loc_18003154D
0x180031538  mov     rcx, [rcx+10h]
0x18003153c  lea     edx, [r12+5Eh]
0x180031541  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180031548  call    WPP_SF_
0x18003154d  lea     rcx, aSvrimplFwdelet_7
0x180031554  call    FwAcquireRPCSharedLock
0x180031559  test    eax, eax
0x18003155b  js      loc_180031934
0x180031561  call    FwLock
0x180031566  mov     edi, eax
0x180031568  test    eax, eax
0x18003156a  jns     short loc_18003157F
0x18003156c  lea     rcx, aSvrimplFwdelet_7
0x180031573  call    FwReleaseRPCSharedLock
0x180031578  mov     eax, edi
0x18003157a  jmp     loc_180031934
0x18003157f  mov     r15, r12
0x180031582  test    rsi, rsi
0x180031585  jz      short loc_1800315CD
0x180031587  lea     rdx, [rbp+var_18]
0x18003158b  mov     rcx, rsi
0x18003158e  call    ExtractRPCClientSID
0x180031593  mov     edi, eax
0x180031595  test    eax, eax
0x180031597  jns     short loc_1800315C4
0x180031599  mov     [rbp+var_30], r12
0x18003159d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800315a4  cmp     rcx, r13
0x1800315a7  jz      loc_1800317A8
0x1800315ad  test    byte ptr [rcx+1Ch], 1
0x1800315b1  jz      loc_1800317A8
0x1800315b7  mov     edx, 5Fh ; '_'
0x1800315bc  mov     r9d, eax
0x1800315bf  jmp     loc_180031798
0x1800315c4  mov     rax, [rbp+var_18]
0x1800315c8  mov     r12, [rax]
0x1800315cb  jmp     short loc_1800315D4
0x1800315cd  mov     r12, cs:qword_18012E050
0x1800315d4  mov     r9d, [rbx+18h]
0x1800315d8  mov     [rbp+var_30], r12
0x1800315dc  cmp     r9d, 2
0x1800315e0  jz      short loc_18003162B
0x1800315e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800315e9  cmp     rcx, r13
0x1800315ec  jz      short loc_180031609
0x1800315ee  test    byte ptr [rcx+1Ch], 1
0x1800315f2  jz      short loc_180031609
0x1800315f4  mov     rcx, [rcx+10h]
0x1800315f8  mov     edx, 60h ; '`'
0x1800315fd  call    WPP_SF_l
0x180031602  mov     rcx, cs:WPP_GLOBAL_Control
0x180031609  mov     edi, 80070005h
0x18003160e  cmp     rcx, r13
0x180031611  jz      loc_1800317A8
0x180031617  test    byte ptr [rcx+1Ch], 1
0x18003161b  jz      loc_1800317A8
0x180031621  mov     edx, 61h ; 'a'
0x180031626  jmp     loc_180031795
0x18003162b  mov     eax, [rbx+10h]
0x18003162e  cmp     eax, 0Ch
0x180031631  ja      loc_180031779
0x180031637  mov     ecx, 1F34h
0x18003163c  bt      ecx, eax
0x18003163f  jnb     loc_180031779
0x180031645  mov     rcx, [rbx]
0x180031648  test    rcx, rcx
0x18003164b  jz      short loc_180031682
0x18003164d  mov     r8, r14
0x180031650  xor     edx, edx
0x180031652  call    cs:__imp_FwDeleteRule
0x180031658  mov     edi, eax
0x18003165a  test    eax, eax
0x18003165c  jns     short loc_180031682
0x18003165e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031665  cmp     rcx, r13
0x180031668  jz      loc_1800317A8
0x18003166e  test    byte ptr [rcx+1Ch], 1
0x180031672  jz      loc_1800317A8
0x180031678  mov     edx, 63h ; 'c'
0x18003167d  jmp     loc_1800315BC
0x180031682  call    cs:__imp_GetTickCount64
0x180031688  mov     edx, [rbx+10h]
0x18003168b  mov     r9, r14
0x18003168e  mov     rcx, [rbx+8]; struct _tag_FW_STORE *
0x180031692  mov     r13, rax
0x180031695  lea     rax, [rbp+var_40]
0x180031699  xor     r8d, r8d
0x18003169c  mov     qword ptr [rsp+80h+var_58], rax; __int64
0x1800316a1  lea     rax, [rbp+var_28]
0x1800316a5  mov     [rsp+80h+var_60], rax; unsigned __int16 **
0x1800316aa  call    FwIncrmDeleteRule
0x1800316af  mov     edi, eax
0x1800316b1  test    eax, eax
0x1800316b3  jns     short loc_1800316E0
0x1800316b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800316bc  lea     rax, WPP_GLOBAL_Control
0x1800316c3  cmp     rcx, rax
0x1800316c6  jz      loc_1800317A8
0x1800316cc  test    byte ptr [rcx+1Ch], 1
0x1800316d0  jz      loc_1800317A8
0x1800316d6  mov     edx, 64h ; 'd'
0x1800316db  jmp     loc_180031795
0x1800316e0  mov     ecx, [rbx+10h]
0x1800316e3  mov     rdx, r14
0x1800316e6  call    FwHyperVMgrDeleteHostFirewallRule
0x1800316eb  mov     edi, eax
0x1800316ed  test    eax, eax
0x1800316ef  jns     short loc_180031719
0x1800316f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800316f8  lea     rax, WPP_GLOBAL_Control
0x1800316ff  cmp     rcx, rax
0x180031702  jz      loc_1800317A8
0x180031708  test    byte ptr [rcx+1Ch], 1
0x18003170c  jz      loc_1800317A8
0x180031712  mov     edx, 65h ; 'e'
0x180031717  jmp     short loc_180031795
0x180031719  call    cs:__imp_GetTickCount64
0x18003171f  sub     eax, r13d
0x180031722  lea     rcx, g_timeDeleteRuleHistogram; struct _HISTOGRAM *
0x180031729  mov     edx, eax; unsigned int
0x18003172b  call    ?NetioHistogramLog@@YAXPEAU_HISTOGRAM@@K@Z
0x180031730  mov     rax, [rbp+var_28]
0x180031734  mov     r9d, 1
0x18003173a  mov     edx, dword ptr [rbp+var_40]
0x18003173d  xor     r8d, r8d
0x180031740  inc     cs:?m_DeleteRuleLoggedToHistogramCount@@3KA
0x180031746  mov     rcx, r12
0x180031749  mov     qword ptr [rsp+80h+var_58], rax
0x18003174e  mov     [rsp+80h+var_60], r14
0x180031753  call    FwAuditLogRuleChange
0x180031758  test    rsi, rsi
0x18003175b  jz      short loc_180031770
0x18003175d  lea     rdx, [rbp+var_20]
0x180031761  mov     rcx, rsi
0x180031764  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18003176a  mov     r15, [rbp+var_20]
0x18003176e  jmp     short loc_1800317A8
0x180031770  mov     r15, cs:qword_18012E058
0x180031777  jmp     short loc_1800317A8
0x180031779  mov     edi, 80070032h
0x18003177e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031785  cmp     rcx, r13
0x180031788  jz      short loc_1800317A8
0x18003178a  test    byte ptr [rcx+1Ch], 1
0x18003178e  jz      short loc_1800317A8
0x180031790  mov     edx, 62h ; 'b'
0x180031795  mov     r9d, edi
0x180031798  mov     rcx, [rcx+10h]
0x18003179c  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x1800317a3  call    WPP_SF_d
0x1800317a8  mov     rax, [rbp+var_38]
0x1800317ac  test    rax, rax
0x1800317af  jz      short loc_1800317D7
0x1800317b1  lea     r9, ?m_HistogramThresholdDeleteRule@@3KA; unsigned int *
0x1800317b8  mov     [rsp+80h+var_60], rax; struct _tlgProvider_t *
0x1800317bd  lea     r8, ?m_DeleteRuleLoggedToHistogramCount@@3KA; unsigned int *
0x1800317c4  lea     rdx, aFwtimetodelete
0x1800317cb  lea     rcx, g_timeDeleteRuleHistogram; struct _HISTOGRAM *
0x1800317d2  call    ?FwUploadHistogramIfNotEmpty@@YAXPEAU_HISTOGRAM@@PEADPEAK2PEBU_tlgProvider_t@@@Z
0x1800317d7  lea     rdx, aSvrimplFwdelet_7
0x1800317de  mov     rcx, rsi; void *
0x1800317e1  call    FwUnlockInternal
0x1800317e6  lea     rcx, aSvrimplFwdelet_7
0x1800317ed  call    FwReleaseRPCSharedLock
0x1800317f2  test    edi, edi
0x1800317f4  js      short loc_1800317FC
0x1800317f6  call    cs:__imp_FwChangeSourceSignal
0x1800317fc  mov     ecx, edi
0x1800317fe  call    cs:__imp_FwHResultToWindowsError
0x180031804  mov     rcx, [rbp+var_28]
0x180031808  lea     rsi, qword_1800F5F90
0x18003180f  test    rcx, rcx
0x180031812  mov     dword ptr [rbp+var_38], eax
0x180031815  mov     rax, [rbp+var_30]
0x180031819  lea     r13, aS100
0x180031820  mov     rbx, rsi
0x180031823  mov     dword ptr [rbp+var_40], 0
0x18003182a  cmovnz  rbx, rcx
0x18003182e  lea     rdx, [rbp+var_40]
0x180031832  test    r14, r14
0x180031835  lea     rcx, WFRuleDeleteEvent0
0x18003183c  mov     r12, rsi
0x18003183f  cmovz   r14, rsi
0x180031843  test    r15, r15
0x180031846  cmovnz  r12, r15
0x18003184a  test    rax, rax
0x18003184d  cmovnz  r13, rax
0x180031851  call    FwIsEventEnbled
0x180031856  movzx   edx, ax
0x180031859  mov     r8d, 80070000h
0x18003185f  test    eax, eax
0x180031861  jg      short loc_180031867
0x180031863  mov     ecx, eax
0x180031865  jmp     short loc_18003186C
0x180031867  mov     ecx, edx
0x180031869  or      ecx, r8d
0x18003186c  test    ecx, ecx
0x18003186e  jns     short loc_18003188A
0x180031870  test    eax, eax
0x180031872  jle     short loc_180031879
0x180031874  mov     eax, edx
0x180031876  or      eax, r8d
0x180031879  mov     edx, eax
0x18003187b  lea     rcx, aFweventruledel
0x180031882  call    cs:__imp_FwReportReturnError
0x180031888  jmp     short loc_1800318B1
0x18003188a  cmp     dword ptr [rbp+var_40], 0
0x18003188e  jz      short loc_1800318B1
0x180031890  mov     eax, dword ptr [rbp+var_38]
0x180031893  lea     rcx, WFRuleDeleteEvent0; struct _EVENT_DESCRIPTOR *
0x18003189a  mov     [rsp+80h+var_58], eax; unsigned int
0x18003189e  mov     r9, r14; unsigned __int16 *
0x1800318a1  mov     r8, r12; unsigned __int16 *
0x1800318a4  mov     [rsp+80h+var_60], rbx; unsigned __int16 *
0x1800318a9  mov     rdx, r13; void *
0x1800318ac  call    ?FwEventObjectDeleted@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBG22K@Z
0x1800318b1  mov     rax, cs:WPP_GLOBAL_Control
0x1800318b8  lea     rcx, WPP_GLOBAL_Control
0x1800318bf  cmp     rax, rcx
0x1800318c2  jz      short loc_18003190E
0x1800318c4  test    byte ptr [rax+1Ch], 4
0x1800318c8  jz      short loc_18003190E
0x1800318ca  mov     rax, [rbp+var_28]
0x1800318ce  mov     rbx, rsi
0x1800318d1  test    rax, rax
0x1800318d4  mov     ecx, edi
0x1800318d6  cmovnz  rbx, rax
0x1800318da  test    r15, r15
0x1800318dd  cmovnz  rsi, r15
0x1800318e1  call    cs:__imp_FwHResultToWindowsError
0x1800318e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800318ee  mov     edx, 66h ; 'f'
0x1800318f3  mov     [rsp+80h+var_50], rbx
0x1800318f8  mov     r9d, eax
0x1800318fb  mov     qword ptr [rsp+80h+var_58], r14
0x180031900  mov     [rsp+80h+var_60], rsi
0x180031905  mov     rcx, [rcx+10h]
0x180031909  call    WPP_SF_DSSS
0x18003190e  mov     rcx, [rbp+var_20]
0x180031912  call    cs:__imp_FwFree
0x180031918  mov     rcx, [rbp+var_18]
0x18003191c  call    cs:__imp_FwFree
0x180031922  mov     rcx, [rbp+var_28]
0x180031926  call    cs:__imp_FwFree
0x18003192c  mov     ecx, edi
0x18003192e  call    cs:__imp_FwHResultToWindowsError
0x180031934  mov     rcx, [rbp+var_10]
0x180031938  xor     rcx, rsp; StackCookie
0x18003193b  call    __security_check_cookie
0x180031940  mov     rbx, [rsp+80h+arg_18]
0x180031948  add     rsp, 80h
0x18003194f  pop     r15
0x180031951  pop     r14
0x180031953  pop     r13
0x180031955  pop     r12
0x180031957  pop     rdi
0x180031958  pop     rsi
0x180031959  pop     rbp
0x18003195a  retn
```
