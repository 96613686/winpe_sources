# IEGetProtectedModeCookie

- ea: `0x18004b370`
- end: `0x18004b853`
- name: `IEGetProtectedModeCookie`
- size: `1251`
- prototype: `HRESULT __stdcall(LPCWSTR lpszURL, LPCWSTR lpszCookieName, LPWSTR lpszCookieData, DWORD *pcchCookieData, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180009610`
- `0x1800123f0`
- `0x1800144d0`
- `0x18004b370`
- `0x18004b85c`
- `0x18004b9b8`
- `0x18004ba44`
- `0x180092c48`
- `0x1800b8fdc`
- `0x1800cd86c`
- `0x180420d1c`
- `0x180591f80`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18004b752`
- `KERNEL32!SetEvent` at `0x18004b752`
- `KERNEL32!GetLastError` at `0x18004b4b5`
- `KERNEL32!GetLastError` at `0x18004b7b5`
- `KERNEL32!GetLastError` at `0x18004b4b5`
- `KERNEL32!GetLastError` at `0x18004b7b5`
- `KERNEL32!ReleaseMutex` at `0x18004b7d3`
- `KERNEL32!ReleaseMutex` at `0x18004b7d3`
- `KERNEL32!WaitForSingleObject` at `0x18004b6bb`
- `KERNEL32!WaitForSingleObject` at `0x18004b76c`
- `KERNEL32!WaitForSingleObject` at `0x18004b6bb`
- `KERNEL32!WaitForSingleObject` at `0x18004b76c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathQuoteSpacesW` at `0x18004b632`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathQuoteSpacesW` at `0x18004b632`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18004b5ee`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18004b5ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b821`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b821`
- `iertutil!__imp_?ITS_CreateThreadScopedState@@YAXXZ` at `0x18004b3cf`
- `iertutil!__imp_?ITS_CreateThreadScopedState@@YAXXZ` at `0x18004b3cf`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x18004b430`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x18004b810`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x18004b430`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x18004b810`
- `WININET!InternetGetCookieExW` at `0x18004b49e`
- `WININET!InternetGetCookieExW` at `0x18004b49e`
- `msIso!__imp_?IsoCreateWindowsProcessInPIC@@YAJPEAGKK_NPEBGPEAU_IsoWindowsContainer@@@Z` at `0x18004b691`
- `msIso!__imp_?IsoCreateWindowsProcessInPIC@@YAJPEAGKK_NPEBGPEAU_IsoWindowsContainer@@@Z` at `0x18004b691`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18004b473`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18004b473`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x18004b412`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x18004b412`

## pseudocode

```c
HRESULT __stdcall IEGetProtectedModeCookie(
        LPCWSTR lpszURL,
        LPCWSTR lpszCookieName,
        LPWSTR lpszCookieData,
        DWORD *pcchCookieData,
        DWORD dwFlags)
{
  HRESULT WindowsProcessInPIC; // ebx
  unsigned int v10; // edi
  signed int Integrity; // eax
  signed int LastError; // eax
  const unsigned __int16 *v13; // rsi
  bool v14; // r9
  unsigned __int16 *FileNameW; // rax
  HANDLE v16; // rsi
  DWORD v17; // eax
  void *v18; // rdi
  unsigned __int16 *v19; // rcx
  signed int v20; // eax
  bool v22; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v23; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE v24; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hEvent; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hHandle; // [rsp+58h] [rbp-A8h] BYREF
  void *v27; // [rsp+60h] [rbp-A0h] BYREF
  void *v28; // [rsp+68h] [rbp-98h] BYREF
  void *v29; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v32[264]; // [rsp+290h] [rbp+190h] BYREF

  if ( !lpszURL || (WindowsProcessInPIC = 0, !pcchCookieData) )
    WindowsProcessInPIC = -2147024809;
  v23 = 0;
  bstrString = 0;
  if ( WindowsProcessInPIC >= 0 )
  {
    ITS_CreateThreadScopedState();
    WindowsProcessInPIC = _ForceIETS();
    if ( WindowsProcessInPIC >= 0 && !LCIEGetRedirectionPolicyForURL2(lpszURL, 0, 1, 0x9000u, &v23, 0, &bstrString) )
    {
      if ( v23 )
      {
        ITS_CloseThreadScopedState();
        v10 = v23 & 0x7F;
        v22 = 0;
        if ( (int)_IsAppContainerEnabled(&v22) >= 0 && !v22 && (v23 & 0x7F) < 0x7B )
          v10 = 123;
        Integrity = IsoGetIntegrity(1);
        if ( v10 == Integrity )
        {
          if ( InternetGetCookieExW(lpszURL, lpszCookieName, lpszCookieData, pcchCookieData, dwFlags, 0) )
          {
            WindowsProcessInPIC = 0;
          }
          else
          {
            LastError = GetLastError();
            WindowsProcessInPIC = LastError;
            if ( LastError > 0 )
              WindowsProcessInPIC = (unsigned __int16)LastError | 0x80070000;
          }
          goto LABEL_53;
        }
        if ( (int)v10 >= Integrity || (unsigned int)IsMICHighProcess() )
        {
          WindowsProcessInPIC = -2147024884;
          goto LABEL_53;
        }
        v29 = 0;
        v24 = 0;
        hEvent = 0;
        hHandle = 0;
        v28 = 0;
        v27 = 0;
        v13 = bstrString;
        if ( (unsigned int)_CheckIfIELowUtilReady(v10) )
        {
          WindowsProcessInPIC = ObtainIELowUtilSyncObjects(0, v10, &v29, &hEvent, &v24, 0, 0, 0);
          if ( WindowsProcessInPIC < 0 )
            goto LABEL_53;
          WindowsProcessInPIC = ObtainIELowUtilSyncObjects(1, v10, 0, 0, 0, &hHandle, &v28, &v27);
          if ( WindowsProcessInPIC < 0 )
            goto LABEL_53;
        }
        else
        {
          WindowsProcessInPIC = ObtainIELowUtilSyncObjects(1, v10, &v29, &hEvent, &v24, &hHandle, &v28, &v27);
          if ( WindowsProcessInPIC < 0 )
            goto LABEL_53;
          if ( GetIEPathFromCsidlW(pszPath, 0x104u, 0x26u, v14) )
          {
            FileNameW = PathFindFileNameW(pszPath);
            if ( FileNameW )
            {
              WindowsProcessInPIC = StringCchCopyW(FileNameW, 260 - (FileNameW - pszPath), L"IELowutil.exe");
              if ( WindowsProcessInPIC < 0 )
                goto LABEL_53;
              PathQuoteSpacesW(pszPath);
              StringCchPrintfW(v32, 0x104u, L" -PID:%d", v10);
              WindowsProcessInPIC = StringCchCatW(pszPath, 0x104u, v32);
              if ( WindowsProcessInPIC < 0 )
                goto LABEL_53;
              WindowsProcessInPIC = IsoCreateWindowsProcessInPIC(pszPath, v10, 0, 0, v13, 0);
              if ( WindowsProcessInPIC < 0 )
                goto LABEL_53;
              _CheckIfIELowUtilReady(v10);
            }
          }
        }
        v16 = hHandle;
        v17 = WaitForSingleObject(hHandle, 0x2710u);
        v18 = v27;
        if ( (v17 & 0xFFFFFF7F) != 0 )
        {
          WindowsProcessInPIC = -2147024884;
          if ( v17 == 258 )
            WindowsProcessInPIC = -2147418113;
          goto LABEL_49;
        }
        v19 = (unsigned __int16 *)((char *)v27 + 4);
        *((_DWORD *)v27 + 11284) = dwFlags;
        *(_DWORD *)v18 = 1;
        *((_DWORD *)v18 + 11283) = 10240;
        WindowsProcessInPIC = StringCchCopyW(v19, 0x824u, lpszURL);
        if ( WindowsProcessInPIC >= 0 )
        {
          if ( !lpszCookieName )
          {
            *((_BYTE *)v18 + 45140) = 1;
            goto LABEL_39;
          }
          WindowsProcessInPIC = StringCchCopyW((unsigned __int16 *)v18 + 2086, 0x2800u, lpszCookieName);
          if ( WindowsProcessInPIC >= 0 )
          {
LABEL_39:
            if ( SetEvent(hEvent) )
            {
              if ( WaitForSingleObject(v24, 0x2710u) )
              {
                WindowsProcessInPIC = -2147418113;
              }
              else
              {
                WindowsProcessInPIC = *((_DWORD *)v18 + 11286);
                if ( WindowsProcessInPIC >= 0 )
                {
                  if ( !lpszCookieData
                    || (WindowsProcessInPIC = StringCchCopyW(
                                                lpszCookieData,
                                                *pcchCookieData,
                                                (const unsigned __int16 *)v18 + 12326),
                        WindowsProcessInPIC >= 0) )
                  {
                    *pcchCookieData = *((_DWORD *)v18 + 11283);
                  }
                }
              }
            }
            else
            {
              v20 = GetLastError();
              WindowsProcessInPIC = v20;
              if ( v20 > 0 )
                WindowsProcessInPIC = (unsigned __int16)v20 | 0x80070000;
            }
          }
        }
        ReleaseMutex(v16);
LABEL_49:
        _CleanUpIELowUtilSyncObjects(v29, hEvent, v24, v16, v28, v18);
        goto LABEL_53;
      }
      WindowsProcessInPIC = -2147024809;
    }
    ITS_CloseThreadScopedState();
  }
LABEL_53:
  SysFreeString(bstrString);
  return WindowsProcessInPIC;
}

```

## disassembly

```asm
0x18004b370  push    rbp
0x18004b372  push    rbx
0x18004b373  push    rsi
0x18004b374  push    rdi
0x18004b375  push    r12
0x18004b377  push    r13
0x18004b379  push    r14
0x18004b37b  push    r15
0x18004b37d  lea     rbp, [rsp-3B8h]
0x18004b385  sub     rsp, 4B8h
0x18004b38c  mov     rax, cs:__security_cookie
0x18004b393  xor     rax, rsp
0x18004b396  mov     [rbp+3F0h+var_50], rax
0x18004b39d  xor     esi, esi
0x18004b39f  mov     r14, r9
0x18004b3a2  mov     r13, r8
0x18004b3a5  mov     r12, rdx
0x18004b3a8  mov     r15, rcx
0x18004b3ab  mov     edi, 80070057h
0x18004b3b0  test    rcx, rcx
0x18004b3b3  jz      short loc_18004B3BC
0x18004b3b5  mov     ebx, esi
0x18004b3b7  test    r9, r9
0x18004b3ba  jnz     short loc_18004B3BE
0x18004b3bc  mov     ebx, edi
0x18004b3be  mov     [rsp+4F0h+var_4AC], esi
0x18004b3c2  mov     [rsp+4F0h+bstrString], rsi
0x18004b3c7  test    ebx, ebx
0x18004b3c9  js      loc_18004B81C
0x18004b3cf  call    cs:__imp_?ITS_CreateThreadScopedState@@YAXXZ; ITS_CreateThreadScopedState(void)
0x18004b3d6  nop     dword ptr [rax+rax+00h]
0x18004b3db  call    ?_ForceIETS@@YAJXZ; _ForceIETS(void)
0x18004b3e0  mov     ebx, eax
0x18004b3e2  test    eax, eax
0x18004b3e4  js      loc_18004B810
0x18004b3ea  xor     edx, edx
0x18004b3ec  lea     rax, [rsp+4F0h+bstrString]
0x18004b3f1  mov     [rsp+4F0h+var_4C0], rax
0x18004b3f6  mov     r9d, 9000h
0x18004b3fc  lea     rax, [rsp+4F0h+var_4AC]
0x18004b401  mov     [rsp+4F0h+lpReserved], rsi
0x18004b406  mov     rcx, r15
0x18004b409  mov     qword ptr [rsp+4F0h+var_4D0], rax
0x18004b40e  lea     r8d, [rdx+1]
0x18004b412  call    cs:__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z; LCIEGetRedirectionPolicyForURL2(ushort const *,int,int,ulong,ulong *,int *,ushort * *)
0x18004b419  nop     dword ptr [rax+rax+00h]
0x18004b41e  test    eax, eax
0x18004b420  jnz     loc_18004B810
0x18004b426  cmp     [rsp+4F0h+var_4AC], esi
0x18004b42a  jz      loc_18004B80E
0x18004b430  call    cs:__imp_?ITS_CloseThreadScopedState@@YAXXZ; ITS_CloseThreadScopedState(void)
0x18004b437  nop     dword ptr [rax+rax+00h]
0x18004b43c  movzx   edi, byte ptr [rsp+4F0h+var_4AC]
0x18004b441  lea     rcx, [rsp+4F0h+var_4B0]; bool *
0x18004b446  and     edi, 7Fh
0x18004b449  mov     [rsp+4F0h+var_4B0], sil
0x18004b44e  call    ?_IsAppContainerEnabled@@YAJPEA_N@Z; _IsAppContainerEnabled(bool *)
0x18004b453  test    eax, eax
0x18004b455  js      short loc_18004B46E
0x18004b457  cmp     [rsp+4F0h+var_4B0], sil
0x18004b45c  jnz     short loc_18004B46E
0x18004b45e  mov     al, byte ptr [rsp+4F0h+var_4AC]
0x18004b462  mov     ecx, 7Bh ; '{'
0x18004b467  and     al, 7Fh
0x18004b469  cmp     al, cl
0x18004b46b  cmovb   edi, ecx
0x18004b46e  mov     ecx, 1
0x18004b473  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18004b47a  nop     dword ptr [rax+rax+00h]
0x18004b47f  cmp     edi, eax
0x18004b481  jnz     short loc_18004B4D9
0x18004b483  mov     eax, [rbp+3F0h+dwFlags]
0x18004b489  mov     r9, r14; lpdwSize
0x18004b48c  mov     [rsp+4F0h+lpReserved], rsi; lpReserved
0x18004b491  mov     r8, r13; lpszCookieData
0x18004b494  mov     rdx, r12; lpszCookieName
0x18004b497  mov     [rsp+4F0h+var_4D0], eax; dwFlags
0x18004b49b  mov     rcx, r15; lpszUrl
0x18004b49e  call    cs:__imp_InternetGetCookieExW
0x18004b4a5  nop     dword ptr [rax+rax+00h]
0x18004b4aa  test    eax, eax
0x18004b4ac  jz      short loc_18004B4B5
0x18004b4ae  mov     ebx, esi
0x18004b4b0  jmp     loc_18004B81C
0x18004b4b5  call    cs:__imp_GetLastError
0x18004b4bc  nop     dword ptr [rax+rax+00h]
0x18004b4c1  mov     ebx, eax
0x18004b4c3  test    eax, eax
0x18004b4c5  jle     loc_18004B81C
0x18004b4cb  movzx   ebx, ax
0x18004b4ce  or      ebx, 80070000h
0x18004b4d4  jmp     loc_18004B81C
0x18004b4d9  jge     loc_18004B807
0x18004b4df  call    ?IsMICHighProcess@@YAHXZ; IsMICHighProcess(void)
0x18004b4e4  test    eax, eax
0x18004b4e6  jnz     loc_18004B807
0x18004b4ec  mov     [rsp+4F0h+var_480], rsi
0x18004b4f1  mov     ecx, edi
0x18004b4f3  mov     [rsp+4F0h+var_4A8], rsi
0x18004b4f8  mov     [rsp+4F0h+hEvent], rsi
0x18004b4fd  mov     [rsp+4F0h+hHandle], rsi
0x18004b502  mov     [rsp+4F0h+var_488], rsi
0x18004b507  mov     [rsp+4F0h+var_490], rsi
0x18004b50c  mov     rsi, [rsp+4F0h+bstrString]
0x18004b511  call    ?_CheckIfIELowUtilReady@@YAHW4_IsoIntegrity@@@Z; _CheckIfIELowUtilReady(_IsoIntegrity)
0x18004b516  lea     r9, [rsp+4F0h+hEvent]; void **
0x18004b51b  mov     edx, edi; unsigned int
0x18004b51d  lea     r8, [rsp+4F0h+var_480]; void **
0x18004b522  test    eax, eax
0x18004b524  jz      short loc_18004B593
0x18004b526  xor     esi, esi
0x18004b528  lea     rax, [rsp+4F0h+var_4A8]
0x18004b52d  mov     [rsp+4F0h+var_4B8], rsi; void **
0x18004b532  xor     ecx, ecx; bool
0x18004b534  mov     [rsp+4F0h+var_4C0], rsi; void **
0x18004b539  mov     [rsp+4F0h+lpReserved], rsi; void **
0x18004b53e  mov     qword ptr [rsp+4F0h+var_4D0], rax; void **
0x18004b543  call    ?ObtainIELowUtilSyncObjects@@YAJ_NKPEAPEAX11111@Z; ObtainIELowUtilSyncObjects(bool,ulong,void * *,void * *,void * *,void * *,void * *,void * *)
0x18004b548  mov     ebx, eax
0x18004b54a  test    eax, eax
0x18004b54c  js      loc_18004B81C
0x18004b552  lea     rax, [rsp+4F0h+var_490]
0x18004b557  xor     r9d, r9d; void **
0x18004b55a  mov     [rsp+4F0h+var_4B8], rax; void **
0x18004b55f  xor     r8d, r8d; void **
0x18004b562  lea     rax, [rsp+4F0h+var_488]
0x18004b567  mov     edx, edi; unsigned int
0x18004b569  mov     [rsp+4F0h+var_4C0], rax; void **
0x18004b56e  mov     cl, 1; bool
0x18004b570  lea     rax, [rsp+4F0h+hHandle]
0x18004b575  mov     [rsp+4F0h+lpReserved], rax; void **
0x18004b57a  mov     qword ptr [rsp+4F0h+var_4D0], rsi; void **
0x18004b57f  call    ?ObtainIELowUtilSyncObjects@@YAJ_NKPEAPEAX11111@Z; ObtainIELowUtilSyncObjects(bool,ulong,void * *,void * *,void * *,void * *,void * *,void * *)
0x18004b584  mov     ebx, eax
0x18004b586  test    eax, eax
0x18004b588  js      loc_18004B81C
0x18004b58e  jmp     loc_18004B6AE
0x18004b593  lea     rax, [rsp+4F0h+var_490]
0x18004b598  mov     cl, 1; bool
0x18004b59a  mov     [rsp+4F0h+var_4B8], rax; void **
0x18004b59f  lea     rax, [rsp+4F0h+var_488]
0x18004b5a4  mov     [rsp+4F0h+var_4C0], rax; void **
0x18004b5a9  lea     rax, [rsp+4F0h+hHandle]
0x18004b5ae  mov     [rsp+4F0h+lpReserved], rax; void **
0x18004b5b3  lea     rax, [rsp+4F0h+var_4A8]
0x18004b5b8  mov     qword ptr [rsp+4F0h+var_4D0], rax; void **
0x18004b5bd  call    ?ObtainIELowUtilSyncObjects@@YAJ_NKPEAPEAX11111@Z; ObtainIELowUtilSyncObjects(bool,ulong,void * *,void * *,void * *,void * *,void * *,void * *)
0x18004b5c2  mov     ebx, eax
0x18004b5c4  test    eax, eax
0x18004b5c6  js      loc_18004B81C
0x18004b5cc  mov     ebx, 104h
0x18004b5d1  lea     rcx, [rbp+3F0h+pszPath]; unsigned __int16 *
0x18004b5d5  mov     edx, ebx; unsigned int
0x18004b5d7  mov     r8d, 26h ; '&'; csidl
0x18004b5dd  call    ?GetIEPathFromCsidlW@@YA_NPEAGKK_N@Z; GetIEPathFromCsidlW(ushort *,ulong,ulong,bool)
0x18004b5e2  test    al, al
0x18004b5e4  jz      loc_18004B6AE
0x18004b5ea  lea     rcx, [rbp+3F0h+pszPath]; pszPath
0x18004b5ee  call    cs:__imp_PathFindFileNameW
0x18004b5f5  nop     dword ptr [rax+rax+00h]
0x18004b5fa  test    rax, rax
0x18004b5fd  jz      loc_18004B6AE
0x18004b603  lea     rdx, [rbp+3F0h+pszPath]
0x18004b607  mov     rcx, rax
0x18004b60a  sub     rcx, rdx
0x18004b60d  lea     r8, aIelowutilExe; "IELowutil.exe"
0x18004b614  sar     rcx, 1
0x18004b617  mov     edx, ebx
0x18004b619  sub     rdx, rcx; unsigned __int64
0x18004b61c  mov     rcx, rax; unsigned __int16 *
0x18004b61f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b624  mov     ebx, eax
0x18004b626  test    eax, eax
0x18004b628  js      loc_18004B81C
0x18004b62e  lea     rcx, [rbp+3F0h+pszPath]; lpsz
0x18004b632  call    cs:__imp_PathQuoteSpacesW
0x18004b639  nop     dword ptr [rax+rax+00h]
0x18004b63e  mov     ebx, 104h
0x18004b643  lea     r8, aPidD; " -PID:%d"
0x18004b64a  mov     edx, ebx; unsigned __int64
0x18004b64c  lea     rcx, [rbp+3F0h+var_260]; unsigned __int16 *
0x18004b653  mov     r9d, edi
0x18004b656  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b65b  lea     r8, [rbp+3F0h+var_260]; unsigned __int16 *
0x18004b662  mov     edx, ebx; unsigned __int64
0x18004b664  lea     rcx, [rbp+3F0h+pszPath]; unsigned __int16 *
0x18004b668  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004b66d  mov     ebx, eax
0x18004b66f  test    eax, eax
0x18004b671  js      loc_18004B81C
0x18004b677  mov     [rsp+4F0h+lpReserved], 0
0x18004b680  lea     rcx, [rbp+3F0h+pszPath]
0x18004b684  xor     r9d, r9d
0x18004b687  mov     qword ptr [rsp+4F0h+var_4D0], rsi
0x18004b68c  xor     r8d, r8d
0x18004b68f  mov     edx, edi
0x18004b691  call    cs:__imp_?IsoCreateWindowsProcessInPIC@@YAJPEAGKK_NPEBGPEAU_IsoWindowsContainer@@@Z; IsoCreateWindowsProcessInPIC(ushort *,ulong,ulong,bool,ushort const *,_IsoWindowsContainer *)
0x18004b698  nop     dword ptr [rax+rax+00h]
0x18004b69d  mov     ebx, eax
0x18004b69f  test    eax, eax
0x18004b6a1  js      loc_18004B81C
0x18004b6a7  mov     ecx, edi
0x18004b6a9  call    ?_CheckIfIELowUtilReady@@YAHW4_IsoIntegrity@@@Z; _CheckIfIELowUtilReady(_IsoIntegrity)
0x18004b6ae  mov     rsi, [rsp+4F0h+hHandle]
0x18004b6b3  mov     edx, 2710h; dwMilliseconds
0x18004b6b8  mov     rcx, rsi; hHandle
0x18004b6bb  call    cs:__imp_WaitForSingleObject
0x18004b6c2  nop     dword ptr [rax+rax+00h]
0x18004b6c7  mov     rdi, [rsp+4F0h+var_490]
0x18004b6cc  test    eax, 0FFFFFF7Fh
0x18004b6d1  jz      short loc_18004B6EA
0x18004b6d3  cmp     eax, 102h
0x18004b6d8  mov     ebx, 8007000Ch
0x18004b6dd  mov     ecx, 8000FFFFh
0x18004b6e2  cmovz   ebx, ecx
0x18004b6e5  jmp     loc_18004B7DF
0x18004b6ea  mov     eax, [rbp+3F0h+dwFlags]
0x18004b6f0  lea     rcx, [rdi+4]; unsigned __int16 *
0x18004b6f4  mov     r8, r15; unsigned __int16 *
0x18004b6f7  mov     [rdi+0B050h], eax
0x18004b6fd  mov     edx, 824h; unsigned __int64
0x18004b702  mov     dword ptr [rdi], 1
0x18004b708  mov     dword ptr [rdi+0B04Ch], 2800h
0x18004b712  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b717  mov     ebx, eax
0x18004b719  test    eax, eax
0x18004b71b  js      loc_18004B7D0
0x18004b721  test    r12, r12
0x18004b724  jz      short loc_18004B746
0x18004b726  lea     rcx, [rdi+104Ch]; unsigned __int16 *
0x18004b72d  mov     r8, r12; unsigned __int16 *
0x18004b730  mov     edx, 2800h; unsigned __int64
0x18004b735  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b73a  mov     ebx, eax
0x18004b73c  test    eax, eax
0x18004b73e  js      loc_18004B7D0
0x18004b744  jmp     short loc_18004B74D
0x18004b746  mov     byte ptr [rdi+0B054h], 1
0x18004b74d  mov     rcx, [rsp+4F0h+hEvent]; hEvent
0x18004b752  call    cs:__imp_SetEvent
0x18004b759  nop     dword ptr [rax+rax+00h]
0x18004b75e  test    eax, eax
0x18004b760  jz      short loc_18004B7B5
0x18004b762  mov     rcx, [rsp+4F0h+var_4A8]; hHandle
0x18004b767  mov     edx, 2710h; dwMilliseconds
0x18004b76c  call    cs:__imp_WaitForSingleObject
0x18004b773  nop     dword ptr [rax+rax+00h]
0x18004b778  test    eax, eax
0x18004b77a  jnz     short loc_18004B7AE
0x18004b77c  mov     ebx, [rdi+0B058h]
0x18004b782  test    ebx, ebx
0x18004b784  js      short loc_18004B7D0
0x18004b786  test    r13, r13
0x18004b789  jz      short loc_18004B7A3
0x18004b78b  mov     edx, [r14]; unsigned __int64
0x18004b78e  lea     r8, [rdi+604Ch]; unsigned __int16 *
0x18004b795  mov     rcx, r13; unsigned __int16 *
0x18004b798  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b79d  mov     ebx, eax
0x18004b79f  test    eax, eax
0x18004b7a1  js      short loc_18004B7D0
0x18004b7a3  mov     eax, [rdi+0B04Ch]
0x18004b7a9  mov     [r14], eax
0x18004b7ac  jmp     short loc_18004B7D0
0x18004b7ae  mov     ebx, 8000FFFFh
0x18004b7b3  jmp     short loc_18004B7D0
0x18004b7b5  call    cs:__imp_GetLastError
0x18004b7bc  nop     dword ptr [rax+rax+00h]
0x18004b7c1  mov     ebx, eax
0x18004b7c3  test    eax, eax
0x18004b7c5  jle     short loc_18004B7D0
0x18004b7c7  movzx   ebx, ax
0x18004b7ca  or      ebx, 80070000h
0x18004b7d0  mov     rcx, rsi; hMutex
0x18004b7d3  call    cs:__imp_ReleaseMutex
0x18004b7da  nop     dword ptr [rax+rax+00h]
0x18004b7df  mov     rax, [rsp+4F0h+var_488]
0x18004b7e4  mov     r9, rsi; void *
0x18004b7e7  mov     r8, [rsp+4F0h+var_4A8]; void *
0x18004b7ec  mov     rdx, [rsp+4F0h+hEvent]; void *
0x18004b7f1  mov     rcx, [rsp+4F0h+var_480]; void *
0x18004b7f6  mov     [rsp+4F0h+lpReserved], rdi; void *
0x18004b7fb  mov     qword ptr [rsp+4F0h+var_4D0], rax; void *
0x18004b800  call    ?_CleanUpIELowUtilSyncObjects@@YAXPEAX00000@Z; _CleanUpIELowUtilSyncObjects(void *,void *,void *,void *,void *,void *)
0x18004b805  jmp     short loc_18004B81C
0x18004b807  mov     ebx, 8007000Ch
0x18004b80c  jmp     short loc_18004B81C
0x18004b80e  mov     ebx, edi
0x18004b810  call    cs:__imp_?ITS_CloseThreadScopedState@@YAXXZ; ITS_CloseThreadScopedState(void)
0x18004b817  nop     dword ptr [rax+rax+00h]
0x18004b81c  mov     rcx, [rsp+4F0h+bstrString]; bstrString
0x18004b821  call    cs:__imp_SysFreeString
0x18004b828  nop     dword ptr [rax+rax+00h]
0x18004b82d  mov     eax, ebx
0x18004b82f  mov     rcx, [rbp+3F0h+var_50]
0x18004b836  xor     rcx, rsp; StackCookie
0x18004b839  call    __security_check_cookie
0x18004b83e  add     rsp, 4B8h
0x18004b845  pop     r15
0x18004b847  pop     r14
  ... truncated ...
```
