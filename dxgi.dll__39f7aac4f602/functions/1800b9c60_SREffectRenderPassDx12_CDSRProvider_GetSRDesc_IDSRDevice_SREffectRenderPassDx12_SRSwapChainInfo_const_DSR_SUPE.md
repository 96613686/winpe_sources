# SREffectRenderPassDx12::CDSRProvider::GetSRDesc(IDSRDevice *,SREffectRenderPassDx12::SRSwapChainInfo const &,DSR_SUPERRES_VARIANT_DESC_INTERNAL *)

- ea: `0x1800b9c60`
- end: `0x1800ba6cf`
- name: `?GetSRDesc@CDSRProvider@SREffectRenderPassDx12@@QEAAJPEAUIDSRDevice@@AEBUSRSwapChainInfo@2@PEAUDSR_SUPERRES_VARIANT_DESC_INTERNAL@@@Z`
- size: `2671`
- prototype: `__int64 __fastcall(SREffectRenderPassDx12::CDSRProvider *__hidden this, struct IDSRDevice *, const struct SREffectRenderPassDx12::SRSwapChainInfo *, struct DSR_SUPERRES_VARIANT_DESC_INTERNAL *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b9548`
- `0x1800bbe98`

## callees

- `0x18000c6b0`
- `0x180014750`
- `0x18001c7a4`
- `0x1800306f4`
- `0x180067d2c`
- `0x18006989c`
- `0x180075fa0`
- `0x180076f20`
- `0x180091e70`
- `0x1800b9c60`
- `0x1800bc2cc`
- `0x1800bc304`
- `0x1800bcb9c`
- `0x1800cb010`

## import_xrefs

- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabase` at `0x1800ba2fc`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabase` at `0x1800ba2fc`

## string_xrefs

- `0x1800b9d38`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b9d85`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800ba116`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800ba1ab`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800ba310`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800ba3d7`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800b9d24`: `No variants available in cache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SREffectRenderPassDx12::CDSRProvider::GetSRDesc(
        SREffectRenderPassDx12::CDSRProvider *this,
        struct IDSRDevice *a2,
        const struct SREffectRenderPassDx12::SRSwapChainInfo *a3,
        struct DSR_SUPERRES_VARIANT_DESC_INTERNAL *a4)
{
  char v7; // r12
  __int64 v8; // r13
  __int64 v9; // rbx
  unsigned __int64 v10; // r14
  unsigned int v11; // ebx
  MODEL_PACKAGE_PREFERENCE *v12; // r12
  unsigned int v14; // eax
  CModule *v15; // rcx
  int v16; // r10d
  __int64 v17; // rsi
  unsigned int v18; // r11d
  __m128i v19; // xmm6
  __int128 v20; // xmm9
  __int128 v21; // xmm10
  __int128 v22; // xmm11
  __int128 v23; // xmm12
  __int128 v24; // xmm13
  __int128 v25; // xmm14
  __int128 v26; // xmm15
  __int128 v27; // xmm7
  struct _GUID v28; // xmm8
  unsigned int v29; // eax
  unsigned int *v30; // r8
  int v31; // eax
  unsigned __int64 v32; // r9
  __int64 v33; // rdx
  unsigned int v34; // eax
  CModule *v35; // rcx
  unsigned int v36; // r14d
  int v37; // eax
  int DirectXDatabase; // eax
  __int64 v39; // rbx
  CModule *v40; // rcx
  unsigned int v41; // esi
  __int64 v42; // r15
  unsigned int v43; // r13d
  __m128i v44; // xmm6
  __int128 v45; // xmm7
  __int128 v46; // xmm8
  __int128 v47; // xmm9
  __int128 v48; // xmm10
  __int128 v49; // xmm11
  __int128 v50; // xmm12
  __int128 v51; // xmm13
  __int128 v52; // xmm14
  __int128 v53; // xmm15
  __int128 v54; // xmm1
  struct _GUID v55; // xmm2
  int v56; // eax
  bool IsModelVersionSatisfied; // al
  int *v58; // [rsp+28h] [rbp-E0h]
  char *v59; // [rsp+30h] [rbp-D8h]
  char *v60; // [rsp+30h] [rbp-D8h]
  char v61; // [rsp+38h] [rbp-D0h]
  int v62[4]; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v63; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v64; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v65[3]; // [rsp+70h] [rbp-98h] BYREF
  struct _GUID v66; // [rsp+88h] [rbp-80h] BYREF
  __int128 v67; // [rsp+98h] [rbp-70h]
  __int128 v68; // [rsp+A8h] [rbp-60h]
  __int128 v69; // [rsp+B8h] [rbp-50h]
  __int128 v70; // [rsp+C8h] [rbp-40h]
  __int128 v71; // [rsp+D8h] [rbp-30h]
  __int128 v72; // [rsp+E8h] [rbp-20h]
  __int128 v73; // [rsp+F8h] [rbp-10h]
  __int128 v74; // [rsp+108h] [rbp+0h]
  __int128 v75; // [rsp+118h] [rbp+10h]
  __int128 v76; // [rsp+128h] [rbp+20h]
  __m128i v77; // [rsp+138h] [rbp+30h]
  __int64 v78; // [rsp+148h] [rbp+40h]
  struct _GUID v79; // [rsp+158h] [rbp+50h] BYREF
  __int128 v80; // [rsp+168h] [rbp+60h]
  __int128 v81; // [rsp+178h] [rbp+70h]
  __int128 v82; // [rsp+188h] [rbp+80h]
  __int128 v83; // [rsp+198h] [rbp+90h]
  __int128 v84; // [rsp+1A8h] [rbp+A0h]
  __int128 v85; // [rsp+1B8h] [rbp+B0h]
  __int128 v86; // [rsp+1C8h] [rbp+C0h]
  __int128 v87; // [rsp+1D8h] [rbp+D0h]
  __int128 v88; // [rsp+1E8h] [rbp+E0h]
  __int128 v89; // [rsp+1F8h] [rbp+F0h]
  __m128i v90; // [rsp+208h] [rbp+100h] BYREF
  __int64 v91; // [rsp+218h] [rbp+110h]
  wil::details::in1diag3 *retaddr; // [rsp+310h] [rbp+208h]

  *(_QWORD *)&v64 = a3;
  v7 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&v63 = 0;
    v31 = (**(__int64 (__fastcall ***)(struct IDSRDevice *, GUID *, __int128 *))a2)(
            a2,
            &GUID_6069f18a_2f9c_4e9c_afec_6a419387d914,
            &v63);
    v11 = v31;
    if ( v31 < 0 )
    {
      v32 = (unsigned int)v31;
      v33 = 545;
      goto LABEL_40;
    }
    v34 = (*(__int64 (__fastcall **)(struct IDSRDevice *))(*(_QWORD *)a2 + 24LL))(a2);
    v36 = v34;
    if ( v34 )
    {
      if ( *(&g_AutoSRConfig + 6) )
        DebugPrint("%d DSR variants found", v34);
      memset_0(&v79, 0, 0xC8u);
      if ( *(&g_AutoSRConfig + 13) != 0xFF && *(&g_AutoSRConfig + 13) < v36 )
      {
        v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _GUID *))(*(_QWORD *)v63 + 40LL))(
                v63,
                *(&g_AutoSRConfig + 13),
                &v79);
        v11 = v37;
        if ( v37 >= 0 )
        {
          *(struct _GUID *)a4 = v79;
          *((_OWORD *)a4 + 1) = v80;
          *((_OWORD *)a4 + 2) = v81;
          *((_OWORD *)a4 + 3) = v82;
          *((_OWORD *)a4 + 4) = v83;
          *((_OWORD *)a4 + 5) = v84;
          *((_OWORD *)a4 + 6) = v85;
          *((_OWORD *)a4 + 7) = v86;
          *((_OWORD *)a4 + 8) = v87;
          *((_OWORD *)a4 + 9) = v88;
          *((_OWORD *)a4 + 10) = v89;
          *((__m128i *)a4 + 11) = v90;
          *((_QWORD *)a4 + 24) = v91;
          v11 = 0;
          goto LABEL_72;
        }
        v32 = (unsigned int)v37;
        v33 = 564;
LABEL_40:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
          (const char *)v32,
          (int)v58);
LABEL_72:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v63);
        return v11;
      }
      *(_QWORD *)v62 = 0x8000000000000000uLL;
      LODWORD(v65[0]) = 8;
      v60 = (char *)v65;
      v58 = v62;
      DirectXDatabase = QueryDirectXDatabase(16, 0, 0, 0);
      if ( DirectXDatabase < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x23D,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
          (const char *)(unsigned int)DirectXDatabase,
          (int)v62);
      *(_QWORD *)&v64 = 0;
      if ( (unsigned int)CompatValueImpl("AutoSR.ModelPkgPrefOverride", (unsigned __int64 *)&v64, 0) )
      {
        v39 = v64;
        *(_QWORD *)v62 = v64;
      }
      else
      {
        v39 = *(_QWORD *)v62;
      }
      if ( v39 == 0x8000000000000000uLL )
      {
        v39 = 0;
        *(_QWORD *)v62 = 0;
      }
      if ( *(&g_AutoSRConfig + 6) )
      {
        DebugPrint(
          "Package preference data: Version %d.%d.%d, Model ID %d, Revision %d",
          v39 & 0xF,
          (unsigned __int8)((unsigned int)v39 >> 4),
          (unsigned __int8)((unsigned int)v39 >> 12),
          (unsigned __int8)((unsigned int)v39 >> 20),
          (unsigned int)v39 >> 28);
        v39 = *(_QWORD *)v62;
      }
      if ( !MODEL_PACKAGE_PREFERENCE::IsPackageVersionSatisfied(
              (MODEL_PACKAGE_PREFERENCE *)v62,
              *((_WORD *)this + 23),
              *((_WORD *)this + 22),
              *((_WORD *)this + 21)) )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x24E,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
          (const char *)0x887A0004LL,
          (int)"Model package version requirement not satisfied",
          v60);
        v11 = -2005270524;
        goto LABEL_72;
      }
      memset_0(&v66, 0, 0xC8u);
      v41 = 0;
      v42 = v78;
      v43 = v77.m128i_u32[1];
      v44 = v77;
      v45 = v76;
      v46 = v75;
      v47 = v74;
      v48 = v73;
      v49 = v72;
      v50 = v71;
      v51 = v70;
      v52 = v69;
      v53 = v68;
      v54 = v67;
      v64 = v67;
      v55 = v66;
      *(struct _GUID *)&v65[1] = v66;
      while ( v41 < v36 )
      {
        v56 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _GUID *))(*(_QWORD *)v63 + 40LL))(v63, v41, &v79);
        v11 = v56;
        if ( v56 < 0 )
        {
          v32 = (unsigned int)v56;
          v33 = 598;
          goto LABEL_40;
        }
        if ( *(&g_AutoSRConfig + 6) )
          DebugPrint(
            "Enumerated variant %d: ID %d, Revision %d, OptimalTargetSize (%d, %d)",
            v41,
            (char)v79.Data4[7],
            v90.m128i_i32[1],
            v91,
            HIDWORD(v91));
        IsModelVersionSatisfied = MODEL_PACKAGE_PREFERENCE::IsModelVersionSatisfied(
                                    (MODEL_PACKAGE_PREFERENCE *)v62,
                                    &v79,
                                    &v90.m128i_u32[1]);
        v39 = *(_QWORD *)v62;
        if ( !IsModelVersionSatisfied )
          goto LABEL_68;
        if ( (v62[0] & 0xF0000000) != 0 )
        {
          v55 = v79;
          v54 = v80;
          v53 = v81;
          v52 = v82;
          v51 = v83;
          v50 = v84;
          v49 = v85;
          v48 = v86;
          v47 = v87;
          v46 = v88;
          v45 = v89;
          v44 = v90;
          v42 = v91;
LABEL_71:
          *(struct _GUID *)a4 = v55;
          *((_OWORD *)a4 + 1) = v54;
          *((_OWORD *)a4 + 2) = v53;
          *((_OWORD *)a4 + 3) = v52;
          *((_OWORD *)a4 + 4) = v51;
          *((_OWORD *)a4 + 5) = v50;
          *((_OWORD *)a4 + 6) = v49;
          *((_OWORD *)a4 + 7) = v48;
          *((_OWORD *)a4 + 8) = v47;
          *((_OWORD *)a4 + 9) = v46;
          *((_OWORD *)a4 + 10) = v45;
          *((__m128i *)a4 + 11) = v44;
          *((_QWORD *)a4 + 24) = v42;
          v11 = 0;
          goto LABEL_72;
        }
        if ( v90.m128i_i32[1] > v43 )
        {
          v7 = 1;
          v55 = v79;
          *(struct _GUID *)&v65[1] = v79;
          v54 = v80;
          v64 = v80;
          v53 = v81;
          v52 = v82;
          v51 = v83;
          v50 = v84;
          v49 = v85;
          v48 = v86;
          v47 = v87;
          v46 = v88;
          v45 = v89;
          v44 = v90;
          v42 = v91;
          v43 = _mm_cvtsi128_si32(_mm_srli_si128(v90, 4));
        }
        else
        {
LABEL_68:
          v55 = *(struct _GUID *)&v65[1];
          v54 = v64;
        }
        ++v41;
      }
      if ( v7 )
        goto LABEL_71;
      if ( *(&g_AutoSRConfig + 6) )
        DebugPrint("No matching variant found, preference raw data %lld", v39);
      CModule::RecordJournalImpl(v40, -2147467259, "No matching variant found");
      v11 = -2147467259;
      v33 = 628;
    }
    else
    {
      if ( *(&g_AutoSRConfig + 6) )
        DebugPrint("No DSR variants available");
      CModule::RecordJournalImpl(v35, -2147023728, "No DSR variants available");
      v11 = -2147023728;
      v33 = 555;
    }
    v32 = v11;
    goto LABEL_40;
  }
  v8 = *((_QWORD *)this + 10);
  v9 = *((_QWORD *)this + 9);
  v10 = 0x4EC4EC4EC4EC4EC5LL * ((v8 - v9) >> 4);
  if ( !v10 )
  {
    v11 = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1D9,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)0x80004005LL,
      (int)"No variants available in cache",
      v59);
    return v11;
  }
  v12 = (SREffectRenderPassDx12::CDSRProvider *)((char *)this + 96);
  if ( !MODEL_PACKAGE_PREFERENCE::IsPackageVersionSatisfied(
          (SREffectRenderPassDx12::CDSRProvider *)((char *)this + 96),
          *((_WORD *)this + 23),
          *((_WORD *)this + 22),
          *((_WORD *)this + 21)) )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)0x887A0004LL,
      (int)"Model package version requirement not satisfied",
      v59);
    return 2289696772LL;
  }
  v14 = *(&g_AutoSRConfig + 13);
  if ( *(&g_AutoSRConfig + 13) == 0xFF || *(&g_AutoSRConfig + 13) >= v10 )
  {
    v61 = 0;
    memset_0(&v79, 0, 0xC8u);
    v16 = 0;
    v17 = v91;
    v18 = v90.m128i_u32[1];
    v19 = v90;
    v20 = v89;
    v21 = v88;
    v22 = v87;
    v23 = v86;
    v24 = v85;
    v25 = v84;
    v26 = v83;
    *(_OWORD *)v62 = v82;
    v63 = v81;
    v27 = v80;
    v28 = v79;
    while ( v9 != v8 )
    {
      if ( *(_DWORD *)(v9 + 188) == (*(_DWORD *)(v64 + 12) & 1) )
      {
        v29 = *(_DWORD *)(v64 + 4);
        if ( v29 < *(_DWORD *)(v9 + 200) || v29 > *(_DWORD *)(v9 + 204) )
        {
          v16 = -2005270524;
        }
        else if ( MODEL_PACKAGE_PREFERENCE::IsModelVersionSatisfied(
                    v12,
                    (const struct _GUID *)v9,
                    (const unsigned int *)(v9 + 180)) )
        {
          if ( *(_DWORD *)v12 >= 0x10000000u )
          {
            v28 = *(struct _GUID *)v9;
            v79 = *(struct _GUID *)v9;
            v27 = *(_OWORD *)(v9 + 16);
            v63 = *(_OWORD *)(v9 + 32);
            *(_OWORD *)v62 = *(_OWORD *)(v9 + 48);
            v26 = *(_OWORD *)(v9 + 64);
            v25 = *(_OWORD *)(v9 + 80);
            v24 = *(_OWORD *)(v9 + 96);
            v23 = *(_OWORD *)(v9 + 112);
            v22 = *(_OWORD *)(v9 + 128);
            v21 = *(_OWORD *)(v9 + 144);
            v20 = *(_OWORD *)(v9 + 160);
            v19 = *(__m128i *)(v9 + 176);
            v17 = *(_QWORD *)(v9 + 192);
            v91 = v17;
            v18 = _mm_cvtsi128_si32(_mm_srli_si128(v19, 4));
LABEL_23:
            if ( *(&g_AutoSRConfig + 6) )
              DebugPrint(
                "Selected variant: ID %d, Revision %d, OptimalTargetSize (%d, %d)",
                (char)v79.Data4[7],
                v18,
                v17,
                HIDWORD(v91));
            *(struct _GUID *)a4 = v28;
            *((_OWORD *)a4 + 1) = v27;
            *((_OWORD *)a4 + 2) = v63;
            *((_OWORD *)a4 + 3) = *(_OWORD *)v62;
            *((_OWORD *)a4 + 4) = v26;
            *((_OWORD *)a4 + 5) = v25;
            *((_OWORD *)a4 + 6) = v24;
            *((_OWORD *)a4 + 7) = v23;
            *((_OWORD *)a4 + 8) = v22;
            *((_OWORD *)a4 + 9) = v21;
            *((_OWORD *)a4 + 10) = v20;
            *((__m128i *)a4 + 11) = v19;
            *((_QWORD *)a4 + 24) = v17;
            return 0;
          }
          if ( *v30 > v18 )
          {
            v61 = 1;
            v28 = *(struct _GUID *)v9;
            v79 = *(struct _GUID *)v9;
            v27 = *(_OWORD *)(v9 + 16);
            v63 = *(_OWORD *)(v9 + 32);
            *(_OWORD *)v62 = *(_OWORD *)(v9 + 48);
            v26 = *(_OWORD *)(v9 + 64);
            v25 = *(_OWORD *)(v9 + 80);
            v24 = *(_OWORD *)(v9 + 96);
            v23 = *(_OWORD *)(v9 + 112);
            v22 = *(_OWORD *)(v9 + 128);
            v21 = *(_OWORD *)(v9 + 144);
            v20 = *(_OWORD *)(v9 + 160);
            v19 = *(__m128i *)(v9 + 176);
            v17 = *(_QWORD *)(v9 + 192);
            v91 = v17;
            v18 = _mm_cvtsi128_si32(_mm_srli_si128(v19, 4));
          }
        }
      }
      else
      {
        v16 = -2147022875;
      }
      v9 += 208;
    }
    if ( v61 )
      goto LABEL_23;
    v11 = -2147023728;
    if ( v16 )
      v11 = v16;
    if ( *(&g_AutoSRConfig + 6) )
      DebugPrint("No matching variant found, preference raw data %lld", *(_QWORD *)v12);
    CModule::RecordJournalImpl(v15, v11, "No matching variant found");
    if ( (v11 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x216,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
        (const char *)v11,
        (int)v58);
    return v11;
  }
  *(_OWORD *)a4 = *(_OWORD *)(208LL * *(&g_AutoSRConfig + 13) + v9);
  *((_OWORD *)a4 + 1) = *(_OWORD *)(208LL * v14 + v9 + 16);
  *((_OWORD *)a4 + 2) = *(_OWORD *)(208LL * v14 + v9 + 32);
  *((_OWORD *)a4 + 3) = *(_OWORD *)(208LL * v14 + v9 + 48);
  *((_OWORD *)a4 + 4) = *(_OWORD *)(208LL * v14 + v9 + 64);
  *((_OWORD *)a4 + 5) = *(_OWORD *)(208LL * v14 + v9 + 80);
  *((_OWORD *)a4 + 6) = *(_OWORD *)(208LL * v14 + v9 + 96);
  *((_OWORD *)a4 + 7) = *(_OWORD *)(208LL * v14 + v9 + 112);
  *((_OWORD *)a4 + 8) = *(_OWORD *)(208LL * v14 + v9 + 128);
  *((_OWORD *)a4 + 9) = *(_OWORD *)(208LL * v14 + v9 + 144);
  *((_OWORD *)a4 + 10) = *(_OWORD *)(208LL * v14 + v9 + 160);
  *((_OWORD *)a4 + 11) = *(_OWORD *)(208LL * v14 + v9 + 176);
  *((_QWORD *)a4 + 24) = *(_QWORD *)(208LL * v14 + v9 + 192);
  return 0;
}

```

## disassembly

```asm
0x1800b9c60  mov     rax, rsp
0x1800b9c63  mov     [rax+18h], rbx
0x1800b9c67  push    rbp
0x1800b9c68  push    rsi
0x1800b9c69  push    rdi
0x1800b9c6a  push    r12
0x1800b9c6c  push    r13
0x1800b9c6e  push    r14
0x1800b9c70  push    r15
0x1800b9c72  lea     rbp, [rax-208h]
0x1800b9c79  sub     rsp, 2D0h
0x1800b9c80  movaps  xmmword ptr [rax-48h], xmm6
0x1800b9c84  movaps  xmmword ptr [rax-58h], xmm7
0x1800b9c88  movaps  xmmword ptr [rax-68h], xmm8
0x1800b9c8d  movaps  xmmword ptr [rax-78h], xmm9
0x1800b9c92  movaps  xmmword ptr [rax-88h], xmm10
0x1800b9c9a  movaps  xmmword ptr [rax-98h], xmm11
0x1800b9ca2  movaps  xmmword ptr [rax-0A8h], xmm12
0x1800b9caa  movaps  xmmword ptr [rax-0B8h], xmm13
0x1800b9cb2  movaps  xmmword ptr [rax-0C8h], xmm14
0x1800b9cba  movaps  xmmword ptr [rax-0D8h], xmm15
0x1800b9cc2  mov     rax, cs:__security_cookie
0x1800b9cc9  xor     rax, rsp
0x1800b9ccc  mov     [rbp+200h+var_E0], rax
0x1800b9cd3  mov     rdi, r9
0x1800b9cd6  mov     qword ptr [rsp+300h+var_2B0+8], r8
0x1800b9cdb  mov     r14, rdx
0x1800b9cde  mov     rsi, rcx
0x1800b9ce1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x1800b9ce8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x1800b9ced  xor     r12d, r12d
0x1800b9cf0  test    al, al
0x1800b9cf2  jz      loc_1800BA12C
0x1800b9cf8  mov     r13, [rsi+50h]
0x1800b9cfc  mov     rbx, [rsi+48h]
0x1800b9d00  mov     r14, r13
0x1800b9d03  sub     r14, rbx
0x1800b9d06  sar     r14, 4
0x1800b9d0a  mov     rax, 4EC4EC4EC4EC4EC5h
0x1800b9d14  imul    r14, rax
0x1800b9d18  test    r14, r14
0x1800b9d1b  jnz     short loc_1800B9D4E
0x1800b9d1d  mov     rcx, [rbp+208h]; this
0x1800b9d24  lea     rax, aNoVariantsAvai; "No variants available in cache"
0x1800b9d2b  mov     qword ptr [rsp+300h+var_2E0], rax; int
0x1800b9d30  mov     ebx, 80004005h
0x1800b9d35  mov     r9d, ebx; char *
0x1800b9d38  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b9d3f  mov     edx, 1D9h; void *
0x1800b9d44  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800b9d49  jmp     loc_1800BA61C
0x1800b9d4e  lea     r12, [rsi+60h]
0x1800b9d52  movzx   r9d, word ptr [rsi+2Ah]; unsigned __int16
0x1800b9d57  movzx   r8d, word ptr [rsi+2Ch]; unsigned __int16
0x1800b9d5c  movzx   edx, word ptr [rsi+2Eh]; unsigned __int16
0x1800b9d60  mov     rcx, r12; this
0x1800b9d63  call    ?IsPackageVersionSatisfied@MODEL_PACKAGE_PREFERENCE@@QEAA_NGGG@Z; MODEL_PACKAGE_PREFERENCE::IsPackageVersionSatisfied(ushort,ushort,ushort)
0x1800b9d68  test    al, al
0x1800b9d6a  jnz     short loc_1800B9DA0
0x1800b9d6c  mov     rcx, [rbp+208h]; this
0x1800b9d73  lea     rax, aModelPackageVe; "Model package version requirement not s"...
0x1800b9d7a  mov     qword ptr [rsp+300h+var_2E0], rax; int
0x1800b9d7f  mov     r9d, 887A0004h; char *
0x1800b9d85  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b9d8c  mov     edx, 1DDh; void *
0x1800b9d91  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800b9d96  mov     eax, 887A0004h
0x1800b9d9b  jmp     loc_1800BA61E
0x1800b9da0  movzx   eax, byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+0Dh; AutoSRConfig g_AutoSRConfig
0x1800b9da7  cmp     al, 0FFh
0x1800b9da9  jz      loc_1800B9E59
0x1800b9daf  mov     ecx, eax
0x1800b9db1  cmp     rax, r14
0x1800b9db4  jnb     loc_1800B9E59
0x1800b9dba  imul    rax, rcx, 0D0h
0x1800b9dc1  movups  xmm0, xmmword ptr [rax+rbx]
0x1800b9dc5  movups  xmmword ptr [rdi], xmm0
0x1800b9dc8  movups  xmm1, xmmword ptr [rax+rbx+10h]
0x1800b9dcd  movups  xmmword ptr [rdi+10h], xmm1
0x1800b9dd1  movups  xmm0, xmmword ptr [rax+rbx+20h]
0x1800b9dd6  movups  xmmword ptr [rdi+20h], xmm0
0x1800b9dda  movups  xmm1, xmmword ptr [rax+rbx+30h]
0x1800b9ddf  movups  xmmword ptr [rdi+30h], xmm1
0x1800b9de3  movups  xmm0, xmmword ptr [rax+rbx+40h]
0x1800b9de8  movups  xmmword ptr [rdi+40h], xmm0
0x1800b9dec  movups  xmm1, xmmword ptr [rax+rbx+50h]
0x1800b9df1  movups  xmmword ptr [rdi+50h], xmm1
0x1800b9df5  movups  xmm0, xmmword ptr [rax+rbx+60h]
0x1800b9dfa  movups  xmmword ptr [rdi+60h], xmm0
0x1800b9dfe  movups  xmm1, xmmword ptr [rax+rbx+70h]
0x1800b9e03  movups  xmmword ptr [rdi+70h], xmm1
0x1800b9e07  movups  xmm0, xmmword ptr [rax+rbx+80h]
0x1800b9e0f  movups  xmmword ptr [rdi+80h], xmm0
0x1800b9e16  movups  xmm1, xmmword ptr [rax+rbx+90h]
0x1800b9e1e  movups  xmmword ptr [rdi+90h], xmm1
0x1800b9e25  movups  xmm0, xmmword ptr [rax+rbx+0A0h]
0x1800b9e2d  movups  xmmword ptr [rdi+0A0h], xmm0
0x1800b9e34  movups  xmm1, xmmword ptr [rax+rbx+0B0h]
0x1800b9e3c  movups  xmmword ptr [rdi+0B0h], xmm1
0x1800b9e43  mov     rax, [rax+rbx+0C0h]
0x1800b9e4b  mov     [rdi+0C0h], rax
0x1800b9e52  xor     eax, eax
0x1800b9e54  jmp     loc_1800BA61E
0x1800b9e59  xor     al, al
0x1800b9e5b  mov     byte ptr [rsp+300h+var_2D0], al
0x1800b9e5f  xor     edx, edx; Val
0x1800b9e61  mov     r8d, 0C8h; Size
0x1800b9e67  lea     rcx, [rbp+200h+var_1B0]; void *
0x1800b9e6b  call    memset_0
0x1800b9e70  xor     r10d, r10d
0x1800b9e73  mov     rsi, [rbp+200h+var_F0]
0x1800b9e7a  mov     r11d, [rbp+200h+var_FC]
0x1800b9e81  movaps  xmm6, xmmword ptr [rbp+100h]
0x1800b9e88  movaps  xmm9, [rbp+200h+var_110]
0x1800b9e90  movaps  xmm10, [rbp+200h+var_120]
0x1800b9e98  movaps  xmm11, [rbp+200h+var_130]
0x1800b9ea0  movaps  xmm12, [rbp+200h+var_140]
0x1800b9ea8  movaps  xmm13, [rbp+200h+var_150]
0x1800b9eb0  movaps  xmm14, [rbp+200h+var_160]
0x1800b9eb8  movaps  xmm15, [rbp+200h+var_170]
0x1800b9ec0  movaps  xmm1, [rbp+200h+var_180]
0x1800b9ec7  movups  xmmword ptr [rsp+300h+var_2D0+8], xmm1
0x1800b9ecc  movaps  xmm1, [rbp+200h+var_190]
0x1800b9ed0  movups  [rsp+300h+var_2C0+8], xmm1
0x1800b9ed5  movaps  xmm7, [rbp+200h+var_1A0]
0x1800b9ed9  movaps  xmm8, xmmword ptr [rbp+200h+var_1B0.Data1]
0x1800b9ede  mov     r14, qword ptr [rsp+300h+var_2B0+8]
0x1800b9ee3  cmp     rbx, r13
0x1800b9ee6  jz      loc_1800BA0C6
0x1800b9eec  mov     eax, [r14+0Ch]
0x1800b9ef0  and     eax, 1
0x1800b9ef3  cmp     [rbx+0BCh], eax
0x1800b9ef9  jz      short loc_1800B9F06
0x1800b9efb  mov     r10d, 800707E5h
0x1800b9f01  jmp     loc_1800B9FCA
0x1800b9f06  mov     eax, [r14+4]
0x1800b9f0a  cmp     eax, [rbx+0C8h]
0x1800b9f10  jb      loc_1800B9FC4
0x1800b9f16  cmp     eax, [rbx+0CCh]
0x1800b9f1c  ja      loc_1800B9FC4
0x1800b9f22  lea     r8, [rbx+0B4h]; unsigned int *
0x1800b9f29  mov     rdx, rbx; struct _GUID *
0x1800b9f2c  mov     rcx, r12; this
0x1800b9f2f  call    ?IsModelVersionSatisfied@MODEL_PACKAGE_PREFERENCE@@QEAA_NAEBU_GUID@@AEBI@Z; MODEL_PACKAGE_PREFERENCE::IsModelVersionSatisfied(_GUID const &,uint const &)
0x1800b9f34  test    al, al
0x1800b9f36  jz      loc_1800B9FCA
0x1800b9f3c  cmp     dword ptr [r12], 10000000h
0x1800b9f44  jnb     loc_1800B9FD6
0x1800b9f4a  cmp     [r8], r11d
0x1800b9f4d  jbe     short loc_1800B9FCA
0x1800b9f4f  mov     byte ptr [rsp+300h+var_2D0], 1
0x1800b9f54  movups  xmm8, xmmword ptr [rbx]
0x1800b9f58  movaps  xmmword ptr [rbp+200h+var_1B0.Data1], xmm8
0x1800b9f5d  movups  xmm7, xmmword ptr [rbx+10h]
0x1800b9f61  movups  xmm0, xmmword ptr [rbx+20h]
0x1800b9f65  movups  [rsp+300h+var_2C0+8], xmm0
0x1800b9f6a  movups  xmm0, xmmword ptr [rbx+30h]
0x1800b9f6e  movups  xmmword ptr [rsp+300h+var_2D0+8], xmm0
0x1800b9f73  movups  xmm15, xmmword ptr [rbx+40h]
0x1800b9f78  movups  xmm14, xmmword ptr [rbx+50h]
0x1800b9f7d  movups  xmm13, xmmword ptr [rbx+60h]
0x1800b9f82  movups  xmm12, xmmword ptr [rbx+70h]
0x1800b9f87  movups  xmm11, xmmword ptr [rbx+80h]
0x1800b9f8f  movups  xmm10, xmmword ptr [rbx+90h]
0x1800b9f97  movups  xmm9, xmmword ptr [rbx+0A0h]
0x1800b9f9f  movups  xmm6, xmmword ptr [rbx+0B0h]
0x1800b9fa6  mov     rsi, [rbx+0C0h]
0x1800b9fad  mov     [rbp+200h+var_F0], rsi
0x1800b9fb4  movdqa  xmm0, xmm6
0x1800b9fb8  psrldq  xmm0, 4
0x1800b9fbd  movd    r11d, xmm0
0x1800b9fc2  jmp     short loc_1800B9FCA
0x1800b9fc4  mov     r10d, 887A0004h
0x1800b9fca  add     rbx, 0D0h
0x1800b9fd1  jmp     loc_1800B9EE3
0x1800b9fd6  movups  xmm8, xmmword ptr [rbx]
0x1800b9fda  movaps  xmmword ptr [rbp+200h+var_1B0.Data1], xmm8
0x1800b9fdf  movups  xmm7, xmmword ptr [rbx+10h]
0x1800b9fe3  movups  xmm0, xmmword ptr [rbx+20h]
0x1800b9fe7  movups  [rsp+300h+var_2C0+8], xmm0
0x1800b9fec  movups  xmm0, xmmword ptr [rbx+30h]
0x1800b9ff0  movups  xmmword ptr [rsp+300h+var_2D0+8], xmm0
0x1800b9ff5  movups  xmm15, xmmword ptr [rbx+40h]
0x1800b9ffa  movups  xmm14, xmmword ptr [rbx+50h]
0x1800b9fff  movups  xmm13, xmmword ptr [rbx+60h]
0x1800ba004  movups  xmm12, xmmword ptr [rbx+70h]
0x1800ba009  movups  xmm11, xmmword ptr [rbx+80h]
0x1800ba011  movups  xmm10, xmmword ptr [rbx+90h]
0x1800ba019  movups  xmm9, xmmword ptr [rbx+0A0h]
0x1800ba021  movups  xmm6, xmmword ptr [rbx+0B0h]
0x1800ba028  mov     rsi, [rbx+0C0h]
0x1800ba02f  mov     [rbp+200h+var_F0], rsi
0x1800ba036  movdqa  xmm0, xmm6
0x1800ba03a  psrldq  xmm0, 4
0x1800ba03f  movd    r11d, xmm0
0x1800ba044  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, 0; AutoSRConfig g_AutoSRConfig
0x1800ba04b  jz      short loc_1800BA06D
0x1800ba04d  movsx   edx, [rbp+200h+var_1B0.Data4+7]
0x1800ba051  mov     eax, dword ptr [rbp+200h+var_F0+4]
0x1800ba057  mov     [rsp+300h+var_2E0], eax
0x1800ba05b  mov     r9d, esi
0x1800ba05e  mov     r8d, r11d
0x1800ba061  lea     rcx, aSelectedVarian; "Selected variant: ID %d, Revision %d, O"...
0x1800ba068  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800ba06d  movups  xmmword ptr [rdi], xmm8
0x1800ba071  movups  xmmword ptr [rdi+10h], xmm7
0x1800ba075  movups  xmm0, [rsp+300h+var_2C0+8]
0x1800ba07a  movups  xmmword ptr [rdi+20h], xmm0
0x1800ba07e  movups  xmm0, xmmword ptr [rsp+300h+var_2D0+8]
0x1800ba083  movups  xmmword ptr [rdi+30h], xmm0
0x1800ba087  movups  xmmword ptr [rdi+40h], xmm15
0x1800ba08c  movups  xmmword ptr [rdi+50h], xmm14
0x1800ba091  movups  xmmword ptr [rdi+60h], xmm13
0x1800ba096  movups  xmmword ptr [rdi+70h], xmm12
0x1800ba09b  movups  xmmword ptr [rdi+80h], xmm11
0x1800ba0a3  movups  xmmword ptr [rdi+90h], xmm10
0x1800ba0ab  movups  xmmword ptr [rdi+0A0h], xmm9
0x1800ba0b3  movups  xmmword ptr [rdi+0B0h], xmm6
0x1800ba0ba  mov     [rdi+0C0h], rsi
0x1800ba0c1  jmp     loc_1800B9E52
0x1800ba0c6  cmp     byte ptr [rsp+300h+var_2D0], 0
0x1800ba0cb  jnz     loc_1800BA044
0x1800ba0d1  mov     ebx, 80070490h
0x1800ba0d6  test    r10d, r10d
0x1800ba0d9  cmovnz  ebx, r10d
0x1800ba0dd  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, 0; AutoSRConfig g_AutoSRConfig
0x1800ba0e4  jz      short loc_1800BA0F6
0x1800ba0e6  mov     rdx, [r12]
0x1800ba0ea  lea     rcx, aNoMatchingVari; "No matching variant found, preference r"...
0x1800ba0f1  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800ba0f6  lea     r8, aNoMatchingVari_0; "No matching variant found"
0x1800ba0fd  mov     edx, ebx; unsigned int
0x1800ba0ff  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800ba104  test    ebx, ebx
0x1800ba106  jns     loc_1800BA61C
0x1800ba10c  mov     rcx, [rbp+208h]; this
0x1800ba113  mov     r9d, ebx; char *
0x1800ba116  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800ba11d  mov     edx, 216h; void *
0x1800ba122  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba127  jmp     loc_1800BA61C
0x1800ba12c  mov     qword ptr [rsp+300h+var_2C0+8], r12
0x1800ba131  mov     rax, [r14]
0x1800ba134  lea     r8, [rsp+300h+var_2C0+8]
0x1800ba139  lea     rdx, _GUID_6069f18a_2f9c_4e9c_afec_6a419387d914
0x1800ba140  mov     rcx, r14
0x1800ba143  mov     rax, [rax]
0x1800ba146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba14b  mov     ebx, eax
0x1800ba14d  test    eax, eax
0x1800ba14f  jns     short loc_1800BA15B
0x1800ba151  mov     r9d, eax
0x1800ba154  mov     edx, 221h
0x1800ba159  jmp     short loc_1800BA1A4
0x1800ba15b  mov     rax, [r14]
0x1800ba15e  mov     rcx, r14
0x1800ba161  mov     rax, [rax+18h]
0x1800ba165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba16a  mov     r14d, eax
0x1800ba16d  test    eax, eax
0x1800ba16f  jnz     short loc_1800BA1BC
0x1800ba171  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, r12b; AutoSRConfig g_AutoSRConfig
0x1800ba178  jz      short loc_1800BA186
0x1800ba17a  lea     rcx, aNoDsrVariantsA; "No DSR variants available"
0x1800ba181  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800ba186  lea     r8, aNoDsrVariantsA; "No DSR variants available"
0x1800ba18d  mov     edx, 80070490h; unsigned int
0x1800ba192  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800ba197  mov     ebx, 80070490h
0x1800ba19c  mov     edx, 22Bh; void *
0x1800ba1a1  mov     r9d, ebx; char *
0x1800ba1a4  mov     rcx, [rbp+208h]; this
0x1800ba1ab  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800ba1b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba1b7  jmp     loc_1800BA612
0x1800ba1bc  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, r12b; AutoSRConfig g_AutoSRConfig
0x1800ba1c3  jz      short loc_1800BA1D4
0x1800ba1c5  mov     edx, r14d
0x1800ba1c8  lea     rcx, aDDsrVariantsFo; "%d DSR variants found"
0x1800ba1cf  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x1800ba1d4  mov     r15d, 0C8h
0x1800ba1da  mov     r8d, r15d; Size
0x1800ba1dd  xor     edx, edx; Val
0x1800ba1df  lea     rcx, [rbp+200h+var_1B0]; void *
0x1800ba1e3  call    memset_0
0x1800ba1e8  movzx   eax, byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+0Dh; AutoSRConfig g_AutoSRConfig
0x1800ba1ef  cmp     al, 0FFh
0x1800ba1f1  jz      loc_1800BA2C6
0x1800ba1f7  mov     edx, eax
0x1800ba1f9  cmp     eax, r14d
0x1800ba1fc  jnb     loc_1800BA2C6
0x1800ba202  mov     rcx, qword ptr [rsp+300h+var_2C0+8]
0x1800ba207  mov     rax, [rcx]
0x1800ba20a  lea     r8, [rbp+200h+var_1B0]
0x1800ba20e  mov     rax, [rax+28h]
0x1800ba212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba217  mov     ebx, eax
0x1800ba219  test    eax, eax
0x1800ba21b  jns     short loc_1800BA22A
0x1800ba21d  mov     r9d, eax
  ... truncated ...
```
