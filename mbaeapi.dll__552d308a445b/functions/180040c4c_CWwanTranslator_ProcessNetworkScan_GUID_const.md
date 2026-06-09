# CWwanTranslator::_ProcessNetworkScan(_GUID const &)

- ea: `0x180040c4c`
- end: `0x180041624`
- name: `?_ProcessNetworkScan@CWwanTranslator@@AEAAJAEBU_GUID@@@Z`
- size: `2520`
- prototype: `int __fastcall(CWwanTranslator *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003812c`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180002efc`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x180032ca0`
- `0x18003320c`
- `0x18003351c`
- `0x18003994c`
- `0x18003d190`
- `0x180040c4c`
- `0x18005c010`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800415f6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800415f6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180040e74`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180041511`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800415e8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180040e74`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180041511`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800415e8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180040d57`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180040d57`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180040dcf`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180040dcf`

## pseudocode

```c
int __fastcall CWwanTranslator::_ProcessNetworkScan(CWwanTranslator *this, struct _GUID *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // eax
  unsigned int Interface; // eax
  unsigned int v10; // ebx
  unsigned int *v11; // rdx
  unsigned int v12; // eax
  _QWORD *v13; // rdx
  unsigned int *v14; // rbx
  unsigned int v15; // ecx
  __int64 v16; // rsi
  unsigned int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // r11
  int v20; // ecx
  int v21; // eax
  __int16 *v22; // r10
  __int64 v23; // rcx
  __int16 *v24; // r8
  __int64 v25; // rdx
  _WORD *v26; // rax
  __int16 v27; // r9
  _WORD *v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rdx
  _WORD *v31; // rax
  __int16 v32; // cx
  _WORD *v33; // rcx
  __int64 v34; // rcx
  __int16 *v35; // r9
  __int64 v36; // rdx
  _WORD *v37; // rax
  __int16 v38; // r8
  _WORD *v39; // rcx
  _WORD *v40; // r11
  __int64 v41; // rcx
  _WORD *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rdx
  _WORD *v45; // rax
  __int16 v46; // r8
  _WORD *v47; // rcx
  unsigned __int16 *v48; // rdx
  _QWORD *v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rsi
  unsigned int v52; // edi
  __int64 v53; // rdx
  __int64 v54; // r11
  int v55; // ecx
  int v56; // eax
  __int16 *v57; // r10
  __int64 v58; // rcx
  __int16 *v59; // r8
  __int64 v60; // rdx
  _WORD *v61; // rax
  __int16 v62; // r9
  _WORD *v63; // rcx
  __int64 v64; // r8
  __int64 v65; // rdx
  _WORD *v66; // rax
  __int16 v67; // cx
  _WORD *v68; // rcx
  __int64 v69; // rcx
  __int16 *v70; // r9
  __int64 v71; // rdx
  _WORD *v72; // rax
  __int16 v73; // r8
  _WORD *v74; // rcx
  _WORD *v75; // r11
  __int64 v76; // rcx
  _WORD *v77; // rax
  __int64 v78; // rcx
  __int64 v79; // rdx
  _WORD *v80; // rax
  __int16 v81; // r8
  _WORD *v82; // rcx
  unsigned __int16 *v83; // rdx
  const struct _tlgProvider_t *v84; // rax
  __int64 v85; // r8
  __int64 v86; // r9
  const struct _tlgProvider_t *v87; // rax
  __int64 v88; // r8
  __int64 v89; // r9
  unsigned int v90; // [rsp+20h] [rbp-E0h]
  unsigned int *v91; // [rsp+20h] [rbp-E0h]
  unsigned int v92[2]; // [rsp+20h] [rbp-E0h]
  unsigned int *v93; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v94[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v95; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v96; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v97[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v98; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v99[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v100; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v101[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v102; // [rsp+A0h] [rbp-60h]
  int v103; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v104; // [rsp+ACh] [rbp-54h] BYREF
  unsigned __int16 *v105[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v106; // [rsp+C0h] [rbp-40h]
  _QWORD v107[2]; // [rsp+C8h] [rbp-38h] BYREF
  char v108; // [rsp+D8h] [rbp-28h]
  __int128 v109; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v110; // [rsp+F0h] [rbp-10h]
  __int128 v111; // [rsp+100h] [rbp+0h]
  __int128 v112; // [rsp+110h] [rbp+10h]
  __int128 v113; // [rsp+120h] [rbp+20h] BYREF
  __int128 v114; // [rsp+130h] [rbp+30h]
  __int128 v115; // [rsp+140h] [rbp+40h]
  __int128 v116; // [rsp+150h] [rbp+50h] BYREF
  __int128 v117; // [rsp+160h] [rbp+60h]
  __int128 v118; // [rsp+170h] [rbp+70h] BYREF
  int v119; // [rsp+180h] [rbp+80h]
  _QWORD v120[7]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD *v121; // [rsp+1C8h] [rbp+C8h]
  _QWORD v122[7]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD *v123; // [rsp+208h] [rbp+108h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v96 = (unsigned __int16 *)a2;
  *(_OWORD *)v105 = 0;
  v106 = 0;
  *(_OWORD *)v94 = 0;
  v95 = 0;
  std::vector<unsigned short>::resize(v105);
  std::vector<unsigned short>::resize(v94);
  StringCchPrintfW(v105[0], v105[1] - v105[0], L"Enter");
  v90 = 2291;
  StringCchPrintfW(v94[0], v94[1] - v94[0], L"%S(%d):%s", "CWwanTranslator::_ProcessNetworkScan");
  v4 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    *(unsigned __int16 **)v97 = v94[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)&byte_180076AFF,
      v5,
      v6,
      (const unsigned __int16 **)v97);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v94);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v105);
  v98 = 0;
  v103 = 0;
  v7 = WwanOpenHandle(1, 0, &v103, &v98);
  if ( v7 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x8F5,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
             (const char *)v7,
             v90);
  v107[1] = &v98;
  v108 = 1;
  v93 = 0;
  v104 = 0;
  v105[0] = (unsigned __int16 *)&v93;
  LOBYTE(v105[1]) = 1;
  v91 = &v104;
  Interface = WwanQueryInterface(v98, a2, 7);
  if ( Interface )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x900,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
            (const char *)Interface,
            (unsigned int)&v104);
    goto LABEL_118;
  }
  v11 = v93;
  v12 = v93[359];
  if ( !v12 )
  {
    v122[0] = off_18005EEE8;
    v122[1] = this;
    v122[2] = a2;
    v123 = v122;
    CWwanTranslator::SafelyNotify(this, v122);
    if ( v123 )
    {
      v13 = v122;
      LOBYTE(v13) = v123 != v122;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v123 + 32LL))(v123, v13);
    }
    if ( v93 )
      WwanFreeMemory(v93);
    v10 = 0;
    goto LABEL_120;
  }
  if ( v12 != 1 )
  {
    v10 = 0;
LABEL_115:
    *(_OWORD *)v99 = 0;
    v100 = 0;
    *(_OWORD *)v101 = 0;
    v102 = 0;
    std::vector<unsigned short>::resize(v99);
    std::vector<unsigned short>::resize(v101);
    StringCchPrintfW(v99[0], v99[1] - v99[0], L"Exit");
    LODWORD(v91) = 2390;
    StringCchPrintfW(
      v101[0],
      v101[1] - v101[0],
      L"%S(%d):%s",
      "CWwanTranslator::_ProcessNetworkScan",
      v91,
      v99[0],
      0,
      0);
    v87 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v87 > 5u )
    {
      v96 = v101[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v87,
        (__int64)&dword_180076ADC,
        v88,
        v89,
        (const unsigned __int16 **)&v96);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v101);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v99);
    goto LABEL_118;
  }
  v14 = v93 + 352;
  v97[0] = v93[353];
  v15 = v97[0];
  *(_OWORD *)v94 = 0;
  v95 = 0;
  v107[0] = v97[0];
  if ( v97[0] )
  {
    std::vector<CellularSettingsOperatorInfo>::_Reallocate<0>(v94, v107);
    v11 = v93;
    v15 = v97[0];
  }
  if ( *v14 != 2 )
  {
    if ( *v14 != 10 )
    {
      *(_OWORD *)v101 = 0;
      v102 = 0;
      *(_OWORD *)v99 = 0;
      v100 = 0;
      std::vector<unsigned short>::resize(v101);
      std::vector<unsigned short>::resize(v99);
      StringCchPrintfW(
        v101[0],
        v101[1] - v101[0],
        L"Error element type of provider list (0x%x)",
        *v14,
        &v104,
        &v93,
        0,
        0);
      v92[0] = 2381;
      StringCchPrintfW(
        v99[0],
        v99[1] - v99[0],
        L"%S(%d):%s",
        "CWwanTranslator::_ProcessNetworkScan",
        *(_QWORD *)v92,
        v101[0]);
      v84 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v84 > 2u )
      {
        v96 = v99[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v84,
          (__int64)byte_180076ABB,
          v85,
          v86,
          (const unsigned __int16 **)&v96);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v99);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v101);
      std::vector<CellularSettingsOperatorInfo>::~vector<CellularSettingsOperatorInfo>(v94);
      if ( v93 )
        WwanFreeMemory(v93);
      v10 = -2147467259;
      goto LABEL_120;
    }
    v51 = (__int64)v11 + *((_QWORD *)v14 + 1);
    v10 = 0;
    v52 = 0;
    if ( v15 )
    {
      while ( 1 )
      {
        memset_0((char *)&v109 + 8, 0, 0x9Cu);
        v53 = 80LL * v52;
        v54 = v53 + v51;
        v55 = *(_DWORD *)(v53 + v51 + 16);
        v56 = 1;
        if ( v55 )
        {
          if ( (v55 & 0x10) != 0 )
          {
            v56 = 3;
          }
          else if ( (v55 & 2) != 0 )
          {
            v56 = 4;
          }
          else
          {
            v56 = (v55 & 4) != 0 ? 5 : 2;
          }
        }
        DWORD1(v109) = v56;
        v57 = (__int16 *)(v51 + v53 + 20);
        v58 = 2147483646;
        v59 = v57;
        v60 = 32;
        v61 = (_WORD *)&v109 + 4;
        do
        {
          if ( !v58 )
            break;
          v62 = *v59;
          if ( !*v59 )
            break;
          ++v59;
          *v61++ = v62;
          --v58;
          --v60;
        }
        while ( v60 );
        v63 = v61 - 1;
        if ( v60 )
          v63 = v61;
        *v63 = 0;
        v64 = 2147483646;
        v65 = 21;
        v66 = (_WORD *)&v113 + 4;
        do
        {
          if ( !v64 )
            break;
          v67 = *v57;
          if ( !*v57 )
            break;
          ++v57;
          *v66++ = v67;
          --v64;
          --v65;
        }
        while ( v65 );
        v68 = v66 - 1;
        if ( v65 )
          v68 = v66;
        *v68 = 0;
        v69 = 2147483646;
        v70 = (__int16 *)v54;
        v71 = 16;
        v72 = (_WORD *)&v116 + 1;
        do
        {
          if ( !v69 )
            break;
          v73 = *v70;
          if ( !*v70 )
            break;
          ++v70;
          *v72++ = v73;
          --v69;
          --v71;
        }
        while ( v71 );
        v74 = v72 - 1;
        if ( v71 )
          v74 = v72;
        *v74 = 0;
        LODWORD(v109) = CWwanTranslator::_DataClassFromWwan(*(_DWORD *)(v54 + 64));
        if ( !v75 )
          break;
        v76 = 7;
        v77 = v75;
        do
        {
          if ( !*v77 )
            break;
          ++v77;
          --v76;
        }
        while ( v76 );
        v10 = v76 == 0 ? 0x80070057 : 0;
        if ( !v76 )
          goto LABEL_108;
        v10 = 0;
        if ( (unsigned int)(7 - v76) >= 3 )
        {
          v78 = 2147483646;
          v79 = 4;
          v80 = (_WORD *)&v118 + 1;
          do
          {
            if ( !v78 )
              break;
            v81 = *v75;
            if ( !*v75 )
              break;
            ++v75;
            *v80++ = v81;
            --v78;
            --v79;
          }
          while ( v79 );
          v82 = v80 - 1;
          if ( v79 )
            v82 = v80;
          *v82 = 0;
        }
        v83 = v94[1];
        if ( v94[1] == v95 )
        {
          std::vector<CellularSettingsOperatorInfo>::_Emplace_reallocate<CellularSettingsOperatorInfo const &>(
            v94,
            v94[1],
            &v109);
        }
        else
        {
          *(_OWORD *)v94[1] = v109;
          *((_OWORD *)v83 + 1) = v110;
          *((_OWORD *)v83 + 2) = v111;
          *((_OWORD *)v83 + 3) = v112;
          *((_OWORD *)v83 + 4) = v113;
          *((_OWORD *)v83 + 5) = v114;
          *((_OWORD *)v83 + 6) = v115;
          *((_OWORD *)v83 + 7) = v116;
          *((_OWORD *)v83 + 8) = v117;
          *((_OWORD *)v83 + 9) = v118;
          *((_DWORD *)v83 + 40) = v119;
          v94[1] += 82;
        }
        if ( ++v52 >= v97[0] )
          goto LABEL_58;
      }
      v10 = -2147024809;
LABEL_108:
      v50 = 2370;
      goto LABEL_62;
    }
    goto LABEL_58;
  }
  v16 = (__int64)v11 + *((_QWORD *)v14 + 1);
  v10 = 0;
  v17 = 0;
  if ( !v15 )
  {
LABEL_58:
    v120[0] = off_18005EE58;
    v120[1] = this;
    v120[2] = v96;
    v120[3] = v94;
    v120[4] = v97;
    v121 = v120;
    CWwanTranslator::SafelyNotify(this, v120);
    if ( v121 )
    {
      v49 = v120;
      LOBYTE(v49) = v121 != v120;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v121 + 32LL))(v121, v49);
    }
    std::vector<CellularSettingsOperatorInfo>::~vector<CellularSettingsOperatorInfo>(v94);
    goto LABEL_115;
  }
  while ( 1 )
  {
    memset_0((char *)&v109 + 8, 0, 0x9Cu);
    v18 = 68LL * v17;
    v19 = v18 + v16;
    v20 = *(_DWORD *)(v18 + v16 + 16);
    v21 = 1;
    if ( v20 )
    {
      if ( (v20 & 0x10) != 0 )
      {
        v21 = 3;
      }
      else if ( (v20 & 2) != 0 )
      {
        v21 = 4;
      }
      else
      {
        v21 = (v20 & 4) != 0 ? 5 : 2;
      }
    }
    DWORD1(v109) = v21;
    v22 = (__int16 *)(v16 + v18 + 20);
    v23 = 2147483646;
    v24 = v22;
    v25 = 32;
    v26 = (_WORD *)&v109 + 4;
    do
    {
      if ( !v23 )
        break;
      v27 = *v24;
      if ( !*v24 )
        break;
      ++v24;
      *v26++ = v27;
      --v23;
      --v25;
    }
    while ( v25 );
    v28 = v26 - 1;
    if ( v25 )
      v28 = v26;
    *v28 = 0;
    v29 = 2147483646;
    v30 = 21;
    v31 = (_WORD *)&v113 + 4;
    do
    {
      if ( !v29 )
        break;
      v32 = *v22;
      if ( !*v22 )
        break;
      ++v22;
      *v31++ = v32;
      --v29;
      --v30;
    }
    while ( v30 );
    v33 = v31 - 1;
    if ( v30 )
      v33 = v31;
    *v33 = 0;
    v34 = 2147483646;
    v35 = (__int16 *)v19;
    v36 = 16;
    v37 = (_WORD *)&v116 + 1;
    do
    {
      if ( !v34 )
        break;
      v38 = *v35;
      if ( !*v35 )
        break;
      ++v35;
      *v37++ = v38;
      --v34;
      --v36;
    }
    while ( v36 );
    v39 = v37 - 1;
    if ( v36 )
      v39 = v37;
    *v39 = 0;
    LODWORD(v109) = CWwanTranslator::_DataClassFromWwan(*(_DWORD *)(v19 + 64));
    v41 = 7;
    v42 = v40;
    do
    {
      if ( !*v42 )
        break;
      ++v42;
      --v41;
    }
    while ( v41 );
    v10 = v41 == 0 ? 0x80070057 : 0;
    if ( !v41 )
      break;
    v10 = 0;
    if ( (unsigned int)(7 - v41) >= 3 )
    {
      v43 = 2147483646;
      v44 = 4;
      v45 = (_WORD *)&v118 + 1;
      do
      {
        if ( !v43 )
          break;
        v46 = *v40;
        if ( !*v40 )
          break;
        ++v40;
        *v45++ = v46;
        --v43;
        --v44;
      }
      while ( v44 );
      v47 = v45 - 1;
      if ( v44 )
        v47 = v45;
      *v47 = 0;
    }
    v48 = v94[1];
    if ( v94[1] == v95 )
    {
      std::vector<CellularSettingsOperatorInfo>::_Emplace_reallocate<CellularSettingsOperatorInfo const &>(
        v94,
        v94[1],
        &v109);
    }
    else
    {
      *(_OWORD *)v94[1] = v109;
      *((_OWORD *)v48 + 1) = v110;
      *((_OWORD *)v48 + 2) = v111;
      *((_OWORD *)v48 + 3) = v112;
      *((_OWORD *)v48 + 4) = v113;
      *((_OWORD *)v48 + 5) = v114;
      *((_OWORD *)v48 + 6) = v115;
      *((_OWORD *)v48 + 7) = v116;
      *((_OWORD *)v48 + 8) = v117;
      *((_OWORD *)v48 + 9) = v118;
      *((_DWORD *)v48 + 40) = v119;
      v94[1] += 82;
    }
    if ( ++v17 >= v97[0] )
      goto LABEL_58;
  }
  v50 = 2342;
LABEL_62:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v50,
    (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
    (const char *)v10,
    (int)&v104);
  std::vector<CellularSettingsOperatorInfo>::~vector<CellularSettingsOperatorInfo>(v94);
LABEL_118:
  if ( v93 )
    WwanFreeMemory(v93);
LABEL_120:
  WwanCloseHandle(v98, 0);
  return v10;
}

```

## disassembly

```asm
0x180040c4c  mov     [rsp-8+arg_10], rbx
0x180040c51  push    rbp
0x180040c52  push    rsi
0x180040c53  push    rdi
0x180040c54  push    r13
0x180040c56  push    r15
0x180040c58  lea     rbp, [rsp-120h]
0x180040c60  sub     rsp, 220h
0x180040c67  mov     rax, cs:__security_cookie
0x180040c6e  xor     rax, rsp
0x180040c71  mov     [rbp+140h+var_30], rax
0x180040c78  mov     rbx, rdx
0x180040c7b  mov     [rsp+240h+var_1E0], rdx
0x180040c80  mov     r13, rcx
0x180040c83  xorps   xmm0, xmm0
0x180040c86  movdqu  xmmword ptr [rbp+140h+var_190], xmm0
0x180040c8b  xor     edi, edi
0x180040c8d  mov     [rbp+140h+var_180], rdi
0x180040c91  movdqu  xmmword ptr [rsp+240h+var_1F8], xmm0
0x180040c97  mov     [rsp+240h+var_1E8], rdi
0x180040c9c  lea     rcx, [rbp+140h+var_190]
0x180040ca0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180040ca5  lea     rcx, [rsp+240h+var_1F8]
0x180040caa  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180040caf  mov     rdx, [rbp+140h+var_190+8]
0x180040cb3  mov     rcx, [rbp+140h+var_190]; unsigned __int16 *
0x180040cb7  sub     rdx, rcx
0x180040cba  sar     rdx, 1; unsigned __int64
0x180040cbd  lea     r8, aEnter; "Enter"
0x180040cc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040cc9  mov     rdx, [rsp+240h+var_1F8+8]
0x180040cce  mov     rcx, [rsp+240h+var_1F8]; unsigned __int16 *
0x180040cd3  sub     rdx, rcx
0x180040cd6  sar     rdx, 1; unsigned __int64
0x180040cd9  mov     rax, [rbp+140h+var_190]
0x180040cdd  mov     [rsp+240h+var_218], rax
0x180040ce2  mov     [rsp+240h+var_220], 8F3h
0x180040cea  lea     r9, aCwwantranslato_19; "CWwanTranslator::_ProcessNetworkScan"
0x180040cf1  lea     r8, aSDS; "%S(%d):%s"
0x180040cf8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040cfd  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180040d02  mov     ecx, [rax]
0x180040d04  cmp     ecx, 5
0x180040d07  jbe     short loc_180040D2D
0x180040d09  mov     rcx, [rsp+240h+var_1F8]
0x180040d0e  mov     qword ptr [rsp+240h+var_1D8], rcx
0x180040d13  lea     rcx, [rsp+240h+var_1D8]
0x180040d18  mov     qword ptr [rsp+240h+var_220], rcx; unsigned int
0x180040d1d  lea     rdx, byte_180076AFF
0x180040d24  mov     rcx, rax
0x180040d27  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180040d2c  nop
0x180040d2d  lea     rcx, [rsp+240h+var_1F8]
0x180040d32  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180040d37  nop
0x180040d38  lea     rcx, [rbp+140h+var_190]
0x180040d3c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180040d41  mov     [rsp+240h+var_1D0], rdi
0x180040d46  mov     [rbp+140h+var_198], edi
0x180040d49  lea     r9, [rsp+240h+var_1D0]
0x180040d4e  lea     r8, [rbp+140h+var_198]
0x180040d52  xor     edx, edx
0x180040d54  lea     ecx, [rdx+1]
0x180040d57  call    cs:__imp_WwanOpenHandle
0x180040d5d  test    eax, eax
0x180040d5f  jz      short loc_180040D81
0x180040d61  mov     rcx, [rbp+148h]; this
0x180040d68  mov     r9d, eax; char *
0x180040d6b  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180040d72  mov     edx, 8F5h; void *
0x180040d77  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040d7c  jmp     loc_1800415FE
0x180040d81  lea     rax, [rsp+240h+var_1D0]
0x180040d86  mov     [rbp+140h+var_170], rax
0x180040d8a  mov     [rbp+140h+var_168], 1
0x180040d8e  mov     [rsp+240h+var_200], rdi
0x180040d93  mov     [rbp+140h+var_194], edi
0x180040d96  lea     rax, [rsp+240h+var_200]
0x180040d9b  mov     [rbp+140h+var_190], rax
0x180040d9f  mov     byte ptr [rbp+140h+var_190+8], 1
0x180040da3  mov     [rsp+240h+var_208], rdi
0x180040da8  mov     [rsp+240h+var_210], rdi
0x180040dad  lea     rax, [rsp+240h+var_200]
0x180040db2  mov     [rsp+240h+var_218], rax
0x180040db7  lea     rax, [rbp+140h+var_194]
0x180040dbb  mov     qword ptr [rsp+240h+var_220], rax; int
0x180040dc0  xor     r9d, r9d
0x180040dc3  lea     r8d, [r9+7]
0x180040dc7  mov     rdx, rbx
0x180040dca  mov     rcx, [rsp+240h+var_1D0]
0x180040dcf  call    cs:__imp_WwanQueryInterface
0x180040dd5  test    eax, eax
0x180040dd7  jz      short loc_180040DFB
0x180040dd9  mov     rcx, [rbp+148h]; this
0x180040de0  mov     r9d, eax; char *
0x180040de3  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180040dea  mov     edx, 900h; void *
0x180040def  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040df4  mov     ebx, eax
0x180040df6  jmp     loc_1800415DE
0x180040dfb  mov     rdx, [rsp+240h+var_200]
0x180040e00  mov     eax, [rdx+59Ch]
0x180040e06  test    eax, eax
0x180040e08  jnz     short loc_180040E81
0x180040e0a  lea     rax, off_18005EEE8
0x180040e11  mov     [rbp+140h+var_70], rax
0x180040e18  mov     [rbp+140h+var_68], r13
0x180040e1f  mov     [rbp+140h+var_60], rbx
0x180040e26  lea     rax, [rbp+140h+var_70]
0x180040e2d  mov     [rbp+140h+var_38], rax
0x180040e34  lea     rdx, [rbp+140h+var_70]
0x180040e3b  mov     rcx, r13
0x180040e3e  call    ?SafelyNotify@CWwanTranslator@@AEAAJ$$QEAV?$function@$$A6AXXZ@std@@@Z; CWwanTranslator::SafelyNotify(std::function<void (void)> &&)
0x180040e43  nop
0x180040e44  mov     rcx, [rbp+140h+var_38]
0x180040e4b  test    rcx, rcx
0x180040e4e  jz      short loc_180040E6A
0x180040e50  mov     rax, [rcx]
0x180040e53  lea     rdx, [rbp+140h+var_70]
0x180040e5a  cmp     rcx, rdx
0x180040e5d  setnz   dl
0x180040e60  mov     rax, [rax+20h]
0x180040e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e69  nop
0x180040e6a  mov     rcx, [rsp+240h+var_200]
0x180040e6f  test    rcx, rcx
0x180040e72  jz      short loc_180040E7A
0x180040e74  call    cs:__imp_WwanFreeMemory
0x180040e7a  mov     ebx, edi
0x180040e7c  jmp     loc_1800415EF
0x180040e81  cmp     eax, 1
0x180040e84  jnz     loc_180041521
0x180040e8a  lea     rbx, [rdx+580h]
0x180040e91  mov     ecx, [rbx+4]
0x180040e94  mov     [rsp+240h+var_1D8], ecx
0x180040e98  xorps   xmm0, xmm0
0x180040e9b  movdqu  xmmword ptr [rsp+240h+var_1F8], xmm0
0x180040ea1  mov     [rsp+240h+var_1E8], rdi
0x180040ea6  mov     [rbp+140h+var_178], rcx
0x180040eaa  test    rcx, rcx
0x180040ead  jz      short loc_180040EC6
0x180040eaf  lea     rdx, [rbp+140h+var_178]
0x180040eb3  lea     rcx, [rsp+240h+var_1F8]
0x180040eb8  call    ??$_Reallocate@$0A@@?$vector@UCellularSettingsOperatorInfo@@V?$allocator@UCellularSettingsOperatorInfo@@@std@@@std@@AEAAXAEA_K@Z; std::vector<CellularSettingsOperatorInfo>::_Reallocate<0>(unsigned __int64 &)
0x180040ebd  mov     rdx, [rsp+240h+var_200]
0x180040ec2  mov     ecx, [rsp+240h+var_1D8]
0x180040ec6  cmp     dword ptr [rbx], 2
0x180040ec9  jnz     loc_1800411CD
0x180040ecf  mov     rsi, [rbx+8]
0x180040ed3  add     rsi, rdx
0x180040ed6  xor     ebx, ebx
0x180040ed8  mov     edi, ebx
0x180040eda  test    ecx, ecx
0x180040edc  jz      loc_180041116
0x180040ee2  mov     r15d, 7FFFFFFEh
0x180040ee8  xor     edx, edx; Val
0x180040eea  mov     r8d, 9Ch; Size
0x180040ef0  lea     rcx, [rbp+140h+var_160+8]; void *
0x180040ef4  call    memset_0
0x180040ef9  mov     eax, edi
0x180040efb  imul    rdx, rax, 44h ; 'D'
0x180040eff  lea     r11, [rdx+rsi]
0x180040f03  mov     ecx, [r11+10h]
0x180040f07  mov     eax, 1
0x180040f0c  test    ecx, ecx
0x180040f0e  jz      short loc_180040F35
0x180040f10  test    cl, 10h
0x180040f13  jz      short loc_180040F1C
0x180040f15  mov     eax, 3
0x180040f1a  jmp     short loc_180040F35
0x180040f1c  test    cl, 2
0x180040f1f  jz      short loc_180040F28
0x180040f21  mov     eax, 4
0x180040f26  jmp     short loc_180040F35
0x180040f28  and     cl, 4
0x180040f2b  neg     cl
0x180040f2d  sbb     eax, eax
0x180040f2f  and     eax, 3
0x180040f32  add     eax, 2
0x180040f35  mov     dword ptr [rbp+140h+var_160+4], eax
0x180040f38  lea     r10, [rdx+14h]
0x180040f3c  add     r10, rsi
0x180040f3f  mov     rcx, r15
0x180040f42  mov     r8, r10
0x180040f45  mov     edx, 20h ; ' '
0x180040f4a  lea     rax, [rbp+140h+var_160+8]
0x180040f4e  test    rcx, rcx
0x180040f51  jz      short loc_180040F72
0x180040f53  movzx   r9d, word ptr [r8]
0x180040f57  test    r9w, r9w
0x180040f5b  jz      short loc_180040F72
0x180040f5d  add     r8, 2
0x180040f61  mov     [rax], r9w
0x180040f65  add     rax, 2
0x180040f69  dec     rcx
0x180040f6c  sub     rdx, 1
0x180040f70  jnz     short loc_180040F4E
0x180040f72  lea     rcx, [rax-2]
0x180040f76  test    rdx, rdx
0x180040f79  cmovnz  rcx, rax
0x180040f7d  mov     [rcx], bx
0x180040f80  mov     r8, r15
0x180040f83  mov     edx, 15h
0x180040f88  lea     rax, [rbp+140h+var_118]
0x180040f8c  test    r8, r8
0x180040f8f  jz      short loc_180040FAE
0x180040f91  movzx   ecx, word ptr [r10]
0x180040f95  test    cx, cx
0x180040f98  jz      short loc_180040FAE
0x180040f9a  add     r10, 2
0x180040f9e  mov     [rax], cx
0x180040fa1  add     rax, 2
0x180040fa5  dec     r8
0x180040fa8  sub     rdx, 1
0x180040fac  jnz     short loc_180040F8C
0x180040fae  lea     rcx, [rax-2]
0x180040fb2  test    rdx, rdx
0x180040fb5  cmovnz  rcx, rax
0x180040fb9  mov     [rcx], bx
0x180040fbc  mov     rcx, r15
0x180040fbf  mov     r9, r11
0x180040fc2  mov     edx, 10h
0x180040fc7  lea     rax, [rbp+140h+var_EE]
0x180040fcb  test    rcx, rcx
0x180040fce  jz      short loc_180040FEF
0x180040fd0  movzx   r8d, word ptr [r9]
0x180040fd4  test    r8w, r8w
0x180040fd8  jz      short loc_180040FEF
0x180040fda  add     r9, 2
0x180040fde  mov     [rax], r8w
0x180040fe2  add     rax, 2
0x180040fe6  dec     rcx
0x180040fe9  sub     rdx, 1
0x180040fed  jnz     short loc_180040FCB
0x180040fef  lea     rcx, [rax-2]
0x180040ff3  test    rdx, rdx
0x180040ff6  cmovnz  rcx, rax
0x180040ffa  mov     [rcx], bx
0x180040ffd  mov     ecx, [r11+40h]; unsigned int
0x180041001  call    ?_DataClassFromWwan@CWwanTranslator@@SA?AW4MBN_DATA_CLASS@@K@Z; CWwanTranslator::_DataClassFromWwan(ulong)
0x180041006  mov     dword ptr [rbp+140h+var_160], eax
0x180041009  mov     edx, 7
0x18004100e  mov     ecx, edx
0x180041010  mov     rax, r11
0x180041013  cmp     [rax], bx
0x180041016  jz      short loc_180041022
0x180041018  add     rax, 2
0x18004101c  sub     rcx, 1
0x180041020  jnz     short loc_180041013
0x180041022  mov     rax, rcx
0x180041025  neg     rax
0x180041028  sbb     ebx, ebx
0x18004102a  not     ebx
0x18004102c  and     ebx, 80070057h
0x180041032  test    rcx, rcx
0x180041035  jz      loc_1800411A2
0x18004103b  mov     rax, rdx
0x18004103e  sub     rax, rcx
0x180041041  xor     ebx, ebx
0x180041043  cmp     eax, 3
0x180041046  jb      short loc_180041084
0x180041048  mov     rcx, r15
0x18004104b  lea     edx, [rbx+4]
0x18004104e  lea     rax, [rbp+140h+var_CE]
0x180041052  test    rcx, rcx
0x180041055  jz      short loc_180041076
0x180041057  movzx   r8d, word ptr [r11]
0x18004105b  test    r8w, r8w
0x18004105f  jz      short loc_180041076
0x180041061  add     r11, 2
0x180041065  mov     [rax], r8w
0x180041069  add     rax, 2
0x18004106d  dec     rcx
0x180041070  sub     rdx, 1
0x180041074  jnz     short loc_180041052
0x180041076  lea     rcx, [rax-2]
0x18004107a  test    rdx, rdx
0x18004107d  cmovnz  rcx, rax
0x180041081  mov     [rcx], bx
0x180041084  mov     rdx, [rsp+240h+var_1F8+8]
0x180041089  cmp     rdx, [rsp+240h+var_1E8]
0x18004108e  jz      short loc_1800410FC
0x180041090  movaps  xmm0, [rbp+140h+var_160]
0x180041094  movups  xmmword ptr [rdx], xmm0
0x180041097  movaps  xmm1, [rbp+140h+var_150]
0x18004109b  movups  xmmword ptr [rdx+10h], xmm1
0x18004109f  movaps  xmm0, [rbp+140h+var_140]
0x1800410a3  movups  xmmword ptr [rdx+20h], xmm0
0x1800410a7  movaps  xmm1, [rbp+140h+var_130]
0x1800410ab  movups  xmmword ptr [rdx+30h], xmm1
0x1800410af  movaps  xmm0, xmmword ptr [rbp+20h]
0x1800410b3  movups  xmmword ptr [rdx+40h], xmm0
0x1800410b7  movaps  xmm1, [rbp+140h+var_110]
0x1800410bb  movups  xmmword ptr [rdx+50h], xmm1
0x1800410bf  movaps  xmm0, [rbp+140h+var_100]
0x1800410c3  movups  xmmword ptr [rdx+60h], xmm0
0x1800410c7  movaps  xmm1, xmmword ptr [rbp+50h]
0x1800410cb  movups  xmmword ptr [rdx+70h], xmm1
0x1800410cf  movaps  xmm0, [rbp+140h+var_E0]
0x1800410d3  movups  xmmword ptr [rdx+80h], xmm0
  ... truncated ...
```
