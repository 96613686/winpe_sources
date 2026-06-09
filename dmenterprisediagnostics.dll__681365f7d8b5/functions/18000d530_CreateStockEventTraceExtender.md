# CreateStockEventTraceExtender

- ea: `0x18000d530`
- end: `0x18000d673`
- name: `CreateStockEventTraceExtender`
- size: `323`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000adcc`
- `0x18000d67c`

## callees

- `0x18000a13c`
- `0x18000a2fc`
- `0x18000af80`
- `0x18000d530`
- `0x18000f670`
- `0x180014a00`
- `0x180019d4c`
- `0x18001ba0c`
- `0x18001d8a0`
- `0x18001fa9c`
- `0x180020e0c`
- `0x18002168c`
- `0x1800226b0`

## pseudocode

```c
__int64 __fastcall CreateStockEventTraceExtender(const struct _GUID *a1)
{
  __int64 v1; // rdx
  const struct _GUID *v2; // rcx
  __int64 v3; // r9
  __int64 v5; // rdx
  const struct _GUID *v6; // rcx
  __int64 v7; // r9
  __int64 v8; // rdx
  const struct _GUID *v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rdx
  const struct _GUID *v12; // rcx
  __int64 v13; // r9
  __int64 v14; // rdx
  const struct _GUID *v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rdx
  const struct _GUID *v18; // rcx
  __int64 v19; // r9
  __int64 v20; // rdx
  const struct _GUID *v21; // rcx
  __int64 v22; // r9
  __int64 v23; // rdx
  const struct _GUID *v24; // rcx
  __int64 v25; // r9
  __int64 v26; // rdx
  const struct _GUID *v27; // rcx
  __int64 v28; // r9
  __int64 v29; // rdx
  const struct _GUID *v30; // rcx
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r9

  if ( (unsigned int)InlineIsEqualGUID(a1, &GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(
             v2,
             v1,
             v3);
  if ( (unsigned int)InlineIsEqualGUID(v2, &GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(
             v6,
             v5,
             v7);
  if ( (unsigned int)InlineIsEqualGUID(v6, &GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(
             v9,
             v8,
             v10);
  if ( (unsigned int)InlineIsEqualGUID(v9, &GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(
             v12,
             v11,
             v13);
  if ( (unsigned int)InlineIsEqualGUID(v12, &GUID_aa981571_9628_42e8_a132_74c040a6fff2) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(
             v15,
             v14,
             v16);
  if ( (unsigned int)InlineIsEqualGUID(v15, &GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(
             v18,
             v17,
             v19);
  if ( (unsigned int)InlineIsEqualGUID(v18, &GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(
             v21,
             v20,
             v22);
  if ( (unsigned int)InlineIsEqualGUID(v21, &GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(
             v24,
             v23,
             v25);
  if ( (unsigned int)InlineIsEqualGUID(v24, &GUID_164122f2_1705_40f8_9bb0_5692e8aa677a) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(
             v27,
             v26,
             v28);
  if ( (unsigned int)InlineIsEqualGUID(v27, &GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(
             v30,
             v29,
             v31);
  if ( (unsigned int)InlineIsEqualGUID(v30, &GUID_109fa25d_d55e_4acd_b170_340b8194720e) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(
             v33,
             v32,
             v34);
  return 2147746065LL;
}

```

## disassembly

```asm
0x18000d530  sub     rsp, 28h
0x18000d534  lea     rdx, _GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d; struct _GUID *
0x18000d53b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d540  test    eax, eax
0x18000d542  jz      short loc_18000D550
0x18000d544  mov     r8, r9
0x18000d547  add     rsp, 28h
0x18000d54b  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d550  lea     rdx, _GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea; struct _GUID *
0x18000d557  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d55c  test    eax, eax
0x18000d55e  jz      short loc_18000D56C
0x18000d560  mov     r8, r9
0x18000d563  add     rsp, 28h
0x18000d567  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d56c  lea     rdx, _GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2; struct _GUID *
0x18000d573  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d578  test    eax, eax
0x18000d57a  jz      short loc_18000D588
0x18000d57c  mov     r8, r9
0x18000d57f  add     rsp, 28h
0x18000d583  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d588  lea     rdx, _GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25; struct _GUID *
0x18000d58f  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d594  test    eax, eax
0x18000d596  jz      short loc_18000D5A4
0x18000d598  mov     r8, r9
0x18000d59b  add     rsp, 28h
0x18000d59f  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d5a4  lea     rdx, _GUID_aa981571_9628_42e8_a132_74c040a6fff2; struct _GUID *
0x18000d5ab  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d5b0  test    eax, eax
0x18000d5b2  jz      short loc_18000D5C0
0x18000d5b4  mov     r8, r9
0x18000d5b7  add     rsp, 28h
0x18000d5bb  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d5c0  lea     rdx, _GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e; struct _GUID *
0x18000d5c7  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d5cc  test    eax, eax
0x18000d5ce  jz      short loc_18000D5DC
0x18000d5d0  mov     r8, r9
0x18000d5d3  add     rsp, 28h
0x18000d5d7  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d5dc  lea     rdx, _GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7; struct _GUID *
0x18000d5e3  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d5e8  test    eax, eax
0x18000d5ea  jz      short loc_18000D5F8
0x18000d5ec  mov     r8, r9
0x18000d5ef  add     rsp, 28h
0x18000d5f3  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d5f8  lea     rdx, _GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295; struct _GUID *
0x18000d5ff  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d604  test    eax, eax
0x18000d606  jz      short loc_18000D614
0x18000d608  mov     r8, r9
0x18000d60b  add     rsp, 28h
0x18000d60f  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d614  lea     rdx, _GUID_164122f2_1705_40f8_9bb0_5692e8aa677a; struct _GUID *
0x18000d61b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d620  test    eax, eax
0x18000d622  jz      short loc_18000D630
0x18000d624  mov     r8, r9
0x18000d627  add     rsp, 28h
0x18000d62b  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d630  lea     rdx, _GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8; struct _GUID *
0x18000d637  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d63c  test    eax, eax
0x18000d63e  jz      short loc_18000D64C
0x18000d640  mov     r8, r9
0x18000d643  add     rsp, 28h
0x18000d647  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d64c  lea     rdx, _GUID_109fa25d_d55e_4acd_b170_340b8194720e; struct _GUID *
0x18000d653  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d658  test    eax, eax
0x18000d65a  jz      short loc_18000D668
0x18000d65c  mov     r8, r9
0x18000d65f  add     rsp, 28h
0x18000d663  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d668  mov     eax, 80040111h
0x18000d66d  add     rsp, 28h
0x18000d671  retn
```
