# CompliantHapticInterface::QueryHapticsSupport(void)

- ea: `0x18019c1f8`
- end: `0x18019ce4e`
- name: `?QueryHapticsSupport@CompliantHapticInterface@@AEAAJXZ`
- size: `3158`
- prototype: `__int64 __fastcall(CompliantHapticInterface *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18019c064`

## callees

- `0x18002f9b4`
- `0x18008ead4`
- `0x1800aa878`
- `0x1800af59c`
- `0x1800f08d8`
- `0x1800f0990`
- `0x1800f2478`
- `0x18018e648`
- `0x18019b63c`
- `0x18019b678`
- `0x18019badc`
- `0x18019bb34`
- `0x18019bc10`
- `0x18019be48`
- `0x18019be78`
- `0x18019be9c`
- `0x18019bedc`
- `0x18019c1f8`
- `0x18019ce54`

## import_xrefs

- `HID!HidP_GetLinkCollectionNodes` at `0x18019c2a5`
- `HID!HidP_GetLinkCollectionNodes` at `0x18019c307`
- `HID!HidP_GetLinkCollectionNodes` at `0x18019c2a5`
- `HID!HidP_GetLinkCollectionNodes` at `0x18019c307`
- `HID!HidP_GetCaps` at `0x18019c24e`
- `HID!HidP_GetCaps` at `0x18019c24e`
- `HID!HidP_GetSpecificValueCaps` at `0x18019c3a9`
- `HID!HidP_GetSpecificValueCaps` at `0x18019c462`
- `HID!HidP_GetSpecificValueCaps` at `0x18019c53a`
- `HID!HidP_GetSpecificValueCaps` at `0x18019c5f8`
- `HID!HidP_GetSpecificValueCaps` at `0x18019c80c`
- `HID!HidP_GetSpecificValueCaps` at `0x18019c3a9`
- `HID!HidP_GetSpecificValueCaps` at `0x18019c462`
- `HID!HidP_GetSpecificValueCaps` at `0x18019c53a`
- `HID!HidP_GetSpecificValueCaps` at `0x18019c5f8`
- `HID!HidP_GetSpecificValueCaps` at `0x18019c80c`
- `HID!HidP_GetUsageValue` at `0x18019caa9`
- `HID!HidP_GetUsageValue` at `0x18019cb92`
- `HID!HidP_GetUsageValue` at `0x18019caa9`
- `HID!HidP_GetUsageValue` at `0x18019cb92`

## string_xrefs

- `0x18019c278`: `onecoreuap\windows\moderncore\inputv2\inputprocessors\devices\haptic\hid\lib\complianthapticinterface.cpp`
- `0x18019c628`: `onecoreuap\windows\moderncore\inputv2\inputprocessors\devices\haptic\hid\lib\complianthapticinterface.cpp`
- `0x18019c838`: `onecoreuap\windows\moderncore\inputv2\inputprocessors\devices\haptic\hid\lib\complianthapticinterface.cpp`
- `0x18019cde7`: `onecoreuap\windows\moderncore\inputv2\inputprocessors\devices\haptic\hid\lib\complianthapticinterface.cpp`
- `0x18019ce22`: `onecoreuap\windows\moderncore\inputv2\inputprocessors\devices\haptic\hid\lib\complianthapticinterface.cpp`
- `0x18019c31a`: `Failed to retrieve the link collection`
- `0x18019c2b2`: `Failed to retrieve the link collection count`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CompliantHapticInterface::QueryHapticsSupport(CompliantHapticInterface *this)
{
  unsigned int Caps; // eax
  int v3; // edx
  int v4; // ebx
  __int64 v5; // rdx
  unsigned __int64 v7; // rax
  struct _HIDP_LINK_COLLECTION_NODE *v8; // rbx
  unsigned int LinkCollectionNodes; // eax
  int v10; // edx
  int v11; // edi
  __int64 v12; // rdx
  USHORT i; // r14
  HapticsTrigger *v14; // rax
  __int128 v15; // xmm1
  __int128 v16; // xmm2
  __int128 v17; // xmm3
  __int64 v18; // xmm4_8
  HapticsTrigger *v19; // rax
  __int128 v20; // xmm1
  __int128 v21; // xmm2
  __int128 v22; // xmm3
  __int64 v23; // xmm4_8
  char *v24; // rcx
  unsigned __int64 v25; // rax
  CHAR *v26; // rbx
  unsigned int SpecificValueCaps; // eax
  int v28; // edx
  int FeatureReport; // ebx
  __int64 v30; // rdx
  USHORT v31; // di
  USHORT j; // r8
  CHAR *v33; // r9
  int v34; // eax
  __int128 v35; // xmm6
  __int128 v36; // xmm7
  __int128 v37; // xmm8
  __int128 v38; // xmm9
  __int64 v39; // xmm10_8
  __int64 v40; // rcx
  unsigned __int64 v41; // rax
  CHAR *v42; // rbx
  unsigned int v43; // eax
  int v44; // edx
  unsigned __int16 v45; // di
  unsigned __int16 k; // dx
  CHAR *v47; // r8
  int v48; // eax
  __int128 v49; // xmm6
  __int128 v50; // xmm7
  __int128 v51; // xmm8
  __int128 v52; // xmm9
  __int64 v53; // xmm10_8
  __int64 v54; // rcx
  USAGE v55; // cx
  USAGE v56; // ax
  USAGE v57; // di
  USAGE v58; // r15
  unsigned int v59; // eax
  int v60; // edx
  __int64 v61; // rcx
  unsigned __int16 v62; // r14
  int v63; // ebx
  __int16 v64; // r10
  __int64 v65; // rax
  unsigned int v66; // eax
  int v67; // edx
  ULONG v68; // edi
  bool v69; // dl
  __int64 v70; // rcx
  int ValueCaps; // [rsp+28h] [rbp-E0h]
  USHORT v72[2]; // [rsp+48h] [rbp-C0h] BYREF
  USAGE v73; // [rsp+4Ch] [rbp-BCh] BYREF
  USHORT ValueCapsLength[2]; // [rsp+50h] [rbp-B8h] BYREF
  USHORT v75[2]; // [rsp+54h] [rbp-B4h] BYREF
  ULONG LinkCollectionNodesLength[2]; // [rsp+58h] [rbp-B0h] BYREF
  PCHAR Report; // [rsp+60h] [rbp-A8h] BYREF
  ULONG UsageValue; // [rsp+68h] [rbp-A0h] BYREF
  _DWORD v79[4]; // [rsp+70h] [rbp-98h] BYREF
  struct _HIDP_LINK_COLLECTION_NODE *v80; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v81[16]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v82; // [rsp+98h] [rbp-70h]
  _BYTE v83[24]; // [rsp+A0h] [rbp-68h] BYREF
  struct _HIDP_VALUE_CAPS v84; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v85[72]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v86[24]; // [rsp+150h] [rbp+48h] BYREF
  struct _HIDP_VALUE_CAPS v87; // [rsp+168h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+260h] [rbp+158h]

  Caps = HidP_GetCaps(*((PHIDP_PREPARSED_DATA *)this + 1), (PHIDP_CAPS)((char *)this + 16));
  v4 = wil::details::NtStatusToHr((wil::details *)Caps, v3);
  if ( v4 < 0 )
  {
    CompliantHapticInterface::ReportValidationError(this, L"Failed to retrieve the top level HID capabilities");
    v5 = 114;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\haptic\\hid\\lib\\complianthapticinterface.cpp",
      (const char *)(unsigned int)v4,
      ValueCaps);
    return (unsigned int)v4;
  }
  LinkCollectionNodesLength[1] = 0;
  if ( HidP_GetLinkCollectionNodes(0, &LinkCollectionNodesLength[1], *((PHIDP_PREPARSED_DATA *)this + 1)) != -1072627705 )
  {
    CompliantHapticInterface::ReportValidationError(this, L"Failed to retrieve the link collection count");
    v4 = -2147418113;
    v5 = 121;
    goto LABEL_3;
  }
  v7 = 24LL * LinkCollectionNodesLength[1];
  if ( !is_mul_ok(LinkCollectionNodesLength[1], 0x18u) )
    v7 = -1;
  v8 = (struct _HIDP_LINK_COLLECTION_NODE *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v80 = v8;
  LinkCollectionNodes = HidP_GetLinkCollectionNodes(
                          v8,
                          &LinkCollectionNodesLength[1],
                          *((PHIDP_PREPARSED_DATA *)this + 1));
  v11 = wil::details::NtStatusToHr((wil::details *)LinkCollectionNodes, v10);
  if ( v11 < 0 )
  {
    CompliantHapticInterface::ReportValidationError(this, L"Failed to retrieve the link collection");
    v12 = 131;
LABEL_127:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\haptic\\hid\\lib\\complianthapticinterface.cpp",
      (const char *)(unsigned int)v11,
      ValueCaps);
    goto LABEL_131;
  }
  for ( i = 0; i < LinkCollectionNodesLength[1]; ++i )
  {
    if ( v8[i].LinkUsagePage == 14 )
    {
      if ( v8[i].LinkUsage == 1 )
      {
        memset_0(&v84, 0, sizeof(v84));
        ValueCapsLength[0] = 1;
        if ( HidP_GetSpecificValueCaps(
               HidP_Output,
               0xEu,
               i,
               0x21u,
               &v84,
               ValueCapsLength,
               *((PHIDP_PREPARSED_DATA *)this + 1)) >= 0 )
        {
          if ( *((_BYTE *)this + 336) )
          {
            CompliantHapticInterface::ReportValidationError(this, L"Duplicate manual trigger usage");
            FeatureReport = -2147418113;
            v30 = 153;
            goto LABEL_130;
          }
          memset_0(v85, 0, 0x58u);
          v14 = HapticsTrigger::HapticsTrigger((HapticsTrigger *)v85);
          std::_Optional_construct_base<HapticsTrigger>::_Assign<HapticsTrigger>((char *)this + 248, v14);
          std::_Tree<std::_Tmap_traits<unsigned short,_HIDP_VALUE_CAPS,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,_HIDP_VALUE_CAPS>>,0>>::~_Tree<std::_Tmap_traits<unsigned short,_HIDP_VALUE_CAPS,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,_HIDP_VALUE_CAPS>>,0>>(v86);
          v15 = *(_OWORD *)&v84.HasNull;
          v16 = *(_OWORD *)&v84.UnitsExp;
          v17 = *(_OWORD *)&v84.PhysicalMin;
          v18 = *(_QWORD *)&v84.NotRange.DesignatorIndex;
          *(_OWORD *)((char *)this + 248) = *(_OWORD *)&v84.UsagePage;
          *(_OWORD *)((char *)this + 264) = v15;
          *(_OWORD *)((char *)this + 280) = v16;
          *(_OWORD *)((char *)this + 296) = v17;
          *((_QWORD *)this + 39) = v18;
        }
        if ( *((_BYTE *)this + 440) )
        {
          ValueCapsLength[0] = 1;
          if ( HidP_GetSpecificValueCaps(
                 HidP_Feature,
                 0xEu,
                 i,
                 0x20u,
                 &v84,
                 ValueCapsLength,
                 *((PHIDP_PREPARSED_DATA *)this + 1)) >= 0 )
          {
            if ( *((_BYTE *)this + 432) )
            {
              CompliantHapticInterface::ReportValidationError(this, L"Duplicate auto trigger usage");
              FeatureReport = -2147418113;
              v30 = 175;
              goto LABEL_130;
            }
            memset_0(v85, 0, 0x58u);
            v19 = HapticsTrigger::HapticsTrigger((HapticsTrigger *)v85);
            std::_Optional_construct_base<HapticsTrigger>::_Assign<HapticsTrigger>((char *)this + 344, v19);
            std::_Tree<std::_Tmap_traits<unsigned short,_HIDP_VALUE_CAPS,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,_HIDP_VALUE_CAPS>>,0>>::~_Tree<std::_Tmap_traits<unsigned short,_HIDP_VALUE_CAPS,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,_HIDP_VALUE_CAPS>>,0>>(v86);
            v20 = *(_OWORD *)&v84.HasNull;
            v21 = *(_OWORD *)&v84.UnitsExp;
            v22 = *(_OWORD *)&v84.PhysicalMin;
            v23 = *(_QWORD *)&v84.NotRange.DesignatorIndex;
            *(_OWORD *)((char *)this + 344) = *(_OWORD *)&v84.UsagePage;
            *(_OWORD *)((char *)this + 360) = v20;
            *(_OWORD *)((char *)this + 376) = v21;
            *(_OWORD *)((char *)this + 392) = v22;
            *((_QWORD *)this + 51) = v23;
          }
        }
      }
      if ( v8[i].LinkUsagePage == 14 && (unsigned __int16)(v8[i].LinkUsage - 16) <= 1u )
      {
        memset_0(&v87, 0, sizeof(v87));
        v72[0] = 1;
        if ( HidP_GetSpecificValueCaps(HidP_Feature, 0xAu, i, 0, &v87, v72, *((PHIDP_PREPARSED_DATA *)this + 1)) >= 0 )
        {
          if ( v8[i].LinkUsage == 16 )
          {
            if ( *((_BYTE *)this + 152) )
            {
              CompliantHapticInterface::ReportValidationError(this, L"Duplicate waveform capability");
              FeatureReport = -2147418113;
              v30 = 204;
              goto LABEL_130;
            }
            v24 = (char *)this + 80;
          }
          else
          {
            if ( *((_BYTE *)this + 228) )
            {
              CompliantHapticInterface::ReportValidationError(this, L"Duplicate duration capability");
              FeatureReport = -2147418113;
              v30 = 214;
              goto LABEL_130;
            }
            v24 = (char *)this + 156;
          }
          std::optional<_HIDP_VALUE_CAPS>::operator=<_HIDP_VALUE_CAPS &,0>(v24, &v87);
        }
      }
    }
  }
  if ( *((_BYTE *)this + 336) )
  {
    v75[0] = *((_WORD *)this + 35);
    v25 = 72LL * v75[0];
    if ( !is_mul_ok(v75[0], 0x48u) )
      v25 = -1;
    v26 = (CHAR *)operator new[](v25, (const struct std::nothrow_t *)&std::nothrow);
    Report = v26;
    SpecificValueCaps = HidP_GetSpecificValueCaps(
                          HidP_Output,
                          0xEu,
                          *((_WORD *)this + 127),
                          0,
                          (PHIDP_VALUE_CAPS)v26,
                          v75,
                          *((PHIDP_PREPARSED_DATA *)this + 1));
    v11 = wil::details::NtStatusToHr((wil::details *)SpecificValueCaps, v28);
    if ( v11 < 0 )
    {
      CompliantHapticInterface::ReportValidationError(this, L"Failed to retrieve the manual trigger secondary usages");
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\haptic\\hid\\lib\\complianthap"
                      "ticinterface.cpp",
        (const char *)(unsigned int)v11,
        ValueCaps);
LABEL_35:
      VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&Report);
LABEL_131:
      VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v80);
      return (unsigned int)v11;
    }
    v31 = 0;
    for ( j = v75[0]; v31 < j; ++v31 )
    {
      if ( v26[72 * v31 + 12] || v26[72 * v31 + 2] != *((_BYTE *)this + 250) )
        continue;
      v33 = &v26[72 * v31];
      switch ( *((_WORD *)v33 + 28) )
      {
        case '#':
          if ( *(_DWORD *)&v26[72 * v31 + 40] || *(int *)&v26[72 * v31 + 44] < 4 )
            continue;
LABEL_54:
          v35 = *(_OWORD *)&v26[72 * v31];
          v36 = *(_OWORD *)&v26[72 * v31 + 16];
          v37 = *(_OWORD *)&v26[72 * v31 + 32];
          v38 = *(_OWORD *)&v26[72 * v31 + 48];
          v39 = *(_QWORD *)&v26[72 * v31 + 64];
          v40 = *(_QWORD *)std::map<unsigned short,_HIDP_VALUE_CAPS>::_Try_emplace<unsigned short const &,>(
                             (char *)this + 320,
                             v79,
                             v33 + 56);
          *(_OWORD *)(v40 + 32) = v35;
          *(_OWORD *)(v40 + 48) = v36;
          *(_OWORD *)(v40 + 64) = v37;
          *(_OWORD *)(v40 + 80) = v38;
          *(_QWORD *)(v40 + 96) = v39;
          j = v75[0];
          continue;
        case '$':
        case '%':
          v34 = *(_DWORD *)&v26[72 * v31 + 40];
          if ( v34 )
            continue;
          break;
        case '(':
          v34 = *(_DWORD *)&v26[72 * v31 + 40];
          if ( v34 <= 0 )
            continue;
          break;
        default:
          continue;
      }
      if ( *(_DWORD *)&v26[72 * v31 + 44] > v34 )
        goto LABEL_54;
    }
    VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&Report);
  }
  if ( *((_BYTE *)this + 432) )
  {
    LOWORD(LinkCollectionNodesLength[0]) = *((_WORD *)this + 38);
    v41 = 72LL * LOWORD(LinkCollectionNodesLength[0]);
    if ( !is_mul_ok(LOWORD(LinkCollectionNodesLength[0]), 0x48u) )
      v41 = -1;
    v42 = (CHAR *)operator new[](v41, (const struct std::nothrow_t *)&std::nothrow);
    Report = v42;
    v43 = HidP_GetSpecificValueCaps(
            HidP_Feature,
            0xEu,
            *((_WORD *)this + 175),
            0,
            (PHIDP_VALUE_CAPS)v42,
            (PUSHORT)LinkCollectionNodesLength,
            *((PHIDP_PREPARSED_DATA *)this + 1));
    v11 = wil::details::NtStatusToHr((wil::details *)v43, v44);
    if ( v11 < 0 )
    {
      CompliantHapticInterface::ReportValidationError(this, L"Error when looking for auto trigger secondary usages");
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\haptic\\hid\\lib\\complianthap"
                      "ticinterface.cpp",
        (const char *)(unsigned int)v11,
        ValueCaps);
      goto LABEL_35;
    }
    v45 = 0;
    for ( k = LinkCollectionNodesLength[0]; v45 < k; ++v45 )
    {
      if ( v42[72 * v45 + 12] || v42[72 * v45 + 2] != *((_BYTE *)this + 346) )
        continue;
      v47 = &v42[72 * v45 + 56];
      if ( *(_WORD *)v47 == 35 )
      {
        if ( *(_DWORD *)&v42[72 * v45 + 40] || *(int *)&v42[72 * v45 + 44] < 4 )
          continue;
      }
      else
      {
        if ( *(_WORD *)v47 != 40 )
          continue;
        v48 = *(_DWORD *)&v42[72 * v45 + 40];
        if ( v48 <= 0 || *(_DWORD *)&v42[72 * v45 + 44] <= v48 )
          continue;
      }
      v49 = *(_OWORD *)&v42[72 * v45];
      v50 = *(_OWORD *)&v42[72 * v45 + 16];
      v51 = *(_OWORD *)&v42[72 * v45 + 32];
      v52 = *(_OWORD *)&v42[72 * v45 + 48];
      v53 = *(_QWORD *)&v42[72 * v45 + 64];
      v54 = *(_QWORD *)std::map<unsigned short,_HIDP_VALUE_CAPS>::_Try_emplace<unsigned short const &,>(
                         (char *)this + 416,
                         v79,
                         v47);
      *(_OWORD *)(v54 + 32) = v49;
      *(_OWORD *)(v54 + 48) = v50;
      *(_OWORD *)(v54 + 64) = v51;
      *(_OWORD *)(v54 + 80) = v52;
      *(_QWORD *)(v54 + 96) = v53;
      k = LinkCollectionNodesLength[0];
    }
    VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&Report);
  }
  if ( *((_BYTE *)this + 152) && *((_BYTE *)this + 228) )
  {
    if ( !*((_BYTE *)this + 152) || !*((_BYTE *)this + 228) )
      std::_Throw_bad_optional_access();
    if ( *((_BYTE *)this + 82) != *((_BYTE *)this + 158) )
    {
      CompliantHapticInterface::ReportValidationError(this, L"Waveform report id does not match duration report id");
      FeatureReport = -2147418113;
      v30 = 327;
LABEL_130:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\haptic\\hid\\lib\\complianthap"
                      "ticinterface.cpp",
        (const char *)(unsigned int)FeatureReport,
        ValueCaps);
      v11 = FeatureReport;
      goto LABEL_131;
    }
    if ( !*((_BYTE *)this + 92) )
    {
      CompliantHapticInterface::ReportValidationError(this, L"Waveforms should have range");
      FeatureReport = -2147418113;
      v30 = 333;
      goto LABEL_130;
    }
    if ( !*((_BYTE *)this + 168) )
    {
      CompliantHapticInterface::ReportValidationError(this, L"Durations should have range");
      FeatureReport = -2147418113;
      v30 = 339;
      goto LABEL_130;
    }
    v55 = *((_WORD *)this + 68);
    if ( v55 != *((_WORD *)this + 106) )
    {
      CompliantHapticInterface::ReportValidationError(
        this,
        L"waveformCaps.Range.UsageMin != durationCaps.Range.UsageMin");
      FeatureReport = -2147418113;
      v30 = 345;
      goto LABEL_130;
    }
    v56 = *((_WORD *)this + 69);
    if ( v56 != *((_WORD *)this + 107) )
    {
      CompliantHapticInterface::ReportValidationError(
        this,
        L"waveformCaps.Range.UsageMax != durationCaps.Range.UsageMax");
      FeatureReport = -2147418113;
      v30 = 351;
      goto LABEL_130;
    }
    v73 = *((_WORD *)this + 68);
    if ( v55 <= v56 )
    {
      v57 = v55;
      v58 = v55;
      while ( 1 )
      {
        v79[1] = 0;
        UsageValue = 0;
        v79[0] = v55;
        Report = 0;
        FeatureReport = CompliantHapticInterface::GetFeatureReport(this, *((_BYTE *)this + 82), &Report);
        if ( FeatureReport < 0 )
          break;
        v59 = HidP_GetUsageValue(
                HidP_Feature,
                *((_WORD *)this + 40),
                *((_WORD *)this + 43),
                v73,
                &UsageValue,
                *((PHIDP_PREPARSED_DATA *)this + 1),
                Report,
                *((unsigned __int16 *)this + 12));
        FeatureReport = wil::details::NtStatusToHr((wil::details *)v59, v60);
        if ( FeatureReport < 0 )
        {
          CompliantHapticInterface::ReportValidationError(this, L"Failed to retrieve waveform usage value");
          v30 = 380;
          goto LABEL_130;
        }
        v62 = UsageValue;
        HIWORD(v79[0]) = UsageValue;
        v63 = 2;
        v79[2] = 2;
        std::_Tree<std::_Tmap_traits<unsigned short,enum WaveformFlags,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,enum WaveformFlags>>,0>>::_Find_lower_bound<unsigned short>(
          v61,
          v81,
          (char *)v79 + 2);
        v65 = v82;
        if ( *(_BYTE *)(v82 + 25) || v62 < *(_WORD *)(v82 + 28) )
          v65 = qword_180243968;
        if ( v65 != qword_180243968 )
          v63 = *(_DWORD *)(v65 + 32) | 3;
        if ( v57 == 1 && v62 != 4097 )
        {
          CompliantHapticInterface::ReportValidationError(this, L"NONE waveform ordinal vs usage mismatch");
          FeatureReport = -2147418113;
          v30 = 397;
          goto LABEL_130;
        }
        if ( v57 == v64 && v62 != 4098 )
        {
          CompliantHapticInterface::ReportValidationError(this, L"STOP waveform ordinal vs usage mismatch");
          FeatureReport = -2147418113;
          v30 = 403;
          goto LABEL_130;
        }
        v11 = CompliantHapticInterface::GetFeatureReport(this, *((_BYTE *)this + 158), &Report);
        if ( v11 < 0 )
        {
          CompliantHapticInterface::ReportValidationError(this, L"Failed to get feature report for duration capability");
          v12 = 410;
          goto LABEL_127;
        }
        v66 = HidP_GetUsageValue(
                HidP_Feature,
                *((_WORD *)this + 78),
                *((_WORD *)this + 81),
                v73,
                &UsageValue,
                *((PHIDP_PREPARSED_DATA *)this + 1),
                Report,
                *((unsigned __int16 *)this + 12));
        v11 = wil::details::NtStatusToHr((wil::details *)v66, v67);
        if ( v11 < 0 )
        {
          CompliantHapticInterface::ReportValidationError(this, L"Failed to retrieve waveform duration usage value");
          v12 = 425;
          goto LABEL_127;
        }
        v68 = UsageValue;
        if ( (v63 & 8) == 0 )
        {
          v69 = 1;
          if ( UsageValue )
          {
            if ( (v63 & 5) == 5 )
              v68 = 0;
          }
          else if ( (v63 & 1) != 0 )
          {
            v69 = (v63 & 4) != 0;
          }
          else
          {
            v63 |= 4u;
          }
          if ( !*((_BYTE *)this + 440) && (v63 & 4) != 0 )
          {
            v69 = 0;
            if ( *((_BYTE *)this + 441) )
            {
              CompliantHapticInterface::ReportValidationError(this, L"Unexpected continuous waveform");
              FeatureReport = -2147418113;
              v30 = 472;
              goto LABEL_130;
            }
          }
          if ( v69 )
          {
            v70 = *(_QWORD *)std::map<unsigned short,HapticsWaveform>::_Try_emplace<unsigned short,>(
                               (char *)this + 232,
                               v83,
                               &v73);
            *(_WORD *)(v70 + 32) = v58;
            *(_WORD *)(v70 + 34) = v62;
            *(_DWORD *)(v70 + 36) = v68;
            *(_DWORD *)(v70 + 40) = v63;
          }
        }
        v55 = v73 + 1;
        v73 = v55;
        v57 = v55;
        v58 = v55;
        if ( v55 > *((_WORD *)this + 69) )
          goto LABEL_117;
      }
      CompliantHapticInterface::ReportValidationError(this, L"Failed to get feature report for waveform capability");
      v30 = 365;
      goto LABEL_130;
    }
LABEL_117:
    if ( *((_QWORD *)this + 30) )
    {
      v72[0] = 1;
      *(_WORD *)std::map<unsigned short,HapticsWaveform>::operator[]((char *)this + 232, v72) = 1;
      v72[0] = 1;
      *(_WORD *)(std::map<unsigned short,HapticsWaveform>::operator[]((char *)this + 232, v72) + 2) = 4097;
      v72[0] = 1;
      *(_DWORD *)(std::map<unsigned short,HapticsWaveform>::operator[]((char *)this + 232, v72) + 8) = 9;
      v72[0] = 2;
      *(_WORD *)std::map<unsigned short,HapticsWaveform>::operator[]((char *)this + 232, v72) = 2;
      v72[0] = 2;
      *(_WORD *)(std::map<unsigned short,HapticsWaveform>::operator[]((char *)this + 232, v72) + 2) = 4098;
      v72[0] = 2;
      *(_DWORD *)(std::map<unsigned short,HapticsWaveform>::operator[]((char *)this + 232, v72) + 8) = 9;
    }
  }
  if ( *((_QWORD *)this + 65) )
    std::_Func_class<void,bool,unsigned short const *>::operator()((char *)this + 464, 0, L"Validation successful");
  VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v80);
  return 0;
}

```

## disassembly

```asm
0x18019c1f8  mov     rax, rsp
0x18019c1fb  push    rbp
0x18019c1fc  push    rbx
0x18019c1fd  push    rsi
0x18019c1fe  push    rdi
0x18019c1ff  push    r12
0x18019c201  push    r13
0x18019c203  push    r14
0x18019c205  push    r15
0x18019c207  lea     rbp, [rax-158h]
0x18019c20e  sub     rsp, 218h
0x18019c215  movaps  xmmword ptr [rax-58h], xmm6
0x18019c219  movaps  xmmword ptr [rax-68h], xmm7
0x18019c21d  movaps  xmmword ptr [rax-78h], xmm8
0x18019c222  movaps  xmmword ptr [rax-88h], xmm9
0x18019c22a  movaps  xmmword ptr [rax-98h], xmm10
0x18019c232  mov     rax, cs:__security_cookie
0x18019c239  xor     rax, rsp
0x18019c23c  mov     [rbp+150h+var_A0], rax
0x18019c243  mov     rsi, rcx
0x18019c246  lea     rdx, [rcx+10h]; Capabilities
0x18019c24a  mov     rcx, [rcx+8]; PreparsedData
0x18019c24e  call    cs:__imp_HidP_GetCaps
0x18019c254  mov     ecx, eax; this
0x18019c256  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18019c25b  mov     ebx, eax
0x18019c25d  xor     r12d, r12d
0x18019c260  test    eax, eax
0x18019c262  jns     short loc_18019C295
0x18019c264  lea     rdx, aFailedToRetrie_2; "Failed to retrieve the top level HID ca"...
0x18019c26b  mov     rcx, rsi; this
0x18019c26e  call    ?ReportValidationError@CompliantHapticInterface@@AEAAXPEBG@Z; CompliantHapticInterface::ReportValidationError(ushort const *)
0x18019c273  lea     edx, [r12+72h]; void *
0x18019c278  lea     r8, aOnecoreuapWind_214; "onecoreuap\\windows\\moderncore\\inputv"...
0x18019c27f  mov     r9d, ebx; char *
0x18019c282  mov     rcx, [rbp+158h]; this
0x18019c289  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019c28e  mov     eax, ebx
0x18019c290  jmp     loc_18019CD1C
0x18019c295  mov     [rsp+250h+LinkCollectionNodesLength+4], r12d
0x18019c29a  mov     r8, [rsi+8]; PreparsedData
0x18019c29e  lea     rdx, [rsp+250h+LinkCollectionNodesLength+4]; LinkCollectionNodesLength
0x18019c2a3  xor     ecx, ecx; LinkCollectionNodes
0x18019c2a5  call    cs:__imp_HidP_GetLinkCollectionNodes
0x18019c2ab  cmp     eax, 0C0110007h
0x18019c2b0  jz      short loc_18019C2CD
0x18019c2b2  lea     rdx, aFailedToRetrie_3; "Failed to retrieve the link collection "...
0x18019c2b9  mov     rcx, rsi; this
0x18019c2bc  call    ?ReportValidationError@CompliantHapticInterface@@AEAAXPEBG@Z; CompliantHapticInterface::ReportValidationError(ushort const *)
0x18019c2c1  mov     ebx, 8000FFFFh
0x18019c2c6  mov     edx, 79h ; 'y'
0x18019c2cb  jmp     short loc_18019C278
0x18019c2cd  mov     ecx, [rsp+250h+LinkCollectionNodesLength+4]
0x18019c2d1  mov     eax, 18h
0x18019c2d6  mul     rcx
0x18019c2d9  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18019c2e0  cmovb   rax, r15
0x18019c2e4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019c2eb  mov     rcx, rax; unsigned __int64
0x18019c2ee  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18019c2f3  mov     rbx, rax
0x18019c2f6  mov     [rsp+250h+var_1D8], rax
0x18019c2fb  mov     r8, [rsi+8]; PreparsedData
0x18019c2ff  lea     rdx, [rsp+250h+LinkCollectionNodesLength+4]; LinkCollectionNodesLength
0x18019c304  mov     rcx, rax; LinkCollectionNodes
0x18019c307  call    cs:__imp_HidP_GetLinkCollectionNodes
0x18019c30d  mov     ecx, eax; this
0x18019c30f  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18019c314  mov     edi, eax
0x18019c316  test    eax, eax
0x18019c318  jns     short loc_18019C333
0x18019c31a  lea     rdx, aFailedToRetrie_0; "Failed to retrieve the link collection"
0x18019c321  mov     rcx, rsi; this
0x18019c324  call    ?ReportValidationError@CompliantHapticInterface@@AEAAXPEBG@Z; CompliantHapticInterface::ReportValidationError(ushort const *)
0x18019c329  mov     edx, 83h
0x18019c32e  jmp     loc_18019CDDD
0x18019c333  mov     r14d, r12d
0x18019c336  mov     edi, 0Eh
0x18019c33b  lea     r13d, [rdi-0Dh]
0x18019c33f  cmp     [rsp+250h+LinkCollectionNodesLength+4], r12d
0x18019c344  jbe     loc_18019C592
0x18019c34a  movzx   eax, r14w
0x18019c34e  lea     r15, [rax+rax*2]
0x18019c352  cmp     [rbx+r15*8+2], di
0x18019c358  jnz     loc_18019C57C
0x18019c35e  cmp     [rbx+r15*8], r13w
0x18019c363  jnz     loc_18019C4DC
0x18019c369  xor     edx, edx; Val
0x18019c36b  lea     r8d, [rdx+48h]; Size
0x18019c36f  lea     rcx, [rbp+150h+var_1A0]; void *
0x18019c373  call    memset_0
0x18019c378  mov     [rsp+250h+var_208], r13w
0x18019c37e  mov     r9d, 21h ; '!'; Usage
0x18019c384  mov     edx, edi; UsagePage
0x18019c386  mov     rax, [rsi+8]
0x18019c38a  mov     [rsp+250h+PreparsedData], rax; PreparsedData
0x18019c38f  lea     rax, [rsp+250h+var_208]
0x18019c394  mov     [rsp+250h+ValueCapsLength], rax; ValueCapsLength
0x18019c399  lea     rax, [rbp+150h+var_1A0]
0x18019c39d  mov     [rsp+250h+ValueCaps], rax; ValueCaps
0x18019c3a2  movzx   r8d, r14w; LinkCollection
0x18019c3a6  mov     ecx, r13d; ReportType
0x18019c3a9  call    cs:__imp_HidP_GetSpecificValueCaps
0x18019c3af  test    eax, eax
0x18019c3b1  js      short loc_18019C423
0x18019c3b3  cmp     [rsi+150h], r12b
0x18019c3ba  jnz     loc_18019C649
0x18019c3c0  xor     edx, edx; Val
0x18019c3c2  lea     r8d, [rdx+58h]; Size
0x18019c3c6  lea     rcx, [rbp+150h+var_150]; void *
0x18019c3ca  call    memset_0
0x18019c3cf  lea     rcx, [rbp+150h+var_150]; this
0x18019c3d3  call    ??0HapticsTrigger@@QEAA@XZ; HapticsTrigger::HapticsTrigger(void)
0x18019c3d8  nop
0x18019c3d9  lea     rdi, [rsi+0F8h]
0x18019c3e0  mov     rdx, rax
0x18019c3e3  mov     rcx, rdi
0x18019c3e6  call    ??$_Assign@UHapticsTrigger@@@?$_Optional_construct_base@UHapticsTrigger@@@std@@QEAAX$$QEAUHapticsTrigger@@@Z; std::_Optional_construct_base<HapticsTrigger>::_Assign<HapticsTrigger>(HapticsTrigger &&)
0x18019c3eb  nop
0x18019c3ec  lea     rcx, [rbp+150h+var_108]
0x18019c3f0  call    ??1?$_Tree@V?$_Tmap_traits@GU_HIDP_VALUE_CAPS@@U?$less@G@std@@V?$allocator@U?$pair@$$CBGU_HIDP_VALUE_CAPS@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ushort,_HIDP_VALUE_CAPS,std::less<ushort>,std::allocator<std::pair<ushort const,_HIDP_VALUE_CAPS>>,0>>::~_Tree<std::_Tmap_traits<ushort,_HIDP_VALUE_CAPS,std::less<ushort>,std::allocator<std::pair<ushort const,_HIDP_VALUE_CAPS>>,0>>(void)
0x18019c3f5  movaps  xmm0, xmmword ptr [rbp+150h+var_1A0.UsagePage]
0x18019c3f9  movaps  xmm1, xmmword ptr [rbp+150h+var_1A0.HasNull]
0x18019c3fd  movaps  xmm2, xmmword ptr [rbp+150h+var_1A0.UnitsExp]
0x18019c401  movaps  xmm3, xmmword ptr [rbp+150h+var_1A0.PhysicalMin]
0x18019c405  movsd   xmm4, qword ptr [rbp+150h+var_1A0.38h+8]
0x18019c40a  movups  xmmword ptr [rdi], xmm0
0x18019c40d  movups  xmmword ptr [rdi+10h], xmm1
0x18019c411  movups  xmmword ptr [rdi+20h], xmm2
0x18019c415  movups  xmmword ptr [rdi+30h], xmm3
0x18019c419  movsd   qword ptr [rdi+40h], xmm4
0x18019c41e  mov     edi, 0Eh
0x18019c423  cmp     [rsi+1B8h], r12b
0x18019c42a  jz      loc_18019C4DC
0x18019c430  mov     [rsp+250h+var_208], r13w
0x18019c436  mov     r9d, 20h ; ' '; Usage
0x18019c43c  mov     edx, edi; UsagePage
0x18019c43e  mov     rax, [rsi+8]
0x18019c442  mov     [rsp+250h+PreparsedData], rax; PreparsedData
0x18019c447  lea     rax, [rsp+250h+var_208]
0x18019c44c  mov     [rsp+250h+ValueCapsLength], rax; ValueCapsLength
0x18019c451  lea     rax, [rbp+150h+var_1A0]
0x18019c455  mov     [rsp+250h+ValueCaps], rax; ValueCaps
0x18019c45a  movzx   r8d, r14w; LinkCollection
0x18019c45e  lea     ecx, [r9-1Eh]; ReportType
0x18019c462  call    cs:__imp_HidP_GetSpecificValueCaps
0x18019c468  test    eax, eax
0x18019c46a  js      short loc_18019C4DC
0x18019c46c  cmp     [rsi+1B0h], r12b
0x18019c473  jnz     loc_18019C667
0x18019c479  xor     edx, edx; Val
0x18019c47b  lea     r8d, [rdx+58h]; Size
0x18019c47f  lea     rcx, [rbp+150h+var_150]; void *
0x18019c483  call    memset_0
0x18019c488  lea     rcx, [rbp+150h+var_150]; this
0x18019c48c  call    ??0HapticsTrigger@@QEAA@XZ; HapticsTrigger::HapticsTrigger(void)
0x18019c491  nop
0x18019c492  lea     rdi, [rsi+158h]
0x18019c499  mov     rdx, rax
0x18019c49c  mov     rcx, rdi
0x18019c49f  call    ??$_Assign@UHapticsTrigger@@@?$_Optional_construct_base@UHapticsTrigger@@@std@@QEAAX$$QEAUHapticsTrigger@@@Z; std::_Optional_construct_base<HapticsTrigger>::_Assign<HapticsTrigger>(HapticsTrigger &&)
0x18019c4a4  nop
0x18019c4a5  lea     rcx, [rbp+150h+var_108]
0x18019c4a9  call    ??1?$_Tree@V?$_Tmap_traits@GU_HIDP_VALUE_CAPS@@U?$less@G@std@@V?$allocator@U?$pair@$$CBGU_HIDP_VALUE_CAPS@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ushort,_HIDP_VALUE_CAPS,std::less<ushort>,std::allocator<std::pair<ushort const,_HIDP_VALUE_CAPS>>,0>>::~_Tree<std::_Tmap_traits<ushort,_HIDP_VALUE_CAPS,std::less<ushort>,std::allocator<std::pair<ushort const,_HIDP_VALUE_CAPS>>,0>>(void)
0x18019c4ae  movaps  xmm0, xmmword ptr [rbp+150h+var_1A0.UsagePage]
0x18019c4b2  movaps  xmm1, xmmword ptr [rbp+150h+var_1A0.HasNull]
0x18019c4b6  movaps  xmm2, xmmword ptr [rbp+150h+var_1A0.UnitsExp]
0x18019c4ba  movaps  xmm3, xmmword ptr [rbp+150h+var_1A0.PhysicalMin]
0x18019c4be  movsd   xmm4, qword ptr [rbp+150h+var_1A0.38h+8]
0x18019c4c3  movups  xmmword ptr [rdi], xmm0
0x18019c4c6  movups  xmmword ptr [rdi+10h], xmm1
0x18019c4ca  movups  xmmword ptr [rdi+20h], xmm2
0x18019c4ce  movups  xmmword ptr [rdi+30h], xmm3
0x18019c4d2  movsd   qword ptr [rdi+40h], xmm4
0x18019c4d7  mov     edi, 0Eh
0x18019c4dc  cmp     [rbx+r15*8+2], di
0x18019c4e2  jnz     loc_18019C57C
0x18019c4e8  movzx   eax, word ptr [rbx+r15*8]
0x18019c4ed  sub     ax, 10h
0x18019c4f1  cmp     ax, r13w
0x18019c4f5  ja      loc_18019C57C
0x18019c4fb  xor     edx, edx; Val
0x18019c4fd  lea     r8d, [rdx+48h]; Size
0x18019c501  lea     rcx, [rbp+150h+var_F0]; void *
0x18019c505  call    memset_0
0x18019c50a  mov     [rsp+250h+var_210], r13w
0x18019c510  xor     r9d, r9d; Usage
0x18019c513  lea     edx, [r9+0Ah]; UsagePage
0x18019c517  mov     rax, [rsi+8]
0x18019c51b  mov     [rsp+250h+PreparsedData], rax; PreparsedData
0x18019c520  lea     rax, [rsp+250h+var_210]
0x18019c525  mov     [rsp+250h+ValueCapsLength], rax; ValueCapsLength
0x18019c52a  lea     rax, [rbp+150h+var_F0]
0x18019c52e  mov     [rsp+250h+ValueCaps], rax; ValueCaps
0x18019c533  movzx   r8d, r14w; LinkCollection
0x18019c537  lea     ecx, [rdx-8]; ReportType
0x18019c53a  call    cs:__imp_HidP_GetSpecificValueCaps
0x18019c540  test    eax, eax
0x18019c542  js      short loc_18019C57C
0x18019c544  cmp     word ptr [rbx+r15*8], 10h
0x18019c54a  jnz     short loc_18019C55F
0x18019c54c  cmp     [rsi+98h], r12b
0x18019c553  jnz     loc_18019C685
0x18019c559  lea     rcx, [rsi+50h]
0x18019c55d  jmp     short loc_18019C573
0x18019c55f  cmp     [rsi+0E4h], r12b
0x18019c566  jnz     loc_18019C6A3
0x18019c56c  lea     rcx, [rsi+9Ch]
0x18019c573  lea     rdx, [rbp+150h+var_F0]
0x18019c577  call    ??$?4AEAU_HIDP_VALUE_CAPS@@$0A@@?$optional@U_HIDP_VALUE_CAPS@@@std@@QEAAAEAV01@AEAU_HIDP_VALUE_CAPS@@@Z; std::optional<_HIDP_VALUE_CAPS>::operator=<_HIDP_VALUE_CAPS &,0>(_HIDP_VALUE_CAPS &)
0x18019c57c  add     r14w, r13w
0x18019c580  movzx   eax, r14w
0x18019c584  cmp     eax, [rsp+250h+LinkCollectionNodesLength+4]
0x18019c588  jb      loc_18019C34A
0x18019c58e  or      r15, 0FFFFFFFFFFFFFFFFh
0x18019c592  mov     r14d, 23h ; '#'
0x18019c598  cmp     [rsi+150h], r12b
0x18019c59f  jz      loc_18019C7AA
0x18019c5a5  movzx   ecx, word ptr [rsi+46h]
0x18019c5a9  mov     [rsp+250h+var_204], cx
0x18019c5ae  lea     eax, [r14+25h]
0x18019c5b2  mul     rcx
0x18019c5b5  cmovb   rax, r15
0x18019c5b9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019c5c0  mov     rcx, rax; unsigned __int64
0x18019c5c3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18019c5c8  mov     rbx, rax
0x18019c5cb  mov     [rsp+250h+Report], rax
0x18019c5d0  xor     r9d, r9d; Usage
0x18019c5d3  mov     edx, edi; UsagePage
0x18019c5d5  mov     rax, [rsi+8]
0x18019c5d9  mov     [rsp+250h+PreparsedData], rax; PreparsedData
0x18019c5de  lea     rax, [rsp+250h+var_204]
0x18019c5e3  mov     [rsp+250h+ValueCapsLength], rax; ValueCapsLength
0x18019c5e8  mov     [rsp+250h+ValueCaps], rbx; int
0x18019c5ed  movzx   r8d, word ptr [rsi+0FEh]; LinkCollection
0x18019c5f5  mov     ecx, r13d; ReportType
0x18019c5f8  call    cs:__imp_HidP_GetSpecificValueCaps
0x18019c5fe  mov     ecx, eax; this
0x18019c600  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18019c605  mov     edi, eax
0x18019c607  test    eax, eax
0x18019c609  jns     loc_18019C6C1
0x18019c60f  lea     rdx, aFailedToRetrie_4; "Failed to retrieve the manual trigger s"...
0x18019c616  mov     rcx, rsi; this
0x18019c619  call    ?ReportValidationError@CompliantHapticInterface@@AEAAXPEBG@Z; CompliantHapticInterface::ReportValidationError(ushort const *)
0x18019c61e  mov     rcx, [rbp+158h]; this
0x18019c625  mov     r9d, edi; char *
0x18019c628  lea     r8, aOnecoreuapWind_214; "onecoreuap\\windows\\moderncore\\inputv"...
0x18019c62f  mov     edx, 0EFh; void *
0x18019c634  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019c639  nop
0x18019c63a  lea     rcx, [rsp+250h+Report]
0x18019c63f  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x18019c644  jmp     loc_18019CE37
0x18019c649  lea     rdx, aDuplicateManua; "Duplicate manual trigger usage"
0x18019c650  mov     rcx, rsi; this
0x18019c653  call    ?ReportValidationError@CompliantHapticInterface@@AEAAXPEBG@Z; CompliantHapticInterface::ReportValidationError(ushort const *)
0x18019c658  mov     ebx, 8000FFFFh
0x18019c65d  mov     edx, 99h
0x18019c662  jmp     loc_18019CE1F
0x18019c667  lea     rdx, aDuplicateAutoT; "Duplicate auto trigger usage"
0x18019c66e  mov     rcx, rsi; this
0x18019c671  call    ?ReportValidationError@CompliantHapticInterface@@AEAAXPEBG@Z; CompliantHapticInterface::ReportValidationError(ushort const *)
0x18019c676  mov     ebx, 8000FFFFh
0x18019c67b  mov     edx, 0AFh
0x18019c680  jmp     loc_18019CE1F
0x18019c685  lea     rdx, aDuplicateWavef; "Duplicate waveform capability"
0x18019c68c  mov     rcx, rsi; this
0x18019c68f  call    ?ReportValidationError@CompliantHapticInterface@@AEAAXPEBG@Z; CompliantHapticInterface::ReportValidationError(ushort const *)
0x18019c694  mov     ebx, 8000FFFFh
0x18019c699  mov     edx, 0CCh
0x18019c69e  jmp     loc_18019CE1F
0x18019c6a3  lea     rdx, aDuplicateDurat; "Duplicate duration capability"
0x18019c6aa  mov     rcx, rsi; this
0x18019c6ad  call    ?ReportValidationError@CompliantHapticInterface@@AEAAXPEBG@Z; CompliantHapticInterface::ReportValidationError(ushort const *)
0x18019c6b2  mov     ebx, 8000FFFFh
0x18019c6b7  mov     edx, 0D6h
0x18019c6bc  jmp     loc_18019CE1F
0x18019c6c1  mov     edi, r12d
0x18019c6c4  movzx   r8d, [rsp+250h+var_204]
0x18019c6ca  cmp     r12w, r8w
0x18019c6ce  jnb     loc_18019C79B
0x18019c6d4  movzx   eax, di
0x18019c6d7  lea     rcx, [rax+rax*8]
0x18019c6db  cmp     [rbx+rcx*8+0Ch], r12b
0x18019c6e0  jnz     loc_18019C78D
0x18019c6e6  mov     al, [rsi+0FAh]
0x18019c6ec  cmp     [rbx+rcx*8+2], al
0x18019c6f0  jnz     loc_18019C78D
0x18019c6f6  lea     r9, [rbx+rcx*8]
0x18019c6fa  movzx   edx, word ptr [r9+38h]
0x18019c6ff  sub     edx, r14d
0x18019c702  jz      short loc_18019C72D
0x18019c704  sub     edx, 1
0x18019c707  jz      short loc_18019C723
0x18019c709  sub     edx, 1
0x18019c70c  jz      short loc_18019C723
0x18019c70e  cmp     edx, 3
0x18019c711  jnz     short loc_18019C78D
  ... truncated ...
```
