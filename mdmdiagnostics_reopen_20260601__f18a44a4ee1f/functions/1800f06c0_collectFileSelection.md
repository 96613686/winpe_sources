# collectFileSelection

- ea: `0x1800f06c0`
- end: `0x1800f0b22`
- name: `collectFileSelection`
- size: `1122`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x1800f2b84`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800a9fc0`
- `0x1800e68b0`
- `0x1800ed46c`
- `0x1800edc3c`
- `0x1800edd28`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x1800f06c0`
- `0x18011a270`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f0824`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f0843`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f0824`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f0843`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800f08ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800f092c`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800f08ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800f092c`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800f07c9`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800f07c9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f08f9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f0952`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f08f9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f0952`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800f0a53`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800f0a53`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800f07e1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800f07e1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f0ae7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f0ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f07f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f09e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0a67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f07f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f09e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0a67`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800f077e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800f077e`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800f09d1`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800f09d1`

## string_xrefs

- `0x1800f0a9d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f0ac1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f09fc`: `Failed to copy file: `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall collectFileSelection(const WCHAR *a1, const unsigned __int16 *a2)
{
  HANDLE FirstFileW; // r15
  signed int result; // eax
  unsigned int v6; // ebx
  int v7; // edi
  char v8; // dl
  __int16 v9; // r8
  int v10; // r9d
  char v11; // di
  __int64 i; // r14
  char v13; // dl
  __int16 v14; // r8
  int v15; // r9d
  __int64 j; // rdi
  int v17; // r14d
  signed int v18; // eax
  const unsigned __int16 *v19; // rax
  TelemetryWriter *v20; // rcx
  signed int LastError; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  int DirCount; // [rsp+20h] [rbp-E0h]
  wchar_t DirCounta; // [rsp+20h] [rbp-E0h]
  wchar_t *Filename; // [rsp+28h] [rbp-D8h]
  wchar_t *Filenamea; // [rsp+28h] [rbp-D8h]
  _BYTE v28[32]; // [rsp+50h] [rbp-B0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Dst[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  WCHAR NewFileName[264]; // [rsp+6E0h] [rbp+5E0h] BYREF
  wchar_t Drive[264]; // [rsp+8F0h] [rbp+7F0h] BYREF
  wchar_t Dir[264]; // [rsp+B00h] [rbp+A00h] BYREF
  wchar_t Ext[264]; // [rsp+D10h] [rbp+C10h] BYREF
  wchar_t v36[264]; // [rsp+F20h] [rbp+E20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1168h] [rbp+1068h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(Drive, 0, 0x208u);
  memset_0(Dir, 0, 0x208u);
  memset_0(v36, 0, 0x208u);
  memset_0(Ext, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  ExpandEnvironmentStringsW(a1, Dst, 0x104u);
  _wsplitpath_s(Dst, Drive, 0x104u, Dir, 0x104u, v36, 0x104u, Ext, 0x104u);
  FirstFileW = FindFirstFileW(Dst, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v6 = 0;
  while ( !(unsigned int)_o__wcsicmp(FindFileData.cFileName, L".")
       || !(unsigned int)_o__wcsicmp(FindFileData.cFileName, L"..")
       || (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
LABEL_26:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      LastError = GetLastError();
      if ( LastError != 18 )
      {
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        else
          v6 = LastError;
      }
      goto LABEL_39;
    }
  }
  memset_0(NewFileName, 0, 0x208u);
  memset_0(ExistingFileName, 0, 0x208u);
  v7 = StringCchCopyW(ExistingFileName, 0x104u, Drive);
  if ( v7 < 0 )
  {
    v23 = 314;
    goto LABEL_37;
  }
  v7 = StringCchCatW(ExistingFileName, 0x104u, Dir);
  if ( v7 < 0 )
  {
    v23 = 316;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
      (const char *)(unsigned int)v7,
      DirCount);
    return v7;
  }
  v11 = 0;
  o((wchar_t)Dst, v8, v9, v10, DirCount, *(long double *)&Filename);
  for ( i = 0; i != 6; ++i )
  {
    if ( wcsstr(Dst, (const wchar_t *)&(&whitelistedFoldersExpanded)[65 * i]) )
      v11 = 1;
  }
  if ( v11 )
  {
    o((wchar_t)FindFileData.cFileName, v13, v14, v15, DirCounta, *(long double *)&Filenamea);
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      if ( (unsigned int)j >= 9 )
        goto LABEL_26;
      if ( wcsstr(FindFileData.cFileName, off_18019D900[j]) )
      {
        v17 = StringCchCatW(ExistingFileName, 0x104u, FindFileData.cFileName);
        if ( v17 < 0 )
        {
          v22 = 339;
          goto LABEL_33;
        }
        v17 = StringCchCopyW(NewFileName, 0x104u, a2);
        if ( v17 < 0 )
        {
          v22 = 341;
          goto LABEL_33;
        }
        v17 = StringCchCatW(NewFileName, 0x104u, FindFileData.cFileName);
        if ( v17 < 0 )
        {
          v22 = 343;
LABEL_33:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
            (const char *)(unsigned int)v17,
            DirCount);
          return v17;
        }
        if ( !CopyFileW(ExistingFileName, NewFileName, 0) )
        {
          v18 = GetLastError();
          v6 = v18;
          if ( v18 > 0 )
            v6 = (unsigned __int16)v18 | 0x80070000;
          std::wstring::wstring(v28, L"Failed to copy file: ");
          std::wstring::append(v28, ExistingFileName);
          v19 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
          TelemetryWriter::Write(v20, v19, v6);
          std::wstring::_Tidy_deallocate(v28);
        }
      }
    }
  }
  v6 = -2147418113;
LABEL_39:
  FindClose(FirstFileW);
  return v6;
}

```

## disassembly

```asm
0x1800f06c0  mov     [rsp-8+arg_10], rbx
0x1800f06c5  mov     [rsp-8+arg_18], rdi
0x1800f06ca  push    rbp
0x1800f06cb  push    r12
0x1800f06cd  push    r13
0x1800f06cf  push    r14
0x1800f06d1  push    r15
0x1800f06d3  lea     rbp, [rsp-1040h]
0x1800f06db  mov     eax, 1140h
0x1800f06e0  call    _alloca_probe
0x1800f06e5  sub     rsp, rax
0x1800f06e8  mov     rax, cs:__security_cookie
0x1800f06ef  xor     rax, rsp
0x1800f06f2  mov     [rbp+1060h+var_30], rax
0x1800f06f9  mov     r12, rdx
0x1800f06fc  mov     rbx, rcx
0x1800f06ff  xor     edx, edx; Val
0x1800f0701  mov     r8d, 250h; Size
0x1800f0707  lea     rcx, [rsp+1160h+FindFileData]; void *
0x1800f070c  call    memset_0
0x1800f0711  mov     edi, 208h
0x1800f0716  mov     r8d, edi; Size
0x1800f0719  xor     edx, edx; Val
0x1800f071b  lea     rcx, [rbp+1060h+Drive]; void *
0x1800f0722  call    memset_0
0x1800f0727  mov     r8d, edi; Size
0x1800f072a  xor     edx, edx; Val
0x1800f072c  lea     rcx, [rbp+1060h+Dir]; void *
0x1800f0733  call    memset_0
0x1800f0738  mov     r8d, edi; Size
0x1800f073b  xor     edx, edx; Val
0x1800f073d  lea     rcx, [rbp+1060h+var_240]; void *
0x1800f0744  call    memset_0
0x1800f0749  mov     r8d, edi; Size
0x1800f074c  xor     edx, edx; Val
0x1800f074e  lea     rcx, [rbp+1060h+var_450]; void *
0x1800f0755  call    memset_0
0x1800f075a  mov     r8d, edi; Size
0x1800f075d  xor     edx, edx; Val
0x1800f075f  lea     rcx, [rbp+1060h+Dst]; void *
0x1800f0766  call    memset_0
0x1800f076b  mov     r13d, 104h
0x1800f0771  mov     r8d, r13d; nSize
0x1800f0774  lea     rdx, [rbp+1060h+Dst]; lpDst
0x1800f077b  mov     rcx, rbx; lpSrc
0x1800f077e  call    cs:__imp_ExpandEnvironmentStringsW
0x1800f0785  nop     dword ptr [rax+rax+00h]
0x1800f078a  mov     [rsp+1160h+ExtCount], r13; ExtCount
0x1800f078f  lea     rax, [rbp+1060h+var_450]
0x1800f0796  mov     [rsp+1160h+Ext], rax; Ext
0x1800f079b  mov     [rsp+1160h+FilenameCount], r13; FilenameCount
0x1800f07a0  lea     rax, [rbp+1060h+var_240]
0x1800f07a7  mov     [rsp+1160h+Filename], rax; Filename
0x1800f07ac  mov     [rsp+1160h+DirCount], r13; int
0x1800f07b1  lea     r9, [rbp+1060h+Dir]; Dir
0x1800f07b8  mov     r8d, r13d; DriveCount
0x1800f07bb  lea     rdx, [rbp+1060h+Drive]; Drive
0x1800f07c2  lea     rcx, [rbp+1060h+Dst]; FullPath
0x1800f07c9  call    cs:__imp__wsplitpath_s
0x1800f07d0  nop     dword ptr [rax+rax+00h]
0x1800f07d5  lea     rdx, [rsp+1160h+FindFileData]; lpFindFileData
0x1800f07da  lea     rcx, [rbp+1060h+Dst]; lpFileName
0x1800f07e1  call    cs:__imp_FindFirstFileW
0x1800f07e8  nop     dword ptr [rax+rax+00h]
0x1800f07ed  mov     r15, rax
0x1800f07f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f07f4  jnz     short loc_1800F0817
0x1800f07f6  call    cs:__imp_GetLastError
0x1800f07fd  nop     dword ptr [rax+rax+00h]
0x1800f0802  test    eax, eax
0x1800f0804  jle     loc_1800F0AF5
0x1800f080a  movzx   eax, ax
0x1800f080d  or      eax, 80070000h
0x1800f0812  jmp     loc_1800F0AF5
0x1800f0817  xor     ebx, ebx
0x1800f0819  lea     rdx, asc_1801BC058; "."
0x1800f0820  lea     rcx, [rbp+1060h+FindFileData.cFileName]
0x1800f0824  call    cs:__imp__o__wcsicmp
0x1800f082b  nop     dword ptr [rax+rax+00h]
0x1800f0830  test    eax, eax
0x1800f0832  jz      loc_1800F0A4B
0x1800f0838  lea     rdx, asc_1801BCB04; ".."
0x1800f083f  lea     rcx, [rbp+1060h+FindFileData.cFileName]
0x1800f0843  call    cs:__imp__o__wcsicmp
0x1800f084a  nop     dword ptr [rax+rax+00h]
0x1800f084f  test    eax, eax
0x1800f0851  jz      loc_1800F0A4B
0x1800f0857  test    byte ptr [rsp+1160h+FindFileData.dwFileAttributes], 10h
0x1800f085c  jnz     loc_1800F0A4B
0x1800f0862  mov     r8, rdi; Size
0x1800f0865  xor     edx, edx; Val
0x1800f0867  lea     rcx, [rbp+1060h+NewFileName]; void *
0x1800f086e  call    memset_0
0x1800f0873  mov     r8, rdi; Size
0x1800f0876  xor     edx, edx; Val
0x1800f0878  lea     rcx, [rbp+1060h+ExistingFileName]; void *
0x1800f087f  call    memset_0
0x1800f0884  lea     r8, [rbp+1060h+Drive]; unsigned __int16 *
0x1800f088b  mov     rdx, r13; unsigned __int64
0x1800f088e  lea     rcx, [rbp+1060h+ExistingFileName]; unsigned __int16 *
0x1800f0895  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f089a  mov     edi, eax
0x1800f089c  test    eax, eax
0x1800f089e  js      loc_1800F0ABC
0x1800f08a4  lea     r8, [rbp+1060h+Dir]; unsigned __int16 *
0x1800f08ab  mov     rdx, r13; unsigned __int64
0x1800f08ae  lea     rcx, [rbp+1060h+ExistingFileName]; unsigned __int16 *
0x1800f08b5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f08ba  mov     edi, eax
0x1800f08bc  test    eax, eax
0x1800f08be  js      loc_1800F0AB5
0x1800f08c4  xor     dil, dil
0x1800f08c7  lea     rcx, [rbp+1060h+Dst]
0x1800f08ce  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800f08d5  nop     dword ptr [rax+rax+00h]
0x1800f08da  xor     r14d, r14d
0x1800f08dd  lea     r13d, [r14+1]
0x1800f08e1  imul    rdx, r14, 208h
0x1800f08e8  lea     rax, ?whitelistedFoldersExpanded@@3PAY0BAE@GA; ushort (near * whitelistedFoldersExpanded)[260]
0x1800f08ef  add     rdx, rax; SubStr
0x1800f08f2  lea     rcx, [rbp+1060h+Dst]; Str
0x1800f08f9  call    cs:__imp_wcsstr
0x1800f0900  nop     dword ptr [rax+rax+00h]
0x1800f0905  movzx   edi, dil
0x1800f0909  test    rax, rax
0x1800f090c  cmovnz  edi, r13d
0x1800f0910  add     r14, r13
0x1800f0913  cmp     r14, 6
0x1800f0917  jnz     short loc_1800F08E1
0x1800f0919  mov     r13d, 104h
0x1800f091f  test    dil, dil
0x1800f0922  jz      loc_1800F0AAE
0x1800f0928  lea     rcx, [rbp+1060h+FindFileData.cFileName]
0x1800f092c  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800f0933  nop     dword ptr [rax+rax+00h]
0x1800f0938  xor     edi, edi
0x1800f093a  cmp     edi, 9
0x1800f093d  jnb     loc_1800F0A46
0x1800f0943  lea     rax, off_18019D900; ".log"
0x1800f094a  mov     rdx, [rax+rdi*8]; SubStr
0x1800f094e  lea     rcx, [rbp+1060h+FindFileData.cFileName]; Str
0x1800f0952  call    cs:__imp_wcsstr
0x1800f0959  nop     dword ptr [rax+rax+00h]
0x1800f095e  test    rax, rax
0x1800f0961  jz      loc_1800F0A3F
0x1800f0967  lea     r8, [rbp+1060h+FindFileData.cFileName]; unsigned __int16 *
0x1800f096b  mov     rdx, r13; unsigned __int64
0x1800f096e  lea     rcx, [rbp+1060h+ExistingFileName]; unsigned __int16 *
0x1800f0975  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f097a  mov     r14d, eax
0x1800f097d  test    eax, eax
0x1800f097f  js      loc_1800F0A8E
0x1800f0985  mov     r8, r12; unsigned __int16 *
0x1800f0988  mov     rdx, r13; unsigned __int64
0x1800f098b  lea     rcx, [rbp+1060h+NewFileName]; unsigned __int16 *
0x1800f0992  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f0997  mov     r14d, eax
0x1800f099a  test    eax, eax
0x1800f099c  js      loc_1800F0A87
0x1800f09a2  lea     r8, [rbp+1060h+FindFileData.cFileName]; unsigned __int16 *
0x1800f09a6  mov     rdx, r13; unsigned __int64
0x1800f09a9  lea     rcx, [rbp+1060h+NewFileName]; unsigned __int16 *
0x1800f09b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f09b5  mov     r14d, eax
0x1800f09b8  test    eax, eax
0x1800f09ba  js      loc_1800F0A80
0x1800f09c0  xor     r8d, r8d; bFailIfExists
0x1800f09c3  lea     rdx, [rbp+1060h+NewFileName]; lpNewFileName
0x1800f09ca  lea     rcx, [rbp+1060h+ExistingFileName]; lpExistingFileName
0x1800f09d1  call    cs:__imp_CopyFileW
0x1800f09d8  nop     dword ptr [rax+rax+00h]
0x1800f09dd  test    eax, eax
0x1800f09df  jnz     short loc_1800F0A3F
0x1800f09e1  call    cs:__imp_GetLastError
0x1800f09e8  nop     dword ptr [rax+rax+00h]
0x1800f09ed  mov     ebx, eax
0x1800f09ef  test    eax, eax
0x1800f09f1  jle     short loc_1800F09FC
0x1800f09f3  movzx   ebx, ax
0x1800f09f6  or      ebx, 80070000h
0x1800f09fc  lea     rdx, aFailedToCopyFi; "Failed to copy file: "
0x1800f0a03  lea     rcx, [rsp+1160h+var_1110]
0x1800f0a08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f0a0d  nop
0x1800f0a0e  lea     rdx, [rbp+1060h+ExistingFileName]
0x1800f0a15  lea     rcx, [rsp+1160h+var_1110]
0x1800f0a1a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800f0a1f  lea     rcx, [rsp+1160h+var_1110]
0x1800f0a24  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f0a29  mov     rdx, rax; unsigned __int16 *
0x1800f0a2c  mov     r8d, ebx; int
0x1800f0a2f  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x1800f0a34  nop
0x1800f0a35  lea     rcx, [rsp+1160h+var_1110]
0x1800f0a3a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f0a3f  inc     edi
0x1800f0a41  jmp     loc_1800F093A
0x1800f0a46  mov     edi, 208h
0x1800f0a4b  lea     rdx, [rsp+1160h+FindFileData]; lpFindFileData
0x1800f0a50  mov     rcx, r15; hFindFile
0x1800f0a53  call    cs:__imp_FindNextFileW
0x1800f0a5a  nop     dword ptr [rax+rax+00h]
0x1800f0a5f  test    eax, eax
0x1800f0a61  jnz     loc_1800F0819
0x1800f0a67  call    cs:__imp_GetLastError
0x1800f0a6e  nop     dword ptr [rax+rax+00h]
0x1800f0a73  cmp     eax, 12h
0x1800f0a76  jz      short loc_1800F0AE4
0x1800f0a78  test    eax, eax
0x1800f0a7a  jg      short loc_1800F0ADB
0x1800f0a7c  mov     ebx, eax
0x1800f0a7e  jmp     short loc_1800F0AE4
0x1800f0a80  mov     edx, 157h
0x1800f0a85  jmp     short loc_1800F0A93
0x1800f0a87  mov     edx, 155h
0x1800f0a8c  jmp     short loc_1800F0A93
0x1800f0a8e  mov     edx, 153h; void *
0x1800f0a93  mov     rcx, [rbp+1068h]; this
0x1800f0a9a  mov     r9d, r14d; char *
0x1800f0a9d  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f0aa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0aa9  mov     eax, r14d
0x1800f0aac  jmp     short loc_1800F0AF5
0x1800f0aae  mov     ebx, 8000FFFFh
0x1800f0ab3  jmp     short loc_1800F0AE4
0x1800f0ab5  mov     edx, 13Ch
0x1800f0aba  jmp     short loc_1800F0AC1
0x1800f0abc  mov     edx, 13Ah; void *
0x1800f0ac1  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f0ac8  mov     r9d, edi; char *
0x1800f0acb  mov     rcx, [rbp+1068h]; this
0x1800f0ad2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0ad7  mov     eax, edi
0x1800f0ad9  jmp     short loc_1800F0AF5
0x1800f0adb  movzx   ebx, ax
0x1800f0ade  or      ebx, 80070000h
0x1800f0ae4  mov     rcx, r15; hFindFile
0x1800f0ae7  call    cs:__imp_FindClose
0x1800f0aee  nop     dword ptr [rax+rax+00h]
0x1800f0af3  mov     eax, ebx
0x1800f0af5  mov     rcx, [rbp+1060h+var_30]
0x1800f0afc  xor     rcx, rsp; StackCookie
0x1800f0aff  call    __security_check_cookie
0x1800f0b04  lea     r11, [rsp+1160h+var_20]
0x1800f0b0c  mov     rbx, [r11+40h]
0x1800f0b10  mov     rdi, [r11+48h]
0x1800f0b14  mov     rsp, r11
0x1800f0b17  pop     r15
0x1800f0b19  pop     r14
0x1800f0b1b  pop     r13
0x1800f0b1d  pop     r12
0x1800f0b1f  pop     rbp
0x1800f0b20  retn
```
