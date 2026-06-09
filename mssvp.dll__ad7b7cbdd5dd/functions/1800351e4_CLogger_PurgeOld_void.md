# CLogger::PurgeOld(void)

- ea: `0x1800351e4`
- end: `0x180035335`
- name: `?PurgeOld@CLogger@@QEAAXXZ`
- size: `337`
- prototype: `void __fastcall(CLogger *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180035080`

## callees

- `0x1800048c0`
- `0x180006270`
- `0x180006dcc`
- `0x180018758`
- `0x180018ea8`
- `0x1800291b0`
- `0x180034738`
- `0x180034954`
- `0x18003505c`
- `0x1800351e4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180035260`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180035260`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800352f4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800352f4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800352ca`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800352ca`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800352e3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800352e3`

## pseudocode

```c
void __fastcall CLogger::PurgeOld(CLogger *this)
{
  LPCWSTR v2; // rbx
  char *v3; // rsi
  int v4; // r8d
  __int64 FirstFileW; // rdi
  LPCWSTR v6; // [rsp+20h] [rbp-288h] BYREF
  LPCWSTR lpFileName; // [rsp+28h] [rbp-280h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+30h] [rbp-278h] BYREF
  __int64 v9; // [rsp+38h] [rbp-270h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-268h] BYREF

  ATL::CTime::GetTickCount(&v6);
  v2 = v6 - 302400;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v3 = (char *)this + 24;
  try
  {
    ((void (*)(void))ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)();
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&lpFileName, "*.txt");
    FirstFileW = (__int64)FindFirstFileW(lpFileName, &FindFileData);
    while ( FirstFileW != -1 )
    {
      ftLastWriteTime = FindFileData.ftLastWriteTime;
      ATL::CTime::CTime((ATL::CTime *)&v9, &ftLastWriteTime, v4);
      if ( v9 < (__int64)v2 )
      {
        ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
          &v6,
          v3);
        ATL::CSimpleStringT<wchar_t,0>::Append(&v6, FindFileData.cFileName);
        if ( (int)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Find(&v6, L".txt") > 0 )
          DeleteFileW(v6);
        ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v6);
      }
      if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
      {
        FindClose((HANDLE)FirstFileW);
        FirstFileW = -1;
      }
    }
    ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&lpFileName);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x1800351e4  mov     [rsp+arg_8], rbx
0x1800351e9  mov     [rsp+arg_10], rsi
0x1800351ee  push    rdi
0x1800351ef  sub     rsp, 2A0h
0x1800351f6  mov     rax, cs:__security_cookie
0x1800351fd  xor     rax, rsp
0x180035200  mov     [rsp+2A8h+var_18], rax
0x180035208  mov     rdi, rcx
0x18003520b  lea     rcx, [rsp+2A8h+var_288]
0x180035210  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x180035215  mov     rbx, [rsp+2A8h+var_288]
0x18003521a  sub     rbx, 93A80h
0x180035221  xor     edx, edx; Val
0x180035223  mov     r8d, 250h; Size
0x180035229  lea     rcx, [rsp+2A8h+FindFileData]; void *
0x18003522e  call    memset_0
0x180035233  lea     rsi, [rdi+18h]
0x180035237  mov     rdx, rsi
0x18003523a  lea     rcx, [rsp+2A8h+lpFileName]
0x18003523f  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180035244  nop
0x180035245  lea     rdx, aTxt_0; "*.txt"
0x18003524c  lea     rcx, [rsp+2A8h+lpFileName]
0x180035251  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180035256  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18003525b  mov     rcx, [rsp+2A8h+lpFileName]; lpFileName
0x180035260  call    cs:__imp_FindFirstFileW
0x180035266  mov     rdi, rax
0x180035269  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003526d  jz      loc_180035303
0x180035273  mov     rcx, qword ptr [rsp+2A8h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x180035278  mov     qword ptr [rsp+2A8h+var_278.dwLowDateTime], rcx
0x18003527d  lea     rdx, [rsp+2A8h+var_278]; struct _FILETIME *
0x180035282  lea     rcx, [rsp+2A8h+var_270]; this
0x180035287  call    ??0CTime@ATL@@QEAA@AEBU_FILETIME@@H@Z; ATL::CTime::CTime(_FILETIME const &,int)
0x18003528c  cmp     [rsp+2A8h+var_270], rbx
0x180035291  jge     short loc_1800352DB
0x180035293  mov     rdx, rsi
0x180035296  lea     rcx, [rsp+2A8h+var_288]
0x18003529b  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x1800352a0  nop
0x1800352a1  lea     rdx, [rsp+2A8h+FindFileData.cFileName]
0x1800352a6  lea     rcx, [rsp+2A8h+var_288]
0x1800352ab  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x1800352b0  lea     rdx, aTxt; ".txt"
0x1800352b7  lea     rcx, [rsp+2A8h+var_288]
0x1800352bc  call    ?Find@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBAHPEB_WH@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Find(wchar_t const *,int)
0x1800352c1  test    eax, eax
0x1800352c3  jle     short loc_1800352D1
0x1800352c5  mov     rcx, [rsp+2A8h+var_288]; lpFileName
0x1800352ca  call    cs:__imp_DeleteFileW
0x1800352d0  nop
0x1800352d1  lea     rcx, [rsp+2A8h+var_288]
0x1800352d6  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x1800352db  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x1800352e0  mov     rcx, rdi; hFindFile
0x1800352e3  call    cs:__imp_FindNextFileW
0x1800352e9  test    eax, eax
0x1800352eb  jnz     loc_180035269
0x1800352f1  mov     rcx, rdi; hFindFile
0x1800352f4  call    cs:__imp_FindClose
0x1800352fa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800352fe  jmp     loc_180035269
0x180035303  lea     rcx, [rsp+2A8h+lpFileName]
0x180035308  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18003530d  nop
0x18003530e  jmp     short $+2
0x180035310  mov     rcx, [rsp+2A8h+var_18]
0x180035318  xor     rcx, rsp; StackCookie
0x18003531b  call    __security_check_cookie
0x180035320  lea     r11, [rsp+2A8h+var_8]
0x180035328  mov     rbx, [r11+18h]
0x18003532c  mov     rsi, [r11+20h]
0x180035330  mov     rsp, r11
0x180035333  pop     rdi
0x180035334  retn
```
