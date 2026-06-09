# TelemetryDetailFromInterfaceAttributes(NCSI_INTERFACE_ATTRIBUTES *,_NLA_CONNECTIVITY_FAMILY,TelemetryDetailLevel)

- ea: `0x1800349f0`
- end: `0x180036261`
- name: `?TelemetryDetailFromInterfaceAttributes@@YA?AV?$unique_ptr@UNCSI_TELEMETRY_DETAIL@@Uncsi_telemetry_deleter@@@std@@PEAVNCSI_INTERFACE_ATTRIBUTES@@W4_NLA_CONNECTIVITY_FAMILY@@W4TelemetryDetailLevel@@@Z`
- size: `6257`
- prototype: ``
- caller_count: `5`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009db4`
- `0x18000a914`
- `0x180036268`
- `0x18006331c`
- `0x180063c5c`

## callees

- `0x180009804`
- `0x18000c5f0`
- `0x18000e350`
- `0x18000e59c`
- `0x180021800`
- `0x18002283c`
- `0x180024790`
- `0x18002575c`
- `0x180025794`
- `0x1800266bc`
- `0x180026714`
- `0x180027908`
- `0x180027938`
- `0x180028384`
- `0x1800296b8`
- `0x18002a02c`
- `0x18002b098`
- `0x18002b6cc`
- `0x18002c7b0`
- `0x18002cd3c`
- `0x18002cda0`
- `0x18002cf0c`
- `0x18002d430`
- `0x18002da58`
- `0x18003136c`
- `0x180034930`
- `0x1800349f0`
- `0x180043cc4`
- `0x180047240`
- `0x180047f78`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800350e3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800350e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034a61`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034a61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034a4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034a4e`
- `WS2_32!WSAAddressToStringW` at `0x18003566f`
- `WS2_32!WSAAddressToStringW` at `0x18003566f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
NCSI_TELEMETRY_DETAIL **__fastcall TelemetryDetailFromInterfaceAttributes(
        NCSI_TELEMETRY_DETAIL **a1,
        __int64 a2,
        unsigned int a3,
        int a4)
{
  __int64 v5; // rdi
  unsigned int v7; // esi
  HANDLE ProcessHeap; // rax
  NCSI_TELEMETRY_DETAIL *v9; // rax
  NCSI_TELEMETRY_DETAIL *v10; // r14
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // ecx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // r9
  NcsiConfigData *v18; // rcx
  char v19; // cl
  __int64 v20; // rcx
  char v21; // cl
  __int64 v22; // rdx
  __int64 v23; // rdx
  unsigned __int64 ZeroSpecialTickCount64; // r14
  unsigned __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // r10
  unsigned __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rax
  unsigned __int64 v32; // r14
  __int64 v33; // rsi
  NCSI_TELEMETRY_DETAIL *v34; // rcx
  WCHAR *v35; // r12
  DWORD v36; // r15d
  int v37; // r13d
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // rcx
  unsigned int v40; // eax
  unsigned int v41; // eax
  __int64 m; // rcx
  NCSI_TELEMETRY_DETAIL *v43; // rdx
  const IN_ADDR *v44; // rcx
  BOOLEAN v45; // al
  __int64 v46; // rdx
  NCSI_TELEMETRY_DETAIL *v47; // rdx
  const IN_ADDR *v48; // rax
  BOOLEAN v49; // al
  bool v50; // zf
  __int64 v51; // r11
  __int64 v52; // r9
  __int64 v53; // r9
  NCSI_TELEMETRY_DETAIL *v54; // rax
  const IN6_ADDR *v55; // rcx
  const IN6_ADDR *v56; // r8
  const IN6_ADDR *v57; // r8
  __int64 v58; // r9
  _WORD *v59; // r10
  UCHAR *v60; // rcx
  const IN6_ADDR *v61; // r8
  char v62; // dl
  const IN6_ADDR *v63; // rcx
  __int64 v64; // r9
  char v65; // al
  const IN6_ADDR *v66; // rcx
  const IN6_ADDR *v67; // r8
  const IN6_ADDR *v68; // r8
  __int64 v69; // r14
  struct sockaddr *v70; // rcx
  DWORD v71; // ecx
  char v72; // al
  __int64 v73; // r8
  __int64 v74; // rcx
  const SOCKADDR *v75; // rcx
  __int64 v76; // r9
  const SOCKADDR *v77; // rcx
  const SOCKADDR *v78; // rdx
  __int64 v79; // r9
  __int64 v80; // r8
  NCSI_TELEMETRY_DETAIL *v81; // rax
  __int64 v82; // rcx
  const SOCKADDR *v83; // rcx
  __int64 v84; // r9
  const SOCKADDR *v85; // rcx
  const SOCKADDR *v86; // rdx
  __int64 v87; // r9
  __int64 v88; // r8
  __int64 v89; // rdx
  __int64 v90; // rdx
  NCSI_TELEMETRY_DETAIL *v91; // rax
  __int64 v92; // rcx
  const SOCKADDR *v93; // rcx
  BOOLEAN v94; // al
  __int64 v95; // r9
  unsigned int v96; // eax
  unsigned int v97; // eax
  __int64 i; // rdx
  const IN_ADDR *v99; // rcx
  _WORD *v100; // r8
  NCSI_TELEMETRY_DETAIL *v101; // rax
  __int64 j; // rdx
  __int64 v103; // rax
  _WORD *v104; // r8
  NCSI_TELEMETRY_DETAIL *v105; // rax
  __int64 k; // rdx
  const IN_ADDR *v107; // rax
  _WORD *v108; // r8
  NCSI_TELEMETRY_DETAIL *v109; // rax
  __int64 v110; // rcx
  __int128 v113; // [rsp+38h] [rbp-A1h] BYREF
  __int128 v114; // [rsp+48h] [rbp-91h]
  __int16 v115; // [rsp+58h] [rbp-81h]
  NCSI_TELEMETRY_DETAIL **v116; // [rsp+60h] [rbp-79h]
  DWORD dwAddressStringLength; // [rsp+68h] [rbp-71h] BYREF
  struct sockaddr v118; // [rsp+70h] [rbp-69h] BYREF
  __int64 v119; // [rsp+80h] [rbp-59h]
  int v120; // [rsp+88h] [rbp-51h]
  struct sockaddr v121; // [rsp+90h] [rbp-49h] BYREF
  _BYTE a[28]; // [rsp+B0h] [rbp-29h] BYREF
  struct sockaddr saAddress[2]; // [rsp+D0h] [rbp-9h] BYREF

  v5 = a2;
  v116 = a1;
  dwAddressStringLength = 1;
  v7 = 0;
  if ( a3 <= 2 )
    v7 = a3;
  *a1 = 0;
  ProcessHeap = GetProcessHeap();
  v9 = (NCSI_TELEMETRY_DETAIL *)HeapAlloc(ProcessHeap, 8u, 0x9A8u);
  v10 = v9;
  *a1 = v9;
  if ( v9 )
  {
    memset_0(v9, 0, 0x9A8u);
    NCSI_TELEMETRY_DETAIL::NCSI_TELEMETRY_DETAIL(v10);
  }
  dwAddressStringLength = 1;
  if ( *a1 )
  {
    *(_BYTE *)*a1 = a4 == 1;
    *((_DWORD *)*a1 + 1) = NCSI_INTERFACE_ATTRIBUTES::GetSuspectEventCountSinceLastInternet(v5, v7);
    *((_BYTE *)*a1 + 55) = NCSI_INTERFACE_ATTRIBUTES::HadInternetSinceReset(v5, v11);
    v12 = *(_DWORD *)(v5 + 4428);
    if ( *(_DWORD *)(v5 + 4424) >= v12 )
      v12 = *(_DWORD *)(v5 + 4424);
    *((_DWORD *)*a1 + 2) = v12;
    v13 = *(_DWORD *)(v5 + 8372);
    if ( *(_DWORD *)(v5 + 8368) >= v13 )
      v13 = *(_DWORD *)(v5 + 8368);
    *((_DWORD *)*a1 + 3) = v13;
    *((_DWORD *)*a1 + 4) = *(_DWORD *)(v5 + 4424);
    *((_DWORD *)*a1 + 5) = *(_DWORD *)(v5 + 8368);
    *((_BYTE *)*a1 + 24) = NCSI_INTERFACE_ATTRIBUTES::GetOperStatus((NCSI_INTERFACE_ATTRIBUTES *)v5) == IfOperStatusUp;
    *((_BYTE *)*a1 + 25) = NCSI_INTERFACE_ATTRIBUTES::GetOperStatus((NCSI_INTERFACE_ATTRIBUTES *)v5) != IfOperStatusUp;
    *((_BYTE *)*a1 + 26) = NCSI_INTERFACE_ATTRIBUTES::IsDormant((NCSI_INTERFACE_ATTRIBUTES *)v5);
    *((_BYTE *)*a1 + 27) = *(_BYTE *)(v5 + 4353);
    *((_BYTE *)*a1 + 28) = *(_BYTE *)(v5 + 8297);
    *((_BYTE *)*a1 + 29) = *(_BYTE *)(v5 + 4354);
    *((_BYTE *)*a1 + 30) = *(_BYTE *)(v5 + 8298);
    *((_BYTE *)*a1 + 47) = *(_BYTE *)(v5 + 4355);
    *((_BYTE *)*a1 + 48) = *(_BYTE *)(v5 + 8299);
    *((_BYTE *)*a1 + 31) = NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(v5, 0);
    *((_BYTE *)*a1 + 32) = NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(v5, 1);
    *((_BYTE *)*a1 + 33) = NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(v5, 0, v14, v15);
    *((_BYTE *)*a1 + 33) = NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(v5, 1, v16, v17);
    *((_BYTE *)*a1 + 35) = *(_BYTE *)(v5 + 11660);
    _m_prefetchw((const void *)(v5 + 32));
    v18 = (NcsiConfigData *)*(unsigned int *)(v5 + 32);
    LOBYTE(v18) = _InterlockedOr((volatile signed __int32 *)(v5 + 32), 0) != 0;
    *((_BYTE *)*a1 + 36) = (_BYTE)v18;
    *((_BYTE *)*a1 + 37) = NcsiConfigData::CorpLocationProbeEnabled(v18);
    _m_prefetchw((const void *)(v5 + 40));
    *((_BYTE *)*a1 + 38) = _InterlockedOr((volatile signed __int32 *)(v5 + 40), 0) != 0;
    *((_BYTE *)*a1 + 39) = *(_WORD *)(v5 + 4360) != 0;
    *((_BYTE *)*a1 + 41) = *(_WORD *)(v5 + 8304) != 0;
    *((_BYTE *)*a1 + 45) = *(_BYTE *)(v5 + 4498);
    *((_BYTE *)*a1 + 46) = *(_BYTE *)(v5 + 8442);
    *((_DWORD *)*a1 + 14) = *(_DWORD *)(v5 + 4528);
    *((_DWORD *)*a1 + 15) = *(_DWORD *)(v5 + 8472);
    *((_DWORD *)*a1 + 16) = NCSI_INTERFACE_ATTRIBUTES::GetInterfaceUpTime((NCSI_INTERFACE_ATTRIBUTES *)v5);
    *((_DWORD *)*a1 + 17) = 0;
    *((_DWORD *)*a1 + 18) = 0;
    if ( *((_BYTE *)*a1 + 25) )
    {
      *((_DWORD *)*a1 + 17) = *(_DWORD *)(v5 + 11688);
      *((_DWORD *)*a1 + 18) = NCSI_INTERFACE_ATTRIBUTES::AgeOfDisconnect((NCSI_INTERFACE_ATTRIBUTES *)v5);
    }
    *((_BYTE *)*a1 + 49) = *(_BYTE *)(v5 + 4496);
    *((_BYTE *)*a1 + 50) = *(_BYTE *)(v5 + 8440);
    *((_BYTE *)*a1 + 51) = *(_BYTE *)(v5 + 4497);
    *((_BYTE *)*a1 + 52) = *(_BYTE *)(v5 + 8441);
    *(_OWORD *)a = *(_OWORD *)(v5 + 4500);
    *(_OWORD *)&a[12] = *(_OWORD *)(v5 + 4512);
    saAddress[0] = *(struct sockaddr *)(v5 + 8444);
    *(struct sockaddr *)&saAddress[0].sa_data[10] = *(struct sockaddr *)(v5 + 8456);
    *((_BYTE *)*a1 + 43) = IN4_IS_ADDR_RFC1918((const IN_ADDR *)&a[4]);
    if ( saAddress[0].sa_data[6] != -2 || (v19 = 1, (saAddress[0].sa_data[7] & 0xC0) != 0x80) )
      v19 = 0;
    *((_BYTE *)*a1 + 44) = v19;
    StringFromAddress((unsigned __int16 *)*a1 + 46, 0x12u, (LPSOCKADDR)a, 0x1Cu);
    StringFromAddress((unsigned __int16 *)*a1 + 64, 0x2Eu, saAddress, 0x1Cu);
    NCSI_INTERFACE_ATTRIBUTES::GetDefaultGatewayAddress(v5, &v121, 0);
    NCSI_INTERFACE_ATTRIBUTES::GetDefaultGatewayAddress(v20, &v118, 1);
    *((_BYTE *)*a1 + 40) = IN4_IS_ADDR_RFC1918((const IN_ADDR *)&v121.sa_data[2]);
    if ( v118.sa_data[6] != -2 || (v21 = 1, (v118.sa_data[7] & 0xC0) != 0x80) )
      v21 = 0;
    *((_BYTE *)*a1 + 42) = v21;
    StringFromAddress((unsigned __int16 *)*a1 + 110, 0x12u, &v121, 0x1Cu);
    StringFromAddress((unsigned __int16 *)*a1 + 128, 0x2Eu, &v118, 0x1Cu);
    v113 = *(_OWORD *)(v5 + 4388);
    v114 = *(_OWORD *)(v5 + 4404);
    v115 = *(_WORD *)(v5 + 4420);
    StringFromMacAddress((char *)*a1 + 348, v22, &v113);
    v113 = *(_OWORD *)(v5 + 8332);
    v114 = *(_OWORD *)(v5 + 8348);
    v115 = *(_WORD *)(v5 + 8364);
    StringFromMacAddress((char *)*a1 + 384, v23, &v113);
    *((_QWORD *)*a1 + 53) = v5 + 156;
    *((_QWORD *)*a1 + 54) = v5 + 668;
    *((_QWORD *)*a1 + 55) = v5 + 1180;
    *((_QWORD *)*a1 + 56) = v5 + 2732;
    *((_QWORD *)*a1 + 57) = v5 + 3244;
    *((_OWORD *)*a1 + 30) = *(_OWORD *)(v5 + 2716);
    *((_QWORD *)*a1 + 58) = v5 + 2204;
    *((_QWORD *)*a1 + 59) = v5 + 1692;
    *((_DWORD *)*a1 + 124) = *(_DWORD *)(v5 + 152);
    ZeroSpecialTickCount64 = GetZeroSpecialTickCount64();
    *((_QWORD *)*a1 + 193) = ZeroSpecialTickCount64 - (unsigned int)NCSI_INTERFACE_ATTRIBUTES::GetReadyTimestamp(v5, v7);
    v25 = ZeroSpecialTickCount64 - *(_QWORD *)(v5 + 11664);
    *((_QWORD *)*a1 + 194) = v25;
    if ( v7 < 2 )
    {
      v26 = v5 + 3944LL * v7;
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v25);
      v26 = v5;
    }
    v27 = *(_QWORD *)(v26 + 4336);
    v28 = 0;
    v29 = v27 ? ZeroSpecialTickCount64 - v27 : 0LL;
    *((_QWORD *)*a1 + 195) = v29;
    if ( v7 < 2 )
    {
      v30 = v5 + 3944LL * v7;
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v29);
      v28 = 0;
      v30 = v5;
    }
    v31 = *(_QWORD *)(v30 + 4344);
    v32 = v31 ? ZeroSpecialTickCount64 - v31 : 0LL;
    *((_QWORD *)*a1 + 196) = v32;
    if ( *(_BYTE *)*a1 )
    {
      v33 = *(_QWORD *)(v5 + 12768);
      *((_DWORD *)*a1 + 125) = 0;
      if ( v33 )
      {
        while ( 1 )
        {
          ++*((_DWORD *)*a1 + 125);
          switch ( *(_WORD *)(v33 + 230) )
          {
            case 6:
              ++*((_DWORD *)*a1 + 373);
              break;
            case 0x17:
              ++*((_DWORD *)*a1 + 377);
              break;
            case 0x47:
              ++*((_DWORD *)*a1 + 374);
              break;
            case 0x83:
              ++*((_DWORD *)*a1 + 376);
              break;
            case 0x8E:
              ++*((_DWORD *)*a1 + 378);
              break;
            default:
              if ( *(_WORD *)(v33 + 230) == 237 || (unsigned __int64)*(unsigned __int16 *)(v33 + 230) - 243 < 2 )
                ++*((_DWORD *)*a1 + 375);
              else
                ++*((_DWORD *)*a1 + 379);
              break;
          }
          v34 = *a1;
          if ( *(_QWORD *)(v33 + 224) != *(_QWORD *)v5 )
          {
            v96 = *(_DWORD *)(v33 + 96);
            if ( v96 < *((_DWORD *)v34 + 371) )
              *((_DWORD *)v34 + 371) = v96;
            v97 = *(_DWORD *)(v33 + 96);
            if ( v97 > *((_DWORD *)*a1 + 372) )
              *((_DWORD *)*a1 + 372) = v97;
            if ( *(_QWORD *)(v33 + 200) != v28 )
              *((_BYTE *)*a1 + 1477) = 1;
            for ( i = *(_QWORD *)(v33 + 24); i; i = *(_QWORD *)(i + 8) )
            {
              v99 = *(const IN_ADDR **)(i + 16);
              if ( v99 )
              {
                if ( v99->S_un.S_un_w.s_w1 == 2 )
                {
                  ++*((_DWORD *)*a1 + 130);
                  v50 = IN4_IS_ADDR_RFC1918(v99 + 1) == 0;
                  v101 = *a1;
                  if ( v50 )
                    ++*((_DWORD *)v101 + 327);
                  else
                    ++*((_DWORD *)v101 + 328);
                  if ( *v100 == 0xFEA9 )
                    ++*((_DWORD *)*a1 + 329);
                }
                else if ( v99->S_un.S_un_w.s_w1 == 23 )
                {
                  ++*((_DWORD *)*a1 + 131);
                }
              }
            }
            for ( j = *(_QWORD *)(v33 + 48); j; j = *(_QWORD *)(j + 8) )
            {
              v103 = *(_QWORD *)(j + 16);
              if ( v103 )
              {
                if ( *(_WORD *)v103 == 2 )
                {
                  v50 = IN4_IS_ADDR_RFC1918((const IN_ADDR *)(v103 + 4)) == 0;
                  v105 = *a1;
                  if ( v50 )
                    ++*((_DWORD *)v105 + 335);
                  else
                    ++*((_DWORD *)v105 + 336);
                  if ( *v104 == 0xFEA9 )
                    ++*((_DWORD *)*a1 + 337);
                }
                else if ( *(_WORD *)v103 == 23 )
                {
                  if ( *(_BYTE *)(v103 + 8) == 0xFE && (*(_BYTE *)(v103 + 9) & 0xC0) == 0x80 )
                    ++*((_DWORD *)*a1 + 339);
                  if ( IN6_IS_ADDR_GLOBAL((const IN6_ADDR *)(v103 + 8)) )
                    ++*((_DWORD *)*a1 + 338);
                }
              }
            }
            for ( k = *(_QWORD *)(v33 + 208); k; k = *(_QWORD *)(k + 8) )
            {
              v107 = *(const IN_ADDR **)(k + 16);
              if ( v107 && v107->S_un.S_un_w.s_w1 == 2 )
              {
                v50 = IN4_IS_ADDR_RFC1918(v107 + 1) == 0;
                v109 = *a1;
                if ( v50 )
                  ++*((_DWORD *)v109 + 344);
                else
                  ++*((_DWORD *)v109 + 345);
                if ( *v108 == 0xFEA9 )
                  ++*((_DWORD *)*a1 + 346);
              }
            }
            goto LABEL_268;
          }
          v35 = (WCHAR *)((char *)v34 + 2092);
          v36 = 189;
          v37 = 4;
          StringCchCopyW((unsigned __int16 *)v34 + 264, 0x80u, *(const unsigned __int16 **)(v33 + 64));
          MultiByteToWideChar(0, 0, *(LPCCH *)(v33 + 16), -1, (LPWSTR)*a1 + 392, 256);
          *((_DWORD *)*a1 + 380) = *(_DWORD *)(v33 + 104);
          *((_DWORD *)*a1 + 430) = *(_DWORD *)(v33 + 268);
          *((_DWORD *)*a1 + 431) = *(_DWORD *)(v33 + 272);
          *((_DWORD *)*a1 + 428) = *(_DWORD *)(v33 + 216);
          *((_DWORD *)*a1 + 429) = *(_DWORD *)(v33 + 220);
          v38 = *(_QWORD *)(v33 + 184);
          if ( v38 < 0x9184E72A000LL )
            *((_QWORD *)*a1 + 191) = v38;
          v39 = *(_QWORD *)(v33 + 192);
          if ( v39 < 0x9184E72A000LL )
            *((_QWORD *)*a1 + 192) = v39;
          *((_DWORD *)*a1 + 370) = *(_DWORD *)(v33 + 96);
          v40 = *(_DWORD *)(v33 + 96);
          if ( v40 < *((_DWORD *)*a1 + 371) )
            *((_DWORD *)*a1 + 371) = v40;
          v41 = *(_DWORD *)(v33 + 96);
          if ( v41 > *((_DWORD *)*a1 + 372) )
            *((_DWORD *)*a1 + 372) = v41;
          v28 = 0;
          if ( *(_QWORD *)(v33 + 200) )
          {
            for ( m = 0; m != 2; ++m )
              *((_BYTE *)*a1 + m + 1476) = 1;
          }
          *((_BYTE *)*a1 + 1576) = (*(_BYTE *)(v33 + 92) & 4) != 0;
          *((_BYTE *)*a1 + 1578) = 0;
          v43 = *a1;
          if ( *((_BYTE *)*a1 + 1576) )
          {
            v44 = *(const IN_ADDR **)(v33 + 232);
            if ( v44 )
            {
              v45 = IN4_IS_ADDR_RFC1918(v44 + 1);
              *(_BYTE *)(v46 + 1578) = v45;
              StringFromAddress(
                (unsigned __int16 *)*a1 + 790,
                0x12u,
                *(LPSOCKADDR *)(v33 + 232),
                *(_DWORD *)(v33 + 240));
              *((_BYTE *)*a1 + 1579) = IsSockAddrOnLink(*(_QWORD *)(v33 + 24), *(_QWORD *)(v33 + 232));
              v43 = *a1;
              v28 = 0;
            }
          }
          *((_BYTE *)v43 + 1616) = *(_QWORD *)(v33 + 280) != 0;
          *((_BYTE *)*a1 + 1618) = 0;
          v47 = *a1;
          if ( *((_BYTE *)*a1 + 1616) )
            break;
LABEL_70:
          v51 = *(_QWORD *)(v33 + 24);
          if ( v51 )
          {
            do
            {
              v52 = *(_QWORD *)(v51 + 16);
              if ( v52 )
              {
                if ( *(_WORD *)v52 == 2 )
                {
                  ++*((_DWORD *)*a1 + 130);
                  ++*((_DWORD *)*a1 + 128);
                  v50 = IN4_IS_ADDR_RFC1918((const IN_ADDR *)(v52 + 4)) == 0;
                  v54 = *a1;
                  if ( v50 )
                  {
                    ++*((_DWORD *)v54 + 324);
                    ++*((_DWORD *)*a1 + 327);
                  }
                  else
                  {
                    ++*((_DWORD *)v54 + 325);
                    ++*((_DWORD *)*a1 + 328);
                  }
                  if ( *(_WORD *)(v53 + 4) == 0xFEA9 )
                  {
                    ++*((_DWORD *)*a1 + 326);
                    ++*((_DWORD *)*a1 + 329);
                  }
                }
                else if ( *(_WORD *)v52 == 23 )
                {
                  ++*((_DWORD *)*a1 + 131);
                  ++*((_DWORD *)*a1 + 129);
                  if ( IN6_IS_ADDR_LOOPBACK((const IN6_ADDR *)(v52 + 8)) )
                    ++*((_DWORD *)*a1 + 348);
                  if ( IN6_IS_ADDR_ISATAP(v55) )
                    ++*((_DWORD *)*a1 + 349);
                  if ( v56->u.Word[0] == in6addr_6to4prefix.u.Word[0] )
                    ++*((_DWORD *)*a1 + 350);
                  if ( *(_DWORD *)v56->u.Byte == *(_DWORD *)in6addr_teredoprefix.u.Byte
                    || *(_DWORD *)v56->u.Byte == *(_DWORD *)in6addr_teredoprefix_old.u.Byte )
                  {
                    ++*((_DWORD *)*a1 + 351);
                  }
                  if ( IN6_IS_ADDR_V4MAPPED(v56) )
                    ++*((_DWORD *)*a1 + 352);
                  if ( !v57->u.Word[0] )
                  {
                    if ( !*v59
                      && !v57->u.Word[2]
                      && !v57->u.Word[3]
                      && !v57->u.Word[4]
                      && !v57->u.Word[5]
                      && (v57->u.Word[6] || v57->u.Byte[14] || v57->u.Byte[15] >= 2u) )
                    {
                      ++*((_DWORD *)*a1 + 353);
                    }
                    if ( !v57->u.Word[0]
                      && !*v59
                      && !v57->u.Word[2]
                      && !v57->u.Word[3]
                      && v57->u.Word[4] == 0xFFFF
                      && !v57->u.Word[5] )
                    {
                      ++*((_DWORD *)*a1 + 354);
                    }
                  }
                  if ( v57->u.Byte[0] == 0xFF && (v57->u.Byte[1] & 0xF) == 8 )
                    ++*((_DWORD *)*a1 + 355);
                  if ( v57->u.Byte[0] == 0xFF )
                  {
                    v60 = &v57->u.Byte[1];
                    if ( (v57->u.Byte[1] & 0xF) == 0xE )
                      ++*((_DWORD *)*a1 + 356);
                    if ( v57->u.Byte[0] == 0xFF )
                    {
                      if ( (*v60 & 0xF) == 5 )
                        ++*((_DWORD *)*a1 + 357);
                      if ( v57->u.Byte[0] == 0xFF && (*v60 & 0xF) == 2 )
                        ++*((_DWORD *)*a1 + 358);
                    }
                  }
                  if ( *(_BYTE *)(v58 + 8) == 0xFF && (*(_BYTE *)(v58 + 9) & 0xF) == 1 )
                    ++*((_DWORD *)*a1 + 359);
                  if ( *(_BYTE *)(v58 + 8) == 0xFE )
                  {
                    if ( (*(_BYTE *)(v58 + 9) & 0xC0) == 0x80 )
                      ++*((_DWORD *)*a1 + 360);
                    if ( *(_BYTE *)(v58 + 8) == 0xFE && (*(_BYTE *)(v58 + 9) & 0xC0) == 0xC0 )
                      ++*((_DWORD *)*a1 + 361);
                  }
                  if ( IN6_IS_ADDR_GLOBAL(v57) )
                    ++*((_DWORD *)*a1 + 362);
                  if ( IN6_IS_ADDR_UNSPECIFIED(v61) )
                    ++*((_DWORD *)*a1 + 363);
                  if ( *(_BYTE *)(v64 + 8) == v62 )
                    ++*((_DWORD *)*a1 + 364);
                  v65 = *(_BYTE *)(v64 + 8);
                  if ( (v65 & 0xE0) != 0 && v65 != v62 )
                    ++*((_DWORD *)*a1 + 365);
                  if ( IN6_IS_ADDR_SUBNET_ROUTER_ANYCAST(v63) )
                    ++*((_DWORD *)*a1 + 366);
                  if ( IN6_IS_ADDR_SUBNET_RESERVED_ANYCAST(v66) )
                    ++*((_DWORD *)*a1 + 367);
                  if ( IN6_IS_ADDR_SUBNET_RESERVED_ANYCAST(v67) || IN6_IS_ADDR_SUBNET_ROUTER_ANYCAST(v68) )
                    ++*((_DWORD *)*a1 + 368);
                }
              }
              v51 = *(_QWORD *)(v51 + 8);
            }
            while ( v51 );
            v5 = a2;
          }
          v69 = *(_QWORD *)(v33 + 48);
          if ( v69 )
          {
            do
            {
              v70 = *(struct sockaddr **)(v69 + 16);
              if ( v70 )
              {
                if ( v37 )
                {
                  if ( v36 > 0x2F )
                  {
                    --v37;
                    dwAddressStringLength = v36;
                    if ( WSAAddressToStringW(v70, *(_DWORD *)(v69 + 24), 0, v35, &dwAddressStringLength) != -1 )
                    {
                      v71 = dwAddressStringLength;
                      if ( dwAddressStringLength < v36 )
                      {
                        if ( *(_QWORD *)(v69 + 8) )
                        {
                          v35[dwAddressStringLength - 1] = 44;
                          v35[dwAddressStringLength] = 0;
                          v71 = dwAddressStringLength;
                        }
                        v35 += v71;
                        v36 -= v71;
                      }
                      else
                      {
                        v37 = 0;
                        v36 = 0;
                      }
                    }
                  }
                }
                v72 = IsSockAddrOnLink(*(_QWORD *)(v33 + 24), *(_QWORD *)(v69 + 16));
                v28 = 0;
                if ( v72 )
                  ++*((_DWORD *)*a1 + 340);
                v73 = *(_QWORD *)(v69 + 16);
                if ( *(_WORD *)v73 == 2 )
                {
                  if ( !*((_BYTE *)*a1 + 504) )
                  {
                    v74 = *(_QWORD *)(v33 + 208);
                    if ( v74 )
                    {
                      v75 = *(const SOCKADDR **)(v74 + 16);
                      if ( v75 )
                      {
                        if ( v75->sa_family == 2 && INETADDR_ISEQUAL(v75, *(const SOCKADDR **)(v69 + 16)) )
                        {
                          *(_BYTE *)(v76 + 1390) = 1;
                          *((_BYTE *)*a1 + 504) = 1;
                        }
                      }
                    }
                  }
                  if ( *((_BYTE *)*a1 + 504) == (_BYTE)v28
                    && v121.sa_family == 2
                    && *(_DWORD *)&v121.sa_data[2] == *(_DWORD *)(v73 + 4) )
                  {
                    *((_BYTE *)*a1 + 1390) = 1;
                    *((_BYTE *)*a1 + 504) = 1;
                  }
                  if ( (*(_BYTE *)(v33 + 92) & 4) != 0 && *((_BYTE *)*a1 + 1577) == (_BYTE)v28 )
                  {
                    v77 = *(const SOCKADDR **)(v33 + 232);
                    if ( v77 )
                    {
                      v78 = *(const SOCKADDR **)(v69 + 16);
                      if ( v77->sa_family == v78->sa_family )
                      {
                        if ( INETADDR_ISEQUAL(v77, v78) )
                          *(_BYTE *)(v79 + 1577) = 1;
                      }
                    }
                  }
                  v50 = IN4_IS_ADDR_RFC1918((const IN_ADDR *)(v73 + 4)) == 0;
                  v81 = *a1;
                  if ( v50 )
                  {
                    ++*((_DWORD *)v81 + 330);
                    ++*((_DWORD *)*a1 + 335);
                  }
                  else
                  {
                    ++*((_DWORD *)v81 + 331);
                    ++*((_DWORD *)*a1 + 336);
                  }
                  if ( *(_WORD *)(v80 + 4) == 0xFEA9 )
                  {
                    ++*((_DWORD *)*a1 + 332);
                    ++*((_DWORD *)*a1 + 337);
                  }
                }
                else if ( *(_WORD *)v73 == 23 )
                {
                  if ( !*((_BYTE *)*a1 + 505) )
                  {
                    v82 = *(_QWORD *)(v33 + 208);
                    if ( v82 )
                    {
                      v83 = *(const SOCKADDR **)(v82 + 16);
                      if ( v83 )
                      {
                        if ( v83->sa_family == 23 && INETADDR_ISEQUAL(v83, *(const SOCKADDR **)(v69 + 16)) )
                        {
                          *(_BYTE *)(v84 + 1390) = 1;
                          *((_BYTE *)*a1 + 505) = 1;
                        }
                      }
                    }
                  }
                  if ( *((_BYTE *)*a1 + 505) == (_BYTE)v28
                    && v118.sa_family == 23
                    && v120 == *(_DWORD *)(v73 + 24)
                    && v119 == *(_QWORD *)(v73 + 16)
                    && *(_QWORD *)&v118.sa_data[6] == *(_QWORD *)(v73 + 8) )
                  {
                    *((_BYTE *)*a1 + 1390) = 1;
                    *((_BYTE *)*a1 + 505) = 1;
                  }
                  if ( *((_BYTE *)*a1 + 1617) == (_BYTE)v28 )
                  {
                    v85 = *(const SOCKADDR **)(v33 + 280);
                    if ( v85 )
                    {
                      v86 = *(const SOCKADDR **)(v69 + 16);
                      if ( v85->sa_family == v86->sa_family )
                      {
                        if ( INETADDR_ISEQUAL(v85, v86) )
                          *(_BYTE *)(v87 + 1617) = 1;
                      }
                    }
                  }
                  if ( *(_BYTE *)(v73 + 8) == 0xFE && (*(_BYTE *)(v73 + 9) & 0xC0) == 0x80 )
                  {
                    ++*((_DWORD *)*a1 + 334);
                    ++*((_DWORD *)*a1 + 339);
                  }
                  if ( IN6_IS_ADDR_GLOBAL((const IN6_ADDR *)(v73 + 8)) )
                  {
                    ++*((_DWORD *)*a1 + 333);
                    ++*((_DWORD *)*a1 + 338);
                  }
                }
              }
              v69 = *(_QWORD *)(v69 + 8);
            }
            while ( v69 );
            v5 = a2;
          }
          v88 = *(_QWORD *)(v33 + 208);
          if ( v88 )
          {
            do
            {
              v89 = *(_QWORD *)(v88 + 16);
              if ( v89 )
              {
                if ( *(_WORD *)v89 == 2 )
                {
                  v50 = IN4_IS_ADDR_RFC1918((const IN_ADDR *)(v89 + 4)) == 0;
                  v91 = *a1;
                  if ( v50 )
                  {
                    ++*((_DWORD *)v91 + 341);
                    ++*((_DWORD *)*a1 + 344);
                  }
                  else
                  {
                    ++*((_DWORD *)v91 + 342);
                    ++*((_DWORD *)*a1 + 345);
                  }
                  if ( *(_WORD *)(v90 + 4) == 0xFEA9 )
                  {
                    ++*((_DWORD *)*a1 + 343);
                    ++*((_DWORD *)*a1 + 346);
                  }
                  if ( *((_BYTE *)*a1 + 1388) == (_BYTE)v28 )
                  {
                    v92 = *(_QWORD *)(v33 + 232);
                    if ( v92 )
                    {
                      if ( *(_WORD *)v92 == 2 )
                        *((_BYTE *)*a1 + 1388) = *(_DWORD *)(v92 + 4) == *(_DWORD *)(v90 + 4);
                    }
                  }
                }
                else if ( *(_WORD *)v89 == 23 && *((_BYTE *)*a1 + 1389) == (_BYTE)v28 )
                {
                  v93 = *(const SOCKADDR **)(v33 + 280);
                  if ( v93 )
                  {
                    if ( v93->sa_family == 23 )
                    {
                      v94 = INETADDR_ISEQUAL(v93, (const SOCKADDR *)v89);
                      *(_BYTE *)(v95 + 1389) = v94;
                    }
                  }
                }
              }
              v88 = *(_QWORD *)(v88 + 8);
            }
            while ( v88 );
            v5 = a2;
          }
LABEL_268:
          v33 = *(_QWORD *)(v33 + 8);
          if ( !v33 )
            goto LABEL_269;
        }
        v48 = *(const IN_ADDR **)(v33 + 280);
        if ( v48->S_un.S_un_w.s_w1 == 2 )
        {
          v49 = IN4_IS_ADDR_RFC1918(v48 + 1);
        }
        else
        {
          if ( v48->S_un.S_un_w.s_w1 != 23 )
          {
LABEL_69:
            StringFromAddress((unsigned __int16 *)*a1 + 810, 0x2Eu, *(LPSOCKADDR *)(v33 + 280), *(_DWORD *)(v33 + 288));
            *((_BYTE *)*a1 + 1619) = IsSockAddrOnLink(*(_QWORD *)(v33 + 24), *(_QWORD *)(v33 + 280));
            v28 = 0;
            goto LABEL_70;
          }
          if ( v48[2].S_un.S_un_b.s_b1 != 0xFE || (v50 = (v48[2].S_un.S_un_b.s_b2 & 0xC0) == 0x80, v49 = 1, !v50) )
            v49 = 0;
        }
        *((_BYTE *)v47 + 1618) = v49;
        goto LABEL_69;
      }
LABEL_269:
      *((_DWORD *)*a1 + 432) = *((_DWORD *)*a1 + 371);
      *((_DWORD *)*a1 + 433) = *((_DWORD *)*a1 + 372);
      *((_DWORD *)*a1 + 434) = *((_DWORD *)*a1 + 124);
      *((_DWORD *)*a1 + 435) = *((_DWORD *)*a1 + 125);
      *((_DWORD *)*a1 + 436) = *((_DWORD *)*a1 + 130);
      *((_DWORD *)*a1 + 437) = *((_DWORD *)*a1 + 131);
      *((_DWORD *)*a1 + 438) = *((_DWORD *)*a1 + 329);
      *((_DWORD *)*a1 + 439) = *((_DWORD *)*a1 + 328);
      *((_DWORD *)*a1 + 440) = *((_DWORD *)*a1 + 327);
      *((_DWORD *)*a1 + 441) = *((_DWORD *)*a1 + 346);
      *((_DWORD *)*a1 + 442) = *((_DWORD *)*a1 + 345);
      *((_DWORD *)*a1 + 443) = *((_DWORD *)*a1 + 344);
      *((_DWORD *)*a1 + 444) = *((_DWORD *)*a1 + 337);
      *((_DWORD *)*a1 + 445) = *((_DWORD *)*a1 + 336);
      *((_DWORD *)*a1 + 446) = *((_DWORD *)*a1 + 335);
      *((_DWORD *)*a1 + 447) = *((_DWORD *)*a1 + 339);
      *((_DWORD *)*a1 + 448) = *((_DWORD *)*a1 + 338);
      *((_DWORD *)*a1 + 449) = *((_DWORD *)*a1 + 373);
      *((_DWORD *)*a1 + 450) = *((_DWORD *)*a1 + 374);
      *((_DWORD *)*a1 + 451) = *((_DWORD *)*a1 + 375);
      *((_DWORD *)*a1 + 452) = *((_DWORD *)*a1 + 376);
      *((_DWORD *)*a1 + 453) = *((_DWORD *)*a1 + 377);
      *((_DWORD *)*a1 + 454) = *((_DWORD *)*a1 + 378);
      *((_DWORD *)*a1 + 455) = *((_DWORD *)*a1 + 379);
      *((_DWORD *)*a1 + 456) = *((unsigned __int8 *)*a1 + 1477);
      *((_DWORD *)*a1 + 457) = *((_DWORD *)*a1 + 325);
      *((_DWORD *)*a1 + 458) = *((_DWORD *)*a1 + 324);
      *((_DWORD *)*a1 + 459) = *((_DWORD *)*a1 + 326);
      *((_DWORD *)*a1 + 460) = *((_DWORD *)*a1 + 348);
      *((_DWORD *)*a1 + 461) = *((_DWORD *)*a1 + 349);
      *((_DWORD *)*a1 + 462) = *((_DWORD *)*a1 + 350);
      *((_DWORD *)*a1 + 463) = *((_DWORD *)*a1 + 351);
      *((_DWORD *)*a1 + 464) = *((_DWORD *)*a1 + 352);
      *((_DWORD *)*a1 + 465) = *((_DWORD *)*a1 + 353);
      *((_DWORD *)*a1 + 466) = *((_DWORD *)*a1 + 354);
      *((_DWORD *)*a1 + 467) = *((_DWORD *)*a1 + 355);
      *((_DWORD *)*a1 + 468) = *((_DWORD *)*a1 + 356);
      *((_DWORD *)*a1 + 469) = *((_DWORD *)*a1 + 357);
      *((_DWORD *)*a1 + 470) = *((_DWORD *)*a1 + 358);
      *((_DWORD *)*a1 + 471) = *((_DWORD *)*a1 + 359);
      *((_DWORD *)*a1 + 472) = *((_DWORD *)*a1 + 360);
      *((_DWORD *)*a1 + 473) = *((_DWORD *)*a1 + 361);
      *((_DWORD *)*a1 + 474) = *((_DWORD *)*a1 + 362);
      *((_DWORD *)*a1 + 475) = *((_DWORD *)*a1 + 363);
      *((_DWORD *)*a1 + 476) = *((_DWORD *)*a1 + 364);
      *((_DWORD *)*a1 + 477) = *((_DWORD *)*a1 + 365);
      *((_DWORD *)*a1 + 478) = *((_DWORD *)*a1 + 366);
      *((_DWORD *)*a1 + 479) = *((_DWORD *)*a1 + 367);
      *((_DWORD *)*a1 + 480) = *((_DWORD *)*a1 + 368);
      *((_DWORD *)*a1 + 481) = *((_DWORD *)*a1 + 340);
      *((_BYTE *)*a1 + 1928) = *((_BYTE *)*a1 + 24);
      *((_BYTE *)*a1 + 1929) = *((_BYTE *)*a1 + 25);
      *((_BYTE *)*a1 + 1930) = *((_BYTE *)*a1 + 26);
      *((_BYTE *)*a1 + 1931) = *((_BYTE *)*a1 + 27);
      *((_BYTE *)*a1 + 1932) = *((_BYTE *)*a1 + 28);
      *((_BYTE *)*a1 + 1933) = *((_BYTE *)*a1 + 29);
      *((_BYTE *)*a1 + 1934) = *((_BYTE *)*a1 + 30);
      *((_BYTE *)*a1 + 1935) = *((_BYTE *)*a1 + 31);
      *((_BYTE *)*a1 + 1936) = *((_BYTE *)*a1 + 32);
      *((_BYTE *)*a1 + 1937) = *((_BYTE *)*a1 + 35);
      *((_BYTE *)*a1 + 1938) = *((_BYTE *)*a1 + 36) == 1;
      *((_BYTE *)*a1 + 1939) = *((_BYTE *)*a1 + 37);
      *((_BYTE *)*a1 + 1940) = *((_BYTE *)*a1 + 38) == 1;
      *((_BYTE *)*a1 + 1941) = *((_BYTE *)*a1 + 39) == 1;
      *((_BYTE *)*a1 + 1942) = *((_BYTE *)*a1 + 41) == 1;
      *((_BYTE *)*a1 + 1943) = *((_BYTE *)*a1 + 45);
      *((_BYTE *)*a1 + 1944) = *((_BYTE *)*a1 + 46);
      *((_BYTE *)*a1 + 1945) = *((_BYTE *)*a1 + 504);
      *((_BYTE *)*a1 + 1946) = *((_BYTE *)*a1 + 505);
      *((_BYTE *)*a1 + 1947) = *((_BYTE *)*a1 + 1576);
      *((_BYTE *)*a1 + 1948) = *((_BYTE *)*a1 + 1577);
      *((_BYTE *)*a1 + 1949) = *((_BYTE *)*a1 + 1578);
      *((_BYTE *)*a1 + 1950) = *((_BYTE *)*a1 + 1616);
      *((_BYTE *)*a1 + 1951) = *((_BYTE *)*a1 + 1617);
      *((_BYTE *)*a1 + 1952) = *((_BYTE *)*a1 + 1618);
      *((_BYTE *)*a1 + 1953) = *((_BYTE *)*a1 + 1476);
      *((_BYTE *)*a1 + 1954) = *((_BYTE *)*a1 + 40);
      *((_BYTE *)*a1 + 1955) = *((_BYTE *)*a1 + 43);
      *((_BYTE *)*a1 + 1956) = *((_BYTE *)*a1 + 42);
      *((_BYTE *)*a1 + 1957) = *((_BYTE *)*a1 + 44);
      *((_BYTE *)*a1 + 1958) = *((_BYTE *)*a1 + 47);
      *((_BYTE *)*a1 + 1959) = *((_BYTE *)*a1 + 1388);
      *((_BYTE *)*a1 + 1960) = *((_BYTE *)*a1 + 1389);
      *((_BYTE *)*a1 + 1961) = *((_BYTE *)*a1 + 1390);
      *((_BYTE *)*a1 + 1962) = *((_BYTE *)*a1 + 1579);
      *((_BYTE *)*a1 + 1963) = *((_BYTE *)*a1 + 1619);
      *((_BYTE *)*a1 + 1964) = *((_BYTE *)*a1 + 49);
      *((_BYTE *)*a1 + 1965) = *((_BYTE *)*a1 + 50);
      *((_BYTE *)*a1 + 1966) = *((_BYTE *)*a1 + 51);
      *((_BYTE *)*a1 + 1967) = *((_BYTE *)*a1 + 52);
      *((_BYTE *)*a1 + 1968) = *((_BYTE *)*a1 + 33);
      *((_BYTE *)*a1 + 1969) = *((_BYTE *)*a1 + 34);
      *((_DWORD *)*a1 + 493) = *((_DWORD *)*a1 + 2);
      *((_DWORD *)*a1 + 494) = *((_DWORD *)*a1 + 3);
      *((_DWORD *)*a1 + 495) = *((_DWORD *)*a1 + 4);
      *((_DWORD *)*a1 + 496) = *((_DWORD *)*a1 + 5);
      *((_DWORD *)*a1 + 497) = *((_DWORD *)*a1 + 380);
      v110 = v28;
      do
        *((_DWORD *)*a1 + v110++ + 498) = v28;
      while ( v110 != 2 );
      *((_DWORD *)*a1 + 500) = *((_DWORD *)*a1 + 16);
      *((_DWORD *)*a1 + 501) = *((_DWORD *)*a1 + 17);
      *((_DWORD *)*a1 + 502) = *((_DWORD *)*a1 + 18);
      *((_DWORD *)*a1 + 503) = *((_DWORD *)*a1 + 127);
      *((_DWORD *)*a1 + 504) = *((_DWORD *)*a1 + 128);
      *((_DWORD *)*a1 + 505) = *((_DWORD *)*a1 + 129);
      *((_DWORD *)*a1 + 506) = *((_DWORD *)*a1 + 430);
      *((_DWORD *)*a1 + 507) = *((_DWORD *)*a1 + 431);
      *((_DWORD *)*a1 + 508) = *((_DWORD *)*a1 + 370);
      *((_DWORD *)*a1 + 509) = *((_DWORD *)*a1 + 428);
      *((_DWORD *)*a1 + 510) = *((_DWORD *)*a1 + 429);
      *((_DWORD *)*a1 + 511) = *((_DWORD *)*a1 + 341);
      *((_DWORD *)*a1 + 512) = *((_DWORD *)*a1 + 342);
      *((_DWORD *)*a1 + 513) = *((_DWORD *)*a1 + 330);
      *((_DWORD *)*a1 + 514) = *((_DWORD *)*a1 + 331);
      *((_DWORD *)*a1 + 515) = *((_DWORD *)*a1 + 332);
      *((_DWORD *)*a1 + 516) = *((_DWORD *)*a1 + 333);
      *((_DWORD *)*a1 + 517) = *((_DWORD *)*a1 + 334);
      *((_DWORD *)*a1 + 518) = *((_DWORD *)*a1 + 14);
      *((_DWORD *)*a1 + 519) = *((_DWORD *)*a1 + 15);
      *((_DWORD *)*a1 + 520) = *((_DWORD *)*a1 + 1);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800349f0  mov     [rsp-8+arg_10], rbx
0x1800349f5  mov     [rsp-8+arg_0], rcx
0x1800349fa  push    rbp
0x1800349fb  push    rsi
0x1800349fc  push    rdi
0x1800349fd  push    r12
0x1800349ff  push    r13
0x180034a01  push    r14
0x180034a03  push    r15
0x180034a05  lea     rbp, [rsp-27h]
0x180034a0a  sub     rsp, 100h
0x180034a11  mov     rax, cs:__security_cookie
0x180034a18  xor     rax, rsp
0x180034a1b  mov     [rbp+57h+var_40], rax
0x180034a1f  mov     r15d, r9d
0x180034a22  mov     rdi, rdx
0x180034a25  mov     [rsp+130h+var_100], rdx
0x180034a2a  mov     rbx, rcx
0x180034a2d  mov     [rbp+57h+var_D0], rcx
0x180034a31  mov     r13d, 1
0x180034a37  mov     [rbp+57h+dwAddressStringLength], r13d
0x180034a3b  xor     r12d, r12d
0x180034a3e  mov     esi, r12d
0x180034a41  cmp     r8d, 2
0x180034a45  cmovbe  esi, r8d
0x180034a49  xor     eax, eax
0x180034a4b  mov     [rcx], rax
0x180034a4e  call    cs:__imp_GetProcessHeap
0x180034a54  mov     rcx, rax; hHeap
0x180034a57  lea     edx, [r13+7]; dwFlags
0x180034a5b  mov     r8d, 9A8h; dwBytes
0x180034a61  call    cs:__imp_HeapAlloc
0x180034a67  mov     r14, rax
0x180034a6a  mov     [rbx], rax
0x180034a6d  test    rax, rax
0x180034a70  jz      short loc_180034A8B
0x180034a72  xor     edx, edx; Val
0x180034a74  mov     r8d, 9A8h; Size
0x180034a7a  mov     rcx, rax; void *
0x180034a7d  call    memset_0
0x180034a82  mov     rcx, r14; this
0x180034a85  call    ??0NCSI_TELEMETRY_DETAIL@@QEAA@XZ; NCSI_TELEMETRY_DETAIL::NCSI_TELEMETRY_DETAIL(void)
0x180034a8a  nop
0x180034a8b  mov     [rbp+57h+dwAddressStringLength], r13d
0x180034a8f  mov     rcx, [rbx]
0x180034a92  test    rcx, rcx
0x180034a95  jz      loc_180036237
0x180034a9b  cmp     r15d, r13d
0x180034a9e  setz    al
0x180034aa1  mov     [rcx], al
0x180034aa3  mov     edx, esi
0x180034aa5  mov     rcx, rdi
0x180034aa8  call    ?GetSuspectEventCountSinceLastInternet@NCSI_INTERFACE_ATTRIBUTES@@QEBAIW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::GetSuspectEventCountSinceLastInternet(_NLA_CONNECTIVITY_FAMILY)
0x180034aad  mov     ecx, eax
0x180034aaf  mov     rax, [rbx]
0x180034ab2  mov     [rax+4], ecx
0x180034ab5  mov     rcx, rdi
0x180034ab8  call    ?HadInternetSinceReset@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HadInternetSinceReset(_NLA_CONNECTIVITY_FAMILY)
0x180034abd  mov     cl, al
0x180034abf  mov     rax, [rbx]
0x180034ac2  mov     [rax+37h], cl
0x180034ac5  mov     ecx, [rdi+114Ch]
0x180034acb  mov     eax, [rdi+1148h]
0x180034ad1  cmp     eax, ecx
0x180034ad3  cmovge  ecx, eax
0x180034ad6  mov     rax, [rbx]
0x180034ad9  mov     [rax+8], ecx
0x180034adc  mov     ecx, [rdi+20B4h]
0x180034ae2  mov     eax, [rdi+20B0h]
0x180034ae8  cmp     eax, ecx
0x180034aea  cmovge  ecx, eax
0x180034aed  mov     rax, [rbx]
0x180034af0  mov     [rax+0Ch], ecx
0x180034af3  mov     rcx, [rbx]
0x180034af6  mov     eax, [rdi+1148h]
0x180034afc  mov     [rcx+10h], eax
0x180034aff  mov     rcx, [rbx]
0x180034b02  mov     eax, [rdi+20B0h]
0x180034b08  mov     [rcx+14h], eax
0x180034b0b  mov     rcx, rdi; this
0x180034b0e  call    ?GetOperStatus@NCSI_INTERFACE_ATTRIBUTES@@QEBA?AW4IF_OPER_STATUS@@XZ; NCSI_INTERFACE_ATTRIBUTES::GetOperStatus(void)
0x180034b13  cmp     eax, r13d
0x180034b16  setz    cl
0x180034b19  mov     rax, [rbx]
0x180034b1c  mov     [rax+18h], cl
0x180034b1f  mov     rcx, rdi; this
0x180034b22  call    ?GetOperStatus@NCSI_INTERFACE_ATTRIBUTES@@QEBA?AW4IF_OPER_STATUS@@XZ; NCSI_INTERFACE_ATTRIBUTES::GetOperStatus(void)
0x180034b27  cmp     eax, r13d
0x180034b2a  setnz   cl
0x180034b2d  mov     rax, [rbx]
0x180034b30  mov     [rax+19h], cl
0x180034b33  mov     rcx, rdi; this
0x180034b36  call    ?IsDormant@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NXZ; NCSI_INTERFACE_ATTRIBUTES::IsDormant(void)
0x180034b3b  mov     cl, al
0x180034b3d  mov     rax, [rbx]
0x180034b40  mov     [rax+1Ah], cl
0x180034b43  mov     rcx, [rbx]
0x180034b46  mov     al, [rdi+1101h]
0x180034b4c  mov     [rcx+1Bh], al
0x180034b4f  mov     rcx, [rbx]
0x180034b52  mov     al, [rdi+2069h]
0x180034b58  mov     [rcx+1Ch], al
0x180034b5b  mov     rcx, [rbx]
0x180034b5e  mov     al, [rdi+1102h]
0x180034b64  mov     [rcx+1Dh], al
0x180034b67  mov     rcx, [rbx]
0x180034b6a  mov     al, [rdi+206Ah]
0x180034b70  mov     [rcx+1Eh], al
0x180034b73  mov     rcx, [rbx]
0x180034b76  mov     al, [rdi+1103h]
0x180034b7c  mov     [rcx+2Fh], al
0x180034b7f  mov     rcx, [rbx]
0x180034b82  mov     al, [rdi+206Bh]
0x180034b88  mov     [rcx+30h], al
0x180034b8b  xor     edx, edx
0x180034b8d  mov     rcx, rdi
0x180034b90  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180034b95  mov     cl, al
0x180034b97  mov     rax, [rbx]
0x180034b9a  mov     [rax+1Fh], cl
0x180034b9d  mov     edx, r13d
0x180034ba0  mov     rcx, rdi
0x180034ba3  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180034ba8  mov     cl, al
0x180034baa  mov     rax, [rbx]
0x180034bad  mov     [rax+20h], cl
0x180034bb0  xor     edx, edx
0x180034bb2  mov     rcx, rdi
0x180034bb5  call    ?HasInternetBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180034bba  mov     cl, al
0x180034bbc  mov     rax, [rbx]
0x180034bbf  mov     [rax+21h], cl
0x180034bc2  mov     edx, r13d
0x180034bc5  mov     rcx, rdi
0x180034bc8  call    ?HasInternetBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180034bcd  mov     cl, al
0x180034bcf  mov     rax, [rbx]
0x180034bd2  mov     [rax+21h], cl
0x180034bd5  mov     rcx, [rbx]
0x180034bd8  mov     al, [rdi+2D8Ch]
0x180034bde  mov     [rcx+23h], al
0x180034be1  prefetchw byte ptr [rdi+20h]
0x180034be5  mov     eax, [rdi+20h]
0x180034be8  mov     ecx, eax
0x180034bea  or      ecx, r12d
0x180034bed  lock cmpxchg [rdi+20h], ecx
0x180034bf2  jnz     short loc_180034BE8
0x180034bf4  test    eax, eax
0x180034bf6  setnz   cl; this
0x180034bf9  mov     rax, [rbx]
0x180034bfc  mov     [rax+24h], cl
0x180034bff  call    ?CorpLocationProbeEnabled@NcsiConfigData@@QEAA_NXZ; NcsiConfigData::CorpLocationProbeEnabled(void)
0x180034c04  mov     cl, al
0x180034c06  mov     rax, [rbx]
0x180034c09  mov     [rax+25h], cl
0x180034c0c  prefetchw byte ptr [rdi+28h]
0x180034c10  mov     eax, [rdi+28h]
0x180034c13  mov     ecx, eax
0x180034c15  or      ecx, r12d
0x180034c18  lock cmpxchg [rdi+28h], ecx
0x180034c1d  jnz     short loc_180034C13
0x180034c1f  test    eax, eax
0x180034c21  setnz   cl
0x180034c24  mov     rax, [rbx]
0x180034c27  mov     [rax+26h], cl
0x180034c2a  cmp     r12w, [rdi+1108h]
0x180034c32  setnz   cl
0x180034c35  mov     rax, [rbx]
0x180034c38  mov     [rax+27h], cl
0x180034c3b  cmp     r12w, [rdi+2070h]
0x180034c43  setnz   cl
0x180034c46  mov     rax, [rbx]
0x180034c49  mov     [rax+29h], cl
0x180034c4c  mov     rcx, [rbx]
0x180034c4f  mov     al, [rdi+1192h]
0x180034c55  mov     [rcx+2Dh], al
0x180034c58  mov     rcx, [rbx]
0x180034c5b  mov     al, [rdi+20FAh]
0x180034c61  mov     [rcx+2Eh], al
0x180034c64  mov     rcx, [rbx]
0x180034c67  mov     eax, [rdi+11B0h]
0x180034c6d  mov     [rcx+38h], eax
0x180034c70  mov     rcx, [rbx]
0x180034c73  mov     eax, [rdi+2118h]
0x180034c79  mov     [rcx+3Ch], eax
0x180034c7c  mov     rcx, rdi; this
0x180034c7f  call    ?GetInterfaceUpTime@NCSI_INTERFACE_ATTRIBUTES@@QEAAKXZ; NCSI_INTERFACE_ATTRIBUTES::GetInterfaceUpTime(void)
0x180034c84  mov     ecx, eax
0x180034c86  mov     rax, [rbx]
0x180034c89  mov     [rax+40h], ecx
0x180034c8c  mov     rax, [rbx]
0x180034c8f  mov     [rax+44h], r12d
0x180034c93  mov     rax, [rbx]
0x180034c96  mov     [rax+48h], r12d
0x180034c9a  mov     rcx, [rbx]
0x180034c9d  cmp     [rcx+19h], r12b
0x180034ca1  jz      short loc_180034CBC
0x180034ca3  mov     eax, [rdi+2DA8h]
0x180034ca9  mov     [rcx+44h], eax
0x180034cac  mov     rcx, rdi; this
0x180034caf  call    ?AgeOfDisconnect@NCSI_INTERFACE_ATTRIBUTES@@QEBAKXZ; NCSI_INTERFACE_ATTRIBUTES::AgeOfDisconnect(void)
0x180034cb4  mov     ecx, eax
0x180034cb6  mov     rax, [rbx]
0x180034cb9  mov     [rax+48h], ecx
0x180034cbc  mov     rcx, [rbx]
0x180034cbf  mov     al, [rdi+1190h]
0x180034cc5  mov     [rcx+31h], al
0x180034cc8  mov     rcx, [rbx]
0x180034ccb  mov     al, [rdi+20F8h]
0x180034cd1  mov     [rcx+32h], al
0x180034cd4  mov     rcx, [rbx]
0x180034cd7  mov     al, [rdi+1191h]
0x180034cdd  mov     [rcx+33h], al
0x180034ce0  mov     rcx, [rbx]
0x180034ce3  mov     al, [rdi+20F9h]
0x180034ce9  mov     [rcx+34h], al
0x180034cec  movups  xmm0, xmmword ptr [rdi+1194h]
0x180034cf3  movups  xmmword ptr [rbp+57h+a.S_un], xmm0
0x180034cf7  movups  xmm1, xmmword ptr [rdi+11A0h]
0x180034cfe  movups  xmmword ptr [rbp+57h+a.S_un+0Ch], xmm1
0x180034d02  movups  xmm0, xmmword ptr [rdi+20FCh]
0x180034d09  movups  xmmword ptr [rbp+57h+saAddress], xmm0
0x180034d0d  movups  xmm1, xmmword ptr [rdi+2108h]
0x180034d14  movups  xmmword ptr [rbp+57h+saAddress+0Ch], xmm1
0x180034d18  lea     rcx, [rbp+57h+a.S_un+4]; a
0x180034d1c  call    IN4_IS_ADDR_RFC1918
0x180034d21  mov     dl, al
0x180034d23  mov     rax, [rbx]
0x180034d26  mov     [rax+2Bh], dl
0x180034d29  mov     r15d, 80h
0x180034d2f  mov     rax, qword ptr [rbp+57h+saAddress+8]
0x180034d33  cmp     al, 0FEh
0x180034d35  jnz     short loc_180034D45
0x180034d37  shr     rax, 8
0x180034d3b  and     al, 0C0h
0x180034d3d  cmp     al, r15b
0x180034d40  mov     cl, r13b
0x180034d43  jz      short loc_180034D48
0x180034d45  mov     cl, r12b
0x180034d48  mov     rax, [rbx]
0x180034d4b  mov     [rax+2Ch], cl
0x180034d4e  mov     rcx, [rbx]
0x180034d51  add     rcx, 5Ch ; '\'; unsigned __int16 *
0x180034d55  mov     r14d, 1Ch
0x180034d5b  mov     r9d, r14d; dwAddressLength
0x180034d5e  lea     r8, [rbp+57h+a]; lpsaAddress
0x180034d62  lea     edx, [r14-0Ah]; unsigned __int64
0x180034d66  call    StringFromAddress
0x180034d6b  mov     rcx, [rbx]
0x180034d6e  add     rcx, r15; unsigned __int16 *
0x180034d71  mov     r9d, r14d; dwAddressLength
0x180034d74  lea     r8, [rbp+57h+saAddress]; lpsaAddress
0x180034d78  lea     edx, [r14+12h]; unsigned __int64
0x180034d7c  call    StringFromAddress
0x180034d81  xor     r8d, r8d
0x180034d84  lea     rdx, [rbp+57h+var_A0]
0x180034d88  mov     rcx, rdi
0x180034d8b  call    ?GetDefaultGatewayAddress@NCSI_INTERFACE_ATTRIBUTES@@QEBA?AT_SOCKADDR_INET@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::GetDefaultGatewayAddress(_NLA_CONNECTIVITY_FAMILY)
0x180034d90  mov     r8d, r13d
0x180034d93  lea     rdx, [rbp+57h+var_C0]
0x180034d97  call    ?GetDefaultGatewayAddress@NCSI_INTERFACE_ATTRIBUTES@@QEBA?AT_SOCKADDR_INET@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::GetDefaultGatewayAddress(_NLA_CONNECTIVITY_FAMILY)
0x180034d9c  lea     rcx, [rbp+57h+var_A0.sa_data+2]; a
0x180034da0  call    IN4_IS_ADDR_RFC1918
0x180034da5  mov     dl, al
0x180034da7  mov     rax, [rbx]
0x180034daa  mov     [rax+28h], dl
0x180034dad  cmp     [rbp+57h+var_C0.sa_data+6], 0FEh
0x180034db1  jnz     short loc_180034DC0
0x180034db3  mov     al, [rbp+57h+var_C0.sa_data+7]
0x180034db6  and     al, 0C0h
0x180034db8  cmp     al, r15b
0x180034dbb  mov     cl, r13b
0x180034dbe  jz      short loc_180034DC3
0x180034dc0  mov     cl, r12b
0x180034dc3  mov     rax, [rbx]
0x180034dc6  mov     [rax+2Ah], cl
0x180034dc9  mov     rcx, [rbx]
0x180034dcc  add     rcx, 0DCh; unsigned __int16 *
0x180034dd3  mov     r9, r14; dwAddressLength
0x180034dd6  lea     r8, [rbp+57h+var_A0]; lpsaAddress
0x180034dda  mov     edx, 12h; unsigned __int64
0x180034ddf  call    StringFromAddress
0x180034de4  mov     rcx, [rbx]
0x180034de7  add     rcx, 100h; unsigned __int16 *
0x180034dee  mov     r9, r14; dwAddressLength
0x180034df1  lea     r8, [rbp+57h+var_C0]; lpsaAddress
0x180034df5  mov     edx, 2Eh ; '.'; unsigned __int64
0x180034dfa  call    StringFromAddress
0x180034dff  movups  xmm0, xmmword ptr [rdi+1124h]
0x180034e06  movups  [rsp+130h+var_F8], xmm0
0x180034e0b  movups  xmm1, xmmword ptr [rdi+1134h]
0x180034e12  movups  [rsp+130h+var_E8], xmm1
0x180034e17  movzx   eax, word ptr [rdi+1144h]
0x180034e1e  mov     [rsp+130h+var_D8], ax
0x180034e23  mov     rcx, [rbx]
0x180034e26  add     rcx, 15Ch
0x180034e2d  lea     r8, [rsp+130h+var_F8]
0x180034e32  call    StringFromMacAddress
0x180034e37  movups  xmm0, xmmword ptr [rdi+208Ch]
0x180034e3e  movups  [rsp+130h+var_F8], xmm0
  ... truncated ...
```
