# PlaiRunTracerpt(ushort const *,IXMLDOMDocument *,ushort const *,ushort const *,ulong)

- ea: `0x1800b9b10`
- end: `0x1800bac4f`
- name: `?PlaiRunTracerpt@@YAJPEBGPEAUIXMLDOMDocument@@00K@Z`
- size: `4415`
- prototype: `int(const unsigned __int16 *, struct IXMLDOMDocument *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180125e60`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180015f98`
- `0x1800182a4`
- `0x180018420`
- `0x1800198b0`
- `0x18001ef94`
- `0x180024ea0`
- `0x180026850`
- `0x18002b3a0`
- `0x180040840`
- `0x180040dcc`
- `0x18004ad94`
- `0x18005179c`
- `0x1800b9b10`
- `0x18013ae9a`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba79f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba8c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800baada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba79f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba8c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800baada`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ba896`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ba896`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bac04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bac17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bac04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bac17`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800ba791`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800ba791`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800baad0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800baad0`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800ba94a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800ba94a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800bab62`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800bab62`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800ba491`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800ba491`

## pseudocode

```c
__int64 __fastcall PlaiRunTracerpt(
        const unsigned __int16 *a1,
        struct IXMLDOMDocument *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const WCHAR *v7; // r13
  struct IXMLDOMDocument *v8; // r12
  const WCHAR *v9; // r14
  int v10; // ebx
  __int64 v11; // rax
  void *p_Buffer; // r9
  WCHAR *v13; // rax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  HRESULT (__stdcall *get_namespaceURI)(IXMLDOMDocument *, BSTR *); // rbx
  __int64 v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rcx
  const char *v24; // rdx
  int v25; // r8d
  OLECHAR *v26; // rax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rax
  WCHAR *v36; // rax
  __int64 v37; // rax
  const char *v38; // r8
  int v39; // r9d
  DWORD LastError; // eax
  __int64 v41; // rax
  int v42; // eax
  __int64 v43; // rax
  HRESULT (__stdcall *save)(IXMLDOMDocument *, VARIANT); // rax
  int v45; // eax
  __int64 v46; // rax
  int v47; // eax
  __int64 v48; // rax
  DWORD v49; // eax
  int v50; // eax
  __int64 v51; // rax
  DWORD v52; // eax
  DWORD v53; // eax
  __int64 v54; // rax
  DWORD v55; // eax
  int v56; // eax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  DWORD v60; // eax
  int v61; // eax
  __int64 v62; // rax
  int bInheritHandles; // [rsp+20h] [rbp-E0h]
  int bInheritHandlesa; // [rsp+20h] [rbp-E0h]
  int bInheritHandlesb; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpCurrentDirectory; // [rsp+38h] [rbp-C8h]
  wchar_t *Buffer; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v69; // [rsp+78h] [rbp-88h] BYREF
  struct IXMLDOMDocument *v70; // [rsp+80h] [rbp-80h] BYREF
  DWORD ExitCode; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpApplicationName; // [rsp+90h] [rbp-70h]
  __int64 v73; // [rsp+98h] [rbp-68h] BYREF
  __int64 v74; // [rsp+A0h] [rbp-60h] BYREF
  LPWSTR lpCommandLine; // [rsp+A8h] [rbp-58h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+B0h] [rbp-50h] BYREF
  BSTR bstrString; // [rsp+C8h] [rbp-38h]
  __int64 v78; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+D8h] [rbp-28h] BYREF
  VARIANTARG v80; // [rsp+F0h] [rbp-10h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v82[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v83[64]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v84[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v85[64]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v86[64]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v87[64]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int16 v88[64]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v89[64]; // [rsp+500h] [rbp+400h] BYREF
  unsigned __int16 v90[64]; // [rsp+580h] [rbp+480h] BYREF
  unsigned __int16 v91[64]; // [rsp+600h] [rbp+500h] BYREF
  unsigned __int16 v92[64]; // [rsp+680h] [rbp+580h] BYREF
  unsigned __int16 v93[64]; // [rsp+700h] [rbp+600h] BYREF
  unsigned __int16 v94[64]; // [rsp+780h] [rbp+680h] BYREF
  unsigned __int16 v95[64]; // [rsp+800h] [rbp+700h] BYREF
  unsigned __int16 v96[64]; // [rsp+880h] [rbp+780h] BYREF
  unsigned __int16 v97[64]; // [rsp+900h] [rbp+800h] BYREF
  unsigned __int16 v98[64]; // [rsp+980h] [rbp+880h] BYREF
  unsigned __int16 v99[64]; // [rsp+A00h] [rbp+900h] BYREF
  unsigned __int16 v100[64]; // [rsp+A80h] [rbp+980h] BYREF
  unsigned __int16 v101[64]; // [rsp+B00h] [rbp+A00h] BYREF
  unsigned __int16 v102[64]; // [rsp+B80h] [rbp+A80h] BYREF

  ExitCode = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  bstrString = 0;
  v73 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v7 = 0;
  v74 = 0;
  v8 = 0;
  v70 = 0;
  v78 = 0;
  PlaiVariantInit(&pvarg);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  lpCommandLine = (LPWSTR)PlaiAlloc(0x800u, 1, 0, qword_180147320, bInheritHandles);
  if ( lpCommandLine )
  {
    v13 = (WCHAR *)PlaiAlloc(0x800u, 1, 0, qword_180147320, bInheritHandlesa);
    lpApplicationName = v13;
    if ( !v13 )
    {
      v10 = -2147024882;
      LODWORD(v69) = 0;
      LODWORD(Buffer) = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_16;
      }
      PlaiWhoAmI(v83, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v83[v14] );
LABEL_15:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &Buffer,
        4,
        qword_180147320,
        1,
        &v69,
        4,
        "PlaiRunTracerpt",
        16);
LABEL_16:
      v9 = lpApplicationName;
      goto LABEL_164;
    }
    v15 = StringCchPrintfW(v13, 0x400u, L"%s\\tracerpt.exe", &g_SysDirectory);
    v10 = v15;
    if ( v15 < 0 )
    {
      LODWORD(Buffer) = v15;
      LODWORD(v69) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_16;
      }
      PlaiWhoAmI(v84, 0x4000000000000800uLL);
      v16 = -1;
      do
        ++v16;
      while ( v84[v16] );
      goto LABEL_15;
    }
    v9 = lpApplicationName;
    Buffer = lpCommandLine;
    v69 = 1024;
    v10 = StringCchPrintfExW(lpCommandLine, 0x400u, &Buffer, &v69, 0, L"\"%s\" *.etl *.blg -report \"%s\" -y");
    if ( v10 < 0 )
    {
      LODWORD(Buffer) = v10;
      LODWORD(v69) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_164;
      }
      PlaiWhoAmI(v85, 0x4000000000000800uLL);
      v17 = -1;
      do
        ++v17;
      while ( v85[v17] );
LABEL_30:
      lpCurrentDirectory = (LPCWSTR)&v69;
      goto LABEL_31;
    }
    if ( a3 )
    {
      if ( *a3 )
      {
        v18 = StringCchPrintfExW(Buffer, v69, &Buffer, &v69, 0, L" -o \"%s\"");
        v10 = v18;
        if ( v18 < 0 )
        {
          LODWORD(v69) = 0;
          LODWORD(Buffer) = v18;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_164;
          }
          PlaiWhoAmI(v86, 0x4000000000000800uLL);
          v19 = -1;
          do
            ++v19;
          while ( v86[v19] );
          goto LABEL_30;
        }
      }
    }
    if ( a2 )
    {
      get_namespaceURI = a2->lpVtbl->get_namespaceURI;
      v21 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v78);
      v22 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64))get_namespaceURI)(a2, v21);
      if ( v22 != 1 )
        MicrosoftTelemetryAssertTriggeredArgs(v23, v22);
      PlaiFreeString(0);
      v26 = PlaiAllocStringEx(L"/ReportSchema/*", v24, v25);
      bstrString = v26;
      if ( !v26 )
      {
        v10 = -2147024882;
        LODWORD(Buffer) = -2147024882;
        LODWORD(v69) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_164;
        }
        PlaiWhoAmI(v87, 0x4000000000000800uLL);
        v27 = -1;
        do
          ++v27;
        while ( v87[v27] );
        goto LABEL_30;
      }
      v28 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, OLECHAR *, __int64 *))a2->lpVtbl->selectSingleNode)(
              a2,
              v26,
              &v73);
      v10 = v28;
      if ( v28 < 0 )
      {
        LODWORD(v69) = 0;
        LODWORD(Buffer) = v28;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_164;
        }
        PlaiWhoAmI(v88, 0x4000000000000800uLL);
        v29 = -1;
        do
          ++v29;
        while ( v88[v29] );
        goto LABEL_30;
      }
      v30 = PlaiCreateXmlDocument(&v70);
      v10 = v30;
      if ( v30 < 0 )
      {
        LODWORD(v69) = 0;
        LODWORD(Buffer) = v30;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_65;
        }
        PlaiWhoAmI(v89, 0x4000000000000800uLL);
        v31 = -1;
        do
          ++v31;
        while ( v89[v31] );
LABEL_64:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &Buffer,
          4,
          qword_180147320,
          1,
          &v69,
          4,
          "PlaiRunTracerpt",
          16);
LABEL_65:
        v8 = v70;
        goto LABEL_164;
      }
      v32 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v73)(v73, &IID_IXMLDOMElement, &v74);
      v10 = v32;
      if ( v32 < 0 )
      {
        LODWORD(v69) = 0;
        LODWORD(Buffer) = v32;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_65;
        }
        PlaiWhoAmI(v90, 0x4000000000000800uLL);
        v33 = -1;
        do
          ++v33;
        while ( v90[v33] );
        goto LABEL_64;
      }
      v8 = v70;
      v34 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64))v70->lpVtbl->putref_documentElement)(v70, v74);
      v10 = v34;
      if ( v34 < 0 )
      {
        LODWORD(v69) = 0;
        LODWORD(Buffer) = v34;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_164;
        }
        PlaiWhoAmI(v91, 0x4000000000000800uLL);
        v35 = -1;
        do
          ++v35;
        while ( v91[v35] );
        goto LABEL_30;
      }
      v36 = (WCHAR *)PlaiAlloc(0x208u, 1, 0, qword_180147320, bInheritHandlesb);
      v7 = v36;
      if ( !v36 )
      {
        v10 = -2147024882;
        LODWORD(Buffer) = -2147024882;
        LODWORD(v69) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_164;
        }
        PlaiWhoAmI(v92, 0x4000000000000800uLL);
        v37 = -1;
        do
          ++v37;
        while ( v92[v37] );
        lpCurrentDirectory = (LPCWSTR)&v69;
LABEL_31:
        p_Buffer = &Buffer;
LABEL_8:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          p_Buffer,
          4,
          qword_180147320,
          1,
          lpCurrentDirectory,
          4,
          "PlaiRunTracerpt",
          16);
        goto LABEL_164;
      }
      if ( !GetTempFileNameW(a4, L"RPT", 0, v36) )
      {
        LastError = GetLastError();
        v10 = PlaiHResultFromWin32(LastError);
        LODWORD(v69) = 0;
        LODWORD(Buffer) = v10;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_163;
        }
        PlaiWhoAmI(v93, 0x4000000000000800uLL);
        v41 = -1;
        do
          ++v41;
        while ( v93[v41] );
LABEL_93:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &Buffer,
          4,
          qword_180147320,
          1,
          &v69,
          4,
          "PlaiRunTracerpt",
          16);
LABEL_163:
        DeleteFileW(v7);
        goto LABEL_164;
      }
      v42 = PlaiSetVariantEx(v7, &pvarg, v38, v39);
      v10 = v42;
      if ( v42 < 0 )
      {
        LODWORD(v69) = 0;
        LODWORD(Buffer) = v42;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_163;
        }
        PlaiWhoAmI(v94, 0x4000000000000800uLL);
        v43 = -1;
        do
          ++v43;
        while ( v94[v43] );
        goto LABEL_93;
      }
      save = v8->lpVtbl->save;
      v80 = pvarg;
      v45 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, VARIANTARG *))save)(v8, &v80);
      v10 = v45;
      if ( v45 < 0 )
      {
        LODWORD(v69) = 0;
        LODWORD(Buffer) = v45;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_163;
        }
        PlaiWhoAmI(v95, 0x4000000000000800uLL);
        v46 = -1;
        do
          ++v46;
        while ( v95[v46] );
        goto LABEL_93;
      }
      v47 = StringCchPrintfExW(Buffer, v69, &Buffer, &v69, 0, L" -df \"%s\"", v7);
      v10 = v47;
      if ( v47 < 0 )
      {
        LODWORD(v69) = 0;
        LODWORD(Buffer) = v47;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_163;
        }
        PlaiWhoAmI(v96, 0x4000000000000800uLL);
        v48 = -1;
        do
          ++v48;
        while ( v96[v48] );
        goto LABEL_93;
      }
    }
    StartupInfo.cb = 104;
    if ( CreateProcessW(v9, lpCommandLine, 0, 0, 0, 0x8000000u, 0, a4, &StartupInfo, &ProcessInformation)
      || (v49 = GetLastError(), v50 = PlaiHResultFromWin32(v49), v10 = v50, v50 >= 0) )
    {
      v52 = WaitForSingleObject(ProcessInformation.hProcess, 0x1499700u);
      switch ( v52 )
      {
        case 0u:
          if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode)
            || (v60 = GetLastError(), v61 = PlaiHResultFromWin32(v60), v10 = v61, v61 >= 0) )
          {
            v10 = ExitCode != 0;
          }
          else
          {
            LODWORD(v69) = 0;
            LODWORD(Buffer) = v61;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v102, 0x4000000000000800uLL);
              v62 = -1;
              do
                ++v62;
              while ( v102[v62] );
              goto LABEL_122;
            }
          }
          goto LABEL_162;
        case 0x80u:
          goto LABEL_147;
        case 0x102u:
          if ( TerminateProcess(ProcessInformation.hProcess, 0xFFFFFFFF)
            || (v55 = GetLastError(), v56 = PlaiHResultFromWin32(v55), v10 = v56, v56 >= 0) )
          {
            v10 = -2144337652;
            LODWORD(Buffer) = -2144337652;
            LODWORD(v69) = 0;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v100, 0x4000000000000800uLL);
              v58 = -1;
              do
                ++v58;
              while ( v100[v58] );
              goto LABEL_122;
            }
          }
          else
          {
            LODWORD(v69) = 0;
            LODWORD(Buffer) = v56;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v99, 0x4000000000000800uLL);
              v57 = -1;
              do
                ++v57;
              while ( v99[v57] );
              goto LABEL_122;
            }
          }
          goto LABEL_162;
      }
      if ( v52 != -1 )
      {
LABEL_147:
        v10 = -2147467259;
        LODWORD(Buffer) = -2147467259;
        LODWORD(v69) = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v101, 0x4000000000000800uLL);
          v59 = -1;
          do
            ++v59;
          while ( v101[v59] );
          goto LABEL_122;
        }
      }
      else
      {
        v53 = GetLastError();
        v10 = PlaiHResultFromWin32(v53);
        LODWORD(v69) = 0;
        LODWORD(Buffer) = v10;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v98, 0x4000000000000800uLL);
          v54 = -1;
          do
            ++v54;
          while ( v98[v54] );
          goto LABEL_122;
        }
      }
    }
    else
    {
      LODWORD(v69) = 0;
      LODWORD(Buffer) = v50;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v97, 0x4000000000000800uLL);
        v51 = -1;
        do
          ++v51;
        while ( v97[v51] );
LABEL_122:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &Buffer,
          4,
          qword_180147320,
          1,
          &v69,
          4,
          "PlaiRunTracerpt",
          16);
      }
    }
LABEL_162:
    if ( !v7 )
      goto LABEL_164;
    goto LABEL_163;
  }
  v9 = 0;
  v10 = -2147024882;
  LODWORD(Buffer) = 0;
  LODWORD(v69) = -2147024882;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v82, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v82[v11] );
    p_Buffer = &v69;
    lpCurrentDirectory = (LPCWSTR)&Buffer;
    goto LABEL_8;
  }
LABEL_164:
  PlaiVariantClear(&pvarg);
  if ( lpCommandLine )
    PlaiFree(lpCommandLine, 1);
  if ( v9 )
    PlaiFree(v9, 1);
  if ( v7 )
    PlaiFree(v7, 1);
  PlaiFreeString(bstrString);
  if ( v73 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    v73 = 0;
  }
  if ( v74 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    v74 = 0;
  }
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v8->lpVtbl->Release)(v8);
  if ( ProcessInformation.hProcess )
  {
    CloseHandle(ProcessInformation.hProcess);
    ProcessInformation.hProcess = 0;
  }
  if ( ProcessInformation.hThread )
  {
    CloseHandle(ProcessInformation.hThread);
    ProcessInformation.hThread = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v78);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800b9b10  push    rbp
0x1800b9b12  push    rbx
0x1800b9b13  push    rsi
0x1800b9b14  push    rdi
0x1800b9b15  push    r12
0x1800b9b17  push    r13
0x1800b9b19  push    r14
0x1800b9b1b  push    r15
0x1800b9b1d  lea     rbp, [rsp-0B18h]
0x1800b9b25  sub     rsp, 0C18h
0x1800b9b2c  mov     rax, cs:__security_cookie
0x1800b9b33  xor     rax, rsp
0x1800b9b36  mov     [rbp+0B50h+var_50], rax
0x1800b9b3d  xor     ebx, ebx
0x1800b9b3f  mov     rsi, r8
0x1800b9b42  mov     rdi, rdx
0x1800b9b45  mov     [rbp+0B50h+ExitCode], ebx
0x1800b9b48  mov     r14, rcx
0x1800b9b4b  xorps   xmm0, xmm0
0x1800b9b4e  xor     eax, eax
0x1800b9b50  lea     rcx, [rbp+0B50h+StartupInfo]; void *
0x1800b9b54  lea     r8d, [rbx+68h]; Size
0x1800b9b58  mov     qword ptr [rbp+0B50h+ProcessInformation.dwProcessId], rax
0x1800b9b5c  xor     edx, edx; Val
0x1800b9b5e  mov     r15, r9
0x1800b9b61  movups  xmmword ptr [rbp+0B50h+ProcessInformation.hProcess], xmm0
0x1800b9b65  call    memset_0
0x1800b9b6a  xorps   xmm0, xmm0
0x1800b9b6d  mov     [rbp+0B50h+bstrString], rbx
0x1800b9b71  xor     eax, eax
0x1800b9b73  mov     [rbp+0B50h+var_BB8], rbx
0x1800b9b77  lea     rcx, [rbp+0B50h+pvarg]; struct tagVARIANT *
0x1800b9b7b  mov     qword ptr [rbp+0B50h+pvarg+10h], rax
0x1800b9b7f  movups  xmmword ptr [rbp+0B50h+pvarg], xmm0
0x1800b9b83  mov     r13d, ebx
0x1800b9b86  mov     [rbp+0B50h+var_BB0], rbx
0x1800b9b8a  mov     r12d, ebx
0x1800b9b8d  mov     [rbp+0B50h+var_BD0], rbx
0x1800b9b91  mov     [rbp+0B50h+var_B80], rbx
0x1800b9b95  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800b9b9a  xorps   xmm0, xmm0
0x1800b9b9d  lea     r8d, [rbx+68h]; Size
0x1800b9ba1  xor     eax, eax
0x1800b9ba3  lea     rcx, [rbp+0B50h+StartupInfo]; void *
0x1800b9ba7  xor     edx, edx; Val
0x1800b9ba9  mov     qword ptr [rbp+0B50h+ProcessInformation.dwProcessId], rax
0x1800b9bad  movups  xmmword ptr [rbp+0B50h+ProcessInformation.hProcess], xmm0
0x1800b9bb1  call    memset_0
0x1800b9bb6  lea     r9, qword_180147320; char *
0x1800b9bbd  xor     r8d, r8d; int
0x1800b9bc0  lea     edx, [rbx+1]; int
0x1800b9bc3  mov     ecx, 800h; dwBytes
0x1800b9bc8  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800b9bcd  mov     [rbp+0B50h+lpCommandLine], rax
0x1800b9bd1  test    rax, rax
0x1800b9bd4  jnz     loc_1800B9CC6
0x1800b9bda  xor     esi, esi
0x1800b9bdc  mov     eax, 8007000Eh
0x1800b9be1  cmp     dword ptr cs:xmmword_180169738, esi
0x1800b9be7  mov     r14d, esi
0x1800b9bea  mov     ebx, eax
0x1800b9bec  mov     dword ptr [rsp+0C50h+Buffer], esi
0x1800b9bf0  mov     dword ptr [rsp+0C50h+var_BD8], eax
0x1800b9bf4  jz      loc_1800BAB68
0x1800b9bfa  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b9c04  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b9c0b  jz      loc_1800BAB68
0x1800b9c11  mov     rax, cs:qword_180169748
0x1800b9c18  and     rax, rdx
0x1800b9c1b  cmp     cs:qword_180169748, rax
0x1800b9c22  jnz     loc_1800BAB68
0x1800b9c28  lea     rcx, [rbp+0B50h+var_AD0]; unsigned __int16 *
0x1800b9c2f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b9c34  lea     rcx, [rbp+0B50h+var_AD0]
0x1800b9c3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b9c3f  inc     rax
0x1800b9c42  cmp     [rcx+rax*2], si
0x1800b9c46  jnz     short loc_1800B9C3F
0x1800b9c48  lea     ecx, [rax+rax]
0x1800b9c4b  add     rcx, 2
0x1800b9c4f  lea     rax, [rbp+0B50h+var_AD0]
0x1800b9c56  mov     [rsp+0C50h+var_BF0], rcx
0x1800b9c5b  lea     r9, [rsp+0C50h+var_BD8]
0x1800b9c60  mov     [rsp+0C50h+var_BF8], rax
0x1800b9c65  lea     rcx, [rsp+0C50h+Buffer]
0x1800b9c6a  mov     [rsp+0C50h+var_C00], 10h
0x1800b9c73  lea     rax, aPlairuntracerp; "PlaiRunTracerpt"
0x1800b9c7a  mov     [rsp+0C50h+lpProcessInformation], rax
0x1800b9c7f  mov     eax, 4
0x1800b9c84  mov     [rsp+0C50h+lpStartupInfo], rax
0x1800b9c89  mov     [rsp+0C50h+lpCurrentDirectory], rcx
0x1800b9c8e  lea     rcx, qword_180147320
0x1800b9c95  mov     [rsp+0C50h+lpEnvironment], 1
0x1800b9c9e  mov     qword ptr [rsp+0C50h+dwCreationFlags], rcx
0x1800b9ca3  mov     r8d, 5
0x1800b9ca9  mov     qword ptr [rsp+0C50h+bInheritHandles], rax
0x1800b9cae  lea     rdx, PLA_EVENT_ERROR
0x1800b9cb5  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800b9cbc  call    EventingWriteEvent
0x1800b9cc1  jmp     loc_1800BAB68
0x1800b9cc6  xor     r8d, r8d; int
0x1800b9cc9  lea     r9, qword_180147320; char *
0x1800b9cd0  mov     ecx, 800h; dwBytes
0x1800b9cd5  lea     edx, [r8+1]; int
0x1800b9cd9  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800b9cde  mov     [rbp+0B50h+lpApplicationName], rax
0x1800b9ce2  test    rax, rax
0x1800b9ce5  jnz     loc_1800B9DD6
0x1800b9ceb  xor     esi, esi
0x1800b9ced  mov     eax, 8007000Eh
0x1800b9cf2  cmp     dword ptr cs:xmmword_180169738, esi
0x1800b9cf8  mov     ebx, eax
0x1800b9cfa  mov     dword ptr [rsp+0C50h+var_BD8], esi
0x1800b9cfe  mov     dword ptr [rsp+0C50h+Buffer], eax
0x1800b9d02  jz      loc_1800B9DCD
0x1800b9d08  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b9d12  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b9d19  jz      loc_1800B9DCD
0x1800b9d1f  mov     rax, cs:qword_180169748
0x1800b9d26  and     rax, rdx
0x1800b9d29  cmp     cs:qword_180169748, rax
0x1800b9d30  jnz     loc_1800B9DCD
0x1800b9d36  lea     rcx, [rbp+0B50h+var_A50]; unsigned __int16 *
0x1800b9d3d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b9d42  lea     rcx, [rbp+0B50h+var_A50]
0x1800b9d49  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b9d4d  inc     rax
0x1800b9d50  cmp     [rcx+rax*2], si
0x1800b9d54  jnz     short loc_1800B9D4D
0x1800b9d56  lea     ecx, [rax+rax]
0x1800b9d59  lea     rax, [rbp+0B50h+var_A50]
0x1800b9d60  add     rcx, 2
0x1800b9d64  lea     r9, [rsp+0C50h+Buffer]
0x1800b9d69  mov     [rsp+0C50h+var_BF0], rcx
0x1800b9d6e  lea     rdx, PLA_EVENT_ERROR
0x1800b9d75  mov     [rsp+0C50h+var_BF8], rax
0x1800b9d7a  lea     rcx, [rsp+0C50h+var_BD8]
0x1800b9d7f  mov     [rsp+0C50h+var_C00], 10h
0x1800b9d88  lea     rax, aPlairuntracerp; "PlaiRunTracerpt"
0x1800b9d8f  mov     [rsp+0C50h+lpProcessInformation], rax
0x1800b9d94  mov     eax, 4
0x1800b9d99  mov     [rsp+0C50h+lpStartupInfo], rax
0x1800b9d9e  mov     [rsp+0C50h+lpCurrentDirectory], rcx
0x1800b9da3  lea     rcx, qword_180147320
0x1800b9daa  mov     [rsp+0C50h+lpEnvironment], 1
0x1800b9db3  mov     qword ptr [rsp+0C50h+dwCreationFlags], rcx
0x1800b9db8  lea     r8d, [rax+1]
0x1800b9dbc  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800b9dc3  mov     qword ptr [rsp+0C50h+bInheritHandles], rax
0x1800b9dc8  call    EventingWriteEvent
0x1800b9dcd  mov     r14, [rbp+0B50h+lpApplicationName]
0x1800b9dd1  jmp     loc_1800BAB68
0x1800b9dd6  lea     r9, ?g_SysDirectory@@3PAGA; ushort near * g_SysDirectory
0x1800b9ddd  mov     edx, 400h; unsigned __int64
0x1800b9de2  lea     r8, aSTracerptExe; "%s\\tracerpt.exe"
0x1800b9de9  mov     rcx, rax; unsigned __int16 *
0x1800b9dec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b9df1  xor     edx, edx
0x1800b9df3  mov     ebx, eax
0x1800b9df5  test    eax, eax
0x1800b9df7  jns     short loc_1800B9E60
0x1800b9df9  xor     esi, esi
0x1800b9dfb  mov     dword ptr [rsp+0C50h+Buffer], eax
0x1800b9dff  cmp     dword ptr cs:xmmword_180169738, esi
0x1800b9e05  mov     dword ptr [rsp+0C50h+var_BD8], esi
0x1800b9e09  jz      short loc_1800B9DCD
0x1800b9e0b  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b9e15  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b9e1c  jz      short loc_1800B9DCD
0x1800b9e1e  mov     rax, cs:qword_180169748
0x1800b9e25  and     rax, rdx
0x1800b9e28  cmp     cs:qword_180169748, rax
0x1800b9e2f  jnz     short loc_1800B9DCD
0x1800b9e31  lea     rcx, [rbp+0B50h+var_9D0]; unsigned __int16 *
0x1800b9e38  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b9e3d  lea     rcx, [rbp+0B50h+var_9D0]
0x1800b9e44  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b9e48  inc     rax
0x1800b9e4b  cmp     [rcx+rax*2], si
0x1800b9e4f  jnz     short loc_1800B9E48
0x1800b9e51  lea     ecx, [rax+rax]
0x1800b9e54  lea     rax, [rbp+0B50h+var_9D0]
0x1800b9e5b  jmp     loc_1800B9D60
0x1800b9e60  mov     rax, [rbp+0B50h+lpCommandLine]
0x1800b9e64  lea     rcx, aSEtlBlgReportS; "\"%s\" *.etl *.blg -report \"%s\" -y"
0x1800b9e6b  mov     [rsp+0C50h+lpCurrentDirectory], r14
0x1800b9e70  lea     r9, [rsp+0C50h+var_BD8]; unsigned __int64 *
0x1800b9e75  mov     r14, [rbp+0B50h+lpApplicationName]
0x1800b9e79  lea     r8, [rsp+0C50h+Buffer]; unsigned __int16 **
0x1800b9e7e  mov     r10d, 400h
0x1800b9e84  mov     [rsp+0C50h+lpEnvironment], r14
0x1800b9e89  mov     qword ptr [rsp+0C50h+dwCreationFlags], rcx; unsigned __int16 *
0x1800b9e8e  mov     rcx, rax; Buffer
0x1800b9e91  mov     qword ptr [rsp+0C50h+bInheritHandles], rdx; int
0x1800b9e96  mov     edx, r10d; unsigned __int64
0x1800b9e99  mov     [rsp+0C50h+Buffer], rax
0x1800b9e9e  mov     [rsp+0C50h+var_BD8], r10
0x1800b9ea3  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800b9ea8  mov     ebx, eax
0x1800b9eaa  xor     eax, eax
0x1800b9eac  test    ebx, ebx
0x1800b9eae  jns     loc_1800B9F78
0x1800b9eb4  xor     esi, esi
0x1800b9eb6  mov     dword ptr [rsp+0C50h+Buffer], ebx
0x1800b9eba  cmp     dword ptr cs:xmmword_180169738, esi
0x1800b9ec0  mov     dword ptr [rsp+0C50h+var_BD8], esi
0x1800b9ec4  jz      loc_1800BAB68
0x1800b9eca  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b9ed4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b9edb  jz      loc_1800BAB68
0x1800b9ee1  mov     rax, cs:qword_180169748
0x1800b9ee8  and     rax, rdx
0x1800b9eeb  cmp     cs:qword_180169748, rax
0x1800b9ef2  jnz     loc_1800BAB68
0x1800b9ef8  lea     rcx, [rbp+0B50h+var_950]; unsigned __int16 *
0x1800b9eff  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b9f04  lea     rcx, [rbp+0B50h+var_950]
0x1800b9f0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b9f0f  inc     rax
0x1800b9f12  cmp     [rcx+rax*2], si
0x1800b9f16  jnz     short loc_1800B9F0F
0x1800b9f18  lea     ecx, [rax+rax]
0x1800b9f1b  lea     rax, [rbp+0B50h+var_950]
0x1800b9f22  add     rcx, 2
0x1800b9f26  mov     [rsp+0C50h+var_BF0], rcx
0x1800b9f2b  lea     rcx, [rsp+0C50h+var_BD8]
0x1800b9f30  mov     [rsp+0C50h+var_BF8], rax
0x1800b9f35  lea     rax, aPlairuntracerp; "PlaiRunTracerpt"
0x1800b9f3c  mov     [rsp+0C50h+var_C00], 10h
0x1800b9f45  mov     [rsp+0C50h+lpProcessInformation], rax
0x1800b9f4a  mov     eax, 4
0x1800b9f4f  mov     [rsp+0C50h+lpStartupInfo], rax
0x1800b9f54  mov     [rsp+0C50h+lpCurrentDirectory], rcx
0x1800b9f59  lea     rcx, qword_180147320
0x1800b9f60  mov     [rsp+0C50h+lpEnvironment], 1
0x1800b9f69  mov     qword ptr [rsp+0C50h+dwCreationFlags], rcx
0x1800b9f6e  lea     r9, [rsp+0C50h+Buffer]
0x1800b9f73  jmp     loc_1800B9CA3
0x1800b9f78  test    rsi, rsi
0x1800b9f7b  jz      loc_1800BA032
0x1800b9f81  cmp     ax, [rsi]
0x1800b9f84  jz      loc_1800BA032
0x1800b9f8a  mov     rdx, [rsp+0C50h+var_BD8]; unsigned __int64
0x1800b9f8f  lea     rax, aOS; " -o \"%s\""
0x1800b9f96  mov     rcx, [rsp+0C50h+Buffer]; Buffer
0x1800b9f9b  lea     r9, [rsp+0C50h+var_BD8]; unsigned __int64 *
0x1800b9fa0  mov     [rsp+0C50h+lpEnvironment], rsi
0x1800b9fa5  lea     r8, [rsp+0C50h+Buffer]; unsigned __int16 **
0x1800b9faa  mov     qword ptr [rsp+0C50h+dwCreationFlags], rax; unsigned __int16 *
0x1800b9faf  xor     esi, esi
0x1800b9fb1  mov     qword ptr [rsp+0C50h+bInheritHandles], rsi; unsigned int
0x1800b9fb6  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800b9fbb  mov     ebx, eax
0x1800b9fbd  test    eax, eax
0x1800b9fbf  jns     short loc_1800BA034
0x1800b9fc1  cmp     dword ptr cs:xmmword_180169738, esi
0x1800b9fc7  mov     dword ptr [rsp+0C50h+var_BD8], esi
0x1800b9fcb  mov     dword ptr [rsp+0C50h+Buffer], eax
0x1800b9fcf  jz      loc_1800BAB68
0x1800b9fd5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b9fdf  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b9fe6  jz      loc_1800BAB68
0x1800b9fec  mov     rax, cs:qword_180169748
0x1800b9ff3  and     rax, rdx
0x1800b9ff6  cmp     cs:qword_180169748, rax
0x1800b9ffd  jnz     loc_1800BAB68
0x1800ba003  lea     rcx, [rbp+0B50h+var_8D0]; unsigned __int16 *
0x1800ba00a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ba00f  lea     rcx, [rbp+0B50h+var_8D0]
0x1800ba016  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ba01a  inc     rax
0x1800ba01d  cmp     [rcx+rax*2], si
0x1800ba021  jnz     short loc_1800BA01A
0x1800ba023  lea     ecx, [rax+rax]
0x1800ba026  lea     rax, [rbp+0B50h+var_8D0]
0x1800ba02d  jmp     loc_1800B9F22
0x1800ba032  xor     esi, esi
0x1800ba034  test    rdi, rdi
0x1800ba037  jz      loc_1800BA74E
0x1800ba03d  mov     rax, [rdi]
0x1800ba040  lea     rcx, [rbp+0B50h+var_B80]
0x1800ba044  mov     rbx, [rax+138h]
0x1800ba04b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800ba050  mov     rdx, rax
0x1800ba053  mov     rcx, rdi
0x1800ba056  mov     rax, rbx
0x1800ba059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba05e  cmp     eax, 1
0x1800ba061  jz      short loc_1800BA06A
0x1800ba063  mov     edx, eax
0x1800ba065  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800ba06a  xor     ecx, ecx; bstrString
0x1800ba06c  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x1800ba071  lea     rcx, aReportschema; "/ReportSchema/*"
0x1800ba078  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x1800ba07d  mov     [rbp+0B50h+bstrString], rax
0x1800ba081  mov     rcx, rax
0x1800ba084  test    rax, rax
0x1800ba087  jnz     short loc_1800BA101
0x1800ba089  cmp     dword ptr cs:xmmword_180169738, esi
  ... truncated ...
```
