# IEGetProtectedModeCookie

- ea: `0x18004aff0`
- end: `0x18004b46e`
- name: `IEGetProtectedModeCookie`
- size: `1150`
- prototype: `HRESULT __stdcall(LPCWSTR lpszURL, LPCWSTR lpszCookieName, LPWSTR lpszCookieData, DWORD *pcchCookieData, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000c530`
- `0x18000f3d0`
- `0x180011230`
- `0x18004aff0`
- `0x18004b474`
- `0x18004b5b0`
- `0x18004b624`
- `0x18008c200`
- `0x1800b27a0`
- `0x1800c6370`
- `0x1803eb590`
- `0x18054e310`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18004b392`
- `KERNEL32!SetEvent` at `0x18004b392`
- `KERNEL32!GetLastError` at `0x18004b117`
- `KERNEL32!GetLastError` at `0x18004b3e9`
- `KERNEL32!GetLastError` at `0x18004b117`
- `KERNEL32!GetLastError` at `0x18004b3e9`
- `KERNEL32!ReleaseMutex` at `0x18004b401`
- `KERNEL32!ReleaseMutex` at `0x18004b401`
- `KERNEL32!WaitForSingleObject` at `0x18004b305`
- `KERNEL32!WaitForSingleObject` at `0x18004b3a6`
- `KERNEL32!WaitForSingleObject` at `0x18004b305`
- `KERNEL32!WaitForSingleObject` at `0x18004b3a6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathQuoteSpacesW` at `0x18004b288`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathQuoteSpacesW` at `0x18004b288`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18004b24a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18004b24a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b443`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b443`
- `iertutil!__imp_?ITS_CreateThreadScopedState@@YAXXZ` at `0x18004b04f`
- `iertutil!__imp_?ITS_CreateThreadScopedState@@YAXXZ` at `0x18004b04f`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x18004b0a4`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x18004b438`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x18004b0a4`
- `iertutil!__imp_?ITS_CloseThreadScopedState@@YAXXZ` at `0x18004b438`
- `WININET!InternetGetCookieExW` at `0x18004b106`
- `WININET!InternetGetCookieExW` at `0x18004b106`
- `msIso!__imp_?IsoCreateWindowsProcessInPIC@@YAJPEAGKK_NPEBGPEAU_IsoWindowsContainer@@@Z` at `0x18004b2e1`
- `msIso!__imp_?IsoCreateWindowsProcessInPIC@@YAJPEAGKK_NPEBGPEAU_IsoWindowsContainer@@@Z` at `0x18004b2e1`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18004b0e1`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18004b0e1`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x18004b08c`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x18004b08c`

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
0x18004aff0  push    rbp
0x18004aff2  push    rbx
0x18004aff3  push    rsi
0x18004aff4  push    rdi
0x18004aff5  push    r12
0x18004aff7  push    r13
0x18004aff9  push    r14
0x18004affb  push    r15
0x18004affd  lea     rbp, [rsp-3B8h]
0x18004b005  sub     rsp, 4B8h
0x18004b00c  mov     rax, cs:__security_cookie
0x18004b013  xor     rax, rsp
0x18004b016  mov     [rbp+3F0h+var_50], rax
0x18004b01d  xor     esi, esi
0x18004b01f  mov     r14, r9
0x18004b022  mov     r13, r8
0x18004b025  mov     r12, rdx
0x18004b028  mov     r15, rcx
0x18004b02b  mov     edi, 80070057h
0x18004b030  test    rcx, rcx
0x18004b033  jz      short loc_18004B03C
0x18004b035  mov     ebx, esi
0x18004b037  test    r9, r9
0x18004b03a  jnz     short loc_18004B03E
0x18004b03c  mov     ebx, edi
0x18004b03e  mov     [rsp+4F0h+var_4AC], esi
0x18004b042  mov     [rsp+4F0h+bstrString], rsi
0x18004b047  test    ebx, ebx
0x18004b049  js      loc_18004B43E
0x18004b04f  call    cs:__imp_?ITS_CreateThreadScopedState@@YAXXZ; ITS_CreateThreadScopedState(void)
0x18004b055  call    ?_ForceIETS@@YAJXZ; _ForceIETS(void)
0x18004b05a  mov     ebx, eax
0x18004b05c  test    eax, eax
0x18004b05e  js      loc_18004B438
0x18004b064  xor     edx, edx
0x18004b066  lea     rax, [rsp+4F0h+bstrString]
0x18004b06b  mov     [rsp+4F0h+var_4C0], rax
0x18004b070  mov     r9d, 9000h
0x18004b076  lea     rax, [rsp+4F0h+var_4AC]
0x18004b07b  mov     [rsp+4F0h+lpReserved], rsi
0x18004b080  mov     rcx, r15
0x18004b083  mov     qword ptr [rsp+4F0h+var_4D0], rax
0x18004b088  lea     r8d, [rdx+1]
0x18004b08c  call    cs:__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z; LCIEGetRedirectionPolicyForURL2(ushort const *,int,int,ulong,ulong *,int *,ushort * *)
0x18004b092  test    eax, eax
0x18004b094  jnz     loc_18004B438
0x18004b09a  cmp     [rsp+4F0h+var_4AC], esi
0x18004b09e  jz      loc_18004B436
0x18004b0a4  call    cs:__imp_?ITS_CloseThreadScopedState@@YAXXZ; ITS_CloseThreadScopedState(void)
0x18004b0aa  movzx   edi, byte ptr [rsp+4F0h+var_4AC]
0x18004b0af  lea     rcx, [rsp+4F0h+var_4B0]; bool *
0x18004b0b4  and     edi, 7Fh
0x18004b0b7  mov     [rsp+4F0h+var_4B0], sil
0x18004b0bc  call    ?_IsAppContainerEnabled@@YAJPEA_N@Z; _IsAppContainerEnabled(bool *)
0x18004b0c1  test    eax, eax
0x18004b0c3  js      short loc_18004B0DC
0x18004b0c5  cmp     [rsp+4F0h+var_4B0], sil
0x18004b0ca  jnz     short loc_18004B0DC
0x18004b0cc  mov     al, byte ptr [rsp+4F0h+var_4AC]
0x18004b0d0  mov     ecx, 7Bh ; '{'
0x18004b0d5  and     al, 7Fh
0x18004b0d7  cmp     al, cl
0x18004b0d9  cmovb   edi, ecx
0x18004b0dc  mov     ecx, 1
0x18004b0e1  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18004b0e7  cmp     edi, eax
0x18004b0e9  jnz     short loc_18004B135
0x18004b0eb  mov     eax, [rbp+3F0h+dwFlags]
0x18004b0f1  mov     r9, r14; lpdwSize
0x18004b0f4  mov     [rsp+4F0h+lpReserved], rsi; lpReserved
0x18004b0f9  mov     r8, r13; lpszCookieData
0x18004b0fc  mov     rdx, r12; lpszCookieName
0x18004b0ff  mov     [rsp+4F0h+var_4D0], eax; dwFlags
0x18004b103  mov     rcx, r15; lpszUrl
0x18004b106  call    cs:__imp_InternetGetCookieExW
0x18004b10c  test    eax, eax
0x18004b10e  jz      short loc_18004B117
0x18004b110  mov     ebx, esi
0x18004b112  jmp     loc_18004B43E
0x18004b117  call    cs:__imp_GetLastError
0x18004b11d  mov     ebx, eax
0x18004b11f  test    eax, eax
0x18004b121  jle     loc_18004B43E
0x18004b127  movzx   ebx, ax
0x18004b12a  or      ebx, 80070000h
0x18004b130  jmp     loc_18004B43E
0x18004b135  jge     loc_18004B42F
0x18004b13b  call    ?IsMICHighProcess@@YAHXZ; IsMICHighProcess(void)
0x18004b140  test    eax, eax
0x18004b142  jnz     loc_18004B42F
0x18004b148  mov     [rsp+4F0h+var_480], rsi
0x18004b14d  mov     ecx, edi
0x18004b14f  mov     [rsp+4F0h+var_4A8], rsi
0x18004b154  mov     [rsp+4F0h+hEvent], rsi
0x18004b159  mov     [rsp+4F0h+hHandle], rsi
0x18004b15e  mov     [rsp+4F0h+var_488], rsi
0x18004b163  mov     [rsp+4F0h+var_490], rsi
0x18004b168  mov     rsi, [rsp+4F0h+bstrString]
0x18004b16d  call    ?_CheckIfIELowUtilReady@@YAHW4_IsoIntegrity@@@Z; _CheckIfIELowUtilReady(_IsoIntegrity)
0x18004b172  lea     r9, [rsp+4F0h+hEvent]; void **
0x18004b177  mov     edx, edi; unsigned int
0x18004b179  lea     r8, [rsp+4F0h+var_480]; void **
0x18004b17e  test    eax, eax
0x18004b180  jz      short loc_18004B1EF
0x18004b182  xor     esi, esi
0x18004b184  lea     rax, [rsp+4F0h+var_4A8]
0x18004b189  mov     [rsp+4F0h+var_4B8], rsi; void **
0x18004b18e  xor     ecx, ecx; bool
0x18004b190  mov     [rsp+4F0h+var_4C0], rsi; void **
0x18004b195  mov     [rsp+4F0h+lpReserved], rsi; void **
0x18004b19a  mov     qword ptr [rsp+4F0h+var_4D0], rax; void **
0x18004b19f  call    ?ObtainIELowUtilSyncObjects@@YAJ_NKPEAPEAX11111@Z; ObtainIELowUtilSyncObjects(bool,ulong,void * *,void * *,void * *,void * *,void * *,void * *)
0x18004b1a4  mov     ebx, eax
0x18004b1a6  test    eax, eax
0x18004b1a8  js      loc_18004B43E
0x18004b1ae  lea     rax, [rsp+4F0h+var_490]
0x18004b1b3  xor     r9d, r9d; void **
0x18004b1b6  mov     [rsp+4F0h+var_4B8], rax; void **
0x18004b1bb  xor     r8d, r8d; void **
0x18004b1be  lea     rax, [rsp+4F0h+var_488]
0x18004b1c3  mov     edx, edi; unsigned int
0x18004b1c5  mov     [rsp+4F0h+var_4C0], rax; void **
0x18004b1ca  mov     cl, 1; bool
0x18004b1cc  lea     rax, [rsp+4F0h+hHandle]
0x18004b1d1  mov     [rsp+4F0h+lpReserved], rax; void **
0x18004b1d6  mov     qword ptr [rsp+4F0h+var_4D0], rsi; void **
0x18004b1db  call    ?ObtainIELowUtilSyncObjects@@YAJ_NKPEAPEAX11111@Z; ObtainIELowUtilSyncObjects(bool,ulong,void * *,void * *,void * *,void * *,void * *,void * *)
0x18004b1e0  mov     ebx, eax
0x18004b1e2  test    eax, eax
0x18004b1e4  js      loc_18004B43E
0x18004b1ea  jmp     loc_18004B2F8
0x18004b1ef  lea     rax, [rsp+4F0h+var_490]
0x18004b1f4  mov     cl, 1; bool
0x18004b1f6  mov     [rsp+4F0h+var_4B8], rax; void **
0x18004b1fb  lea     rax, [rsp+4F0h+var_488]
0x18004b200  mov     [rsp+4F0h+var_4C0], rax; void **
0x18004b205  lea     rax, [rsp+4F0h+hHandle]
0x18004b20a  mov     [rsp+4F0h+lpReserved], rax; void **
0x18004b20f  lea     rax, [rsp+4F0h+var_4A8]
0x18004b214  mov     qword ptr [rsp+4F0h+var_4D0], rax; void **
0x18004b219  call    ?ObtainIELowUtilSyncObjects@@YAJ_NKPEAPEAX11111@Z; ObtainIELowUtilSyncObjects(bool,ulong,void * *,void * *,void * *,void * *,void * *,void * *)
0x18004b21e  mov     ebx, eax
0x18004b220  test    eax, eax
0x18004b222  js      loc_18004B43E
0x18004b228  mov     ebx, 104h
0x18004b22d  lea     rcx, [rbp+3F0h+pszPath]; unsigned __int16 *
0x18004b231  mov     edx, ebx; unsigned int
0x18004b233  mov     r8d, 26h ; '&'; csidl
0x18004b239  call    ?GetIEPathFromCsidlW@@YA_NPEAGKK_N@Z; GetIEPathFromCsidlW(ushort *,ulong,ulong,bool)
0x18004b23e  test    al, al
0x18004b240  jz      loc_18004B2F8
0x18004b246  lea     rcx, [rbp+3F0h+pszPath]; pszPath
0x18004b24a  call    cs:__imp_PathFindFileNameW
0x18004b250  test    rax, rax
0x18004b253  jz      loc_18004B2F8
0x18004b259  lea     rdx, [rbp+3F0h+pszPath]
0x18004b25d  mov     rcx, rax
0x18004b260  sub     rcx, rdx
0x18004b263  lea     r8, aIelowutilExe; "IELowutil.exe"
0x18004b26a  sar     rcx, 1
0x18004b26d  mov     edx, ebx
0x18004b26f  sub     rdx, rcx; unsigned __int64
0x18004b272  mov     rcx, rax; unsigned __int16 *
0x18004b275  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b27a  mov     ebx, eax
0x18004b27c  test    eax, eax
0x18004b27e  js      loc_18004B43E
0x18004b284  lea     rcx, [rbp+3F0h+pszPath]; lpsz
0x18004b288  call    cs:__imp_PathQuoteSpacesW
0x18004b28e  mov     ebx, 104h
0x18004b293  lea     r8, aPidD; " -PID:%d"
0x18004b29a  mov     edx, ebx; unsigned __int64
0x18004b29c  lea     rcx, [rbp+3F0h+var_260]; unsigned __int16 *
0x18004b2a3  mov     r9d, edi
0x18004b2a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b2ab  lea     r8, [rbp+3F0h+var_260]; unsigned __int16 *
0x18004b2b2  mov     edx, ebx; unsigned __int64
0x18004b2b4  lea     rcx, [rbp+3F0h+pszPath]; unsigned __int16 *
0x18004b2b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004b2bd  mov     ebx, eax
0x18004b2bf  test    eax, eax
0x18004b2c1  js      loc_18004B43E
0x18004b2c7  mov     [rsp+4F0h+lpReserved], 0
0x18004b2d0  lea     rcx, [rbp+3F0h+pszPath]
0x18004b2d4  xor     r9d, r9d
0x18004b2d7  mov     qword ptr [rsp+4F0h+var_4D0], rsi
0x18004b2dc  xor     r8d, r8d
0x18004b2df  mov     edx, edi
0x18004b2e1  call    cs:__imp_?IsoCreateWindowsProcessInPIC@@YAJPEAGKK_NPEBGPEAU_IsoWindowsContainer@@@Z; IsoCreateWindowsProcessInPIC(ushort *,ulong,ulong,bool,ushort const *,_IsoWindowsContainer *)
0x18004b2e7  mov     ebx, eax
0x18004b2e9  test    eax, eax
0x18004b2eb  js      loc_18004B43E
0x18004b2f1  mov     ecx, edi
0x18004b2f3  call    ?_CheckIfIELowUtilReady@@YAHW4_IsoIntegrity@@@Z; _CheckIfIELowUtilReady(_IsoIntegrity)
0x18004b2f8  mov     rsi, [rsp+4F0h+hHandle]
0x18004b2fd  mov     edx, 2710h; dwMilliseconds
0x18004b302  mov     rcx, rsi; hHandle
0x18004b305  call    cs:__imp_WaitForSingleObject
0x18004b30b  mov     rdi, [rsp+4F0h+var_490]
0x18004b310  test    eax, 0FFFFFF7Fh
0x18004b315  jz      short loc_18004B32E
0x18004b317  cmp     eax, 102h
0x18004b31c  mov     ebx, 8007000Ch
0x18004b321  mov     ecx, 8000FFFFh
0x18004b326  cmovz   ebx, ecx
0x18004b329  jmp     loc_18004B407
0x18004b32e  mov     eax, [rbp+3F0h+dwFlags]
0x18004b334  lea     rcx, [rdi+4]; unsigned __int16 *
0x18004b338  mov     r8, r15; unsigned __int16 *
0x18004b33b  mov     [rdi+0B050h], eax
0x18004b341  mov     edx, 824h; unsigned __int64
0x18004b346  mov     dword ptr [rdi], 1
0x18004b34c  mov     dword ptr [rdi+0B04Ch], 2800h
0x18004b356  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b35b  mov     ebx, eax
0x18004b35d  test    eax, eax
0x18004b35f  js      loc_18004B3FE
0x18004b365  test    r12, r12
0x18004b368  jz      short loc_18004B386
0x18004b36a  lea     rcx, [rdi+104Ch]; unsigned __int16 *
0x18004b371  mov     r8, r12; unsigned __int16 *
0x18004b374  mov     edx, 2800h; unsigned __int64
0x18004b379  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b37e  mov     ebx, eax
0x18004b380  test    eax, eax
0x18004b382  js      short loc_18004B3FE
0x18004b384  jmp     short loc_18004B38D
0x18004b386  mov     byte ptr [rdi+0B054h], 1
0x18004b38d  mov     rcx, [rsp+4F0h+hEvent]; hEvent
0x18004b392  call    cs:__imp_SetEvent
0x18004b398  test    eax, eax
0x18004b39a  jz      short loc_18004B3E9
0x18004b39c  mov     rcx, [rsp+4F0h+var_4A8]; hHandle
0x18004b3a1  mov     edx, 2710h; dwMilliseconds
0x18004b3a6  call    cs:__imp_WaitForSingleObject
0x18004b3ac  test    eax, eax
0x18004b3ae  jnz     short loc_18004B3E2
0x18004b3b0  mov     ebx, [rdi+0B058h]
0x18004b3b6  test    ebx, ebx
0x18004b3b8  js      short loc_18004B3FE
0x18004b3ba  test    r13, r13
0x18004b3bd  jz      short loc_18004B3D7
0x18004b3bf  mov     edx, [r14]; unsigned __int64
0x18004b3c2  lea     r8, [rdi+604Ch]; unsigned __int16 *
0x18004b3c9  mov     rcx, r13; unsigned __int16 *
0x18004b3cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b3d1  mov     ebx, eax
0x18004b3d3  test    eax, eax
0x18004b3d5  js      short loc_18004B3FE
0x18004b3d7  mov     eax, [rdi+0B04Ch]
0x18004b3dd  mov     [r14], eax
0x18004b3e0  jmp     short loc_18004B3FE
0x18004b3e2  mov     ebx, 8000FFFFh
0x18004b3e7  jmp     short loc_18004B3FE
0x18004b3e9  call    cs:__imp_GetLastError
0x18004b3ef  mov     ebx, eax
0x18004b3f1  test    eax, eax
0x18004b3f3  jle     short loc_18004B3FE
0x18004b3f5  movzx   ebx, ax
0x18004b3f8  or      ebx, 80070000h
0x18004b3fe  mov     rcx, rsi; hMutex
0x18004b401  call    cs:__imp_ReleaseMutex
0x18004b407  mov     rax, [rsp+4F0h+var_488]
0x18004b40c  mov     r9, rsi; void *
0x18004b40f  mov     r8, [rsp+4F0h+var_4A8]; void *
0x18004b414  mov     rdx, [rsp+4F0h+hEvent]; void *
0x18004b419  mov     rcx, [rsp+4F0h+var_480]; void *
0x18004b41e  mov     [rsp+4F0h+lpReserved], rdi; void *
0x18004b423  mov     qword ptr [rsp+4F0h+var_4D0], rax; void *
0x18004b428  call    ?_CleanUpIELowUtilSyncObjects@@YAXPEAX00000@Z; _CleanUpIELowUtilSyncObjects(void *,void *,void *,void *,void *,void *)
0x18004b42d  jmp     short loc_18004B43E
0x18004b42f  mov     ebx, 8007000Ch
0x18004b434  jmp     short loc_18004B43E
0x18004b436  mov     ebx, edi
0x18004b438  call    cs:__imp_?ITS_CloseThreadScopedState@@YAXXZ; ITS_CloseThreadScopedState(void)
0x18004b43e  mov     rcx, [rsp+4F0h+bstrString]; bstrString
0x18004b443  call    cs:__imp_SysFreeString
0x18004b449  mov     eax, ebx
0x18004b44b  mov     rcx, [rbp+3F0h+var_50]
0x18004b452  xor     rcx, rsp; StackCookie
0x18004b455  call    __security_check_cookie
0x18004b45a  add     rsp, 4B8h
0x18004b461  pop     r15
0x18004b463  pop     r14
0x18004b465  pop     r13
0x18004b467  pop     r12
0x18004b469  pop     rdi
0x18004b46a  pop     rsi
0x18004b46b  pop     rbx
0x18004b46c  pop     rbp
0x18004b46d  retn
```
