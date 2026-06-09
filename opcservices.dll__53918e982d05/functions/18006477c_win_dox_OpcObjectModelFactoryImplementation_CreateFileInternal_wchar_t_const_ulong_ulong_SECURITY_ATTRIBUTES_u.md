# win_dox::OpcObjectModelFactoryImplementation::CreateFileInternal(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)

- ea: `0x18006477c`
- end: `0x180064d20`
- name: `?CreateFileInternal@OpcObjectModelFactoryImplementation@win_dox@@AEBAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KK@Z`
- size: `1444`
- prototype: `HANDLE __fastcall(win_dox::OpcObjectModelFactoryImplementation *this, const wchar_t *, DWORD, DWORD, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD, DWORD dwFlagsAndAttributes)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800643fc`

## callees

- `0x180012468`
- `0x1800124f4`
- `0x180017320`
- `0x18002db70`
- `0x180060c90`
- `0x18006477c`
- `0x18006554c`
- `0x180084010`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x1800d0afc`
- `0x1800d0b6c`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800648ee`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800648ee`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18006496c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180064b03`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18006496c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180064b03`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180064acf`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180064acf`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180064b6c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180064c28`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180064b6c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180064c28`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180064ae4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180064b2a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180064b88`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180064ae4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180064b2a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180064b88`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180064839`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180064839`

## string_xrefs

- `0x18006488d`: `Call to ::CreateFile failed with HResult 0x%X.`
- `0x1800649b0`: `Call to ::LoadLibraryEx failed with HResult 0x%X.`
- `0x180064ada`: `SetDefaultDllDirectories`
- `0x180064ac8`: `api-ms-win-core-libraryloader-l1-1-0.dll`
- `0x180064b7e`: `CreateFile2`
- `0x180064cc8`: `Call to ::CreateFile2 failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
HANDLE __fastcall win_dox::OpcObjectModelFactoryImplementation::CreateFileInternal(
        win_dox::OpcObjectModelFactoryImplementation *this,
        const wchar_t *a2,
        DWORD a3,
        DWORD a4,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        DWORD a6,
        DWORD dwFlagsAndAttributes)
{
  struct _SECURITY_ATTRIBUTES *v10; // rbx
  DWORD dwCreationDisposition; // edi
  HANDLE result; // rax
  win_musl::detail *v13; // rcx
  unsigned int v14; // edi
  HMODULE v15; // rax
  HMODULE v16; // rcx
  unsigned int LastErrorAsFailHR; // ebx
  win_musl::Formatter *v18; // rcx
  struct win_musl::TStringEllipseBase *v19; // rax
  HMODULE ModuleHandleW; // rax
  DWORD v21; // r14d
  HMODULE Library; // rax
  HMODULE v23; // rbx
  FARPROC ProcAddress; // rax
  int v25; // eax
  win_musl::detail *v26; // rcx
  unsigned int v27; // ebx
  int v28; // edi
  win_musl::detail *v29; // rcx
  unsigned int v30; // ebx
  __int64 v31; // [rsp+48h] [rbp-C0h] BYREF
  const char *v32; // [rsp+50h] [rbp-B8h] BYREF
  struct _SECURITY_ATTRIBUTES *v33; // [rsp+58h] [rbp-B0h]
  __int64 v34; // [rsp+60h] [rbp-A8h]
  _DWORD v35[3]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v36; // [rsp+74h] [rbp-94h]
  __int128 v37; // [rsp+78h] [rbp-90h]
  wchar_t pExceptionObject[12]; // [rsp+98h] [rbp-70h] BYREF
  _DWORD v39[2]; // [rsp+B0h] [rbp-58h] BYREF
  const char *v40; // [rsp+B8h] [rbp-50h]
  _BYTE v41[56]; // [rsp+C0h] [rbp-48h] BYREF
  GUID v42; // [rsp+F8h] [rbp-10h]
  int v43; // [rsp+120h] [rbp+18h]
  wchar_t v44[512]; // [rsp+498h] [rbp+390h] BYREF

  v34 = -2;
  v10 = lpSecurityAttributes;
  v33 = lpSecurityAttributes;
  dwCreationDisposition = a6;
  if ( dword_1801C5380 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1801C5380);
    if ( dword_1801C5380 == -1 )
    {
      atexit(win_dox::OpcObjectModelFactoryImplementation::CreateFileInternal_::_2_::_dynamic_atexit_destructor_for__s_hmoduleKernelBase__);
      Init_thread_footer(&dword_1801C5380);
    }
  }
  if ( !byte_1801C5100 )
  {
    ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-libraryloader-l1-1-0.dll");
    if ( ModuleHandleW )
      ModuleHandleW = (HMODULE)GetProcAddress(ModuleHandleW, "SetDefaultDllDirectories");
    v21 = ModuleHandleW != 0 ? 0x800 : 0;
    Library = LoadLibraryExW(L"api-ms-win-appmodel-runtime-l1-1-0", 0, v21);
    v23 = Library;
    if ( Library )
    {
      v32 = (const char *)Library;
      ProcAddress = GetProcAddress(Library, "GetCurrentPackageId");
      if ( ProcAddress )
      {
        HIDWORD(v31) = 0;
        v25 = ((__int64 (__fastcall *)(char *, _QWORD))ProcAddress)((char *)&v31 + 4, 0);
        v28 = v25;
        if ( v25 == 122 )
        {
          v15 = LoadLibraryExW(L"kernelbase", 0, v21);
          v16 = hLibModule;
          hLibModule = v15;
          if ( v16 )
          {
            FreeLibrary(v16);
            v15 = hLibModule;
          }
          if ( !v15 )
          {
            LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR((win_musl::detail *)v16);
            memset_0(v44, 0, sizeof(v44));
            StringCchPrintfW(v44, 0x200u, L"Call to ::LoadLibraryEx failed with HResult 0x%X.", LastErrorAsFailHR);
            win_musl::detail::ThrowBuilder<SplException::THResultException>(
              (SplException::TSystemException *)pExceptionObject,
              0x4Fu,
              LastErrorAsFailHR,
              (struct win_musl::TStringEllipseBase *)v44);
            throw (SplException::THResultException *)pExceptionObject;
          }
          hTemplateFile = GetProcAddress(v15, "CreateFile2");
          if ( !hTemplateFile )
          {
            v27 = win_musl::detail::GetLastErrorAsFailHR(v26);
            memset_0(v44, 0, sizeof(v44));
            StringCchPrintfW(v44, 0x200u, L"Call to ::GetProcAddress failed with HResult 0x%X.", v27);
            win_musl::detail::ThrowBuilder<SplException::THResultException>(
              (SplException::TSystemException *)pExceptionObject,
              0x52u,
              v27,
              (struct win_musl::TStringEllipseBase *)v44);
            throw (SplException::THResultException *)pExceptionObject;
          }
        }
        else if ( v25 != 15700 )
        {
          std::wstring::wstring(v35, L"::GetCurrentPackageId failed");
          v18 = (win_musl::Formatter *)win_musl::Formatter::Formatter(pExceptionObject, v35);
          v19 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v18);
          if ( v28 > 0 )
            v28 = (unsigned __int16)v28 | 0x80070000;
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::TSystemException *)v44,
            0x58u,
            v28,
            v19);
          throw (SplException::THResultException *)v44;
        }
        dwCreationDisposition = a6;
      }
    }
    else
    {
      v32 = 0;
    }
    byte_1801C5100 = 1;
    if ( v23 )
      FreeLibrary(v23);
    v10 = v33;
  }
  if ( hTemplateFile )
  {
    v35[0] = 32;
    v36 = 0;
    v37 = 0;
    v35[1] = (unsigned __int16)dwFlagsAndAttributes;
    v35[2] = dwFlagsAndAttributes & 0xFFF80000;
    if ( (dwFlagsAndAttributes & 0x100000) != 0 )
      v36 = dwFlagsAndAttributes & 0x1F0000;
    else
      v36 = 0;
    *(_QWORD *)&v37 = v10;
    result = (HANDLE)((__int64 (__fastcall *)(const wchar_t *, _QWORD, _QWORD, _QWORD, _DWORD *))hTemplateFile)(
                       a2,
                       a3,
                       a4,
                       dwCreationDisposition,
                       v35);
    if ( result == (HANDLE)-1LL )
    {
      v30 = win_musl::detail::GetLastErrorAsFailHR(v29);
      memset_0(pExceptionObject, 0, 0x400u);
      StringCchPrintfW(pExceptionObject, 0x200u, L"Call to ::CreateFile2 failed with HResult 0x%X.", v30);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v44,
        0x7Au,
        v30,
        (struct win_musl::TStringEllipseBase *)pExceptionObject);
      throw (SplException::THResultException *)v44;
    }
  }
  else
  {
    result = CreateFileW(a2, a3, a4, v10, dwCreationDisposition, dwFlagsAndAttributes, 0);
    if ( result == (HANDLE)-1LL )
    {
      v14 = win_musl::detail::GetLastErrorAsFailHR(v13);
      memset_0(v44, 0, sizeof(v44));
      StringCchPrintfW(v44, 0x200u, L"Call to ::CreateFile failed with HResult 0x%X.", v14);
      win_musl::DebugLogHelper("(no filename)", &word_180139126, 105, 1024, v14, v44);
      v32 = "Unexpected HRESULT returned by API";
      exception::exception((exception *)pExceptionObject, &v32);
      memset_0(v41, 0, 0x68u);
      v40 = "(no filename)";
      v39[1] = 105;
      v43 = -1;
      *(_QWORD *)pExceptionObject = &SplException::THResultException::`vftable';
      v39[0] = -2147467259;
      if ( v14 )
        v39[0] = v14;
      v42 = GUID_NULL;
      if ( SplException::Functions )
        v43 = SplException::Functions(v39);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006477c  mov     rax, rsp
0x18006477f  push    rbp
0x180064780  push    rsi
0x180064781  push    rdi
0x180064782  push    r12
0x180064784  push    r13
0x180064786  push    r14
0x180064788  push    r15
0x18006478a  lea     rbp, [rax-7D8h]
0x180064791  sub     rsp, 8A0h
0x180064798  mov     qword ptr [rsp+8D0h+var_878], 0FFFFFFFFFFFFFFFEh
0x1800647a1  mov     [rax+8], rbx
0x1800647a5  mov     rax, cs:__security_cookie
0x1800647ac  xor     rax, rsp
0x1800647af  mov     [rbp+7D0h+var_40], rax
0x1800647b6  mov     r13d, r9d
0x1800647b9  mov     r12d, r8d
0x1800647bc  mov     r15, rdx
0x1800647bf  mov     rbx, [rbp+7D0h+lpSecurityAttributes]
0x1800647c6  mov     [rsp+8D0h+var_880], rbx
0x1800647cb  mov     edi, [rbp+7D0h+arg_28]
0x1800647d1  mov     dword ptr [rsp+8D0h+var_890], edi
0x1800647d5  mov     esi, [rbp+7D0h+arg_30]
0x1800647db  mov     ecx, cs:_tls_index
0x1800647e1  mov     rax, gs:58h
0x1800647ea  mov     edx, 4
0x1800647ef  mov     rax, [rax+rcx*8]
0x1800647f3  mov     eax, [rdx+rax]
0x1800647f6  cmp     cs:dword_1801C5380, eax
0x1800647fc  jg      loc_180064A92
0x180064802  mov     al, cs:byte_1801C5100
0x180064808  test    al, al
0x18006480a  jz      loc_180064AC8
0x180064810  mov     rax, cs:hTemplateFile
0x180064817  test    rax, rax
0x18006481a  jnz     loc_180064C3B
0x180064820  mov     [rsp+30h], rax; hTemplateFile
0x180064825  mov     [rsp+8D0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180064829  mov     [rsp+8D0h+dwCreationDisposition], edi; dwCreationDisposition
0x18006482d  mov     r9, rbx; lpSecurityAttributes
0x180064830  mov     r8d, r13d; dwShareMode
0x180064833  mov     edx, r12d; dwDesiredAccess
0x180064836  mov     rcx, r15; lpFileName
0x180064839  call    cs:__imp_CreateFileW
0x18006483f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180064843  jz      short loc_18006486F
0x180064845  mov     rcx, [rbp+7D0h+var_40]
0x18006484c  xor     rcx, rsp; StackCookie
0x18006484f  call    __security_check_cookie
0x180064854  mov     rbx, [rsp+8D0h+arg_0]
0x18006485c  add     rsp, 8A0h
0x180064863  pop     r15
0x180064865  pop     r14
0x180064867  pop     r13
0x180064869  pop     r12
0x18006486b  pop     rdi
0x18006486c  pop     rsi
0x18006486d  pop     rbp
0x18006486e  retn
0x18006486f  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180064874  mov     edi, eax
0x180064876  xor     edx, edx; Val
0x180064878  mov     r8d, 400h; Size
0x18006487e  lea     rcx, [rbp+7D0h+var_440]; void *
0x180064885  call    memset_0
0x18006488a  mov     r9d, edi
0x18006488d  lea     r8, aCallToCreatefi; "Call to ::CreateFile failed with HResul"...
0x180064894  mov     edx, 200h; unsigned __int64
0x180064899  lea     rcx, [rbp+7D0h+var_440]; wchar_t *
0x1800648a0  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800648a5  lea     rax, [rbp+7D0h+var_440]
0x1800648ac  mov     qword ptr [rsp+8D0h+dwFlagsAndAttributes], rax
0x1800648b1  mov     [rsp+8D0h+dwCreationDisposition], edi
0x1800648b5  mov     esi, 69h ; 'i'
0x1800648ba  mov     r9d, 400h
0x1800648c0  mov     r8d, esi
0x1800648c3  lea     rdx, word_180139126
0x1800648ca  lea     rbx, aNoFilename; "(no filename)"
0x1800648d1  mov     rcx, rbx
0x1800648d4  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x1800648d9  lea     rax, aUnexpectedHres; "Unexpected HRESULT returned by API"
0x1800648e0  mov     [rsp+8D0h+var_888], rax
0x1800648e5  lea     rdx, [rsp+8D0h+var_888]
0x1800648ea  lea     rcx, [rbp+7D0h+pExceptionObject]
0x1800648ee  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x1800648f4  xor     edx, edx; Val
0x1800648f6  lea     r8d, [rsi-1]; Size
0x1800648fa  lea     rcx, [rbp+7D0h+var_818]; void *
0x1800648fe  call    memset_0
0x180064903  mov     [rbp+7D0h+var_820], rbx
0x180064907  mov     [rbp+7D0h+var_824], esi
0x18006490a  mov     [rbp+7D0h+var_7B8], 0FFFFFFFFh
0x180064911  lea     rax, ??_7THResultException@SplException@@6B@; const SplException::THResultException::`vftable'
0x180064918  mov     qword ptr [rbp+7D0h+pExceptionObject], rax
0x18006491c  mov     [rbp+7D0h+var_828], 80004005h
0x180064923  test    edi, edi
0x180064925  jnz     loc_180064C33
0x18006492b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180064932  movdqu  [rbp+7D0h+var_7E0], xmm0
0x180064937  mov     rax, cs:?Functions@SplException@@3UExceptionTableFunctions@1@A; SplException::ExceptionTableFunctions SplException::Functions
0x18006493e  test    rax, rax
0x180064941  jz      short loc_18006494F
0x180064943  lea     rcx, [rbp+7D0h+var_828]
0x180064947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006494c  mov     [rbp+7D0h+var_7B8], eax
0x18006494f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180064956  lea     rcx, [rbp+7D0h+pExceptionObject]; pExceptionObject
0x18006495a  call    _CxxThrowException_0
0x180064960  mov     r8d, r14d; dwFlags
0x180064963  xor     edx, edx; hFile
0x180064965  lea     rcx, aKernelbase; "kernelbase"
0x18006496c  call    cs:__imp_LoadLibraryExW
0x180064972  mov     rcx, cs:hLibModule; this
0x180064979  mov     cs:hLibModule, rax
0x180064980  test    rcx, rcx
0x180064983  jnz     loc_180064B6C
0x180064989  test    rax, rax
0x18006498c  jnz     loc_180064B7E
0x180064992  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180064997  mov     ebx, eax
0x180064999  xor     edx, edx; Val
0x18006499b  mov     r8d, 400h; Size
0x1800649a1  lea     rcx, [rbp+7D0h+var_440]; void *
0x1800649a8  call    memset_0
0x1800649ad  mov     r9d, ebx
0x1800649b0  lea     r8, aCallToLoadlibr; "Call to ::LoadLibraryEx failed with HRe"...
0x1800649b7  mov     edx, 200h; unsigned __int64
0x1800649bc  lea     rcx, [rbp+7D0h+var_440]; wchar_t *
0x1800649c3  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800649c8  lea     rax, [rbp+7D0h+var_440]
0x1800649cf  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x1800649d4  mov     [rsp+8D0h+dwFlagsAndAttributes], ebx; unsigned int
0x1800649d8  mov     [rsp+8D0h+dwCreationDisposition], 4Fh ; 'O'; unsigned int
0x1800649e0  lea     r9, word_180139126
0x1800649e7  lea     r8, aNoFilename; "(no filename)"
0x1800649ee  lea     rcx, [rbp+7D0h+pExceptionObject]; this
0x1800649f2  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800649f7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800649fe  lea     rcx, [rbp+7D0h+pExceptionObject]; pExceptionObject
0x180064a02  call    _CxxThrowException_0
0x180064a08  mov     cs:byte_1801C5100, 1
0x180064a0f  test    rbx, rbx
0x180064a12  jnz     loc_180064C25
0x180064a18  mov     rbx, [rsp+8D0h+var_880]
0x180064a1d  jmp     loc_180064810
0x180064a22  lea     rdx, aGetcurrentpack; "::GetCurrentPackageId failed"
0x180064a29  lea     rcx, [rsp+8D0h+var_874+4]
0x180064a2e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180064a33  nop
0x180064a34  lea     rdx, [rsp+8D0h+var_874+4]
0x180064a39  lea     rcx, [rbp+7D0h+pExceptionObject]
0x180064a3d  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180064a42  nop
0x180064a43  mov     rcx, rax; this
0x180064a46  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180064a4b  test    edi, edi
0x180064a4d  jg      loc_180064C17
0x180064a53  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180064a58  mov     [rsp+8D0h+dwFlagsAndAttributes], edi; unsigned int
0x180064a5c  mov     [rsp+8D0h+dwCreationDisposition], 58h ; 'X'; unsigned int
0x180064a64  lea     r9, word_180139126
0x180064a6b  lea     r8, aNoFilename; "(no filename)"
0x180064a72  lea     rcx, [rbp+7D0h+var_440]; this
0x180064a79  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180064a7e  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180064a85  lea     rcx, [rbp+7D0h+var_440]; pExceptionObject
0x180064a8c  call    _CxxThrowException_0
0x180064a92  lea     rcx, dword_1801C5380
0x180064a99  call    _Init_thread_header
0x180064a9e  cmp     cs:dword_1801C5380, 0FFFFFFFFh
0x180064aa5  jnz     loc_180064802
0x180064aab  lea     rcx, _win_dox__OpcObjectModelFactoryImplementation__CreateFileInternal____2____dynamic_atexit_destructor_for__s_hmoduleKernelBase__; void (__cdecl *)()
0x180064ab2  call    atexit
0x180064ab7  lea     rcx, dword_1801C5380
0x180064abe  call    _Init_thread_footer
0x180064ac3  jmp     loc_180064802
0x180064ac8  lea     rcx, ModuleName; "api-ms-win-core-libraryloader-l1-1-0.dl"...
0x180064acf  call    cs:__imp_GetModuleHandleW
0x180064ad5  test    rax, rax
0x180064ad8  jz      short loc_180064AEA
0x180064ada  lea     rdx, ProcName; "SetDefaultDllDirectories"
0x180064ae1  mov     rcx, rax; hModule
0x180064ae4  call    cs:__imp_GetProcAddress
0x180064aea  neg     rax
0x180064aed  sbb     r14d, r14d
0x180064af0  and     r14d, 800h
0x180064af7  mov     r8d, r14d; dwFlags
0x180064afa  xor     edx, edx; hFile
0x180064afc  lea     rcx, aApiMsWinAppmod; "api-ms-win-appmodel-runtime-l1-1-0"
0x180064b03  call    cs:__imp_LoadLibraryExW
0x180064b09  mov     rbx, rax
0x180064b0c  test    rax, rax
0x180064b0f  jnz     short loc_180064B1B
0x180064b11  mov     [rsp+8D0h+var_888], rax
0x180064b16  jmp     loc_180064A08
0x180064b1b  mov     [rsp+8D0h+var_888], rax
0x180064b20  lea     rdx, aGetcurrentpack_0; "GetCurrentPackageId"
0x180064b27  mov     rcx, rax; hModule
0x180064b2a  call    cs:__imp_GetProcAddress
0x180064b30  test    rax, rax
0x180064b33  jz      loc_180064A08
0x180064b39  mov     dword ptr [rsp+8D0h+var_890+4], 0
0x180064b41  xor     edx, edx
0x180064b43  lea     rcx, [rsp+8D0h+var_890+4]
0x180064b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b4d  mov     edi, eax
0x180064b4f  cmp     eax, 7Ah ; 'z'
0x180064b52  jz      loc_180064960
0x180064b58  cmp     eax, 3D54h
0x180064b5d  jnz     loc_180064A22
0x180064b63  mov     edi, dword ptr [rsp+8D0h+var_890]
0x180064b67  jmp     loc_180064A08
0x180064b6c  call    cs:__imp_FreeLibrary
0x180064b72  mov     rax, cs:hLibModule
0x180064b79  jmp     loc_180064989
0x180064b7e  lea     rdx, aCreatefile2; "CreateFile2"
0x180064b85  mov     rcx, rax; hModule
0x180064b88  call    cs:__imp_GetProcAddress
0x180064b8e  mov     cs:hTemplateFile, rax
0x180064b95  mov     rax, cs:hTemplateFile
0x180064b9c  test    rax, rax
0x180064b9f  jnz     short loc_180064B63
0x180064ba1  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180064ba6  mov     ebx, eax
0x180064ba8  xor     edx, edx; Val
0x180064baa  mov     r8d, 400h; Size
0x180064bb0  lea     rcx, [rbp+7D0h+var_440]; void *
0x180064bb7  call    memset_0
0x180064bbc  mov     r9d, ebx
0x180064bbf  lea     r8, aCallToGetproca; "Call to ::GetProcAddress failed with HR"...
0x180064bc6  mov     edx, 200h; unsigned __int64
0x180064bcb  lea     rcx, [rbp+7D0h+var_440]; wchar_t *
0x180064bd2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180064bd7  lea     rax, [rbp+7D0h+var_440]
0x180064bde  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180064be3  mov     [rsp+8D0h+dwFlagsAndAttributes], ebx; unsigned int
0x180064be7  mov     [rsp+8D0h+dwCreationDisposition], 52h ; 'R'; unsigned int
0x180064bef  lea     r9, word_180139126
0x180064bf6  lea     r8, aNoFilename; "(no filename)"
0x180064bfd  lea     rcx, [rbp+7D0h+pExceptionObject]; this
0x180064c01  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180064c06  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180064c0d  lea     rcx, [rbp+7D0h+pExceptionObject]; pExceptionObject
0x180064c11  call    _CxxThrowException_0
0x180064c17  movzx   edi, di
0x180064c1a  or      edi, 80070000h
0x180064c20  jmp     loc_180064A53
0x180064c25  mov     rcx, rbx; hLibModule
0x180064c28  call    cs:__imp_FreeLibrary
0x180064c2e  jmp     loc_180064A18
0x180064c33  mov     [rbp+7D0h+var_828], edi
0x180064c36  jmp     loc_18006492B
0x180064c3b  mov     dword ptr [rsp+8D0h+var_874+4], 20h ; ' '
0x180064c43  xorps   xmm0, xmm0
0x180064c46  movups  [rsp+8D0h+var_874+8], xmm0
0x180064c4b  movups  [rsp+8D0h+var_860], xmm0
0x180064c50  movzx   eax, si
0x180064c53  mov     dword ptr [rsp+8D0h+var_874+8], eax
0x180064c57  mov     eax, esi
0x180064c59  and     eax, 0FFF80000h
0x180064c5e  mov     dword ptr [rsp+8D0h+var_874+0Ch], eax
0x180064c62  bt      esi, 14h
0x180064c66  jnb     short loc_180064C74
0x180064c68  and     esi, 1F0000h
0x180064c6e  mov     [rsp+8D0h+var_864], esi
0x180064c72  jmp     short loc_180064C7C
0x180064c74  mov     [rsp+8D0h+var_864], 0
0x180064c7c  mov     qword ptr [rsp+8D0h+var_860], rbx
0x180064c81  mov     rax, cs:hTemplateFile
0x180064c88  lea     rcx, [rsp+8D0h+var_874+4]
0x180064c8d  mov     qword ptr [rsp+8D0h+dwCreationDisposition], rcx
0x180064c92  mov     r9d, edi
0x180064c95  mov     r8d, r13d
0x180064c98  mov     edx, r12d
0x180064c9b  mov     rcx, r15
0x180064c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ca3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180064ca7  jnz     loc_180064845
0x180064cad  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180064cb2  mov     ebx, eax
0x180064cb4  xor     edx, edx; Val
0x180064cb6  mov     r8d, 400h; Size
0x180064cbc  lea     rcx, [rbp+7D0h+pExceptionObject]; void *
0x180064cc0  call    memset_0
0x180064cc5  mov     r9d, ebx
0x180064cc8  lea     r8, aCallToCreatefi_0; "Call to ::CreateFile2 failed with HResu"...
0x180064ccf  mov     edx, 200h; unsigned __int64
0x180064cd4  lea     rcx, [rbp+7D0h+pExceptionObject]; wchar_t *
0x180064cd8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180064cdd  lea     rax, [rbp+7D0h+pExceptionObject]
0x180064ce1  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180064ce6  mov     [rsp+8D0h+dwFlagsAndAttributes], ebx; unsigned int
0x180064cea  mov     [rsp+8D0h+dwCreationDisposition], 7Ah ; 'z'; unsigned int
0x180064cf2  lea     r9, word_180139126
0x180064cf9  lea     r8, aNoFilename; "(no filename)"
0x180064d00  lea     rcx, [rbp+7D0h+var_440]; this
0x180064d07  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180064d0c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180064d13  lea     rcx, [rbp+7D0h+var_440]; pExceptionObject
0x180064d1a  call    _CxxThrowException_0
  ... truncated ...
```
