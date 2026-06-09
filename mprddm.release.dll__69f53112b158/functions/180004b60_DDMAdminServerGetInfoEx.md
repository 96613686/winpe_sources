# DDMAdminServerGetInfoEx

- ea: `0x180004b60`
- end: `0x1800057e3`
- name: `DDMAdminServerGetInfoEx`
- size: `3203`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004b60`
- `0x180007c0c`
- `0x18003d230`
- `0x18003d278`
- `0x1800755b8`
- `0x180076510`
- `0x180076ea0`
- `0x180077264`
- `0x1800772c0`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180004efa`
- `KERNEL32!HeapAlloc` at `0x180004efa`
- `KERNEL32!LeaveCriticalSection` at `0x180005716`
- `KERNEL32!LeaveCriticalSection` at `0x180005716`
- `KERNEL32!EnterCriticalSection` at `0x180004c08`
- `KERNEL32!EnterCriticalSection` at `0x180004c08`
- `KERNEL32!HeapFree` at `0x180005733`
- `KERNEL32!HeapFree` at `0x180005733`
- `ADVAPI32!RegCloseKey` at `0x180005092`
- `ADVAPI32!RegCloseKey` at `0x18000516a`
- `ADVAPI32!RegCloseKey` at `0x180005092`
- `ADVAPI32!RegCloseKey` at `0x18000516a`
- `rasman!RasGetDeviceConfigInfo` at `0x180004be4`
- `sstpcfg!GetSstpConfiguration` at `0x180004f8f`
- `sstpcfg!GetSstpConfiguration` at `0x180004f8f`

## string_xrefs

- `0x1800051f6`: `DDMAdminServerSetInfoEx:GSetSstpConfiguration: Failed. error %d`
- `0x1800052b7`: `DDMAdminServerGetInfoEx:OpenIkev2ConfigKey: Failed. error %d`
- `0x180005346`: `DDMAdminServerGetInfoEx:OpenIkev2ConfigKey: Failed. error %d`
- `0x180005273`: `DDMAdminServerGetInfoEx:GetIkev2ConfigParams: Failed. error %d`
- `0x180005307`: `DDMAdminServerGetInfoEx:GetIkev2ConfigParams: Failed. error %d`

## pseudocode

```c
__int64 __fastcall DDMAdminServerGetInfoEx(unsigned __int8 *a1)
{
  _DWORD *v2; // r15
  __int64 (__fastcall *v3)(int, int, int, int, void *); // r14
  unsigned int v4; // edx
  __int64 v5; // r13
  __int64 v6; // r8
  __int64 v7; // rax
  unsigned int v8; // ecx
  unsigned __int8 v9; // al
  __int64 v10; // r9
  __int64 v11; // r9
  __int64 v12; // r9
  __int64 v13; // r9
  DdmDeviceTable *Instance; // rax
  unsigned int v15; // eax
  unsigned int SstpConfiguration; // ebx
  _DWORD *v17; // rax
  unsigned int v18; // edx
  __int64 v19; // r14
  __int64 v20; // r12
  int v21; // eax
  unsigned int v22; // r12d
  __int64 v23; // rcx
  unsigned int v24; // eax
  int v25; // ecx
  __int64 v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // edx
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // rax
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  __int128 v55; // xmm0
  __int128 v56; // xmm1
  __int128 v57; // xmm0
  __int128 v58; // xmm1
  __int128 v59; // xmm0
  __int128 v60; // xmm1
  __int128 v61; // xmm0
  __int128 v62; // xmm1
  __int128 v63; // xmm1
  __int128 v64; // xmm0
  __int128 v65; // xmm1
  __int64 v66; // rax
  __int128 v67; // xmm1
  __int128 v68; // xmm0
  __int128 v69; // xmm1
  __int128 v70; // xmm0
  __int128 v71; // xmm1
  __int128 v72; // xmm0
  __int128 v73; // xmm1
  __int64 v74; // rax
  __int128 v75; // xmm0
  __int128 v76; // xmm1
  int v77; // eax
  int v78; // eax
  __int128 v79; // xmm1
  __int64 v80; // rax
  __int128 v81; // xmm0
  __int64 v82; // rax
  __int128 v83; // xmm1
  __int64 v84; // r9
  int v86; // [rsp+28h] [rbp-E0h]
  int v87; // [rsp+28h] [rbp-E0h]
  int v88; // [rsp+28h] [rbp-E0h]
  int v89; // [rsp+28h] [rbp-E0h]
  int v90; // [rsp+28h] [rbp-E0h]
  unsigned int v91; // [rsp+38h] [rbp-D0h] BYREF
  SIZE_T dwBytes; // [rsp+3Ch] [rbp-CCh] BYREF
  unsigned int v93; // [rsp+44h] [rbp-C4h]
  HKEY hKey[2]; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int8 v95; // [rsp+58h] [rbp-B0h] BYREF
  char v96; // [rsp+59h] [rbp-AFh] BYREF
  __int16 v97; // [rsp+5Ah] [rbp-AEh]
  int v98; // [rsp+5Ch] [rbp-ACh]
  int v99; // [rsp+60h] [rbp-A8h]
  unsigned int DeviceCount; // [rsp+64h] [rbp-A4h]
  int v101; // [rsp+68h] [rbp-A0h]
  __int128 v102; // [rsp+70h] [rbp-98h]
  __int128 v103; // [rsp+80h] [rbp-88h] BYREF
  __int128 v104; // [rsp+90h] [rbp-78h]
  __int128 v105; // [rsp+A0h] [rbp-68h]
  __int128 v106; // [rsp+B0h] [rbp-58h]
  __int128 v107; // [rsp+C0h] [rbp-48h]
  __int128 v108; // [rsp+D0h] [rbp-38h]
  __int128 v109; // [rsp+E0h] [rbp-28h]
  __int128 v110; // [rsp+F0h] [rbp-18h]
  __int128 v111; // [rsp+100h] [rbp-8h]
  __int128 v112; // [rsp+110h] [rbp+8h]
  __int128 v113; // [rsp+120h] [rbp+18h] BYREF
  __int128 v114; // [rsp+130h] [rbp+28h] BYREF
  __int128 v115; // [rsp+140h] [rbp+38h]
  _BYTE v116[16]; // [rsp+158h] [rbp+50h] BYREF
  int *v117; // [rsp+168h] [rbp+60h]
  int v118; // [rsp+170h] [rbp+68h]
  int v119; // [rsp+174h] [rbp+6Ch]
  int v120; // [rsp+178h] [rbp+70h] BYREF
  char v121[2044]; // [rsp+17Ch] [rbp+74h] BYREF

  v2 = 0;
  memset_0(&v96, 0, 0xF7u);
  v91 = 0;
  dwBytes = 0;
  v120 = 0;
  memset_0(v121, 0, sizeof(v121));
  v3 = (__int64 (__fastcall *)(int, int, int, int, void *))RasGetDeviceConfigInfo;
  if ( dword_1800CF654 )
    v3 = DdmGetDeviceConfigInfo;
  memset_0(&v95, 0, 0xE8u);
  EnterCriticalSection(&gblDeviceTable);
  v4 = *a1;
  v5 = -1;
  if ( v4 == 1 )
  {
    v8 = *((unsigned __int16 *)a1 + 5);
    if ( (unsigned __int16)v8 < 0x80u || a1[9] != 2 || (v9 = a1[8], v9 != 1) )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_142;
      v84 = a1[9];
      v90 = a1[8];
      LOWORD(v120) = 0;
      FormatRRASErrorString(&v120, L"DDMAdminServerGetInfoEx: Invalid Version %d/type%d/size %d", v8, v84, v90);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_142;
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)&v121[2 * v7 - 4] );
      goto LABEL_141;
    }
  }
  else
  {
    switch ( *a1 )
    {
      case 2u:
        v8 = *((unsigned __int16 *)a1 + 5);
        if ( (unsigned __int16)v8 < 0xA0u || a1[9] != 2 || (v9 = a1[8], v9 != (_BYTE)v4) )
        {
          if ( (byte_1800CF404 & 0x10) == 0 )
            goto LABEL_142;
          v13 = a1[9];
          v89 = a1[8];
          LOWORD(v120) = 0;
          FormatRRASErrorString(&v120, L"DDMAdminServerGetInfoEx: Invalid Version %d/type%d/size %d", v8, v13, v89);
          if ( (byte_1800CF404 & 0x10) == 0 )
            goto LABEL_142;
          v7 = -1;
          do
            ++v7;
          while ( *(_WORD *)&v121[2 * v7 - 4] );
          goto LABEL_141;
        }
        break;
      case 3u:
        v8 = *((unsigned __int16 *)a1 + 5);
        if ( (unsigned __int16)v8 < 0xE0u || a1[9] != 2 || (v9 = a1[8], v9 != (_BYTE)v4) )
        {
          if ( (byte_1800CF404 & 0x10) == 0 )
            goto LABEL_142;
          v12 = a1[9];
          v88 = a1[8];
          LOWORD(v120) = 0;
          FormatRRASErrorString(&v120, L"DDMAdminServerGetInfoEx: Invalid Version %d/type%d/size %d", v8, v12, v88);
          if ( (byte_1800CF404 & 0x10) == 0 )
            goto LABEL_142;
          v7 = -1;
          do
            ++v7;
          while ( *(_WORD *)&v121[2 * v7 - 4] );
          goto LABEL_141;
        }
        break;
      case 4u:
        v8 = *((unsigned __int16 *)a1 + 5);
        if ( (unsigned __int16)v8 < 8u || a1[9] != 2 || (v9 = a1[8], v9 != (_BYTE)v4) )
        {
          if ( (byte_1800CF404 & 0x10) == 0 )
            goto LABEL_142;
          v11 = a1[9];
          v87 = a1[8];
          LOWORD(v120) = 0;
          FormatRRASErrorString(&v120, L"DDMAdminServerGetInfoEx: Invalid Version %d/type%d/size %d", v8, v11, v87);
          if ( (byte_1800CF404 & 0x10) == 0 )
            goto LABEL_142;
          v7 = -1;
          do
            ++v7;
          while ( *(_WORD *)&v121[2 * v7 - 4] );
          goto LABEL_141;
        }
        break;
      case 5u:
        v8 = *((unsigned __int16 *)a1 + 5);
        if ( (unsigned __int16)v8 < 8u || a1[9] != 2 || (v9 = a1[8], v9 != (_BYTE)v4) )
        {
          if ( (byte_1800CF404 & 0x10) == 0 )
            goto LABEL_142;
          v10 = a1[9];
          v86 = a1[8];
          LOWORD(v120) = 0;
          FormatRRASErrorString(&v120, L"DDMAdminServerGetInfoEx: Invalid Version %d/type%d/size %d", v8, v10, v86);
          if ( (byte_1800CF404 & 0x10) == 0 )
            goto LABEL_142;
          v7 = -1;
          do
            ++v7;
          while ( *(_WORD *)&v121[2 * v7 - 4] );
          goto LABEL_141;
        }
        break;
      default:
        if ( (byte_1800CF404 & 0x10) == 0 )
          goto LABEL_142;
        LOWORD(v120) = 0;
        FormatRRASErrorString(&v120, L"DDMAdminServerGetInfoEx: Invalid revision %d", v4);
        if ( (byte_1800CF404 & 0x10) == 0 )
          goto LABEL_142;
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)&v121[2 * v7 - 4] );
LABEL_141:
        v119 = 0;
        v118 = 2 * v7 + 2;
        v117 = &v120;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v6, 2, v116);
LABEL_142:
        SstpConfiguration = 87;
        goto LABEL_143;
    }
  }
  v97 = v8;
  v96 = 2;
  v95 = v9;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DeviceCount = DdmDeviceTable::GetDeviceCount(Instance);
  v101 = dword_1800CF4B0;
  HIDWORD(dwBytes) = 6;
  v15 = v3(0, (int)&dwBytes + 4, (int)&v91, (int)&dwBytes, 0);
  SstpConfiguration = v15;
  if ( !v15 )
  {
    SstpConfiguration = 4319;
    goto LABEL_143;
  }
  if ( v15 == 603 )
  {
    SstpConfiguration = 8;
    v17 = HeapAlloc(hHeap, 8u, (unsigned int)dwBytes);
    v2 = v17;
    if ( v17 )
    {
      SstpConfiguration = v3(0, (int)&dwBytes + 4, (int)&v91, (int)&dwBytes, v17);
      if ( !SstpConfiguration )
      {
        v18 = 0;
        v93 = 0;
        if ( !v91 )
          goto LABEL_127;
        while ( 1 )
        {
          v19 = v18;
          v20 = 118LL * v18;
          if ( LOWORD(v2[v20 + 12]) == 14 )
          {
            LODWORD(v113) = v2[v20 + 7];
            v21 = DWORD1(v113);
            if ( v2[v20 + 2] )
            {
              v21 = DWORD1(v113) | 1;
              DWORD1(v113) |= 1u;
            }
            if ( v2[v20 + 3] )
              DWORD1(v113) = v21 | 2;
            SstpConfiguration = GetSstpConfiguration(0, 0, &v114, (char *)&v113 + 8);
            if ( SstpConfiguration )
            {
              if ( (byte_1800CF404 & 8) != 0 )
              {
                LOWORD(v120) = 0;
                FormatRRASErrorString(
                  &v120,
                  L"DDMAdminServerSetInfoEx:GSetSstpConfiguration: Failed. error %d",
                  SstpConfiguration);
                if ( (byte_1800CF404 & 8) != 0 )
                {
                  v30 = -1;
                  do
                    ++v30;
                  while ( *(_WORD *)&v121[2 * v30 - 4] );
                  v119 = 0;
                  goto LABEL_106;
                }
              }
              goto LABEL_143;
            }
            HIDWORD(v113) = 32780;
          }
          if ( LOWORD(v2[v20 + 12]) == 8 )
          {
            v22 = 0;
            DWORD2(v109) = v2[118 * v19 + 7];
            if ( v2[118 * v19 + 2] )
              HIDWORD(v109) |= 1u;
            if ( v2[118 * v19 + 3] )
              HIDWORD(v109) |= 2u;
          }
          else
          {
            v22 = 0;
          }
          if ( LOWORD(v2[118 * v19 + 12]) == 9 )
          {
            LODWORD(v110) = v2[118 * v19 + 7];
            if ( v2[118 * v19 + 2] )
              DWORD1(v110) |= 1u;
            if ( v2[118 * v19 + 3] )
              DWORD1(v110) |= 2u;
            if ( v95 >= 3u )
            {
              hKey[0] = 0;
              v23 = (unsigned int)((char)v95 - 3);
              if ( v95 != 3 )
                v23 = (unsigned int)((char)v95 - 4);
              v24 = OpenL2tpConfigKey(v23, hKey);
              SstpConfiguration = v24;
              if ( v24 )
              {
                if ( (byte_1800CF404 & 8) != 0 )
                {
                  LOWORD(v120) = 0;
                  FormatRRASErrorString(&v120, L"DDMAdminServerGetInfoEx:OpenIkev2ConfigKey: Failed. error %d", v24);
                  if ( (byte_1800CF404 & 8) != 0 )
                  {
                    v32 = -1;
                    do
                      ++v32;
                    while ( *(_WORD *)&v121[2 * v32 - 4] );
LABEL_126:
                    v119 = 0;
                    v118 = 2 * v32 + 2;
                    v117 = &v120;
                    McGenEventWrite_EventWriteTransfer(
                      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      RasDdmTraceError,
                      v31,
                      2,
                      v116);
                  }
                }
LABEL_127:
                switch ( *a1 )
                {
                  case 1u:
                    v75 = v113;
                    *((_DWORD *)a1 + 3) = v98;
                    v76 = v114;
                    *((_DWORD *)a1 + 5) = DeviceCount;
                    v77 = v101;
                    *((_OWORD *)a1 + 6) = v75;
                    *((_DWORD *)a1 + 6) = v77;
                    *(_QWORD *)&v75 = v115;
                    v78 = v99;
                    *((_OWORD *)a1 + 7) = v76;
                    *((_DWORD *)a1 + 4) = v78;
                    v79 = v102;
                    v80 = *((_QWORD *)&v109 + 1);
                    *((_QWORD *)a1 + 16) = v75;
                    v81 = v103;
                    *((_QWORD *)a1 + 10) = v80;
                    v82 = v110;
                    *((_OWORD *)a1 + 2) = v79;
                    *((_QWORD *)a1 + 11) = v82;
                    v83 = v104;
                    *((_OWORD *)a1 + 3) = v81;
                    *((_OWORD *)a1 + 4) = v83;
                    break;
                  case 2u:
                    *((_DWORD *)a1 + 3) = v98;
                    *((_DWORD *)a1 + 5) = DeviceCount;
                    *((_DWORD *)a1 + 6) = v101;
                    *((_DWORD *)a1 + 4) = v99;
                    v67 = v103;
                    *((_OWORD *)a1 + 2) = v102;
                    v68 = v104;
                    *((_OWORD *)a1 + 3) = v67;
                    v69 = v105;
                    *((_OWORD *)a1 + 4) = v68;
                    v70 = v106;
                    *((_OWORD *)a1 + 5) = v69;
                    v71 = v107;
                    *((_OWORD *)a1 + 6) = v70;
                    v72 = v108;
                    *((_OWORD *)a1 + 7) = v71;
                    v73 = v109;
                    v74 = v110;
                    *((_OWORD *)a1 + 8) = v72;
                    *((_OWORD *)a1 + 9) = v73;
                    *((_QWORD *)a1 + 20) = v74;
                    break;
                  case 3u:
                    *((_DWORD *)a1 + 3) = v98;
                    *((_DWORD *)a1 + 5) = DeviceCount;
                    *((_DWORD *)a1 + 6) = v101;
                    *((_DWORD *)a1 + 4) = v99;
                    v56 = v103;
                    *((_OWORD *)a1 + 2) = v102;
                    v57 = v104;
                    *((_OWORD *)a1 + 3) = v56;
                    v58 = v105;
                    *((_OWORD *)a1 + 4) = v57;
                    v59 = v106;
                    *((_OWORD *)a1 + 5) = v58;
                    v60 = v107;
                    *((_OWORD *)a1 + 6) = v59;
                    v61 = v108;
                    *((_OWORD *)a1 + 7) = v60;
                    v62 = v109;
                    *((_OWORD *)a1 + 8) = v61;
                    *((_OWORD *)a1 + 9) = v62;
                    v63 = v111;
                    *((_OWORD *)a1 + 10) = v110;
                    v64 = v112;
                    *((_OWORD *)a1 + 11) = v63;
                    v65 = v113;
                    v66 = v114;
                    *((_OWORD *)a1 + 12) = v64;
                    *((_OWORD *)a1 + 13) = v65;
                    *((_QWORD *)a1 + 28) = v66;
                    break;
                  case 4u:
                    *((_DWORD *)a1 + 3) = v98;
                    *((_DWORD *)a1 + 5) = DeviceCount;
                    *((_DWORD *)a1 + 6) = v101;
                    *((_DWORD *)a1 + 4) = v99;
                    v45 = v103;
                    *((_OWORD *)a1 + 2) = v102;
                    v46 = v104;
                    *((_OWORD *)a1 + 3) = v45;
                    v47 = v105;
                    *((_OWORD *)a1 + 4) = v46;
                    v48 = v106;
                    *((_OWORD *)a1 + 5) = v47;
                    v49 = v107;
                    *((_OWORD *)a1 + 6) = v48;
                    v50 = v108;
                    *((_OWORD *)a1 + 7) = v49;
                    v51 = v109;
                    *((_OWORD *)a1 + 8) = v50;
                    *((_OWORD *)a1 + 9) = v51;
                    v52 = v111;
                    *((_OWORD *)a1 + 10) = v110;
                    v53 = v112;
                    *((_OWORD *)a1 + 11) = v52;
                    v54 = v113;
                    *((_OWORD *)a1 + 12) = v53;
                    v55 = v114;
                    *((_OWORD *)a1 + 13) = v54;
                    *((_OWORD *)a1 + 14) = v55;
                    break;
                  case 5u:
                    *((_DWORD *)a1 + 3) = v98;
                    *((_DWORD *)a1 + 5) = DeviceCount;
                    *((_DWORD *)a1 + 6) = v101;
                    *((_DWORD *)a1 + 4) = v99;
                    v33 = v103;
                    *((_OWORD *)a1 + 2) = v102;
                    v34 = v104;
                    *((_OWORD *)a1 + 3) = v33;
                    v35 = v105;
                    *((_OWORD *)a1 + 4) = v34;
                    v36 = v106;
                    *((_OWORD *)a1 + 5) = v35;
                    v37 = v107;
                    *((_OWORD *)a1 + 6) = v36;
                    v38 = v108;
                    *((_OWORD *)a1 + 7) = v37;
                    v39 = v109;
                    *((_OWORD *)a1 + 8) = v38;
                    *((_OWORD *)a1 + 9) = v39;
                    v40 = v111;
                    *((_OWORD *)a1 + 10) = v110;
                    v41 = v112;
                    *((_OWORD *)a1 + 11) = v40;
                    v42 = v113;
                    *((_OWORD *)a1 + 12) = v41;
                    v43 = v114;
                    *((_OWORD *)a1 + 13) = v42;
                    v44 = v115;
                    *((_OWORD *)a1 + 14) = v43;
                    *((_OWORD *)a1 + 15) = v44;
                    break;
                }
                goto LABEL_143;
              }
              SstpConfiguration = GetL2tpConfigParams(hKey[0]);
              RegCloseKey(hKey[0]);
              v22 = 0;
              if ( SstpConfiguration )
                break;
            }
          }
          if ( LOWORD(v2[118 * v19 + 12]) == 15 )
          {
            hKey[0] = 0;
            LODWORD(v102) = v2[118 * v19 + 7];
            v25 = DWORD1(v102);
            if ( v2[118 * v19 + 2] )
            {
              v25 = DWORD1(v102) | 1;
              DWORD1(v102) |= 1u;
            }
            if ( v2[118 * v19 + 3] )
              DWORD1(v102) = v25 | 2;
            v26 = (unsigned int)((char)v95 - 1);
            if ( v95 == 1 )
            {
              v22 = 32;
            }
            else
            {
              v26 = (unsigned int)((char)v95 - 2);
              if ( v95 == 2 )
              {
                v22 = 64;
              }
              else
              {
                v26 = (unsigned int)((char)v95 - 3);
                if ( v95 == 3 || (v26 = (unsigned int)((char)v95 - 4), v95 == 4) )
                {
                  v22 = 96;
                }
                else if ( v95 == 5 )
                {
                  v22 = 104;
                }
              }
            }
            v27 = OpenIkev2ConfigKey(v26, hKey);
            SstpConfiguration = v27;
            if ( v27 )
            {
              if ( (byte_1800CF404 & 8) != 0 )
              {
                LOWORD(v120) = 0;
                FormatRRASErrorString(&v120, L"DDMAdminServerGetInfoEx:OpenIkev2ConfigKey: Failed. error %d", v27);
                if ( (byte_1800CF404 & 8) != 0 )
                {
                  v32 = -1;
                  do
                    ++v32;
                  while ( *(_WORD *)&v121[2 * v32 - 4] );
                  goto LABEL_126;
                }
              }
              goto LABEL_127;
            }
            SstpConfiguration = GetIkev2ConfigParams(hKey[0], v95, (__int64)&v103, v22);
            RegCloseKey(hKey[0]);
            if ( SstpConfiguration )
            {
              if ( (byte_1800CF404 & 8) == 0 )
                goto LABEL_143;
              LOWORD(v120) = 0;
              FormatRRASErrorString(
                &v120,
                L"DDMAdminServerGetInfoEx:GetIkev2ConfigParams: Failed. error %d",
                SstpConfiguration);
              if ( (byte_1800CF404 & 8) == 0 )
                goto LABEL_143;
              v30 = -1;
              do
                ++v30;
              while ( *(_WORD *)&v121[2 * v30 - 4] );
              goto LABEL_111;
            }
          }
          if ( LOWORD(v2[118 * v19 + 12]) == 16 )
          {
            v28 = v93;
            DWORD2(v115) = v2[118 * v93 + 7];
            if ( v2[118 * v93 + 2] )
              HIDWORD(v115) |= 1u;
            if ( v2[118 * v93 + 3] )
              HIDWORD(v115) |= 2u;
          }
          else
          {
            v28 = v93;
          }
          v18 = v28 + 1;
          v93 = v18;
          if ( v18 >= v91 )
            goto LABEL_127;
        }
        if ( (byte_1800CF404 & 8) == 0 )
          goto LABEL_143;
        LOWORD(v120) = 0;
        FormatRRASErrorString(
          &v120,
          L"DDMAdminServerGetInfoEx:GetIkev2ConfigParams: Failed. error %d",
          SstpConfiguration);
        if ( (byte_1800CF404 & 8) == 0 )
          goto LABEL_143;
        v30 = -1;
        do
          ++v30;
        while ( *(_WORD *)&v121[2 * v30 - 4] );
LABEL_111:
        v119 = 0;
LABEL_106:
        v118 = 2 * v30 + 2;
        v117 = &v120;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v29, 2, v116);
      }
    }
  }
LABEL_143:
  LeaveCriticalSection(&gblDeviceTable);
  if ( v2 )
    HeapFree(hHeap, 0, v2);
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v120) = 0;
    FormatRRASErrorString(&v120, L"DDMAdminServerSetInfoEx: done %d", SstpConfiguration);
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      do
        ++v5;
      while ( *(_WORD *)&v121[2 * v5 - 4] );
      v119 = 0;
      v118 = 2 * v5 + 2;
      v117 = &v120;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, &v120, 2, v116);
    }
  }
  return SstpConfiguration;
}

```

## disassembly

```asm
0x180004b60  mov     rax, rsp
0x180004b63  mov     [rax+10h], rbx
0x180004b67  mov     [rax+18h], rsi
0x180004b6b  mov     [rax+20h], rdi
0x180004b6f  push    rbp
0x180004b70  push    r12
0x180004b72  push    r13
0x180004b74  push    r14
0x180004b76  push    r15
0x180004b78  lea     rbp, [rax-8A8h]
0x180004b7f  sub     rsp, 980h
0x180004b86  mov     rax, cs:__security_cookie
0x180004b8d  xor     rax, rsp
0x180004b90  mov     [rbp+8A0h+var_30], rax
0x180004b97  mov     rdi, rcx
0x180004b9a  xor     r12d, r12d
0x180004b9d  lea     rcx, [rsp+9A0h+var_950+1]; void *
0x180004ba2  xor     edx, edx; Val
0x180004ba4  mov     r8d, 0F7h; Size
0x180004baa  mov     r15d, r12d
0x180004bad  call    memset_0
0x180004bb2  xor     edx, edx; Val
0x180004bb4  mov     dword ptr [rsp+9A0h+dwBytes+4], r12d
0x180004bb9  mov     r8d, 7FCh; Size
0x180004bbf  mov     [rsp+9A0h+var_970], r12d
0x180004bc4  lea     rcx, [rbp+8A0h+var_82C]; void *
0x180004bc8  mov     dword ptr [rsp+9A0h+dwBytes], r12d
0x180004bcd  mov     [rbp+8A0h+var_830], r12d
0x180004bd1  call    memset_0
0x180004bd6  cmp     cs:dword_1800CF654, r12d
0x180004bdd  lea     rax, DdmGetDeviceConfigInfo
0x180004be4  mov     r14, cs:__imp_RasGetDeviceConfigInfo
0x180004beb  lea     rcx, [rsp+9A0h+var_950]; void *
0x180004bf0  cmovnz  r14, rax
0x180004bf4  mov     r8d, 0E8h; Size
0x180004bfa  xor     edx, edx; Val
0x180004bfc  call    memset_0
0x180004c01  lea     rcx, gblDeviceTable; lpCriticalSection
0x180004c08  call    cs:__imp_EnterCriticalSection
0x180004c0f  nop     dword ptr [rax+rax+00h]
0x180004c14  movzx   edx, byte ptr [rdi]
0x180004c17  lea     ebx, [r12+10h]
0x180004c1c  mov     ecx, edx
0x180004c1e  lea     eax, [rbx-8]
0x180004c21  or      r13, 0FFFFFFFFFFFFFFFFh
0x180004c25  lea     r8d, [rbx+70h]
0x180004c29  lea     esi, [rbx-0Eh]
0x180004c2c  sub     ecx, 1
0x180004c2f  jz      loc_180004E55
0x180004c35  sub     ecx, 1
0x180004c38  jz      loc_180004DE7
0x180004c3e  sub     ecx, 1
0x180004c41  jz      loc_180004D75
0x180004c47  sub     ecx, 1
0x180004c4a  jz      loc_180004D08
0x180004c50  cmp     ecx, 1
0x180004c53  jz      short loc_180004C9B
0x180004c55  test    cs:byte_1800CF404, bl
0x180004c5b  jz      loc_18000570A
0x180004c61  mov     r8d, edx
0x180004c64  mov     word ptr [rbp+8A0h+var_830], r12w
0x180004c69  lea     rdx, aDdmadminserver_15; "DDMAdminServerGetInfoEx: Invalid revisi"...
0x180004c70  lea     rcx, [rbp+8A0h+var_830]
0x180004c74  call    FormatRRASErrorString
0x180004c79  test    cs:byte_1800CF404, bl
0x180004c7f  jz      loc_18000570A
0x180004c85  lea     rcx, [rbp+8A0h+var_830]
0x180004c89  mov     rax, r13
0x180004c8c  inc     rax
0x180004c8f  cmp     [rcx+rax*2], r12w
0x180004c94  jnz     short loc_180004C8C
0x180004c96  jmp     loc_1800056D5
0x180004c9b  movzx   ecx, word ptr [rdi+0Ah]
0x180004c9f  cmp     cx, ax
0x180004ca2  jb      short loc_180004CB5
0x180004ca4  cmp     [rdi+9], sil
0x180004ca8  jnz     short loc_180004CB5
0x180004caa  mov     al, [rdi+8]
0x180004cad  cmp     al, dl
0x180004caf  jz      loc_180004E78
0x180004cb5  test    cs:byte_1800CF404, bl
0x180004cbb  jz      loc_18000570A
0x180004cc1  movzx   eax, byte ptr [rdi+8]
0x180004cc5  lea     rdx, aDdmadminserver_12; "DDMAdminServerGetInfoEx: Invalid Versio"...
0x180004ccc  movzx   r9d, byte ptr [rdi+9]
0x180004cd1  mov     r8d, ecx
0x180004cd4  lea     rcx, [rbp+8A0h+var_830]
0x180004cd8  mov     [rsp+9A0h+var_980], eax
0x180004cdc  mov     word ptr [rbp+8A0h+var_830], r12w
0x180004ce1  call    FormatRRASErrorString
0x180004ce6  test    cs:byte_1800CF404, bl
0x180004cec  jz      loc_18000570A
0x180004cf2  lea     rcx, [rbp+8A0h+var_830]
0x180004cf6  mov     rax, r13
0x180004cf9  inc     rax
0x180004cfc  cmp     [rcx+rax*2], r12w
0x180004d01  jnz     short loc_180004CF9
0x180004d03  jmp     loc_1800056D5
0x180004d08  movzx   ecx, word ptr [rdi+0Ah]
0x180004d0c  cmp     cx, ax
0x180004d0f  jb      short loc_180004D22
0x180004d11  cmp     [rdi+9], sil
0x180004d15  jnz     short loc_180004D22
0x180004d17  mov     al, [rdi+8]
0x180004d1a  cmp     al, dl
0x180004d1c  jz      loc_180004E78
0x180004d22  test    cs:byte_1800CF404, bl
0x180004d28  jz      loc_18000570A
0x180004d2e  movzx   eax, byte ptr [rdi+8]
0x180004d32  lea     rdx, aDdmadminserver_12; "DDMAdminServerGetInfoEx: Invalid Versio"...
0x180004d39  movzx   r9d, byte ptr [rdi+9]
0x180004d3e  mov     r8d, ecx
0x180004d41  lea     rcx, [rbp+8A0h+var_830]
0x180004d45  mov     [rsp+9A0h+var_980], eax
0x180004d49  mov     word ptr [rbp+8A0h+var_830], r12w
0x180004d4e  call    FormatRRASErrorString
0x180004d53  test    cs:byte_1800CF404, bl
0x180004d59  jz      loc_18000570A
0x180004d5f  lea     rcx, [rbp+8A0h+var_830]
0x180004d63  mov     rax, r13
0x180004d66  inc     rax
0x180004d69  cmp     [rcx+rax*2], r12w
0x180004d6e  jnz     short loc_180004D66
0x180004d70  jmp     loc_1800056D5
0x180004d75  movzx   ecx, word ptr [rdi+0Ah]
0x180004d79  mov     eax, 0E0h
0x180004d7e  cmp     cx, ax
0x180004d81  jb      short loc_180004D94
0x180004d83  cmp     [rdi+9], sil
0x180004d87  jnz     short loc_180004D94
0x180004d89  mov     al, [rdi+8]
0x180004d8c  cmp     al, dl
0x180004d8e  jz      loc_180004E78
0x180004d94  test    cs:byte_1800CF404, bl
0x180004d9a  jz      loc_18000570A
0x180004da0  movzx   eax, byte ptr [rdi+8]
0x180004da4  lea     rdx, aDdmadminserver_12; "DDMAdminServerGetInfoEx: Invalid Versio"...
0x180004dab  movzx   r9d, byte ptr [rdi+9]
0x180004db0  mov     r8d, ecx
0x180004db3  lea     rcx, [rbp+8A0h+var_830]
0x180004db7  mov     [rsp+9A0h+var_980], eax
0x180004dbb  mov     word ptr [rbp+8A0h+var_830], r12w
0x180004dc0  call    FormatRRASErrorString
0x180004dc5  test    cs:byte_1800CF404, bl
0x180004dcb  jz      loc_18000570A
0x180004dd1  lea     rcx, [rbp+8A0h+var_830]
0x180004dd5  mov     rax, r13
0x180004dd8  inc     rax
0x180004ddb  cmp     [rcx+rax*2], r12w
0x180004de0  jnz     short loc_180004DD8
0x180004de2  jmp     loc_1800056D5
0x180004de7  movzx   ecx, word ptr [rdi+0Ah]
0x180004deb  mov     eax, 0A0h
0x180004df0  cmp     cx, ax
0x180004df3  jb      short loc_180004E02
0x180004df5  cmp     [rdi+9], sil
0x180004df9  jnz     short loc_180004E02
0x180004dfb  mov     al, [rdi+8]
0x180004dfe  cmp     al, dl
0x180004e00  jz      short loc_180004E78
0x180004e02  test    cs:byte_1800CF404, bl
0x180004e08  jz      loc_18000570A
0x180004e0e  movzx   eax, byte ptr [rdi+8]
0x180004e12  lea     rdx, aDdmadminserver_12; "DDMAdminServerGetInfoEx: Invalid Versio"...
0x180004e19  movzx   r9d, byte ptr [rdi+9]
0x180004e1e  mov     r8d, ecx
0x180004e21  lea     rcx, [rbp+8A0h+var_830]
0x180004e25  mov     [rsp+9A0h+var_980], eax
0x180004e29  mov     word ptr [rbp+8A0h+var_830], r12w
0x180004e2e  call    FormatRRASErrorString
0x180004e33  test    cs:byte_1800CF404, bl
0x180004e39  jz      loc_18000570A
0x180004e3f  lea     rcx, [rbp+8A0h+var_830]
0x180004e43  mov     rax, r13
0x180004e46  inc     rax
0x180004e49  cmp     [rcx+rax*2], r12w
0x180004e4e  jnz     short loc_180004E46
0x180004e50  jmp     loc_1800056D5
0x180004e55  movzx   ecx, word ptr [rdi+0Ah]
0x180004e59  cmp     cx, r8w
0x180004e5d  jb      loc_18000568F
0x180004e63  cmp     [rdi+9], sil
0x180004e67  jnz     loc_18000568F
0x180004e6d  mov     al, [rdi+8]
0x180004e70  cmp     al, dl
0x180004e72  jnz     loc_18000568F
0x180004e78  mov     word ptr [rsp+9A0h+var_950+2], cx
0x180004e7d  mov     ecx, 11h; unsigned int
0x180004e82  mov     byte ptr [rsp+9A0h+var_950+1], sil
0x180004e87  mov     byte ptr [rsp+9A0h+var_950], al
0x180004e8b  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180004e90  mov     rcx, rax; this
0x180004e93  call    ?GetDeviceCount@DdmDeviceTable@@QEAAKXZ; DdmDeviceTable::GetDeviceCount(void)
0x180004e98  mov     [rsp+9A0h+var_944], eax
0x180004e9c  lea     r9, [rsp+9A0h+dwBytes]
0x180004ea1  mov     eax, cs:dword_1800CF4B0
0x180004ea7  lea     r8, [rsp+9A0h+var_970]
0x180004eac  mov     dword ptr [rsp+9A0h+var_940], eax
0x180004eb0  lea     rdx, [rsp+9A0h+dwBytes+4]
0x180004eb5  mov     rax, r14
0x180004eb8  mov     dword ptr [rsp+9A0h+dwBytes+4], 6
0x180004ec0  xor     ecx, ecx
0x180004ec2  mov     qword ptr [rsp+9A0h+var_980], r12
0x180004ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ecc  mov     ebx, eax
0x180004ece  test    eax, eax
0x180004ed0  jnz     short loc_180004EDC
0x180004ed2  mov     ebx, 10DFh
0x180004ed7  jmp     loc_18000570F
0x180004edc  cmp     eax, 25Bh
0x180004ee1  jnz     loc_18000570F
0x180004ee7  mov     r8d, dword ptr [rsp+9A0h+dwBytes]; dwBytes
0x180004eec  mov     ebx, 8
0x180004ef1  mov     rcx, cs:hHeap; hHeap
0x180004ef8  mov     edx, ebx; dwFlags
0x180004efa  call    cs:__imp_HeapAlloc
0x180004f01  nop     dword ptr [rax+rax+00h]
0x180004f06  mov     r15, rax
0x180004f09  test    rax, rax
0x180004f0c  jz      loc_18000570F
0x180004f12  mov     qword ptr [rsp+9A0h+var_980], rax
0x180004f17  lea     r9, [rsp+9A0h+dwBytes]
0x180004f1c  mov     rax, r14
0x180004f1f  lea     r8, [rsp+9A0h+var_970]
0x180004f24  lea     rdx, [rsp+9A0h+dwBytes+4]
0x180004f29  xor     ecx, ecx
0x180004f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f30  mov     ebx, eax
0x180004f32  test    eax, eax
0x180004f34  jnz     loc_18000570F
0x180004f3a  mov     edx, r12d
0x180004f3d  mov     [rsp+9A0h+var_964], edx
0x180004f41  cmp     [rsp+9A0h+var_970], r12d
0x180004f46  jbe     loc_1800053AD
0x180004f4c  mov     r14d, edx
0x180004f4f  imul    r12, r14, 1D8h
0x180004f56  cmp     word ptr [r12+r15+30h], 0Eh
0x180004f5d  jnz     short loc_180004FAE
0x180004f5f  mov     eax, [r12+r15+1Ch]
0x180004f64  xor     ecx, ecx
0x180004f66  mov     dword ptr [rbp+8A0h+var_888], eax
0x180004f69  mov     eax, dword ptr [rbp+8A0h+var_888+4]
0x180004f6c  cmp     [r12+r15+8], ecx
0x180004f71  jz      short loc_180004F79
0x180004f73  or      eax, 1
0x180004f76  mov     dword ptr [rbp+8A0h+var_888+4], eax
0x180004f79  cmp     [r12+r15+0Ch], ecx
0x180004f7e  jz      short loc_180004F85
0x180004f80  or      eax, esi
0x180004f82  mov     dword ptr [rbp+8A0h+var_888+4], eax
0x180004f85  lea     r9, [rbp+8A0h+var_888+8]
0x180004f89  xor     edx, edx
0x180004f8b  lea     r8, [rbp+8A0h+var_878]
0x180004f8f  call    cs:__imp_GetSstpConfiguration
0x180004f96  nop     dword ptr [rax+rax+00h]
0x180004f9b  mov     ebx, eax
0x180004f9d  xor     eax, eax
0x180004f9f  test    ebx, ebx
0x180004fa1  jnz     loc_1800051E2
0x180004fa7  mov     dword ptr [rbp+8A0h+var_888+0Ch], 800Ch
0x180004fae  cmp     word ptr [r12+r15+30h], 8
0x180004fb5  jnz     short loc_180004FEE
0x180004fb7  imul    rax, r14, 1D8h
0x180004fbe  xor     r12d, r12d
0x180004fc1  mov     ecx, [rax+r15+1Ch]
0x180004fc6  imul    rax, r14, 1D8h
0x180004fcd  mov     dword ptr [rbp+8A0h+var_8C0], ecx
0x180004fd0  cmp     [rax+r15+8], r12d
0x180004fd5  jz      short loc_180004FDB
0x180004fd7  or      dword ptr [rbp+8A0h+var_8C0+4], 1
0x180004fdb  imul    rax, r14, 1D8h
0x180004fe2  cmp     [rax+r15+0Ch], r12d
0x180004fe7  jz      short loc_180004FF1
0x180004fe9  or      dword ptr [rbp+8A0h+var_8C0+4], esi
0x180004fec  jmp     short loc_180004FF1
0x180004fee  xor     r12d, r12d
0x180004ff1  imul    rax, r14, 1D8h
0x180004ff8  cmp     word ptr [rax+r15+30h], 9
0x180004fff  jnz     loc_1800050A9
0x180005005  imul    rax, r14, 1D8h
0x18000500c  mov     ecx, [rax+r15+1Ch]
0x180005011  imul    rax, r14, 1D8h
0x180005018  mov     dword ptr [rbp+8A0h+var_8B8], ecx
0x18000501b  cmp     [rax+r15+8], r12d
0x180005020  jz      short loc_180005026
0x180005022  or      dword ptr [rbp+8A0h+var_8B8+4], 1
0x180005026  imul    rax, r14, 1D8h
0x18000502d  cmp     [rax+r15+0Ch], r12d
0x180005032  jz      short loc_180005037
0x180005034  or      dword ptr [rbp+8A0h+var_8B8+4], esi
0x180005037  movsx   eax, byte ptr [rsp+9A0h+var_950]
0x18000503c  cmp     al, 3
0x18000503e  jb      short loc_1800050A9
0x180005040  mov     ecx, eax
0x180005042  mov     [rsp+9A0h+hKey], r12
0x180005047  sub     ecx, 3
0x18000504a  jz      short loc_18000505C
0x18000504c  sub     ecx, 1
0x18000504f  jz      short loc_18000505C
0x180005051  cmp     ecx, 1
  ... truncated ...
```
