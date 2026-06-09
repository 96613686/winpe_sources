# SvrImpl_FWGetGlobalConfig2_10(void *,ushort,_tag_FW_STORE_TYPE,_tag_FW_GLOBAL_CONFIG,ulong,uchar *,ulong *,_tag_FW_RULE_ORIGIN_TYPE *)

- ea: `0x180033580`
- end: `0x1800339d1`
- name: `?SvrImpl_FWGetGlobalConfig2_10@@YAKPEAXGW4_tag_FW_STORE_TYPE@@W4_tag_FW_GLOBAL_CONFIG@@KPEAEPEAKPEAW4_tag_FW_RULE_ORIGIN_TYPE@@@Z`
- size: `1105`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800321c0`
- `0x180033100`

## callees

- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000ae9c`
- `0x18000af3c`
- `0x180030db8`
- `0x180033580`
- `0x1800533bc`
- `0x1800a1600`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800339ba`
- `fwbase!FwHResultToWindowsError` at `0x1800339ba`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x1800339a6`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x1800339a6`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x18003387d`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x180033917`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x18003387d`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x180033917`
- `FWPolicyIOMgr!FWGPLock` at `0x1800335be`
- `FWPolicyIOMgr!FWGPLock` at `0x1800335be`

## string_xrefs

- `0x180033597`: `SvrImpl_FWGetGlobalConfig2_10`
- `0x180033988`: `SvrImpl_FWGetGlobalConfig2_10`
- `0x18003399c`: `SvrImpl_FWGetGlobalConfig2_10`
- `0x1800339ac`: `SvrImpl_FWGetGlobalConfig2_10`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWGetGlobalConfig2_10(
        void *a1,
        unsigned __int16 a2,
        unsigned int a3,
        unsigned int a4,
        char a5,
        _DWORD *a6,
        unsigned int *a7)
{
  __int64 result; // rax
  __int64 v12; // r12
  int DefaultConfig; // ebx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int v19; // ecx
  __int64 v20; // rcx
  unsigned int *v21; // rbp
  _DWORD *v22; // r14
  int GlobalConfig; // eax
  int v24; // eax

  result = FwAcquireRPCSharedLock("SvrImpl_FWGetGlobalConfig2_10");
  if ( (int)result >= 0 )
  {
    v12 = 0;
    if ( a3 == 1 )
    {
      v12 = FWGPLock();
      if ( !v12 )
      {
        DefaultConfig = -2147024894;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_Ds(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            183,
            (unsigned int)WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
            -2147024894,
            (__int64)"FWGPLock");
LABEL_72:
        FwReleaseRPCSharedLock("SvrImpl_FWGetGlobalConfig2_10");
        return FwHResultToWindowsError((unsigned int)DefaultConfig);
      }
    }
    DefaultConfig = FwLock();
    if ( DefaultConfig < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          184,
          WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
          (unsigned int)DefaultConfig);
      goto LABEL_70;
    }
    switch ( a3 )
    {
      case 2u:
        goto LABEL_26;
      case 1u:
        if ( a4 == 1 )
        {
          v18 = 2147942487LL;
          DefaultConfig = -2147024809;
          v16 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_69;
          v17 = 186;
          goto LABEL_68;
        }
        break;
      case 5u:
        break;
      case 0xBu:
LABEL_26:
        if ( a4 == 1 )
        {
          if ( a6 )
          {
            if ( *a7 < 4 )
            {
              v18 = 2147942487LL;
              DefaultConfig = -2147024809;
              v16 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_69;
              }
              v17 = 189;
              goto LABEL_68;
            }
            *a6 = 545;
            *a7 = 4;
          }
          else
          {
            if ( a7 )
            {
              if ( *a7 < 4 )
                *a7 = 4;
              goto LABEL_69;
            }
            v18 = 2147942487LL;
            DefaultConfig = -2147024809;
            v16 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v17 = 188;
LABEL_68:
              WPP_SF_d(*(_QWORD *)(v16 + 16), v17, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v18);
            }
          }
LABEL_69:
          FwUnlockInternal(a1, "SvrImpl_FWGetGlobalConfig2_10");
LABEL_70:
          if ( v12 )
            FWGPUnlockEx(v12, "SvrImpl_FWGetGlobalConfig2_10");
          goto LABEL_72;
        }
        if ( a4 == 11 )
        {
          v19 = *a7;
          *a7 = 4;
          if ( v19 >= 4 )
          {
            *a6 = 545;
            goto LABEL_69;
          }
          DefaultConfig = -2147024662;
          v16 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_69;
          v17 = 190;
        }
        else
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening>::__private_IsEnabled(
                                  `wil::Feature<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening>::GetImpl'::`2'::impl,
                                  v14,
                                  v15) )
          {
            if ( a3 == 5 || a4 == 18 )
            {
              v22 = a6;
              v21 = a7;
              GlobalConfig = FwDynamicStoreGetGlobalConfig(v20, a3, a4, a6, a7);
            }
            else
            {
              v21 = a7;
              v22 = a6;
              GlobalConfig = FwGetGlobalConfig(a2, a3, 0, a4, a6, a7);
            }
            DefaultConfig = GlobalConfig;
            if ( GlobalConfig < 0 )
            {
              v16 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_69;
              }
              v17 = 191;
              goto LABEL_67;
            }
          }
          else
          {
            v21 = a7;
            v22 = a6;
            if ( a3 == 5 )
              v24 = FwDynamicStoreGetGlobalConfig(v20, 5, a4, a6, a7);
            else
              v24 = FwGetGlobalConfig(a2, a3, 0, a4, a6, a7);
            DefaultConfig = v24;
          }
          if ( (a5 & 1) != 0 && DefaultConfig == -2147024894 )
          {
            if ( (int)a4 >= 19 )
            {
              DefaultConfig = 87;
              goto LABEL_69;
            }
            DefaultConfig = FwGetDefaultConfig(a4, &g_GlobalConfigDescriptor, v22, v21);
          }
          if ( DefaultConfig >= 0 )
            goto LABEL_69;
          v16 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_69;
          v17 = 192;
        }
LABEL_67:
        v18 = (unsigned int)DefaultConfig;
        goto LABEL_68;
      default:
        DefaultConfig = -2147024846;
        v16 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_69;
        v17 = 185;
        goto LABEL_67;
    }
    if ( a4 == 10 )
    {
      v18 = 2147942487LL;
      DefaultConfig = -2147024809;
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_69;
      v17 = 187;
      goto LABEL_68;
    }
    goto LABEL_26;
  }
  return result;
}

```

## disassembly

```asm
0x180033580  push    rbx
0x180033582  push    rbp
0x180033583  push    rsi
0x180033584  push    rdi
0x180033585  push    r12
0x180033587  push    r13
0x180033589  push    r14
0x18003358b  push    r15
0x18003358d  sub     rsp, 38h
0x180033591  mov     r13, rcx
0x180033594  mov     esi, r9d
0x180033597  lea     rcx, aSvrimplFwgetgl; "SvrImpl_FWGetGlobalConfig2_10"
0x18003359e  mov     edi, r8d
0x1800335a1  movzx   r15d, dx
0x1800335a5  call    FwAcquireRPCSharedLock
0x1800335aa  test    eax, eax
0x1800335ac  js      loc_1800339C0
0x1800335b2  xor     r12d, r12d
0x1800335b5  lea     ebp, [r12+1]
0x1800335ba  cmp     edi, ebp
0x1800335bc  jnz     short loc_18003361B
0x1800335be  call    cs:__imp_FWGPLock
0x1800335c4  mov     r12, rax
0x1800335c7  test    rax, rax
0x1800335ca  jnz     short loc_18003361B
0x1800335cc  mov     ebx, 80070002h
0x1800335d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800335d8  lea     rax, WPP_GLOBAL_Control
0x1800335df  cmp     rcx, rax
0x1800335e2  jz      loc_1800339AC
0x1800335e8  test    [rcx+1Ch], bpl
0x1800335ec  jz      loc_1800339AC
0x1800335f2  mov     rcx, [rcx+10h]
0x1800335f6  lea     rax, aFwgplock_0; "FWGPLock"
0x1800335fd  mov     edx, 0B7h
0x180033602  mov     [rsp+78h+var_58], rax
0x180033607  mov     r9d, ebx
0x18003360a  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180033611  call    WPP_SF_Ds
0x180033616  jmp     loc_1800339AC
0x18003361b  call    FwLock
0x180033620  mov     ebx, eax
0x180033622  test    eax, eax
0x180033624  jns     short loc_180033664
0x180033626  mov     rcx, cs:WPP_GLOBAL_Control
0x18003362d  lea     rax, WPP_GLOBAL_Control
0x180033634  cmp     rcx, rax
0x180033637  jz      loc_180033997
0x18003363d  test    [rcx+1Ch], bpl
0x180033641  jz      loc_180033997
0x180033647  mov     rcx, [rcx+10h]
0x18003364b  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180033652  mov     edx, 0B8h
0x180033657  mov     r9d, ebx
0x18003365a  call    WPP_SF_d
0x18003365f  jmp     loc_180033997
0x180033664  cmp     edi, 2
0x180033667  jz      loc_180033720
0x18003366d  cmp     edi, ebp
0x18003366f  jz      short loc_1800336AF
0x180033671  cmp     edi, 5
0x180033674  jz      short loc_1800336E7
0x180033676  cmp     edi, 0Bh
0x180033679  jz      loc_180033720
0x18003367f  mov     ebx, 80070032h
0x180033684  mov     rcx, cs:WPP_GLOBAL_Control
0x18003368b  lea     rax, WPP_GLOBAL_Control
0x180033692  cmp     rcx, rax
0x180033695  jz      loc_180033988
0x18003369b  test    [rcx+1Ch], bpl
0x18003369f  jz      loc_180033988
0x1800336a5  mov     edx, 0B9h
0x1800336aa  jmp     loc_180033975
0x1800336af  cmp     esi, ebp
0x1800336b1  jnz     short loc_1800336E7
0x1800336b3  mov     r9d, 80070057h
0x1800336b9  mov     ebx, r9d
0x1800336bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800336c3  lea     rax, WPP_GLOBAL_Control
0x1800336ca  cmp     rcx, rax
0x1800336cd  jz      loc_180033988
0x1800336d3  test    [rcx+1Ch], bpl
0x1800336d7  jz      loc_180033988
0x1800336dd  mov     edx, 0BAh
0x1800336e2  jmp     loc_180033978
0x1800336e7  cmp     esi, 0Ah
0x1800336ea  jnz     short loc_180033720
0x1800336ec  mov     r9d, 80070057h
0x1800336f2  mov     ebx, r9d
0x1800336f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800336fc  lea     rax, WPP_GLOBAL_Control
0x180033703  cmp     rcx, rax
0x180033706  jz      loc_180033988
0x18003370c  test    [rcx+1Ch], bpl
0x180033710  jz      loc_180033988
0x180033716  mov     edx, 0BBh
0x18003371b  jmp     loc_180033978
0x180033720  cmp     esi, ebp
0x180033722  jnz     loc_1800337DC
0x180033728  mov     rax, [rsp+78h+arg_28]
0x180033730  test    rax, rax
0x180033733  jnz     short loc_18003378A
0x180033735  mov     rax, [rsp+78h+arg_30]
0x18003373d  test    rax, rax
0x180033740  jnz     short loc_180033776
0x180033742  mov     r9d, 80070057h
0x180033748  mov     ebx, r9d
0x18003374b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033752  lea     rax, WPP_GLOBAL_Control
0x180033759  cmp     rcx, rax
0x18003375c  jz      loc_180033988
0x180033762  test    [rcx+1Ch], bpl
0x180033766  jz      loc_180033988
0x18003376c  mov     edx, 0BCh
0x180033771  jmp     loc_180033978
0x180033776  cmp     dword ptr [rax], 4
0x180033779  jnb     loc_180033988
0x18003377f  mov     dword ptr [rax], 4
0x180033785  jmp     loc_180033988
0x18003378a  mov     rcx, [rsp+78h+arg_30]
0x180033792  cmp     dword ptr [rcx], 4
0x180033795  jnb     short loc_1800337CB
0x180033797  mov     r9d, 80070057h
0x18003379d  mov     ebx, r9d
0x1800337a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800337a7  lea     rax, WPP_GLOBAL_Control
0x1800337ae  cmp     rcx, rax
0x1800337b1  jz      loc_180033988
0x1800337b7  test    [rcx+1Ch], bpl
0x1800337bb  jz      loc_180033988
0x1800337c1  mov     edx, 0BDh
0x1800337c6  jmp     loc_180033978
0x1800337cb  mov     dword ptr [rax], 221h
0x1800337d1  mov     dword ptr [rcx], 4
0x1800337d7  jmp     loc_180033988
0x1800337dc  cmp     esi, 0Bh
0x1800337df  jnz     short loc_180033839
0x1800337e1  mov     rax, [rsp+78h+arg_30]
0x1800337e9  mov     ecx, [rax]
0x1800337eb  mov     dword ptr [rax], 4
0x1800337f1  cmp     ecx, 4
0x1800337f4  jnb     short loc_180033826
0x1800337f6  mov     ebx, 800700EAh
0x1800337fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180033802  lea     rax, WPP_GLOBAL_Control
0x180033809  cmp     rcx, rax
0x18003380c  jz      loc_180033988
0x180033812  test    [rcx+1Ch], bpl
0x180033816  jz      loc_180033988
0x18003381c  mov     edx, 0BEh
0x180033821  jmp     loc_180033975
0x180033826  mov     rax, [rsp+78h+arg_28]
0x18003382e  mov     dword ptr [rax], 221h
0x180033834  jmp     loc_180033988
0x180033839  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening> `wil::Feature<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening>::GetImpl(void)'::`2'::impl
0x180033840  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening>::__private_IsEnabled(void)
0x180033845  test    al, al
0x180033847  jz      loc_1800338D8
0x18003384d  cmp     edi, 5
0x180033850  jz      short loc_180033885
0x180033852  cmp     esi, 12h
0x180033855  jz      short loc_180033885
0x180033857  mov     rbp, [rsp+78h+arg_30]
0x18003385f  mov     r9d, esi
0x180033862  mov     r14, [rsp+78h+arg_28]
0x18003386a  xor     r8d, r8d
0x18003386d  mov     [rsp+78h+var_50], rbp
0x180033872  mov     edx, edi
0x180033874  movzx   ecx, r15w
0x180033878  mov     [rsp+78h+var_58], r14
0x18003387d  call    cs:__imp_FwGetGlobalConfig
0x180033883  jmp     short loc_1800338A7
0x180033885  mov     r14, [rsp+78h+arg_28]
0x18003388d  mov     r8d, esi
0x180033890  mov     rbp, [rsp+78h+arg_30]
0x180033898  mov     r9, r14
0x18003389b  mov     edx, edi
0x18003389d  mov     [rsp+78h+var_58], rbp
0x1800338a2  call    FwDynamicStoreGetGlobalConfig
0x1800338a7  mov     ebx, eax
0x1800338a9  test    eax, eax
0x1800338ab  jns     short loc_18003391F
0x1800338ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800338b4  lea     rax, WPP_GLOBAL_Control
0x1800338bb  cmp     rcx, rax
0x1800338be  jz      loc_180033988
0x1800338c4  test    byte ptr [rcx+1Ch], 1
0x1800338c8  jz      loc_180033988
0x1800338ce  mov     edx, 0BFh
0x1800338d3  jmp     loc_180033975
0x1800338d8  mov     rbp, [rsp+78h+arg_30]
0x1800338e0  mov     r14, [rsp+78h+arg_28]
0x1800338e8  cmp     edi, 5
0x1800338eb  jnz     short loc_180033901
0x1800338ed  mov     r9, r14
0x1800338f0  mov     [rsp+78h+var_58], rbp
0x1800338f5  mov     r8d, esi
0x1800338f8  mov     edx, edi
0x1800338fa  call    FwDynamicStoreGetGlobalConfig
0x1800338ff  jmp     short loc_18003391D
0x180033901  mov     [rsp+78h+var_50], rbp
0x180033906  mov     r9d, esi
0x180033909  xor     r8d, r8d
0x18003390c  mov     [rsp+78h+var_58], r14
0x180033911  mov     edx, edi
0x180033913  movzx   ecx, r15w
0x180033917  call    cs:__imp_FwGetGlobalConfig
0x18003391d  mov     ebx, eax
0x18003391f  test    [rsp+78h+arg_20], 1
0x180033927  jz      short loc_180033953
0x180033929  cmp     ebx, 80070002h
0x18003392f  jnz     short loc_180033953
0x180033931  cmp     esi, 13h
0x180033934  jl      short loc_18003393D
0x180033936  mov     ebx, 57h ; 'W'
0x18003393b  jmp     short loc_180033988
0x18003393d  mov     r9, rbp
0x180033940  lea     rdx, ?g_GlobalConfigDescriptor@@3PAU_tag_FW_CONFIG_SERVICE_DESCRIPTOR@@A; _tag_FW_CONFIG_SERVICE_DESCRIPTOR near * g_GlobalConfigDescriptor
0x180033947  mov     r8, r14
0x18003394a  mov     ecx, esi
0x18003394c  call    ?FwGetDefaultConfig@@YAJW4_tag_FW_PROFILE_CONFIG@@PEAU_tag_FW_CONFIG_SERVICE_DESCRIPTOR@@PEAXPEAK@Z; FwGetDefaultConfig(_tag_FW_PROFILE_CONFIG,_tag_FW_CONFIG_SERVICE_DESCRIPTOR *,void *,ulong *)
0x180033951  mov     ebx, eax
0x180033953  test    ebx, ebx
0x180033955  jns     short loc_180033988
0x180033957  mov     rcx, cs:WPP_GLOBAL_Control
0x18003395e  lea     rax, WPP_GLOBAL_Control
0x180033965  cmp     rcx, rax
0x180033968  jz      short loc_180033988
0x18003396a  test    byte ptr [rcx+1Ch], 1
0x18003396e  jz      short loc_180033988
0x180033970  mov     edx, 0C0h
0x180033975  mov     r9d, ebx
0x180033978  mov     rcx, [rcx+10h]
0x18003397c  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180033983  call    WPP_SF_d
0x180033988  lea     rdx, aSvrimplFwgetgl; "SvrImpl_FWGetGlobalConfig2_10"
0x18003398f  mov     rcx, r13; void *
0x180033992  call    FwUnlockInternal
0x180033997  test    r12, r12
0x18003399a  jz      short loc_1800339AC
0x18003399c  lea     rdx, aSvrimplFwgetgl; "SvrImpl_FWGetGlobalConfig2_10"
0x1800339a3  mov     rcx, r12
0x1800339a6  call    cs:__imp_FWGPUnlockEx
0x1800339ac  lea     rcx, aSvrimplFwgetgl; "SvrImpl_FWGetGlobalConfig2_10"
0x1800339b3  call    FwReleaseRPCSharedLock
0x1800339b8  mov     ecx, ebx
0x1800339ba  call    cs:__imp_FwHResultToWindowsError
0x1800339c0  add     rsp, 38h
0x1800339c4  pop     r15
0x1800339c6  pop     r14
0x1800339c8  pop     r13
0x1800339ca  pop     r12
0x1800339cc  pop     rdi
0x1800339cd  pop     rsi
0x1800339ce  pop     rbp
0x1800339cf  pop     rbx
0x1800339d0  retn
```
