# FwLoadAllConfigsFromStoreRegistry

- ea: `0x180036518`
- end: `0x18003698a`
- name: `FwLoadAllConfigsFromStoreRegistry`
- size: `1138`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800362e4`

## callees

- `0x18000af3c`
- `0x1800362b0`
- `0x180036518`
- `0x180038b34`
- `0x180043f78`
- `0x18006f520`
- `0x18007ed10`
- `0x180080468`
- `0x180080830`
- `0x180081444`

## import_xrefs

- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800367f6`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800367f6`
- `fwbase!FwFree` at `0x180036958`
- `fwbase!FwFree` at `0x180036958`
- `FWPolicyIOMgr!FwGetHyperVProfileConfigFromRegistry` at `0x180036848`
- `FWPolicyIOMgr!FwGetHyperVProfileConfigFromRegistry` at `0x180036848`
- `FWPolicyIOMgr!FwGetHyperVVMCreatorIdsFromRegistry` at `0x1800365cc`
- `FWPolicyIOMgr!FwGetHyperVVMCreatorIdsFromRegistry` at `0x1800365cc`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x18003694a`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x18003694a`
- `FWPolicyIOMgr!FwGetHyperVVMConfigFromRegistry` at `0x180036771`
- `FWPolicyIOMgr!FwGetHyperVVMConfigFromRegistry` at `0x180036771`
- `FWPolicyIOMgr!FwUpgradeHyperVVMConfigToProfileConfig` at `0x180036698`
- `FWPolicyIOMgr!FwUpgradeHyperVVMConfigToProfileConfig` at `0x180036698`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x18003656a`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x18003656a`

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
  const void *v10; // rbx
  const void *v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rcx
  int k; // ebx
  int HyperVVMConfigFromRegistry; // r13d
  int *v16; // r8
  unsigned int m; // r13d
  unsigned int ProfileTypeFromProfileIndex; // eax
  __int64 v19; // rdx
  int v20; // eax
  int *v21; // r9
  __int64 v23; // [rsp+20h] [rbp-B8h]
  __int64 v24; // [rsp+20h] [rbp-B8h]
  __int64 v25; // [rsp+28h] [rbp-B0h]
  unsigned int v26; // [rsp+40h] [rbp-98h]
  int HyperVProfileConfigFromRegistry; // [rsp+44h] [rbp-94h]
  unsigned int v28; // [rsp+48h] [rbp-90h]
  unsigned int v29; // [rsp+4Ch] [rbp-8Ch]
  int v30; // [rsp+50h] [rbp-88h]
  __int128 v31; // [rsp+60h] [rbp-78h] BYREF
  __int128 v32; // [rsp+70h] [rbp-68h] BYREF
  __int64 v33; // [rsp+80h] [rbp-58h]
  __int64 v34; // [rsp+98h] [rbp-40h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-38h] BYREF
  int v36; // [rsp+A8h] [rbp-30h] BYREF
  unsigned int v37; // [rsp+ACh] [rbp-2Ch] BYREF
  int v38; // [rsp+B0h] [rbp-28h] BYREF

  v30 = a1;
  v38 = 4;
  v35 = 0;
  v37 = 0;
  v34 = 0;
  v36 = 0;
  HyperVVMCreatorIdsFromRegistry = FwOpenPolicyStore(a1, 2, 0, &v35);
  v2 = HyperVVMCreatorIdsFromRegistry;
  if ( HyperVVMCreatorIdsFromRegistry >= 0 )
  {
    HyperVVMCreatorIdsFromRegistry = FwGetHyperVVMCreatorIdsFromRegistry(v35, &v37, &v34);
    v2 = HyperVVMCreatorIdsFromRegistry;
    if ( HyperVVMCreatorIdsFromRegistry >= 0 )
    {
      for ( i = 0; ; i = v29 + 1 )
      {
        v29 = i;
        if ( i >= v37 )
          break;
        v6 = 16LL * i;
        v7 = FwHyperVMgrInitializeVMCreator(v6 + v34, 0);
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
          v31 = *(_OWORD *)(v6 + v34);
          v9 = FwUpgradeHyperVVMConfigToProfileConfig(v35, (unsigned int)j, &v31);
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
        v10 = (const void *)(v6 + v34);
        std::_Tree<std::_Tmap_traits<_GUID,_tag_FW_HYPERV_CONFIG_STORE *,GuidComparer,std::allocator<std::pair<_GUID const,_tag_FW_HYPERV_CONFIG_STORE *>>,0>>::_Find_lower_bound<_GUID>(
          (__int64)&qword_18012C988[4 * v30],
          &v32,
          (const void *)(v6 + v34));
        v11 = v10;
        v12 = v33;
        if ( !std::_Tree<std::_Tmap_traits<_GUID,_tag_FW_DYNAMIC_KEYWORD_ADDRESS_INTERNAL *,GuidComparer,std::allocator<std::pair<_GUID const,_tag_FW_DYNAMIC_KEYWORD_ADDRESS_INTERNAL *>>,0>>::_Lower_bound_duplicate<_GUID>(
                v13,
                v33,
                v11)
          || v12 == qword_18012C988[4 * v30] )
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
        *(_QWORD *)&v31 = *(_QWORD *)(v12 + 48);
        for ( k = 1; k < 3; ++k )
        {
          v32 = *(_OWORD *)(v6 + v34);
          HyperVVMConfigFromRegistry = FwGetHyperVVMConfigFromRegistry(v35, (unsigned int)k, &v32, &v36, &v38);
          v16 = &v36;
          if ( HyperVVMConfigFromRegistry < 0 )
            v16 = 0;
          FwHyperVMgrSetVMConfigValue(v31, (unsigned int)k, v16);
          if ( (int)(HyperVVMConfigFromRegistry + 0x80000000) >= 0
            && HyperVVMConfigFromRegistry != -2147024894
            && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            LODWORD(v25) = HyperVVMConfigFromRegistry;
            LODWORD(v23) = k;
            WPP_SF__guid_dd(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              143,
              WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
              v6 + v34,
              v23,
              v25);
          }
        }
        for ( m = 0; m < 3; ++m )
        {
          ProfileTypeFromProfileIndex = FwGetProfileTypeFromProfileIndex(m);
          v19 = ProfileTypeFromProfileIndex;
          v28 = ProfileTypeFromProfileIndex;
          v20 = 1;
          v26 = 1;
          do
          {
            v32 = *(_OWORD *)(v6 + v34);
            HyperVProfileConfigFromRegistry = FwGetHyperVProfileConfigFromRegistry(
                                                v35,
                                                v19,
                                                (unsigned int)v20,
                                                &v32,
                                                &v36,
                                                &v38);
            v21 = &v36;
            if ( HyperVProfileConfigFromRegistry < 0 )
              v21 = 0;
            FwHyperVMgrSetProfileConfigValue(v31, m, v26, v21);
            if ( (int)(HyperVProfileConfigFromRegistry + 0x80000000) >= 0
              && HyperVProfileConfigFromRegistry != -2147024894
              && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              LODWORD(v25) = v26;
              LODWORD(v24) = v28;
              WPP_SF__guid_ddd(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                144,
                WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                v6 + v34,
                v24,
                v25,
                HyperVProfileConfigFromRegistry);
            }
            v2 = 0;
            v20 = v26 + 1;
            v26 = v20;
            v19 = v28;
          }
          while ( v20 < 5 );
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
  if ( v35 )
    FwClosePolicyStore(v35);
  FwFree(v34);
  return v2;
}

```

## disassembly

```asm
0x180036518  mov     r11, rsp
0x18003651b  mov     [r11+10h], rbx
0x18003651f  mov     [r11+18h], rsi
0x180036523  push    r12
0x180036525  push    r13
0x180036527  push    r14
0x180036529  sub     rsp, 0C0h
0x180036530  mov     rax, cs:__security_cookie
0x180036537  xor     rax, rsp
0x18003653a  mov     [rsp+0D8h+var_20], rax
0x180036542  mov     [rsp+0D8h+var_88], ecx
0x180036546  mov     dword ptr [r11-28h], 4
0x18003654e  xor     esi, esi
0x180036550  mov     [r11-38h], rsi
0x180036554  mov     [r11-2Ch], esi
0x180036558  mov     [r11-40h], rsi
0x18003655c  mov     [r11-30h], esi
0x180036560  lea     r9, [r11-38h]
0x180036564  xor     r8d, r8d
0x180036567  lea     edx, [rsi+2]
0x18003656a  call    cs:__imp_FwOpenPolicyStore
0x180036570  mov     ebx, eax
0x180036572  test    eax, eax
0x180036574  jns     short loc_1800365B4
0x180036576  lea     r14, WPP_GLOBAL_Control
0x18003657d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036584  cmp     rcx, r14
0x180036587  jz      loc_18003693D
0x18003658d  test    byte ptr [rcx+1Ch], 1
0x180036591  jz      loc_18003693D
0x180036597  mov     edx, 8Ah
0x18003659c  mov     r9d, eax
0x18003659f  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800365a6  mov     rcx, [rcx+10h]
0x1800365aa  call    WPP_SF_d
0x1800365af  jmp     loc_18003693D
0x1800365b4  lea     r8, [rsp+0D8h+var_40]
0x1800365bc  lea     rdx, [rsp+0D8h+var_2C]
0x1800365c4  mov     rcx, [rsp+0D8h+var_38]
0x1800365cc  call    cs:__imp_FwGetHyperVVMCreatorIdsFromRegistry
0x1800365d2  mov     ebx, eax
0x1800365d4  test    eax, eax
0x1800365d6  jns     short loc_180036600
0x1800365d8  lea     r14, WPP_GLOBAL_Control
0x1800365df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365e6  cmp     rcx, r14
0x1800365e9  jz      loc_18003693D
0x1800365ef  test    byte ptr [rcx+1Ch], 1
0x1800365f3  jz      loc_18003693D
0x1800365f9  mov     edx, 8Bh
0x1800365fe  jmp     short loc_18003659C
0x180036600  mov     eax, esi
0x180036602  lea     r14, WPP_GLOBAL_Control
0x180036609  mov     [rsp+0D8h+var_8C], eax
0x18003660d  cmp     eax, [rsp+0D8h+var_2C]
0x180036614  jnb     loc_180036937
0x18003661a  mov     r12d, eax
0x18003661d  shl     r12, 4
0x180036621  mov     rcx, [rsp+0D8h+var_40]
0x180036629  add     rcx, r12
0x18003662c  xor     edx, edx
0x18003662e  call    FwHyperVMgrInitializeVMCreator
0x180036633  mov     ebx, eax
0x180036635  test    eax, eax
0x180036637  jns     short loc_180036669
0x180036639  mov     rcx, cs:WPP_GLOBAL_Control
0x180036640  cmp     rcx, r14
0x180036643  jz      short loc_180036664
0x180036645  test    byte ptr [rcx+1Ch], 1
0x180036649  jz      short loc_180036664
0x18003664b  mov     edx, 8Ch
0x180036650  mov     r9d, eax
0x180036653  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18003665a  mov     rcx, [rcx+10h]
0x18003665e  call    WPP_SF_d
0x180036663  nop
0x180036664  jmp     loc_18003693D
0x180036669  mov     r13d, 1
0x18003666f  cmp     r13d, 3
0x180036673  jg      short loc_1800366D9
0x180036675  mov     rax, [rsp+0D8h+var_40]
0x18003667d  movups  xmm0, xmmword ptr [r12+rax]
0x180036682  movdqu  [rsp+0D8h+var_78], xmm0
0x180036688  lea     r8, [rsp+0D8h+var_78]
0x18003668d  mov     edx, r13d
0x180036690  mov     rcx, [rsp+0D8h+var_38]
0x180036698  call    cs:__imp_FwUpgradeHyperVVMConfigToProfileConfig
0x18003669e  mov     ebx, eax
0x1800366a0  test    eax, eax
0x1800366a2  jns     short loc_1800366D4
0x1800366a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366ab  cmp     rcx, r14
0x1800366ae  jz      short loc_1800366CF
0x1800366b0  test    byte ptr [rcx+1Ch], 1
0x1800366b4  jz      short loc_1800366CF
0x1800366b6  mov     edx, 8Dh
0x1800366bb  mov     r9d, eax
0x1800366be  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800366c5  mov     rcx, [rcx+10h]
0x1800366c9  call    WPP_SF_d
0x1800366ce  nop
0x1800366cf  jmp     loc_18003693D
0x1800366d4  inc     r13d
0x1800366d7  jmp     short loc_18003666F
0x1800366d9  movsxd  r13, [rsp+0D8h+var_88]
0x1800366de  shl     r13, 5
0x1800366e2  lea     rcx, qword_18012C988
0x1800366e9  add     r13, rcx
0x1800366ec  mov     rbx, [rsp+0D8h+var_40]
0x1800366f4  add     rbx, r12
0x1800366f7  mov     r8, rbx
0x1800366fa  lea     rdx, [rsp+0D8h+var_68]
0x1800366ff  mov     rcx, r13
0x180036702  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAU_tag_FW_HYPERV_CONFIG_STORE@@UGuidComparer@@V?$allocator@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_CONFIG_STORE@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_CONFIG_STORE@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,_tag_FW_HYPERV_CONFIG_STORE *,GuidComparer,std::allocator<std::pair<_GUID const,_tag_FW_HYPERV_CONFIG_STORE *>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x180036707  mov     r8, rbx
0x18003670a  mov     rbx, [rsp+0D8h+var_58]
0x180036712  mov     rdx, rbx
0x180036715  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAU_tag_FW_DYNAMIC_KEYWORD_ADDRESS_INTERNAL@@UGuidComparer@@V?$allocator@U?$pair@$$CBU_GUID@@PEAU_tag_FW_DYNAMIC_KEYWORD_ADDRESS_INTERNAL@@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAU_tag_FW_DYNAMIC_KEYWORD_ADDRESS_INTERNAL@@@std@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,_tag_FW_DYNAMIC_KEYWORD_ADDRESS_INTERNAL *,GuidComparer,std::allocator<std::pair<_GUID const,_tag_FW_DYNAMIC_KEYWORD_ADDRESS_INTERNAL *>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,_tag_FW_DYNAMIC_KEYWORD_ADDRESS_INTERNAL *>,void *> * const,_GUID const &)
0x18003671a  test    al, al
0x18003671c  jz      loc_180036905
0x180036722  cmp     rbx, [r13+0]
0x180036726  jz      loc_180036905
0x18003672c  mov     rax, [rbx+30h]
0x180036730  mov     qword ptr [rsp+0D8h+var_78], rax
0x180036735  mov     ebx, 1
0x18003673a  mov     rax, [rsp+0D8h+var_40]
0x180036742  movups  xmm0, xmmword ptr [r12+rax]
0x180036747  movdqu  [rsp+0D8h+var_68], xmm0
0x18003674d  lea     rax, [rsp+0D8h+var_28]
0x180036755  mov     [rsp+0D8h+var_B8], rax
0x18003675a  lea     r9, [rsp+0D8h+var_30]
0x180036762  lea     r8, [rsp+0D8h+var_68]
0x180036767  mov     edx, ebx
0x180036769  mov     rcx, [rsp+0D8h+var_38]
0x180036771  call    cs:__imp_FwGetHyperVVMConfigFromRegistry
0x180036777  mov     r13d, eax
0x18003677a  lea     r8, [rsp+0D8h+var_30]
0x180036782  test    eax, eax
0x180036784  cmovs   r8, rsi
0x180036788  mov     edx, ebx
0x18003678a  mov     rcx, qword ptr [rsp+0D8h+var_78]
0x18003678f  call    FwHyperVMgrSetVMConfigValue
0x180036794  mov     eax, 80000000h
0x180036799  lea     ecx, [rax+r13]
0x18003679d  test    eax, ecx
0x18003679f  jnz     short loc_1800367E5
0x1800367a1  cmp     r13d, 80070002h
0x1800367a8  jz      short loc_1800367E5
0x1800367aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367b1  cmp     rcx, r14
0x1800367b4  jz      short loc_1800367E5
0x1800367b6  test    byte ptr [rcx+1Ch], 1
0x1800367ba  jz      short loc_1800367E5
0x1800367bc  mov     r9, [rsp+0D8h+var_40]
0x1800367c4  add     r9, r12
0x1800367c7  mov     edx, 8Fh
0x1800367cc  mov     dword ptr [rsp+0D8h+var_B0], r13d
0x1800367d1  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x1800367d5  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800367dc  mov     rcx, [rcx+10h]
0x1800367e0  call    WPP_SF__guid_dd
0x1800367e5  inc     ebx
0x1800367e7  cmp     ebx, 3
0x1800367ea  jl      loc_18003673A
0x1800367f0  mov     r13d, esi
0x1800367f3  mov     ecx, r13d
0x1800367f6  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x1800367fc  mov     edx, eax
0x1800367fe  mov     [rsp+0D8h+var_90], eax
0x180036802  mov     eax, 1
0x180036807  mov     [rsp+0D8h+var_98], eax
0x18003680b  mov     rcx, [rsp+0D8h+var_40]
0x180036813  movups  xmm0, xmmword ptr [r12+rcx]
0x180036818  movdqu  [rsp+0D8h+var_68], xmm0
0x18003681e  lea     rcx, [rsp+0D8h+var_28]
0x180036826  mov     [rsp+0D8h+var_B0], rcx
0x18003682b  lea     rcx, [rsp+0D8h+var_30]
0x180036833  mov     [rsp+0D8h+var_B8], rcx
0x180036838  lea     r9, [rsp+0D8h+var_68]
0x18003683d  mov     r8d, eax
0x180036840  mov     rcx, [rsp+0D8h+var_38]
0x180036848  call    cs:__imp_FwGetHyperVProfileConfigFromRegistry
0x18003684e  mov     [rsp+0D8h+var_94], eax
0x180036852  lea     r9, [rsp+0D8h+var_30]
0x18003685a  test    eax, eax
0x18003685c  cmovs   r9, rsi
0x180036860  mov     ebx, [rsp+0D8h+var_98]
0x180036864  mov     r8d, ebx
0x180036867  mov     edx, r13d
0x18003686a  mov     rcx, qword ptr [rsp+0D8h+var_78]
0x18003686f  call    FwHyperVMgrSetProfileConfigValue
0x180036874  mov     r8d, [rsp+0D8h+var_94]
0x180036879  mov     r9d, 80000000h
0x18003687f  lea     ecx, [r8+r9]
0x180036883  test    r9d, ecx
0x180036886  jnz     short loc_1800368D4
0x180036888  cmp     r8d, 80070002h
0x18003688f  jz      short loc_1800368D4
0x180036891  mov     rcx, cs:WPP_GLOBAL_Control
0x180036898  cmp     rcx, r14
0x18003689b  jz      short loc_1800368D4
0x18003689d  test    byte ptr [rcx+1Ch], 1
0x1800368a1  jz      short loc_1800368D4
0x1800368a3  mov     r9, [rsp+0D8h+var_40]
0x1800368ab  add     r9, r12
0x1800368ae  mov     edx, 90h
0x1800368b3  mov     [rsp+0D8h+var_A8], r8d
0x1800368b8  mov     dword ptr [rsp+0D8h+var_B0], ebx
0x1800368bc  mov     eax, [rsp+0D8h+var_90]
0x1800368c0  mov     dword ptr [rsp+0D8h+var_B8], eax
0x1800368c4  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800368cb  mov     rcx, [rcx+10h]
0x1800368cf  call    WPP_SF__guid_ddd
0x1800368d4  mov     ebx, esi
0x1800368d6  mov     eax, [rsp+0D8h+var_98]
0x1800368da  inc     eax
0x1800368dc  mov     [rsp+0D8h+var_98], eax
0x1800368e0  cmp     eax, 5
0x1800368e3  mov     edx, [rsp+0D8h+var_90]
0x1800368e7  jl      loc_18003680B
0x1800368ed  inc     r13d
0x1800368f0  cmp     r13d, 3
0x1800368f4  jb      loc_1800367F3
0x1800368fa  mov     eax, [rsp+0D8h+var_8C]
0x1800368fe  inc     eax
0x180036900  jmp     loc_180036609
0x180036905  mov     ebx, 8007054Fh
0x18003690a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036911  cmp     rcx, r14
0x180036914  jz      short loc_180036935
0x180036916  test    byte ptr [rcx+1Ch], 1
0x18003691a  jz      short loc_180036935
0x18003691c  mov     edx, 8Eh
0x180036921  mov     r9d, ebx
0x180036924  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18003692b  mov     rcx, [rcx+10h]
0x18003692f  call    WPP_SF_d
0x180036934  nop
0x180036935  jmp     short loc_18003693D
0x180036937  jmp     short loc_18003693D
0x180036939  mov     ebx, [rsp+0D8h+var_94]
0x18003693d  mov     rcx, [rsp+0D8h+var_38]
0x180036945  test    rcx, rcx
0x180036948  jz      short loc_180036950
0x18003694a  call    cs:__imp_FwClosePolicyStore
0x180036950  mov     rcx, [rsp+0D8h+var_40]
0x180036958  call    cs:__imp_FwFree
0x18003695e  mov     eax, ebx
0x180036960  mov     rcx, [rsp+0D8h+var_20]
0x180036968  xor     rcx, rsp; StackCookie
0x18003696b  call    __security_check_cookie
0x180036970  lea     r11, [rsp+0D8h+var_18]
0x180036978  mov     rbx, [r11+28h]
0x18003697c  mov     rsi, [r11+30h]
0x180036980  mov     rsp, r11
0x180036983  pop     r14
0x180036985  pop     r13
0x180036987  pop     r12
0x180036989  retn
```
