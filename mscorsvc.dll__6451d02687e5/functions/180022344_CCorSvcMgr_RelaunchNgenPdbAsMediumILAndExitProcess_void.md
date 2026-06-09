# CCorSvcMgr::RelaunchNgenPdbAsMediumILAndExitProcess(void)

- ea: `0x180022344`
- end: `0x180022842`
- name: `?RelaunchNgenPdbAsMediumILAndExitProcess@CCorSvcMgr@@AEAAXXZ`
- size: `1278`
- prototype: `void __fastcall __noreturn(CCorSvcMgr *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002142c`

## callees

- `0x180001de0`
- `0x180001e8c`
- `0x1800020f0`
- `0x180022344`
- `0x180022844`
- `0x18002d624`
- `0x18002e540`
- `0x180030ab8`
- `0x180030d84`
- `0x180032ef4`
- `0x180032f44`
- `0x18003303c`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180022392`
- `KERNEL32!LoadLibraryExW` at `0x180022392`
- `KERNEL32!GetCommandLineW` at `0x1800223d3`
- `KERNEL32!GetCommandLineW` at `0x1800223d3`
- `KERNEL32!GetExitCodeProcess` at `0x1800227ef`
- `KERNEL32!GetExitCodeProcess` at `0x1800227ef`
- `KERNEL32!ExitProcess` at `0x180022813`
- `KERNEL32!ExitProcess` at `0x180022832`
- `KERNEL32!ExitProcess` at `0x180022813`
- `KERNEL32!ExitProcess` at `0x180022832`
- `KERNEL32!WaitForSingleObject` at `0x1800227d0`
- `KERNEL32!WaitForSingleObject` at `0x1800227d0`
- `KERNEL32!CloseHandle` at `0x180022667`
- `KERNEL32!CloseHandle` at `0x180022667`
- `KERNEL32!GetLastError` at `0x1800227f9`
- `KERNEL32!GetLastError` at `0x1800227f9`
- `KERNEL32!GetProcAddress` at `0x1800223c1`
- `KERNEL32!GetProcAddress` at `0x1800223c1`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1800224d2`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1800224f0`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002250e`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1800224d2`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1800224f0`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002250e`

## string_xrefs

- `0x18002238b`: `shell32.dll`
- `0x1800223b7`: `CommandLineToArgvW`
- `0x180022616`: `Relaunching %s createpdb as medium integrity level...\n`
- `0x1800227d6`: `Medium integrity level ngen has completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
void __fastcall __noreturn CCorSvcMgr::RelaunchNgenPdbAsMediumILAndExitProcess(unsigned __int16 **this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  LPWSTR CommandLineW; // rax
  __int64 v5; // rbx
  int v6; // esi
  const wchar_t **v7; // rbx
  char v8; // cl
  unsigned int v9; // ebx
  char v10; // r14
  unsigned int v11; // ebx
  __int64 v12; // rdx
  int v13; // edx
  int v14; // ecx
  int v15; // eax
  char *v16; // rax
  Logger *v17; // rbx
  DWORD LastError; // eax
  unsigned int v19; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v20; // [rsp+3Ch] [rbp-CCh]
  __int64 v21; // [rsp+40h] [rbp-C8h]
  LPWSTR lpCommandLine; // [rsp+48h] [rbp-C0h]
  int v23; // [rsp+50h] [rbp-B8h]
  int v24; // [rsp+54h] [rbp-B4h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-B0h] BYREF
  int v26; // [rsp+60h] [rbp-A8h]
  DWORD ExitCode[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+70h] [rbp-98h] BYREF
  int v29; // [rsp+78h] [rbp-90h]
  __int64 v30[2]; // [rsp+80h] [rbp-88h] BYREF
  BOOL v31; // [rsp+90h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-70h]
  BOOL v33; // [rsp+A0h] [rbp-68h]
  __int64 *v34; // [rsp+A8h] [rbp-60h]
  HANDLE *p_hObject; // [rsp+B0h] [rbp-58h]
  _DWORD v36[4]; // [rsp+B8h] [rbp-50h] BYREF
  __int16 *v37; // [rsp+C8h] [rbp-40h]
  __int16 v38; // [rsp+D0h] [rbp-38h] BYREF

  v23 = 0;
  Library = LoadLibraryExW(L"shell32.dll", 0, 0);
  v30[1] = (__int64)Library;
  v31 = Library != 0;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "CommandLineToArgvW");
    if ( ProcAddress )
    {
      CommandLineW = GetCommandLineW();
      if ( CommandLineW )
      {
        v24 = 0;
        v5 = ((__int64 (__fastcall *)(LPWSTR, int *))ProcAddress)(CommandLineW, &v24);
        v32 = v5;
        v33 = v5 != 0;
        if ( !v5 )
          CCorSvcMgr::WarnUserAboutIntegrityLevelAndThrow((CCorSvcMgr *)this);
        *(_QWORD *)&v36[1] = 512;
        v37 = &v38;
        v36[0] = 2;
        v38 = 0;
        Helpers::GetVersionDirectoryPathFromCurrentModulePath((struct SString *)v36);
        SString::Append((SString *)v36, L"\\ngen.exe");
        v19 = 2;
        v20 = 2;
        LODWORD(v21) = 16;
        lpCommandLine = (LPWSTR)&SString::s_EmptyBuffer;
        SString::Set((SString *)&v19, L"\"");
        SString::Append((SString *)&v19, (const struct SString *)v36);
        SString::Append((SString *)&v19, L"\" ");
        v6 = 1;
        if ( v24 > 1 )
        {
          v7 = (const wchar_t **)(v5 + 8);
          do
          {
            if ( !_wcsnicmp(*v7, L"/Package:", 9u)
              || !_wcsnicmp(*v7, L"/LocalAppData:", 0xEu)
              || !_wcsnicmp(*v7, L"/NoRoot", 7u) )
            {
              CCorSvcMgr::WarnUserAboutIntegrityLevelAndThrow((CCorSvcMgr *)this);
            }
            SString::Append((SString *)&v19, L" ");
            SString::Append((SString *)&v19, L"\"");
            SString::Append((SString *)&v19, (unsigned __int16 *)*v7);
            SString::Append((SString *)&v19, L"\"");
            ++v6;
            ++v7;
          }
          while ( v6 < v24 );
        }
        SString::Append((SString *)&v19, L" ");
        SString::Append((SString *)&v19, L"/Package:");
        SString::Append((SString *)&v19, this[39]);
        SString::Append((SString *)&v19, L" ");
        SString::Append((SString *)&v19, L"/LocalAppData:");
        SString::Append((SString *)&v19, L"\"");
        SString::Append((SString *)&v19, this[41]);
        SString::Append((SString *)&v19, L"\"");
        SString::Append((SString *)&v19, L" ");
        SString::Append((SString *)&v19, L"/NoRoot");
        SString::ConvertToUnicode((SString *)v36);
        Logger::Printf((Logger *)(this + 26), L"Relaunching %s createpdb as medium integrity level...\n", v37);
        v26 = 0;
        v29 = 0;
        v34 = &v28;
        v28 = -1;
        p_hObject = &hObject;
        hObject = (HANDLE)-1LL;
        v23 = 3;
        v8 = v21;
        if ( (v21 & 2) != 0 && ((v21 & 7) != 7 || SString::s_IsANSIMultibyte) )
        {
          if ( !(unsigned int)SString::ScanASCII((SString *)&v19) )
            SString::ConvertToUnicode((SString *)&v19);
          v8 = v21;
        }
        v9 = v19 >> ((v8 & 1) == 0);
        SString::Resize(&v19, v9 - 1, 4);
        v10 = v21;
        v11 = v9 << ((v21 & 1) == 0);
        v12 = v20;
        if ( v11 > v20 )
        {
          SBuffer::ReallocateBuffer(&v19, v11, 1);
          v10 = v21;
          v12 = v20;
        }
        v19 = v11;
        if ( (v10 & 0x10) != 0 )
        {
          SBuffer::ReallocateBuffer(&v19, v12, 1);
          v10 = v21;
          v11 = v19;
        }
        v13 = CorCreateNGenProcess(0, lpCommandLine, (__int64)this[39], &hObject, (HANDLE *)&v28, (DWORD *)v30);
        v23 = 1;
        v14 = v26;
        if ( hObject != (HANDLE)-1LL )
          v14 = 1;
        v26 = v14;
        v23 = 0;
        v15 = v29;
        if ( v28 != -1 )
          v15 = 1;
        v29 = v15;
        v16 = (char *)lpCommandLine + v11;
        if ( (v10 & 1) != 0 )
          *(v16 - 1) = 0;
        else
          *((_WORD *)v16 - 1) = 0;
        v17 = (Logger *)(this + 26);
        if ( !v13 )
        {
          Logger::Printf((Logger *)(this + 26), L"Relaunch failed.\n");
          CCorSvcMgr::WarnUserAboutIntegrityLevelAndThrow((CCorSvcMgr *)this);
        }
        WaitForSingleObject(hObject, 0xFFFFFFFF);
        Logger::Printf(v17, L"Medium integrity level ngen has completed");
        if ( !GetExitCodeProcess(hObject, ExitCode) )
        {
          LastError = GetLastError();
          Logger::Printf(v17, L"; cannot determine exit code, error %d.  Returning -1.\n", LastError);
          ExitProcess(0xFFFFFFFF);
        }
        Logger::Printf(v17, L" with exit code %d.\n", ExitCode[0]);
        ExitProcess(ExitCode[0]);
      }
    }
  }
  CCorSvcMgr::WarnUserAboutIntegrityLevelAndThrow((CCorSvcMgr *)this);
}

```

## disassembly

```asm
0x180022344  mov     rax, rsp
0x180022347  mov     [rax+10h], rbx
0x18002234b  mov     [rax+18h], rsi
0x18002234f  mov     [rax+20h], rdi
0x180022353  push    rbp
0x180022354  push    r12
0x180022356  push    r13
0x180022358  push    r14
0x18002235a  push    r15
0x18002235c  lea     rbp, [rax-208h]
0x180022363  sub     rsp, 2E0h
0x18002236a  mov     rax, cs:__security_cookie
0x180022371  xor     rax, rsp
0x180022374  mov     [rbp+200h+var_30], rax
0x18002237b  mov     rdi, rcx
0x18002237e  xor     r15d, r15d
0x180022381  mov     dword ptr [rsp+300h+var_2B8], r15d
0x180022386  xor     r8d, r8d; dwFlags
0x180022389  xor     edx, edx; hFile
0x18002238b  lea     rcx, aShell32Dll; "shell32.dll"
0x180022392  call    cs:__imp_LoadLibraryExW
0x180022398  mov     [rbp+200h+var_280], rax
0x18002239c  mov     [rbp+200h+var_278], r15d
0x1800223a0  mov     ecx, r15d
0x1800223a3  lea     r12d, [r15+1]
0x1800223a7  test    rax, rax
0x1800223aa  cmovnz  ecx, r12d
0x1800223ae  mov     [rbp+200h+var_278], ecx
0x1800223b1  jz      loc_180022839
0x1800223b7  lea     rdx, aCommandlinetoa; "CommandLineToArgvW"
0x1800223be  mov     rcx, rax; hModule
0x1800223c1  call    cs:__imp_GetProcAddress
0x1800223c7  mov     rbx, rax
0x1800223ca  test    rax, rax
0x1800223cd  jz      loc_180022839
0x1800223d3  call    cs:__imp_GetCommandLineW
0x1800223d9  test    rax, rax
0x1800223dc  jz      loc_180022839
0x1800223e2  mov     dword ptr [rsp+300h+var_2B8+4], r15d
0x1800223e7  lea     rdx, [rsp+300h+var_2B8+4]
0x1800223ec  mov     rcx, rax
0x1800223ef  mov     rax, rbx
0x1800223f2  call    cs:__guard_dispatch_icall_fptr
0x1800223f8  mov     rbx, rax
0x1800223fb  mov     [rbp+200h+var_270], rax
0x1800223ff  mov     [rbp+200h+var_268], r15d
0x180022403  mov     ecx, r15d
0x180022406  test    rax, rax
0x180022409  cmovnz  ecx, r12d
0x18002240d  mov     [rbp+200h+var_268], ecx
0x180022410  jnz     short loc_18002241B
0x180022412  mov     rcx, rdi; this
0x180022415  call    ?WarnUserAboutIntegrityLevelAndThrow@CCorSvcMgr@@AEAAXXZ; CCorSvcMgr::WarnUserAboutIntegrityLevelAndThrow(void)
0x18002241b  mov     qword ptr [rbp+200h+var_250], r15
0x18002241f  mov     qword ptr [rbp+200h+var_250+4], 200h
0x180022427  mov     [rbp+200h+var_240], r15
0x18002242b  lea     rax, [rbp+200h+var_238]
0x18002242f  mov     [rbp+200h+var_240], rax
0x180022433  mov     r14d, 2
0x180022439  mov     [rbp+200h+var_250], r14d
0x18002243d  mov     rax, [rbp+200h+var_240]
0x180022441  mov     [rax], r15w
0x180022445  lea     rcx, [rbp+200h+var_250]; this
0x180022449  call    ?GetVersionDirectoryPathFromCurrentModulePath@Helpers@@SAXAEAVSString@@@Z; Helpers::GetVersionDirectoryPathFromCurrentModulePath(SString &)
0x18002244e  lea     rdx, aNgenExe; "\\ngen.exe"
0x180022455  lea     rcx, [rbp+200h+var_250]; this
0x180022459  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002245e  mov     [rsp+300h+var_2D0], r14d
0x180022463  mov     [rsp+300h+var_2CC], r14d
0x180022468  mov     dword ptr [rsp+300h+var_2C8], 10h
0x180022470  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180022477  mov     [rsp+300h+lpCommandLine], rax
0x18002247c  lea     r13, asc_18005A60C; "\""
0x180022483  mov     rdx, r13; unsigned __int16 *
0x180022486  lea     rcx, [rsp+300h+var_2D0]; this
0x18002248b  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180022490  nop
0x180022491  lea     rdx, [rbp+200h+var_250]; struct SString *
0x180022495  lea     rcx, [rsp+300h+var_2D0]; this
0x18002249a  call    ?Append@SString@@QEAAXAEBV1@@Z; SString::Append(SString const &)
0x18002249f  lea     rdx, asc_18005A610; "\" "
0x1800224a6  lea     rcx, [rsp+300h+var_2D0]; this
0x1800224ab  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800224b0  mov     esi, r12d
0x1800224b3  cmp     dword ptr [rsp+300h+var_2B8+4], r12d
0x1800224b8  jle     loc_180022565
0x1800224be  add     rbx, 8
0x1800224c2  mov     r8d, 9; MaxCount
0x1800224c8  lea     rdx, aPackage_0; "/Package:"
0x1800224cf  mov     rcx, [rbx]; String1
0x1800224d2  call    cs:__imp__wcsnicmp
0x1800224d8  test    eax, eax
0x1800224da  jz      loc_180022795
0x1800224e0  mov     r8d, 0Eh; MaxCount
0x1800224e6  lea     rdx, aLocalappdata_0; "/LocalAppData:"
0x1800224ed  mov     rcx, [rbx]; String1
0x1800224f0  call    cs:__imp__wcsnicmp
0x1800224f6  test    eax, eax
0x1800224f8  jz      loc_180022795
0x1800224fe  mov     r8d, 7; MaxCount
0x180022504  lea     rdx, aNoroot_0; "/NoRoot"
0x18002250b  mov     rcx, [rbx]; String1
0x18002250e  call    cs:__imp__wcsnicmp
0x180022514  test    eax, eax
0x180022516  jz      loc_180022795
0x18002251c  lea     rdx, asc_180055D68; " "
0x180022523  lea     rcx, [rsp+300h+var_2D0]; this
0x180022528  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002252d  mov     rdx, r13; unsigned __int16 *
0x180022530  lea     rcx, [rsp+300h+var_2D0]; this
0x180022535  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002253a  mov     rdx, [rbx]; unsigned __int16 *
0x18002253d  lea     rcx, [rsp+300h+var_2D0]; this
0x180022542  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180022547  mov     rdx, r13; unsigned __int16 *
0x18002254a  lea     rcx, [rsp+300h+var_2D0]; this
0x18002254f  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180022554  add     esi, r12d
0x180022557  add     rbx, 8
0x18002255b  cmp     esi, dword ptr [rsp+300h+var_2B8+4]
0x18002255f  jl      loc_1800224C2
0x180022565  lea     rbx, asc_180055D68; " "
0x18002256c  mov     rdx, rbx; unsigned __int16 *
0x18002256f  lea     rcx, [rsp+300h+var_2D0]; this
0x180022574  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180022579  lea     rdx, aPackage_0; "/Package:"
0x180022580  lea     rcx, [rsp+300h+var_2D0]; this
0x180022585  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002258a  mov     rdx, [rdi+138h]; unsigned __int16 *
0x180022591  lea     rcx, [rsp+300h+var_2D0]; this
0x180022596  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002259b  mov     rdx, rbx; unsigned __int16 *
0x18002259e  lea     rcx, [rsp+300h+var_2D0]; this
0x1800225a3  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800225a8  lea     rdx, aLocalappdata_0; "/LocalAppData:"
0x1800225af  lea     rcx, [rsp+300h+var_2D0]; this
0x1800225b4  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800225b9  mov     rdx, r13; unsigned __int16 *
0x1800225bc  lea     rcx, [rsp+300h+var_2D0]; this
0x1800225c1  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800225c6  mov     rdx, [rdi+148h]; unsigned __int16 *
0x1800225cd  lea     rcx, [rsp+300h+var_2D0]; this
0x1800225d2  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800225d7  mov     rdx, r13; unsigned __int16 *
0x1800225da  lea     rcx, [rsp+300h+var_2D0]; this
0x1800225df  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800225e4  mov     rdx, rbx; unsigned __int16 *
0x1800225e7  lea     rcx, [rsp+300h+var_2D0]; this
0x1800225ec  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800225f1  lea     rdx, aNoroot_0; "/NoRoot"
0x1800225f8  lea     rcx, [rsp+300h+var_2D0]; this
0x1800225fd  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180022602  lea     rcx, [rbp+200h+var_250]; this
0x180022606  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002260b  lea     rcx, [rdi+0D0h]; this
0x180022612  mov     r8, [rbp+200h+var_240]
0x180022616  lea     rdx, aRelaunchingSCr; "Relaunching %s createpdb as medium inte"...
0x18002261d  call    ?Printf@Logger@@QEAAXPEBGZZ; Logger::Printf(ushort const *,...)
0x180022622  or      r13, 0FFFFFFFFFFFFFFFFh
0x180022626  mov     [rsp+300h+hObject], r13
0x18002262b  mov     [rsp+300h+var_2A8], r15d
0x180022630  mov     [rsp+300h+var_298], r13
0x180022635  mov     [rsp+300h+var_290], r15d
0x18002263a  lea     rax, [rsp+300h+var_298]
0x18002263f  mov     [rbp+200h+var_260], rax
0x180022643  mov     [rsp+300h+var_298], r13
0x180022648  mov     dword ptr [rsp+300h+var_2B8], r12d
0x18002264d  lea     rax, [rsp+300h+hObject]
0x180022652  mov     [rbp+200h+var_258], rax
0x180022656  cmp     [rsp+300h+var_2A8], r15d
0x18002265b  jz      short loc_180022672
0x18002265d  mov     rcx, [rsp+300h+hObject]; hObject
0x180022662  test    rcx, rcx
0x180022665  jz      short loc_18002266D
0x180022667  call    cs:__imp_CloseHandle
0x18002266d  mov     [rsp+300h+var_2A8], r15d
0x180022672  mov     [rsp+300h+hObject], r13
0x180022677  mov     esi, 3
0x18002267c  mov     dword ptr [rsp+300h+var_2B8], esi
0x180022680  mov     ecx, dword ptr [rsp+300h+var_2C8]
0x180022684  test    r14b, cl
0x180022687  jz      short loc_1800226B7
0x180022689  mov     eax, ecx
0x18002268b  and     eax, 7
0x18002268e  cmp     al, 7
0x180022690  jnz     short loc_18002269B
0x180022692  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, r15d; int SString::s_IsANSIMultibyte
0x180022699  jz      short loc_1800226B7
0x18002269b  lea     rcx, [rsp+300h+var_2D0]; this
0x1800226a0  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x1800226a5  test    eax, eax
0x1800226a7  jnz     short loc_1800226B3
0x1800226a9  lea     rcx, [rsp+300h+var_2D0]; this
0x1800226ae  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800226b3  mov     ecx, dword ptr [rsp+300h+var_2C8]
0x1800226b7  not     ecx
0x1800226b9  and     ecx, r12d
0x1800226bc  mov     ebx, [rsp+300h+var_2D0]
0x1800226c0  shr     ebx, cl
0x1800226c2  lea     edx, [rbx-1]
0x1800226c5  xor     r9d, r9d
0x1800226c8  lea     r8d, [r9+4]
0x1800226cc  lea     rcx, [rsp+300h+var_2D0]
0x1800226d1  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x1800226d6  mov     r14d, dword ptr [rsp+300h+var_2C8]
0x1800226db  mov     ecx, r14d
0x1800226de  not     ecx
0x1800226e0  and     ecx, r12d
0x1800226e3  shl     ebx, cl
0x1800226e5  mov     edx, [rsp+300h+var_2CC]
0x1800226e9  cmp     ebx, edx
0x1800226eb  jbe     short loc_180022705
0x1800226ed  mov     r8d, r12d
0x1800226f0  mov     edx, ebx
0x1800226f2  lea     rcx, [rsp+300h+var_2D0]
0x1800226f7  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x1800226fc  mov     r14d, dword ptr [rsp+300h+var_2C8]
0x180022701  mov     edx, [rsp+300h+var_2CC]
0x180022705  mov     [rsp+300h+var_2D0], ebx
0x180022709  test    r14b, 10h
0x18002270d  jz      short loc_180022725
0x18002270f  mov     r8d, r12d
0x180022712  lea     rcx, [rsp+300h+var_2D0]
0x180022717  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18002271c  mov     r14d, dword ptr [rsp+300h+var_2C8]
0x180022721  mov     ebx, [rsp+300h+var_2D0]
0x180022725  lea     rax, [rsp+300h+var_288]
0x18002272a  mov     [rsp+300h+var_2D8], rax; __int64
0x18002272f  lea     rax, [rsp+300h+var_298]
0x180022734  mov     [rsp+300h+var_2E0], rax; __int64
0x180022739  lea     r9, [rsp+300h+hObject]
0x18002273e  mov     r8, [rdi+138h]
0x180022745  mov     rdx, [rsp+300h+lpCommandLine]; lpCommandLine
0x18002274a  xor     ecx, ecx; lpApplicationName
0x18002274c  call    CorCreateNGenProcess
0x180022751  mov     edx, eax
0x180022753  and     esi, 0FFFFFFFDh
0x180022756  mov     dword ptr [rsp+300h+var_2B8], esi
0x18002275a  mov     ecx, [rsp+300h+var_2A8]
0x18002275e  cmp     [rsp+300h+hObject], r13
0x180022763  cmovnz  ecx, r12d
0x180022767  mov     [rsp+300h+var_2A8], ecx
0x18002276b  and     esi, 0FFFFFFFEh
0x18002276e  mov     dword ptr [rsp+300h+var_2B8], esi
0x180022772  mov     eax, [rsp+300h+var_290]
0x180022776  cmp     [rsp+300h+var_298], r13
0x18002277b  cmovnz  eax, r12d
0x18002277f  mov     [rsp+300h+var_290], eax
0x180022783  mov     eax, ebx
0x180022785  add     rax, [rsp+300h+lpCommandLine]
0x18002278a  test    r12b, r14b
0x18002278d  jz      short loc_18002279E
0x18002278f  mov     [rax-1], r15b
0x180022793  jmp     short loc_1800227A3
0x180022795  mov     rcx, rdi; this
0x180022798  call    ?WarnUserAboutIntegrityLevelAndThrow@CCorSvcMgr@@AEAAXXZ; CCorSvcMgr::WarnUserAboutIntegrityLevelAndThrow(void)
0x18002279e  mov     [rax-2], r15w
0x1800227a3  lea     rbx, [rdi+0D0h]
0x1800227aa  test    edx, edx
0x1800227ac  jnz     short loc_1800227C6
0x1800227ae  lea     rdx, aRelaunchFailed; "Relaunch failed.\n"
0x1800227b5  mov     rcx, rbx; this
0x1800227b8  call    ?Printf@Logger@@QEAAXPEBGZZ; Logger::Printf(ushort const *,...)
0x1800227bd  mov     rcx, rdi; this
0x1800227c0  call    ?WarnUserAboutIntegrityLevelAndThrow@CCorSvcMgr@@AEAAXXZ; CCorSvcMgr::WarnUserAboutIntegrityLevelAndThrow(void)
0x1800227c6  or      edi, 0FFFFFFFFh
0x1800227c9  mov     edx, edi; dwMilliseconds
0x1800227cb  mov     rcx, [rsp+300h+hObject]; hHandle
0x1800227d0  call    cs:__imp_WaitForSingleObject
0x1800227d6  lea     rdx, aMediumIntegrit; "Medium integrity level ngen has complet"...
0x1800227dd  mov     rcx, rbx; this
0x1800227e0  call    ?Printf@Logger@@QEAAXPEBGZZ; Logger::Printf(ushort const *,...)
0x1800227e5  lea     rdx, [rsp+300h+ExitCode]; lpExitCode
0x1800227ea  mov     rcx, [rsp+300h+hObject]; hProcess
0x1800227ef  call    cs:__imp_GetExitCodeProcess
0x1800227f5  test    eax, eax
0x1800227f7  jnz     short loc_18002281A
0x1800227f9  call    cs:__imp_GetLastError
0x1800227ff  mov     r8d, eax
0x180022802  lea     rdx, aCannotDetermin; "; cannot determine exit code, error %d."...
0x180022809  mov     rcx, rbx; this
0x18002280c  call    ?Printf@Logger@@QEAAXPEBGZZ; Logger::Printf(ushort const *,...)
0x180022811  mov     ecx, edi; uExitCode
0x180022813  call    cs:__imp_ExitProcess
0x18002281a  mov     r8d, [rsp+300h+ExitCode]
0x18002281f  lea     rdx, aWithExitCodeD; " with exit code %d.\n"
0x180022826  mov     rcx, rbx; this
0x180022829  call    ?Printf@Logger@@QEAAXPEBGZZ; Logger::Printf(ushort const *,...)
0x18002282e  mov     ecx, [rsp+300h+ExitCode]; uExitCode
0x180022832  call    cs:__imp_ExitProcess
0x180022839  mov     rcx, rdi; this
0x18002283c  call    ?WarnUserAboutIntegrityLevelAndThrow@CCorSvcMgr@@AEAAXXZ; CCorSvcMgr::WarnUserAboutIntegrityLevelAndThrow(void)
```
