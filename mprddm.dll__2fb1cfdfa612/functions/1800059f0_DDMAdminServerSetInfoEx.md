# DDMAdminServerSetInfoEx

- ea: `0x1800059f0`
- end: `0x180006d95`
- name: `DDMAdminServerSetInfoEx`
- size: `5029`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800059f0`
- `0x180007b7c`
- `0x180020098`
- `0x180071cec`
- `0x1800736f8`
- `0x18007374c`
- `0x180073a40`
- `0x180074028`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000685a`
- `KERNEL32!HeapAlloc` at `0x18000685a`
- `KERNEL32!LeaveCriticalSection` at `0x18000622e`
- `KERNEL32!LeaveCriticalSection` at `0x18000622e`
- `KERNEL32!EnterCriticalSection` at `0x180005aad`
- `KERNEL32!EnterCriticalSection` at `0x180005aad`
- `KERNEL32!HeapFree` at `0x1800062d2`
- `KERNEL32!HeapFree` at `0x1800062d2`
- `ADVAPI32!RegCloseKey` at `0x1800069e3`
- `ADVAPI32!RegCloseKey` at `0x180006a9b`
- `ADVAPI32!RegCloseKey` at `0x1800069e3`
- `ADVAPI32!RegCloseKey` at `0x180006a9b`
- `rasman!RasGetDeviceConfigInfo` at `0x180005a2a`
- `rasman!RasSetDeviceConfigInfo` at `0x180005a58`
- `sstpcfg!SetSstpConfiguration` at `0x1800068fd`
- `sstpcfg!SetSstpConfiguration` at `0x1800068fd`

## string_xrefs

- `0x180006b90`: `DDMAdminServerSetInfoEx:SetSstpConfiguration: unsupported HASH type. error %d`
- `0x180006928`: `DDMAdminServerSetInfoEx:SetSstpConfiguration: Failed. error %d`
- `0x180006c1f`: `DDMAdminServerSetInfoEx:OpenL2tpConfigKey: Failed. error %d`
- `0x180006a0c`: `DDMAdminServerSetInfoEx:SetL2tpConfigParams: Failed. error %d`
- `0x180006d02`: `DDMAdminServerSetInfoEx:OpenIkev2ConfigKey: Failed. error %d`
- `0x180006c6c`: `DDMAdminServerSetInfoEx:SetIkev2ConfigParams: Failed. error %d`

## pseudocode

```c
__int64 __fastcall DDMAdminServerSetInfoEx(char *a1)
{
  __int64 (__fastcall *v1)(int, int, int, int, void *); // r14
  int v2; // r12d
  __int64 (__fastcall *v4)(__int64, unsigned int, unsigned int, __int64); // rcx
  char *v5; // r15
  char v6; // di
  char v7; // r13
  char v8; // dl
  __int64 v9; // rsi
  unsigned int v10; // ecx
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  int v13; // eax
  __int128 v14; // xmm1
  __int64 v15; // rax
  __int128 v16; // xmm1
  __int64 v17; // rax
  __int64 v18; // r9
  __int64 v19; // r8
  __int64 v20; // rax
  unsigned int v21; // ecx
  __int128 v22; // xmm1
  int v23; // eax
  __int128 v24; // xmm1
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int64 v27; // r9
  unsigned int v28; // ecx
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int64 v31; // rax
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int64 v34; // rax
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int64 v38; // r9
  unsigned int v39; // ecx
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  int v42; // eax
  __int128 v43; // xmm0
  int v44; // eax
  __int128 v45; // xmm1
  __int64 v46; // rax
  __int128 v47; // xmm0
  __int64 v48; // r9
  unsigned int v49; // ebx
  unsigned int v50; // ecx
  __int64 v51; // xmm0_8
  unsigned int v52; // eax
  __int64 v53; // r8
  __int64 v54; // rax
  __int64 v56; // r9
  unsigned int v57; // ecx
  unsigned int v58; // ebx
  __int64 v59; // r8
  __int64 v60; // rax
  unsigned int v61; // eax
  char *v62; // rax
  __int64 v63; // rcx
  unsigned int v64; // r8d
  char v65; // dl
  char *v66; // r13
  int v67; // eax
  unsigned int v68; // r14d
  char v69; // r15
  unsigned int v70; // eax
  __int64 v71; // r8
  __int64 v72; // rax
  unsigned int v73; // eax
  unsigned int v74; // eax
  int v75; // ecx
  int v76; // edx
  __int64 v77; // r8
  __int64 v78; // rax
  __int64 v79; // r9
  int v80; // [rsp+20h] [rbp-E0h]
  int v81; // [rsp+20h] [rbp-E0h]
  int v82; // [rsp+20h] [rbp-E0h]
  int v83; // [rsp+20h] [rbp-E0h]
  int v84; // [rsp+20h] [rbp-E0h]
  char v85; // [rsp+30h] [rbp-D0h]
  char v86; // [rsp+31h] [rbp-CFh]
  char *v87; // [rsp+38h] [rbp-C8h]
  unsigned int v88; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int dwBytes; // [rsp+44h] [rbp-BCh] BYREF
  int dwBytes_4; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v92; // [rsp+60h] [rbp-A0h] BYREF
  char v93; // [rsp+61h] [rbp-9Fh]
  __int16 v94; // [rsp+62h] [rbp-9Eh]
  int v95; // [rsp+64h] [rbp-9Ch]
  __int128 v96; // [rsp+68h] [rbp-98h]
  __int128 v97; // [rsp+78h] [rbp-88h] BYREF
  __int128 v98; // [rsp+88h] [rbp-78h]
  __int128 v99; // [rsp+98h] [rbp-68h]
  __int128 v100; // [rsp+A8h] [rbp-58h]
  __int128 v101; // [rsp+B8h] [rbp-48h]
  __int128 v102; // [rsp+C8h] [rbp-38h]
  __int64 v103; // [rsp+D8h] [rbp-28h]
  __int64 v104; // [rsp+E0h] [rbp-20h]
  __int64 v105; // [rsp+E8h] [rbp-18h]
  int v106; // [rsp+F0h] [rbp-10h]
  int v107; // [rsp+F4h] [rbp-Ch]
  int v108; // [rsp+F8h] [rbp-8h] BYREF
  int v109; // [rsp+FCh] [rbp-4h]
  int v110; // [rsp+100h] [rbp+0h]
  int v111; // [rsp+104h] [rbp+4h]
  __int128 v112; // [rsp+108h] [rbp+8h]
  unsigned int v113; // [rsp+118h] [rbp+18h]
  unsigned int v114; // [rsp+11Ch] [rbp+1Ch]
  unsigned int v115; // [rsp+120h] [rbp+20h]
  int v116; // [rsp+124h] [rbp+24h]
  __int64 v117; // [rsp+128h] [rbp+28h]
  int v118; // [rsp+130h] [rbp+30h]
  int v119; // [rsp+134h] [rbp+34h]
  __int64 v120; // [rsp+138h] [rbp+38h]
  __int64 v121; // [rsp+140h] [rbp+40h]
  unsigned int v122; // [rsp+150h] [rbp+50h] BYREF
  __int64 (__fastcall *v123)(__int64, unsigned int, unsigned int, __int64); // [rsp+158h] [rbp+58h]
  _BYTE v124[16]; // [rsp+160h] [rbp+60h] BYREF
  int *v125; // [rsp+170h] [rbp+70h]
  int v126; // [rsp+178h] [rbp+78h]
  int v127; // [rsp+17Ch] [rbp+7Ch]
  int v128; // [rsp+180h] [rbp+80h] BYREF
  char v129[2044]; // [rsp+184h] [rbp+84h] BYREF

  v1 = (__int64 (__fastcall *)(int, int, int, int, void *))RasGetDeviceConfigInfo;
  v2 = 0;
  v85 = 0;
  v86 = 0;
  dwBytes_4 = 0;
  if ( dword_1800C8654 )
    v1 = DdmGetDeviceConfigInfo;
  v88 = 0;
  v4 = (__int64 (__fastcall *)(__int64, unsigned int, unsigned int, __int64))RasSetDeviceConfigInfo;
  if ( dword_1800C8654 )
    v4 = DdmSetDeviceConfigInfo;
  dwBytes = 0;
  v123 = v4;
  v122 = 0;
  v5 = 0;
  v128 = 0;
  v6 = 0;
  v7 = 0;
  memset_0(v129, 0, sizeof(v129));
  memset_0(&v92, 0, 0xE8u);
  EnterCriticalSection(&gblDeviceTable);
  v8 = *a1;
  v9 = -1;
  switch ( *a1 )
  {
    case 1:
      v50 = *((unsigned __int16 *)a1 + 5);
      if ( v50 >= 0x70 && a1[9] == 3 && a1[8] == v8 )
      {
        v51 = *(_QWORD *)(a1 + 52);
        v92 = a1[8];
        v95 = *((_DWORD *)a1 + 3);
        v104 = *((_QWORD *)a1 + 8);
        v105 = *((_QWORD *)a1 + 9);
        v113 = *((_DWORD *)a1 + 20);
        v114 = *((_DWORD *)a1 + 21);
        v115 = *((_DWORD *)a1 + 22);
        v116 = *((_DWORD *)a1 + 23);
        v117 = *((_QWORD *)a1 + 12);
        v118 = *((_DWORD *)a1 + 26);
        v119 = *((_DWORD *)a1 + 27);
        v120 = *((_QWORD *)a1 + 14);
        v96 = *((_OWORD *)a1 + 1);
        v97 = *((_OWORD *)a1 + 2);
        LODWORD(v98) = *((_DWORD *)a1 + 12);
        HIDWORD(v98) = *((_DWORD *)a1 + 15);
        v93 = 3;
        v94 = v50;
        *(_QWORD *)((char *)&v98 + 4) = v51;
        goto LABEL_52;
      }
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v79 = (unsigned __int8)a1[9];
      v84 = (unsigned __int8)a1[8];
      LOWORD(v128) = 0;
      FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: Invalid Version %d/type%d/size %d", v50, v79, v84);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v129[2 * v20 - 4] );
      goto LABEL_46;
    case 2:
      v39 = *((unsigned __int16 *)a1 + 5);
      if ( (unsigned __int16)v39 >= 0x90u && a1[9] == 3 && a1[8] == v8 )
      {
        v40 = *((_OWORD *)a1 + 1);
        v92 = a1[8];
        v41 = *((_OWORD *)a1 + 2);
        v95 = *((_DWORD *)a1 + 3);
        v104 = *((_QWORD *)a1 + 12);
        v105 = *((_QWORD *)a1 + 13);
        v113 = *((_DWORD *)a1 + 28);
        v114 = *((_DWORD *)a1 + 29);
        v115 = *((_DWORD *)a1 + 30);
        v116 = *((_DWORD *)a1 + 31);
        v117 = *((_QWORD *)a1 + 16);
        v42 = *((_DWORD *)a1 + 34);
        v96 = v40;
        v118 = v42;
        v43 = *((_OWORD *)a1 + 3);
        v44 = *((_DWORD *)a1 + 35);
        v97 = v41;
        v119 = v44;
        v45 = *((_OWORD *)a1 + 4);
        v46 = *((_QWORD *)a1 + 18);
        v98 = v43;
        v120 = v46;
        v47 = *((_OWORD *)a1 + 5);
        v93 = 3;
        v94 = v39;
        v99 = v45;
        v100 = v47;
        goto LABEL_52;
      }
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v48 = (unsigned __int8)a1[9];
      v83 = (unsigned __int8)a1[8];
      LOWORD(v128) = 0;
      FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: Invalid Version %d/type%d/size %d", v39, v48, v83);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v129[2 * v20 - 4] );
      goto LABEL_46;
    case 3:
      v28 = *((unsigned __int16 *)a1 + 5);
      if ( (unsigned __int16)v28 >= 0xD0u && a1[9] == 3 && a1[8] == v8 )
      {
        v29 = *((_OWORD *)a1 + 1);
        v92 = a1[8];
        v30 = *((_OWORD *)a1 + 2);
        v95 = *((_DWORD *)a1 + 3);
        v104 = *((_QWORD *)a1 + 16);
        v105 = *((_QWORD *)a1 + 17);
        v106 = *((_DWORD *)a1 + 36);
        v107 = *((_DWORD *)a1 + 37);
        v108 = *((_DWORD *)a1 + 38);
        v109 = *((_DWORD *)a1 + 39);
        v110 = *((_DWORD *)a1 + 40);
        v111 = *((_DWORD *)a1 + 41);
        *(_QWORD *)&v112 = *((_QWORD *)a1 + 21);
        v113 = *((_DWORD *)a1 + 44);
        v114 = *((_DWORD *)a1 + 45);
        v115 = *((_DWORD *)a1 + 46);
        v116 = *((_DWORD *)a1 + 47);
        v31 = *((_QWORD *)a1 + 24);
        v96 = v29;
        v117 = v31;
        v32 = *((_OWORD *)a1 + 3);
        v118 = *((_DWORD *)a1 + 50);
        LODWORD(v31) = *((_DWORD *)a1 + 51);
        v97 = v30;
        v119 = v31;
        v33 = *((_OWORD *)a1 + 4);
        v34 = *((_QWORD *)a1 + 26);
        v98 = v32;
        v120 = v34;
        v35 = *((_OWORD *)a1 + 5);
        v93 = 3;
        v99 = v33;
        v94 = v28;
        v36 = *((_OWORD *)a1 + 6);
        v100 = v35;
        v37 = *((_OWORD *)a1 + 7);
        v101 = v36;
        v102 = v37;
        goto LABEL_52;
      }
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v38 = (unsigned __int8)a1[9];
      v82 = (unsigned __int8)a1[8];
      LOWORD(v128) = 0;
      FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: Invalid Version %d/type%d/size %d", v28, v38, v82);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v129[2 * v20 - 4] );
      goto LABEL_46;
    case 4:
      v21 = *((unsigned __int16 *)a1 + 5);
      if ( (unsigned __int16)v21 >= 0xD8u && a1[9] == 3 && a1[8] == v8 )
      {
        v22 = *((_OWORD *)a1 + 2);
        v92 = a1[8];
        v95 = *((_DWORD *)a1 + 3);
        v104 = *((_QWORD *)a1 + 16);
        v105 = *((_QWORD *)a1 + 17);
        v106 = *((_DWORD *)a1 + 36);
        v107 = *((_DWORD *)a1 + 37);
        v108 = *((_DWORD *)a1 + 38);
        v109 = *((_DWORD *)a1 + 39);
        v110 = *((_DWORD *)a1 + 40);
        v111 = *((_DWORD *)a1 + 41);
        *(_QWORD *)&v112 = *((_QWORD *)a1 + 21);
        v113 = *((_DWORD *)a1 + 44);
        v114 = *((_DWORD *)a1 + 45);
        v115 = *((_DWORD *)a1 + 46);
        v116 = *((_DWORD *)a1 + 47);
        v117 = *((_QWORD *)a1 + 24);
        v118 = *((_DWORD *)a1 + 50);
        v23 = *((_DWORD *)a1 + 51);
        v97 = v22;
        v119 = v23;
        v24 = *((_OWORD *)a1 + 4);
        v120 = *((_QWORD *)a1 + 26);
        v17 = *((_QWORD *)a1 + 27);
        v99 = v24;
        v93 = 3;
        v25 = *((_OWORD *)a1 + 6);
        v94 = v21;
        v101 = v25;
        goto LABEL_23;
      }
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v27 = (unsigned __int8)a1[9];
      v81 = (unsigned __int8)a1[8];
      LOWORD(v128) = 0;
      FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: Invalid Version %d/type%d/size %d", v21, v27, v81);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v129[2 * v20 - 4] );
LABEL_46:
      v127 = 0;
      v126 = 2 * v20 + 2;
      v125 = &v128;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v19, 2, v124);
      goto LABEL_47;
  }
  if ( *a1 != 5 )
  {
LABEL_47:
    v49 = 87;
    goto LABEL_59;
  }
  v10 = *((unsigned __int16 *)a1 + 5);
  if ( (unsigned __int16)v10 < 0xE8u || a1[9] != 3 || a1[8] != v8 )
  {
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_47;
    v18 = (unsigned __int8)a1[9];
    v80 = (unsigned __int8)a1[8];
    LOWORD(v128) = 0;
    FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: Invalid Version %d/type%d/size %d", v10, v18, v80);
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_47;
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)&v129[2 * v20 - 4] );
    goto LABEL_46;
  }
  v11 = *((_OWORD *)a1 + 2);
  v92 = a1[8];
  v12 = *((_OWORD *)a1 + 11);
  v95 = *((_DWORD *)a1 + 3);
  v104 = *((_QWORD *)a1 + 17);
  v105 = *((_QWORD *)a1 + 18);
  v106 = *((_DWORD *)a1 + 38);
  v107 = *((_DWORD *)a1 + 39);
  v108 = *((_DWORD *)a1 + 40);
  v109 = *((_DWORD *)a1 + 41);
  v110 = *((_DWORD *)a1 + 42);
  v111 = *((_DWORD *)a1 + 43);
  v113 = *((_DWORD *)a1 + 48);
  v114 = *((_DWORD *)a1 + 49);
  v115 = *((_DWORD *)a1 + 50);
  v116 = *((_DWORD *)a1 + 51);
  v117 = *((_QWORD *)a1 + 26);
  v13 = *((_DWORD *)a1 + 54);
  v97 = v11;
  v118 = v13;
  v14 = *((_OWORD *)a1 + 4);
  v119 = *((_DWORD *)a1 + 55);
  v15 = *((_QWORD *)a1 + 28);
  v99 = v14;
  v120 = v15;
  v16 = *((_OWORD *)a1 + 6);
  v17 = *((_QWORD *)a1 + 29);
  v93 = 3;
  v101 = v16;
  v94 = v10;
  *(_QWORD *)&v16 = *((_QWORD *)a1 + 16);
  v112 = v12;
  v103 = v16;
LABEL_23:
  v26 = *((_OWORD *)a1 + 1);
  v121 = v17;
  v96 = v26;
  v98 = *((_OWORD *)a1 + 3);
  v100 = *((_OWORD *)a1 + 5);
  v102 = *((_OWORD *)a1 + 7);
LABEL_52:
  v52 = DDMGetRestrictedPortCount(&v122);
  v49 = v52;
  if ( v52 )
  {
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_58;
    LOWORD(v128) = 0;
    FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: DDMGetRestrictedPortCount Failed with %d", v52);
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_58;
    v54 = -1;
    do
      ++v54;
    while ( *(_WORD *)&v129[2 * v54 - 4] );
    goto LABEL_57;
  }
  v56 = v122;
  if ( v122 == -1 )
  {
    v57 = 30000;
    v56 = 0x4000;
    v58 = 30000;
  }
  else
  {
    v58 = 0;
    v57 = v122;
  }
  if ( (v95 & 1) != 0 )
  {
    if ( (unsigned int)v104 > (unsigned int)v56 )
    {
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      LOWORD(v128) = 0;
      FormatRRASErrorString(
        &v128,
        L"DDMAdminServerSetInfoEx: Number of PPTP ports %d are exceeding Max Number of ports %d");
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v129[2 * v20 - 4] );
      goto LABEL_46;
    }
    if ( (v104 & 0xFFFFFFFC00000000uLL) != 0 )
    {
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      LOWORD(v128) = 0;
      FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: Invalid PPTP port flags %d ");
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v129[2 * v20 - 4] );
      goto LABEL_46;
    }
  }
  if ( (v95 & 2) != 0 )
  {
    if ( (unsigned int)v105 > v57 )
    {
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      LOWORD(v128) = 0;
      FormatRRASErrorString(
        &v128,
        L"DDMAdminServerSetInfoEx: Number of L2TP ports %d are exceeding Max Number of ports %d",
        (unsigned int)v105,
        v56);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v129[2 * v20 - 4] );
      goto LABEL_46;
    }
    if ( (v105 & 0xFFFFFFFC00000000uLL) != 0 )
    {
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      LOWORD(v128) = 0;
      FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: Invalid L2TP port flags %d ", HIDWORD(v105), v56);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v129[2 * v20 - 4] );
      goto LABEL_46;
    }
    if ( (v106 & 1) != 0
      && (unsigned __int8)(v92 - 3) <= 2u
      && (v108 < 300 || v110 < 300 || v111 < 1024 || (int)v97 > 172799 || SDWORD2(v97) > 172799) )
    {
      v49 = 87;
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_58;
      LOWORD(v128) = 0;
      FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: ValidateL2tpParams failed : %d", 87, v56);
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_58;
      v54 = -1;
      do
        ++v54;
      while ( *(_WORD *)&v129[2 * v54 - 4] );
LABEL_57:
      v127 = 0;
      v126 = 2 * v54 + 2;
      v125 = &v128;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v53, 2, v124);
LABEL_58:
      v6 = 0;
      goto LABEL_59;
    }
  }
  if ( (v95 & 4) != 0 )
  {
    if ( v113 > v57 )
    {
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      LOWORD(v128) = 0;
      FormatRRASErrorString(
        &v128,
        L"DDMAdminServerSetInfoEx: Number of SSTP ports %d are exceeding Max Number of ports %d",
        v113,
        v56);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v129[2 * v20 - 4] );
      goto LABEL_46;
    }
    if ( (v114 & 0xFFFFFFFC) != 0 )
    {
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      LOWORD(v128) = 0;
      FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: Invalid SSTP port flags %d ", v114, v56);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_47;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v129[2 * v20 - 4] );
      goto LABEL_46;
    }
  }
  if ( (v95 & 8) != 0 )
  {
    if ( (unsigned int)v96 > v57 )
    {
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_132;
      LOWORD(v128) = 0;
      FormatRRASErrorString(
        &v128,
        L"DDMAdminServerSetInfoEx: Number of IKEV2 ports %d are exceeding Max Number of ports %d",
        (unsigned int)v96,
        v56);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_132;
      v60 = -1;
      do
        ++v60;
      while ( *(_WORD *)&v129[2 * v60 - 4] );
LABEL_131:
      v127 = 0;
      v126 = 2 * v60 + 2;
      v125 = &v128;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v59, 2, v124);
LABEL_132:
      v49 = 87;
      goto LABEL_58;
    }
    if ( (DWORD1(v96) & 0xFFFFFFFC) != 0 )
    {
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_132;
      LOWORD(v128) = 0;
      FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: Invalid IKEv2 port flags %d ", DWORD1(v96), v56);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_132;
      v60 = -1;
      do
        ++v60;
      while ( *(_WORD *)&v129[2 * v60 - 4] );
      goto LABEL_131;
    }
    if ( (BYTE8(v96) & 1) != 0
      && ((int)v97 < 300
       || SDWORD1(v97) < 120
       || SDWORD2(v97) < 300
       || (int)v103 < 300
       || SHIDWORD(v97) < 1024
       || (int)v97 > 172799
       || SDWORD2(v97) > 172799
       || (int)v103 > 172799
       || (_DWORD)v98) )
    {
      goto LABEL_132;
    }
  }
  if ( (v95 & 0x10) != 0 )
  {
    if ( (unsigned int)v121 > v58 )
    {
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_132;
      LOWORD(v128) = 0;
      FormatRRASErrorString(
        &v128,
        L"DDMAdminServerSetInfoEx: Number of GRE ports %d are exceeding Max Number of ports %d",
        (unsigned int)v121,
        v58);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_132;
      v60 = -1;
      do
        ++v60;
      while ( *(_WORD *)&v129[2 * v60 - 4] );
      goto LABEL_131;
    }
    if ( (v121 & 0xFFFFFFFC00000000uLL) != 0 )
    {
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_132;
      LOWORD(v128) = 0;
      FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: Invalid GRE port flags %d ", HIDWORD(v121), v56);
      if ( (byte_1800C8404 & 0x10) == 0 )
        goto LABEL_132;
      v60 = -1;
      do
        ++v60;
      while ( *(_WORD *)&v129[2 * v60 - 4] );
      goto LABEL_131;
    }
  }
  dwBytes_4 = 6;
  v61 = v1(0, (int)&dwBytes_4, (int)&v88, (int)&dwBytes, 0);
  v49 = v61;
  if ( !v61 )
  {
    v49 = 4319;
    goto LABEL_58;
  }
  if ( v61 != 603 )
    goto LABEL_58;
  v62 = (char *)HeapAlloc(hHeap, 8u, dwBytes);
  v87 = v62;
  v5 = v62;
  if ( !v62 )
  {
    v49 = 8;
    goto LABEL_58;
  }
  v49 = v1(0, (int)&dwBytes_4, (int)&v88, (int)&dwBytes, v62);
  if ( v49 )
    goto LABEL_58;
  v64 = v88;
  if ( !v88 )
    goto LABEL_58;
  v65 = v95;
  while ( 1 )
  {
    v66 = &v5[472 * v2];
    v67 = (unsigned __int16)*((_DWORD *)v66 + 12);
    if ( v67 == 14 )
      break;
    switch ( v67 )
    {
      case 8:
        if ( (v65 & 1) == 0 )
          goto LABEL_210;
        v68 = v104;
        v69 = BYTE4(v104);
        goto LABEL_202;
      case 9:
        if ( (v65 & 2) == 0 )
          goto LABEL_210;
        v68 = v105;
        v69 = BYTE4(v105);
        if ( (v106 & 1) == 0 || (unsigned __int8)(v92 - 3) > 2u )
          goto LABEL_202;
        hKey[0] = 0;
        v73 = OpenL2tpConfigKey(v63, hKey);
        v49 = v73;
        if ( v73 )
        {
          if ( (byte_1800C8404 & 8) != 0 )
          {
            LOWORD(v128) = 0;
            FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx:OpenL2tpConfigKey: Failed. error %d", v73);
            if ( (byte_1800C8404 & 8) != 0 )
            {
              v72 = -1;
              do
                ++v72;
              while ( *(_WORD *)&v129[2 * v72 - 4] );
              goto LABEL_226;
            }
          }
          goto LABEL_227;
        }
        v49 = SetL2tpConfigParams(hKey[0], v92, (__int64)&v108);
        RegCloseKey(hKey[0]);
        if ( v49 )
        {
          if ( (byte_1800C8404 & 8) != 0 )
          {
            LOWORD(v128) = 0;
            FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx:SetL2tpConfigParams: Failed. error %d", v49);
            if ( (byte_1800C8404 & 8) != 0 )
            {
              v72 = -1;
              do
                ++v72;
              while ( *(_WORD *)&v129[2 * v72 - 4] );
              goto LABEL_226;
            }
          }
          goto LABEL_227;
        }
        break;
      case 15:
        if ( (v65 & 8) == 0 )
          goto LABEL_210;
        v68 = v96;
        v69 = BYTE4(v96);
        if ( (BYTE8(v96) & 1) == 0 )
          goto LABEL_202;
        hKey[0] = 0;
        v74 = OpenIkev2ConfigKey(v63, hKey);
        v49 = v74;
        if ( v74 )
        {
          if ( (byte_1800C8404 & 8) != 0 )
          {
            LOWORD(v128) = 0;
            FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx:OpenIkev2ConfigKey: Failed. error %d", v74);
            if ( (byte_1800C8404 & 8) != 0 )
            {
              v72 = -1;
              do
                ++v72;
              while ( *(_WORD *)&v129[2 * v72 - 4] );
LABEL_226:
              v127 = 0;
              v126 = 2 * v72 + 2;
              v125 = &v128;
              McGenEventWrite_EventWriteTransfer(
                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                RasDdmTraceError,
                v71,
                2,
                v124);
            }
          }
LABEL_227:
          v5 = v87;
          goto LABEL_228;
        }
        v49 = SetIkev2ConfigParams(hKey[0], v92, (__int64)&v97);
        RegCloseKey(hKey[0]);
        if ( v49 )
        {
          if ( (byte_1800C8404 & 8) != 0 )
          {
            LOWORD(v128) = 0;
            FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx:SetIkev2ConfigParams: Failed. error %d", v49);
            if ( (byte_1800C8404 & 8) != 0 )
            {
              v72 = -1;
              do
                ++v72;
              while ( *(_WORD *)&v129[2 * v72 - 4] );
              goto LABEL_226;
            }
          }
          goto LABEL_227;
        }
        break;
      default:
        if ( v67 != 16 || (v65 & 0x10) == 0 )
          goto LABEL_210;
        v68 = v121;
        v69 = BYTE4(v121);
        goto LABEL_202;
    }
LABEL_198:
    v85 = 1;
LABEL_202:
    if ( v68 > *((_DWORD *)v66 + 11) )
      *((_DWORD *)v66 + 11) = v68;
    if ( *((_DWORD *)v66 + 7) != v68
      || (v75 = v69 & 1, *((_DWORD *)v66 + 2) != v75)
      || (v76 = v69 & 2, *((_DWORD *)v66 + 3) != (v76 != 0)) )
    {
      v86 = 1;
      v75 = v69 & 1;
      v76 = v69 & 2;
    }
    *((_DWORD *)v66 + 2) = v75;
    *((_DWORD *)v66 + 7) = v68;
    *((_DWORD *)v66 + 1) = 1;
    *((_DWORD *)v66 + 3) = v76 != 0;
    v5 = v87;
    v49 = v123(0, 1u, 472u, (__int64)v66);
    if ( v49 )
    {
LABEL_211:
      v6 = v85;
      v7 = v86;
      goto LABEL_59;
    }
    v64 = v88;
    v65 = v95;
LABEL_210:
    if ( ++v2 >= v64 )
      goto LABEL_211;
  }
  if ( (v65 & 4) == 0 )
    goto LABEL_210;
  if ( v116 == 32780 )
  {
    v68 = v113;
    v69 = v114;
    v70 = SetSstpConfiguration(0, 0, v115, v120 & -(__int64)(v118 != 0));
    v49 = v70;
    if ( v70 )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v128) = 0;
        FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx:SetSstpConfiguration: Failed. error %d", v70);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v72 = -1;
          do
            ++v72;
          while ( *(_WORD *)&v129[2 * v72 - 4] );
          goto LABEL_226;
        }
      }
      goto LABEL_227;
    }
    goto LABEL_198;
  }
  v49 = 87;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v128) = 0;
    FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx:SetSstpConfiguration: unsupported HASH type. error %d", 87);
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v78 = -1;
      do
        ++v78;
      while ( *(_WORD *)&v129[2 * v78 - 4] );
      v127 = 0;
      v126 = 2 * v78 + 2;
      v125 = &v128;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v77, 2, v124);
    }
  }
LABEL_228:
  v6 = v85;
  v7 = v86;
LABEL_59:
  LeaveCriticalSection(&gblDeviceTable);
  if ( v7 )
    ((void (*)(void))qword_1800C86A8)();
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v128) = 0;
    FormatRRASErrorString(&v128, L"DDMAdminServerSetInfoEx: done %d", v49);
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      do
        ++v9;
      while ( *(_WORD *)&v129[2 * v9 - 4] );
      v127 = 0;
      v126 = 2 * v9 + 2;
      v125 = &v128;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, &v128, 2, v124);
    }
  }
  if ( v5 )
    HeapFree(hHeap, 0, v5);
  if ( v6 && !v49 )
    return 3011;
  return v49;
}

```

## disassembly

```asm
0x1800059f0  push    rbp
0x1800059f2  push    rbx
0x1800059f3  push    rsi
0x1800059f4  push    rdi
0x1800059f5  push    r12
0x1800059f7  push    r13
0x1800059f9  push    r14
0x1800059fb  push    r15
0x1800059fd  lea     rbp, [rsp-898h]
0x180005a05  sub     rsp, 998h
0x180005a0c  mov     rax, cs:__security_cookie
0x180005a13  xor     rax, rsp
0x180005a16  mov     [rbp+8D0h+var_50], rax
0x180005a1d  mov     eax, cs:dword_1800C8654
0x180005a23  lea     rdx, DdmSetDeviceConfigInfo
0x180005a2a  mov     r14, cs:__imp_RasGetDeviceConfigInfo
0x180005a31  xor     r12d, r12d
0x180005a34  mov     rbx, rcx
0x180005a37  mov     [rsp+9D0h+var_9A0], r12b
0x180005a3c  test    eax, eax
0x180005a3e  mov     [rsp+9D0h+var_99F], r12b
0x180005a43  lea     rcx, DdmGetDeviceConfigInfo
0x180005a4a  mov     dword ptr [rsp+9D0h+dwBytes+4], r12d
0x180005a4f  cmovnz  r14, rcx
0x180005a53  mov     [rsp+9D0h+var_990], r12d
0x180005a58  mov     rcx, cs:__imp_RasSetDeviceConfigInfo
0x180005a5f  mov     r8d, 7FCh; Size
0x180005a65  cmovnz  rcx, rdx
0x180005a69  mov     dword ptr [rsp+9D0h+dwBytes], r12d
0x180005a6e  mov     [rbp+8D0h+var_878], rcx
0x180005a72  xor     edx, edx; Val
0x180005a74  lea     rcx, [rbp+8D0h+var_84C]; void *
0x180005a7b  mov     [rbp+8D0h+var_880], r12d
0x180005a7f  mov     r15d, r12d
0x180005a82  mov     [rbp+8D0h+var_850], r12d
0x180005a89  mov     dil, r12b
0x180005a8c  mov     r13b, r12b
0x180005a8f  call    memset_0
0x180005a94  xor     edx, edx; Val
0x180005a96  lea     rcx, [rsp+9D0h+var_970]; void *
0x180005a9b  mov     r8d, 0E8h; Size
0x180005aa1  call    memset_0
0x180005aa6  lea     rcx, gblDeviceTable; lpCriticalSection
0x180005aad  call    cs:__imp_EnterCriticalSection
0x180005ab3  movzx   edx, byte ptr [rbx]
0x180005ab6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005aba  mov     ecx, edx
0x180005abc  sub     ecx, 1
0x180005abf  jz      loc_1800060C6
0x180005ac5  sub     ecx, 1
0x180005ac8  jz      loc_180005F71
0x180005ace  sub     ecx, 1
0x180005ad1  jz      loc_180005DEE
0x180005ad7  sub     ecx, 1
0x180005ada  jz      loc_180005C60
0x180005ae0  cmp     ecx, 1
0x180005ae3  jnz     loc_1800060BC
0x180005ae9  movzx   ecx, word ptr [rbx+0Ah]
0x180005aed  mov     eax, 0E8h
0x180005af2  cmp     cx, ax
0x180005af5  jb      loc_180005C02
0x180005afb  cmp     byte ptr [rbx+9], 3
0x180005aff  jnz     loc_180005C02
0x180005b05  mov     al, [rbx+8]
0x180005b08  cmp     al, dl
0x180005b0a  jnz     loc_180005C02
0x180005b10  movups  xmm1, xmmword ptr [rbx+20h]
0x180005b14  mov     [rsp+9D0h+var_970], al
0x180005b18  mov     eax, [rbx+0Ch]
0x180005b1b  movups  xmm0, xmmword ptr [rbx+0B0h]
0x180005b22  mov     [rsp+9D0h+var_96C], eax
0x180005b26  mov     rax, [rbx+88h]
0x180005b2d  mov     [rbp+8D0h+var_8F0], rax
0x180005b31  mov     eax, [rbx+90h]
0x180005b37  mov     dword ptr [rbp+8D0h+var_8E8], eax
0x180005b3a  mov     eax, [rbx+94h]
0x180005b40  mov     dword ptr [rbp+8D0h+var_8E8+4], eax
0x180005b43  mov     eax, [rbx+98h]
0x180005b49  mov     [rbp+8D0h+var_8E0], eax
0x180005b4c  mov     eax, [rbx+9Ch]
0x180005b52  mov     [rbp+8D0h+var_8DC], eax
0x180005b55  mov     eax, [rbx+0A0h]
0x180005b5b  mov     [rbp+8D0h+var_8D8], eax
0x180005b5e  mov     eax, [rbx+0A4h]
0x180005b64  mov     [rbp+8D0h+var_8D4], eax
0x180005b67  mov     eax, [rbx+0A8h]
0x180005b6d  mov     [rbp+8D0h+var_8D0], eax
0x180005b70  mov     eax, [rbx+0ACh]
0x180005b76  mov     [rbp+8D0h+var_8CC], eax
0x180005b79  mov     eax, [rbx+0C0h]
0x180005b7f  mov     [rbp+8D0h+var_8B8], eax
0x180005b82  mov     eax, [rbx+0C4h]
0x180005b88  mov     [rbp+8D0h+var_8B4], eax
0x180005b8b  mov     eax, [rbx+0C8h]
0x180005b91  mov     [rbp+8D0h+var_8B0], eax
0x180005b94  mov     eax, [rbx+0CCh]
0x180005b9a  mov     [rbp+8D0h+var_8AC], eax
0x180005b9d  mov     rax, [rbx+0D0h]
0x180005ba4  mov     [rbp+8D0h+var_8A8], rax
0x180005ba8  mov     eax, [rbx+0D8h]
0x180005bae  movups  [rsp+9D0h+var_958], xmm1
0x180005bb3  mov     [rbp+8D0h+var_8A0], eax
0x180005bb6  movups  xmm1, xmmword ptr [rbx+40h]
0x180005bba  mov     eax, [rbx+0DCh]
0x180005bc0  mov     [rbp+8D0h+var_89C], eax
0x180005bc3  mov     rax, [rbx+0E0h]
0x180005bca  movups  [rbp+8D0h+var_938], xmm1
0x180005bce  mov     [rbp+8D0h+var_898], rax
0x180005bd2  movups  xmm1, xmmword ptr [rbx+60h]
0x180005bd6  mov     rax, [rbx+0E8h]
0x180005bdd  mov     [rsp+9D0h+var_96F], 3
0x180005be2  movups  [rbp+8D0h+var_918], xmm1
0x180005be6  mov     [rsp+9D0h+var_96E], cx
0x180005beb  movsd   xmm1, qword ptr [rbx+80h]
0x180005bf3  movdqu  [rbp+8D0h+var_8C8], xmm0
0x180005bf8  movsd   [rbp+8D0h+var_8F8], xmm1
0x180005bfd  jmp     loc_180005D66
0x180005c02  test    cs:byte_1800C8404, 10h
0x180005c09  jz      loc_1800060BC
0x180005c0f  movzx   eax, byte ptr [rbx+8]
0x180005c13  lea     rdx, aDdmadminserver_10; "DDMAdminServerSetInfoEx: Invalid Versio"...
0x180005c1a  movzx   r9d, byte ptr [rbx+9]
0x180005c1f  mov     r8d, ecx
0x180005c22  lea     rcx, [rbp+8D0h+var_850]
0x180005c29  mov     [rsp+9D0h+var_9B0], eax
0x180005c2d  mov     word ptr [rbp+8D0h+var_850], r12w
0x180005c35  call    FormatRRASErrorString
0x180005c3a  test    cs:byte_1800C8404, 10h
0x180005c41  jz      loc_1800060BC
0x180005c47  lea     rcx, [rbp+8D0h+var_850]
0x180005c4e  mov     rax, rsi
0x180005c51  inc     rax
0x180005c54  cmp     [rcx+rax*2], r12w
0x180005c59  jnz     short loc_180005C51
0x180005c5b  jmp     loc_180006081
0x180005c60  movzx   ecx, word ptr [rbx+0Ah]
0x180005c64  mov     eax, 0D8h
0x180005c69  cmp     cx, ax
0x180005c6c  jb      loc_180005D90
0x180005c72  cmp     byte ptr [rbx+9], 3
0x180005c76  jnz     loc_180005D90
0x180005c7c  mov     al, [rbx+8]
0x180005c7f  cmp     al, dl
0x180005c81  jnz     loc_180005D90
0x180005c87  movups  xmm1, xmmword ptr [rbx+20h]
0x180005c8b  mov     [rsp+9D0h+var_970], al
0x180005c8f  mov     eax, [rbx+0Ch]
0x180005c92  mov     [rsp+9D0h+var_96C], eax
0x180005c96  mov     rax, [rbx+80h]
0x180005c9d  mov     [rbp+8D0h+var_8F0], rax
0x180005ca1  mov     eax, [rbx+88h]
0x180005ca7  mov     dword ptr [rbp+8D0h+var_8E8], eax
0x180005caa  mov     eax, [rbx+8Ch]
0x180005cb0  mov     dword ptr [rbp+8D0h+var_8E8+4], eax
0x180005cb3  mov     eax, [rbx+90h]
0x180005cb9  mov     [rbp+8D0h+var_8E0], eax
0x180005cbc  mov     eax, [rbx+94h]
0x180005cc2  mov     [rbp+8D0h+var_8DC], eax
0x180005cc5  mov     eax, [rbx+98h]
0x180005ccb  mov     [rbp+8D0h+var_8D8], eax
0x180005cce  mov     eax, [rbx+9Ch]
0x180005cd4  mov     [rbp+8D0h+var_8D4], eax
0x180005cd7  mov     eax, [rbx+0A0h]
0x180005cdd  mov     [rbp+8D0h+var_8D0], eax
0x180005ce0  mov     eax, [rbx+0A4h]
0x180005ce6  mov     [rbp+8D0h+var_8CC], eax
0x180005ce9  mov     rax, [rbx+0A8h]
0x180005cf0  mov     qword ptr [rbp+8D0h+var_8C8], rax
0x180005cf4  mov     eax, [rbx+0B0h]
0x180005cfa  mov     [rbp+8D0h+var_8B8], eax
0x180005cfd  mov     eax, [rbx+0B4h]
0x180005d03  mov     [rbp+8D0h+var_8B4], eax
0x180005d06  mov     eax, [rbx+0B8h]
0x180005d0c  mov     [rbp+8D0h+var_8B0], eax
0x180005d0f  mov     eax, [rbx+0BCh]
0x180005d15  mov     [rbp+8D0h+var_8AC], eax
0x180005d18  mov     rax, [rbx+0C0h]
0x180005d1f  mov     [rbp+8D0h+var_8A8], rax
0x180005d23  mov     eax, [rbx+0C8h]
0x180005d29  mov     [rbp+8D0h+var_8A0], eax
0x180005d2c  mov     eax, [rbx+0CCh]
0x180005d32  movups  [rsp+9D0h+var_958], xmm1
0x180005d37  mov     [rbp+8D0h+var_89C], eax
0x180005d3a  movups  xmm1, xmmword ptr [rbx+40h]
0x180005d3e  mov     rax, [rbx+0D0h]
0x180005d45  mov     [rbp+8D0h+var_898], rax
0x180005d49  mov     rax, [rbx+0D8h]
0x180005d50  movups  [rbp+8D0h+var_938], xmm1
0x180005d54  mov     [rsp+9D0h+var_96F], 3
0x180005d59  movups  xmm1, xmmword ptr [rbx+60h]
0x180005d5d  mov     [rsp+9D0h+var_96E], cx
0x180005d62  movups  [rbp+8D0h+var_918], xmm1
0x180005d66  movups  xmm0, xmmword ptr [rbx+10h]
0x180005d6a  mov     [rbp+8D0h+var_890], rax
0x180005d6e  movups  [rsp+9D0h+var_968], xmm0
0x180005d73  movups  xmm0, xmmword ptr [rbx+30h]
0x180005d77  movups  [rbp+8D0h+var_948], xmm0
0x180005d7b  movups  xmm0, xmmword ptr [rbx+50h]
0x180005d7f  movups  [rbp+8D0h+var_928], xmm0
0x180005d83  movups  xmm0, xmmword ptr [rbx+70h]
0x180005d87  movups  [rbp+8D0h+var_908], xmm0
0x180005d8b  jmp     loc_18000618D
0x180005d90  test    cs:byte_1800C8404, 10h
0x180005d97  jz      loc_1800060BC
0x180005d9d  movzx   eax, byte ptr [rbx+8]
0x180005da1  lea     rdx, aDdmadminserver_10; "DDMAdminServerSetInfoEx: Invalid Versio"...
0x180005da8  movzx   r9d, byte ptr [rbx+9]
0x180005dad  mov     r8d, ecx
0x180005db0  lea     rcx, [rbp+8D0h+var_850]
0x180005db7  mov     [rsp+9D0h+var_9B0], eax
0x180005dbb  mov     word ptr [rbp+8D0h+var_850], r12w
0x180005dc3  call    FormatRRASErrorString
0x180005dc8  test    cs:byte_1800C8404, 10h
0x180005dcf  jz      loc_1800060BC
0x180005dd5  lea     rcx, [rbp+8D0h+var_850]
0x180005ddc  mov     rax, rsi
0x180005ddf  inc     rax
0x180005de2  cmp     [rcx+rax*2], r12w
0x180005de7  jnz     short loc_180005DDF
0x180005de9  jmp     loc_180006081
0x180005dee  movzx   ecx, word ptr [rbx+0Ah]
0x180005df2  mov     eax, 0D0h
0x180005df7  cmp     cx, ax
0x180005dfa  jb      loc_180005F13
0x180005e00  cmp     byte ptr [rbx+9], 3
0x180005e04  jnz     loc_180005F13
0x180005e0a  mov     al, [rbx+8]
0x180005e0d  cmp     al, dl
0x180005e0f  jnz     loc_180005F13
0x180005e15  movups  xmm0, xmmword ptr [rbx+10h]
0x180005e19  mov     [rsp+9D0h+var_970], al
0x180005e1d  mov     eax, [rbx+0Ch]
0x180005e20  movups  xmm1, xmmword ptr [rbx+20h]
0x180005e24  mov     [rsp+9D0h+var_96C], eax
0x180005e28  mov     rax, [rbx+80h]
0x180005e2f  mov     [rbp+8D0h+var_8F0], rax
0x180005e33  mov     eax, [rbx+88h]
0x180005e39  mov     dword ptr [rbp+8D0h+var_8E8], eax
0x180005e3c  mov     eax, [rbx+8Ch]
0x180005e42  mov     dword ptr [rbp+8D0h+var_8E8+4], eax
0x180005e45  mov     eax, [rbx+90h]
0x180005e4b  mov     [rbp+8D0h+var_8E0], eax
0x180005e4e  mov     eax, [rbx+94h]
0x180005e54  mov     [rbp+8D0h+var_8DC], eax
0x180005e57  mov     eax, [rbx+98h]
0x180005e5d  mov     [rbp+8D0h+var_8D8], eax
0x180005e60  mov     eax, [rbx+9Ch]
0x180005e66  mov     [rbp+8D0h+var_8D4], eax
0x180005e69  mov     eax, [rbx+0A0h]
0x180005e6f  mov     [rbp+8D0h+var_8D0], eax
0x180005e72  mov     eax, [rbx+0A4h]
0x180005e78  mov     [rbp+8D0h+var_8CC], eax
0x180005e7b  mov     rax, [rbx+0A8h]
0x180005e82  mov     qword ptr [rbp+8D0h+var_8C8], rax
0x180005e86  mov     eax, [rbx+0B0h]
0x180005e8c  mov     [rbp+8D0h+var_8B8], eax
0x180005e8f  mov     eax, [rbx+0B4h]
0x180005e95  mov     [rbp+8D0h+var_8B4], eax
0x180005e98  mov     eax, [rbx+0B8h]
0x180005e9e  mov     [rbp+8D0h+var_8B0], eax
0x180005ea1  mov     eax, [rbx+0BCh]
0x180005ea7  mov     [rbp+8D0h+var_8AC], eax
0x180005eaa  mov     rax, [rbx+0C0h]
0x180005eb1  movups  [rsp+9D0h+var_968], xmm0
0x180005eb6  mov     [rbp+8D0h+var_8A8], rax
0x180005eba  mov     eax, [rbx+0C8h]
0x180005ec0  movups  xmm0, xmmword ptr [rbx+30h]
0x180005ec4  mov     [rbp+8D0h+var_8A0], eax
0x180005ec7  mov     eax, [rbx+0CCh]
0x180005ecd  movups  [rsp+9D0h+var_958], xmm1
0x180005ed2  mov     [rbp+8D0h+var_89C], eax
0x180005ed5  movups  xmm1, xmmword ptr [rbx+40h]
0x180005ed9  mov     rax, [rbx+0D0h]
0x180005ee0  movups  [rbp+8D0h+var_948], xmm0
0x180005ee4  mov     [rbp+8D0h+var_898], rax
0x180005ee8  movups  xmm0, xmmword ptr [rbx+50h]
0x180005eec  mov     [rsp+9D0h+var_96F], 3
0x180005ef1  movups  [rbp+8D0h+var_938], xmm1
0x180005ef5  mov     [rsp+9D0h+var_96E], cx
0x180005efa  movups  xmm1, xmmword ptr [rbx+60h]
0x180005efe  movups  [rbp+8D0h+var_928], xmm0
0x180005f02  movups  xmm0, xmmword ptr [rbx+70h]
0x180005f06  movups  [rbp+8D0h+var_918], xmm1
0x180005f0a  movups  [rbp+8D0h+var_908], xmm0
0x180005f0e  jmp     loc_18000618D
0x180005f13  test    cs:byte_1800C8404, 10h
0x180005f1a  jz      loc_1800060BC
0x180005f20  movzx   eax, byte ptr [rbx+8]
0x180005f24  lea     rdx, aDdmadminserver_10; "DDMAdminServerSetInfoEx: Invalid Versio"...
0x180005f2b  movzx   r9d, byte ptr [rbx+9]
0x180005f30  mov     r8d, ecx
0x180005f33  lea     rcx, [rbp+8D0h+var_850]
0x180005f3a  mov     [rsp+9D0h+var_9B0], eax
0x180005f3e  mov     word ptr [rbp+8D0h+var_850], r12w
0x180005f46  call    FormatRRASErrorString
0x180005f4b  test    cs:byte_1800C8404, 10h
0x180005f52  jz      loc_1800060BC
0x180005f58  lea     rcx, [rbp+8D0h+var_850]
0x180005f5f  mov     rax, rsi
0x180005f62  inc     rax
  ... truncated ...
```
