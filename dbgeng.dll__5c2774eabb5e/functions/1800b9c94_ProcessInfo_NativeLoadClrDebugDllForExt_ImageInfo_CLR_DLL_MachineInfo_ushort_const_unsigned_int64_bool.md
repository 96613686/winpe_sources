# ProcessInfo::NativeLoadClrDebugDllForExt(ImageInfo *,CLR_DLL,MachineInfo *,ushort const *,unsigned __int64,bool)

- ea: `0x1800b9c94`
- end: `0x1800bac8c`
- name: `?NativeLoadClrDebugDllForExt@ProcessInfo@@AEAAJPEAVImageInfo@@W4CLR_DLL@@PEAVMachineInfo@@PEBG_K_N@Z`
- size: `4088`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b995c`

## callees

- `0x1800727b8`
- `0x180073230`
- `0x1800793cc`
- `0x18007c2dc`
- `0x18007cf9c`
- `0x18007d14c`
- `0x18007d448`
- `0x18007daa4`
- `0x1800804c4`
- `0x180085700`
- `0x18008d550`
- `0x1800b94c4`
- `0x1800b9c94`
- `0x1800e8b30`
- `0x1800f0f40`
- `0x1800f17b0`
- `0x1800f2560`
- `0x180164300`
- `0x180264e84`
- `0x18026a9fc`
- `0x18028a1bc`
- `0x18028a5e8`
- `0x1804da880`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!isdigit` at `0x1800ba083`
- `api-ms-win-crt-string-l1-1-0!isdigit` at `0x1800ba09d`
- `api-ms-win-crt-string-l1-1-0!isdigit` at `0x1800ba0d2`
- `api-ms-win-crt-string-l1-1-0!isdigit` at `0x1800ba083`
- `api-ms-win-crt-string-l1-1-0!isdigit` at `0x1800ba09d`
- `api-ms-win-crt-string-l1-1-0!isdigit` at `0x1800ba0d2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800ba189`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800ba1a8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800ba189`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800ba1a8`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800b9e45`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800ba06e`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800b9e45`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800ba06e`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800ba5c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800ba6f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800ba5c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800ba6f5`

## string_xrefs

- `0x1800bab22`: `CLRDLL: Unable to find %s by search\n`
- `0x1800b9f26`: `CLRDLL: %s\n`
- `0x1800ba00f`: `CLRDLL: %s\n`
- `0x1800ba588`: `CLRDLL: %s\n`
- `0x1800baab3`: `CLRDLL: %s\n`
- `0x1800bab8e`: `CLRDLL: %s\n`
- `0x1800bac35`: `CLRDLL: %s\n`
- `0x1800ba66b`: `CLRDLL: Consider using ".cordll -lp <path>" command to specify .NET runtime directory.\n`
- `0x1800ba7e7`: `CLRDLL: Consider using ".cordll -lp <path>" command to specify .NET runtime directory.\n`
- `0x1800ba90f`: `CLRDLL: Consider using ".cordll -lp <path>" command to specify .NET runtime directory.\n`
- `0x1800baa55`: `CLRDLL: Consider using ".cordll -lp <path>" command to specify .NET runtime directory.\n`
- `0x1800bab9a`: `CLRDLL: Consider using ".cordll -lp <path>" command to specify .NET runtime directory.\n`
- `0x1800bac57`: `CLRDLL: CLR DLL load disabled\n`
- `0x1800b9f56`: `Downlevel CLR, sos.dll not available for non-x86`
- `0x1800bac11`: `ERROR: Unsupported mscor DLL type %s`
- `0x1800b9fe2`: `ERROR: Unknown mscor DLL type %s`
- `0x1800ba270`: `mrt%sdac_win%s.dll`
- `0x1800ba231`: `mscordac%s_%s_%s_%u.%u.%u.%02u%s.dll`
- `0x1800ba55b`: `ERROR: Path overflow`
- `0x1800baa8b`: `ERROR: Path overflow`
- `0x1800ba28f`: `mrt%sdac_win%s_%s.dll`
- `0x1800ba340`: `mrt%ssos.dll`
- `0x1800ba30d`: `SOS_%s_%s_%u.%u.%u.%02u%s.dll`
- `0x1800ba6a6`: `SOS.dll`
- `0x1800ba35a`: `mrt%ssos_%s.dll`
- `0x1800ba8c8`: `CLRDLL: Unable to find %s by mscorwks search\n`
- `0x1800ba723`: `Automatically loaded SOS Extension\n`
- `0x1800bab66`: `ERROR: Unable to load DLL %s, %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ProcessInfo::NativeLoadClrDebugDllForExt(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7)
{
  int v11; // edx
  bool v12; // di
  int *v14; // rdx
  int v15; // r8d
  int *v16; // rcx
  int v17; // r9d
  const wchar_t *v18; // rcx
  bool v19; // cl
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned int v25; // r15d
  __int64 v26; // rsi
  unsigned int v27; // esi
  const unsigned __int16 *v28; // rcx
  const unsigned __int16 *v29; // r15
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  int v34; // r9d
  char v35; // r10
  int v36; // r9d
  char v37; // r10
  const wchar_t *v38; // rsi
  const wchar_t *v39; // r9
  int v40; // eax
  int v41; // eax
  __int64 v42; // r12
  int *v43; // rdx
  int v44; // r8d
  int *v45; // rcx
  int v46; // r9d
  unsigned __int16 *v47; // rcx
  unsigned __int16 *v48; // rdx
  unsigned int v49; // esi
  unsigned __int16 *v50; // rcx
  wchar_t *v51; // r13
  wchar_t *v52; // r15
  wchar_t *v53; // rax
  __int64 v54; // r8
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // r9
  int v58; // r13d
  int ImageFilePath; // eax
  __int64 v60; // r8
  int v61; // ecx
  unsigned int v62; // esi
  __int64 v63; // r9
  __int64 v64; // rdx
  wchar_t *v65; // r13
  __int64 v66; // r8
  __int64 v67; // rax
  __int64 v68; // r9
  __int64 v69; // rdx
  unsigned __int16 *v70; // r15
  unsigned __int16 *v71; // rdx
  __int64 v72; // r8
  __int64 v73; // r9
  const unsigned __int16 *v74; // rcx
  const unsigned __int16 *v75; // rax
  const wchar_t *v76; // [rsp+28h] [rbp-D8h]
  __int64 v77; // [rsp+28h] [rbp-D8h]
  int v78; // [rsp+30h] [rbp-D0h]
  int v79; // [rsp+30h] [rbp-D0h]
  int v80; // [rsp+38h] [rbp-C8h]
  int v81; // [rsp+38h] [rbp-C8h]
  int v82; // [rsp+40h] [rbp-C0h]
  int v83; // [rsp+40h] [rbp-C0h]
  const wchar_t *v84; // [rsp+48h] [rbp-B8h]
  __int64 v85; // [rsp+48h] [rbp-B8h]
  const wchar_t *v86; // [rsp+50h] [rbp-B0h]
  __int64 v87; // [rsp+50h] [rbp-B0h]
  int v89; // [rsp+64h] [rbp-9Ch]
  bool v90; // [rsp+70h] [rbp-90h]
  UINT uMode; // [rsp+74h] [rbp-8Ch]
  __int128 v92; // [rsp+80h] [rbp-80h] BYREF
  __int128 v93; // [rsp+90h] [rbp-70h]
  __int128 v94; // [rsp+A0h] [rbp-60h]
  int v95; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v96; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v97; // [rsp+CCh] [rbp-34h]
  char v98; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v99[3]; // [rsp+270h] [rbp+170h] BYREF
  char v100; // [rsp+288h] [rbp+188h] BYREF
  __int64 v101; // [rsp+420h] [rbp+320h] BYREF
  unsigned int v102; // [rsp+42Ch] [rbp+32Ch]
  char v103; // [rsp+438h] [rbp+338h] BYREF
  _WORD v104[16]; // [rsp+5D0h] [rbp+4D0h]
  wchar_t Src[128]; // [rsp+5F0h] [rbp+4F0h] BYREF
  wchar_t Buffer[128]; // [rsp+6F0h] [rbp+5F0h] BYREF

  v11 = *(_DWORD *)(a1 + 392);
  v12 = (v11 & 0x80) != 0;
  if ( *(_QWORD *)(a1 + 528) )
    return 0;
  if ( (((v11 & 0x40) == 0) & !_bittest((const signed __int32 *)&g_EngOptions, 0xEu)) != 0 )
  {
    v14 = *(int **)(a1 + 88);
    if ( !v14 )
    {
LABEL_23:
      v19 = 0;
      if ( !a5 )
        v19 = v12;
      v90 = v19;
      v92 = 0;
      v93 = 0;
      v94 = 0;
      v95 = 0;
      if ( *(_DWORD *)(a2 + 548) < 2u )
        v20 = 0;
      else
        v20 = *(_QWORD *)(a2 + 536);
      v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, const wchar_t *, __int128 *, int, _QWORD))(**(_QWORD **)(a1 + 88) + 784LL))(
              *(_QWORD *)(a1 + 88),
              a1,
              v20,
              *(_QWORD *)(a2 + 32),
              L"\\",
              &v92,
              52,
              0);
      v25 = v21;
      if ( v21 )
      {
        FormatStatusCode(v21);
        PrintStringW((wchar_t *)(a1 + 536), 0x145u, (wchar_t *)L"ERROR: Unable to get version information for %s, %s");
        if ( !a7 && (*(_DWORD *)(a1 + 392) & 0x100) != 0 )
          ErrOut(L"CLRDLL: %s\n", a1 + 536);
        return v25;
      }
      if ( ((a3 - 4) & 0xFFFFFFFD) != 0 && DWORD2(v92) < 0x20000 )
      {
        v26 = a1 + 536;
        PrintStringW((wchar_t *)(a1 + 536), 0x145u, (wchar_t *)L"Downlevel CLR, sos.dll not available for non-x86");
        *(_DWORD *)(a1 + 392) |= 0x40u;
        if ( (*(_DWORD *)(a1 + 392) & 0x100) == 0 || a7 )
          return 2147549183LL;
        goto LABEL_193;
      }
      v104[0] = 0;
      if ( a3 == 1 )
      {
        v26 = a1 + 536;
        PrintStringW((wchar_t *)(a1 + 536), 0x145u, (wchar_t *)L"ERROR: Unsupported mscor DLL type %s");
        if ( (*(_DWORD *)(a1 + 392) & 0x100) == 0 )
          return 2147549183LL;
LABEL_193:
        ErrOut(L"CLRDLL: %s\n", v26);
        return 2147549183LL;
      }
      if ( a3 != 2 && a3 != 3 && a3 != 4 && a3 != 5 )
      {
        if ( a3 != 6 )
        {
          PrintStringW((wchar_t *)(a1 + 536), 0x145u, (wchar_t *)L"ERROR: Unknown mscor DLL type %s");
          if ( (*(_DWORD *)(a1 + 392) & 0x100) != 0 && !a7 )
            ErrOut(L"CLRDLL: %s\n", a1 + 536);
          return 2147942487LL;
        }
        v27 = 0;
        if ( *(_DWORD *)(a2 + 548) < 2u || !*(_QWORD *)(a2 + 536) )
          MicrosoftTelemetryAssertTriggeredNoArgs(a3 - 5, v22, v23, v24);
        if ( *(_DWORD *)(a2 + 548) < 2u )
          v28 = 0;
        else
          v28 = *(const unsigned __int16 **)(a2 + 536);
        v29 = PathTail(v28);
        if ( _wcsnicmp(v29, L"mrt", 3u) || !isdigit(v29[3]) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v31, v30, v32, v33);
        if ( isdigit(v29[3]) )
        {
          while ( v27 < 0xF )
          {
            v104[v27] = v29[v27 + 3];
            if ( !isdigit(v29[++v27 + 3]) )
            {
              if ( v27 >= 0xF )
                return 2147549183LL;
              goto LABEL_61;
            }
          }
          return 2147549183LL;
        }
LABEL_61:
        if ( 2 * (unsigned __int64)v27 >= 0x20 )
          _report_rangecheckfailure();
        v104[v27] = 0;
      }
      DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>(
        (unsigned int)&v96,
        (unsigned int)&v98,
        200,
        200,
        1);
      DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>(
        (unsigned int)v99,
        (unsigned int)&v100,
        v34,
        v34,
        v35);
      DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>(
        (unsigned int)&v101,
        (unsigned int)&v103,
        v36,
        v36,
        v37);
      if ( !_wcsicmp(*(const wchar_t **)(a4 + 24), L"x86") || !_wcsicmp(*(const wchar_t **)(a4 + 24), L"ARM") )
      {
        v49 = 2;
LABEL_191:
        DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v101);
        DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(v99);
        DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v96);
        return v49;
      }
      v38 = L".dbg";
      if ( a3 == 6 )
      {
        if ( **(_DWORD **)(a4 + 48) == 34404 )
        {
          v40 = PrintStringW(Src, 0x80u, (wchar_t *)L"mrt%sdac_win%s.dll");
        }
        else
        {
          v76 = L"AMD64";
          v40 = PrintStringW(Src, 0x80u, (wchar_t *)L"mrt%sdac_win%s_%s.dll");
        }
      }
      else
      {
        if ( (BYTE12(v93) & 1) != 0 )
        {
          v39 = L".dbg";
          if ( (BYTE12(v93) & 0x20) == 0 )
            v39 = L".chk";
        }
        else
        {
          v39 = &strIn;
        }
        v86 = v39;
        LODWORD(v84) = WORD6(v92);
        v82 = HIWORD(HIDWORD(v92));
        v80 = WORD4(v92);
        v78 = HIWORD(DWORD2(v92));
        v76 = *(const wchar_t **)(a4 + 24);
        v40 = PrintStringW(Src, 0x80u, (wchar_t *)L"mscordac%s_%s_%s_%u.%u.%u.%02u%s.dll");
      }
      if ( !v40 )
        goto LABEL_121;
      if ( a3 == 6 )
      {
        v41 = **(_DWORD **)(a4 + 48) == 34404
            ? PrintStringW(Buffer, 0x80u, (wchar_t *)L"mrt%ssos.dll")
            : PrintStringW(Buffer, 0x80u, (wchar_t *)L"mrt%ssos_%s.dll");
      }
      else
      {
        if ( (BYTE12(v93) & 1) != 0 )
        {
          if ( (BYTE12(v93) & 0x20) == 0 )
            v38 = L".chk";
        }
        else
        {
          v38 = &strIn;
        }
        v84 = v38;
        v82 = WORD6(v92);
        v80 = HIWORD(HIDWORD(v92));
        v78 = WORD4(v92);
        LODWORD(v76) = HIWORD(DWORD2(v92));
        v41 = PrintStringW(Buffer, 0x80u, (wchar_t *)L"SOS_%s_%s_%u.%u.%u.%02u%s.dll");
      }
      if ( !v41 )
      {
LABEL_121:
        PrintStringW((wchar_t *)(a1 + 536), 0x145u, (wchar_t *)L"ERROR: Path overflow");
        if ( !a7 && (*(_DWORD *)(a1 + 392) & 0x100) != 0 )
          ErrOut(L"CLRDLL: %s\n", a1 + 536);
        v49 = -2147024882;
        goto LABEL_191;
      }
      if ( a5 )
      {
        v42 = a5;
LABEL_109:
        if ( !DbsDynamicString<unsigned short>::CopyStr(&v96, v42, 0xFFFFFFFFLL) )
          goto LABEL_121;
        if ( a5 )
        {
          if ( (unsigned __int16)DbsDynamicString<unsigned short>::GetLastChar(&v96) != 47
            && (unsigned __int16)DbsDynamicString<unsigned short>::GetLastChar(&v96) != 92
            && (unsigned __int16)DbsDynamicString<unsigned short>::GetLastChar(&v96) != 58 )
          {
            DbsDynamicString<unsigned short>::AppendChar((DbsDynamicBuffer *)&v96);
          }
        }
        else
        {
          v47 = 0;
          if ( v97 >= 2 )
            v47 = v96;
          PathTail(v47);
          DbsDynamicString<unsigned short>::SetTerminatorAt((DbsDynamicBuffer *)&v96);
        }
        v48 = 0;
        if ( v97 >= 2 )
          v48 = v96;
        DbsDynamicString<unsigned short>::CopyStr(&v101, v48, 0xFFFFFFFFLL);
        if ( (unsigned int)DbsDynamicString<unsigned short>::AppendStr((DbsDynamicBuffer *)&v96, Src) )
          goto LABEL_121;
        v89 = -2147467259;
        v50 = 0;
        if ( v97 >= 2 )
          v50 = v96;
        v51 = (wchar_t *)PathTail(v50);
        uMode = SetErrorMode(1u);
        v52 = v96;
        if ( v90 )
        {
          v49 = -2147024891;
        }
        else
        {
          v53 = wcschr(v51, 0x5Fu);
          *(_QWORD *)v53 = *(_QWORD *)L".dll";
          v53[4] = Extension[4];
          v54 = *(_DWORD *)(a1 + 392) >> 8;
          LOBYTE(v54) = BYTE1(*(_DWORD *)(a1 + 392)) & 1;
          v49 = SecureLoadClrModule(v52, &v92, v54, a3, a1 + 528, v76, v78, v80, v82, v84, v86);
          if ( !v49 )
          {
            v49 = ProcessInfo::InitializeClrDac(
                    (ProcessInfo *)a1,
                    v52,
                    L"CLRDLL: Consider using \".cordll -lp <path>\" command to specify .NET runtime directory.\n");
            v56 = 0;
            if ( v102 >= 2 )
              v56 = v101;
            DbsDynamicString<unsigned short>::CopyStr(v99, v56, 0xFFFFFFFFLL);
            DbsDynamicString<unsigned short>::AppendStr((DbsDynamicBuffer *)v99, L"SOS.dll");
            v57 = *(_DWORD *)(a1 + 392) >> 8;
            LOBYTE(v57) = BYTE1(*(_DWORD *)(a1 + 392)) & 1;
            v58 = LoadSOSAndCheckVer(a1, v99[0], &v92, v57, a3);
            v89 = v58;
            if ( !v49 )
              goto LABEL_135;
LABEL_141:
            if ( !a5 )
            {
              if ( (IMAGE_HEADER_INFO::Update(
                      (IMAGE_HEADER_INFO *)(a2 + 48),
                      *(struct ProcessInfo **)a2,
                      *(_QWORD *)(a2 + 32),
                      *(void **)(a2 + 24),
                      2u)
                  & 2) == 0 )
              {
LABEL_146:
                if ( !v49 )
                  goto LABEL_135;
                goto LABEL_147;
              }
              v52 = v96;
              ImageFilePath = FindImageFilePath(
                                a1,
                                (unsigned int)Src,
                                *(_DWORD *)(a2 + 40),
                                0,
                                *(_DWORD *)(a2 + 64),
                                6,
                                (__int64)&v96);
              v61 = *(_DWORD *)(a1 + 392);
              if ( !ImageFilePath )
              {
                v52 = v96;
                v62 = a3;
                LOBYTE(v60) = BYTE1(v61) & 1;
                if ( (unsigned int)SecureLoadClrModule(v96, &v92, v60, a3, a1 + 528, v76, v78, v80, v82, v84, v86) )
                  goto LABEL_148;
                v49 = ProcessInfo::InitializeClrDac(
                        (ProcessInfo *)a1,
                        v52,
                        L"CLRDLL: Consider using \".cordll -lp <path>\" command to specify .NET runtime directory.\n");
                FindImageFilePath(
                  a1,
                  (unsigned int)Buffer,
                  *(_DWORD *)(a2 + 40),
                  0,
                  *(_DWORD *)(a2 + 64),
                  6,
                  (__int64)v99);
                v63 = *(_DWORD *)(a1 + 392) >> 8;
                LOBYTE(v63) = BYTE1(*(_DWORD *)(a1 + 392)) & 1;
                v58 = LoadSOSAndCheckVer(a1, v99[0], &v92, v63, a3);
                v89 = v58;
                goto LABEL_146;
              }
              if ( (v61 & 0x100) != 0 )
                ErrOut(L"CLRDLL: Unable to find %s by mscorwks search\n", Src);
            }
LABEL_147:
            v62 = a3;
LABEL_148:
            v64 = 0;
            if ( v102 >= 2 )
              v64 = v101;
            DbsDynamicString<unsigned short>::CopyStr(v99, v64, 0xFFFFFFFFLL);
            DbsDynamicString<unsigned short>::AppendStr((DbsDynamicBuffer *)v99, Buffer);
            if ( a5 )
            {
              v65 = (wchar_t *)v99[0];
            }
            else
            {
              v52 = Src;
              v65 = Buffer;
            }
            v66 = *(_DWORD *)(a1 + 392) >> 8;
            LOBYTE(v66) = BYTE1(*(_DWORD *)(a1 + 392)) & 1;
            v49 = SecureLoadClrModule(v52, &v92, v66, v62, a1 + 528, v76, v78, v80, v82, v84, v86);
            v67 = 0;
            if ( v49 )
            {
              v58 = v89;
            }
            else
            {
              v49 = ProcessInfo::InitializeClrDac(
                      (ProcessInfo *)a1,
                      v52,
                      L"CLRDLL: Consider using \".cordll -lp <path>\" command to specify .NET runtime directory.\n");
              v68 = *(_DWORD *)(a1 + 392) >> 8;
              LOBYTE(v68) = BYTE1(*(_DWORD *)(a1 + 392)) & 1;
              v58 = LoadSOSAndCheckVer(a1, v65, &v92, v68, a3);
              v67 = 0;
              if ( !v49 )
                goto LABEL_135;
            }
            if ( a5 )
              goto LABEL_135;
            if ( *(_DWORD *)(a2 + 980) >= 2u )
              v67 = *(_QWORD *)(a2 + 968);
            if ( v42 == v67 )
              goto LABEL_135;
            if ( *(_DWORD *)(a2 + 548) < 2u )
              LODWORD(v69) = 0;
            else
              v69 = *(_QWORD *)(a2 + 536);
            v49 = FindImageFilePath(
                    a1,
                    v69,
                    *(_DWORD *)(a2 + 40),
                    *(_DWORD *)(a2 + 60),
                    *(_DWORD *)(a2 + 64),
                    0,
                    (__int64)&v96);
            if ( v49 )
            {
              if ( (*(_DWORD *)(a1 + 392) & 0x100) != 0 )
              {
                if ( *(_DWORD *)(a2 + 548) < 2u )
                  v74 = 0;
                else
                  v74 = *(const unsigned __int16 **)(a2 + 536);
                v75 = PathTail(v74);
                ErrOut(L"CLRDLL: Unable to find %s by search\n", v75);
              }
              goto LABEL_135;
            }
            v70 = v96;
            PathTail(v96);
            DbsDynamicString<unsigned short>::SetTerminatorAt((DbsDynamicBuffer *)&v96);
            v71 = 0;
            if ( v97 >= 2 )
              v71 = v96;
            DbsDynamicString<unsigned short>::CopyStr(v99, v71, 0xFFFFFFFFLL);
            if ( (unsigned int)DbsDynamicString<unsigned short>::AppendStr((DbsDynamicBuffer *)&v96, Src) )
              goto LABEL_172;
            v72 = *(_DWORD *)(a1 + 392) >> 8;
            LOBYTE(v72) = BYTE1(*(_DWORD *)(a1 + 392)) & 1;
            v49 = SecureLoadClrModule(v70, &v92, v72, a3, a1 + 528, v77, v79, v81, v83, v85, v87);
            if ( !v49 )
            {
              v49 = ProcessInfo::InitializeClrDac(
                      (ProcessInfo *)a1,
                      v70,
                      L"CLRDLL: Consider using \".cordll -lp <path>\" command to specify .NET runtime directory.\n");
              if ( (unsigned int)DbsDynamicString<unsigned short>::AppendStr((DbsDynamicBuffer *)v99, Buffer) )
              {
LABEL_172:
                PrintStringW((wchar_t *)(a1 + 536), 0x145u, (wchar_t *)L"ERROR: Path overflow");
                if ( !a7 && (*(_DWORD *)(a1 + 392) & 0x100) != 0 )
                  ErrOut(L"CLRDLL: %s\n", a1 + 536);
                v49 = -2147024882;
                goto LABEL_135;
              }
              v73 = *(_DWORD *)(a1 + 392) >> 8;
              LOBYTE(v73) = BYTE1(*(_DWORD *)(a1 + 392)) & 1;
              v58 = LoadSOSAndCheckVer(a1, v99[0], &v92, v73, a3);
            }
LABEL_135:
            SetErrorMode(uMode);
            if ( (*(_DWORD *)(a1 + 392) & 0x100) != 0 && !a7 )
            {
              if ( v58 )
                ErrOut(L"Cannot Automatically load SOS\n");
              else
                dprintf(L"Automatically loaded SOS Extension\n");
            }
            if ( !v49 )
            {
              DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v101);
              DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(v99);
              DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v96);
              return 0;
            }
            FormatStatusCode(v49);
            PrintStringW((wchar_t *)(a1 + 536), 0x145u, (wchar_t *)L"ERROR: Unable to load DLL %s, %s");
            if ( !a7 )
            {
              if ( (*(_DWORD *)(a1 + 392) & 0x100) != 0 )
                ErrOut(L"CLRDLL: %s\n", a1 + 536);
              ErrOut(L"CLRDLL: Consider using \".cordll -lp <path>\" command to specify .NET runtime directory.\n");
            }
            *(_DWORD *)(a1 + 392) |= 0x40u;
            goto LABEL_191;
          }
          v55 = -1;
          do
            ++v55;
          while ( Src[v55] );
          memmove(v51, Src, 2 * v55 + 2);
        }
        v58 = -2147467259;
        goto LABEL_141;
      }
      v43 = *(int **)(a1 + 88);
      if ( !v43 )
      {
LABEL_106:
        if ( *(_DWORD *)(a2 + 548) < 2u )
          v42 = 0;
        else
          v42 = *(_QWORD *)(a2 + 536);
        goto LABEL_109;
      }
      v44 = v43[1026];
      v45 = v43 + 1027;
      if ( !v44 )
        goto LABEL_98;
      v46 = *v45;
      if ( (unsigned int)(*v45 - 1024) <= 5 || v46 == 3143 )
        goto LABEL_104;
      if ( v44 == 2 )
      {
        if ( v46 != 3 )
          goto LABEL_106;
      }
      else
      {
LABEL_98:
        if ( v44 != 1 || *v45 != 5 )
          goto LABEL_106;
      }
      if ( !(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v43 + 1552LL))(*(_QWORD *)(a1 + 88))
        || !*(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 88) + 1552LL))(*(_QWORD *)(a1 + 88))
                      + 4104)
        || (*(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 88) + 1552LL))(*(_QWORD *)(a1 + 88))
                      + 4108) < 0x400u
         || *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 88) + 1552LL))(*(_QWORD *)(a1 + 88))
                      + 4108) > 0x405u)
        && *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 88) + 1552LL))(*(_QWORD *)(a1 + 88)) + 4108) != 3143 )
      {
        goto LABEL_106;
      }
LABEL_104:
      if ( *(_DWORD *)(a2 + 980) >= 4u )
      {
        v42 = *(_QWORD *)(a2 + 968);
        if ( v42 )
          goto LABEL_109;
      }
      goto LABEL_106;
    }
    v15 = v14[1026];
    v16 = v14 + 1027;
    if ( !v15 )
      goto LABEL_12;
    v17 = *v16;
    if ( (unsigned int)(*v16 - 1024) <= 5 || v17 == 3143 )
      goto LABEL_18;
    if ( v15 == 2 )
    {
      if ( v17 != 3 )
        goto LABEL_23;
    }
    else
    {
LABEL_12:
      if ( v15 != 1 || *v16 != 5 )
        goto LABEL_23;
    }
    if ( !(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v14 + 1552LL))(*(_QWORD *)(a1 + 88))
      || !*(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 88) + 1552LL))(*(_QWORD *)(a1 + 88)) + 4104)
      || (*(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 88) + 1552LL))(*(_QWORD *)(a1 + 88)) + 4108) < 0x400u
       || *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 88) + 1552LL))(*(_QWORD *)(a1 + 88)) + 4108) > 0x405u)
      && *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 88) + 1552LL))(*(_QWORD *)(a1 + 88)) + 4108) != 3143 )
    {
      goto LABEL_23;
    }
LABEL_18:
    if ( *(_DWORD *)(a2 + 548) < 2u )
      v18 = 0;
    else
      v18 = *(const wchar_t **)(a2 + 536);
    if ( !_wcsnicmp(v18, L"\\\\", 2u) )
      v12 = 1;
    goto LABEL_23;
  }
  if ( !a7 && (v11 & 0x100) != 0 )
    ErrOut(L"CLRDLL: CLR DLL load disabled\n");
  return 2147942412LL;
}

```

## disassembly

```asm
0x1800b9c94  push    rbp
0x1800b9c96  push    rbx
0x1800b9c97  push    rsi
0x1800b9c98  push    rdi
0x1800b9c99  push    r12
0x1800b9c9b  push    r13
0x1800b9c9d  push    r14
0x1800b9c9f  push    r15
0x1800b9ca1  lea     rbp, [rsp-708h]
0x1800b9ca9  sub     rsp, 808h
0x1800b9cb0  mov     [rsp+840h+var_7C8], 0FFFFFFFFFFFFFFFEh
0x1800b9cb9  mov     rax, cs:__security_cookie
0x1800b9cc0  xor     rax, rsp
0x1800b9cc3  mov     [rbp+740h+var_50], rax
0x1800b9cca  mov     r13, r9
0x1800b9ccd  mov     r12d, r8d
0x1800b9cd0  mov     [rsp+840h+var_7E0], r8d
0x1800b9cd5  mov     r14, rdx
0x1800b9cd8  mov     rbx, rcx
0x1800b9cdb  mov     rsi, [rbp+740h+arg_20]
0x1800b9ce2  mov     [rsp+840h+var_7D8], rsi
0x1800b9ce7  mov     edx, [rcx+188h]
0x1800b9ced  mov     edi, edx
0x1800b9cef  shr     edi, 7
0x1800b9cf2  mov     r10d, 1
0x1800b9cf8  and     dil, r10b
0x1800b9cfb  xor     r15d, r15d
0x1800b9cfe  cmp     [rcx+210h], r15
0x1800b9d05  jz      short loc_1800B9D0E
0x1800b9d07  xor     eax, eax
0x1800b9d09  jmp     loc_1800BAC68
0x1800b9d0e  test    dl, 40h
0x1800b9d11  setz    cl
0x1800b9d14  bt      cs:?g_EngOptions@@3KA, 0Eh; ulong g_EngOptions
0x1800b9d1c  setnb   al
0x1800b9d1f  test    al, cl
0x1800b9d21  jz      loc_1800BAC48
0x1800b9d27  mov     rdx, [rbx+58h]
0x1800b9d2b  test    rdx, rdx
0x1800b9d2e  jz      loc_1800B9E5F
0x1800b9d34  mov     r8d, [rdx+1008h]
0x1800b9d3b  lea     rcx, [rdx+100Ch]
0x1800b9d42  test    r8d, r8d
0x1800b9d45  jz      short loc_1800B9D78
0x1800b9d47  mov     r9d, [rcx]
0x1800b9d4a  lea     eax, [r9-400h]
0x1800b9d51  cmp     eax, 5
0x1800b9d54  jbe     loc_1800B9E22
0x1800b9d5a  cmp     r9d, 0C47h
0x1800b9d61  jz      loc_1800B9E22
0x1800b9d67  cmp     r8d, 2
0x1800b9d6b  jnz     short loc_1800B9D78
0x1800b9d6d  cmp     r9d, 3
0x1800b9d71  jz      short loc_1800B9D8A
0x1800b9d73  jmp     loc_1800B9E5F
0x1800b9d78  cmp     r8d, r10d
0x1800b9d7b  jnz     loc_1800B9E5F
0x1800b9d81  cmp     dword ptr [rcx], 5
0x1800b9d84  jnz     loc_1800B9E5F
0x1800b9d8a  mov     rax, [rdx]
0x1800b9d8d  mov     rcx, rdx
0x1800b9d90  mov     rax, [rax+610h]
0x1800b9d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9d9c  test    rax, rax
0x1800b9d9f  jz      loc_1800B9E5F
0x1800b9da5  mov     rcx, [rbx+58h]
0x1800b9da9  mov     rax, [rcx]
0x1800b9dac  mov     rax, [rax+610h]
0x1800b9db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9db8  cmp     [rax+1008h], r15d
0x1800b9dbf  jz      loc_1800B9E5F
0x1800b9dc5  mov     rcx, [rbx+58h]
0x1800b9dc9  mov     rax, [rcx]
0x1800b9dcc  mov     rax, [rax+610h]
0x1800b9dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9dd8  cmp     dword ptr [rax+100Ch], 400h
0x1800b9de2  jb      short loc_1800B9E03
0x1800b9de4  mov     rcx, [rbx+58h]
0x1800b9de8  mov     rax, [rcx]
0x1800b9deb  mov     rax, [rax+610h]
0x1800b9df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9df7  cmp     dword ptr [rax+100Ch], 405h
0x1800b9e01  jbe     short loc_1800B9E22
0x1800b9e03  mov     rcx, [rbx+58h]
0x1800b9e07  mov     rax, [rcx]
0x1800b9e0a  mov     rax, [rax+610h]
0x1800b9e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9e16  cmp     dword ptr [rax+100Ch], 0C47h
0x1800b9e20  jnz     short loc_1800B9E5F
0x1800b9e22  cmp     dword ptr [r14+224h], 2
0x1800b9e2a  jb      short loc_1800B9E35
0x1800b9e2c  mov     rcx, [r14+218h]
0x1800b9e33  jmp     short loc_1800B9E38
0x1800b9e35  mov     rcx, r15; String1
0x1800b9e38  mov     r8d, 2; MaxCount
0x1800b9e3e  lea     rdx, asc_1805B9A8C; "\\\\"
0x1800b9e45  call    cs:__imp__wcsnicmp
0x1800b9e4c  nop     dword ptr [rax+rax+00h]
0x1800b9e51  movzx   edi, dil
0x1800b9e55  test    eax, eax
0x1800b9e57  mov     ecx, 1
0x1800b9e5c  cmovz   edi, ecx
0x1800b9e5f  mov     ecx, r15d
0x1800b9e62  movzx   eax, dil
0x1800b9e66  test    rsi, rsi
0x1800b9e69  cmovz   ecx, eax
0x1800b9e6c  mov     [rsp+840h+var_7D0], ecx
0x1800b9e70  xorps   xmm0, xmm0
0x1800b9e73  xor     eax, eax
0x1800b9e75  movups  [rbp+740h+var_7C0], xmm0
0x1800b9e79  movups  [rbp+740h+var_7B0], xmm0
0x1800b9e7d  movups  [rbp+740h+var_7A0], xmm0
0x1800b9e81  mov     [rbp+740h+var_790], eax
0x1800b9e84  mov     rcx, [rbx+58h]
0x1800b9e88  mov     rax, [rcx]
0x1800b9e8b  cmp     dword ptr [r14+224h], 2
0x1800b9e93  jb      short loc_1800B9E9E
0x1800b9e95  mov     r8, [r14+218h]
0x1800b9e9c  jmp     short loc_1800B9EA1
0x1800b9e9e  mov     r8, r15
0x1800b9ea1  mov     [rsp+840h+var_808], r15
0x1800b9ea6  mov     dword ptr [rsp+840h+var_810], 34h ; '4'
0x1800b9eae  lea     rdx, [rbp+740h+var_7C0]
0x1800b9eb2  mov     [rsp+840h+var_818], rdx
0x1800b9eb7  lea     rdx, asc_1805DF320; "\\"
0x1800b9ebe  mov     qword ptr [rsp+840h+var_820], rdx
0x1800b9ec3  mov     r9, [r14+20h]
0x1800b9ec7  mov     rdx, rbx
0x1800b9eca  mov     rax, [rax+310h]
0x1800b9ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9ed6  mov     r15d, eax
0x1800b9ed9  xor     edi, edi
0x1800b9edb  test    eax, eax
0x1800b9edd  jz      short loc_1800B9F3A
0x1800b9edf  mov     ecx, eax; int
0x1800b9ee1  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1800b9ee6  lea     rsi, [rbx+218h]
0x1800b9eed  mov     qword ptr [rsp+840h+var_820], rax
0x1800b9ef2  mov     r9, [r14+0E0h]
0x1800b9ef9  lea     r8, aErrorUnableToG; "ERROR: Unable to get version informatio"...
0x1800b9f00  mov     edx, 145h; BufferCount
0x1800b9f05  mov     rcx, rsi; Buffer
0x1800b9f08  call    PrintStringW
0x1800b9f0d  cmp     [rbp+740h+arg_30], dil
0x1800b9f14  jnz     short loc_1800B9F32
0x1800b9f16  mov     edi, 100h
0x1800b9f1b  test    [rbx+188h], edi
0x1800b9f21  jz      short loc_1800B9F32
0x1800b9f23  mov     rdx, rsi
0x1800b9f26  lea     rcx, aClrdllS; "CLRDLL: %s\n"
0x1800b9f2d  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800b9f32  mov     eax, r15d
0x1800b9f35  jmp     loc_1800BAC68
0x1800b9f3a  lea     eax, [r12-4]
0x1800b9f3f  test    eax, 0FFFFFFFDh
0x1800b9f44  jz      short loc_1800B9F94
0x1800b9f46  cmp     dword ptr [rbp+740h+var_7C0+8], 20000h
0x1800b9f4d  jnb     short loc_1800B9F94
0x1800b9f4f  lea     rsi, [rbx+218h]
0x1800b9f56  lea     r8, aDownlevelClrSo; "Downlevel CLR, sos.dll not available fo"...
0x1800b9f5d  mov     edx, 145h; BufferCount
0x1800b9f62  mov     rcx, rsi; Buffer
0x1800b9f65  call    PrintStringW
0x1800b9f6a  or      dword ptr [rbx+188h], 40h
0x1800b9f71  mov     edi, 100h
0x1800b9f76  test    [rbx+188h], edi
0x1800b9f7c  jz      loc_1800BAC41
0x1800b9f82  cmp     [rbp+740h+arg_30], 0
0x1800b9f89  jnz     loc_1800BAC41
0x1800b9f8f  jmp     loc_1800BAC32
0x1800b9f94  xor     r15d, r15d
0x1800b9f97  mov     [rbp+740h+var_270], r15w
0x1800b9f9f  mov     ecx, r12d
0x1800b9fa2  sub     ecx, 1
0x1800b9fa5  jz      loc_1800BAC03
0x1800b9fab  sub     ecx, 1
0x1800b9fae  jz      loc_1800BA11D
0x1800b9fb4  sub     ecx, 1
0x1800b9fb7  jz      loc_1800BA114
0x1800b9fbd  sub     ecx, 1
0x1800b9fc0  jz      loc_1800BA10B
0x1800b9fc6  sub     ecx, 1
0x1800b9fc9  jz      loc_1800BA11D
0x1800b9fcf  cmp     ecx, 1
0x1800b9fd2  jz      short loc_1800BA025
0x1800b9fd4  lea     rsi, [rbx+218h]
0x1800b9fdb  mov     r9, [r14+0E0h]
0x1800b9fe2  lea     r8, aErrorUnknownMs; "ERROR: Unknown mscor DLL type %s"
0x1800b9fe9  mov     edx, 145h; BufferCount
0x1800b9fee  mov     rcx, rsi; Buffer
0x1800b9ff1  call    PrintStringW
0x1800b9ff6  mov     edi, 100h
0x1800b9ffb  test    [rbx+188h], edi
0x1800ba001  jz      short loc_1800BA01B
0x1800ba003  cmp     [rbp+740h+arg_30], r15b
0x1800ba00a  jnz     short loc_1800BA01B
0x1800ba00c  mov     rdx, rsi
0x1800ba00f  lea     rcx, aClrdllS; "CLRDLL: %s\n"
0x1800ba016  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800ba01b  mov     eax, 80070057h
0x1800ba020  jmp     loc_1800BAC68
0x1800ba025  mov     esi, r15d
0x1800ba028  cmp     dword ptr [r14+224h], 2
0x1800ba030  jb      short loc_1800BA03B
0x1800ba032  cmp     [r14+218h], r15
0x1800ba039  jnz     short loc_1800BA040
0x1800ba03b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ba040  cmp     dword ptr [r14+224h], 2
0x1800ba048  jb      short loc_1800BA053
0x1800ba04a  mov     rcx, [r14+218h]
0x1800ba051  jmp     short loc_1800BA056
0x1800ba053  mov     rcx, r15; unsigned __int16 *
0x1800ba056  call    ?PathTail@@YAPEBGPEBG@Z; PathTail(ushort const *)
0x1800ba05b  mov     r15, rax
0x1800ba05e  mov     r8d, 3; MaxCount
0x1800ba064  lea     rdx, aMrt; "mrt"
0x1800ba06b  mov     rcx, rax; String1
0x1800ba06e  call    cs:__imp__wcsnicmp
0x1800ba075  nop     dword ptr [rax+rax+00h]
0x1800ba07a  test    eax, eax
0x1800ba07c  jnz     short loc_1800BA093
0x1800ba07e  movzx   ecx, word ptr [r15+6]; C
0x1800ba083  call    cs:__imp_isdigit
0x1800ba08a  nop     dword ptr [rax+rax+00h]
0x1800ba08f  test    eax, eax
0x1800ba091  jnz     short loc_1800BA098
0x1800ba093  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ba098  movzx   ecx, word ptr [r15+6]; C
0x1800ba09d  call    cs:__imp_isdigit
0x1800ba0a4  nop     dword ptr [rax+rax+00h]
0x1800ba0a9  test    eax, eax
0x1800ba0ab  jz      short loc_1800BA0EB
0x1800ba0ad  cmp     esi, 0Fh
0x1800ba0b0  jnb     loc_1800BAC41
0x1800ba0b6  lea     eax, [rsi+3]
0x1800ba0b9  mov     ecx, esi
0x1800ba0bb  movzx   eax, word ptr [r15+rax*2]
0x1800ba0c0  mov     [rbp+rcx*2+740h+var_270], ax
0x1800ba0c8  inc     esi
0x1800ba0ca  lea     eax, [rsi+3]
0x1800ba0cd  movzx   ecx, word ptr [r15+rax*2]; C
0x1800ba0d2  call    cs:__imp_isdigit
0x1800ba0d9  nop     dword ptr [rax+rax+00h]
0x1800ba0de  test    eax, eax
0x1800ba0e0  jnz     short loc_1800BA0AD
0x1800ba0e2  cmp     esi, 0Fh
0x1800ba0e5  jnb     loc_1800BAC41
0x1800ba0eb  mov     eax, esi
0x1800ba0ed  lea     rcx, [rax+rax]
0x1800ba0f1  cmp     rcx, 20h ; ' '
0x1800ba0f5  jnb     short loc_1800BA105
0x1800ba0f7  xor     r15d, r15d
0x1800ba0fa  mov     [rbp+rcx+740h+var_270], r15w
0x1800ba103  jmp     short loc_1800BA124
0x1800ba105  call    __report_rangecheckfailure
0x1800ba10b  lea     rdi, aCore; "core"
0x1800ba112  jmp     short loc_1800BA124
0x1800ba114  lea     rdi, aSvr; "svr"
0x1800ba11b  jmp     short loc_1800BA124
0x1800ba11d  lea     rdi, aWks; "wks"
0x1800ba124  mov     r10d, 1
0x1800ba12a  mov     byte ptr [rsp+840h+var_820], r10b
0x1800ba12f  mov     r9d, 0C8h
0x1800ba135  mov     r8d, r9d
0x1800ba138  lea     rdx, [rbp+740h+var_768]
0x1800ba13c  lea     rcx, [rbp+740h+var_780]
0x1800ba140  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x1800ba145  nop
0x1800ba146  mov     byte ptr [rsp+840h+var_820], r10b
0x1800ba14b  mov     r8d, r9d
0x1800ba14e  lea     rdx, [rbp+740h+var_5B8]
0x1800ba155  lea     rcx, [rbp+740h+var_5D0]
0x1800ba15c  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x1800ba161  nop
0x1800ba162  mov     byte ptr [rsp+840h+var_820], r10b
0x1800ba167  mov     r8d, r9d
0x1800ba16a  lea     rdx, [rbp+740h+var_408]
0x1800ba171  lea     rcx, [rbp+740h+var_420]
0x1800ba178  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x1800ba17d  nop
0x1800ba17e  lea     rdx, aX86_0; "x86"
0x1800ba185  mov     rcx, [r13+18h]; String1
0x1800ba189  call    cs:__imp__wcsicmp
0x1800ba190  nop     dword ptr [rax+rax+00h]
0x1800ba195  test    eax, eax
0x1800ba197  jz      loc_1800BABD7
0x1800ba19d  lea     rdx, aArm_0; "ARM"
0x1800ba1a4  mov     rcx, [r13+18h]; String1
0x1800ba1a8  call    cs:__imp__wcsicmp
0x1800ba1af  nop     dword ptr [rax+rax+00h]
0x1800ba1b4  test    eax, eax
0x1800ba1b6  jz      loc_1800BABD7
0x1800ba1bc  lea     rax, aChk; ".chk"
0x1800ba1c3  lea     rsi, aDbg_1; ".dbg"
0x1800ba1ca  lea     r10, aAmd64_0; "AMD64"
0x1800ba1d1  cmp     r12d, 6
0x1800ba1d5  jz      short loc_1800BA24D
0x1800ba1d7  mov     ecx, 1
0x1800ba1dc  test    byte ptr [rbp+740h+var_7B0+0Ch], cl
0x1800ba1df  jz      short loc_1800BA1EE
  ... truncated ...
```
