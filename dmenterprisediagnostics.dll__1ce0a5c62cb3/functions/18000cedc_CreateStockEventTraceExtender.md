# CreateStockEventTraceExtender

- ea: `0x18000cedc`
- end: `0x18000d01e`
- name: `CreateStockEventTraceExtender`
- size: `322`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000a844`
- `0x18000d024`

## callees

- `0x180009bd8`
- `0x180009d98`
- `0x18000a9e8`
- `0x18000cedc`
- `0x18000efe8`
- `0x180014198`
- `0x180019318`
- `0x18001af5c`
- `0x18001cd8c`
- `0x18001eeac`
- `0x18002012c`
- `0x18002097c`
- `0x180021960`

## pseudocode

```c
__int64 __fastcall CreateStockEventTraceExtender(const struct _GUID *a1)
{
  __int64 v1; // rdx
  const struct _GUID *v2; // rcx
  _QWORD *v3; // r9
  __int64 v5; // rdx
  const struct _GUID *v6; // rcx
  _QWORD *v7; // r9
  __int64 v8; // rdx
  const struct _GUID *v9; // rcx
  _QWORD *v10; // r9
  __int64 v11; // rdx
  const struct _GUID *v12; // rcx
  _QWORD *v13; // r9
  __int64 v14; // rdx
  const struct _GUID *v15; // rcx
  _QWORD *v16; // r9
  __int64 v17; // rdx
  const struct _GUID *v18; // rcx
  _QWORD *v19; // r9
  __int64 v20; // rdx
  const struct _GUID *v21; // rcx
  _QWORD *v22; // r9
  __int64 v23; // rdx
  const struct _GUID *v24; // rcx
  _QWORD *v25; // r9
  __int64 v26; // rdx
  const struct _GUID *v27; // rcx
  _QWORD *v28; // r9
  __int64 v29; // rdx
  const struct _GUID *v30; // rcx
  _QWORD *v31; // r9
  __int64 v32; // rdx
  __int64 v33; // rcx
  _QWORD *v34; // r9

  if ( (unsigned int)InlineIsEqualGUID(a1, &GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(
             (__int64)v2,
             v1,
             v3);
  if ( (unsigned int)InlineIsEqualGUID(v2, &GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(
             (__int64)v6,
             v5,
             v7);
  if ( (unsigned int)InlineIsEqualGUID(v6, &GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(
             (__int64)v9,
             v8,
             v10);
  if ( (unsigned int)InlineIsEqualGUID(v9, &GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(
             (__int64)v12,
             v11,
             v13);
  if ( (unsigned int)InlineIsEqualGUID(v12, &GUID_aa981571_9628_42e8_a132_74c040a6fff2) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(
             (__int64)v15,
             v14,
             v16);
  if ( (unsigned int)InlineIsEqualGUID(v15, &GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(
             (__int64)v18,
             v17,
             v19);
  if ( (unsigned int)InlineIsEqualGUID(v18, &GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(
             (__int64)v21,
             v20,
             v22);
  if ( (unsigned int)InlineIsEqualGUID(v21, &GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(
             (__int64)v24,
             v23,
             v25);
  if ( (unsigned int)InlineIsEqualGUID(v24, &GUID_164122f2_1705_40f8_9bb0_5692e8aa677a) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(
             (__int64)v27,
             v26,
             v28);
  if ( (unsigned int)InlineIsEqualGUID(v27, &GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8) )
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(
             (__int64)v30,
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
0x18000cedc  sub     rsp, 28h
0x18000cee0  lea     rdx, _GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d; struct _GUID *
0x18000cee7  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000ceec  test    eax, eax
0x18000ceee  jz      short loc_18000CEFC
0x18000cef0  mov     r8, r9
0x18000cef3  add     rsp, 28h
0x18000cef7  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000cefc  lea     rdx, _GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea; struct _GUID *
0x18000cf03  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000cf08  test    eax, eax
0x18000cf0a  jz      short loc_18000CF18
0x18000cf0c  mov     r8, r9
0x18000cf0f  add     rsp, 28h
0x18000cf13  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000cf18  lea     rdx, _GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2; struct _GUID *
0x18000cf1f  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000cf24  test    eax, eax
0x18000cf26  jz      short loc_18000CF34
0x18000cf28  mov     r8, r9
0x18000cf2b  add     rsp, 28h
0x18000cf2f  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000cf34  lea     rdx, _GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25; struct _GUID *
0x18000cf3b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000cf40  test    eax, eax
0x18000cf42  jz      short loc_18000CF50
0x18000cf44  mov     r8, r9
0x18000cf47  add     rsp, 28h
0x18000cf4b  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000cf50  lea     rdx, _GUID_aa981571_9628_42e8_a132_74c040a6fff2; struct _GUID *
0x18000cf57  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000cf5c  test    eax, eax
0x18000cf5e  jz      short loc_18000CF6C
0x18000cf60  mov     r8, r9
0x18000cf63  add     rsp, 28h
0x18000cf67  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000cf6c  lea     rdx, _GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e; struct _GUID *
0x18000cf73  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000cf78  test    eax, eax
0x18000cf7a  jz      short loc_18000CF88
0x18000cf7c  mov     r8, r9
0x18000cf7f  add     rsp, 28h
0x18000cf83  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000cf88  lea     rdx, _GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7; struct _GUID *
0x18000cf8f  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000cf94  test    eax, eax
0x18000cf96  jz      short loc_18000CFA4
0x18000cf98  mov     r8, r9
0x18000cf9b  add     rsp, 28h
0x18000cf9f  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000cfa4  lea     rdx, _GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295; struct _GUID *
0x18000cfab  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000cfb0  test    eax, eax
0x18000cfb2  jz      short loc_18000CFC0
0x18000cfb4  mov     r8, r9
0x18000cfb7  add     rsp, 28h
0x18000cfbb  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000cfc0  lea     rdx, _GUID_164122f2_1705_40f8_9bb0_5692e8aa677a; struct _GUID *
0x18000cfc7  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000cfcc  test    eax, eax
0x18000cfce  jz      short loc_18000CFDC
0x18000cfd0  mov     r8, r9
0x18000cfd3  add     rsp, 28h
0x18000cfd7  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000cfdc  lea     rdx, _GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8; struct _GUID *
0x18000cfe3  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000cfe8  test    eax, eax
0x18000cfea  jz      short loc_18000CFF8
0x18000cfec  mov     r8, r9
0x18000cfef  add     rsp, 28h
0x18000cff3  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000cff8  lea     rdx, _GUID_109fa25d_d55e_4acd_b170_340b8194720e; struct _GUID *
0x18000cfff  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000d004  test    eax, eax
0x18000d006  jz      short loc_18000D014
0x18000d008  mov     r8, r9
0x18000d00b  add     rsp, 28h
0x18000d00f  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d014  mov     eax, 80040111h
0x18000d019  add     rsp, 28h
0x18000d01d  retn
```
