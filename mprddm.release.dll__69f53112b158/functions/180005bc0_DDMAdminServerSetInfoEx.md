# DDMAdminServerSetInfoEx

- ea: `0x180005bc0`
- end: `0x180006dc8`
- name: `DDMAdminServerSetInfoEx`
- size: `4616`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005bc0`
- `0x180007c0c`
- `0x180020e2c`
- `0x1800755b8`
- `0x180077264`
- `0x1800772c0`
- `0x1800775f0`
- `0x180077c70`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800068ab`
- `KERNEL32!HeapAlloc` at `0x1800068ab`
- `KERNEL32!LeaveCriticalSection` at `0x180006264`
- `KERNEL32!LeaveCriticalSection` at `0x180006264`
- `KERNEL32!EnterCriticalSection` at `0x180005c88`
- `KERNEL32!EnterCriticalSection` at `0x180005c88`
- `KERNEL32!HeapFree` at `0x180006310`
- `KERNEL32!HeapFree` at `0x180006310`
- `ADVAPI32!RegCloseKey` at `0x180006a3d`
- `ADVAPI32!RegCloseKey` at `0x180006af8`
- `ADVAPI32!RegCloseKey` at `0x180006a3d`
- `ADVAPI32!RegCloseKey` at `0x180006af8`
- `rasman!RasGetDeviceConfigInfo` at `0x180005c04`
- `rasman!RasSetDeviceConfigInfo` at `0x180005c32`
- `sstpcfg!SetSstpConfiguration` at `0x180006954`
- `sstpcfg!SetSstpConfiguration` at `0x180006954`

## string_xrefs

- `0x180006bf2`: `DDMAdminServerSetInfoEx:SetSstpConfiguration: unsupported HASH type. error %d`
- `0x180006985`: `DDMAdminServerSetInfoEx:SetSstpConfiguration: Failed. error %d`
- `0x180006c4d`: `DDMAdminServerSetInfoEx:OpenL2tpConfigKey: Failed. error %d`
- `0x180006a6c`: `DDMAdminServerSetInfoEx:SetL2tpConfigParams: Failed. error %d`
- `0x180006d2b`: `DDMAdminServerSetInfoEx:OpenIkev2ConfigKey: Failed. error %d`
- `0x180006c9a`: `DDMAdminServerSetInfoEx:SetIkev2ConfigParams: Failed. error %d`

## pseudocode

```c
__int64 __fastcall DDMAdminServerSetInfoEx(char *a1)
{
  __int64 (__fastcall *v1)(int, int, int, int, void *); // r15
  unsigned int v2; // r12d
  __int64 (__fastcall *v4)(__int64, unsigned int, unsigned int, __int64); // rcx
  char *v5; // r13
  char v6; // di
  unsigned int v7; // r14d
  char v8; // dl
  __int64 v9; // rsi
  unsigned int v10; // ecx
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  int v13; // eax
  __int128 v14; // xmm1
  __int64 v15; // rax
  __int128 v16; // xmm0
  __int64 v17; // rax
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rax
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  int v25; // eax
  __int128 v26; // xmm1
  __int64 v27; // rax
  __int128 v28; // xmm1
  __int64 v29; // r9
  unsigned int v30; // ecx
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  int v33; // eax
  __int64 v34; // rax
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int64 v44; // r9
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  int v47; // eax
  __int128 v48; // xmm1
  __int64 v49; // rax
  __int64 v50; // rax
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  __int64 v55; // r9
  unsigned int v56; // ebx
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  int v59; // eax
  __int128 v60; // xmm1
  __int64 v61; // rax
  __int128 v62; // xmm1
  __int128 v63; // xmm0
  unsigned int v64; // eax
  __int64 v65; // r8
  __int64 v66; // rax
  unsigned int v68; // ecx
  __int64 v69; // r9
  __int64 v70; // r8
  __int64 v71; // rax
  unsigned int v72; // eax
  char *v73; // rax
  unsigned int v74; // r8d
  char v75; // dl
  __int64 v76; // rcx
  char *v77; // r13
  int v78; // eax
  unsigned int v79; // r14d
  char v80; // r15
  unsigned int v81; // eax
  __int64 v82; // r8
  __int64 v83; // rax
  unsigned int v84; // eax
  unsigned int v85; // eax
  int v86; // ecx
  int v87; // edx
  __int64 *v88; // rdx
  __int64 v89; // r9
  int v90; // [rsp+28h] [rbp-E0h]
  int v91; // [rsp+28h] [rbp-E0h]
  int v92; // [rsp+28h] [rbp-E0h]
  int v93; // [rsp+28h] [rbp-E0h]
  int v94; // [rsp+28h] [rbp-E0h]
  __int16 v95; // [rsp+38h] [rbp-D0h]
  char *v96; // [rsp+40h] [rbp-C8h]
  unsigned int v97; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int dwBytes; // [rsp+4Ch] [rbp-BCh] BYREF
  int dwBytes_4; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v101; // [rsp+60h] [rbp-A8h] BYREF
  char v102; // [rsp+68h] [rbp-A0h] BYREF
  char v103; // [rsp+69h] [rbp-9Fh]
  __int16 v104; // [rsp+6Ah] [rbp-9Eh]
  int v105; // [rsp+6Ch] [rbp-9Ch]
  __int128 v106; // [rsp+70h] [rbp-98h]
  __int128 v107; // [rsp+80h] [rbp-88h] BYREF
  __int128 v108; // [rsp+90h] [rbp-78h]
  __int128 v109; // [rsp+A0h] [rbp-68h]
  __int128 v110; // [rsp+B0h] [rbp-58h]
  __int128 v111; // [rsp+C0h] [rbp-48h]
  __int128 v112; // [rsp+D0h] [rbp-38h]
  __int64 v113; // [rsp+E0h] [rbp-28h]
  __int64 v114; // [rsp+E8h] [rbp-20h]
  __int128 v115; // [rsp+F0h] [rbp-18h]
  __int128 v116; // [rsp+100h] [rbp-8h] BYREF
  __int128 v117; // [rsp+110h] [rbp+8h]
  __int128 v118; // [rsp+120h] [rbp+18h]
  __int128 v119; // [rsp+130h] [rbp+28h]
  __int64 v120; // [rsp+140h] [rbp+38h]
  __int64 v121; // [rsp+148h] [rbp+40h]
  __int64 (__fastcall *v122)(__int64, unsigned int, unsigned int, __int64); // [rsp+158h] [rbp+50h]
  _BYTE v123[16]; // [rsp+160h] [rbp+58h] BYREF
  int *v124; // [rsp+170h] [rbp+68h]
  int v125; // [rsp+178h] [rbp+70h]
  int v126; // [rsp+17Ch] [rbp+74h]
  int v127; // [rsp+188h] [rbp+80h] BYREF
  char v128[2044]; // [rsp+18Ch] [rbp+84h] BYREF

  v1 = (__int64 (__fastcall *)(int, int, int, int, void *))RasGetDeviceConfigInfo;
  v2 = 0;
  v95 = 0;
  dwBytes_4 = 0;
  if ( dword_1800CF654 )
    v1 = DdmGetDeviceConfigInfo;
  v97 = 0;
  v4 = (__int64 (__fastcall *)(__int64, unsigned int, unsigned int, __int64))RasSetDeviceConfigInfo;
  if ( dword_1800CF654 )
    v4 = DdmSetDeviceConfigInfo;
  dwBytes = 0;
  v122 = v4;
  v101 = 0;
  v5 = 0;
  v127 = 0;
  v6 = 0;
  v7 = 0;
  memset_0(v128, 0, sizeof(v128));
  memset_0(&v102, 0, 0xE8u);
  EnterCriticalSection(&gblDeviceTable);
  v8 = *a1;
  v9 = -1;
  if ( *a1 == 1 )
  {
    v10 = *((unsigned __int16 *)a1 + 5);
    if ( v10 < 0x70 || a1[9] != 3 || a1[8] != v8 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v89 = (unsigned __int8)a1[9];
      v94 = (unsigned __int8)a1[8];
      LOWORD(v127) = 0;
      FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: Invalid Version %d/type%d/size %d", v10, v89, v94);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)&v128[2 * v22 - 4] );
      goto LABEL_46;
    }
    v57 = *((_OWORD *)a1 + 6);
    v102 = a1[8];
    v58 = *((_OWORD *)a1 + 5);
    v59 = *((_DWORD *)a1 + 3);
    v119 = v57;
    v105 = v59;
    v60 = *((_OWORD *)a1 + 1);
    v61 = *((_QWORD *)a1 + 8);
    v118 = v58;
    v114 = v61;
    *(_QWORD *)&v58 = *((_QWORD *)a1 + 14);
    v50 = *((_QWORD *)a1 + 9);
    v106 = v60;
    v62 = *((_OWORD *)a1 + 3);
    v120 = v58;
    v63 = *((_OWORD *)a1 + 2);
    v108 = v62;
    v107 = v63;
LABEL_52:
    *(_QWORD *)&v115 = v50;
    goto LABEL_53;
  }
  if ( *a1 == 2 )
  {
    v10 = *((unsigned __int16 *)a1 + 5);
    if ( (unsigned __int16)v10 < 0x90u || a1[9] != 3 || a1[8] != v8 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v55 = (unsigned __int8)a1[9];
      v93 = (unsigned __int8)a1[8];
      LOWORD(v127) = 0;
      FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: Invalid Version %d/type%d/size %d", v10, v55, v93);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)&v128[2 * v22 - 4] );
      goto LABEL_46;
    }
    v45 = *((_OWORD *)a1 + 8);
    v102 = a1[8];
    v46 = *((_OWORD *)a1 + 7);
    v47 = *((_DWORD *)a1 + 3);
    v119 = v45;
    v105 = v47;
    v48 = *((_OWORD *)a1 + 1);
    v49 = *((_QWORD *)a1 + 12);
    v118 = v46;
    v114 = v49;
    *(_QWORD *)&v46 = *((_QWORD *)a1 + 18);
    v50 = *((_QWORD *)a1 + 13);
    v106 = v48;
    v51 = *((_OWORD *)a1 + 3);
    v120 = v46;
    v52 = *((_OWORD *)a1 + 2);
    v108 = v51;
    v53 = *((_OWORD *)a1 + 5);
    v107 = v52;
    v54 = *((_OWORD *)a1 + 4);
    v110 = v53;
    v109 = v54;
    goto LABEL_52;
  }
  if ( *a1 != 3 )
  {
    if ( *a1 == 4 )
    {
      v10 = *((unsigned __int16 *)a1 + 5);
      if ( (unsigned __int16)v10 >= 0xD8u && a1[9] == 3 && a1[8] == v8 )
      {
        v23 = *(_OWORD *)(a1 + 152);
        v102 = a1[8];
        v24 = *(_OWORD *)(a1 + 136);
        v25 = *((_DWORD *)a1 + 3);
        v116 = v23;
        v105 = v25;
        v26 = *((_OWORD *)a1 + 11);
        v27 = *((_QWORD *)a1 + 16);
        v115 = v24;
        v114 = v27;
        *(_QWORD *)&v24 = *((_QWORD *)a1 + 21);
        v17 = *((_QWORD *)a1 + 27);
        v118 = v26;
        v120 = *((_QWORD *)a1 + 26);
        v28 = *((_OWORD *)a1 + 2);
        *(_QWORD *)&v117 = v24;
        v19 = *((_OWORD *)a1 + 12);
        v107 = v28;
        v109 = *((_OWORD *)a1 + 4);
        v111 = *((_OWORD *)a1 + 6);
        goto LABEL_23;
      }
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v29 = (unsigned __int8)a1[9];
      v91 = (unsigned __int8)a1[8];
      LOWORD(v127) = 0;
      FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: Invalid Version %d/type%d/size %d", v10, v29, v91);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)&v128[2 * v22 - 4] );
    }
    else
    {
      if ( *a1 != 5 )
      {
LABEL_47:
        v56 = 87;
        goto LABEL_61;
      }
      v10 = *((unsigned __int16 *)a1 + 5);
      if ( (unsigned __int16)v10 >= 0xE8u && a1[9] == 3 && a1[8] == v8 )
      {
        v11 = *((_OWORD *)a1 + 10);
        v102 = a1[8];
        v12 = *((_OWORD *)a1 + 9);
        v13 = *((_DWORD *)a1 + 3);
        v116 = v11;
        v105 = v13;
        v14 = *((_OWORD *)a1 + 12);
        v15 = *((_QWORD *)a1 + 17);
        v115 = v12;
        v114 = v15;
        v16 = *((_OWORD *)a1 + 11);
        v17 = *((_QWORD *)a1 + 29);
        v118 = v14;
        v120 = *((_QWORD *)a1 + 28);
        v18 = *((_OWORD *)a1 + 2);
        v117 = v16;
        v19 = *((_OWORD *)a1 + 13);
        v107 = v18;
        v109 = *((_OWORD *)a1 + 4);
        v111 = *((_OWORD *)a1 + 6);
        v113 = *((_QWORD *)a1 + 16);
LABEL_23:
        v119 = v19;
        v121 = v17;
        v106 = *((_OWORD *)a1 + 1);
        v108 = *((_OWORD *)a1 + 3);
        v110 = *((_OWORD *)a1 + 5);
        v112 = *((_OWORD *)a1 + 7);
LABEL_53:
        v103 = 3;
        v104 = v10;
        goto LABEL_54;
      }
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v20 = (unsigned __int8)a1[9];
      v90 = (unsigned __int8)a1[8];
      LOWORD(v127) = 0;
      FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: Invalid Version %d/type%d/size %d", v10, v20, v90);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)&v128[2 * v22 - 4] );
    }
LABEL_46:
    v126 = 0;
    v125 = 2 * v22 + 2;
    v124 = &v127;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v21, 2, v123);
    goto LABEL_47;
  }
  v30 = *((unsigned __int16 *)a1 + 5);
  if ( (unsigned __int16)v30 < 0xD0u || a1[9] != 3 || a1[8] != v8 )
  {
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_47;
    v44 = (unsigned __int8)a1[9];
    v92 = (unsigned __int8)a1[8];
    LOWORD(v127) = 0;
    FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: Invalid Version %d/type%d/size %d", v30, v44, v92);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_47;
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)&v128[2 * v22 - 4] );
    goto LABEL_46;
  }
  v31 = *(_OWORD *)(a1 + 136);
  v102 = a1[8];
  v32 = *(_OWORD *)(a1 + 152);
  v33 = *((_DWORD *)a1 + 3);
  v115 = v31;
  v105 = v33;
  v34 = *((_QWORD *)a1 + 16);
  *(_QWORD *)&v117 = *((_QWORD *)a1 + 21);
  v35 = *((_OWORD *)a1 + 12);
  v103 = 3;
  v116 = v32;
  v104 = v30;
  v36 = *((_OWORD *)a1 + 11);
  v114 = v34;
  v119 = v35;
  v37 = *((_OWORD *)a1 + 1);
  v118 = v36;
  *(_QWORD *)&v36 = *((_QWORD *)a1 + 26);
  v106 = v37;
  v38 = *((_OWORD *)a1 + 3);
  v120 = v36;
  v39 = *((_OWORD *)a1 + 2);
  v108 = v38;
  v40 = *((_OWORD *)a1 + 5);
  v107 = v39;
  v41 = *((_OWORD *)a1 + 4);
  v110 = v40;
  v42 = *((_OWORD *)a1 + 7);
  v109 = v41;
  v43 = *((_OWORD *)a1 + 6);
  v112 = v42;
  v111 = v43;
LABEL_54:
  v64 = DDMGetRestrictedPortCount(&v101);
  v56 = v64;
  if ( v64 )
  {
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_60;
    LOWORD(v127) = 0;
    FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: DDMGetRestrictedPortCount Failed with %d", v64);
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_60;
    v66 = -1;
    do
      ++v66;
    while ( *(_WORD *)&v128[2 * v66 - 4] );
    goto LABEL_59;
  }
  v68 = v101;
  if ( v101 == -1 )
  {
    v7 = 30000;
    v69 = 0x4000;
    v68 = 30000;
  }
  else
  {
    v69 = v101;
  }
  if ( (v105 & 1) != 0 )
  {
    if ( (unsigned int)v114 > (unsigned int)v69 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      LOWORD(v127) = 0;
      FormatRRASErrorString(
        &v127,
        L"DDMAdminServerSetInfoEx: Number of PPTP ports %d are exceeding Max Number of ports %d");
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)&v128[2 * v22 - 4] );
      goto LABEL_46;
    }
    if ( (v114 & 0xFFFFFFFC00000000uLL) != 0 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      LOWORD(v127) = 0;
      FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: Invalid PPTP port flags %d ");
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)&v128[2 * v22 - 4] );
      goto LABEL_46;
    }
  }
  if ( (v105 & 2) != 0 )
  {
    if ( (unsigned int)v115 > v68 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      LOWORD(v127) = 0;
      FormatRRASErrorString(
        &v127,
        L"DDMAdminServerSetInfoEx: Number of L2TP ports %d are exceeding Max Number of ports %d",
        (unsigned int)v115,
        v69);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)&v128[2 * v22 - 4] );
      goto LABEL_46;
    }
    if ( (DWORD1(v115) & 0xFFFFFFFC) != 0 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      LOWORD(v127) = 0;
      FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: Invalid L2TP port flags %d ", DWORD1(v115), v69);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)&v128[2 * v22 - 4] );
      goto LABEL_46;
    }
    if ( (BYTE8(v115) & 1) != 0
      && (unsigned __int8)(v102 - 3) <= 2u
      && ((int)v116 < 300 || SDWORD2(v116) < 300
                          || SHIDWORD(v116) < 1024
                          || (int)v107 > 172799
                          || SDWORD2(v107) > 172799) )
    {
      v56 = 87;
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_60;
      LOWORD(v127) = 0;
      FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: ValidateL2tpParams failed : %d", 87, v69);
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_60;
      v66 = -1;
      do
        ++v66;
      while ( *(_WORD *)&v128[2 * v66 - 4] );
LABEL_59:
      v126 = 0;
      v125 = 2 * v66 + 2;
      v124 = &v127;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v65, 2, v123);
LABEL_60:
      v6 = 0;
      goto LABEL_61;
    }
  }
  if ( (v105 & 4) != 0 )
  {
    if ( (unsigned int)v118 > v68 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      LOWORD(v127) = 0;
      FormatRRASErrorString(
        &v127,
        L"DDMAdminServerSetInfoEx: Number of SSTP ports %d are exceeding Max Number of ports %d",
        (unsigned int)v118,
        v69);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)&v128[2 * v22 - 4] );
      goto LABEL_46;
    }
    if ( (DWORD1(v118) & 0xFFFFFFFC) != 0 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      LOWORD(v127) = 0;
      FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: Invalid SSTP port flags %d ", DWORD1(v118), v69);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_47;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)&v128[2 * v22 - 4] );
      goto LABEL_46;
    }
  }
  if ( (v105 & 8) != 0 )
  {
    if ( (unsigned int)v106 > v68 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_134;
      LOWORD(v127) = 0;
      FormatRRASErrorString(
        &v127,
        L"DDMAdminServerSetInfoEx: Number of IKEV2 ports %d are exceeding Max Number of ports %d",
        (unsigned int)v106,
        v69);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_134;
      v71 = -1;
      do
        ++v71;
      while ( *(_WORD *)&v128[2 * v71 - 4] );
LABEL_133:
      v126 = 0;
      v125 = 2 * v71 + 2;
      v124 = &v127;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v70, 2, v123);
LABEL_134:
      v56 = 87;
      goto LABEL_60;
    }
    if ( (DWORD1(v106) & 0xFFFFFFFC) != 0 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_134;
      LOWORD(v127) = 0;
      FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: Invalid IKEv2 port flags %d ", DWORD1(v106), v69);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_134;
      v71 = -1;
      do
        ++v71;
      while ( *(_WORD *)&v128[2 * v71 - 4] );
      goto LABEL_133;
    }
    if ( (BYTE8(v106) & 1) != 0
      && ((int)v107 < 300
       || SDWORD1(v107) < 120
       || SDWORD2(v107) < 300
       || (int)v113 < 300
       || SHIDWORD(v107) < 1024
       || (int)v107 > 172799
       || SDWORD2(v107) > 172799
       || (int)v113 > 172799
       || (_DWORD)v108) )
    {
      goto LABEL_134;
    }
  }
  if ( (v105 & 0x10) != 0 )
  {
    if ( (unsigned int)v121 > v7 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_134;
      LOWORD(v127) = 0;
      FormatRRASErrorString(
        &v127,
        L"DDMAdminServerSetInfoEx: Number of GRE ports %d are exceeding Max Number of ports %d",
        (unsigned int)v121,
        v7);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_134;
      v71 = -1;
      do
        ++v71;
      while ( *(_WORD *)&v128[2 * v71 - 4] );
      goto LABEL_133;
    }
    if ( (v121 & 0xFFFFFFFC00000000uLL) != 0 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_134;
      LOWORD(v127) = 0;
      FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: Invalid GRE port flags %d ", HIDWORD(v121), v69);
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_134;
      v71 = -1;
      do
        ++v71;
      while ( *(_WORD *)&v128[2 * v71 - 4] );
      goto LABEL_133;
    }
  }
  dwBytes_4 = 6;
  v72 = v1(0, (int)&dwBytes_4, (int)&v97, (int)&dwBytes, 0);
  v56 = v72;
  if ( !v72 )
  {
    v56 = 4319;
    goto LABEL_60;
  }
  if ( v72 != 603 )
    goto LABEL_60;
  v73 = (char *)HeapAlloc(hHeap, 8u, dwBytes);
  v96 = v73;
  v5 = v73;
  if ( !v73 )
  {
    v56 = 8;
    goto LABEL_60;
  }
  v56 = v1(0, (int)&dwBytes_4, (int)&v97, (int)&dwBytes, v73);
  if ( v56 )
    goto LABEL_60;
  v74 = v97;
  if ( !v97 )
    goto LABEL_60;
  v75 = v105;
  while ( 1 )
  {
    v76 = 472LL * v2;
    v77 = &v5[v76];
    v78 = (unsigned __int16)*((_DWORD *)v77 + 12);
    switch ( v78 )
    {
      case 14:
        if ( (v75 & 4) == 0 )
          goto LABEL_212;
        v79 = v118;
        v80 = BYTE4(v118);
        if ( HIDWORD(v118) != 32780 )
        {
          v56 = 87;
          if ( (byte_1800CF404 & 0x10) == 0 )
            goto LABEL_230;
          LOWORD(v127) = 0;
          FormatRRASErrorString(
            &v127,
            L"DDMAdminServerSetInfoEx:SetSstpConfiguration: unsupported HASH type. error %d",
            87);
          if ( (byte_1800CF404 & 0x10) == 0 )
            goto LABEL_230;
          v83 = -1;
          do
            ++v83;
          while ( *(_WORD *)&v128[2 * v83 - 4] );
          v88 = RasDdmTraceInfo;
          goto LABEL_229;
        }
        v81 = SetSstpConfiguration(0, 0, DWORD2(v118), v120 & -(__int64)(DWORD2(v119) != 0));
        v56 = v81;
        if ( v81 )
        {
          if ( (byte_1800CF404 & 8) != 0 )
          {
            LOWORD(v127) = 0;
            FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx:SetSstpConfiguration: Failed. error %d", v81);
            if ( (byte_1800CF404 & 8) != 0 )
            {
              v83 = -1;
              do
                ++v83;
              while ( *(_WORD *)&v128[2 * v83 - 4] );
              goto LABEL_228;
            }
          }
          goto LABEL_230;
        }
        goto LABEL_200;
      case 8:
        if ( (v75 & 1) == 0 )
          goto LABEL_212;
        v79 = v114;
        v80 = BYTE4(v114);
        goto LABEL_204;
      case 9:
        if ( (v75 & 2) == 0 )
          goto LABEL_212;
        v79 = v115;
        v80 = BYTE4(v115);
        if ( (BYTE8(v115) & 1) == 0 || (unsigned __int8)(v102 - 3) > 2u )
          goto LABEL_204;
        hKey = 0;
        v84 = OpenL2tpConfigKey(v76, &hKey);
        v56 = v84;
        if ( v84 )
        {
          if ( (byte_1800CF404 & 8) != 0 )
          {
            LOWORD(v127) = 0;
            FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx:OpenL2tpConfigKey: Failed. error %d", v84);
            if ( (byte_1800CF404 & 8) != 0 )
            {
              v83 = -1;
              do
                ++v83;
              while ( *(_WORD *)&v128[2 * v83 - 4] );
              goto LABEL_228;
            }
          }
          goto LABEL_230;
        }
        v56 = SetL2tpConfigParams(hKey, v102, (__int64)&v116);
        RegCloseKey(hKey);
        if ( v56 )
        {
          if ( (byte_1800CF404 & 8) != 0 )
          {
            LOWORD(v127) = 0;
            FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx:SetL2tpConfigParams: Failed. error %d", v56);
            if ( (byte_1800CF404 & 8) != 0 )
            {
              v83 = -1;
              do
                ++v83;
              while ( *(_WORD *)&v128[2 * v83 - 4] );
              goto LABEL_228;
            }
          }
          goto LABEL_230;
        }
        goto LABEL_200;
    }
    if ( v78 != 15 )
    {
      if ( v78 != 16 || (v75 & 0x10) == 0 )
        goto LABEL_212;
      v79 = v121;
      v80 = BYTE4(v121);
      goto LABEL_204;
    }
    if ( (v75 & 8) == 0 )
      goto LABEL_212;
    v79 = v106;
    v80 = BYTE4(v106);
    if ( (BYTE8(v106) & 1) == 0 )
      goto LABEL_204;
    hKey = 0;
    v85 = OpenIkev2ConfigKey(v76, &hKey);
    v56 = v85;
    if ( v85 )
    {
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_230;
      LOWORD(v127) = 0;
      FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx:OpenIkev2ConfigKey: Failed. error %d", v85);
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_230;
      v83 = -1;
      do
        ++v83;
      while ( *(_WORD *)&v128[2 * v83 - 4] );
LABEL_228:
      v88 = RasDdmTraceError;
LABEL_229:
      v126 = 0;
      v125 = 2 * v83 + 2;
      v124 = &v127;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v88, v82, 2, v123);
      goto LABEL_230;
    }
    v56 = SetIkev2ConfigParams(hKey, v102, (__int64)&v107);
    RegCloseKey(hKey);
    if ( v56 )
      break;
LABEL_200:
    LOBYTE(v95) = 1;
LABEL_204:
    if ( v79 > *((_DWORD *)v77 + 11) )
      *((_DWORD *)v77 + 11) = v79;
    if ( *((_DWORD *)v77 + 7) != v79
      || (v86 = v80 & 1, *((_DWORD *)v77 + 2) != v86)
      || (v87 = v80 & 2, *((_DWORD *)v77 + 3) != (v87 != 0)) )
    {
      HIBYTE(v95) = 1;
      v86 = v80 & 1;
      v87 = v80 & 2;
    }
    *((_DWORD *)v77 + 2) = v86;
    *((_DWORD *)v77 + 7) = v79;
    *((_DWORD *)v77 + 1) = 1;
    *((_DWORD *)v77 + 3) = v87 != 0;
    v56 = v122(0, 1u, 472u, (__int64)v77);
    if ( v56 )
    {
      v5 = v96;
LABEL_213:
      v6 = v95;
      goto LABEL_61;
    }
    v74 = v97;
    v75 = v105;
LABEL_212:
    v5 = v96;
    if ( ++v2 >= v74 )
      goto LABEL_213;
  }
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v127) = 0;
    FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx:SetIkev2ConfigParams: Failed. error %d", v56);
    if ( (byte_1800CF404 & 8) != 0 )
    {
      v83 = -1;
      do
        ++v83;
      while ( *(_WORD *)&v128[2 * v83 - 4] );
      goto LABEL_228;
    }
  }
LABEL_230:
  v5 = v96;
  v6 = v95;
LABEL_61:
  LeaveCriticalSection(&gblDeviceTable);
  if ( HIBYTE(v95) )
    ((void (*)(void))qword_1800CF6A8)();
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v127) = 0;
    FormatRRASErrorString(&v127, L"DDMAdminServerSetInfoEx: done %d", v56);
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      do
        ++v9;
      while ( *(_WORD *)&v128[2 * v9 - 4] );
      v126 = 0;
      v125 = 2 * v9 + 2;
      v124 = &v127;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, &v127, 2, v123);
    }
  }
  if ( v5 )
    HeapFree(hHeap, 0, v5);
  if ( v6 && !v56 )
    return 3011;
  return v56;
}

```

## disassembly

```asm
0x180005bc0  mov     rax, rsp
0x180005bc3  mov     [rax+10h], rbx
0x180005bc7  mov     [rax+18h], rsi
0x180005bcb  mov     [rax+20h], rdi
0x180005bcf  push    rbp
0x180005bd0  push    r12
0x180005bd2  push    r13
0x180005bd4  push    r14
0x180005bd6  push    r15
0x180005bd8  lea     rbp, [rax-8B8h]
0x180005bdf  sub     rsp, 990h
0x180005be6  mov     rax, cs:__security_cookie
0x180005bed  xor     rax, rsp
0x180005bf0  mov     [rbp+8B0h+var_30], rax
0x180005bf7  mov     eax, cs:dword_1800CF654
0x180005bfd  lea     rdx, DdmSetDeviceConfigInfo
0x180005c04  mov     r15, cs:__imp_RasGetDeviceConfigInfo
0x180005c0b  xor     r12d, r12d
0x180005c0e  mov     rbx, rcx
0x180005c11  mov     byte ptr [rsp+9B0h+var_980], r12b
0x180005c16  test    eax, eax
0x180005c18  mov     byte ptr [rsp+9B0h+var_980+1], r12b
0x180005c1d  lea     rcx, DdmGetDeviceConfigInfo
0x180005c24  mov     dword ptr [rsp+9B0h+dwBytes+4], r12d
0x180005c29  cmovnz  r15, rcx
0x180005c2d  mov     [rsp+9B0h+var_970], r12d
0x180005c32  mov     rcx, cs:__imp_RasSetDeviceConfigInfo
0x180005c39  mov     r8d, 7FCh; Size
0x180005c3f  cmovnz  rcx, rdx
0x180005c43  mov     dword ptr [rsp+9B0h+dwBytes], r12d
0x180005c48  mov     [rbp+8B0h+var_860], rcx
0x180005c4c  xor     edx, edx; Val
0x180005c4e  lea     rcx, [rbp+8B0h+var_82C]; void *
0x180005c55  mov     [rsp+9B0h+var_958], r12d
0x180005c5a  mov     r13d, r12d
0x180005c5d  mov     [rbp+8B0h+var_830], r12d
0x180005c64  mov     dil, r12b
0x180005c67  mov     r14d, r12d
0x180005c6a  call    memset_0
0x180005c6f  xor     edx, edx; Val
0x180005c71  lea     rcx, [rsp+9B0h+var_950]; void *
0x180005c76  mov     r8d, 0E8h; Size
0x180005c7c  call    memset_0
0x180005c81  lea     rcx, gblDeviceTable; lpCriticalSection
0x180005c88  call    cs:__imp_EnterCriticalSection
0x180005c8f  nop     dword ptr [rax+rax+00h]
0x180005c94  movzx   edx, byte ptr [rbx]
0x180005c97  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005c9b  mov     ecx, edx
0x180005c9d  sub     ecx, 1
0x180005ca0  jz      loc_180006147
0x180005ca6  sub     ecx, 1
0x180005ca9  jz      loc_18000602C
0x180005caf  sub     ecx, 1
0x180005cb2  jz      loc_180005F02
0x180005cb8  sub     ecx, 1
0x180005cbb  jz      loc_180005DD7
0x180005cc1  cmp     ecx, 1
0x180005cc4  jnz     loc_18000613D
0x180005cca  movzx   ecx, word ptr [rbx+0Ah]
0x180005cce  mov     eax, 0E8h
0x180005cd3  cmp     cx, ax
0x180005cd6  jb      loc_180005D79
0x180005cdc  cmp     byte ptr [rbx+9], 3
0x180005ce0  jnz     loc_180005D79
0x180005ce6  mov     al, [rbx+8]
0x180005ce9  cmp     al, dl
0x180005ceb  jnz     loc_180005D79
0x180005cf1  movups  xmm1, xmmword ptr [rbx+0A0h]
0x180005cf8  mov     byte ptr [rsp+9B0h+var_950], al
0x180005cfc  movups  xmm0, xmmword ptr [rbx+90h]
0x180005d03  mov     eax, [rbx+0Ch]
0x180005d06  movups  [rbp+8B0h+var_8B8], xmm1
0x180005d0a  mov     dword ptr [rsp+9B0h+var_950+4], eax
0x180005d0e  movups  xmm1, xmmword ptr [rbx+0C0h]
0x180005d15  mov     rax, [rbx+88h]
0x180005d1c  movups  [rbp+8B0h+var_8C8], xmm0
0x180005d20  mov     [rbp+8B0h+var_8D0], rax
0x180005d24  movups  xmm0, xmmword ptr [rbx+0B0h]
0x180005d2b  mov     rax, [rbx+0E8h]
0x180005d32  movups  [rbp+8B0h+var_898], xmm1
0x180005d36  movsd   xmm1, qword ptr [rbx+0E0h]
0x180005d3e  movsd   [rbp+8B0h+var_878], xmm1
0x180005d43  movups  xmm1, xmmword ptr [rbx+20h]
0x180005d47  movups  [rbp+8B0h+var_8A8], xmm0
0x180005d4b  movups  xmm0, xmmword ptr [rbx+0D0h]
0x180005d52  movups  [rsp+9B0h+var_940+8], xmm1
0x180005d57  movups  xmm1, xmmword ptr [rbx+40h]
0x180005d5b  movups  [rbp+8B0h+var_918], xmm1
0x180005d5f  movups  xmm1, xmmword ptr [rbx+60h]
0x180005d63  movups  [rbp+8B0h+var_8F8], xmm1
0x180005d67  movsd   xmm1, qword ptr [rbx+80h]
0x180005d6f  movsd   [rbp+8B0h+var_8D8], xmm1
0x180005d74  jmp     loc_180005E76
0x180005d79  test    cs:byte_1800CF404, 10h
0x180005d80  jz      loc_18000613D
0x180005d86  movzx   eax, byte ptr [rbx+8]
0x180005d8a  lea     rdx, aDdmadminserver_10; "DDMAdminServerSetInfoEx: Invalid Versio"...
0x180005d91  movzx   r9d, byte ptr [rbx+9]
0x180005d96  mov     r8d, ecx
0x180005d99  lea     rcx, [rbp+8B0h+var_830]
0x180005da0  mov     [rsp+9B0h+var_990], eax
0x180005da4  mov     word ptr [rbp+8B0h+var_830], r12w
0x180005dac  call    FormatRRASErrorString
0x180005db1  test    cs:byte_1800CF404, 10h
0x180005db8  jz      loc_18000613D
0x180005dbe  lea     rcx, [rbp+8B0h+var_830]
0x180005dc5  mov     rax, rsi
0x180005dc8  inc     rax
0x180005dcb  cmp     [rcx+rax*2], r12w
0x180005dd0  jnz     short loc_180005DC8
0x180005dd2  jmp     loc_180006102
0x180005dd7  movzx   ecx, word ptr [rbx+0Ah]
0x180005ddb  mov     eax, 0D8h
0x180005de0  cmp     cx, ax
0x180005de3  jb      loc_180005EA4
0x180005de9  cmp     byte ptr [rbx+9], 3
0x180005ded  jnz     loc_180005EA4
0x180005df3  mov     al, [rbx+8]
0x180005df6  cmp     al, dl
0x180005df8  jnz     loc_180005EA4
0x180005dfe  movups  xmm1, xmmword ptr [rbx+98h]
0x180005e05  mov     byte ptr [rsp+9B0h+var_950], al
0x180005e09  movups  xmm0, xmmword ptr [rbx+88h]
0x180005e10  mov     eax, [rbx+0Ch]
0x180005e13  movups  [rbp+8B0h+var_8B8], xmm1
0x180005e17  mov     dword ptr [rsp+9B0h+var_950+4], eax
0x180005e1b  movups  xmm1, xmmword ptr [rbx+0B0h]
0x180005e22  mov     rax, [rbx+80h]
0x180005e29  movups  [rbp+8B0h+var_8C8], xmm0
0x180005e2d  mov     [rbp+8B0h+var_8D0], rax
0x180005e31  movsd   xmm0, qword ptr [rbx+0A8h]
0x180005e39  mov     rax, [rbx+0D8h]
0x180005e40  movups  [rbp+8B0h+var_898], xmm1
0x180005e44  movsd   xmm1, qword ptr [rbx+0D0h]
0x180005e4c  movsd   [rbp+8B0h+var_878], xmm1
0x180005e51  movups  xmm1, xmmword ptr [rbx+20h]
0x180005e55  movsd   qword ptr [rbp+8B0h+var_8A8], xmm0
0x180005e5a  movups  xmm0, xmmword ptr [rbx+0C0h]
0x180005e61  movups  [rsp+9B0h+var_940+8], xmm1
0x180005e66  movups  xmm1, xmmword ptr [rbx+40h]
0x180005e6a  movups  [rbp+8B0h+var_918], xmm1
0x180005e6e  movups  xmm1, xmmword ptr [rbx+60h]
0x180005e72  movups  [rbp+8B0h+var_8F8], xmm1
0x180005e76  movups  [rbp+8B0h+var_888], xmm0
0x180005e7a  mov     [rbp+8B0h+var_870], rax
0x180005e7e  movups  xmm0, xmmword ptr [rbx+10h]
0x180005e82  movups  [rsp+9B0h+var_950+8], xmm0
0x180005e87  movups  xmm0, xmmword ptr [rbx+30h]
0x180005e8b  movups  [rbp+8B0h+var_928], xmm0
0x180005e8f  movups  xmm0, xmmword ptr [rbx+50h]
0x180005e93  movups  [rbp+8B0h+var_908], xmm0
0x180005e97  movups  xmm0, xmmword ptr [rbx+70h]
0x180005e9b  movups  [rbp+8B0h+var_8E8], xmm0
0x180005e9f  jmp     loc_1800061B8
0x180005ea4  test    cs:byte_1800CF404, 10h
0x180005eab  jz      loc_18000613D
0x180005eb1  movzx   eax, byte ptr [rbx+8]
0x180005eb5  lea     rdx, aDdmadminserver_10; "DDMAdminServerSetInfoEx: Invalid Versio"...
0x180005ebc  movzx   r9d, byte ptr [rbx+9]
0x180005ec1  mov     r8d, ecx
0x180005ec4  lea     rcx, [rbp+8B0h+var_830]
0x180005ecb  mov     [rsp+9B0h+var_990], eax
0x180005ecf  mov     word ptr [rbp+8B0h+var_830], r12w
0x180005ed7  call    FormatRRASErrorString
0x180005edc  test    cs:byte_1800CF404, 10h
0x180005ee3  jz      loc_18000613D
0x180005ee9  lea     rcx, [rbp+8B0h+var_830]
0x180005ef0  mov     rax, rsi
0x180005ef3  inc     rax
0x180005ef6  cmp     [rcx+rax*2], r12w
0x180005efb  jnz     short loc_180005EF3
0x180005efd  jmp     loc_180006102
0x180005f02  movzx   ecx, word ptr [rbx+0Ah]
0x180005f06  mov     eax, 0D0h
0x180005f0b  cmp     cx, ax
0x180005f0e  jb      loc_180005FCE
0x180005f14  cmp     byte ptr [rbx+9], 3
0x180005f18  jnz     loc_180005FCE
0x180005f1e  mov     al, [rbx+8]
0x180005f21  cmp     al, dl
0x180005f23  jnz     loc_180005FCE
0x180005f29  movups  xmm0, xmmword ptr [rbx+88h]
0x180005f30  mov     byte ptr [rsp+9B0h+var_950], al
0x180005f34  movups  xmm1, xmmword ptr [rbx+98h]
0x180005f3b  mov     eax, [rbx+0Ch]
0x180005f3e  movups  [rbp+8B0h+var_8C8], xmm0
0x180005f42  mov     dword ptr [rsp+9B0h+var_950+4], eax
0x180005f46  movsd   xmm0, qword ptr [rbx+0A8h]
0x180005f4e  mov     rax, [rbx+80h]
0x180005f55  movsd   qword ptr [rbp+8B0h+var_8A8], xmm0
0x180005f5a  movups  xmm0, xmmword ptr [rbx+0C0h]
0x180005f61  mov     byte ptr [rsp+9B0h+var_950+1], 3
0x180005f66  movups  [rbp+8B0h+var_8B8], xmm1
0x180005f6a  mov     word ptr [rsp+9B0h+var_950+2], cx
0x180005f6f  movups  xmm1, xmmword ptr [rbx+0B0h]
0x180005f76  mov     [rbp+8B0h+var_8D0], rax
0x180005f7a  movups  [rbp+8B0h+var_888], xmm0
0x180005f7e  movups  xmm0, xmmword ptr [rbx+10h]
0x180005f82  movups  [rbp+8B0h+var_898], xmm1
0x180005f86  movsd   xmm1, qword ptr [rbx+0D0h]
0x180005f8e  movups  [rsp+9B0h+var_950+8], xmm0
0x180005f93  movups  xmm0, xmmword ptr [rbx+30h]
0x180005f97  movsd   [rbp+8B0h+var_878], xmm1
0x180005f9c  movups  xmm1, xmmword ptr [rbx+20h]
0x180005fa0  movups  [rbp+8B0h+var_928], xmm0
0x180005fa4  movups  xmm0, xmmword ptr [rbx+50h]
0x180005fa8  movups  [rsp+9B0h+var_940+8], xmm1
0x180005fad  movups  xmm1, xmmword ptr [rbx+40h]
0x180005fb1  movups  [rbp+8B0h+var_908], xmm0
0x180005fb5  movups  xmm0, xmmword ptr [rbx+70h]
0x180005fb9  movups  [rbp+8B0h+var_918], xmm1
0x180005fbd  movups  xmm1, xmmword ptr [rbx+60h]
0x180005fc1  movups  [rbp+8B0h+var_8E8], xmm0
0x180005fc5  movups  [rbp+8B0h+var_8F8], xmm1
0x180005fc9  jmp     loc_1800061C2
0x180005fce  test    cs:byte_1800CF404, 10h
0x180005fd5  jz      loc_18000613D
0x180005fdb  movzx   eax, byte ptr [rbx+8]
0x180005fdf  lea     rdx, aDdmadminserver_10; "DDMAdminServerSetInfoEx: Invalid Versio"...
0x180005fe6  movzx   r9d, byte ptr [rbx+9]
0x180005feb  mov     r8d, ecx
0x180005fee  lea     rcx, [rbp+8B0h+var_830]
0x180005ff5  mov     [rsp+9B0h+var_990], eax
0x180005ff9  mov     word ptr [rbp+8B0h+var_830], r12w
0x180006001  call    FormatRRASErrorString
0x180006006  test    cs:byte_1800CF404, 10h
0x18000600d  jz      loc_18000613D
0x180006013  lea     rcx, [rbp+8B0h+var_830]
0x18000601a  mov     rax, rsi
0x18000601d  inc     rax
0x180006020  cmp     [rcx+rax*2], r12w
0x180006025  jnz     short loc_18000601D
0x180006027  jmp     loc_180006102
0x18000602c  movzx   ecx, word ptr [rbx+0Ah]
0x180006030  mov     eax, 90h
0x180006035  cmp     cx, ax
0x180006038  jb      short loc_1800060AD
0x18000603a  cmp     byte ptr [rbx+9], 3
0x18000603e  jnz     short loc_1800060AD
0x180006040  mov     al, [rbx+8]
0x180006043  cmp     al, dl
0x180006045  jnz     short loc_1800060AD
0x180006047  movups  xmm1, xmmword ptr [rbx+80h]
0x18000604e  mov     byte ptr [rsp+9B0h+var_950], al
0x180006052  movups  xmm0, xmmword ptr [rbx+70h]
0x180006056  mov     eax, [rbx+0Ch]
0x180006059  movups  [rbp+8B0h+var_888], xmm1
0x18000605d  mov     dword ptr [rsp+9B0h+var_950+4], eax
0x180006061  movups  xmm1, xmmword ptr [rbx+10h]
0x180006065  mov     rax, [rbx+60h]
0x180006069  movups  [rbp+8B0h+var_898], xmm0
0x18000606d  mov     [rbp+8B0h+var_8D0], rax
0x180006071  movsd   xmm0, qword ptr [rbx+90h]
0x180006079  mov     rax, [rbx+68h]
0x18000607d  movups  [rsp+9B0h+var_950+8], xmm1
0x180006082  movups  xmm1, xmmword ptr [rbx+30h]
0x180006086  movsd   [rbp+8B0h+var_878], xmm0
0x18000608b  movups  xmm0, xmmword ptr [rbx+20h]
0x18000608f  movups  [rbp+8B0h+var_928], xmm1
0x180006093  movups  xmm1, xmmword ptr [rbx+50h]
0x180006097  movups  [rsp+9B0h+var_940+8], xmm0
0x18000609c  movups  xmm0, xmmword ptr [rbx+40h]
0x1800060a0  movups  [rbp+8B0h+var_908], xmm1
0x1800060a4  movups  [rbp+8B0h+var_918], xmm0
0x1800060a8  jmp     loc_1800061B4
0x1800060ad  test    cs:byte_1800CF404, 10h
0x1800060b4  jz      loc_18000613D
0x1800060ba  movzx   eax, byte ptr [rbx+8]
0x1800060be  lea     rdx, aDdmadminserver_10; "DDMAdminServerSetInfoEx: Invalid Versio"...
0x1800060c5  movzx   r9d, byte ptr [rbx+9]
0x1800060ca  mov     r8d, ecx
0x1800060cd  lea     rcx, [rbp+8B0h+var_830]
0x1800060d4  mov     [rsp+9B0h+var_990], eax
0x1800060d8  mov     word ptr [rbp+8B0h+var_830], r12w
0x1800060e0  call    FormatRRASErrorString
0x1800060e5  test    cs:byte_1800CF404, 10h
0x1800060ec  jz      short loc_18000613D
0x1800060ee  lea     rcx, [rbp+8B0h+var_830]
0x1800060f5  mov     rax, rsi
0x1800060f8  inc     rax
0x1800060fb  cmp     [rcx+rax*2], r12w
0x180006100  jnz     short loc_1800060F8
0x180006102  mov     r9d, 2
0x180006108  lea     eax, ds:2[rax*2]
0x18000610f  mov     [rbp+8B0h+var_83C], r12d
0x180006113  lea     rcx, [rbp+8B0h+var_830]
0x18000611a  mov     [rbp+8B0h+var_840], eax
0x18000611d  lea     rax, [rbp+8B0h+var_858]
0x180006121  mov     [rbp+8B0h+var_848], rcx
0x180006125  lea     rdx, RasDdmTraceInfo
0x18000612c  mov     qword ptr [rsp+9B0h+var_990], rax
0x180006131  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006138  call    McGenEventWrite_EventWriteTransfer
0x18000613d  mov     ebx, 57h ; 'W'
0x180006142  jmp     loc_18000625D
0x180006147  movzx   ecx, word ptr [rbx+0Ah]
0x18000614b  cmp     ecx, 70h ; 'p'
0x18000614e  jb      loc_180006D60
0x180006154  cmp     byte ptr [rbx+9], 3
  ... truncated ...
```
