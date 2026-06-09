# CMsiPath::BindImage(IMsiString const &,IMsiString const &)

- ea: `0x180215cd0`
- end: `0x180216256`
- name: `?BindImage@CMsiPath@@UEAAPEAVIMsiRecord@@AEBVIMsiString@@0@Z`
- size: `1414`
- prototype: `struct IMsiRecord *__fastcall(CMsiPath *__hidden this, const struct IMsiString *, const struct IMsiString *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callees

- `0x180025a18`
- `0x18006e484`
- `0x1800713d0`
- `0x18007ed04`
- `0x180083178`
- `0x1800833ec`
- `0x1800c2854`
- `0x18011c474`
- `0x18012b6ac`
- `0x18014148c`
- `0x180215cd0`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!SetFileTime` at `0x1802161c1`
- `KERNEL32!SetFileTime` at `0x1802161c1`
- `KERNEL32!CloseHandle` at `0x180215fa1`
- `KERNEL32!CloseHandle` at `0x1802161ca`
- `KERNEL32!CloseHandle` at `0x180215fa1`
- `KERNEL32!CloseHandle` at `0x1802161ca`
- `KERNEL32!GetLastError` at `0x180216081`
- `KERNEL32!GetLastError` at `0x180216081`
- `KERNEL32!GetProcAddress` at `0x180215dab`
- `KERNEL32!GetProcAddress` at `0x180215dab`
- `KERNEL32!CreateFileW` at `0x180215f7c`
- `KERNEL32!CreateFileW` at `0x1802161a5`
- `KERNEL32!CreateFileW` at `0x180215f7c`
- `KERNEL32!CreateFileW` at `0x1802161a5`
- `KERNEL32!FreeLibrary` at `0x180215dbc`
- `KERNEL32!FreeLibrary` at `0x180215e7f`
- `KERNEL32!FreeLibrary` at `0x18021608d`
- `KERNEL32!FreeLibrary` at `0x180216202`
- `KERNEL32!FreeLibrary` at `0x180215dbc`
- `KERNEL32!FreeLibrary` at `0x180215e7f`
- `KERNEL32!FreeLibrary` at `0x18021608d`
- `KERNEL32!FreeLibrary` at `0x180216202`
- `KERNEL32!GetSystemDirectoryW` at `0x180215e10`
- `KERNEL32!GetSystemDirectoryW` at `0x180215e10`
- `KERNEL32!GetFileTime` at `0x180215f98`
- `KERNEL32!GetFileTime` at `0x180215f98`
- `KERNEL32!SetFileAttributesW` at `0x180215f33`
- `KERNEL32!SetFileAttributesW` at `0x1802160b2`
- `KERNEL32!SetFileAttributesW` at `0x1802161ef`
- `KERNEL32!SetFileAttributesW` at `0x180215f33`
- `KERNEL32!SetFileAttributesW` at `0x1802160b2`
- `KERNEL32!SetFileAttributesW` at `0x1802161ef`

## string_xrefs

- `0x180215d4e`: `imagehlp.dll`
- `0x180215d67`: `imagehlp.dll`

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
0x180215cd0  mov     [rsp-8+arg_18], rbx
0x180215cd5  push    rbp
0x180215cd6  push    rsi
0x180215cd7  push    rdi
0x180215cd8  push    r12
0x180215cda  push    r13
0x180215cdc  push    r14
0x180215cde  push    r15
0x180215ce0  lea     rbp, [rsp-250h]
0x180215ce8  sub     rsp, 350h
0x180215cef  mov     rax, cs:__security_cookie
0x180215cf6  xor     rax, rsp
0x180215cf9  mov     [rbp+280h+var_40], rax
0x180215d00  mov     rax, [rcx]
0x180215d03  mov     rsi, rcx
0x180215d06  xor     r13d, r13d
0x180215d09  mov     rcx, rdx
0x180215d0c  mov     r12, r8
0x180215d0f  mov     [rbp+280h+var_300], r13d
0x180215d13  mov     r14, rdx
0x180215d16  mov     rbx, [rax+78h]
0x180215d1a  mov     rax, [rdx]
0x180215d1d  mov     rax, [rax+50h]
0x180215d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215d26  mov     rdx, rax
0x180215d29  lea     r8, [rbp+280h+var_300]
0x180215d2d  mov     rax, rbx
0x180215d30  xor     r9d, r9d
0x180215d33  mov     rcx, rsi
0x180215d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215d3b  test    rax, rax
0x180215d3e  jnz     loc_18021622C
0x180215d44  cmp     [rbp+280h+var_300], r13d
0x180215d48  jz      loc_18021622C
0x180215d4e  lea     rcx, aImagehlpDll_0; "imagehlp.dll"
0x180215d55  call    IsolationAwareLoadLibraryW
0x180215d5a  mov     rdi, rax
0x180215d5d  test    rax, rax
0x180215d60  jnz     short loc_180215DA1
0x180215d62  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180215d67  lea     rcx, aImagehlpDll_0; "imagehlp.dll"
0x180215d6e  call    IsolationAwareLoadLibraryW
0x180215d73  mov     rdi, rax
0x180215d76  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180215d7b  test    rdi, rdi
0x180215d7e  jnz     short loc_180215DA1
0x180215d80  mov     rax, [r14]
0x180215d83  mov     rcx, r14
0x180215d86  mov     rax, [rax+50h]
0x180215d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215d8f  mov     rdx, rax; unsigned __int16 *
0x180215d92  mov     ecx, 93Dh; int
0x180215d97  call    ?PostError@@YAPEAVIMsiRecord@@HPEBG@Z; PostError(int,ushort const *)
0x180215d9c  jmp     loc_18021622C
0x180215da1  lea     rdx, aBindimage_0; "BindImage"
0x180215da8  mov     rcx, rdi; hModule
0x180215dab  call    cs:__imp_GetProcAddress
0x180215db1  mov     r15, rax
0x180215db4  test    rax, rax
0x180215db7  jnz     short loc_180215DC4
0x180215db9  mov     rcx, rdi; hLibModule
0x180215dbc  call    cs:__imp_FreeLibrary
0x180215dc2  jmp     short loc_180215D80
0x180215dc4  mov     rax, [rsi]
0x180215dc7  mov     rcx, rsi
0x180215dca  mov     rax, [rax+38h]
0x180215dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215dd3  lea     rdx, asc_180290858; ";"
0x180215dda  mov     [rsp+380h+var_310], rax
0x180215ddf  lea     rcx, [rsp+380h+var_310]
0x180215de4  call    ??YMsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator+=(ushort const *)
0x180215de9  mov     rdx, r12
0x180215dec  lea     rcx, [rsp+380h+var_310]
0x180215df1  call    ??YMsiString@@QEAAAEAV0@AEBVIMsiString@@@Z; MsiString::operator+=(IMsiString const &)
0x180215df6  lea     rdx, asc_180290858; ";"
0x180215dfd  lea     rcx, [rsp+380h+var_310]
0x180215e02  call    ??YMsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator+=(ushort const *)
0x180215e07  mov     edx, 104h; uSize
0x180215e0c  lea     rcx, [rbp+280h+Buffer]; lpBuffer
0x180215e10  call    cs:__imp_GetSystemDirectoryW
0x180215e16  lea     rdx, [rbp+280h+Buffer]
0x180215e1a  lea     rcx, [rsp+380h+var_310]
0x180215e1f  call    ??YMsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator+=(ushort const *)
0x180215e24  mov     rax, [rsi]
0x180215e27  lea     r12, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180215e2e  mov     rcx, r12
0x180215e31  mov     [rsp+380h+var_320], r12
0x180215e36  mov     rbx, [rax+88h]
0x180215e3d  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180215e44  mov     rax, [rax+10h]
0x180215e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215e4d  mov     rcx, [r14]
0x180215e50  mov     [rsp+380h+var_320], r12
0x180215e55  mov     rax, [rcx+50h]
0x180215e59  mov     rcx, r14
0x180215e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215e61  mov     rdx, rax
0x180215e64  lea     r8, [rsp+380h+var_320]
0x180215e69  mov     rax, rbx
0x180215e6c  mov     rcx, rsi
0x180215e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215e74  mov     rbx, rax
0x180215e77  test    rax, rax
0x180215e7a  jz      short loc_180215EB5
0x180215e7c  mov     rcx, rdi; hLibModule
0x180215e7f  call    cs:__imp_FreeLibrary
0x180215e85  mov     rdx, [rsp+380h+var_320]
0x180215e8a  mov     rcx, [rdx]
0x180215e8d  mov     rax, [rcx+10h]
0x180215e91  mov     rcx, rdx
0x180215e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215e99  mov     rdx, [rsp+380h+var_310]
0x180215e9e  mov     rcx, [rdx]
0x180215ea1  mov     rax, [rcx+10h]
0x180215ea5  mov     rcx, rdx
0x180215ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215ead  mov     rax, rbx
0x180215eb0  jmp     loc_18021622C
0x180215eb5  lea     r9, [rsp+380h+LastWriteTime]; struct _FILETIME *
0x180215eba  mov     qword ptr [rsp+380h+LastWriteTime.dwLowDateTime], r13
0x180215ebf  xor     edx, edx; struct _FILETIME *
0x180215ec1  mov     rcx, rsi; this
0x180215ec4  call    ?ChkCurFileAttributes@CMsiPath@@IEAAXPEAU_FILETIME@@00@Z; CMsiPath::ChkCurFileAttributes(_FILETIME *,_FILETIME *,_FILETIME *)
0x180215ec9  mov     rax, [rsi]
0x180215ecc  lea     rdx, [rsp+380h+dwFileAttributes]
0x180215ed1  mov     rcx, rsi
0x180215ed4  mov     [rsp+380h+dwFileAttributes], r13d
0x180215ed9  mov     rax, [rax+208h]
0x180215ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215ee5  mov     rbx, rax
0x180215ee8  test    rax, rax
0x180215eeb  jnz     short loc_180215E85
0x180215eed  mov     rax, [rsi]
0x180215ef0  mov     rcx, rsi
0x180215ef3  mov     rax, [rax+220h]
0x180215efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215eff  mov     sil, al
0x180215f02  test    al, al
0x180215f04  jz      short loc_180215F0B
0x180215f06  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180215f0b  mov     ebx, [rsp+380h+dwFileAttributes]
0x180215f0f  mov     r12d, 1
0x180215f15  test    r12b, bl
0x180215f18  jz      short loc_180215F39
0x180215f1a  mov     rcx, [rsp+380h+var_320]
0x180215f1f  and     ebx, 0FFFFFFFEh
0x180215f22  mov     rax, [rcx]
0x180215f25  mov     rax, [rax+50h]
0x180215f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215f2e  mov     edx, ebx; dwFileAttributes
0x180215f30  mov     rcx, rax; lpFileName
0x180215f33  call    cs:__imp_SetFileAttributesW
0x180215f39  mov     ebx, 3
0x180215f3e  cmp     [rsp+380h+LastWriteTime.dwLowDateTime], r13d
0x180215f43  jnz     short loc_180215FA7
0x180215f45  cmp     [rsp+380h+LastWriteTime.dwHighDateTime], r13d
0x180215f4a  jnz     short loc_180215FA7
0x180215f4c  mov     rcx, [rsp+380h+var_320]
0x180215f51  mov     rax, [rcx]
0x180215f54  mov     rax, [rax+50h]
0x180215f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215f5d  mov     [rsp+380h+hTemplateFile], r13; hTemplateFile
0x180215f62  xor     r9d, r9d; lpSecurityAttributes
0x180215f65  mov     [rsp+380h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x180215f6d  mov     r8d, ebx; dwShareMode
0x180215f70  mov     edx, 80000000h; dwDesiredAccess
0x180215f75  mov     [rsp+380h+dwCreationDisposition], ebx; dwCreationDisposition
0x180215f79  mov     rcx, rax; lpFileName
0x180215f7c  call    cs:__imp_CreateFileW
0x180215f82  mov     rbx, rax
0x180215f85  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180215f89  jz      short loc_180215FA7
0x180215f8b  lea     r9, [rsp+380h+LastWriteTime]; lpLastWriteTime
0x180215f90  xor     r8d, r8d; lpLastAccessTime
0x180215f93  xor     edx, edx; lpCreationTime
0x180215f95  mov     rcx, rax; hFile
0x180215f98  call    cs:__imp_GetFileTime
0x180215f9e  mov     rcx, rbx; hObject
0x180215fa1  call    cs:__imp_CloseHandle
0x180215fa7  mov     rcx, [rsp+380h+var_310]
0x180215fac  mov     rax, [rcx]
0x180215faf  mov     rax, [rax+50h]
0x180215fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215fb8  xor     ecx, ecx
0x180215fba  mov     [rbp+280h+var_268], rax
0x180215fbe  mov     [rbp+280h+var_290], cl
0x180215fc1  lea     rdx, [rbp+280h+var_290]
0x180215fc5  mov     [rbp+280h+var_278], cx
0x180215fc9  mov     r14d, 30h ; '0'
0x180215fcf  mov     [rbp+280h+var_298], r12d
0x180215fd3  lea     rcx, [rbp+280h+var_278]
0x180215fd7  mov     [rbp+280h+var_288], rcx
0x180215fdb  lea     rcx, [rbp+280h+var_2A0]
0x180215fdf  mov     [rbp+280h+var_2A0], rdx
0x180215fe3  mov     [rbp+280h+var_280], r12d
0x180215fe7  mov     [rbp+280h+var_270], r13
0x180215feb  mov     [rdx], r14b
0x180215fee  mov     rax, [rbp+280h+var_288]
0x180215ff2  mov     [rax], r14w
0x180215ff6  mov     [rbp+280h+var_260], r13d
0x180215ffa  call    ??BCConvertString@@QEAAPEBDXZ; CConvertString::operator char const *(void)
0x180215fff  mov     rcx, [rsp+380h+var_320]
0x180216004  mov     rbx, rax
0x180216007  mov     rdx, [rcx]
0x18021600a  mov     rax, [rdx+50h]
0x18021600e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216013  xor     ecx, ecx
0x180216015  mov     [rbp+280h+var_2B8], rax
0x180216019  mov     [rbp+280h+var_2E0], cl
0x18021601c  lea     rdx, [rbp+280h+var_2E0]
0x180216020  mov     [rbp+280h+var_2C8], cx
0x180216024  lea     rcx, [rbp+280h+var_2C8]
0x180216028  mov     [rbp+280h+var_2D8], rcx
0x18021602c  lea     rcx, [rbp+280h+var_2F0]
0x180216030  mov     [rbp+280h+var_2E8], r12d
0x180216034  mov     [rbp+280h+var_2F0], rdx
0x180216038  mov     [rbp+280h+var_2D0], r12d
0x18021603c  mov     [rbp+280h+var_2C0], r13
0x180216040  mov     [rdx], r14b
0x180216043  mov     rax, [rbp+280h+var_2D8]
0x180216047  mov     [rax], r14w
0x18021604b  mov     [rbp+280h+var_2B0], r13d
0x18021604f  call    ??BCConvertString@@QEAAPEBDXZ; CConvertString::operator char const *(void)
0x180216054  mov     rcx, rax
0x180216057  xor     r8d, r8d
0x18021605a  mov     rax, r15
0x18021605d  mov     rdx, rbx
0x180216060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216065  lea     rcx, [rbp+280h+var_2F0]; this
0x180216069  mov     ebx, eax
0x18021606b  call    ??1CConvertString@@QEAA@XZ; CConvertString::~CConvertString(void)
0x180216070  lea     rcx, [rbp+280h+var_2A0]; this
0x180216074  call    ??1CConvertString@@QEAA@XZ; CConvertString::~CConvertString(void)
0x180216079  test    ebx, ebx
0x18021607b  jnz     loc_180216162
0x180216081  call    cs:__imp_GetLastError
0x180216087  mov     rcx, rdi; hLibModule
0x18021608a  mov     r14d, eax
0x18021608d  call    cs:__imp_FreeLibrary
0x180216093  mov     ebx, [rsp+380h+dwFileAttributes]
0x180216097  test    r12b, bl
0x18021609a  jz      short loc_1802160B8
0x18021609c  mov     rcx, [rsp+380h+var_320]
0x1802160a1  mov     r8, [rcx]
0x1802160a4  mov     rax, [r8+50h]
0x1802160a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802160ad  mov     edx, ebx; dwFileAttributes
0x1802160af  mov     rcx, rax; lpFileName
0x1802160b2  call    cs:__imp_SetFileAttributesW
0x1802160b8  test    sil, sil
0x1802160bb  jz      short loc_1802160C2
0x1802160bd  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x1802160c2  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1802160c9  jz      short loc_18021611F
0x1802160cb  mov     rcx, [rsp+380h+var_320]
0x1802160d0  mov     rax, [rcx]
0x1802160d3  mov     rax, [rax+50h]
0x1802160d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802160dc  mov     [rsp+380h+var_328], r13; void *
0x1802160e1  lea     r8, aNull; "(NULL)"
0x1802160e8  mov     [rsp+380h+var_330], r13d; unsigned int
0x1802160ed  lea     r9, aBindimageForFi; "BindImage for file '%s' failed with las"...
0x1802160f4  mov     [rsp+380h+var_338], r8; unsigned __int16 *
0x1802160f9  xor     edx, edx; unsigned __int16
0x1802160fb  mov     [rsp+380h+var_340], r8; unsigned __int16 *
0x180216100  mov     [rsp+380h+var_348], r8; unsigned __int16 *
0x180216105  mov     [rsp+380h+hTemplateFile], r8; unsigned __int16 *
0x18021610a  xor     r8d, r8d; int
0x18021610d  mov     qword ptr [rsp+380h+dwFlagsAndAttributes], r14; unsigned __int16 *
0x180216112  lea     ecx, [rdx+9]; int
0x180216115  mov     qword ptr [rsp+380h+dwCreationDisposition], rax; unsigned __int16 *
0x18021611a  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18021611f  mov     rcx, [rsp+380h+var_320]
0x180216124  mov     rax, [rcx]
0x180216127  mov     rax, [rax+50h]
0x18021612b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216130  mov     rdx, rax; unsigned __int16 *
0x180216133  mov     ecx, 93Dh; int
0x180216138  call    ?PostError@@YAPEAVIMsiRecord@@HPEBG@Z; PostError(int,ushort const *)
0x18021613d  mov     rcx, [rsp+380h+var_320]
0x180216142  mov     rbx, rax
0x180216145  mov     rdx, [rcx]
0x180216148  mov     rax, [rdx+10h]
0x18021614c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216151  mov     rcx, [rsp+380h+var_310]
0x180216156  mov     rdx, [rcx]
0x180216159  mov     rax, [rdx+10h]
0x18021615d  jmp     loc_180215EA8
0x180216162  cmp     [rsp+380h+LastWriteTime.dwLowDateTime], r13d
0x180216167  jnz     short loc_180216170
0x180216169  cmp     [rsp+380h+LastWriteTime.dwHighDateTime], r13d
0x18021616e  jz      short loc_1802161D0
0x180216170  mov     rcx, [rsp+380h+var_320]
0x180216175  mov     rax, [rcx]
0x180216178  mov     rax, [rax+50h]
0x18021617c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216181  xor     r9d, r9d; lpSecurityAttributes
0x180216184  mov     [rsp+380h+hTemplateFile], r13; hTemplateFile
0x180216189  mov     [rsp+380h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x180216191  mov     edx, 40000000h; dwDesiredAccess
  ... truncated ...
```
