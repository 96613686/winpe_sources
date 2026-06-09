# DdmModernDevice::ProcessMakeCallComplete(void)

- ea: `0x180044060`
- end: `0x180045033`
- name: `?ProcessMakeCallComplete@DdmModernDevice@@UEAAKXZ`
- size: `4051`
- prototype: `__int64 __fastcall(DdmModernDevice *this)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002be6`
- `0x180007c0c`
- `0x180007d00`
- `0x180007e60`
- `0x180044060`
- `0x180075588`
- `0x1800755b8`
- `0x180085cb4`
- `0x180087a34`
- `0x180087d80`
- `0x180092a92`
- `0x180092a9e`
- `0x180092ad0`
- `0x180092b90`
- `0x180095010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180044bfd`
- `KERNEL32!LocalFree` at `0x180044d3f`
- `KERNEL32!LocalFree` at `0x180044d98`
- `KERNEL32!LocalFree` at `0x180044e20`
- `KERNEL32!LocalFree` at `0x180044e2f`
- `KERNEL32!LocalFree` at `0x180044e65`
- `KERNEL32!LocalFree` at `0x180044e9a`
- `KERNEL32!LocalFree` at `0x180044bfd`
- `KERNEL32!LocalFree` at `0x180044d3f`
- `KERNEL32!LocalFree` at `0x180044d98`
- `KERNEL32!LocalFree` at `0x180044e20`
- `KERNEL32!LocalFree` at `0x180044e2f`
- `KERNEL32!LocalFree` at `0x180044e65`
- `KERNEL32!LocalFree` at `0x180044e9a`
- `KERNEL32!GetLastError` at `0x180044713`
- `KERNEL32!GetLastError` at `0x180044b46`
- `KERNEL32!GetLastError` at `0x180044d15`
- `KERNEL32!GetLastError` at `0x180044d7a`
- `KERNEL32!GetLastError` at `0x180044dec`
- `KERNEL32!GetLastError` at `0x180044713`
- `KERNEL32!GetLastError` at `0x180044b46`
- `KERNEL32!GetLastError` at `0x180044d15`
- `KERNEL32!GetLastError` at `0x180044d7a`
- `KERNEL32!GetLastError` at `0x180044dec`
- `KERNEL32!LocalAlloc` at `0x180044b2e`
- `KERNEL32!LocalAlloc` at `0x180044d64`
- `KERNEL32!LocalAlloc` at `0x180044b2e`
- `KERNEL32!LocalAlloc` at `0x180044d64`
- `KERNEL32!WideCharToMultiByte` at `0x180044703`
- `KERNEL32!WideCharToMultiByte` at `0x180044d01`
- `KERNEL32!WideCharToMultiByte` at `0x180044dd6`
- `KERNEL32!WideCharToMultiByte` at `0x180044703`
- `KERNEL32!WideCharToMultiByte` at `0x180044d01`
- `KERNEL32!WideCharToMultiByte` at `0x180044dd6`
- `RASAPI32!DDMUpdateProtocolConfigInfoFromEntry` at `0x180044426`
- `RASAPI32!DDMUpdateProtocolConfigInfoFromEntry` at `0x180044426`
- `RASAPI32!DDMGetEapInfo` at `0x180044506`
- `RASAPI32!DDMGetEapInfo` at `0x180044506`
- `RASAPI32!DDMGetProtocolStartParams` at `0x18004459a`
- `RASAPI32!DDMGetProtocolStartParams` at `0x18004459a`
- `RASAPI32!DDMComputeLuid` at `0x180044475`
- `RASAPI32!DDMComputeLuid` at `0x180044475`
- `RASAPI32!DDMGetRasDialParams` at `0x1800440d6`
- `RASAPI32!DDMGetRasDialParams` at `0x1800440d6`

## string_xrefs

- `0x180044235`: `DdmModernDevice::ProcessMakeCallComplete`
- `0x180044f0f`: `DdmModernDevice::ProcessMakeCallComplete`
- `0x18004423c`: `%s: Makecall completed (hport: %ld)`
- `0x180044464`: `DdmUpdateProtocolConfigInfoFromEntry failed: (%d)`
- `0x1800444bd`: `DDMComputeLuid failed: (%d)`
- `0x1800445d8`: `DDMGetProtocolStartParams failed: (%d)`
- `0x180044613`: `RasProtocolStart(cfg=0x%x)...`
- `0x180044f16`: `%s: Sending protocol_start to protocol engine (hport: %ld)`
- `0x180044fcc`: `RasProtocolStart done(%d)`

## pseudocode

```c
__int64 __fastcall DdmModernDevice::ProcessMakeCallComplete(DdmModernDevice *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  int v4; // r14d
  unsigned __int64 cbMultiByte; // r12
  WCHAR *v6; // r15
  __int64 v7; // r8
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rax
  DWORD started; // esi
  __int64 v12; // rdx
  __int64 v13; // rdx
  DWORD v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int EntryDialParams; // edi
  DWORD LastError; // edi
  __int64 v23; // rdx
  __int64 v24; // rdx
  char *v25; // rcx
  __int64 v26; // rdx
  char v27; // al
  bool v28; // zf
  char *v29; // rax
  __int64 v30; // rdx
  _BYTE *v31; // rcx
  char v32; // al
  _BYTE *v33; // rax
  __int64 v34; // rdx
  _BYTE *v35; // rcx
  char v36; // al
  _BYTE *v37; // rax
  __int64 v38; // rdx
  _BYTE *v39; // rcx
  char v40; // al
  _BYTE *v41; // rax
  __int64 v42; // rdx
  _BYTE *v43; // rcx
  char v44; // al
  _BYTE *v45; // rax
  __int64 v46; // rdx
  _BYTE *v47; // rcx
  char v48; // al
  _BYTE *v49; // rax
  __int64 v50; // rdx
  char *v51; // rcx
  _OWORD *v52; // rax
  __int128 v53; // xmm1
  _OWORD *v54; // rcx
  __int64 v55; // rdx
  char *v56; // rax
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  const void *v64; // rdx
  __int128 v65; // xmm1
  __int128 v66; // xmm0
  __int128 v67; // xmm0
  int v68; // ecx
  DWORD Key; // r14d
  WCHAR *v70; // rax
  int v71; // ecx
  __int64 v72; // rdx
  DWORD v74; // eax
  unsigned int v75; // edi
  unsigned int v76; // r13d
  unsigned int v77; // eax
  WCHAR *v78; // r13
  CHAR *lpMultiByteStr; // rax
  __int64 v80; // rdx
  int v81; // eax
  void (__fastcall *v82)(__int64 *); // rdx
  __int64 v83; // rdx
  SIZE_T uBytes; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL UsedDefaultChar; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v86; // [rsp+4Ch] [rbp-B4h] BYREF
  int v87; // [rsp+50h] [rbp-B0h]
  int v88; // [rsp+54h] [rbp-ACh]
  unsigned __int64 v89; // [rsp+58h] [rbp-A8h]
  __int64 v90; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD *v91; // [rsp+68h] [rbp-98h] BYREF
  __int64 v92; // [rsp+70h] [rbp-90h] BYREF
  __int64 v93; // [rsp+78h] [rbp-88h]
  __int64 v94[3]; // [rsp+80h] [rbp-80h] BYREF
  char v95; // [rsp+99h] [rbp-67h] BYREF
  _BYTE v96[1537]; // [rsp+19Dh] [rbp+9Dh] BYREF
  _BYTE v97[128]; // [rsp+79Eh] [rbp+69Eh] BYREF
  _BYTE v98[257]; // [rsp+81Eh] [rbp+71Eh] BYREF
  _BYTE v99[257]; // [rsp+91Fh] [rbp+81Fh] BYREF
  _BYTE v100[16]; // [rsp+A20h] [rbp+920h] BYREF
  __int64 v101; // [rsp+A30h] [rbp+930h]
  char v102; // [rsp+A38h] [rbp+938h] BYREF
  char v103; // [rsp+E68h] [rbp+D68h] BYREF
  char v104[536]; // [rsp+1078h] [rbp+F78h] BYREF
  int v105[568]; // [rsp+1290h] [rbp+1190h] BYREF
  __int64 v106; // [rsp+1B70h] [rbp+1A70h]
  __int64 v107; // [rsp+1B78h] [rbp+1A78h]
  __int128 v108; // [rsp+1B90h] [rbp+1A90h]
  WCHAR *v109; // [rsp+1BA0h] [rbp+1AA0h]
  unsigned int v110; // [rsp+1BA8h] [rbp+1AA8h]
  _BYTE v111[12]; // [rsp+1C50h] [rbp+1B50h] BYREF
  int v112; // [rsp+1C5Ch] [rbp+1B5Ch]
  __int64 v113; // [rsp+1C60h] [rbp+1B60h]
  DWORD v114; // [rsp+1C90h] [rbp+1B90h]
  __int128 v115; // [rsp+2330h] [rbp+2230h] BYREF
  __int64 v116; // [rsp+2340h] [rbp+2240h] BYREF
  int v117; // [rsp+2348h] [rbp+2248h]
  int v118; // [rsp+234Ch] [rbp+224Ch]
  __int64 v119; // [rsp+2350h] [rbp+2250h]
  int v120; // [rsp+2358h] [rbp+2258h]
  int v121; // [rsp+235Ch] [rbp+225Ch]
  __int64 v122; // [rsp+2360h] [rbp+2260h]
  int v123; // [rsp+2368h] [rbp+2268h]
  int v124; // [rsp+236Ch] [rbp+226Ch]
  _DWORD v125[268]; // [rsp+2370h] [rbp+2270h] BYREF
  _BYTE v126[1034]; // [rsp+27A0h] [rbp+26A0h] BYREF
  WCHAR WideCharStr[275]; // [rsp+2BAAh] [rbp+2AAAh] BYREF
  char v128[16]; // [rsp+2DD0h] [rbp+2CD0h] BYREF
  const wchar_t *v129; // [rsp+2DE0h] [rbp+2CE0h]
  int v130; // [rsp+2DE8h] [rbp+2CE8h]
  int v131; // [rsp+2DECh] [rbp+2CECh]
  int v132; // [rsp+2DF0h] [rbp+2CF0h] BYREF
  __int128 v133; // [rsp+2DF4h] [rbp+2CF4h]
  __int128 v134; // [rsp+2E04h] [rbp+2D04h]
  int v135; // [rsp+2E14h] [rbp+2D14h]
  __int16 v136; // [rsp+2E18h] [rbp+2D18h] BYREF
  __int128 v137; // [rsp+2E1Ah] [rbp+2D1Ah]
  __int64 v138; // [rsp+2E2Ah] [rbp+2D2Ah]
  int v139; // [rsp+2E32h] [rbp+2D32h]
  __int16 v140; // [rsp+2E36h] [rbp+2D36h]
  __int16 v141; // [rsp+2E40h] [rbp+2D40h] BYREF
  char v142[142]; // [rsp+2E42h] [rbp+2D42h] BYREF
  char Str1[272]; // [rsp+2ED0h] [rbp+2DD0h] BYREF
  __int16 v144; // [rsp+2FE0h] [rbp+2EE0h] BYREF
  char v145[270]; // [rsp+2FE2h] [rbp+2EE2h] BYREF
  int v146; // [rsp+30F0h] [rbp+2FF0h] BYREF
  char v147[2044]; // [rsp+30F4h] [rbp+2FF4h] BYREF
  __int16 v148; // [rsp+38F0h] [rbp+37F0h] BYREF
  char v149[270]; // [rsp+38F2h] [rbp+37F2h] BYREF
  __int16 v150; // [rsp+3A00h] [rbp+3900h] BYREF
  char v151[1550]; // [rsp+3A02h] [rbp+3902h] BYREF

  v90 = 0;
  v119 = 0;
  v122 = 0;
  memset_0(v125, 0, sizeof(v125));
  v2 = *((_QWORD *)this + 1365);
  v86 = 0;
  uBytes = 0;
  v92 = 0;
  v3 = DDMGetRasDialParams(v2);
  v93 = 0;
  v4 = 0;
  LODWORD(cbMultiByte) = 0;
  v6 = 0;
  memset_0(v94, 0, 0x1BD0u);
  v144 = 0;
  memset_0(v145, 0, 0xFFu);
  *(_WORD *)Str1 = 0;
  memset_0(&Str1[2], 0, 0xFFu);
  v136 = 0;
  v138 = 0;
  v139 = 0;
  v140 = 0;
  v148 = 0;
  v137 = 0;
  memset_0(v149, 0, 0x102u);
  v150 = 0;
  memset_0(v151, 0, 0x5FFu);
  v141 = 0;
  memset_0(v142, 0, 0x7Fu);
  v91 = 0;
  v146 = 0;
  memset_0(v147, 0, sizeof(v147));
  v132 = 0;
  v133 = 0;
  v135 = 0;
  v134 = 0;
  v115 = 0;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v8 = *((unsigned int *)this + 24);
    LOWORD(v146) = 0;
    LOWORD(v132) = 0;
    ConvertPortNoToString(&v132, v8);
    FormatRRASErrorString(
      &v146,
      L"%s: Makecall completed (hport: %ld)",
      L"DdmModernDevice::ProcessMakeCallComplete",
      *((_QWORD *)this + 12));
    if ( (byte_1800CF404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v146,
        (unsigned int)&v115,
        0,
        (__int64)&v132);
  }
  *((_DWORD *)this + 2780) = 3;
  v124 = -1;
  v123 = -1;
  v118 = 1600;
  v117 = 1600;
  v9 = *((_DWORD *)this + 486) - 15;
  v116 = 0;
  v119 = 0;
  v122 = 0;
  if ( v9 <= 1 )
  {
    v121 = 0x10000000;
    v116 = 0x5DC000005DCLL;
    v120 = 0x10000000;
  }
  else
  {
    v121 = 256;
    v120 = 256;
  }
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v10 = -1;
    do
      ++v10;
    while ( aSetframingex[v10] );
    v129 = L"SetFramingEx...";
    v130 = 2 * v10 + 2;
    v131 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v7, 2, v128);
  }
  started = (*(__int64 (__fastcall **)(DdmModernDevice *, __int64 *))(*(_QWORD *)this + 624LL))(this, &v116);
  if ( !started )
  {
    started = DDMUpdateProtocolConfigInfoFromEntry(*((_QWORD *)this + 1365), &v86, v125);
    if ( started )
    {
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_95;
      v13 = *((unsigned int *)this + 24);
      LOWORD(v146) = 0;
      LOWORD(v132) = 0;
      ConvertPortNoToString(&v132, v13);
      FormatRRASErrorString(&v146, L"DdmUpdateProtocolConfigInfoFromEntry failed: (%d)", started);
      goto LABEL_14;
    }
    v14 = DDMComputeLuid(&v90);
    started = v14;
    if ( !*(_WORD *)(v3 + 1034) )
    {
      if ( v14 )
      {
        if ( (byte_1800CF404 & 8) == 0 )
          goto LABEL_95;
        v15 = *((unsigned int *)this + 24);
        LOWORD(v146) = 0;
        LOWORD(v132) = 0;
        ConvertPortNoToString(&v132, v15);
        FormatRRASErrorString(&v146, L"DDMComputeLuid failed: (%d)", started);
        goto LABEL_14;
      }
      *((_QWORD *)this + 1367) = v90;
    }
    if ( (v125[0] & 0x8000) != 0 )
    {
      started = DDMGetEapInfo(
                  *((_QWORD *)this + 1365),
                  v86,
                  (char *)this + 10960,
                  (char *)this + 10944,
                  (char *)this + 10952);
      if ( started )
      {
        if ( (byte_1800CF404 & 8) == 0 )
          goto LABEL_95;
        v16 = *((unsigned int *)this + 24);
        LOWORD(v146) = 0;
        LOWORD(v132) = 0;
        ConvertPortNoToString(&v132, v16);
        FormatRRASErrorString(&v146, L"DDMGetEapInfo failed: (%d)", started);
        goto LABEL_14;
      }
    }
    started = DDMGetProtocolStartParams(*((_QWORD *)this + 1365), &v144, Str1, &v136, &v148, &v150, &v141, &v91);
    if ( started )
    {
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_95;
      v17 = *((unsigned int *)this + 24);
      LOWORD(v146) = 0;
      LOWORD(v132) = 0;
      ConvertPortNoToString(&v132, v17);
      FormatRRASErrorString(&v146, L"DDMGetProtocolStartParams failed: (%d)", started);
      goto LABEL_14;
    }
    if ( (byte_1800CF404 & 8) != 0 )
    {
      v18 = *((unsigned int *)this + 24);
      LOWORD(v146) = 0;
      LOWORD(v132) = 0;
      ConvertPortNoToString(&v132, v18);
      FormatRRASErrorString(&v146, L"RasProtocolStart(cfg=0x%x)...", v125[0]);
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v146,
          (unsigned int)&v115,
          0,
          (__int64)&v132);
    }
    if ( (_BYTE)v144 && !strcmp_0(Str1, "****************") )
    {
      memset_0(v126, 0, 0x630u);
      v19 = *((unsigned int *)this + 2733);
      UsedDefaultChar = -2147483646;
      EntryDialParams = GetEntryDialParams(v20, v19, &UsedDefaultChar, v126);
      if ( EntryDialParams || (UsedDefaultChar & 2) == 0 )
      {
        if ( (byte_1800CF404 & 8) == 0 )
          goto LABEL_46;
        v24 = *((unsigned int *)this + 24);
        LOWORD(v146) = 0;
        LOWORD(v132) = 0;
        ConvertPortNoToString(&v132, v24);
        FormatRRASErrorString(&v146, L"Failed to get dialparams. 0x%x", EntryDialParams);
        goto LABEL_44;
      }
      if ( WideCharToMultiByte(0, 0x400u, WideCharStr, -1, Str1, 257, 0, 0) )
      {
        HIDWORD(uBytes) = 1;
        goto LABEL_46;
      }
      LastError = GetLastError();
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v23 = *((unsigned int *)this + 24);
        LOWORD(v146) = 0;
        LOWORD(v132) = 0;
        ConvertPortNoToString(&v132, v23);
        FormatRRASErrorString(&v146, L"Failed to convert pwd to ansi. 0x%x", LastError);
LABEL_44:
        if ( (byte_1800CF404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v146,
            (unsigned int)&v115,
            0,
            (__int64)&v132);
      }
    }
LABEL_46:
    v93 = *((_QWORD *)this + 12);
    v25 = &v95;
    v26 = 260;
    v94[0] = *((_QWORD *)this + 15);
    LODWORD(v92) = 0;
    do
    {
      if ( v26 == -2147483386 )
        break;
      v27 = v25[14423];
      if ( !v27 )
        break;
      *v25++ = v27;
      --v26;
    }
    while ( v26 );
    v28 = v26 == 0;
    v29 = v25 - 1;
    v30 = 1537;
    if ( !v28 )
      v29 = v25;
    v31 = v96;
    *v29 = 0;
    do
    {
      if ( v30 == -2147482109 )
        break;
      v32 = v31[(char *)&v150 - v96];
      if ( !v32 )
        break;
      *v31++ = v32;
      --v30;
    }
    while ( v30 );
    v33 = v31 - 1;
    if ( v30 )
      v33 = v31;
    v34 = 128;
    v35 = v97;
    *v33 = 0;
    do
    {
      if ( v34 == -2147483518 )
        break;
      v36 = v35[(char *)&v141 - v97];
      if ( !v36 )
        break;
      *v35++ = v36;
      --v34;
    }
    while ( v34 );
    v37 = v35 - 1;
    if ( v34 )
      v37 = v35;
    v38 = 257;
    v39 = v98;
    *v37 = 0;
    do
    {
      if ( v38 == -2147483389 )
        break;
      v40 = v39[(char *)&v144 - v98];
      if ( !v40 )
        break;
      *v39++ = v40;
      --v38;
    }
    while ( v38 );
    v28 = v38 == 0;
    v41 = v39 - 1;
    v42 = 257;
    if ( !v28 )
      v41 = v39;
    v43 = v99;
    *v41 = 0;
    do
    {
      if ( v42 == -2147483389 )
        break;
      v44 = v43[Str1 - v99];
      if ( !v44 )
        break;
      *v43++ = v44;
      --v42;
    }
    while ( v42 );
    v28 = v42 == 0;
    v45 = v43 - 1;
    v46 = 16;
    if ( !v28 )
      v45 = v43;
    v47 = v100;
    *v45 = 0;
    do
    {
      if ( v46 == -2147483630 )
        break;
      v48 = v47[(char *)&v136 - v100];
      if ( !v48 )
        break;
      *v47++ = v48;
      --v46;
    }
    while ( v46 );
    v28 = v46 == 0;
    v49 = v47 - 1;
    v50 = 4;
    if ( !v28 )
      v49 = v47;
    v51 = &v103;
    *v49 = 0;
    v52 = v91;
    do
    {
      *(_OWORD *)v51 = *v52;
      *((_OWORD *)v51 + 1) = v52[1];
      *((_OWORD *)v51 + 2) = v52[2];
      *((_OWORD *)v51 + 3) = v52[3];
      *((_OWORD *)v51 + 4) = v52[4];
      *((_OWORD *)v51 + 5) = v52[5];
      *((_OWORD *)v51 + 6) = v52[6];
      v51 += 128;
      v53 = v52[7];
      v52 += 8;
      *((_OWORD *)v51 - 1) = v53;
      --v50;
    }
    while ( v50 );
    v54 = v125;
    v101 = *((_QWORD *)this + 1367);
    v55 = 8;
    v56 = &v102;
    do
    {
      v57 = v54[1];
      *(_OWORD *)v56 = *v54;
      v58 = v54[2];
      *((_OWORD *)v56 + 1) = v57;
      v59 = v54[3];
      *((_OWORD *)v56 + 2) = v58;
      v60 = v54[4];
      *((_OWORD *)v56 + 3) = v59;
      v61 = v54[5];
      *((_OWORD *)v56 + 4) = v60;
      v62 = v54[6];
      *((_OWORD *)v56 + 5) = v61;
      v63 = v54[7];
      v54 += 8;
      *((_OWORD *)v56 + 6) = v62;
      v56 += 128;
      *((_OWORD *)v56 - 1) = v63;
      --v55;
    }
    while ( v55 );
    v64 = (const void *)*((_QWORD *)this + 242);
    v65 = v54[1];
    *(_OWORD *)v56 = *v54;
    v66 = v54[2];
    *((_OWORD *)v56 + 1) = v65;
    *((_OWORD *)v56 + 2) = v66;
    v67 = *(_OWORD *)((char *)this + 10852);
    v105[567] = *((_DWORD *)this + 2740);
    v106 = *((_QWORD *)this + 1368);
    v107 = *((_QWORD *)this + 1369);
    v108 = v67;
    memcpy_0(v104, v64, 0xAE8u);
    if ( (v125[0] & 0x10000000) == 0 && (v125[0] & 0x40000000) == 0 )
      goto LABEL_122;
    UsedDefaultChar = 0;
    Key = GetKey(v68, (int)v105, 512, (int)&uBytes, 0, 0);
    if ( Key == 603 )
    {
      LODWORD(cbMultiByte) = uBytes;
      v70 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)uBytes);
      v6 = v70;
      if ( !v70 )
      {
        Key = GetLastError();
        started = Key;
LABEL_91:
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v72 = *((unsigned int *)this + 24);
          LOWORD(v146) = 0;
          LOWORD(v132) = 0;
          ConvertPortNoToString(&v132, v72);
          FormatRRASErrorString(&v146, L"DwGetPresharedKey failed. Error: %d", Key);
          if ( (byte_1800CF404 & 8) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v146,
              (unsigned int)&v115,
              0,
              (__int64)&v132);
        }
LABEL_94:
        v4 = HIDWORD(uBytes);
        goto LABEL_95;
      }
      v74 = GetKey(v71, (int)v105, 512, (int)&uBytes, v70, 0);
      cbMultiByte = (unsigned int)uBytes;
      Key = v74;
      started = v74;
      if ( (unsigned int)uBytes > 2 )
      {
        LOWORD(uBytes) = *(WCHAR *)((char *)v6 + (unsigned int)uBytes - 2);
        v75 = (unsigned int)cbMultiByte >> 1;
        v76 = cbMultiByte;
        v89 = cbMultiByte;
        v87 = cbMultiByte;
        v77 = WideCharToMultiByte(0, 0x400u, v6, (unsigned int)cbMultiByte >> 1, 0, 0, 0, 0);
        cbMultiByte = v77;
        if ( !v77 )
        {
          Key = GetLastError();
          RasIpsecTrace("DwGetPresharedKey: WideCharToMultiByte failed error %d");
          memset(v6, 0, v76);
          LocalFree(v6);
          started = Key;
          LODWORD(cbMultiByte) = 0;
LABEL_120:
          if ( Key )
            goto LABEL_91;
          v109 = v6;
          v110 = cbMultiByte;
LABEL_122:
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            v80 = *((unsigned int *)this + 24);
            LOWORD(v146) = 0;
            LOWORD(v132) = 0;
            ConvertPortNoToString(&v132, v80);
            FormatRRASErrorString(
              &v146,
              L"%s: Sending protocol_start to protocol engine (hport: %ld)",
              L"DdmModernDevice::ProcessMakeCallComplete",
              *((_QWORD *)this + 12));
            if ( (byte_1800CF404 & 0x10) != 0 )
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDdmParamTraceInfo,
                (unsigned int)&v146,
                (unsigned int)&v115,
                0,
                (__int64)&v132);
          }
          v81 = (unsigned __int16)*((_DWORD *)this + 34);
          if ( v81 == 15 )
          {
            ((void (__fastcall *)(__int64 *))qword_1800CE518)(&v92);
          }
          else
          {
            v82 = (void (__fastcall *)(__int64 *))qword_1800CE4C8[0];
            if ( v81 == 16 )
              v82 = (void (__fastcall *)(__int64 *))qword_1800CE568;
            v82(&v92);
          }
          *((_DWORD *)this + 2864) |= 0x20u;
          if ( (byte_1800CF404 & 8) != 0 )
          {
            v83 = *((unsigned int *)this + 24);
            LOWORD(v146) = 0;
            LOWORD(v132) = 0;
            ConvertPortNoToString(&v132, v83);
            FormatRRASErrorString(&v146, L"RasProtocolStart done(%d)", 0);
            if ( (byte_1800CF404 & 8) != 0 )
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDdmParamTraceError,
                (unsigned int)&v146,
                (unsigned int)&v115,
                0,
                (__int64)&v132);
          }
          *((_DWORD *)this + 2780) = 6;
          *((_DWORD *)this + 32) = 2;
          goto LABEL_94;
        }
        v78 = v6;
        lpMultiByteStr = (CHAR *)LocalAlloc(0x40u, v77);
        v6 = (WCHAR *)lpMultiByteStr;
        if ( !lpMultiByteStr )
        {
          Key = GetLastError();
          memset(v78, 0, v89);
          LocalFree(v78);
LABEL_109:
          LODWORD(cbMultiByte) = 0;
          started = Key;
          goto LABEL_91;
        }
        v88 = WideCharToMultiByte(0, 0x400u, v78, v75, lpMultiByteStr, cbMultiByte, 0, &UsedDefaultChar);
        if ( !v88 )
        {
          Key = GetLastError();
          RasIpsecTrace("DwGetPresharedKey: WideCharToMultiByte failed error %d");
          memset(v78, 0, v89);
          memset(v6, 0, cbMultiByte);
          LocalFree(v78);
          LocalFree(v6);
          v6 = 0;
          goto LABEL_109;
        }
        if ( UsedDefaultChar )
        {
          RasIpsecTrace("DwGetPresharedKey: Can not convert pre-shared key Using Key as widechars");
          memset(v6, 0, cbMultiByte);
          LocalFree(v6);
          if ( !(_WORD)uBytes )
            LODWORD(cbMultiByte) = v87 - 2;
          v6 = v78;
          goto LABEL_120;
        }
        memset(v78, 0, v89);
        LocalFree(v78);
        if ( !(_WORD)uBytes )
        {
          LODWORD(cbMultiByte) = v88 - 1;
          goto LABEL_120;
        }
      }
    }
    else
    {
      LODWORD(cbMultiByte) = uBytes;
    }
    started = Key;
    if ( !v6 )
      goto LABEL_91;
    goto LABEL_120;
  }
  if ( (byte_1800CF404 & 8) == 0 )
    goto LABEL_95;
  v12 = *((unsigned int *)this + 24);
  LOWORD(v146) = 0;
  LOWORD(v132) = 0;
  ConvertPortNoToString(&v132, v12);
  FormatRRASErrorString(&v146, L"SetFramingEx failed: %d", started);
LABEL_14:
  if ( (byte_1800CF404 & 8) != 0 )
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceError,
      (unsigned int)&v146,
      (unsigned int)&v115,
      0,
      (__int64)&v132);
LABEL_95:
  if ( v109 )
    memset(v109, 0, v110);
  if ( v6 )
  {
    memset(v6, 0, (unsigned int)cbMultiByte);
    LocalFree(v6);
  }
  if ( v4 )
    memset(Str1, 0, 0x101u);
  if ( started )
  {
    memset_0(v111, 0, 0x6D8u);
    v113 = *((_QWORD *)this + 12);
    v112 = 1;
    v114 = started;
    SendProtocolMessageToDDM(v111);
  }
  return started;
}

```

## disassembly

```asm
0x180044060  mov     rax, rsp
0x180044063  mov     [rax+10h], rbx
0x180044067  mov     [rax+18h], rsi
0x18004406b  mov     [rax+20h], rdi
0x18004406f  push    rbp
0x180044070  push    r12
0x180044072  push    r13
0x180044074  push    r14
0x180044076  push    r15
0x180044078  lea     rbp, [rax-3F48h]
0x18004407f  mov     eax, 4020h
0x180044084  call    _alloca_probe
0x180044089  sub     rsp, rax
0x18004408c  mov     rax, cs:__security_cookie
0x180044093  xor     rax, rsp
0x180044096  mov     [rbp+3F40h+var_30], rax
0x18004409d  xor     r13d, r13d
0x1800440a0  mov     rbx, rcx
0x1800440a3  lea     rcx, [rbp+3F40h+var_1CD0]; void *
0x1800440aa  mov     [rsp+4040h+var_3FE0], r13
0x1800440af  xor     edx, edx; Val
0x1800440b1  mov     [rbp+3F40h+var_1CF0], r13
0x1800440b8  mov     r8d, 430h; Size
0x1800440be  mov     [rbp+3F40h+var_1CE0], r13
0x1800440c5  call    memset_0
0x1800440ca  mov     rcx, [rbx+2AA8h]
0x1800440d1  mov     [rsp+4040h+var_3FF4], r13d
0x1800440d6  call    cs:__imp_DDMGetRasDialParams
0x1800440dd  nop     dword ptr [rax+rax+00h]
0x1800440e2  xor     edx, edx; Val
0x1800440e4  mov     dword ptr [rsp+4040h+uBytes+4], r13d
0x1800440e9  mov     r8d, 1BD0h; Size
0x1800440ef  mov     dword ptr [rsp+4040h+uBytes], r13d
0x1800440f4  lea     rcx, [rbp+3F40h+var_3FC0]; void *
0x1800440f8  mov     [rsp+4040h+var_3FD0], r13
0x1800440fd  mov     rdi, rax
0x180044100  mov     [rsp+4040h+var_3FC8], r13
0x180044105  mov     r14d, r13d
0x180044108  mov     r12d, r13d
0x18004410b  mov     r15d, r13d
0x18004410e  call    memset_0
0x180044113  mov     esi, 0FFh
0x180044118  mov     [rbp+3F40h+var_1060], r13w
0x180044120  mov     r8d, esi; Size
0x180044123  lea     rcx, [rbp+3F40h+var_105E]; void *
0x18004412a  xor     edx, edx; Val
0x18004412c  call    memset_0
0x180044131  mov     r8d, esi; Size
0x180044134  mov     word ptr [rbp+3F40h+Str1], r13w
0x18004413c  xor     edx, edx; Val
0x18004413e  lea     rcx, [rbp+3F40h+var_116E]; void *
0x180044145  call    memset_0
0x18004414a  xor     eax, eax
0x18004414c  mov     [rbp+3F40h+var_1228], r13w
0x180044154  xorps   xmm0, xmm0
0x180044157  mov     [rbp+3F40h+var_1216], rax
0x18004415e  xor     edx, edx; Val
0x180044160  mov     [rbp+3F40h+var_120E], eax
0x180044166  lea     r8d, [rsi+3]; Size
0x18004416a  mov     [rbp+3F40h+var_120A], ax
0x180044171  lea     rcx, [rbp+3F40h+var_74E]; void *
0x180044178  mov     [rbp+3F40h+var_750], r13w
0x180044180  movups  [rbp+3F40h+var_1226], xmm0
0x180044187  call    memset_0
0x18004418c  xor     edx, edx; Val
0x18004418e  mov     [rbp+3F40h+var_640], r13w
0x180044196  mov     r8d, 5FFh; Size
0x18004419c  lea     rcx, [rbp+3F40h+var_63E]; void *
0x1800441a3  call    memset_0
0x1800441a8  xor     edx, edx; Val
0x1800441aa  mov     [rbp+3F40h+var_1200], r13w
0x1800441b2  lea     r8d, [r13+7Fh]; Size
0x1800441b6  lea     rcx, [rbp+3F40h+var_11FE]; void *
0x1800441bd  call    memset_0
0x1800441c2  xor     edx, edx; Val
0x1800441c4  mov     [rsp+4040h+var_3FD8], r13
0x1800441c9  mov     r8d, 7FCh; Size
0x1800441cf  mov     [rbp+3F40h+var_F50], r13d
0x1800441d6  lea     rcx, [rbp+3F40h+var_F4C]; void *
0x1800441dd  call    memset_0
0x1800441e2  xorps   xmm0, xmm0
0x1800441e5  mov     [rbp+3F40h+var_1250], r13d
0x1800441ec  xor     eax, eax
0x1800441ee  test    cs:byte_1800CF404, 10h
0x1800441f5  movups  [rbp+3F40h+var_124C], xmm0
0x1800441fc  mov     [rbp+3F40h+var_122C], eax
0x180044202  movups  [rbp+3F40h+var_123C], xmm0
0x180044209  movups  [rbp+3F40h+var_1D10], xmm0
0x180044210  jz      short loc_18004428A
0x180044212  mov     edx, [rbx+60h]
0x180044215  lea     rcx, [rbp+3F40h+var_1250]
0x18004421c  mov     word ptr [rbp+3F40h+var_F50], r13w
0x180044224  mov     word ptr [rbp+3F40h+var_1250], r13w
0x18004422c  call    ConvertPortNoToString
0x180044231  mov     r9, [rbx+60h]
0x180044235  lea     r8, aDdmmoderndevic_0; "DdmModernDevice::ProcessMakeCallComplet"...
0x18004423c  lea     rdx, aSMakecallCompl; "%s: Makecall completed (hport: %ld)"
0x180044243  lea     rcx, [rbp+3F40h+var_F50]
0x18004424a  call    FormatRRASErrorString
0x18004424f  test    cs:byte_1800CF404, 10h
0x180044256  jz      short loc_18004428A
0x180044258  lea     rax, [rbp+3F40h+var_1250]
0x18004425f  mov     qword ptr [rsp+4040h+cbMultiByte], rax
0x180044264  lea     r9, [rbp+3F40h+var_1D10]
0x18004426b  lea     r8, [rbp+3F40h+var_F50]
0x180044272  mov     [rsp+4040h+lpMultiByteStr], r13
0x180044277  lea     rdx, RasDdmParamTraceInfo
0x18004427e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180044285  call    McTemplateU0zjzz_EventWriteTransfer
0x18004428a  or      eax, 0FFFFFFFFh
0x18004428d  mov     dword ptr [rbx+2B70h], 3
0x180044297  mov     [rbp+3F40h+var_1CD4], eax
0x18004429d  mov     ecx, 10000000h
0x1800442a2  mov     [rbp+3F40h+var_1CD8], eax
0x1800442a8  mov     eax, 640h
0x1800442ad  mov     [rbp+3F40h+var_1CF4], eax
0x1800442b3  mov     [rbp+3F40h+var_1CF8], eax
0x1800442b9  mov     eax, [rbx+798h]
0x1800442bf  sub     eax, 0Fh
0x1800442c2  mov     [rbp+3F40h+var_1D00], r13
0x1800442c9  mov     [rbp+3F40h+var_1CF0], r13
0x1800442d0  mov     [rbp+3F40h+var_1CE0], r13
0x1800442d7  cmp     eax, 1
0x1800442da  jbe     short loc_1800442EF
0x1800442dc  mov     eax, 100h
0x1800442e1  mov     [rbp+3F40h+var_1CE4], eax
0x1800442e7  mov     [rbp+3F40h+var_1CE8], eax
0x1800442ed  jmp     short loc_18004430C
0x1800442ef  mov     eax, 5DCh
0x1800442f4  mov     [rbp+3F40h+var_1CE4], ecx
0x1800442fa  mov     dword ptr [rbp+3F40h+var_1D00+4], eax
0x180044300  mov     dword ptr [rbp+3F40h+var_1D00], eax
0x180044306  mov     [rbp+3F40h+var_1CE8], ecx
0x18004430c  test    cs:byte_1800CF404, 10h
0x180044313  jz      short loc_18004436A
0x180044315  lea     rcx, aSetframingex; "SetFramingEx..."
0x18004431c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044320  inc     rax
0x180044323  cmp     [rcx+rax*2], r13w
0x180044328  jnz     short loc_180044320
0x18004432a  lea     eax, ds:2[rax*2]
0x180044331  mov     [rbp+3F40h+var_1260], rcx
0x180044338  mov     [rbp+3F40h+var_1258], eax
0x18004433e  lea     rdx, RasDdmTraceInfo
0x180044345  lea     rax, [rbp+3F40h+var_1270]
0x18004434c  mov     [rbp+3F40h+var_1254], r13d
0x180044353  mov     r9d, 2
0x180044359  mov     [rsp+4040h+lpMultiByteStr], rax
0x18004435e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180044365  call    McGenEventWrite_EventWriteTransfer
0x18004436a  mov     rax, [rbx]
0x18004436d  lea     rdx, [rbp+3F40h+var_1D00]
0x180044374  mov     rcx, rbx
0x180044377  mov     rax, [rax+270h]
0x18004437e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044383  mov     esi, eax
0x180044385  test    eax, eax
0x180044387  jz      loc_180044413
0x18004438d  test    cs:byte_1800CF404, 8
0x180044394  jz      loc_180044BD5
0x18004439a  mov     edx, [rbx+60h]
0x18004439d  lea     rcx, [rbp+3F40h+var_1250]
0x1800443a4  mov     word ptr [rbp+3F40h+var_F50], r13w
0x1800443ac  mov     word ptr [rbp+3F40h+var_1250], r13w
0x1800443b4  call    ConvertPortNoToString
0x1800443b9  lea     rdx, aSetframingexFa; "SetFramingEx failed: %d"
0x1800443c0  mov     r8d, esi
0x1800443c3  lea     rcx, [rbp+3F40h+var_F50]
0x1800443ca  call    FormatRRASErrorString
0x1800443cf  test    cs:byte_1800CF404, 8
0x1800443d6  jz      loc_180044BD5
0x1800443dc  lea     rax, [rbp+3F40h+var_1250]
0x1800443e3  mov     qword ptr [rsp+4040h+cbMultiByte], rax
0x1800443e8  lea     r9, [rbp+3F40h+var_1D10]
0x1800443ef  lea     r8, [rbp+3F40h+var_F50]
0x1800443f6  mov     [rsp+4040h+lpMultiByteStr], r13
0x1800443fb  lea     rdx, RasDdmParamTraceError
0x180044402  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180044409  call    McTemplateU0zjzz_EventWriteTransfer
0x18004440e  jmp     loc_180044BD5
0x180044413  mov     rcx, [rbx+2AA8h]
0x18004441a  lea     r8, [rbp+3F40h+var_1CD0]
0x180044421  lea     rdx, [rsp+4040h+var_3FF4]
0x180044426  call    cs:__imp_DDMUpdateProtocolConfigInfoFromEntry
0x18004442d  nop     dword ptr [rax+rax+00h]
0x180044432  mov     esi, eax
0x180044434  test    eax, eax
0x180044436  jz      short loc_180044470
0x180044438  test    cs:byte_1800CF404, 8
0x18004443f  jz      loc_180044BD5
0x180044445  mov     edx, [rbx+60h]
0x180044448  lea     rcx, [rbp+3F40h+var_1250]
0x18004444f  mov     word ptr [rbp+3F40h+var_F50], r13w
0x180044457  mov     word ptr [rbp+3F40h+var_1250], r13w
0x18004445f  call    ConvertPortNoToString
0x180044464  lea     rdx, aDdmupdateproto; "DdmUpdateProtocolConfigInfoFromEntry fa"...
0x18004446b  jmp     loc_1800443C0
0x180044470  lea     rcx, [rsp+4040h+var_3FE0]
0x180044475  call    cs:__imp_DDMComputeLuid
0x18004447c  nop     dword ptr [rax+rax+00h]
0x180044481  mov     esi, eax
0x180044483  cmp     [rdi+40Ah], r13w
0x18004448b  jnz     short loc_1800444D5
0x18004448d  test    eax, eax
0x18004448f  jz      short loc_1800444C9
0x180044491  test    cs:byte_1800CF404, 8
0x180044498  jz      loc_180044BD5
0x18004449e  mov     edx, [rbx+60h]
0x1800444a1  lea     rcx, [rbp+3F40h+var_1250]
0x1800444a8  mov     word ptr [rbp+3F40h+var_F50], r13w
0x1800444b0  mov     word ptr [rbp+3F40h+var_1250], r13w
0x1800444b8  call    ConvertPortNoToString
0x1800444bd  lea     rdx, aDdmcomputeluid; "DDMComputeLuid failed: (%d)"
0x1800444c4  jmp     loc_1800443C0
0x1800444c9  mov     rax, [rsp+4040h+var_3FE0]
0x1800444ce  mov     [rbx+2AB8h], rax
0x1800444d5  test    [rbp+3F40h+var_1CD0], 8000h
0x1800444df  jz      short loc_180044550
0x1800444e1  mov     edx, [rsp+4040h+var_3FF4]
0x1800444e5  lea     rax, [rbx+2AC8h]
0x1800444ec  mov     rcx, [rbx+2AA8h]
0x1800444f3  lea     r9, [rbx+2AC0h]
0x1800444fa  lea     r8, [rbx+2AD0h]
0x180044501  mov     [rsp+4040h+lpMultiByteStr], rax
0x180044506  call    cs:__imp_DDMGetEapInfo
0x18004450d  nop     dword ptr [rax+rax+00h]
0x180044512  mov     esi, eax
0x180044514  test    eax, eax
0x180044516  jz      short loc_180044550
0x180044518  test    cs:byte_1800CF404, 8
0x18004451f  jz      loc_180044BD5
0x180044525  mov     edx, [rbx+60h]
0x180044528  lea     rcx, [rbp+3F40h+var_1250]
0x18004452f  mov     word ptr [rbp+3F40h+var_F50], r13w
0x180044537  mov     word ptr [rbp+3F40h+var_1250], r13w
0x18004453f  call    ConvertPortNoToString
0x180044544  lea     rdx, aDdmgeteapinfoF; "DDMGetEapInfo failed: (%d)"
0x18004454b  jmp     loc_1800443C0
0x180044550  mov     rcx, [rbx+2AA8h]
0x180044557  lea     rax, [rsp+4040h+var_3FD8]
0x18004455c  mov     [rsp+4040h+lpUsedDefaultChar], rax
0x180044561  lea     r9, [rbp+3F40h+var_1228]
0x180044568  lea     rax, [rbp+3F40h+var_1200]
0x18004456f  mov     [rsp+4040h+lpDefaultChar], rax
0x180044574  lea     r8, [rbp+3F40h+Str1]
0x18004457b  lea     rax, [rbp+3F40h+var_640]
0x180044582  mov     qword ptr [rsp+4040h+cbMultiByte], rax
0x180044587  lea     rdx, [rbp+3F40h+var_1060]
0x18004458e  lea     rax, [rbp+3F40h+var_750]
0x180044595  mov     [rsp+4040h+lpMultiByteStr], rax
0x18004459a  call    cs:__imp_DDMGetProtocolStartParams
0x1800445a1  nop     dword ptr [rax+rax+00h]
0x1800445a6  mov     esi, eax
0x1800445a8  test    eax, eax
0x1800445aa  jz      short loc_1800445E4
0x1800445ac  test    cs:byte_1800CF404, 8
0x1800445b3  jz      loc_180044BD5
0x1800445b9  mov     edx, [rbx+60h]
0x1800445bc  lea     rcx, [rbp+3F40h+var_1250]
0x1800445c3  mov     word ptr [rbp+3F40h+var_F50], r13w
0x1800445cb  mov     word ptr [rbp+3F40h+var_1250], r13w
0x1800445d3  call    ConvertPortNoToString
0x1800445d8  lea     rdx, aDdmgetprotocol_0; "DDMGetProtocolStartParams failed: (%d)"
0x1800445df  jmp     loc_1800443C0
0x1800445e4  test    cs:byte_1800CF404, 8
0x1800445eb  jz      short loc_180044661
0x1800445ed  mov     edx, [rbx+60h]
0x1800445f0  lea     rcx, [rbp+3F40h+var_1250]
0x1800445f7  mov     word ptr [rbp+3F40h+var_F50], r13w
0x1800445ff  mov     word ptr [rbp+3F40h+var_1250], r13w
0x180044607  call    ConvertPortNoToString
0x18004460c  mov     r8d, [rbp+3F40h+var_1CD0]
0x180044613  lea     rdx, aRasprotocolsta_0; "RasProtocolStart(cfg=0x%x)..."
0x18004461a  lea     rcx, [rbp+3F40h+var_F50]
0x180044621  call    FormatRRASErrorString
0x180044626  test    cs:byte_1800CF404, 8
0x18004462d  jz      short loc_180044661
0x18004462f  lea     rax, [rbp+3F40h+var_1250]
0x180044636  mov     qword ptr [rsp+4040h+cbMultiByte], rax
0x18004463b  lea     r9, [rbp+3F40h+var_1D10]
0x180044642  lea     r8, [rbp+3F40h+var_F50]
0x180044649  mov     [rsp+4040h+lpMultiByteStr], r13
0x18004464e  lea     rdx, RasDdmParamTraceError
0x180044655  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004465c  call    McTemplateU0zjzz_EventWriteTransfer
0x180044661  cmp     byte ptr [rbp+3F40h+var_1060], r13b
0x180044668  jz      loc_1800447D9
0x18004466e  lea     rdx, Str2; "****************"
0x180044675  lea     rcx, [rbp+3F40h+Str1]; Str1
0x18004467c  call    strcmp_0
0x180044681  test    eax, eax
0x180044683  jnz     loc_1800447D9
0x180044689  xor     edx, edx; Val
0x18004468b  lea     rcx, [rbp+3F40h+var_18A0]; void *
0x180044692  mov     r8d, 630h; Size
0x180044698  call    memset_0
0x18004469d  mov     edx, [rbx+2AB4h]
0x1800446a3  lea     r9, [rbp+3F40h+var_18A0]
0x1800446aa  lea     r8, [rsp+4040h+UsedDefaultChar]
0x1800446af  mov     [rsp+4040h+UsedDefaultChar], 80000002h
  ... truncated ...
```
