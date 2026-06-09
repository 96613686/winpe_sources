# SvrImpl_FWRestoreDefaults(void *)

- ea: `0x1800a2578`
- end: `0x1800a2cd3`
- name: `?SvrImpl_FWRestoreDefaults@@YAKPEAX@Z`
- size: `1883`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x1800cacf0`

## callees

- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x1800192e0`
- `0x180036b64`
- `0x180059714`
- `0x18005e408`
- `0x1800729c0`
- `0x18007f048`
- `0x180089090`
- `0x18008bc14`
- `0x180091c9c`
- `0x1800999a4`
- `0x1800a2578`
- `0x1800a6f5c`

## import_xrefs

- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x1800a2645`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x1800a2645`
- `fwbase!FwHResultToWindowsError` at `0x1800a2bb2`
- `fwbase!FwHResultToWindowsError` at `0x1800a2c0f`
- `fwbase!FwHResultToWindowsError` at `0x1800a2ca9`
- `fwbase!FwHResultToWindowsError` at `0x1800a2bb2`
- `fwbase!FwHResultToWindowsError` at `0x1800a2c0f`
- `fwbase!FwHResultToWindowsError` at `0x1800a2ca9`
- `fwbase!FwRegDeleteAllValues` at `0x1800a2ae5`
- `fwbase!FwRegDeleteAllValues` at `0x1800a2ae5`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x1800a26fd`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x1800a26fd`
- `fwbase!FwRegOpenKey` at `0x1800a272a`
- `fwbase!FwRegOpenKey` at `0x1800a27b1`
- `fwbase!FwRegOpenKey` at `0x1800a272a`
- `fwbase!FwRegOpenKey` at `0x1800a27b1`
- `fwbase!FwRegCloseKey` at `0x1800a2c5c`
- `fwbase!FwRegCloseKey` at `0x1800a2c6c`
- `fwbase!FwRegCloseKey` at `0x1800a2c7a`
- `fwbase!FwRegCloseKey` at `0x1800a2c5c`
- `fwbase!FwRegCloseKey` at `0x1800a2c6c`
- `fwbase!FwRegCloseKey` at `0x1800a2c7a`
- `fwbase!FwChangeSourceSignal` at `0x1800a2ba4`
- `fwbase!FwChangeSourceSignal` at `0x1800a2ba4`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800a29b5`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800a29b5`
- `fwbase!FwFree` at `0x1800a2c3c`
- `fwbase!FwFree` at `0x1800a2c4c`
- `fwbase!FwFree` at `0x1800a2c3c`
- `fwbase!FwFree` at `0x1800a2c4c`
- `FWPolicyIOMgr!FwSetConfig` at `0x1800a29d2`
- `FWPolicyIOMgr!FwSetConfig` at `0x1800a29d2`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x1800a2876`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x1800a28b3`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x1800a28ef`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x1800a2876`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x1800a28b3`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x1800a28ef`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x1800a292e`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x1800a296d`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x1800a2a46`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x1800a2a86`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x1800a292e`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x1800a296d`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x1800a2a46`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x1800a2a86`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x1800a2ac0`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x1800a2c8f`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x1800a2ac0`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x1800a2c8f`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x1800a2825`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x1800a2825`

## string_xrefs

- `0x1800a271c`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x1800a27a3`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Defaults\FirewallPolicy`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWRestoreDefaults(void *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax
  int v4; // ebx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // eax
  unsigned int v10; // esi
  unsigned int i; // edi
  unsigned int ProfileTypeFromProfileIndex; // eax
  int v13; // eax
  unsigned __int16 *v14; // rdi
  unsigned __int16 *v15; // rdx
  wchar_t *v16; // rcx
  int v17; // eax
  int v18; // r8d
  __int64 v19; // [rsp+30h] [rbp-48h] BYREF
  void **v20; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int16 *v21; // [rsp+40h] [rbp-38h] BYREF
  __int64 v22; // [rsp+48h] [rbp-30h] BYREF
  HKEY v23; // [rsp+50h] [rbp-28h] BYREF
  BOOLEAN pfEnabled[4]; // [rsp+58h] [rbp-20h] BYREF
  int v25; // [rsp+5Ch] [rbp-1Ch] BYREF

  v22 = 0;
  v23 = 0;
  v25 = 0;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 52, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 8) != 0 )
      WPP_SF_(*(_QWORD *)(v2 + 16), 53, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
  }
  result = FwAcquireRPCSharedLock("SvrImpl_FWRestoreDefaults");
  if ( (int)result >= 0 )
  {
    v4 = FwLock();
    if ( v4 < 0 )
    {
      FwReleaseRPCSharedLock("SvrImpl_FWRestoreDefaults");
      return (unsigned int)v4;
    }
    pfEnabled[0] = 0;
    if ( BCryptGetFipsAlgorithmMode(pfEnabled) >= 0
      && pfEnabled[0]
      && (int)FwRpcAPIsSecModeAccessCheckForClient(2, 2, a1) >= 0
      && (unsigned int)FwAnyNonDefaultSetsAreInUse(qword_180134C08, 1, 2) )
    {
      v5 = -2147022494;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_97;
      v7 = 54;
      v8 = 2147944802LL;
      goto LABEL_17;
    }
    v9 = ExtractRPCClientSID(a1, &v20);
    v5 = v9;
    if ( v9 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_97;
      v7 = 55;
      goto LABEL_22;
    }
    FwGetRpcCallersProcessImageName(a1, &v21);
    v9 = FwRegOpenKey(
           -2147483646,
           L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
           131103,
           &v22,
           &v25);
    v5 = v9;
    if ( v9 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_97;
      v7 = 56;
      goto LABEL_22;
    }
    if ( !v25 )
    {
      v8 = 2147942403LL;
      v5 = -2147024893;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_97;
      v7 = 57;
      goto LABEL_17;
    }
    v9 = FwRegOpenKey(
           -2147483646,
           L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Defaults\\FirewallPolicy",
           131097,
           &v23,
           &v25);
    v5 = v9;
    if ( v9 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_97;
      v7 = 58;
      goto LABEL_22;
    }
    if ( !v25 )
    {
      v8 = 2147942403LL;
      v5 = -2147024893;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_97;
      v7 = 59;
      goto LABEL_17;
    }
    v9 = FwOpenPolicyStore(2, 2, 0, &v19);
    v5 = v9;
    if ( v9 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_97;
      v7 = 60;
      goto LABEL_22;
    }
    if ( (int)FwRpcAPIsSecModeAccessCheckForClient(1, 2, a1) >= 0 )
    {
      v9 = FwDeleteAllRules(v19, 0);
      v5 = v9;
      if ( v9 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 61;
        goto LABEL_22;
      }
      v9 = FwDeleteAllRules(v19, 1);
      v5 = v9;
      if ( v9 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 62;
        goto LABEL_22;
      }
      v9 = FwDeleteAllRules(v19, 2);
      v5 = v9;
      if ( v9 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 63;
        goto LABEL_22;
      }
      v9 = FwDeleteAllSets(v19, 0, 1);
      v5 = v9;
      if ( v9 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 64;
        goto LABEL_22;
      }
      v9 = FwDeleteAllSets(v19, 0, 2);
      v5 = v9;
      if ( v9 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 65;
        goto LABEL_22;
      }
      v10 = 0;
LABEL_65:
      if ( v10 < 3 )
      {
        for ( i = 1; ; ++i )
        {
          if ( i >= 0x13 )
          {
            ++v10;
            goto LABEL_65;
          }
          ProfileTypeFromProfileIndex = FwGetProfileTypeFromProfileIndex(v10);
          v13 = FwSetConfig(v19, i, ProfileTypeFromProfileIndex, 0, 0);
          v5 = v13;
          if ( v13 < 0 )
            break;
        }
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 66;
        v8 = (unsigned int)v13;
        goto LABEL_17;
      }
    }
    if ( (int)FwRpcAPIsSecModeAccessCheckForClient(2, 2, a1) >= 0 )
    {
      v9 = FwDeleteAllSets(v19, 1, 1);
      v5 = v9;
      if ( v9 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 67;
        goto LABEL_22;
      }
      v9 = FwDeleteAllSets(v19, 1, 2);
      v5 = v9;
      if ( v9 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 68;
LABEL_22:
        v8 = (unsigned int)v9;
LABEL_17:
        WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v8);
LABEL_97:
        FwUnlockInternal(a1, "SvrImpl_FWRestoreDefaults");
        if ( (v5 & 0x80000000) == 0 )
          FwChangeSourceSignal();
        FwHResultToWindowsError(v5);
        v14 = (unsigned __int16 *)&qword_1800FBFF0;
        v15 = (unsigned __int16 *)&qword_1800FBFF0;
        if ( v21 )
          v15 = v21;
        if ( v20 )
          v16 = (wchar_t *)*v20;
        else
          v16 = L"S-1-0-0";
        FwEventRestoreDefaults(v16, v15);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          if ( v21 )
            v14 = v21;
          v17 = FwHResultToWindowsError(v5);
          WPP_SF_DS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 72, v18, v17, (__int64)v14);
        }
        FwFree(v20);
        FwFree(v21);
        FwRegCloseKey(v22);
        FwRegCloseKey(v23);
        FwRegCloseKey(0);
        if ( v19 )
          FwClosePolicyStore(v19);
        FwReleaseRPCSharedLock("SvrImpl_FWRestoreDefaults");
        return FwHResultToWindowsError(v5);
      }
    }
    FwClosePolicyStore(v19);
    v19 = 0;
    if ( (int)FwRpcAPIsSecModeAccessCheckForClient(1, 2, a1) < 0 || (v9 = FwRegDeleteAllValues(v22), v5 = v9, v9 >= 0) )
    {
      v9 = FwCopyDefaultsToLocalStorePerUserRights(a1, v23);
      v5 = v9;
      if ( v9 >= 0 )
      {
        v9 = FwProfileMgrOnPolicyChange(0, 1, 0, 0, 1);
        v5 = v9;
        if ( v9 >= 0 )
        {
          FwAuditLogRestoreDefaults(*v20);
          FwUpdateConsecPresenceDataPoint();
          goto LABEL_97;
        }
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 71;
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 70;
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_97;
      v7 = 69;
    }
    goto LABEL_22;
  }
  return result;
}

```

## disassembly

```asm
0x1800a2578  push    rbp
0x1800a257a  push    rbx
0x1800a257b  push    rsi
0x1800a257c  push    rdi
0x1800a257d  push    r12
0x1800a257f  push    r13
0x1800a2581  push    r14
0x1800a2583  push    r15
0x1800a2585  mov     rbp, rsp
0x1800a2588  sub     rsp, 78h
0x1800a258c  mov     rax, cs:__security_cookie
0x1800a2593  xor     rax, rsp
0x1800a2596  mov     [rbp+var_18], rax
0x1800a259a  xor     r15d, r15d
0x1800a259d  mov     r14, rcx
0x1800a25a0  mov     [rbp+var_30], r15
0x1800a25a4  mov     [rbp+var_28], r15
0x1800a25a8  mov     [rbp+var_1C], r15d
0x1800a25ac  mov     [rbp+var_40], r15
0x1800a25b0  mov     [rbp+var_48], r15
0x1800a25b4  mov     [rbp+var_38], r15
0x1800a25b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a25bf  lea     r13, WPP_GLOBAL_Control
0x1800a25c6  lea     rdi, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a25cd  cmp     rcx, r13
0x1800a25d0  jz      short loc_1800A260B
0x1800a25d2  test    byte ptr [rcx+1Ch], 8
0x1800a25d6  jz      short loc_1800A25EF
0x1800a25d8  mov     rcx, [rcx+10h]
0x1800a25dc  lea     edx, [r15+34h]
0x1800a25e0  mov     r8, rdi
0x1800a25e3  call    WPP_SF_
0x1800a25e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a25ef  cmp     rcx, r13
0x1800a25f2  jz      short loc_1800A260B
0x1800a25f4  test    byte ptr [rcx+1Ch], 8
0x1800a25f8  jz      short loc_1800A260B
0x1800a25fa  mov     rcx, [rcx+10h]
0x1800a25fe  mov     edx, 35h ; '5'
0x1800a2603  mov     r8, rdi
0x1800a2606  call    WPP_SF_
0x1800a260b  lea     rcx, aSvrimplFwresto; "SvrImpl_FWRestoreDefaults"
0x1800a2612  call    FwAcquireRPCSharedLock
0x1800a2617  test    eax, eax
0x1800a2619  js      loc_1800A2CB5
0x1800a261f  call    FwLock
0x1800a2624  mov     ebx, eax
0x1800a2626  test    eax, eax
0x1800a2628  jns     short loc_1800A263D
0x1800a262a  lea     rcx, aSvrimplFwresto; "SvrImpl_FWRestoreDefaults"
0x1800a2631  call    FwReleaseRPCSharedLock
0x1800a2636  mov     eax, ebx
0x1800a2638  jmp     loc_1800A2CB5
0x1800a263d  lea     rcx, [rbp+pfEnabled]; pfEnabled
0x1800a2641  mov     [rbp+pfEnabled], r15b
0x1800a2645  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x1800a264c  nop     dword ptr [rax+rax+00h]
0x1800a2651  mov     esi, 2
0x1800a2656  lea     r12d, [rsi-1]
0x1800a265a  test    eax, eax
0x1800a265c  js      short loc_1800A26C0
0x1800a265e  cmp     [rbp+pfEnabled], r15b
0x1800a2662  jz      short loc_1800A26C0
0x1800a2664  mov     r8, r14
0x1800a2667  mov     edx, esi
0x1800a2669  mov     ecx, esi
0x1800a266b  call    FwRpcAPIsSecModeAccessCheckForClient
0x1800a2670  test    eax, eax
0x1800a2672  js      short loc_1800A26C0
0x1800a2674  mov     r8d, esi
0x1800a2677  lea     rcx, qword_180134C08
0x1800a267e  mov     edx, r12d
0x1800a2681  call    FwAnyNonDefaultSetsAreInUse
0x1800a2686  test    eax, eax
0x1800a2688  jz      short loc_1800A26C0
0x1800a268a  mov     ebx, 80070962h
0x1800a268f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2696  cmp     rcx, r13
0x1800a2699  jz      loc_1800A2B91
0x1800a269f  test    [rcx+1Ch], r12b
0x1800a26a3  jz      loc_1800A2B91
0x1800a26a9  lea     edx, [rsi+34h]
0x1800a26ac  mov     r9d, ebx
0x1800a26af  mov     r8, rdi
0x1800a26b2  mov     rcx, [rcx+10h]
0x1800a26b6  call    WPP_SF_d
0x1800a26bb  jmp     loc_1800A2B91
0x1800a26c0  lea     rdx, [rbp+var_40]
0x1800a26c4  mov     rcx, r14
0x1800a26c7  call    ExtractRPCClientSID
0x1800a26cc  mov     ebx, eax
0x1800a26ce  test    eax, eax
0x1800a26d0  jns     short loc_1800A26F6
0x1800a26d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a26d9  cmp     rcx, r13
0x1800a26dc  jz      loc_1800A2B91
0x1800a26e2  test    [rcx+1Ch], r12b
0x1800a26e6  jz      loc_1800A2B91
0x1800a26ec  mov     edx, 37h ; '7'
0x1800a26f1  mov     r9d, eax
0x1800a26f4  jmp     short loc_1800A26AF
0x1800a26f6  lea     rdx, [rbp+var_38]
0x1800a26fa  mov     rcx, r14
0x1800a26fd  call    cs:__imp_FwGetRpcCallersProcessImageName
0x1800a2704  nop     dword ptr [rax+rax+00h]
0x1800a2709  lea     rax, [rbp+var_1C]
0x1800a270d  mov     r8d, 2001Fh
0x1800a2713  lea     r9, [rbp+var_30]
0x1800a2717  mov     qword ptr [rsp+78h+var_58], rax
0x1800a271c  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x1800a2723  mov     rcx, 0FFFFFFFF80000002h
0x1800a272a  call    cs:__imp_FwRegOpenKey
0x1800a2731  nop     dword ptr [rax+rax+00h]
0x1800a2736  mov     ebx, eax
0x1800a2738  test    eax, eax
0x1800a273a  jns     short loc_1800A275D
0x1800a273c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2743  cmp     rcx, r13
0x1800a2746  jz      loc_1800A2B91
0x1800a274c  test    [rcx+1Ch], r12b
0x1800a2750  jz      loc_1800A2B91
0x1800a2756  mov     edx, 38h ; '8'
0x1800a275b  jmp     short loc_1800A26F1
0x1800a275d  cmp     [rbp+var_1C], r15d
0x1800a2761  jnz     short loc_1800A2790
0x1800a2763  mov     r9d, 80070003h
0x1800a2769  mov     ebx, r9d
0x1800a276c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2773  cmp     rcx, r13
0x1800a2776  jz      loc_1800A2B91
0x1800a277c  test    [rcx+1Ch], r12b
0x1800a2780  jz      loc_1800A2B91
0x1800a2786  mov     edx, 39h ; '9'
0x1800a278b  jmp     loc_1800A26AF
0x1800a2790  lea     rax, [rbp+var_1C]
0x1800a2794  mov     r8d, 20019h
0x1800a279a  lea     r9, [rbp+var_28]
0x1800a279e  mov     qword ptr [rsp+78h+var_58], rax
0x1800a27a3  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x1800a27aa  mov     rcx, 0FFFFFFFF80000002h
0x1800a27b1  call    cs:__imp_FwRegOpenKey
0x1800a27b8  nop     dword ptr [rax+rax+00h]
0x1800a27bd  mov     ebx, eax
0x1800a27bf  test    eax, eax
0x1800a27c1  jns     short loc_1800A27E7
0x1800a27c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a27ca  cmp     rcx, r13
0x1800a27cd  jz      loc_1800A2B91
0x1800a27d3  test    [rcx+1Ch], r12b
0x1800a27d7  jz      loc_1800A2B91
0x1800a27dd  mov     edx, 3Ah ; ':'
0x1800a27e2  jmp     loc_1800A26F1
0x1800a27e7  cmp     [rbp+var_1C], r15d
0x1800a27eb  jnz     short loc_1800A281A
0x1800a27ed  mov     r9d, 80070003h
0x1800a27f3  mov     ebx, r9d
0x1800a27f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a27fd  cmp     rcx, r13
0x1800a2800  jz      loc_1800A2B91
0x1800a2806  test    [rcx+1Ch], r12b
0x1800a280a  jz      loc_1800A2B91
0x1800a2810  mov     edx, 3Bh ; ';'
0x1800a2815  jmp     loc_1800A26AF
0x1800a281a  lea     r9, [rbp+var_48]
0x1800a281e  xor     r8d, r8d
0x1800a2821  mov     edx, esi
0x1800a2823  mov     ecx, esi
0x1800a2825  call    cs:__imp_FwOpenPolicyStore
0x1800a282c  nop     dword ptr [rax+rax+00h]
0x1800a2831  mov     ebx, eax
0x1800a2833  test    eax, eax
0x1800a2835  jns     short loc_1800A285B
0x1800a2837  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a283e  cmp     rcx, r13
0x1800a2841  jz      loc_1800A2B91
0x1800a2847  test    [rcx+1Ch], r12b
0x1800a284b  jz      loc_1800A2B91
0x1800a2851  mov     edx, 3Ch ; '<'
0x1800a2856  jmp     loc_1800A26F1
0x1800a285b  mov     r8, r14
0x1800a285e  mov     edx, esi
0x1800a2860  mov     ecx, r12d
0x1800a2863  call    FwRpcAPIsSecModeAccessCheckForClient
0x1800a2868  test    eax, eax
0x1800a286a  js      loc_1800A2A28
0x1800a2870  mov     rcx, [rbp+var_48]
0x1800a2874  xor     edx, edx
0x1800a2876  call    cs:__imp_FwDeleteAllRules
0x1800a287d  nop     dword ptr [rax+rax+00h]
0x1800a2882  mov     ebx, eax
0x1800a2884  test    eax, eax
0x1800a2886  jns     short loc_1800A28AC
0x1800a2888  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a288f  cmp     rcx, r13
0x1800a2892  jz      loc_1800A2B91
0x1800a2898  test    [rcx+1Ch], r12b
0x1800a289c  jz      loc_1800A2B91
0x1800a28a2  mov     edx, 3Dh ; '='
0x1800a28a7  jmp     loc_1800A26F1
0x1800a28ac  mov     rcx, [rbp+var_48]
0x1800a28b0  mov     edx, r12d
0x1800a28b3  call    cs:__imp_FwDeleteAllRules
0x1800a28ba  nop     dword ptr [rax+rax+00h]
0x1800a28bf  mov     ebx, eax
0x1800a28c1  test    eax, eax
0x1800a28c3  jns     short loc_1800A28E9
0x1800a28c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a28cc  cmp     rcx, r13
0x1800a28cf  jz      loc_1800A2B91
0x1800a28d5  test    [rcx+1Ch], r12b
0x1800a28d9  jz      loc_1800A2B91
0x1800a28df  mov     edx, 3Eh ; '>'
0x1800a28e4  jmp     loc_1800A26F1
0x1800a28e9  mov     rcx, [rbp+var_48]
0x1800a28ed  mov     edx, esi
0x1800a28ef  call    cs:__imp_FwDeleteAllRules
0x1800a28f6  nop     dword ptr [rax+rax+00h]
0x1800a28fb  mov     ebx, eax
0x1800a28fd  test    eax, eax
0x1800a28ff  jns     short loc_1800A2925
0x1800a2901  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2908  cmp     rcx, r13
0x1800a290b  jz      loc_1800A2B91
0x1800a2911  test    [rcx+1Ch], r12b
0x1800a2915  jz      loc_1800A2B91
0x1800a291b  mov     edx, 3Fh ; '?'
0x1800a2920  jmp     loc_1800A26F1
0x1800a2925  mov     rcx, [rbp+var_48]
0x1800a2929  mov     r8d, r12d
0x1800a292c  xor     edx, edx
0x1800a292e  call    cs:__imp_FwDeleteAllSets
0x1800a2935  nop     dword ptr [rax+rax+00h]
0x1800a293a  mov     ebx, eax
0x1800a293c  test    eax, eax
0x1800a293e  jns     short loc_1800A2964
0x1800a2940  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2947  cmp     rcx, r13
0x1800a294a  jz      loc_1800A2B91
0x1800a2950  test    [rcx+1Ch], r12b
0x1800a2954  jz      loc_1800A2B91
0x1800a295a  mov     edx, 40h ; '@'
0x1800a295f  jmp     loc_1800A26F1
0x1800a2964  mov     rcx, [rbp+var_48]
0x1800a2968  mov     r8d, esi
0x1800a296b  xor     edx, edx
0x1800a296d  call    cs:__imp_FwDeleteAllSets
0x1800a2974  nop     dword ptr [rax+rax+00h]
0x1800a2979  mov     ebx, eax
0x1800a297b  test    eax, eax
0x1800a297d  jns     short loc_1800A29A3
0x1800a297f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2986  cmp     rcx, r13
0x1800a2989  jz      loc_1800A2B91
0x1800a298f  test    [rcx+1Ch], r12b
0x1800a2993  jz      loc_1800A2B91
0x1800a2999  mov     edx, 41h ; 'A'
0x1800a299e  jmp     loc_1800A26F1
0x1800a29a3  mov     esi, r15d
0x1800a29a6  cmp     esi, 3
0x1800a29a9  jnb     short loc_1800A2A1C
0x1800a29ab  mov     edi, r12d
0x1800a29ae  cmp     edi, 13h
0x1800a29b1  jnb     short loc_1800A29E9
0x1800a29b3  mov     ecx, esi
0x1800a29b5  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x1800a29bc  nop     dword ptr [rax+rax+00h]
0x1800a29c1  mov     rcx, [rbp+var_48]
0x1800a29c5  xor     r9d, r9d
0x1800a29c8  mov     r8d, eax
0x1800a29cb  mov     [rsp+78h+var_58], r15d
0x1800a29d0  mov     edx, edi
0x1800a29d2  call    cs:__imp_FwSetConfig
0x1800a29d9  nop     dword ptr [rax+rax+00h]
0x1800a29de  mov     ebx, eax
0x1800a29e0  test    eax, eax
0x1800a29e2  js      short loc_1800A29EE
0x1800a29e4  add     edi, r12d
0x1800a29e7  jmp     short loc_1800A29AE
0x1800a29e9  add     esi, r12d
0x1800a29ec  jmp     short loc_1800A29A6
0x1800a29ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a29f5  cmp     rcx, r13
0x1800a29f8  jz      loc_1800A2B91
0x1800a29fe  test    [rcx+1Ch], r12b
0x1800a2a02  jz      loc_1800A2B91
0x1800a2a08  mov     edx, 42h ; 'B'
0x1800a2a0d  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a2a14  mov     r9d, eax
0x1800a2a17  jmp     loc_1800A26B2
0x1800a2a1c  lea     rdi, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a2a23  mov     esi, 2
0x1800a2a28  mov     r8, r14
0x1800a2a2b  mov     edx, esi
0x1800a2a2d  mov     ecx, esi
0x1800a2a2f  call    FwRpcAPIsSecModeAccessCheckForClient
0x1800a2a34  test    eax, eax
0x1800a2a36  js      loc_1800A2ABC
0x1800a2a3c  mov     rcx, [rbp+var_48]
0x1800a2a40  mov     r8d, r12d
0x1800a2a43  mov     edx, r12d
  ... truncated ...
```
