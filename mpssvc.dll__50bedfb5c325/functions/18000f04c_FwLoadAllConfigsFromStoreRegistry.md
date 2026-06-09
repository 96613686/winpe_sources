# FwLoadAllConfigsFromStoreRegistry

- ea: `0x18000f04c`
- end: `0x18000f4d9`
- name: `FwLoadAllConfigsFromStoreRegistry`
- size: `1165`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ee14`

## callees

- `0x18000a710`
- `0x18000f04c`
- `0x180011458`
- `0x180044fc4`
- `0x1800729c0`
- `0x180082d70`
- `0x180084528`
- `0x1800848f8`
- `0x18008552c`

## import_xrefs

- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000f35e`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000f35e`
- `fwbase!FwFree` at `0x18000f4a0`
- `fwbase!FwFree` at `0x18000f4a0`
- `FWPolicyIOMgr!FwGetHyperVProfileConfigFromRegistry` at `0x18000f3b6`
- `FWPolicyIOMgr!FwGetHyperVProfileConfigFromRegistry` at `0x18000f3b6`
- `FWPolicyIOMgr!FwGetHyperVVMCreatorIdsFromRegistry` at `0x18000f106`
- `FWPolicyIOMgr!FwGetHyperVVMCreatorIdsFromRegistry` at `0x18000f106`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x18000f48c`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x18000f48c`
- `FWPolicyIOMgr!FwGetHyperVVMConfigFromRegistry` at `0x18000f2d3`
- `FWPolicyIOMgr!FwGetHyperVVMConfigFromRegistry` at `0x18000f2d3`
- `FWPolicyIOMgr!FwUpgradeHyperVVMConfigToProfileConfig` at `0x18000f1d8`
- `FWPolicyIOMgr!FwUpgradeHyperVVMConfigToProfileConfig` at `0x18000f1d8`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x18000f09e`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x18000f09e`

## pseudocode

```c
__int64 __fastcall FwLoadAllConfigsFromStoreRegistry(__int64 a1)
{
  int HyperVVMCreatorIdsFromRegistry; // eax
  unsigned int v2; // ebx
  __int64 v3; // rcx
  __int64 v4; // rdx
  unsigned int i; // eax
  __int64 v6; // r12
  int v7; // eax
  int j; // r13d
  int v9; // eax
  __int64 *v10; // rbx
  int k; // ebx
  int HyperVVMConfigFromRegistry; // r13d
  int *v13; // r8
  unsigned int m; // r13d
  unsigned int ProfileTypeFromProfileIndex; // eax
  __int64 v16; // rdx
  int v17; // eax
  int *v18; // r9
  __int64 v20; // [rsp+20h] [rbp-A8h]
  __int64 v21; // [rsp+20h] [rbp-A8h]
  __int64 v22; // [rsp+28h] [rbp-A0h]
  unsigned int v23; // [rsp+40h] [rbp-88h]
  unsigned int v24; // [rsp+44h] [rbp-84h]
  unsigned int v25; // [rsp+48h] [rbp-80h]
  __int128 v26; // [rsp+50h] [rbp-78h] BYREF
  int v27; // [rsp+60h] [rbp-68h]
  __int128 v28; // [rsp+70h] [rbp-58h] BYREF
  __int64 v29; // [rsp+88h] [rbp-40h] BYREF
  __int64 v30; // [rsp+90h] [rbp-38h] BYREF
  int v31; // [rsp+98h] [rbp-30h] BYREF
  unsigned int v32; // [rsp+9Ch] [rbp-2Ch] BYREF
  int v33; // [rsp+A0h] [rbp-28h] BYREF

  v27 = a1;
  v33 = 4;
  v30 = 0;
  v32 = 0;
  v29 = 0;
  v31 = 0;
  HyperVVMCreatorIdsFromRegistry = FwOpenPolicyStore(a1, 2, 0, &v30);
  v2 = HyperVVMCreatorIdsFromRegistry;
  if ( HyperVVMCreatorIdsFromRegistry >= 0 )
  {
    HyperVVMCreatorIdsFromRegistry = FwGetHyperVVMCreatorIdsFromRegistry(v30, &v32, &v29);
    v2 = HyperVVMCreatorIdsFromRegistry;
    if ( HyperVVMCreatorIdsFromRegistry >= 0 )
    {
      for ( i = 0; ; i = v25 + 1 )
      {
        v25 = i;
        if ( i >= v32 )
          break;
        v6 = 16LL * i;
        v7 = FwHyperVMgrInitializeVMCreator(v6 + v29, 0);
        v2 = v7;
        if ( v7 < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              140,
              WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
              (unsigned int)v7);
          break;
        }
        for ( j = 1; j <= 3; ++j )
        {
          v28 = *(_OWORD *)(v6 + v29);
          v9 = FwUpgradeHyperVVMConfigToProfileConfig(v30, (unsigned int)j, &v28);
          v2 = v9;
          if ( v9 < 0 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                141,
                WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                (unsigned int)v9);
            }
            goto LABEL_51;
          }
        }
        *(_QWORD *)&v26 = 0;
        v10 = &qword_180132B58[4 * v27];
        std::_Tree<std::_Tmap_traits<_GUID,_tag_FW_HYPERV_CONFIG_STORE *,GuidComparer,std::allocator<std::pair<_GUID const,_tag_FW_HYPERV_CONFIG_STORE *>>,0>>::find(
          v10,
          &v26,
          v6 + v29);
        if ( (_QWORD)v26 == *v10 )
        {
          v2 = -2147023537;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              142,
              WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
              2147943759LL);
          break;
        }
        *(_QWORD *)&v28 = *(_QWORD *)(v26 + 48);
        for ( k = 1; k < 3; ++k )
        {
          v26 = *(_OWORD *)(v6 + v29);
          HyperVVMConfigFromRegistry = FwGetHyperVVMConfigFromRegistry(v30, (unsigned int)k, &v26, &v31, &v33);
          v13 = &v31;
          if ( HyperVVMConfigFromRegistry < 0 )
            v13 = 0;
          FwHyperVMgrSetVMConfigValue(v28, (unsigned int)k, v13);
          if ( (int)(HyperVVMConfigFromRegistry + 0x80000000) >= 0
            && HyperVVMConfigFromRegistry != -2147024894
            && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            LODWORD(v22) = HyperVVMConfigFromRegistry;
            LODWORD(v20) = k;
            WPP_SF__guid_dd(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              143,
              WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
              v6 + v29,
              v20,
              v22);
          }
        }
        for ( m = 0; m < 3; ++m )
        {
          ProfileTypeFromProfileIndex = FwGetProfileTypeFromProfileIndex(m);
          v16 = ProfileTypeFromProfileIndex;
          v24 = ProfileTypeFromProfileIndex;
          v17 = 1;
          v23 = 1;
          do
          {
            v26 = *(_OWORD *)(v6 + v29);
            LODWORD(v26) = FwGetHyperVProfileConfigFromRegistry(v30, v16, (unsigned int)v17, &v26, &v31, &v33);
            v18 = &v31;
            if ( (int)v26 < 0 )
              v18 = 0;
            FwHyperVMgrSetProfileConfigValue(v28, m, v23, v18);
            if ( (int)(v26 + 0x80000000) >= 0
              && (_DWORD)v26 != -2147024894
              && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              LODWORD(v22) = v23;
              LODWORD(v21) = v24;
              WPP_SF__guid_ddd(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                144,
                WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                v6 + v29,
                v21,
                v22,
                v26);
            }
            v2 = 0;
            v17 = v23 + 1;
            v23 = v17;
            v16 = v24;
          }
          while ( v17 < 5 );
        }
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v4 = 139;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v4 = 138;
LABEL_5:
      WPP_SF_d(
        *(_QWORD *)(v3 + 16),
        v4,
        WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
        (unsigned int)HyperVVMCreatorIdsFromRegistry);
    }
  }
LABEL_51:
  if ( v30 )
    FwClosePolicyStore(v30);
  FwFree(v29);
  return v2;
}

```

## disassembly

```asm
0x18000f04c  mov     r11, rsp
0x18000f04f  mov     [r11+10h], rbx
0x18000f053  mov     [r11+18h], rsi
0x18000f057  push    r12
0x18000f059  push    r13
0x18000f05b  push    r14
0x18000f05d  sub     rsp, 0B0h
0x18000f064  mov     rax, cs:__security_cookie
0x18000f06b  xor     rax, rsp
0x18000f06e  mov     [rsp+0C8h+var_20], rax
0x18000f076  mov     [rsp+0C8h+var_68], ecx
0x18000f07a  mov     dword ptr [r11-28h], 4
0x18000f082  xor     esi, esi
0x18000f084  mov     [r11-38h], rsi
0x18000f088  mov     [r11-2Ch], esi
0x18000f08c  mov     [r11-40h], rsi
0x18000f090  mov     [r11-30h], esi
0x18000f094  lea     r9, [r11-38h]
0x18000f098  xor     r8d, r8d
0x18000f09b  lea     edx, [rsi+2]
0x18000f09e  call    cs:__imp_FwOpenPolicyStore
0x18000f0a5  nop     dword ptr [rax+rax+00h]
0x18000f0aa  mov     ebx, eax
0x18000f0ac  test    eax, eax
0x18000f0ae  jns     short loc_18000F0EE
0x18000f0b0  lea     r14, WPP_GLOBAL_Control
0x18000f0b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0be  cmp     rcx, r14
0x18000f0c1  jz      loc_18000F47F
0x18000f0c7  test    byte ptr [rcx+1Ch], 1
0x18000f0cb  jz      loc_18000F47F
0x18000f0d1  mov     edx, 8Ah
0x18000f0d6  mov     r9d, eax
0x18000f0d9  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18000f0e0  mov     rcx, [rcx+10h]
0x18000f0e4  call    WPP_SF_d
0x18000f0e9  jmp     loc_18000F47F
0x18000f0ee  lea     r8, [rsp+0C8h+var_40]
0x18000f0f6  lea     rdx, [rsp+0C8h+var_2C]
0x18000f0fe  mov     rcx, [rsp+0C8h+var_38]
0x18000f106  call    cs:__imp_FwGetHyperVVMCreatorIdsFromRegistry
0x18000f10d  nop     dword ptr [rax+rax+00h]
0x18000f112  mov     ebx, eax
0x18000f114  test    eax, eax
0x18000f116  jns     short loc_18000F140
0x18000f118  lea     r14, WPP_GLOBAL_Control
0x18000f11f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f126  cmp     rcx, r14
0x18000f129  jz      loc_18000F47F
0x18000f12f  test    byte ptr [rcx+1Ch], 1
0x18000f133  jz      loc_18000F47F
0x18000f139  mov     edx, 8Bh
0x18000f13e  jmp     short loc_18000F0D6
0x18000f140  mov     eax, esi
0x18000f142  lea     r14, WPP_GLOBAL_Control
0x18000f149  mov     [rsp+0C8h+var_80], eax
0x18000f14d  cmp     eax, [rsp+0C8h+var_2C]
0x18000f154  jnb     loc_18000F479
0x18000f15a  mov     r12d, eax
0x18000f15d  shl     r12, 4
0x18000f161  mov     rcx, [rsp+0C8h+var_40]
0x18000f169  add     rcx, r12
0x18000f16c  xor     edx, edx
0x18000f16e  call    FwHyperVMgrInitializeVMCreator
0x18000f173  mov     ebx, eax
0x18000f175  test    eax, eax
0x18000f177  jns     short loc_18000F1A9
0x18000f179  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f180  cmp     rcx, r14
0x18000f183  jz      short loc_18000F1A4
0x18000f185  test    byte ptr [rcx+1Ch], 1
0x18000f189  jz      short loc_18000F1A4
0x18000f18b  mov     edx, 8Ch
0x18000f190  mov     r9d, eax
0x18000f193  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18000f19a  mov     rcx, [rcx+10h]
0x18000f19e  call    WPP_SF_d
0x18000f1a3  nop
0x18000f1a4  jmp     loc_18000F47F
0x18000f1a9  mov     r13d, 1
0x18000f1af  cmp     r13d, 3
0x18000f1b3  jg      short loc_18000F21F
0x18000f1b5  mov     rax, [rsp+0C8h+var_40]
0x18000f1bd  movups  xmm0, xmmword ptr [r12+rax]
0x18000f1c2  movdqu  [rsp+0C8h+var_58], xmm0
0x18000f1c8  lea     r8, [rsp+0C8h+var_58]
0x18000f1cd  mov     edx, r13d
0x18000f1d0  mov     rcx, [rsp+0C8h+var_38]
0x18000f1d8  call    cs:__imp_FwUpgradeHyperVVMConfigToProfileConfig
0x18000f1df  nop     dword ptr [rax+rax+00h]
0x18000f1e4  mov     ebx, eax
0x18000f1e6  test    eax, eax
0x18000f1e8  jns     short loc_18000F21A
0x18000f1ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1f1  cmp     rcx, r14
0x18000f1f4  jz      short loc_18000F215
0x18000f1f6  test    byte ptr [rcx+1Ch], 1
0x18000f1fa  jz      short loc_18000F215
0x18000f1fc  mov     edx, 8Dh
0x18000f201  mov     r9d, eax
0x18000f204  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18000f20b  mov     rcx, [rcx+10h]
0x18000f20f  call    WPP_SF_d
0x18000f214  nop
0x18000f215  jmp     loc_18000F47F
0x18000f21a  inc     r13d
0x18000f21d  jmp     short loc_18000F1AF
0x18000f21f  mov     qword ptr [rsp+0C8h+var_78], rsi
0x18000f224  movsxd  rbx, [rsp+0C8h+var_68]
0x18000f229  shl     rbx, 5
0x18000f22d  lea     rcx, qword_180132B58
0x18000f234  add     rbx, rcx
0x18000f237  mov     r8, [rsp+0C8h+var_40]
0x18000f23f  add     r8, r12
0x18000f242  lea     rdx, [rsp+0C8h+var_78]
0x18000f247  mov     rcx, rbx
0x18000f24a  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAU_tag_FW_HYPERV_CONFIG_STORE@@UGuidComparer@@V?$allocator@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_CONFIG_STORE@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_CONFIG_STORE@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,_tag_FW_HYPERV_CONFIG_STORE *,GuidComparer,std::allocator<std::pair<_GUID const,_tag_FW_HYPERV_CONFIG_STORE *>>,0>>::find(_GUID const &)
0x18000f24f  mov     rax, qword ptr [rsp+0C8h+var_78]
0x18000f254  cmp     rax, [rbx]
0x18000f257  jnz     short loc_18000F28E
0x18000f259  mov     ebx, 8007054Fh
0x18000f25e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f265  cmp     rcx, r14
0x18000f268  jz      short loc_18000F289
0x18000f26a  test    byte ptr [rcx+1Ch], 1
0x18000f26e  jz      short loc_18000F289
0x18000f270  mov     edx, 8Eh
0x18000f275  mov     r9d, ebx
0x18000f278  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18000f27f  mov     rcx, [rcx+10h]
0x18000f283  call    WPP_SF_d
0x18000f288  nop
0x18000f289  jmp     loc_18000F47F
0x18000f28e  mov     rax, [rax+30h]
0x18000f292  mov     qword ptr [rsp+0C8h+var_58], rax
0x18000f297  mov     ebx, 1
0x18000f29c  mov     rax, [rsp+0C8h+var_40]
0x18000f2a4  movups  xmm0, xmmword ptr [r12+rax]
0x18000f2a9  movdqu  [rsp+0C8h+var_78], xmm0
0x18000f2af  lea     rax, [rsp+0C8h+var_28]
0x18000f2b7  mov     [rsp+0C8h+var_A8], rax
0x18000f2bc  lea     r9, [rsp+0C8h+var_30]
0x18000f2c4  lea     r8, [rsp+0C8h+var_78]
0x18000f2c9  mov     edx, ebx
0x18000f2cb  mov     rcx, [rsp+0C8h+var_38]
0x18000f2d3  call    cs:__imp_FwGetHyperVVMConfigFromRegistry
0x18000f2da  nop     dword ptr [rax+rax+00h]
0x18000f2df  mov     r13d, eax
0x18000f2e2  lea     r8, [rsp+0C8h+var_30]
0x18000f2ea  test    eax, eax
0x18000f2ec  cmovs   r8, rsi
0x18000f2f0  mov     edx, ebx
0x18000f2f2  mov     rcx, qword ptr [rsp+0C8h+var_58]
0x18000f2f7  call    FwHyperVMgrSetVMConfigValue
0x18000f2fc  mov     eax, 80000000h
0x18000f301  lea     ecx, [rax+r13]
0x18000f305  test    eax, ecx
0x18000f307  jnz     short loc_18000F34D
0x18000f309  cmp     r13d, 80070002h
0x18000f310  jz      short loc_18000F34D
0x18000f312  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f319  cmp     rcx, r14
0x18000f31c  jz      short loc_18000F34D
0x18000f31e  test    byte ptr [rcx+1Ch], 1
0x18000f322  jz      short loc_18000F34D
0x18000f324  mov     r9, [rsp+0C8h+var_40]
0x18000f32c  add     r9, r12
0x18000f32f  mov     edx, 8Fh
0x18000f334  mov     dword ptr [rsp+0C8h+var_A0], r13d
0x18000f339  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x18000f33d  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18000f344  mov     rcx, [rcx+10h]
0x18000f348  call    WPP_SF__guid_dd
0x18000f34d  inc     ebx
0x18000f34f  cmp     ebx, 3
0x18000f352  jl      loc_18000F29C
0x18000f358  mov     r13d, esi
0x18000f35b  mov     ecx, r13d
0x18000f35e  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x18000f365  nop     dword ptr [rax+rax+00h]
0x18000f36a  mov     edx, eax
0x18000f36c  mov     [rsp+0C8h+var_84], eax
0x18000f370  mov     eax, 1
0x18000f375  mov     [rsp+0C8h+var_88], eax
0x18000f379  mov     rcx, [rsp+0C8h+var_40]
0x18000f381  movups  xmm0, xmmword ptr [r12+rcx]
0x18000f386  movdqu  [rsp+0C8h+var_78], xmm0
0x18000f38c  lea     rcx, [rsp+0C8h+var_28]
0x18000f394  mov     [rsp+0C8h+var_A0], rcx
0x18000f399  lea     rcx, [rsp+0C8h+var_30]
0x18000f3a1  mov     [rsp+0C8h+var_A8], rcx
0x18000f3a6  lea     r9, [rsp+0C8h+var_78]
0x18000f3ab  mov     r8d, eax
0x18000f3ae  mov     rcx, [rsp+0C8h+var_38]
0x18000f3b6  call    cs:__imp_FwGetHyperVProfileConfigFromRegistry
0x18000f3bd  nop     dword ptr [rax+rax+00h]
0x18000f3c2  mov     dword ptr [rsp+0C8h+var_78], eax
0x18000f3c6  lea     r9, [rsp+0C8h+var_30]
0x18000f3ce  test    eax, eax
0x18000f3d0  cmovs   r9, rsi
0x18000f3d4  mov     ebx, [rsp+0C8h+var_88]
0x18000f3d8  mov     r8d, ebx
0x18000f3db  mov     edx, r13d
0x18000f3de  mov     rcx, qword ptr [rsp+0C8h+var_58]
0x18000f3e3  call    FwHyperVMgrSetProfileConfigValue
0x18000f3e8  mov     r8d, dword ptr [rsp+0C8h+var_78]
0x18000f3ed  mov     r9d, 80000000h
0x18000f3f3  lea     ecx, [r8+r9]
0x18000f3f7  test    r9d, ecx
0x18000f3fa  jnz     short loc_18000F448
0x18000f3fc  cmp     r8d, 80070002h
0x18000f403  jz      short loc_18000F448
0x18000f405  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f40c  cmp     rcx, r14
0x18000f40f  jz      short loc_18000F448
0x18000f411  test    byte ptr [rcx+1Ch], 1
0x18000f415  jz      short loc_18000F448
0x18000f417  mov     r9, [rsp+0C8h+var_40]
0x18000f41f  add     r9, r12
0x18000f422  mov     edx, 90h
0x18000f427  mov     [rsp+0C8h+var_98], r8d
0x18000f42c  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x18000f430  mov     eax, [rsp+0C8h+var_84]
0x18000f434  mov     dword ptr [rsp+0C8h+var_A8], eax
0x18000f438  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18000f43f  mov     rcx, [rcx+10h]
0x18000f443  call    WPP_SF__guid_ddd
0x18000f448  mov     ebx, esi
0x18000f44a  mov     eax, [rsp+0C8h+var_88]
0x18000f44e  inc     eax
0x18000f450  mov     [rsp+0C8h+var_88], eax
0x18000f454  cmp     eax, 5
0x18000f457  mov     edx, [rsp+0C8h+var_84]
0x18000f45b  jl      loc_18000F379
0x18000f461  inc     r13d
0x18000f464  cmp     r13d, 3
0x18000f468  jb      loc_18000F35B
0x18000f46e  mov     eax, [rsp+0C8h+var_80]
0x18000f472  inc     eax
0x18000f474  jmp     loc_18000F149
0x18000f479  jmp     short loc_18000F47F
0x18000f47b  mov     ebx, dword ptr [rsp+0C8h+var_78]
0x18000f47f  mov     rcx, [rsp+0C8h+var_38]
0x18000f487  test    rcx, rcx
0x18000f48a  jz      short loc_18000F498
0x18000f48c  call    cs:__imp_FwClosePolicyStore
0x18000f493  nop     dword ptr [rax+rax+00h]
0x18000f498  mov     rcx, [rsp+0C8h+var_40]
0x18000f4a0  call    cs:__imp_FwFree
0x18000f4a7  nop     dword ptr [rax+rax+00h]
0x18000f4ac  mov     eax, ebx
0x18000f4ae  mov     rcx, [rsp+0C8h+var_20]
0x18000f4b6  xor     rcx, rsp; StackCookie
0x18000f4b9  call    __security_check_cookie
0x18000f4be  lea     r11, [rsp+0C8h+var_18]
0x18000f4c6  mov     rbx, [r11+28h]
0x18000f4ca  mov     rsi, [r11+30h]
0x18000f4ce  mov     rsp, r11
0x18000f4d1  pop     r14
0x18000f4d3  pop     r13
0x18000f4d5  pop     r12
0x18000f4d7  retn
```
