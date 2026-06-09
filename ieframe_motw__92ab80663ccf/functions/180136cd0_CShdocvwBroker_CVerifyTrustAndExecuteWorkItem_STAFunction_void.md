# CShdocvwBroker::CVerifyTrustAndExecuteWorkItem::STAFunction(void)

- ea: `0x180136cd0`
- end: `0x180137533`
- name: `?STAFunction@CVerifyTrustAndExecuteWorkItem@CShdocvwBroker@@MEAAJXZ`
- size: `2147`
- prototype: `__int64 __fastcall(CShdocvwBroker::CVerifyTrustAndExecuteWorkItem *__hidden this)`
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005030`
- `0x180007010`
- `0x1800096a0`
- `0x1800144d0`
- `0x180097100`
- `0x18009b248`
- `0x18009c758`
- `0x1800f18c0`
- `0x1800f32e8`
- `0x1800f3ca4`
- `0x1800f5cc0`
- `0x180136cd0`
- `0x18013a864`
- `0x1801629a8`
- `0x180163180`
- `0x180163280`
- `0x180163450`
- `0x180163530`
- `0x1801a27f4`
- `0x180420fbc`
- `0x180425acc`
- `0x180427db4`
- `0x180429b6c`
- `0x180528cac`
- `0x18052cdac`
- `0x18052d21c`
- `0x180532204`
- `0x180591ef6`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `SHLWAPI!AssocIsDangerous` at `0x180136d2d`
- `SHLWAPI!AssocIsDangerous` at `0x180136d2d`
- `msvcrt!_wcsicmp` at `0x1801373ea`
- `msvcrt!_wcsicmp` at `0x180137408`
- `msvcrt!_wcsicmp` at `0x1801373ea`
- `msvcrt!_wcsicmp` at `0x180137408`
- `KERNEL32!CreateFileW` at `0x180136eef`
- `KERNEL32!CreateFileW` at `0x180136eef`
- `KERNEL32!CopyFileW` at `0x180136de7`
- `KERNEL32!CopyFileW` at `0x180136de7`
- `KERNEL32!CreateThread` at `0x180136fc3`
- `KERNEL32!CreateThread` at `0x180136fc3`
- `KERNEL32!GetExitCodeThread` at `0x180136ff5`
- `KERNEL32!GetExitCodeThread` at `0x180136ff5`
- `KERNEL32!LocalFree` at `0x1801374db`
- `KERNEL32!LocalFree` at `0x1801374db`
- `KERNEL32!CloseHandle` at `0x180136f47`
- `KERNEL32!CloseHandle` at `0x18013702c`
- `KERNEL32!CloseHandle` at `0x180136f47`
- `KERNEL32!CloseHandle` at `0x18013702c`
- `KERNEL32!GetLastError` at `0x180136db3`
- `KERNEL32!GetLastError` at `0x180136df7`
- `KERNEL32!GetLastError` at `0x180136e69`
- `KERNEL32!GetLastError` at `0x180137005`
- `KERNEL32!GetLastError` at `0x18013703a`
- `KERNEL32!GetLastError` at `0x180136db3`
- `KERNEL32!GetLastError` at `0x180136df7`
- `KERNEL32!GetLastError` at `0x180136e69`
- `KERNEL32!GetLastError` at `0x180137005`
- `KERNEL32!GetLastError` at `0x18013703a`
- `KERNEL32!WaitForSingleObject` at `0x180136fdd`
- `KERNEL32!WaitForSingleObject` at `0x180136fdd`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x180136d16`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x180136d16`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801373d4`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801373d4`
- `OLEAUT32!__imp_SysFreeString` at `0x180137294`
- `OLEAUT32!__imp_SysFreeString` at `0x180137294`
- `SHELL32!ShellExecuteExW` at `0x1801374a3`
- `SHELL32!ShellExecuteExW` at `0x1801374a3`
- `SHELL32!__imp_PathIsExe` at `0x180137083`
- `SHELL32!__imp_PathIsExe` at `0x180137083`
- `WININET!CommitUrlCacheEntryW` at `0x180136e59`
- `WININET!CommitUrlCacheEntryW` at `0x180136e59`
- `WININET!DeleteUrlCacheEntryW` at `0x18013706f`
- `WININET!DeleteUrlCacheEntryW` at `0x18013706f`
- `WININET!CreateUrlCacheEntryW` at `0x180136da3`
- `WININET!CreateUrlCacheEntryW` at `0x180136da3`
- `urlmon!__imp_IsFileInSpecialDirs` at `0x180136d65`
- `urlmon!__imp_IsFileInSpecialDirs` at `0x180136d65`
- `urlmon!__imp_GetVersionManager` at `0x1801371cf`
- `urlmon!__imp_GetVersionManager` at `0x1801371cf`

## string_xrefs

- `0x180137259`: `CShdocvwBroker::CVerifyTrustAndExecuteWorkItem::STAFunction`
- `0x1801372a6`: `CShdocvwBroker::CVerifyTrustAndExecuteWorkItem::STAFunction`
- `0x1801373e3`: `infopath.exe`

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
0x180136cd0  push    rbp
0x180136cd2  push    rbx
0x180136cd3  push    rsi
0x180136cd4  push    rdi
0x180136cd5  push    r12
0x180136cd7  push    r13
0x180136cd9  push    r14
0x180136cdb  push    r15
0x180136cdd  lea     rbp, [rsp-1698h]
0x180136ce5  mov     eax, 1798h
0x180136cea  call    _alloca_probe
0x180136cef  sub     rsp, rax
0x180136cf2  mov     rax, cs:__security_cookie
0x180136cf9  xor     rax, rsp
0x180136cfc  mov     [rbp+16D0h+var_50], rax
0x180136d03  mov     rsi, rcx
0x180136d06  xor     r13d, r13d
0x180136d09  mov     rcx, [rcx+8]
0x180136d0d  mov     [rsp+17D0h+ExitCode], r13d
0x180136d12  mov     rcx, [rcx+8]; pszPath
0x180136d16  call    cs:__imp_PathFindExtensionW
0x180136d1d  nop     dword ptr [rax+rax+00h]
0x180136d22  mov     rcx, rax; pszAssoc
0x180136d25  mov     [rbp+16D0h+szFileName], r13w
0x180136d2a  mov     r15, rax
0x180136d2d  call    cs:__imp_AssocIsDangerous
0x180136d34  nop     dword ptr [rax+rax+00h]
0x180136d39  test    eax, eax
0x180136d3b  jz      loc_180137080
0x180136d41  mov     rcx, [rsi+8]
0x180136d45  mov     rcx, [rcx+8]; unsigned __int16 *
0x180136d49  call    ?IsSignable@CDownloadUtilities@@SAHPEBG@Z; CDownloadUtilities::IsSignable(ushort const *)
0x180136d4e  test    eax, eax
0x180136d50  jz      loc_180137080
0x180136d56  mov     rcx, [rsi+8]
0x180136d5a  lea     r14d, [r13+1]
0x180136d5e  mov     edx, r14d
0x180136d61  mov     rcx, [rcx+8]
0x180136d65  call    cs:__imp_IsFileInSpecialDirs
0x180136d6c  nop     dword ptr [rax+rax+00h]
0x180136d71  mov     r12d, 80070000h
0x180136d77  test    eax, eax
0x180136d79  jnz     loc_180136E81
0x180136d7f  cmp     word ptr [r15], 2Eh ; '.'
0x180136d84  lea     r8, [r15+2]
0x180136d88  mov     edi, r14d
0x180136d8b  jz      short loc_180136D90
0x180136d8d  mov     r8, r15; lpszFileExtension
0x180136d90  mov     rcx, [rsi+8]
0x180136d94  lea     r9, [rbp+16D0h+szFileName]; lpszFileName
0x180136d98  xor     edx, edx; dwExpectedFileSize
0x180136d9a  mov     [rsp+17D0h+dwReserved], r13d; dwReserved
0x180136d9f  mov     rcx, [rcx+10h]; lpszUrlName
0x180136da3  call    cs:__imp_CreateUrlCacheEntryW
0x180136daa  nop     dword ptr [rax+rax+00h]
0x180136daf  test    eax, eax
0x180136db1  jnz     short loc_180136DCD
0x180136db3  call    cs:__imp_GetLastError
0x180136dba  nop     dword ptr [rax+rax+00h]
0x180136dbf  test    eax, eax
0x180136dc1  jle     short loc_180136DC9
0x180136dc3  movzx   eax, ax
0x180136dc6  or      eax, r12d
0x180136dc9  mov     [rsp+17D0h+ExitCode], eax
0x180136dcd  cmp     [rsp+17D0h+ExitCode], r13d
0x180136dd2  jl      loc_18013705F
0x180136dd8  mov     rcx, [rsi+8]
0x180136ddc  lea     rdx, [rbp+16D0h+szFileName]; lpNewFileName
0x180136de0  xor     r8d, r8d; bFailIfExists
0x180136de3  mov     rcx, [rcx+8]; lpExistingFileName
0x180136de7  call    cs:__imp_CopyFileW
0x180136dee  nop     dword ptr [rax+rax+00h]
0x180136df3  test    eax, eax
0x180136df5  jnz     short loc_180136E11
0x180136df7  call    cs:__imp_GetLastError
0x180136dfe  nop     dword ptr [rax+rax+00h]
0x180136e03  test    eax, eax
0x180136e05  jle     short loc_180136E0D
0x180136e07  movzx   eax, ax
0x180136e0a  or      eax, r12d
0x180136e0d  mov     [rsp+17D0h+ExitCode], eax
0x180136e11  cmp     [rsp+17D0h+ExitCode], r13d
0x180136e16  jl      loc_18013705F
0x180136e1c  cmp     word ptr [r15], 2Eh ; '.'
0x180136e21  mov     qword ptr [rsp+17D0h+LastModifiedTime.dwLowDateTime], r13
0x180136e26  jnz     short loc_180136E2C
0x180136e28  add     r15, 2
0x180136e2c  mov     rcx, [rsi+8]
0x180136e30  lea     rdx, [rbp+16D0h+szFileName]; lpszLocalFileName
0x180136e34  mov     r8, qword ptr [rsp+17D0h+LastModifiedTime.dwLowDateTime]; ExpireTime
0x180136e39  mov     [rsp+17D0h+lpszOriginalUrl], r13; lpszOriginalUrl
0x180136e3e  mov     r9, r8; LastModifiedTime
0x180136e41  mov     [rsp+17D0h+lpszFileExtension], r15; lpszFileExtension
0x180136e46  mov     rcx, [rcx+10h]; lpszUrlName
0x180136e4a  mov     [rsp+17D0h+cchHeaderInfo], r13d; cchHeaderInfo
0x180136e4f  mov     [rsp+17D0h+lpszHeaderInfo], r13; lpszHeaderInfo
0x180136e54  mov     [rsp+17D0h+dwReserved], r14d; CacheEntryType
0x180136e59  call    cs:__imp_CommitUrlCacheEntryW
0x180136e60  nop     dword ptr [rax+rax+00h]
0x180136e65  test    eax, eax
0x180136e67  jnz     short loc_180136E9E
0x180136e69  call    cs:__imp_GetLastError
0x180136e70  nop     dword ptr [rax+rax+00h]
0x180136e75  test    eax, eax
0x180136e77  jle     short loc_180136E9A
0x180136e79  movzx   eax, ax
0x180136e7c  or      eax, r12d
0x180136e7f  jmp     short loc_180136E9A
0x180136e81  mov     r8, [rsi+8]
0x180136e85  lea     rcx, [rbp+16D0h+szFileName]; unsigned __int16 *
0x180136e89  mov     edx, 104h; unsigned __int64
0x180136e8e  mov     edi, r13d
0x180136e91  mov     r8, [r8+8]; unsigned __int16 *
0x180136e95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180136e9a  mov     [rsp+17D0h+ExitCode], eax
0x180136e9e  cmp     [rsp+17D0h+ExitCode], r13d
0x180136ea3  jl      loc_18013705F
0x180136ea9  lea     r8, aCheckexesignat; "CheckExeSignatures"
0x180136eb0  lea     rdx, aSoftwarePolici_6; "Software\\Policies\\Microsoft\\Internet"...
0x180136eb7  lea     rcx, aSoftwareMicros_114; "Software\\Microsoft\\Internet Explorer"...
0x180136ebe  call    ?IERegGetBoolWithPoliciesW@@YAHPEBG00H@Z; IERegGetBoolWithPoliciesW(ushort const *,ushort const *,ushort const *,int)
0x180136ec3  test    eax, eax
0x180136ec5  jz      loc_180136F53
0x180136ecb  mov     qword ptr [rsp+17D0h+cchHeaderInfo], r13; hTemplateFile
0x180136ed0  lea     rcx, [rbp+16D0h+szFileName]; lpFileName
0x180136ed4  mov     dword ptr [rsp+17D0h+lpszHeaderInfo], 2000000h; dwFlagsAndAttributes
0x180136edc  xor     r9d, r9d; lpSecurityAttributes
0x180136edf  mov     r8d, r14d; dwShareMode
0x180136ee2  mov     [rsp+17D0h+dwReserved], 3; dwCreationDisposition
0x180136eea  mov     edx, 80000000h; dwDesiredAccess
0x180136eef  call    cs:__imp_CreateFileW
0x180136ef6  nop     dword ptr [rax+rax+00h]
0x180136efb  mov     rbx, rax
0x180136efe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180136f02  jnz     short loc_180136F0F
0x180136f04  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180136f09  mov     [rsp+17D0h+ExitCode], eax
0x180136f0d  jmp     short loc_180136F53
0x180136f0f  lea     rdx, [rsp+17D0h+bstrString]; int *
0x180136f14  mov     dword ptr [rsp+17D0h+bstrString], r13d
0x180136f19  lea     rcx, [rbp+16D0h+szFileName]; lpApplicationName
0x180136f1d  call    ?ShouldVerifyTrustBeforeExecute@@YAJPEBGPEAH@Z; ShouldVerifyTrustBeforeExecute(ushort const *,int *)
0x180136f22  mov     [rsp+17D0h+ExitCode], eax
0x180136f26  test    eax, eax
0x180136f28  js      short loc_180136F31
0x180136f2a  cmp     dword ptr [rsp+17D0h+bstrString], r13d
0x180136f2f  jz      short loc_180136F44
0x180136f31  lea     r8, [rbp+16D0h+szFileName]; unsigned __int16 *
0x180136f35  mov     rdx, rbx; void *
0x180136f38  mov     rcx, rsi; this
0x180136f3b  call    ?_CallWinVerifyTrust@CVerifyTrustAndExecuteWorkItem@CShdocvwBroker@@AEBAJPEAXPEBG@Z; CShdocvwBroker::CVerifyTrustAndExecuteWorkItem::_CallWinVerifyTrust(void *,ushort const *)
0x180136f40  mov     [rsp+17D0h+ExitCode], eax
0x180136f44  mov     rcx, rbx; hObject
0x180136f47  call    cs:__imp_CloseHandle
0x180136f4e  nop     dword ptr [rax+rax+00h]
0x180136f53  cmp     [rsp+17D0h+ExitCode], r13d
0x180136f58  jnz     loc_180137059
0x180136f5e  mov     rcx, [rsi+8]
0x180136f62  xor     eax, eax
0x180136f64  mov     [rbp+16D0h+var_1710], rax
0x180136f68  xorps   xmm0, xmm0
0x180136f6b  movups  [rbp+16D0h+Parameter], xmm0
0x180136f6f  movups  [rbp+16D0h+var_1720], xmm0
0x180136f73  movups  [rbp+16D0h+var_1730], xmm0
0x180136f77  mov     rax, [rcx]
0x180136f7a  mov     qword ptr [rbp+16D0h+var_1720], rax
0x180136f7e  lea     rax, [rbp+16D0h+szFileName]
0x180136f82  mov     qword ptr [rbp+16D0h+Parameter+8], rax
0x180136f86  test    edi, edi
0x180136f88  jz      short loc_180136F94
0x180136f8a  mov     rax, [rcx+8]
0x180136f8e  mov     qword ptr [rbp+16D0h+var_1730], rax
0x180136f92  jmp     short loc_180136F98
0x180136f94  mov     qword ptr [rbp+16D0h+var_1730], r13
0x180136f98  mov     rax, [rcx+10h]
0x180136f9c  lea     r9, [rbp+16D0h+Parameter]; lpParameter
0x180136fa0  mov     qword ptr [rbp+16D0h+Parameter], rax
0x180136fa4  lea     r8, ?AESOperationThreadProc@CDownloadUtilities@@SAKPEAU_AESOPSTRUCT@@@Z; lpStartAddress
0x180136fab  mov     dword ptr [rbp+16D0h+var_1720+8], r13d
0x180136faf  xor     edx, edx; dwStackSize
0x180136fb1  mov     eax, [rcx+20h]
0x180136fb4  xor     ecx, ecx; lpThreadAttributes
0x180136fb6  mov     [rsp+17D0h+lpszHeaderInfo], r13; lpThreadId
0x180136fbb  mov     dword ptr [rbp+16D0h+var_1720+0Ch], eax
0x180136fbe  mov     [rsp+17D0h+dwReserved], r13d; dwCreationFlags
0x180136fc3  call    cs:__imp_CreateThread
0x180136fca  nop     dword ptr [rax+rax+00h]
0x180136fcf  mov     rbx, rax
0x180136fd2  test    rax, rax
0x180136fd5  jz      short loc_18013703A
0x180136fd7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180136fda  mov     rcx, rax; hHandle
0x180136fdd  call    cs:__imp_WaitForSingleObject
0x180136fe4  nop     dword ptr [rax+rax+00h]
0x180136fe9  test    eax, eax
0x180136feb  jnz     short loc_180137021
0x180136fed  lea     rdx, [rsp+17D0h+ExitCode]; lpExitCode
0x180136ff2  mov     rcx, rbx; hThread
0x180136ff5  call    cs:__imp_GetExitCodeThread
0x180136ffc  nop     dword ptr [rax+rax+00h]
0x180137001  test    eax, eax
0x180137003  jnz     short loc_180137029
0x180137005  call    cs:__imp_GetLastError
0x18013700c  nop     dword ptr [rax+rax+00h]
0x180137011  test    eax, eax
0x180137013  jle     short loc_18013701B
0x180137015  movzx   eax, ax
0x180137018  or      eax, r12d
0x18013701b  mov     [rsp+17D0h+ExitCode], eax
0x18013701f  jmp     short loc_180137029
0x180137021  mov     [rsp+17D0h+ExitCode], 80004005h
0x180137029  mov     rcx, rbx; hObject
0x18013702c  call    cs:__imp_CloseHandle
0x180137033  nop     dword ptr [rax+rax+00h]
0x180137038  jmp     short loc_180137054
0x18013703a  call    cs:__imp_GetLastError
0x180137041  nop     dword ptr [rax+rax+00h]
0x180137046  test    eax, eax
0x180137048  jle     short loc_180137050
0x18013704a  movzx   eax, ax
0x18013704d  or      eax, r12d
0x180137050  mov     [rsp+17D0h+ExitCode], eax
0x180137054  cmp     [rsp+17D0h+ExitCode], r13d
0x180137059  jge     loc_1801374F5
0x18013705f  test    edi, edi
0x180137061  jz      loc_1801374F5
0x180137067  mov     rcx, [rsi+8]
0x18013706b  mov     rcx, [rcx+10h]; lpszUrlName
0x18013706f  call    cs:__imp_DeleteUrlCacheEntryW
0x180137076  nop     dword ptr [rax+rax+00h]
0x18013707b  jmp     loc_1801374F5
0x180137080  mov     rcx, r15; pszPath
0x180137083  call    cs:__imp_PathIsExe
0x18013708a  nop     dword ptr [rax+rax+00h]
0x18013708f  mov     r14d, 1
0x180137095  mov     [rsp+17D0h+ExitCode], r14d
0x18013709a  test    eax, eax
0x18013709c  jnz     loc_18013750B
0x1801370a2  lea     r9, [rsp+17D0h+var_176C]; int *
0x1801370a7  mov     [rsp+17D0h+var_176C], r14d
0x1801370ac  lea     rdx, [rbp+16D0h+pszPath]; unsigned __int16 *
0x1801370b3  mov     rcx, r15; unsigned __int16 *
0x1801370b6  call    ?GetHandler@CDownloadUtilities@@SAJPEBGPEAGKPEAH@Z; CDownloadUtilities::GetHandler(ushort const *,ushort *,ulong,int *)
0x1801370bb  test    eax, eax
0x1801370bd  js      loc_1801374F5
0x1801370c3  lea     rax, [rsp+17D0h+var_1758]
0x1801370c8  mov     [rsp+17D0h+LastModifiedTime.dwLowDateTime], r14d
0x1801370cd  mov     [rsp+17D0h+lpszHeaderInfo], rax; int *
0x1801370d2  lea     r9, [rsp+17D0h+bstrString]; unsigned int *
0x1801370d7  lea     rax, [rbp+16D0h+lpMem]
0x1801370db  mov     dword ptr [rsp+17D0h+bstrString], 30h ; '0'
0x1801370e3  lea     r8, [rsp+17D0h+LastModifiedTime]; enum CProcessElevationPolicy::_RunMode *
0x1801370e8  mov     qword ptr [rsp+17D0h+dwReserved], rax; unsigned __int16 **
0x1801370ed  xor     edx, edx; unsigned __int16 *
0x1801370ef  mov     [rsp+17D0h+var_1758], r14d
0x1801370f4  lea     rcx, [rbp+16D0h+pszPath]; unsigned __int16 *
0x1801370fb  mov     [rbp+16D0h+hMem], r13
0x1801370ff  mov     [rbp+16D0h+lpMem], r13
0x180137103  call    ?GetElevationPolicy@CProcessElevationPolicy@@SAJPEAGPEBGPEAW4_RunMode@1@PEAKPEAPEAGPEAH5@Z; CProcessElevationPolicy::GetElevationPolicy(ushort *,ushort const *,CProcessElevationPolicy::_RunMode *,ulong *,ushort * *,int *,int *)
0x180137108  mov     [rsp+17D0h+ExitCode], eax
0x18013710c  test    eax, eax
0x18013710e  js      short loc_18013713C
0x180137110  test    byte ptr [rsp+17D0h+bstrString], 20h
0x180137115  jz      short loc_180137124
0x180137117  mov     [rsp+17D0h+ExitCode], 80070005h
0x18013711f  jmp     loc_1801374E7
0x180137124  lea     rcx, [rbp+16D0h+pszPath]; unsigned __int16 *
0x18013712b  call    ?IsAppIE@@YA_NPEBG@Z; IsAppIE(ushort const *)
0x180137130  test    al, al
0x180137132  jz      short loc_18013713C
0x180137134  mov     [rsp+17D0h+ExitCode], 80070005h
0x18013713c  cmp     [rsp+17D0h+ExitCode], r13d
0x180137141  jl      loc_1801374E7
0x180137147  lea     r8, [rbp+16D0h+hMem]; unsigned __int16 **
0x18013714b  xor     edx, edx; unsigned __int16 *
0x18013714d  lea     rcx, [rbp+16D0h+pszPath]; unsigned __int16 *
0x180137154  call    ?GetElevationDialogDisplayInfo@@YAJPEBG0PEAPEAG@Z; GetElevationDialogDisplayInfo(ushort const *,ushort const *,ushort * *)
0x180137159  mov     r12, [rbp+16D0h+hMem]
0x18013715d  mov     [rsp+17D0h+ExitCode], eax
0x180137161  test    eax, eax
0x180137163  js      loc_1801374D3
0x180137169  cmp     [rsp+17D0h+var_1758], r13d
0x18013716e  mov     r8d, r13d
0x180137171  mov     eax, [rsp+17D0h+var_176C]
0x180137175  mov     ecx, [rsp+17D0h+LastModifiedTime.dwLowDateTime]
0x180137179  setnz   r8b
0x18013717d  neg     eax
0x18013717f  sbb     edx, edx
0x180137181  and     edx, 2
0x180137184  test    ecx, ecx
0x180137186  jz      loc_1801372D3
0x18013718c  sub     ecx, r14d
0x18013718f  jz      loc_1801372D3
0x180137195  sub     ecx, r14d
0x180137198  jz      loc_1801372A2
0x18013719e  sub     ecx, r14d
0x1801371a1  jz      short loc_1801371B6
0x1801371a3  cmp     ecx, r14d
0x1801371a6  jz      loc_1801372A2
0x1801371ac  mov     [rsp+17D0h+ExitCode], r14d
  ... truncated ...
```
