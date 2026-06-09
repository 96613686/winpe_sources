# FwLogHyperVRuleAddOrSetHelper(_EVENT_DESCRIPTOR const *,_tag_FW_STORE_TYPE,_tag_FW_HYPERV_RULE1 *,void *,ushort *,ulong)

- ea: `0x18008fff8`
- end: `0x1800902f2`
- name: `?FwLogHyperVRuleAddOrSetHelper@@YAKPEBU_EVENT_DESCRIPTOR@@W4_tag_FW_STORE_TYPE@@PEAU_tag_FW_HYPERV_RULE1@@PEAXPEAGK@Z`
- size: `762`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18009cb7c`
- `0x1800a575c`

## callees

- `0x18000a710`
- `0x18002d340`
- `0x180048250`
- `0x18004f864`
- `0x18006b940`
- `0x18006b9ac`
- `0x18006e340`
- `0x1800729c0`
- `0x18008fff8`

## import_xrefs

- `fwbase!FwPortsToString` at `0x18009010e`
- `fwbase!FwPortsToString` at `0x180090126`
- `fwbase!FwPortsToString` at `0x18009010e`
- `fwbase!FwPortsToString` at `0x180090126`
- `fwbase!FwFree` at `0x180090290`
- `fwbase!FwFree` at `0x1800902a1`
- `fwbase!FwFree` at `0x1800902b2`
- `fwbase!FwFree` at `0x1800902c3`
- `fwbase!FwFree` at `0x180090290`
- `fwbase!FwFree` at `0x1800902a1`
- `fwbase!FwFree` at `0x1800902b2`
- `fwbase!FwFree` at `0x1800902c3`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180090141`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18009015f`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180090141`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18009015f`

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
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
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
0x18008fff8  mov     [rsp-8+arg_8], edx
0x18008fffc  push    rbp
0x18008fffd  push    rbx
0x18008fffe  push    rsi
0x18008ffff  push    rdi
0x180090000  push    r12
0x180090002  push    r13
0x180090004  push    r14
0x180090006  push    r15
0x180090008  lea     rbp, [rsp-78h]
0x18009000d  sub     rsp, 178h
0x180090014  mov     rax, cs:__security_cookie
0x18009001b  xor     rax, rsp
0x18009001e  mov     [rbp+0B0h+var_50], rax
0x180090022  mov     rax, [rbp+0B0h+arg_20]
0x180090029  lea     rdx, [rsp+1B0h+var_190]
0x18009002e  xor     esi, esi
0x180090030  mov     [rsp+1B0h+var_188], rax
0x180090035  mov     [rsp+1B0h+var_190], esi
0x180090039  mov     r13, r9
0x18009003c  mov     [rsp+1B0h+var_180], rsi
0x180090041  mov     rbx, r8
0x180090044  mov     [rsp+1B0h+var_178], rsi
0x180090049  mov     r12, rcx
0x18009004c  mov     [rsp+1B0h+var_170], rsi
0x180090051  mov     [rsp+1B0h+var_168], rsi
0x180090056  mov     [rsp+1B0h+var_160], si
0x18009005b  call    FwIsEventEnbled
0x180090060  mov     edi, eax
0x180090062  test    eax, eax
0x180090064  jz      short loc_1800900A2
0x180090066  mov     rax, cs:WPP_GLOBAL_Control
0x18009006d  lea     rcx, WPP_GLOBAL_Control
0x180090074  cmp     rax, rcx
0x180090077  jz      loc_18009028B
0x18009007d  test    byte ptr [rax+1Ch], 1
0x180090081  jz      loc_18009028B
0x180090087  lea     edx, [rsi+31h]
0x18009008a  mov     r9d, edi
0x18009008d  mov     rcx, [rax+10h]
0x180090091  lea     r8, WPP_cd8e8a94727e3fe3d514260ab96ea5e9_Traceguids
0x180090098  call    WPP_SF_d
0x18009009d  jmp     loc_18009028B
0x1800900a2  cmp     [rsp+1B0h+var_190], esi
0x1800900a6  jnz     short loc_1800900D5
0x1800900a8  mov     edi, esi
0x1800900aa  mov     rax, cs:WPP_GLOBAL_Control
0x1800900b1  lea     rcx, WPP_GLOBAL_Control
0x1800900b8  cmp     rax, rcx
0x1800900bb  jz      loc_18009028B
0x1800900c1  test    byte ptr [rax+1Ch], 1
0x1800900c5  jz      loc_18009028B
0x1800900cb  mov     edx, 32h ; '2'
0x1800900d0  xor     r9d, r9d
0x1800900d3  jmp     short loc_18009008D
0x1800900d5  test    rbx, rbx
0x1800900d8  jnz     short loc_180090102
0x1800900da  mov     edi, esi
0x1800900dc  mov     rax, cs:WPP_GLOBAL_Control
0x1800900e3  lea     rcx, WPP_GLOBAL_Control
0x1800900ea  cmp     rax, rcx
0x1800900ed  jz      loc_18009028B
0x1800900f3  test    byte ptr [rax+1Ch], 1
0x1800900f7  jz      loc_18009028B
0x1800900fd  lea     edx, [rbx+33h]
0x180090100  jmp     short loc_1800900D0
0x180090102  lea     rcx, [rbx+88h]
0x180090109  lea     rdx, [rsp+1B0h+var_180]
0x18009010e  call    cs:__imp_?FwPortsToString@@YAJQEAU_tag_FW_PORTS@@PEAPEAG@Z; FwPortsToString(_tag_FW_PORTS * const,ushort * *)
0x180090115  nop     dword ptr [rax+rax+00h]
0x18009011a  lea     rcx, [rbx+0E8h]
0x180090121  lea     rdx, [rsp+1B0h+var_178]
0x180090126  call    cs:__imp_?FwPortsToString@@YAJQEAU_tag_FW_PORTS@@PEAPEAG@Z; FwPortsToString(_tag_FW_PORTS * const,ushort * *)
0x18009012d  nop     dword ptr [rax+rax+00h]
0x180090132  lea     rcx, [rbx+40h]
0x180090136  mov     r8d, 1
0x18009013c  lea     rdx, [rsp+1B0h+var_170]
0x180090141  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x180090148  nop     dword ptr [rax+rax+00h]
0x18009014d  lea     rcx, [rbx+0A0h]
0x180090154  mov     r8d, 1
0x18009015a  lea     rdx, [rsp+1B0h+var_168]
0x18009015f  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x180090166  nop     dword ptr [rax+rax+00h]
0x18009016b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x180090172  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x180090177  mov     rdx, [rbx+10h]; unsigned __int16 *
0x18009017b  lea     rcx, [rbp+0B0h+var_130]; struct _EVENT_DATA_DESCRIPTOR *
0x18009017f  test    al, al
0x180090181  mov     qword ptr [rsp+1B0h+var_150.Size], 4
0x18009018a  lea     rax, [rbp+0B0h+arg_28]
0x180090191  mov     [rsp+1B0h+var_138], 4
0x18009019a  mov     [rsp+1B0h+var_150.Ptr], rax
0x18009019f  lea     rsi, [rbx+28h]
0x1800901a3  lea     rax, [rbp+0B0h+arg_8]
0x1800901aa  mov     [rsp+1B0h+var_140], rax
0x1800901af  lea     r14, [rbx+20h]
0x1800901b3  lea     r15, [rbx+24h]
0x1800901b7  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800901bc  mov     rdx, [rbx+18h]; unsigned __int16 *
0x1800901c0  lea     rcx, [rbp+0B0h+var_120]; struct _EVENT_DATA_DESCRIPTOR *
0x1800901c4  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800901c9  mov     rdx, [rsp+1B0h+var_180]; unsigned __int16 *
0x1800901ce  lea     rax, [rbx+100h]
0x1800901d5  mov     [rbp+0B0h+var_E0], rax
0x1800901d9  lea     rcx, [rbp+0B0h+var_C0]; struct _EVENT_DATA_DESCRIPTOR *
0x1800901dd  lea     rax, [rbx+38h]
0x1800901e1  mov     [rbp+0B0h+var_D8], 4
0x1800901e9  mov     [rbp+0B0h+var_D0], rax
0x1800901ed  mov     [rbp+0B0h+var_E8], 4
0x1800901f5  mov     [rbp+0B0h+var_F0], r15
0x1800901f9  mov     [rbp+0B0h+var_F8], 2
0x180090201  mov     [rbp+0B0h+var_100], r14
0x180090205  mov     [rbp+0B0h+var_108], 10h
0x18009020d  mov     [rbp+0B0h+var_110], rsi
0x180090211  mov     [rbp+0B0h+var_C8], 2
0x180090219  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18009021e  mov     rdx, [rsp+1B0h+var_178]; unsigned __int16 *
0x180090223  lea     rcx, [rbp+0B0h+var_B0]; struct _EVENT_DATA_DESCRIPTOR *
0x180090227  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18009022c  mov     rdx, [rsp+1B0h+var_170]; unsigned __int16 *
0x180090231  lea     rcx, [rbp+0B0h+var_A0]; struct _EVENT_DATA_DESCRIPTOR *
0x180090235  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18009023a  mov     rdx, [rsp+1B0h+var_168]; unsigned __int16 *
0x18009023f  lea     rcx, [rbp+0B0h+var_90]; struct _EVENT_DATA_DESCRIPTOR *
0x180090243  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180090248  movzx   edx, word ptr [rbx+104h]; unsigned __int16
0x18009024f  lea     r8, [rsp+1B0h+var_160]; unsigned __int16 *
0x180090254  lea     rcx, [rbp+0B0h+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x180090258  call    ?FwSerializeActiveEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@GPEAG@Z; FwSerializeActiveEventParam(_EVENT_DATA_DESCRIPTOR *,ushort,ushort *)
0x18009025d  mov     rdx, r13; void *
0x180090260  lea     rcx, [rbp+0B0h+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x180090264  call    ?FwSerializeSIDEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEAX@Z; FwSerializeSIDEventParam(_EVENT_DATA_DESCRIPTOR *,void *)
0x180090269  mov     rdx, [rsp+1B0h+var_188]; unsigned __int16 *
0x18009026e  lea     rcx, [rbp+0B0h+var_60]; struct _EVENT_DATA_DESCRIPTOR *
0x180090272  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180090277  lea     r8, [rsp+1B0h+var_150]; struct _EVENT_DATA_DESCRIPTOR *
0x18009027c  mov     edx, 10h; unsigned int
0x180090281  mov     rcx, r12; struct _EVENT_DESCRIPTOR *
0x180090284  call    ?FwLogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; FwLogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x180090289  mov     edi, eax
0x18009028b  mov     rcx, [rsp+1B0h+var_180]
0x180090290  call    cs:__imp_FwFree
0x180090297  nop     dword ptr [rax+rax+00h]
0x18009029c  mov     rcx, [rsp+1B0h+var_178]
0x1800902a1  call    cs:__imp_FwFree
0x1800902a8  nop     dword ptr [rax+rax+00h]
0x1800902ad  mov     rcx, [rsp+1B0h+var_170]
0x1800902b2  call    cs:__imp_FwFree
0x1800902b9  nop     dword ptr [rax+rax+00h]
0x1800902be  mov     rcx, [rsp+1B0h+var_168]
0x1800902c3  call    cs:__imp_FwFree
0x1800902ca  nop     dword ptr [rax+rax+00h]
0x1800902cf  mov     eax, edi
0x1800902d1  mov     rcx, [rbp+0B0h+var_50]
0x1800902d5  xor     rcx, rsp; StackCookie
0x1800902d8  call    __security_check_cookie
0x1800902dd  add     rsp, 178h
0x1800902e4  pop     r15
0x1800902e6  pop     r14
0x1800902e8  pop     r13
0x1800902ea  pop     r12
0x1800902ec  pop     rdi
0x1800902ed  pop     rsi
0x1800902ee  pop     rbx
0x1800902ef  pop     rbp
0x1800902f0  retn
```
