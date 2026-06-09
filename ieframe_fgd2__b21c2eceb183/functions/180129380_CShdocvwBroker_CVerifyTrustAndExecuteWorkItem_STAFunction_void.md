# CShdocvwBroker::CVerifyTrustAndExecuteWorkItem::STAFunction(void)

- ea: `0x180129380`
- end: `0x180129b42`
- name: `?STAFunction@CVerifyTrustAndExecuteWorkItem@CShdocvwBroker@@MEAAJXZ`
- size: `1986`
- prototype: `__int64 __fastcall(CShdocvwBroker::CVerifyTrustAndExecuteWorkItem *__hidden this)`
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x18000c5c0`
- `0x180011230`
- `0x18002acc0`
- `0x1800906d4`
- `0x180093ec0`
- `0x180095408`
- `0x1800e7f54`
- `0x1800e96b0`
- `0x1800e9fd8`
- `0x1800ebdd0`
- `0x180129380`
- `0x18012cc10`
- `0x180152cd8`
- `0x180153440`
- `0x180153540`
- `0x180153700`
- `0x1801537d0`
- `0x18018eed4`
- `0x1803eb7ec`
- `0x1803efe64`
- `0x1803f1de4`
- `0x1803f39ac`
- `0x1804ea1d0`
- `0x1804edd10`
- `0x1804ee158`
- `0x1804f2c58`
- `0x18054e286`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `SHLWAPI!AssocIsDangerous` at `0x1801293d7`
- `SHLWAPI!AssocIsDangerous` at `0x1801293d7`
- `msvcrt!_wcsicmp` at `0x180129a12`
- `msvcrt!_wcsicmp` at `0x180129a2a`
- `msvcrt!_wcsicmp` at `0x180129a12`
- `msvcrt!_wcsicmp` at `0x180129a2a`
- `KERNEL32!CreateFileW` at `0x180129565`
- `KERNEL32!CreateFileW` at `0x180129565`
- `KERNEL32!CopyFileW` at `0x180129479`
- `KERNEL32!CopyFileW` at `0x180129479`
- `KERNEL32!CreateThread` at `0x18012962d`
- `KERNEL32!CreateThread` at `0x18012962d`
- `KERNEL32!GetExitCodeThread` at `0x180129653`
- `KERNEL32!GetExitCodeThread` at `0x180129653`
- `KERNEL32!LocalFree` at `0x180129af1`
- `KERNEL32!LocalFree` at `0x180129af1`
- `KERNEL32!CloseHandle` at `0x1801295b7`
- `KERNEL32!CloseHandle` at `0x18012967e`
- `KERNEL32!CloseHandle` at `0x1801295b7`
- `KERNEL32!CloseHandle` at `0x18012967e`
- `KERNEL32!GetLastError` at `0x18012944b`
- `KERNEL32!GetLastError` at `0x180129483`
- `KERNEL32!GetLastError` at `0x1801294e9`
- `KERNEL32!GetLastError` at `0x18012965d`
- `KERNEL32!GetLastError` at `0x180129686`
- `KERNEL32!GetLastError` at `0x18012944b`
- `KERNEL32!GetLastError` at `0x180129483`
- `KERNEL32!GetLastError` at `0x1801294e9`
- `KERNEL32!GetLastError` at `0x18012965d`
- `KERNEL32!GetLastError` at `0x180129686`
- `KERNEL32!WaitForSingleObject` at `0x180129641`
- `KERNEL32!WaitForSingleObject` at `0x180129641`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1801293c6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1801293c6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180129a02`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180129a02`
- `OLEAUT32!__imp_SysFreeString` at `0x1801298c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1801298c8`
- `SHELL32!ShellExecuteExW` at `0x180129abf`
- `SHELL32!ShellExecuteExW` at `0x180129abf`
- `SHELL32!__imp_PathIsExe` at `0x1801296c3`
- `SHELL32!__imp_PathIsExe` at `0x1801296c3`
- `WININET!CommitUrlCacheEntryW` at `0x1801294df`
- `WININET!CommitUrlCacheEntryW` at `0x1801294df`
- `WININET!DeleteUrlCacheEntryW` at `0x1801296b5`
- `WININET!DeleteUrlCacheEntryW` at `0x1801296b5`
- `WININET!CreateUrlCacheEntryW` at `0x180129441`
- `WININET!CreateUrlCacheEntryW` at `0x180129441`
- `urlmon!__imp_IsFileInSpecialDirs` at `0x180129409`
- `urlmon!__imp_IsFileInSpecialDirs` at `0x180129409`
- `urlmon!__imp_GetVersionManager` at `0x180129809`
- `urlmon!__imp_GetVersionManager` at `0x180129809`

## string_xrefs

- `0x18012988d`: `CShdocvwBroker::CVerifyTrustAndExecuteWorkItem::STAFunction`
- `0x1801298d4`: `CShdocvwBroker::CVerifyTrustAndExecuteWorkItem::STAFunction`
- `0x180129a0b`: `infopath.exe`

## pseudocode

```c
__int64 __fastcall CShdocvwBroker::CVerifyTrustAndExecuteWorkItem::STAFunction(
        CShdocvwBroker::CVerifyTrustAndExecuteWorkItem *this)
{
  __int64 v2; // rcx
  const WCHAR *ExtensionW; // rax
  const WCHAR *lpszFileExtension; // r15
  const WCHAR *v5; // r8
  int v6; // edi
  int LastError; // eax
  int v8; // eax
  bool v9; // zf
  int v10; // r9d
  int v11; // eax
  HANDLE FileW; // rbx
  bool v13; // sf
  __int64 v14; // rcx
  HANDLE v15; // rax
  void *v16; // rbx
  int v17; // eax
  int v18; // eax
  unsigned int v19; // r8d
  signed int ElevationDialogDisplayInfo; // eax
  HLOCAL v21; // r12
  _BOOL8 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rdi
  int (__fastcall *v25)(__int64, HLOCAL, _QWORD, _QWORD, bool, _DWORD, _QWORD, BSTR *, FILETIME *, int *); // rbx
  bool v26; // al
  DWORD v27; // eax
  CAttachmentServices *v28; // rax
  CAttachmentServices *v29; // rax
  CAttachmentServices *v30; // rbx
  __int64 v31; // rcx
  const wchar_t *FileNameW; // rax
  DirectUI *v33; // rcx
  DWORD HresultFromWin32; // eax
  int *cchHeaderInfo; // [rsp+30h] [rbp-D0h]
  DWORD ExitCode; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+64h] [rbp-9Ch] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  FILETIME LastModifiedTime; // [rsp+70h] [rbp-90h] BYREF
  int v41[2]; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-80h] BYREF
  void *lpMem; // [rsp+88h] [rbp-78h] BYREF
  SHELLEXECUTEINFOW Parameter; // [rsp+90h] [rbp-70h] BYREF
  WCHAR szFileName[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR pszPath[264]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v47[2352]; // [rsp+520h] [rbp+420h] BYREF

  v2 = *((_QWORD *)this + 1);
  ExitCode = 0;
  ExtensionW = PathFindExtensionW(*(LPCWSTR *)(v2 + 8));
  szFileName[0] = 0;
  lpszFileExtension = ExtensionW;
  if ( AssocIsDangerous(ExtensionW)
    && (unsigned int)CDownloadUtilities::IsSignable(*(const unsigned __int16 **)(*((_QWORD *)this + 1) + 8LL)) )
  {
    if ( (unsigned int)IsFileInSpecialDirs(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL), 1) )
    {
      v6 = 0;
      v11 = StringCchCopyW(szFileName, 0x104u, *(const unsigned __int16 **)(*((_QWORD *)this + 1) + 8LL));
    }
    else
    {
      v5 = lpszFileExtension + 1;
      v6 = 1;
      if ( *lpszFileExtension != 46 )
        v5 = lpszFileExtension;
      if ( !CreateUrlCacheEntryW(*(LPCWSTR *)(*((_QWORD *)this + 1) + 16LL), 0, v5, szFileName, 0) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        ExitCode = LastError;
      }
      if ( (ExitCode & 0x80000000) != 0 )
        goto LABEL_48;
      if ( !CopyFileW(*(LPCWSTR *)(*((_QWORD *)this + 1) + 8LL), szFileName, 0) )
      {
        v8 = GetLastError();
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        ExitCode = v8;
      }
      if ( (ExitCode & 0x80000000) != 0 )
      {
LABEL_48:
        if ( v6 )
          DeleteUrlCacheEntryW(*(LPCWSTR *)(*((_QWORD *)this + 1) + 16LL));
        goto LABEL_100;
      }
      v9 = *lpszFileExtension == 46;
      LastModifiedTime = 0;
      if ( v9 )
        ++lpszFileExtension;
      if ( CommitUrlCacheEntryW(
             *(LPCWSTR *)(*((_QWORD *)this + 1) + 16LL),
             szFileName,
             LastModifiedTime,
             LastModifiedTime,
             1u,
             0,
             0,
             lpszFileExtension,
             0) )
      {
LABEL_23:
        if ( (ExitCode & 0x80000000) == 0 )
        {
          if ( (unsigned int)IERegGetBoolWithPoliciesW(
                               L"Software\\Microsoft\\Internet Explorer\\Download",
                               L"Software\\Policies\\Microsoft\\Internet Explorer\\Download",
                               L"CheckExeSignatures",
                               v10) )
          {
            FileW = CreateFileW(szFileName, 0x80000000, 1u, 0, 3u, 0x2000000u, 0);
            if ( FileW == (HANDLE)-1LL )
            {
              ExitCode = HRESULTFromLastErrorError();
            }
            else
            {
              LODWORD(bstrString) = 0;
              ExitCode = ShouldVerifyTrustBeforeExecute(szFileName, (int *)&bstrString);
              if ( (ExitCode & 0x80000000) != 0 || (_DWORD)bstrString )
                ExitCode = CShdocvwBroker::CVerifyTrustAndExecuteWorkItem::_CallWinVerifyTrust(this, FileW, szFileName);
              CloseHandle(FileW);
            }
          }
          v13 = (ExitCode & 0x80000000) != 0;
          if ( !ExitCode )
          {
            v14 = *((_QWORD *)this + 1);
            memset(&Parameter, 0, 56);
            Parameter.lpParameters = *(LPCWSTR *)v14;
            Parameter.hwnd = (HWND)szFileName;
            if ( v6 )
              Parameter.lpVerb = *(LPCWSTR *)(v14 + 8);
            else
              Parameter.lpVerb = 0;
            *(_QWORD *)&Parameter.cbSize = *(_QWORD *)(v14 + 16);
            LODWORD(Parameter.lpDirectory) = 0;
            HIDWORD(Parameter.lpDirectory) = *(_DWORD *)(v14 + 32);
            v15 = CreateThread(0, 0, CDownloadUtilities::AESOperationThreadProc, &Parameter, 0, 0);
            v16 = v15;
            if ( v15 )
            {
              if ( WaitForSingleObject(v15, 0xFFFFFFFF) )
              {
                ExitCode = -2147467259;
              }
              else if ( !GetExitCodeThread(v16, &ExitCode) )
              {
                v17 = GetLastError();
                if ( v17 > 0 )
                  v17 = (unsigned __int16)v17 | 0x80070000;
                ExitCode = v17;
              }
              CloseHandle(v16);
            }
            else
            {
              v18 = GetLastError();
              if ( v18 > 0 )
                v18 = (unsigned __int16)v18 | 0x80070000;
              ExitCode = v18;
            }
            v13 = (ExitCode & 0x80000000) != 0;
          }
          if ( !v13 )
            goto LABEL_100;
        }
        goto LABEL_48;
      }
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
    }
    ExitCode = v11;
    goto LABEL_23;
  }
  ExitCode = 1;
  if ( PathIsExe(lpszFileExtension) )
    return ExitCode;
  v38 = 1;
  if ( (int)CDownloadUtilities::GetHandler(lpszFileExtension, pszPath, v19, &v38) >= 0 )
  {
    LastModifiedTime.dwLowDateTime = 1;
    LODWORD(bstrString) = 48;
    v41[0] = 1;
    hMem = 0;
    lpMem = 0;
    ExitCode = CProcessElevationPolicy::GetElevationPolicy(
                 pszPath,
                 0,
                 (enum CProcessElevationPolicy::_RunMode *)&LastModifiedTime,
                 (unsigned int *)&bstrString,
                 (unsigned __int16 **)&lpMem,
                 v41,
                 cchHeaderInfo);
    if ( (ExitCode & 0x80000000) == 0 )
    {
      if ( ((unsigned __int8)bstrString & 0x20) != 0 )
      {
        ExitCode = -2147024891;
        goto LABEL_98;
      }
      if ( IsAppIE(pszPath) )
        ExitCode = -2147024891;
    }
    if ( (ExitCode & 0x80000000) != 0 )
    {
LABEL_98:
      if ( lpMem )
        operator delete(lpMem);
      goto LABEL_100;
    }
    ElevationDialogDisplayInfo = GetElevationDialogDisplayInfo(pszPath, 0, (unsigned __int16 **)&hMem);
    v21 = hMem;
    ExitCode = ElevationDialogDisplayInfo;
    if ( ElevationDialogDisplayInfo < 0 )
    {
LABEL_96:
      if ( v21 )
        LocalFree(v21);
      goto LABEL_98;
    }
    v22 = v41[0] != 0;
    v23 = v38 != 0 ? 2 : 0;
    if ( LastModifiedTime.dwLowDateTime < 2 )
    {
      ExitCode = 1;
    }
    else
    {
      if ( LastModifiedTime.dwLowDateTime == 2 )
      {
LABEL_72:
        ExitCode = ShowElevationPrompt(
                     **((HWND **)this + 1),
                     0,
                     pszPath,
                     (const unsigned __int16 *)hMem,
                     "CShdocvwBroker::CVerifyTrustAndExecuteWorkItem::STAFunction",
                     (unsigned int)v22 | (unsigned int)v23);
        goto LABEL_74;
      }
      if ( LastModifiedTime.dwLowDateTime != 3 )
      {
        if ( LastModifiedTime.dwLowDateTime != 4 )
        {
          ExitCode = 1;
          goto LABEL_96;
        }
        goto LABEL_72;
      }
      LastModifiedTime.dwLowDateTime = 1;
      v38 = 0;
      bstrString = 0;
      *(_QWORD *)v41 = 0;
      if ( (int)GetVersionManager(v41, v23, v22) < 0
        || (v24 = *(_QWORD *)v41,
            v25 = *(int (__fastcall **)(__int64, HLOCAL, _QWORD, _QWORD, bool, _DWORD, _QWORD, BSTR *, FILETIME *, int *))(**(_QWORD **)v41 + 24LL),
            v26 = IsOs_Wow6432(),
            v25(v24, v21, 0, *(_QWORD *)(*((_QWORD *)this + 1) + 16LL), v26, 0, 0, &bstrString, &LastModifiedTime, &v38) < 0)
        || LastModifiedTime.dwLowDateTime )
      {
        v27 = 0;
      }
      else if ( v38 )
      {
        v27 = -2147023673;
      }
      else
      {
        v27 = ShowVersionPrompt(
                **((HWND **)this + 1),
                pszPath,
                (const unsigned __int16 *)v21,
                bstrString,
                "CShdocvwBroker::CVerifyTrustAndExecuteWorkItem::STAFunction");
      }
      ExitCode = v27;
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(v41);
      SysFreeString(bstrString);
    }
LABEL_74:
    if ( !ExitCode )
    {
      v28 = (CAttachmentServices *)operator new(0x138u);
      if ( v28 )
      {
        v29 = CAttachmentServices::CAttachmentServices(v28);
        ExitCode = -2147024882;
        v30 = v29;
        if ( v29 )
        {
          ExitCode = CAttachmentServices::SetLocalPath(v29, *(const unsigned __int16 **)(*((_QWORD *)this + 1) + 8LL));
          if ( (ExitCode & 0x80000000) == 0 )
          {
            ExitCode = CAttachmentServices::SetSource(v30, *(const unsigned __int16 **)(*((_QWORD *)this + 1) + 16LL));
            if ( (ExitCode & 0x80000000) == 0
              && (!*(_DWORD *)(*((_QWORD *)this + 1) + 32LL) || (int)CAttachmentServices::SetOperationConfig(v30, 9) >= 0) )
            {
              ExitCode = CAttachmentServices::SaveWithUI(v30, 0);
              if ( (ExitCode & 0x80000000) == 0 )
              {
                if ( ShouldDisableIEShellExecuteCallsWithoutProtocol() )
                {
                  ExitCode = -2147467259;
                }
                else
                {
                  memset_0(&Parameter.fMask, 0, 0x6Cu);
                  v31 = *((_QWORD *)this + 1);
                  *(_QWORD *)&Parameter.cbSize = 0x80010000000070LL;
                  Parameter.lpFile = *(LPCWSTR *)(v31 + 8);
                  Parameter.lpVerb = 0;
                  Parameter.hwnd = *(HWND *)v31;
                  Parameter.nShow = 1;
                  FileNameW = PathFindFileNameW(pszPath);
                  if ( !_wcsicmp(FileNameW, L"infopath.exe") && !_wcsicmp(lpszFileExtension, L".xsn") )
                  {
                    memset_0(v47, 0, 0x1254u);
                    if ( (int)StringCchCopyW(v47, 0x92Au, *(const unsigned __int16 **)(*((_QWORD *)this + 1) + 8LL)) >= 0 )
                    {
                      hMem = 0;
                      if ( (int)StringCchLengthW(v47, 0x92Au, (unsigned __int64 *)&hMem) >= 0
                        && (int)StringCchCopyW(
                                  &v47[(_QWORD)hMem + 1],
                                  2345LL - (_QWORD)hMem,
                                  *(const unsigned __int16 **)(*((_QWORD *)this + 1) + 16LL)) >= 0 )
                      {
                        Parameter.fMask |= 0x400000u;
                        Parameter.lpFile = v47;
                      }
                    }
                  }
                  if ( ShellExecuteExW(&Parameter) )
                    HresultFromWin32 = 0;
                  else
                    HresultFromWin32 = DirectUI::GetHresultFromWin32(v33);
                  ExitCode = HresultFromWin32;
                }
              }
            }
          }
          CAttachmentServices::Release(v30);
        }
      }
      else
      {
        ExitCode = -2147024882;
      }
    }
    goto LABEL_96;
  }
LABEL_100:
  if ( ExitCode == -2147023636 )
    CDownloadUtilities::NotifyAccessDisabledByPolicyError(**((HWND **)this + 1));
  return ExitCode;
}

```

## disassembly

```asm
0x180129380  push    rbp
0x180129382  push    rbx
0x180129383  push    rsi
0x180129384  push    rdi
0x180129385  push    r12
0x180129387  push    r13
0x180129389  push    r14
0x18012938b  push    r15
0x18012938d  lea     rbp, [rsp-1698h]
0x180129395  mov     eax, 1798h
0x18012939a  call    _alloca_probe
0x18012939f  sub     rsp, rax
0x1801293a2  mov     rax, cs:__security_cookie
0x1801293a9  xor     rax, rsp
0x1801293ac  mov     [rbp+16D0h+var_50], rax
0x1801293b3  mov     rsi, rcx
0x1801293b6  xor     r13d, r13d
0x1801293b9  mov     rcx, [rcx+8]
0x1801293bd  mov     [rsp+17D0h+ExitCode], r13d
0x1801293c2  mov     rcx, [rcx+8]; pszPath
0x1801293c6  call    cs:__imp_PathFindExtensionW
0x1801293cc  mov     rcx, rax; pszAssoc
0x1801293cf  mov     [rbp+16D0h+szFileName], r13w
0x1801293d4  mov     r15, rax
0x1801293d7  call    cs:__imp_AssocIsDangerous
0x1801293dd  test    eax, eax
0x1801293df  jz      loc_1801296C0
0x1801293e5  mov     rcx, [rsi+8]
0x1801293e9  mov     rcx, [rcx+8]; unsigned __int16 *
0x1801293ed  call    ?IsSignable@CDownloadUtilities@@SAHPEBG@Z; CDownloadUtilities::IsSignable(ushort const *)
0x1801293f2  test    eax, eax
0x1801293f4  jz      loc_1801296C0
0x1801293fa  mov     rcx, [rsi+8]
0x1801293fe  lea     r14d, [r13+1]
0x180129402  mov     edx, r14d
0x180129405  mov     rcx, [rcx+8]
0x180129409  call    cs:__imp_IsFileInSpecialDirs
0x18012940f  mov     r12d, 80070000h
0x180129415  test    eax, eax
0x180129417  jnz     loc_1801294FB
0x18012941d  cmp     word ptr [r15], 2Eh ; '.'
0x180129422  lea     r8, [r15+2]
0x180129426  mov     edi, r14d
0x180129429  jz      short loc_18012942E
0x18012942b  mov     r8, r15; lpszFileExtension
0x18012942e  mov     rcx, [rsi+8]
0x180129432  lea     r9, [rbp+16D0h+szFileName]; lpszFileName
0x180129436  xor     edx, edx; dwExpectedFileSize
0x180129438  mov     [rsp+17D0h+dwReserved], r13d; dwReserved
0x18012943d  mov     rcx, [rcx+10h]; lpszUrlName
0x180129441  call    cs:__imp_CreateUrlCacheEntryW
0x180129447  test    eax, eax
0x180129449  jnz     short loc_18012945F
0x18012944b  call    cs:__imp_GetLastError
0x180129451  test    eax, eax
0x180129453  jle     short loc_18012945B
0x180129455  movzx   eax, ax
0x180129458  or      eax, r12d
0x18012945b  mov     [rsp+17D0h+ExitCode], eax
0x18012945f  cmp     [rsp+17D0h+ExitCode], r13d
0x180129464  jl      loc_1801296A5
0x18012946a  mov     rcx, [rsi+8]
0x18012946e  lea     rdx, [rbp+16D0h+szFileName]; lpNewFileName
0x180129472  xor     r8d, r8d; bFailIfExists
0x180129475  mov     rcx, [rcx+8]; lpExistingFileName
0x180129479  call    cs:__imp_CopyFileW
0x18012947f  test    eax, eax
0x180129481  jnz     short loc_180129497
0x180129483  call    cs:__imp_GetLastError
0x180129489  test    eax, eax
0x18012948b  jle     short loc_180129493
0x18012948d  movzx   eax, ax
0x180129490  or      eax, r12d
0x180129493  mov     [rsp+17D0h+ExitCode], eax
0x180129497  cmp     [rsp+17D0h+ExitCode], r13d
0x18012949c  jl      loc_1801296A5
0x1801294a2  cmp     word ptr [r15], 2Eh ; '.'
0x1801294a7  mov     qword ptr [rsp+17D0h+LastModifiedTime.dwLowDateTime], r13
0x1801294ac  jnz     short loc_1801294B2
0x1801294ae  add     r15, 2
0x1801294b2  mov     rcx, [rsi+8]
0x1801294b6  lea     rdx, [rbp+16D0h+szFileName]; lpszLocalFileName
0x1801294ba  mov     r8, qword ptr [rsp+17D0h+LastModifiedTime.dwLowDateTime]; ExpireTime
0x1801294bf  mov     [rsp+17D0h+lpszOriginalUrl], r13; lpszOriginalUrl
0x1801294c4  mov     r9, r8; LastModifiedTime
0x1801294c7  mov     [rsp+17D0h+lpszFileExtension], r15; lpszFileExtension
0x1801294cc  mov     rcx, [rcx+10h]; lpszUrlName
0x1801294d0  mov     [rsp+17D0h+cchHeaderInfo], r13d; cchHeaderInfo
0x1801294d5  mov     [rsp+17D0h+lpszHeaderInfo], r13; lpszHeaderInfo
0x1801294da  mov     [rsp+17D0h+dwReserved], r14d; CacheEntryType
0x1801294df  call    cs:__imp_CommitUrlCacheEntryW
0x1801294e5  test    eax, eax
0x1801294e7  jnz     short loc_180129518
0x1801294e9  call    cs:__imp_GetLastError
0x1801294ef  test    eax, eax
0x1801294f1  jle     short loc_180129514
0x1801294f3  movzx   eax, ax
0x1801294f6  or      eax, r12d
0x1801294f9  jmp     short loc_180129514
0x1801294fb  mov     r8, [rsi+8]
0x1801294ff  lea     rcx, [rbp+16D0h+szFileName]; unsigned __int16 *
0x180129503  mov     edx, 104h; unsigned __int64
0x180129508  mov     edi, r13d
0x18012950b  mov     r8, [r8+8]; unsigned __int16 *
0x18012950f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180129514  mov     [rsp+17D0h+ExitCode], eax
0x180129518  cmp     [rsp+17D0h+ExitCode], r13d
0x18012951d  jl      loc_1801296A5
0x180129523  lea     r8, aCheckexesignat; "CheckExeSignatures"
0x18012952a  lea     rdx, aSoftwarePolici_6; "Software\\Policies\\Microsoft\\Internet"...
0x180129531  lea     rcx, aSoftwareMicros_114; "Software\\Microsoft\\Internet Explorer"...
0x180129538  call    ?IERegGetBoolWithPoliciesW@@YAHPEBG00H@Z; IERegGetBoolWithPoliciesW(ushort const *,ushort const *,ushort const *,int)
0x18012953d  test    eax, eax
0x18012953f  jz      short loc_1801295BD
0x180129541  mov     qword ptr [rsp+17D0h+cchHeaderInfo], r13; hTemplateFile
0x180129546  lea     rcx, [rbp+16D0h+szFileName]; lpFileName
0x18012954a  mov     dword ptr [rsp+17D0h+lpszHeaderInfo], 2000000h; dwFlagsAndAttributes
0x180129552  xor     r9d, r9d; lpSecurityAttributes
0x180129555  mov     r8d, r14d; dwShareMode
0x180129558  mov     [rsp+17D0h+dwReserved], 3; dwCreationDisposition
0x180129560  mov     edx, 80000000h; dwDesiredAccess
0x180129565  call    cs:__imp_CreateFileW
0x18012956b  mov     rbx, rax
0x18012956e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180129572  jnz     short loc_18012957F
0x180129574  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180129579  mov     [rsp+17D0h+ExitCode], eax
0x18012957d  jmp     short loc_1801295BD
0x18012957f  lea     rdx, [rsp+17D0h+bstrString]; int *
0x180129584  mov     dword ptr [rsp+17D0h+bstrString], r13d
0x180129589  lea     rcx, [rbp+16D0h+szFileName]; lpApplicationName
0x18012958d  call    ?ShouldVerifyTrustBeforeExecute@@YAJPEBGPEAH@Z; ShouldVerifyTrustBeforeExecute(ushort const *,int *)
0x180129592  mov     [rsp+17D0h+ExitCode], eax
0x180129596  test    eax, eax
0x180129598  js      short loc_1801295A1
0x18012959a  cmp     dword ptr [rsp+17D0h+bstrString], r13d
0x18012959f  jz      short loc_1801295B4
0x1801295a1  lea     r8, [rbp+16D0h+szFileName]; unsigned __int16 *
0x1801295a5  mov     rdx, rbx; void *
0x1801295a8  mov     rcx, rsi; this
0x1801295ab  call    ?_CallWinVerifyTrust@CVerifyTrustAndExecuteWorkItem@CShdocvwBroker@@AEBAJPEAXPEBG@Z; CShdocvwBroker::CVerifyTrustAndExecuteWorkItem::_CallWinVerifyTrust(void *,ushort const *)
0x1801295b0  mov     [rsp+17D0h+ExitCode], eax
0x1801295b4  mov     rcx, rbx; hObject
0x1801295b7  call    cs:__imp_CloseHandle
0x1801295bd  cmp     [rsp+17D0h+ExitCode], r13d
0x1801295c2  jnz     loc_18012969F
0x1801295c8  mov     rcx, [rsi+8]
0x1801295cc  xor     eax, eax
0x1801295ce  mov     [rbp+16D0h+var_1710], rax
0x1801295d2  xorps   xmm0, xmm0
0x1801295d5  movups  [rbp+16D0h+Parameter], xmm0
0x1801295d9  movups  [rbp+16D0h+var_1720], xmm0
0x1801295dd  movups  [rbp+16D0h+var_1730], xmm0
0x1801295e1  mov     rax, [rcx]
0x1801295e4  mov     qword ptr [rbp+16D0h+var_1720], rax
0x1801295e8  lea     rax, [rbp+16D0h+szFileName]
0x1801295ec  mov     qword ptr [rbp+16D0h+Parameter+8], rax
0x1801295f0  test    edi, edi
0x1801295f2  jz      short loc_1801295FE
0x1801295f4  mov     rax, [rcx+8]
0x1801295f8  mov     qword ptr [rbp+16D0h+var_1730], rax
0x1801295fc  jmp     short loc_180129602
0x1801295fe  mov     qword ptr [rbp+16D0h+var_1730], r13
0x180129602  mov     rax, [rcx+10h]
0x180129606  lea     r9, [rbp+16D0h+Parameter]; lpParameter
0x18012960a  mov     qword ptr [rbp+16D0h+Parameter], rax
0x18012960e  lea     r8, ?AESOperationThreadProc@CDownloadUtilities@@SAKPEAU_AESOPSTRUCT@@@Z; lpStartAddress
0x180129615  mov     dword ptr [rbp+16D0h+var_1720+8], r13d
0x180129619  xor     edx, edx; dwStackSize
0x18012961b  mov     eax, [rcx+20h]
0x18012961e  xor     ecx, ecx; lpThreadAttributes
0x180129620  mov     [rsp+17D0h+lpszHeaderInfo], r13; lpThreadId
0x180129625  mov     dword ptr [rbp+16D0h+var_1720+0Ch], eax
0x180129628  mov     [rsp+17D0h+dwReserved], r13d; dwCreationFlags
0x18012962d  call    cs:__imp_CreateThread
0x180129633  mov     rbx, rax
0x180129636  test    rax, rax
0x180129639  jz      short loc_180129686
0x18012963b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18012963e  mov     rcx, rax; hHandle
0x180129641  call    cs:__imp_WaitForSingleObject
0x180129647  test    eax, eax
0x180129649  jnz     short loc_180129673
0x18012964b  lea     rdx, [rsp+17D0h+ExitCode]; lpExitCode
0x180129650  mov     rcx, rbx; hThread
0x180129653  call    cs:__imp_GetExitCodeThread
0x180129659  test    eax, eax
0x18012965b  jnz     short loc_18012967B
0x18012965d  call    cs:__imp_GetLastError
0x180129663  test    eax, eax
0x180129665  jle     short loc_18012966D
0x180129667  movzx   eax, ax
0x18012966a  or      eax, r12d
0x18012966d  mov     [rsp+17D0h+ExitCode], eax
0x180129671  jmp     short loc_18012967B
0x180129673  mov     [rsp+17D0h+ExitCode], 80004005h
0x18012967b  mov     rcx, rbx; hObject
0x18012967e  call    cs:__imp_CloseHandle
0x180129684  jmp     short loc_18012969A
0x180129686  call    cs:__imp_GetLastError
0x18012968c  test    eax, eax
0x18012968e  jle     short loc_180129696
0x180129690  movzx   eax, ax
0x180129693  or      eax, r12d
0x180129696  mov     [rsp+17D0h+ExitCode], eax
0x18012969a  cmp     [rsp+17D0h+ExitCode], r13d
0x18012969f  jge     loc_180129B05
0x1801296a5  test    edi, edi
0x1801296a7  jz      loc_180129B05
0x1801296ad  mov     rcx, [rsi+8]
0x1801296b1  mov     rcx, [rcx+10h]; lpszUrlName
0x1801296b5  call    cs:__imp_DeleteUrlCacheEntryW
0x1801296bb  jmp     loc_180129B05
0x1801296c0  mov     rcx, r15; pszPath
0x1801296c3  call    cs:__imp_PathIsExe
0x1801296c9  mov     r14d, 1
0x1801296cf  mov     [rsp+17D0h+ExitCode], r14d
0x1801296d4  test    eax, eax
0x1801296d6  jnz     loc_180129B1B
0x1801296dc  lea     r9, [rsp+17D0h+var_176C]; int *
0x1801296e1  mov     [rsp+17D0h+var_176C], r14d
0x1801296e6  lea     rdx, [rbp+16D0h+pszPath]; unsigned __int16 *
0x1801296ed  mov     rcx, r15; unsigned __int16 *
0x1801296f0  call    ?GetHandler@CDownloadUtilities@@SAJPEBGPEAGKPEAH@Z; CDownloadUtilities::GetHandler(ushort const *,ushort *,ulong,int *)
0x1801296f5  test    eax, eax
0x1801296f7  js      loc_180129B05
0x1801296fd  lea     rax, [rsp+17D0h+var_1758]
0x180129702  mov     [rsp+17D0h+LastModifiedTime.dwLowDateTime], r14d
0x180129707  mov     [rsp+17D0h+lpszHeaderInfo], rax; int *
0x18012970c  lea     r9, [rsp+17D0h+bstrString]; unsigned int *
0x180129711  lea     rax, [rbp+16D0h+lpMem]
0x180129715  mov     dword ptr [rsp+17D0h+bstrString], 30h ; '0'
0x18012971d  lea     r8, [rsp+17D0h+LastModifiedTime]; enum CProcessElevationPolicy::_RunMode *
0x180129722  mov     qword ptr [rsp+17D0h+dwReserved], rax; unsigned __int16 **
0x180129727  xor     edx, edx; unsigned __int16 *
0x180129729  mov     [rsp+17D0h+var_1758], r14d
0x18012972e  lea     rcx, [rbp+16D0h+pszPath]; unsigned __int16 *
0x180129735  mov     [rbp+16D0h+hMem], r13
0x180129739  mov     [rbp+16D0h+lpMem], r13
0x18012973d  call    ?GetElevationPolicy@CProcessElevationPolicy@@SAJPEAGPEBGPEAW4_RunMode@1@PEAKPEAPEAGPEAH5@Z; CProcessElevationPolicy::GetElevationPolicy(ushort *,ushort const *,CProcessElevationPolicy::_RunMode *,ulong *,ushort * *,int *,int *)
0x180129742  mov     [rsp+17D0h+ExitCode], eax
0x180129746  test    eax, eax
0x180129748  js      short loc_180129776
0x18012974a  test    byte ptr [rsp+17D0h+bstrString], 20h
0x18012974f  jz      short loc_18012975E
0x180129751  mov     [rsp+17D0h+ExitCode], 80070005h
0x180129759  jmp     loc_180129AF7
0x18012975e  lea     rcx, [rbp+16D0h+pszPath]; unsigned __int16 *
0x180129765  call    ?IsAppIE@@YA_NPEBG@Z; IsAppIE(ushort const *)
0x18012976a  test    al, al
0x18012976c  jz      short loc_180129776
0x18012976e  mov     [rsp+17D0h+ExitCode], 80070005h
0x180129776  cmp     [rsp+17D0h+ExitCode], r13d
0x18012977b  jl      loc_180129AF7
0x180129781  lea     r8, [rbp+16D0h+hMem]; unsigned __int16 **
0x180129785  xor     edx, edx; unsigned __int16 *
0x180129787  lea     rcx, [rbp+16D0h+pszPath]; unsigned __int16 *
0x18012978e  call    ?GetElevationDialogDisplayInfo@@YAJPEBG0PEAPEAG@Z; GetElevationDialogDisplayInfo(ushort const *,ushort const *,ushort * *)
0x180129793  mov     r12, [rbp+16D0h+hMem]
0x180129797  mov     [rsp+17D0h+ExitCode], eax
0x18012979b  test    eax, eax
0x18012979d  js      loc_180129AE9
0x1801297a3  cmp     [rsp+17D0h+var_1758], r13d
0x1801297a8  mov     r8d, r13d
0x1801297ab  mov     eax, [rsp+17D0h+var_176C]
0x1801297af  mov     ecx, [rsp+17D0h+LastModifiedTime.dwLowDateTime]
0x1801297b3  setnz   r8b
0x1801297b7  neg     eax
0x1801297b9  sbb     edx, edx
0x1801297bb  and     edx, 2
0x1801297be  test    ecx, ecx
0x1801297c0  jz      loc_180129901
0x1801297c6  sub     ecx, r14d
0x1801297c9  jz      loc_180129901
0x1801297cf  sub     ecx, r14d
0x1801297d2  jz      loc_1801298D0
0x1801297d8  sub     ecx, r14d
0x1801297db  jz      short loc_1801297F0
0x1801297dd  cmp     ecx, r14d
0x1801297e0  jz      loc_1801298D0
0x1801297e6  mov     [rsp+17D0h+ExitCode], r14d
0x1801297eb  jmp     loc_180129AE9
0x1801297f0  lea     rcx, [rsp+17D0h+var_1758]
0x1801297f5  mov     [rsp+17D0h+LastModifiedTime.dwLowDateTime], r14d
0x1801297fa  mov     [rsp+17D0h+var_176C], r13d
0x1801297ff  mov     [rsp+17D0h+bstrString], r13
0x180129804  mov     qword ptr [rsp+17D0h+var_1758], r13
0x180129809  call    cs:__imp_GetVersionManager
0x18012980f  test    eax, eax
0x180129811  js      loc_1801298B2
0x180129817  mov     rdi, qword ptr [rsp+17D0h+var_1758]
0x18012981c  mov     rax, [rdi]
0x18012981f  mov     rbx, [rax+18h]
0x180129823  call    ?IsOs_Wow6432@@YA_NXZ; IsOs_Wow6432(void)
0x180129828  mov     r9, [rsi+8]
0x18012982c  xor     r8d, r8d
0x18012982f  movzx   edx, al
0x180129832  mov     rcx, rdi
0x180129835  lea     rax, [rsp+17D0h+var_176C]
0x18012983a  mov     [rsp+17D0h+var_1788], rax
  ... truncated ...
```
