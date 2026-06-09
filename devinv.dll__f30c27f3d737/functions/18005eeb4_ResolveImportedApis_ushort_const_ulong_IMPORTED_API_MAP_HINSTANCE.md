# ResolveImportedApis(ushort const *,ulong,_IMPORTED_API_MAP *,HINSTANCE__ * *)

- ea: `0x18005eeb4`
- end: `0x18005fb0a`
- name: `?ResolveImportedApis@@YAJPEBGKPEAU_IMPORTED_API_MAP@@PEAPEAUHINSTANCE__@@@Z`
- size: `3158`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct _IMPORTED_API_MAP *, HINSTANCE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800466f4`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180006ec4`
- `0x180007014`
- `0x18000dbc8`
- `0x18000dcec`
- `0x18005eeb4`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005f9f9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005f9f9`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005f01f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005f01f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f213`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f35e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f597`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f213`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f35e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f597`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005fad1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005fad1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f7e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f7e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ef76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f02e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f8e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f9ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ef76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f02e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f8e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f9ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005ef4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005ef4e`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18005f51e`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18005f51e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005f258`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005f258`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005f459`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005f459`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18005ef68`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18005ef68`

## string_xrefs

- `0x18005f105`: `psapi.dll`
- `0x18005f26b`: `psapi.dll`
- `0x18005f54c`: `psapi.dll`
- `0x18005f9ed`: `dismapi.dll`
- `0x18005f055`: `[%#x] wcsrchr failed, dllFolder=%ws`
- `0x18005f141`: `[%#x] Failed StringCchPrintf, dllFolder=%ws`
- `0x18005f689`: `[%#x] GetSystemDirectory failed`
- `0x18005f38f`: `\compattel`
- `0x18005f468`: `Compattel folder does not exist`
- `0x18005f53a`: `[%#x] Failed SetDllDirectory`
- `0x18005f5d2`: `[%#x] Failed LoadLibraryExW for %ws`
- `0x18005fa0c`: `[%#x] LoadLibrary for dismapi.dll failed, 0x%08x, 0x%08x, 0x%08x`

## pseudocode

```c
__int64 __fastcall ResolveImportedApis(
        const unsigned __int16 *a1,
        __int64 a2,
        struct _IMPORTED_API_MAP *a3,
        HINSTANCE *a4)
{
  struct _IMPORTED_API_MAP *v4; // rbx
  unsigned int v5; // r14d
  unsigned int v6; // r13d
  HMODULE v7; // r12
  __int64 i; // rcx
  __int64 v9; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v12; // edi
  const char *v13; // rbx
  FILE *v14; // rax
  FILE *v15; // rax
  FILE *v16; // rax
  bool v17; // zf
  wchar_t *v18; // rax
  signed int v19; // eax
  const char *v20; // rbx
  FILE *v21; // rax
  FILE *v22; // rax
  FILE *v23; // rax
  WCHAR *v24; // r9
  __int64 v25; // r8
  __int64 v26; // rcx
  FILE *v27; // rax
  FILE *v28; // rax
  FILE *v29; // rax
  signed int v30; // eax
  int v31; // eax
  FILE *v32; // rax
  FILE *v33; // rax
  FILE *v34; // rax
  signed int v35; // eax
  unsigned __int64 v36; // rdx
  const char *v37; // rbx
  __int64 v38; // r14
  FILE *v39; // rax
  FILE *v40; // rax
  FILE *v41; // rax
  FILE *v42; // rax
  FILE *v43; // rax
  FILE *v44; // rax
  signed int v45; // eax
  __int64 v46; // r14
  signed int v47; // eax
  FILE *v48; // rax
  FILE *v49; // rax
  FILE *v50; // rax
  signed int v51; // eax
  FILE *v52; // rax
  FILE *v53; // rax
  FILE *v54; // rax
  FILE *v55; // rax
  FILE *v56; // rax
  FILE *v57; // rax
  unsigned int v58; // edi
  __int64 v59; // r15
  FILE *v60; // rax
  __int64 v61; // rbx
  FILE *v62; // rax
  FILE *v63; // rax
  signed int v64; // eax
  FILE *v65; // rax
  signed int v66; // eax
  unsigned int v67; // r12d
  __int64 v68; // rbx
  FILE *v69; // rax
  FILE *v70; // rax
  signed int v71; // eax
  FILE *v72; // rax
  FILE *v73; // rax
  FILE *v74; // rax
  __int64 v76; // [rsp+20h] [rbp-E0h]
  __int64 v77; // [rsp+20h] [rbp-E0h]
  __int64 v78; // [rsp+20h] [rbp-E0h]
  unsigned int v79; // [rsp+40h] [rbp-C0h]
  unsigned int v80; // [rsp+44h] [rbp-BCh]
  HMODULE Library; // [rsp+48h] [rbp-B8h]
  WCHAR LibFileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+270h] [rbp+170h] BYREF

  v4 = a3;
  memset_0(Filename, 0, 0x208u);
  memset_0(LibFileName, 0, 0x208u);
  if ( v4 )
  {
    v5 = 0;
    v79 = 0;
    v80 = 0;
    v6 = 0;
    v7 = 0;
    for ( i = 0; i != 2; ++i )
    {
      v9 = i;
      **((_QWORD **)v4 + 2 * v9 + 1) = 0;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !K32GetModuleFileNameExW(CurrentProcess, 0, Filename, 0x104u) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      v13 = "[%#x] GetModuleFileNameEx failed";
      AslLogCallPrintf(2, "ResolveImportedApis", 690, "[%#x] GetModuleFileNameEx failed", v12);
      if ( EnableDevInvStdErrLog )
      {
        v14 = o___acrt_iob_func_0(2u);
        fprintf(v14, "Error: %s, %u: ", "ResolveImportedApis", 690);
        v15 = o___acrt_iob_func_0(2u);
        fprintf(v15, "[%#x] GetModuleFileNameEx failed", v12);
        v16 = o___acrt_iob_func_0(2u);
        fprintf(v16, "\n");
      }
      v17 = g_DeviceMapLogFunction == 0;
LABEL_68:
      if ( !v17 )
        TraceMessageCallback(0x2000000, v13, v12);
      goto LABEL_70;
    }
    v18 = wcsrchr(Filename, 0x5Cu);
    if ( !v18 )
    {
      v19 = GetLastError();
      v12 = v19;
      if ( v19 > 0 )
        v12 = (unsigned __int16)v19 | 0x80070000;
      v20 = "[%#x] wcsrchr failed, dllFolder=%ws";
      AslLogCallPrintf(2, "ResolveImportedApis", 698, "[%#x] wcsrchr failed, dllFolder=%ws", v12, Filename);
      if ( EnableDevInvStdErrLog )
      {
        v21 = o___acrt_iob_func_0(2u);
        fprintf(v21, "Error: %s, %u: ", "ResolveImportedApis", 698);
        v22 = o___acrt_iob_func_0(2u);
        fprintf(v22, "[%#x] wcsrchr failed, dllFolder=%ws", v12, Filename);
        v23 = o___acrt_iob_func_0(2u);
        fprintf(v23, "\n");
      }
      if ( g_DeviceMapLogFunction )
      {
        v24 = Filename;
        v25 = v12;
        v26 = 0x2000000;
LABEL_17:
        TraceMessageCallback(v26, v20, v25, v24);
        goto LABEL_70;
      }
      goto LABEL_70;
    }
    *v18 = 0;
    v12 = StringCchPrintfW(LibFileName, 0x104u, L"%ls\\%ls", Filename, L"psapi.dll");
    if ( (v12 & 0x80000000) != 0 )
    {
      LODWORD(v76) = v12;
      AslLogCallPrintf(2, "ResolveImportedApis", 706, "[%#x] Failed StringCchPrintf, dllFolder=%ws", v76, Filename);
      if ( EnableDevInvStdErrLog )
      {
        v27 = o___acrt_iob_func_0(2u);
        fprintf(v27, "Error: %s, %u: ", "ResolveImportedApis", 706);
        v28 = o___acrt_iob_func_0(2u);
        fprintf(v28, "[%#x] Failed StringCchPrintf, dllFolder=%ws", v12, Filename);
        v29 = o___acrt_iob_func_0(2u);
        fprintf(v29, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "[%#x] Failed StringCchPrintf, dllFolder=%ws", v12, Filename);
      LODWORD(v77) = v12;
      AslLogCallPrintf(1, "ResolveImportedApis", 706, "[%#x] Failed StringCchPrintf, dllFolder=%ws", v77, Filename);
      goto LABEL_95;
    }
    Library = LoadLibraryExW(LibFileName, 0, 0);
    v7 = Library;
    if ( !Library )
    {
      v30 = GetLastError();
      v79 = v30;
      if ( v30 > 0 )
        v79 = (unsigned __int16)v30 | 0x80070000;
      if ( GetSystemDirectoryW(Filename, 0x104u) - 1 > 0x103 )
      {
        v51 = GetLastError();
        v12 = v51;
        if ( v51 > 0 )
          v12 = (unsigned __int16)v51 | 0x80070000;
        v13 = "[%#x] GetSystemDirectory failed";
        v46 = 724;
        goto LABEL_65;
      }
      v31 = StringCchPrintfW(LibFileName, 0x104u, L"%ls\\%ls", Filename, L"psapi.dll");
      v12 = v31;
      if ( v31 < 0 )
      {
        AslLogCallPrintf(2, "ResolveImportedApis", 731, "[%#x] Failed StringCchPrintf", v31);
        if ( EnableDevInvStdErrLog )
        {
          v32 = o___acrt_iob_func_0(2u);
          fprintf(v32, "Error: %s, %u: ", "ResolveImportedApis", 731);
          v33 = o___acrt_iob_func_0(2u);
          fprintf(v33, "[%#x] Failed StringCchPrintf", v12);
          v34 = o___acrt_iob_func_0(2u);
          fprintf(v34, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "[%#x] Failed StringCchPrintf", v12);
        AslLogCallPrintf(1, "ResolveImportedApis", 731, "[%#x] Failed StringCchPrintf", v12);
LABEL_94:
        v5 = v79;
LABEL_95:
        if ( wcsstr(LibFileName, L"dismapi.dll") )
        {
          AslLogCallPrintf(
            2,
            "ResolveImportedApis",
            836,
            "[%#x] LoadLibrary for dismapi.dll failed, 0x%08x, 0x%08x, 0x%08x",
            v12,
            v5,
            v80,
            v6);
          if ( EnableDevInvStdErrLog )
          {
            v72 = o___acrt_iob_func_0(2u);
            fprintf(v72, "Error: %s, %u: ", "ResolveImportedApis", 836);
            v73 = o___acrt_iob_func_0(2u);
            fprintf(v73, "[%#x] LoadLibrary for dismapi.dll failed, 0x%08x, 0x%08x, 0x%08x", v12, v5, v80, v6);
            v74 = o___acrt_iob_func_0(2u);
            fprintf(v74, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(
              0x2000000,
              "[%#x] LoadLibrary for dismapi.dll failed, 0x%08x, 0x%08x, 0x%08x",
              v12,
              v5,
              v80,
              v6);
        }
        if ( v7 )
          FreeLibrary(v7);
        return v12;
      }
      Library = LoadLibraryExW(LibFileName, 0, 0);
      v7 = Library;
      if ( !Library )
      {
        v35 = GetLastError();
        v80 = v35;
        if ( v35 > 0 )
          v80 = (unsigned __int16)v35 | 0x80070000;
        v12 = StringCchCatW(Filename, v36, L"\\compattel");
        if ( (v12 & 0x80000000) != 0 )
        {
          v37 = "[%#x] StringCchCat";
          v38 = 749;
LABEL_39:
          LODWORD(v76) = v12;
          AslLogCallPrintf(2, "ResolveImportedApis", v38, v37, v76);
          if ( EnableDevInvStdErrLog )
          {
            v39 = o___acrt_iob_func_0(2u);
            fprintf(v39, "Error: %s, %u: ", "ResolveImportedApis", v38);
            v40 = o___acrt_iob_func_0(2u);
            fprintf(v40, v37, v12);
            v41 = o___acrt_iob_func_0(2u);
            fprintf(v41, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(0x2000000, v37, v12);
          goto LABEL_94;
        }
        if ( GetFileAttributesW(Filename) == -1 )
        {
          v12 = -2147024894;
          AslLogCallPrintf(2, "ResolveImportedApis", 761, "Compattel folder does not exist");
          if ( EnableDevInvStdErrLog )
          {
            v42 = o___acrt_iob_func_0(2u);
            fprintf(v42, "Warning: %s, %u: ", "ResolveImportedApis", 761);
            v43 = o___acrt_iob_func_0(2u);
            fprintf(v43, "Compattel folder does not exist");
            v44 = o___acrt_iob_func_0(2u);
            fprintf(v44, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(50331648, "Compattel folder does not exist");
          goto LABEL_94;
        }
        if ( dword_180155C64 )
        {
          dword_180155C64 = 0;
          if ( !SetDllDirectoryW(Filename) )
          {
            v45 = GetLastError();
            v12 = v45;
            if ( v45 > 0 )
              v12 = (unsigned __int16)v45 | 0x80070000;
            v13 = "[%#x] Failed SetDllDirectory";
            v46 = 778;
LABEL_65:
            LODWORD(v76) = v12;
            AslLogCallPrintf(2, "ResolveImportedApis", v46, v13, v76);
            if ( EnableDevInvStdErrLog )
            {
              v52 = o___acrt_iob_func_0(2u);
              fprintf(v52, "Error: %s, %u: ", "ResolveImportedApis", v46);
              v53 = o___acrt_iob_func_0(2u);
              fprintf(v53, v13, v12);
              v54 = o___acrt_iob_func_0(2u);
              fprintf(v54, "\n");
            }
            v17 = g_DeviceMapLogFunction == 0;
            goto LABEL_68;
          }
        }
        v12 = StringCchPrintfW(LibFileName, 0x104u, L"%ls\\%ls", Filename, L"psapi.dll");
        if ( (v12 & 0x80000000) != 0 )
        {
          v37 = "[%#x] Failed StringCchPrintf";
          v38 = 786;
          goto LABEL_39;
        }
        Library = LoadLibraryExW(LibFileName, 0, 0);
        v7 = Library;
        if ( !Library )
        {
          v47 = GetLastError();
          v6 = v47;
          if ( v47 > 0 )
            v6 = (unsigned __int16)v47 | 0x80070000;
          v20 = "[%#x] Failed LoadLibraryExW for %ws";
          LODWORD(v76) = v6;
          v12 = v6;
          AslLogCallPrintf(2, "ResolveImportedApis", 795, "[%#x] Failed LoadLibraryExW for %ws", v76, LibFileName);
          if ( EnableDevInvStdErrLog )
          {
            v48 = o___acrt_iob_func_0(2u);
            fprintf(v48, "Warning: %s, %u: ", "ResolveImportedApis", 795);
            v49 = o___acrt_iob_func_0(2u);
            fprintf(v49, "[%#x] Failed LoadLibraryExW for %ws", v6, LibFileName);
            v50 = o___acrt_iob_func_0(2u);
            fprintf(v50, "\n");
          }
          if ( g_DeviceMapLogFunction )
          {
            v24 = LibFileName;
            v25 = v6;
            v26 = 50331648;
            goto LABEL_17;
          }
LABEL_70:
          if ( (v12 & 0x80000000) == 0 )
            return v12;
          goto LABEL_94;
        }
      }
    }
    AslLogCallPrintf(3, "ResolveImportedApis", 801, "Library [%ws] loaded successfully", LibFileName);
    if ( EnableDevInvStdErrLog )
    {
      v55 = o___acrt_iob_func_0(2u);
      fprintf(v55, "Info: %s, %u: ", "ResolveImportedApis", 801);
      v56 = o___acrt_iob_func_0(2u);
      fprintf(v56, "Library [%ws] loaded successfully", LibFileName);
      v57 = o___acrt_iob_func_0(2u);
      fprintf(v57, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x4000000, "Library [%ws] loaded successfully", LibFileName);
    v58 = 0;
    while ( 1 )
    {
      v59 = 2LL * v58;
      **((_QWORD **)v4 + 2 * v58 + 1) = GetProcAddress(v7, *((LPCSTR *)v4 + 2 * v58));
      if ( !**((_QWORD **)v4 + 2 * v58 + 1) )
        break;
      AslLogCallPrintf(
        3,
        "ResolveImportedApis",
        822,
        "Function [%hs] from library [%ws] imported successfully",
        *((_QWORD *)v4 + 2 * v58),
        LibFileName);
      if ( EnableDevInvStdErrLog )
      {
        v60 = o___acrt_iob_func_0(2u);
        fprintf(v60, "Info: %s, %u: ", "ResolveImportedApis", 822);
        v61 = *((_QWORD *)v4 + 2 * v58);
        v62 = o___acrt_iob_func_0(2u);
        fprintf(v62, "Function [%hs] from library [%ws] imported successfully", v61, LibFileName);
        v63 = o___acrt_iob_func_0(2u);
        fprintf(v63, "\n");
        v4 = a3;
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(
          0x4000000,
          "Function [%hs] from library [%ws] imported successfully",
          *((_QWORD *)v4 + 2 * v58),
          LibFileName);
      if ( ++v58 >= 2 )
      {
        v12 = 0;
        *a4 = v7;
        return v12;
      }
    }
    v12 = -2147467263;
    v64 = GetLastError();
    if ( v64 > 0 )
      v64 = (unsigned __int16)v64 | 0x80070000;
    AslLogCallPrintf(
      2,
      "ResolveImportedApis",
      818,
      "GetProcAddress failed for [%hs] [%ws] with [%#x]",
      *((_QWORD *)v4 + v59),
      LibFileName,
      v64);
    if ( EnableDevInvStdErrLog )
    {
      v65 = o___acrt_iob_func_0(2u);
      fprintf(v65, "Warning: %s, %u: ", "ResolveImportedApis", 818);
      v66 = GetLastError();
      v67 = v66;
      if ( v66 > 0 )
        v67 = (unsigned __int16)v66 | 0x80070000;
      v68 = *((_QWORD *)v4 + v59);
      v69 = o___acrt_iob_func_0(2u);
      LODWORD(v78) = v67;
      fprintf(v69, "GetProcAddress failed for [%hs] [%ws] with [%#x]", v68, LibFileName, v78);
      v70 = o___acrt_iob_func_0(2u);
      fprintf(v70, "\n");
      v4 = a3;
      v7 = Library;
    }
    if ( g_DeviceMapLogFunction )
    {
      v71 = GetLastError();
      if ( v71 > 0 )
        v71 = (unsigned __int16)v71 | 0x80070000;
      LODWORD(v78) = v71;
      TraceMessageCallback(
        50331648,
        "GetProcAddress failed for [%hs] [%ws] with [%#x]",
        *((_QWORD *)v4 + v59),
        LibFileName,
        v78);
    }
    goto LABEL_94;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18005eeb4  mov     [rsp-8+arg_0], rbx
0x18005eeb9  push    rbp
0x18005eeba  push    rsi
0x18005eebb  push    rdi
0x18005eebc  push    r12
0x18005eebe  push    r13
0x18005eec0  push    r14
0x18005eec2  push    r15
0x18005eec4  lea     rbp, [rsp-390h]
0x18005eecc  sub     rsp, 490h
0x18005eed3  mov     rax, cs:__security_cookie
0x18005eeda  xor     rax, rsp
0x18005eedd  mov     [rbp+3C0h+var_40], rax
0x18005eee4  mov     rbx, r8
0x18005eee7  mov     [rsp+4C0h+var_468], r9
0x18005eeec  mov     edi, 208h
0x18005eef1  mov     [rsp+4C0h+var_470], rbx
0x18005eef6  mov     r8d, edi; Size
0x18005eef9  lea     rcx, [rbp+3C0h+Filename]; void *
0x18005ef00  xor     edx, edx; Val
0x18005ef02  call    memset_0
0x18005ef07  mov     r8d, edi; Size
0x18005ef0a  lea     rcx, [rsp+4C0h+LibFileName]; void *
0x18005ef0f  xor     edx, edx; Val
0x18005ef11  call    memset_0
0x18005ef16  xor     esi, esi
0x18005ef18  test    rbx, rbx
0x18005ef1b  jz      loc_18005FADB
0x18005ef21  mov     r14d, esi
0x18005ef24  mov     [rsp+4C0h+var_480], esi
0x18005ef28  mov     [rsp+4C0h+var_47C], esi
0x18005ef2c  lea     r15d, [rsi+2]
0x18005ef30  mov     r13d, esi
0x18005ef33  mov     r12d, esi
0x18005ef36  mov     ecx, esi
0x18005ef38  mov     rax, rcx
0x18005ef3b  inc     rcx
0x18005ef3e  add     rax, rax
0x18005ef41  mov     rax, [rbx+rax*8+8]
0x18005ef46  mov     [rax], rsi
0x18005ef49  cmp     rcx, r15
0x18005ef4c  jnz     short loc_18005EF38
0x18005ef4e  call    cs:__imp_GetCurrentProcess
0x18005ef54  mov     edi, 104h
0x18005ef59  lea     r8, [rbp+3C0h+Filename]; lpFilename
0x18005ef60  mov     rcx, rax; hProcess
0x18005ef63  mov     r9d, edi; nSize
0x18005ef66  xor     edx, edx; hModule
0x18005ef68  call    cs:__imp_K32GetModuleFileNameExW
0x18005ef6e  test    eax, eax
0x18005ef70  jnz     loc_18005F013
0x18005ef76  call    cs:__imp_GetLastError
0x18005ef7c  mov     edi, eax
0x18005ef7e  test    eax, eax
0x18005ef80  jle     short loc_18005EF8B
0x18005ef82  movzx   edi, ax
0x18005ef85  or      edi, 80070000h
0x18005ef8b  lea     rbx, aXGetmodulefile; "[%#x] GetModuleFileNameEx failed"
0x18005ef92  mov     dword ptr [rsp+4C0h+var_4A0], edi
0x18005ef96  mov     r14d, 2B2h
0x18005ef9c  lea     rsi, aResolveimporte; "ResolveImportedApis"
0x18005efa3  mov     r9, rbx
0x18005efa6  mov     r8d, r14d
0x18005efa9  mov     rdx, rsi
0x18005efac  mov     ecx, r15d
0x18005efaf  call    AslLogCallPrintf
0x18005efb4  cmp     cs:EnableDevInvStdErrLog, r12d
0x18005efbb  jz      short loc_18005F007
0x18005efbd  mov     ecx, r15d; Ix
0x18005efc0  call    _o___acrt_iob_func_0
0x18005efc5  mov     rcx, rax; Stream
0x18005efc8  lea     rdx, Format; "Error: %s, %u: "
0x18005efcf  mov     r9d, r14d
0x18005efd2  mov     r8, rsi
0x18005efd5  call    fprintf
0x18005efda  mov     ecx, r15d; Ix
0x18005efdd  call    _o___acrt_iob_func_0
0x18005efe2  mov     rcx, rax; Stream
0x18005efe5  mov     r8d, edi
0x18005efe8  mov     rdx, rbx; Format
0x18005efeb  call    fprintf
0x18005eff0  mov     ecx, r15d; Ix
0x18005eff3  call    _o___acrt_iob_func_0
0x18005eff8  mov     rcx, rax; Stream
0x18005effb  lea     rdx, asc_18011EAD8; "\n"
0x18005f002  call    fprintf
0x18005f007  cmp     cs:g_DeviceMapLogFunction, r12
0x18005f00e  jmp     loc_18005F712
0x18005f013  mov     edx, 5Ch ; '\'; Ch
0x18005f018  lea     rcx, [rbp+3C0h+Filename]; Str
0x18005f01f  call    cs:__imp_wcsrchr
0x18005f025  test    rax, rax
0x18005f028  jnz     loc_18005F0FB
0x18005f02e  call    cs:__imp_GetLastError
0x18005f034  mov     edi, eax
0x18005f036  test    eax, eax
0x18005f038  jle     short loc_18005F043
0x18005f03a  movzx   edi, ax
0x18005f03d  or      edi, 80070000h
0x18005f043  lea     rax, [rbp+3C0h+Filename]
0x18005f04a  mov     r14d, 2BAh
0x18005f050  mov     [rsp+4C0h+var_498], rax
0x18005f055  lea     rbx, aXWcsrchrFailed; "[%#x] wcsrchr failed, dllFolder=%ws"
0x18005f05c  lea     rsi, aResolveimporte; "ResolveImportedApis"
0x18005f063  mov     dword ptr [rsp+4C0h+var_4A0], edi
0x18005f067  mov     r9, rbx
0x18005f06a  mov     r8d, r14d
0x18005f06d  mov     rdx, rsi
0x18005f070  mov     ecx, r15d
0x18005f073  call    AslLogCallPrintf
0x18005f078  cmp     cs:EnableDevInvStdErrLog, r12d
0x18005f07f  jz      short loc_18005F0D2
0x18005f081  mov     ecx, r15d; Ix
0x18005f084  call    _o___acrt_iob_func_0
0x18005f089  mov     rcx, rax; Stream
0x18005f08c  lea     rdx, Format; "Error: %s, %u: "
0x18005f093  mov     r9d, r14d
0x18005f096  mov     r8, rsi
0x18005f099  call    fprintf
0x18005f09e  mov     ecx, r15d; Ix
0x18005f0a1  call    _o___acrt_iob_func_0
0x18005f0a6  mov     rcx, rax; Stream
0x18005f0a9  lea     r9, [rbp+3C0h+Filename]
0x18005f0b0  mov     r8d, edi
0x18005f0b3  mov     rdx, rbx; Format
0x18005f0b6  call    fprintf
0x18005f0bb  mov     ecx, r15d; Ix
0x18005f0be  call    _o___acrt_iob_func_0
0x18005f0c3  mov     rcx, rax; Stream
0x18005f0c6  lea     rdx, asc_18011EAD8; "\n"
0x18005f0cd  call    fprintf
0x18005f0d2  cmp     cs:g_DeviceMapLogFunction, r12
0x18005f0d9  jz      loc_18005F724
0x18005f0df  lea     r9, [rbp+3C0h+Filename]
0x18005f0e6  mov     r8d, edi
0x18005f0e9  mov     ecx, 2000000h
0x18005f0ee  mov     rdx, rbx
0x18005f0f1  call    TraceMessageCallback
0x18005f0f6  jmp     loc_18005F724
0x18005f0fb  mov     [rax], si
0x18005f0fe  lea     r9, [rbp+3C0h+Filename]
0x18005f105  lea     rax, aPsapiDll; "psapi.dll"
0x18005f10c  mov     rdx, rdi; unsigned __int64
0x18005f10f  lea     r8, aLsLs; "%ls\\%ls"
0x18005f116  mov     [rsp+4C0h+var_4A0], rax
0x18005f11b  lea     rcx, [rsp+4C0h+LibFileName]; unsigned __int16 *
0x18005f120  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005f125  mov     edi, eax
0x18005f127  test    eax, eax
0x18005f129  jns     loc_18005F209
0x18005f12f  lea     rax, [rbp+3C0h+Filename]
0x18005f136  mov     r8d, 2C2h
0x18005f13c  mov     [rsp+4C0h+var_498], rax
0x18005f141  lea     rbx, aXFailedStringc_0; "[%#x] Failed StringCchPrintf, dllFolder"...
0x18005f148  lea     rsi, aResolveimporte; "ResolveImportedApis"
0x18005f14f  mov     dword ptr [rsp+4C0h+var_4A0], edi
0x18005f153  mov     r9, rbx
0x18005f156  mov     rdx, rsi
0x18005f159  mov     ecx, r15d
0x18005f15c  call    AslLogCallPrintf
0x18005f161  cmp     cs:EnableDevInvStdErrLog, r12d
0x18005f168  jz      short loc_18005F1BE
0x18005f16a  mov     ecx, r15d; Ix
0x18005f16d  call    _o___acrt_iob_func_0
0x18005f172  mov     rcx, rax; Stream
0x18005f175  lea     rdx, Format; "Error: %s, %u: "
0x18005f17c  mov     r9d, 2C2h
0x18005f182  mov     r8, rsi
0x18005f185  call    fprintf
0x18005f18a  mov     ecx, r15d; Ix
0x18005f18d  call    _o___acrt_iob_func_0
0x18005f192  mov     rcx, rax; Stream
0x18005f195  lea     r9, [rbp+3C0h+Filename]
0x18005f19c  mov     r8d, edi
0x18005f19f  mov     rdx, rbx; Format
0x18005f1a2  call    fprintf
0x18005f1a7  mov     ecx, r15d; Ix
0x18005f1aa  call    _o___acrt_iob_func_0
0x18005f1af  mov     rcx, rax; Stream
0x18005f1b2  lea     rdx, asc_18011EAD8; "\n"
0x18005f1b9  call    fprintf
0x18005f1be  cmp     cs:g_DeviceMapLogFunction, r12
0x18005f1c5  jz      short loc_18005F1DE
0x18005f1c7  lea     r9, [rbp+3C0h+Filename]
0x18005f1ce  mov     r8d, edi
0x18005f1d1  mov     rdx, rbx
0x18005f1d4  mov     ecx, 2000000h
0x18005f1d9  call    TraceMessageCallback
0x18005f1de  lea     rax, [rbp+3C0h+Filename]
0x18005f1e5  mov     r9, rbx
0x18005f1e8  mov     [rsp+4C0h+var_498], rax
0x18005f1ed  mov     r8d, 2C2h
0x18005f1f3  mov     rdx, rsi
0x18005f1f6  mov     dword ptr [rsp+4C0h+var_4A0], edi
0x18005f1fa  mov     ecx, 1
0x18005f1ff  call    AslLogCallPrintf
0x18005f204  jmp     loc_18005F9ED
0x18005f209  xor     r8d, r8d; dwFlags
0x18005f20c  lea     rcx, [rsp+4C0h+LibFileName]; lpLibFileName
0x18005f211  xor     edx, edx; hFile
0x18005f213  call    cs:__imp_LoadLibraryExW
0x18005f219  mov     [rsp+4C0h+var_478], rax
0x18005f21e  mov     r12, rax
0x18005f221  mov     r14d, 80070000h
0x18005f227  test    rax, rax
0x18005f22a  jnz     loc_18005F737
0x18005f230  call    cs:__imp_GetLastError
0x18005f236  mov     [rsp+4C0h+var_480], eax
0x18005f23a  test    eax, eax
0x18005f23c  jle     short loc_18005F24A
0x18005f23e  movzx   r15d, ax
0x18005f242  or      r15d, r14d
0x18005f245  mov     [rsp+4C0h+var_480], r15d
0x18005f24a  mov     edi, 104h
0x18005f24f  lea     rcx, [rbp+3C0h+Filename]; lpBuffer
0x18005f256  mov     edx, edi; uSize
0x18005f258  call    cs:__imp_GetSystemDirectoryW
0x18005f25e  dec     eax
0x18005f260  cmp     eax, 103h
0x18005f265  ja      loc_18005F677
0x18005f26b  lea     rax, aPsapiDll; "psapi.dll"
0x18005f272  mov     edx, edi; unsigned __int64
0x18005f274  lea     r9, [rbp+3C0h+Filename]
0x18005f27b  mov     [rsp+4C0h+var_4A0], rax
0x18005f280  lea     r8, aLsLs; "%ls\\%ls"
0x18005f287  lea     rcx, [rsp+4C0h+LibFileName]; unsigned __int16 *
0x18005f28c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005f291  mov     edi, eax
0x18005f293  test    eax, eax
0x18005f295  jns     loc_18005F354
0x18005f29b  lea     rbx, aXFailedStringc; "[%#x] Failed StringCchPrintf"
0x18005f2a2  mov     dword ptr [rsp+4C0h+var_4A0], eax
0x18005f2a6  mov     r14d, 2DBh
0x18005f2ac  lea     rsi, aResolveimporte; "ResolveImportedApis"
0x18005f2b3  mov     r9, rbx
0x18005f2b6  mov     r8d, r14d
0x18005f2b9  mov     rdx, rsi
0x18005f2bc  mov     ecx, 2
0x18005f2c1  call    AslLogCallPrintf
0x18005f2c6  cmp     cs:EnableDevInvStdErrLog, r13d
0x18005f2cd  jz      short loc_18005F31F
0x18005f2cf  mov     ecx, 2; Ix
0x18005f2d4  call    _o___acrt_iob_func_0
0x18005f2d9  mov     rcx, rax; Stream
0x18005f2dc  lea     rdx, Format; "Error: %s, %u: "
0x18005f2e3  mov     r9d, r14d
0x18005f2e6  mov     r8, rsi
0x18005f2e9  call    fprintf
0x18005f2ee  mov     ecx, 2; Ix
0x18005f2f3  call    _o___acrt_iob_func_0
0x18005f2f8  mov     rcx, rax; Stream
0x18005f2fb  mov     r8d, edi
0x18005f2fe  mov     rdx, rbx; Format
0x18005f301  call    fprintf
0x18005f306  mov     ecx, 2; Ix
0x18005f30b  call    _o___acrt_iob_func_0
0x18005f310  mov     rcx, rax; Stream
0x18005f313  lea     rdx, asc_18011EAD8; "\n"
0x18005f31a  call    fprintf
0x18005f31f  cmp     cs:g_DeviceMapLogFunction, r13
0x18005f326  jz      short loc_18005F338
0x18005f328  mov     r8d, edi
0x18005f32b  mov     rdx, rbx
0x18005f32e  mov     ecx, 2000000h
0x18005f333  call    TraceMessageCallback
0x18005f338  mov     r9, rbx
0x18005f33b  mov     dword ptr [rsp+4C0h+var_4A0], edi
0x18005f33f  mov     r8, r14
0x18005f342  mov     rdx, rsi
0x18005f345  mov     ecx, 1
0x18005f34a  call    AslLogCallPrintf
0x18005f34f  jmp     loc_18005F9E8
0x18005f354  xor     r8d, r8d; dwFlags
0x18005f357  lea     rcx, [rsp+4C0h+LibFileName]; lpLibFileName
0x18005f35c  xor     edx, edx; hFile
0x18005f35e  call    cs:__imp_LoadLibraryExW
0x18005f364  mov     [rsp+4C0h+var_478], rax
0x18005f369  mov     r12, rax
0x18005f36c  test    rax, rax
0x18005f36f  jnz     loc_18005F731
0x18005f375  call    cs:__imp_GetLastError
0x18005f37b  mov     [rsp+4C0h+var_47C], eax
0x18005f37f  test    eax, eax
0x18005f381  jle     short loc_18005F38F
0x18005f383  movzx   r15d, ax
0x18005f387  or      r15d, r14d
0x18005f38a  mov     [rsp+4C0h+var_47C], r15d
0x18005f38f  lea     r8, aCompattel; "\\compattel"
0x18005f396  lea     rcx, [rbp+3C0h+Filename]; unsigned __int16 *
0x18005f39d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005f3a2  mov     edi, eax
0x18005f3a4  test    eax, eax
0x18005f3a6  jns     loc_18005F452
0x18005f3ac  lea     rbx, aXStringcchcat; "[%#x] StringCchCat"
0x18005f3b3  mov     r14d, 2EDh
0x18005f3b9  lea     rsi, aResolveimporte; "ResolveImportedApis"
0x18005f3c0  mov     dword ptr [rsp+4C0h+var_4A0], edi
0x18005f3c4  mov     rdx, rsi
0x18005f3c7  mov     r9, rbx
0x18005f3ca  mov     r8, r14
  ... truncated ...
```
