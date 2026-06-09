# FwCopyDefaultsToLocalStorePerUserRights(void *,HKEY__ *)

- ea: `0x180094b58`
- end: `0x180094f48`
- name: `?FwCopyDefaultsToLocalStorePerUserRights@@YAJPEAXPEAUHKEY__@@@Z`
- size: `1008`
- prototype: `__int64 __fastcall(void *, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18009d0c8`

## callees

- `0x18000af3c`
- `0x180032774`
- `0x18006f520`
- `0x180094b58`
- `0x180094f50`

## import_xrefs

- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180094d0c`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180094d0c`
- `FWPolicyIOMgr!FwGetGlobalConfigFromLocalTempStore` at `0x180094c86`
- `FWPolicyIOMgr!FwGetGlobalConfigFromLocalTempStore` at `0x180094c86`
- `FWPolicyIOMgr!FwSetConfig` at `0x180094d61`
- `FWPolicyIOMgr!FwSetConfig` at `0x180094d61`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x180094cb2`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x180094cb2`
- `FWPolicyIOMgr!FwDestroyLocalTempStore` at `0x180094f19`
- `FWPolicyIOMgr!FwDestroyLocalTempStore` at `0x180094f19`
- `FWPolicyIOMgr!FwCreateLocalTempStore` at `0x180094bb1`
- `FWPolicyIOMgr!FwCreateLocalTempStore` at `0x180094bb1`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x180094f00`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x180094f00`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x180094c0d`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x180094c0d`
- `FWPolicyIOMgr!FwGetConfig` at `0x180094d3d`
- `FWPolicyIOMgr!FwGetConfig` at `0x180094d3d`

## string_xrefs

- `0x180094b90`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Defaults\FirewallPolicy`

## pseudocode

```c
__int64 __fastcall FwCopyDefaultsToLocalStorePerUserRights(void *a1, HKEY a2)
{
  int GlobalConfigFromLocalTempStore; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // esi
  unsigned int v8; // esi
  unsigned int ProfileTypeFromProfileIndex; // r15d
  unsigned int i; // r14d
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v14[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v14[0] = 0;
  v13 = 0;
  v12 = 0;
  GlobalConfigFromLocalTempStore = FwCreateLocalTempStore(
                                     L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Defaults\\FirewallPolicy",
                                     a2,
                                     &v13);
  if ( GlobalConfigFromLocalTempStore < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_53;
    v6 = 43;
    goto LABEL_5;
  }
  GlobalConfigFromLocalTempStore = FwOpenPolicyStore(2, 2, 0, &v12);
  if ( GlobalConfigFromLocalTempStore < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_53;
    v6 = 44;
LABEL_5:
    WPP_SF_d(
      *(_QWORD *)(v5 + 16),
      v6,
      WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
      (unsigned int)GlobalConfigFromLocalTempStore);
    goto LABEL_53;
  }
  if ( (int)FwRpcAPIsSecModeAccessCheckForClient(1u, 2, a1) >= 0 )
  {
    v7 = 3;
    while ( 1 )
    {
      if ( v7 != 11 && v7 != 18 )
      {
        v14[0] = 4;
        GlobalConfigFromLocalTempStore = FwGetGlobalConfigFromLocalTempStore(a2, v7, v15, v14);
        if ( GlobalConfigFromLocalTempStore < 0 )
        {
          if ( GlobalConfigFromLocalTempStore != -2147024894 && GlobalConfigFromLocalTempStore != -2147024846 )
          {
            v5 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v6 = 46;
              goto LABEL_5;
            }
            goto LABEL_53;
          }
        }
        else
        {
          GlobalConfigFromLocalTempStore = FwSetGlobalConfig(512, 2, 0, v7, v15, 4);
          if ( GlobalConfigFromLocalTempStore < 0 )
          {
            v5 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v6 = 45;
              goto LABEL_5;
            }
            goto LABEL_53;
          }
        }
      }
      if ( ++v7 >= 0x13 )
      {
        v8 = 0;
        while ( 2 )
        {
          ProfileTypeFromProfileIndex = FwGetProfileTypeFromProfileIndex(v8);
          for ( i = 1; i < 0x13; ++i )
          {
            v14[0] = 1024;
            GlobalConfigFromLocalTempStore = FwGetConfig(v13, i, ProfileTypeFromProfileIndex, v15, v14);
            if ( GlobalConfigFromLocalTempStore < 0 )
            {
              if ( GlobalConfigFromLocalTempStore != -2147024894 && GlobalConfigFromLocalTempStore != -2147024846 )
              {
                v5 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  v6 = 48;
                  goto LABEL_5;
                }
                goto LABEL_53;
              }
            }
            else
            {
              GlobalConfigFromLocalTempStore = FwSetConfig(v12, i, ProfileTypeFromProfileIndex, v15, v14[0]);
              if ( GlobalConfigFromLocalTempStore < 0 )
              {
                v5 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  v6 = 47;
                  goto LABEL_5;
                }
                goto LABEL_53;
              }
            }
          }
          if ( ++v8 < 3 )
            continue;
          break;
        }
        GlobalConfigFromLocalTempStore = FwCopyPolicyObjs(v13, v12, 1);
        if ( GlobalConfigFromLocalTempStore >= 0 )
        {
          GlobalConfigFromLocalTempStore = FwCopyPolicyObjs(v13, v12, 0);
          if ( GlobalConfigFromLocalTempStore >= 0 )
            break;
          v5 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v6 = 50;
            goto LABEL_5;
          }
        }
        else
        {
          v5 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v6 = 49;
            goto LABEL_5;
          }
        }
        goto LABEL_53;
      }
    }
  }
  if ( (int)FwRpcAPIsSecModeAccessCheckForClient(2u, 2, a1) < 0
    || (GlobalConfigFromLocalTempStore = FwCopyPolicyObjs(v13, v12, 0), GlobalConfigFromLocalTempStore >= 0) )
  {
    GlobalConfigFromLocalTempStore = 0;
    goto LABEL_53;
  }
  v5 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v6 = 51;
    goto LABEL_5;
  }
LABEL_53:
  if ( v12 )
  {
    FwClosePolicyStore(v12);
    v12 = 0;
  }
  if ( v13 )
    FwDestroyLocalTempStore();
  return (unsigned int)GlobalConfigFromLocalTempStore;
}

```

## disassembly

```asm
0x180094b58  mov     [rsp-8+arg_10], rbx
0x180094b5d  push    rbp
0x180094b5e  push    rsi
0x180094b5f  push    r12
0x180094b61  push    r14
0x180094b63  push    r15
0x180094b65  lea     rbp, [rsp-360h]
0x180094b6d  sub     rsp, 460h
0x180094b74  mov     rax, cs:__security_cookie
0x180094b7b  xor     rax, rsp
0x180094b7e  mov     [rbp+380h+var_30], rax
0x180094b85  mov     r12, rcx
0x180094b88  mov     [rsp+480h+var_440], 0
0x180094b90  lea     rcx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x180094b97  mov     [rsp+480h+var_448], 0
0x180094ba0  lea     r8, [rsp+480h+var_448]
0x180094ba5  mov     [rsp+480h+var_450], 0
0x180094bae  mov     r14, rdx
0x180094bb1  call    cs:__imp_FwCreateLocalTempStore
0x180094bb7  mov     ebx, eax
0x180094bb9  test    eax, eax
0x180094bbb  jns     short loc_180094BFB
0x180094bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180094bc4  lea     rax, WPP_GLOBAL_Control
0x180094bcb  cmp     rcx, rax
0x180094bce  jz      loc_180094EF6
0x180094bd4  test    byte ptr [rcx+1Ch], 1
0x180094bd8  jz      loc_180094EF6
0x180094bde  mov     edx, 2Bh ; '+'
0x180094be3  mov     rcx, [rcx+10h]
0x180094be7  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180094bee  mov     r9d, ebx
0x180094bf1  call    WPP_SF_d
0x180094bf6  jmp     loc_180094EF6
0x180094bfb  xor     r8d, r8d
0x180094bfe  lea     r9, [rsp+480h+var_450]
0x180094c03  lea     r15d, [r8+2]
0x180094c07  mov     edx, r15d
0x180094c0a  mov     ecx, r15d
0x180094c0d  call    cs:__imp_FwOpenPolicyStore
0x180094c13  mov     ebx, eax
0x180094c15  test    eax, eax
0x180094c17  jns     short loc_180094C40
0x180094c19  mov     rcx, cs:WPP_GLOBAL_Control
0x180094c20  lea     rax, WPP_GLOBAL_Control
0x180094c27  cmp     rcx, rax
0x180094c2a  jz      loc_180094EF6
0x180094c30  test    byte ptr [rcx+1Ch], 1
0x180094c34  jz      loc_180094EF6
0x180094c3a  lea     edx, [r15+2Ah]
0x180094c3e  jmp     short loc_180094BE3
0x180094c40  mov     r8, r12
0x180094c43  mov     edx, r15d
0x180094c46  mov     ecx, 1
0x180094c4b  call    FwRpcAPIsSecModeAccessCheckForClient
0x180094c50  test    eax, eax
0x180094c52  js      loc_180094EA1
0x180094c58  mov     esi, 3
0x180094c5d  cmp     esi, 0Bh
0x180094c60  jz      loc_180094CFD
0x180094c66  cmp     esi, 12h
0x180094c69  jz      loc_180094CFD
0x180094c6f  lea     r9, [rsp+480h+var_440]
0x180094c74  mov     [rsp+480h+var_440], 4
0x180094c7c  lea     r8, [rsp+480h+var_430]
0x180094c81  mov     edx, esi
0x180094c83  mov     rcx, r14
0x180094c86  call    cs:__imp_FwGetGlobalConfigFromLocalTempStore
0x180094c8c  mov     ebx, eax
0x180094c8e  test    eax, eax
0x180094c90  js      short loc_180094CE9
0x180094c92  lea     rax, [rsp+480h+var_430]
0x180094c97  mov     [rsp+480h+var_458], 4
0x180094c9f  mov     ecx, 200h
0x180094ca4  mov     [rsp+480h+var_460], rax
0x180094ca9  mov     r9d, esi
0x180094cac  xor     r8d, r8d
0x180094caf  mov     edx, r15d
0x180094cb2  call    cs:__imp_FwSetGlobalConfig
0x180094cb8  mov     ebx, eax
0x180094cba  test    eax, eax
0x180094cbc  jns     short loc_180094CFD
0x180094cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180094cc5  lea     rax, WPP_GLOBAL_Control
0x180094ccc  cmp     rcx, rax
0x180094ccf  jz      loc_180094EF6
0x180094cd5  test    byte ptr [rcx+1Ch], 1
0x180094cd9  jz      loc_180094EF6
0x180094cdf  mov     edx, 2Dh ; '-'
0x180094ce4  jmp     loc_180094BE3
0x180094ce9  cmp     ebx, 80070002h
0x180094cef  jz      short loc_180094CFD
0x180094cf1  cmp     ebx, 80070032h
0x180094cf7  jnz     loc_180094D98
0x180094cfd  inc     esi
0x180094cff  cmp     esi, 13h
0x180094d02  jb      loc_180094C5D
0x180094d08  xor     esi, esi
0x180094d0a  mov     ecx, esi
0x180094d0c  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180094d12  mov     r15d, eax
0x180094d15  mov     r14d, 1
0x180094d1b  mov     rcx, [rsp+480h+var_448]
0x180094d20  lea     rax, [rsp+480h+var_440]
0x180094d25  lea     r9, [rsp+480h+var_430]
0x180094d2a  mov     [rsp+480h+var_460], rax
0x180094d2f  mov     r8d, r15d
0x180094d32  mov     [rsp+480h+var_440], 400h
0x180094d3a  mov     edx, r14d
0x180094d3d  call    cs:__imp_FwGetConfig
0x180094d43  mov     ebx, eax
0x180094d45  test    eax, eax
0x180094d47  js      short loc_180094DC3
0x180094d49  mov     eax, [rsp+480h+var_440]
0x180094d4d  lea     r9, [rsp+480h+var_430]
0x180094d52  mov     rcx, [rsp+480h+var_450]
0x180094d57  mov     r8d, r15d
0x180094d5a  mov     edx, r14d
0x180094d5d  mov     dword ptr [rsp+480h+var_460], eax
0x180094d61  call    cs:__imp_FwSetConfig
0x180094d67  mov     ebx, eax
0x180094d69  test    eax, eax
0x180094d6b  jns     short loc_180094DD3
0x180094d6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180094d74  lea     rax, WPP_GLOBAL_Control
0x180094d7b  cmp     rcx, rax
0x180094d7e  jz      loc_180094EF6
0x180094d84  test    byte ptr [rcx+1Ch], 1
0x180094d88  jz      loc_180094EF6
0x180094d8e  mov     edx, 2Fh ; '/'
0x180094d93  jmp     loc_180094BE3
0x180094d98  mov     rcx, cs:WPP_GLOBAL_Control
0x180094d9f  lea     rax, WPP_GLOBAL_Control
0x180094da6  cmp     rcx, rax
0x180094da9  jz      loc_180094EF6
0x180094daf  test    byte ptr [rcx+1Ch], 1
0x180094db3  jz      loc_180094EF6
0x180094db9  mov     edx, 2Eh ; '.'
0x180094dbe  jmp     loc_180094BE3
0x180094dc3  cmp     ebx, 80070002h
0x180094dc9  jz      short loc_180094DD3
0x180094dcb  cmp     ebx, 80070032h
0x180094dd1  jnz     short loc_180094E32
0x180094dd3  inc     r14d
0x180094dd6  cmp     r14d, 13h
0x180094dda  jb      loc_180094D1B
0x180094de0  inc     esi
0x180094de2  cmp     esi, 3
0x180094de5  jb      loc_180094D0A
0x180094deb  mov     rdx, [rsp+480h+var_450]
0x180094df0  xor     r9d, r9d
0x180094df3  mov     rcx, [rsp+480h+var_448]
0x180094df8  lea     r8d, [r9+1]
0x180094dfc  call    ?FwCopyPolicyObjs@@YAJPEAX0HKW4_tag_FW_IPSEC_PHASE@@@Z; FwCopyPolicyObjs(void *,void *,int,ulong,_tag_FW_IPSEC_PHASE)
0x180094e01  mov     ebx, eax
0x180094e03  test    eax, eax
0x180094e05  jns     short loc_180094E5D
0x180094e07  mov     rcx, cs:WPP_GLOBAL_Control
0x180094e0e  lea     rax, WPP_GLOBAL_Control
0x180094e15  cmp     rcx, rax
0x180094e18  jz      loc_180094EF6
0x180094e1e  test    byte ptr [rcx+1Ch], 1
0x180094e22  jz      loc_180094EF6
0x180094e28  mov     edx, 31h ; '1'
0x180094e2d  jmp     loc_180094BE3
0x180094e32  mov     rcx, cs:WPP_GLOBAL_Control
0x180094e39  lea     rax, WPP_GLOBAL_Control
0x180094e40  cmp     rcx, rax
0x180094e43  jz      loc_180094EF6
0x180094e49  test    byte ptr [rcx+1Ch], 1
0x180094e4d  jz      loc_180094EF6
0x180094e53  mov     edx, 30h ; '0'
0x180094e58  jmp     loc_180094BE3
0x180094e5d  mov     rdx, [rsp+480h+var_450]
0x180094e62  xor     r9d, r9d
0x180094e65  mov     rcx, [rsp+480h+var_448]
0x180094e6a  xor     r8d, r8d
0x180094e6d  call    ?FwCopyPolicyObjs@@YAJPEAX0HKW4_tag_FW_IPSEC_PHASE@@@Z; FwCopyPolicyObjs(void *,void *,int,ulong,_tag_FW_IPSEC_PHASE)
0x180094e72  mov     ebx, eax
0x180094e74  test    eax, eax
0x180094e76  jns     short loc_180094E9B
0x180094e78  mov     rcx, cs:WPP_GLOBAL_Control
0x180094e7f  lea     rax, WPP_GLOBAL_Control
0x180094e86  cmp     rcx, rax
0x180094e89  jz      short loc_180094EF6
0x180094e8b  test    byte ptr [rcx+1Ch], 1
0x180094e8f  jz      short loc_180094EF6
0x180094e91  mov     edx, 32h ; '2'
0x180094e96  jmp     loc_180094BE3
0x180094e9b  mov     r15d, 2
0x180094ea1  mov     r8, r12
0x180094ea4  mov     edx, r15d
0x180094ea7  mov     ecx, r15d
0x180094eaa  call    FwRpcAPIsSecModeAccessCheckForClient
0x180094eaf  test    eax, eax
0x180094eb1  js      short loc_180094EF4
0x180094eb3  mov     rdx, [rsp+480h+var_450]
0x180094eb8  mov     r9d, 1
0x180094ebe  mov     rcx, [rsp+480h+var_448]
0x180094ec3  xor     r8d, r8d
0x180094ec6  call    ?FwCopyPolicyObjs@@YAJPEAX0HKW4_tag_FW_IPSEC_PHASE@@@Z; FwCopyPolicyObjs(void *,void *,int,ulong,_tag_FW_IPSEC_PHASE)
0x180094ecb  mov     ebx, eax
0x180094ecd  test    eax, eax
0x180094ecf  jns     short loc_180094EF4
0x180094ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x180094ed8  lea     rax, WPP_GLOBAL_Control
0x180094edf  cmp     rcx, rax
0x180094ee2  jz      short loc_180094EF6
0x180094ee4  test    byte ptr [rcx+1Ch], 1
0x180094ee8  jz      short loc_180094EF6
0x180094eea  mov     edx, 33h ; '3'
0x180094eef  jmp     loc_180094BE3
0x180094ef4  xor     ebx, ebx
0x180094ef6  mov     rcx, [rsp+480h+var_450]
0x180094efb  test    rcx, rcx
0x180094efe  jz      short loc_180094F0F
0x180094f00  call    cs:__imp_FwClosePolicyStore
0x180094f06  mov     [rsp+480h+var_450], 0
0x180094f0f  mov     rcx, [rsp+480h+var_448]
0x180094f14  test    rcx, rcx
0x180094f17  jz      short loc_180094F1F
0x180094f19  call    cs:__imp_FwDestroyLocalTempStore
0x180094f1f  mov     eax, ebx
0x180094f21  mov     rcx, [rbp+380h+var_30]
0x180094f28  xor     rcx, rsp; StackCookie
0x180094f2b  call    __security_check_cookie
0x180094f30  mov     rbx, [rsp+480h+arg_10]
0x180094f38  add     rsp, 460h
0x180094f3f  pop     r15
0x180094f41  pop     r14
0x180094f43  pop     r12
0x180094f45  pop     rsi
0x180094f46  pop     rbp
0x180094f47  retn
```
