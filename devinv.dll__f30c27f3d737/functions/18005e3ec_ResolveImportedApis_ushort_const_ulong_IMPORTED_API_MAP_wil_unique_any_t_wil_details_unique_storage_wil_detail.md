# ResolveImportedApis(ushort const *,ulong,_IMPORTED_API_MAP *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &)

- ea: `0x18005e3ec`
- end: `0x18005eeab`
- name: `?ResolveImportedApis@@YAJPEBGKPEAU_IMPORTED_API_MAP@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `2751`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034d4c`
- `0x180038184`
- `0x18004e618`
- `0x18005a510`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180006ec4`
- `0x180007014`
- `0x18000dbc8`
- `0x18000dcec`
- `0x18005e3ec`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005e568`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005e568`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005e755`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005e89c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005eacd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005e755`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005e89c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005eacd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005e772`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005e8b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005eaed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005e772`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005e8b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005eaed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005eca6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005eca6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e77a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e8c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005eaf5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e77a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e8c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005eaf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e4aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e8ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e9cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eb08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ebc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005edf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e4aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e8ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e9cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eb08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ebc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005edf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005e482`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005e482`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18005e9c5`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18005e9c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005e79e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005e79e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005e909`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005e909`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18005e49c`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18005e49c`

## string_xrefs

- `0x18005e59e`: `[%#x] wcsrchr failed, dllFolder=%ws`
- `0x18005e685`: `[%#x] Failed StringCchPrintf, dllFolder=%ws`
- `0x18005ebda`: `[%#x] GetSystemDirectory failed`
- `0x18005e8d7`: `\compattel`
- `0x18005e918`: `Compattel folder does not exist`
- `0x18005e9e4`: `[%#x] Failed SetDllDirectory`
- `0x18005eb2d`: `[%#x] Failed LoadLibraryExW for %ws`

## pseudocode

```c
__int64 __fastcall ResolveImportedApis(__int64 a1, unsigned int a2, __int64 a3, HMODULE *a4)
{
  unsigned int i; // ecx
  __int64 v9; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v12; // ebx
  const char *v13; // r15
  __int64 v14; // r12
  FILE *v15; // rax
  FILE *v16; // rax
  FILE *v17; // rax
  wchar_t *v19; // rax
  signed int v20; // eax
  const char *v21; // r15
  FILE *v22; // rax
  FILE *v23; // rax
  FILE *v24; // rax
  WCHAR *v25; // r9
  __int64 v26; // rcx
  FILE *v27; // rax
  FILE *v28; // rax
  FILE *v29; // rax
  HMODULE Library; // rax
  HMODULE v31; // r14
  HMODULE v32; // rsi
  DWORD v33; // ebx
  unsigned int v34; // r14d
  int v35; // eax
  unsigned int v36; // r14d
  FILE *v37; // rax
  FILE *v38; // rax
  FILE *v39; // rax
  HMODULE v40; // rax
  unsigned __int64 v41; // rdx
  HMODULE v42; // r14
  HMODULE v43; // rsi
  DWORD v44; // ebx
  FILE *v45; // rax
  FILE *v46; // rax
  FILE *v47; // rax
  signed int v48; // eax
  int v49; // eax
  FILE *v50; // rax
  FILE *v51; // rax
  FILE *v52; // rax
  HMODULE v53; // rax
  HMODULE v54; // rsi
  HMODULE v55; // rdi
  DWORD v56; // ebx
  signed int v57; // eax
  FILE *v58; // rax
  FILE *v59; // rax
  FILE *v60; // rax
  signed int v61; // eax
  FILE *v62; // rax
  FILE *v63; // rax
  FILE *v64; // rax
  FILE *v65; // rax
  __int64 v66; // rbx
  FILE *v67; // rax
  FILE *v68; // rax
  signed int v69; // eax
  FILE *v70; // rax
  signed int v71; // eax
  unsigned int v72; // esi
  __int64 v73; // rbx
  FILE *v74; // rax
  FILE *v75; // rax
  signed int v76; // eax
  __int64 v77; // [rsp+20h] [rbp-E0h]
  __int64 v78; // [rsp+20h] [rbp-E0h]
  __int64 v79; // [rsp+20h] [rbp-E0h]
  __int64 v80; // [rsp+20h] [rbp-E0h]
  WCHAR LibFileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+260h] [rbp+160h] BYREF

  memset_0(Filename, 0, 0x208u);
  memset_0(LibFileName, 0, 0x208u);
  if ( !a1 || !a3 )
    return 2147942487LL;
  for ( i = 0; i < a2; **(_QWORD **)(a3 + 16 * v9 + 8) = 0 )
    v9 = i++;
  CurrentProcess = GetCurrentProcess();
  if ( !K32GetModuleFileNameExW(CurrentProcess, 0, Filename, 0x104u) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    v13 = "[%#x] GetModuleFileNameEx failed";
    v14 = 887;
    goto LABEL_9;
  }
  v19 = wcsrchr(Filename, 0x5Cu);
  if ( !v19 )
  {
    v20 = GetLastError();
    v12 = v20;
    if ( v20 > 0 )
      v12 = (unsigned __int16)v20 | 0x80070000;
    v21 = "[%#x] wcsrchr failed, dllFolder=%ws";
    AslLogCallPrintf(2, "ResolveImportedApis", 895, "[%#x] wcsrchr failed, dllFolder=%ws", v12, Filename);
    if ( EnableDevInvStdErrLog )
    {
      v22 = o___acrt_iob_func_0(2u);
      fprintf(v22, "Error: %s, %u: ", "ResolveImportedApis", 895);
      v23 = o___acrt_iob_func_0(2u);
      fprintf(v23, "[%#x] wcsrchr failed, dllFolder=%ws", v12, Filename);
      v24 = o___acrt_iob_func_0(2u);
      fprintf(v24, "\n");
    }
    if ( !g_DeviceMapLogFunction )
      return v12;
    v25 = Filename;
    v26 = 0x2000000;
    goto LABEL_21;
  }
  *v19 = 0;
  v12 = StringCchPrintfW(LibFileName, 0x104u, L"%ls\\%ls", Filename, a1);
  if ( (v12 & 0x80000000) != 0 )
  {
    LODWORD(v77) = v12;
    AslLogCallPrintf(2, "ResolveImportedApis", 903, "[%#x] Failed StringCchPrintf, dllFolder=%ws", v77, Filename);
    if ( EnableDevInvStdErrLog )
    {
      v27 = o___acrt_iob_func_0(2u);
      fprintf(v27, "Error: %s, %u: ", "ResolveImportedApis", 903);
      v28 = o___acrt_iob_func_0(2u);
      fprintf(v28, "[%#x] Failed StringCchPrintf, dllFolder=%ws", v12, Filename);
      v29 = o___acrt_iob_func_0(2u);
      fprintf(v29, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "[%#x] Failed StringCchPrintf, dllFolder=%ws", v12, Filename);
    LODWORD(v78) = v12;
    AslLogCallPrintf(1, "ResolveImportedApis", 903, "[%#x] Failed StringCchPrintf, dllFolder=%ws", v78, Filename);
    return v12;
  }
  Library = LoadLibraryExW(LibFileName, 0, 0);
  v31 = *a4;
  v32 = Library;
  if ( *a4 )
  {
    v33 = GetLastError();
    FreeLibrary(v31);
    SetLastError(v33);
  }
  v34 = 0;
  *a4 = v32;
  if ( !v32 )
  {
    if ( GetSystemDirectoryW(Filename, 0x104u) - 1 > 0x103 )
    {
      v61 = GetLastError();
      v12 = v61;
      if ( v61 > 0 )
        v12 = (unsigned __int16)v61 | 0x80070000;
      v13 = "[%#x] GetSystemDirectory failed";
      v14 = 919;
      goto LABEL_9;
    }
    v35 = StringCchPrintfW(LibFileName, 0x104u, L"%ls\\%ls", Filename, a1);
    v36 = v35;
    if ( v35 < 0 )
    {
      AslLogCallPrintf(2, "ResolveImportedApis", 926, "[%#x] Failed StringCchPrintf", v35);
      if ( EnableDevInvStdErrLog )
      {
        v37 = o___acrt_iob_func_0(2u);
        fprintf(v37, "Error: %s, %u: ", "ResolveImportedApis", 926);
        v38 = o___acrt_iob_func_0(2u);
        fprintf(v38, "[%#x] Failed StringCchPrintf", v36);
        v39 = o___acrt_iob_func_0(2u);
        fprintf(v39, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "[%#x] Failed StringCchPrintf", v36);
      AslLogCallPrintf(1, "ResolveImportedApis", 926, "[%#x] Failed StringCchPrintf", v36);
      return v36;
    }
    v40 = LoadLibraryExW(LibFileName, 0, 0);
    v42 = *a4;
    v43 = v40;
    if ( *a4 )
    {
      v44 = GetLastError();
      FreeLibrary(v42);
      SetLastError(v44);
    }
    v34 = 0;
    *a4 = v43;
    if ( !v43 )
    {
      v12 = StringCchCatW(Filename, v41, L"\\compattel");
      if ( (v12 & 0x80000000) != 0 )
      {
        v13 = "[%#x] StringCchCat";
        v14 = 942;
LABEL_9:
        LODWORD(v77) = v12;
        AslLogCallPrintf(2, "ResolveImportedApis", v14, v13, v77);
        if ( EnableDevInvStdErrLog )
        {
          v15 = o___acrt_iob_func_0(2u);
          fprintf(v15, "Error: %s, %u: ", "ResolveImportedApis", v14);
          v16 = o___acrt_iob_func_0(2u);
          fprintf(v16, v13, v12);
          v17 = o___acrt_iob_func_0(2u);
          fprintf(v17, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, v13, v12);
        return v12;
      }
      if ( GetFileAttributesW(Filename) == -1 )
      {
        AslLogCallPrintf(2, "ResolveImportedApis", 954, "Compattel folder does not exist");
        if ( EnableDevInvStdErrLog )
        {
          v45 = o___acrt_iob_func_0(2u);
          fprintf(v45, "Warning: %s, %u: ", "ResolveImportedApis", 954);
          v46 = o___acrt_iob_func_0(2u);
          fprintf(v46, "Compattel folder does not exist");
          v47 = o___acrt_iob_func_0(2u);
          fprintf(v47, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(50331648, "Compattel folder does not exist");
        return 2147942402LL;
      }
      if ( dword_180155C60 )
      {
        dword_180155C60 = 0;
        if ( !SetDllDirectoryW(Filename) )
        {
          v48 = GetLastError();
          v12 = v48;
          if ( v48 > 0 )
            v12 = (unsigned __int16)v48 | 0x80070000;
          v13 = "[%#x] Failed SetDllDirectory";
          v14 = 971;
          goto LABEL_9;
        }
      }
      v49 = StringCchPrintfW(LibFileName, 0x104u, L"%ls\\%ls", Filename, a1);
      v36 = v49;
      if ( v49 < 0 )
      {
        AslLogCallPrintf(2, "ResolveImportedApis", 979, "[%#x] Failed StringCchPrintf", v49);
        if ( EnableDevInvStdErrLog )
        {
          v50 = o___acrt_iob_func_0(2u);
          fprintf(v50, "Error: %s, %u: ", "ResolveImportedApis", 979);
          v51 = o___acrt_iob_func_0(2u);
          fprintf(v51, "[%#x] Failed StringCchPrintf", v36);
          v52 = o___acrt_iob_func_0(2u);
          fprintf(v52, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "[%#x] Failed StringCchPrintf", v36);
        return v36;
      }
      v53 = LoadLibraryExW(LibFileName, 0, 0);
      v54 = *a4;
      v34 = 0;
      v55 = v53;
      if ( *a4 )
      {
        v56 = GetLastError();
        FreeLibrary(v54);
        SetLastError(v56);
      }
      *a4 = v55;
      if ( !v55 )
      {
        v57 = GetLastError();
        v12 = v57;
        if ( v57 > 0 )
          v12 = (unsigned __int16)v57 | 0x80070000;
        v21 = "[%#x] Failed LoadLibraryExW for %ws";
        LODWORD(v79) = v12;
        AslLogCallPrintf(2, "ResolveImportedApis", 987, "[%#x] Failed LoadLibraryExW for %ws", v79, LibFileName);
        if ( EnableDevInvStdErrLog )
        {
          v58 = o___acrt_iob_func_0(2u);
          fprintf(v58, "Warning: %s, %u: ", "ResolveImportedApis", 987);
          v59 = o___acrt_iob_func_0(2u);
          fprintf(v59, "[%#x] Failed LoadLibraryExW for %ws", v12, LibFileName);
          v60 = o___acrt_iob_func_0(2u);
          fprintf(v60, "\n");
        }
        if ( !g_DeviceMapLogFunction )
          return v12;
        v25 = LibFileName;
        v26 = 50331648;
LABEL_21:
        TraceMessageCallback(v26, v21, v12, v25);
        return v12;
      }
    }
  }
  AslLogCallPrintf(3, "ResolveImportedApis", 993, "Library [%ws] loaded successfully", LibFileName);
  if ( EnableDevInvStdErrLog )
  {
    v62 = o___acrt_iob_func_0(2u);
    fprintf(v62, "Info: %s, %u: ", "ResolveImportedApis", 993);
    v63 = o___acrt_iob_func_0(2u);
    fprintf(v63, "Library [%ws] loaded successfully", LibFileName);
    v64 = o___acrt_iob_func_0(2u);
    fprintf(v64, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x4000000, "Library [%ws] loaded successfully", LibFileName);
  if ( !a2 )
    return 0;
  while ( 1 )
  {
    **(_QWORD **)(a3 + 16LL * v34 + 8) = GetProcAddress(*a4, *(LPCSTR *)(a3 + 16LL * v34));
    if ( !**(_QWORD **)(a3 + 16LL * v34 + 8) )
      break;
    AslLogCallPrintf(
      3,
      "ResolveImportedApis",
      1014,
      "Function [%hs] from library [%ws] imported successfully",
      *(_QWORD *)(a3 + 16LL * v34),
      LibFileName);
    if ( EnableDevInvStdErrLog )
    {
      v65 = o___acrt_iob_func_0(2u);
      fprintf(v65, "Info: %s, %u: ", "ResolveImportedApis", 1014);
      v66 = *(_QWORD *)(a3 + 16LL * v34);
      v67 = o___acrt_iob_func_0(2u);
      fprintf(v67, "Function [%hs] from library [%ws] imported successfully", v66, LibFileName);
      v68 = o___acrt_iob_func_0(2u);
      fprintf(v68, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(
        0x4000000,
        "Function [%hs] from library [%ws] imported successfully",
        *(_QWORD *)(a3 + 16LL * v34),
        LibFileName);
    if ( ++v34 >= a2 )
      return 0;
  }
  v69 = GetLastError();
  if ( v69 > 0 )
    v69 = (unsigned __int16)v69 | 0x80070000;
  AslLogCallPrintf(
    2,
    "ResolveImportedApis",
    1010,
    "GetProcAddress failed for [%hs] [%ws] with [%#x]",
    *(_QWORD *)(a3 + 16LL * v34),
    LibFileName,
    v69);
  if ( EnableDevInvStdErrLog )
  {
    v70 = o___acrt_iob_func_0(2u);
    fprintf(v70, "Warning: %s, %u: ", "ResolveImportedApis", 1010);
    v71 = GetLastError();
    v72 = v71;
    if ( v71 > 0 )
      v72 = (unsigned __int16)v71 | 0x80070000;
    v73 = *(_QWORD *)(a3 + 16LL * v34);
    v74 = o___acrt_iob_func_0(2u);
    LODWORD(v80) = v72;
    fprintf(v74, "GetProcAddress failed for [%hs] [%ws] with [%#x]", v73, LibFileName, v80);
    v75 = o___acrt_iob_func_0(2u);
    fprintf(v75, "\n");
  }
  if ( g_DeviceMapLogFunction )
  {
    v76 = GetLastError();
    if ( v76 > 0 )
      v76 = (unsigned __int16)v76 | 0x80070000;
    LODWORD(v80) = v76;
    TraceMessageCallback(
      50331648,
      "GetProcAddress failed for [%hs] [%ws] with [%#x]",
      *(_QWORD *)(a3 + 16LL * v34),
      LibFileName,
      v80);
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x18005e3ec  mov     [rsp-8+arg_8], rbx
0x18005e3f1  push    rbp
0x18005e3f2  push    rsi
0x18005e3f3  push    rdi
0x18005e3f4  push    r12
0x18005e3f6  push    r13
0x18005e3f8  push    r14
0x18005e3fa  push    r15
0x18005e3fc  lea     rbp, [rsp-380h]
0x18005e404  sub     rsp, 480h
0x18005e40b  mov     rax, cs:__security_cookie
0x18005e412  xor     rax, rsp
0x18005e415  mov     [rbp+3B0h+var_40], rax
0x18005e41c  mov     r12, r8
0x18005e41f  mov     [rsp+4B0h+var_470], edx
0x18005e423  mov     r15d, edx
0x18005e426  mov     rdi, rcx
0x18005e429  mov     ebx, 208h
0x18005e42e  lea     rcx, [rbp+3B0h+Filename]; void *
0x18005e435  mov     r8d, ebx; Size
0x18005e438  xor     edx, edx; Val
0x18005e43a  mov     r13, r9
0x18005e43d  call    memset_0
0x18005e442  mov     r8d, ebx; Size
0x18005e445  lea     rcx, [rsp+4B0h+LibFileName]; void *
0x18005e44a  xor     edx, edx; Val
0x18005e44c  call    memset_0
0x18005e451  xor     r14d, r14d
0x18005e454  test    rdi, rdi
0x18005e457  jz      loc_18005EE7C
0x18005e45d  test    r12, r12
0x18005e460  jz      loc_18005EE7C
0x18005e466  mov     ecx, r14d
0x18005e469  test    r15d, r15d
0x18005e46c  jz      short loc_18005E482
0x18005e46e  mov     eax, ecx
0x18005e470  inc     ecx
0x18005e472  add     rax, rax
0x18005e475  mov     rax, [r12+rax*8+8]
0x18005e47a  mov     [rax], r14
0x18005e47d  cmp     ecx, r15d
0x18005e480  jb      short loc_18005E46E
0x18005e482  call    cs:__imp_GetCurrentProcess
0x18005e488  mov     ebx, 104h
0x18005e48d  lea     r8, [rbp+3B0h+Filename]; lpFilename
0x18005e494  mov     rcx, rax; hProcess
0x18005e497  mov     r9d, ebx; nSize
0x18005e49a  xor     edx, edx; hModule
0x18005e49c  call    cs:__imp_K32GetModuleFileNameExW
0x18005e4a2  test    eax, eax
0x18005e4a4  jnz     loc_18005E55C
0x18005e4aa  call    cs:__imp_GetLastError
0x18005e4b0  mov     ebx, eax
0x18005e4b2  test    eax, eax
0x18005e4b4  jle     short loc_18005E4BF
0x18005e4b6  movzx   ebx, ax
0x18005e4b9  or      ebx, 80070000h
0x18005e4bf  lea     r15, aXGetmodulefile; "[%#x] GetModuleFileNameEx failed"
0x18005e4c6  mov     r12d, 377h
0x18005e4cc  lea     rsi, aResolveimporte; "ResolveImportedApis"
0x18005e4d3  mov     dword ptr [rsp+4B0h+var_490], ebx
0x18005e4d7  mov     edi, 2
0x18005e4dc  mov     rdx, rsi
0x18005e4df  mov     ecx, edi
0x18005e4e1  mov     r9, r15
0x18005e4e4  mov     r8, r12
0x18005e4e7  call    AslLogCallPrintf
0x18005e4ec  cmp     cs:EnableDevInvStdErrLog, r14d
0x18005e4f3  jz      short loc_18005E53C
0x18005e4f5  mov     ecx, edi; Ix
0x18005e4f7  call    _o___acrt_iob_func_0
0x18005e4fc  mov     rcx, rax; Stream
0x18005e4ff  lea     rdx, Format; "Error: %s, %u: "
0x18005e506  mov     r9d, r12d
0x18005e509  mov     r8, rsi
0x18005e50c  call    fprintf
0x18005e511  mov     ecx, edi; Ix
0x18005e513  call    _o___acrt_iob_func_0
0x18005e518  mov     rcx, rax; Stream
0x18005e51b  mov     r8d, ebx
0x18005e51e  mov     rdx, r15; Format
0x18005e521  call    fprintf
0x18005e526  mov     ecx, edi; Ix
0x18005e528  call    _o___acrt_iob_func_0
0x18005e52d  mov     rcx, rax; Stream
0x18005e530  lea     rdx, asc_18011EAD8; "\n"
0x18005e537  call    fprintf
0x18005e53c  cmp     cs:g_DeviceMapLogFunction, r14
0x18005e543  jz      short loc_18005E555
0x18005e545  mov     r8d, ebx
0x18005e548  mov     rdx, r15
0x18005e54b  mov     ecx, 2000000h
0x18005e550  call    TraceMessageCallback
0x18005e555  mov     eax, ebx
0x18005e557  jmp     loc_18005EE81
0x18005e55c  mov     edx, 5Ch ; '\'; Ch
0x18005e561  lea     rcx, [rbp+3B0h+Filename]; Str
0x18005e568  call    cs:__imp_wcsrchr
0x18005e56e  test    rax, rax
0x18005e571  jnz     loc_18005E645
0x18005e577  call    cs:__imp_GetLastError
0x18005e57d  mov     ebx, eax
0x18005e57f  test    eax, eax
0x18005e581  jle     short loc_18005E58C
0x18005e583  movzx   ebx, ax
0x18005e586  or      ebx, 80070000h
0x18005e58c  lea     rax, [rbp+3B0h+Filename]
0x18005e593  mov     r12d, 37Fh
0x18005e599  mov     [rsp+4B0h+var_488], rax
0x18005e59e  lea     r15, aXWcsrchrFailed; "[%#x] wcsrchr failed, dllFolder=%ws"
0x18005e5a5  lea     rsi, aResolveimporte; "ResolveImportedApis"
0x18005e5ac  mov     dword ptr [rsp+4B0h+var_490], ebx
0x18005e5b0  mov     edi, 2
0x18005e5b5  mov     r9, r15
0x18005e5b8  mov     r8d, r12d
0x18005e5bb  mov     rdx, rsi
0x18005e5be  mov     ecx, edi
0x18005e5c0  call    AslLogCallPrintf
0x18005e5c5  cmp     cs:EnableDevInvStdErrLog, r14d
0x18005e5cc  jz      short loc_18005E61C
0x18005e5ce  mov     ecx, edi; Ix
0x18005e5d0  call    _o___acrt_iob_func_0
0x18005e5d5  mov     rcx, rax; Stream
0x18005e5d8  lea     rdx, Format; "Error: %s, %u: "
0x18005e5df  mov     r9d, r12d
0x18005e5e2  mov     r8, rsi
0x18005e5e5  call    fprintf
0x18005e5ea  mov     ecx, edi; Ix
0x18005e5ec  call    _o___acrt_iob_func_0
0x18005e5f1  mov     rcx, rax; Stream
0x18005e5f4  lea     r9, [rbp+3B0h+Filename]
0x18005e5fb  mov     r8d, ebx
0x18005e5fe  mov     rdx, r15; Format
0x18005e601  call    fprintf
0x18005e606  mov     ecx, edi; Ix
0x18005e608  call    _o___acrt_iob_func_0
0x18005e60d  mov     rcx, rax; Stream
0x18005e610  lea     rdx, asc_18011EAD8; "\n"
0x18005e617  call    fprintf
0x18005e61c  cmp     cs:g_DeviceMapLogFunction, r14
0x18005e623  jz      loc_18005E555
0x18005e629  lea     r9, [rbp+3B0h+Filename]
0x18005e630  mov     ecx, 2000000h
0x18005e635  mov     rdx, r15
0x18005e638  mov     r8d, ebx
0x18005e63b  call    TraceMessageCallback
0x18005e640  jmp     loc_18005E555
0x18005e645  lea     r9, [rbp+3B0h+Filename]
0x18005e64c  mov     [rax], r14w
0x18005e650  lea     r8, aLsLs; "%ls\\%ls"
0x18005e657  mov     [rsp+4B0h+var_490], rdi
0x18005e65c  mov     rdx, rbx; unsigned __int64
0x18005e65f  lea     rcx, [rsp+4B0h+LibFileName]; unsigned __int16 *
0x18005e664  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005e669  mov     ebx, eax
0x18005e66b  test    eax, eax
0x18005e66d  jns     loc_18005E74B
0x18005e673  lea     rax, [rbp+3B0h+Filename]
0x18005e67a  mov     r12d, 387h
0x18005e680  mov     [rsp+4B0h+var_488], rax
0x18005e685  lea     r15, aXFailedStringc_0; "[%#x] Failed StringCchPrintf, dllFolder"...
0x18005e68c  lea     rsi, aResolveimporte; "ResolveImportedApis"
0x18005e693  mov     dword ptr [rsp+4B0h+var_490], ebx
0x18005e697  mov     edi, 2
0x18005e69c  mov     r9, r15
0x18005e69f  mov     r8d, r12d
0x18005e6a2  mov     rdx, rsi
0x18005e6a5  mov     ecx, edi
0x18005e6a7  call    AslLogCallPrintf
0x18005e6ac  cmp     cs:EnableDevInvStdErrLog, r14d
0x18005e6b3  jz      short loc_18005E703
0x18005e6b5  mov     ecx, edi; Ix
0x18005e6b7  call    _o___acrt_iob_func_0
0x18005e6bc  mov     rcx, rax; Stream
0x18005e6bf  lea     rdx, Format; "Error: %s, %u: "
0x18005e6c6  mov     r9d, r12d
0x18005e6c9  mov     r8, rsi
0x18005e6cc  call    fprintf
0x18005e6d1  mov     ecx, edi; Ix
0x18005e6d3  call    _o___acrt_iob_func_0
0x18005e6d8  mov     rcx, rax; Stream
0x18005e6db  lea     r9, [rbp+3B0h+Filename]
0x18005e6e2  mov     r8d, ebx
0x18005e6e5  mov     rdx, r15; Format
0x18005e6e8  call    fprintf
0x18005e6ed  mov     ecx, edi; Ix
0x18005e6ef  call    _o___acrt_iob_func_0
0x18005e6f4  mov     rcx, rax; Stream
0x18005e6f7  lea     rdx, asc_18011EAD8; "\n"
0x18005e6fe  call    fprintf
0x18005e703  cmp     cs:g_DeviceMapLogFunction, r14
0x18005e70a  jz      short loc_18005E723
0x18005e70c  lea     r9, [rbp+3B0h+Filename]
0x18005e713  mov     r8d, ebx
0x18005e716  mov     rdx, r15
0x18005e719  mov     ecx, 2000000h
0x18005e71e  call    TraceMessageCallback
0x18005e723  lea     rax, [rbp+3B0h+Filename]
0x18005e72a  mov     r9, r15
0x18005e72d  mov     [rsp+4B0h+var_488], rax
0x18005e732  mov     r8, r12
0x18005e735  mov     rdx, rsi
0x18005e738  mov     dword ptr [rsp+4B0h+var_490], ebx
0x18005e73c  mov     ecx, 1
0x18005e741  call    AslLogCallPrintf
0x18005e746  jmp     loc_18005E555
0x18005e74b  xor     r8d, r8d; dwFlags
0x18005e74e  lea     rcx, [rsp+4B0h+LibFileName]; lpLibFileName
0x18005e753  xor     edx, edx; hFile
0x18005e755  call    cs:__imp_LoadLibraryExW
0x18005e75b  mov     r14, [r13+0]
0x18005e75f  mov     rsi, rax
0x18005e762  test    r14, r14
0x18005e765  jz      short loc_18005E780
0x18005e767  call    cs:__imp_GetLastError
0x18005e76d  mov     rcx, r14; hLibModule
0x18005e770  mov     ebx, eax
0x18005e772  call    cs:__imp_FreeLibrary
0x18005e778  mov     ecx, ebx; dwErrCode
0x18005e77a  call    cs:__imp_SetLastError
0x18005e780  xor     r14d, r14d
0x18005e783  mov     [r13+0], rsi
0x18005e787  test    rsi, rsi
0x18005e78a  jnz     loc_18005EBEC
0x18005e790  mov     ebx, 104h
0x18005e795  lea     rcx, [rbp+3B0h+Filename]; lpBuffer
0x18005e79c  mov     edx, ebx; uSize
0x18005e79e  call    cs:__imp_GetSystemDirectoryW
0x18005e7a4  dec     eax
0x18005e7a6  cmp     eax, 103h
0x18005e7ab  ja      loc_18005EBC5
0x18005e7b1  lea     r9, [rbp+3B0h+Filename]
0x18005e7b8  mov     [rsp+4B0h+var_490], rdi
0x18005e7bd  lea     r8, aLsLs; "%ls\\%ls"
0x18005e7c4  mov     edx, ebx; unsigned __int64
0x18005e7c6  lea     rcx, [rsp+4B0h+LibFileName]; unsigned __int16 *
0x18005e7cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005e7d0  mov     r14d, eax
0x18005e7d3  test    eax, eax
0x18005e7d5  jns     loc_18005E892
0x18005e7db  lea     rbx, aXFailedStringc; "[%#x] Failed StringCchPrintf"
0x18005e7e2  mov     dword ptr [rsp+4B0h+var_490], eax
0x18005e7e6  mov     r15d, 39Eh
0x18005e7ec  lea     rsi, aResolveimporte; "ResolveImportedApis"
0x18005e7f3  mov     edi, 2
0x18005e7f8  mov     r9, rbx
0x18005e7fb  mov     r8d, r15d
0x18005e7fe  mov     rdx, rsi
0x18005e801  mov     ecx, edi
0x18005e803  call    AslLogCallPrintf
0x18005e808  cmp     cs:EnableDevInvStdErrLog, 0
0x18005e80f  jz      short loc_18005E858
0x18005e811  mov     ecx, edi; Ix
0x18005e813  call    _o___acrt_iob_func_0
0x18005e818  mov     rcx, rax; Stream
0x18005e81b  lea     rdx, Format; "Error: %s, %u: "
0x18005e822  mov     r9d, r15d
0x18005e825  mov     r8, rsi
0x18005e828  call    fprintf
0x18005e82d  mov     ecx, edi; Ix
0x18005e82f  call    _o___acrt_iob_func_0
0x18005e834  mov     rcx, rax; Stream
0x18005e837  mov     r8d, r14d
0x18005e83a  mov     rdx, rbx; Format
0x18005e83d  call    fprintf
0x18005e842  mov     ecx, edi; Ix
0x18005e844  call    _o___acrt_iob_func_0
0x18005e849  mov     rcx, rax; Stream
0x18005e84c  lea     rdx, asc_18011EAD8; "\n"
0x18005e853  call    fprintf
0x18005e858  cmp     cs:g_DeviceMapLogFunction, 0
0x18005e860  jz      short loc_18005E872
0x18005e862  mov     r8d, r14d
0x18005e865  mov     rdx, rbx
0x18005e868  mov     ecx, 2000000h
0x18005e86d  call    TraceMessageCallback
0x18005e872  mov     r9, rbx
0x18005e875  mov     dword ptr [rsp+4B0h+var_490], r14d
0x18005e87a  mov     r8, r15
0x18005e87d  mov     rdx, rsi
0x18005e880  mov     ecx, 1
0x18005e885  call    AslLogCallPrintf
0x18005e88a  mov     eax, r14d
0x18005e88d  jmp     loc_18005EE81
0x18005e892  xor     r8d, r8d; dwFlags
0x18005e895  lea     rcx, [rsp+4B0h+LibFileName]; lpLibFileName
0x18005e89a  xor     edx, edx; hFile
0x18005e89c  call    cs:__imp_LoadLibraryExW
0x18005e8a2  mov     r14, [r13+0]
0x18005e8a6  mov     rsi, rax
0x18005e8a9  test    r14, r14
0x18005e8ac  jz      short loc_18005E8C7
0x18005e8ae  call    cs:__imp_GetLastError
0x18005e8b4  mov     rcx, r14; hLibModule
0x18005e8b7  mov     ebx, eax
0x18005e8b9  call    cs:__imp_FreeLibrary
0x18005e8bf  mov     ecx, ebx; dwErrCode
0x18005e8c1  call    cs:__imp_SetLastError
0x18005e8c7  xor     r14d, r14d
0x18005e8ca  mov     [r13+0], rsi
  ... truncated ...
```
