# DeleteOldestLogFiles

- ea: `0x140012b88`
- end: `0x140012f4b`
- name: `DeleteOldestLogFiles`
- size: `963`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140013288`

## callees

- `0x140002360`
- `0x140002d98`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x14000726c`
- `0x14000952c`
- `0x140011100`
- `0x1400113d4`
- `0x140011884`
- `0x140012a58`
- `0x140012b88`
- `0x1400237c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012df8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140012dd4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140012dd4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140012d81`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140012d81`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140012ca2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140012ca2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140012ce0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140012ce0`

## string_xrefs

- `0x140012e0c`: `Failed to delete oldest backup log.`

## pseudocode

```c
__int64 __fastcall DeleteOldestLogFiles(__int64 a1)
{
  int Property; // eax
  unsigned int v3; // esi
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // eax
  HANDLE FirstFileW; // rax
  void *v9; // rbx
  unsigned int v10; // edi
  _OWORD *v11; // rax
  _WIN32_FIND_DATAW *p_FindFileData; // rcx
  __int64 v13; // rdx
  int v14; // eax
  signed int LastError; // ebx
  int v16; // edx
  unsigned int v17; // eax
  unsigned int v18; // [rsp+28h] [rbp-E0h]
  unsigned int v19[2]; // [rsp+38h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C8h] BYREF
  LPCWSTR v21; // [rsp+48h] [rbp-C0h] BYREF
  HANDLE v22; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v23[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A8h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v26[20]; // [rsp+2B8h] [rbp+1B0h] BYREF
  FILETIME FileTime1; // [rsp+2CCh] [rbp+1C4h] BYREF
  _BYTE v28[548]; // [rsp+2E4h] [rbp+1DCh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+530h] [rbp+428h]

  v24 = -2;
  lpFileName = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(v26, 0, 0x250u);
  v19[0] = 0;
  Property = OnlineConfigGetProperty(L"NumCBSPersistLogs", v19);
  v3 = v19[0];
  if ( Property < 0 )
    v3 = 5;
  v4 = SczAllocFromSz(&lpFileName, a1);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v4,
      v18);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    return v5;
  }
  v7 = SczAllocConcatSz(&lpFileName, L"\\CbsPersist_*.*");
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v7,
      v18);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    return v5;
  }
  while ( 1 )
  {
    FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
    v9 = FirstFileW;
    v22 = FirstFileW;
    if ( !FirstFileW )
      goto LABEL_31;
    v10 = 0;
    if ( FirstFileW == (HANDLE)-1LL )
      goto LABEL_31;
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        if ( !v10 || CompareFileTime(&FileTime1, &FindFileData.ftLastWriteTime) > 0 )
        {
          v11 = v26;
          p_FindFileData = &FindFileData;
          v13 = 4;
          do
          {
            *v11 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
            v11[1] = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
            v11[2] = *(_OWORD *)&p_FindFileData->nFileSizeLow;
            v11[3] = *(_OWORD *)&p_FindFileData->cFileName[2];
            v11[4] = *(_OWORD *)&p_FindFileData->cFileName[10];
            v11[5] = *(_OWORD *)&p_FindFileData->cFileName[18];
            v11[6] = *(_OWORD *)&p_FindFileData->cFileName[26];
            v11[7] = *(_OWORD *)&p_FindFileData->cFileName[34];
            v11 += 8;
            p_FindFileData = (_WIN32_FIND_DATAW *)((char *)p_FindFileData + 128);
            --v13;
          }
          while ( v13 );
          *v11 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
          v11[1] = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
          v11[2] = *(_OWORD *)&p_FindFileData->nFileSizeLow;
          v11[3] = *(_OWORD *)&p_FindFileData->cFileName[2];
          v11[4] = *(_OWORD *)&p_FindFileData->cFileName[10];
        }
        ++v10;
      }
    }
    while ( FindNextFileW(v9, &FindFileData) );
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&v22);
    if ( v10 <= v3 )
    {
LABEL_31:
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&v22);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
      return 0;
    }
    v21 = 0;
    v14 = SczAllocFormatted(&v21, L"%ws\\%ws", a1, v28);
    v5 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
        (const char *)(unsigned int)v14,
        v18);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v21);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&v22);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
      return v5;
    }
    if ( !DeleteFileW(v21) )
      break;
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v21);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&v22);
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to delete oldest backup log.");
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    else
      v17 = LastError;
    v19[0] = v17;
    *(_QWORD *)v23 = v19;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v16,
      3,
      (unsigned int)": {0}",
      (__int64)v23);
  }
  if ( LastError )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1CF,
           (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
           (const char *)(unsigned int)LastError,
           v18);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v21);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&v22);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    return v5;
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v21);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&v22);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  return 0;
}

```

## disassembly

```asm
0x140012b88  mov     rax, rsp
0x140012b8b  push    rbp
0x140012b8c  push    rdi
0x140012b8d  push    r14
0x140012b8f  lea     rbp, [rax-428h]
0x140012b96  sub     rsp, 510h
0x140012b9d  mov     [rsp+520h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x140012ba6  mov     [rax+10h], rbx
0x140012baa  mov     [rax+18h], rsi
0x140012bae  mov     rax, cs:__security_cookie
0x140012bb5  xor     rax, rsp
0x140012bb8  mov     [rbp+420h+var_20], rax
0x140012bbf  mov     r14, rcx
0x140012bc2  mov     [rsp+520h+lpFileName], 0
0x140012bcb  mov     ebx, 250h
0x140012bd0  mov     r8d, ebx; Size
0x140012bd3  xor     edx, edx; Val
0x140012bd5  lea     rcx, [rsp+520h+FindFileData]; void *
0x140012bda  call    memset_0
0x140012bdf  mov     r8d, ebx; Size
0x140012be2  xor     edx, edx; Val
0x140012be4  lea     rcx, [rbp+420h+var_270]; void *
0x140012beb  call    memset_0
0x140012bf0  mov     [rsp+520h+var_4F0], 0
0x140012bf8  lea     rdx, [rsp+520h+var_4F0]; unsigned int *
0x140012bfd  lea     rcx, aNumcbspersistl; "NumCBSPersistLogs"
0x140012c04  call    ?OnlineConfigGetProperty@@YAJPEB_WPEAK@Z; OnlineConfigGetProperty(wchar_t const *,ulong *)
0x140012c09  mov     esi, [rsp+520h+var_4F0]
0x140012c0d  mov     ecx, 5
0x140012c12  test    eax, eax
0x140012c14  cmovs   esi, ecx
0x140012c17  mov     rdx, r14
0x140012c1a  lea     rcx, [rsp+520h+lpFileName]
0x140012c1f  call    SczAllocFromSz
0x140012c24  mov     ebx, eax
0x140012c26  test    eax, eax
0x140012c28  jns     short loc_140012C58
0x140012c2a  mov     rcx, [rbp+428h]; this
0x140012c31  mov     r9d, eax; char *
0x140012c34  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140012c3b  mov     edx, 1A5h; void *
0x140012c40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012c45  nop
0x140012c46  lea     rcx, [rsp+520h+lpFileName]
0x140012c4b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012c50  nop
0x140012c51  mov     eax, ebx
0x140012c53  jmp     loc_140012F24
0x140012c58  lea     rdx, aCbspersist; "\\CbsPersist_*.*"
0x140012c5f  lea     rcx, [rsp+520h+lpFileName]
0x140012c64  call    SczAllocConcatSz
0x140012c69  mov     ebx, eax
0x140012c6b  test    eax, eax
0x140012c6d  jns     short loc_140012C98
0x140012c6f  mov     rcx, [rbp+428h]; this
0x140012c76  mov     r9d, eax; char *
0x140012c79  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140012c80  mov     edx, 1A6h; void *
0x140012c85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012c8a  nop
0x140012c8b  lea     rcx, [rsp+520h+lpFileName]
0x140012c90  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012c95  nop
0x140012c96  jmp     short loc_140012C51
0x140012c98  lea     rdx, [rsp+520h+FindFileData]; lpFindFileData
0x140012c9d  mov     rcx, [rsp+520h+lpFileName]; lpFileName
0x140012ca2  call    cs:__imp_FindFirstFileW
0x140012ca8  mov     rbx, rax
0x140012cab  mov     [rsp+520h+var_4D8], rax
0x140012cb0  test    rax, rax
0x140012cb3  jz      loc_140012F0C
0x140012cb9  xor     edi, edi
0x140012cbb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140012cbf  jz      loc_140012F0C
0x140012cc5  test    byte ptr [rsp+520h+FindFileData.dwFileAttributes], 10h
0x140012cca  jnz     loc_140012D79
0x140012cd0  test    edi, edi
0x140012cd2  jz      short loc_140012CEE
0x140012cd4  lea     rdx, [rsp+520h+FindFileData.ftLastWriteTime]; lpFileTime2
0x140012cd9  lea     rcx, [rbp+420h+FileTime1]; lpFileTime1
0x140012ce0  call    cs:__imp_CompareFileTime
0x140012ce6  test    eax, eax
0x140012ce8  jle     loc_140012D77
0x140012cee  lea     rax, [rbp+420h+var_270]
0x140012cf5  lea     rcx, [rsp+520h+FindFileData]
0x140012cfa  mov     edx, 4
0x140012cff  movups  xmm0, xmmword ptr [rcx]
0x140012d02  movups  xmmword ptr [rax], xmm0
0x140012d05  movups  xmm1, xmmword ptr [rcx+10h]
0x140012d09  movups  xmmword ptr [rax+10h], xmm1
0x140012d0d  movups  xmm0, xmmword ptr [rcx+20h]
0x140012d11  movups  xmmword ptr [rax+20h], xmm0
0x140012d15  movups  xmm1, xmmword ptr [rcx+30h]
0x140012d19  movups  xmmword ptr [rax+30h], xmm1
0x140012d1d  movups  xmm0, xmmword ptr [rcx+40h]
0x140012d21  movups  xmmword ptr [rax+40h], xmm0
0x140012d25  movups  xmm1, xmmword ptr [rcx+50h]
0x140012d29  movups  xmmword ptr [rax+50h], xmm1
0x140012d2d  movups  xmm0, xmmword ptr [rcx+60h]
0x140012d31  movups  xmmword ptr [rax+60h], xmm0
0x140012d35  movups  xmm1, xmmword ptr [rcx+70h]
0x140012d39  movups  xmmword ptr [rax+70h], xmm1
0x140012d3d  lea     rax, [rax+80h]
0x140012d44  lea     rcx, [rcx+80h]
0x140012d4b  sub     rdx, 1
0x140012d4f  jnz     short loc_140012CFF
0x140012d51  movups  xmm0, xmmword ptr [rcx]
0x140012d54  movups  xmmword ptr [rax], xmm0
0x140012d57  movups  xmm1, xmmword ptr [rcx+10h]
0x140012d5b  movups  xmmword ptr [rax+10h], xmm1
0x140012d5f  movups  xmm0, xmmword ptr [rcx+20h]
0x140012d63  movups  xmmword ptr [rax+20h], xmm0
0x140012d67  movups  xmm1, xmmword ptr [rcx+30h]
0x140012d6b  movups  xmmword ptr [rax+30h], xmm1
0x140012d6f  movups  xmm0, xmmword ptr [rcx+40h]
0x140012d73  movups  xmmword ptr [rax+40h], xmm0
0x140012d77  inc     edi
0x140012d79  lea     rdx, [rsp+520h+FindFileData]; lpFindFileData
0x140012d7e  mov     rcx, rbx; hFindFile
0x140012d81  call    cs:__imp_FindNextFileW
0x140012d87  test    eax, eax
0x140012d89  jnz     loc_140012CC5
0x140012d8f  lea     rcx, [rsp+520h+var_4D8]
0x140012d94  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x140012d99  cmp     edi, esi
0x140012d9b  jbe     loc_140012F0C
0x140012da1  mov     [rsp+520h+var_4E0], 0
0x140012daa  lea     r9, [rbp+420h+var_244]
0x140012db1  mov     r8, r14
0x140012db4  lea     rdx, aWsWs; "%ws\\%ws"
0x140012dbb  lea     rcx, [rsp+520h+var_4E0]
0x140012dc0  call    SczAllocFormatted
0x140012dc5  mov     ebx, eax
0x140012dc7  test    eax, eax
0x140012dc9  js      loc_140012ECA
0x140012dcf  mov     rcx, [rsp+520h+var_4E0]; lpFileName
0x140012dd4  call    cs:__imp_DeleteFileW
0x140012dda  test    eax, eax
0x140012ddc  jz      short loc_140012DF8
0x140012dde  lea     rcx, [rsp+520h+var_4E0]
0x140012de3  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012de8  nop
0x140012de9  lea     rcx, [rsp+520h+var_4D8]
0x140012dee  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x140012df3  jmp     loc_140012C98
0x140012df8  call    cs:__imp_GetLastError
0x140012dfe  mov     ebx, eax
0x140012e00  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012e07  test    rcx, rcx
0x140012e0a  jz      short loc_140012E60
0x140012e0c  lea     r9, aFailedToDelete; "Failed to delete oldest backup log."
0x140012e13  mov     edi, 3
0x140012e18  mov     r8d, edi
0x140012e1b  xor     edx, edx
0x140012e1d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140012e22  test    ebx, ebx
0x140012e24  jg      short loc_140012E2A
0x140012e26  mov     eax, ebx
0x140012e28  jmp     short loc_140012E32
0x140012e2a  movzx   eax, bx
0x140012e2d  or      eax, 80070000h
0x140012e32  mov     [rsp+520h+var_4F0], eax
0x140012e36  lea     rax, [rsp+520h+var_4F0]
0x140012e3b  mov     qword ptr [rsp+520h+var_4D0], rax
0x140012e40  lea     rax, [rsp+520h+var_4D0]
0x140012e45  mov     qword ptr [rsp+520h+var_500], rax; unsigned int
0x140012e4a  lea     r9, a0; ": {0}"
0x140012e51  mov     r8d, edi
0x140012e54  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012e5b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140012e60  test    ebx, ebx
0x140012e62  jz      short loc_140012EA7
0x140012e64  mov     rcx, [rbp+428h]; this
0x140012e6b  mov     r9d, ebx; char *
0x140012e6e  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140012e75  mov     edx, 1CFh; void *
0x140012e7a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140012e7f  mov     ebx, eax
0x140012e81  lea     rcx, [rsp+520h+var_4E0]
0x140012e86  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012e8b  nop
0x140012e8c  lea     rcx, [rsp+520h+var_4D8]
0x140012e91  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x140012e96  nop
0x140012e97  lea     rcx, [rsp+520h+lpFileName]
0x140012e9c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012ea1  nop
0x140012ea2  jmp     loc_140012C51
0x140012ea7  lea     rcx, [rsp+520h+var_4E0]
0x140012eac  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012eb1  nop
0x140012eb2  lea     rcx, [rsp+520h+var_4D8]
0x140012eb7  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x140012ebc  nop
0x140012ebd  lea     rcx, [rsp+520h+lpFileName]
0x140012ec2  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012ec7  nop
0x140012ec8  jmp     short loc_140012F22
0x140012eca  mov     rcx, [rbp+428h]; this
0x140012ed1  mov     r9d, ebx; char *
0x140012ed4  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140012edb  mov     edx, 1CDh; void *
0x140012ee0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012ee5  nop
0x140012ee6  lea     rcx, [rsp+520h+var_4E0]
0x140012eeb  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012ef0  nop
0x140012ef1  lea     rcx, [rsp+520h+var_4D8]
0x140012ef6  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x140012efb  nop
0x140012efc  lea     rcx, [rsp+520h+lpFileName]
0x140012f01  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012f06  nop
0x140012f07  jmp     loc_140012C51
0x140012f0c  lea     rcx, [rsp+520h+var_4D8]
0x140012f11  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x140012f16  nop
0x140012f17  lea     rcx, [rsp+520h+lpFileName]
0x140012f1c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012f21  nop
0x140012f22  xor     eax, eax
0x140012f24  mov     rcx, [rbp+420h+var_20]
0x140012f2b  xor     rcx, rsp; StackCookie
0x140012f2e  call    __security_check_cookie
0x140012f33  lea     r11, [rsp+520h+var_10]
0x140012f3b  mov     rbx, [r11+28h]
0x140012f3f  mov     rsi, [r11+30h]
0x140012f43  mov     rsp, r11
0x140012f46  pop     r14
0x140012f48  pop     rdi
0x140012f49  pop     rbp
0x140012f4a  retn
```
