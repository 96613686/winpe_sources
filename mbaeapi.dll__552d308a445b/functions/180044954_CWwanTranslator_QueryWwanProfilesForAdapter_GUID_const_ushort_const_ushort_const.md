# CWwanTranslator::_QueryWwanProfilesForAdapter(_GUID const &,ushort const *,ushort const *)

- ea: `0x180044954`
- end: `0x1800458be`
- name: `?_QueryWwanProfilesForAdapter@CWwanTranslator@@AEAAJAEBU_GUID@@PEBG1@Z`
- size: `3946`
- prototype: `int __fastcall(CWwanTranslator *this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update`

## callers

- `0x180039f54`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180002efc`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800171b8`
- `0x1800172bc`
- `0x18001dd10`
- `0x18001e0d0`
- `0x180032ed8`
- `0x18003994c`
- `0x180043de4`
- `0x180044954`
- `0x1800588d0`
- `0x18005c010`

## import_xrefs

- `WwanPrfl!WwanProfileLoadXml` at `0x18004539a`
- `WwanPrfl!WwanProfileLoadXml` at `0x18004539a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004583f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004583f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800452ca`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800455f0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180045825`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180045831`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800452ca`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800455f0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180045825`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180045831`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180044abb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180044abb`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfileList` at `0x180045302`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfileList` at `0x180045302`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfile` at `0x18004536b`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfile` at `0x18004536b`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileList` at `0x180044b14`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileList` at `0x180044b14`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileIstream` at `0x180044b87`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileIstream` at `0x180044b87`

## string_xrefs

- `0x180044eea`: `Profile skipped: WwanGetProfileIstream returned for [profilename=%s] with [IMSI=%s], which does not match with the [current IMSI=%s].`
- `0x18004542a`: `Profile skipped: WwanGetDMConfigProfile returned for [profilename=%s] with [ICCID=%s], which does not match with the [current ICCID=%s].`
- `0x180045542`: `Profile skipped: WwanGetDMConfigProfile returned for [profilename=%s] with [IMSI=%s], which does not match with the [current IMSI=%s].`

## pseudocode

```c
int __fastcall CWwanTranslator::_QueryWwanProfilesForAdapter(
        CWwanTranslator *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const struct _tlgProvider_t *v7; // rax
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // rbx
  unsigned int v14; // eax
  int ProfileList; // eax
  bool v17; // sf
  unsigned int v18; // edi
  unsigned int *v19; // rcx
  __m128i si128; // xmm6
  __int64 v21; // rbx
  int ProfileIstream; // eax
  bool v23; // sf
  const struct _tlgProvider_t *v24; // rax
  int v25; // r8d
  int v26; // r9d
  unsigned __int16 **v27; // rcx
  __int64 v28; // rcx
  const struct _tlgProvider_t *v29; // rax
  int v30; // r8d
  int v31; // r9d
  unsigned __int16 *v32; // rax
  int v33; // ecx
  int v34; // edx
  const struct _tlgProvider_t *v35; // rax
  int v36; // r8d
  int v37; // r9d
  char *v38; // rax
  signed __int64 v39; // r8
  int v40; // ecx
  int v41; // edx
  const struct _tlgProvider_t *v42; // rax
  int v43; // r8d
  int v44; // r9d
  const struct _tlgProvider_t *v45; // rax
  int v46; // r8d
  int v47; // r9d
  __int64 v48; // r8
  _OWORD *v49; // rdx
  const struct _tlgProvider_t *v50; // rax
  int v51; // r8d
  int v52; // r9d
  __int64 v53; // r8
  _OWORD *v54; // rdx
  const struct _tlgProvider_t *v55; // rax
  int v56; // r8d
  int v57; // r9d
  int DMConfigProfileList; // eax
  signed int v59; // ebx
  unsigned int v60; // esi
  unsigned int *v61; // rdi
  unsigned int *v62; // rdi
  unsigned int DMConfigProfile; // eax
  unsigned __int16 *v64; // rax
  int v65; // ecx
  int v66; // edx
  const struct _tlgProvider_t *v67; // rax
  int v68; // r8d
  int v69; // r9d
  unsigned __int16 *v70; // rax
  const unsigned __int16 *v71; // r14
  int v72; // ecx
  int v73; // edx
  const struct _tlgProvider_t *v74; // rax
  int v75; // r8d
  int v76; // r9d
  _QWORD *v77; // rdx
  _QWORD *v78; // rdx
  const struct _tlgProvider_t *v79; // rax
  int v80; // r8d
  int v81; // r9d
  const struct _tlgProvider_t *v82; // rax
  int v83; // r8d
  int v84; // r9d
  __int64 v85; // rdx
  unsigned int *v86; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v87[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v88; // [rsp+40h] [rbp-C0h]
  unsigned int v89[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v90; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v91; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int *v92; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v93; // [rsp+68h] [rbp-98h] BYREF
  __int64 v94; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v95; // [rsp+78h] [rbp-88h]
  char v96; // [rsp+80h] [rbp-80h]
  int v97; // [rsp+88h] [rbp-78h] BYREF
  int v98; // [rsp+8Ch] [rbp-74h] BYREF
  const unsigned __int16 *v99; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v100[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v101; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v102[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v103; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v104[2]; // [rsp+C8h] [rbp-38h] BYREF
  __m128i v105; // [rsp+D8h] [rbp-28h]
  _QWORD v106[7]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD *v107; // [rsp+128h] [rbp+28h]
  _QWORD v108[7]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD *v109; // [rsp+168h] [rbp+68h]
  _BYTE v110[3112]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v111[1536]; // [rsp+D98h] [rbp+C98h] BYREF
  _WORD v112[836]; // [rsp+1398h] [rbp+1298h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A88h] [rbp+1988h]

  v99 = a4;
  *(_OWORD *)v100 = 0;
  v101 = 0;
  *(_OWORD *)v102 = 0;
  v103 = 0;
  std::vector<unsigned short>::resize(v100);
  std::vector<unsigned short>::resize(v102);
  StringCchPrintfW(v100[0], v100[1] - v100[0], L"Enter");
  LODWORD(v86) = 1932;
  StringCchPrintfW(v102[0], v102[1] - v102[0], L"%S(%d):%s", "CWwanTranslator::_QueryWwanProfilesForAdapter");
  v7 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    *(unsigned __int16 **)v89 = v102[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v7,
      (unsigned int)&word_180076DDE,
      v8,
      v9,
      (__int64)v89);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v102);
  std::vector<unsigned short>::~vector<unsigned short>(v100);
  v94 = 0;
  v10 = *((_QWORD *)this + 12);
  v11 = *((_QWORD *)this + 11);
  if ( v11 != v10 )
  {
    do
    {
      std::wstring::~wstring(v11);
      v11 += 32;
    }
    while ( v11 != v10 );
    *((_QWORD *)this + 12) = *((_QWORD *)this + 11);
  }
  v12 = *((_QWORD *)this + 15);
  v13 = *((_QWORD *)this + 14);
  if ( v13 != v12 )
  {
    do
    {
      std::wstring::~wstring(v13);
      v13 += 32;
    }
    while ( v13 != v12 );
    *((_QWORD *)this + 15) = *((_QWORD *)this + 14);
  }
  v97 = 0;
  v14 = WwanOpenHandle(1, 0, &v97, &v94);
  if ( v14 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x796,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
             (const char *)v14,
             (unsigned int)v86);
  v100[0] = (unsigned __int16 *)&v94;
  LOBYTE(v100[1]) = 1;
  v92 = 0;
  v102[0] = (unsigned __int16 *)&v92;
  LOBYTE(v102[1]) = 1;
  ProfileList = WwanGetProfileList(v94, a2, 0, &v92);
  v17 = ProfileList < 0;
  if ( ProfileList > 0 )
    v17 = 1;
  if ( !v17 )
  {
    v18 = 0;
    v19 = v92;
    if ( *v92 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        v91 = 0;
        *(_QWORD *)v89 = 0;
        v95 = v89;
        v96 = 1;
        v98 = 0;
        v21 = 129LL * v18;
        ProfileIstream = WwanGetProfileIstream(v94, &v19[v21 + 1], &v98, &v91, v89);
        v23 = ProfileIstream < 0;
        if ( ProfileIstream > 0 )
          v23 = 1;
        if ( v23 )
        {
          *(_OWORD *)v104 = 0;
          v105.m128i_i64[0] = 0;
          *(_OWORD *)v87 = 0;
          v88 = 0;
          std::vector<unsigned short>::resize(v104);
          std::vector<unsigned short>::resize(v87);
          StringCchPrintfW(
            v104[0],
            v104[1] - v104[0],
            L"Profile skipped: WwanGetProfileIstream failed for [profilename=%s].",
            &v92[v21 + 1]);
          LODWORD(v86) = 1972;
          StringCchPrintfW(v87[0], v87[1] - v87[0], L"%S(%d):%s", "CWwanTranslator::_QueryWwanProfilesForAdapter");
          v24 = MbaeApiLogging::Provider();
          if ( *(_DWORD *)v24 > 3u )
          {
            v90 = v87[0];
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (_DWORD)v24,
              (unsigned int)byte_180076DBB,
              v25,
              v26,
              (__int64)&v90);
          }
          std::vector<unsigned short>::~vector<unsigned short>(v87);
          v27 = v104;
        }
        else
        {
          if ( v91 >= 0x18D8 )
          {
            v32 = (unsigned __int16 *)(*(_QWORD *)v89 + 3112LL);
            do
            {
              v33 = *(unsigned __int16 *)((char *)a3 + (_QWORD)v32 - *(_QWORD *)v89 - 3112);
              v34 = *v32 - v33;
              if ( v34 )
                break;
              ++v32;
            }
            while ( v33 );
            if ( v34 )
            {
              *(_OWORD *)v87 = 0;
              v88 = 0;
              *(_OWORD *)v104 = 0;
              v105.m128i_i64[0] = 0;
              std::vector<unsigned short>::resize(v87);
              std::vector<unsigned short>::resize(v104);
              StringCchPrintfW(
                v87[0],
                v87[1] - v87[0],
                L"Profile skipped: WwanGetProfileIstream returned for [profilename=%s] with [ICCID=%s], which does not mat"
                 "ch with the [current ICCID=%s].",
                &v92[v21 + 1],
                *(_QWORD *)v89 + 3112LL,
                a3);
              LODWORD(v86) = 1990;
              StringCchPrintfW(
                v104[0],
                v104[1] - v104[0],
                L"%S(%d):%s",
                "CWwanTranslator::_QueryWwanProfilesForAdapter");
              v35 = MbaeApiLogging::Provider();
              if ( *(_DWORD *)v35 > 4u )
              {
                v90 = v104[0];
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                  (_DWORD)v35,
                  (unsigned int)byte_180076D9B,
                  v36,
                  v37,
                  (__int64)&v90);
              }
            }
            else
            {
              v38 = (char *)(*(_QWORD *)v89 + 4648LL);
              if ( !*(_WORD *)(*(_QWORD *)v89 + 4648LL) )
                goto LABEL_42;
              v39 = (char *)v99 - v38;
              do
              {
                v40 = *(unsigned __int16 *)&v38[v39];
                v41 = *(unsigned __int16 *)v38 - v40;
                if ( v41 )
                  break;
                v38 += 2;
              }
              while ( v40 );
              if ( !v41 )
              {
LABEL_42:
                CWwanTranslator::_ProcessWwanProfile((__int64)this, (__int64)a2, 3, *(__int64 *)v89, 0);
                *(_OWORD *)v87 = 0;
                v88 = 0;
                *(_OWORD *)v104 = 0;
                v105.m128i_i64[0] = 0;
                std::vector<unsigned short>::resize(v87);
                std::vector<unsigned short>::resize(v104);
                StringCchPrintfW(
                  v87[0],
                  v87[1] - v87[0],
                  L"Process one manual profile with [profilename=%s]",
                  *(_QWORD *)v89);
                LODWORD(v86) = 2009;
                StringCchPrintfW(
                  v104[0],
                  v104[1] - v104[0],
                  L"%S(%d):%s",
                  "CWwanTranslator::_QueryWwanProfilesForAdapter");
                v45 = MbaeApiLogging::Provider();
                if ( *(_DWORD *)v45 > 4u )
                {
                  v90 = v104[0];
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                    (_DWORD)v45,
                    (unsigned int)qword_180076D58,
                    v46,
                    v47,
                    (__int64)&v90);
                }
                std::vector<unsigned short>::~vector<unsigned short>(v104);
                std::vector<unsigned short>::~vector<unsigned short>(v87);
                v28 = *(_QWORD *)v89;
                if ( *(_DWORD *)(*(_QWORD *)v89 + 3076LL) > 1u )
                {
                  if ( (*(_BYTE *)(*(_QWORD *)v89 + 5536LL) & 8) != 0 )
                  {
                    *(_OWORD *)v104 = 0;
                    v105 = 0;
                    v48 = -1;
                    do
                      ++v48;
                    while ( *(_WORD *)(*(_QWORD *)v89 + 2 * v48) );
                    std::wstring::_Construct<1,unsigned short const *>(v104, *(_QWORD *)v89);
                    v49 = (_OWORD *)*((_QWORD *)this + 12);
                    if ( v49 == *((_OWORD **)this + 13) )
                    {
                      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>((char *)this + 88, v49, v104);
                    }
                    else
                    {
                      *v49 = *(_OWORD *)v104;
                      v49[1] = v105;
                      v105 = si128;
                      LOWORD(v104[0]) = 0;
                      *((_QWORD *)this + 12) += 32LL;
                    }
                    std::wstring::~wstring(v104);
                    *(_OWORD *)v87 = 0;
                    v88 = 0;
                    *(_OWORD *)v104 = 0;
                    v105.m128i_i64[0] = 0;
                    std::vector<unsigned short>::resize(v87);
                    std::vector<unsigned short>::resize(v104);
                    StringCchPrintfW(
                      v87[0],
                      v87[1] - v87[0],
                      L"Import one provisioned Internet profile with [profilename=%s]",
                      *(_QWORD *)v89);
                    LODWORD(v86) = 2019;
                    StringCchPrintfW(
                      v104[0],
                      v104[1] - v104[0],
                      L"%S(%d):%s",
                      "CWwanTranslator::_QueryWwanProfilesForAdapter");
                    v50 = MbaeApiLogging::Provider();
                    if ( *(_DWORD *)v50 > 4u )
                    {
                      v90 = v104[0];
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                        (_DWORD)v50,
                        (unsigned int)qword_180076CF8,
                        v51,
                        v52,
                        (__int64)&v90);
                    }
                    std::vector<unsigned short>::~vector<unsigned short>(v104);
                    std::vector<unsigned short>::~vector<unsigned short>(v87);
                    v28 = *(_QWORD *)v89;
                  }
                  if ( (*(_BYTE *)(v28 + 5536) & 2) != 0 )
                  {
                    *(_OWORD *)v104 = 0;
                    v105 = 0;
                    v53 = -1;
                    do
                      ++v53;
                    while ( *(_WORD *)(v28 + 2 * v53) );
                    std::wstring::_Construct<1,unsigned short const *>(v104, v28);
                    v54 = (_OWORD *)*((_QWORD *)this + 15);
                    if ( v54 == *((_OWORD **)this + 16) )
                    {
                      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>((char *)this + 112, v54, v104);
                    }
                    else
                    {
                      *v54 = *(_OWORD *)v104;
                      v54[1] = v105;
                      v105 = si128;
                      LOWORD(v104[0]) = 0;
                      *((_QWORD *)this + 15) += 32LL;
                    }
                    std::wstring::~wstring(v104);
                    *(_OWORD *)v87 = 0;
                    v88 = 0;
                    *(_OWORD *)v104 = 0;
                    v105.m128i_i64[0] = 0;
                    std::vector<unsigned short>::resize(v87);
                    std::vector<unsigned short>::resize(v104);
                    StringCchPrintfW(
                      v87[0],
                      v87[1] - v87[0],
                      L"Import one provisioned MMS profile with [profilename=%s]",
                      *(_QWORD *)v89);
                    LODWORD(v86) = 2026;
                    StringCchPrintfW(
                      v104[0],
                      v104[1] - v104[0],
                      L"%S(%d):%s",
                      "CWwanTranslator::_QueryWwanProfilesForAdapter");
                    v55 = MbaeApiLogging::Provider();
                    if ( *(_DWORD *)v55 > 4u )
                    {
                      v90 = v104[0];
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                        (_DWORD)v55,
                        (unsigned int)qword_180076D18,
                        v56,
                        v57,
                        (__int64)&v90);
                    }
                    std::vector<unsigned short>::~vector<unsigned short>(v104);
                    std::vector<unsigned short>::~vector<unsigned short>(v87);
                    v28 = *(_QWORD *)v89;
                  }
                }
                goto LABEL_63;
              }
              *(_OWORD *)v87 = 0;
              v88 = 0;
              *(_OWORD *)v104 = 0;
              v105.m128i_i64[0] = 0;
              std::vector<unsigned short>::resize(v87);
              std::vector<unsigned short>::resize(v104);
              StringCchPrintfW(
                v87[0],
                v87[1] - v87[0],
                L"Profile skipped: WwanGetProfileIstream returned for [profilename=%s] with [IMSI=%s], which does not matc"
                 "h with the [current IMSI=%s].",
                &v92[v21 + 1],
                *(_QWORD *)v89 + 4648LL,
                v99);
              LODWORD(v86) = 2002;
              StringCchPrintfW(
                v104[0],
                v104[1] - v104[0],
                L"%S(%d):%s",
                "CWwanTranslator::_QueryWwanProfilesForAdapter");
              v42 = MbaeApiLogging::Provider();
              if ( *(_DWORD *)v42 > 4u )
              {
                v90 = v104[0];
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                  (_DWORD)v42,
                  (unsigned int)qword_180076D38,
                  v43,
                  v44,
                  (__int64)&v90);
              }
            }
          }
          else
          {
            *(_OWORD *)v87 = 0;
            v88 = 0;
            *(_OWORD *)v104 = 0;
            v105.m128i_i64[0] = 0;
            std::vector<unsigned short>::resize(v87);
            std::vector<unsigned short>::resize(v104);
            StringCchPrintfW(
              v87[0],
              v87[1] - v87[0],
              L"Profile skipped: WwanGetProfileIstream returned bad size for [profilename=%s].",
              &v92[v21 + 1]);
            LODWORD(v86) = 1979;
            StringCchPrintfW(v104[0], v104[1] - v104[0], L"%S(%d):%s", "CWwanTranslator::_QueryWwanProfilesForAdapter");
            v29 = MbaeApiLogging::Provider();
            if ( *(_DWORD *)v29 > 3u )
            {
              v90 = v104[0];
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                (_DWORD)v29,
                (unsigned int)qword_180076D78,
                v30,
                v31,
                (__int64)&v90);
            }
          }
          std::vector<unsigned short>::~vector<unsigned short>(v104);
          v27 = v87;
        }
        std::vector<unsigned short>::~vector<unsigned short>(v27);
        v28 = *(_QWORD *)v89;
LABEL_63:
        v96 = 0;
        WwanFreeMemory(v28);
        ++v18;
        v19 = v92;
      }
      while ( v18 < *v92 );
    }
  }
  v93 = 0;
  v95 = (unsigned int *)&v93;
  v96 = 1;
  DMConfigProfileList = WwanGetDMConfigProfileList(v94, a2, &v93);
  v59 = DMConfigProfileList;
  if ( DMConfigProfileList > 0 )
    v59 = (unsigned __int16)DMConfigProfileList | 0x80070000;
  if ( v59 < 0 || (v60 = 0, v61 = v93, !*v93) )
  {
LABEL_89:
    v106[0] = off_18005EF18;
    v106[1] = this;
    v106[2] = a2;
    v107 = v106;
    CWwanTranslator::SafelyNotify(this, v106);
    if ( v107 )
    {
      v77 = v106;
      LOBYTE(v77) = v107 != v106;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v107 + 32LL))(v107, v77);
    }
    v108[0] = off_18005EF48;
    v108[1] = this;
    v108[2] = a2;
    v109 = v108;
    CWwanTranslator::SafelyNotify(this, v108);
    if ( v109 )
    {
      v78 = v108;
      LOBYTE(v78) = v109 != v108;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v109 + 32LL))(v109, v78);
    }
    if ( v59 == -2147023728 )
    {
      *(_OWORD *)v87 = 0;
      v88 = 0;
      *(_OWORD *)v104 = 0;
      v105.m128i_i64[0] = 0;
      std::vector<unsigned short>::resize(v87);
      std::vector<unsigned short>::resize(v104);
      StringCchPrintfW(v87[0], v87[1] - v87[0], L"No profile found by Wwansvc.");
      LODWORD(v86) = 2105;
      StringCchPrintfW(
        v104[0],
        v104[1] - v104[0],
        L"%S(%d):%s",
        "CWwanTranslator::_QueryWwanProfilesForAdapter",
        v86,
        v87[0]);
      v79 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v79 > 4u )
      {
        v90 = v104[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v79,
          (unsigned int)qword_180076CB8,
          v80,
          v81,
          (__int64)&v90);
      }
      std::vector<unsigned short>::~vector<unsigned short>(v104);
      std::vector<unsigned short>::~vector<unsigned short>(v87);
      v59 = 0;
    }
    *(_OWORD *)v87 = 0;
    v88 = 0;
    *(_OWORD *)v104 = 0;
    v105.m128i_i64[0] = 0;
    std::vector<unsigned short>::resize(v87);
    std::vector<unsigned short>::resize(v104);
    StringCchPrintfW(v87[0], v87[1] - v87[0], L"Exit");
    LODWORD(v86) = 2109;
    StringCchPrintfW(
      v104[0],
      v104[1] - v104[0],
      L"%S(%d):%s",
      "CWwanTranslator::_QueryWwanProfilesForAdapter",
      v86,
      v87[0]);
    v82 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v82 > 5u )
    {
      v90 = v104[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v82,
        (unsigned int)byte_180076C75,
        v83,
        v84,
        (__int64)&v90);
    }
    std::vector<unsigned short>::~vector<unsigned short>(v104);
    std::vector<unsigned short>::~vector<unsigned short>(v87);
    goto LABEL_100;
  }
  while ( 1 )
  {
    *(_QWORD *)v89 = 0;
    memset_0(v110, 0, 0x18B0u);
    v91 = 0;
    v62 = &v61[129 * v60 + 1];
    DMConfigProfile = WwanGetDMConfigProfile(v94, a2, v62, v89);
    if ( DMConfigProfile )
      break;
    v86 = &v91;
    DMConfigProfile = WwanProfileLoadXml(v110, *(_QWORD *)v89, 0, 0);
    if ( DMConfigProfile )
    {
      v85 = 2055;
      goto LABEL_105;
    }
    if ( v91 )
    {
      v59 = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x809,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
        (const char *)0x80004005LL,
        (int)&v91);
      goto LABEL_100;
    }
    v64 = (unsigned __int16 *)v111;
    do
    {
      v65 = *(unsigned __int16 *)((char *)v64 + (char *)a3 - v111);
      v66 = *v64 - v65;
      if ( v66 )
        break;
      ++v64;
    }
    while ( v65 );
    if ( v66 )
    {
      *(_OWORD *)v87 = 0;
      v88 = 0;
      *(_OWORD *)v104 = 0;
      v105.m128i_i64[0] = 0;
      std::vector<unsigned short>::resize(v87);
      std::vector<unsigned short>::resize(v104);
      StringCchPrintfW(
        v87[0],
        v87[1] - v87[0],
        L"Profile skipped: WwanGetDMConfigProfile returned for [profilename=%s] with [ICCID=%s], which does not match with"
         " the [current ICCID=%s].",
        v62,
        v111,
        a3);
      LODWORD(v86) = 2066;
      StringCchPrintfW(v104[0], v104[1] - v104[0], L"%S(%d):%s", "CWwanTranslator::_QueryWwanProfilesForAdapter");
      v67 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v67 > 4u )
      {
        v90 = v104[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v67,
          (unsigned int)qword_180076CD8,
          v68,
          v69,
          (__int64)&v90);
      }
    }
    else
    {
      if ( !v112[0] )
        goto LABEL_86;
      v70 = v112;
      v71 = v99;
      do
      {
        v72 = *(unsigned __int16 *)((char *)v70 + (char *)v99 - (char *)v112);
        v73 = *v70 - v72;
        if ( v73 )
          break;
        ++v70;
      }
      while ( v72 );
      if ( !v73 )
      {
LABEL_86:
        CWwanTranslator::_ProcessWwanProfile((__int64)this, (__int64)a2, 3, (__int64)v110, 1);
        if ( *(_QWORD *)v89 )
          WwanFreeMemory(*(_QWORD *)v89);
        goto LABEL_88;
      }
      *(_OWORD *)v87 = 0;
      v88 = 0;
      *(_OWORD *)v104 = 0;
      v105.m128i_i64[0] = 0;
      std::vector<unsigned short>::resize(v87);
      std::vector<unsigned short>::resize(v104);
      StringCchPrintfW(
        v87[0],
        v87[1] - v87[0],
        L"Profile skipped: WwanGetDMConfigProfile returned for [profilename=%s] with [IMSI=%s], which does not match with "
         "the [current IMSI=%s].",
        v62,
        v112,
        v71);
      LODWORD(v86) = 2078;
      StringCchPrintfW(v104[0], v104[1] - v104[0], L"%S(%d):%s", "CWwanTranslator::_QueryWwanProfilesForAdapter");
      v74 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v74 > 4u )
      {
        v90 = v104[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v74,
          (unsigned int)qword_180076C98,
          v75,
          v76,
          (__int64)&v90);
      }
    }
    std::vector<unsigned short>::~vector<unsigned short>(v104);
    std::vector<unsigned short>::~vector<unsigned short>(v87);
LABEL_88:
    ++v60;
    v61 = v93;
    if ( v60 >= *v93 )
      goto LABEL_89;
  }
  v85 = 2053;
LABEL_105:
  v59 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v85,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
          (const char *)DMConfigProfile,
          (unsigned int)v86);
LABEL_100:
  if ( v93 )
    WwanFreeMemory(v93);
  WwanFreeMemory(v92);
  WwanCloseHandle(v94, 0);
  return v59;
}

```

## disassembly

```asm
0x180044954  push    rbp
0x180044956  push    rbx
0x180044957  push    rsi
0x180044958  push    rdi
0x180044959  push    r12
0x18004495b  push    r13
0x18004495d  push    r14
0x18004495f  push    r15
0x180044961  lea     rbp, [rsp-1948h]
0x180044969  mov     eax, 1A48h
0x18004496e  call    _alloca_probe
0x180044973  sub     rsp, rax
0x180044976  movaps  [rsp+1A80h+var_50], xmm6
0x18004497e  mov     rax, cs:__security_cookie
0x180044985  xor     rax, rsp
0x180044988  mov     [rbp+1980h+var_60], rax
0x18004498f  mov     [rbp+1980h+var_19F0], r9
0x180044993  mov     r13, r8
0x180044996  mov     r12, rdx
0x180044999  mov     r15, rcx
0x18004499c  xorps   xmm0, xmm0
0x18004499f  movdqu  xmmword ptr [rbp+1980h+var_19E8], xmm0
0x1800449a4  xor     ebx, ebx
0x1800449a6  mov     [rbp+1980h+var_19D8], rbx
0x1800449aa  movdqu  xmmword ptr [rbp+1980h+var_19D0], xmm0
0x1800449af  mov     [rbp+1980h+var_19C0], rbx
0x1800449b3  lea     rcx, [rbp+1980h+var_19E8]
0x1800449b7  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800449bc  lea     rcx, [rbp+1980h+var_19D0]
0x1800449c0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800449c5  mov     rdx, [rbp+1980h+var_19E8+8]
0x1800449c9  mov     rcx, [rbp+1980h+var_19E8]; unsigned __int16 *
0x1800449cd  sub     rdx, rcx
0x1800449d0  sar     rdx, 1; unsigned __int64
0x1800449d3  lea     r8, aEnter; "Enter"
0x1800449da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800449df  mov     rdx, [rbp+1980h+var_19D0+8]
0x1800449e3  mov     rcx, [rbp+1980h+var_19D0]; unsigned __int16 *
0x1800449e7  sub     rdx, rcx
0x1800449ea  sar     rdx, 1; unsigned __int64
0x1800449ed  mov     rax, [rbp+1980h+var_19E8]
0x1800449f1  mov     [rsp+1A80h+var_1A58], rax
0x1800449f6  mov     [rsp+1A80h+var_1A60], 78Ch
0x1800449fe  lea     r9, aCwwantranslato_41; "CWwanTranslator::_QueryWwanProfilesForA"...
0x180044a05  lea     r8, aSDS; "%S(%d):%s"
0x180044a0c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044a11  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180044a16  mov     ecx, [rax]
0x180044a18  cmp     ecx, 5
0x180044a1b  jbe     short loc_180044A40
0x180044a1d  mov     rcx, [rbp+1980h+var_19D0]
0x180044a21  mov     qword ptr [rsp+1A80h+var_1A38], rcx
0x180044a26  lea     rcx, [rsp+1A80h+var_1A38]
0x180044a2b  mov     qword ptr [rsp+1A80h+var_1A60], rcx; unsigned int
0x180044a30  lea     rdx, word_180076DDE
0x180044a37  mov     rcx, rax
0x180044a3a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180044a3f  nop
0x180044a40  lea     rcx, [rbp+1980h+var_19D0]
0x180044a44  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180044a49  nop
0x180044a4a  lea     rcx, [rbp+1980h+var_19E8]
0x180044a4e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180044a53  mov     [rsp+1A80h+var_1A10], rbx
0x180044a58  lea     r14, [r15+58h]
0x180044a5c  mov     rdi, [r14+8]
0x180044a60  mov     rbx, [r14]
0x180044a63  cmp     rbx, rdi
0x180044a66  jz      short loc_180044A80
0x180044a68  mov     rcx, rbx
0x180044a6b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044a70  add     rbx, 20h ; ' '
0x180044a74  cmp     rbx, rdi
0x180044a77  jnz     short loc_180044A68
0x180044a79  mov     rax, [r14]
0x180044a7c  mov     [r14+8], rax
0x180044a80  lea     rsi, [r15+70h]
0x180044a84  mov     rdi, [rsi+8]
0x180044a88  mov     rbx, [rsi]
0x180044a8b  cmp     rbx, rdi
0x180044a8e  jz      short loc_180044AA8
0x180044a90  mov     rcx, rbx
0x180044a93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044a98  add     rbx, 20h ; ' '
0x180044a9c  cmp     rbx, rdi
0x180044a9f  jnz     short loc_180044A90
0x180044aa1  mov     rax, [rsi]
0x180044aa4  mov     [rsi+8], rax
0x180044aa8  xor     ebx, ebx
0x180044aaa  mov     [rbp+1980h+var_19F8], ebx
0x180044aad  lea     r9, [rsp+1A80h+var_1A10]
0x180044ab2  lea     r8, [rbp+1980h+var_19F8]
0x180044ab6  xor     edx, edx
0x180044ab8  lea     ecx, [rbx+1]
0x180044abb  call    cs:__imp_WwanOpenHandle
0x180044ac1  test    eax, eax
0x180044ac3  jz      short loc_180044AE5
0x180044ac5  mov     rcx, [rbp+1988h]; this
0x180044acc  mov     r9d, eax; char *
0x180044acf  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180044ad6  mov     edx, 796h; void *
0x180044adb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180044ae0  jmp     loc_180045847
0x180044ae5  lea     rax, [rsp+1A80h+var_1A10]
0x180044aea  mov     [rbp+1980h+var_19E8], rax
0x180044aee  mov     byte ptr [rbp+1980h+var_19E8+8], 1
0x180044af2  mov     [rsp+1A80h+var_1A20], rbx
0x180044af7  lea     rax, [rsp+1A80h+var_1A20]
0x180044afc  mov     [rbp+1980h+var_19D0], rax
0x180044b00  mov     byte ptr [rbp+1980h+var_19D0+8], 1
0x180044b04  lea     r9, [rsp+1A80h+var_1A20]
0x180044b09  xor     r8d, r8d
0x180044b0c  mov     rdx, r12
0x180044b0f  mov     rcx, [rsp+1A80h+var_1A10]
0x180044b14  call    cs:__imp_WwanGetProfileList
0x180044b1a  test    eax, eax
0x180044b1c  jle     short loc_180044B28
0x180044b1e  movzx   eax, ax
0x180044b21  or      eax, 80070000h
0x180044b26  test    eax, eax
0x180044b28  js      loc_1800452DF
0x180044b2e  mov     edi, ebx
0x180044b30  mov     rcx, [rsp+1A80h+var_1A20]
0x180044b35  cmp     [rcx], ebx
0x180044b37  jbe     loc_1800452DF
0x180044b3d  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180044b45  mov     [rsp+1A80h+var_1A28], ebx
0x180044b49  mov     qword ptr [rsp+1A80h+var_1A38], rbx
0x180044b4e  lea     rax, [rsp+1A80h+var_1A38]
0x180044b53  mov     [rsp+1A80h+var_1A08], rax
0x180044b58  mov     [rbp+1980h+var_1A00], 1
0x180044b5c  mov     [rbp+1980h+var_19F4], ebx
0x180044b5f  mov     eax, edi
0x180044b61  imul    rbx, rax, 204h
0x180044b68  lea     rdx, [rcx+4]
0x180044b6c  add     rdx, rbx
0x180044b6f  lea     rax, [rsp+1A80h+var_1A38]
0x180044b74  mov     qword ptr [rsp+1A80h+var_1A60], rax
0x180044b79  lea     r9, [rsp+1A80h+var_1A28]
0x180044b7e  lea     r8, [rbp+1980h+var_19F4]
0x180044b82  mov     rcx, [rsp+1A80h+var_1A10]
0x180044b87  call    cs:__imp_WwanGetProfileIstream
0x180044b8d  xor     r10d, r10d
0x180044b90  test    eax, eax
0x180044b92  jle     short loc_180044B9E
0x180044b94  movzx   eax, ax
0x180044b97  or      eax, 80070000h
0x180044b9c  test    eax, eax
0x180044b9e  jns     loc_180044C79
0x180044ba4  xorps   xmm0, xmm0
0x180044ba7  movdqu  xmmword ptr [rbp+1980h+var_19B8], xmm0
0x180044bac  mov     qword ptr [rbp+1980h+var_19A8], r10
0x180044bb0  movdqu  xmmword ptr [rsp+1A80h+var_1A50], xmm0
0x180044bb6  mov     [rsp+1A80h+var_1A40], r10
0x180044bbb  lea     rcx, [rbp+1980h+var_19B8]
0x180044bbf  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180044bc4  lea     rcx, [rsp+1A80h+var_1A50]
0x180044bc9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180044bce  mov     r9, [rsp+1A80h+var_1A20]
0x180044bd3  add     r9, 4
0x180044bd7  add     r9, rbx
0x180044bda  mov     rdx, [rbp+1980h+var_19B8+8]
0x180044bde  mov     rcx, [rbp+1980h+var_19B8]; unsigned __int16 *
0x180044be2  sub     rdx, rcx
0x180044be5  sar     rdx, 1; unsigned __int64
0x180044be8  lea     r8, aProfileSkipped_2; "Profile skipped: WwanGetProfileIstream "...
0x180044bef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044bf4  mov     rdx, [rsp+1A80h+var_1A50+8]
0x180044bf9  mov     rcx, [rsp+1A80h+var_1A50]; unsigned __int16 *
0x180044bfe  sub     rdx, rcx
0x180044c01  sar     rdx, 1; unsigned __int64
0x180044c04  mov     rax, [rbp+1980h+var_19B8]
0x180044c08  mov     [rsp+1A80h+var_1A58], rax
0x180044c0d  mov     [rsp+1A80h+var_1A60], 7B4h
0x180044c15  lea     r9, aCwwantranslato_41; "CWwanTranslator::_QueryWwanProfilesForA"...
0x180044c1c  lea     r8, aSDS; "%S(%d):%s"
0x180044c23  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044c28  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180044c2d  mov     ecx, [rax]
0x180044c2f  cmp     ecx, 3
0x180044c32  jbe     short loc_180044C58
0x180044c34  mov     rcx, [rsp+1A80h+var_1A50]
0x180044c39  mov     [rsp+1A80h+var_1A30], rcx
0x180044c3e  lea     rcx, [rsp+1A80h+var_1A30]
0x180044c43  mov     qword ptr [rsp+1A80h+var_1A60], rcx
0x180044c48  lea     rdx, byte_180076DBB
0x180044c4f  mov     rcx, rax
0x180044c52  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180044c57  nop
0x180044c58  lea     rcx, [rsp+1A80h+var_1A50]
0x180044c5d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180044c62  nop
0x180044c63  lea     rcx, [rbp+1980h+var_19B8]
0x180044c67  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180044c6c  nop
0x180044c6d  xor     ebx, ebx
0x180044c6f  mov     rcx, qword ptr [rsp+1A80h+var_1A38]
0x180044c74  jmp     loc_1800452C7
0x180044c79  cmp     [rsp+1A80h+var_1A28], 18D8h
0x180044c81  jnb     loc_180044D4F
0x180044c87  xorps   xmm0, xmm0
0x180044c8a  movdqu  xmmword ptr [rsp+1A80h+var_1A50], xmm0
0x180044c90  mov     [rsp+1A80h+var_1A40], r10
0x180044c95  movdqu  xmmword ptr [rbp+1980h+var_19B8], xmm0
0x180044c9a  mov     qword ptr [rbp+1980h+var_19A8], r10
0x180044c9e  lea     rcx, [rsp+1A80h+var_1A50]
0x180044ca3  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180044ca8  lea     rcx, [rbp+1980h+var_19B8]
0x180044cac  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180044cb1  mov     r9, [rsp+1A80h+var_1A20]
0x180044cb6  add     r9, 4
0x180044cba  add     r9, rbx
0x180044cbd  mov     rdx, [rsp+1A80h+var_1A50+8]
0x180044cc2  mov     rcx, [rsp+1A80h+var_1A50]; unsigned __int16 *
0x180044cc7  sub     rdx, rcx
0x180044cca  sar     rdx, 1; unsigned __int64
0x180044ccd  lea     r8, aProfileSkipped_1; "Profile skipped: WwanGetProfileIstream "...
0x180044cd4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044cd9  mov     rdx, [rbp+1980h+var_19B8+8]
0x180044cdd  mov     rcx, [rbp+1980h+var_19B8]; unsigned __int16 *
0x180044ce1  sub     rdx, rcx
0x180044ce4  sar     rdx, 1; unsigned __int64
0x180044ce7  mov     rax, [rsp+1A80h+var_1A50]
0x180044cec  mov     [rsp+1A80h+var_1A58], rax
0x180044cf1  mov     [rsp+1A80h+var_1A60], 7BBh
0x180044cf9  lea     r9, aCwwantranslato_41; "CWwanTranslator::_QueryWwanProfilesForA"...
0x180044d00  lea     r8, aSDS; "%S(%d):%s"
0x180044d07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044d0c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180044d11  mov     ecx, [rax]
0x180044d13  cmp     ecx, 3
0x180044d16  jbe     short loc_180044D3B
0x180044d18  mov     rcx, [rbp+1980h+var_19B8]
0x180044d1c  mov     [rsp+1A80h+var_1A30], rcx
0x180044d21  lea     rcx, [rsp+1A80h+var_1A30]
0x180044d26  mov     qword ptr [rsp+1A80h+var_1A60], rcx
0x180044d2b  lea     rdx, qword_180076D78
0x180044d32  mov     rcx, rax
0x180044d35  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180044d3a  nop
0x180044d3b  lea     rcx, [rbp+1980h+var_19B8]
0x180044d3f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180044d44  nop
0x180044d45  lea     rcx, [rsp+1A80h+var_1A50]
0x180044d4a  jmp     loc_180044C67
0x180044d4f  mov     r9, qword ptr [rsp+1A80h+var_1A38]
0x180044d54  lea     rax, [r9+0C28h]
0x180044d5b  mov     r8, r13
0x180044d5e  sub     r8, rax
0x180044d61  movzx   edx, word ptr [rax]
0x180044d64  movzx   ecx, word ptr [rax+r8]
0x180044d69  sub     edx, ecx
0x180044d6b  jnz     short loc_180044D75
0x180044d6d  add     rax, 2
0x180044d71  test    ecx, ecx
0x180044d73  jnz     short loc_180044D61
0x180044d75  test    edx, edx
0x180044d77  jz      loc_180044E56
0x180044d7d  xorps   xmm0, xmm0
0x180044d80  movdqu  xmmword ptr [rsp+1A80h+var_1A50], xmm0
0x180044d86  mov     [rsp+1A80h+var_1A40], r10
0x180044d8b  movdqu  xmmword ptr [rbp+1980h+var_19B8], xmm0
0x180044d90  mov     qword ptr [rbp+1980h+var_19A8], r10
0x180044d94  lea     rcx, [rsp+1A80h+var_1A50]
0x180044d99  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180044d9e  lea     rcx, [rbp+1980h+var_19B8]
0x180044da2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180044da7  mov     r8, qword ptr [rsp+1A80h+var_1A38]
0x180044dac  add     r8, 0C28h
0x180044db3  mov     r9, [rsp+1A80h+var_1A20]
0x180044db8  add     r9, 4
0x180044dbc  add     r9, rbx
0x180044dbf  mov     rdx, [rsp+1A80h+var_1A50+8]
0x180044dc4  mov     rcx, [rsp+1A80h+var_1A50]; unsigned __int16 *
0x180044dc9  sub     rdx, rcx
0x180044dcc  sar     rdx, 1; unsigned __int64
0x180044dcf  mov     [rsp+1A80h+var_1A58], r13
0x180044dd4  mov     qword ptr [rsp+1A80h+var_1A60], r8
0x180044dd9  lea     r8, aProfileSkipped_3; "Profile skipped: WwanGetProfileIstream "...
0x180044de0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044de5  mov     rdx, [rbp+1980h+var_19B8+8]
0x180044de9  mov     rcx, [rbp+1980h+var_19B8]; unsigned __int16 *
0x180044ded  sub     rdx, rcx
0x180044df0  sar     rdx, 1; unsigned __int64
0x180044df3  mov     rax, [rsp+1A80h+var_1A50]
0x180044df8  mov     [rsp+1A80h+var_1A58], rax
0x180044dfd  mov     [rsp+1A80h+var_1A60], 7C6h
0x180044e05  lea     r9, aCwwantranslato_41; "CWwanTranslator::_QueryWwanProfilesForA"...
0x180044e0c  lea     r8, aSDS; "%S(%d):%s"
0x180044e13  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044e18  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180044e1d  mov     ecx, [rax]
0x180044e1f  cmp     ecx, 4
0x180044e22  jbe     short loc_180044E47
0x180044e24  mov     rcx, [rbp+1980h+var_19B8]
0x180044e28  mov     [rsp+1A80h+var_1A30], rcx
0x180044e2d  lea     rcx, [rsp+1A80h+var_1A30]
0x180044e32  mov     qword ptr [rsp+1A80h+var_1A60], rcx
0x180044e37  lea     rdx, byte_180076D9B
0x180044e3e  mov     rcx, rax
  ... truncated ...
```
