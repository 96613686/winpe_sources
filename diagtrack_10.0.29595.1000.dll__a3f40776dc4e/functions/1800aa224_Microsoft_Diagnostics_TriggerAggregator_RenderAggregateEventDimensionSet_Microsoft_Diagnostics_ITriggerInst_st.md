# Microsoft::Diagnostics::TriggerAggregator::RenderAggregateEventDimensionSet(Microsoft::Diagnostics::ITriggerInst &,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::vector<unsigned __int64,std::allocator<unsigned __int64>>>>>> &,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::vector<unsigned __int64,std::allocator<unsigned __int64>>>>>>,ulong,unsigned __int64)

- ea: `0x1800aa224`
- end: `0x1800ab2d0`
- name: `?RenderAggregateEventDimensionSet@TriggerAggregator@Diagnostics@Microsoft@@CAXAEAVITriggerInst@23@AEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$vector@_KV?$allocator@_K@std@@@std@@@std@@@std@@@std@@@std@@V56@K_K@Z`
- size: `4268`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18018c14c`

## callees

- `0x18001d9a0`
- `0x1800252d0`
- `0x18002be90`
- `0x18002df00`
- `0x18003d318`
- `0x18004702c`
- `0x18004cfec`
- `0x18004f874`
- `0x180056a90`
- `0x18006019c`
- `0x1800624ac`
- `0x180064f14`
- `0x180064f58`
- `0x18007d3d8`
- `0x1800a9124`
- `0x1800a9de0`
- `0x1800a9fb0`
- `0x1800aa224`
- `0x1800ab2d8`
- `0x1800ab56c`
- `0x1801a38f4`
- `0x1801a9494`
- `0x1801bbc78`
- `0x1801e9e74`
- `0x1801edea0`
- `0x1801f9b48`
- `0x1801fe944`
- `0x18020aac0`
- `0x1802dedfc`
- `0x180369010`

## string_xrefs

- `0x1800aa88b`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aa8ac`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aa9ed`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aaa05`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aaa1d`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aaa35`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aaa4d`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aaa84`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aaa9c`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aac2a`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aac43`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aaca9`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aae1f`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aaf30`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aaf48`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aaf63`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800aafc6`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800ab00a`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800ab04e`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800ab092`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800ab0d6`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800ab11a`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800ab15e`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800ab1a2`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800ab1e6`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800ab20f`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800ab244`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800ab281`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`
- `0x1800ab2be`: `onecore\base\telemetry\utc\service\triggers\triggeraggregator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 Microsoft::Diagnostics::TriggerAggregator::RenderAggregateEventDimensionSet(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4,
        ...)
{
  unsigned int v4; // r15d
  __int64 v5; // rsi
  _QWORD *v6; // rdi
  _QWORD *v7; // rbx
  __int64 *v8; // r14
  const char *v9; // r9
  unsigned int v10; // eax
  _QWORD *v11; // r13
  __int64 v12; // rax
  __int64 v13; // r12
  char v14; // r15
  _QWORD *v15; // rdi
  __int64 v16; // rbx
  int v18; // r8d
  _QWORD *v19; // rax
  __int64 v20; // rdx
  __int64 i; // rdi
  char v22; // al
  int v23; // r9d
  char *v24; // r8
  char *v25; // rdx
  __int64 j; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  _QWORD *v29; // rdi
  _QWORD *v30; // r15
  _QWORD *v31; // rdx
  __int64 *v32; // rcx
  __int64 *v33; // rax
  __int64 *k; // rbx
  char v35; // al
  int *v36; // rdi
  int *m; // rbx
  int v38; // ecx
  int v39; // edx
  _QWORD *v40; // rax
  _QWORD *v41; // rax
  _QWORD *v42; // rdx
  const char *v43; // r9
  unsigned int v44; // eax
  void **Src; // r8
  __int64 v46; // rcx
  char v48; // al
  __int64 v49; // rax
  void **v50; // rdx
  int v51; // eax
  __int64 v52; // rax
  void **v53; // rdx
  int v54; // eax
  __int64 *MetricDatapointValueName; // rax
  unsigned int v56; // edi
  int *v57; // r15
  int *v58; // rbx
  int v59; // ecx
  __int64 v60; // rax
  int v61; // eax
  __int64 v62; // rax
  int v63; // eax
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // rax
  int v67; // eax
  __int64 v68; // rax
  int v69; // eax
  __int64 v70; // rax
  int v71; // eax
  __int64 v72; // rax
  int v73; // eax
  __int64 v74; // rax
  int v75; // eax
  int v76; // [rsp+20h] [rbp-E0h]
  unsigned int v77; // [rsp+20h] [rbp-E0h]
  size_t Size; // [rsp+30h] [rbp-D0h]
  size_t Sizec; // [rsp+30h] [rbp-D0h]
  size_t Sized; // [rsp+30h] [rbp-D0h]
  size_t Sizee; // [rsp+30h] [rbp-D0h]
  size_t Sizea; // [rsp+30h] [rbp-D0h]
  size_t Sizef; // [rsp+30h] [rbp-D0h]
  size_t Sizeg; // [rsp+30h] [rbp-D0h]
  size_t Sizeb; // [rsp+30h] [rbp-D0h]
  char v86; // [rsp+40h] [rbp-C0h]
  int v87; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v88; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v89; // [rsp+58h] [rbp-A8h]
  __int64 v90; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v91; // [rsp+68h] [rbp-98h]
  unsigned int v92; // [rsp+70h] [rbp-90h]
  __int128 v93; // [rsp+78h] [rbp-88h] BYREF
  __int64 v94; // [rsp+88h] [rbp-78h]
  __int64 v95; // [rsp+90h] [rbp-70h]
  unsigned int v96; // [rsp+98h] [rbp-68h]
  __int64 v97; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v98; // [rsp+A8h] [rbp-58h]
  void *v99; // [rsp+B0h] [rbp-50h] BYREF
  int v100; // [rsp+B8h] [rbp-48h]
  int v101; // [rsp+BCh] [rbp-44h]
  __int64 v102; // [rsp+C0h] [rbp-40h]
  unsigned int v103; // [rsp+C8h] [rbp-38h]
  int v104[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v105; // [rsp+D8h] [rbp-28h]
  int v106[3]; // [rsp+E0h] [rbp-20h] BYREF
  int v107; // [rsp+ECh] [rbp-14h]
  _QWORD *v108; // [rsp+F0h] [rbp-10h]
  int v109[2]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v110; // [rsp+100h] [rbp+0h]
  __int64 v111; // [rsp+108h] [rbp+8h]
  __int64 v112; // [rsp+110h] [rbp+10h]
  int v113[4]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v114[2]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v115[2]; // [rsp+138h] [rbp+38h] BYREF
  int v116[2]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v117; // [rsp+150h] [rbp+50h]
  __int128 v118; // [rsp+158h] [rbp+58h] BYREF
  unsigned int v119[2]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v120; // [rsp+170h] [rbp+70h]
  __int64 v121[2]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v122[2]; // [rsp+188h] [rbp+88h] BYREF
  __int64 v123[2]; // [rsp+198h] [rbp+98h] BYREF
  __int64 v124[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v125[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  int v126[4]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v127[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v128; // [rsp+1E8h] [rbp+E8h] BYREF
  int v129[4]; // [rsp+1F8h] [rbp+F8h] BYREF
  int v130[4]; // [rsp+208h] [rbp+108h] BYREF
  int v131[4]; // [rsp+218h] [rbp+118h] BYREF
  int v132[4]; // [rsp+228h] [rbp+128h] BYREF
  char v133; // [rsp+238h] [rbp+138h] BYREF
  int v134; // [rsp+248h] [rbp+148h] BYREF
  int v135; // [rsp+258h] [rbp+158h] BYREF
  char v136[16]; // [rsp+268h] [rbp+168h] BYREF
  int v137; // [rsp+278h] [rbp+178h] BYREF
  void *v138[2]; // [rsp+288h] [rbp+188h] BYREF
  __int64 v139; // [rsp+298h] [rbp+198h]
  unsigned __int64 v140; // [rsp+2A0h] [rbp+1A0h]
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]
  va_list va; // [rsp+310h] [rbp+210h] BYREF

  va_start(va, a4);
  v4 = a4;
  v103 = a4;
  v5 = a3;
  v112 = a3;
  v6 = a2;
  *(_QWORD *)v109 = a2;
  v7 = a1;
  v108 = a1;
  v8 = a1 + 2;
  v90 = (__int64)L"data";
  v91 = 4;
  v88 = (__int64)(a1 + 2);
  LODWORD(v89) = 0;
  HIDWORD(v89) = v107;
  JsonBuilder::find<>(a1 + 2, v104, &v88, &v90);
  if ( !v105 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x70C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
      v9);
  if ( *(__int64 **)v104 != v8 )
    __int2c();
  *(_BYTE *)(*v8 + 4LL * v105 + 7) = -3;
  v90 = (__int64)L"data";
  v91 = 4;
  v88 = (__int64)v8;
  LODWORD(v89) = 0;
  HIDWORD(v89) = v107;
  LODWORD(Size) = 0;
  JsonBuilder::AddValue((int)v8, (int)v104, 0, (int)&v88, (__int64)&v90, 255, Size, 0);
  v88 = (__int64)L"baseType";
  v89 = 8;
  JsonImplementType<wchar_t *>::AddValue((int)v106, (int)v8, 0, (int)v104, (__int64)&v88, L"MetricStream");
  v90 = (__int64)L"baseData";
  v91 = 8;
  LODWORD(Sizec) = 0;
  JsonBuilder::AddValue((int)v8, (int)&v88, 0, (int)v104, (__int64)&v90, 255, Sizec, 0);
  v90 = (__int64)L"baseVer";
  v91 = 7;
  JsonImplementType<wchar_t *>::AddValue((int)v106, (int)v8, 0, (int)&v88, (__int64)&v90, L"1.0");
  v90 = (__int64)L"startTimeExclusive";
  v91 = 18;
  LODWORD(Sized) = 8;
  JsonBuilder::AddValue((int)v8, (int)v106, 0, (int)&v88, (__int64)&v90, 250, Sized, va);
  v90 = (__int64)L"metrics";
  v91 = 7;
  LODWORD(Sizee) = 0;
  JsonBuilder::AddValue((int)v8, (int)v129, 0, (int)&v88, (__int64)&v90, 254, Sizee, 0);
  v111 = v7[104] + 64LL;
  v10 = 0;
  while ( 1 )
  {
    v96 = v10;
    if ( v10 >= v4 )
      break;
    v11 = (_QWORD *)*v6;
    if ( *v6 == v5 )
      break;
    v124[0] = (__int64)&::Src;
    v124[1] = 0;
    LODWORD(Sizea) = 0;
    JsonBuilder::AddValue((int)v8, (int)v113, 0, (int)v129, (__int64)v124, 255, Sizea, 0);
    v125[0] = (__int64)L"attributes";
    v125[1] = 10;
    LODWORD(Sizef) = 0;
    JsonBuilder::AddValue((int)v8, (int)v106, 0, (int)v113, (__int64)v125, 255, Sizef, 0);
    v127[0] = (__int64)L"datapoints";
    v127[1] = 10;
    LODWORD(Sizeg) = 0;
    JsonBuilder::AddValue((int)v8, (int)v130, 0, (int)v113, (__int64)v127, 254, Sizeg, 0);
    v12 = v11[6];
    v90 = v12;
    v13 = v11[5];
    if ( v13 == v12 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x744,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
        (const char *)0x87C52612LL,
        v76);
    v14 = 0;
    v86 = 0;
    while ( v13 != v12 )
    {
      v15 = (_QWORD *)v111;
      std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned long,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned long>>,0>>::find(
        v111,
        v104,
        v13);
      v16 = *(_QWORD *)v104;
      if ( *(_QWORD *)v104 == *v15 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x74A,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
          (const char *)0x80070490LL,
          v76);
      if ( !*(_QWORD *)(*(_QWORD *)v104 + 160LL) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x74F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
          (const char *)0x87C52613LL,
          v76);
      if ( !*(_QWORD *)(*(_QWORD *)v104 + 184LL)
        && (*(char *)(*(_QWORD *)v104 + 40LL) >= 0
         || *(_QWORD *)(*(_QWORD *)v104 + 120LL) == *(_QWORD *)(*(_QWORD *)v104 + 128LL)) )
      {
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x756,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
          (const char *)0x87C52614LL,
          v76);
      }
      v114[0] = (__int64)&::Src;
      v114[1] = 0;
      LODWORD(Sizea) = 0;
      JsonBuilder::AddValue((int)v8, (int)&v88, 0, (int)v130, (__int64)v114, 255, Sizea, 0);
      v19 = (_QWORD *)(v16 + 144);
      if ( *(_QWORD *)(v16 + 168) > 7u )
        v19 = (_QWORD *)*v19;
      v115[0] = v19;
      v115[1] = *(_QWORD *)(v16 + 160);
      *(_QWORD *)v116 = L"name";
      v117 = 4;
      JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(
        (unsigned int)&v133,
        (_DWORD)v8,
        v18,
        (unsigned int)&v88,
        (__int64)v116,
        (__int64)v115);
      for ( i = **(_QWORD **)(v16 + 176); !*(_BYTE *)(i + 25); i = j )
      {
        LOBYTE(v20) = *(_BYTE *)(i + 32);
        Microsoft::Diagnostics::TriggerAggregator::GetMetricDatapointValueName(&v118, v20);
        v22 = *(_BYTE *)(i + 32);
        v23 = 246;
        if ( v22 != 8 )
          v23 = *(_DWORD *)(v16 + 80);
        v24 = *(char **)(i + 48);
        v25 = *(char **)(i + 40);
        if ( v25 == v24 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x761,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
            (const char *)0x87C52615LL,
            v76);
        if ( (unsigned __int8)(v22 - 8) <= 1u )
        {
          if ( v24 - v25 != 4 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x765,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
              (const char *)0x87C52615LL,
              v76);
          if ( !*(_DWORD *)v25 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x768,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
              (const char *)0x87C52615LL,
              v76);
          if ( v14 )
          {
            if ( v92 != *(_DWORD *)v25 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x76C,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                (const char *)0x87C52615LL,
                v76);
          }
          else
          {
            v92 = *(_DWORD *)v25;
            v14 = 1;
            v86 = 1;
          }
          v23 = 246;
        }
        v128 = v118;
        LODWORD(Sizea) = (_DWORD)v24 - (_DWORD)v25;
        JsonBuilder::AddValue((int)v8, (int)&v134, 0, (int)&v88, (__int64)&v128, v23, Sizea, v25);
        if ( *(_BYTE *)(*(_QWORD *)(i + 16) + 25LL) )
        {
          for ( j = *(_QWORD *)(i + 8); !*(_BYTE *)(j + 25) && i == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
            i = j;
        }
        else
        {
          j = std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<unsigned long,std::wstring> const,unsigned __int64>>>::_Min();
        }
      }
      if ( *(char *)(v16 + 40) < 0 )
      {
        v27 = *(_QWORD *)(v16 + 128);
        if ( *(_QWORD *)(v16 + 120) == v27 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x780,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
            (const char *)0x87C52615LL,
            v76);
        if ( (__int64)(*(_QWORD *)(v16 + 104) - *(_QWORD *)(v16 + 96)) >> 5 != ((v27 - *(_QWORD *)(v16 + 120)) >> 2) - 1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x781,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
            (const char *)0x87C52615LL,
            v76);
        *(_QWORD *)v119 = L"explicitBounds";
        v120 = 14;
        LODWORD(Sizea) = 0;
        JsonBuilder::AddValue((int)v8, (int)v131, 0, (int)&v88, (__int64)v119, 254, Sizea, 0);
        v29 = *(_QWORD **)(v16 + 96);
        v30 = *(_QWORD **)(v16 + 104);
        while ( v29 != v30 )
        {
          *(_OWORD *)v138 = 0;
          v139 = 0;
          v140 = 0;
          if ( v29[3] <= 0xFu )
            v31 = v29;
          else
            v31 = (_QWORD *)*v29;
          std::string::_Construct<2,char const *>(v138, v31, v29[2]);
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(&v99);
          switch ( *(_DWORD *)(v16 + 80) )
          {
            case 0xF6:
              v49 = *(_QWORD *)(v16 + 88);
              switch ( v49 )
              {
                case 8LL:
                  v93 = 0;
                  v94 = 0;
                  v95 = 0;
                  v50 = v138;
                  if ( v140 > 0xF )
                    v50 = (void **)v138[0];
                  std::string::_Construct<2,char const *>(&v93, v50, v139);
                  v51 = Microsoft::Diagnostics::Utils::Json::ConvertJsonTypeStringToByteArray<unsigned __int64,std::string>(
                          *(unsigned int *)(v16 + 80),
                          &v93,
                          &v99);
                  if ( v51 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x7AA,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                      (const char *)(unsigned int)v51,
                      v77);
                  break;
                case 4LL:
                  v70 = std::string::string(&v93, v138);
                  v71 = Microsoft::Diagnostics::Utils::Json::ConvertJsonTypeStringToByteArray<unsigned long,std::string>(
                          *(unsigned int *)(v16 + 80),
                          v70,
                          &v99);
                  if ( v71 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x7AE,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                      (const char *)(unsigned int)v71,
                      v77);
                  break;
                case 2LL:
                  v72 = std::string::string(&v93, v138);
                  v73 = Microsoft::Diagnostics::Utils::Json::ConvertJsonTypeStringToByteArray<short,std::string>(
                          *(unsigned int *)(v16 + 80),
                          v72,
                          &v99);
                  if ( v73 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x7B2,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                      (const char *)(unsigned int)v73,
                      v77);
                  break;
                case 1LL:
                  v74 = std::string::string(&v93, v138);
                  v75 = Microsoft::Diagnostics::Utils::Json::ConvertJsonTypeStringToByteArray<char,std::string>(
                          *(unsigned int *)(v16 + 80),
                          v74,
                          &v99);
                  if ( v75 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x7B6,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                      (const char *)(unsigned int)v75,
                      v77);
                  break;
                default:
                  wil::details::in1diag3::Throw_Win32(
                    retaddr,
                    (void *)0x7BA,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                    (const char *)0x70C,
                    v77);
              }
              break;
            case 0xF7:
              v52 = *(_QWORD *)(v16 + 88);
              switch ( v52 )
              {
                case 8LL:
                  v93 = 0;
                  v94 = 0;
                  v95 = 0;
                  v53 = v138;
                  if ( v140 > 0xF )
                    v53 = (void **)v138[0];
                  std::string::_Construct<2,char const *>(&v93, v53, v139);
                  v54 = Microsoft::Diagnostics::Utils::Json::ConvertJsonTypeStringToByteArray<__int64,std::string>(
                          *(unsigned int *)(v16 + 80),
                          &v93,
                          &v99);
                  if ( v54 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x791,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                      (const char *)(unsigned int)v54,
                      v77);
                  break;
                case 4LL:
                  v64 = std::string::string(&v93, v138);
                  v65 = Microsoft::Diagnostics::Utils::Json::ConvertJsonTypeStringToByteArray<long,std::string>(
                          *(unsigned int *)(v16 + 80),
                          v64,
                          &v99);
                  if ( v65 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x795,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                      (const char *)(unsigned int)v65,
                      v77);
                  break;
                case 2LL:
                  v66 = std::string::string(&v93, v138);
                  v67 = Microsoft::Diagnostics::Utils::Json::ConvertJsonTypeStringToByteArray<short,std::string>(
                          *(unsigned int *)(v16 + 80),
                          v66,
                          &v99);
                  if ( v67 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x799,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                      (const char *)(unsigned int)v67,
                      v77);
                  break;
                case 1LL:
                  v68 = std::string::string(&v93, v138);
                  v69 = Microsoft::Diagnostics::Utils::Json::ConvertJsonTypeStringToByteArray<char,std::string>(
                          *(unsigned int *)(v16 + 80),
                          v68,
                          &v99);
                  if ( v69 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x79D,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                      (const char *)(unsigned int)v69,
                      v77);
                  break;
                default:
                  wil::details::in1diag3::Throw_Win32(
                    retaddr,
                    (void *)0x7A1,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                    (const char *)0x70C,
                    v77);
              }
              break;
            case 0xF8:
              if ( *(_QWORD *)(v16 + 88) == 8 )
              {
                v60 = std::string::string(&v93, v138);
                v61 = Microsoft::Diagnostics::Utils::Json::ConvertJsonTypeStringToByteArray<double,std::string>(
                        *(unsigned int *)(v16 + 80),
                        v60,
                        &v99);
                if ( v61 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x7C3,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                    (const char *)(unsigned int)v61,
                    v77);
              }
              else
              {
                if ( *(_QWORD *)(v16 + 88) != 4 )
                  wil::details::in1diag3::Throw_Win32(
                    retaddr,
                    (void *)0x7CB,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                    (const char *)0x70C,
                    v77);
                v62 = std::string::string(&v93, v138);
                v63 = Microsoft::Diagnostics::Utils::Json::ConvertJsonTypeStringToByteArray<float,std::string>(
                        *(unsigned int *)(v16 + 80),
                        v62,
                        &v99);
                if ( v63 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x7C7,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                    (const char *)(unsigned int)v63,
                    v77);
              }
              break;
            default:
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x7D1,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
                (const char *)0x8007065ELL,
                v77);
          }
          v121[0] = (__int64)&::Src;
          v121[1] = 0;
          LODWORD(Sizeb) = v100 - (_DWORD)v99;
          JsonBuilder::AddValue((int)v8, (int)&v135, 0, (int)v131, (__int64)v121, *(_DWORD *)(v16 + 80), Sizeb, v99);
          if ( v99 )
            std::_Deallocate<16>(v99, v102 - (_QWORD)v99);
          std::string::_Tidy_deallocate(v138);
          v29 += 4;
        }
        LOBYTE(v28) = 7;
        MetricDatapointValueName = (__int64 *)Microsoft::Diagnostics::TriggerAggregator::GetMetricDatapointValueName(
                                                v136,
                                                v28);
        v122[0] = *MetricDatapointValueName;
        v122[1] = MetricDatapointValueName[1];
        LODWORD(Sizeb) = 0;
        JsonBuilder::AddValue((int)v8, (int)v132, 0, (int)&v88, (__int64)v122, 254, Sizeb, 0);
        v56 = 0;
        v57 = *(int **)(v16 + 128);
        v58 = *(int **)(v16 + 120);
        if ( v58 == v57 )
          goto LABEL_87;
        do
        {
          v87 = *v58;
          v59 = v56 + v87;
          if ( v56 + v87 < v56 )
            v59 = -1;
          v56 = v59;
          v123[0] = (__int64)&::Src;
          v123[1] = 0;
          LODWORD(Sizea) = 4;
          JsonBuilder::AddValue((int)v8, (int)&v137, 0, (int)v132, (__int64)v123, 246, Sizea, &v87);
          ++v58;
        }
        while ( v58 != v57 );
        v5 = v112;
        if ( !v56 )
LABEL_87:
          v48 = 1;
        else
          v48 = 0;
        if ( v48 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7E6,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
            (const char *)0x87C52615LL,
            v76);
        v14 = v86;
        if ( v86 )
        {
          if ( v92 != v56 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x7EA,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
              (const char *)0x87C52615LL,
              v76);
        }
        else
        {
          v92 = v56;
        }
      }
      v13 += 8;
      v12 = v90;
    }
    v32 = *(__int64 **)(v108[104] + 32LL);
    v33 = (__int64 *)v32[1];
    v101 = 0;
    for ( k = v32; !*((_BYTE *)v33 + 25); v33 = (__int64 *)*v33 )
    {
      if ( (unsigned __int64)v33[4] >= v11[4] )
        k = v33;
      else
        v33 += 2;
    }
    if ( *((_BYTE *)k + 25) || v11[4] < (unsigned __int64)k[4] )
    {
      k = v32;
LABEL_49:
      v35 = 1;
      goto LABEL_50;
    }
    if ( k == v32 )
      goto LABEL_49;
    v35 = 0;
LABEL_50:
    if ( v35 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7F8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
        (const char *)0x80070490LL,
        v76);
    v36 = (int *)k[6];
    for ( m = (int *)k[5]; m != v36; m += 18 )
    {
      v38 = *m;
      v39 = m[8];
      v40 = m + 10;
      if ( *((_QWORD *)m + 8) > 7u )
        v40 = (_QWORD *)*v40;
      v97 = (__int64)v40;
      v98 = *((_QWORD *)m + 7);
      LODWORD(Sizea) = v38;
      JsonBuilder::AddValue((int)v8, (int)v126, 0, (int)v106, (__int64)&v97, v39, Sizea, *((void **)m + 1));
    }
    v6 = *(_QWORD **)v109;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>>>>,std::_Iterator_base0>::operator++(*(_QWORD *)v109);
    v10 = v96 + 1;
    v7 = v108;
    v4 = v103;
  }
  v41 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD *))(*v7 + 120LL))(v7);
  if ( v41[5] <= 7u )
    v42 = v41 + 2;
  else
    v42 = (_QWORD *)v41[2];
  *(_OWORD *)v138 = 0;
  v139 = 0;
  v140 = 0;
  std::wstring::_Construct<1,wchar_t *>(v138, v42, v41[4]);
  if ( v139 )
  {
    v97 = (__int64)L"a";
    v98 = 1;
    v88 = (__int64)v8;
    LODWORD(v89) = 0;
    HIDWORD(v89) = v126[3];
    JsonBuilder::find<>(v8, v109, &v88, &v97);
    if ( !v110 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x812,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\triggeraggregator.cpp",
        v43);
    v97 = (__int64)L"name";
    v98 = 4;
    if ( *(__int64 **)v109 != v8 )
      __int2c();
    v44 = JsonBuilder::Find<>(v8, v110, &v97);
    if ( !v44 )
      __int2c();
    *(_BYTE *)(*v8 + 4LL * v44 + 7) = -3;
    Src = v138;
    if ( v140 > 7 )
      Src = (void **)v138[0];
    v46 = *v8;
    v97 = *v8 + 12 + 4LL * v44;
    v98 = *(_DWORD *)(v46 + 4LL * v44 + 4) & 0xFFFFFF;
    JsonImplementType<wchar_t *>::AddValue((int)v126, (int)v8, 0, (int)v109, (__int64)&v97, Src);
  }
  return std::wstring::_Tidy_deallocate(v138);
}

```

## disassembly

```asm
0x1800aa224  mov     [rsp-8+arg_10], rbx
0x1800aa229  push    rbp
0x1800aa22a  push    rsi
0x1800aa22b  push    rdi
0x1800aa22c  push    r12
0x1800aa22e  push    r13
0x1800aa230  push    r14
0x1800aa232  push    r15
0x1800aa234  lea     rbp, [rsp-1B0h]
0x1800aa23c  sub     rsp, 2B0h
0x1800aa243  mov     rax, cs:__security_cookie
0x1800aa24a  xor     rax, rsp
0x1800aa24d  mov     [rbp+1E0h+var_38], rax
0x1800aa254  mov     r15d, r9d
0x1800aa257  mov     [rbp+1E0h+var_218], r9d
0x1800aa25b  mov     rsi, r8
0x1800aa25e  mov     [rbp+1E0h+var_1D0], r8
0x1800aa262  mov     rdi, rdx
0x1800aa265  mov     qword ptr [rbp+1E0h+var_1E8], rdx
0x1800aa269  mov     rbx, rcx
0x1800aa26c  mov     [rbp+1E0h+var_1F0], rcx
0x1800aa270  lea     r14, [rcx+10h]
0x1800aa274  lea     r13, aData_0; "data"
0x1800aa27b  mov     [rsp+2E0h+var_280], r13
0x1800aa280  mov     [rsp+2E0h+var_278], 4
0x1800aa289  mov     [rsp+2E0h+var_290], r14
0x1800aa28e  xor     r12d, r12d
0x1800aa291  mov     dword ptr [rsp+2E0h+var_288], r12d
0x1800aa296  mov     eax, [rbp+1E0h+var_1F4]
0x1800aa299  mov     dword ptr [rsp+2E0h+var_288+4], eax
0x1800aa29d  lea     r9, [rsp+2E0h+var_280]
0x1800aa2a2  lea     r8, [rsp+2E0h+var_290]
0x1800aa2a7  lea     rdx, [rbp+1E0h+var_210]
0x1800aa2ab  mov     rcx, r14
0x1800aa2ae  call    ??$find@$$V@JsonBuilder@@QEAA?AVJsonIterator@@AEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800aa2b3  mov     edx, [rbp+1E0h+var_208]
0x1800aa2b6  test    edx, edx
0x1800aa2b8  setz    al
0x1800aa2bb  mov     rcx, [rbp+1E8h]; this
0x1800aa2c2  test    al, al
0x1800aa2c4  jnz     loc_1800AAC2A
0x1800aa2ca  cmp     qword ptr [rbp+1E0h+var_210], r14
0x1800aa2ce  jnz     loc_1800AAF78
0x1800aa2d4  test    edx, edx
0x1800aa2d6  jz      loc_1800AAC3C
0x1800aa2dc  mov     rax, [r14]
0x1800aa2df  mov     byte ptr [rax+rdx*4+7], 0FDh
0x1800aa2e4  mov     [rsp+2E0h+var_280], r13
0x1800aa2e9  mov     [rsp+2E0h+var_278], 4
0x1800aa2f2  mov     [rsp+2E0h+var_290], r14
0x1800aa2f7  mov     dword ptr [rsp+2E0h+var_288], r12d
0x1800aa2fc  mov     eax, [rbp+1E0h+var_1F4]
0x1800aa2ff  mov     dword ptr [rsp+2E0h+var_288+4], eax
0x1800aa303  mov     [rsp+2E0h+var_2A8], r12; Src
0x1800aa308  mov     dword ptr [rsp+2E0h+Size], r12d; Size
0x1800aa30d  mov     dword ptr [rsp+2E0h+Src], 0FFh; int
0x1800aa315  lea     rax, [rsp+2E0h+var_280]
0x1800aa31a  mov     qword ptr [rsp+2E0h+var_2C0], rax; __int64
0x1800aa31f  lea     r9, [rsp+2E0h+var_290]; int
0x1800aa324  xor     r8d, r8d; int
0x1800aa327  lea     rdx, [rbp+1E0h+var_210]; int
0x1800aa32b  mov     rcx, r14; int
0x1800aa32e  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x1800aa333  lea     rax, aBasetype; "baseType"
0x1800aa33a  mov     [rsp+2E0h+var_290], rax
0x1800aa33f  mov     r13d, 8
0x1800aa345  mov     [rsp+2E0h+var_288], r13
0x1800aa34a  lea     rax, aMetricstream; "MetricStream"
0x1800aa351  mov     [rsp+2E0h+Src], rax; Src
0x1800aa356  lea     rax, [rsp+2E0h+var_290]
0x1800aa35b  mov     qword ptr [rsp+2E0h+var_2C0], rax; __int64
0x1800aa360  lea     r9, [rbp+1E0h+var_210]; int
0x1800aa364  xor     r8d, r8d; int
0x1800aa367  mov     rdx, r14; int
0x1800aa36a  lea     rcx, [rbp+1E0h+var_200]; int
0x1800aa36e  call    ?AddValue@?$JsonImplementType@PEA_W@@SA?AVJsonIterator@@AEAVJsonBuilder@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEB_W@Z; JsonImplementType<wchar_t *>::AddValue(JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,wchar_t const *)
0x1800aa373  lea     rax, aBasedata; "baseData"
0x1800aa37a  mov     [rsp+2E0h+var_280], rax
0x1800aa37f  mov     [rsp+2E0h+var_278], r13
0x1800aa384  mov     [rsp+2E0h+var_2A8], r12; Src
0x1800aa389  mov     dword ptr [rsp+2E0h+Size], r12d; Size
0x1800aa38e  mov     dword ptr [rsp+2E0h+Src], 0FFh; int
0x1800aa396  lea     rax, [rsp+2E0h+var_280]
0x1800aa39b  mov     qword ptr [rsp+2E0h+var_2C0], rax; __int64
0x1800aa3a0  lea     r9, [rbp+1E0h+var_210]; int
0x1800aa3a4  xor     r8d, r8d; int
0x1800aa3a7  lea     rdx, [rsp+2E0h+var_290]; int
0x1800aa3ac  mov     rcx, r14; int
0x1800aa3af  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x1800aa3b4  lea     rax, aBasever_0; "baseVer"
0x1800aa3bb  mov     [rsp+2E0h+var_280], rax
0x1800aa3c0  mov     [rsp+2E0h+var_278], 7
0x1800aa3c9  lea     rax, a10_0; "1.0"
0x1800aa3d0  mov     [rsp+2E0h+Src], rax; Src
0x1800aa3d5  lea     rax, [rsp+2E0h+var_280]
0x1800aa3da  mov     qword ptr [rsp+2E0h+var_2C0], rax; __int64
0x1800aa3df  lea     r9, [rsp+2E0h+var_290]; int
0x1800aa3e4  xor     r8d, r8d; int
0x1800aa3e7  mov     rdx, r14; int
0x1800aa3ea  lea     rcx, [rbp+1E0h+var_200]; int
0x1800aa3ee  call    ?AddValue@?$JsonImplementType@PEA_W@@SA?AVJsonIterator@@AEAVJsonBuilder@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEB_W@Z; JsonImplementType<wchar_t *>::AddValue(JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,wchar_t const *)
0x1800aa3f3  lea     rax, aStarttimeexclu; "startTimeExclusive"
0x1800aa3fa  mov     [rsp+2E0h+var_280], rax
0x1800aa3ff  mov     [rsp+2E0h+var_278], 12h
0x1800aa408  lea     rax, [rbp+1E0h+arg_20]
0x1800aa40f  mov     [rsp+2E0h+var_2A8], rax; Src
0x1800aa414  mov     dword ptr [rsp+2E0h+Size], r13d; Size
0x1800aa419  mov     dword ptr [rsp+2E0h+Src], 0FAh; int
0x1800aa421  lea     rax, [rsp+2E0h+var_280]
0x1800aa426  mov     qword ptr [rsp+2E0h+var_2C0], rax; __int64
0x1800aa42b  lea     r9, [rsp+2E0h+var_290]; int
0x1800aa430  xor     r8d, r8d; int
0x1800aa433  lea     rdx, [rbp+1E0h+var_200]; int
0x1800aa437  mov     rcx, r14; int
0x1800aa43a  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x1800aa43f  lea     rax, aMetrics; "metrics"
0x1800aa446  mov     [rsp+2E0h+var_280], rax
0x1800aa44b  mov     [rsp+2E0h+var_278], 7
0x1800aa454  mov     [rsp+2E0h+var_2A8], r12; Src
0x1800aa459  mov     dword ptr [rsp+2E0h+Size], r12d; Size
0x1800aa45e  mov     dword ptr [rsp+2E0h+Src], 0FEh; int
0x1800aa466  lea     rax, [rsp+2E0h+var_280]
0x1800aa46b  mov     qword ptr [rsp+2E0h+var_2C0], rax; __int64
0x1800aa470  lea     r9, [rsp+2E0h+var_290]; int
0x1800aa475  xor     r8d, r8d; int
0x1800aa478  lea     rdx, [rbp+1E0h+var_E8]; int
0x1800aa47f  mov     rcx, r14; int
0x1800aa482  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x1800aa487  mov     rax, [rbx+340h]
0x1800aa48e  add     rax, 40h ; '@'
0x1800aa492  mov     [rbp+1E0h+var_1D8], rax
0x1800aa496  mov     eax, r12d
0x1800aa499  lea     rcx, Src
0x1800aa4a0  mov     [rbp+1E0h+var_248], eax
0x1800aa4a3  cmp     eax, r15d
0x1800aa4a6  jnb     loc_1800AAAAE
0x1800aa4ac  mov     r13, [rdi]
0x1800aa4af  cmp     r13, rsi
0x1800aa4b2  jz      loc_1800AAAAE
0x1800aa4b8  mov     [rbp+1E0h+var_138], rcx
0x1800aa4bf  mov     [rbp+1E0h+var_130], r12
0x1800aa4c6  mov     [rsp+2E0h+var_2A8], r12; Src
0x1800aa4cb  mov     dword ptr [rsp+2E0h+Size], r12d; Size
0x1800aa4d0  mov     ebx, 0FFh
0x1800aa4d5  mov     dword ptr [rsp+2E0h+Src], ebx; int
0x1800aa4d9  lea     rax, [rbp+1E0h+var_138]
0x1800aa4e0  mov     qword ptr [rsp+2E0h+var_2C0], rax; __int64
0x1800aa4e5  lea     r9, [rbp+1E0h+var_E8]; int
0x1800aa4ec  xor     r8d, r8d; int
0x1800aa4ef  lea     rdx, [rbp+1E0h+var_1C8]; int
0x1800aa4f3  mov     rcx, r14; int
0x1800aa4f6  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x1800aa4fb  lea     rax, aAttributes; "attributes"
0x1800aa502  mov     [rbp+1E0h+var_128], rax
0x1800aa509  mov     edi, 0Ah
0x1800aa50e  mov     [rbp+1E0h+var_120], rdi
0x1800aa515  mov     [rsp+2E0h+var_2A8], r12; Src
0x1800aa51a  mov     dword ptr [rsp+2E0h+Size], r12d; Size
0x1800aa51f  mov     dword ptr [rsp+2E0h+Src], ebx; int
0x1800aa523  lea     rax, [rbp+1E0h+var_128]
0x1800aa52a  mov     qword ptr [rsp+2E0h+var_2C0], rax; __int64
0x1800aa52f  lea     r9, [rbp+1E0h+var_1C8]; int
0x1800aa533  xor     r8d, r8d; int
0x1800aa536  lea     rdx, [rbp+1E0h+var_200]; int
0x1800aa53a  mov     rcx, r14; int
0x1800aa53d  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x1800aa542  lea     rax, aDatapoints; "datapoints"
0x1800aa549  mov     [rbp+1E0h+var_108], rax
0x1800aa550  mov     [rbp+1E0h+var_100], rdi
0x1800aa557  mov     [rsp+2E0h+var_2A8], r12; Src
0x1800aa55c  mov     dword ptr [rsp+2E0h+Size], r12d; Size
0x1800aa561  mov     dword ptr [rsp+2E0h+Src], 0FEh; int
0x1800aa569  lea     rax, [rbp+1E0h+var_108]
0x1800aa570  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x1800aa575  lea     r9, [rbp+1E0h+var_1C8]; int
0x1800aa579  xor     r8d, r8d; int
0x1800aa57c  lea     rdx, [rbp+1E0h+var_D8]; int
0x1800aa583  mov     rcx, r14; int
0x1800aa586  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x1800aa58b  mov     rax, [r13+30h]
0x1800aa58f  mov     [rsp+2E0h+var_280], rax
0x1800aa594  mov     r12, [r13+28h]
0x1800aa598  mov     rcx, [rbp+1E8h]; this
0x1800aa59f  cmp     r12, rax
0x1800aa5a2  jz      loc_1800AAA96
0x1800aa5a8  xor     r15b, r15b
0x1800aa5ab  mov     [rsp+2E0h+var_2A0], r15b
0x1800aa5b0  cmp     r12, rax
0x1800aa5b3  jz      loc_1800AA907
0x1800aa5b9  mov     r8, r12
0x1800aa5bc  lea     rdx, [rbp+1E0h+var_210]
0x1800aa5c0  mov     rdi, [rbp+1E0h+var_1D8]
0x1800aa5c4  mov     rcx, rdi
0x1800aa5c7  call    ?find@?$_Tree@V?$_Tmap_traits@_KKU?$less@_K@std@@V?$allocator@U?$pair@$$CB_KK@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KK@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,ulong,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,ulong>>,0>>::find(unsigned __int64 const &)
0x1800aa5cc  mov     rbx, qword ptr [rbp+1E0h+var_210]
0x1800aa5d0  cmp     rbx, [rdi]
0x1800aa5d3  setz    al
0x1800aa5d6  mov     rcx, [rbp+1E8h]; this
0x1800aa5dd  xor     edx, edx
0x1800aa5df  test    al, al
0x1800aa5e1  jnz     loc_1800AAA17
0x1800aa5e7  mov     rcx, [rbp+1E8h]; this
0x1800aa5ee  cmp     [rbx+0A0h], rdx
0x1800aa5f5  jz      loc_1800AA9FF
0x1800aa5fb  cmp     [rbx+0B8h], rdx
0x1800aa602  jz      loc_1800AAF8D
0x1800aa608  mov     al, dl
0x1800aa60a  mov     rcx, [rbp+1E8h]; this
0x1800aa611  test    al, al
0x1800aa613  jnz     loc_1800AA9E7
0x1800aa619  lea     rax, Src
0x1800aa620  mov     [rbp+1E0h+var_1B8], rax
0x1800aa624  mov     [rbp+1E0h+var_1B0], rdx
0x1800aa628  mov     [rsp+2E0h+var_2A8], rdx; Src
0x1800aa62d  mov     dword ptr [rsp+2E0h+Size], edx; Size
0x1800aa631  mov     dword ptr [rsp+2E0h+Src], 0FFh; int
0x1800aa639  lea     rax, [rbp+1E0h+var_1B8]
0x1800aa63d  mov     qword ptr [rsp+2E0h+var_2C0], rax; __int64
0x1800aa642  lea     r9, [rbp+1E0h+var_D8]; int
0x1800aa649  xor     r8d, r8d; int
0x1800aa64c  lea     rdx, [rsp+2E0h+var_290]; int
0x1800aa651  mov     rcx, r14; int
0x1800aa654  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x1800aa659  lea     rax, [rbx+90h]
0x1800aa660  cmp     qword ptr [rbx+0A8h], 7
0x1800aa668  jbe     short loc_1800AA66D
0x1800aa66a  mov     rax, [rax]
0x1800aa66d  mov     [rbp+1E0h+var_1A8], rax
0x1800aa671  mov     rax, [rbx+0A0h]
0x1800aa678  mov     [rbp+1E0h+var_1A0], rax
0x1800aa67c  lea     rax, aName_3; "name"
0x1800aa683  mov     qword ptr [rbp+1E0h+var_198], rax
0x1800aa687  mov     [rbp+1E0h+var_190], 4
0x1800aa68f  lea     rax, [rbp+1E0h+var_1A8]
0x1800aa693  mov     [rsp+2E0h+Src], rax
0x1800aa698  lea     rax, [rbp+1E0h+var_198]
0x1800aa69c  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x1800aa6a1  lea     r9, [rsp+2E0h+var_290]
0x1800aa6a6  mov     rdx, r14
0x1800aa6a9  lea     rcx, [rbp+1E0h+var_A8]
0x1800aa6b0  call    ?AddValue@?$JsonImplementType@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@@SA?AVJsonIterator@@AEAVJsonBuilder@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@3@Z; JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800aa6b5  mov     rdi, [rbx+0B0h]
0x1800aa6bc  mov     rdi, [rdi]
0x1800aa6bf  cmp     byte ptr [rdi+19h], 0
0x1800aa6c3  jnz     loc_1800AA76E
0x1800aa6c9  mov     dl, [rdi+20h]
0x1800aa6cc  lea     rcx, [rbp+1E0h+var_188]
0x1800aa6d0  call    ?GetMetricDatapointValueName@TriggerAggregator@Diagnostics@Microsoft@@CA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@VFieldAggregationMode@23@@Z; Microsoft::Diagnostics::TriggerAggregator::GetMetricDatapointValueName(Microsoft::Diagnostics::FieldAggregationMode)
0x1800aa6d5  mov     al, [rdi+20h]
0x1800aa6d8  cmp     al, 8
0x1800aa6da  mov     r9d, 0F6h
0x1800aa6e0  jnz     loc_1800AA89D
0x1800aa6e6  mov     r8, [rdi+30h]
0x1800aa6ea  mov     rdx, [rdi+28h]
0x1800aa6ee  mov     rcx, [rbp+1E8h]; this
0x1800aa6f5  cmp     rdx, r8
0x1800aa6f8  jz      loc_1800AA8A6
0x1800aa6fe  sub     al, 8
0x1800aa700  cmp     al, 1
0x1800aa702  jbe     loc_1800AA8BE
0x1800aa708  mov     rax, qword ptr [rbp+1E0h+var_188]
0x1800aa70c  mov     rcx, qword ptr [rbp+1E0h+var_188+8]
0x1800aa710  mov     qword ptr [rbp+1E0h+var_F8], rax
0x1800aa717  mov     qword ptr [rbp+1E0h+var_F8+8], rcx
0x1800aa71e  sub     r8d, edx
0x1800aa721  mov     [rsp+2E0h+var_2A8], rdx; Src
0x1800aa726  mov     dword ptr [rsp+2E0h+Size], r8d; Size
0x1800aa72b  mov     dword ptr [rsp+2E0h+Src], r9d; int
0x1800aa730  lea     rax, [rbp+1E0h+var_F8]
0x1800aa737  mov     qword ptr [rsp+2E0h+var_2C0], rax; __int64
0x1800aa73c  lea     r9, [rsp+2E0h+var_290]; int
0x1800aa741  xor     r8d, r8d; int
0x1800aa744  lea     rdx, [rbp+1E0h+var_98]; int
0x1800aa74b  mov     rcx, r14; int
0x1800aa74e  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x1800aa753  mov     rcx, [rdi+10h]
0x1800aa757  cmp     byte ptr [rcx+19h], 0
0x1800aa75b  jnz     loc_1800AAC55
0x1800aa761  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBU?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<ulong,std::wstring> const,unsigned __int64>>>::_Min(std::_Tree_node<std::pair<std::pair<ulong,std::wstring> const,unsigned __int64>,void *> *)
0x1800aa766  mov     rdi, rax
0x1800aa769  jmp     loc_1800AA6BF
0x1800aa76e  test    byte ptr [rbx+28h], 80h
0x1800aa772  jz      loc_1800AAC95
0x1800aa778  mov     rcx, [rbx+80h]
0x1800aa77f  mov     rax, [rbp+1E8h]
0x1800aa786  cmp     [rbx+78h], rcx
0x1800aa78a  jz      loc_1800AAF5D
0x1800aa790  mov     r10, [rbp+1E8h]
0x1800aa797  mov     rax, [rbx+68h]
0x1800aa79b  sub     rax, [rbx+60h]
0x1800aa79f  sar     rax, 5
0x1800aa7a3  sub     rcx, [rbx+78h]
0x1800aa7a7  sar     rcx, 2
0x1800aa7ab  dec     rcx
0x1800aa7ae  cmp     rax, rcx
0x1800aa7b1  jnz     loc_1800AAF42
0x1800aa7b7  lea     rax, aExplicitbounds_0; "explicitBounds"
0x1800aa7be  mov     qword ptr [rbp+1E0h+var_178], rax
0x1800aa7c2  mov     [rbp+1E0h+var_170], 0Eh
0x1800aa7ca  mov     [rsp+2E0h+var_2A8], 0; Src
  ... truncated ...
```
