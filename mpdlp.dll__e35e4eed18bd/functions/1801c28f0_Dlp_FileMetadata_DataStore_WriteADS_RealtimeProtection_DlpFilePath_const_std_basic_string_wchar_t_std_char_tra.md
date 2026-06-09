# Dlp::FileMetadata::DataStore::WriteADS(RealtimeProtection::DlpFilePath const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,uchar const *,uint)

- ea: `0x1801c28f0`
- end: `0x1801c2d0d`
- name: `?WriteADS@DataStore@FileMetadata@Dlp@@YAJAEBVDlpFilePath@RealtimeProtection@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBEI@Z`
- size: `1053`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1801bcd30`

## callees

- `0x180002c84`
- `0x180004f3c`
- `0x180034420`
- `0x180065394`
- `0x1800a1860`
- `0x1800cba98`
- `0x18010cb40`
- `0x18016cfe4`
- `0x1801c2498`
- `0x1801c28f0`
- `0x18023a290`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1801c2bb3`
- `KERNEL32!WriteFile` at `0x1801c2bb3`
- `KERNEL32!SetFileTime` at `0x1801c2c21`
- `KERNEL32!SetFileTime` at `0x1801c2c21`
- `KERNEL32!GetFileTime` at `0x1801c2ac8`
- `KERNEL32!GetFileTime` at `0x1801c2ac8`
- `KERNEL32!GetLastError` at `0x1801c2a20`
- `KERNEL32!GetLastError` at `0x1801c2b34`
- `KERNEL32!GetLastError` at `0x1801c2c6b`
- `KERNEL32!GetLastError` at `0x1801c2a20`
- `KERNEL32!GetLastError` at `0x1801c2b34`
- `KERNEL32!GetLastError` at `0x1801c2c6b`
- `KERNEL32!CreateFileW` at `0x1801c29de`
- `KERNEL32!CreateFileW` at `0x1801c2b21`
- `KERNEL32!CreateFileW` at `0x1801c29de`
- `KERNEL32!CreateFileW` at `0x1801c2b21`
- `SHLWAPI!PathFileExistsW` at `0x1801c2a12`
- `SHLWAPI!PathFileExistsW` at `0x1801c2a12`

## string_xrefs

- `0x1801c2c9c`: `Failed to write Dlp Info metadata to ADS file`
- `0x1801c2b69`: `Failed to create ADS file`
- `0x1801c293b`: `src\epp\Dlp\FileMetadataBroker\data_store\fs_utils\src\rw_ads.cpp`
- `0x1801c2ad6`: `src\epp\Dlp\FileMetadataBroker\data_store\fs_utils\src\rw_ads.cpp`
- `0x1801c2c2f`: `src\epp\Dlp\FileMetadataBroker\data_store\fs_utils\src\rw_ads.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Dlp::FileMetadata::DataStore::WriteADS(_QWORD *a1, __int64 a2, const void *a3, DWORD a4)
{
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // rax
  HANDLE FileW; // rbx
  __int64 v11; // rax
  signed int LastError; // eax
  const struct _tlgProvider_t *v13; // rdi
  _QWORD *v14; // rax
  const char *v15; // r9
  const WCHAR *v16; // rcx
  HANDLE v17; // rax
  void *v18; // rbx
  signed int v19; // eax
  const struct _tlgProvider_t *v20; // rax
  LPCWSTR *v21; // rcx
  __int64 *v22; // rcx
  __int16 *v23; // rdx
  const struct _tlgProvider_t *v24; // rax
  int v25; // r8d
  int v26; // r9d
  LPCWSTR *v27; // rcx
  const char *v28; // r9
  signed int v30; // eax
  LPCWSTR *v31; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-59h]
  __int64 *dwFlagsAndAttributes; // [rsp+28h] [rbp-51h]
  __int64 v34; // [rsp+40h] [rbp-39h] BYREF
  __int64 v35; // [rsp+48h] [rbp-31h] BYREF
  __int64 v36; // [rsp+50h] [rbp-29h] BYREF
  __int64 v37; // [rsp+58h] [rbp-21h] BYREF
  HANDLE v38; // [rsp+60h] [rbp-19h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp-11h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int64 v41; // [rsp+88h] [rbp+Fh]
  struct _FILETIME LastWriteTime; // [rsp+90h] [rbp+17h] BYREF
  struct _FILETIME LastAccessTime; // [rsp+98h] [rbp+1Fh] BYREF
  struct _FILETIME CreationTime; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( *(_QWORD *)((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1) + 16) )
  {
    if ( !qword_180311AB8 )
    {
      v7 = 100;
      goto LABEL_3;
    }
    if ( !a3 )
    {
      v7 = 101;
      goto LABEL_3;
    }
    if ( !a4 )
    {
      v7 = 102;
      goto LABEL_3;
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    std::operator+<wchar_t>(lpFileName);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    if ( *(_QWORD *)(v9 + 24) > 7u )
      v9 = *(_QWORD *)v9;
    FileW = CreateFileW((LPCWSTR)v9, 0x80000000, 3u, 0, 3u, 0x80u, 0);
    v38 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
      if ( *(_QWORD *)(v11 + 24) > 7u )
        v11 = *(_QWORD *)v11;
      if ( !PathFileExistsW((LPCWSTR)v11) )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        v13 = FmbTrace::Provider();
        if ( *(_DWORD *)v13 > 3u )
        {
          LODWORD(v34) = v8;
          v14 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
          if ( v14[3] > 7u )
            v14 = (_QWORD *)*v14;
          v36 = (__int64)v14;
          v35 = (__int64)L"Not writing ADS since file doesn't exist";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            (int)v13,
            (int)&word_1802C54C6,
            (__int64)&v35,
            (__int64)&v36,
            (__int64)&v34);
        }
        goto LABEL_50;
      }
    }
    CreationTime = 0;
    LastAccessTime = 0;
    LastWriteTime = 0;
    if ( !GetFileTime(FileW, &CreationTime, &LastAccessTime, &LastWriteTime) )
    {
      v8 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x88,
             (unsigned int)"src\\epp\\Dlp\\FileMetadataBroker\\data_store\\fs_utils\\src\\rw_ads.cpp",
             v15);
LABEL_50:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpFileName);
      return v8;
    }
    v16 = (const WCHAR *)lpFileName;
    if ( v41 > 7 )
      v16 = lpFileName[0];
    v17 = CreateFileW(v16, 0x40000000u, 7u, 0, 2u, 0x80u, 0);
    v18 = v17;
    v36 = (__int64)v17;
    if ( v17 == (HANDLE)-1LL )
    {
      v19 = GetLastError();
      v8 = v19;
      if ( v19 > 0 )
        v8 = (unsigned __int16)v19 | 0x80070000;
      v20 = FmbTrace::Provider();
      if ( *(_DWORD *)v20 <= 3u )
        goto LABEL_49;
      v21 = lpFileName;
      if ( v41 > 7 )
        v21 = (LPCWSTR *)lpFileName[0];
      v35 = (__int64)v21;
      v37 = (__int64)L"Failed to create ADS file";
      dwFlagsAndAttributes = &v35;
      v22 = &v37;
      v23 = word_1802C554A;
    }
    else
    {
      NumberOfBytesWritten = 0;
      if ( WriteFile(v17, a3, a4, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == a4 )
      {
        v24 = FmbTrace::Provider();
        if ( *(_DWORD *)v24 > 5u )
        {
          v27 = lpFileName;
          if ( v41 > 7 )
            v27 = (LPCWSTR *)lpFileName[0];
          v37 = (__int64)v27;
          v35 = (__int64)L"Successfully wrote DlpInfo data to ADS file";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
            (_DWORD)v24,
            (unsigned int)byte_1802C560B,
            v25,
            v26,
            (__int64)&v35,
            (__int64)&v37);
        }
        if ( SetFileTime(v18, &CreationTime, &LastAccessTime, &LastWriteTime) )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpFileName);
          return 0;
        }
        v8 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xB1,
               (unsigned int)"src\\epp\\Dlp\\FileMetadataBroker\\data_store\\fs_utils\\src\\rw_ads.cpp",
               v28);
        goto LABEL_49;
      }
      v30 = GetLastError();
      v8 = v30;
      if ( v30 > 0 )
        v8 = (unsigned __int16)v30 | 0x80070000;
      v20 = FmbTrace::Provider();
      if ( *(_DWORD *)v20 <= 3u )
      {
LABEL_49:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
        goto LABEL_50;
      }
      v31 = lpFileName;
      if ( v41 > 7 )
        v31 = (LPCWSTR *)lpFileName[0];
      v37 = (__int64)v31;
      v35 = (__int64)L"Failed to write Dlp Info metadata to ADS file";
      dwFlagsAndAttributes = &v37;
      v22 = &v35;
      v23 = (__int16 *)&dword_1802C5644;
    }
    LODWORD(v34) = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      (int)v20,
      (int)v23,
      (__int64)v22,
      (__int64)dwFlagsAndAttributes,
      (__int64)&v34);
    goto LABEL_49;
  }
  v7 = 99;
LABEL_3:
  v8 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"src\\epp\\Dlp\\FileMetadataBroker\\data_store\\fs_utils\\src\\rw_ads.cpp",
    (const char *)0x80070057LL,
    dwCreationDisposition);
  return v8;
}

```

## disassembly

```asm
0x1801c28f0  push    rbp
0x1801c28f2  push    rbx
0x1801c28f3  push    rsi
0x1801c28f4  push    rdi
0x1801c28f5  push    r14
0x1801c28f7  lea     rbp, [rsp-37h]
0x1801c28fc  sub     rsp, 0B0h
0x1801c2903  mov     rax, cs:__security_cookie
0x1801c290a  xor     rax, rsp
0x1801c290d  mov     [rbp+57h+var_28], rax
0x1801c2911  mov     edi, r9d
0x1801c2914  mov     r14, r8
0x1801c2917  mov     rsi, rcx
0x1801c291a  mov     rcx, [rcx]
0x1801c291d  mov     rax, [rcx]
0x1801c2920  mov     rax, [rax+10h]
0x1801c2924  call    cs:__guard_dispatch_icall_fptr
0x1801c292a  cmp     qword ptr [rax+10h], 0
0x1801c292f  jnz     short loc_1801C2953
0x1801c2931  mov     edx, 63h ; 'c'; void *
0x1801c2936  mov     ebx, 80070057h
0x1801c293b  lea     r8, aSrcEppDlpFilem_1; "src\\epp\\Dlp\\FileMetadataBroker\\data"...
0x1801c2942  mov     r9d, ebx; char *
0x1801c2945  mov     rcx, [rbp+5Fh]; this
0x1801c2949  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c294e  jmp     loc_1801C2CF1
0x1801c2953  cmp     cs:qword_180311AB8, 0
0x1801c295b  jnz     short loc_1801C2964
0x1801c295d  mov     edx, 64h ; 'd'
0x1801c2962  jmp     short loc_1801C2936
0x1801c2964  test    r14, r14
0x1801c2967  jnz     short loc_1801C296F
0x1801c2969  lea     edx, [r14+65h]
0x1801c296d  jmp     short loc_1801C2936
0x1801c296f  test    edi, edi
0x1801c2971  jnz     short loc_1801C2978
0x1801c2973  lea     edx, [rdi+66h]
0x1801c2976  jmp     short loc_1801C2936
0x1801c2978  mov     rcx, [rsi]
0x1801c297b  mov     rax, [rcx]
0x1801c297e  mov     rax, [rax+10h]
0x1801c2982  call    cs:__guard_dispatch_icall_fptr
0x1801c2988  lea     r8, qword_180311AA8
0x1801c298f  mov     rdx, rax
0x1801c2992  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801c2996  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@0@Z; std::operator+<wchar_t>(std::wstring const &,std::wstring const &)
0x1801c299b  nop
0x1801c299c  mov     rcx, [rsi]
0x1801c299f  mov     rax, [rcx]
0x1801c29a2  mov     rax, [rax+10h]
0x1801c29a6  call    cs:__guard_dispatch_icall_fptr
0x1801c29ac  cmp     qword ptr [rax+18h], 7
0x1801c29b1  jbe     short loc_1801C29B6
0x1801c29b3  mov     rax, [rax]
0x1801c29b6  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x1801c29bf  mov     [rsp+0D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1801c29c7  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x1801c29cf  xor     r9d, r9d; lpSecurityAttributes
0x1801c29d2  mov     edx, 80000000h; dwDesiredAccess
0x1801c29d7  lea     r8d, [r9+3]; dwShareMode
0x1801c29db  mov     rcx, rax; lpFileName
0x1801c29de  call    cs:__imp_CreateFileW
0x1801c29e4  mov     rbx, rax
0x1801c29e7  mov     [rbp+57h+var_70], rax
0x1801c29eb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801c29ef  jnz     loc_1801C2AA1
0x1801c29f5  mov     rcx, [rsi]
0x1801c29f8  mov     rax, [rcx]
0x1801c29fb  mov     rax, [rax+10h]
0x1801c29ff  call    cs:__guard_dispatch_icall_fptr
0x1801c2a05  cmp     qword ptr [rax+18h], 7
0x1801c2a0a  jbe     short loc_1801C2A0F
0x1801c2a0c  mov     rax, [rax]
0x1801c2a0f  mov     rcx, rax; pszPath
0x1801c2a12  call    cs:__imp_PathFileExistsW
0x1801c2a18  test    eax, eax
0x1801c2a1a  jnz     loc_1801C2AA1
0x1801c2a20  call    cs:__imp_GetLastError
0x1801c2a26  mov     ebx, eax
0x1801c2a28  test    eax, eax
0x1801c2a2a  jle     short loc_1801C2A35
0x1801c2a2c  movzx   ebx, ax
0x1801c2a2f  or      ebx, 80070000h
0x1801c2a35  call    ?Provider@FmbTrace@@SAPEBU_tlgProvider_t@@XZ; FmbTrace::Provider(void)
0x1801c2a3a  mov     rdi, rax
0x1801c2a3d  cmp     dword ptr [rax], 3
0x1801c2a40  jbe     loc_1801C2CDE
0x1801c2a46  mov     dword ptr [rbp+57h+var_90], ebx
0x1801c2a49  mov     rcx, [rsi]
0x1801c2a4c  mov     rdx, [rcx]
0x1801c2a4f  mov     rax, [rdx+10h]
0x1801c2a53  call    cs:__guard_dispatch_icall_fptr
0x1801c2a59  cmp     qword ptr [rax+18h], 7
0x1801c2a5e  jbe     short loc_1801C2A63
0x1801c2a60  mov     rax, [rax]
0x1801c2a63  mov     [rbp+57h+var_80], rax
0x1801c2a67  lea     rax, aNotWritingAdsS; "Not writing ADS since file doesn't exis"...
0x1801c2a6e  mov     [rbp+57h+var_88], rax
0x1801c2a72  lea     rax, [rbp+57h+var_90]
0x1801c2a76  mov     [rsp+0D0h+hTemplateFile], rax; __int64
0x1801c2a7b  lea     rax, [rbp+57h+var_80]
0x1801c2a7f  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax; __int64
0x1801c2a84  lea     rax, [rbp+57h+var_88]
0x1801c2a88  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; __int64
0x1801c2a8d  lea     rdx, word_1802C54C6; int
0x1801c2a94  mov     rcx, rdi; int
0x1801c2a97  call    ??$Write@U?$_tlgWrapSz@_W@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1801c2a9c  jmp     loc_1801C2CDE
0x1801c2aa1  mov     qword ptr [rbp+57h+CreationTime.dwLowDateTime], 0
0x1801c2aa9  mov     qword ptr [rbp+57h+LastAccessTime.dwLowDateTime], 0
0x1801c2ab1  mov     qword ptr [rbp+57h+LastWriteTime.dwLowDateTime], 0
0x1801c2ab9  lea     r9, [rbp+57h+LastWriteTime]; lpLastWriteTime
0x1801c2abd  lea     r8, [rbp+57h+LastAccessTime]; lpLastAccessTime
0x1801c2ac1  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x1801c2ac5  mov     rcx, rbx; hFile
0x1801c2ac8  call    cs:__imp_GetFileTime
0x1801c2ace  test    eax, eax
0x1801c2ad0  jnz     short loc_1801C2AEE
0x1801c2ad2  mov     rcx, [rbp+5Fh]; this
0x1801c2ad6  lea     r8, aSrcEppDlpFilem_1; "src\\epp\\Dlp\\FileMetadataBroker\\data"...
0x1801c2add  mov     edx, 88h; void *
0x1801c2ae2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801c2ae7  mov     ebx, eax
0x1801c2ae9  jmp     loc_1801C2CDE
0x1801c2aee  lea     rcx, [rbp+57h+lpFileName]
0x1801c2af2  cmp     [rbp+57h+var_48], 7
0x1801c2af7  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1801c2afc  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x1801c2b05  mov     [rsp+0D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1801c2b0d  mov     [rsp+0D0h+dwCreationDisposition], 2; dwCreationDisposition
0x1801c2b15  xor     r9d, r9d; lpSecurityAttributes
0x1801c2b18  mov     edx, 40000000h; dwDesiredAccess
0x1801c2b1d  lea     r8d, [r9+7]; dwShareMode
0x1801c2b21  call    cs:__imp_CreateFileW
0x1801c2b27  mov     rbx, rax
0x1801c2b2a  mov     [rbp+57h+var_80], rax
0x1801c2b2e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801c2b32  jnz     short loc_1801C2B96
0x1801c2b34  call    cs:__imp_GetLastError
0x1801c2b3a  mov     ebx, eax
0x1801c2b3c  test    eax, eax
0x1801c2b3e  jle     short loc_1801C2B49
0x1801c2b40  movzx   ebx, ax
0x1801c2b43  or      ebx, 80070000h
0x1801c2b49  call    ?Provider@FmbTrace@@SAPEBU_tlgProvider_t@@XZ; FmbTrace::Provider(void)
0x1801c2b4e  cmp     dword ptr [rax], 3
0x1801c2b51  jbe     loc_1801C2CD4
0x1801c2b57  lea     rcx, [rbp+57h+lpFileName]
0x1801c2b5b  cmp     [rbp+57h+var_48], 7
0x1801c2b60  cmova   rcx, [rbp+57h+lpFileName]
0x1801c2b65  mov     [rbp+57h+var_88], rcx
0x1801c2b69  lea     rcx, aFailedToCreate_1; "Failed to create ADS file"
0x1801c2b70  mov     [rbp+57h+var_78], rcx
0x1801c2b74  lea     rcx, [rbp+57h+var_90]
0x1801c2b78  mov     [rsp+0D0h+hTemplateFile], rcx
0x1801c2b7d  lea     rcx, [rbp+57h+var_88]
0x1801c2b81  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rcx
0x1801c2b86  lea     rcx, [rbp+57h+var_78]
0x1801c2b8a  lea     rdx, word_1802C554A
0x1801c2b91  jmp     loc_1801C2CC4
0x1801c2b96  mov     [rbp+57h+NumberOfBytesWritten], 0
0x1801c2b9d  mov     qword ptr [rsp+0D0h+dwCreationDisposition], 0; lpOverlapped
0x1801c2ba6  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801c2baa  mov     r8d, edi; nNumberOfBytesToWrite
0x1801c2bad  mov     rdx, r14; lpBuffer
0x1801c2bb0  mov     rcx, rbx; hFile
0x1801c2bb3  call    cs:__imp_WriteFile
0x1801c2bb9  test    eax, eax
0x1801c2bbb  jz      loc_1801C2C6B
0x1801c2bc1  cmp     [rbp+57h+NumberOfBytesWritten], edi
0x1801c2bc4  jnz     loc_1801C2C6B
0x1801c2bca  call    ?Provider@FmbTrace@@SAPEBU_tlgProvider_t@@XZ; FmbTrace::Provider(void)
0x1801c2bcf  cmp     dword ptr [rax], 5
0x1801c2bd2  jbe     short loc_1801C2C12
0x1801c2bd4  lea     rcx, [rbp+57h+lpFileName]
0x1801c2bd8  cmp     [rbp+57h+var_48], 7
0x1801c2bdd  cmova   rcx, [rbp+57h+lpFileName]
0x1801c2be2  mov     [rbp+57h+var_78], rcx
0x1801c2be6  lea     rcx, aSuccessfullyWr; "Successfully wrote DlpInfo data to ADS "...
0x1801c2bed  mov     [rbp+57h+var_88], rcx
0x1801c2bf1  lea     rcx, [rbp+57h+var_78]
0x1801c2bf5  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rcx
0x1801c2bfa  lea     rcx, [rbp+57h+var_88]
0x1801c2bfe  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rcx
0x1801c2c03  lea     rdx, byte_1802C560B
0x1801c2c0a  mov     rcx, rax
0x1801c2c0d  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x1801c2c12  lea     r9, [rbp+57h+LastWriteTime]; lpLastWriteTime
0x1801c2c16  lea     r8, [rbp+57h+LastAccessTime]; lpLastAccessTime
0x1801c2c1a  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x1801c2c1e  mov     rcx, rbx; hFile
0x1801c2c21  call    cs:__imp_SetFileTime
0x1801c2c27  test    eax, eax
0x1801c2c29  jnz     short loc_1801C2C47
0x1801c2c2b  mov     rcx, [rbp+5Fh]; this
0x1801c2c2f  lea     r8, aSrcEppDlpFilem_1; "src\\epp\\Dlp\\FileMetadataBroker\\data"...
0x1801c2c36  mov     edx, 0B1h; void *
0x1801c2c3b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801c2c40  mov     ebx, eax
0x1801c2c42  jmp     loc_1801C2CD4
0x1801c2c47  lea     rcx, [rbp+57h+var_80]
0x1801c2c4b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c2c50  nop
0x1801c2c51  lea     rcx, [rbp+57h+var_70]
0x1801c2c55  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c2c5a  nop
0x1801c2c5b  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801c2c5f  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801c2c64  xor     eax, eax
0x1801c2c66  jmp     loc_1801C2CF3
0x1801c2c6b  call    cs:__imp_GetLastError
0x1801c2c71  mov     ebx, eax
0x1801c2c73  test    eax, eax
0x1801c2c75  jle     short loc_1801C2C80
0x1801c2c77  movzx   ebx, ax
0x1801c2c7a  or      ebx, 80070000h
0x1801c2c80  call    ?Provider@FmbTrace@@SAPEBU_tlgProvider_t@@XZ; FmbTrace::Provider(void)
0x1801c2c85  cmp     dword ptr [rax], 3
0x1801c2c88  jbe     short loc_1801C2CD4
0x1801c2c8a  lea     rcx, [rbp+57h+lpFileName]
0x1801c2c8e  cmp     [rbp+57h+var_48], 7
0x1801c2c93  cmova   rcx, [rbp+57h+lpFileName]
0x1801c2c98  mov     [rbp+57h+var_78], rcx
0x1801c2c9c  lea     rcx, aFailedToWriteD; "Failed to write Dlp Info metadata to AD"...
0x1801c2ca3  mov     [rbp+57h+var_88], rcx
0x1801c2ca7  lea     rcx, [rbp+57h+var_90]
0x1801c2cab  mov     [rsp+0D0h+hTemplateFile], rcx; __int64
0x1801c2cb0  lea     rcx, [rbp+57h+var_78]
0x1801c2cb4  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rcx; __int64
0x1801c2cb9  lea     rcx, [rbp+57h+var_88]
0x1801c2cbd  lea     rdx, dword_1802C5644; int
0x1801c2cc4  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rcx; __int64
0x1801c2cc9  mov     dword ptr [rbp+57h+var_90], ebx
0x1801c2ccc  mov     rcx, rax; int
0x1801c2ccf  call    ??$Write@U?$_tlgWrapSz@_W@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1801c2cd4  lea     rcx, [rbp+57h+var_80]
0x1801c2cd8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c2cdd  nop
0x1801c2cde  lea     rcx, [rbp+57h+var_70]
0x1801c2ce2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c2ce7  nop
0x1801c2ce8  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801c2cec  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801c2cf1  mov     eax, ebx
0x1801c2cf3  mov     rcx, [rbp+57h+var_28]
0x1801c2cf7  xor     rcx, rsp; StackCookie
0x1801c2cfa  call    __security_check_cookie
0x1801c2cff  add     rsp, 0B0h
0x1801c2d06  pop     r14
0x1801c2d08  pop     rdi
0x1801c2d09  pop     rsi
0x1801c2d0a  pop     rbx
0x1801c2d0b  pop     rbp
0x1801c2d0c  retn
```
