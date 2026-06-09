# CDiskCleanupPage::OnDeleteTemporaryFiles(void)

- ea: `0x1400c9ed0`
- end: `0x1400ca226`
- name: `?OnDeleteTemporaryFiles@CDiskCleanupPage@@IEAAXXZ`
- size: `854`
- prototype: `void __fastcall(CDiskCleanupPage *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops`

## callees

- `0x14000d150`
- `0x14000d720`
- `0x140033828`
- `0x140042dc0`
- `0x14005b688`
- `0x140062455`
- `0x140067bc0`
- `0x140067e90`
- `0x14006875c`
- `0x14007ff20`
- `0x1400c9ed0`
- `0x1400ca780`
- `0x1400cad30`
- `0x1400cadac`
- `0x1400e0310`
- `0x1400e9e10`

## import_xrefs

- `USER32!MessageBoxW` at `0x1400c9f7a`
- `USER32!MessageBoxW` at `0x1400c9f7a`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x1400c9f27`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x1400c9f33`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x1400c9f27`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x1400c9f33`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400ca1e9`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400ca1f5`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400ca1e9`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400ca1f5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400c9fd1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ca1aa`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ca201`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400c9fd1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ca1aa`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400ca201`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400c9fdc`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400ca1b5`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400c9fdc`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400ca1b5`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400c9f09`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400c9f09`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x1400ca05b`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x1400ca158`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x1400ca05b`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x1400ca158`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400ca1dd`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400ca1dd`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400c9fc5`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400ca19e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400c9fc5`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400ca19e`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400c9f1c`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400c9f1c`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x1400ca161`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x1400ca1c8`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x1400ca161`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x1400ca1c8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400ca12d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400ca12d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1400ca047`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1400ca047`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400ca149`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400ca149`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400ca182`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400ca182`

## string_xrefs

- `0x1400c9f10`: `CDiskCleanupPage::OnDeleteTemporaryFiles`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall CDiskCleanupPage::OnDeleteTemporaryFiles(HWND *this)
{
  unsigned int v2; // edi
  __int64 UserDataFolder; // rax
  __int64 v4; // rdx
  const WCHAR *v5; // rcx
  HANDLE FirstFileW; // rsi
  __int64 v7; // rdx
  int v8; // edi
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  char dwFileAttributes; // bl
  __int64 v13; // rdx
  BOOL NextFileW; // r15d
  const WCHAR *v15; // rcx
  mmcerror::SC *Error; // rax
  __int64 v17; // rax
  _BYTE v18[8]; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpCaption; // [rsp+28h] [rbp-D8h] BYREF
  LPCWSTR lpText; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+38h] [rbp-C8h]
  _BYTE v22[24]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[16]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+70h] [rbp-90h]
  _BYTE v26[16]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v27; // [rsp+88h] [rbp-78h]
  __int64 v28; // [rsp+90h] [rbp-70h]
  LPCWSTR lpFileName[4]; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR v30[4]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v31[40]; // [rsp+D8h] [rbp-28h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+100h] [rbp+0h] BYREF

  v2 = 0;
  v21 = 0;
  mmcerror::SC::SC((mmcerror::SC *)v22, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v22, L"CDiskCleanupPage::OnDeleteTemporaryFiles");
  CString::CString(&lpText);
  CString::CString(&lpCaption);
  if ( LoadStringW((struct CString *)&lpText, 0x3472u) && LoadStringW((struct CString *)&lpCaption, 0x80u) )
  {
    if ( MessageBoxW(this[8], lpText, lpCaption, 0x34u) == 6 )
    {
      CWaitCursor::CWaitCursor((CWaitCursor *)v18);
      v27 = 0;
      v28 = 7;
      std::wstring::_Eos(v26, 0);
      UserDataFolder = CConsoleFilePersistor::ScGetUserDataFolder(v23, v26);
      mmcerror::SC::operator=(v22, UserDataFolder);
      mmcerror::SC::~SC((mmcerror::SC *)v23);
      if ( !(unsigned __int8)mmcerror::SC::operator bool(v22) )
      {
        tstring::tstring((tstring *)lpFileName, (const struct tstring *)v26);
        std::wstring::append(lpFileName, L"\\*.*");
        memset_0(&FindFileData, 0, sizeof(FindFileData));
        v5 = (const WCHAR *)lpFileName;
        if ( lpFileName[3] >= (LPCWSTR)8 )
          v5 = lpFileName[0];
        FirstFileW = FindFirstFileW(v5, &FindFileData);
        if ( FirstFileW == (HANDLE)-1LL )
        {
          mmcerror::SC::FromLastError((mmcerror::SC *)v22);
        }
        else
        {
          do
          {
            v24 = 0;
            v25 = 7;
            std::wstring::_Eos(v23, 0);
            v8 = v2 | 1;
            v21 = v8;
            std::wstring::reserve(v23, v27 + 1);
            std::wstring::append(v23, v26, 0, -1);
            std::wstring::append(v23, 1, 92);
            v9 = std::wstring::append(v23, FindFileData.cFileName);
            std::wstring::wstring(v31, v9);
            v8 |= 2u;
            v21 = v8;
            tstring::tstring((tstring *)v30, (const struct tstring *)v31);
            LOBYTE(v10) = 1;
            std::wstring::_Tidy(v31, v10, 0);
            v2 = v8 & 0xFFFFFFFE;
            LOBYTE(v11) = 1;
            std::wstring::_Tidy(v23, v11, 0);
            dwFileAttributes = FindFileData.dwFileAttributes;
            NextFileW = FindNextFileW(FirstFileW, &FindFileData);
            if ( (dwFileAttributes & 0x10) == 0 )
            {
              v15 = (const WCHAR *)v30;
              if ( v30[3] >= (LPCWSTR)8 )
                v15 = v30[0];
              if ( !DeleteFileW(v15) )
              {
                Error = mmcerror::SC::FromLastError((mmcerror::SC *)v22);
                mmcerror::SC::TraceAndClear(Error);
              }
            }
            LOBYTE(v13) = 1;
            std::wstring::_Tidy(v30, v13, 0);
          }
          while ( NextFileW );
          FindClose(FirstFileW);
          v17 = CDiskCleanupPage::ScRecalculateUsedSpace(this, v23);
          mmcerror::SC::operator=(v22, v17);
          mmcerror::SC::~SC((mmcerror::SC *)v23);
          if ( (unsigned __int8)mmcerror::SC::operator bool(v22) )
            mmcerror::SC::TraceAndClear((mmcerror::SC *)v22);
        }
        LOBYTE(v7) = 1;
        std::wstring::_Tidy(lpFileName, v7, 0);
      }
      LOBYTE(v4) = 1;
      std::wstring::_Tidy(v26, v4, 0);
      CWaitCursor::~CWaitCursor((CWaitCursor *)v18);
    }
  }
  else
  {
    mmcerror::SC::operator=(v22, 2147549183LL);
  }
  CString::~CString(&lpCaption);
  CString::~CString(&lpText);
  mmcerror::SC::~SC((mmcerror::SC *)v22);
}

```

## disassembly

```asm
0x1400c9ed0  push    rbp
0x1400c9ed2  push    rbx
0x1400c9ed3  push    rsi
0x1400c9ed4  push    rdi
0x1400c9ed5  push    r14
0x1400c9ed7  push    r15
0x1400c9ed9  lea     rbp, [rsp-268h]
0x1400c9ee1  sub     rsp, 368h
0x1400c9ee8  mov     rax, cs:__security_cookie
0x1400c9eef  xor     rax, rsp
0x1400c9ef2  mov     [rbp+290h+var_40], rax
0x1400c9ef9  mov     r14, rcx
0x1400c9efc  xor     edi, edi
0x1400c9efe  mov     [rsp+390h+var_358], edi
0x1400c9f02  xor     edx, edx
0x1400c9f04  lea     rcx, [rsp+390h+var_350]
0x1400c9f09  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1400c9f0f  nop
0x1400c9f10  lea     rdx, aCdiskcleanuppa_1; "CDiskCleanupPage::OnDeleteTemporaryFile"...
0x1400c9f17  lea     rcx, [rsp+390h+var_350]
0x1400c9f1c  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1400c9f22  lea     rcx, [rsp+390h+lpText]
0x1400c9f27  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x1400c9f2d  nop
0x1400c9f2e  lea     rcx, [rsp+390h+lpCaption]
0x1400c9f33  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x1400c9f39  nop
0x1400c9f3a  mov     edx, 3472h; unsigned int
0x1400c9f3f  lea     rcx, [rsp+390h+lpText]; struct CString *
0x1400c9f44  call    ?LoadStringW@@YAHAEAVCString@@I@Z; LoadStringW(CString &,uint)
0x1400c9f49  test    eax, eax
0x1400c9f4b  jz      loc_1400CA1D3
0x1400c9f51  mov     edx, 80h; unsigned int
0x1400c9f56  lea     rcx, [rsp+390h+lpCaption]; struct CString *
0x1400c9f5b  call    ?LoadStringW@@YAHAEAVCString@@I@Z; LoadStringW(CString &,uint)
0x1400c9f60  test    eax, eax
0x1400c9f62  jz      loc_1400CA1D3
0x1400c9f68  lea     r9d, [rdi+34h]; uType
0x1400c9f6c  mov     r8, [rsp+390h+lpCaption]; lpCaption
0x1400c9f71  mov     rdx, [rsp+390h+lpText]; lpText
0x1400c9f76  mov     rcx, [r14+40h]; hWnd
0x1400c9f7a  call    cs:__imp_MessageBoxW
0x1400c9f80  cmp     eax, 6
0x1400c9f83  jnz     loc_1400CA1E4
0x1400c9f89  lea     rcx, [rsp+390h+var_370]; this
0x1400c9f8e  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x1400c9f93  nop
0x1400c9f94  mov     [rbp+290h+var_308], rdi
0x1400c9f98  mov     [rbp+290h+var_300], 7
0x1400c9fa0  xor     edx, edx
0x1400c9fa2  lea     rcx, [rsp+390h+var_318]
0x1400c9fa7  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1400c9fac  nop
0x1400c9fad  lea     rdx, [rsp+390h+var_318]
0x1400c9fb2  lea     rcx, [rsp+390h+var_338]
0x1400c9fb7  call    ?ScGetUserDataFolder@CConsoleFilePersistor@@SA?AVSC@mmcerror@@AEAVtstring@@@Z; CConsoleFilePersistor::ScGetUserDataFolder(tstring &)
0x1400c9fbc  nop
0x1400c9fbd  mov     rdx, rax
0x1400c9fc0  lea     rcx, [rsp+390h+var_350]
0x1400c9fc5  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400c9fcb  nop
0x1400c9fcc  lea     rcx, [rsp+390h+var_338]
0x1400c9fd1  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400c9fd7  lea     rcx, [rsp+390h+var_350]
0x1400c9fdc  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400c9fe2  test    al, al
0x1400c9fe4  jz      short loc_1400CA005
0x1400c9fe6  xor     r8d, r8d
0x1400c9fe9  mov     dl, 1
0x1400c9feb  lea     rcx, [rsp+390h+var_318]
0x1400c9ff0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1400c9ff5  nop
0x1400c9ff6  lea     rcx, [rsp+390h+var_370]; this
0x1400c9ffb  call    ??1CWaitCursor@@QEAA@XZ; CWaitCursor::~CWaitCursor(void)
0x1400ca000  jmp     loc_1400CA1E4
0x1400ca005  lea     rdx, [rsp+390h+var_318]; struct tstring *
0x1400ca00a  lea     rcx, [rbp+290h+lpFileName]; this
0x1400ca00e  call    ??0tstring@@QEAA@AEBV0@@Z; tstring::tstring(tstring const &)
0x1400ca013  nop
0x1400ca014  lea     rdx, asc_1401194A0; "\\*.*"
0x1400ca01b  lea     rcx, [rbp+290h+lpFileName]
0x1400ca01f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1400ca024  xor     edx, edx; Val
0x1400ca026  mov     r8d, 250h; Size
0x1400ca02c  lea     rcx, [rbp+290h+FindFileData]; void *
0x1400ca030  call    memset_0
0x1400ca035  lea     rcx, [rbp+290h+lpFileName]
0x1400ca039  cmp     [rbp+290h+var_2E0], 8
0x1400ca03e  cmovnb  rcx, [rbp+290h+lpFileName]; lpFileName
0x1400ca043  lea     rdx, [rbp+290h+FindFileData]; lpFindFileData
0x1400ca047  call    cs:__imp_FindFirstFileW
0x1400ca04d  mov     rsi, rax
0x1400ca050  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400ca054  jnz     short loc_1400CA075
0x1400ca056  lea     rcx, [rsp+390h+var_350]
0x1400ca05b  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x1400ca061  nop
0x1400ca062  xor     r8d, r8d
0x1400ca065  mov     dl, 1
0x1400ca067  lea     rcx, [rbp+290h+lpFileName]
0x1400ca06b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1400ca070  jmp     loc_1400C9FE6
0x1400ca075  mov     [rsp+390h+var_328], 0
0x1400ca07e  mov     [rsp+390h+var_320], 7
0x1400ca087  xor     edx, edx
0x1400ca089  lea     rcx, [rsp+390h+var_338]
0x1400ca08e  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1400ca093  or      edi, 1
0x1400ca096  mov     [rsp+390h+var_358], edi
0x1400ca09a  mov     rdx, [rbp+290h+var_308]
0x1400ca09e  inc     rdx
0x1400ca0a1  lea     rcx, [rsp+390h+var_338]
0x1400ca0a6  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x1400ca0ab  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400ca0af  xor     r8d, r8d
0x1400ca0b2  lea     rdx, [rsp+390h+var_318]
0x1400ca0b7  lea     rcx, [rsp+390h+var_338]
0x1400ca0bc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1400ca0c1  mov     edx, 1
0x1400ca0c6  lea     r8d, [rdx+5Bh]
0x1400ca0ca  lea     rcx, [rsp+390h+var_338]
0x1400ca0cf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x1400ca0d4  lea     rdx, [rbp+290h+FindFileData.cFileName]
0x1400ca0d8  lea     rcx, [rsp+390h+var_338]
0x1400ca0dd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1400ca0e2  mov     rdx, rax
0x1400ca0e5  lea     rcx, [rbp+290h+var_2B8]
0x1400ca0e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1400ca0ee  or      edi, 2
0x1400ca0f1  mov     [rsp+390h+var_358], edi
0x1400ca0f5  lea     rdx, [rbp+290h+var_2B8]; struct tstring *
0x1400ca0f9  lea     rcx, [rbp+290h+var_2D8]; this
0x1400ca0fd  call    ??0tstring@@QEAA@AEBV0@@Z; tstring::tstring(tstring const &)
0x1400ca102  nop
0x1400ca103  xor     r8d, r8d
0x1400ca106  mov     dl, 1
0x1400ca108  lea     rcx, [rbp+290h+var_2B8]
0x1400ca10c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1400ca111  and     edi, 0FFFFFFFEh
0x1400ca114  xor     r8d, r8d
0x1400ca117  mov     dl, 1
0x1400ca119  lea     rcx, [rsp+390h+var_338]
0x1400ca11e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1400ca123  mov     ebx, [rbp+290h+FindFileData.dwFileAttributes]
0x1400ca126  lea     rdx, [rbp+290h+FindFileData]; lpFindFileData
0x1400ca12a  mov     rcx, rsi; hFindFile
0x1400ca12d  call    cs:__imp_FindNextFileW
0x1400ca133  mov     r15d, eax
0x1400ca136  test    bl, 10h
0x1400ca139  jnz     short loc_1400CA168
0x1400ca13b  lea     rcx, [rbp+290h+var_2D8]
0x1400ca13f  cmp     [rbp+290h+var_2C0], 8
0x1400ca144  cmovnb  rcx, [rbp+290h+var_2D8]; lpFileName
0x1400ca149  call    cs:__imp_DeleteFileW
0x1400ca14f  test    eax, eax
0x1400ca151  jnz     short loc_1400CA168
0x1400ca153  lea     rcx, [rsp+390h+var_350]
0x1400ca158  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x1400ca15e  mov     rcx, rax
0x1400ca161  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x1400ca167  nop
0x1400ca168  xor     r8d, r8d
0x1400ca16b  mov     dl, 1
0x1400ca16d  lea     rcx, [rbp+290h+var_2D8]
0x1400ca171  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1400ca176  test    r15d, r15d
0x1400ca179  jnz     loc_1400CA075
0x1400ca17f  mov     rcx, rsi; hFindFile
0x1400ca182  call    cs:__imp_FindClose
0x1400ca188  lea     rdx, [rsp+390h+var_338]
0x1400ca18d  mov     rcx, r14
0x1400ca190  call    ?ScRecalculateUsedSpace@CDiskCleanupPage@@AEAA?AVSC@mmcerror@@XZ; CDiskCleanupPage::ScRecalculateUsedSpace(void)
0x1400ca195  nop
0x1400ca196  mov     rdx, rax
0x1400ca199  lea     rcx, [rsp+390h+var_350]
0x1400ca19e  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400ca1a4  nop
0x1400ca1a5  lea     rcx, [rsp+390h+var_338]
0x1400ca1aa  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400ca1b0  lea     rcx, [rsp+390h+var_350]
0x1400ca1b5  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400ca1bb  test    al, al
0x1400ca1bd  jz      loc_1400CA062
0x1400ca1c3  lea     rcx, [rsp+390h+var_350]
0x1400ca1c8  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x1400ca1ce  jmp     loc_1400CA062
0x1400ca1d3  mov     edx, 8000FFFFh
0x1400ca1d8  lea     rcx, [rsp+390h+var_350]
0x1400ca1dd  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400ca1e3  nop
0x1400ca1e4  lea     rcx, [rsp+390h+lpCaption]
0x1400ca1e9  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1400ca1ef  nop
0x1400ca1f0  lea     rcx, [rsp+390h+lpText]
0x1400ca1f5  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1400ca1fb  nop
0x1400ca1fc  lea     rcx, [rsp+390h+var_350]
0x1400ca201  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400ca207  mov     rcx, [rbp+290h+var_40]
0x1400ca20e  xor     rcx, rsp; StackCookie
0x1400ca211  call    __security_check_cookie
0x1400ca216  add     rsp, 368h
0x1400ca21d  pop     r15
0x1400ca21f  pop     r14
0x1400ca221  pop     rdi
0x1400ca222  pop     rsi
0x1400ca223  pop     rbx
0x1400ca224  pop     rbp
0x1400ca225  retn
```
