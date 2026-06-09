# SvrImpl_FWRestoreDefaults(void *)

- ea: `0x18009d0c8`
- end: `0x18009d782`
- name: `?SvrImpl_FWRestoreDefaults@@YAKPEAX@Z`
- size: `1722`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x1800c3b50`

## callees

- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180017110`
- `0x180032774`
- `0x18005441c`
- `0x180059384`
- `0x18006f520`
- `0x18007b1b4`
- `0x180084d70`
- `0x180087588`
- `0x18008d3b4`
- `0x180094b58`
- `0x18009d0c8`
- `0x1800a17bc`

## import_xrefs

- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18009d195`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18009d195`
- `fwbase!FwRegDeleteAllValues` at `0x18009d5d7`
- `fwbase!FwRegDeleteAllValues` at `0x18009d5d7`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009d247`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009d247`
- `fwbase!FwRegOpenKey` at `0x18009d26e`
- `fwbase!FwRegOpenKey` at `0x18009d2ef`
- `fwbase!FwRegOpenKey` at `0x18009d26e`
- `fwbase!FwRegOpenKey` at `0x18009d2ef`
- `fwbase!FwRegCloseKey` at `0x18009d72a`
- `fwbase!FwRegCloseKey` at `0x18009d734`
- `fwbase!FwRegCloseKey` at `0x18009d73c`
- `fwbase!FwRegCloseKey` at `0x18009d72a`
- `fwbase!FwRegCloseKey` at `0x18009d734`
- `fwbase!FwRegCloseKey` at `0x18009d73c`
- `fwbase!FwChangeSourceSignal` at `0x18009d690`
- `fwbase!FwChangeSourceSignal` at `0x18009d690`
- `fwbase!FwHResultToWindowsError` at `0x18009d698`
- `fwbase!FwHResultToWindowsError` at `0x18009d6ef`
- `fwbase!FwHResultToWindowsError` at `0x18009d75f`
- `fwbase!FwHResultToWindowsError` at `0x18009d698`
- `fwbase!FwHResultToWindowsError` at `0x18009d6ef`
- `fwbase!FwHResultToWindowsError` at `0x18009d75f`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18009d4c9`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18009d4c9`
- `fwbase!FwFree` at `0x18009d716`
- `fwbase!FwFree` at `0x18009d720`
- `fwbase!FwFree` at `0x18009d716`
- `fwbase!FwFree` at `0x18009d720`
- `FWPolicyIOMgr!FwSetConfig` at `0x18009d4e0`
- `FWPolicyIOMgr!FwSetConfig` at `0x18009d4e0`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x18009d3a8`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x18009d3df`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x18009d415`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x18009d3a8`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x18009d3df`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x18009d415`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18009d44e`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18009d487`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18009d54a`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18009d584`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18009d44e`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18009d487`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18009d54a`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18009d584`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x18009d5b8`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x18009d74b`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x18009d5b8`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x18009d74b`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x18009d35d`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x18009d35d`

## string_xrefs

- `0x18009d260`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x18009d2e1`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Defaults\FirewallPolicy`

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
  int RPCClientSID; // eax
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
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 52, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 8) != 0 )
      WPP_SF_(*(_QWORD *)(v2 + 16), 53, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
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
      && (int)FwRpcAPIsSecModeAccessCheckForClient(2u, 2, a1) >= 0
      && (unsigned int)FwAnyNonDefaultSetsAreInUse(qword_18012EA48, 1, 2) )
    {
      v5 = -2147022494;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_97;
      v7 = 54;
      v8 = 2147944802LL;
      goto LABEL_17;
    }
    RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v20);
    v5 = RPCClientSID;
    if ( RPCClientSID < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_97;
      v7 = 55;
      goto LABEL_22;
    }
    FwGetRpcCallersProcessImageName(a1, &v21);
    RPCClientSID = FwRegOpenKey(
                     -2147483646,
                     L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
                     131103,
                     &v22,
                     &v25);
    v5 = RPCClientSID;
    if ( RPCClientSID < 0 )
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
    RPCClientSID = FwRegOpenKey(
                     -2147483646,
                     L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Defaults\\FirewallPolicy",
                     131097,
                     &v23,
                     &v25);
    v5 = RPCClientSID;
    if ( RPCClientSID < 0 )
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
    RPCClientSID = FwOpenPolicyStore(2, 2, 0, &v19);
    v5 = RPCClientSID;
    if ( RPCClientSID < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_97;
      v7 = 60;
      goto LABEL_22;
    }
    if ( (int)FwRpcAPIsSecModeAccessCheckForClient(1u, 2, a1) >= 0 )
    {
      RPCClientSID = FwDeleteAllRules(v19, 0);
      v5 = RPCClientSID;
      if ( RPCClientSID < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 61;
        goto LABEL_22;
      }
      RPCClientSID = FwDeleteAllRules(v19, 1);
      v5 = RPCClientSID;
      if ( RPCClientSID < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 62;
        goto LABEL_22;
      }
      RPCClientSID = FwDeleteAllRules(v19, 2);
      v5 = RPCClientSID;
      if ( RPCClientSID < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 63;
        goto LABEL_22;
      }
      RPCClientSID = FwDeleteAllSets(v19, 0, 1);
      v5 = RPCClientSID;
      if ( RPCClientSID < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 64;
        goto LABEL_22;
      }
      RPCClientSID = FwDeleteAllSets(v19, 0, 2);
      v5 = RPCClientSID;
      if ( RPCClientSID < 0 )
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
    if ( (int)FwRpcAPIsSecModeAccessCheckForClient(2u, 2, a1) >= 0 )
    {
      RPCClientSID = FwDeleteAllSets(v19, 1, 1);
      v5 = RPCClientSID;
      if ( RPCClientSID < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 67;
        goto LABEL_22;
      }
      RPCClientSID = FwDeleteAllSets(v19, 1, 2);
      v5 = RPCClientSID;
      if ( RPCClientSID < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_97;
        v7 = 68;
LABEL_22:
        v8 = (unsigned int)RPCClientSID;
LABEL_17:
        WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v8);
LABEL_97:
        FwUnlockInternal(a1, "SvrImpl_FWRestoreDefaults");
        if ( (v5 & 0x80000000) == 0 )
          FwChangeSourceSignal();
        FwHResultToWindowsError(v5);
        v14 = (unsigned __int16 *)&qword_1800F5F90;
        v15 = (unsigned __int16 *)&qword_1800F5F90;
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
    if ( (int)FwRpcAPIsSecModeAccessCheckForClient(1u, 2, a1) < 0
      || (RPCClientSID = FwRegDeleteAllValues(v22), v5 = RPCClientSID, RPCClientSID >= 0) )
    {
      RPCClientSID = FwCopyDefaultsToLocalStorePerUserRights(a1, v23);
      v5 = RPCClientSID;
      if ( RPCClientSID >= 0 )
      {
        RPCClientSID = FwProfileMgrOnPolicyChange(0, 1, 0, 0, 1);
        v5 = RPCClientSID;
        if ( RPCClientSID >= 0 )
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
0x18009d0c8  push    rbp
0x18009d0ca  push    rbx
0x18009d0cb  push    rsi
0x18009d0cc  push    rdi
0x18009d0cd  push    r12
0x18009d0cf  push    r13
0x18009d0d1  push    r14
0x18009d0d3  push    r15
0x18009d0d5  mov     rbp, rsp
0x18009d0d8  sub     rsp, 78h
0x18009d0dc  mov     rax, cs:__security_cookie
0x18009d0e3  xor     rax, rsp
0x18009d0e6  mov     [rbp+var_18], rax
0x18009d0ea  xor     r15d, r15d
0x18009d0ed  mov     r14, rcx
0x18009d0f0  mov     [rbp+var_30], r15
0x18009d0f4  mov     [rbp+var_28], r15
0x18009d0f8  mov     [rbp+var_1C], r15d
0x18009d0fc  mov     [rbp+var_40], r15
0x18009d100  mov     [rbp+var_48], r15
0x18009d104  mov     [rbp+var_38], r15
0x18009d108  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d10f  lea     r13, WPP_GLOBAL_Control
0x18009d116  lea     rdi, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009d11d  cmp     rcx, r13
0x18009d120  jz      short loc_18009D15B
0x18009d122  test    byte ptr [rcx+1Ch], 8
0x18009d126  jz      short loc_18009D13F
0x18009d128  mov     rcx, [rcx+10h]
0x18009d12c  lea     edx, [r15+34h]
0x18009d130  mov     r8, rdi
0x18009d133  call    WPP_SF_
0x18009d138  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d13f  cmp     rcx, r13
0x18009d142  jz      short loc_18009D15B
0x18009d144  test    byte ptr [rcx+1Ch], 8
0x18009d148  jz      short loc_18009D15B
0x18009d14a  mov     rcx, [rcx+10h]
0x18009d14e  mov     edx, 35h ; '5'
0x18009d153  mov     r8, rdi
0x18009d156  call    WPP_SF_
0x18009d15b  lea     rcx, aSvrimplFwresto; "SvrImpl_FWRestoreDefaults"
0x18009d162  call    FwAcquireRPCSharedLock
0x18009d167  test    eax, eax
0x18009d169  js      loc_18009D765
0x18009d16f  call    FwLock
0x18009d174  mov     ebx, eax
0x18009d176  test    eax, eax
0x18009d178  jns     short loc_18009D18D
0x18009d17a  lea     rcx, aSvrimplFwresto; "SvrImpl_FWRestoreDefaults"
0x18009d181  call    FwReleaseRPCSharedLock
0x18009d186  mov     eax, ebx
0x18009d188  jmp     loc_18009D765
0x18009d18d  lea     rcx, [rbp+pfEnabled]; pfEnabled
0x18009d191  mov     [rbp+pfEnabled], r15b
0x18009d195  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x18009d19b  mov     esi, 2
0x18009d1a0  lea     r12d, [rsi-1]
0x18009d1a4  test    eax, eax
0x18009d1a6  js      short loc_18009D20A
0x18009d1a8  cmp     [rbp+pfEnabled], r15b
0x18009d1ac  jz      short loc_18009D20A
0x18009d1ae  mov     r8, r14
0x18009d1b1  mov     edx, esi
0x18009d1b3  mov     ecx, esi
0x18009d1b5  call    FwRpcAPIsSecModeAccessCheckForClient
0x18009d1ba  test    eax, eax
0x18009d1bc  js      short loc_18009D20A
0x18009d1be  mov     r8d, esi
0x18009d1c1  lea     rcx, qword_18012EA48
0x18009d1c8  mov     edx, r12d
0x18009d1cb  call    FwAnyNonDefaultSetsAreInUse
0x18009d1d0  test    eax, eax
0x18009d1d2  jz      short loc_18009D20A
0x18009d1d4  mov     ebx, 80070962h
0x18009d1d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d1e0  cmp     rcx, r13
0x18009d1e3  jz      loc_18009D67D
0x18009d1e9  test    [rcx+1Ch], r12b
0x18009d1ed  jz      loc_18009D67D
0x18009d1f3  lea     edx, [rsi+34h]
0x18009d1f6  mov     r9d, ebx
0x18009d1f9  mov     r8, rdi
0x18009d1fc  mov     rcx, [rcx+10h]
0x18009d200  call    WPP_SF_d
0x18009d205  jmp     loc_18009D67D
0x18009d20a  lea     rdx, [rbp+var_40]
0x18009d20e  mov     rcx, r14
0x18009d211  call    ExtractRPCClientSID
0x18009d216  mov     ebx, eax
0x18009d218  test    eax, eax
0x18009d21a  jns     short loc_18009D240
0x18009d21c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d223  cmp     rcx, r13
0x18009d226  jz      loc_18009D67D
0x18009d22c  test    [rcx+1Ch], r12b
0x18009d230  jz      loc_18009D67D
0x18009d236  mov     edx, 37h ; '7'
0x18009d23b  mov     r9d, eax
0x18009d23e  jmp     short loc_18009D1F9
0x18009d240  lea     rdx, [rbp+var_38]
0x18009d244  mov     rcx, r14
0x18009d247  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009d24d  lea     rax, [rbp+var_1C]
0x18009d251  mov     r8d, 2001Fh
0x18009d257  lea     r9, [rbp+var_30]
0x18009d25b  mov     qword ptr [rsp+78h+var_58], rax
0x18009d260  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18009d267  mov     rcx, 0FFFFFFFF80000002h
0x18009d26e  call    cs:__imp_FwRegOpenKey
0x18009d274  mov     ebx, eax
0x18009d276  test    eax, eax
0x18009d278  jns     short loc_18009D29B
0x18009d27a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d281  cmp     rcx, r13
0x18009d284  jz      loc_18009D67D
0x18009d28a  test    [rcx+1Ch], r12b
0x18009d28e  jz      loc_18009D67D
0x18009d294  mov     edx, 38h ; '8'
0x18009d299  jmp     short loc_18009D23B
0x18009d29b  cmp     [rbp+var_1C], r15d
0x18009d29f  jnz     short loc_18009D2CE
0x18009d2a1  mov     r9d, 80070003h
0x18009d2a7  mov     ebx, r9d
0x18009d2aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d2b1  cmp     rcx, r13
0x18009d2b4  jz      loc_18009D67D
0x18009d2ba  test    [rcx+1Ch], r12b
0x18009d2be  jz      loc_18009D67D
0x18009d2c4  mov     edx, 39h ; '9'
0x18009d2c9  jmp     loc_18009D1F9
0x18009d2ce  lea     rax, [rbp+var_1C]
0x18009d2d2  mov     r8d, 20019h
0x18009d2d8  lea     r9, [rbp+var_28]
0x18009d2dc  mov     qword ptr [rsp+78h+var_58], rax
0x18009d2e1  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18009d2e8  mov     rcx, 0FFFFFFFF80000002h
0x18009d2ef  call    cs:__imp_FwRegOpenKey
0x18009d2f5  mov     ebx, eax
0x18009d2f7  test    eax, eax
0x18009d2f9  jns     short loc_18009D31F
0x18009d2fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d302  cmp     rcx, r13
0x18009d305  jz      loc_18009D67D
0x18009d30b  test    [rcx+1Ch], r12b
0x18009d30f  jz      loc_18009D67D
0x18009d315  mov     edx, 3Ah ; ':'
0x18009d31a  jmp     loc_18009D23B
0x18009d31f  cmp     [rbp+var_1C], r15d
0x18009d323  jnz     short loc_18009D352
0x18009d325  mov     r9d, 80070003h
0x18009d32b  mov     ebx, r9d
0x18009d32e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d335  cmp     rcx, r13
0x18009d338  jz      loc_18009D67D
0x18009d33e  test    [rcx+1Ch], r12b
0x18009d342  jz      loc_18009D67D
0x18009d348  mov     edx, 3Bh ; ';'
0x18009d34d  jmp     loc_18009D1F9
0x18009d352  lea     r9, [rbp+var_48]
0x18009d356  xor     r8d, r8d
0x18009d359  mov     edx, esi
0x18009d35b  mov     ecx, esi
0x18009d35d  call    cs:__imp_FwOpenPolicyStore
0x18009d363  mov     ebx, eax
0x18009d365  test    eax, eax
0x18009d367  jns     short loc_18009D38D
0x18009d369  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d370  cmp     rcx, r13
0x18009d373  jz      loc_18009D67D
0x18009d379  test    [rcx+1Ch], r12b
0x18009d37d  jz      loc_18009D67D
0x18009d383  mov     edx, 3Ch ; '<'
0x18009d388  jmp     loc_18009D23B
0x18009d38d  mov     r8, r14
0x18009d390  mov     edx, esi
0x18009d392  mov     ecx, r12d
0x18009d395  call    FwRpcAPIsSecModeAccessCheckForClient
0x18009d39a  test    eax, eax
0x18009d39c  js      loc_18009D530
0x18009d3a2  mov     rcx, [rbp+var_48]
0x18009d3a6  xor     edx, edx
0x18009d3a8  call    cs:__imp_FwDeleteAllRules
0x18009d3ae  mov     ebx, eax
0x18009d3b0  test    eax, eax
0x18009d3b2  jns     short loc_18009D3D8
0x18009d3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d3bb  cmp     rcx, r13
0x18009d3be  jz      loc_18009D67D
0x18009d3c4  test    [rcx+1Ch], r12b
0x18009d3c8  jz      loc_18009D67D
0x18009d3ce  mov     edx, 3Dh ; '='
0x18009d3d3  jmp     loc_18009D23B
0x18009d3d8  mov     rcx, [rbp+var_48]
0x18009d3dc  mov     edx, r12d
0x18009d3df  call    cs:__imp_FwDeleteAllRules
0x18009d3e5  mov     ebx, eax
0x18009d3e7  test    eax, eax
0x18009d3e9  jns     short loc_18009D40F
0x18009d3eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d3f2  cmp     rcx, r13
0x18009d3f5  jz      loc_18009D67D
0x18009d3fb  test    [rcx+1Ch], r12b
0x18009d3ff  jz      loc_18009D67D
0x18009d405  mov     edx, 3Eh ; '>'
0x18009d40a  jmp     loc_18009D23B
0x18009d40f  mov     rcx, [rbp+var_48]
0x18009d413  mov     edx, esi
0x18009d415  call    cs:__imp_FwDeleteAllRules
0x18009d41b  mov     ebx, eax
0x18009d41d  test    eax, eax
0x18009d41f  jns     short loc_18009D445
0x18009d421  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d428  cmp     rcx, r13
0x18009d42b  jz      loc_18009D67D
0x18009d431  test    [rcx+1Ch], r12b
0x18009d435  jz      loc_18009D67D
0x18009d43b  mov     edx, 3Fh ; '?'
0x18009d440  jmp     loc_18009D23B
0x18009d445  mov     rcx, [rbp+var_48]
0x18009d449  mov     r8d, r12d
0x18009d44c  xor     edx, edx
0x18009d44e  call    cs:__imp_FwDeleteAllSets
0x18009d454  mov     ebx, eax
0x18009d456  test    eax, eax
0x18009d458  jns     short loc_18009D47E
0x18009d45a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d461  cmp     rcx, r13
0x18009d464  jz      loc_18009D67D
0x18009d46a  test    [rcx+1Ch], r12b
0x18009d46e  jz      loc_18009D67D
0x18009d474  mov     edx, 40h ; '@'
0x18009d479  jmp     loc_18009D23B
0x18009d47e  mov     rcx, [rbp+var_48]
0x18009d482  mov     r8d, esi
0x18009d485  xor     edx, edx
0x18009d487  call    cs:__imp_FwDeleteAllSets
0x18009d48d  mov     ebx, eax
0x18009d48f  test    eax, eax
0x18009d491  jns     short loc_18009D4B7
0x18009d493  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d49a  cmp     rcx, r13
0x18009d49d  jz      loc_18009D67D
0x18009d4a3  test    [rcx+1Ch], r12b
0x18009d4a7  jz      loc_18009D67D
0x18009d4ad  mov     edx, 41h ; 'A'
0x18009d4b2  jmp     loc_18009D23B
0x18009d4b7  mov     esi, r15d
0x18009d4ba  cmp     esi, 3
0x18009d4bd  jnb     short loc_18009D524
0x18009d4bf  mov     edi, r12d
0x18009d4c2  cmp     edi, 13h
0x18009d4c5  jnb     short loc_18009D4F1
0x18009d4c7  mov     ecx, esi
0x18009d4c9  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x18009d4cf  mov     rcx, [rbp+var_48]
0x18009d4d3  xor     r9d, r9d
0x18009d4d6  mov     r8d, eax
0x18009d4d9  mov     [rsp+78h+var_58], r15d
0x18009d4de  mov     edx, edi
0x18009d4e0  call    cs:__imp_FwSetConfig
0x18009d4e6  mov     ebx, eax
0x18009d4e8  test    eax, eax
0x18009d4ea  js      short loc_18009D4F6
0x18009d4ec  add     edi, r12d
0x18009d4ef  jmp     short loc_18009D4C2
0x18009d4f1  add     esi, r12d
0x18009d4f4  jmp     short loc_18009D4BA
0x18009d4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d4fd  cmp     rcx, r13
0x18009d500  jz      loc_18009D67D
0x18009d506  test    [rcx+1Ch], r12b
0x18009d50a  jz      loc_18009D67D
0x18009d510  mov     edx, 42h ; 'B'
0x18009d515  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009d51c  mov     r9d, eax
0x18009d51f  jmp     loc_18009D1FC
0x18009d524  lea     rdi, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009d52b  mov     esi, 2
0x18009d530  mov     r8, r14
0x18009d533  mov     edx, esi
0x18009d535  mov     ecx, esi
0x18009d537  call    FwRpcAPIsSecModeAccessCheckForClient
0x18009d53c  test    eax, eax
0x18009d53e  js      short loc_18009D5B4
0x18009d540  mov     rcx, [rbp+var_48]
0x18009d544  mov     r8d, r12d
0x18009d547  mov     edx, r12d
0x18009d54a  call    cs:__imp_FwDeleteAllSets
0x18009d550  mov     ebx, eax
0x18009d552  test    eax, eax
0x18009d554  jns     short loc_18009D57A
0x18009d556  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d55d  cmp     rcx, r13
0x18009d560  jz      loc_18009D67D
0x18009d566  test    [rcx+1Ch], r12b
0x18009d56a  jz      loc_18009D67D
0x18009d570  mov     edx, 43h ; 'C'
0x18009d575  jmp     loc_18009D23B
0x18009d57a  mov     rcx, [rbp+var_48]
  ... truncated ...
```
