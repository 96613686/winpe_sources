# ColorFiltering::ColorFilterHelper::UpdateActiveFilter(void)

- ea: `0x1400237b8`
- end: `0x140023e97`
- name: `?UpdateActiveFilter@ColorFilterHelper@ColorFiltering@@SAXXZ`
- size: `1759`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140020938`

## callees

- `0x140002de3`
- `0x140005c90`
- `0x140007e90`
- `0x140017644`
- `0x14002219c`
- `0x140022584`
- `0x1400227c0`
- `0x14002328c`
- `0x1400237b8`
- `0x140023ff8`
- `0x140024154`
- `0x1400242b0`
- `0x14002440c`
- `0x14002443c`
- `0x140025d70`

## import_xrefs

- `USER32!SetDesktopColorTransform` at `0x140023e5e`
- `USER32!SetDesktopColorTransform` at `0x140023e5e`
- `mscms!__imp_?InternalSetAccessibilityColorMatrix@@YAJAEAY144M@Z` at `0x140023e50`
- `mscms!__imp_?InternalSetAccessibilityColorMatrix@@YAJAEAY144M@Z` at `0x140023e50`

## string_xrefs

- `0x140023829`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
void ColorFiltering::ColorFilterHelper::UpdateActiveFilter(void)
{
  char v0; // si
  char v1; // bl
  char v2; // di
  __int64 v3; // rdx
  float v4; // eax
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  const struct _MAGN_COLOR_TRANSFORM *v7; // rcx
  __int64 *v8; // r9
  __int64 *v9; // r8
  __int128 v10; // xmm1
  __int64 *v11; // rax
  __int64 *v12; // [rsp+28h] [rbp-D8h]
  __int64 *v13; // [rsp+30h] [rbp-D0h]
  __int64 *v14; // [rsp+38h] [rbp-C8h]
  __int64 *v15; // [rsp+40h] [rbp-C0h]
  __int64 *v16; // [rsp+48h] [rbp-B8h]
  __int64 *v17; // [rsp+50h] [rbp-B0h]
  __int64 *v18; // [rsp+58h] [rbp-A8h]
  ColorFiltering::Filters *v19; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h]
  __int64 v23; // [rsp+80h] [rbp-80h]
  _QWORD v24[3]; // [rsp+88h] [rbp-78h] BYREF
  __m256i v25; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v26; // [rsp+C0h] [rbp-40h]
  __m128i si128; // [rsp+D0h] [rbp-30h]
  __int128 v28; // [rsp+E0h] [rbp-20h]
  __int128 v29; // [rsp+F0h] [rbp-10h]
  int v30; // [rsp+100h] [rbp+0h]
  float v31[5][5]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v32; // [rsp+180h] [rbp+80h] BYREF
  __int128 v33; // [rsp+190h] [rbp+90h]
  __int128 v34; // [rsp+1A0h] [rbp+A0h]
  __int128 v35; // [rsp+1B0h] [rbp+B0h]
  __int128 v36; // [rsp+1C0h] [rbp+C0h]
  __int128 v37; // [rsp+1D0h] [rbp+D0h]
  int v38; // [rsp+1E0h] [rbp+E0h]
  __int128 v39; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v40; // [rsp+200h] [rbp+100h]
  __int128 v41; // [rsp+210h] [rbp+110h]
  __int128 v42; // [rsp+220h] [rbp+120h]
  __int128 v43; // [rsp+230h] [rbp+130h]
  __int128 v44; // [rsp+240h] [rbp+140h]
  int v45; // [rsp+250h] [rbp+150h]

  v20 = -1;
  v19 = (ColorFiltering::Filters *)0x6400000046LL;
  if ( ColorFiltering::ColorFilterHelper::IsActive() )
  {
    memset(v24, 0, sizeof(v24));
    v0 = 1;
    v1 = 1;
    if ( (unsigned int)ATL::CRegKey::Open(
                         (ATL::CRegKey *)v24,
                         HKEY_CURRENT_USER,
                         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\colorfiltering",
                         1u) )
      goto LABEL_22;
    if ( (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v24, L"FilterType", &v20) )
    {
      v21 = 0;
      v22 = 0;
      v23 = 0;
      v2 = 1;
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)&v21,
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\ColorFiltering",
                            1u)
        && !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v21, L"FilterType", &v20) )
      {
        v2 = 0;
        ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(v20);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)&v21);
    }
    else
    {
      v2 = 0;
    }
    if ( (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v24, L"Intensity", (unsigned int *)&v19 + 1) )
    {
      v21 = 0;
      v22 = 0;
      v23 = 0;
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)&v21,
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\ColorFiltering",
                            1u)
        && !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v21, L"Intensity", (unsigned int *)&v19 + 1) )
      {
        v0 = 0;
        ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(SHIDWORD(v19));
      }
      ATL::CRegKey::Close((ATL::CRegKey *)&v21);
    }
    else
    {
      v0 = 0;
    }
    if ( (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v24, L"Gain", (unsigned int *)&v19) )
    {
      v21 = 0;
      v22 = 0;
      v23 = 0;
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)&v21,
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\ColorFiltering",
                            1u)
        && !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v21, L"Gain", (unsigned int *)&v19) )
      {
        v1 = 0;
        ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain((int)v19);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)&v21);
    }
    else
    {
      v1 = 0;
    }
    if ( v2 )
LABEL_22:
      v20 = 0;
    if ( v0 )
      HIDWORD(v19) = 100;
    if ( v1 )
      LODWORD(v19) = 70;
    ATL::CRegKey::Close((ATL::CRegKey *)v24);
  }
  memset_0(v31, 0, sizeof(v31));
  switch ( v20 )
  {
    case 0u:
      v4 = 1.0;
      *(_OWORD *)&v31[0][0] = ColorFiltering::Filters::Greyscale;
      *(_OWORD *)&v31[0][4] = xmmword_14002E1F0;
      *(_OWORD *)&v31[1][3] = xmmword_14002E200;
      v5 = xmmword_14002E220;
      *(_OWORD *)&v31[2][2] = xmmword_14002E210;
      v6 = xmmword_14002E230;
      goto LABEL_43;
    case 1u:
      v4 = 1.0;
      *(_OWORD *)&v31[0][0] = ColorFiltering::Filters::InvertFilter;
      *(_OWORD *)&v31[0][4] = xmmword_14002D770;
      *(_OWORD *)&v31[1][3] = xmmword_14002D780;
      v5 = xmmword_14002D7A0;
      *(_OWORD *)&v31[2][2] = xmmword_14002D790;
      v6 = xmmword_14002D7B0;
      goto LABEL_43;
    case 2u:
      v4 = 1.0;
      *(_OWORD *)&v31[0][0] = ColorFiltering::Filters::GreyscaleInvert;
      *(_OWORD *)&v31[0][4] = xmmword_14002D5B0;
      *(_OWORD *)&v31[1][3] = xmmword_14002D5C0;
      v5 = xmmword_14002D5E0;
      *(_OWORD *)&v31[2][2] = xmmword_14002D5D0;
      v6 = xmmword_14002D5F0;
      goto LABEL_43;
    case 3u:
      v25.m256i_i32[1] = ColorFiltering::Filters::_ConvertToPercent((ColorFiltering::Filters *)(unsigned int)v19, v3);
      v18 = qword_14002D450;
      v8 = qword_14002D990;
      HIDWORD(v26) = v25.m256i_i32[1];
      v17 = qword_14002E100;
      v9 = qword_14002D6F0;
      v25.m256i_i32[0] = 1065353216;
      v16 = qword_14002E170;
      v10 = 0;
      memset(&v25.m256i_u64[1], 0, 24);
      v15 = qword_14002DF40;
      v14 = qword_14002DD10;
      v13 = qword_14002D8B0;
      v12 = qword_14002DC30;
      v11 = qword_14002DFB0;
      DWORD2(v26) = 0;
      goto LABEL_38;
    case 4u:
      v25.m256i_i32[5] = ColorFiltering::Filters::_ConvertToPercent((ColorFiltering::Filters *)(unsigned int)v19, v3);
      v18 = qword_14002DAE0;
      v8 = qword_14002D840;
      *((_QWORD *)&v26 + 1) = v25.m256i_u32[5];
      v17 = qword_14002DE60;
      v9 = qword_14002DA00;
      v16 = qword_14002DD80;
      v10 = 0;
      memset(&v25, 0, 20);
      v15 = qword_14002DCA0;
      v14 = qword_14002D3C0;
      v13 = qword_14002DBC0;
      v12 = qword_14002D530;
      v11 = qword_14002DA70;
      v25.m256i_i64[3] = 1065353216;
LABEL_38:
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v28 = 0;
      v30 = 0;
      v29 = v10;
      *(_QWORD *)&v26 = 0;
      ColorFiltering::Filters::_GetAppearance(&v39, HIDWORD(v19), v9, v8, v11, v12, v13, v14, v15, v16, v17, v18);
      v7 = (const struct _MAGN_COLOR_TRANSFORM *)&v32;
      v38 = v45;
      v32 = v39;
      v33 = v40;
      v34 = v41;
      v35 = v42;
      v36 = v43;
      v37 = v44;
      goto LABEL_39;
    case 5u:
      v25.m256i_i32[2] = ColorFiltering::Filters::_ConvertToPercent((ColorFiltering::Filters *)(unsigned int)v19, v3);
      v25.m256i_i32[7] = v25.m256i_i32[2];
      v25.m256i_i64[0] = 1065353216;
      *(__int64 *)((char *)&v25.m256i_i64[1] + 4) = 0;
      *(__int64 *)((char *)&v25.m256i_i64[2] + 4) = 0x3F80000000000000LL;
      v26 = 0;
      si128 = 0;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      ColorFiltering::Filters::_GetAppearance(
        &v32,
        HIDWORD(v19),
        qword_14002D610,
        qword_14002D4C0,
        qword_14002E020,
        qword_14002D7D0,
        qword_14002E090,
        qword_14002DB50,
        qword_14002D680,
        qword_14002DED0,
        qword_14002D920,
        qword_14002DDF0);
      v7 = (const struct _MAGN_COLOR_TRANSFORM *)&v39;
      v45 = v38;
      v39 = v32;
      v40 = v33;
      v41 = v34;
      v42 = v35;
      v43 = v36;
      v44 = v37;
LABEL_39:
      ColorFiltering::ColorFilterHelper::GenerateAdaptationFilter(
        v7,
        (const struct _MAGN_COLOR_TRANSFORM *)&v25,
        (struct _MAGN_COLOR_TRANSFORM *)v31);
      goto LABEL_44;
  }
  v4 = *(float *)&dword_140036B20;
  *(_OWORD *)&v31[0][0] = ColorFiltering::Filters::PassthroughFilter;
  *(_OWORD *)&v31[0][4] = xmmword_140036AD0;
  *(_OWORD *)&v31[1][3] = xmmword_140036AE0;
  v5 = xmmword_140036B00;
  *(_OWORD *)&v31[2][2] = xmmword_140036AF0;
  v6 = xmmword_140036B10;
LABEL_43:
  v31[4][4] = v4;
  *(_OWORD *)&v31[4][0] = v6;
  *(_OWORD *)&v31[3][1] = v5;
LABEL_44:
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::GetImpl'::`2'::impl,
    v3);
  if ( (int)InternalSetAccessibilityColorMatrix((float (*)[5][5])v31) < 0 )
    SetDesktopColorTransform((float *)v31);
  AccessibilitySettingsTelemetry::ColorFilterWithOptions<unsigned long &,unsigned long &,unsigned long &>(
    &v20,
    (char *)&v19 + 4,
    &v19);
}

```

## disassembly

```asm
0x1400237b8  push    rbp
0x1400237ba  push    rbx
0x1400237bb  push    rsi
0x1400237bc  push    rdi
0x1400237bd  push    r12
0x1400237bf  push    r14
0x1400237c1  lea     rbp, [rsp-178h]
0x1400237c9  sub     rsp, 278h
0x1400237d0  mov     rax, cs:__security_cookie
0x1400237d7  xor     rax, rsp
0x1400237da  mov     [rbp+1A0h+var_40], rax
0x1400237e1  mov     [rsp+2A0h+var_238], 0FFFFFFFFh
0x1400237e9  mov     dword ptr [rsp+2A0h+var_240+4], 64h ; 'd'
0x1400237f1  mov     dword ptr [rsp+2A0h+var_240], 46h ; 'F'
0x1400237f9  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x1400237fe  xor     r14d, r14d
0x140023801  test    al, al
0x140023803  jz      loc_1400239DE
0x140023809  mov     r12, 0FFFFFFFF80000001h
0x140023810  mov     [rbp+1A0h+var_218], r14
0x140023814  mov     sil, 1
0x140023817  mov     [rbp+1A0h+var_210], r14
0x14002381b  mov     rdx, r12; hKey
0x14002381e  mov     [rbp+1A0h+var_208], r14
0x140023822  lea     r9d, [r14+1]; unsigned int
0x140023826  mov     bl, sil
0x140023829  lea     r8, aSoftwareMicros_16; "Software\\Microsoft\\Windows NT\\Curren"...
0x140023830  lea     rcx, [rbp+1A0h+var_218]; this
0x140023834  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140023839  test    eax, eax
0x14002383b  jnz     loc_1400239B7
0x140023841  lea     r8, [rsp+2A0h+var_238]; unsigned int *
0x140023846  lea     rdx, aFiltertype_0; "FilterType"
0x14002384d  lea     rcx, [rbp+1A0h+var_218]; this
0x140023851  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x140023856  test    eax, eax
0x140023858  jnz     short loc_14002385F
0x14002385a  mov     dil, r14b
0x14002385d  jmp     short loc_1400238BE
0x14002385f  mov     r9d, 1; unsigned int
0x140023865  mov     [rsp+2A0h+var_230], r14
0x14002386a  lea     r8, aSoftwareMicros_17; "Software\\Microsoft\\ColorFiltering"
0x140023871  mov     [rsp+2A0h+var_228], r14
0x140023876  mov     rdx, r12; hKey
0x140023879  mov     [rbp+1A0h+var_220], r14
0x14002387d  lea     rcx, [rsp+2A0h+var_230]; this
0x140023882  mov     dil, bl
0x140023885  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14002388a  test    eax, eax
0x14002388c  jnz     short loc_1400238B4
0x14002388e  lea     r8, [rsp+2A0h+var_238]; unsigned int *
0x140023893  lea     rdx, aFiltertype_0; "FilterType"
0x14002389a  lea     rcx, [rsp+2A0h+var_230]; this
0x14002389f  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1400238a4  test    eax, eax
0x1400238a6  jnz     short loc_1400238B4
0x1400238a8  mov     ecx, [rsp+2A0h+var_238]; unsigned int
0x1400238ac  mov     dil, r14b
0x1400238af  call    ?UpdateTransferSettingsFilterType@ColorFilterHelper@ColorFiltering@@SAXK@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(ulong)
0x1400238b4  lea     rcx, [rsp+2A0h+var_230]; this
0x1400238b9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400238be  lea     r8, [rsp+2A0h+var_240+4]; unsigned int *
0x1400238c3  lea     rdx, aIntensity_0; "Intensity"
0x1400238ca  lea     rcx, [rbp+1A0h+var_218]; this
0x1400238ce  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1400238d3  test    eax, eax
0x1400238d5  jnz     short loc_1400238DC
0x1400238d7  mov     sil, r14b
0x1400238da  jmp     short loc_140023938
0x1400238dc  mov     r9d, 1; unsigned int
0x1400238e2  mov     [rsp+2A0h+var_230], r14
0x1400238e7  lea     r8, aSoftwareMicros_17; "Software\\Microsoft\\ColorFiltering"
0x1400238ee  mov     [rsp+2A0h+var_228], r14
0x1400238f3  mov     rdx, r12; hKey
0x1400238f6  mov     [rbp+1A0h+var_220], r14
0x1400238fa  lea     rcx, [rsp+2A0h+var_230]; this
0x1400238ff  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140023904  test    eax, eax
0x140023906  jnz     short loc_14002392E
0x140023908  lea     r8, [rsp+2A0h+var_240+4]; unsigned int *
0x14002390d  lea     rdx, aIntensity_0; "Intensity"
0x140023914  lea     rcx, [rsp+2A0h+var_230]; this
0x140023919  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14002391e  test    eax, eax
0x140023920  jnz     short loc_14002392E
0x140023922  mov     ecx, dword ptr [rsp+2A0h+var_240+4]; unsigned int
0x140023926  mov     sil, r14b
0x140023929  call    ?UpdateTransferSettingsIntensity@ColorFilterHelper@ColorFiltering@@SAXK@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(ulong)
0x14002392e  lea     rcx, [rsp+2A0h+var_230]; this
0x140023933  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140023938  lea     r8, [rsp+2A0h+var_240]; unsigned int *
0x14002393d  lea     rdx, aGain_0; "Gain"
0x140023944  lea     rcx, [rbp+1A0h+var_218]; this
0x140023948  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14002394d  test    eax, eax
0x14002394f  jnz     short loc_140023956
0x140023951  mov     bl, r14b
0x140023954  jmp     short loc_1400239B2
0x140023956  mov     r9d, 1; unsigned int
0x14002395c  mov     [rsp+2A0h+var_230], r14
0x140023961  lea     r8, aSoftwareMicros_17; "Software\\Microsoft\\ColorFiltering"
0x140023968  mov     [rsp+2A0h+var_228], r14
0x14002396d  mov     rdx, r12; hKey
0x140023970  mov     [rbp+1A0h+var_220], r14
0x140023974  lea     rcx, [rsp+2A0h+var_230]; this
0x140023979  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14002397e  test    eax, eax
0x140023980  jnz     short loc_1400239A8
0x140023982  lea     r8, [rsp+2A0h+var_240]; unsigned int *
0x140023987  lea     rdx, aGain_0; "Gain"
0x14002398e  lea     rcx, [rsp+2A0h+var_230]; this
0x140023993  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x140023998  test    eax, eax
0x14002399a  jnz     short loc_1400239A8
0x14002399c  mov     ecx, dword ptr [rsp+2A0h+var_240]; unsigned int
0x1400239a0  mov     bl, r14b
0x1400239a3  call    ?UpdateTransferSettingsGain@ColorFilterHelper@ColorFiltering@@SAXK@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(ulong)
0x1400239a8  lea     rcx, [rsp+2A0h+var_230]; this
0x1400239ad  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400239b2  test    dil, dil
0x1400239b5  jz      short loc_1400239BC
0x1400239b7  mov     [rsp+2A0h+var_238], r14d
0x1400239bc  test    sil, sil
0x1400239bf  jz      short loc_1400239C9
0x1400239c1  mov     dword ptr [rsp+2A0h+var_240+4], 64h ; 'd'
0x1400239c9  test    bl, bl
0x1400239cb  jz      short loc_1400239D5
0x1400239cd  mov     dword ptr [rsp+2A0h+var_240], 46h ; 'F'
0x1400239d5  lea     rcx, [rbp+1A0h+var_218]; this
0x1400239d9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400239de  xor     edx, edx; Val
0x1400239e0  lea     rcx, [rbp+1A0h+var_190]; void *
0x1400239e4  lea     r8d, [rdx+64h]; Size
0x1400239e8  call    memset_0
0x1400239ed  mov     eax, [rsp+2A0h+var_238]
0x1400239f1  test    eax, eax
0x1400239f3  jz      loc_140023DF3
0x1400239f9  cmp     eax, 1
0x1400239fc  jz      loc_140023DB1
0x140023a02  cmp     eax, 2
0x140023a05  jz      loc_140023D6C
0x140023a0b  cmp     eax, 3
0x140023a0e  jz      loc_140023C2D
0x140023a14  cmp     eax, 4
0x140023a17  jz      loc_140023B95
0x140023a1d  cmp     eax, 5
0x140023a20  jz      short loc_140023A67
0x140023a22  movaps  xmm0, cs:?PassthroughFilter@Filters@ColorFiltering@@3U_MAGN_COLOR_TRANSFORM@@A; _MAGN_COLOR_TRANSFORM ColorFiltering::Filters::PassthroughFilter
0x140023a29  movaps  xmm1, cs:xmmword_140036AD0
0x140023a30  mov     eax, cs:dword_140036B20
0x140023a36  movaps  [rbp+1A0h+var_190], xmm0
0x140023a3a  movaps  xmm0, cs:xmmword_140036AE0
0x140023a41  movaps  [rbp+1A0h+var_180], xmm1
0x140023a45  movaps  xmm1, cs:xmmword_140036AF0
0x140023a4c  movaps  [rbp+1A0h+var_170], xmm0
0x140023a50  movaps  xmm0, cs:xmmword_140036B00
0x140023a57  movaps  [rbp+1A0h+var_160], xmm1
0x140023a5b  movaps  xmm1, cs:xmmword_140036B10
0x140023a62  jmp     loc_140023E33
0x140023a67  mov     ecx, dword ptr [rsp+2A0h+var_240]; this
0x140023a6b  call    ?_ConvertToPercent@Filters@ColorFiltering@@YAMK@Z; ColorFiltering::Filters::_ConvertToPercent(ulong)
0x140023a70  mov     edx, dword ptr [rsp+2A0h+var_240+4]
0x140023a74  lea     rax, qword_14002DDF0
0x140023a7b  mov     [rsp+2A0h+var_248], rax
0x140023a80  lea     r9, qword_14002D4C0
0x140023a87  xorps   xmm1, xmm1
0x140023a8a  movss   dword ptr [rbp+1A0h+var_200+8], xmm0
0x140023a8f  lea     rax, qword_14002D920
0x140023a96  movss   dword ptr [rbp+1A0h+var_1E8+4], xmm0
0x140023a9b  mov     [rsp+2A0h+var_250], rax
0x140023aa0  lea     r8, qword_14002D610
0x140023aa7  xorps   xmm0, xmm0
0x140023aaa  mov     qword ptr [rbp+1A0h+var_200], 3F800000h
0x140023ab2  lea     rax, qword_14002DED0
0x140023ab9  mov     qword ptr [rbp+1A0h+var_200+0Ch], r14
0x140023abd  mov     [rsp+2A0h+var_258], rax
0x140023ac2  lea     rcx, [rbp+1A0h+var_120]
0x140023ac9  lea     rax, qword_14002D680
0x140023ad0  mov     [rbp+1A0h+var_1EC], r14d
0x140023ad4  mov     [rsp+2A0h+var_260], rax
0x140023ad9  lea     rax, qword_14002DB50
0x140023ae0  mov     [rsp+2A0h+var_268], rax
0x140023ae5  lea     rax, qword_14002E090
0x140023aec  mov     [rsp+2A0h+var_270], rax
0x140023af1  lea     rax, qword_14002D7D0
0x140023af8  mov     [rsp+2A0h+var_278], rax
0x140023afd  lea     rax, qword_14002E020
0x140023b04  mov     [rsp+2A0h+var_280], rax
0x140023b09  mov     dword ptr [rbp+1A0h+var_1E8], 3F800000h
0x140023b10  movaps  [rbp+1A0h+var_1E0], xmm0
0x140023b14  movaps  [rbp+1A0h+var_1D0], xmm1
0x140023b18  movaps  [rbp+1A0h+var_1C0], xmm0
0x140023b1c  movaps  [rbp+1A0h+var_1B0], xmm1
0x140023b20  mov     [rbp+1A0h+var_1A0], r14d
0x140023b24  call    ?_GetAppearance@Filters@ColorFiltering@@YA?AU_MAGN_COLOR_TRANSFORM@@KAEBU3@000000000@Z; ColorFiltering::Filters::_GetAppearance(ulong,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &)
0x140023b29  movups  xmm0, [rbp+1A0h+var_120]
0x140023b30  mov     eax, [rbp+1A0h+var_C0]
0x140023b36  lea     rcx, [rbp+1A0h+var_B0]
0x140023b3d  movups  xmm1, [rbp+1A0h+var_110]
0x140023b44  mov     [rbp+1A0h+var_50], eax
0x140023b4a  movaps  [rbp+1A0h+var_B0], xmm0
0x140023b51  movups  xmm0, [rbp+1A0h+var_100]
0x140023b58  movaps  [rbp+1A0h+var_A0], xmm1
0x140023b5f  movups  xmm1, [rbp+1A0h+var_F0]
0x140023b66  movaps  [rbp+1A0h+var_90], xmm0
0x140023b6d  movups  xmm0, [rbp+1A0h+var_E0]
0x140023b74  movaps  [rbp+1A0h+var_80], xmm1
0x140023b7b  movups  xmm1, [rbp+1A0h+var_D0]
0x140023b82  movaps  [rbp+1A0h+var_70], xmm0
0x140023b89  movaps  [rbp+1A0h+var_60], xmm1
0x140023b90  jmp     loc_140023D5A
0x140023b95  mov     ecx, dword ptr [rsp+2A0h+var_240]; this
0x140023b99  call    ?_ConvertToPercent@Filters@ColorFiltering@@YAMK@Z; ColorFiltering::Filters::_ConvertToPercent(ulong)
0x140023b9e  lea     rax, qword_14002DAE0
0x140023ba5  movss   [rbp+1A0h+var_1EC], xmm0
0x140023baa  mov     [rsp+2A0h+var_248], rax
0x140023baf  lea     r9, qword_14002D840
0x140023bb6  lea     rax, qword_14002DE60
0x140023bbd  movss   dword ptr [rbp+1A0h+var_1E0+8], xmm0
0x140023bc2  mov     [rsp+2A0h+var_250], rax
0x140023bc7  lea     r8, qword_14002DA00
0x140023bce  lea     rax, qword_14002DD80
0x140023bd5  mov     [rbp-50h], r14d
0x140023bd9  mov     [rsp+2A0h+var_258], rax
0x140023bde  xorps   xmm1, xmm1
0x140023be1  lea     rax, qword_14002DCA0
0x140023be8  movaps  [rbp+1A0h+var_200], xmm1
0x140023bec  mov     [rsp+2A0h+var_260], rax
0x140023bf1  lea     rax, qword_14002D3C0
0x140023bf8  mov     [rsp+2A0h+var_268], rax
0x140023bfd  lea     rax, qword_14002DBC0
0x140023c04  mov     [rsp+2A0h+var_270], rax
0x140023c09  lea     rax, qword_14002D530
0x140023c10  mov     [rsp+2A0h+var_278], rax
0x140023c15  lea     rax, qword_14002DA70
0x140023c1c  mov     [rbp+1A0h+var_1E8], 3F800000h
0x140023c24  mov     dword ptr [rbp+1A0h+var_1E0+0Ch], r14d
0x140023c28  jmp     loc_140023CBF
0x140023c2d  mov     ecx, dword ptr [rsp+2A0h+var_240]; this
0x140023c31  call    ?_ConvertToPercent@Filters@ColorFiltering@@YAMK@Z; ColorFiltering::Filters::_ConvertToPercent(ulong)
0x140023c36  lea     rax, qword_14002D450
0x140023c3d  movss   dword ptr [rbp+1A0h+var_200+4], xmm0
0x140023c42  mov     [rsp+2A0h+var_248], rax
0x140023c47  lea     r9, qword_14002D990
0x140023c4e  lea     rax, qword_14002E100
0x140023c55  movss   dword ptr [rbp+1A0h+var_1E0+0Ch], xmm0
0x140023c5a  mov     [rsp+2A0h+var_250], rax
0x140023c5f  lea     r8, qword_14002D6F0
0x140023c66  lea     rax, qword_14002E170
0x140023c6d  mov     dword ptr [rbp+1A0h+var_200], 3F800000h
0x140023c74  mov     [rsp+2A0h+var_258], rax
0x140023c79  xorps   xmm1, xmm1
0x140023c7c  lea     rax, qword_14002DF40
0x140023c83  mov     qword ptr [rbp+1A0h+var_200+8], r14
0x140023c87  mov     [rsp+2A0h+var_260], rax
0x140023c8c  lea     rax, qword_14002DD10
0x140023c93  mov     [rsp+2A0h+var_268], rax
0x140023c98  lea     rax, qword_14002D8B0
0x140023c9f  mov     [rsp+2A0h+var_270], rax
0x140023ca4  lea     rax, qword_14002DC30
0x140023cab  mov     [rsp+2A0h+var_278], rax
0x140023cb0  lea     rax, qword_14002DFB0
0x140023cb7  movaps  xmmword ptr [rbp-50h], xmm1
0x140023cbb  mov     dword ptr [rbp+1A0h+var_1E0+8], r14d
0x140023cbf  movdqa  xmm0, cs:__xmm@0000000000000000000000003f800000
0x140023cc7  lea     rcx, [rbp+1A0h+var_B0]
0x140023cce  mov     edx, dword ptr [rsp+2A0h+var_240+4]
0x140023cd2  movaps  [rbp+1A0h+var_1D0], xmm0
0x140023cd6  xorps   xmm0, xmm0
0x140023cd9  movaps  [rbp+1A0h+var_1C0], xmm0
0x140023cdd  mov     [rsp+2A0h+var_280], rax
0x140023ce2  mov     [rbp+1A0h+var_1A0], r14d
0x140023ce6  movaps  [rbp+1A0h+var_1B0], xmm1
0x140023cea  mov     qword ptr [rbp+1A0h+var_1E0], r14
0x140023cee  call    ?_GetAppearance@Filters@ColorFiltering@@YA?AU_MAGN_COLOR_TRANSFORM@@KAEBU3@000000000@Z; ColorFiltering::Filters::_GetAppearance(ulong,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &)
0x140023cf3  movups  xmm0, [rbp+1A0h+var_B0]
0x140023cfa  mov     eax, [rbp+1A0h+var_50]
0x140023d00  lea     rcx, [rbp+1A0h+var_120]; struct _MAGN_COLOR_TRANSFORM *
0x140023d07  movups  xmm1, [rbp+1A0h+var_A0]
0x140023d0e  mov     [rbp+1A0h+var_C0], eax
0x140023d14  movaps  [rbp+1A0h+var_120], xmm0
0x140023d1b  movups  xmm0, [rbp+1A0h+var_90]
0x140023d22  movaps  [rbp+1A0h+var_110], xmm1
0x140023d29  movups  xmm1, [rbp+1A0h+var_80]
0x140023d30  movaps  [rbp+1A0h+var_100], xmm0
0x140023d37  movups  xmm0, [rbp+1A0h+var_70]
0x140023d3e  movaps  [rbp+1A0h+var_F0], xmm1
0x140023d45  movups  xmm1, [rbp+1A0h+var_60]
0x140023d4c  movaps  [rbp+1A0h+var_E0], xmm0
0x140023d53  movaps  [rbp+1A0h+var_D0], xmm1
0x140023d5a  lea     rdx, [rbp+1A0h+var_200]; struct _MAGN_COLOR_TRANSFORM *
0x140023d5e  lea     r8, [rbp+1A0h+var_190]; struct _MAGN_COLOR_TRANSFORM *
0x140023d62  call    ?GenerateAdaptationFilter@ColorFilterHelper@ColorFiltering@@CAXAEBU_MAGN_COLOR_TRANSFORM@@0AEAU3@@Z; ColorFiltering::ColorFilterHelper::GenerateAdaptationFilter(_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM &)
0x140023d67  jmp     loc_140023E3E
0x140023d6c  movaps  xmm0, cs:?GreyscaleInvert@Filters@ColorFiltering@@3U_MAGN_COLOR_TRANSFORM@@A; _MAGN_COLOR_TRANSFORM ColorFiltering::Filters::GreyscaleInvert
0x140023d73  movaps  xmm1, cs:xmmword_14002D5B0
0x140023d7a  mov     eax, cs:dword_14002D600
0x140023d80  movaps  [rbp+1A0h+var_190], xmm0
0x140023d84  movaps  xmm0, cs:xmmword_14002D5C0
0x140023d8b  movaps  [rbp+1A0h+var_180], xmm1
  ... truncated ...
```
