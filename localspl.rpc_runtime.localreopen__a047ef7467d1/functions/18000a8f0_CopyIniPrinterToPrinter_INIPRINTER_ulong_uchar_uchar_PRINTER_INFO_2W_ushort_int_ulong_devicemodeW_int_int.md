# CopyIniPrinterToPrinter(_INIPRINTER *,ulong,uchar *,uchar *,_PRINTER_INFO_2W *,ushort *,int,ulong,_devicemodeW *,int,int)

- ea: `0x18000a8f0`
- end: `0x18000b5f8`
- name: `?CopyIniPrinterToPrinter@@YAPEAEPEAU_INIPRINTER@@KPEAE1PEAU_PRINTER_INFO_2W@@PEAGHKPEAU_devicemodeW@@HH@Z`
- size: `3336`
- prototype: `unsigned __int8 *__fastcall(struct _INIPRINTER *, unsigned int, unsigned __int8 *, unsigned __int8 *, struct _PRINTER_INFO_2W *, unsigned __int16 *, int, unsigned int, struct _devicemodeW *Src, int, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005ab8c`
- `0x18005afa4`

## callees

- `0x18000a8f0`
- `0x18000b600`
- `0x18000b778`
- `0x18000b870`
- `0x18000b9ec`
- `0x18000bb60`
- `0x18000bc30`
- `0x18000edc4`
- `0x180046650`
- `0x180047318`
- `0x180047330`
- `0x1800e3840`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000aecd`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000aeeb`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000aecd`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000aeeb`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x18000b2b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x18000b2b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000ad39`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000add0`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000ad39`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000add0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000b2cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000b2cb`
- `SPOOLSS!DllFreeSplStr` at `0x18000b1a2`
- `SPOOLSS!DllFreeSplStr` at `0x18000b1a2`
- `SPOOLSS!DllFreeSplMem` at `0x18000ac5e`
- `SPOOLSS!DllFreeSplMem` at `0x18000b0ae`
- `SPOOLSS!DllFreeSplMem` at `0x18000ac5e`
- `SPOOLSS!DllFreeSplMem` at `0x18000b0ae`
- `SPOOLSS!DllAllocSplMem` at `0x18000aa20`
- `SPOOLSS!DllAllocSplMem` at `0x18000b05a`
- `SPOOLSS!DllAllocSplMem` at `0x18000aa20`
- `SPOOLSS!DllAllocSplMem` at `0x18000b05a`
- `SPOOLSS!PackStrings` at `0x18000aaa0`
- `SPOOLSS!PackStrings` at `0x18000ac52`
- `SPOOLSS!PackStrings` at `0x18000b089`
- `SPOOLSS!PackStrings` at `0x18000b188`
- `SPOOLSS!PackStrings` at `0x18000b26c`
- `SPOOLSS!PackStrings` at `0x18000b4aa`
- `SPOOLSS!PackStrings` at `0x18000aaa0`
- `SPOOLSS!PackStrings` at `0x18000ac52`
- `SPOOLSS!PackStrings` at `0x18000b089`
- `SPOOLSS!PackStrings` at `0x18000b188`
- `SPOOLSS!PackStrings` at `0x18000b26c`
- `SPOOLSS!PackStrings` at `0x18000b4aa`

## string_xrefs

- `0x18000abce`: `Microsoft enhanced Point and Print compatibility driver`

## pseudocode

```c
unsigned __int8 *__fastcall CopyIniPrinterToPrinter(
        struct _INIPRINTER *a1,
        int a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        struct _PRINTER_INFO_2W *a5,
        unsigned __int16 *a6,
        int a7,
        unsigned int a8,
        struct _devicemodeW *Src,
        int a10,
        int a11)
{
  __int64 v12; // rax
  unsigned __int8 *v13; // rsi
  unsigned __int8 *v14; // r13
  unsigned __int16 *v15; // rbx
  const unsigned int near *const *v16; // r12
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rsi
  const unsigned __int16 *v20; // rax
  __int64 v21; // r8
  int v22; // edx
  bool v23; // cf
  __int64 v25; // r9
  __int64 v26; // rax
  int v27; // r9d
  int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rcx
  LPWSTR pParameters; // rax
  const unsigned int near *const *v32; // r8
  __int64 v33; // r12
  unsigned int v34; // ecx
  _WORD *v35; // rdx
  unsigned __int64 v36; // r8
  unsigned __int64 v37; // r8
  __int64 v38; // rax
  _WORD *v39; // rcx
  int v40; // ebx
  __int32 v41; // r9d
  __int32 v42; // r8d
  int v43; // ecx
  int v44; // eax
  int v45; // ebx
  __int32 v46; // r9d
  __int32 v47; // r8d
  int v48; // ecx
  int v49; // eax
  int v50; // r9d
  unsigned int near **v51; // rax
  int v52; // edx
  unsigned int near **v53; // rax
  unsigned int i; // ecx
  DWORD v55; // eax
  LONG DaylightBias; // ecx
  DWORD v57; // eax
  LONG v58; // ecx
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 *v61; // rax
  __int64 *v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // rax
  _WORD *v65; // r8
  __int64 v66; // rdx
  _WORD *v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rax
  __int64 v70; // rbx
  __int64 v71; // rdx
  DWORD Version; // eax
  int v73; // ecx
  unsigned int v74; // eax
  DWORD v75; // eax
  DWORD cJobs; // ecx
  DWORD Status; // edx
  DWORD v78; // r8d
  __int64 v79; // rax
  unsigned int v80; // [rsp+60h] [rbp-A0h] BYREF
  int v81; // [rsp+64h] [rbp-9Ch]
  _BYTE *v82; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v83; // [rsp+70h] [rbp-90h]
  _SYSTEM_INFO SystemInfo; // [rsp+78h] [rbp-88h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+A8h] [rbp-58h] BYREF
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v87; // [rsp+170h] [rbp+70h] BYREF
  __int128 v88; // [rsp+180h] [rbp+80h]
  __int128 v89; // [rsp+190h] [rbp+90h]
  __int128 v90; // [rsp+1A0h] [rbp+A0h]
  __int128 v91; // [rsp+1B0h] [rbp+B0h]
  __int128 v92; // [rsp+1C0h] [rbp+C0h]
  __int128 v93; // [rsp+1D0h] [rbp+D0h]
  __int128 v94; // [rsp+1E0h] [rbp+E0h]
  __int64 v95; // [rsp+1F0h] [rbp+F0h]
  _BYTE v96[528]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v97[1048]; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v98[1040]; // [rsp+C40h] [rbp+B40h] BYREF

  v95 = 0;
  *(_QWORD *)&SystemTime.wYear = a3;
  v12 = 544;
  if ( !a11 )
    v12 = 24;
  v13 = a3;
  v83 = a8;
  v14 = a4;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v15 = *(unsigned __int16 **)((char *)a1 + v12);
  v82 = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( a2 )
  {
    switch ( a2 )
    {
      case 1:
        v16 = (const unsigned int near *const *)L"\b";
        goto LABEL_5;
      case 2:
        v16 = &PrinterInfo2Strings;
        goto LABEL_5;
      case 3:
        v16 = &PrinterInfo3Strings;
        goto LABEL_5;
      case 4:
        v16 = &PrinterInfo4Strings;
        goto LABEL_5;
      case 5:
        v16 = &PrinterInfo5Strings;
        goto LABEL_5;
      case 6:
        v16 = &PrinterInfo6Strings;
        goto LABEL_5;
      case 7:
        v16 = &PrinterInfo7Strings;
        goto LABEL_5;
      default:
        return v14;
    }
  }
  else
  {
    v16 = &PrinterInfoStressStrings;
LABEL_5:
    v17 = *((_DWORD *)a1 + 38) | 0x40;
    v81 = v17;
    if ( a5 && (a5->Attributes & 0x800000) != 0 )
      v81 = v17 | 0x800000;
    if ( a2 == 2 )
    {
      if ( a6 )
      {
        *(_QWORD *)&v87 = a6;
        if ( (unsigned int)StrNCatBuff(v97, 1041, a6, L"\\") )
          return 0;
        *((_QWORD *)&v87 + 1) = v97;
      }
      else
      {
        *((_QWORD *)&v87 + 1) = v15;
      }
      *(_QWORD *)&v88 = *((_QWORD *)a1 + 5);
      v80 = 0;
      GetPrinterPorts(a1, 0, &v80);
      v18 = DllAllocSplMem(v80);
      v19 = v18;
      if ( v18 )
      {
        GetPrinterPorts(a1, v18, &v80);
        *((_QWORD *)&v88 + 1) = v19;
        if ( a10
          || !a6
          || (*(_DWORD *)(*((_QWORD *)a1 + 35) + 168LL) & 0x4000000) != 0
          || (*((_BYTE *)a1 + 136) & 0x10) != 0
          || (v59 = *((_QWORD *)a1 + 11), *(_DWORD *)(v59 + 236) < 4u)
          || (*(_BYTE *)(v59 + 200) & 0x20) != 0 )
        {
          v20 = (const unsigned __int16 *)*((_QWORD *)a1 + 11);
          if ( v20 )
            v20 = (const unsigned __int16 *)*((_QWORD *)v20 + 3);
        }
        else
        {
          v20 = L"Microsoft enhanced Point and Print compatibility driver";
        }
        *(_QWORD *)&v89 = v20;
        *((_QWORD *)&v89 + 1) = *((_QWORD *)a1 + 10);
        *(_QWORD *)&v90 = *((_QWORD *)a1 + 18);
        *((_QWORD *)&v90 + 1) = *((_QWORD *)a1 + 16);
        v29 = *((_QWORD *)a1 + 7);
        if ( v29 )
          v30 = *(_QWORD *)(v29 + 24);
        else
          v30 = 0;
        *((_QWORD *)&v91 + 1) = *((_QWORD *)a1 + 8);
        *(_QWORD *)&v91 = v30;
        if ( !a5 || (pParameters = a5->pParameters) == 0 )
          pParameters = (LPWSTR)*((_QWORD *)a1 + 9);
        v32 = v16;
        *(_QWORD *)&v92 = pParameters;
        v33 = *(_QWORD *)&SystemTime.wYear;
        v14 = (unsigned __int8 *)PackStrings(&v87, *(_QWORD *)&SystemTime.wYear, v32, v14);
        DllFreeSplMem(v19);
        if ( Src )
        {
          v14 = (unsigned __int8 *)((unsigned __int64)&v14[-Src->dmSize - Src->dmDriverExtra] & 0xFFFFFFFFFFFFFFF8uLL);
          *(_QWORD *)(v33 + 56) = v14;
          memcpy_0(v14, Src, Src->dmDriverExtra + (unsigned __int64)Src->dmSize);
          v34 = *((_DWORD *)a1 + 24);
          if ( a6 )
            v15 = v97;
          if ( v34 )
          {
            v35 = *(_WORD **)(v33 + 56);
            if ( v35 )
            {
              v36 = 64;
              if ( v34 < 0x40 )
                v36 = v34;
              v37 = v36 >> 1;
              if ( v37 )
              {
                v38 = 2147483646;
                do
                {
                  if ( !v38 )
                    break;
                  if ( !*v15 )
                    break;
                  *v35++ = *v15++;
                  --v38;
                  --v37;
                }
                while ( v37 );
                v39 = v35 - 1;
                if ( v37 )
                  v39 = v35;
                *v39 = 0;
              }
            }
          }
        }
        else
        {
          *(_QWORD *)(v33 + 56) = 0;
        }
        *(_DWORD *)(v33 + 104) = v81;
        *(_DWORD *)(v33 + 108) = *((_DWORD *)a1 + 28);
        *(_DWORD *)(v33 + 112) = *((_DWORD *)a1 + 29);
        memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
        v40 = *((_DWORD *)a1 + 30);
        SystemTime = 0;
        GetLocalTime(&SystemTime);
        v41 = _InterlockedExchange(&dword_18013F228, SystemTime.wHour | (SystemTime.wDay << 16));
        v42 = _InterlockedExchange(&dword_18013F220, SystemTime.wMinute);
        if ( _InterlockedExchange(&dword_18013F224, SystemTime.wMonth | (SystemTime.wYear << 16)) != (SystemTime.wMonth | (SystemTime.wYear << 16))
          || v41 != (SystemTime.wHour | (SystemTime.wDay << 16))
          || v42 != SystemTime.wMinute )
        {
          v55 = GetTimeZoneInformation(&TimeZoneInformation);
          DaylightBias = 0;
          if ( v55 == 2 )
            DaylightBias = TimeZoneInformation.DaylightBias;
          dword_18013F22C = DaylightBias;
        }
        v43 = _InterlockedExchangeAdd(&dword_18013F22C, 0) + v40;
        v44 = v43 + 1440;
        if ( v43 >= 0 )
          v44 = v43;
        *(_DWORD *)(v33 + 116) = v44;
        memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
        v45 = *((_DWORD *)a1 + 31);
        SystemTime = 0;
        GetLocalTime(&SystemTime);
        v46 = _InterlockedExchange(&dword_18013F228, SystemTime.wHour | (SystemTime.wDay << 16));
        v47 = _InterlockedExchange(&dword_18013F220, SystemTime.wMinute);
        if ( _InterlockedExchange(&dword_18013F224, SystemTime.wMonth | (SystemTime.wYear << 16)) != (SystemTime.wMonth | (SystemTime.wYear << 16))
          || v46 != (SystemTime.wHour | (SystemTime.wDay << 16))
          || v47 != SystemTime.wMinute )
        {
          v57 = GetTimeZoneInformation(&TimeZoneInformation);
          v58 = 0;
          if ( v57 == 2 )
            v58 = TimeZoneInformation.DaylightBias;
          dword_18013F22C = v58;
        }
        v48 = _InterlockedExchangeAdd(&dword_18013F22C, 0) + v45;
        v49 = v48 + 1440;
        if ( v48 >= 0 )
          v49 = v48;
        *(_DWORD *)(v33 + 120) = v49;
        if ( a5 )
        {
          cJobs = a5->cJobs;
          *(_DWORD *)(v33 + 128) = cJobs;
          Status = a5->Status;
          *(_DWORD *)(v33 + 124) = Status;
          v78 = cJobs + *((_DWORD *)a1 + 39);
          *(_DWORD *)(v33 + 128) = v78;
          v79 = *((_QWORD *)a1 + 22);
          if ( v79 && (*(_BYTE *)(v79 + 32) & 1) != 0 )
            *(_DWORD *)(v33 + 128) = v78 - 1;
          if ( (*((_BYTE *)a1 + 136) & 0x10) == 0 )
            goto LABEL_21;
          v22 = Status | 4;
        }
        else
        {
          v50 = 0;
          *(_DWORD *)(v33 + 128) = *((_DWORD *)a1 + 39);
          v51 = &ReadablePrinterStatusMappings;
          do
          {
            if ( !*(_DWORD *)v51 )
              break;
            if ( (*(_DWORD *)v51 & *((_DWORD *)a1 + 34)) != 0 )
              v50 |= *((_DWORD *)v51 + 1);
            ++v51;
          }
          while ( v51 );
          v52 = 0;
          v53 = &ReadablePrinterStatusMappingsExt;
          for ( i = 0; i < 4; i += 2 )
          {
            if ( !v53 || !*(_DWORD *)v53 )
              break;
            if ( (*(_DWORD *)v53 & *((_DWORD *)a1 + 35)) != 0 )
              v52 |= *((_DWORD *)v53 + 1);
            ++v53;
          }
          v21 = 0;
          v22 = v50 | *((_DWORD *)a1 + 80) | v52;
          v23 = *((_DWORD *)a1 + 77) != 0;
          do
          {
            if ( v23 )
            {
              v25 = *(_QWORD *)(*((_QWORD *)a1 + 39) + 8 * v21);
              if ( v25 )
              {
                v26 = *(_QWORD *)(v25 + 72);
                if ( v26 )
                {
                  v27 = *(_DWORD *)(v26 + 32);
                  if ( (v27 & 0x1000000) == 0 )
                  {
                    if ( (v27 & 0x10) != 0 )
                      v22 |= 0x10u;
                    v28 = v22 | 0x80;
                    if ( (v27 & 8) == 0 )
                      v28 = v22;
                    v22 = v28;
                    if ( (v27 & 4) != 0 )
                      v22 = v28 | 2;
                  }
                }
              }
            }
            v21 = (unsigned int)(v21 + 1);
            v23 = (unsigned int)v21 < *((_DWORD *)a1 + 77);
          }
          while ( (unsigned int)v21 <= *((_DWORD *)a1 + 77) );
        }
        *(_DWORD *)(v33 + 124) = v22;
LABEL_21:
        *(_DWORD *)(v33 + 132) = *((_DWORD *)a1 + 40);
        if ( a7 )
          return CopyIniPrinterSecurityDescriptor(
                   *((PSECURITY_DESCRIPTOR *)a1 + 24),
                   2u,
                   (unsigned __int8 *)v33,
                   v14,
                   v83);
        *(_QWORD *)(v33 + 96) = 0;
        return v14;
      }
      return 0;
    }
    switch ( a2 )
    {
      case 0:
        if ( a6 )
        {
          v74 = StringCchPrintfW(v97, 0x411u, L"%ws\\%ws", a6, v15);
          if ( !(unsigned int)BoolFromHResult(v74) )
            return 0;
          *((_QWORD *)&v87 + 1) = a6;
          *(_QWORD *)&v87 = v97;
        }
        else
        {
          v87 = (unsigned __int64)v15;
        }
        v14 = (unsigned __int8 *)PackStrings(&v87, v13, v16, v14);
        *((_DWORD *)v13 + 4) = *((_DWORD *)a1 + 39);
        *((_DWORD *)v13 + 5) = *((_DWORD *)a1 + 54);
        *((_DWORD *)v13 + 6) = *((_DWORD *)a1 + 56);
        *((_DWORD *)v13 + 23) = *((_DWORD *)a1 + 57);
        *(_OWORD *)(v13 + 28) = *(_OWORD *)((char *)a1 + 232);
        *((_DWORD *)v13 + 11) = *((_DWORD *)a1 + 62);
        *((_DWORD *)v13 + 12) = *((_DWORD *)a1 + 63);
        Version = GetVersion();
        *((_DWORD *)v13 + 14) = 1;
        *((_DWORD *)v13 + 13) = Version;
        GetSystemInfo(&SystemInfo);
        *((_DWORD *)v13 + 22) = SystemInfo.dwProcessorType;
        *((_DWORD *)v13 + 21) = SystemInfo.dwNumberOfProcessors;
        *((_DWORD *)v13 + 15) = *((_DWORD *)a1 + 64);
        *((_DWORD *)v13 + 16) = *((_DWORD *)a1 + 65);
        *((_DWORD *)v13 + 17) = *((_DWORD *)a1 + 4);
        *((_DWORD *)v13 + 18) = *((_DWORD *)a1 + 66);
        *((_DWORD *)v13 + 19) = *((_DWORD *)a1 + 67);
        *((_DWORD *)v13 + 20) = *((_DWORD *)a1 + 68);
        *((_DWORD *)v13 + 24) = *((_DWORD *)a1 + 76);
        *((_DWORD *)v13 + 25) = *((_DWORD *)a1 + 73);
        *((_DWORD *)v13 + 26) = MapToPrinterQueueStatus(a1, 0);
        *((_DWORD *)v13 + 27) = *(_DWORD *)(*((_QWORD *)a1 + 35) + 200LL);
        v73 = *(_DWORD *)(*((_QWORD *)a1 + 35) + 204LL);
        *((_WORD *)v13 + 58) = SystemInfo.wProcessorArchitecture;
        *((_WORD *)v13 + 59) = SystemInfo.wProcessorLevel;
        *((_DWORD *)v13 + 28) = v73;
        *((_DWORD *)v13 + 30) = *((_DWORD *)a1 + 92);
        break;
      case 1:
        v60 = *((_QWORD *)a1 + 18);
        v61 = &szNull;
        v62 = &szNull;
        if ( a6 )
        {
          v71 = *((_QWORD *)a1 + 11);
          if ( v71 )
            v61 = *(__int64 **)(v71 + 24);
          if ( (unsigned int)StrCatUseBufferOrAlloc(v96, 260, &v82, a6, L"\\", v15, L",", v61, L",")
            || (unsigned int)StrNCatBuff(v98, 519, a6, L"\\") )
          {
            return 0;
          }
          v13 = *(unsigned __int8 **)&SystemTime.wYear;
        }
        else
        {
          if ( v60 )
            v62 = (__int64 *)*((_QWORD *)a1 + 18);
          v63 = *((_QWORD *)a1 + 11);
          if ( v63 )
            v61 = *(__int64 **)(v63 + 24);
          if ( (unsigned int)StrCatUseBufferOrAlloc(v96, 260, &v82, v15, L",", v61, L",", v62, 0) )
            return 0;
          v64 = 2147483646;
          v65 = v98;
          v66 = 519;
          do
          {
            if ( !v64 )
              break;
            if ( !*v15 )
              break;
            *v65++ = *v15++;
            --v64;
            --v66;
          }
          while ( v66 );
          v67 = v65 - 1;
          if ( v66 )
            v67 = v65;
          *v67 = 0;
          v68 = 2147942522LL;
          if ( v66 )
            v68 = 0;
          if ( !(unsigned int)BoolFromHResult(v68) )
            return 0;
        }
        *(_QWORD *)&v87 = v82;
        *((_QWORD *)&v87 + 1) = v98;
        *(_QWORD *)&v88 = *((_QWORD *)a1 + 10);
        v14 = (unsigned __int8 *)PackStrings(&v87, v13, v16, v14);
        if ( v96 != v82 )
          DllFreeSplStr(v82);
        *(_DWORD *)v13 = 0x800000;
        break;
      case 3:
        v14 = CopyIniPrinterSecurityDescriptor(*((PSECURITY_DESCRIPTOR *)a1 + 24), 3u, a3, a4, a8);
        break;
      case 4:
        if ( a6 )
        {
          if ( (unsigned int)StrNCatBuff(v97, 1041, a6, L"\\") )
            return 0;
          *((_QWORD *)&v87 + 1) = a6;
          *(_QWORD *)&v87 = v97;
        }
        else
        {
          v87 = (unsigned __int64)v15;
        }
        v14 = (unsigned __int8 *)PackStrings(&v87, v13, v16, v14);
        *((_DWORD *)v13 + 4) = v81;
        break;
      case 5:
        if ( a6 )
        {
          if ( (unsigned int)StrNCatBuff(v97, 1041, a6, L"\\") )
            return 0;
          *(_QWORD *)&v87 = v97;
        }
        else
        {
          *(_QWORD *)&v87 = v15;
        }
        v80 = 0;
        GetPrinterPorts(a1, 0, &v80);
        v69 = DllAllocSplMem(v80);
        v70 = v69;
        if ( !v69 )
          return 0;
        GetPrinterPorts(a1, v69, &v80);
        *((_QWORD *)&v87 + 1) = v70;
        v14 = (unsigned __int8 *)PackStrings(&v87, v13, v16, v14);
        *((_DWORD *)v13 + 4) = v81;
        *((_DWORD *)v13 + 5) = *((_DWORD *)a1 + 81);
        *((_DWORD *)v13 + 6) = *((_DWORD *)a1 + 82);
        DllFreeSplMem(v70);
        break;
      case 6:
        if ( a5 )
        {
          v75 = a5->Status;
          *(_DWORD *)a3 = v75;
          if ( (*((_BYTE *)a1 + 136) & 0x10) != 0 )
            *(_DWORD *)a3 = v75 | 4;
        }
        else
        {
          *(_DWORD *)a3 = MapToPrinterQueueStatus(a1, 0);
        }
        break;
      case 7:
        *(_QWORD *)&v87 = *((_QWORD *)a1 + 42);
        v14 = (unsigned __int8 *)PackStrings(&v87, a3, v16, a4);
        if ( (*(_DWORD *)(*((_QWORD *)a1 + 35) + 168LL) & 0x4000000) != 0 )
        {
          *((_DWORD *)v13 + 2) = *((_DWORD *)a1 + 93);
        }
        else if ( (*((_DWORD *)a1 + 38) & 0x2000) != 0 )
        {
          *((_DWORD *)v13 + 2) = 1;
          if ( !*((_QWORD *)a1 + 42) || *((_DWORD *)a1 + 86) || *((_DWORD *)a1 + 97) )
            *((_DWORD *)v13 + 2) = -2147483647;
        }
        else
        {
          *((_DWORD *)v13 + 2) = 4;
          if ( *((_QWORD *)a1 + 42)
            || (*((_DWORD *)a1 + 86) & 0x20000000) != 0
            || (*((_DWORD *)a1 + 97) & 0x20000000) != 0 )
          {
            *((_DWORD *)v13 + 2) = -2147483644;
          }
        }
        break;
      default:
        return v14;
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18000a8f0  push    rbp
0x18000a8f2  push    rbx
0x18000a8f3  push    rsi
0x18000a8f4  push    rdi
0x18000a8f5  push    r12
0x18000a8f7  push    r13
0x18000a8f9  push    r14
0x18000a8fb  push    r15
0x18000a8fd  lea     rbp, [rsp-0F68h]
0x18000a905  mov     eax, 1068h
0x18000a90a  call    _alloca_probe
0x18000a90f  sub     rsp, rax
0x18000a912  mov     rax, cs:__security_cookie
0x18000a919  xor     rax, rsp
0x18000a91c  mov     [rbp+0FA0h+var_50], rax
0x18000a923  mov     r15, [rbp+0FA0h+arg_28]
0x18000a92a  xorps   xmm0, xmm0
0x18000a92d  mov     r14, [rbp+0FA0h+Src]
0x18000a934  xor     eax, eax
0x18000a936  cmp     [rbp+0FA0h+arg_50], 0
0x18000a93d  mov     rdi, rcx
0x18000a940  mov     [rbp+0FA0h+var_EB0], rax
0x18000a947  mov     ecx, 18h
0x18000a94c  mov     qword ptr [rbp+0FA0h+SystemTime.wYear], r8
0x18000a950  mov     eax, 220h
0x18000a955  cmovz   eax, ecx
0x18000a958  mov     rsi, r8
0x18000a95b  mov     r8d, [rbp+0FA0h+arg_38]
0x18000a962  xor     r10d, r10d
0x18000a965  mov     [rsp+10A0h+var_1030], r8d
0x18000a96a  mov     r13, r9
0x18000a96d  lea     r9, __ImageBase
0x18000a974  movups  [rbp+0FA0h+var_F30], xmm0
0x18000a978  movups  [rbp+0FA0h+var_F20], xmm0
0x18000a97f  movups  [rbp+0FA0h+var_F10], xmm0
0x18000a986  movups  [rbp+0FA0h+var_F00], xmm0
0x18000a98d  movups  [rbp+0FA0h+var_EF0], xmm0
0x18000a994  movups  [rbp+0FA0h+var_EE0], xmm0
0x18000a99b  movups  [rbp+0FA0h+var_ED0], xmm0
0x18000a9a2  movups  [rbp+0FA0h+var_EC0], xmm0
0x18000a9a9  mov     rbx, [rax+rdi]
0x18000a9ad  mov     [rsp+10A0h+var_1038], r10
0x18000a9b2  movups  xmmword ptr [rsp+10A0h+SystemInfo], xmm0
0x18000a9b7  movups  xmmword ptr [rbp+0FA0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000a9bb  movups  xmmword ptr [rbp+0FA0h+SystemInfo.dwNumberOfProcessors], xmm0
0x18000a9bf  test    edx, edx
0x18000a9c1  jnz     loc_18000AB46
0x18000a9c7  lea     r12, ?PrinterInfoStressStrings@@3QBKB; ulong const near * const PrinterInfoStressStrings
0x18000a9ce  mov     eax, [rdi+98h]
0x18000a9d4  mov     rcx, [rbp+0FA0h+arg_20]
0x18000a9db  or      eax, 40h
0x18000a9de  mov     [rsp+10A0h+var_103C], eax
0x18000a9e2  test    rcx, rcx
0x18000a9e5  jnz     loc_18000B3F0
0x18000a9eb  cmp     edx, 2
0x18000a9ee  jnz     short loc_18000AA6C
0x18000a9f0  test    r15, r15
0x18000a9f3  jnz     loc_18000B394
0x18000a9f9  mov     qword ptr [rbp+0FA0h+var_F30+8], rbx
0x18000a9fd  mov     rax, [rdi+28h]
0x18000aa01  lea     r8, [rsp+10A0h+var_1040]
0x18000aa06  xor     edx, edx
0x18000aa08  mov     qword ptr [rbp+0FA0h+var_F20], rax
0x18000aa0f  mov     rcx, rdi
0x18000aa12  mov     [rsp+10A0h+var_1040], r10d
0x18000aa17  call    GetPrinterPorts
0x18000aa1c  mov     ecx, [rsp+10A0h+var_1040]
0x18000aa20  call    cs:__imp_DllAllocSplMem
0x18000aa26  mov     rsi, rax
0x18000aa29  test    rax, rax
0x18000aa2c  jz      loc_18000B021
0x18000aa32  lea     r8, [rsp+10A0h+var_1040]
0x18000aa37  mov     rdx, rax
0x18000aa3a  mov     rcx, rdi
0x18000aa3d  call    GetPrinterPorts
0x18000aa42  cmp     [rbp+0FA0h+arg_48], 0
0x18000aa49  mov     qword ptr [rbp+0FA0h+var_F20+8], rsi
0x18000aa50  jz      loc_18000AF18
0x18000aa56  mov     rax, [rdi+58h]
0x18000aa5a  test    rax, rax
0x18000aa5d  jz      loc_18000B471
0x18000aa63  mov     rax, [rax+18h]
0x18000aa67  jmp     loc_18000ABD5
0x18000aa6c  cmp     edx, 7; switch 8 cases
0x18000aa6f  ja      def_18000AA80; jumptable 000000018000AA80 default case, case 2
0x18000aa75  mov     eax, ds:(jpt_18000AA80 - 180000000h)[r9+rdx*4]
0x18000aa7d  add     rax, r9
0x18000aa80  jmp     rax; switch jump
0x18000aa82  test    r15, r15; jumptable 000000018000AA80 case 4
0x18000aa85  jnz     loc_18000B1BF
0x18000aa8b  mov     qword ptr [rbp+0FA0h+var_F30], rbx
0x18000aa8f  mov     qword ptr [rbp+0FA0h+var_F30+8], r10
0x18000aa93  mov     r9, r13
0x18000aa96  lea     rcx, [rbp+0FA0h+var_F30]
0x18000aa9a  mov     r8, r12
0x18000aa9d  mov     rdx, rsi
0x18000aaa0  call    cs:__imp_PackStrings
0x18000aaa6  mov     r13, rax
0x18000aaa9  mov     eax, [rsp+10A0h+var_103C]
0x18000aaad  mov     [rsi+10h], eax
0x18000aab0  jmp     short def_18000AA80; jumptable 000000018000AA80 default case, case 2
0x18000aab2  or      edx, [rdi+140h]
0x18000aab8  xor     r8d, r8d
0x18000aabb  or      edx, r9d
0x18000aabe  cmp     r8d, [rdi+134h]
0x18000aac5  jb      loc_18000AB67
0x18000aacb  inc     r8d
0x18000aace  cmp     r8d, [rdi+134h]
0x18000aad5  jbe     short loc_18000AAC5
0x18000aad7  mov     [r12+7Ch], edx
0x18000aadc  cmp     [rbp+0FA0h+arg_30], 0
0x18000aae3  mov     eax, [rdi+0A0h]
0x18000aae9  mov     [r12+84h], eax
0x18000aaf1  jnz     short loc_18000AB22
0x18000aaf3  mov     qword ptr [r12+60h], 0
0x18000aafc  mov     rax, r13; jumptable 000000018000AA80 default case, case 2
0x18000aaff  mov     rcx, [rbp+0FA0h+var_50]
0x18000ab06  xor     rcx, rsp; StackCookie
0x18000ab09  call    __security_check_cookie
0x18000ab0e  add     rsp, 1068h
0x18000ab15  pop     r15
0x18000ab17  pop     r14
0x18000ab19  pop     r13
0x18000ab1b  pop     r12
0x18000ab1d  pop     rdi
0x18000ab1e  pop     rsi
0x18000ab1f  pop     rbx
0x18000ab20  pop     rbp
0x18000ab21  retn
0x18000ab22  mov     eax, [rsp+10A0h+var_1030]
0x18000ab26  mov     r9, r13; unsigned __int8 *
0x18000ab29  mov     rcx, [rdi+0C0h]; pSecurityDescriptor
0x18000ab30  mov     r8, r12; unsigned __int8 *
0x18000ab33  mov     edx, 2; unsigned int
0x18000ab38  mov     [rsp+10A0h+var_1080], eax; unsigned int
0x18000ab3c  call    ?CopyIniPrinterSecurityDescriptor@@YAPEAEPEAXKPEAE1K@Z; CopyIniPrinterSecurityDescriptor(void *,ulong,uchar *,uchar *,ulong)
0x18000ab41  mov     r13, rax
0x18000ab44  jmp     short def_18000AA80; jumptable 000000018000AA80 default case, case 2
0x18000ab46  lea     eax, [rdx-1]; switch 7 cases
0x18000ab49  cmp     eax, 6
0x18000ab4c  ja      short def_18000AA80; jumptable 000000018000AA80 default case, case 2
0x18000ab4e  mov     eax, ds:(jpt_18000AB59 - 180000000h)[r9+rax*4]
0x18000ab56  add     rax, r9
0x18000ab59  jmp     rax; switch jump
0x18000ab5b  lea     r12, ?PrinterInfo2Strings@@3QBKB; jumptable 000000018000AB59 case 2
0x18000ab62  jmp     loc_18000A9CE
0x18000ab67  mov     rax, [rdi+138h]
0x18000ab6e  mov     r9, [rax+r8*8]
0x18000ab72  test    r9, r9
0x18000ab75  jz      loc_18000AACB
0x18000ab7b  mov     rax, [r9+48h]
0x18000ab7f  test    rax, rax
0x18000ab82  jz      loc_18000AACB
0x18000ab88  mov     r9d, [rax+20h]
0x18000ab8c  bt      r9d, 18h
0x18000ab91  jb      loc_18000AACB
0x18000ab97  test    r9b, 10h
0x18000ab9b  jz      short loc_18000ABA0
0x18000ab9d  or      edx, 10h
0x18000aba0  mov     ecx, edx
0x18000aba2  bts     ecx, 7
0x18000aba6  test    r9b, 8
0x18000abaa  cmovz   ecx, edx
0x18000abad  mov     edx, ecx
0x18000abaf  test    r9b, 4
0x18000abb3  jz      loc_18000AACB
0x18000abb9  or      edx, 2
0x18000abbc  jmp     loc_18000AACB
0x18000abc1  test    byte ptr [rax+0C8h], 20h
0x18000abc8  jnz     loc_18000AA56
0x18000abce  lea     rax, ?gszMUDDriverName@@3QBGB; "Microsoft enhanced Point and Print comp"...
0x18000abd5  mov     qword ptr [rbp+0FA0h+var_F10], rax
0x18000abdc  mov     rax, [rdi+50h]
0x18000abe0  mov     qword ptr [rbp+0FA0h+var_F10+8], rax
0x18000abe7  mov     rax, [rdi+90h]
0x18000abee  mov     qword ptr [rbp+0FA0h+var_F00], rax
0x18000abf5  mov     rax, [rdi+80h]
0x18000abfc  mov     qword ptr [rbp+0FA0h+var_F00+8], rax
0x18000ac03  mov     rax, [rdi+38h]
0x18000ac07  test    rax, rax
0x18000ac0a  jz      loc_18000AF11
0x18000ac10  mov     rcx, [rax+18h]
0x18000ac14  mov     rax, [rdi+40h]
0x18000ac18  mov     qword ptr [rbp+0FA0h+var_EF0+8], rax
0x18000ac1f  mov     rax, [rbp+0FA0h+arg_20]
0x18000ac26  mov     qword ptr [rbp+0FA0h+var_EF0], rcx
0x18000ac2d  test    rax, rax
0x18000ac30  jnz     loc_18000B54C
0x18000ac36  mov     rax, [rdi+48h]
0x18000ac3a  mov     r8, r12
0x18000ac3d  mov     qword ptr [rbp+0FA0h+var_EE0], rax
0x18000ac44  mov     r12, qword ptr [rbp+0FA0h+SystemTime.wYear]
0x18000ac48  lea     rcx, [rbp+0FA0h+var_F30]
0x18000ac4c  mov     rdx, r12
0x18000ac4f  mov     r9, r13
0x18000ac52  call    cs:__imp_PackStrings
0x18000ac58  mov     rcx, rsi
0x18000ac5b  mov     r13, rax
0x18000ac5e  call    cs:__imp_DllFreeSplMem
0x18000ac64  test    r14, r14
0x18000ac67  jz      loc_18000B200
0x18000ac6d  movzx   eax, word ptr [r14+44h]
0x18000ac72  mov     rdx, r14; Src
0x18000ac75  sub     r13, rax
0x18000ac78  movzx   eax, word ptr [r14+46h]
0x18000ac7d  sub     r13, rax
0x18000ac80  and     r13, 0FFFFFFFFFFFFFFF8h
0x18000ac84  mov     [r12+38h], r13
0x18000ac89  mov     rcx, r13; void *
0x18000ac8c  movzx   r8d, word ptr [r14+44h]
0x18000ac91  movzx   eax, word ptr [r14+46h]
0x18000ac96  add     r8, rax; Size
0x18000ac99  call    memcpy_0
0x18000ac9e  mov     ecx, [rdi+60h]
0x18000aca1  test    r15, r15
0x18000aca4  jnz     loc_18000B029
0x18000acaa  test    ecx, ecx
0x18000acac  jz      short loc_18000AD01
0x18000acae  mov     rdx, [r12+38h]
0x18000acb3  test    rdx, rdx
0x18000acb6  jz      short loc_18000AD01
0x18000acb8  mov     r8d, 40h ; '@'
0x18000acbe  cmp     ecx, r8d
0x18000acc1  cmovb   r8d, ecx
0x18000acc5  shr     r8, 1
0x18000acc8  jz      short loc_18000AD01
0x18000acca  mov     eax, 7FFFFFFEh
0x18000accf  nop
0x18000acd0  test    rax, rax
0x18000acd3  jz      short loc_18000ACF1
0x18000acd5  movzx   ecx, word ptr [rbx]
0x18000acd8  test    cx, cx
0x18000acdb  jz      short loc_18000ACF1
0x18000acdd  mov     [rdx], cx
0x18000ace0  add     rbx, 2
0x18000ace4  add     rdx, 2
0x18000ace8  dec     rax
0x18000aceb  sub     r8, 1
0x18000acef  jnz     short loc_18000ACD0
0x18000acf1  test    r8, r8
0x18000acf4  lea     rcx, [rdx-2]
0x18000acf8  cmovnz  rcx, rdx
0x18000acfc  xor     eax, eax
0x18000acfe  mov     [rcx], ax
0x18000ad01  mov     eax, [rsp+10A0h+var_103C]
0x18000ad05  lea     rcx, [rbp+0FA0h+TimeZoneInformation]; void *
0x18000ad09  mov     [r12+68h], eax
0x18000ad0e  xor     edx, edx; Val
0x18000ad10  mov     eax, [rdi+70h]
0x18000ad13  mov     r8d, 0ACh; Size
0x18000ad19  mov     [r12+6Ch], eax
0x18000ad1e  mov     eax, [rdi+74h]
0x18000ad21  mov     [r12+70h], eax
0x18000ad26  call    memset_0
0x18000ad2b  mov     ebx, [rdi+78h]
0x18000ad2e  lea     rcx, [rbp+0FA0h+SystemTime]; lpSystemTime
0x18000ad32  xorps   xmm0, xmm0
0x18000ad35  movups  xmmword ptr [rbp+0FA0h+SystemTime.wYear], xmm0
0x18000ad39  call    cs:__imp_GetLocalTime
0x18000ad3f  movzx   eax, [rbp+0FA0h+SystemTime.wMonth]
0x18000ad43  movzx   ecx, [rbp+0FA0h+SystemTime.wYear]
0x18000ad47  movzx   edx, [rbp+0FA0h+SystemTime.wDay]
0x18000ad4b  movzx   r10d, [rbp+0FA0h+SystemTime.wMinute]
0x18000ad50  shl     ecx, 10h
0x18000ad53  mov     r8d, r10d
0x18000ad56  or      ecx, eax
0x18000ad58  shl     edx, 10h
0x18000ad5b  movzx   eax, [rbp+0FA0h+SystemTime.wHour]
0x18000ad5f  or      edx, eax
0x18000ad61  mov     eax, ecx
0x18000ad63  xchg    eax, cs:dword_18013F224
0x18000ad69  mov     r9d, edx
0x18000ad6c  xchg    r9d, cs:dword_18013F228
0x18000ad73  xchg    r8d, cs:dword_18013F220
0x18000ad7a  cmp     eax, ecx
0x18000ad7c  jnz     loc_18000AEC9
0x18000ad82  cmp     r9d, edx
0x18000ad85  jnz     loc_18000AEC9
0x18000ad8b  cmp     r8d, r10d
0x18000ad8e  jnz     loc_18000AEC9
0x18000ad94  xor     eax, eax
0x18000ad96  lock xadd cs:dword_18013F22C, eax
0x18000ad9e  lea     ecx, [rax+rbx]
0x18000ada1  mov     r8d, 0ACh; Size
0x18000ada7  test    ecx, ecx
0x18000ada9  lea     eax, [rcx+5A0h]
0x18000adaf  cmovns  eax, ecx
0x18000adb2  xor     edx, edx; Val
0x18000adb4  lea     rcx, [rbp+0FA0h+TimeZoneInformation]; void *
0x18000adb8  mov     [r12+74h], eax
0x18000adbd  call    memset_0
0x18000adc2  mov     ebx, [rdi+7Ch]
0x18000adc5  lea     rcx, [rbp+0FA0h+SystemTime]; lpSystemTime
0x18000adc9  xorps   xmm0, xmm0
0x18000adcc  movups  xmmword ptr [rbp+0FA0h+SystemTime.wYear], xmm0
0x18000add0  call    cs:__imp_GetLocalTime
0x18000add6  movzx   eax, [rbp+0FA0h+SystemTime.wMonth]
0x18000adda  movzx   ecx, [rbp+0FA0h+SystemTime.wYear]
0x18000adde  movzx   edx, [rbp+0FA0h+SystemTime.wDay]
0x18000ade2  movzx   r10d, [rbp+0FA0h+SystemTime.wMinute]
  ... truncated ...
```
