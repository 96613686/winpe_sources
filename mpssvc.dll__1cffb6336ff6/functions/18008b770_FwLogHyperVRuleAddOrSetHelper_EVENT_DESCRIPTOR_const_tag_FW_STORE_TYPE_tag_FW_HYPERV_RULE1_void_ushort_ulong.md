# FwLogHyperVRuleAddOrSetHelper(_EVENT_DESCRIPTOR const *,_tag_FW_STORE_TYPE,_tag_FW_HYPERV_RULE1 *,void *,ushort *,ulong)

- ea: `0x18008b770`
- end: `0x18008ba39`
- name: `?FwLogHyperVRuleAddOrSetHelper@@YAKPEBU_EVENT_DESCRIPTOR@@W4_tag_FW_STORE_TYPE@@PEAU_tag_FW_HYPERV_RULE1@@PEAXPEAGK@Z`
- size: `713`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180097afc`
- `0x1800a00c8`

## callees

- `0x18000af3c`
- `0x180029b48`
- `0x180049d98`
- `0x18004c870`
- `0x180067fc8`
- `0x180068034`
- `0x18006b278`
- `0x18006f520`
- `0x18008b770`

## import_xrefs

- `fwbase!FwPortsToString` at `0x18008b886`
- `fwbase!FwPortsToString` at `0x18008b898`
- `fwbase!FwPortsToString` at `0x18008b886`
- `fwbase!FwPortsToString` at `0x18008b898`
- `fwbase!FwFree` at `0x18008b9f0`
- `fwbase!FwFree` at `0x18008b9fb`
- `fwbase!FwFree` at `0x18008ba06`
- `fwbase!FwFree` at `0x18008ba11`
- `fwbase!FwFree` at `0x18008b9f0`
- `fwbase!FwFree` at `0x18008b9fb`
- `fwbase!FwFree` at `0x18008ba06`
- `fwbase!FwFree` at `0x18008ba11`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18008b8ad`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18008b8c5`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18008b8ad`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18008b8c5`

## pseudocode

```c
__int64 __fastcall FwLogHyperVRuleAddOrSetHelper(
        const struct _EVENT_DESCRIPTOR *a1,
        int a2,
        __int64 a3,
        void *a4,
        unsigned __int16 *a5,
        char a6)
{
  unsigned int IsEventEnbled; // edi
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r9
  const unsigned __int16 *v13; // rdx
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v16; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v17; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v18; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v20; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v21[8]; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+60h] [rbp-A0h] BYREF
  int *v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+78h] [rbp-88h]
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+A8h] [rbp-58h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+B8h] [rbp-48h]
  __int64 v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  __int64 v33; // [rsp+D0h] [rbp-30h]
  __int64 v34; // [rsp+D8h] [rbp-28h]
  __int64 v35; // [rsp+E0h] [rbp-20h]
  __int64 v36; // [rsp+E8h] [rbp-18h]
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+F0h] [rbp-10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+100h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+110h] [rbp+10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+120h] [rbp+20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v41; // [rsp+130h] [rbp+30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v42; // [rsp+140h] [rbp+40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v43; // [rsp+150h] [rbp+50h] BYREF
  int v44; // [rsp+1C8h] [rbp+C8h] BYREF

  v44 = a2;
  v16 = a5;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21[0] = 0;
  IsEventEnbled = FwIsEventEnbled(a1, &v15);
  if ( !IsEventEnbled )
  {
    if ( v15 )
    {
      if ( a3 )
      {
        FwPortsToString((struct _tag_FW_PORTS *const)(a3 + 136), &v17);
        FwPortsToString((struct _tag_FW_PORTS *const)(a3 + 232), &v18);
        GetOpenPortorAuthAppAddrAsString(a3 + 64, &v19, 1);
        GetOpenPortorAuthAppAddrAsString(a3 + 160, &v20, 1);
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
        v13 = *(const unsigned __int16 **)(a3 + 16);
        *(_QWORD *)&v22.Size = 4;
        v24 = 4;
        v22.Ptr = (ULONGLONG)&a6;
        v23 = &v44;
        FwSerializeStringEventParam(&v25, v13);
        FwSerializeStringEventParam(&v26, *(const unsigned __int16 **)(a3 + 24));
        v33 = a3 + 256;
        v34 = 4;
        v35 = a3 + 56;
        v32 = 4;
        v31 = a3 + 36;
        v30 = 2;
        v29 = a3 + 32;
        v28 = 16;
        v27 = a3 + 40;
        v36 = 2;
        FwSerializeStringEventParam(&v37, v17);
        FwSerializeStringEventParam(&v38, v18);
        FwSerializeStringEventParam(&v39, v19);
        FwSerializeStringEventParam(&v40, v20);
        FwSerializeActiveEventParam(&v41, *(_WORD *)(a3 + 260), v21);
        FwSerializeSIDEventParam(&v42, a4);
        FwSerializeStringEventParam(&v43, v16);
        IsEventEnbled = FwLogEvent(a1, 0x10u, &v22);
        goto LABEL_16;
      }
      IsEventEnbled = 0;
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_16;
      v11 = 51;
    }
    else
    {
      IsEventEnbled = 0;
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_16;
      v11 = 50;
    }
    v12 = 0;
    goto LABEL_5;
  }
  v10 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v11 = 49;
    v12 = IsEventEnbled;
LABEL_5:
    WPP_SF_d(*(_QWORD *)(v10 + 16), v11, WPP_cd8e8a94727e3fe3d514260ab96ea5e9_Traceguids, v12);
  }
LABEL_16:
  FwFree(v17);
  FwFree(v18);
  FwFree(v19);
  FwFree(v20);
  return IsEventEnbled;
}

```

## disassembly

```asm
0x18008b770  mov     [rsp-8+arg_8], edx
0x18008b774  push    rbp
0x18008b775  push    rbx
0x18008b776  push    rsi
0x18008b777  push    rdi
0x18008b778  push    r12
0x18008b77a  push    r13
0x18008b77c  push    r14
0x18008b77e  push    r15
0x18008b780  lea     rbp, [rsp-78h]
0x18008b785  sub     rsp, 178h
0x18008b78c  mov     rax, cs:__security_cookie
0x18008b793  xor     rax, rsp
0x18008b796  mov     [rbp+0B0h+var_50], rax
0x18008b79a  mov     rax, [rbp+0B0h+arg_20]
0x18008b7a1  lea     rdx, [rsp+1B0h+var_190]
0x18008b7a6  xor     esi, esi
0x18008b7a8  mov     [rsp+1B0h+var_188], rax
0x18008b7ad  mov     [rsp+1B0h+var_190], esi
0x18008b7b1  mov     r13, r9
0x18008b7b4  mov     [rsp+1B0h+var_180], rsi
0x18008b7b9  mov     rbx, r8
0x18008b7bc  mov     [rsp+1B0h+var_178], rsi
0x18008b7c1  mov     r12, rcx
0x18008b7c4  mov     [rsp+1B0h+var_170], rsi
0x18008b7c9  mov     [rsp+1B0h+var_168], rsi
0x18008b7ce  mov     [rsp+1B0h+var_160], si
0x18008b7d3  call    FwIsEventEnbled
0x18008b7d8  mov     edi, eax
0x18008b7da  test    eax, eax
0x18008b7dc  jz      short loc_18008B81A
0x18008b7de  mov     rax, cs:WPP_GLOBAL_Control
0x18008b7e5  lea     rcx, WPP_GLOBAL_Control
0x18008b7ec  cmp     rax, rcx
0x18008b7ef  jz      loc_18008B9EB
0x18008b7f5  test    byte ptr [rax+1Ch], 1
0x18008b7f9  jz      loc_18008B9EB
0x18008b7ff  lea     edx, [rsi+31h]
0x18008b802  mov     r9d, edi
0x18008b805  mov     rcx, [rax+10h]
0x18008b809  lea     r8, WPP_cd8e8a94727e3fe3d514260ab96ea5e9_Traceguids
0x18008b810  call    WPP_SF_d
0x18008b815  jmp     loc_18008B9EB
0x18008b81a  cmp     [rsp+1B0h+var_190], esi
0x18008b81e  jnz     short loc_18008B84D
0x18008b820  mov     edi, esi
0x18008b822  mov     rax, cs:WPP_GLOBAL_Control
0x18008b829  lea     rcx, WPP_GLOBAL_Control
0x18008b830  cmp     rax, rcx
0x18008b833  jz      loc_18008B9EB
0x18008b839  test    byte ptr [rax+1Ch], 1
0x18008b83d  jz      loc_18008B9EB
0x18008b843  mov     edx, 32h ; '2'
0x18008b848  xor     r9d, r9d
0x18008b84b  jmp     short loc_18008B805
0x18008b84d  test    rbx, rbx
0x18008b850  jnz     short loc_18008B87A
0x18008b852  mov     edi, esi
0x18008b854  mov     rax, cs:WPP_GLOBAL_Control
0x18008b85b  lea     rcx, WPP_GLOBAL_Control
0x18008b862  cmp     rax, rcx
0x18008b865  jz      loc_18008B9EB
0x18008b86b  test    byte ptr [rax+1Ch], 1
0x18008b86f  jz      loc_18008B9EB
0x18008b875  lea     edx, [rbx+33h]
0x18008b878  jmp     short loc_18008B848
0x18008b87a  lea     rcx, [rbx+88h]
0x18008b881  lea     rdx, [rsp+1B0h+var_180]
0x18008b886  call    cs:__imp_?FwPortsToString@@YAJQEAU_tag_FW_PORTS@@PEAPEAG@Z; FwPortsToString(_tag_FW_PORTS * const,ushort * *)
0x18008b88c  lea     rcx, [rbx+0E8h]
0x18008b893  lea     rdx, [rsp+1B0h+var_178]
0x18008b898  call    cs:__imp_?FwPortsToString@@YAJQEAU_tag_FW_PORTS@@PEAPEAG@Z; FwPortsToString(_tag_FW_PORTS * const,ushort * *)
0x18008b89e  lea     rcx, [rbx+40h]
0x18008b8a2  mov     r8d, 1
0x18008b8a8  lea     rdx, [rsp+1B0h+var_170]
0x18008b8ad  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18008b8b3  lea     rcx, [rbx+0A0h]
0x18008b8ba  mov     r8d, 1
0x18008b8c0  lea     rdx, [rsp+1B0h+var_168]
0x18008b8c5  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18008b8cb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18008b8d2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18008b8d7  mov     rdx, [rbx+10h]; unsigned __int16 *
0x18008b8db  lea     rcx, [rbp+0B0h+var_130]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b8df  test    al, al
0x18008b8e1  mov     qword ptr [rsp+1B0h+var_150.Size], 4
0x18008b8ea  lea     rax, [rbp+0B0h+arg_28]
0x18008b8f1  mov     [rsp+1B0h+var_138], 4
0x18008b8fa  mov     [rsp+1B0h+var_150.Ptr], rax
0x18008b8ff  lea     rsi, [rbx+28h]
0x18008b903  lea     rax, [rbp+0B0h+arg_8]
0x18008b90a  mov     [rsp+1B0h+var_140], rax
0x18008b90f  lea     r14, [rbx+20h]
0x18008b913  lea     r15, [rbx+24h]
0x18008b917  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b91c  mov     rdx, [rbx+18h]; unsigned __int16 *
0x18008b920  lea     rcx, [rbp+0B0h+var_120]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b924  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b929  mov     rdx, [rsp+1B0h+var_180]; unsigned __int16 *
0x18008b92e  lea     rax, [rbx+100h]
0x18008b935  mov     [rbp+0B0h+var_E0], rax
0x18008b939  lea     rcx, [rbp+0B0h+var_C0]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b93d  lea     rax, [rbx+38h]
0x18008b941  mov     [rbp+0B0h+var_D8], 4
0x18008b949  mov     [rbp+0B0h+var_D0], rax
0x18008b94d  mov     [rbp+0B0h+var_E8], 4
0x18008b955  mov     [rbp+0B0h+var_F0], r15
0x18008b959  mov     [rbp+0B0h+var_F8], 2
0x18008b961  mov     [rbp+0B0h+var_100], r14
0x18008b965  mov     [rbp+0B0h+var_108], 10h
0x18008b96d  mov     [rbp+0B0h+var_110], rsi
0x18008b971  mov     [rbp+0B0h+var_C8], 2
0x18008b979  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b97e  mov     rdx, [rsp+1B0h+var_178]; unsigned __int16 *
0x18008b983  lea     rcx, [rbp+0B0h+var_B0]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b987  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b98c  mov     rdx, [rsp+1B0h+var_170]; unsigned __int16 *
0x18008b991  lea     rcx, [rbp+0B0h+var_A0]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b995  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b99a  mov     rdx, [rsp+1B0h+var_168]; unsigned __int16 *
0x18008b99f  lea     rcx, [rbp+0B0h+var_90]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b9a3  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b9a8  movzx   edx, word ptr [rbx+104h]; unsigned __int16
0x18008b9af  lea     r8, [rsp+1B0h+var_160]; unsigned __int16 *
0x18008b9b4  lea     rcx, [rbp+0B0h+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b9b8  call    ?FwSerializeActiveEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@GPEAG@Z; FwSerializeActiveEventParam(_EVENT_DATA_DESCRIPTOR *,ushort,ushort *)
0x18008b9bd  mov     rdx, r13; void *
0x18008b9c0  lea     rcx, [rbp+0B0h+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b9c4  call    ?FwSerializeSIDEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEAX@Z; FwSerializeSIDEventParam(_EVENT_DATA_DESCRIPTOR *,void *)
0x18008b9c9  mov     rdx, [rsp+1B0h+var_188]; unsigned __int16 *
0x18008b9ce  lea     rcx, [rbp+0B0h+var_60]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b9d2  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18008b9d7  lea     r8, [rsp+1B0h+var_150]; struct _EVENT_DATA_DESCRIPTOR *
0x18008b9dc  mov     edx, 10h; unsigned int
0x18008b9e1  mov     rcx, r12; struct _EVENT_DESCRIPTOR *
0x18008b9e4  call    ?FwLogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; FwLogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18008b9e9  mov     edi, eax
0x18008b9eb  mov     rcx, [rsp+1B0h+var_180]
0x18008b9f0  call    cs:__imp_FwFree
0x18008b9f6  mov     rcx, [rsp+1B0h+var_178]
0x18008b9fb  call    cs:__imp_FwFree
0x18008ba01  mov     rcx, [rsp+1B0h+var_170]
0x18008ba06  call    cs:__imp_FwFree
0x18008ba0c  mov     rcx, [rsp+1B0h+var_168]
0x18008ba11  call    cs:__imp_FwFree
0x18008ba17  mov     eax, edi
0x18008ba19  mov     rcx, [rbp+0B0h+var_50]
0x18008ba1d  xor     rcx, rsp; StackCookie
0x18008ba20  call    __security_check_cookie
0x18008ba25  add     rsp, 178h
0x18008ba2c  pop     r15
0x18008ba2e  pop     r14
0x18008ba30  pop     r13
0x18008ba32  pop     r12
0x18008ba34  pop     rdi
0x18008ba35  pop     rsi
0x18008ba36  pop     rbx
0x18008ba37  pop     rbp
0x18008ba38  retn
```
