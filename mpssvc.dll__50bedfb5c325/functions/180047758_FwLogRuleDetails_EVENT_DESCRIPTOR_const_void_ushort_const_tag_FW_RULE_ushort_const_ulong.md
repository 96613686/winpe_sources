# FwLogRuleDetails(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_RULE *,ushort const *,ulong)

- ea: `0x180047758`
- end: `0x180047bfd`
- name: `?FwLogRuleDetails@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGPEAU_tag_FW_RULE@@2K@Z`
- size: `1189`
- prototype: `unsigned int __usercall@<eax>(const struct _EVENT_DESCRIPTOR *@<rcx>, void *@<rdx>, const unsigned __int16 *@<r8>, struct _tag_FW_RULE *@<r9>, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800476e4`

## callees

- `0x18002d340`
- `0x180047758`
- `0x180048250`
- `0x1800482b0`
- `0x18006b940`
- `0x18006b9ac`
- `0x18006d29c`
- `0x1800729c0`
- `0x180073488`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004781f`
- `OLEAUT32!__imp_SysAllocString` at `0x180047859`
- `OLEAUT32!__imp_SysAllocString` at `0x18004781f`
- `OLEAUT32!__imp_SysAllocString` at `0x180047859`
- `OLEAUT32!__imp_SysFreeString` at `0x180047b84`
- `OLEAUT32!__imp_SysFreeString` at `0x180047b98`
- `OLEAUT32!__imp_SysFreeString` at `0x180047b84`
- `OLEAUT32!__imp_SysFreeString` at `0x180047b98`
- `fwbase!FwGetPolicyAppIdFromSDDLString` at `0x180047885`
- `fwbase!FwGetPolicyAppIdFromSDDLString` at `0x180047885`
- `fwbase!FwPortsToString` at `0x18004780e`
- `fwbase!FwPortsToString` at `0x180047848`
- `fwbase!FwPortsToString` at `0x18004780e`
- `fwbase!FwPortsToString` at `0x180047848`
- `fwbase!FwFree` at `0x180047833`
- `fwbase!FwFree` at `0x18004786d`
- `fwbase!FwFree` at `0x180047ba9`
- `fwbase!FwFree` at `0x180047bba`
- `fwbase!FwFree` at `0x180047bcb`
- `fwbase!FwFree` at `0x180047833`
- `fwbase!FwFree` at `0x18004786d`
- `fwbase!FwFree` at `0x180047ba9`
- `fwbase!FwFree` at `0x180047bba`
- `fwbase!FwFree` at `0x180047bcb`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18004789d`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x1800478b8`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18004789d`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x1800478b8`

## pseudocode

```c
__int64 __fastcall FwLogRuleDetails(
        const struct _EVENT_DESCRIPTOR *a1,
        void *a2,
        const unsigned __int16 *a3,
        struct _tag_FW_RULE *a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  const unsigned __int16 *v6; // rbx
  unsigned __int16 *v8; // r15
  unsigned __int16 *v9; // r14
  const unsigned __int16 *v11; // rdx
  __int16 v12; // ax
  unsigned __int16 v13; // dx
  __int64 v14; // r8
  __int64 v15; // rdx
  unsigned int v16; // ebx
  OLECHAR *psz; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v21; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v22; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v23; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v25; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v26; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v27; // [rsp+5Ch] [rbp-A4h] BYREF
  _WORD v28[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[512]; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+270h] [rbp+170h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+280h] [rbp+180h] BYREF
  char *v32; // [rsp+290h] [rbp+190h]
  __int64 v33; // [rsp+298h] [rbp+198h]
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+2A0h] [rbp+1A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+2B0h] [rbp+1B0h] BYREF
  char *v36; // [rsp+2C0h] [rbp+1C0h]
  __int64 v37; // [rsp+2C8h] [rbp+1C8h]
  char *v38; // [rsp+2D0h] [rbp+1D0h]
  __int64 v39; // [rsp+2D8h] [rbp+1D8h]
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+2E0h] [rbp+1E0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v41; // [rsp+2F0h] [rbp+1F0h] BYREF
  char *v42; // [rsp+300h] [rbp+200h]
  __int64 v43; // [rsp+308h] [rbp+208h]
  char *v44; // [rsp+310h] [rbp+210h]
  __int64 v45; // [rsp+318h] [rbp+218h]
  struct _EVENT_DATA_DESCRIPTOR v46; // [rsp+320h] [rbp+220h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+330h] [rbp+230h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v48; // [rsp+340h] [rbp+240h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+350h] [rbp+250h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v50; // [rsp+360h] [rbp+260h] BYREF
  char *v51; // [rsp+370h] [rbp+270h]
  __int64 v52; // [rsp+378h] [rbp+278h]
  __int16 *v53; // [rsp+380h] [rbp+280h]
  __int64 v54; // [rsp+388h] [rbp+288h]
  struct _EVENT_DATA_DESCRIPTOR v55; // [rsp+390h] [rbp+290h] BYREF
  __int16 *v56; // [rsp+3A0h] [rbp+2A0h]
  __int64 v57; // [rsp+3A8h] [rbp+2A8h]
  _BYTE v58[16]; // [rsp+3B0h] [rbp+2B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v59; // [rsp+3C0h] [rbp+2C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v60; // [rsp+3D0h] [rbp+2D0h] BYREF
  char *v61; // [rsp+3E0h] [rbp+2E0h]
  __int64 v62; // [rsp+3E8h] [rbp+2E8h]
  char *v63; // [rsp+3F0h] [rbp+2F0h]
  __int64 v64; // [rsp+3F8h] [rbp+2F8h]
  __int16 *v65; // [rsp+400h] [rbp+300h]
  __int64 v66; // [rsp+408h] [rbp+308h]
  struct _EVENT_DATA_DESCRIPTOR v67; // [rsp+410h] [rbp+310h] BYREF
  unsigned int *v68; // [rsp+420h] [rbp+320h]
  __int64 v69; // [rsp+428h] [rbp+328h]

  v6 = a5;
  v21 = 0;
  v22 = 0;
  v8 = 0;
  v23 = 0;
  v9 = 0;
  v25 = 0;
  v26 = 0;
  v24 = 0;
  v28[0] = 0;
  v27 = 0;
  memset_0(v29, 0, 0x1F8u);
  if ( a4 )
  {
    if ( *((_WORD *)a4 + 24) == 6 || *((_WORD *)a4 + 24) == 17 )
    {
      psz = 0;
      FwPortsToString((struct _tag_FW_RULE *)((char *)a4 + 56), &psz);
      v8 = SysAllocString(psz);
      FwFree(psz);
      FwPortsToString((struct _tag_FW_RULE *)((char *)a4 + 80), &psz);
      v9 = SysAllocString(psz);
      FwFree(psz);
    }
    FwGetPolicyAppIdFromSDDLString(*((_QWORD *)a4 + 46), &v23);
    GetOpenPortorAuthAppAddrAsString((char *)a4 + 104, &v21, 1);
    GetOpenPortorAuthAppAddrAsString((char *)a4 + 176, &v22, 1);
  }
  else
  {
    a4 = (struct _tag_FW_RULE *)v29;
  }
  FwSerializeStringEventParam(&v30, *((const unsigned __int16 **)a4 + 2));
  if ( !a5 )
    v6 = (const unsigned __int16 *)*((_QWORD *)a4 + 3);
  FwSerializeStringEventParam(&v31, v6);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
  v11 = (const unsigned __int16 *)*((_QWORD *)a4 + 34);
  v32 = (char *)a4 + 340;
  v33 = 4;
  FwSerializeStringEventParam(&v34, v11);
  FwSerializeStringEventParam(&v35, *((const unsigned __int16 **)a4 + 35));
  v36 = (char *)a4 + 44;
  v37 = 4;
  v38 = (char *)a4 + 48;
  v39 = 2;
  FwSerializeStringEventParam(&v40, v8);
  FwSerializeStringEventParam(&v41, v9);
  v44 = (char *)a4 + 40;
  v42 = (char *)a4 + 288;
  v43 = 4;
  v45 = 4;
  FwSerializeStringEventParam(&v46, v21);
  FwSerializeStringEventParam(&v47, v22);
  FwSerializeStringEventParam(&v48, *((const unsigned __int16 **)a4 + 37));
  FwSerializeStringEventParam(&v49, *((const unsigned __int16 **)a4 + 38));
  FwSerializeStringEventParam(&v50, *((const unsigned __int16 **)a4 + 39));
  v52 = 2;
  v12 = *((_WORD *)a4 + 146) & 1;
  v51 = (char *)a4 + 292;
  v24 = v12;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
  v13 = *((_WORD *)a4 + 146);
  v53 = &v24;
  v54 = 2;
  FwSerializeEdgeTraversalEventParam(&v55, v13, &v27);
  v25 = (*((_BYTE *)a4 + 292) & 0x10) != 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
  v14 = *((unsigned __int16 *)a4 + 146);
  v15 = *((unsigned int *)a4 + 72);
  v56 = &v25;
  v57 = 2;
  FwSerializeSecurityEventParam(v58, v15, v14, v28);
  FwSerializeSIDEventParam(&v59, a2);
  FwSerializeStringEventParam(&v60, a3);
  v64 = 4;
  v61 = (char *)a4 + 8;
  v63 = (char *)a4 + 336;
  v62 = 2;
  v26 = (*((_WORD *)a4 + 146) & 0x800) != 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
  v65 = &v26;
  v66 = 2;
  FwSerializeStringEventParam(&v67, v23);
  v69 = 4;
  v68 = &a6;
  v16 = FwLogEvent(a1, 0x1Cu, &v30);
  if ( v8 )
    SysFreeString(v8);
  if ( v9 )
    SysFreeString(v9);
  FwFree(v21);
  FwFree(v22);
  FwFree(v23);
  return v16;
}

```

## disassembly

```asm
0x180047758  push    rbp
0x18004775a  push    rbx
0x18004775b  push    rsi
0x18004775c  push    rdi
0x18004775d  push    r12
0x18004775f  push    r13
0x180047761  push    r14
0x180047763  push    r15
0x180047765  lea     rbp, [rsp-348h]
0x18004776d  sub     rsp, 448h
0x180047774  mov     rax, cs:__security_cookie
0x18004777b  xor     rax, rsp
0x18004777e  mov     [rbp+380h+var_50], rax
0x180047785  mov     rbx, [rbp+380h+arg_20]
0x18004778c  xor     r12d, r12d
0x18004778f  mov     [rsp+480h+var_458], r8
0x180047794  mov     r13, rcx
0x180047797  mov     [rsp+480h+var_460], rdx
0x18004779c  lea     rcx, [rsp+480h+var_410]; void *
0x1800477a1  xor     edx, edx; Val
0x1800477a3  mov     [rsp+480h+var_448], r12
0x1800477a8  mov     r8d, 1F8h; Size
0x1800477ae  mov     [rsp+480h+var_440], r12
0x1800477b3  mov     r15d, r12d
0x1800477b6  mov     [rsp+480h+var_438], r12
0x1800477bb  mov     r14d, r12d
0x1800477be  mov     [rsp+480h+var_42C], r12w
0x1800477c4  mov     [rsp+480h+var_428], r12w
0x1800477ca  mov     rsi, r9
0x1800477cd  mov     [rsp+480h+var_430], r12w
0x1800477d3  mov     [rsp+480h+var_420], r12w
0x1800477d9  mov     [rsp+480h+var_424], r12w
0x1800477df  call    memset_0
0x1800477e4  lea     edi, [r12+1]
0x1800477e9  test    rsi, rsi
0x1800477ec  jz      loc_1800478C6
0x1800477f2  cmp     word ptr [rsi+30h], 6
0x1800477f7  jz      short loc_180047800
0x1800477f9  cmp     word ptr [rsi+30h], 11h
0x1800477fe  jnz     short loc_180047879
0x180047800  lea     rcx, [rsi+38h]
0x180047804  mov     [rsp+480h+psz], r12
0x180047809  lea     rdx, [rsp+480h+psz]
0x18004780e  call    cs:__imp_?FwPortsToString@@YAJQEAU_tag_FW_PORTS@@PEAPEAG@Z; FwPortsToString(_tag_FW_PORTS * const,ushort * *)
0x180047815  nop     dword ptr [rax+rax+00h]
0x18004781a  mov     rcx, [rsp+480h+psz]; psz
0x18004781f  call    cs:__imp_SysAllocString
0x180047826  nop     dword ptr [rax+rax+00h]
0x18004782b  mov     rcx, [rsp+480h+psz]
0x180047830  mov     r15, rax
0x180047833  call    cs:__imp_FwFree
0x18004783a  nop     dword ptr [rax+rax+00h]
0x18004783f  lea     rcx, [rsi+50h]
0x180047843  lea     rdx, [rsp+480h+psz]
0x180047848  call    cs:__imp_?FwPortsToString@@YAJQEAU_tag_FW_PORTS@@PEAPEAG@Z; FwPortsToString(_tag_FW_PORTS * const,ushort * *)
0x18004784f  nop     dword ptr [rax+rax+00h]
0x180047854  mov     rcx, [rsp+480h+psz]; psz
0x180047859  call    cs:__imp_SysAllocString
0x180047860  nop     dword ptr [rax+rax+00h]
0x180047865  mov     rcx, [rsp+480h+psz]
0x18004786a  mov     r14, rax
0x18004786d  call    cs:__imp_FwFree
0x180047874  nop     dword ptr [rax+rax+00h]
0x180047879  mov     rcx, [rsi+170h]
0x180047880  lea     rdx, [rsp+480h+var_438]
0x180047885  call    cs:__imp_FwGetPolicyAppIdFromSDDLString
0x18004788c  nop     dword ptr [rax+rax+00h]
0x180047891  lea     rcx, [rsi+68h]
0x180047895  mov     r8d, edi
0x180047898  lea     rdx, [rsp+480h+var_448]
0x18004789d  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x1800478a4  nop     dword ptr [rax+rax+00h]
0x1800478a9  lea     rcx, [rsi+0B0h]
0x1800478b0  mov     r8d, edi
0x1800478b3  lea     rdx, [rsp+480h+var_440]
0x1800478b8  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x1800478bf  nop     dword ptr [rax+rax+00h]
0x1800478c4  jmp     short loc_1800478CB
0x1800478c6  lea     rsi, [rsp+480h+var_410]
0x1800478cb  mov     rdx, [rsi+10h]; unsigned __int16 *
0x1800478cf  lea     rcx, [rbp+380h+var_210]; struct _EVENT_DATA_DESCRIPTOR *
0x1800478d6  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800478db  test    rbx, rbx
0x1800478de  jnz     short loc_1800478E4
0x1800478e0  mov     rbx, [rsi+18h]
0x1800478e4  mov     rdx, rbx; unsigned __int16 *
0x1800478e7  lea     rcx, [rbp+380h+var_200]; struct _EVENT_DATA_DESCRIPTOR *
0x1800478ee  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800478f3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x1800478fa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x1800478ff  mov     rdx, [rsi+110h]; unsigned __int16 *
0x180047906  lea     rcx, [rsi+154h]
0x18004790d  mov     [rbp+380h+var_1F0], rcx
0x180047914  lea     rbx, [rsi+2Ch]
0x180047918  lea     rcx, [rbp+380h+var_1E0]; struct _EVENT_DATA_DESCRIPTOR *
0x18004791f  mov     [rbp+380h+var_1E8], 4
0x18004792a  lea     rdi, [rsi+30h]
0x18004792e  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180047933  mov     rdx, [rsi+118h]; unsigned __int16 *
0x18004793a  lea     rcx, [rbp+380h+var_1D0]; struct _EVENT_DATA_DESCRIPTOR *
0x180047941  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180047946  mov     rdx, r15; unsigned __int16 *
0x180047949  mov     [rbp+380h+var_1C0], rbx
0x180047950  lea     rcx, [rbp+380h+var_1A0]; struct _EVENT_DATA_DESCRIPTOR *
0x180047957  mov     [rbp+380h+var_1B8], 4
0x180047962  mov     [rbp+380h+var_1B0], rdi
0x180047969  mov     [rbp+380h+var_1A8], 2
0x180047974  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180047979  mov     rdx, r14; unsigned __int16 *
0x18004797c  lea     rcx, [rbp+380h+var_190]; struct _EVENT_DATA_DESCRIPTOR *
0x180047983  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180047988  mov     rdx, [rsp+480h+var_448]; unsigned __int16 *
0x18004798d  lea     rax, [rsi+28h]
0x180047991  lea     rdi, [rsi+120h]
0x180047998  mov     [rbp+380h+var_170], rax
0x18004799f  lea     rcx, [rbp+380h+var_160]; struct _EVENT_DATA_DESCRIPTOR *
0x1800479a6  mov     [rbp+380h+var_180], rdi
0x1800479ad  mov     [rbp+380h+var_178], 4
0x1800479b8  mov     [rbp+380h+var_168], 4
0x1800479c3  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800479c8  mov     rdx, [rsp+480h+var_440]; unsigned __int16 *
0x1800479cd  lea     rcx, [rbp+380h+var_150]; struct _EVENT_DATA_DESCRIPTOR *
0x1800479d4  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800479d9  mov     rdx, [rsi+128h]; unsigned __int16 *
0x1800479e0  lea     rcx, [rbp+380h+var_140]; struct _EVENT_DATA_DESCRIPTOR *
0x1800479e7  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800479ec  mov     rdx, [rsi+130h]; unsigned __int16 *
0x1800479f3  lea     rcx, [rbp+380h+var_130]; struct _EVENT_DATA_DESCRIPTOR *
0x1800479fa  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800479ff  mov     rdx, [rsi+138h]; unsigned __int16 *
0x180047a06  lea     rcx, [rbp+380h+var_120]; struct _EVENT_DATA_DESCRIPTOR *
0x180047a0d  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180047a12  lea     rbx, [rsi+124h]
0x180047a19  mov     [rbp+380h+var_108], 2
0x180047a24  movzx   eax, word ptr [rbx]
0x180047a27  and     ax, 1
0x180047a2b  mov     [rbp+380h+var_110], rbx
0x180047a32  mov     [rsp+480h+var_430], ax
0x180047a37  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x180047a3e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x180047a43  movzx   edx, word ptr [rbx]; unsigned __int16
0x180047a46  lea     rax, [rsp+480h+var_430]
0x180047a4b  lea     r8, [rsp+480h+var_424]; unsigned __int16 *
0x180047a50  mov     [rbp+380h+var_100], rax
0x180047a57  lea     rcx, [rbp+380h+var_F0]; struct _EVENT_DATA_DESCRIPTOR *
0x180047a5e  mov     [rbp+380h+var_F8], 2
0x180047a69  call    ?FwSerializeEdgeTraversalEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@GPEAG@Z; FwSerializeEdgeTraversalEventParam(_EVENT_DATA_DESCRIPTOR *,ushort,ushort *)
0x180047a6e  test    byte ptr [rbx], 10h
0x180047a71  mov     eax, r12d
0x180047a74  setnbe  al
0x180047a77  mov     [rsp+480h+var_42C], ax
0x180047a7c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x180047a83  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x180047a88  movzx   r8d, word ptr [rbx]
0x180047a8c  lea     rax, [rsp+480h+var_42C]
0x180047a91  mov     edx, [rdi]
0x180047a93  lea     r9, [rsp+480h+var_420]
0x180047a98  lea     rcx, [rbp+380h+var_D0]
0x180047a9f  mov     [rbp+380h+var_E0], rax
0x180047aa6  mov     [rbp+380h+var_D8], 2
0x180047ab1  call    ?FwSerializeSecurityEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@W4_tag_FW_RULE_ACTION@@GPEAG@Z; FwSerializeSecurityEventParam(_EVENT_DATA_DESCRIPTOR *,_tag_FW_RULE_ACTION,ushort,ushort *)
0x180047ab6  mov     rdx, [rsp+480h+var_460]; void *
0x180047abb  lea     rcx, [rbp+380h+var_C0]; struct _EVENT_DATA_DESCRIPTOR *
0x180047ac2  call    ?FwSerializeSIDEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEAX@Z; FwSerializeSIDEventParam(_EVENT_DATA_DESCRIPTOR *,void *)
0x180047ac7  mov     rdx, [rsp+480h+var_458]; unsigned __int16 *
0x180047acc  lea     rcx, [rbp+380h+var_B0]; struct _EVENT_DATA_DESCRIPTOR *
0x180047ad3  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180047ad8  lea     rax, [rsi+8]
0x180047adc  mov     [rbp+380h+var_88], 4
0x180047ae7  mov     [rbp+380h+var_A0], rax
0x180047aee  lea     rax, [rsi+150h]
0x180047af5  mov     [rbp+380h+var_90], rax
0x180047afc  xor     esi, esi
0x180047afe  mov     eax, 800h
0x180047b03  mov     [rbp+380h+var_98], 2
0x180047b0e  test    [rbx], ax
0x180047b11  mov     eax, esi
0x180047b13  setnbe  al
0x180047b16  mov     [rsp+480h+var_428], ax
0x180047b1b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x180047b22  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x180047b27  mov     rdx, [rsp+480h+var_438]; unsigned __int16 *
0x180047b2c  lea     rax, [rsp+480h+var_428]
0x180047b31  lea     rcx, [rbp+380h+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x180047b38  mov     [rbp+380h+var_80], rax
0x180047b3f  mov     [rbp+380h+var_78], 2
0x180047b4a  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180047b4f  lea     rax, [rbp+380h+arg_28]
0x180047b56  mov     [rbp+380h+var_58], 4
0x180047b61  lea     r8, [rbp+380h+var_210]; struct _EVENT_DATA_DESCRIPTOR *
0x180047b68  mov     [rbp+380h+var_60], rax
0x180047b6f  lea     edx, [rsi+1Ch]; unsigned int
0x180047b72  mov     rcx, r13; struct _EVENT_DESCRIPTOR *
0x180047b75  call    ?FwLogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; FwLogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x180047b7a  mov     ebx, eax
0x180047b7c  test    r15, r15
0x180047b7f  jz      short loc_180047B90
0x180047b81  mov     rcx, r15; bstrString
0x180047b84  call    cs:__imp_SysFreeString
0x180047b8b  nop     dword ptr [rax+rax+00h]
0x180047b90  test    r14, r14
0x180047b93  jz      short loc_180047BA4
0x180047b95  mov     rcx, r14; bstrString
0x180047b98  call    cs:__imp_SysFreeString
0x180047b9f  nop     dword ptr [rax+rax+00h]
0x180047ba4  mov     rcx, [rsp+480h+var_448]
0x180047ba9  call    cs:__imp_FwFree
0x180047bb0  nop     dword ptr [rax+rax+00h]
0x180047bb5  mov     rcx, [rsp+480h+var_440]
0x180047bba  call    cs:__imp_FwFree
0x180047bc1  nop     dword ptr [rax+rax+00h]
0x180047bc6  mov     rcx, [rsp+480h+var_438]
0x180047bcb  call    cs:__imp_FwFree
0x180047bd2  nop     dword ptr [rax+rax+00h]
0x180047bd7  mov     eax, ebx
0x180047bd9  mov     rcx, [rbp+380h+var_50]
0x180047be0  xor     rcx, rsp; StackCookie
0x180047be3  call    __security_check_cookie
0x180047be8  add     rsp, 448h
0x180047bef  pop     r15
0x180047bf1  pop     r14
0x180047bf3  pop     r13
0x180047bf5  pop     r12
0x180047bf7  pop     rdi
0x180047bf8  pop     rsi
0x180047bf9  pop     rbx
0x180047bfa  pop     rbp
0x180047bfb  retn
```
