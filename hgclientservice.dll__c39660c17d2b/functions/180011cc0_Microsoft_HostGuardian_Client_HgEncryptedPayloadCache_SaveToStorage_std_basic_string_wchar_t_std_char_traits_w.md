# Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::SaveToStorage(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180011cc0`
- end: `0x180011e89`
- name: `?SaveToStorage@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@6@1111@Z`
- size: `457`
- prototype: `char __fastcall(_QWORD *, _QWORD *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180011e90`

## callees

- `0x180001770`
- `0x180004274`
- `0x1800084bc`
- `0x180008760`
- `0x18000a7bc`
- `0x180011848`
- `0x180011cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011df2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011dd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011dd4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180011da2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180011da2`

## string_xrefs

- `0x180011e21`: `servercommon\base\securehostingservice\common\service\lib\hgencryptedpayloadcache.cpp`
- `0x180011e5c`: `servercommon\base\securehostingservice\common\service\lib\hgencryptedpayloadcache.cpp`
- `0x180011e77`: `servercommon\base\securehostingservice\common\service\lib\hgencryptedpayloadcache.cpp`
- `0x180011e0f`: `Failed to open the cached key material file '%ws' for writing.`

## pseudocode

```c
char __fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::SaveToStorage(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  int v9; // ebx
  char *v10; // rdi
  __int64 v11; // rsi
  const char *v12; // r9
  WCHAR *v14; // rax
  int lpOverlapped; // [rsp+20h] [rbp-81h]
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-51h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-49h] BYREF
  _QWORD v18[5]; // [rsp+60h] [rbp-41h]
  WCHAR FileName[8]; // [rsp+88h] [rbp-19h] BYREF
  __m128i si128; // [rsp+98h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]

  v18[0] = a3;
  v18[1] = a4;
  v18[2] = a5;
  v18[3] = a6;
  v18[4] = a7;
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
      0x40000000u,
      0,
      2u,
      0x80000000,
      FileName);
    v10 = (char *)hFile;
    if ( hFile == (HANDLE)-1LL )
      break;
    NumberOfBytesWritten = 0;
    v11 = v18[v9];
    if ( !WriteFile(hFile, *(LPCVOID *)v11, *(_DWORD *)(v11 + 8) - *(_DWORD *)v11, &NumberOfBytesWritten, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xA7,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgencryptedpayloadcache.cpp",
        v12);
    if ( NumberOfBytesWritten != *(_QWORD *)(v11 + 8) - *(_QWORD *)v11 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgencryptedpayloadcache.cpp",
        (const char *)0x8000FFFFLL,
        lpOverlapped);
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v10);
    if ( (unsigned int)++v9 >= 5 )
    {
      std::wstring::~wstring(FileName);
      return 1;
    }
  }
  GetLastError();
  v14 = FileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v14 = *(WCHAR **)FileName;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x9E,
    (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgencryptedpayloadcache.cpp",
    (const char *)1,
    (bool)"Failed to open the cached key material file '%ws' for writing.",
    (const char *)v14);
  std::wstring::~wstring(FileName);
  return 0;
}

```

## disassembly

```asm
0x180011cc0  push    rbp
0x180011cc2  push    rbx
0x180011cc3  push    rsi
0x180011cc4  push    rdi
0x180011cc5  push    r12
0x180011cc7  push    r14
0x180011cc9  push    r15
0x180011ccb  lea     rbp, [rsp-0Fh]
0x180011cd0  sub     rsp, 0B0h
0x180011cd7  mov     rax, cs:__security_cookie
0x180011cde  xor     rax, rsp
0x180011ce1  mov     [rbp+3Fh+var_38], rax
0x180011ce5  mov     r12, rdx
0x180011ce8  mov     r15, rcx
0x180011ceb  mov     rax, [rbp+3Fh+arg_20]
0x180011cef  mov     r10, [rbp+3Fh+arg_28]
0x180011cf3  mov     r11, [rbp+3Fh+arg_30]
0x180011cf7  mov     [rbp+3Fh+var_80], r8
0x180011cfb  mov     [rbp+3Fh+var_78], r9
0x180011cff  mov     [rbp+3Fh+var_70], rax
0x180011d03  mov     [rbp+3Fh+var_68], r10
0x180011d07  mov     [rbp+3Fh+var_60], r11
0x180011d0b  xorps   xmm0, xmm0
0x180011d0e  movups  xmmword ptr [rbp+3Fh+FileName], xmm0
0x180011d12  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180011d1a  movdqu  [rbp+3Fh+var_48], xmm1
0x180011d1f  xor     eax, eax
0x180011d21  mov     [rbp+3Fh+FileName], ax
0x180011d25  xor     ebx, ebx
0x180011d27  movsxd  rsi, ebx
0x180011d2a  lea     r9, ?fileNames@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@0QBQEB_WB; wchar_t const * const near * const Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::fileNames
0x180011d31  lea     rax, [rbp+3Fh+FileName]
0x180011d35  mov     [rsp+0E0h+lpFileName], rax; lpFileName
0x180011d3a  mov     [rsp+0E0h+var_A8], 80000000h; DWORD
0x180011d42  mov     [rsp+0E0h+var_B0], 2; DWORD
0x180011d4a  mov     [rsp+0E0h+dwShareMode], 0; dwShareMode
0x180011d52  mov     dword ptr [rsp+0E0h+lpOverlapped], 40000000h; dwDesiredAccess
0x180011d5a  mov     r9, [r9+rsi*8]; int
0x180011d5e  mov     r8, r12; int
0x180011d61  lea     rdx, [rbp+3Fh+hFile]; int
0x180011d65  mov     rcx, r15; int
0x180011d68  call    ?GetCachedItemHandle@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_WIIIIAEAV78@@Z; Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::GetCachedItemHandle(std::wstring const &,wchar_t const * const,uint,uint,uint,uint,std::wstring &)
0x180011d6d  nop
0x180011d6e  mov     rdi, [rbp+3Fh+hFile]
0x180011d72  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180011d76  jz      short loc_180011DF2
0x180011d78  mov     [rbp+3Fh+NumberOfBytesWritten], 0
0x180011d7f  mov     rsi, [rbp+rsi*8+3Fh+var_80]
0x180011d84  mov     r14, [rbp+47h]
0x180011d88  mov     r8d, [rsi+8]
0x180011d8c  sub     r8d, [rsi]; nNumberOfBytesToWrite
0x180011d8f  mov     [rsp+0E0h+lpOverlapped], 0; int
0x180011d98  lea     r9, [rbp+3Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180011d9c  mov     rdx, [rsi]; lpBuffer
0x180011d9f  mov     rcx, rdi; hFile
0x180011da2  call    cs:__imp_WriteFile
0x180011da8  test    eax, eax
0x180011daa  jz      loc_180011E5C
0x180011db0  mov     rcx, [rbp+47h]; this
0x180011db4  mov     rdx, [rsi+8]
0x180011db8  sub     rdx, [rsi]
0x180011dbb  mov     eax, [rbp+3Fh+NumberOfBytesWritten]
0x180011dbe  cmp     rax, rdx
0x180011dc1  jnz     loc_180011E71
0x180011dc7  lea     rax, [rdi-1]
0x180011dcb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011dcf  ja      short loc_180011DDA
0x180011dd1  mov     rcx, rdi; hObject
0x180011dd4  call    cs:__imp_CloseHandle
0x180011dda  inc     ebx
0x180011ddc  cmp     ebx, 5
0x180011ddf  jb      loc_180011D27
0x180011de5  lea     rcx, [rbp+3Fh+FileName]
0x180011de9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011dee  mov     al, 1
0x180011df0  jmp     short loc_180011E3E
0x180011df2  call    cs:__imp_GetLastError
0x180011df8  lea     rax, [rbp+3Fh+FileName]
0x180011dfc  cmp     qword ptr [rbp+3Fh+var_48+8], 7
0x180011e01  cmova   rax, qword ptr [rbp+3Fh+FileName]
0x180011e06  mov     rcx, [rbp+47h]; this
0x180011e0a  mov     qword ptr [rsp+0E0h+dwShareMode], rax; char *
0x180011e0f  lea     rax, aFailedToOpenTh; "Failed to open the cached key material "...
0x180011e16  mov     [rsp+0E0h+lpOverlapped], rax; bool
0x180011e1b  mov     r9d, 1; char *
0x180011e21  lea     r8, aServercommonBa_7; "servercommon\\base\\securehostingservic"...
0x180011e28  mov     edx, 9Eh; void *
0x180011e2d  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180011e32  nop
0x180011e33  lea     rcx, [rbp+3Fh+FileName]
0x180011e37  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011e3c  xor     al, al
0x180011e3e  mov     rcx, [rbp+3Fh+var_38]
0x180011e42  xor     rcx, rsp; StackCookie
0x180011e45  call    __security_check_cookie
0x180011e4a  add     rsp, 0B0h
0x180011e51  pop     r15
0x180011e53  pop     r14
0x180011e55  pop     r12
0x180011e57  pop     rdi
0x180011e58  pop     rsi
0x180011e59  pop     rbx
0x180011e5a  pop     rbp
0x180011e5b  retn
0x180011e5c  lea     r8, aServercommonBa_7; "servercommon\\base\\securehostingservic"...
0x180011e63  mov     edx, 0A7h; void *
0x180011e68  mov     rcx, r14; this
0x180011e6b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180011e71  mov     r9d, 8000FFFFh; char *
0x180011e77  lea     r8, aServercommonBa_7; "servercommon\\base\\securehostingservic"...
0x180011e7e  mov     edx, 0A8h; void *
0x180011e83  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
