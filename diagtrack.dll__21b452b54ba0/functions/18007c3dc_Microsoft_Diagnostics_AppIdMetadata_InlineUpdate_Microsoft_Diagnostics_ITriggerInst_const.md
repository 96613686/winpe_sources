# Microsoft::Diagnostics::AppIdMetadata::InlineUpdate(Microsoft::Diagnostics::ITriggerInst const &)

- ea: `0x18007c3dc`
- end: `0x18007d3cf`
- name: `?InlineUpdate@AppIdMetadata@Diagnostics@Microsoft@@QEAAXAEBVITriggerInst@23@@Z`
- size: `4083`
- prototype: `void __fastcall(Microsoft::Diagnostics::AppIdMetadata *__hidden this, const struct Microsoft::Diagnostics::ITriggerInst *)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180182cb0`
- `0x1801fece4`

## callees

- `0x18002be90`
- `0x18002cae0`
- `0x18002df00`
- `0x18002df70`
- `0x18002e030`
- `0x180052240`
- `0x180055730`
- `0x180058e60`
- `0x18005acbc`
- `0x18007afd0`
- `0x18007c3dc`
- `0x18007d3d8`
- `0x18007d47c`
- `0x18007e2e4`
- `0x18007e31c`
- `0x1800ca190`
- `0x1800ca65c`
- `0x1800e6994`
- `0x18015b798`
- `0x18015bbb8`
- `0x18015c800`
- `0x1801a9494`
- `0x1801b7bd0`
- `0x18020aac0`
- `0x1802a4444`
- `0x180369010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18007c558`
- `msvcp_win!_Mtx_unlock` at `0x18007c558`

## string_xrefs

- `0x18007c983`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d031`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d049`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d064`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d07c`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d097`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d0af`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d0ca`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d0e2`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d0fd`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d115`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d130`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d148`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d163`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d17b`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d193`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d1ab`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d1c3`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d1db`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d1f3`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d20b`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d226`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d23e`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d259`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d271`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d28c`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d2a4`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d2c9`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d2e1`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d2fc`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d314`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d383`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007d39b`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007caf9`: `SessionCreateTime`
- `0x18007cbb7`: `CommandLine`
- `0x18007cc8a`: `UserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Microsoft::Diagnostics::AppIdMetadata::InlineUpdate(
        Microsoft::Diagnostics::AppIdMetadata *this,
        const struct Microsoft::Diagnostics::ITriggerInst *a2)
{
  char v4; // r12
  char *v5; // rbx
  unsigned int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rax
  unsigned int i; // edx
  __int64 v10; // r9
  const wchar_t *v11; // r10
  _WORD *v12; // r11
  _QWORD *v13; // rax
  __int64 v14; // rcx
  char *v15; // r15
  __int64 v16; // r13
  _QWORD *v17; // rax
  _QWORD *v18; // rcx
  char *v19; // r15
  __int64 v20; // r12
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  unsigned int v23; // eax
  wil::details::in1diag3 *v24; // r10
  unsigned int v25; // eax
  wil::details::in1diag3 *v26; // r10
  unsigned int v27; // eax
  wil::details::in1diag3 *v28; // r10
  _QWORD *v29; // rax
  __int64 v30; // rcx
  Microsoft::Diagnostics::AppIdMetadata *v31; // rdi
  __int64 v32; // r15
  _QWORD *v33; // rax
  __int64 v34; // rcx
  JsonValue *v35; // rcx
  void *v36; // rdi
  unsigned __int64 v37; // rbx
  __int64 *v38; // rax
  __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v41; // rdx
  std::_Ref_count_base *v42; // rcx
  unsigned int v43; // eax
  wil::details::in1diag3 *v44; // r10
  unsigned int v45; // r15d
  unsigned int v46; // eax
  wil::details::in1diag3 *v47; // r10
  std::_Ref_count_base *v48; // rsi
  unsigned int v49; // eax
  wil::details::in1diag3 *v50; // r10
  unsigned int v51; // eax
  wil::details::in1diag3 *v52; // r10
  unsigned int v53; // eax
  wil::details::in1diag3 *v54; // r10
  unsigned int v55; // eax
  __int64 v56; // rdx
  const void *v57; // r9
  unsigned __int64 v58; // r8
  char v59; // al
  __int128 *v60; // rax
  unsigned int v61; // eax
  __int64 v62; // rdx
  const void *v63; // r9
  unsigned __int64 v64; // r8
  char v65; // al
  unsigned int v66; // eax
  __int64 v67; // rdx
  const void *v68; // r9
  unsigned __int64 v69; // r8
  char v70; // al
  __int128 *v71; // rdx
  unsigned int v72; // eax
  __int64 v73; // rdx
  const void *v74; // rcx
  char *v75; // r8
  char v76; // al
  unsigned int v77; // eax
  __int64 v78; // rdx
  const void *v79; // rcx
  char *v80; // r8
  unsigned int v81; // eax
  wil::details::in1diag3 *v82; // r10
  unsigned int v83; // eax
  wil::details::in1diag3 *v84; // r10
  _QWORD *CacheEntry; // rbx
  int v86[2]; // [rsp+20h] [rbp-E0h] BYREF
  std::_Ref_count_base *v87; // [rsp+28h] [rbp-D8h]
  unsigned int v88[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v89; // [rsp+38h] [rbp-C8h]
  __int64 v90; // [rsp+40h] [rbp-C0h] BYREF
  _Mtx_t v91; // [rsp+48h] [rbp-B8h]
  char v92; // [rsp+50h] [rbp-B0h]
  __int128 v93; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v94; // [rsp+68h] [rbp-98h]
  __int128 v95; // [rsp+78h] [rbp-88h] BYREF
  char *v96; // [rsp+88h] [rbp-78h]
  unsigned __int64 v97; // [rsp+90h] [rbp-70h]
  _OWORD v98[2]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v99[4]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v100; // [rsp+C4h] [rbp-3Ch]
  unsigned int v101; // [rsp+C8h] [rbp-38h]
  int v102; // [rsp+CCh] [rbp-34h]
  std::_Ref_count_base *v103; // [rsp+D0h] [rbp-30h]
  std::_Ref_count_base *v104; // [rsp+D8h] [rbp-28h]
  std::_Ref_count_base *v105; // [rsp+E0h] [rbp-20h]
  _QWORD v106[2]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v107[48]; // [rsp+F8h] [rbp-8h] BYREF
  std::_Ref_count_base *v108; // [rsp+128h] [rbp+28h]
  char *v109[4]; // [rsp+130h] [rbp+30h] BYREF
  char *v110[4]; // [rsp+150h] [rbp+50h] BYREF
  char *v111[4]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v112; // [rsp+190h] [rbp+90h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v91 = (Microsoft::Diagnostics::AppIdMetadata *)((char *)this + 408);
  std::_Mutex_base::lock((Microsoft::Diagnostics::AppIdMetadata *)((char *)this + 408));
  v4 = 1;
  v92 = 1;
  if ( !*(_BYTE *)((*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 120LL))(a2)
                 + 48) )
  {
    v5 = (char *)a2 + 16;
    v6 = 0;
    if ( *((_DWORD *)a2 + 6) )
    {
      v7 = *(_QWORD *)v5;
      if ( *(_BYTE *)(*(_QWORD *)v5 + 7LL) >= 0xFEu )
      {
        v8 = (2 * (*(_DWORD *)(v7 + 4) & 0xFFFFFFu) + 15) >> 2;
        if ( (_DWORD)v8 != *(_DWORD *)(v7 + 8) )
        {
          for ( i = *(_DWORD *)(v7 + 4 * v8);
                *(_BYTE *)(v7 + 4LL * i + 7) == 0xFD || (*(_DWORD *)(v7 + 4LL * i + 4) & 0xFFFFFF) != 4;
                i = *(_DWORD *)(v7 + 4LL * i) )
          {
LABEL_12:
            if ( i == *(_DWORD *)(v7 + 8) )
              goto LABEL_19;
          }
          v10 = 4;
          v11 = L"data";
          v12 = (_WORD *)(v7 + 12 + 4LL * i);
          while ( v10 )
          {
            if ( *v12 != *v11 )
              goto LABEL_12;
            --v10;
            ++v12;
            ++v11;
          }
          v6 = i;
        }
      }
    }
LABEL_19:
    *(_QWORD *)&v93 = (char *)a2 + 16;
    DWORD2(v93) = v6;
    if ( !v6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
        (const char *)0x80070490LL,
        v86[0]);
    v13 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 80LL))(a2);
    v14 = *v13 - *(_QWORD *)&Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid.Data1;
    if ( *v13 == *(_QWORD *)&Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid.Data1 )
      v14 = v13[1] - *(_QWORD *)Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid.Data4;
    if ( v14 )
    {
      v29 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 80LL))(a2);
      v30 = *v29 - *(_QWORD *)&Microsoft::Diagnostics::EventBasedMetadata::k_appTelemetryMetadataProviderGuid.Data1;
      if ( *v29 == *(_QWORD *)&Microsoft::Diagnostics::EventBasedMetadata::k_appTelemetryMetadataProviderGuid.Data1 )
        v30 = v29[1] - *(_QWORD *)Microsoft::Diagnostics::EventBasedMetadata::k_appTelemetryMetadataProviderGuid.Data4;
      if ( !v30 )
      {
        v31 = *((_QWORD *)this + 19) <= 7u
            ? (Microsoft::Diagnostics::AppIdMetadata *)((char *)this + 128)
            : (Microsoft::Diagnostics::AppIdMetadata *)*((_QWORD *)this + 16);
        v32 = *((_QWORD *)this + 18);
        v33 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 120LL))(a2);
        v34 = v33[5] <= 7u ? (__int64)(v33 + 2) : v33[2];
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v34, v33[4], v31, v32) )
        {
          *(_QWORD *)v86 = L"AccountId";
          v87 = (std::_Ref_count_base *)9;
          JsonBuilder::find<>((char *)a2 + 16, v88, &v93, v86);
          if ( !v89 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1F9,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v86[0]);
          v35 = (JsonValue *)(**(_QWORD **)v88 + 4LL * v89);
          if ( *((_BYTE *)v35 + 7) == 0xF5 )
          {
            v88[0] = 0;
            v36 = JsonValue::Data(v35, v88);
            v37 = (unsigned __int64)v88[0] >> 1;
            v4 = 0;
          }
          else
          {
            v36 = 0;
            v37 = 0;
          }
          if ( v4 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1FA,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v86[0]);
          v86[0] = *((_DWORD *)a2 + 170);
          v87 = (std::_Ref_count_base *)*((_QWORD *)a2 + 84);
          Microsoft::Diagnostics::AppIdMetadata::FindProcess(this, &v90, v86);
          if ( v90 != *((_QWORD *)this + 40) )
          {
            *(_QWORD *)v88 = v37;
            *(_QWORD *)&v93 = v36;
            v38 = (__int64 *)std::make_shared<std::wstring,wchar_t const *,unsigned __int64>(v86, &v93, v88);
            v39 = v90;
            v40 = *v38;
            v41 = v38[1];
            *v38 = 0;
            v38[1] = 0;
            *(_QWORD *)(v39 + 120) = v40;
            v42 = *(std::_Ref_count_base **)(v39 + 128);
            *(_QWORD *)(v39 + 128) = v41;
            if ( v42 )
              std::_Ref_count_base::_Decref(v42);
            if ( v87 )
              std::_Ref_count_base::_Decref(v87);
          }
        }
      }
    }
    else
    {
      if ( *((_QWORD *)this + 11) <= 7u )
        v15 = (char *)this + 64;
      else
        v15 = (char *)*((_QWORD *)this + 8);
      v16 = *((_QWORD *)this + 10);
      v17 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 120LL))(a2);
      if ( v17[5] <= 7u )
        v18 = v17 + 2;
      else
        v18 = (_QWORD *)v17[2];
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v18, v17[4], v15, v16) )
      {
        *(_QWORD *)v88 = 0;
        *(_QWORD *)&v93 = L"InstanceId";
        *((_QWORD *)&v93 + 1) = 10;
        v43 = JsonBuilder::Find<>((char *)a2 + 16, v6, &v93);
        if ( !v43 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x174,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
            (const char *)0x80070490LL,
            v86[0]);
        if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*(_QWORD *)v5 + 4LL * v43, v88) )
          wil::details::in1diag3::Throw_Hr(
            v44,
            (void *)0x175,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
            (const char *)0x8007070CLL,
            v86[0]);
        v45 = v88[0];
        v86[0] = v88[0];
        *(_QWORD *)v88 = 0;
        *(_QWORD *)&v93 = L"ProcessStartKey";
        *((_QWORD *)&v93 + 1) = 15;
        v46 = JsonBuilder::Find<>((char *)a2 + 16, v6, &v93);
        if ( !v46 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x17A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
            (const char *)0x80070490LL,
            v86[0]);
        if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*(_QWORD *)v5 + 4LL * v46, v88) )
          wil::details::in1diag3::Throw_Hr(
            v47,
            (void *)0x17B,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
            (const char *)0x8007070CLL,
            v86[0]);
        v48 = *(std::_Ref_count_base **)v88;
        v87 = *(std::_Ref_count_base **)v88;
        Microsoft::Diagnostics::AppIdMetadata::FindProcess(this, &v90, v86);
        if ( v90 == *((_QWORD *)this + 40) )
        {
          Microsoft::Diagnostics::AppIdMetadata::ProcessInfo::ProcessInfo((Microsoft::Diagnostics::AppIdMetadata::ProcessInfo *)v99);
          v100 = v45;
          v104 = v48;
          *(_QWORD *)v88 = 0;
          *(_QWORD *)v86 = L"SessionId";
          v87 = (std::_Ref_count_base *)9;
          v49 = JsonBuilder::Find<>(v5, v6, v86);
          if ( !v49 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x18A,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v86[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*(_QWORD *)v5 + 4LL * v49, v88) )
            wil::details::in1diag3::Throw_Hr(
              v50,
              (void *)0x18B,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v86[0]);
          v101 = v88[0];
          *(_QWORD *)v88 = 0;
          *(_QWORD *)v86 = L"SessionCreateTime";
          v87 = (std::_Ref_count_base *)17;
          v51 = JsonBuilder::Find<>(v5, v6, v86);
          if ( !v51 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x190,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v86[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*(_QWORD *)v5 + 4LL * v51, v88) )
            wil::details::in1diag3::Throw_Hr(
              v52,
              (void *)0x191,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v86[0]);
          v103 = *(std::_Ref_count_base **)v88;
          *(_QWORD *)v88 = 0;
          *(_QWORD *)v86 = L"InstanceStartTime";
          v87 = (std::_Ref_count_base *)17;
          v53 = JsonBuilder::Find<>(v5, v6, v86);
          if ( !v53 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x196,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v86[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*(_QWORD *)v5 + 4LL * v53, v88) )
            wil::details::in1diag3::Throw_Hr(
              v54,
              (void *)0x197,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v86[0]);
          v105 = *(std::_Ref_count_base **)v88;
          *(_QWORD *)v86 = L"CommandLine";
          v87 = (std::_Ref_count_base *)11;
          v55 = JsonBuilder::Find<>(v5, v6, v86);
          if ( !v55 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x19C,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v86[0]);
          v56 = *(_QWORD *)v5 + 4LL * v55;
          if ( *(_BYTE *)(v56 + 7) == 0xF5 )
          {
            v57 = (const void *)(v56 + 4 * ((2 * (*(_DWORD *)(v56 + 4) & 0xFFFFFFuLL) + 15) >> 2));
            v58 = (unsigned __int64)*(unsigned int *)(v56 + 8) >> 1;
            v59 = 0;
          }
          else
          {
            v57 = 0;
            v58 = 0;
            v59 = 1;
          }
          if ( v59 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x19D,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v86[0]);
          v93 = 0;
          v94 = 0;
          std::wstring::_Construct<1,wchar_t *>(&v93, v57, v58);
          v60 = &v93;
          if ( *((_QWORD *)&v94 + 1) > 7u )
            v60 = (__int128 *)v93;
          *(_QWORD *)v86 = v60;
          v87 = (std::_Ref_count_base *)v94;
          v102 = Microsoft::Diagnostics::AppIdMetadata::CalculateCommandLineHash(v86);
          std::wstring::_Tidy_deallocate(&v93);
          *(_QWORD *)v86 = L"UserSid";
          v87 = (std::_Ref_count_base *)7;
          v61 = JsonBuilder::Find<>(v5, v6, v86);
          if ( !v61 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1A2,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v86[0]);
          v62 = *(_QWORD *)v5 + 4LL * v61;
          if ( *(_BYTE *)(v62 + 7) == 0xF5 )
          {
            v63 = (const void *)(v62 + 4 * ((2 * (*(_DWORD *)(v62 + 4) & 0xFFFFFFuLL) + 15) >> 2));
            v64 = (unsigned __int64)*(unsigned int *)(v62 + 8) >> 1;
            v65 = 0;
          }
          else
          {
            v63 = 0;
            v64 = 0;
            v65 = 1;
          }
          if ( v65 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1A3,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v86[0]);
          memset(v98, 0, sizeof(v98));
          std::wstring::_Construct<1,wchar_t *>(v98, v63, v64);
          std::wstring::_Tidy_deallocate(v107);
          std::wstring::_Take_contents(v107, v98);
          std::wstring::wstring(v109);
          std::wstring::wstring(v110);
          std::wstring::wstring(v111);
          v112 = 0;
          *(_QWORD *)v86 = L"ImageFileName";
          v87 = (std::_Ref_count_base *)13;
          v66 = JsonBuilder::Find<>(v5, v6, v86);
          if ( !v66 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1AC,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v86[0]);
          v67 = *(_QWORD *)v5 + 4LL * v66;
          if ( *(_BYTE *)(v67 + 7) == 0xF5 )
          {
            v68 = (const void *)(v67 + 4 * ((2 * (*(_DWORD *)(v67 + 4) & 0xFFFFFFuLL) + 15) >> 2));
            v69 = (unsigned __int64)*(unsigned int *)(v67 + 8) >> 1;
            v70 = 0;
          }
          else
          {
            v68 = 0;
            v69 = 0;
            v70 = 1;
          }
          if ( v70 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1AD,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v86[0]);
          v95 = 0;
          v96 = 0;
          v97 = 0;
          std::wstring::_Construct<1,wchar_t *>(&v95, v68, v69);
          Microsoft::Diagnostics::Utils::String::ToLowercase(&v95);
          v71 = &v95;
          if ( v97 > 7 )
            v71 = (__int128 *)v95;
          std::wstring::_Assign<wchar_t>(v109, v71, v96);
          *(_QWORD *)v86 = L"PackageName";
          v87 = (std::_Ref_count_base *)11;
          v72 = JsonBuilder::Find<>(v5, v6, v86);
          if ( !v72 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1B4,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v86[0]);
          v73 = *(_QWORD *)v5 + 4LL * v72;
          if ( *(_BYTE *)(v73 + 7) == 0xF5 )
          {
            v74 = (const void *)(v73 + 4 * ((2 * (*(_DWORD *)(v73 + 4) & 0xFFFFFFuLL) + 15) >> 2));
            v75 = (char *)((unsigned __int64)*(unsigned int *)(v73 + 8) >> 1);
            v76 = 0;
          }
          else
          {
            v74 = 0;
            v75 = 0;
            v76 = 1;
          }
          if ( v76 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1B5,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v86[0]);
          std::wstring::_Assign<wchar_t>(v110, v74, v75);
          *(_QWORD *)v86 = L"PRAID";
          v87 = (std::_Ref_count_base *)5;
          v77 = JsonBuilder::Find<>(v5, v6, v86);
          if ( !v77 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1BA,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v86[0]);
          v78 = *(_QWORD *)v5 + 4LL * v77;
          if ( *(_BYTE *)(v78 + 7) == 0xF5 )
          {
            v79 = (const void *)(v78 + 4 * ((2 * (*(_DWORD *)(v78 + 4) & 0xFFFFFFuLL) + 15) >> 2));
            v80 = (char *)((unsigned __int64)*(unsigned int *)(v78 + 8) >> 1);
            v4 = 0;
          }
          else
          {
            v79 = 0;
            v80 = 0;
          }
          if ( v4 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1BB,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v86[0]);
          std::wstring::_Assign<wchar_t>(v111, v79, v80);
          *(_QWORD *)v88 = 0;
          *(_QWORD *)v86 = L"ImageChecksum";
          v87 = (std::_Ref_count_base *)13;
          v81 = JsonBuilder::Find<>(v5, v6, v86);
          if ( !v81 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1C0,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v86[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*(_QWORD *)v5 + 4LL * v81, v88) )
            wil::details::in1diag3::Throw_Hr(
              v82,
              (void *)0x1C1,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v86[0]);
          LODWORD(v112) = v88[0];
          *(_QWORD *)v88 = 0;
          *(_QWORD *)v86 = L"ImageTimeDateStamp";
          v87 = (std::_Ref_count_base *)18;
          v83 = JsonBuilder::Find<>(v5, v6, v86);
          if ( !v83 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1C6,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v86[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*(_QWORD *)v5 + 4LL * v83, v88) )
            wil::details::in1diag3::Throw_Hr(
              v84,
              (void *)0x1C7,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v86[0]);
          HIDWORD(v112) = v88[0];
          CacheEntry = (_QWORD *)Microsoft::Diagnostics::AppIdCache::GetCacheEntry((char *)this + 168, v86, v109);
          if ( v106 != CacheEntry )
          {
            Microsoft::Diagnostics::IteratorSmartRef<Microsoft::Diagnostics::AppIdCache,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Microsoft::Diagnostics::AppIdCache::AppIdCacheEntry>>>>>::Clear(v106);
            v106[0] = *CacheEntry;
            *CacheEntry = 0;
            v106[1] = CacheEntry[1];
            CacheEntry[1] = 0;
          }
          if ( *(_QWORD *)v86 )
            Microsoft::Diagnostics::AppIdCache::Dereference(*(_QWORD *)v86, v87);
          Microsoft::Diagnostics::AppIdMetadata::AddProcess(this);
          std::wstring::_Tidy_deallocate(&v95);
          std::wstring::_Tidy_deallocate(v111);
          std::wstring::_Tidy_deallocate(v110);
          std::wstring::_Tidy_deallocate(v109);
          std::wstring::_Tidy_deallocate(v98);
          if ( v108 )
            std::_Ref_count_base::_Decref(v108);
          std::wstring::_Tidy_deallocate(v107);
          Microsoft::Diagnostics::IteratorSmartRef<Microsoft::Diagnostics::AppIdCache,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Microsoft::Diagnostics::AppIdCache::AppIdCacheEntry>>>>>::Clear(v106);
        }
      }
      else
      {
        if ( *((_QWORD *)this + 15) <= 7u )
          v19 = (char *)this + 96;
        else
          v19 = (char *)*((_QWORD *)this + 12);
        v20 = *((_QWORD *)this + 14);
        v21 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 120LL))(a2);
        if ( v21[5] <= 7u )
          v22 = v21 + 2;
        else
          v22 = (_QWORD *)v21[2];
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v22, v21[4], v19, v20) )
        {
          *(_QWORD *)v88 = 0;
          *(_QWORD *)v86 = L"AppStateChange";
          v87 = (std::_Ref_count_base *)14;
          v23 = JsonBuilder::Find<>((char *)a2 + 16, v6, v86);
          if ( !v23 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1D5,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v86[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*(_QWORD *)v5 + 4LL * v23, v88) )
            wil::details::in1diag3::Throw_Hr(
              v24,
              (void *)0x1D6,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v86[0]);
          if ( v88[0] == 3 )
          {
            *(_QWORD *)v88 = 0;
            *(_QWORD *)v86 = L"InstanceId";
            v87 = (std::_Ref_count_base *)10;
            v25 = JsonBuilder::Find<>((char *)a2 + 16, v6, v86);
            if ( !v25 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1DE,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
                (const char *)0x80070490LL,
                v86[0]);
            if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*(_QWORD *)v5 + 4LL * v25, v88) )
              wil::details::in1diag3::Throw_Hr(
                v26,
                (void *)0x1DF,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
                (const char *)0x8007070CLL,
                v86[0]);
            LODWORD(v93) = v88[0];
            *(_QWORD *)v88 = 0;
            *(_QWORD *)v86 = L"ProcessStartKey";
            v87 = (std::_Ref_count_base *)15;
            v27 = JsonBuilder::Find<>((char *)a2 + 16, v6, v86);
            if ( !v27 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1E4,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
                (const char *)0x80070490LL,
                v86[0]);
            if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*(_QWORD *)v5 + 4LL * v27, v88) )
              wil::details::in1diag3::Throw_Hr(
                v28,
                (void *)0x1E5,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
                (const char *)0x8007070CLL,
                v86[0]);
            *((_QWORD *)&v93 + 1) = *(_QWORD *)v88;
            Microsoft::Diagnostics::AppIdMetadata::FindProcess(this, &v90, &v93);
            if ( v90 != *((_QWORD *)this + 40) && !*(_BYTE *)(v90 + 24) )
              Microsoft::Diagnostics::AppIdMetadata::MarkProcessEnded(this);
          }
        }
      }
    }
  }
  _Mtx_unlock(v91);
}

```

## disassembly

```asm
0x18007c3dc  mov     [rsp-8+arg_10], rbx
0x18007c3e1  push    rbp
0x18007c3e2  push    rsi
0x18007c3e3  push    rdi
0x18007c3e4  push    r12
0x18007c3e6  push    r13
0x18007c3e8  push    r14
0x18007c3ea  push    r15
0x18007c3ec  lea     rbp, [rsp-0B0h]
0x18007c3f4  sub     rsp, 1B0h
0x18007c3fb  mov     rax, cs:__security_cookie
0x18007c402  xor     rax, rsp
0x18007c405  mov     [rbp+0E0h+var_40], rax
0x18007c40c  mov     rsi, rdx
0x18007c40f  mov     r14, rcx
0x18007c412  lea     rax, [rcx+198h]
0x18007c419  mov     [rsp+1E0h+var_198], rax
0x18007c41e  mov     rcx, rax; this
0x18007c421  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18007c426  mov     r12d, 1
0x18007c42c  mov     [rsp+1E0h+var_190], r12b
0x18007c431  mov     rax, [rsi]
0x18007c434  mov     rcx, rsi
0x18007c437  mov     rax, [rax+78h]
0x18007c43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c440  xor     r13d, r13d
0x18007c443  cmp     [rax+30h], r13b
0x18007c447  jnz     loc_18007C553
0x18007c44d  lea     rbx, [rsi+10h]
0x18007c451  mov     edi, r13d
0x18007c454  cmp     [rbx+8], r13d
0x18007c458  jz      loc_18007C58A
0x18007c45e  mov     rcx, [rbx]
0x18007c461  cmp     byte ptr [rcx+7], 0FEh
0x18007c465  jb      loc_18007C58A
0x18007c46b  mov     eax, [rcx+4]
0x18007c46e  and     eax, 0FFFFFFh
0x18007c473  lea     eax, ds:0Fh[rax*2]
0x18007c47a  shr     eax, 2
0x18007c47d  cmp     eax, [rcx+8]
0x18007c480  jz      loc_18007C58A
0x18007c486  mov     edx, [rcx+rax*4]
0x18007c489  mov     r8d, edx
0x18007c48c  cmp     byte ptr [rcx+r8*4+7], 0FDh
0x18007c492  jz      short loc_18007C4D5
0x18007c494  mov     eax, [rcx+r8*4+4]
0x18007c499  and     eax, 0FFFFFFh
0x18007c49e  cmp     eax, 4
0x18007c4a1  jnz     short loc_18007C4D5
0x18007c4a3  mov     r9d, eax
0x18007c4a6  lea     r10, aData_0; "data"
0x18007c4ad  lea     r11, [rcx+0Ch]
0x18007c4b1  lea     r11, [r11+r8*4]
0x18007c4b5  test    r9, r9
0x18007c4b8  jz      loc_18007C588
0x18007c4be  movzx   eax, word ptr [r10]
0x18007c4c2  cmp     [r11], ax
0x18007c4c6  jnz     short loc_18007C4D5
0x18007c4c8  sub     r9, r12
0x18007c4cb  add     r11, 2
0x18007c4cf  add     r10, 2
0x18007c4d3  jmp     short loc_18007C4B5
0x18007c4d5  cmp     edx, [rcx+8]
0x18007c4d8  jz      loc_18007C58A
0x18007c4de  mov     edx, [rcx+r8*4]
0x18007c4e2  jmp     short loc_18007C489
0x18007c4e4  mov     rdx, [rsp+1E0h+var_1B8]
0x18007c4e9  call    ?Dereference@AppIdCache@Diagnostics@Microsoft@@AEAAXV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUAppIdCacheEntry@AppIdCache@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@Z; Microsoft::Diagnostics::AppIdCache::Dereference(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Microsoft::Diagnostics::AppIdCache::AppIdCacheEntry>>>>)
0x18007c4ee  nop
0x18007c4ef  lea     r8, [rbp+0E0h+var_120]
0x18007c4f3  lea     rdx, [rsp+1E0h+var_188]
0x18007c4f8  mov     rcx, r14
0x18007c4fb  call    ?AddProcess@AppIdMetadata@Diagnostics@Microsoft@@AEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUProcessInfo@AppIdMetadata@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@AEBUProcessInfo@123@@Z; Microsoft::Diagnostics::AppIdMetadata::AddProcess(Microsoft::Diagnostics::AppIdMetadata::ProcessInfo const &)
0x18007c500  nop
0x18007c501  lea     rcx, [rsp+1E0h+var_168]
0x18007c506  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c50b  nop
0x18007c50c  lea     rcx, [rbp+0E0h+var_70]
0x18007c510  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c515  lea     rcx, [rbp+0E0h+var_90]
0x18007c519  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c51e  lea     rcx, [rbp+0E0h+var_B0]
0x18007c522  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c527  nop
0x18007c528  lea     rcx, [rbp+0E0h+var_148]
0x18007c52c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c531  nop
0x18007c532  mov     rcx, [rbp+0E0h+var_B8]; this
0x18007c536  test    rcx, rcx
0x18007c539  jnz     loc_18007D2B9
0x18007c53f  lea     rcx, [rbp+0E0h+var_E8]
0x18007c543  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c548  nop
0x18007c549  lea     rcx, [rbp+0E0h+var_F8]
0x18007c54d  call    ?Clear@?$IteratorSmartRef@VAppIdCache@Diagnostics@Microsoft@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUAppIdCacheEntry@AppIdCache@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::IteratorSmartRef<Microsoft::Diagnostics::AppIdCache,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Microsoft::Diagnostics::AppIdCache::AppIdCacheEntry>>>>>::Clear(void)
0x18007c552  nop
0x18007c553  mov     rcx, [rsp+1E0h+var_198]; _Mtx_t
0x18007c558  call    cs:__imp__Mtx_unlock
0x18007c55e  mov     rcx, [rbp+0E0h+var_40]
0x18007c565  xor     rcx, rsp; StackCookie
0x18007c568  call    __security_check_cookie
0x18007c56d  mov     rbx, [rsp+1E0h+arg_10]
0x18007c575  add     rsp, 1B0h
0x18007c57c  pop     r15
0x18007c57e  pop     r14
0x18007c580  pop     r13
0x18007c582  pop     r12
0x18007c584  pop     rdi
0x18007c585  pop     rsi
0x18007c586  pop     rbp
0x18007c587  retn
0x18007c588  mov     edi, edx
0x18007c58a  mov     qword ptr [rsp+1E0h+var_188], rbx
0x18007c58f  mov     dword ptr [rsp+1E0h+var_188+8], edi
0x18007c593  mov     rcx, [rbp+0E8h]; this
0x18007c59a  test    edi, edi
0x18007c59c  jz      loc_18007C97D
0x18007c5a2  mov     rax, [rsi]
0x18007c5a5  mov     rcx, rsi
0x18007c5a8  mov     rax, [rax+50h]
0x18007c5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c5b1  mov     rcx, [rax]
0x18007c5b4  sub     rcx, qword ptr cs:?k_kernelTLProcessProviderGuid@EventBasedMetadata@Diagnostics@Microsoft@@1U_GUID@@B.Data1; _GUID const Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid ...
0x18007c5bb  jnz     short loc_18007C5C8
0x18007c5bd  mov     rcx, [rax+8]
0x18007c5c1  sub     rcx, qword ptr cs:?k_kernelTLProcessProviderGuid@EventBasedMetadata@Diagnostics@Microsoft@@1U_GUID@@B.Data4; _GUID const Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid ...
0x18007c5c8  test    rcx, rcx
0x18007c5cb  jnz     loc_18007C7CA
0x18007c5d1  cmp     qword ptr [r14+58h], 7
0x18007c5d6  jbe     loc_18007C959
0x18007c5dc  mov     r15, [r14+40h]
0x18007c5e0  mov     r13, [r14+50h]
0x18007c5e4  mov     rax, [rsi]
0x18007c5e7  mov     rcx, rsi
0x18007c5ea  mov     rax, [rax+78h]
0x18007c5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c5f3  cmp     qword ptr [rax+28h], 7
0x18007c5f8  jbe     loc_18007C962
0x18007c5fe  mov     rcx, [rax+10h]
0x18007c602  mov     r9, r13
0x18007c605  mov     r8, r15
0x18007c608  mov     rdx, [rax+20h]
0x18007c60c  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18007c611  xor     r13d, r13d
0x18007c614  test    al, al
0x18007c616  jnz     loc_18007C995
0x18007c61c  cmp     qword ptr [r14+78h], 7
0x18007c621  jbe     loc_18007C96B
0x18007c627  mov     r15, [r14+60h]
0x18007c62b  mov     r12, [r14+70h]
0x18007c62f  mov     rax, [rsi]
0x18007c632  mov     rcx, rsi
0x18007c635  mov     rax, [rax+78h]
0x18007c639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c63e  cmp     qword ptr [rax+28h], 7
0x18007c643  jbe     loc_18007C974
0x18007c649  mov     rcx, [rax+10h]
0x18007c64d  mov     r9, r12
0x18007c650  mov     r8, r15
0x18007c653  mov     rdx, [rax+20h]
0x18007c657  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18007c65c  test    al, al
0x18007c65e  jz      loc_18007C553
0x18007c664  mov     qword ptr [rsp+1E0h+var_1B0], r13
0x18007c669  lea     rax, aAppstatechange; "AppStateChange"
0x18007c670  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18007c675  mov     [rsp+1E0h+var_1B8], 0Eh
0x18007c67e  lea     r8, [rsp+1E0h+var_1C0]
0x18007c683  mov     edx, edi
0x18007c685  mov     rcx, rbx
0x18007c688  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007c68d  mov     rcx, [rbp+0E8h]; this
0x18007c694  test    eax, eax
0x18007c696  jz      loc_18007D02B
0x18007c69c  mov     r10, [rbp+0E8h]
0x18007c6a3  mov     edx, eax
0x18007c6a5  mov     rax, [rbx]
0x18007c6a8  lea     rcx, [rax+rdx*4]
0x18007c6ac  lea     rdx, [rsp+1E0h+var_1B0]
0x18007c6b1  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007c6b6  test    al, al
0x18007c6b8  jz      loc_18007D043
0x18007c6be  cmp     [rsp+1E0h+var_1B0], 3
0x18007c6c3  jnz     loc_18007C553
0x18007c6c9  mov     qword ptr [rsp+1E0h+var_1B0], r13
0x18007c6ce  lea     rax, aInstanceid_0; "InstanceId"
0x18007c6d5  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18007c6da  mov     [rsp+1E0h+var_1B8], 0Ah
0x18007c6e3  lea     r8, [rsp+1E0h+var_1C0]
0x18007c6e8  mov     edx, edi
0x18007c6ea  mov     rcx, rbx
0x18007c6ed  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007c6f2  mov     rcx, [rbp+0E8h]; this
0x18007c6f9  test    eax, eax
0x18007c6fb  jz      loc_18007D2C3
0x18007c701  mov     r10, [rbp+0E8h]
0x18007c708  mov     edx, eax
0x18007c70a  mov     rax, [rbx]
0x18007c70d  lea     rcx, [rax+rdx*4]
0x18007c711  lea     rdx, [rsp+1E0h+var_1B0]
0x18007c716  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007c71b  test    al, al
0x18007c71d  jz      loc_18007D2DB
0x18007c723  mov     eax, [rsp+1E0h+var_1B0]
0x18007c727  mov     dword ptr [rsp+1E0h+var_188], eax
0x18007c72b  mov     qword ptr [rsp+1E0h+var_1B0], r13
0x18007c730  lea     rax, aProcessstartke; "ProcessStartKey"
0x18007c737  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18007c73c  mov     [rsp+1E0h+var_1B8], 0Fh
0x18007c745  lea     r8, [rsp+1E0h+var_1C0]
0x18007c74a  mov     edx, edi
0x18007c74c  mov     rcx, rbx
0x18007c74f  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007c754  mov     rcx, [rbp+0E8h]; this
0x18007c75b  test    eax, eax
0x18007c75d  jz      loc_18007D2F6
0x18007c763  mov     r10, [rbp+0E8h]
0x18007c76a  mov     edx, eax
0x18007c76c  mov     rax, [rbx]
0x18007c76f  lea     rcx, [rax+rdx*4]
0x18007c773  lea     rdx, [rsp+1E0h+var_1B0]
0x18007c778  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007c77d  test    al, al
0x18007c77f  jz      loc_18007D30E
0x18007c785  mov     rax, qword ptr [rsp+1E0h+var_1B0]
0x18007c78a  mov     qword ptr [rsp+1E0h+var_188+8], rax
0x18007c78f  lea     r8, [rsp+1E0h+var_188]
0x18007c794  lea     rdx, [rsp+1E0h+var_1A0]
0x18007c799  mov     rcx, r14
0x18007c79c  call    ?FindProcess@AppIdMetadata@Diagnostics@Microsoft@@AEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUProcessInfo@AppIdMetadata@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@AEBUProcessKey@@@Z; Microsoft::Diagnostics::AppIdMetadata::FindProcess(ProcessKey const &)
0x18007c7a1  mov     rdx, [rsp+1E0h+var_1A0]
0x18007c7a6  cmp     rdx, [r14+140h]
0x18007c7ad  jz      loc_18007C553
0x18007c7b3  cmp     [rdx+18h], r13b
0x18007c7b7  jnz     loc_18007C553
0x18007c7bd  mov     rcx, r14
0x18007c7c0  call    ?MarkProcessEnded@AppIdMetadata@Diagnostics@Microsoft@@AEAAXV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUProcessInfo@AppIdMetadata@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@Z; Microsoft::Diagnostics::AppIdMetadata::MarkProcessEnded(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,Microsoft::Diagnostics::AppIdMetadata::ProcessInfo>>>>)
0x18007c7c5  jmp     loc_18007C553
0x18007c7ca  mov     rax, [rsi]
0x18007c7cd  mov     rcx, rsi
0x18007c7d0  mov     rax, [rax+50h]
0x18007c7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c7d9  mov     rcx, [rax]
0x18007c7dc  sub     rcx, qword ptr cs:?k_appTelemetryMetadataProviderGuid@EventBasedMetadata@Diagnostics@Microsoft@@1U_GUID@@B.Data1; _GUID const Microsoft::Diagnostics::EventBasedMetadata::k_appTelemetryMetadataProviderGuid ...
0x18007c7e3  jnz     short loc_18007C7F0
0x18007c7e5  mov     rcx, [rax+8]
0x18007c7e9  sub     rcx, qword ptr cs:?k_appTelemetryMetadataProviderGuid@EventBasedMetadata@Diagnostics@Microsoft@@1U_GUID@@B.Data4; _GUID const Microsoft::Diagnostics::EventBasedMetadata::k_appTelemetryMetadataProviderGuid ...
0x18007c7f0  test    rcx, rcx
0x18007c7f3  jnz     loc_18007C553
0x18007c7f9  lea     rax, [r14+80h]
0x18007c800  cmp     qword ptr [rax+18h], 7
0x18007c805  jbe     loc_18007D35E
0x18007c80b  mov     rdi, [rax]
0x18007c80e  mov     r15, [rax+10h]
0x18007c812  mov     rax, [rsi]
0x18007c815  mov     rcx, rsi
0x18007c818  mov     rax, [rax+78h]
0x18007c81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c821  cmp     qword ptr [rax+28h], 7
0x18007c826  jbe     loc_18007D366
0x18007c82c  mov     rcx, [rax+10h]
0x18007c830  mov     r9, r15
0x18007c833  mov     r8, rdi
0x18007c836  mov     rdx, [rax+20h]
0x18007c83a  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18007c83f  test    al, al
0x18007c841  jz      loc_18007C553
0x18007c847  lea     rax, aAccountid; "AccountId"
0x18007c84e  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18007c853  mov     [rsp+1E0h+var_1B8], 9
0x18007c85c  lea     r9, [rsp+1E0h+var_1C0]
0x18007c861  lea     r8, [rsp+1E0h+var_188]
0x18007c866  lea     rdx, [rsp+1E0h+var_1B0]
0x18007c86b  mov     rcx, rbx
0x18007c86e  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007c873  mov     edx, [rsp+1E0h+var_1A8]
0x18007c877  test    edx, edx
0x18007c879  setz    al
0x18007c87c  mov     rcx, [rbp+0E8h]; this
0x18007c883  test    al, al
0x18007c885  jnz     loc_18007D37D
0x18007c88b  mov     rax, qword ptr [rsp+1E0h+var_1B0]
0x18007c890  mov     rcx, [rax]
0x18007c893  lea     rcx, [rcx+rdx*4]; this
0x18007c897  mov     r15b, 0F5h
0x18007c89a  cmp     [rcx+7], r15b
0x18007c89e  jz      loc_18007D3AD
0x18007c8a4  mov     rdi, r13
0x18007c8a7  mov     rbx, r13
0x18007c8aa  mov     rcx, [rbp+0E8h]; this
0x18007c8b1  test    r12b, r12b
0x18007c8b4  jnz     loc_18007D395
0x18007c8ba  mov     eax, [rsi+2A8h]
0x18007c8c0  mov     [rsp+1E0h+var_1C0], eax
0x18007c8c4  mov     rax, [rsi+2A0h]
0x18007c8cb  mov     [rsp+1E0h+var_1B8], rax
0x18007c8d0  lea     r8, [rsp+1E0h+var_1C0]
0x18007c8d5  lea     rdx, [rsp+1E0h+var_1A0]
0x18007c8da  mov     rcx, r14
0x18007c8dd  call    ?FindProcess@AppIdMetadata@Diagnostics@Microsoft@@AEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUProcessInfo@AppIdMetadata@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@AEBUProcessKey@@@Z; Microsoft::Diagnostics::AppIdMetadata::FindProcess(ProcessKey const &)
  ... truncated ...
```
