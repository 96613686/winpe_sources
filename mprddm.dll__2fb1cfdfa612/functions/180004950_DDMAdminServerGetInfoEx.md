# DDMAdminServerGetInfoEx

- ea: `0x180004950`
- end: `0x18000563d`
- name: `DDMAdminServerGetInfoEx`
- size: `3309`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004950`
- `0x180007b7c`
- `0x18003b8b0`
- `0x18003b8f4`
- `0x180071cec`
- `0x180072acc`
- `0x18007339c`
- `0x1800736f8`
- `0x18007374c`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180004d54`
- `KERNEL32!HeapAlloc` at `0x180004d54`
- `KERNEL32!LeaveCriticalSection` at `0x1800050b6`
- `KERNEL32!LeaveCriticalSection` at `0x1800050b6`
- `KERNEL32!EnterCriticalSection` at `0x1800049f4`
- `KERNEL32!EnterCriticalSection` at `0x1800049f4`
- `KERNEL32!HeapFree` at `0x1800050cd`
- `KERNEL32!HeapFree` at `0x1800050cd`
- `ADVAPI32!RegCloseKey` at `0x180004eca`
- `ADVAPI32!RegCloseKey` at `0x180004f84`
- `ADVAPI32!RegCloseKey` at `0x180004eca`
- `ADVAPI32!RegCloseKey` at `0x180004f84`
- `rasman!RasGetDeviceConfigInfo` at `0x1800049d0`
- `sstpcfg!GetSstpConfiguration` at `0x180004df9`
- `sstpcfg!GetSstpConfiguration` at `0x180004df9`

## string_xrefs

- `0x180005189`: `DDMAdminServerSetInfoEx:GSetSstpConfiguration: Failed. error %d`
- `0x180005266`: `DDMAdminServerGetInfoEx:OpenIkev2ConfigKey: Failed. error %d`
- `0x18000534b`: `DDMAdminServerGetInfoEx:OpenIkev2ConfigKey: Failed. error %d`
- `0x180005215`: `DDMAdminServerGetInfoEx:GetIkev2ConfigParams: Failed. error %d`
- `0x1800052fa`: `DDMAdminServerGetInfoEx:GetIkev2ConfigParams: Failed. error %d`

## pseudocode

```c
__int64 __fastcall DDMAdminServerGetInfoEx(unsigned __int8 *a1)
{
  char *v2; // r12
  __int64 (__fastcall *v3)(int, int, int, int, void *); // r14
  unsigned int v4; // edx
  __int64 v5; // r8
  __int64 v6; // rax
  unsigned int v7; // ecx
  unsigned __int8 v8; // al
  __int64 v9; // r9
  __int64 v10; // r9
  __int64 v11; // r9
  __int64 v12; // r9
  unsigned int L2tpConfigParams; // edi
  __int64 v14; // r14
  DdmDeviceTable *Instance; // rax
  unsigned int v16; // eax
  char *v17; // rax
  char *v18; // r15
  __int64 v19; // rax
  __int64 v20; // r14
  char *v21; // r12
  char *v22; // r13
  int v23; // eax
  unsigned int SstpConfiguration; // eax
  __int64 v25; // rcx
  unsigned int v26; // eax
  int v27; // eax
  unsigned int v28; // r15d
  __int64 v29; // rcx
  unsigned int v30; // eax
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  unsigned int v33; // eax
  __int128 v34; // xmm0
  int v35; // eax
  __int128 v36; // xmm1
  int v37; // eax
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int64 v49; // r8
  __int64 v50; // rax
  __int64 v51; // r8
  __int64 v52; // rax
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  unsigned int v55; // eax
  __int128 v56; // xmm0
  int v57; // eax
  __int128 v58; // xmm1
  int v59; // eax
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  __int128 v64; // xmm0
  __int128 v65; // xmm1
  __int128 v66; // xmm0
  __int128 v67; // xmm1
  __int128 v68; // xmm0
  __int128 v69; // xmm0
  __int128 v70; // xmm1
  int v71; // eax
  __int128 v72; // xmm0
  int v73; // eax
  __int128 v74; // xmm1
  __int64 v75; // rax
  __int128 v76; // xmm0
  __int128 v77; // xmm1
  __int128 v78; // xmm0
  __int128 v79; // xmm1
  __int128 v80; // xmm0
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  __int128 v84; // xmm0
  __int128 v85; // xmm1
  int v86; // eax
  __int128 v87; // xmm0
  int v88; // eax
  __int128 v89; // xmm1
  __int64 v90; // rax
  __int128 v91; // xmm0
  __int128 v92; // xmm1
  __int128 v93; // xmm0
  __int128 v94; // xmm1
  __int128 v95; // xmm0
  __int64 v96; // xmm1_8
  int v97; // eax
  int v98; // eax
  int v99; // eax
  __int64 v100; // r9
  int v101; // [rsp+20h] [rbp-E0h]
  int v102; // [rsp+20h] [rbp-E0h]
  int v103; // [rsp+20h] [rbp-E0h]
  int v104; // [rsp+20h] [rbp-E0h]
  int v105; // [rsp+20h] [rbp-E0h]
  char *v106; // [rsp+30h] [rbp-D0h]
  unsigned int v107; // [rsp+38h] [rbp-C8h] BYREF
  SIZE_T dwBytes; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int v110; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v111; // [rsp+60h] [rbp-A0h] BYREF
  char v112; // [rsp+61h] [rbp-9Fh] BYREF
  __int16 v113; // [rsp+62h] [rbp-9Eh]
  int v114; // [rsp+64h] [rbp-9Ch]
  int v115; // [rsp+68h] [rbp-98h]
  unsigned int DeviceCount; // [rsp+6Ch] [rbp-94h]
  int v117; // [rsp+70h] [rbp-90h]
  _BYTE v118[48]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v119; // [rsp+A8h] [rbp-58h]
  __int128 v120; // [rsp+B8h] [rbp-48h]
  __int128 v121; // [rsp+C8h] [rbp-38h]
  __int128 v122; // [rsp+D8h] [rbp-28h]
  __int128 v123; // [rsp+E8h] [rbp-18h]
  __int128 v124; // [rsp+F8h] [rbp-8h]
  __int128 v125; // [rsp+108h] [rbp+8h]
  __int128 v126; // [rsp+118h] [rbp+18h]
  __int128 v127; // [rsp+128h] [rbp+28h] BYREF
  __int128 v128; // [rsp+138h] [rbp+38h] BYREF
  __int128 v129; // [rsp+148h] [rbp+48h]
  _BYTE v130[16]; // [rsp+160h] [rbp+60h] BYREF
  int *v131; // [rsp+170h] [rbp+70h]
  int v132; // [rsp+178h] [rbp+78h]
  int v133; // [rsp+17Ch] [rbp+7Ch]
  int v134; // [rsp+180h] [rbp+80h] BYREF
  char v135[2044]; // [rsp+184h] [rbp+84h] BYREF

  v2 = 0;
  memset_0(&v112, 0, 0xF7u);
  v107 = 0;
  dwBytes = 0;
  v134 = 0;
  memset_0(v135, 0, sizeof(v135));
  v3 = (__int64 (__fastcall *)(int, int, int, int, void *))RasGetDeviceConfigInfo;
  if ( dword_1800C8654 )
    v3 = DdmGetDeviceConfigInfo;
  memset_0(&v111, 0, 0xE8u);
  EnterCriticalSection(&gblDeviceTable);
  v4 = *a1;
  if ( v4 == 1 )
  {
    v7 = *((unsigned __int16 *)a1 + 5);
    if ( (unsigned __int16)v7 < 0x80u || a1[9] != 2 || (v8 = a1[8], v8 != 1) )
    {
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_45;
      v100 = a1[9];
      v105 = a1[8];
      LOWORD(v134) = 0;
      FormatRRASErrorString(&v134, L"DDMAdminServerGetInfoEx: Invalid Version %d/type%d/size %d", v7, v100, v105);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_45;
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)&v135[2 * v6 - 4] );
      goto LABEL_44;
    }
  }
  else
  {
    switch ( *a1 )
    {
      case 2u:
        v7 = *((unsigned __int16 *)a1 + 5);
        if ( (unsigned __int16)v7 < 0xA0u || a1[9] != 2 || (v8 = a1[8], v8 != (_BYTE)v4) )
        {
          if ( (byte_1800C8404 & 0x10) == 0 )
            goto LABEL_45;
          v12 = a1[9];
          v104 = a1[8];
          LOWORD(v134) = 0;
          FormatRRASErrorString(&v134, L"DDMAdminServerGetInfoEx: Invalid Version %d/type%d/size %d", v7, v12, v104);
          if ( (byte_1800C8404 & 0x10) == 0 )
            goto LABEL_45;
          v6 = -1;
          do
            ++v6;
          while ( *(_WORD *)&v135[2 * v6 - 4] );
          goto LABEL_44;
        }
        break;
      case 3u:
        v7 = *((unsigned __int16 *)a1 + 5);
        if ( (unsigned __int16)v7 < 0xE0u || a1[9] != 2 || (v8 = a1[8], v8 != (_BYTE)v4) )
        {
          if ( (byte_1800C8404 & 0x10) == 0 )
            goto LABEL_45;
          v11 = a1[9];
          v103 = a1[8];
          LOWORD(v134) = 0;
          FormatRRASErrorString(&v134, L"DDMAdminServerGetInfoEx: Invalid Version %d/type%d/size %d", v7, v11, v103);
          if ( (byte_1800C8404 & 0x10) == 0 )
            goto LABEL_45;
          v6 = -1;
          do
            ++v6;
          while ( *(_WORD *)&v135[2 * v6 - 4] );
          goto LABEL_44;
        }
        break;
      case 4u:
        v7 = *((unsigned __int16 *)a1 + 5);
        if ( (unsigned __int16)v7 < 8u || a1[9] != 2 || (v8 = a1[8], v8 != (_BYTE)v4) )
        {
          if ( (byte_1800C8404 & 0x10) == 0 )
            goto LABEL_45;
          v10 = a1[9];
          v102 = a1[8];
          LOWORD(v134) = 0;
          FormatRRASErrorString(&v134, L"DDMAdminServerGetInfoEx: Invalid Version %d/type%d/size %d", v7, v10, v102);
          if ( (byte_1800C8404 & 0x10) == 0 )
            goto LABEL_45;
          v6 = -1;
          do
            ++v6;
          while ( *(_WORD *)&v135[2 * v6 - 4] );
          goto LABEL_44;
        }
        break;
      case 5u:
        v7 = *((unsigned __int16 *)a1 + 5);
        if ( (unsigned __int16)v7 < 8u || a1[9] != 2 || (v8 = a1[8], v8 != (_BYTE)v4) )
        {
          if ( (byte_1800C8404 & 0x10) == 0 )
            goto LABEL_45;
          v9 = a1[9];
          v101 = a1[8];
          LOWORD(v134) = 0;
          FormatRRASErrorString(&v134, L"DDMAdminServerGetInfoEx: Invalid Version %d/type%d/size %d", v7, v9, v101);
          if ( (byte_1800C8404 & 0x10) == 0 )
            goto LABEL_45;
          v6 = -1;
          do
            ++v6;
          while ( *(_WORD *)&v135[2 * v6 - 4] );
          goto LABEL_44;
        }
        break;
      default:
        if ( (byte_1800C8404 & 0x10) == 0 )
          goto LABEL_45;
        LOWORD(v134) = 0;
        FormatRRASErrorString(&v134, L"DDMAdminServerGetInfoEx: Invalid revision %d", v4);
        if ( (byte_1800C8404 & 0x10) == 0 )
          goto LABEL_45;
        v6 = -1;
        do
          ++v6;
        while ( *(_WORD *)&v135[2 * v6 - 4] );
LABEL_44:
        v133 = 0;
        v132 = 2 * v6 + 2;
        v131 = &v134;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v5, 2, v130);
LABEL_45:
        L2tpConfigParams = 87;
LABEL_46:
        v14 = -1;
        goto LABEL_111;
    }
  }
  v113 = v7;
  v112 = 2;
  v111 = v8;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DeviceCount = DdmDeviceTable::GetDeviceCount(Instance);
  v117 = dword_1800C84B0;
  HIDWORD(dwBytes) = 6;
  v16 = v3(0, (int)&dwBytes + 4, (int)&v107, (int)&dwBytes, 0);
  L2tpConfigParams = v16;
  if ( !v16 )
  {
    L2tpConfigParams = 4319;
    goto LABEL_46;
  }
  if ( v16 != 603 )
    goto LABEL_46;
  L2tpConfigParams = 8;
  v17 = (char *)HeapAlloc(hHeap, 8u, (unsigned int)dwBytes);
  v106 = v17;
  v18 = v17;
  if ( !v17 )
  {
    v14 = -1;
    v2 = 0;
    goto LABEL_111;
  }
  L2tpConfigParams = v3(0, (int)&dwBytes + 4, (int)&v107, (int)&dwBytes, v17);
  if ( L2tpConfigParams )
  {
    v14 = -1;
    v2 = v18;
    goto LABEL_111;
  }
  v19 = 0;
  v110 = 0;
  if ( !v107 )
    goto LABEL_103;
  while ( 1 )
  {
    v20 = 472 * v19;
    v21 = &v18[472 * v19 + 28];
    v22 = &v18[472 * v19 + 8];
    if ( *(_WORD *)&v18[472 * v19 + 48] != 14 )
      goto LABEL_64;
    LODWORD(v127) = *(_DWORD *)v21;
    v23 = DWORD1(v127);
    if ( *(_DWORD *)v22 )
    {
      v23 = DWORD1(v127) | 1;
      DWORD1(v127) |= 1u;
    }
    if ( *(_DWORD *)&v18[v20 + 12] )
      DWORD1(v127) = v23 | 2;
    SstpConfiguration = GetSstpConfiguration(0, 0, &v128, (char *)&v127 + 8);
    L2tpConfigParams = SstpConfiguration;
    if ( SstpConfiguration )
      break;
    HIDWORD(v127) = 32780;
LABEL_64:
    if ( *(_WORD *)&v18[v20 + 48] == 8 )
    {
      v21 = &v18[v20 + 28];
      v22 = &v18[v20 + 8];
      DWORD2(v123) = *(_DWORD *)v21;
      if ( *(_DWORD *)v22 )
        HIDWORD(v123) |= 1u;
      if ( *(_DWORD *)&v18[v20 + 12] )
        HIDWORD(v123) |= 2u;
    }
    if ( *(_WORD *)&v18[v20 + 48] == 9 )
    {
      LODWORD(v124) = *(_DWORD *)v21;
      if ( *(_DWORD *)v22 )
        DWORD1(v124) |= 1u;
      if ( *(_DWORD *)&v18[v20 + 12] )
        DWORD1(v124) |= 2u;
      if ( v111 >= 3u )
      {
        hKey = 0;
        v25 = (unsigned int)((char)v111 - 3);
        if ( v111 != 3 )
          v25 = (unsigned int)((char)v111 - 4);
        v26 = OpenL2tpConfigKey(v25, &hKey);
        L2tpConfigParams = v26;
        if ( v26 )
        {
          if ( (byte_1800C8404 & 8) != 0 )
          {
            LOWORD(v134) = 0;
            FormatRRASErrorString(&v134, L"DDMAdminServerGetInfoEx:OpenIkev2ConfigKey: Failed. error %d", v26);
            v14 = -1;
            if ( (byte_1800C8404 & 8) == 0 )
              goto LABEL_104;
            v52 = -1;
            do
              ++v52;
            while ( *(_WORD *)&v135[2 * v52 - 4] );
            goto LABEL_132;
          }
LABEL_103:
          v14 = -1;
          goto LABEL_104;
        }
        L2tpConfigParams = GetL2tpConfigParams(hKey);
        RegCloseKey(hKey);
        if ( L2tpConfigParams )
        {
          if ( (byte_1800C8404 & 8) == 0 )
            goto LABEL_152;
          LOWORD(v134) = 0;
          FormatRRASErrorString(
            &v134,
            L"DDMAdminServerGetInfoEx:GetIkev2ConfigParams: Failed. error %d",
            L2tpConfigParams);
          v14 = -1;
          if ( (byte_1800C8404 & 8) == 0 )
            goto LABEL_110;
          v50 = -1;
          do
            ++v50;
          while ( *(_WORD *)&v135[2 * v50 - 4] );
          goto LABEL_122;
        }
        v18 = v106;
      }
    }
    if ( *(_WORD *)&v18[v20 + 48] == 15 )
    {
      *(_DWORD *)v118 = *(_DWORD *)v21;
      v27 = *(_DWORD *)&v118[4];
      hKey = 0;
      if ( *(_DWORD *)v22 )
      {
        v27 = *(_DWORD *)&v118[4] | 1;
        *(_DWORD *)&v118[4] |= 1u;
      }
      if ( *(_DWORD *)&v18[v20 + 12] )
        *(_DWORD *)&v118[4] = v27 | 2;
      v28 = 0;
      v29 = (unsigned int)((char)v111 - 1);
      if ( v111 == 1 )
      {
        v28 = 32;
      }
      else
      {
        v29 = (unsigned int)((char)v111 - 2);
        if ( v111 == 2 )
        {
          v28 = 64;
        }
        else
        {
          v29 = (unsigned int)((char)v111 - 3);
          if ( v111 == 3 || (v29 = (unsigned int)((char)v111 - 4), v111 == 4) )
          {
            v28 = 96;
          }
          else if ( v111 == 5 )
          {
            v28 = 104;
          }
        }
      }
      v30 = OpenIkev2ConfigKey(v29, &hKey);
      L2tpConfigParams = v30;
      if ( !v30 )
      {
        L2tpConfigParams = GetIkev2ConfigParams(hKey, v111, (__int64)&v118[16], v28);
        RegCloseKey(hKey);
        if ( !L2tpConfigParams )
        {
          v18 = v106;
          goto LABEL_97;
        }
        if ( (byte_1800C8404 & 8) == 0 )
          goto LABEL_152;
        LOWORD(v134) = 0;
        FormatRRASErrorString(
          &v134,
          L"DDMAdminServerGetInfoEx:GetIkev2ConfigParams: Failed. error %d",
          L2tpConfigParams);
        v14 = -1;
        if ( (byte_1800C8404 & 8) == 0 )
          goto LABEL_110;
        v50 = -1;
        do
          ++v50;
        while ( *(_WORD *)&v135[2 * v50 - 4] );
LABEL_122:
        v133 = 0;
        v132 = 2 * v50 + 2;
        v131 = &v134;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v49, 2, v130);
        goto LABEL_110;
      }
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v134) = 0;
        FormatRRASErrorString(&v134, L"DDMAdminServerGetInfoEx:OpenIkev2ConfigKey: Failed. error %d", v30);
        v14 = -1;
        if ( (byte_1800C8404 & 8) == 0 )
        {
LABEL_104:
          switch ( *a1 )
          {
            case 1u:
              v95 = v128;
              *((_DWORD *)a1 + 3) = v114;
              v96 = v129;
              *((_DWORD *)a1 + 5) = DeviceCount;
              *((_DWORD *)a1 + 6) = v117;
              *((_DWORD *)a1 + 4) = v115;
              *((_QWORD *)a1 + 10) = *((_QWORD *)&v123 + 1);
              *((_QWORD *)a1 + 11) = v124;
              *((_QWORD *)a1 + 12) = v127;
              *((_DWORD *)a1 + 26) = DWORD2(v127);
              v97 = HIDWORD(v127);
              *((_OWORD *)a1 + 7) = v95;
              *((_DWORD *)a1 + 27) = v97;
              v98 = *(_DWORD *)v118;
              *(_OWORD *)(a1 + 40) = *(_OWORD *)&v118[8];
              *((_DWORD *)a1 + 8) = v98;
              *(_QWORD *)&v95 = *(_QWORD *)&v118[40];
              v99 = *(_DWORD *)&v118[4];
              *((_QWORD *)a1 + 16) = v96;
              *(_OWORD *)(a1 + 56) = *(_OWORD *)&v118[24];
              *((_DWORD *)a1 + 9) = v99;
              *((_QWORD *)a1 + 9) = v95;
              break;
            case 2u:
              v84 = *(_OWORD *)v118;
              *((_DWORD *)a1 + 3) = v114;
              v85 = *(_OWORD *)&v118[16];
              *((_DWORD *)a1 + 5) = DeviceCount;
              v86 = v117;
              *((_OWORD *)a1 + 2) = v84;
              *((_DWORD *)a1 + 6) = v86;
              v87 = *(_OWORD *)&v118[32];
              v88 = v115;
              *((_OWORD *)a1 + 3) = v85;
              *((_DWORD *)a1 + 4) = v88;
              v89 = v119;
              v90 = v124;
              *((_OWORD *)a1 + 4) = v87;
              v91 = v120;
              *((_OWORD *)a1 + 5) = v89;
              v92 = v121;
              *((_OWORD *)a1 + 6) = v91;
              v93 = v122;
              *((_OWORD *)a1 + 7) = v92;
              v94 = v123;
              *((_OWORD *)a1 + 8) = v93;
              *((_OWORD *)a1 + 9) = v94;
              *((_QWORD *)a1 + 20) = v90;
              break;
            case 3u:
              v69 = *(_OWORD *)v118;
              *((_DWORD *)a1 + 3) = v114;
              v70 = *(_OWORD *)&v118[16];
              *((_DWORD *)a1 + 5) = DeviceCount;
              v71 = v117;
              *((_OWORD *)a1 + 2) = v69;
              *((_DWORD *)a1 + 6) = v71;
              v72 = *(_OWORD *)&v118[32];
              v73 = v115;
              *((_OWORD *)a1 + 3) = v70;
              *((_DWORD *)a1 + 4) = v73;
              v74 = v119;
              v75 = v128;
              *((_OWORD *)a1 + 4) = v72;
              v76 = v120;
              *((_OWORD *)a1 + 5) = v74;
              v77 = v121;
              *((_OWORD *)a1 + 6) = v76;
              v78 = v122;
              *((_OWORD *)a1 + 7) = v77;
              v79 = v123;
              *((_OWORD *)a1 + 8) = v78;
              v80 = v124;
              *((_OWORD *)a1 + 9) = v79;
              v81 = v125;
              *((_OWORD *)a1 + 10) = v80;
              v82 = v126;
              *((_OWORD *)a1 + 11) = v81;
              v83 = v127;
              *((_OWORD *)a1 + 12) = v82;
              *((_OWORD *)a1 + 13) = v83;
              *((_QWORD *)a1 + 28) = v75;
              break;
            case 4u:
              v53 = *(_OWORD *)v118;
              v54 = *(_OWORD *)&v118[16];
              *((_DWORD *)a1 + 3) = v114;
              v55 = DeviceCount;
              *((_OWORD *)a1 + 2) = v53;
              *((_DWORD *)a1 + 5) = v55;
              v56 = *(_OWORD *)&v118[32];
              v57 = v117;
              *((_OWORD *)a1 + 3) = v54;
              *((_DWORD *)a1 + 6) = v57;
              v58 = v119;
              v59 = v115;
              *((_OWORD *)a1 + 4) = v56;
              *((_DWORD *)a1 + 4) = v59;
              v60 = v120;
              *((_OWORD *)a1 + 5) = v58;
              v61 = v121;
              *((_OWORD *)a1 + 6) = v60;
              v62 = v122;
              *((_OWORD *)a1 + 7) = v61;
              v63 = v123;
              *((_OWORD *)a1 + 8) = v62;
              v64 = v124;
              *((_OWORD *)a1 + 9) = v63;
              v65 = v125;
              *((_OWORD *)a1 + 10) = v64;
              v66 = v126;
              *((_OWORD *)a1 + 11) = v65;
              v67 = v127;
              *((_OWORD *)a1 + 12) = v66;
              v68 = v128;
              *((_OWORD *)a1 + 13) = v67;
              *((_OWORD *)a1 + 14) = v68;
              break;
            case 5u:
              v31 = *(_OWORD *)v118;
              v32 = *(_OWORD *)&v118[16];
              *((_DWORD *)a1 + 3) = v114;
              v33 = DeviceCount;
              *((_OWORD *)a1 + 2) = v31;
              *((_DWORD *)a1 + 5) = v33;
              v34 = *(_OWORD *)&v118[32];
              v35 = v117;
              *((_OWORD *)a1 + 3) = v32;
              *((_DWORD *)a1 + 6) = v35;
              v36 = v119;
              v37 = v115;
              *((_OWORD *)a1 + 4) = v34;
              *((_DWORD *)a1 + 4) = v37;
              v38 = v120;
              *((_OWORD *)a1 + 5) = v36;
              v39 = v121;
              *((_OWORD *)a1 + 6) = v38;
              v40 = v122;
              *((_OWORD *)a1 + 7) = v39;
              v41 = v123;
              *((_OWORD *)a1 + 8) = v40;
              v42 = v124;
              *((_OWORD *)a1 + 9) = v41;
              v43 = v125;
              *((_OWORD *)a1 + 10) = v42;
              v44 = v126;
              *((_OWORD *)a1 + 11) = v43;
              v45 = v127;
              *((_OWORD *)a1 + 12) = v44;
              v46 = v128;
              *((_OWORD *)a1 + 13) = v45;
              v47 = v129;
              *((_OWORD *)a1 + 14) = v46;
              *((_OWORD *)a1 + 15) = v47;
              break;
          }
          goto LABEL_110;
        }
        v52 = -1;
        do
          ++v52;
        while ( *(_WORD *)&v135[2 * v52 - 4] );
LABEL_132:
        v133 = 0;
        v132 = 2 * v52 + 2;
        v131 = &v134;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v51, 2, v130);
        goto LABEL_104;
      }
      goto LABEL_103;
    }
LABEL_97:
    if ( *(_WORD *)&v18[v20 + 48] == 16 )
    {
      DWORD2(v129) = *(_DWORD *)v21;
      if ( *(_DWORD *)v22 )
        HIDWORD(v129) |= 1u;
      if ( *(_DWORD *)&v18[v20 + 12] )
        HIDWORD(v129) |= 2u;
    }
    v19 = (unsigned int)(v110 + 1);
    v110 = v19;
    if ( (unsigned int)v19 >= v107 )
      goto LABEL_103;
  }
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v134) = 0;
    FormatRRASErrorString(&v134, L"DDMAdminServerSetInfoEx:GSetSstpConfiguration: Failed. error %d", SstpConfiguration);
    v14 = -1;
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_110;
    v50 = -1;
    do
      ++v50;
    while ( *(_WORD *)&v135[2 * v50 - 4] );
    goto LABEL_122;
  }
LABEL_152:
  v14 = -1;
LABEL_110:
  v2 = v106;
LABEL_111:
  LeaveCriticalSection(&gblDeviceTable);
  if ( v2 )
    HeapFree(hHeap, 0, v2);
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v134) = 0;
    FormatRRASErrorString(&v134, L"DDMAdminServerSetInfoEx: done %d", L2tpConfigParams);
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      do
        ++v14;
      while ( *(_WORD *)&v135[2 * v14 - 4] );
      v133 = 0;
      v132 = 2 * v14 + 2;
      v131 = &v134;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, &v134, 2, v130);
    }
  }
  return L2tpConfigParams;
}

```

## disassembly

```asm
0x180004950  push    rbp
0x180004952  push    rbx
0x180004953  push    rsi
0x180004954  push    rdi
0x180004955  push    r12
0x180004957  push    r13
0x180004959  push    r14
0x18000495b  push    r15
0x18000495d  lea     rbp, [rsp-898h]
0x180004965  sub     rsp, 998h
0x18000496c  mov     rax, cs:__security_cookie
0x180004973  xor     rax, rsp
0x180004976  mov     [rbp+8D0h+var_50], rax
0x18000497d  mov     rbx, rcx
0x180004980  xor     r13d, r13d
0x180004983  lea     rcx, [rsp+9D0h+var_96F]; void *
0x180004988  xor     edx, edx; Val
0x18000498a  mov     r8d, 0F7h; Size
0x180004990  mov     r12d, r13d
0x180004993  call    memset_0
0x180004998  xor     edx, edx; Val
0x18000499a  mov     dword ptr [rsp+9D0h+dwBytes+4], r13d
0x18000499f  mov     r8d, 7FCh; Size
0x1800049a5  mov     [rsp+9D0h+var_998], r13d
0x1800049aa  lea     rcx, [rbp+8D0h+var_84C]; void *
0x1800049b1  mov     dword ptr [rsp+9D0h+dwBytes], r13d
0x1800049b6  mov     [rbp+8D0h+var_850], r13d
0x1800049bd  call    memset_0
0x1800049c2  cmp     cs:dword_1800C8654, r13d
0x1800049c9  lea     rax, DdmGetDeviceConfigInfo
0x1800049d0  mov     r14, cs:__imp_RasGetDeviceConfigInfo
0x1800049d7  lea     rcx, [rsp+9D0h+var_970]; void *
0x1800049dc  cmovnz  r14, rax
0x1800049e0  mov     r8d, 0E8h; Size
0x1800049e6  xor     edx, edx; Val
0x1800049e8  call    memset_0
0x1800049ed  lea     rcx, gblDeviceTable; lpCriticalSection
0x1800049f4  call    cs:__imp_EnterCriticalSection
0x1800049fa  movzx   edx, byte ptr [rbx]
0x1800049fd  lea     edi, [r13+10h]
0x180004a01  mov     ecx, edx
0x180004a03  lea     eax, [rdi-8]
0x180004a06  or      r15, 0FFFFFFFFFFFFFFFFh
0x180004a0a  lea     esi, [rdi-0Eh]
0x180004a0d  sub     ecx, 1
0x180004a10  jz      loc_180004CAB
0x180004a16  sub     ecx, 1
0x180004a19  jz      loc_180004BF1
0x180004a1f  sub     ecx, 1
0x180004a22  jz      loc_180004B77
0x180004a28  sub     ecx, 1
0x180004a2b  jz      loc_180004AFF
0x180004a31  cmp     ecx, 1
0x180004a34  jz      short loc_180004A87
0x180004a36  test    cs:byte_1800C8404, dil
0x180004a3d  jz      loc_180004C9D
0x180004a43  mov     r8d, edx
0x180004a46  mov     word ptr [rbp+8D0h+var_850], r13w
0x180004a4e  lea     rdx, aDdmadminserver_15; "DDMAdminServerGetInfoEx: Invalid revisi"...
0x180004a55  lea     rcx, [rbp+8D0h+var_850]
0x180004a5c  call    FormatRRASErrorString
0x180004a61  test    cs:byte_1800C8404, dil
0x180004a68  jz      loc_180004C9D
0x180004a6e  lea     rcx, [rbp+8D0h+var_850]
0x180004a75  mov     rax, r15
0x180004a78  inc     rax
0x180004a7b  cmp     [rcx+rax*2], r13w
0x180004a80  jnz     short loc_180004A78
0x180004a82  jmp     loc_180004C65
0x180004a87  movzx   ecx, word ptr [rbx+0Ah]
0x180004a8b  cmp     cx, ax
0x180004a8e  jb      short loc_180004AA1
0x180004a90  cmp     [rbx+9], sil
0x180004a94  jnz     short loc_180004AA1
0x180004a96  mov     al, [rbx+8]
0x180004a99  cmp     al, dl
0x180004a9b  jz      loc_180004CD2
0x180004aa1  test    cs:byte_1800C8404, dil
0x180004aa8  jz      loc_180004C9D
0x180004aae  movzx   eax, byte ptr [rbx+8]
0x180004ab2  lea     rdx, aDdmadminserver_12; "DDMAdminServerGetInfoEx: Invalid Versio"...
0x180004ab9  movzx   r9d, byte ptr [rbx+9]
0x180004abe  mov     r8d, ecx
0x180004ac1  lea     rcx, [rbp+8D0h+var_850]
0x180004ac8  mov     [rsp+9D0h+var_9B0], eax
0x180004acc  mov     word ptr [rbp+8D0h+var_850], r13w
0x180004ad4  call    FormatRRASErrorString
0x180004ad9  test    cs:byte_1800C8404, dil
0x180004ae0  jz      loc_180004C9D
0x180004ae6  lea     rcx, [rbp+8D0h+var_850]
0x180004aed  mov     rax, r15
0x180004af0  inc     rax
0x180004af3  cmp     [rcx+rax*2], r13w
0x180004af8  jnz     short loc_180004AF0
0x180004afa  jmp     loc_180004C65
0x180004aff  movzx   ecx, word ptr [rbx+0Ah]
0x180004b03  cmp     cx, ax
0x180004b06  jb      short loc_180004B19
0x180004b08  cmp     [rbx+9], sil
0x180004b0c  jnz     short loc_180004B19
0x180004b0e  mov     al, [rbx+8]
0x180004b11  cmp     al, dl
0x180004b13  jz      loc_180004CD2
0x180004b19  test    cs:byte_1800C8404, dil
0x180004b20  jz      loc_180004C9D
0x180004b26  movzx   eax, byte ptr [rbx+8]
0x180004b2a  lea     rdx, aDdmadminserver_12; "DDMAdminServerGetInfoEx: Invalid Versio"...
0x180004b31  movzx   r9d, byte ptr [rbx+9]
0x180004b36  mov     r8d, ecx
0x180004b39  lea     rcx, [rbp+8D0h+var_850]
0x180004b40  mov     [rsp+9D0h+var_9B0], eax
0x180004b44  mov     word ptr [rbp+8D0h+var_850], r13w
0x180004b4c  call    FormatRRASErrorString
0x180004b51  test    cs:byte_1800C8404, dil
0x180004b58  jz      loc_180004C9D
0x180004b5e  lea     rcx, [rbp+8D0h+var_850]
0x180004b65  mov     rax, r15
0x180004b68  inc     rax
0x180004b6b  cmp     [rcx+rax*2], r13w
0x180004b70  jnz     short loc_180004B68
0x180004b72  jmp     loc_180004C65
0x180004b77  movzx   ecx, word ptr [rbx+0Ah]
0x180004b7b  mov     eax, 0E0h
0x180004b80  cmp     cx, ax
0x180004b83  jb      short loc_180004B96
0x180004b85  cmp     [rbx+9], sil
0x180004b89  jnz     short loc_180004B96
0x180004b8b  mov     al, [rbx+8]
0x180004b8e  cmp     al, dl
0x180004b90  jz      loc_180004CD2
0x180004b96  test    cs:byte_1800C8404, dil
0x180004b9d  jz      loc_180004C9D
0x180004ba3  movzx   eax, byte ptr [rbx+8]
0x180004ba7  lea     rdx, aDdmadminserver_12; "DDMAdminServerGetInfoEx: Invalid Versio"...
0x180004bae  movzx   r9d, byte ptr [rbx+9]
0x180004bb3  mov     r8d, ecx
0x180004bb6  lea     rcx, [rbp+8D0h+var_850]
0x180004bbd  mov     [rsp+9D0h+var_9B0], eax
0x180004bc1  mov     word ptr [rbp+8D0h+var_850], r13w
0x180004bc9  call    FormatRRASErrorString
0x180004bce  test    cs:byte_1800C8404, dil
0x180004bd5  jz      loc_180004C9D
0x180004bdb  lea     rcx, [rbp+8D0h+var_850]
0x180004be2  mov     rax, r15
0x180004be5  inc     rax
0x180004be8  cmp     [rcx+rax*2], r13w
0x180004bed  jnz     short loc_180004BE5
0x180004bef  jmp     short loc_180004C65
0x180004bf1  movzx   ecx, word ptr [rbx+0Ah]
0x180004bf5  mov     eax, 0A0h
0x180004bfa  cmp     cx, ax
0x180004bfd  jb      short loc_180004C10
0x180004bff  cmp     [rbx+9], sil
0x180004c03  jnz     short loc_180004C10
0x180004c05  mov     al, [rbx+8]
0x180004c08  cmp     al, dl
0x180004c0a  jz      loc_180004CD2
0x180004c10  test    cs:byte_1800C8404, dil
0x180004c17  jz      loc_180004C9D
0x180004c1d  movzx   eax, byte ptr [rbx+8]
0x180004c21  lea     rdx, aDdmadminserver_12; "DDMAdminServerGetInfoEx: Invalid Versio"...
0x180004c28  movzx   r9d, byte ptr [rbx+9]
0x180004c2d  mov     r8d, ecx
0x180004c30  lea     rcx, [rbp+8D0h+var_850]
0x180004c37  mov     [rsp+9D0h+var_9B0], eax
0x180004c3b  mov     word ptr [rbp+8D0h+var_850], r13w
0x180004c43  call    FormatRRASErrorString
0x180004c48  test    cs:byte_1800C8404, dil
0x180004c4f  jz      short loc_180004C9D
0x180004c51  lea     rcx, [rbp+8D0h+var_850]
0x180004c58  mov     rax, r15
0x180004c5b  inc     rax
0x180004c5e  cmp     [rcx+rax*2], r13w
0x180004c63  jnz     short loc_180004C5B
0x180004c65  lea     eax, ds:2[rax*2]
0x180004c6c  mov     [rbp+8D0h+var_854], r13d
0x180004c70  lea     rcx, [rbp+8D0h+var_850]
0x180004c77  mov     [rbp+8D0h+var_858], eax
0x180004c7a  lea     rax, [rbp+8D0h+var_870]
0x180004c7e  mov     [rbp+8D0h+var_860], rcx
0x180004c82  mov     r9d, esi
0x180004c85  mov     qword ptr [rsp+9D0h+var_9B0], rax
0x180004c8a  lea     rdx, RasDdmTraceInfo
0x180004c91  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004c98  call    McGenEventWrite_EventWriteTransfer
0x180004c9d  mov     edi, 57h ; 'W'
0x180004ca2  or      r14, 0FFFFFFFFFFFFFFFFh
0x180004ca6  jmp     loc_1800050AF
0x180004cab  movzx   ecx, word ptr [rbx+0Ah]
0x180004caf  mov     eax, 80h
0x180004cb4  cmp     cx, ax
0x180004cb7  jb      loc_1800055CA
0x180004cbd  cmp     [rbx+9], sil
0x180004cc1  jnz     loc_1800055CA
0x180004cc7  mov     al, [rbx+8]
0x180004cca  cmp     al, dl
0x180004ccc  jnz     loc_1800055CA
0x180004cd2  mov     [rsp+9D0h+var_96E], cx
0x180004cd7  mov     ecx, 11h; unsigned int
0x180004cdc  mov     [rsp+9D0h+var_96F], sil
0x180004ce1  mov     [rsp+9D0h+var_970], al
0x180004ce5  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180004cea  mov     rcx, rax; this
0x180004ced  call    ?GetDeviceCount@DdmDeviceTable@@QEAAKXZ; DdmDeviceTable::GetDeviceCount(void)
0x180004cf2  mov     [rsp+9D0h+var_964], eax
0x180004cf6  lea     r9, [rsp+9D0h+dwBytes]
0x180004cfb  mov     eax, cs:dword_1800C84B0
0x180004d01  lea     r8, [rsp+9D0h+var_998]
0x180004d06  mov     [rsp+9D0h+var_960], eax
0x180004d0a  lea     rdx, [rsp+9D0h+dwBytes+4]
0x180004d0f  mov     rax, r14
0x180004d12  mov     dword ptr [rsp+9D0h+dwBytes+4], 6
0x180004d1a  xor     ecx, ecx
0x180004d1c  mov     qword ptr [rsp+9D0h+var_9B0], r13
0x180004d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d26  mov     edi, eax
0x180004d28  test    eax, eax
0x180004d2a  jnz     short loc_180004D36
0x180004d2c  mov     edi, 10DFh
0x180004d31  jmp     loc_180004CA2
0x180004d36  cmp     eax, 25Bh
0x180004d3b  jnz     loc_180004CA2
0x180004d41  mov     r8d, dword ptr [rsp+9D0h+dwBytes]; dwBytes
0x180004d46  mov     edi, 8
0x180004d4b  mov     rcx, cs:hHeap; hHeap
0x180004d52  mov     edx, edi; dwFlags
0x180004d54  call    cs:__imp_HeapAlloc
0x180004d5a  mov     [rsp+9D0h+var_9A0], rax
0x180004d5f  mov     r15, rax
0x180004d62  test    rax, rax
0x180004d65  jnz     short loc_180004D73
0x180004d67  or      r14, 0FFFFFFFFFFFFFFFFh
0x180004d6b  mov     r12, rax
0x180004d6e  jmp     loc_1800050AF
0x180004d73  mov     qword ptr [rsp+9D0h+var_9B0], rax
0x180004d78  lea     r9, [rsp+9D0h+dwBytes]
0x180004d7d  mov     rax, r14
0x180004d80  lea     r8, [rsp+9D0h+var_998]
0x180004d85  lea     rdx, [rsp+9D0h+dwBytes+4]
0x180004d8a  xor     ecx, ecx
0x180004d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d91  mov     edi, eax
0x180004d93  test    eax, eax
0x180004d95  jnz     loc_180005631
0x180004d9b  mov     eax, r13d
0x180004d9e  mov     [rsp+9D0h+var_980], eax
0x180004da2  cmp     [rsp+9D0h+var_998], r13d
0x180004da7  jbe     loc_180004FD1
0x180004dad  imul    r14, rax, 1D8h
0x180004db4  lea     r12, [r15+1Ch]
0x180004db8  xor     ecx, ecx
0x180004dba  lea     r13, [r15+8]
0x180004dbe  add     r12, r14
0x180004dc1  add     r13, r14
0x180004dc4  cmp     word ptr [r14+r15+30h], 0Eh
0x180004dcb  jnz     short loc_180004E12
0x180004dcd  mov     eax, [r12]
0x180004dd1  mov     dword ptr [rbp+8D0h+var_8A8], eax
0x180004dd4  mov     eax, dword ptr [rbp+8D0h+var_8A8+4]
0x180004dd7  cmp     [r13+0], ecx
0x180004ddb  jz      short loc_180004DE3
0x180004ddd  or      eax, 1
0x180004de0  mov     dword ptr [rbp+8D0h+var_8A8+4], eax
0x180004de3  cmp     [r14+r15+0Ch], ecx
0x180004de8  jz      short loc_180004DEF
0x180004dea  or      eax, esi
0x180004dec  mov     dword ptr [rbp+8D0h+var_8A8+4], eax
0x180004def  lea     r9, [rbp+8D0h+var_8A8+8]
0x180004df3  xor     edx, edx
0x180004df5  lea     r8, [rbp+8D0h+var_898]
0x180004df9  call    cs:__imp_GetSstpConfiguration
0x180004dff  xor     ecx, ecx
0x180004e01  mov     edi, eax
0x180004e03  test    eax, eax
0x180004e05  jnz     loc_180005175
0x180004e0b  mov     dword ptr [rbp+8D0h+var_8A8+0Ch], 800Ch
0x180004e12  cmp     word ptr [r14+r15+30h], 8
0x180004e19  jnz     short loc_180004E44
0x180004e1b  lea     r12, [r15+1Ch]
0x180004e1f  add     r12, r14
0x180004e22  lea     r13, [r15+8]
0x180004e26  add     r13, r14
0x180004e29  mov     eax, [r12]
0x180004e2d  mov     dword ptr [rbp+8D0h+var_8E0], eax
0x180004e30  cmp     [r13+0], ecx
0x180004e34  jz      short loc_180004E3A
0x180004e36  or      dword ptr [rbp+8D0h+var_8E0+4], 1
0x180004e3a  cmp     [r14+r15+0Ch], ecx
0x180004e3f  jz      short loc_180004E44
0x180004e41  or      dword ptr [rbp+8D0h+var_8E0+4], esi
0x180004e44  cmp     word ptr [r14+r15+30h], 9
0x180004e4b  jnz     loc_180004EDF
0x180004e51  mov     eax, [r12]
0x180004e55  mov     dword ptr [rbp+8D0h+var_8D8], eax
0x180004e58  cmp     [r13+0], ecx
0x180004e5c  jz      short loc_180004E62
0x180004e5e  or      dword ptr [rbp+8D0h+var_8D8+4], 1
0x180004e62  cmp     [r14+r15+0Ch], ecx
0x180004e67  jz      short loc_180004E6C
0x180004e69  or      dword ptr [rbp+8D0h+var_8D8+4], esi
  ... truncated ...
```
