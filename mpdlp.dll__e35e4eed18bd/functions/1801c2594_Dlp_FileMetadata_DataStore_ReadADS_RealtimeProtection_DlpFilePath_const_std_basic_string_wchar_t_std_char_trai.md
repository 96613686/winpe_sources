# Dlp::FileMetadata::DataStore::ReadADS(RealtimeProtection::DlpFilePath const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::optional<std::vector<uchar,std::allocator<uchar>>> &)

- ea: `0x1801c2594`
- end: `0x1801c28f0`
- name: `?ReadADS@DataStore@FileMetadata@Dlp@@YAJAEBVDlpFilePath@RealtimeProtection@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$optional@V?$vector@EV?$allocator@E@std@@@std@@@7@@Z`
- size: `860`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1801bcba8`

## callees

- `0x180002c84`
- `0x180004f3c`
- `0x180034420`
- `0x180065394`
- `0x180065438`
- `0x1800a1824`
- `0x1800a1860`
- `0x1800cba98`
- `0x18010cb40`
- `0x18016d82c`
- `0x1801c2498`
- `0x1801c2594`
- `0x18023a290`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1801c2804`
- `KERNEL32!ReadFile` at `0x1801c2804`
- `KERNEL32!GetFileSize` at `0x1801c2741`
- `KERNEL32!GetFileSize` at `0x1801c2741`
- `KERNEL32!GetLastError` at `0x1801c2674`
- `KERNEL32!GetLastError` at `0x1801c2753`
- `KERNEL32!GetLastError` at `0x1801c2844`
- `KERNEL32!GetLastError` at `0x1801c2674`
- `KERNEL32!GetLastError` at `0x1801c2753`
- `KERNEL32!GetLastError` at `0x1801c2844`
- `KERNEL32!CreateFileW` at `0x1801c265d`
- `KERNEL32!CreateFileW` at `0x1801c265d`

## string_xrefs

- `0x1801c2878`: `Could not read ADS file`
- `0x1801c25e2`: `src\epp\Dlp\FileMetadataBroker\data_store\fs_utils\src\rw_ads.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Dlp::FileMetadata::DataStore::ReadADS(_QWORD *a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // edi
  __int64 v6; // rdx
  unsigned int v7; // ebx
  const WCHAR *v8; // rcx
  HANDLE FileW; // rax
  void *v10; // rbx
  signed int LastError; // eax
  unsigned int v12; // ebx
  const struct _tlgProvider_t *v13; // rax
  int v14; // r8d
  int v15; // r9d
  LPCWSTR *v16; // rcx
  LPCWSTR *v17; // rcx
  __int64 *v18; // rcx
  char *v19; // rdx
  DWORD FileSize; // eax
  DWORD v21; // r14d
  signed int v22; // eax
  LPCWSTR *v23; // rcx
  signed int v25; // eax
  const struct _tlgProvider_t *v26; // rax
  LPCWSTR *v27; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-49h]
  __int64 *dwFlagsAndAttributes; // [rsp+28h] [rbp-41h]
  __int64 v30; // [rsp+40h] [rbp-29h] BYREF
  __int64 v31; // [rsp+48h] [rbp-21h] BYREF
  __int64 v32; // [rsp+50h] [rbp-19h] BYREF
  HANDLE v33; // [rsp+58h] [rbp-11h] BYREF
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp-9h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int64 v36; // [rsp+80h] [rbp+17h]
  LPVOID lpBuffer[2]; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v38; // [rsp+98h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v5 = 0;
  if ( !*(_QWORD *)((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1) + 16) )
  {
    v6 = 30;
LABEL_3:
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"src\\epp\\Dlp\\FileMetadataBroker\\data_store\\fs_utils\\src\\rw_ads.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return v7;
  }
  if ( !qword_180311AB8 )
  {
    v6 = 31;
    goto LABEL_3;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
  std::operator+<wchar_t>(lpFileName);
  v8 = (const WCHAR *)lpFileName;
  if ( v36 > 7 )
    v8 = lpFileName[0];
  FileW = CreateFileW(v8, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v10 = FileW;
  v33 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    v13 = FmbTrace::Provider();
    if ( v12 == -2147024894 )
    {
      if ( *(_DWORD *)v13 > 4u )
      {
        v16 = lpFileName;
        if ( v36 > 7 )
          v16 = (LPCWSTR *)lpFileName[0];
        v30 = (__int64)v16;
        v31 = (__int64)L"ADS is not present";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
          (_DWORD)v13,
          (unsigned int)&word_1802C558E,
          v14,
          v15,
          (__int64)&v31,
          (__int64)&v30);
      }
      if ( *(_BYTE *)(a3 + 24) )
      {
        std::vector<unsigned char>::_Tidy(a3);
        *(_BYTE *)(a3 + 24) = 0;
      }
      goto LABEL_31;
    }
    if ( *(_DWORD *)v13 <= 3u )
    {
LABEL_30:
      v5 = v12;
LABEL_31:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpFileName);
      return v5;
    }
    v17 = lpFileName;
    if ( v36 > 7 )
      v17 = (LPCWSTR *)lpFileName[0];
    v31 = (__int64)v17;
    v32 = (__int64)L"Invalid ADS file handle";
    dwFlagsAndAttributes = &v31;
    v18 = &v32;
    v19 = &byte_1802C55C7;
LABEL_29:
    LODWORD(v30) = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      (int)v13,
      (int)v19,
      (__int64)v18,
      (__int64)dwFlagsAndAttributes,
      (__int64)&v30);
    goto LABEL_30;
  }
  NumberOfBytesRead = 0;
  FileSize = GetFileSize(FileW, 0);
  v21 = FileSize;
  if ( FileSize == -1 )
  {
    v22 = GetLastError();
    v12 = v22;
    if ( v22 > 0 )
      v12 = (unsigned __int16)v22 | 0x80070000;
    v13 = FmbTrace::Provider();
    if ( *(_DWORD *)v13 <= 3u )
      goto LABEL_30;
    v23 = lpFileName;
    if ( v36 > 7 )
      v23 = (LPCWSTR *)lpFileName[0];
    v32 = (__int64)v23;
    v31 = (__int64)L"Invalid ADS file size";
    dwFlagsAndAttributes = &v32;
    v18 = &v31;
    v19 = (char *)&word_1802C5482;
    goto LABEL_29;
  }
  *(_OWORD *)lpBuffer = 0;
  v38 = 0;
  std::vector<unsigned char>::vector<unsigned char>(lpBuffer, FileSize);
  if ( ReadFile(v10, lpBuffer[0], v21, &NumberOfBytesRead, 0) && NumberOfBytesRead == v21 )
  {
    std::optional<std::vector<unsigned char>>::operator=<std::vector<unsigned char>,0>(a3, lpBuffer);
    std::vector<unsigned char>::_Tidy(lpBuffer);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpFileName);
    return 0;
  }
  v25 = GetLastError();
  v7 = v25;
  if ( v25 > 0 )
    v7 = (unsigned __int16)v25 | 0x80070000;
  v26 = FmbTrace::Provider();
  if ( *(_DWORD *)v26 > 3u )
  {
    LODWORD(v30) = v7;
    v27 = lpFileName;
    if ( v36 > 7 )
      v27 = (LPCWSTR *)lpFileName[0];
    v32 = (__int64)v27;
    v31 = (__int64)L"Could not read ADS file";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      (int)v26,
      (int)&word_1802C5506,
      (__int64)&v31,
      (__int64)&v32,
      (__int64)&v30);
  }
  std::vector<unsigned char>::_Tidy(lpBuffer);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpFileName);
  return v7;
}

```

## disassembly

```asm
0x1801c2594  mov     [rsp-8+arg_8], rbx
0x1801c2599  mov     [rsp-8+arg_18], rsi
0x1801c259e  push    rbp
0x1801c259f  push    rdi
0x1801c25a0  push    r14
0x1801c25a2  lea     rbp, [rsp-47h]
0x1801c25a7  sub     rsp, 0B0h
0x1801c25ae  mov     rax, cs:__security_cookie
0x1801c25b5  xor     rax, rsp
0x1801c25b8  mov     [rbp+57h+var_20], rax
0x1801c25bc  mov     rsi, r8
0x1801c25bf  mov     rbx, rcx
0x1801c25c2  mov     rcx, [rcx]
0x1801c25c5  mov     rax, [rcx]
0x1801c25c8  mov     rax, [rax+10h]
0x1801c25cc  call    cs:__guard_dispatch_icall_fptr
0x1801c25d2  xor     edi, edi
0x1801c25d4  cmp     [rax+10h], rdi
0x1801c25d8  jnz     short loc_1801C25FA
0x1801c25da  lea     edx, [rdi+1Eh]; void *
0x1801c25dd  mov     ebx, 80070057h
0x1801c25e2  lea     r8, aSrcEppDlpFilem_1; "src\\epp\\Dlp\\FileMetadataBroker\\data"...
0x1801c25e9  mov     r9d, ebx; char *
0x1801c25ec  mov     rcx, [rbp+5Fh]; this
0x1801c25f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c25f5  jmp     loc_1801C28CA
0x1801c25fa  cmp     cs:qword_180311AB8, rdi
0x1801c2601  jnz     short loc_1801C260A
0x1801c2603  mov     edx, 1Fh
0x1801c2608  jmp     short loc_1801C25DD
0x1801c260a  mov     rcx, [rbx]
0x1801c260d  mov     rax, [rcx]
0x1801c2610  mov     rax, [rax+10h]
0x1801c2614  call    cs:__guard_dispatch_icall_fptr
0x1801c261a  lea     r8, qword_180311AA8
0x1801c2621  mov     rdx, rax
0x1801c2624  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801c2628  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@0@Z; std::operator+<wchar_t>(std::wstring const &,std::wstring const &)
0x1801c262d  nop
0x1801c262e  lea     rcx, [rbp+57h+lpFileName]
0x1801c2632  cmp     [rbp+57h+var_40], 7
0x1801c2637  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1801c263c  mov     [rsp+0C0h+hTemplateFile], rdi; hTemplateFile
0x1801c2641  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1801c2649  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x1801c2651  xor     r9d, r9d; lpSecurityAttributes
0x1801c2654  mov     edx, 80000000h; dwDesiredAccess
0x1801c2659  lea     r8d, [r9+7]; dwShareMode
0x1801c265d  call    cs:__imp_CreateFileW
0x1801c2663  mov     rbx, rax
0x1801c2666  mov     [rbp+57h+var_68], rax
0x1801c266a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801c266e  jnz     loc_1801C2739
0x1801c2674  call    cs:__imp_GetLastError
0x1801c267a  mov     ebx, eax
0x1801c267c  test    eax, eax
0x1801c267e  jle     short loc_1801C2689
0x1801c2680  movzx   ebx, ax
0x1801c2683  or      ebx, 80070000h
0x1801c2689  call    ?Provider@FmbTrace@@SAPEBU_tlgProvider_t@@XZ; FmbTrace::Provider(void)
0x1801c268e  cmp     ebx, 80070002h
0x1801c2694  jnz     short loc_1801C26F4
0x1801c2696  cmp     dword ptr [rax], 4
0x1801c2699  jbe     short loc_1801C26D9
0x1801c269b  lea     rcx, [rbp+57h+lpFileName]
0x1801c269f  cmp     [rbp+57h+var_40], 7
0x1801c26a4  cmova   rcx, [rbp+57h+lpFileName]
0x1801c26a9  mov     [rbp+57h+var_80], rcx
0x1801c26ad  lea     rcx, aAdsIsNotPresen; "ADS is not present"
0x1801c26b4  mov     [rbp+57h+var_78], rcx
0x1801c26b8  lea     rcx, [rbp+57h+var_80]
0x1801c26bc  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rcx
0x1801c26c1  lea     rcx, [rbp+57h+var_78]
0x1801c26c5  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx
0x1801c26ca  lea     rdx, word_1802C558E
0x1801c26d1  mov     rcx, rax
0x1801c26d4  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x1801c26d9  cmp     [rsi+18h], dil
0x1801c26dd  jz      loc_1801C27BE
0x1801c26e3  mov     rcx, rsi
0x1801c26e6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801c26eb  mov     [rsi+18h], dil
0x1801c26ef  jmp     loc_1801C27BE
0x1801c26f4  cmp     dword ptr [rax], 3
0x1801c26f7  jbe     loc_1801C27BC
0x1801c26fd  lea     rcx, [rbp+57h+lpFileName]
0x1801c2701  cmp     [rbp+57h+var_40], 7
0x1801c2706  cmova   rcx, [rbp+57h+lpFileName]
0x1801c270b  mov     [rbp+57h+var_78], rcx
0x1801c270f  lea     rcx, aInvalidAdsFile; "Invalid ADS file handle"
0x1801c2716  mov     [rbp+57h+var_70], rcx
0x1801c271a  lea     rcx, [rbp+57h+var_80]
0x1801c271e  mov     [rsp+0C0h+hTemplateFile], rcx
0x1801c2723  lea     rcx, [rbp+57h+var_78]
0x1801c2727  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rcx
0x1801c272c  lea     rcx, [rbp+57h+var_70]
0x1801c2730  lea     rdx, byte_1802C55C7
0x1801c2737  jmp     short loc_1801C27AC
0x1801c2739  mov     [rbp+57h+NumberOfBytesRead], edi
0x1801c273c  xor     edx, edx; lpFileSizeHigh
0x1801c273e  mov     rcx, rbx; hFile
0x1801c2741  call    cs:__imp_GetFileSize
0x1801c2747  mov     r14d, eax
0x1801c274a  cmp     eax, 0FFFFFFFFh
0x1801c274d  jnz     loc_1801C27D8
0x1801c2753  call    cs:__imp_GetLastError
0x1801c2759  mov     ebx, eax
0x1801c275b  test    eax, eax
0x1801c275d  jle     short loc_1801C2768
0x1801c275f  movzx   ebx, ax
0x1801c2762  or      ebx, 80070000h
0x1801c2768  call    ?Provider@FmbTrace@@SAPEBU_tlgProvider_t@@XZ; FmbTrace::Provider(void)
0x1801c276d  cmp     dword ptr [rax], 3
0x1801c2770  jbe     short loc_1801C27BC
0x1801c2772  lea     rcx, [rbp+57h+lpFileName]
0x1801c2776  cmp     [rbp+57h+var_40], 7
0x1801c277b  cmova   rcx, [rbp+57h+lpFileName]
0x1801c2780  mov     [rbp+57h+var_70], rcx
0x1801c2784  lea     rcx, aInvalidAdsFile_0; "Invalid ADS file size"
0x1801c278b  mov     [rbp+57h+var_78], rcx
0x1801c278f  lea     rcx, [rbp+57h+var_80]
0x1801c2793  mov     [rsp+0C0h+hTemplateFile], rcx; __int64
0x1801c2798  lea     rcx, [rbp+57h+var_70]
0x1801c279c  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rcx; __int64
0x1801c27a1  lea     rcx, [rbp+57h+var_78]
0x1801c27a5  lea     rdx, word_1802C5482; int
0x1801c27ac  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx; __int64
0x1801c27b1  mov     dword ptr [rbp+57h+var_80], ebx
0x1801c27b4  mov     rcx, rax; int
0x1801c27b7  call    ??$Write@U?$_tlgWrapSz@_W@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1801c27bc  mov     edi, ebx
0x1801c27be  lea     rcx, [rbp+57h+var_68]
0x1801c27c2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c27c7  nop
0x1801c27c8  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801c27cc  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801c27d1  mov     eax, edi
0x1801c27d3  jmp     loc_1801C28CC
0x1801c27d8  xorps   xmm0, xmm0
0x1801c27db  xor     eax, eax
0x1801c27dd  movups  xmmword ptr [rbp+57h+lpBuffer], xmm0
0x1801c27e1  mov     [rbp+57h+var_28], rax
0x1801c27e5  mov     rdx, r14
0x1801c27e8  lea     rcx, [rbp+57h+lpBuffer]
0x1801c27ec  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1801c27f1  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdi; lpOverlapped
0x1801c27f6  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801c27fa  mov     r8d, r14d; nNumberOfBytesToRead
0x1801c27fd  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x1801c2801  mov     rcx, rbx; hFile
0x1801c2804  call    cs:__imp_ReadFile
0x1801c280a  test    eax, eax
0x1801c280c  jz      short loc_1801C2844
0x1801c280e  cmp     [rbp+57h+NumberOfBytesRead], r14d
0x1801c2812  jnz     short loc_1801C2844
0x1801c2814  lea     rdx, [rbp+57h+lpBuffer]
0x1801c2818  mov     rcx, rsi
0x1801c281b  call    ??$?4V?$vector@EV?$allocator@E@std@@@std@@$0A@@?$optional@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAAEAV01@$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::optional<std::vector<uchar>>::operator=<std::vector<uchar>,0>(std::vector<uchar> &&)
0x1801c2820  lea     rcx, [rbp+57h+lpBuffer]
0x1801c2824  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801c2829  nop
0x1801c282a  lea     rcx, [rbp+57h+var_68]
0x1801c282e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c2833  nop
0x1801c2834  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801c2838  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801c283d  xor     eax, eax
0x1801c283f  jmp     loc_1801C28CC
0x1801c2844  call    cs:__imp_GetLastError
0x1801c284a  mov     ebx, eax
0x1801c284c  test    eax, eax
0x1801c284e  jle     short loc_1801C2859
0x1801c2850  movzx   ebx, ax
0x1801c2853  or      ebx, 80070000h
0x1801c2859  call    ?Provider@FmbTrace@@SAPEBU_tlgProvider_t@@XZ; FmbTrace::Provider(void)
0x1801c285e  cmp     dword ptr [rax], 3
0x1801c2861  jbe     short loc_1801C28AD
0x1801c2863  mov     dword ptr [rbp+57h+var_80], ebx
0x1801c2866  lea     rcx, [rbp+57h+lpFileName]
0x1801c286a  cmp     [rbp+57h+var_40], 7
0x1801c286f  cmova   rcx, [rbp+57h+lpFileName]
0x1801c2874  mov     [rbp+57h+var_70], rcx
0x1801c2878  lea     rcx, aCouldNotReadAd; "Could not read ADS file"
0x1801c287f  mov     [rbp+57h+var_78], rcx
0x1801c2883  lea     rcx, [rbp+57h+var_80]
0x1801c2887  mov     [rsp+0C0h+hTemplateFile], rcx; __int64
0x1801c288c  lea     rcx, [rbp+57h+var_70]
0x1801c2890  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rcx; __int64
0x1801c2895  lea     rcx, [rbp+57h+var_78]
0x1801c2899  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx; __int64
0x1801c289e  lea     rdx, word_1802C5506; int
0x1801c28a5  mov     rcx, rax; int
0x1801c28a8  call    ??$Write@U?$_tlgWrapSz@_W@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1801c28ad  lea     rcx, [rbp+57h+lpBuffer]
0x1801c28b1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801c28b6  nop
0x1801c28b7  lea     rcx, [rbp+57h+var_68]
0x1801c28bb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c28c0  nop
0x1801c28c1  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801c28c5  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801c28ca  mov     eax, ebx
0x1801c28cc  mov     rcx, [rbp+57h+var_20]
0x1801c28d0  xor     rcx, rsp; StackCookie
0x1801c28d3  call    __security_check_cookie
0x1801c28d8  lea     r11, [rsp+0C0h+var_10]
0x1801c28e0  mov     rbx, [r11+28h]
0x1801c28e4  mov     rsi, [r11+38h]
0x1801c28e8  mov     rsp, r11
0x1801c28eb  pop     r14
0x1801c28ed  pop     rdi
0x1801c28ee  pop     rbp
0x1801c28ef  retn
```
