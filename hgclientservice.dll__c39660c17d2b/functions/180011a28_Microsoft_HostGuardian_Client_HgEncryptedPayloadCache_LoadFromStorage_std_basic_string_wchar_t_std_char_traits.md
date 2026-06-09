# Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::LoadFromStorage(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<uchar,std::allocator<uchar>> &,std::vector<uchar,std::allocator<uchar>> &,std::vector<uchar,std::allocator<uchar>> &,std::vector<uchar,std::allocator<uchar>> &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180011a28`
- end: `0x180011cb7`
- name: `?LoadFromStorage@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@6@1111@Z`
- size: `655`
- prototype: `char __fastcall(_QWORD *, _QWORD *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180011600`

## callees

- `0x180001770`
- `0x1800021f0`
- `0x180004274`
- `0x1800084bc`
- `0x180008760`
- `0x18000a7bc`
- `0x180011400`
- `0x180011848`
- `0x180011a28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011bce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011bce`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180011bb3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180011bb3`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180011b0a`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180011b0a`

## string_xrefs

- `0x180011c1b`: `servercommon\base\securehostingservice\common\service\lib\hgencryptedpayloadcache.cpp`
- `0x180011c75`: `servercommon\base\securehostingservice\common\service\lib\hgencryptedpayloadcache.cpp`
- `0x180011c8a`: `servercommon\base\securehostingservice\common\service\lib\hgencryptedpayloadcache.cpp`
- `0x180011ca5`: `servercommon\base\securehostingservice\common\service\lib\hgencryptedpayloadcache.cpp`
- `0x180011c09`: `Failed to open the cached key material file '%ws' for reading.`

## pseudocode

```c
char __fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::LoadFromStorage(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  int v9; // ebx
  char *v10; // r14
  const char *v11; // r9
  DWORD nFileSizeLow; // r8d
  LPVOID *v14; // rsi
  char *v15; // rdx
  char *v16; // r15
  unsigned __int64 v17; // rcx
  char *v18; // rax
  size_t v19; // rdi
  const char *v20; // r9
  WCHAR *v22; // rax
  _QWORD *v23; // rcx
  int lpOverlapped; // [rsp+20h] [rbp-D1h]
  HANDLE hFile; // [rsp+58h] [rbp-99h] BYREF
  _QWORD v26[5]; // [rsp+60h] [rbp-91h]
  WCHAR FileName[8]; // [rsp+88h] [rbp-69h] BYREF
  __m128i si128; // [rsp+98h] [rbp-59h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+A8h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+47h]

  v26[0] = a3;
  v26[1] = a4;
  v26[2] = a5;
  v26[3] = a6;
  v26[4] = a7;
  *(_OWORD *)FileName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  FileName[0] = 0;
  v9 = 0;
  while ( 1 )
  {
    Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::GetCachedItemHandle(
      a1,
      &hFile,
      a2,
      (__int64)(&Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::fileNames)[v9],
      0x80000000,
      1u,
      3u,
      0x8000000u,
      FileName);
    v10 = (char *)hFile;
    if ( hFile == (HANDLE)-1LL )
      break;
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( !GetFileInformationByHandle(hFile, &FileInformation) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xE3,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgencryptedpayloadcache.cpp",
        v11);
    nFileSizeLow = FileInformation.nFileSizeLow;
    if ( !*(_QWORD *)&FileInformation.nFileSizeHigh
      || FileInformation.nFileSizeHigh
      || FileInformation.nFileSizeLow > 0xFFFF )
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgencryptedpayloadcache.cpp",
        (const char *)0x8000FFFFLL,
        lpOverlapped);
    }
    v14 = (LPVOID *)v26[v9];
    v15 = (char *)*v14;
    v16 = (char *)v14[1];
    v17 = v16 - (_BYTE *)*v14;
    if ( FileInformation.nFileSizeLow < v17 )
    {
      v18 = &v15[FileInformation.nFileSizeLow];
      goto LABEL_16;
    }
    if ( FileInformation.nFileSizeLow > v17 )
    {
      if ( FileInformation.nFileSizeLow <= (unsigned __int64)((_BYTE *)v14[2] - v15) )
      {
        v19 = FileInformation.nFileSizeLow - v17;
        memset_0(v14[1], 0, v19);
        v18 = &v16[v19];
LABEL_16:
        v14[1] = v18;
      }
      else
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v14, FileInformation.nFileSizeLow);
      }
      nFileSizeLow = FileInformation.nFileSizeLow;
    }
    if ( !ReadFile(v10, *v14, nFileSizeLow, &FileInformation.nFileSizeHigh, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xED,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgencryptedpayloadcache.cpp",
        v20);
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v10);
    if ( (unsigned int)++v9 >= 5 )
    {
      std::wstring::~wstring(FileName);
      return 1;
    }
  }
  GetLastError();
  v22 = FileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v22 = *(WCHAR **)FileName;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xD7,
    (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgencryptedpayloadcache.cpp",
    (const char *)1,
    (bool)"Failed to open the cached key material file '%ws' for reading.",
    (const char *)v22);
  while ( v9 > -1 )
  {
    v23 = (_QWORD *)v26[v9];
    if ( *v23 != v23[1] )
      v23[1] = *v23;
    --v9;
  }
  std::wstring::~wstring(FileName);
  return 0;
}

```

## disassembly

```asm
0x180011a28  push    rbp
0x180011a2a  push    rbx
0x180011a2b  push    rsi
0x180011a2c  push    rdi
0x180011a2d  push    r12
0x180011a2f  push    r13
0x180011a31  push    r14
0x180011a33  push    r15
0x180011a35  lea     rbp, [rsp-7]
0x180011a3a  sub     rsp, 0F8h
0x180011a41  mov     rax, cs:__security_cookie
0x180011a48  xor     rax, rsp
0x180011a4b  mov     [rbp+3Fh+var_50], rax
0x180011a4f  mov     r13, rdx
0x180011a52  mov     r12, rcx
0x180011a55  mov     rax, [rbp+3Fh+arg_20]
0x180011a59  mov     r10, [rbp+3Fh+arg_28]
0x180011a5d  mov     r11, [rbp+3Fh+arg_30]
0x180011a61  mov     [rsp+130h+var_D0], r8
0x180011a66  mov     [rsp+130h+var_C8], r9
0x180011a6b  mov     [rsp+130h+var_C0], rax
0x180011a70  mov     [rbp+3Fh+var_B8], r10
0x180011a74  mov     [rbp+3Fh+var_B0], r11
0x180011a78  xorps   xmm0, xmm0
0x180011a7b  movups  xmmword ptr [rbp+3Fh+FileName], xmm0
0x180011a7f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180011a87  movdqu  [rbp+3Fh+var_98], xmm1
0x180011a8c  xor     eax, eax
0x180011a8e  mov     [rbp+3Fh+FileName], ax
0x180011a92  xor     ebx, ebx
0x180011a94  movsxd  rsi, ebx
0x180011a97  lea     r9, ?fileNames@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@0QBQEB_WB; wchar_t const * const near * const Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::fileNames
0x180011a9e  lea     rax, [rbp+3Fh+FileName]
0x180011aa2  mov     [rsp+130h+lpFileName], rax; lpFileName
0x180011aa7  mov     [rsp+130h+var_F8], 8000000h; DWORD
0x180011aaf  mov     [rsp+130h+var_100], 3; DWORD
0x180011ab7  mov     [rsp+130h+dwShareMode], 1; dwShareMode
0x180011abf  mov     dword ptr [rsp+130h+lpOverlapped], 80000000h; int
0x180011ac7  mov     r9, [r9+rsi*8]; int
0x180011acb  mov     r8, r13; int
0x180011ace  lea     rdx, [rsp+130h+hFile]; int
0x180011ad3  mov     rcx, r12; int
0x180011ad6  call    ?GetCachedItemHandle@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_WIIIIAEAV78@@Z; Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::GetCachedItemHandle(std::wstring const &,wchar_t const * const,uint,uint,uint,uint,std::wstring &)
0x180011adb  nop
0x180011adc  mov     r14, [rsp+130h+hFile]
0x180011ae1  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180011ae5  jz      loc_180011BEC
0x180011aeb  xorps   xmm0, xmm0
0x180011aee  xor     eax, eax
0x180011af0  movups  xmmword ptr [rbp+3Fh+FileInformation.dwFileAttributes], xmm0
0x180011af4  movups  xmmword ptr [rbp+3Fh+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180011af8  movups  xmmword ptr [rbp+3Fh+FileInformation.nFileSizeHigh], xmm0
0x180011afc  mov     [rbp+3Fh+FileInformation.nFileIndexLow], eax
0x180011aff  mov     rdi, [rbp+47h]
0x180011b03  lea     rdx, [rbp+3Fh+FileInformation]; lpFileInformation
0x180011b07  mov     rcx, r14; hFile
0x180011b0a  call    cs:__imp_GetFileInformationByHandle
0x180011b10  test    eax, eax
0x180011b12  jz      loc_180011C75
0x180011b18  mov     ecx, [rbp+3Fh+FileInformation.nFileSizeHigh]
0x180011b1b  mov     eax, ecx
0x180011b1d  mov     r8d, [rbp+3Fh+FileInformation.nFileSizeLow]
0x180011b21  or      eax, r8d
0x180011b24  jz      short loc_180011B37
0x180011b26  test    ecx, ecx
0x180011b28  jnz     short loc_180011B37
0x180011b2a  cmp     r8d, 0FFFFh
0x180011b31  ja      short loc_180011B37
0x180011b33  xor     al, al
0x180011b35  jmp     short loc_180011B39
0x180011b37  mov     al, 1
0x180011b39  mov     rcx, [rbp+47h]; this
0x180011b3d  test    al, al
0x180011b3f  jnz     loc_180011C9F
0x180011b45  mov     rsi, [rsp+rsi*8+130h+var_D0]
0x180011b4a  mov     rdi, r8
0x180011b4d  mov     rdx, [rsi]
0x180011b50  mov     r15, [rsi+8]
0x180011b54  mov     rcx, r15
0x180011b57  sub     rcx, rdx
0x180011b5a  cmp     r8, rcx
0x180011b5d  jnb     short loc_180011B65
0x180011b5f  lea     rax, [rdx+r8]
0x180011b63  jmp     short loc_180011B94
0x180011b65  jbe     short loc_180011B9C
0x180011b67  mov     rax, [rsi+10h]
0x180011b6b  sub     rax, rdx
0x180011b6e  cmp     rdi, rax
0x180011b71  jbe     short loc_180011B80
0x180011b73  mov     rdx, rdi
0x180011b76  mov     rcx, rsi
0x180011b79  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180011b7e  jmp     short loc_180011B98
0x180011b80  sub     rdi, rcx
0x180011b83  mov     r8, rdi; Size
0x180011b86  xor     edx, edx; Val
0x180011b88  mov     rcx, r15; void *
0x180011b8b  call    memset_0
0x180011b90  lea     rax, [rdi+r15]
0x180011b94  mov     [rsi+8], rax
0x180011b98  mov     r8d, [rbp+3Fh+FileInformation.nFileSizeLow]; nNumberOfBytesToRead
0x180011b9c  mov     rdi, [rbp+47h]
0x180011ba0  mov     [rsp+130h+lpOverlapped], 0; lpOverlapped
0x180011ba9  lea     r9, [rbp+3Fh+FileInformation.nFileSizeHigh]; lpNumberOfBytesRead
0x180011bad  mov     rdx, [rsi]; lpBuffer
0x180011bb0  mov     rcx, r14; hFile
0x180011bb3  call    cs:__imp_ReadFile
0x180011bb9  test    eax, eax
0x180011bbb  jz      loc_180011C8A
0x180011bc1  lea     rax, [r14-1]
0x180011bc5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011bc9  ja      short loc_180011BD4
0x180011bcb  mov     rcx, r14; hObject
0x180011bce  call    cs:__imp_CloseHandle
0x180011bd4  inc     ebx
0x180011bd6  cmp     ebx, 5
0x180011bd9  jb      loc_180011A94
0x180011bdf  lea     rcx, [rbp+3Fh+FileName]
0x180011be3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011be8  mov     al, 1
0x180011bea  jmp     short loc_180011C55
0x180011bec  call    cs:__imp_GetLastError
0x180011bf2  lea     rax, [rbp+3Fh+FileName]
0x180011bf6  cmp     qword ptr [rbp+3Fh+var_98+8], 7
0x180011bfb  cmova   rax, qword ptr [rbp+3Fh+FileName]
0x180011c00  mov     rcx, [rbp+47h]; this
0x180011c04  mov     qword ptr [rsp+130h+dwShareMode], rax; char *
0x180011c09  lea     rax, aFailedToOpenTh_0; "Failed to open the cached key material "...
0x180011c10  mov     [rsp+130h+lpOverlapped], rax; bool
0x180011c15  mov     r9d, 1; char *
0x180011c1b  lea     r8, aServercommonBa_7; "servercommon\\base\\securehostingservic"...
0x180011c22  mov     edx, 0D7h; void *
0x180011c27  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180011c2c  jmp     short loc_180011C45
0x180011c2e  movsxd  rax, ebx
0x180011c31  mov     rcx, [rsp+rax*8+130h+var_D0]
0x180011c36  mov     rax, [rcx]
0x180011c39  cmp     rax, [rcx+8]
0x180011c3d  jz      short loc_180011C43
0x180011c3f  mov     [rcx+8], rax
0x180011c43  dec     ebx
0x180011c45  cmp     ebx, 0FFFFFFFFh
0x180011c48  jg      short loc_180011C2E
0x180011c4a  lea     rcx, [rbp+3Fh+FileName]
0x180011c4e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011c53  xor     al, al
0x180011c55  mov     rcx, [rbp+3Fh+var_50]
0x180011c59  xor     rcx, rsp; StackCookie
0x180011c5c  call    __security_check_cookie
0x180011c61  add     rsp, 0F8h
0x180011c68  pop     r15
0x180011c6a  pop     r14
0x180011c6c  pop     r13
0x180011c6e  pop     r12
0x180011c70  pop     rdi
0x180011c71  pop     rsi
0x180011c72  pop     rbx
0x180011c73  pop     rbp
0x180011c74  retn
0x180011c75  lea     r8, aServercommonBa_7; "servercommon\\base\\securehostingservic"...
0x180011c7c  mov     edx, 0E3h; void *
0x180011c81  mov     rcx, rdi; this
0x180011c84  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180011c8a  lea     r8, aServercommonBa_7; "servercommon\\base\\securehostingservic"...
0x180011c91  mov     edx, 0EDh; void *
0x180011c96  mov     rcx, rdi; this
0x180011c99  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180011c9f  mov     r9d, 8000FFFFh; char *
0x180011ca5  lea     r8, aServercommonBa_7; "servercommon\\base\\securehostingservic"...
0x180011cac  mov     edx, 0E6h; void *
0x180011cb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
