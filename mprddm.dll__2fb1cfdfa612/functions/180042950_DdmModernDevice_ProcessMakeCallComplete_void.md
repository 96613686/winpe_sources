# DdmModernDevice::ProcessMakeCallComplete(void)

- ea: `0x180042950`
- end: `0x18004398d`
- name: `?ProcessMakeCallComplete@DdmModernDevice@@UEAAKXZ`
- size: `4157`
- prototype: `unsigned int __fastcall(DdmModernDevice *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002ba6`
- `0x180007b7c`
- `0x180007c50`
- `0x180007da0`
- `0x180042950`
- `0x180071cec`
- `0x1800803a8`
- `0x180081e20`
- `0x180082174`
- `0x18008c5f2`
- `0x18008c5fe`
- `0x18008c630`
- `0x18008c6f0`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180042b11`
- `msvcrt!_itow_s` at `0x180042ca5`
- `msvcrt!_itow_s` at `0x180042d5a`
- `msvcrt!_itow_s` at `0x180042dbd`
- `msvcrt!_itow_s` at `0x180042e4e`
- `msvcrt!_itow_s` at `0x180042eec`
- `msvcrt!_itow_s` at `0x180042f36`
- `msvcrt!_itow_s` at `0x180043076`
- `msvcrt!_itow_s` at `0x1800430c3`
- `msvcrt!_itow_s` at `0x1800434a1`
- `msvcrt!_itow_s` at `0x18004384b`
- `msvcrt!_itow_s` at `0x18004391d`
- `msvcrt!_itow_s` at `0x180042b11`
- `msvcrt!_itow_s` at `0x180042ca5`
- `msvcrt!_itow_s` at `0x180042d5a`
- `msvcrt!_itow_s` at `0x180042dbd`
- `msvcrt!_itow_s` at `0x180042e4e`
- `msvcrt!_itow_s` at `0x180042eec`
- `msvcrt!_itow_s` at `0x180042f36`
- `msvcrt!_itow_s` at `0x180043076`
- `msvcrt!_itow_s` at `0x1800430c3`
- `msvcrt!_itow_s` at `0x1800434a1`
- `msvcrt!_itow_s` at `0x18004384b`
- `msvcrt!_itow_s` at `0x18004391d`
- `KERNEL32!LocalFree` at `0x180043540`
- `KERNEL32!LocalFree` at `0x180043669`
- `KERNEL32!LocalFree` at `0x1800436ba`
- `KERNEL32!LocalFree` at `0x180043748`
- `KERNEL32!LocalFree` at `0x180043751`
- `KERNEL32!LocalFree` at `0x18004378b`
- `KERNEL32!LocalFree` at `0x1800437c6`
- `KERNEL32!LocalFree` at `0x180043540`
- `KERNEL32!LocalFree` at `0x180043669`
- `KERNEL32!LocalFree` at `0x1800436ba`
- `KERNEL32!LocalFree` at `0x180043748`
- `KERNEL32!LocalFree` at `0x180043751`
- `KERNEL32!LocalFree` at `0x18004378b`
- `KERNEL32!LocalFree` at `0x1800437c6`
- `KERNEL32!GetLastError` at `0x180043039`
- `KERNEL32!GetLastError` at `0x180043461`
- `KERNEL32!GetLastError` at `0x18004363a`
- `KERNEL32!GetLastError` at `0x18004369b`
- `KERNEL32!GetLastError` at `0x180043703`
- `KERNEL32!GetLastError` at `0x180043039`
- `KERNEL32!GetLastError` at `0x180043461`
- `KERNEL32!GetLastError` at `0x18004363a`
- `KERNEL32!GetLastError` at `0x18004369b`
- `KERNEL32!GetLastError` at `0x180043703`
- `KERNEL32!LocalAlloc` at `0x18004344f`
- `KERNEL32!LocalAlloc` at `0x18004368d`
- `KERNEL32!LocalAlloc` at `0x18004344f`
- `KERNEL32!LocalAlloc` at `0x18004368d`
- `KERNEL32!WideCharToMultiByte` at `0x18004302f`
- `KERNEL32!WideCharToMultiByte` at `0x18004362c`
- `KERNEL32!WideCharToMultiByte` at `0x1800436f5`
- `KERNEL32!WideCharToMultiByte` at `0x18004302f`
- `KERNEL32!WideCharToMultiByte` at `0x18004362c`
- `KERNEL32!WideCharToMultiByte` at `0x1800436f5`
- `RASAPI32!DDMUpdateProtocolConfigInfoFromEntry` at `0x180042d18`
- `RASAPI32!DDMUpdateProtocolConfigInfoFromEntry` at `0x180042d18`
- `RASAPI32!DDMGetEapInfo` at `0x180042e0c`
- `RASAPI32!DDMGetEapInfo` at `0x180042e0c`
- `RASAPI32!DDMGetProtocolStartParams` at `0x180042eaa`
- `RASAPI32!DDMGetProtocolStartParams` at `0x180042eaa`
- `RASAPI32!DDMComputeLuid` at `0x180042d71`
- `RASAPI32!DDMComputeLuid` at `0x180042d71`
- `RASAPI32!DDMGetRasDialParams` at `0x1800429c6`
- `RASAPI32!DDMGetRasDialParams` at `0x1800429c6`

## string_xrefs

- `0x180042b1b`: `DdmModernDevice::ProcessMakeCallComplete`
- `0x180043855`: `DdmModernDevice::ProcessMakeCallComplete`
- `0x180042b22`: `%s: Makecall completed (hport: %ld)`
- `0x180042d60`: `DdmUpdateProtocolConfigInfoFromEntry failed: (%d)`
- `0x180042dc3`: `DDMComputeLuid failed: (%d)`
- `0x180042ef2`: `DDMGetProtocolStartParams failed: (%d)`
- `0x180042f43`: `RasProtocolStart(cfg=0x%x)...`
- `0x18004385c`: `%s: Sending protocol_start to protocol engine (hport: %ld)`
- `0x180043926`: `RasProtocolStart done(%d)`

## pseudocode

```c
__int64 __fastcall DdmModernDevice::ProcessMakeCallComplete(DdmModernDevice *this)
{
  __int64 v2; // rcx
  __int64 v3; // rsi
  __int64 v4; // r8
  int v5; // ecx
  int v6; // r12d
  WCHAR *lpMultiByteStr; // r15
  unsigned int v8; // eax
  DWORD started; // edi
  int v10; // ecx
  int v11; // ecx
  DWORD v12; // eax
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // ecx
  int v20; // ecx
  __int16 *v21; // r9
  char *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  bool v26; // zf
  char *v27; // rax
  __int16 *v28; // r9
  __int64 v29; // r8
  char *v30; // rcx
  __int64 v31; // rax
  char *v32; // rax
  __int16 *v33; // r9
  __int64 v34; // r8
  char *v35; // rcx
  __int64 v36; // rax
  char *v37; // rax
  __int16 *v38; // r9
  __int64 v39; // r8
  char *v40; // rcx
  __int64 v41; // rax
  char *v42; // rax
  char *v43; // r9
  __int64 v44; // r8
  char *v45; // rcx
  __int64 v46; // rax
  char *v47; // rax
  __int64 v48; // r8
  char *v49; // rcx
  char *v50; // rax
  char *v51; // rax
  __int64 v52; // rdx
  char *v53; // rcx
  _OWORD *v54; // rax
  __int128 v55; // xmm1
  _OWORD *v56; // rcx
  __int64 v57; // rdx
  char *v58; // rax
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  __int128 v64; // xmm0
  __int128 v65; // xmm1
  const void *v66; // rdx
  __int128 v67; // xmm1
  __int128 v68; // xmm0
  __int128 v69; // xmm0
  int v70; // ecx
  DWORD Key; // esi
  WCHAR *v72; // rax
  int v73; // ecx
  int v74; // ecx
  WCHAR *v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rcx
  WCHAR *v78; // rax
  char *v79; // rax
  __int64 v80; // rcx
  DWORD v82; // eax
  __int64 v83; // r14
  int v84; // edi
  int v85; // r9d
  unsigned int v86; // eax
  WCHAR *i; // rax
  WCHAR *v88; // r12
  WCHAR *j; // rax
  WCHAR *k; // rax
  __int64 v91; // rcx
  WCHAR *v92; // rax
  __int64 v93; // rcx
  WCHAR *v94; // rax
  WCHAR *m; // rax
  int v96; // ecx
  int v97; // eax
  void (__fastcall *v98)(__int64 *); // rdx
  int v99; // ecx
  unsigned int cbMultiByte; // [rsp+40h] [rbp-C0h]
  unsigned int uBytes; // [rsp+44h] [rbp-BCh] BYREF
  int uBytes_4; // [rsp+48h] [rbp-B8h]
  WINBOOL UsedDefaultChar; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v104; // [rsp+50h] [rbp-B0h] BYREF
  int v105; // [rsp+54h] [rbp-ACh]
  __int64 v106; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD *v107; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v108; // [rsp+68h] [rbp-98h]
  __int64 v109; // [rsp+70h] [rbp-90h] BYREF
  __int64 v110; // [rsp+78h] [rbp-88h]
  __int64 v111[3]; // [rsp+80h] [rbp-80h] BYREF
  char v112; // [rsp+99h] [rbp-67h] BYREF
  char v113; // [rsp+19Dh] [rbp+9Dh] BYREF
  char v114; // [rsp+79Eh] [rbp+69Eh] BYREF
  char v115; // [rsp+81Eh] [rbp+71Eh] BYREF
  char v116; // [rsp+91Fh] [rbp+81Fh] BYREF
  char v117; // [rsp+A20h] [rbp+920h] BYREF
  __int64 v118; // [rsp+A30h] [rbp+930h]
  char v119; // [rsp+A38h] [rbp+938h] BYREF
  char v120; // [rsp+E68h] [rbp+D68h] BYREF
  char v121[536]; // [rsp+1078h] [rbp+F78h] BYREF
  int v122[568]; // [rsp+1290h] [rbp+1190h] BYREF
  __int64 v123; // [rsp+1B70h] [rbp+1A70h]
  __int64 v124; // [rsp+1B78h] [rbp+1A78h]
  __int128 v125; // [rsp+1B90h] [rbp+1A90h]
  WCHAR *v126; // [rsp+1BA0h] [rbp+1AA0h]
  unsigned int v127; // [rsp+1BA8h] [rbp+1AA8h]
  _BYTE v128[12]; // [rsp+1C50h] [rbp+1B50h] BYREF
  int v129; // [rsp+1C5Ch] [rbp+1B5Ch]
  __int64 v130; // [rsp+1C60h] [rbp+1B60h]
  DWORD v131; // [rsp+1C90h] [rbp+1B90h]
  __int128 v132; // [rsp+2330h] [rbp+2230h] BYREF
  __int128 v133; // [rsp+2340h] [rbp+2240h] BYREF
  __int128 v134; // [rsp+2350h] [rbp+2250h]
  __int128 v135; // [rsp+2360h] [rbp+2260h]
  _DWORD v136[268]; // [rsp+2370h] [rbp+2270h] BYREF
  _BYTE v137[1034]; // [rsp+27A0h] [rbp+26A0h] BYREF
  WCHAR WideCharStr[275]; // [rsp+2BAAh] [rbp+2AAAh] BYREF
  char v139[16]; // [rsp+2DD0h] [rbp+2CD0h] BYREF
  const wchar_t *v140; // [rsp+2DE0h] [rbp+2CE0h]
  __int64 v141; // [rsp+2DE8h] [rbp+2CE8h]
  wchar_t Buffer[2]; // [rsp+2DF0h] [rbp+2CF0h] BYREF
  __int128 v143; // [rsp+2DF4h] [rbp+2CF4h]
  __int128 v144; // [rsp+2E04h] [rbp+2D04h]
  int v145; // [rsp+2E14h] [rbp+2D14h]
  _WORD v146[20]; // [rsp+2E18h] [rbp+2D18h] BYREF
  __int16 v147; // [rsp+2E40h] [rbp+2D40h] BYREF
  char v148[142]; // [rsp+2E42h] [rbp+2D42h] BYREF
  char Str1[2]; // [rsp+2ED0h] [rbp+2DD0h] BYREF
  char v150[270]; // [rsp+2ED2h] [rbp+2DD2h] BYREF
  __int16 v151; // [rsp+2FE0h] [rbp+2EE0h] BYREF
  char v152[270]; // [rsp+2FE2h] [rbp+2EE2h] BYREF
  __int16 v153; // [rsp+30F0h] [rbp+2FF0h] BYREF
  char v154[270]; // [rsp+30F2h] [rbp+2FF2h] BYREF
  int v155; // [rsp+3200h] [rbp+3100h] BYREF
  char v156[2044]; // [rsp+3204h] [rbp+3104h] BYREF
  __int16 v157; // [rsp+3A00h] [rbp+3900h] BYREF
  char v158[1550]; // [rsp+3A02h] [rbp+3902h] BYREF

  v106 = 0;
  v133 = 0;
  v134 = 0;
  v135 = 0;
  memset_0(v136, 0, sizeof(v136));
  v2 = *((_QWORD *)this + 1365);
  v104 = 0;
  cbMultiByte = 0;
  uBytes = 0;
  v109 = 0;
  v3 = DDMGetRasDialParams(v2);
  v110 = 0;
  memset_0(v111, 0, 0x1BD0u);
  v151 = 0;
  memset_0(v152, 0, 0xFFu);
  *(_WORD *)Str1 = 0;
  memset_0(v150, 0, 0xFFu);
  memset(v146, 0, 32);
  v153 = 0;
  memset_0(v154, 0, 0x102u);
  v157 = 0;
  memset_0(v158, 0, 0x5FFu);
  v147 = 0;
  memset_0(v148, 0, 0x7Fu);
  v107 = 0;
  v155 = 0;
  memset_0(v156, 0, sizeof(v156));
  *(_DWORD *)Buffer = 0;
  v143 = 0;
  v145 = 0;
  v144 = 0;
  v132 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v5 = *((_DWORD *)this + 24);
    LOWORD(v155) = 0;
    Buffer[0] = 0;
    if ( v5 != -1 )
      _itow_s(v5, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v155,
      L"%s: Makecall completed (hport: %ld)",
      L"DdmModernDevice::ProcessMakeCallComplete",
      *((_QWORD *)this + 12));
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v155,
        (unsigned int)&v132,
        0,
        (__int64)Buffer);
  }
  uBytes_4 = 0;
  v6 = 0;
  *((_QWORD *)&v133 + 1) = 0x64000000640LL;
  lpMultiByteStr = 0;
  v8 = *((_DWORD *)this + 486) - 15;
  *((_DWORD *)this + 2780) = 3;
  *(_QWORD *)&v133 = 0;
  *(_QWORD *)&v134 = 0;
  *(_QWORD *)&v135 = 0;
  *((_QWORD *)&v135 + 1) = -1;
  if ( v8 <= 1 )
  {
    *(_QWORD *)&v133 = 0x5DC000005DCLL;
    *((_QWORD *)&v134 + 1) = 0x1000000010000000LL;
  }
  else
  {
    *((_QWORD *)&v134 + 1) = 0x10000000100LL;
  }
  LOBYTE(v105) = byte_1800C8404 & 0x10;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v141 = 32;
    v140 = L"SetFramingEx...";
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v4, 2, v139);
  }
  started = (*(__int64 (__fastcall **)(DdmModernDevice *, __int128 *))(*(_QWORD *)this + 624LL))(this, &v133);
  if ( !started )
  {
    started = DDMUpdateProtocolConfigInfoFromEntry(*((_QWORD *)this + 1365), &v104, v136);
    if ( started )
    {
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_113;
      v11 = *((_DWORD *)this + 24);
      LOWORD(v155) = 0;
      Buffer[0] = 0;
      if ( v11 != -1 )
        _itow_s(v11, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v155, L"DdmUpdateProtocolConfigInfoFromEntry failed: (%d)", started);
      goto LABEL_16;
    }
    v12 = DDMComputeLuid(&v106);
    started = v12;
    if ( !*(_WORD *)(v3 + 1034) )
    {
      if ( v12 )
      {
        if ( (byte_1800C8404 & 8) == 0 )
          goto LABEL_113;
        v13 = *((_DWORD *)this + 24);
        LOWORD(v155) = 0;
        Buffer[0] = 0;
        if ( v13 != -1 )
          _itow_s(v13, Buffer, 0x14u, 10);
        FormatRRASErrorString(&v155, L"DDMComputeLuid failed: (%d)", started);
        goto LABEL_16;
      }
      *((_QWORD *)this + 1367) = v106;
    }
    if ( (v136[0] & 0x8000) != 0 )
    {
      started = DDMGetEapInfo(
                  *((_QWORD *)this + 1365),
                  v104,
                  (char *)this + 10960,
                  (char *)this + 10944,
                  (char *)this + 10952);
      if ( started )
      {
        if ( (byte_1800C8404 & 8) == 0 )
          goto LABEL_113;
        v14 = *((_DWORD *)this + 24);
        LOWORD(v155) = 0;
        Buffer[0] = 0;
        if ( v14 != -1 )
          _itow_s(v14, Buffer, 0x14u, 10);
        FormatRRASErrorString(&v155, L"DDMGetEapInfo failed: (%d)", started);
        goto LABEL_16;
      }
    }
    started = DDMGetProtocolStartParams(*((_QWORD *)this + 1365), &v151, Str1, v146, &v153, &v157, &v147, &v107);
    if ( started )
    {
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_113;
      v15 = *((_DWORD *)this + 24);
      LOWORD(v155) = 0;
      Buffer[0] = 0;
      if ( v15 != -1 )
        _itow_s(v15, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v155, L"DDMGetProtocolStartParams failed: (%d)", started);
      goto LABEL_16;
    }
    if ( (byte_1800C8404 & 8) != 0 )
    {
      v16 = *((_DWORD *)this + 24);
      LOWORD(v155) = 0;
      Buffer[0] = 0;
      if ( v16 != -1 )
        _itow_s(v16, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v155, L"RasProtocolStart(cfg=0x%x)...", v136[0]);
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v155,
          (unsigned int)&v132,
          0,
          (__int64)Buffer);
    }
    if ( (_BYTE)v151 && !strcmp_0(Str1, "****************") )
    {
      memset_0(v137, 0, 0x630u);
      v17 = *((unsigned int *)this + 2733);
      UsedDefaultChar = -2147483646;
      started = GetEntryDialParams(v18, v17, &UsedDefaultChar, v137);
      if ( started || (UsedDefaultChar & 2) == 0 )
      {
        if ( (byte_1800C8404 & 8) == 0 )
          goto LABEL_62;
        v20 = *((_DWORD *)this + 24);
        LOWORD(v155) = 0;
        Buffer[0] = 0;
        if ( v20 != -1 )
          _itow_s(v20, Buffer, 0x14u, 10);
        FormatRRASErrorString(&v155, L"Failed to get dialparams. 0x%x", started);
        goto LABEL_60;
      }
      if ( WideCharToMultiByte(0, 0x400u, WideCharStr, -1, Str1, 257, 0, 0) )
      {
        uBytes_4 = 1;
        goto LABEL_62;
      }
      started = GetLastError();
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v19 = *((_DWORD *)this + 24);
        LOWORD(v155) = 0;
        Buffer[0] = 0;
        if ( v19 != -1 )
          _itow_s(v19, Buffer, 0x14u, 10);
        FormatRRASErrorString(&v155, L"Failed to convert pwd to ansi. 0x%x", started);
LABEL_60:
        if ( (byte_1800C8404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v155,
            (unsigned int)&v132,
            0,
            (__int64)Buffer);
      }
    }
LABEL_62:
    v21 = &v153;
    v110 = *((_QWORD *)this + 12);
    v22 = &v112;
    v23 = 2147483646;
    v111[0] = *((_QWORD *)this + 15);
    v24 = 260;
    v25 = 2147483646;
    LODWORD(v109) = 0;
    do
    {
      if ( !v25 )
        break;
      if ( !*(_BYTE *)v21 )
        break;
      *v22 = *(_BYTE *)v21;
      v21 = (__int16 *)((char *)v21 + 1);
      ++v22;
      --v25;
      --v24;
    }
    while ( v24 );
    v26 = v24 == 0;
    v27 = v22 - 1;
    v28 = &v157;
    v29 = 1537;
    if ( !v26 )
      v27 = v22;
    v30 = &v113;
    *v27 = 0;
    v31 = 2147483646;
    do
    {
      if ( !v31 )
        break;
      if ( !*(_BYTE *)v28 )
        break;
      *v30 = *(_BYTE *)v28;
      v28 = (__int16 *)((char *)v28 + 1);
      ++v30;
      --v31;
      --v29;
    }
    while ( v29 );
    v32 = v30 - 1;
    v33 = &v147;
    if ( v29 )
      v32 = v30;
    v34 = 128;
    v35 = &v114;
    *v32 = 0;
    v36 = 2147483646;
    do
    {
      if ( !v36 )
        break;
      if ( !*(_BYTE *)v33 )
        break;
      *v35 = *(_BYTE *)v33;
      v33 = (__int16 *)((char *)v33 + 1);
      ++v35;
      --v36;
      --v34;
    }
    while ( v34 );
    v26 = v34 == 0;
    v37 = v35 - 1;
    v38 = &v151;
    v39 = 257;
    if ( !v26 )
      v37 = v35;
    v40 = &v115;
    *v37 = 0;
    v41 = 2147483646;
    do
    {
      if ( !v41 )
        break;
      if ( !*(_BYTE *)v38 )
        break;
      *v40 = *(_BYTE *)v38;
      v38 = (__int16 *)((char *)v38 + 1);
      ++v40;
      --v41;
      --v39;
    }
    while ( v39 );
    v26 = v39 == 0;
    v42 = v40 - 1;
    v43 = Str1;
    v44 = 257;
    if ( !v26 )
      v42 = v40;
    v45 = &v116;
    *v42 = 0;
    v46 = 2147483646;
    do
    {
      if ( !v46 )
        break;
      if ( !*v43 )
        break;
      *v45++ = *v43++;
      --v46;
      --v44;
    }
    while ( v44 );
    v26 = v44 == 0;
    v47 = v45 - 1;
    v48 = 16;
    if ( !v26 )
      v47 = v45;
    v49 = &v117;
    *v47 = 0;
    v50 = (char *)v146;
    do
    {
      if ( !v23 )
        break;
      if ( !*v50 )
        break;
      *v49++ = *v50++;
      --v23;
      --v48;
    }
    while ( v48 );
    v51 = v49 - 1;
    v52 = 4;
    if ( v48 )
      v51 = v49;
    v53 = &v120;
    *v51 = 0;
    v54 = v107;
    do
    {
      *(_OWORD *)v53 = *v54;
      *((_OWORD *)v53 + 1) = v54[1];
      *((_OWORD *)v53 + 2) = v54[2];
      *((_OWORD *)v53 + 3) = v54[3];
      *((_OWORD *)v53 + 4) = v54[4];
      *((_OWORD *)v53 + 5) = v54[5];
      *((_OWORD *)v53 + 6) = v54[6];
      v55 = v54[7];
      v54 += 8;
      *((_OWORD *)v53 + 7) = v55;
      v53 += 128;
      --v52;
    }
    while ( v52 );
    v56 = v136;
    v118 = *((_QWORD *)this + 1367);
    v57 = 8;
    v58 = &v119;
    do
    {
      v59 = v56[1];
      *(_OWORD *)v58 = *v56;
      v60 = v56[2];
      *((_OWORD *)v58 + 1) = v59;
      v61 = v56[3];
      *((_OWORD *)v58 + 2) = v60;
      v62 = v56[4];
      *((_OWORD *)v58 + 3) = v61;
      v63 = v56[5];
      *((_OWORD *)v58 + 4) = v62;
      v64 = v56[6];
      *((_OWORD *)v58 + 5) = v63;
      v65 = v56[7];
      v56 += 8;
      *((_OWORD *)v58 + 6) = v64;
      *((_OWORD *)v58 + 7) = v65;
      v58 += 128;
      --v57;
    }
    while ( v57 );
    v66 = (const void *)*((_QWORD *)this + 242);
    v67 = v56[1];
    *(_OWORD *)v58 = *v56;
    v68 = v56[2];
    *((_OWORD *)v58 + 1) = v67;
    *((_OWORD *)v58 + 2) = v68;
    v69 = *(_OWORD *)((char *)this + 10852);
    v122[567] = *((_DWORD *)this + 2740);
    v123 = *((_QWORD *)this + 1368);
    v124 = *((_QWORD *)this + 1369);
    v125 = v69;
    memcpy_0(v121, v66, 0xAE8u);
    if ( (v136[0] & 0x10000000) == 0 && (v136[0] & 0x40000000) == 0 )
      goto LABEL_158;
    UsedDefaultChar = 0;
    Key = GetKey(v70, (int)v122, 512, (int)&uBytes, 0, 0);
    if ( Key == 603 )
    {
      cbMultiByte = uBytes;
      v72 = (WCHAR *)LocalAlloc(0x40u, uBytes);
      lpMultiByteStr = v72;
      if ( !v72 )
      {
        Key = GetLastError();
        started = Key;
        goto LABEL_107;
      }
      v82 = GetKey(v73, (int)v122, 512, (int)&uBytes, v72, 0);
      v83 = uBytes;
      Key = v82;
      cbMultiByte = uBytes;
      if ( uBytes > 2 )
      {
        v84 = uBytes >> 1;
        v85 = uBytes >> 1;
        LOWORD(uBytes) = *(WCHAR *)((char *)lpMultiByteStr + uBytes - 2);
        v86 = WideCharToMultiByte(0, 0x400u, lpMultiByteStr, v85, 0, 0, 0, 0);
        cbMultiByte = v86;
        if ( !v86 )
        {
          Key = GetLastError();
          started = Key;
          RasIpsecTrace("DwGetPresharedKey: WideCharToMultiByte failed error %d");
          for ( i = lpMultiByteStr; v83; --v83 )
          {
            *(_BYTE *)i = 0;
            i = (WCHAR *)((char *)i + 1);
          }
          LocalFree(lpMultiByteStr);
          LODWORD(v83) = 0;
          cbMultiByte = 0;
LABEL_156:
          if ( !Key )
          {
            v126 = lpMultiByteStr;
            v127 = v83;
LABEL_158:
            if ( (byte_1800C8404 & 0x10) != 0 )
            {
              v96 = *((_DWORD *)this + 24);
              LOWORD(v155) = 0;
              Buffer[0] = 0;
              if ( v96 != -1 )
                _itow_s(v96, Buffer, 0x14u, 10);
              FormatRRASErrorString(
                &v155,
                L"%s: Sending protocol_start to protocol engine (hport: %ld)",
                L"DdmModernDevice::ProcessMakeCallComplete",
                *((_QWORD *)this + 12));
              if ( (byte_1800C8404 & 0x10) != 0 )
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasDdmParamTraceInfo,
                  (unsigned int)&v155,
                  (unsigned int)&v132,
                  0,
                  (__int64)Buffer);
            }
            v97 = (unsigned __int16)*((_DWORD *)this + 34);
            if ( v97 == 15 )
            {
              ((void (__fastcall *)(__int64 *))qword_1800C7518)(&v109);
            }
            else
            {
              v98 = (void (__fastcall *)(__int64 *))qword_1800C74C8[0];
              if ( v97 == 16 )
                v98 = (void (__fastcall *)(__int64 *))qword_1800C7568;
              v98(&v109);
            }
            *((_DWORD *)this + 2864) |= 0x20u;
            if ( (byte_1800C8404 & 8) != 0 )
            {
              v99 = *((_DWORD *)this + 24);
              LOWORD(v155) = 0;
              Buffer[0] = 0;
              if ( v99 != -1 )
                _itow_s(v99, Buffer, 0x14u, 10);
              FormatRRASErrorString(&v155, L"RasProtocolStart done(%d)", started);
              if ( (byte_1800C8404 & 8) != 0 )
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasDdmParamTraceError,
                  (unsigned int)&v155,
                  (unsigned int)&v132,
                  0,
                  (__int64)Buffer);
            }
            *((_DWORD *)this + 2780) = 6;
            *((_DWORD *)this + 32) = 2;
            goto LABEL_112;
          }
LABEL_107:
          if ( (byte_1800C8404 & 8) != 0 )
          {
            v74 = *((_DWORD *)this + 24);
            LOWORD(v155) = 0;
            Buffer[0] = 0;
            if ( v74 != -1 )
              _itow_s(v74, Buffer, 0x14u, 10);
            FormatRRASErrorString(&v155, L"DwGetPresharedKey failed. Error: %d", Key);
            if ( (byte_1800C8404 & 8) != 0 )
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDdmParamTraceError,
                (unsigned int)&v155,
                (unsigned int)&v132,
                0,
                (__int64)Buffer);
          }
LABEL_112:
          v6 = uBytes_4;
          goto LABEL_113;
        }
        v108 = v86;
        v88 = lpMultiByteStr;
        lpMultiByteStr = (WCHAR *)LocalAlloc(0x40u, v86);
        if ( !lpMultiByteStr )
        {
          Key = GetLastError();
          for ( j = v88; v83; --v83 )
          {
            *(_BYTE *)j = 0;
            j = (WCHAR *)((char *)j + 1);
          }
          LocalFree(v88);
LABEL_135:
          cbMultiByte = 0;
          started = Key;
          goto LABEL_107;
        }
        v105 = WideCharToMultiByte(0, 0x400u, v88, v84, (LPSTR)lpMultiByteStr, cbMultiByte, 0, &UsedDefaultChar);
        if ( !v105 )
        {
          Key = GetLastError();
          RasIpsecTrace("DwGetPresharedKey: WideCharToMultiByte failed error %d");
          for ( k = v88; v83; --v83 )
          {
            *(_BYTE *)k = 0;
            k = (WCHAR *)((char *)k + 1);
          }
          v91 = cbMultiByte;
          v92 = lpMultiByteStr;
          if ( cbMultiByte )
          {
            do
            {
              *(_BYTE *)v92 = 0;
              v92 = (WCHAR *)((char *)v92 + 1);
              --v91;
            }
            while ( v91 );
          }
          LocalFree(v88);
          LocalFree(lpMultiByteStr);
          lpMultiByteStr = 0;
          goto LABEL_135;
        }
        started = Key;
        if ( UsedDefaultChar )
        {
          RasIpsecTrace("DwGetPresharedKey: Can not convert pre-shared key Using Key as widechars");
          v93 = v108;
          v94 = lpMultiByteStr;
          do
          {
            *(_BYTE *)v94 = 0;
            v94 = (WCHAR *)((char *)v94 + 1);
            --v93;
          }
          while ( v93 );
          LocalFree(lpMultiByteStr);
          if ( (_WORD)uBytes )
          {
            LODWORD(v83) = cbMultiByte;
          }
          else
          {
            LODWORD(v83) = v83 - 2;
            cbMultiByte = v83;
          }
          lpMultiByteStr = v88;
          goto LABEL_156;
        }
        for ( m = v88; v83; --v83 )
        {
          *(_BYTE *)m = 0;
          m = (WCHAR *)((char *)m + 1);
        }
        LocalFree(v88);
        if ( !(_WORD)uBytes )
        {
          LODWORD(v83) = v105 - 1;
          cbMultiByte = v105 - 1;
          goto LABEL_156;
        }
        LODWORD(v83) = cbMultiByte;
      }
    }
    else
    {
      LODWORD(v83) = uBytes;
      cbMultiByte = uBytes;
    }
    started = Key;
    if ( !lpMultiByteStr )
      goto LABEL_107;
    goto LABEL_156;
  }
  if ( (byte_1800C8404 & 8) == 0 )
    goto LABEL_113;
  v10 = *((_DWORD *)this + 24);
  LOWORD(v155) = 0;
  Buffer[0] = 0;
  if ( v10 != -1 )
    _itow_s(v10, Buffer, 0x14u, 10);
  FormatRRASErrorString(&v155, L"SetFramingEx failed: %d", started);
LABEL_16:
  if ( (byte_1800C8404 & 8) != 0 )
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceError,
      (unsigned int)&v155,
      (unsigned int)&v132,
      0,
      (__int64)Buffer);
LABEL_113:
  v75 = v126;
  if ( v126 )
  {
    v76 = v127;
    if ( v127 )
    {
      do
      {
        *(_BYTE *)v75 = 0;
        v75 = (WCHAR *)((char *)v75 + 1);
        --v76;
      }
      while ( v76 );
    }
  }
  if ( lpMultiByteStr )
  {
    v77 = cbMultiByte;
    v78 = lpMultiByteStr;
    if ( cbMultiByte )
    {
      do
      {
        *(_BYTE *)v78 = 0;
        v78 = (WCHAR *)((char *)v78 + 1);
        --v77;
      }
      while ( v77 );
    }
    LocalFree(lpMultiByteStr);
  }
  if ( v6 )
  {
    v79 = Str1;
    v80 = 257;
    do
    {
      *v79++ = 0;
      --v80;
    }
    while ( v80 );
  }
  if ( started )
  {
    memset_0(v128, 0, 0x6D8u);
    v130 = *((_QWORD *)this + 12);
    v129 = 1;
    v131 = started;
    SendProtocolMessageToDDM(v128);
  }
  return started;
}

```

## disassembly

```asm
0x180042950  push    rbp
0x180042952  push    rbx
0x180042953  push    rsi
0x180042954  push    rdi
0x180042955  push    r12
0x180042957  push    r13
0x180042959  push    r14
0x18004295b  push    r15
0x18004295d  lea     rbp, [rsp-3F28h]
0x180042965  mov     eax, 4028h
0x18004296a  call    _alloca_probe
0x18004296f  sub     rsp, rax
0x180042972  mov     rax, cs:__security_cookie
0x180042979  xor     rax, rsp
0x18004297c  mov     [rbp+3F60h+var_50], rax
0x180042983  xorps   xmm0, xmm0
0x180042986  mov     rbx, rcx
0x180042989  xor     r13d, r13d
0x18004298c  lea     rcx, [rbp+3F60h+var_1CF0]; void *
0x180042993  xor     edx, edx; Val
0x180042995  mov     [rsp+4060h+var_4008], r13
0x18004299a  mov     r8d, 430h; Size
0x1800429a0  movups  [rbp+3F60h+var_1D20], xmm0
0x1800429a7  movups  [rbp+3F60h+var_1D10], xmm0
0x1800429ae  movups  [rbp+3F60h+var_1D00], xmm0
0x1800429b5  call    memset_0
0x1800429ba  mov     rcx, [rbx+2AA8h]
0x1800429c1  mov     [rsp+4060h+var_4010], r13d
0x1800429c6  call    cs:__imp_DDMGetRasDialParams
0x1800429cc  xor     edx, edx; Val
0x1800429ce  mov     [rsp+4060h+var_4020], r13d
0x1800429d3  mov     r8d, 1BD0h; Size
0x1800429d9  mov     dword ptr [rsp+4060h+uBytes], r13d
0x1800429de  lea     rcx, [rbp+3F60h+var_3FE0]; void *
0x1800429e2  mov     [rsp+4060h+var_3FF0], r13
0x1800429e7  mov     rsi, rax
0x1800429ea  mov     [rsp+4060h+var_3FE8], r13
0x1800429ef  call    memset_0
0x1800429f4  mov     edi, 0FFh
0x1800429f9  mov     [rbp+3F60h+var_1080], r13w
0x180042a01  mov     r8d, edi; Size
0x180042a04  lea     rcx, [rbp+3F60h+var_107E]; void *
0x180042a0b  xor     edx, edx; Val
0x180042a0d  call    memset_0
0x180042a12  mov     r8d, edi; Size
0x180042a15  mov     word ptr [rbp+3F60h+Str1], r13w
0x180042a1d  xor     edx, edx; Val
0x180042a1f  lea     rcx, [rbp+3F60h+var_118E]; void *
0x180042a26  call    memset_0
0x180042a2b  xorps   xmm0, xmm0
0x180042a2e  mov     [rbp+3F60h+var_1248], r13w
0x180042a36  movups  xmmword ptr [rbp+3F60h+var_1246], xmm0
0x180042a3d  xor     edx, edx; Val
0x180042a3f  mov     [rbp+3F60h+var_F70], r13w
0x180042a47  lea     r8d, [rdi+3]; Size
0x180042a4b  lea     rcx, [rbp+3F60h+var_F6E]; void *
0x180042a52  movups  xmmword ptr [rbp+3F60h+var_1246+0Eh], xmm0
0x180042a59  call    memset_0
0x180042a5e  xor     edx, edx; Val
0x180042a60  mov     [rbp+3F60h+var_660], r13w
0x180042a68  mov     r8d, 5FFh; Size
0x180042a6e  lea     rcx, [rbp+3F60h+var_65E]; void *
0x180042a75  call    memset_0
0x180042a7a  xor     edx, edx; Val
0x180042a7c  mov     [rbp+3F60h+var_1220], r13w
0x180042a84  lea     r8d, [r13+7Fh]; Size
0x180042a88  lea     rcx, [rbp+3F60h+var_121E]; void *
0x180042a8f  call    memset_0
0x180042a94  xor     edx, edx; Val
0x180042a96  mov     [rsp+4060h+var_4000], r13
0x180042a9b  mov     r8d, 7FCh; Size
0x180042aa1  mov     [rbp+3F60h+var_E60], r13d
0x180042aa8  lea     rcx, [rbp+3F60h+var_E5C]; void *
0x180042aaf  call    memset_0
0x180042ab4  xorps   xmm0, xmm0
0x180042ab7  mov     dword ptr [rbp+3F60h+Buffer], r13d
0x180042abe  xor     eax, eax
0x180042ac0  or      edi, 0FFFFFFFFh
0x180042ac3  test    cs:byte_1800C8404, 10h
0x180042aca  movups  [rbp+3F60h+var_126C], xmm0
0x180042ad1  mov     [rbp+3F60h+var_124C], eax
0x180042ad7  movups  [rbp+3F60h+var_125C], xmm0
0x180042ade  movups  [rbp+3F60h+var_1D30], xmm0
0x180042ae5  jz      loc_180042B70
0x180042aeb  mov     ecx, [rbx+60h]; Value
0x180042aee  mov     word ptr [rbp+3F60h+var_E60], r13w
0x180042af6  mov     [rbp+3F60h+Buffer], r13w
0x180042afe  cmp     ecx, edi
0x180042b00  jz      short loc_180042B17
0x180042b02  lea     r9d, [r13+0Ah]; Radix
0x180042b06  lea     r8d, [r13+14h]; BufferCount
0x180042b0a  lea     rdx, [rbp+3F60h+Buffer]; Buffer
0x180042b11  call    cs:__imp__itow_s
0x180042b17  mov     r9, [rbx+60h]
0x180042b1b  lea     r8, aDdmmoderndevic_0; "DdmModernDevice::ProcessMakeCallComplet"...
0x180042b22  lea     rdx, aSMakecallCompl; "%s: Makecall completed (hport: %ld)"
0x180042b29  lea     rcx, [rbp+3F60h+var_E60]
0x180042b30  call    FormatRRASErrorString
0x180042b35  test    cs:byte_1800C8404, 10h
0x180042b3c  jz      short loc_180042B70
0x180042b3e  lea     rax, [rbp+3F60h+Buffer]
0x180042b45  mov     qword ptr [rsp+4060h+cbMultiByte], rax
0x180042b4a  lea     r9, [rbp+3F60h+var_1D30]
0x180042b51  lea     r8, [rbp+3F60h+var_E60]
0x180042b58  mov     [rsp+4060h+lpMultiByteStr], r13
0x180042b5d  lea     rdx, RasDdmParamTraceInfo
0x180042b64  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180042b6b  call    McTemplateU0zjzz_EventWriteTransfer
0x180042b70  mov     eax, 640h
0x180042b75  mov     dword ptr [rsp+4060h+uBytes+4], r13d
0x180042b7a  mov     dword ptr [rbp+3F60h+var_1D20+0Ch], eax
0x180042b80  mov     r12d, r13d
0x180042b83  mov     dword ptr [rbp+3F60h+var_1D20+8], eax
0x180042b89  mov     r15, r13
0x180042b8c  mov     eax, [rbx+798h]
0x180042b92  mov     ecx, 10000000h
0x180042b97  sub     eax, 0Fh
0x180042b9a  mov     dword ptr [rbx+2B70h], 3
0x180042ba4  mov     qword ptr [rbp+3F60h+var_1D20], r13
0x180042bab  mov     qword ptr [rbp+3F60h+var_1D10], r13
0x180042bb2  mov     qword ptr [rbp+3F60h+var_1D00], r13
0x180042bb9  mov     dword ptr [rbp+3F60h+var_1D00+0Ch], edi
0x180042bbf  mov     dword ptr [rbp+3F60h+var_1D00+8], edi
0x180042bc5  cmp     eax, 1
0x180042bc8  jbe     short loc_180042BDD
0x180042bca  mov     eax, 100h
0x180042bcf  mov     dword ptr [rbp+3F60h+var_1D10+0Ch], eax
0x180042bd5  mov     dword ptr [rbp+3F60h+var_1D10+8], eax
0x180042bdb  jmp     short loc_180042BFA
0x180042bdd  mov     eax, 5DCh
0x180042be2  mov     dword ptr [rbp+3F60h+var_1D10+0Ch], ecx
0x180042be8  mov     dword ptr [rbp+3F60h+var_1D20+4], eax
0x180042bee  mov     dword ptr [rbp+3F60h+var_1D20], eax
0x180042bf4  mov     dword ptr [rbp+3F60h+var_1D10+8], ecx
0x180042bfa  mov     al, cs:byte_1800C8404
0x180042c00  and     al, 10h
0x180042c02  mov     byte ptr [rsp+4060h+var_400C], al
0x180042c06  jz      short loc_180042C46
0x180042c08  lea     rax, aSetframingex; "SetFramingEx..."
0x180042c0f  mov     [rbp+3F60h+var_1278], 20h ; ' '
0x180042c1a  mov     [rbp+3F60h+var_1280], rax
0x180042c21  lea     rdx, RasDdmTraceInfo
0x180042c28  lea     rax, [rbp+3F60h+var_1290]
0x180042c2f  mov     r9d, 2
0x180042c35  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180042c3c  mov     [rsp+4060h+lpMultiByteStr], rax
0x180042c41  call    McGenEventWrite_EventWriteTransfer
0x180042c46  mov     rax, [rbx]
0x180042c49  lea     rdx, [rbp+3F60h+var_1D20]
0x180042c50  mov     rcx, rbx
0x180042c53  mov     rax, [rax+270h]
0x180042c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c5f  mov     edi, eax
0x180042c61  mov     r14d, 101h
0x180042c67  test    eax, eax
0x180042c69  jz      loc_180042D05
0x180042c6f  test    cs:byte_1800C8404, 8
0x180042c76  jz      loc_1800434FD
0x180042c7c  mov     ecx, [rbx+60h]; Value
0x180042c7f  mov     word ptr [rbp+3F60h+var_E60], r13w
0x180042c87  mov     [rbp+3F60h+Buffer], r13w
0x180042c8f  cmp     ecx, 0FFFFFFFFh
0x180042c92  jz      short loc_180042CAB
0x180042c94  mov     r9d, 0Ah; Radix
0x180042c9a  lea     rdx, [rbp+3F60h+Buffer]; Buffer
0x180042ca1  lea     r8d, [r9+0Ah]; BufferCount
0x180042ca5  call    cs:__imp__itow_s
0x180042cab  lea     rdx, aSetframingexFa; "SetFramingEx failed: %d"
0x180042cb2  mov     r8d, edi
0x180042cb5  lea     rcx, [rbp+3F60h+var_E60]
0x180042cbc  call    FormatRRASErrorString
0x180042cc1  test    cs:byte_1800C8404, 8
0x180042cc8  jz      loc_1800434FD
0x180042cce  lea     rax, [rbp+3F60h+Buffer]
0x180042cd5  mov     qword ptr [rsp+4060h+cbMultiByte], rax
0x180042cda  lea     r9, [rbp+3F60h+var_1D30]
0x180042ce1  lea     r8, [rbp+3F60h+var_E60]
0x180042ce8  mov     [rsp+4060h+lpMultiByteStr], r13
0x180042ced  lea     rdx, RasDdmParamTraceError
0x180042cf4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180042cfb  call    McTemplateU0zjzz_EventWriteTransfer
0x180042d00  jmp     loc_1800434FD
0x180042d05  mov     rcx, [rbx+2AA8h]
0x180042d0c  lea     r8, [rbp+3F60h+var_1CF0]
0x180042d13  lea     rdx, [rsp+4060h+var_4010]
0x180042d18  call    cs:__imp_DDMUpdateProtocolConfigInfoFromEntry
0x180042d1e  mov     edi, eax
0x180042d20  test    eax, eax
0x180042d22  jz      short loc_180042D6C
0x180042d24  test    cs:byte_1800C8404, 8
0x180042d2b  jz      loc_1800434FD
0x180042d31  mov     ecx, [rbx+60h]; Value
0x180042d34  mov     word ptr [rbp+3F60h+var_E60], r13w
0x180042d3c  mov     [rbp+3F60h+Buffer], r13w
0x180042d44  cmp     ecx, 0FFFFFFFFh
0x180042d47  jz      short loc_180042D60
0x180042d49  mov     r9d, 0Ah; Radix
0x180042d4f  lea     rdx, [rbp+3F60h+Buffer]; Buffer
0x180042d56  lea     r8d, [r9+0Ah]; BufferCount
0x180042d5a  call    cs:__imp__itow_s
0x180042d60  lea     rdx, aDdmupdateproto; "DdmUpdateProtocolConfigInfoFromEntry fa"...
0x180042d67  jmp     loc_180042CB2
0x180042d6c  lea     rcx, [rsp+4060h+var_4008]
0x180042d71  call    cs:__imp_DDMComputeLuid
0x180042d77  mov     edi, eax
0x180042d79  cmp     [rsi+40Ah], r13w
0x180042d81  jnz     short loc_180042DDB
0x180042d83  test    eax, eax
0x180042d85  jz      short loc_180042DCF
0x180042d87  test    cs:byte_1800C8404, 8
0x180042d8e  jz      loc_1800434FD
0x180042d94  mov     ecx, [rbx+60h]; Value
0x180042d97  mov     word ptr [rbp+3F60h+var_E60], r13w
0x180042d9f  mov     [rbp+3F60h+Buffer], r13w
0x180042da7  cmp     ecx, 0FFFFFFFFh
0x180042daa  jz      short loc_180042DC3
0x180042dac  mov     r9d, 0Ah; Radix
0x180042db2  lea     rdx, [rbp+3F60h+Buffer]; Buffer
0x180042db9  lea     r8d, [r9+0Ah]; BufferCount
0x180042dbd  call    cs:__imp__itow_s
0x180042dc3  lea     rdx, aDdmcomputeluid; "DDMComputeLuid failed: (%d)"
0x180042dca  jmp     loc_180042CB2
0x180042dcf  mov     rax, [rsp+4060h+var_4008]
0x180042dd4  mov     [rbx+2AB8h], rax
0x180042ddb  test    [rbp+3F60h+var_1CF0], 8000h
0x180042de5  jz      short loc_180042E60
0x180042de7  mov     edx, [rsp+4060h+var_4010]
0x180042deb  lea     rax, [rbx+2AC8h]
0x180042df2  mov     rcx, [rbx+2AA8h]
0x180042df9  lea     r9, [rbx+2AC0h]
0x180042e00  lea     r8, [rbx+2AD0h]
0x180042e07  mov     [rsp+4060h+lpMultiByteStr], rax
0x180042e0c  call    cs:__imp_DDMGetEapInfo
0x180042e12  mov     edi, eax
0x180042e14  test    eax, eax
0x180042e16  jz      short loc_180042E60
0x180042e18  test    cs:byte_1800C8404, 8
0x180042e1f  jz      loc_1800434FD
0x180042e25  mov     ecx, [rbx+60h]; Value
0x180042e28  mov     word ptr [rbp+3F60h+var_E60], r13w
0x180042e30  mov     [rbp+3F60h+Buffer], r13w
0x180042e38  cmp     ecx, 0FFFFFFFFh
0x180042e3b  jz      short loc_180042E54
0x180042e3d  mov     r9d, 0Ah; Radix
0x180042e43  lea     rdx, [rbp+3F60h+Buffer]; Buffer
0x180042e4a  lea     r8d, [r9+0Ah]; BufferCount
0x180042e4e  call    cs:__imp__itow_s
0x180042e54  lea     rdx, aDdmgeteapinfoF; "DDMGetEapInfo failed: (%d)"
0x180042e5b  jmp     loc_180042CB2
0x180042e60  mov     rcx, [rbx+2AA8h]
0x180042e67  lea     rax, [rsp+4060h+var_4000]
0x180042e6c  mov     [rsp+4060h+lpUsedDefaultChar], rax
0x180042e71  lea     r9, [rbp+3F60h+var_1248]
0x180042e78  lea     rax, [rbp+3F60h+var_1220]
0x180042e7f  mov     [rsp+4060h+lpDefaultChar], rax
0x180042e84  lea     r8, [rbp+3F60h+Str1]
0x180042e8b  lea     rax, [rbp+3F60h+var_660]
0x180042e92  mov     qword ptr [rsp+4060h+cbMultiByte], rax
0x180042e97  lea     rdx, [rbp+3F60h+var_1080]
0x180042e9e  lea     rax, [rbp+3F60h+var_F70]
0x180042ea5  mov     [rsp+4060h+lpMultiByteStr], rax
0x180042eaa  call    cs:__imp_DDMGetProtocolStartParams
0x180042eb0  mov     edi, eax
0x180042eb2  test    eax, eax
0x180042eb4  jz      short loc_180042EFE
0x180042eb6  test    cs:byte_1800C8404, 8
0x180042ebd  jz      loc_1800434FD
0x180042ec3  mov     ecx, [rbx+60h]; Value
0x180042ec6  mov     word ptr [rbp+3F60h+var_E60], r13w
0x180042ece  mov     [rbp+3F60h+Buffer], r13w
0x180042ed6  cmp     ecx, 0FFFFFFFFh
0x180042ed9  jz      short loc_180042EF2
0x180042edb  mov     r9d, 0Ah; Radix
0x180042ee1  lea     rdx, [rbp+3F60h+Buffer]; Buffer
0x180042ee8  lea     r8d, [r9+0Ah]; BufferCount
0x180042eec  call    cs:__imp__itow_s
0x180042ef2  lea     rdx, aDdmgetprotocol_0; "DDMGetProtocolStartParams failed: (%d)"
0x180042ef9  jmp     loc_180042CB2
0x180042efe  or      esi, 0FFFFFFFFh
0x180042f01  test    cs:byte_1800C8404, 8
0x180042f08  jz      loc_180042F91
0x180042f0e  mov     ecx, [rbx+60h]; Value
0x180042f11  mov     word ptr [rbp+3F60h+var_E60], r13w
0x180042f19  mov     [rbp+3F60h+Buffer], r13w
0x180042f21  cmp     ecx, esi
0x180042f23  jz      short loc_180042F3C
0x180042f25  mov     r9d, 0Ah; Radix
0x180042f2b  lea     rdx, [rbp+3F60h+Buffer]; Buffer
0x180042f32  lea     r8d, [r9+0Ah]; BufferCount
0x180042f36  call    cs:__imp__itow_s
0x180042f3c  mov     r8d, [rbp+3F60h+var_1CF0]
0x180042f43  lea     rdx, aRasprotocolsta_0; "RasProtocolStart(cfg=0x%x)..."
0x180042f4a  lea     rcx, [rbp+3F60h+var_E60]
0x180042f51  call    FormatRRASErrorString
0x180042f56  test    cs:byte_1800C8404, 8
0x180042f5d  jz      short loc_180042F91
0x180042f5f  lea     rax, [rbp+3F60h+Buffer]
0x180042f66  mov     qword ptr [rsp+4060h+cbMultiByte], rax
0x180042f6b  lea     r9, [rbp+3F60h+var_1D30]
0x180042f72  lea     r8, [rbp+3F60h+var_E60]
  ... truncated ...
```
