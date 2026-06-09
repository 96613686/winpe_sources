# CreateV4DriverEntry(_INIVERSION *,_INIENVIRONMENT *,_INISPOOLER *,_PSETUP_LOCAL_DATA *,_INIDRIVER *)

- ea: `0x1800bf1e0`
- end: `0x1800bfb87`
- name: `?CreateV4DriverEntry@@YAPEAU_INIDRIVER@@PEAU_INIVERSION@@PEAU_INIENVIRONMENT@@PEAU_INISPOOLER@@PEAU_PSETUP_LOCAL_DATA@@PEAU1@@Z`
- size: `2471`
- prototype: `struct _INIDRIVER *__usercall@<rax>(struct _INIVERSION *@<rcx>, struct _INIENVIRONMENT *@<rdx>, struct _INISPOOLER *@<r8>, struct _PSETUP_LOCAL_DATA *@<r9>, struct _INIDRIVER *)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800bdf84`
- `0x1800beae8`

## callees

- `0x180008730`
- `0x180011f00`
- `0x1800166b4`
- `0x18001683c`
- `0x18001fb10`
- `0x180020d94`
- `0x180020dd0`
- `0x180033734`
- `0x18003ea2c`
- `0x18003fd40`
- `0x180046650`
- `0x180047318`
- `0x18006aa20`
- `0x18006b2a4`
- `0x18006fb94`
- `0x18007342c`
- `0x18007405c`
- `0x1800bf1e0`
- `0x1800c1a6c`
- `0x1800ccbd8`
- `0x1800d020c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800bf5b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800bf646`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800bf5b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800bf646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf86b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf86b`
- `SPOOLSS!DllFreeSplMem` at `0x1800bf8a4`
- `SPOOLSS!DllFreeSplMem` at `0x1800bf8a4`
- `SPOOLSS!DllAllocSplMem` at `0x1800bf238`
- `SPOOLSS!DllAllocSplMem` at `0x1800bf6d1`
- `SPOOLSS!DllAllocSplMem` at `0x1800bf716`
- `SPOOLSS!DllAllocSplMem` at `0x1800bf852`
- `SPOOLSS!DllAllocSplMem` at `0x1800bf238`
- `SPOOLSS!DllAllocSplMem` at `0x1800bf6d1`
- `SPOOLSS!DllAllocSplMem` at `0x1800bf716`
- `SPOOLSS!DllAllocSplMem` at `0x1800bf852`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bf3bb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bf3bb`

## string_xrefs

- `0x1800bf259`: `CreateV4DriverEntry`
- `0x1800bf738`: `CreateV4DriverEntry`
- `0x1800bf7f3`: `CreateV4DriverEntry`
- `0x1800bf87e`: `CreateV4DriverEntry`
- `0x1800bf8e2`: `CreateV4DriverEntry`
- `0x1800bf98a`: `CreateV4DriverEntry`
- `0x1800bfa67`: `CreateV4DriverEntry`
- `0x1800bf983`: `Driver '%ws' does not have a pipelineconfig file`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _INIDRIVER *__fastcall CreateV4DriverEntry(
        struct _INIVERSION *a1,
        struct _INIENVIRONMENT *a2,
        struct _INISPOOLER *a3,
        struct _PSETUP_LOCAL_DATA *a4,
        struct _INIDRIVER *a5)
{
  struct _INIVERSION *v6; // r13
  struct _INIDRIVER *v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rbx
  DWORD LastError; // eax
  char v12; // r12
  _OWORD *v13; // rcx
  struct _INIDRIVER *v14; // rax
  __int64 v15; // rdx
  int v16; // ecx
  __int64 v17; // r8
  const unsigned __int16 *v18; // rdx
  int updated; // edi
  wchar_t *v20; // r10
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // r8
  NCoreLibrary *v26; // r15
  const unsigned __int16 *v27; // r13
  int v28; // eax
  unsigned int v29; // r15d
  wchar_t *v30; // r12
  wchar_t *v31; // rax
  bool v32; // zf
  wchar_t *v33; // r9
  NCoreLibrary::TString *v34; // rcx
  __int64 v35; // rax
  unsigned int v36; // eax
  unsigned int v37; // edi
  void *v38; // rax
  int MultiSZLen; // eax
  unsigned int v40; // r15d
  void *v41; // rax
  DWORD v42; // eax
  __int64 v43; // r8
  __int64 v44; // r8
  unsigned int v45; // edi
  __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // rax
  DWORD v49; // eax
  NCoreLibrary::TMultiString *v50; // rcx
  const void *v51; // rdx
  __int64 v52; // r8
  int v53; // r12d
  int v54; // r15d
  struct SplLogType *v55; // rax
  __int64 v56; // r10
  __int64 v57; // r11
  __int64 v58; // rax
  __int64 v59; // rcx
  _QWORD *v60; // rdi
  __int64 v61; // rax
  char v62; // [rsp+30h] [rbp-D0h]
  int v63; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 *v64; // [rsp+38h] [rbp-C8h] BYREF
  struct _INIVERSION *v65; // [rsp+40h] [rbp-C0h]
  wchar_t *Context; // [rsp+48h] [rbp-B8h] BYREF
  struct _INISPOOLER *v67; // [rsp+50h] [rbp-B0h]
  struct _INIENVIRONMENT *v68; // [rsp+58h] [rbp-A8h]
  int v69; // [rsp+60h] [rbp-A0h] BYREF
  void *v70; // [rsp+68h] [rbp-98h]
  int v71; // [rsp+70h] [rbp-90h]
  int v72; // [rsp+78h] [rbp-88h] BYREF
  __int64 v73; // [rsp+80h] [rbp-80h]
  int v74; // [rsp+88h] [rbp-78h]
  _BYTE v75[24]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v76[24]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v77[32]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[40]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t String[344]; // [rsp+130h] [rbp+30h] BYREF

  v67 = a3;
  v68 = a2;
  v6 = a1;
  v65 = a1;
  v7 = a5;
  v63 = 0;
  v8 = DllAllocSplMem(312);
  v9 = v8;
  if ( !v8 )
  {
    LastError = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreateV4DriverEntry",
      L"Failed to allocate %u bytes of memory for INIDRIVER: %d",
      312,
      LastError);
    return 0;
  }
  v12 = 0;
  v62 = 0;
  if ( a5 && *((_DWORD *)a5 + 59) >= 4u )
  {
    v12 = 1;
    v62 = 1;
    v13 = (_OWORD *)v8;
    v14 = a5;
    v15 = 2;
    do
    {
      *v13 = *(_OWORD *)v14;
      v13[1] = *((_OWORD *)v14 + 1);
      v13[2] = *((_OWORD *)v14 + 2);
      v13[3] = *((_OWORD *)v14 + 3);
      v13[4] = *((_OWORD *)v14 + 4);
      v13[5] = *((_OWORD *)v14 + 5);
      v13[6] = *((_OWORD *)v14 + 6);
      v13[7] = *((_OWORD *)v14 + 7);
      v13 += 8;
      v14 = (struct _INIDRIVER *)((char *)v14 + 128);
      --v15;
    }
    while ( v15 );
    *v13 = *(_OWORD *)v14;
    v13[1] = *((_OWORD *)v14 + 1);
    v13[2] = *((_OWORD *)v14 + 2);
    *((_QWORD *)v13 + 6) = *((_QWORD *)v14 + 6);
  }
  *(_DWORD *)v9 = 17476;
  *(_DWORD *)(v9 + 236) = *((_DWORD *)v6 + 8);
  *(_DWORD *)(v9 + 232) = 2;
  *(_QWORD *)(v9 + 120) = *((_QWORD *)a4 + 9);
  v16 = *((_DWORD *)a4 + 20);
  *(_DWORD *)(v9 + 200) = v16;
  *(_QWORD *)(v9 + 112) = *((_QWORD *)a4 + 8);
  *(_DWORD *)(v9 + 304) = OsVersionInfoEx.dwBuildNumber;
  if ( *((_DWORD *)a4 + 32) )
  {
    v16 |= 8u;
  }
  else if ( *((_QWORD *)a4 + 14) )
  {
    v16 |= 0x10u;
  }
  *(_DWORD *)(v9 + 200) = v16 | 1;
  if ( v12 )
    v17 = *((_QWORD *)a5 + 3);
  else
    LODWORD(v17) = 0;
  LODWORD(v64) = 0;
  updated = AllocOrUpdateStringAndTestSame((int)v9 + 24, *((_QWORD *)a4 + 1), v17, 1, (__int64)&v63, (__int64)&v64);
  v20 = 0;
  if ( updated )
  {
    updated = StringFromGUID2((const GUID *const)((char *)a4 + 132), sz, 39);
    v20 = 0;
    if ( updated )
    {
      if ( v12 )
        v21 = *((_QWORD *)a5 + 35);
      else
        LODWORD(v21) = 0;
      LODWORD(v64) = 0;
      updated = AllocOrUpdateStringAndTestSame((int)v9 + 280, (unsigned int)sz, v21, 1, (__int64)&v63, (__int64)&v64);
      v20 = 0;
      if ( updated )
      {
        if ( v12 )
          v22 = *((_QWORD *)a5 + 6);
        else
          LODWORD(v22) = 0;
        LODWORD(v64) = 0;
        updated = AllocOrUpdateStringAndTestSame(
                    (int)v9 + 48,
                    *((_QWORD *)a4 + 37),
                    v22,
                    1,
                    (__int64)&v63,
                    (__int64)&v64);
        v20 = 0;
        if ( updated )
        {
          if ( v12 )
            v23 = *((_QWORD *)a5 + 24);
          else
            LODWORD(v23) = 0;
          LODWORD(v64) = 0;
          updated = AllocOrUpdateStringAndTestSame((int)v9 + 192, *(_QWORD *)a4, v23, 1, (__int64)&v63, (__int64)&v64);
          v20 = 0;
          if ( updated )
          {
            if ( v12 )
              v24 = *((_QWORD *)a5 + 16);
            else
              LODWORD(v24) = 0;
            LODWORD(v64) = 0;
            updated = AllocOrUpdateStringAndTestSame(
                        (int)v9 + 128,
                        *((_QWORD *)a4 + 5),
                        v24,
                        1,
                        (__int64)&v63,
                        (__int64)&v64);
            v20 = 0;
            if ( updated )
            {
              if ( v12 )
                v25 = *((_QWORD *)a5 + 19);
              else
                LODWORD(v25) = 0;
              LODWORD(v64) = 0;
              updated = AllocOrUpdateStringAndTestSame(
                          (int)v9 + 152,
                          *((_QWORD *)a4 + 7),
                          v25,
                          1,
                          (__int64)&v63,
                          (__int64)&v64);
              v20 = 0;
            }
          }
        }
      }
    }
  }
  *(_DWORD *)(v9 + 288) = 0;
  *(_QWORD *)(v9 + 296) = 0;
  v69 = 1920234349;
  v26 = (NCoreLibrary *)&NCoreLibrary::TMultiString::gszzEmpty;
  v70 = &NCoreLibrary::TMultiString::gszzEmpty;
  v71 = 0;
  if ( updated )
  {
    v27 = (const unsigned __int16 *)*((_QWORD *)a4 + 19);
    if ( v27 )
    {
      while ( *v27 != (_WORD)v20 )
      {
        v28 = StringCchCopyW(String, 0x154u, v27);
        updated = v28 >= 0;
        Context = v20;
        if ( v28 >= 0 )
        {
          v29 = (unsigned int)v20;
          v30 = v20;
          v31 = wcstok_s(String, L",", &Context);
          v20 = 0;
          if ( v31 )
          {
            while ( 1 )
            {
              v32 = v29++ == -1;
              v33 = 0;
              if ( v32 )
                break;
              if ( v29 == 1 )
              {
                v30 = v31;
              }
              else if ( v29 == 2 )
              {
                v33 = v31;
                break;
              }
              if ( v29 < 2 )
              {
                v31 = wcstok_s(0, L",", &Context);
                v20 = 0;
                v33 = 0;
                if ( v31 )
                  continue;
              }
              break;
            }
            if ( v30 && v33 )
            {
              v64 = &NCoreLibrary::TString::gszNullState;
              updated = NCoreLibrary::TString::Format((NCoreLibrary::TString *)&v64, L"%ws,%ws", v30) >= 0
                     && NCoreLibrary::TMultiString::Cat((NCoreLibrary::TMultiString *)&v69, v64) >= 0;
              NCoreLibrary::TString::vFree(v34, v64);
              v20 = 0;
            }
          }
        }
        v35 = -1;
        do
          ++v35;
        while ( v27[v35] != (_WORD)v20 );
        v27 += v35 + 1;
        if ( !updated )
        {
          v12 = v62;
          goto LABEL_80;
        }
      }
      v26 = (NCoreLibrary *)v70;
      v12 = v62;
    }
    updated = (int)v20;
    if ( *((wchar_t **)a4 + 19) != v20 )
    {
      v36 = NCoreLibrary::MultiSzSize(v26, v18);
      *(_DWORD *)(v9 + 288) = v36;
      if ( !v36 )
        goto LABEL_80;
      v37 = 2 * v36;
      if ( *((wchar_t **)a4 + 19) != v20 )
      {
        v38 = (void *)DllAllocSplMem(v37);
        *(_QWORD *)(v9 + 296) = v38;
        v20 = 0;
        if ( !v38 )
        {
          updated = 0;
          goto LABEL_80;
        }
        memcpy_0(v38, v26, v37);
      }
    }
    MultiSZLen = GetMultiSZLen(*((_QWORD *)a4 + 40), 0);
    *(_DWORD *)(v9 + 64) = MultiSZLen;
    updated = 0;
    if ( MultiSZLen )
    {
      v40 = 2 * MultiSZLen;
      v41 = (void *)DllAllocSplMem((unsigned int)(2 * MultiSZLen));
      *(_QWORD *)(v9 + 72) = v41;
      if ( v41 )
      {
        memcpy_0(v41, *((const void **)a4 + 40), v40);
        if ( v12 )
          v43 = *((_QWORD *)a5 + 4);
        else
          LODWORD(v43) = 0;
        LODWORD(v64) = 0;
        updated = AllocOrUpdateStringAndTestSame(
                    (int)v9 + 32,
                    *((_QWORD *)a4 + 36),
                    v43,
                    1,
                    (__int64)&v63,
                    (__int64)&v64);
        v20 = 0;
        if ( !updated )
          goto LABEL_80;
        if ( v12 )
          v44 = *((_QWORD *)a5 + 18);
        else
          LODWORD(v44) = 0;
        LODWORD(v64) = 0;
        updated = AllocOrUpdateStringAndTestSame(
                    (int)v9 + 144,
                    *((_QWORD *)a4 + 4),
                    v44,
                    1,
                    (__int64)&v63,
                    (__int64)&v64);
      }
      else
      {
        v42 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "CreateV4DriverEntry",
          L"Failed to allocate %u bytes of memory for dependent files list: %d",
          v40,
          v42);
      }
    }
    else
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "CreateV4DriverEntry",
        L"Failed to calculate size of dependent files list");
    }
    v20 = 0;
LABEL_80:
    v6 = v65;
  }
  *(_DWORD *)(v9 + 176) = (_DWORD)v20;
  *(_QWORD *)(v9 + 184) = v20;
  if ( !updated )
  {
LABEL_88:
    FreeStructurePointers(v9, 0, IniDriverOffsets);
    v7 = 0;
    goto LABEL_89;
  }
  v45 = (unsigned int)v20;
  v46 = *((_QWORD *)a4 + 24);
  if ( v46 )
  {
    v47 = GetMultiSZLen(v46, 0);
    *(_DWORD *)(v9 + 176) = v47;
    v20 = 0;
    if ( !v47 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "CreateV4DriverEntry",
        L"Failed to calculate size of color profiles list");
      goto LABEL_88;
    }
    v45 = 2 * v47;
  }
  if ( *((wchar_t **)a4 + 24) != v20 )
  {
    v48 = DllAllocSplMem(v45);
    *(_QWORD *)(v9 + 184) = v48;
    LODWORD(v20) = 0;
    if ( !v48 )
    {
      v49 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "CreateV4DriverEntry",
        L"Failed to allocate %u bytes of memory for color profiles list: %d",
        v45,
        v49);
      goto LABEL_88;
    }
  }
  v51 = (const void *)*((_QWORD *)a4 + 24);
  if ( v51 )
  {
    memcpy_0(*(void **)(v9 + 184), v51, v45);
    LODWORD(v20) = 0;
  }
  if ( v12 )
    v52 = *((_QWORD *)a5 + 33);
  else
    LODWORD(v52) = (_DWORD)v20;
  LODWORD(v64) = (_DWORD)v20;
  if ( !(unsigned int)AllocOrUpdateStringAndTestSame(
                        (int)v9 + 264,
                        *((_QWORD *)a4 + 14),
                        v52,
                        1,
                        (__int64)&v63,
                        (__int64)&v64) )
    goto LABEL_88;
  v53 = ResolveBaseDriverReference((struct _INIDRIVER *)v9, v6);
  CheckXpsDriver((struct _INIDRIVER *)v9);
  v54 = *(_DWORD *)(v9 + 200) & 2;
  if ( !v54 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreateV4DriverEntry",
      L"Driver '%ws' does not have a pipelineconfig file",
      *((_QWORD *)a4 + 1));
    v72 = -2147467259;
    v73 = 4;
    v74 = 0;
    SplLogType::SplLogType((SplLogType *)v75, *((const unsigned __int16 **)a4 + 14));
    SplLogType::SplLogType((SplLogType *)v76, *(const unsigned __int16 **)a4);
    v55 = SplLogType::SplLogType((SplLogType *)v77, *((const unsigned __int16 **)a4 + 1));
    SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_MISSING_PIPELINECONFIG, v55, v56, v57, &v72, 0);
    goto LABEL_100;
  }
  v59 = *((unsigned int *)a4 + 37);
  v63 = 0;
  if ( (_DWORD)v59 )
  {
    if ( (int)ConvertDriverCategoryToPrinterDriverAttribute(v59, &v63) < 0 )
    {
      v54 = 0;
      LocalSpoolerTelemetry::WriteDbgTraceError("CreateV4DriverEntry", L"Invalid driver category specified somehow");
    }
    else
    {
      *(_DWORD *)(v9 + 200) |= v63;
    }
    v60 = (_QWORD *)(v9 + 272);
    if ( !v54 )
      goto LABEL_100;
  }
  else
  {
    v60 = (_QWORD *)(v9 + 272);
    v61 = *(_QWORD *)(v9 + 272);
    if ( v61 )
      *(_DWORD *)(v9 + 200) |= *(_DWORD *)(v61 + 232) & 0x33C0;
  }
  if ( !(unsigned int)WriteDriverIniInternal((struct _INIDRIVER *)v9, v6, v68, v67, 0) )
  {
LABEL_100:
    if ( v53 )
    {
      v58 = *(_QWORD *)(v9 + 272);
      if ( v58 )
      {
        if ( *(_DWORD *)(v58 + 16) )
          SafeDecrementReference((unsigned int *)(v58 + 16));
      }
    }
    goto LABEL_88;
  }
  if ( !a5 )
  {
    *(_QWORD *)(v9 + 8) = *((_QWORD *)v6 + 6);
    *((_QWORD *)v6 + 6) = v9;
    v7 = (struct _INIDRIVER *)v9;
    goto LABEL_90;
  }
  CopyNewOffsets(a5, v9);
  *((_DWORD *)a5 + 72) = *(_DWORD *)(v9 + 288);
  *((_DWORD *)a5 + 44) = *(_DWORD *)(v9 + 176);
  *((_DWORD *)a5 + 16) = *(_DWORD *)(v9 + 64);
  *((_DWORD *)a5 + 24) = 0;
  *((_DWORD *)a5 + 59) = *(_DWORD *)(v9 + 236);
  *((_DWORD *)a5 + 58) = *(_DWORD *)(v9 + 232);
  *((_DWORD *)a5 + 64) = 0;
  *((_QWORD *)a5 + 15) = *(_QWORD *)(v9 + 120);
  *((_QWORD *)a5 + 28) = 0;
  *((_DWORD *)a5 + 50) = *(_DWORD *)(v9 + 200);
  *((_DWORD *)a5 + 60) = 0;
  *((_QWORD *)a5 + 14) = *(_QWORD *)(v9 + 112);
  *((_QWORD *)a5 + 27) = 0;
  *((_DWORD *)a5 + 65) = 0;
  *((_QWORD *)a5 + 34) = *v60;
  *((_QWORD *)a5 + 31) = 0;
  *((_DWORD *)a5 + 76) = OsVersionInfoEx.dwBuildNumber;
LABEL_89:
  DllFreeSplMem(v9);
LABEL_90:
  NCoreLibrary::TMultiString::vFree(v50, v70);
  return v7;
}

```

## disassembly

```asm
0x1800bf1e0  push    rbp
0x1800bf1e2  push    rbx
0x1800bf1e3  push    rsi
0x1800bf1e4  push    rdi
0x1800bf1e5  push    r12
0x1800bf1e7  push    r13
0x1800bf1e9  push    r14
0x1800bf1eb  push    r15
0x1800bf1ed  lea     rbp, [rsp-2F8h]
0x1800bf1f5  sub     rsp, 3F8h
0x1800bf1fc  mov     rax, cs:__security_cookie
0x1800bf203  xor     rax, rsp
0x1800bf206  mov     [rbp+330h+var_50], rax
0x1800bf20d  mov     r14, r9
0x1800bf210  mov     [rsp+430h+var_3E0], r8
0x1800bf215  mov     [rsp+430h+var_3D8], rdx
0x1800bf21a  mov     r13, rcx
0x1800bf21d  mov     [rsp+430h+var_3F0], rcx
0x1800bf222  mov     rsi, [rbp+330h+arg_20]
0x1800bf229  xor     edi, edi
0x1800bf22b  mov     [rsp+430h+var_3FC], edi
0x1800bf22f  mov     r15d, 138h
0x1800bf235  mov     ecx, r15d
0x1800bf238  call    cs:__imp_DllAllocSplMem
0x1800bf23e  mov     rbx, rax
0x1800bf241  test    rax, rax
0x1800bf244  jnz     short loc_1800BF26C
0x1800bf246  call    cs:__imp_GetLastError
0x1800bf24c  mov     r9d, eax
0x1800bf24f  mov     r8d, r15d
0x1800bf252  lea     rdx, aFailedToAlloca_19; "Failed to allocate %u bytes of memory f"...
0x1800bf259  lea     rcx, aCreatev4driver; "CreateV4DriverEntry"
0x1800bf260  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800bf265  xor     eax, eax
0x1800bf267  jmp     loc_1800BF8B8
0x1800bf26c  mov     r12b, dil
0x1800bf26f  mov     [rsp+430h+var_400], dil
0x1800bf274  mov     r15d, 1
0x1800bf27a  lea     r9d, [r15+1]
0x1800bf27e  test    rsi, rsi
0x1800bf281  jz      loc_1800BF30C
0x1800bf287  cmp     dword ptr [rsi+0ECh], 4
0x1800bf28e  jb      short loc_1800BF30C
0x1800bf290  mov     r12b, r15b
0x1800bf293  mov     [rsp+430h+var_400], r15b
0x1800bf298  mov     rcx, rbx
0x1800bf29b  mov     rax, rsi
0x1800bf29e  mov     edx, r9d
0x1800bf2a1  lea     r8d, [r15+7Fh]
0x1800bf2a5  movups  xmm0, xmmword ptr [rax]
0x1800bf2a8  movups  xmmword ptr [rcx], xmm0
0x1800bf2ab  movups  xmm1, xmmword ptr [rax+10h]
0x1800bf2af  movups  xmmword ptr [rcx+10h], xmm1
0x1800bf2b3  movups  xmm0, xmmword ptr [rax+20h]
0x1800bf2b7  movups  xmmword ptr [rcx+20h], xmm0
0x1800bf2bb  movups  xmm1, xmmword ptr [rax+30h]
0x1800bf2bf  movups  xmmword ptr [rcx+30h], xmm1
0x1800bf2c3  movups  xmm0, xmmword ptr [rax+40h]
0x1800bf2c7  movups  xmmword ptr [rcx+40h], xmm0
0x1800bf2cb  movups  xmm1, xmmword ptr [rax+50h]
0x1800bf2cf  movups  xmmword ptr [rcx+50h], xmm1
0x1800bf2d3  movups  xmm0, xmmword ptr [rax+60h]
0x1800bf2d7  movups  xmmword ptr [rcx+60h], xmm0
0x1800bf2db  movups  xmm1, xmmword ptr [rax+70h]
0x1800bf2df  movups  xmmword ptr [rcx+70h], xmm1
0x1800bf2e3  add     rcx, r8
0x1800bf2e6  add     rax, r8
0x1800bf2e9  sub     rdx, r15
0x1800bf2ec  jnz     short loc_1800BF2A5
0x1800bf2ee  movups  xmm0, xmmword ptr [rax]
0x1800bf2f1  movups  xmmword ptr [rcx], xmm0
0x1800bf2f4  movups  xmm1, xmmword ptr [rax+10h]
0x1800bf2f8  movups  xmmword ptr [rcx+10h], xmm1
0x1800bf2fc  movups  xmm0, xmmword ptr [rax+20h]
0x1800bf300  movups  xmmword ptr [rcx+20h], xmm0
0x1800bf304  mov     rax, [rax+30h]
0x1800bf308  mov     [rcx+30h], rax
0x1800bf30c  mov     dword ptr [rbx], 4444h
0x1800bf312  mov     eax, [r13+20h]
0x1800bf316  mov     [rbx+0ECh], eax
0x1800bf31c  mov     [rbx+0E8h], r9d
0x1800bf323  mov     rax, [r14+48h]
0x1800bf327  mov     [rbx+78h], rax
0x1800bf32b  mov     ecx, [r14+50h]
0x1800bf32f  mov     [rbx+0C8h], ecx
0x1800bf335  mov     rax, [r14+40h]
0x1800bf339  mov     [rbx+70h], rax
0x1800bf33d  mov     eax, cs:OsVersionInfoEx.dwBuildNumber
0x1800bf343  mov     [rbx+130h], eax
0x1800bf349  cmp     [r14+80h], edi
0x1800bf350  jz      short loc_1800BF357
0x1800bf352  or      ecx, 8
0x1800bf355  jmp     short loc_1800BF360
0x1800bf357  cmp     [r14+70h], rdi
0x1800bf35b  jz      short loc_1800BF360
0x1800bf35d  or      ecx, 10h
0x1800bf360  or      ecx, r15d
0x1800bf363  mov     [rbx+0C8h], ecx
0x1800bf369  test    r12b, r12b
0x1800bf36c  jz      short loc_1800BF374
0x1800bf36e  mov     r8, [rsi+18h]
0x1800bf372  jmp     short loc_1800BF377
0x1800bf374  mov     r8, rdi
0x1800bf377  mov     dword ptr [rsp+430h+var_3F8], edi
0x1800bf37b  lea     rcx, [rbx+18h]
0x1800bf37f  lea     rax, [rsp+430h+var_3F8]
0x1800bf384  mov     [rsp+430h+var_408], rax
0x1800bf389  lea     rax, [rsp+430h+var_3FC]
0x1800bf38e  mov     qword ptr [rsp+430h+var_410], rax
0x1800bf393  mov     r9d, r15d
0x1800bf396  mov     rdx, [r14+8]
0x1800bf39a  call    AllocOrUpdateStringAndTestSame
0x1800bf39f  mov     edi, eax
0x1800bf3a1  xor     r10d, r10d
0x1800bf3a4  test    eax, eax
0x1800bf3a6  jz      loc_1800BF530
0x1800bf3ac  lea     rcx, [r14+84h]; rguid
0x1800bf3b3  lea     r8d, [r10+27h]; cchMax
0x1800bf3b7  lea     rdx, [rbp+330h+sz]; lpsz
0x1800bf3bb  call    cs:__imp_StringFromGUID2
0x1800bf3c1  mov     edi, eax
0x1800bf3c3  xor     r10d, r10d
0x1800bf3c6  test    eax, eax
0x1800bf3c8  jz      loc_1800BF530
0x1800bf3ce  test    r12b, r12b
0x1800bf3d1  jz      short loc_1800BF3DC
0x1800bf3d3  mov     r8, [rsi+118h]
0x1800bf3da  jmp     short loc_1800BF3DF
0x1800bf3dc  mov     r8, r10
0x1800bf3df  mov     dword ptr [rsp+430h+var_3F8], r10d
0x1800bf3e4  lea     rcx, [rbx+118h]
0x1800bf3eb  lea     rax, [rsp+430h+var_3F8]
0x1800bf3f0  mov     [rsp+430h+var_408], rax
0x1800bf3f5  lea     rax, [rsp+430h+var_3FC]
0x1800bf3fa  mov     qword ptr [rsp+430h+var_410], rax
0x1800bf3ff  mov     r9d, r15d
0x1800bf402  lea     rdx, [rbp+330h+sz]
0x1800bf406  call    AllocOrUpdateStringAndTestSame
0x1800bf40b  mov     edi, eax
0x1800bf40d  xor     r10d, r10d
0x1800bf410  test    eax, eax
0x1800bf412  jz      loc_1800BF530
0x1800bf418  test    r12b, r12b
0x1800bf41b  jz      short loc_1800BF423
0x1800bf41d  mov     r8, [rsi+30h]
0x1800bf421  jmp     short loc_1800BF426
0x1800bf423  mov     r8, r10
0x1800bf426  mov     dword ptr [rsp+430h+var_3F8], r10d
0x1800bf42b  lea     rcx, [rbx+30h]
0x1800bf42f  lea     rax, [rsp+430h+var_3F8]
0x1800bf434  mov     [rsp+430h+var_408], rax
0x1800bf439  lea     rax, [rsp+430h+var_3FC]
0x1800bf43e  mov     qword ptr [rsp+430h+var_410], rax
0x1800bf443  mov     r9d, r15d
0x1800bf446  mov     rdx, [r14+128h]
0x1800bf44d  call    AllocOrUpdateStringAndTestSame
0x1800bf452  mov     edi, eax
0x1800bf454  xor     r10d, r10d
0x1800bf457  test    eax, eax
0x1800bf459  jz      loc_1800BF530
0x1800bf45f  test    r12b, r12b
0x1800bf462  jz      short loc_1800BF46D
0x1800bf464  mov     r8, [rsi+0C0h]
0x1800bf46b  jmp     short loc_1800BF470
0x1800bf46d  mov     r8, r10
0x1800bf470  mov     dword ptr [rsp+430h+var_3F8], r10d
0x1800bf475  lea     rcx, [rbx+0C0h]
0x1800bf47c  lea     rax, [rsp+430h+var_3F8]
0x1800bf481  mov     [rsp+430h+var_408], rax
0x1800bf486  lea     rax, [rsp+430h+var_3FC]
0x1800bf48b  mov     qword ptr [rsp+430h+var_410], rax
0x1800bf490  mov     r9d, r15d
0x1800bf493  mov     rdx, [r14]
0x1800bf496  call    AllocOrUpdateStringAndTestSame
0x1800bf49b  mov     edi, eax
0x1800bf49d  xor     r10d, r10d
0x1800bf4a0  test    eax, eax
0x1800bf4a2  jz      loc_1800BF530
0x1800bf4a8  test    r12b, r12b
0x1800bf4ab  jz      short loc_1800BF4B6
0x1800bf4ad  mov     r8, [rsi+80h]
0x1800bf4b4  jmp     short loc_1800BF4B9
0x1800bf4b6  mov     r8, r10
0x1800bf4b9  mov     dword ptr [rsp+430h+var_3F8], r10d
0x1800bf4be  lea     rcx, [rbx+80h]
0x1800bf4c5  lea     rax, [rsp+430h+var_3F8]
0x1800bf4ca  mov     [rsp+430h+var_408], rax
0x1800bf4cf  lea     rax, [rsp+430h+var_3FC]
0x1800bf4d4  mov     qword ptr [rsp+430h+var_410], rax
0x1800bf4d9  mov     r9d, r15d
0x1800bf4dc  mov     rdx, [r14+28h]
0x1800bf4e0  call    AllocOrUpdateStringAndTestSame
0x1800bf4e5  mov     edi, eax
0x1800bf4e7  xor     r10d, r10d
0x1800bf4ea  test    eax, eax
0x1800bf4ec  jz      short loc_1800BF530
0x1800bf4ee  test    r12b, r12b
0x1800bf4f1  jz      short loc_1800BF4FC
0x1800bf4f3  mov     r8, [rsi+98h]
0x1800bf4fa  jmp     short loc_1800BF4FF
0x1800bf4fc  mov     r8, r10
0x1800bf4ff  mov     dword ptr [rsp+430h+var_3F8], r10d
0x1800bf504  lea     rcx, [rbx+98h]
0x1800bf50b  lea     rax, [rsp+430h+var_3F8]
0x1800bf510  mov     [rsp+430h+var_408], rax
0x1800bf515  lea     rax, [rsp+430h+var_3FC]
0x1800bf51a  mov     qword ptr [rsp+430h+var_410], rax
0x1800bf51f  mov     r9d, r15d
0x1800bf522  mov     rdx, [r14+38h]
0x1800bf526  call    AllocOrUpdateStringAndTestSame
0x1800bf52b  mov     edi, eax
0x1800bf52d  xor     r10d, r10d
0x1800bf530  mov     [rbx+120h], r10d
0x1800bf537  mov     [rbx+128h], r10
0x1800bf53e  mov     [rsp+430h+var_3D0], 7274736Dh
0x1800bf546  lea     r15, ?gszzEmpty@TMultiString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TMultiString::gszzEmpty
0x1800bf54d  mov     [rsp+430h+var_3C8], r15
0x1800bf552  mov     [rsp+430h+var_3C0], r10d
0x1800bf557  test    edi, edi
0x1800bf559  jz      loc_1800BF807
0x1800bf55f  mov     r13, [r14+98h]
0x1800bf566  test    r13, r13
0x1800bf569  jz      loc_1800BF6A1
0x1800bf56f  cmp     [r13+0], r10w
0x1800bf574  jz      loc_1800BF697
0x1800bf57a  mov     r8, r13; unsigned __int16 *
0x1800bf57d  mov     edx, 154h; unsigned __int64
0x1800bf582  lea     rcx, [rbp+330h+String]; unsigned __int16 *
0x1800bf586  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bf58b  mov     edi, eax
0x1800bf58d  not     edi
0x1800bf58f  shr     edi, 1Fh
0x1800bf592  mov     [rsp+430h+Context], r10
0x1800bf597  test    edi, edi
0x1800bf599  jz      loc_1800BF66D
0x1800bf59f  mov     r15d, r10d
0x1800bf5a2  mov     r12, r10
0x1800bf5a5  lea     r8, [rsp+430h+Context]; Context
0x1800bf5aa  lea     rdx, Delimiter; ","
0x1800bf5b1  lea     rcx, [rbp+330h+String]; String
0x1800bf5b5  call    cs:__imp_wcstok_s
0x1800bf5bb  xor     r10d, r10d
0x1800bf5be  test    rax, rax
0x1800bf5c1  jz      loc_1800BF66D
0x1800bf5c7  add     r15d, 1
0x1800bf5cb  mov     r9, r10
0x1800bf5ce  jz      short loc_1800BF5E0
0x1800bf5d0  mov     ecx, r15d
0x1800bf5d3  sub     ecx, 1
0x1800bf5d6  jz      short loc_1800BF62F
0x1800bf5d8  cmp     ecx, 1
0x1800bf5db  jnz     short loc_1800BF632
0x1800bf5dd  mov     r9, rax
0x1800bf5e0  test    r12, r12
0x1800bf5e3  jz      loc_1800BF66D
0x1800bf5e9  test    r9, r9
0x1800bf5ec  jz      short loc_1800BF66D
0x1800bf5ee  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x1800bf5f5  mov     [rsp+430h+var_3F8], rax
0x1800bf5fa  mov     r8, r12
0x1800bf5fd  lea     rdx, aWsWs_4; "%ws,%ws"
0x1800bf604  lea     rcx, [rsp+430h+var_3F8]; this
0x1800bf609  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x1800bf60e  xor     r15d, r15d
0x1800bf611  test    eax, eax
0x1800bf613  js      short loc_1800BF65D
0x1800bf615  mov     rdx, [rsp+430h+var_3F8]; unsigned __int16 *
0x1800bf61a  lea     rcx, [rsp+430h+var_3D0]; this
0x1800bf61f  call    ?Cat@TMultiString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TMultiString::Cat(ushort const *)
0x1800bf624  mov     edi, r15d
0x1800bf627  test    eax, eax
0x1800bf629  setns   dil
0x1800bf62d  jmp     short loc_1800BF660
0x1800bf62f  mov     r12, rax
0x1800bf632  cmp     r15d, 2
0x1800bf636  jnb     short loc_1800BF5E0
0x1800bf638  lea     r8, [rsp+430h+Context]; Context
0x1800bf63d  lea     rdx, Delimiter; ","
0x1800bf644  xor     ecx, ecx; String
0x1800bf646  call    cs:__imp_wcstok_s
0x1800bf64c  xor     r10d, r10d
0x1800bf64f  mov     r9d, r10d
0x1800bf652  test    rax, rax
0x1800bf655  jnz     loc_1800BF5C7
0x1800bf65b  jmp     short loc_1800BF5E0
0x1800bf65d  mov     edi, r15d
0x1800bf660  mov     rdx, [rsp+430h+var_3F8]; void *
0x1800bf665  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x1800bf66a  xor     r10d, r10d
0x1800bf66d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bf671  inc     rax
0x1800bf674  cmp     [r13+rax*2+0], r10w
0x1800bf67a  jnz     short loc_1800BF671
0x1800bf67c  lea     r13, [r13+rax*2+0]
0x1800bf681  add     r13, 2
0x1800bf685  test    edi, edi
0x1800bf687  jnz     loc_1800BF56F
0x1800bf68d  mov     r12b, [rsp+430h+var_400]
0x1800bf692  jmp     loc_1800BF802
0x1800bf697  mov     r15, [rsp+430h+var_3C8]
  ... truncated ...
```
