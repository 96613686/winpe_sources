# CMsiPath::BindImage(IMsiString const &,IMsiString const &)

- ea: `0x18021f6c0`
- end: `0x18021fca7`
- name: `?BindImage@CMsiPath@@UEAAPEAVIMsiRecord@@AEBVIMsiString@@0@Z`
- size: `1511`
- prototype: `struct IMsiRecord *__fastcall(CMsiPath *__hidden this, const struct IMsiString *, const struct IMsiString *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callees

- `0x18000c4bc`
- `0x18009436c`
- `0x180097540`
- `0x18009cdb8`
- `0x18009d06c`
- `0x1800d04fc`
- `0x1801153cc`
- `0x180121f90`
- `0x180134dac`
- `0x18014676c`
- `0x18021f6c0`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!SetFileTime` at `0x18021fbf9`
- `KERNEL32!SetFileTime` at `0x18021fbf9`
- `KERNEL32!CloseHandle` at `0x18021f9bb`
- `KERNEL32!CloseHandle` at `0x18021fc08`
- `KERNEL32!CloseHandle` at `0x18021f9bb`
- `KERNEL32!CloseHandle` at `0x18021fc08`
- `KERNEL32!GetLastError` at `0x18021faa1`
- `KERNEL32!GetLastError` at `0x18021faa1`
- `KERNEL32!GetProcAddress` at `0x18021f79b`
- `KERNEL32!GetProcAddress` at `0x18021f79b`
- `KERNEL32!CreateFileW` at `0x18021f98a`
- `KERNEL32!CreateFileW` at `0x18021fbd7`
- `KERNEL32!CreateFileW` at `0x18021f98a`
- `KERNEL32!CreateFileW` at `0x18021fbd7`
- `KERNEL32!FreeLibrary` at `0x18021f7b2`
- `KERNEL32!FreeLibrary` at `0x18021f881`
- `KERNEL32!FreeLibrary` at `0x18021fab3`
- `KERNEL32!FreeLibrary` at `0x18021fc4c`
- `KERNEL32!FreeLibrary` at `0x18021f7b2`
- `KERNEL32!FreeLibrary` at `0x18021f881`
- `KERNEL32!FreeLibrary` at `0x18021fab3`
- `KERNEL32!FreeLibrary` at `0x18021fc4c`
- `KERNEL32!GetSystemDirectoryW` at `0x18021f80c`
- `KERNEL32!GetSystemDirectoryW` at `0x18021f80c`
- `KERNEL32!GetFileTime` at `0x18021f9ac`
- `KERNEL32!GetFileTime` at `0x18021f9ac`
- `KERNEL32!SetFileAttributesW` at `0x18021f93b`
- `KERNEL32!SetFileAttributesW` at `0x18021fade`
- `KERNEL32!SetFileAttributesW` at `0x18021fc33`
- `KERNEL32!SetFileAttributesW` at `0x18021f93b`
- `KERNEL32!SetFileAttributesW` at `0x18021fade`
- `KERNEL32!SetFileAttributesW` at `0x18021fc33`

## string_xrefs

- `0x18021f73e`: `imagehlp.dll`
- `0x18021f757`: `imagehlp.dll`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiPath::BindImage(
        CMsiPath *this,
        const struct IMsiString *a2,
        const struct IMsiString *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v7)(CMsiPath *, __int64, _DWORD *, _QWORD); // rbx
  __int64 v8; // rax
  struct IMsiRecord *result; // rax
  HMODULE LibraryW; // rdi
  bool v11; // cl
  const unsigned __int16 *v12; // rax
  FARPROC ProcAddress; // r15
  __int64 v14; // rax
  __int64 (__fastcall *v15)(CMsiPath *, __int64, void **); // rbx
  __int64 v16; // rcx
  __int64 v17; // rax
  struct IMsiRecord *v18; // rbx
  struct _FILETIME *v19; // r8
  __int64 v20; // rax
  char v21; // si
  DWORD v22; // ebx
  const WCHAR *v23; // rax
  const WCHAR *v24; // rax
  HANDLE FileW; // rax
  void *v26; // rbx
  __int64 v27; // rbx
  __int64 v28; // rax
  bool v29; // cl
  const unsigned __int16 *LastError; // r14
  bool v31; // cl
  DWORD v32; // ebx
  const WCHAR *v33; // rax
  const unsigned __int16 *v34; // rax
  const unsigned __int16 *v35; // rax
  const WCHAR *v36; // rax
  HANDLE v37; // rax
  void *v38; // rbx
  DWORD v39; // ebx
  const WCHAR *v40; // rax
  void *v41; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwFileAttributes; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v45[4]; // [rsp+80h] [rbp-80h] BYREF
  char *v46; // [rsp+90h] [rbp-70h] BYREF
  int v47; // [rsp+98h] [rbp-68h]
  char v48[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 *v49; // [rsp+A8h] [rbp-58h]
  int v50; // [rsp+B0h] [rbp-50h]
  __int16 v51; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-40h]
  __int64 v53; // [rsp+C8h] [rbp-38h]
  int v54; // [rsp+D0h] [rbp-30h]
  char *v55; // [rsp+E0h] [rbp-20h] BYREF
  int v56; // [rsp+E8h] [rbp-18h]
  char v57[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 *v58; // [rsp+F8h] [rbp-8h]
  int v59; // [rsp+100h] [rbp+0h]
  __int16 v60; // [rsp+108h] [rbp+8h] BYREF
  __int64 v61; // [rsp+110h] [rbp+10h]
  __int64 v62; // [rsp+118h] [rbp+18h]
  int v63; // [rsp+120h] [rbp+20h]
  WCHAR Buffer[264]; // [rsp+130h] [rbp+30h] BYREF

  v3 = *(_QWORD *)this;
  v45[0] = 0;
  v7 = *(__int64 (__fastcall **)(CMsiPath *, __int64, _DWORD *, _QWORD))(v3 + 120);
  v8 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)a2 + 80LL))(a2);
  result = (struct IMsiRecord *)v7(this, v8, v45, 0);
  if ( !result && v45[0] )
  {
    LibraryW = (HMODULE)IsolationAwareLoadLibraryW(L"imagehlp.dll");
    if ( !LibraryW )
    {
      StartImpersonating();
      LibraryW = (HMODULE)IsolationAwareLoadLibraryW(L"imagehlp.dll");
      StopImpersonating(v11);
      if ( !LibraryW )
        goto LABEL_5;
    }
    ProcAddress = GetProcAddress(LibraryW, "BindImage");
    if ( !ProcAddress )
    {
      FreeLibrary(LibraryW);
LABEL_5:
      v12 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)a2 + 80LL))(a2);
      return PostError(2365, v12);
    }
    v43 = (*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 56LL))(this);
    MsiString::operator+=(&v43, L";");
    MsiString::operator+=(&v43, a3);
    MsiString::operator+=(&v43, L";");
    GetSystemDirectoryW(Buffer, 0x104u);
    MsiString::operator+=(&v43, Buffer);
    v14 = *(_QWORD *)this;
    v41 = &MsiString::s_NullString;
    v15 = *(__int64 (__fastcall **)(CMsiPath *, __int64, void **))(v14 + 136);
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    v16 = *(_QWORD *)a2;
    v41 = &MsiString::s_NullString;
    v17 = (*(__int64 (__fastcall **)(const struct IMsiString *))(v16 + 80))(a2);
    v18 = (struct IMsiRecord *)v15(this, v17, &v41);
    if ( v18 )
    {
      FreeLibrary(LibraryW);
LABEL_10:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      return v18;
    }
    LastWriteTime = 0;
    CMsiPath::ChkCurFileAttributes(this, 0, v19, &LastWriteTime);
    v20 = *(_QWORD *)this;
    dwFileAttributes = 0;
    v18 = (struct IMsiRecord *)(*(__int64 (__fastcall **)(CMsiPath *, DWORD *))(v20 + 520))(this, &dwFileAttributes);
    if ( v18 )
      goto LABEL_10;
    v21 = (*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 544LL))(this);
    if ( v21 )
      StartImpersonating();
    v22 = dwFileAttributes;
    if ( (dwFileAttributes & 1) != 0 )
    {
      v23 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v41 + 80LL))(v41);
      SetFileAttributesW(v23, v22 & 0xFFFFFFFE);
    }
    if ( !LastWriteTime.dwLowDateTime && !LastWriteTime.dwHighDateTime )
    {
      v24 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v41 + 80LL))(v41);
      FileW = CreateFileW(v24, 0x80000000, 3u, 0, 3u, 0x100000u, 0);
      v26 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        GetFileTime(FileW, 0, 0, &LastWriteTime);
        CloseHandle(v26);
      }
    }
    v62 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 80LL))(v43);
    v56 = 1;
    v58 = &v60;
    v55 = v57;
    v59 = 1;
    v61 = 0;
    v57[0] = 48;
    v60 = 48;
    v63 = 0;
    v27 = CConvertString::operator char const *(&v55, v57);
    v53 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v41 + 80LL))(v41);
    v49 = &v51;
    v47 = 1;
    v46 = v48;
    v50 = 1;
    v52 = 0;
    v48[0] = 48;
    v51 = 48;
    v54 = 0;
    v28 = CConvertString::operator char const *(&v46, v48);
    LODWORD(v27) = ((__int64 (__fastcall *)(__int64, __int64, _QWORD))ProcAddress)(v28, v27, 0);
    CConvertString::~CConvertString((CConvertString *)&v46);
    CConvertString::~CConvertString((CConvertString *)&v55);
    if ( !(_DWORD)v27 )
    {
      LastError = (const unsigned __int16 *)GetLastError();
      FreeLibrary(LibraryW);
      v32 = dwFileAttributes;
      if ( (dwFileAttributes & 1) != 0 )
      {
        v33 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v41 + 80LL))(v41);
        SetFileAttributesW(v33, v32);
      }
      if ( v21 )
        StopImpersonating(v31);
      if ( g_dmDiagnosticMode )
      {
        v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v41 + 80LL))(v41);
        DebugString(
          9,
          0,
          0,
          L"BindImage for file '%s' failed with last error %d",
          v34,
          LastError,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      v35 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v41 + 80LL))(v41);
      v18 = PostError(2365, v35);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      return v18;
    }
    if ( LastWriteTime.dwLowDateTime || LastWriteTime.dwHighDateTime )
    {
      v36 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v41 + 80LL))(v41);
      v37 = CreateFileW(v36, 0x40000000u, 2u, 0, 3u, 0x100000u, 0);
      v38 = v37;
      if ( v37 != (HANDLE)-1LL )
      {
        SetFileTime(v37, 0, 0, &LastWriteTime);
        CloseHandle(v38);
      }
    }
    v39 = dwFileAttributes;
    if ( (dwFileAttributes & 1) != 0 )
    {
      v40 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v41 + 80LL))(v41);
      SetFileAttributesW(v40, v39);
    }
    if ( v21 )
      StopImpersonating(v29);
    FreeLibrary(LibraryW);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18021f6c0  mov     [rsp-8+arg_18], rbx
0x18021f6c5  push    rbp
0x18021f6c6  push    rsi
0x18021f6c7  push    rdi
0x18021f6c8  push    r12
0x18021f6ca  push    r13
0x18021f6cc  push    r14
0x18021f6ce  push    r15
0x18021f6d0  lea     rbp, [rsp-250h]
0x18021f6d8  sub     rsp, 350h
0x18021f6df  mov     rax, cs:__security_cookie
0x18021f6e6  xor     rax, rsp
0x18021f6e9  mov     [rbp+280h+var_40], rax
0x18021f6f0  mov     rax, [rcx]
0x18021f6f3  mov     rsi, rcx
0x18021f6f6  xor     r13d, r13d
0x18021f6f9  mov     rcx, rdx
0x18021f6fc  mov     r12, r8
0x18021f6ff  mov     [rbp+280h+var_300], r13d
0x18021f703  mov     r14, rdx
0x18021f706  mov     rbx, [rax+78h]
0x18021f70a  mov     rax, [rdx]
0x18021f70d  mov     rax, [rax+50h]
0x18021f711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f716  mov     rdx, rax
0x18021f719  lea     r8, [rbp+280h+var_300]
0x18021f71d  mov     rax, rbx
0x18021f720  xor     r9d, r9d
0x18021f723  mov     rcx, rsi
0x18021f726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f72b  test    rax, rax
0x18021f72e  jnz     loc_18021FC7C
0x18021f734  cmp     [rbp+280h+var_300], r13d
0x18021f738  jz      loc_18021FC7C
0x18021f73e  lea     rcx, aImagehlpDll_0; "imagehlp.dll"
0x18021f745  call    IsolationAwareLoadLibraryW
0x18021f74a  mov     rdi, rax
0x18021f74d  test    rax, rax
0x18021f750  jnz     short loc_18021F791
0x18021f752  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18021f757  lea     rcx, aImagehlpDll_0; "imagehlp.dll"
0x18021f75e  call    IsolationAwareLoadLibraryW
0x18021f763  mov     rdi, rax
0x18021f766  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18021f76b  test    rdi, rdi
0x18021f76e  jnz     short loc_18021F791
0x18021f770  mov     rax, [r14]
0x18021f773  mov     rcx, r14
0x18021f776  mov     rax, [rax+50h]
0x18021f77a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f77f  mov     rdx, rax; unsigned __int16 *
0x18021f782  mov     ecx, 93Dh; int
0x18021f787  call    ?PostError@@YAPEAVIMsiRecord@@HPEBG@Z; PostError(int,ushort const *)
0x18021f78c  jmp     loc_18021FC7C
0x18021f791  lea     rdx, aBindimage_0; "BindImage"
0x18021f798  mov     rcx, rdi; hModule
0x18021f79b  call    cs:__imp_GetProcAddress
0x18021f7a2  nop     dword ptr [rax+rax+00h]
0x18021f7a7  mov     r15, rax
0x18021f7aa  test    rax, rax
0x18021f7ad  jnz     short loc_18021F7C0
0x18021f7af  mov     rcx, rdi; hLibModule
0x18021f7b2  call    cs:__imp_FreeLibrary
0x18021f7b9  nop     dword ptr [rax+rax+00h]
0x18021f7be  jmp     short loc_18021F770
0x18021f7c0  mov     rax, [rsi]
0x18021f7c3  mov     rcx, rsi
0x18021f7c6  mov     rax, [rax+38h]
0x18021f7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f7cf  lea     rdx, asc_18029A7E8; ";"
0x18021f7d6  mov     [rsp+380h+var_310], rax
0x18021f7db  lea     rcx, [rsp+380h+var_310]
0x18021f7e0  call    ??YMsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator+=(ushort const *)
0x18021f7e5  mov     rdx, r12
0x18021f7e8  lea     rcx, [rsp+380h+var_310]
0x18021f7ed  call    ??YMsiString@@QEAAAEAV0@AEBVIMsiString@@@Z; MsiString::operator+=(IMsiString const &)
0x18021f7f2  lea     rdx, asc_18029A7E8; ";"
0x18021f7f9  lea     rcx, [rsp+380h+var_310]
0x18021f7fe  call    ??YMsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator+=(ushort const *)
0x18021f803  mov     edx, 104h; uSize
0x18021f808  lea     rcx, [rbp+280h+Buffer]; lpBuffer
0x18021f80c  call    cs:__imp_GetSystemDirectoryW
0x18021f813  nop     dword ptr [rax+rax+00h]
0x18021f818  lea     rdx, [rbp+280h+Buffer]
0x18021f81c  lea     rcx, [rsp+380h+var_310]
0x18021f821  call    ??YMsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator+=(ushort const *)
0x18021f826  mov     rax, [rsi]
0x18021f829  lea     r12, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18021f830  mov     rcx, r12
0x18021f833  mov     [rsp+380h+var_320], r12
0x18021f838  mov     rbx, [rax+88h]
0x18021f83f  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18021f846  mov     rax, [rax+10h]
0x18021f84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f84f  mov     rcx, [r14]
0x18021f852  mov     [rsp+380h+var_320], r12
0x18021f857  mov     rax, [rcx+50h]
0x18021f85b  mov     rcx, r14
0x18021f85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f863  mov     rdx, rax
0x18021f866  lea     r8, [rsp+380h+var_320]
0x18021f86b  mov     rax, rbx
0x18021f86e  mov     rcx, rsi
0x18021f871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f876  mov     rbx, rax
0x18021f879  test    rax, rax
0x18021f87c  jz      short loc_18021F8BD
0x18021f87e  mov     rcx, rdi; hLibModule
0x18021f881  call    cs:__imp_FreeLibrary
0x18021f888  nop     dword ptr [rax+rax+00h]
0x18021f88d  mov     rdx, [rsp+380h+var_320]
0x18021f892  mov     rcx, [rdx]
0x18021f895  mov     rax, [rcx+10h]
0x18021f899  mov     rcx, rdx
0x18021f89c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f8a1  mov     rdx, [rsp+380h+var_310]
0x18021f8a6  mov     rcx, [rdx]
0x18021f8a9  mov     rax, [rcx+10h]
0x18021f8ad  mov     rcx, rdx
0x18021f8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f8b5  mov     rax, rbx
0x18021f8b8  jmp     loc_18021FC7C
0x18021f8bd  lea     r9, [rsp+380h+LastWriteTime]; struct _FILETIME *
0x18021f8c2  mov     qword ptr [rsp+380h+LastWriteTime.dwLowDateTime], r13
0x18021f8c7  xor     edx, edx; struct _FILETIME *
0x18021f8c9  mov     rcx, rsi; this
0x18021f8cc  call    ?ChkCurFileAttributes@CMsiPath@@IEAAXPEAU_FILETIME@@00@Z; CMsiPath::ChkCurFileAttributes(_FILETIME *,_FILETIME *,_FILETIME *)
0x18021f8d1  mov     rax, [rsi]
0x18021f8d4  lea     rdx, [rsp+380h+dwFileAttributes]
0x18021f8d9  mov     rcx, rsi
0x18021f8dc  mov     [rsp+380h+dwFileAttributes], r13d
0x18021f8e1  mov     rax, [rax+208h]
0x18021f8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f8ed  mov     rbx, rax
0x18021f8f0  test    rax, rax
0x18021f8f3  jnz     short loc_18021F88D
0x18021f8f5  mov     rax, [rsi]
0x18021f8f8  mov     rcx, rsi
0x18021f8fb  mov     rax, [rax+220h]
0x18021f902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f907  mov     sil, al
0x18021f90a  test    al, al
0x18021f90c  jz      short loc_18021F913
0x18021f90e  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18021f913  mov     ebx, [rsp+380h+dwFileAttributes]
0x18021f917  mov     r12d, 1
0x18021f91d  test    r12b, bl
0x18021f920  jz      short loc_18021F947
0x18021f922  mov     rcx, [rsp+380h+var_320]
0x18021f927  and     ebx, 0FFFFFFFEh
0x18021f92a  mov     rax, [rcx]
0x18021f92d  mov     rax, [rax+50h]
0x18021f931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f936  mov     edx, ebx; dwFileAttributes
0x18021f938  mov     rcx, rax; lpFileName
0x18021f93b  call    cs:__imp_SetFileAttributesW
0x18021f942  nop     dword ptr [rax+rax+00h]
0x18021f947  mov     ebx, 3
0x18021f94c  cmp     [rsp+380h+LastWriteTime.dwLowDateTime], r13d
0x18021f951  jnz     short loc_18021F9C7
0x18021f953  cmp     [rsp+380h+LastWriteTime.dwHighDateTime], r13d
0x18021f958  jnz     short loc_18021F9C7
0x18021f95a  mov     rcx, [rsp+380h+var_320]
0x18021f95f  mov     rax, [rcx]
0x18021f962  mov     rax, [rax+50h]
0x18021f966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f96b  mov     [rsp+380h+hTemplateFile], r13; hTemplateFile
0x18021f970  xor     r9d, r9d; lpSecurityAttributes
0x18021f973  mov     [rsp+380h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18021f97b  mov     r8d, ebx; dwShareMode
0x18021f97e  mov     edx, 80000000h; dwDesiredAccess
0x18021f983  mov     [rsp+380h+dwCreationDisposition], ebx; dwCreationDisposition
0x18021f987  mov     rcx, rax; lpFileName
0x18021f98a  call    cs:__imp_CreateFileW
0x18021f991  nop     dword ptr [rax+rax+00h]
0x18021f996  mov     rbx, rax
0x18021f999  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18021f99d  jz      short loc_18021F9C7
0x18021f99f  lea     r9, [rsp+380h+LastWriteTime]; lpLastWriteTime
0x18021f9a4  xor     r8d, r8d; lpLastAccessTime
0x18021f9a7  xor     edx, edx; lpCreationTime
0x18021f9a9  mov     rcx, rax; hFile
0x18021f9ac  call    cs:__imp_GetFileTime
0x18021f9b3  nop     dword ptr [rax+rax+00h]
0x18021f9b8  mov     rcx, rbx; hObject
0x18021f9bb  call    cs:__imp_CloseHandle
0x18021f9c2  nop     dword ptr [rax+rax+00h]
0x18021f9c7  mov     rcx, [rsp+380h+var_310]
0x18021f9cc  mov     rax, [rcx]
0x18021f9cf  mov     rax, [rax+50h]
0x18021f9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f9d8  xor     ecx, ecx
0x18021f9da  mov     [rbp+280h+var_268], rax
0x18021f9de  mov     [rbp+280h+var_290], cl
0x18021f9e1  lea     rdx, [rbp+280h+var_290]
0x18021f9e5  mov     [rbp+280h+var_278], cx
0x18021f9e9  mov     r14d, 30h ; '0'
0x18021f9ef  mov     [rbp+280h+var_298], r12d
0x18021f9f3  lea     rcx, [rbp+280h+var_278]
0x18021f9f7  mov     [rbp+280h+var_288], rcx
0x18021f9fb  lea     rcx, [rbp+280h+var_2A0]
0x18021f9ff  mov     [rbp+280h+var_2A0], rdx
0x18021fa03  mov     [rbp+280h+var_280], r12d
0x18021fa07  mov     [rbp+280h+var_270], r13
0x18021fa0b  mov     [rdx], r14b
0x18021fa0e  mov     rax, [rbp+280h+var_288]
0x18021fa12  mov     [rax], r14w
0x18021fa16  mov     [rbp+280h+var_260], r13d
0x18021fa1a  call    ??BCConvertString@@QEAAPEBDXZ; CConvertString::operator char const *(void)
0x18021fa1f  mov     rcx, [rsp+380h+var_320]
0x18021fa24  mov     rbx, rax
0x18021fa27  mov     rdx, [rcx]
0x18021fa2a  mov     rax, [rdx+50h]
0x18021fa2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021fa33  xor     ecx, ecx
0x18021fa35  mov     [rbp+280h+var_2B8], rax
0x18021fa39  mov     [rbp+280h+var_2E0], cl
0x18021fa3c  lea     rdx, [rbp+280h+var_2E0]
0x18021fa40  mov     [rbp+280h+var_2C8], cx
0x18021fa44  lea     rcx, [rbp+280h+var_2C8]
0x18021fa48  mov     [rbp+280h+var_2D8], rcx
0x18021fa4c  lea     rcx, [rbp+280h+var_2F0]
0x18021fa50  mov     [rbp+280h+var_2E8], r12d
0x18021fa54  mov     [rbp+280h+var_2F0], rdx
0x18021fa58  mov     [rbp+280h+var_2D0], r12d
0x18021fa5c  mov     [rbp+280h+var_2C0], r13
0x18021fa60  mov     [rdx], r14b
0x18021fa63  mov     rax, [rbp+280h+var_2D8]
0x18021fa67  mov     [rax], r14w
0x18021fa6b  mov     [rbp+280h+var_2B0], r13d
0x18021fa6f  call    ??BCConvertString@@QEAAPEBDXZ; CConvertString::operator char const *(void)
0x18021fa74  mov     rcx, rax
0x18021fa77  xor     r8d, r8d
0x18021fa7a  mov     rax, r15
0x18021fa7d  mov     rdx, rbx
0x18021fa80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021fa85  lea     rcx, [rbp+280h+var_2F0]; this
0x18021fa89  mov     ebx, eax
0x18021fa8b  call    ??1CConvertString@@QEAA@XZ; CConvertString::~CConvertString(void)
0x18021fa90  lea     rcx, [rbp+280h+var_2A0]; this
0x18021fa94  call    ??1CConvertString@@QEAA@XZ; CConvertString::~CConvertString(void)
0x18021fa99  test    ebx, ebx
0x18021fa9b  jnz     loc_18021FB94
0x18021faa1  call    cs:__imp_GetLastError
0x18021faa8  nop     dword ptr [rax+rax+00h]
0x18021faad  mov     rcx, rdi; hLibModule
0x18021fab0  mov     r14d, eax
0x18021fab3  call    cs:__imp_FreeLibrary
0x18021faba  nop     dword ptr [rax+rax+00h]
0x18021fabf  mov     ebx, [rsp+380h+dwFileAttributes]
0x18021fac3  test    r12b, bl
0x18021fac6  jz      short loc_18021FAEA
0x18021fac8  mov     rcx, [rsp+380h+var_320]
0x18021facd  mov     r8, [rcx]
0x18021fad0  mov     rax, [r8+50h]
0x18021fad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021fad9  mov     edx, ebx; dwFileAttributes
0x18021fadb  mov     rcx, rax; lpFileName
0x18021fade  call    cs:__imp_SetFileAttributesW
0x18021fae5  nop     dword ptr [rax+rax+00h]
0x18021faea  test    sil, sil
0x18021faed  jz      short loc_18021FAF4
0x18021faef  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18021faf4  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18021fafb  jz      short loc_18021FB51
0x18021fafd  mov     rcx, [rsp+380h+var_320]
0x18021fb02  mov     rax, [rcx]
0x18021fb05  mov     rax, [rax+50h]
0x18021fb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021fb0e  mov     [rsp+380h+var_328], r13; void *
0x18021fb13  lea     r8, aNull; "(NULL)"
0x18021fb1a  mov     [rsp+380h+var_330], r13d; unsigned int
0x18021fb1f  lea     r9, aBindimageForFi; "BindImage for file '%s' failed with las"...
0x18021fb26  mov     [rsp+380h+var_338], r8; unsigned __int16 *
0x18021fb2b  xor     edx, edx; unsigned __int16
0x18021fb2d  mov     [rsp+380h+var_340], r8; unsigned __int16 *
0x18021fb32  mov     [rsp+380h+var_348], r8; unsigned __int16 *
0x18021fb37  mov     [rsp+380h+hTemplateFile], r8; unsigned __int16 *
0x18021fb3c  xor     r8d, r8d; int
0x18021fb3f  mov     qword ptr [rsp+380h+dwFlagsAndAttributes], r14; unsigned __int16 *
0x18021fb44  lea     ecx, [rdx+9]; int
0x18021fb47  mov     qword ptr [rsp+380h+dwCreationDisposition], rax; unsigned __int16 *
0x18021fb4c  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18021fb51  mov     rcx, [rsp+380h+var_320]
0x18021fb56  mov     rax, [rcx]
0x18021fb59  mov     rax, [rax+50h]
0x18021fb5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021fb62  mov     rdx, rax; unsigned __int16 *
0x18021fb65  mov     ecx, 93Dh; int
0x18021fb6a  call    ?PostError@@YAPEAVIMsiRecord@@HPEBG@Z; PostError(int,ushort const *)
0x18021fb6f  mov     rcx, [rsp+380h+var_320]
0x18021fb74  mov     rbx, rax
0x18021fb77  mov     rdx, [rcx]
0x18021fb7a  mov     rax, [rdx+10h]
0x18021fb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021fb83  mov     rcx, [rsp+380h+var_310]
0x18021fb88  mov     rdx, [rcx]
0x18021fb8b  mov     rax, [rdx+10h]
0x18021fb8f  jmp     loc_18021F8B0
0x18021fb94  cmp     [rsp+380h+LastWriteTime.dwLowDateTime], r13d
  ... truncated ...
```
