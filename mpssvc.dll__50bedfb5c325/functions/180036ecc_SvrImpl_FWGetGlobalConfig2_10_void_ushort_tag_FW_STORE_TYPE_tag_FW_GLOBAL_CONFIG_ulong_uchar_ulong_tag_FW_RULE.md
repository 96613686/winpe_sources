# SvrImpl_FWGetGlobalConfig2_10(void *,ushort,_tag_FW_STORE_TYPE,_tag_FW_GLOBAL_CONFIG,ulong,uchar *,ulong *,_tag_FW_RULE_ORIGIN_TYPE *)

- ea: `0x180036ecc`
- end: `0x18003733c`
- name: `?SvrImpl_FWGetGlobalConfig2_10@@YAKPEAXGW4_tag_FW_STORE_TYPE@@W4_tag_FW_GLOBAL_CONFIG@@KPEAEPEAKPEAW4_tag_FW_RULE_ORIGIN_TYPE@@@Z`
- size: `1136`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036360`
- `0x180036980`

## callees

- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a66c`
- `0x18000a710`
- `0x180034e2c`
- `0x180036ecc`
- `0x180057954`
- `0x1800a6d90`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18003731e`
- `fwbase!FwHResultToWindowsError` at `0x18003731e`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x180037304`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x180037304`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x1800371cf`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x18003726f`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x1800371cf`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x18003726f`
- `FWPolicyIOMgr!FWGPLock` at `0x180036f0a`
- `FWPolicyIOMgr!FWGPLock` at `0x180036f0a`

## string_xrefs

- `0x180036ee3`: `SvrImpl_FWGetGlobalConfig2_10`
- `0x1800372e6`: `SvrImpl_FWGetGlobalConfig2_10`
- `0x1800372fa`: `SvrImpl_FWGetGlobalConfig2_10`
- `0x180037310`: `SvrImpl_FWGetGlobalConfig2_10`

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
            (unsigned int)WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
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
          WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
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
              WPP_SF_d(*(_QWORD *)(v16 + 16), v17, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v18);
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
0x180036ecc  push    rbx
0x180036ece  push    rbp
0x180036ecf  push    rsi
0x180036ed0  push    rdi
0x180036ed1  push    r12
0x180036ed3  push    r13
0x180036ed5  push    r14
0x180036ed7  push    r15
0x180036ed9  sub     rsp, 38h
0x180036edd  mov     r13, rcx
0x180036ee0  mov     esi, r9d
0x180036ee3  lea     rcx, aSvrimplFwgetgl; "SvrImpl_FWGetGlobalConfig2_10"
0x180036eea  mov     edi, r8d
0x180036eed  movzx   r15d, dx
0x180036ef1  call    FwAcquireRPCSharedLock
0x180036ef6  test    eax, eax
0x180036ef8  js      loc_18003732A
0x180036efe  xor     r12d, r12d
0x180036f01  lea     ebp, [r12+1]
0x180036f06  cmp     edi, ebp
0x180036f08  jnz     short loc_180036F6D
0x180036f0a  call    cs:__imp_FWGPLock
0x180036f11  nop     dword ptr [rax+rax+00h]
0x180036f16  mov     r12, rax
0x180036f19  test    rax, rax
0x180036f1c  jnz     short loc_180036F6D
0x180036f1e  mov     ebx, 80070002h
0x180036f23  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f2a  lea     rax, WPP_GLOBAL_Control
0x180036f31  cmp     rcx, rax
0x180036f34  jz      loc_180037310
0x180036f3a  test    [rcx+1Ch], bpl
0x180036f3e  jz      loc_180037310
0x180036f44  mov     rcx, [rcx+10h]
0x180036f48  lea     rax, aFwgplock_0; "FWGPLock"
0x180036f4f  mov     edx, 0B7h
0x180036f54  mov     [rsp+78h+var_58], rax
0x180036f59  mov     r9d, ebx
0x180036f5c  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180036f63  call    WPP_SF_Ds
0x180036f68  jmp     loc_180037310
0x180036f6d  call    FwLock
0x180036f72  mov     ebx, eax
0x180036f74  test    eax, eax
0x180036f76  jns     short loc_180036FB6
0x180036f78  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f7f  lea     rax, WPP_GLOBAL_Control
0x180036f86  cmp     rcx, rax
0x180036f89  jz      loc_1800372F5
0x180036f8f  test    [rcx+1Ch], bpl
0x180036f93  jz      loc_1800372F5
0x180036f99  mov     rcx, [rcx+10h]
0x180036f9d  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180036fa4  mov     edx, 0B8h
0x180036fa9  mov     r9d, ebx
0x180036fac  call    WPP_SF_d
0x180036fb1  jmp     loc_1800372F5
0x180036fb6  cmp     edi, 2
0x180036fb9  jz      loc_180037072
0x180036fbf  cmp     edi, ebp
0x180036fc1  jz      short loc_180037001
0x180036fc3  cmp     edi, 5
0x180036fc6  jz      short loc_180037039
0x180036fc8  cmp     edi, 0Bh
0x180036fcb  jz      loc_180037072
0x180036fd1  mov     ebx, 80070032h
0x180036fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180036fdd  lea     rax, WPP_GLOBAL_Control
0x180036fe4  cmp     rcx, rax
0x180036fe7  jz      loc_1800372E6
0x180036fed  test    [rcx+1Ch], bpl
0x180036ff1  jz      loc_1800372E6
0x180036ff7  mov     edx, 0B9h
0x180036ffc  jmp     loc_1800372D3
0x180037001  cmp     esi, ebp
0x180037003  jnz     short loc_180037039
0x180037005  mov     r9d, 80070057h
0x18003700b  mov     ebx, r9d
0x18003700e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037015  lea     rax, WPP_GLOBAL_Control
0x18003701c  cmp     rcx, rax
0x18003701f  jz      loc_1800372E6
0x180037025  test    [rcx+1Ch], bpl
0x180037029  jz      loc_1800372E6
0x18003702f  mov     edx, 0BAh
0x180037034  jmp     loc_1800372D6
0x180037039  cmp     esi, 0Ah
0x18003703c  jnz     short loc_180037072
0x18003703e  mov     r9d, 80070057h
0x180037044  mov     ebx, r9d
0x180037047  mov     rcx, cs:WPP_GLOBAL_Control
0x18003704e  lea     rax, WPP_GLOBAL_Control
0x180037055  cmp     rcx, rax
0x180037058  jz      loc_1800372E6
0x18003705e  test    [rcx+1Ch], bpl
0x180037062  jz      loc_1800372E6
0x180037068  mov     edx, 0BBh
0x18003706d  jmp     loc_1800372D6
0x180037072  cmp     esi, ebp
0x180037074  jnz     loc_18003712E
0x18003707a  mov     rax, [rsp+78h+arg_28]
0x180037082  test    rax, rax
0x180037085  jnz     short loc_1800370DC
0x180037087  mov     rax, [rsp+78h+arg_30]
0x18003708f  test    rax, rax
0x180037092  jnz     short loc_1800370C8
0x180037094  mov     r9d, 80070057h
0x18003709a  mov     ebx, r9d
0x18003709d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370a4  lea     rax, WPP_GLOBAL_Control
0x1800370ab  cmp     rcx, rax
0x1800370ae  jz      loc_1800372E6
0x1800370b4  test    [rcx+1Ch], bpl
0x1800370b8  jz      loc_1800372E6
0x1800370be  mov     edx, 0BCh
0x1800370c3  jmp     loc_1800372D6
0x1800370c8  cmp     dword ptr [rax], 4
0x1800370cb  jnb     loc_1800372E6
0x1800370d1  mov     dword ptr [rax], 4
0x1800370d7  jmp     loc_1800372E6
0x1800370dc  mov     rcx, [rsp+78h+arg_30]
0x1800370e4  cmp     dword ptr [rcx], 4
0x1800370e7  jnb     short loc_18003711D
0x1800370e9  mov     r9d, 80070057h
0x1800370ef  mov     ebx, r9d
0x1800370f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370f9  lea     rax, WPP_GLOBAL_Control
0x180037100  cmp     rcx, rax
0x180037103  jz      loc_1800372E6
0x180037109  test    [rcx+1Ch], bpl
0x18003710d  jz      loc_1800372E6
0x180037113  mov     edx, 0BDh
0x180037118  jmp     loc_1800372D6
0x18003711d  mov     dword ptr [rax], 221h
0x180037123  mov     dword ptr [rcx], 4
0x180037129  jmp     loc_1800372E6
0x18003712e  cmp     esi, 0Bh
0x180037131  jnz     short loc_18003718B
0x180037133  mov     rax, [rsp+78h+arg_30]
0x18003713b  mov     ecx, [rax]
0x18003713d  mov     dword ptr [rax], 4
0x180037143  cmp     ecx, 4
0x180037146  jnb     short loc_180037178
0x180037148  mov     ebx, 800700EAh
0x18003714d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037154  lea     rax, WPP_GLOBAL_Control
0x18003715b  cmp     rcx, rax
0x18003715e  jz      loc_1800372E6
0x180037164  test    [rcx+1Ch], bpl
0x180037168  jz      loc_1800372E6
0x18003716e  mov     edx, 0BEh
0x180037173  jmp     loc_1800372D3
0x180037178  mov     rax, [rsp+78h+arg_28]
0x180037180  mov     dword ptr [rax], 221h
0x180037186  jmp     loc_1800372E6
0x18003718b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening> `wil::Feature<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening>::GetImpl(void)'::`2'::impl
0x180037192  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening>::__private_IsEnabled(void)
0x180037197  test    al, al
0x180037199  jz      loc_180037230
0x18003719f  cmp     edi, 5
0x1800371a2  jz      short loc_1800371DD
0x1800371a4  cmp     esi, 12h
0x1800371a7  jz      short loc_1800371DD
0x1800371a9  mov     rbp, [rsp+78h+arg_30]
0x1800371b1  mov     r9d, esi
0x1800371b4  mov     r14, [rsp+78h+arg_28]
0x1800371bc  xor     r8d, r8d
0x1800371bf  mov     [rsp+78h+var_50], rbp
0x1800371c4  mov     edx, edi
0x1800371c6  movzx   ecx, r15w
0x1800371ca  mov     [rsp+78h+var_58], r14
0x1800371cf  call    cs:__imp_FwGetGlobalConfig
0x1800371d6  nop     dword ptr [rax+rax+00h]
0x1800371db  jmp     short loc_1800371FF
0x1800371dd  mov     r14, [rsp+78h+arg_28]
0x1800371e5  mov     r8d, esi
0x1800371e8  mov     rbp, [rsp+78h+arg_30]
0x1800371f0  mov     r9, r14
0x1800371f3  mov     edx, edi
0x1800371f5  mov     [rsp+78h+var_58], rbp
0x1800371fa  call    FwDynamicStoreGetGlobalConfig
0x1800371ff  mov     ebx, eax
0x180037201  test    eax, eax
0x180037203  jns     short loc_18003727D
0x180037205  mov     rcx, cs:WPP_GLOBAL_Control
0x18003720c  lea     rax, WPP_GLOBAL_Control
0x180037213  cmp     rcx, rax
0x180037216  jz      loc_1800372E6
0x18003721c  test    byte ptr [rcx+1Ch], 1
0x180037220  jz      loc_1800372E6
0x180037226  mov     edx, 0BFh
0x18003722b  jmp     loc_1800372D3
0x180037230  mov     rbp, [rsp+78h+arg_30]
0x180037238  mov     r14, [rsp+78h+arg_28]
0x180037240  cmp     edi, 5
0x180037243  jnz     short loc_180037259
0x180037245  mov     r9, r14
0x180037248  mov     [rsp+78h+var_58], rbp
0x18003724d  mov     r8d, esi
0x180037250  mov     edx, edi
0x180037252  call    FwDynamicStoreGetGlobalConfig
0x180037257  jmp     short loc_18003727B
0x180037259  mov     [rsp+78h+var_50], rbp
0x18003725e  mov     r9d, esi
0x180037261  xor     r8d, r8d
0x180037264  mov     [rsp+78h+var_58], r14
0x180037269  mov     edx, edi
0x18003726b  movzx   ecx, r15w
0x18003726f  call    cs:__imp_FwGetGlobalConfig
0x180037276  nop     dword ptr [rax+rax+00h]
0x18003727b  mov     ebx, eax
0x18003727d  test    [rsp+78h+arg_20], 1
0x180037285  jz      short loc_1800372B1
0x180037287  cmp     ebx, 80070002h
0x18003728d  jnz     short loc_1800372B1
0x18003728f  cmp     esi, 13h
0x180037292  jl      short loc_18003729B
0x180037294  mov     ebx, 57h ; 'W'
0x180037299  jmp     short loc_1800372E6
0x18003729b  mov     r9, rbp
0x18003729e  lea     rdx, ?g_GlobalConfigDescriptor@@3PAU_tag_FW_CONFIG_SERVICE_DESCRIPTOR@@A; _tag_FW_CONFIG_SERVICE_DESCRIPTOR near * g_GlobalConfigDescriptor
0x1800372a5  mov     r8, r14
0x1800372a8  mov     ecx, esi
0x1800372aa  call    ?FwGetDefaultConfig@@YAJW4_tag_FW_PROFILE_CONFIG@@PEAU_tag_FW_CONFIG_SERVICE_DESCRIPTOR@@PEAXPEAK@Z; FwGetDefaultConfig(_tag_FW_PROFILE_CONFIG,_tag_FW_CONFIG_SERVICE_DESCRIPTOR *,void *,ulong *)
0x1800372af  mov     ebx, eax
0x1800372b1  test    ebx, ebx
0x1800372b3  jns     short loc_1800372E6
0x1800372b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372bc  lea     rax, WPP_GLOBAL_Control
0x1800372c3  cmp     rcx, rax
0x1800372c6  jz      short loc_1800372E6
0x1800372c8  test    byte ptr [rcx+1Ch], 1
0x1800372cc  jz      short loc_1800372E6
0x1800372ce  mov     edx, 0C0h
0x1800372d3  mov     r9d, ebx
0x1800372d6  mov     rcx, [rcx+10h]
0x1800372da  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800372e1  call    WPP_SF_d
0x1800372e6  lea     rdx, aSvrimplFwgetgl; "SvrImpl_FWGetGlobalConfig2_10"
0x1800372ed  mov     rcx, r13; void *
0x1800372f0  call    FwUnlockInternal
0x1800372f5  test    r12, r12
0x1800372f8  jz      short loc_180037310
0x1800372fa  lea     rdx, aSvrimplFwgetgl; "SvrImpl_FWGetGlobalConfig2_10"
0x180037301  mov     rcx, r12
0x180037304  call    cs:__imp_FWGPUnlockEx
0x18003730b  nop     dword ptr [rax+rax+00h]
0x180037310  lea     rcx, aSvrimplFwgetgl; "SvrImpl_FWGetGlobalConfig2_10"
0x180037317  call    FwReleaseRPCSharedLock
0x18003731c  mov     ecx, ebx
0x18003731e  call    cs:__imp_FwHResultToWindowsError
0x180037325  nop     dword ptr [rax+rax+00h]
0x18003732a  add     rsp, 38h
0x18003732e  pop     r15
0x180037330  pop     r14
0x180037332  pop     r13
0x180037334  pop     r12
0x180037336  pop     rdi
0x180037337  pop     rsi
0x180037338  pop     rbp
0x180037339  pop     rbx
0x18003733a  retn
```
