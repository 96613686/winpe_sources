# _lambda_e5075cba4ceb4f6fbbae6c93eb464079_::operator()

- ea: `0x1801a5544`
- end: `0x1801a5ce5`
- name: `_lambda_e5075cba4ceb4f6fbbae6c93eb464079_::operator()`
- size: `1953`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801a0720`

## callees

- `0x1800727b8`
- `0x1800793cc`
- `0x18007cf9c`
- `0x18007d308`
- `0x18007daa4`
- `0x18007fca0`
- `0x180080424`
- `0x180080468`
- `0x1800954c4`
- `0x180099f30`
- `0x1800b94c4`
- `0x1800bd704`
- `0x1800c1688`
- `0x1800c6710`
- `0x1800c7034`
- `0x1800e8b30`
- `0x1800f0f40`
- `0x180159910`
- `0x1801918f8`
- `0x1801937dc`
- `0x180194358`
- `0x180194a38`
- `0x1801951ec`
- `0x18019679c`
- `0x1801a2fa8`
- `0x1801a5544`
- `0x1801a8934`
- `0x1801b10ac`
- `0x180274314`
- `0x1802cf56c`
- `0x1802d07a4`
- `0x1802d1484`
- `0x1802d4a14`
- `0x18037d9b8`
- `0x180415074`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801a59a6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801a59a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a5752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a5769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a5752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a5769`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a5b82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a5cd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a5b82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a5cd0`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1801a5b51`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1801a5b51`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801a5742`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801a5742`

## string_xrefs

- `0x1801a5a30`: `CabManifest.xml`
- `0x1801a5cad`: `Could not open dump file [%ws], %s\n    "%s"\n`
- `0x1801a5784`: `Unable to get full path of dump file\n`
- `0x1801a5c4d`: `A native dump is available in this archive: <link cmd=".opendump /c &quot;%s&quot; %ls">Click to open</link>\n`
- `0x1801a5c5b`: `A native dump is available in this archive. Run this command to open it: .opendump /c "%s" %ls\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_e5075cba4ceb4f6fbbae6c93eb464079_::operator()(unsigned __int16 ***a1)
{
  const unsigned __int16 *v2; // r13
  char *v3; // r15
  char *v4; // rsi
  unsigned int FilePathNameByHandle; // ebx
  DebuggerMeasuresLogger *v6; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  DebuggerMeasuresLogger *Instance; // rax
  unsigned int v13; // r8d
  int v14; // r12d
  const WCHAR *v15; // r14
  signed int LastError; // eax
  DebuggerMeasuresLogger *v17; // rax
  const char *v18; // rbx
  int v19; // r9d
  const WCHAR *v20; // rdx
  const char *v21; // rdx
  unsigned int v22; // esi
  DebuggerMeasuresLogger *v23; // rax
  const char *v24; // r8
  int v25; // r9d
  __int64 v26; // rax
  int v27; // r9d
  char *v28; // rdx
  int v29; // r12d
  TargetInfo *v30; // rbx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  unsigned __int16 *v35; // r8
  int *v36; // r8
  unsigned __int16 **v37; // r9
  const unsigned __int16 *v38; // rbx
  unsigned __int16 *v39; // rax
  DebuggerMeasuresLogger *v40; // rax
  unsigned int v41; // [rsp+28h] [rbp-D8h]
  int v42; // [rsp+50h] [rbp-B0h]
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h] BYREF
  void *v44; // [rsp+60h] [rbp-A0h] BYREF
  TargetInfo *v45; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h]
  __int64 v47; // [rsp+78h] [rbp-88h]
  _BYTE v48[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+90h] [rbp-70h]
  _BYTE v50[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v51[32]; // [rsp+C0h] [rbp-40h] BYREF
  const char *v52; // [rsp+E0h] [rbp-20h] BYREF
  int v53; // [rsp+ECh] [rbp-14h]
  const char *v54; // [rsp+200h] [rbp+100h] BYREF
  int v55; // [rsp+20Ch] [rbp+10Ch]
  char *v56; // [rsp+320h] [rbp+220h] BYREF
  int v57; // [rsp+32Ch] [rbp+22Ch]
  WCHAR v58[40]; // [rsp+540h] [rbp+440h] BYREF
  wchar_t Buffer[520]; // [rsp+590h] [rbp+490h] BYREF
  unsigned __int16 v60[520]; // [rsp+9A0h] [rbp+8A0h] BYREF
  WCHAR WideCharStr[520]; // [rsp+DB0h] [rbp+CB0h] BYREF
  unsigned __int16 v62[520]; // [rsp+11C0h] [rbp+10C0h] BYREF

  v47 = -2;
  v2 = 0;
  v45 = 0;
  v3 = (char *)*a1[1];
  v4 = 0;
  v44 = 0;
  memset(Buffer, 0, sizeof(Buffer));
  if ( (unsigned __int64)(v3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
LABEL_5:
    if ( !**a1 )
      return 2147942487LL;
    std::wstring::wstring(v50);
    v8 = Debugger::Ntsd::ExtensionGallery::trim(v51, v50);
    std::wstring::operator=(v50, v8);
    std::wstring::_Tidy_deallocate(v51);
    std::wstring::wstring(v48);
    v9 = Debugger::Ntsd::ExtensionGallery::trim(v51, v48);
    std::wstring::operator=(v48, v9);
    std::wstring::_Tidy_deallocate(v51);
    if ( !v49 )
      goto LABEL_22;
    **a1 = (unsigned __int16 *)std::wstring::c_str(v48, v10);
    lpFileName = (LPCWSTR)std::wstring::c_str(v50, v11);
    Instance = DebuggerMeasuresLogger::GetInstance();
    DebuggerMeasuresLogger::StartNewSession(Instance);
    FilePathNameByHandle = ConvertFileUrlPath(**a1, Buffer, v13, &lpFileName);
    if ( FilePathNameByHandle )
    {
LABEL_19:
      v17 = DebuggerMeasuresLogger::GetInstance();
      DebuggerMeasuresLogger::EndCurrentSession(v17, 0);
LABEL_23:
      std::wstring::_Tidy_deallocate(v48);
      std::wstring::_Tidy_deallocate(v50);
      return FilePathNameByHandle;
    }
    hObject = 0;
    v14 = 0;
    v42 = 0;
    v15 = lpFileName;
    if ( !(unsigned int)StringEndsWithW(lpFileName, L".zip") && !(unsigned int)StringEndsWithW(v15, L".cab") )
    {
      if ( (unsigned __int64)(v3 - 1) > 0xFFFFFFFFFFFFFFFDuLL && v15 != Buffer )
      {
        if ( !GetFullPathNameW(v15, 0x208u, Buffer, 0) )
        {
          if ( GetLastError() )
          {
            LastError = GetLastError();
            FilePathNameByHandle = LastError;
            if ( LastError > 0 )
              FilePathNameByHandle = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            FilePathNameByHandle = -2147467259;
          }
          ErrOut(L"Unable to get full path of dump file\n");
          Debugger::Utils::ConvertException__lambda_8fa64ac1834a4a0407a9ed2f1111f00c___();
          goto LABEL_19;
        }
        v15 = Buffer;
LABEL_57:
        v29 = IdentifyTargetFromFile(v15, (unsigned __int64)v3, v2, EngineConfiguration::s_UseReptTargetSupport, &v45);
        v30 = v45;
        if ( v29 >= 0 )
        {
          if ( v2 )
          {
            SendCabGuidTelemetry(v2, v45);
          }
          else if ( GetEnvironmentVariableW(L"CAB_GUID", v58, 0x25u) )
          {
            SendCabGuidTelemetry(v58, v30);
          }
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && !CloseHandle(hObject) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v32, v31, v33, v34);
          if ( v4 == v3 )
            v4 = 0;
          if ( v30 )
          {
            TargetInfo::InitializeBuildLab(v30);
            if ( v4 )
            {
              DbsDynamicString<unsigned short>::CopyStr((char *)v30 + 1792, **a1, 0xFFFFFFFFLL);
              *((_BYTE *)v30 + 46) = 1;
            }
          }
        }
        if ( v29 )
        {
          DbsDynamicString<unsigned short>::CopyStr(&g_LastFailedDumpFileW, v15, 0xFFFFFFFFLL);
          v38 = FormatAnyStatus(v29, (va_list *)*a1, v36, v37);
          v39 = FormatStatusCode(v29);
          ErrOut(L"Could not open dump file [%ws], %s\n    \"%s\"\n", **a1, v39, v38);
        }
        else
        {
          TargetInfo::SetFilename(v30, v15);
          v29 = TryFileTargetInitialize(v30, *a1[3], *(_DWORD *)a1[4]);
          if ( !v29 )
          {
            *((_DWORD *)v30 + 687) = *(_DWORD *)a1[5];
            if ( v42 )
            {
              v35 = **a1;
              if ( (g_EngOptions & 0x40000) != 0 )
                DmlOut(
                  L"A native dump is available in this archive: <link cmd=\".opendump /c &quot;%s&quot; %ls\">Click to open</link>\n",
                  v62,
                  v35);
              else
                dprintf(
                  L"A native dump is available in this archive. Run this command to open it: .opendump /c \"%s\" %ls\n",
                  v62,
                  v35);
            }
            TargetInfo::Link(v30);
            *(_QWORD *)*a1[6] = v30;
            goto LABEL_81;
          }
          if ( v30 )
            (**(void (__fastcall ***)(TargetInfo *, __int64))v30)(v30, 1);
        }
        v40 = DebuggerMeasuresLogger::GetInstance();
        DebuggerMeasuresLogger::EndCurrentSession(v40, 0);
LABEL_81:
        if ( v4 )
          CloseHandle(v4);
        FilePathNameByHandle = v29;
        goto LABEL_23;
      }
      if ( v15 )
        goto LABEL_57;
LABEL_22:
      FilePathNameByHandle = -2147467259;
      goto LABEL_23;
    }
    DbsDeclDynamicString<char,260,1>::DbsDeclDynamicString<char,260,1>(&v52);
    if ( v15 )
    {
      if ( !DbsDynamicString<char>::CopyStr((DbsDynamicBuffer *)&v52, v15, -1) )
      {
LABEL_28:
        DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v52);
        FilePathNameByHandle = -2147024882;
        goto LABEL_23;
      }
      v18 = 0;
      if ( v53 )
        v18 = v52;
    }
    else
    {
      v18 = 0;
    }
    DbsDeclDynamicString<char,260,1>::DbsDeclDynamicString<char,260,1>(&v54);
    v20 = *a1[2];
    if ( v20 )
    {
      if ( !DbsDynamicString<char>::CopyStr((DbsDynamicBuffer *)&v54, v20, -1) )
      {
LABEL_34:
        DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v54);
        goto LABEL_28;
      }
      v21 = 0;
      if ( v55 )
        v21 = v54;
    }
    else
    {
      v21 = 0;
    }
    v22 = ExpandDumpCab2(
            v18,
            v3,
            (g_EngOptions & 0x400000) == 0 ? 7 : 0,
            v19,
            (g_EngOptions >> 23) & 1,
            v21,
            CheckTargetCompositionExtraction,
            Buffer,
            0x208u,
            &v44);
    if ( v22 )
    {
      ErrOut(L"Unable to extract dump file from CAB file\n");
      Debugger::Utils::ConvertException__lambda_8fa64ac1834a4a0407a9ed2f1111f00c___();
      v23 = DebuggerMeasuresLogger::GetInstance();
      DebuggerMeasuresLogger::EndCurrentSession(v23, 0);
      DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v54);
      DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v52);
      FilePathNameByHandle = v22;
      goto LABEL_23;
    }
    v2 = v15;
    v15 = Buffer;
    DbsDynamicString<unsigned short>::CopyStr(&g_LastCabFileW, **a1, 0xFFFFFFFFLL);
    dprintf(L"Extracted %s from\n %ws\n", Buffer, **a1);
    v26 = -1;
    do
      ++v26;
    while ( Buffer[v26] );
    if ( (unsigned int)v26 < 5 || _wcsicmp(&Buffer[(unsigned int)(v26 - 5)], L".ndmp") )
    {
      if ( !(unsigned int)FindMatchInCab(v18, v3, v24, v25, v62, v41) )
        v14 = 1;
      v42 = v14;
    }
    lpFileName = 0;
    memset(WideCharStr, 0, sizeof(WideCharStr));
    if ( !(unsigned int)ExpandDumpCab2(
                          v18,
                          v3,
                          (g_EngOptions & 0x400000) == 0 ? 7 : 0,
                          v27,
                          0,
                          "CabManifest.xml",
                          0,
                          WideCharStr,
                          0x208u,
                          (void **)&lpFileName) )
    {
      DbsDeclDynamicString<char,520,1>::DbsDeclDynamicString<char,520,1>(&v56);
      if ( !DbsDynamicString<char>::CopyStr((DbsDynamicBuffer *)&v56, WideCharStr, -1) )
      {
        DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v56);
        goto LABEL_34;
      }
      v28 = 0;
      if ( v57 )
        v28 = v56;
      if ( (unsigned int)MakeTargetInformationFile(v18, v28, (HANDLE)lpFileName) )
        ErrOut(L"Unable to build a TIF file from page files in CAB\n");
      DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v56);
    }
    v4 = (char *)v44;
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      hObject = v3;
      v3 = (char *)v44;
    }
    DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v54);
    DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v52);
    goto LABEL_57;
  }
  g_IsDumpOpenedByFileHandle = 1;
  FilePathNameByHandle = DbgGetFilePathNameByHandle(v3, v60);
  if ( !FilePathNameByHandle )
  {
    v60[519] = 0;
    **a1 = v60;
    goto LABEL_5;
  }
  v6 = DebuggerMeasuresLogger::GetInstance();
  DebuggerMeasuresLogger::EndCurrentSession(v6, 0);
  return FilePathNameByHandle;
}

```

## disassembly

```asm
0x1801a5544  push    rbp
0x1801a5546  push    rbx
0x1801a5547  push    rsi
0x1801a5548  push    rdi
0x1801a5549  push    r12
0x1801a554b  push    r13
0x1801a554d  push    r14
0x1801a554f  push    r15
0x1801a5551  lea     rbp, [rsp-14E8h]
0x1801a5559  mov     eax, 15E8h
0x1801a555e  call    _alloca_probe
0x1801a5563  sub     rsp, rax
0x1801a5566  mov     [rsp+1620h+var_15A8], 0FFFFFFFFFFFFFFFEh
0x1801a556f  mov     rax, cs:__security_cookie
0x1801a5576  xor     rax, rsp
0x1801a5579  mov     [rbp+1520h+var_50], rax
0x1801a5580  mov     rdi, rcx
0x1801a5583  xor     r13d, r13d
0x1801a5586  mov     [rsp+1620h+var_15B8], r13
0x1801a558b  mov     rax, [rcx]
0x1801a558e  mov     rbx, [rax]
0x1801a5591  mov     rax, [rcx+8]
0x1801a5595  mov     r15, [rax]
0x1801a5598  mov     esi, r13d
0x1801a559b  mov     [rsp+1620h+var_15C0], r13
0x1801a55a0  xor     edx, edx; Val
0x1801a55a2  mov     r8d, 410h; Size
0x1801a55a8  lea     rcx, [rbp+1520h+Buffer]; void *
0x1801a55af  call    memset
0x1801a55b4  lea     rax, [r15-1]
0x1801a55b8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801a55bc  ja      short loc_1801A560A
0x1801a55be  mov     cs:?g_IsDumpOpenedByFileHandle@@3EA, 1; uchar g_IsDumpOpenedByFileHandle
0x1801a55c5  lea     rdx, [rbp+1520h+var_C80]; unsigned __int16 *
0x1801a55cc  mov     rcx, r15; hFile
0x1801a55cf  call    DbgGetFilePathNameByHandle
0x1801a55d4  mov     ebx, eax
0x1801a55d6  test    eax, eax
0x1801a55d8  jz      short loc_1801A55EE
0x1801a55da  call    ?GetInstance@DebuggerMeasuresLogger@@SAPEAV1@XZ; DebuggerMeasuresLogger::GetInstance(void)
0x1801a55df  xor     edx, edx; bool
0x1801a55e1  mov     rcx, rax; this
0x1801a55e4  call    ?EndCurrentSession@DebuggerMeasuresLogger@@QEAAX_N@Z; DebuggerMeasuresLogger::EndCurrentSession(bool)
0x1801a55e9  jmp     loc_1801A57D6
0x1801a55ee  mov     [rbp+1520h+var_872], r13w
0x1801a55f6  lea     rbx, [rbp+1520h+var_C80]
0x1801a55fd  mov     rax, [rdi]
0x1801a5600  lea     rcx, [rbp+1520h+var_C80]
0x1801a5607  mov     [rax], rcx
0x1801a560a  mov     rax, [rdi]
0x1801a560d  cmp     [rax], r13
0x1801a5610  jnz     short loc_1801A561C
0x1801a5612  mov     eax, 80070057h
0x1801a5617  jmp     loc_1801A57D8
0x1801a561c  mov     rdx, rbx
0x1801a561f  lea     rcx, [rbp+1520h+var_1580]
0x1801a5623  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801a5628  nop
0x1801a5629  lea     rdx, [rbp+1520h+var_1580]
0x1801a562d  lea     rcx, [rbp+1520h+var_1560]
0x1801a5631  call    ?trim@ExtensionGallery@Ntsd@Debugger@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; Debugger::Ntsd::ExtensionGallery::trim(std::wstring const &)
0x1801a5636  mov     rdx, rax
0x1801a5639  lea     rcx, [rbp+1520h+var_1580]
0x1801a563d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801a5642  lea     rcx, [rbp+1520h+var_1560]
0x1801a5646  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a564b  mov     rdx, [rdi]
0x1801a564e  mov     rdx, [rdx]
0x1801a5651  lea     rcx, [rbp+1520h+var_15A0]
0x1801a5655  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801a565a  nop
0x1801a565b  lea     rdx, [rbp+1520h+var_15A0]
0x1801a565f  lea     rcx, [rbp+1520h+var_1560]
0x1801a5663  call    ?trim@ExtensionGallery@Ntsd@Debugger@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; Debugger::Ntsd::ExtensionGallery::trim(std::wstring const &)
0x1801a5668  mov     rdx, rax
0x1801a566b  lea     rcx, [rbp+1520h+var_15A0]
0x1801a566f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801a5674  lea     rcx, [rbp+1520h+var_1560]
0x1801a5678  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a567d  cmp     [rbp+1520h+var_1590], r13
0x1801a5681  jz      loc_1801A57BE
0x1801a5687  lea     rcx, [rbp+1520h+var_15A0]
0x1801a568b  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1801a5690  mov     rcx, [rdi]
0x1801a5693  mov     [rcx], rax
0x1801a5696  lea     rcx, [rbp+1520h+var_1580]
0x1801a569a  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1801a569f  mov     [rsp+1620h+lpFileName], rax
0x1801a56a4  call    ?GetInstance@DebuggerMeasuresLogger@@SAPEAV1@XZ; DebuggerMeasuresLogger::GetInstance(void)
0x1801a56a9  mov     rcx, rax; this
0x1801a56ac  call    ?StartNewSession@DebuggerMeasuresLogger@@QEAAXXZ; DebuggerMeasuresLogger::StartNewSession(void)
0x1801a56b1  mov     rcx, [rdi]
0x1801a56b4  lea     r9, [rsp+1620h+lpFileName]; unsigned __int16 **
0x1801a56b9  lea     rdx, [rbp+1520h+Buffer]; unsigned __int16 *
0x1801a56c0  mov     rcx, [rcx]; unsigned __int16 *
0x1801a56c3  call    ?ConvertFileUrlPath@@YAJPEBGPEAGKPEAPEBG@Z; ConvertFileUrlPath(ushort const *,ushort *,ulong,ushort const * *)
0x1801a56c8  mov     ebx, eax
0x1801a56ca  test    eax, eax
0x1801a56cc  jnz     loc_1801A5795
0x1801a56d2  mov     [rsp+1620h+hObject], r13
0x1801a56d7  mov     r12d, r13d
0x1801a56da  mov     [rsp+1620h+var_15D0], r13d
0x1801a56df  mov     r14, [rsp+1620h+lpFileName]
0x1801a56e4  lea     rdx, aZip; ".zip"
0x1801a56eb  mov     rcx, r14; unsigned __int16 *
0x1801a56ee  call    ?StringEndsWithW@@YAHPEBG0@Z; StringEndsWithW(ushort const *,ushort const *)
0x1801a56f3  test    eax, eax
0x1801a56f5  jnz     loc_1801A57FC
0x1801a56fb  lea     rdx, aCab; ".cab"
0x1801a5702  mov     rcx, r14; unsigned __int16 *
0x1801a5705  call    ?StringEndsWithW@@YAHPEBG0@Z; StringEndsWithW(ushort const *,ushort const *)
0x1801a570a  test    eax, eax
0x1801a570c  jnz     loc_1801A57FC
0x1801a5712  lea     rax, [r15-1]
0x1801a5716  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801a571a  jbe     loc_1801A57B2
0x1801a5720  lea     rax, [rbp+1520h+Buffer]
0x1801a5727  cmp     r14, rax
0x1801a572a  jz      loc_1801A57B2
0x1801a5730  xor     r9d, r9d; lpFilePart
0x1801a5733  lea     r8, [rbp+1520h+Buffer]; lpBuffer
0x1801a573a  mov     edx, 208h; nBufferLength
0x1801a573f  mov     rcx, r14; lpFileName
0x1801a5742  call    cs:__imp_GetFullPathNameW
0x1801a5749  nop     dword ptr [rax+rax+00h]
0x1801a574e  test    eax, eax
0x1801a5750  jnz     short loc_1801A57A6
0x1801a5752  call    cs:__imp_GetLastError
0x1801a5759  nop     dword ptr [rax+rax+00h]
0x1801a575e  test    eax, eax
0x1801a5760  jnz     short loc_1801A5769
0x1801a5762  mov     ebx, 80004005h
0x1801a5767  jmp     short loc_1801A5784
0x1801a5769  call    cs:__imp_GetLastError
0x1801a5770  nop     dword ptr [rax+rax+00h]
0x1801a5775  mov     ebx, eax
0x1801a5777  test    eax, eax
0x1801a5779  jle     short loc_1801A5784
0x1801a577b  movzx   ebx, ax
0x1801a577e  or      ebx, 80070000h
0x1801a5784  lea     rcx, aUnableToGetFul; "Unable to get full path of dump file\n"
0x1801a578b  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1801a5790  call    Debugger__Utils__ConvertException__lambda_8fa64ac1834a4a0407a9ed2f1111f00c___
0x1801a5795  call    ?GetInstance@DebuggerMeasuresLogger@@SAPEAV1@XZ; DebuggerMeasuresLogger::GetInstance(void)
0x1801a579a  xor     edx, edx; bool
0x1801a579c  mov     rcx, rax; this
0x1801a579f  call    ?EndCurrentSession@DebuggerMeasuresLogger@@QEAAX_N@Z; DebuggerMeasuresLogger::EndCurrentSession(bool)
0x1801a57a4  jmp     short loc_1801A57C3
0x1801a57a6  lea     r14, [rbp+1520h+Buffer]
0x1801a57ad  jmp     loc_1801A5AF2
0x1801a57b2  mov     rax, r14
0x1801a57b5  test    rax, rax
0x1801a57b8  jnz     loc_1801A5AF2
0x1801a57be  mov     ebx, 80004005h
0x1801a57c3  lea     rcx, [rbp+1520h+var_15A0]
0x1801a57c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a57cc  nop
0x1801a57cd  lea     rcx, [rbp+1520h+var_1580]
0x1801a57d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a57d6  mov     eax, ebx
0x1801a57d8  mov     rcx, [rbp+1520h+var_50]
0x1801a57df  xor     rcx, rsp; StackCookie
0x1801a57e2  call    __security_check_cookie
0x1801a57e7  add     rsp, 15E8h
0x1801a57ee  pop     r15
0x1801a57f0  pop     r14
0x1801a57f2  pop     r13
0x1801a57f4  pop     r12
0x1801a57f6  pop     rdi
0x1801a57f7  pop     rsi
0x1801a57f8  pop     rbx
0x1801a57f9  pop     rbp
0x1801a57fa  retn
0x1801a57fc  lea     rcx, [rbp+1520h+var_1540]
0x1801a5800  call    ??0?$DbsDeclDynamicString@D$0BAE@$00@@QEAA@XZ; DbsDeclDynamicString<char,260,1>::DbsDeclDynamicString<char,260,1>(void)
0x1801a5805  nop
0x1801a5806  test    r14, r14
0x1801a5809  jnz     short loc_1801A5814
0x1801a580b  mov     rbx, r13
0x1801a580e  lea     esi, [r14+1]
0x1801a5812  jmp     short loc_1801A5849
0x1801a5814  or      r8d, 0FFFFFFFFh; cchWideChar
0x1801a5818  mov     rdx, r14; lpWideCharStr
0x1801a581b  lea     rcx, [rbp+1520h+var_1540]; this
0x1801a581f  call    ?CopyStr@?$DbsDynamicString@D@@QEAAPEADPEBGK@Z; DbsDynamicString<char>::CopyStr(ushort const *,ulong)
0x1801a5824  test    rax, rax
0x1801a5827  jnz     short loc_1801A5839
0x1801a5829  lea     rcx, [rbp+1520h+var_1540]
0x1801a582d  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1801a5832  mov     ebx, 8007000Eh
0x1801a5837  jmp     short loc_1801A57C3
0x1801a5839  mov     rbx, r13
0x1801a583c  mov     esi, 1
0x1801a5841  cmp     [rbp+1520h+var_1534], esi
0x1801a5844  cmovnb  rbx, [rbp+1520h+var_1540]
0x1801a5849  lea     rcx, [rbp+1520h+var_1420]
0x1801a5850  call    ??0?$DbsDeclDynamicString@D$0BAE@$00@@QEAA@XZ; DbsDeclDynamicString<char,260,1>::DbsDeclDynamicString<char,260,1>(void)
0x1801a5855  nop
0x1801a5856  mov     rax, [rdi+10h]
0x1801a585a  mov     rdx, [rax]; lpWideCharStr
0x1801a585d  test    rdx, rdx
0x1801a5860  jnz     short loc_1801A5867
0x1801a5862  mov     rdx, r13
0x1801a5865  jmp     short loc_1801A589B
0x1801a5867  or      r8d, 0FFFFFFFFh; cchWideChar
0x1801a586b  lea     rcx, [rbp+1520h+var_1420]; this
0x1801a5872  call    ?CopyStr@?$DbsDynamicString@D@@QEAAPEADPEBGK@Z; DbsDynamicString<char>::CopyStr(ushort const *,ulong)
0x1801a5877  test    rax, rax
0x1801a587a  jnz     short loc_1801A588A
0x1801a587c  lea     rcx, [rbp+1520h+var_1420]
0x1801a5883  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1801a5888  jmp     short loc_1801A5829
0x1801a588a  mov     rdx, r13
0x1801a588d  cmp     [rbp+1520h+var_1414], esi
0x1801a5893  cmovnb  rdx, [rbp+1520h+var_1420]
0x1801a589b  mov     eax, cs:?g_EngOptions@@3KA; ulong g_EngOptions
0x1801a58a1  mov     ecx, eax
0x1801a58a3  shr     ecx, 17h
0x1801a58a6  and     ecx, esi
0x1801a58a8  and     eax, 400000h
0x1801a58ad  neg     eax
0x1801a58af  sbb     r8d, r8d
0x1801a58b2  not     r8d
0x1801a58b5  and     r8d, 7; unsigned int
0x1801a58b9  lea     rax, [rsp+1620h+var_15C0]
0x1801a58be  mov     [rsp+1620h+var_15D8], rax; void **
0x1801a58c3  mov     [rsp+1620h+var_15E0], 208h; unsigned int
0x1801a58cb  lea     rax, [rbp+1520h+Buffer]
0x1801a58d2  mov     [rsp+1620h+var_15E8], rax; wchar_t *
0x1801a58d7  lea     rax, ?CheckTargetCompositionExtraction@@YAHKPEBDPEAXK1@Z; CheckTargetCompositionExtraction(ulong,char const *,void *,ulong,void *)
0x1801a58de  mov     [rsp+1620h+var_15F0], rax; int (*)(unsigned int, const char *, void *, unsigned int, void *)
0x1801a58e3  mov     [rsp+1620h+var_15F8], rdx; unsigned int
0x1801a58e8  mov     dword ptr [rsp+1620h+var_1600], ecx; int
0x1801a58ec  mov     rdx, r15; void *
0x1801a58ef  mov     rcx, rbx; char *
0x1801a58f2  call    ?ExpandDumpCab2@@YAJPEBDPEAXKHH0P6AHK01K1@ZPEAGKPEAPEAX@Z; ExpandDumpCab2(char const *,void *,ulong,int,int,char const *,int (*)(ulong,char const *,void *,ulong,void *),ushort *,ulong,void * *)
0x1801a58f7  mov     esi, eax
0x1801a58f9  test    eax, eax
0x1801a58fb  jz      short loc_1801A593B
0x1801a58fd  lea     rcx, aUnableToExtrac_0; "Unable to extract dump file from CAB fi"...
0x1801a5904  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1801a5909  call    Debugger__Utils__ConvertException__lambda_8fa64ac1834a4a0407a9ed2f1111f00c___
0x1801a590e  call    ?GetInstance@DebuggerMeasuresLogger@@SAPEAV1@XZ; DebuggerMeasuresLogger::GetInstance(void)
0x1801a5913  xor     edx, edx; bool
0x1801a5915  mov     rcx, rax; this
0x1801a5918  call    ?EndCurrentSession@DebuggerMeasuresLogger@@QEAAX_N@Z; DebuggerMeasuresLogger::EndCurrentSession(bool)
0x1801a591d  nop
0x1801a591e  lea     rcx, [rbp+1520h+var_1420]
0x1801a5925  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1801a592a  nop
0x1801a592b  lea     rcx, [rbp+1520h+var_1540]
0x1801a592f  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1801a5934  mov     ebx, esi
0x1801a5936  jmp     loc_1801A57C3
0x1801a593b  mov     r13, r14
0x1801a593e  lea     r14, [rbp+1520h+Buffer]
0x1801a5945  mov     rdx, [rdi]
0x1801a5948  or      r8d, 0FFFFFFFFh
0x1801a594c  mov     rdx, [rdx]
0x1801a594f  lea     rcx, ?g_LastCabFileW@@3V?$DbsDeclDynamicString@G$0BAE@$00@@A; DbsDeclDynamicString<ushort,260,1> g_LastCabFileW
0x1801a5956  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x1801a595b  mov     r8, [rdi]
0x1801a595e  mov     r8, [r8]
0x1801a5961  lea     rdx, [rbp+1520h+Buffer]
0x1801a5968  lea     rcx, aExtractedSFrom; "Extracted %s from\n %ws\n"
0x1801a596f  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801a5974  lea     rcx, [rbp+1520h+Buffer]
0x1801a597b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801a597f  xor     esi, esi
0x1801a5981  inc     rax
0x1801a5984  cmp     [rcx+rax*2], si
0x1801a5988  jnz     short loc_1801A5981
0x1801a598a  cmp     eax, 5
0x1801a598d  jb      short loc_1801A59B6
0x1801a598f  add     eax, 0FFFFFFFBh
0x1801a5992  mov     ecx, eax
0x1801a5994  lea     rax, [rbp+1520h+Buffer]
0x1801a599b  lea     rcx, [rax+rcx*2]; String1
0x1801a599f  lea     rdx, aNdmp; ".ndmp"
0x1801a59a6  call    cs:__imp__wcsicmp
0x1801a59ad  nop     dword ptr [rax+rax+00h]
0x1801a59b2  test    eax, eax
0x1801a59b4  jz      short loc_1801A59DD
0x1801a59b6  lea     rax, [rbp+1520h+var_460]
0x1801a59bd  mov     [rsp+1620h+var_1600], rax; unsigned __int16 *
0x1801a59c2  mov     rdx, r15; void *
0x1801a59c5  mov     rcx, rbx; char *
0x1801a59c8  call    ?FindMatchInCab@@YAJPEBDPEAX0HPEAGK@Z; FindMatchInCab(char const *,void *,char const *,int,ushort *,ulong)
0x1801a59cd  test    eax, eax
0x1801a59cf  mov     eax, 1
0x1801a59d4  cmovz   r12d, eax
0x1801a59d8  mov     [rsp+1620h+var_15D0], r12d
0x1801a59dd  mov     [rsp+1620h+lpFileName], rsi
0x1801a59e2  xor     edx, edx; Val
0x1801a59e4  mov     r8d, 410h; Size
0x1801a59ea  lea     rcx, [rbp+1520h+WideCharStr]; void *
0x1801a59f1  call    memset
0x1801a59f6  mov     eax, cs:?g_EngOptions@@3KA; ulong g_EngOptions
0x1801a59fc  and     eax, 400000h
0x1801a5a01  neg     eax
  ... truncated ...
```
