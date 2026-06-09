# FwLogRuleDetails(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_RULE *,ushort const *,ulong)

- ea: `0x180027690`
- end: `0x180027afe`
- name: `?FwLogRuleDetails@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGPEAU_tag_FW_RULE@@2K@Z`
- size: `1134`
- prototype: `unsigned int __fastcall(const struct _EVENT_DESCRIPTOR *, void *, const unsigned __int16 *, struct _tag_FW_RULE *, const unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027624`

## callees

- `0x180027690`
- `0x180027b04`
- `0x180029b48`
- `0x180067fc8`
- `0x180068034`
- `0x18006a4a8`
- `0x18006f520`
- `0x18006ffc8`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180027a94`
- `ntdll!EtwEventWrite` at `0x180027a94`
- `ntdll!EtwEventEnabled` at `0x180027a75`
- `ntdll!EtwEventEnabled` at `0x180027a75`
- `OLEAUT32!__imp_SysAllocString` at `0x180027750`
- `OLEAUT32!__imp_SysAllocString` at `0x180027778`
- `OLEAUT32!__imp_SysAllocString` at `0x180027750`
- `OLEAUT32!__imp_SysAllocString` at `0x180027778`
- `OLEAUT32!__imp_SysFreeString` at `0x180027aa4`
- `OLEAUT32!__imp_SysFreeString` at `0x180027ab2`
- `OLEAUT32!__imp_SysFreeString` at `0x180027aa4`
- `OLEAUT32!__imp_SysFreeString` at `0x180027ab2`
- `fwbase!FwGetPolicyAppIdFromSDDLString` at `0x180027798`
- `fwbase!FwGetPolicyAppIdFromSDDLString` at `0x180027798`
- `fwbase!FwPortsToString` at `0x180027745`
- `fwbase!FwPortsToString` at `0x18002776d`
- `fwbase!FwPortsToString` at `0x180027745`
- `fwbase!FwPortsToString` at `0x18002776d`
- `fwbase!FwFree` at `0x18002775e`
- `fwbase!FwFree` at `0x180027786`
- `fwbase!FwFree` at `0x180027abd`
- `fwbase!FwFree` at `0x180027ac8`
- `fwbase!FwFree` at `0x180027ad3`
- `fwbase!FwFree` at `0x18002775e`
- `fwbase!FwFree` at `0x180027786`
- `fwbase!FwFree` at `0x180027abd`
- `fwbase!FwFree` at `0x180027ac8`
- `fwbase!FwFree` at `0x180027ad3`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x1800277aa`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x1800277bf`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x1800277aa`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x1800277bf`

## pseudocode

```c
__int64 __fastcall FwLogRuleDetails(
        const struct _EVENT_DESCRIPTOR *a1,
        void *a2,
        const unsigned __int16 *a3,
        struct _tag_FW_RULE *a4,
        unsigned __int16 *a5,
        char a6)
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
  char *v68; // [rsp+420h] [rbp+320h]
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
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
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
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
  v13 = *((_WORD *)a4 + 146);
  v53 = &v24;
  v54 = 2;
  FwSerializeEdgeTraversalEventParam(&v55, v13, &v27);
  v25 = (*((_BYTE *)a4 + 292) & 0x10) != 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
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
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
  v65 = &v26;
  v66 = 2;
  FwSerializeStringEventParam(&v67, v23);
  v68 = &a6;
  v69 = 4;
  v16 = 0;
  if ( (unsigned __int8)EtwEventEnabled(qword_180131410, a1) )
    v16 = EtwEventWrite(qword_180131410, a1, 28, &v30);
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
0x180027690  push    rbp
0x180027692  push    rbx
0x180027693  push    rsi
0x180027694  push    rdi
0x180027695  push    r12
0x180027697  push    r13
0x180027699  push    r14
0x18002769b  push    r15
0x18002769d  lea     rbp, [rsp-348h]
0x1800276a5  sub     rsp, 448h
0x1800276ac  mov     rax, cs:__security_cookie
0x1800276b3  xor     rax, rsp
0x1800276b6  mov     [rbp+380h+var_50], rax
0x1800276bd  mov     rbx, [rbp+380h+arg_20]
0x1800276c4  xor     r13d, r13d
0x1800276c7  mov     [rsp+480h+var_458], r8
0x1800276cc  mov     r12, rcx
0x1800276cf  mov     [rsp+480h+var_460], rdx
0x1800276d4  lea     rcx, [rsp+480h+var_410]; void *
0x1800276d9  xor     edx, edx; Val
0x1800276db  mov     [rsp+480h+var_448], r13
0x1800276e0  mov     r8d, 1F8h; Size
0x1800276e6  mov     [rsp+480h+var_440], r13
0x1800276eb  mov     r15d, r13d
0x1800276ee  mov     [rsp+480h+var_438], r13
0x1800276f3  mov     r14d, r13d
0x1800276f6  mov     [rsp+480h+var_42C], r13w
0x1800276fc  mov     [rsp+480h+var_428], r13w
0x180027702  mov     rsi, r9
0x180027705  mov     [rsp+480h+var_430], r13w
0x18002770b  mov     [rsp+480h+var_420], r13w
0x180027711  mov     [rsp+480h+var_424], r13w
0x180027717  call    memset_0
0x18002771c  lea     edi, [r13+1]
0x180027720  test    rsi, rsi
0x180027723  jz      loc_1800277C7
0x180027729  cmp     word ptr [rsi+30h], 6
0x18002772e  jz      short loc_180027737
0x180027730  cmp     word ptr [rsi+30h], 11h
0x180027735  jnz     short loc_18002778C
0x180027737  lea     rcx, [rsi+38h]
0x18002773b  mov     [rsp+480h+psz], r13
0x180027740  lea     rdx, [rsp+480h+psz]
0x180027745  call    cs:__imp_?FwPortsToString@@YAJQEAU_tag_FW_PORTS@@PEAPEAG@Z; FwPortsToString(_tag_FW_PORTS * const,ushort * *)
0x18002774b  mov     rcx, [rsp+480h+psz]; psz
0x180027750  call    cs:__imp_SysAllocString
0x180027756  mov     rcx, [rsp+480h+psz]
0x18002775b  mov     r15, rax
0x18002775e  call    cs:__imp_FwFree
0x180027764  lea     rcx, [rsi+50h]
0x180027768  lea     rdx, [rsp+480h+psz]
0x18002776d  call    cs:__imp_?FwPortsToString@@YAJQEAU_tag_FW_PORTS@@PEAPEAG@Z; FwPortsToString(_tag_FW_PORTS * const,ushort * *)
0x180027773  mov     rcx, [rsp+480h+psz]; psz
0x180027778  call    cs:__imp_SysAllocString
0x18002777e  mov     rcx, [rsp+480h+psz]
0x180027783  mov     r14, rax
0x180027786  call    cs:__imp_FwFree
0x18002778c  mov     rcx, [rsi+170h]
0x180027793  lea     rdx, [rsp+480h+var_438]
0x180027798  call    cs:__imp_FwGetPolicyAppIdFromSDDLString
0x18002779e  lea     rcx, [rsi+68h]
0x1800277a2  mov     r8d, edi
0x1800277a5  lea     rdx, [rsp+480h+var_448]
0x1800277aa  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x1800277b0  lea     rcx, [rsi+0B0h]
0x1800277b7  mov     r8d, edi
0x1800277ba  lea     rdx, [rsp+480h+var_440]
0x1800277bf  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x1800277c5  jmp     short loc_1800277CC
0x1800277c7  lea     rsi, [rsp+480h+var_410]
0x1800277cc  mov     rdx, [rsi+10h]; unsigned __int16 *
0x1800277d0  lea     rcx, [rbp+380h+var_210]; struct _EVENT_DATA_DESCRIPTOR *
0x1800277d7  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800277dc  test    rbx, rbx
0x1800277df  jnz     short loc_1800277E5
0x1800277e1  mov     rbx, [rsi+18h]
0x1800277e5  mov     rdx, rbx; unsigned __int16 *
0x1800277e8  lea     rcx, [rbp+380h+var_200]; struct _EVENT_DATA_DESCRIPTOR *
0x1800277ef  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800277f4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x1800277fb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x180027800  mov     rdx, [rsi+110h]; unsigned __int16 *
0x180027807  lea     rcx, [rsi+154h]
0x18002780e  mov     [rbp+380h+var_1F0], rcx
0x180027815  lea     rbx, [rsi+2Ch]
0x180027819  lea     rcx, [rbp+380h+var_1E0]; struct _EVENT_DATA_DESCRIPTOR *
0x180027820  mov     [rbp+380h+var_1E8], 4
0x18002782b  lea     rdi, [rsi+30h]
0x18002782f  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180027834  mov     rdx, [rsi+118h]; unsigned __int16 *
0x18002783b  lea     rcx, [rbp+380h+var_1D0]; struct _EVENT_DATA_DESCRIPTOR *
0x180027842  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180027847  mov     rdx, r15; unsigned __int16 *
0x18002784a  mov     [rbp+380h+var_1C0], rbx
0x180027851  lea     rcx, [rbp+380h+var_1A0]; struct _EVENT_DATA_DESCRIPTOR *
0x180027858  mov     [rbp+380h+var_1B8], 4
0x180027863  mov     [rbp+380h+var_1B0], rdi
0x18002786a  mov     [rbp+380h+var_1A8], 2
0x180027875  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18002787a  mov     rdx, r14; unsigned __int16 *
0x18002787d  lea     rcx, [rbp+380h+var_190]; struct _EVENT_DATA_DESCRIPTOR *
0x180027884  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180027889  mov     rdx, [rsp+480h+var_448]; unsigned __int16 *
0x18002788e  lea     rax, [rsi+28h]
0x180027892  lea     rdi, [rsi+120h]
0x180027899  mov     [rbp+380h+var_170], rax
0x1800278a0  lea     rcx, [rbp+380h+var_160]; struct _EVENT_DATA_DESCRIPTOR *
0x1800278a7  mov     [rbp+380h+var_180], rdi
0x1800278ae  mov     [rbp+380h+var_178], 4
0x1800278b9  mov     [rbp+380h+var_168], 4
0x1800278c4  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800278c9  mov     rdx, [rsp+480h+var_440]; unsigned __int16 *
0x1800278ce  lea     rcx, [rbp+380h+var_150]; struct _EVENT_DATA_DESCRIPTOR *
0x1800278d5  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800278da  mov     rdx, [rsi+128h]; unsigned __int16 *
0x1800278e1  lea     rcx, [rbp+380h+var_140]; struct _EVENT_DATA_DESCRIPTOR *
0x1800278e8  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800278ed  mov     rdx, [rsi+130h]; unsigned __int16 *
0x1800278f4  lea     rcx, [rbp+380h+var_130]; struct _EVENT_DATA_DESCRIPTOR *
0x1800278fb  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180027900  mov     rdx, [rsi+138h]; unsigned __int16 *
0x180027907  lea     rcx, [rbp+380h+var_120]; struct _EVENT_DATA_DESCRIPTOR *
0x18002790e  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180027913  lea     rbx, [rsi+124h]
0x18002791a  mov     [rbp+380h+var_108], 2
0x180027925  movzx   eax, word ptr [rbx]
0x180027928  and     ax, 1
0x18002792c  mov     [rbp+380h+var_110], rbx
0x180027933  mov     [rsp+480h+var_430], ax
0x180027938  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18002793f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x180027944  movzx   edx, word ptr [rbx]; unsigned __int16
0x180027947  lea     rax, [rsp+480h+var_430]
0x18002794c  lea     r8, [rsp+480h+var_424]; unsigned __int16 *
0x180027951  mov     [rbp+380h+var_100], rax
0x180027958  lea     rcx, [rbp+380h+var_F0]; struct _EVENT_DATA_DESCRIPTOR *
0x18002795f  mov     [rbp+380h+var_F8], 2
0x18002796a  call    ?FwSerializeEdgeTraversalEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@GPEAG@Z; FwSerializeEdgeTraversalEventParam(_EVENT_DATA_DESCRIPTOR *,ushort,ushort *)
0x18002796f  test    byte ptr [rbx], 10h
0x180027972  mov     eax, r13d
0x180027975  setnbe  al
0x180027978  mov     [rsp+480h+var_42C], ax
0x18002797d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x180027984  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x180027989  movzx   r8d, word ptr [rbx]
0x18002798d  lea     rax, [rsp+480h+var_42C]
0x180027992  mov     edx, [rdi]
0x180027994  lea     r9, [rsp+480h+var_420]
0x180027999  lea     rcx, [rbp+380h+var_D0]
0x1800279a0  mov     [rbp+380h+var_E0], rax
0x1800279a7  mov     [rbp+380h+var_D8], 2
0x1800279b2  call    ?FwSerializeSecurityEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@W4_tag_FW_RULE_ACTION@@GPEAG@Z; FwSerializeSecurityEventParam(_EVENT_DATA_DESCRIPTOR *,_tag_FW_RULE_ACTION,ushort,ushort *)
0x1800279b7  mov     rdx, [rsp+480h+var_460]; void *
0x1800279bc  lea     rcx, [rbp+380h+var_C0]; struct _EVENT_DATA_DESCRIPTOR *
0x1800279c3  call    ?FwSerializeSIDEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEAX@Z; FwSerializeSIDEventParam(_EVENT_DATA_DESCRIPTOR *,void *)
0x1800279c8  mov     rdx, [rsp+480h+var_458]; unsigned __int16 *
0x1800279cd  lea     rcx, [rbp+380h+var_B0]; struct _EVENT_DATA_DESCRIPTOR *
0x1800279d4  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800279d9  lea     rax, [rsi+8]
0x1800279dd  mov     [rbp+380h+var_88], 4
0x1800279e8  mov     [rbp+380h+var_A0], rax
0x1800279ef  lea     rax, [rsi+150h]
0x1800279f6  mov     [rbp+380h+var_90], rax
0x1800279fd  xor     esi, esi
0x1800279ff  mov     eax, 800h
0x180027a04  mov     [rbp+380h+var_98], 2
0x180027a0f  test    [rbx], ax
0x180027a12  mov     eax, esi
0x180027a14  setnbe  al
0x180027a17  mov     [rsp+480h+var_428], ax
0x180027a1c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x180027a23  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x180027a28  mov     rdx, [rsp+480h+var_438]; unsigned __int16 *
0x180027a2d  lea     rax, [rsp+480h+var_428]
0x180027a32  lea     rcx, [rbp+380h+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x180027a39  mov     [rbp+380h+var_80], rax
0x180027a40  mov     [rbp+380h+var_78], 2
0x180027a4b  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180027a50  mov     rcx, cs:qword_180131410
0x180027a57  lea     rax, [rbp+380h+arg_28]
0x180027a5e  mov     rdx, r12
0x180027a61  mov     [rbp+380h+var_60], rax
0x180027a68  mov     [rbp+380h+var_58], 4
0x180027a73  mov     ebx, esi
0x180027a75  call    cs:__imp_EtwEventEnabled
0x180027a7b  test    al, al
0x180027a7d  jz      short loc_180027A9C
0x180027a7f  mov     rcx, cs:qword_180131410
0x180027a86  lea     r9, [rbp+380h+var_210]
0x180027a8d  lea     r8d, [rsi+1Ch]
0x180027a91  mov     rdx, r12
0x180027a94  call    cs:__imp_EtwEventWrite
0x180027a9a  mov     ebx, eax
0x180027a9c  test    r15, r15
0x180027a9f  jz      short loc_180027AAA
0x180027aa1  mov     rcx, r15; bstrString
0x180027aa4  call    cs:__imp_SysFreeString
0x180027aaa  test    r14, r14
0x180027aad  jz      short loc_180027AB8
0x180027aaf  mov     rcx, r14; bstrString
0x180027ab2  call    cs:__imp_SysFreeString
0x180027ab8  mov     rcx, [rsp+480h+var_448]
0x180027abd  call    cs:__imp_FwFree
0x180027ac3  mov     rcx, [rsp+480h+var_440]
0x180027ac8  call    cs:__imp_FwFree
0x180027ace  mov     rcx, [rsp+480h+var_438]
0x180027ad3  call    cs:__imp_FwFree
0x180027ad9  mov     eax, ebx
0x180027adb  mov     rcx, [rbp+380h+var_50]
0x180027ae2  xor     rcx, rsp; StackCookie
0x180027ae5  call    __security_check_cookie
0x180027aea  add     rsp, 448h
0x180027af1  pop     r15
0x180027af3  pop     r14
0x180027af5  pop     r13
0x180027af7  pop     r12
0x180027af9  pop     rdi
0x180027afa  pop     rsi
0x180027afb  pop     rbx
0x180027afc  pop     rbp
0x180027afd  retn
```
