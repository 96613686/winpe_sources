# NetInitializeInternetServices()

- ea: `0x10022628`
- end: `0x10022832`
- name: `_NetInitializeInternetServices@0`
- size: `522`
- prototype: `_DWORD __stdcall()`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x100234fb`
- `0x10023563`
- `0x10023815`
- `0x10023a8d`
- `0x10023bdb`
- `0x10024042`

## callees

- `0x10022628`
- `0x10032d47`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10022822`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10022822`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002264c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002266a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10022688`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100226a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100226c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100226e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10022700`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002271e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002273c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002275a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10022778`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10022796`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100227b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100227ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100227e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002264c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002266a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10022688`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100226a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100226c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100226e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10022700`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002271e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002273c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1002275a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10022778`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10022796`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100227b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100227ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100227e4`

## string_xrefs

- `0x1002262f`: `wininet.dll`
- `0x10022646`: `InternetOpenA`
- `0x1002265f`: `InternetOpenUrlA`
- `0x100226b9`: `InternetReadFile`
- `0x100226d7`: `InternetWriteFile`
- `0x1002274f`: `FtpDeleteFileA`
- `0x100227a5`: `FtpSetCurrentDirectoryA`

## pseudocode

```c
int __stdcall NetInitializeInternetServices()
{
  HMODULE Library; // eax

  Library = JetLoadLibraryExW(L"wininet.dll", 0, 0);
  hLibModule = Library;
  if ( Library )
  {
    InternetOpenA = (HINTERNET (__stdcall *)(LPCSTR, DWORD, LPCSTR, LPCSTR, DWORD))GetProcAddress(
                                                                                     Library,
                                                                                     "InternetOpenA");
    if ( InternetOpenA )
    {
      InternetOpenUrlA = (HINTERNET (__stdcall *)(HINTERNET, LPCSTR, LPCSTR, DWORD, DWORD, DWORD_PTR))GetProcAddress(hLibModule, "InternetOpenUrlA");
      if ( InternetOpenUrlA )
      {
        InternetCanonicalizeUrlA = (BOOL (__stdcall *)(LPCSTR, LPSTR, LPDWORD, DWORD))GetProcAddress(
                                                                                        hLibModule,
                                                                                        "InternetCanonicalizeUrlA");
        if ( InternetCanonicalizeUrlA )
        {
          InternetConnectA = (HINTERNET (__stdcall *)(HINTERNET, LPCSTR, INTERNET_PORT, LPCSTR, LPCSTR, DWORD, DWORD, DWORD_PTR))GetProcAddress(hLibModule, "InternetConnectA");
          if ( InternetConnectA )
          {
            InternetReadFile = (BOOL (__stdcall *)(HINTERNET, LPVOID, DWORD, LPDWORD))GetProcAddress(
                                                                                        hLibModule,
                                                                                        "InternetReadFile");
            if ( InternetReadFile )
            {
              InternetWriteFile = (BOOL (__stdcall *)(HINTERNET, LPCVOID, DWORD, LPDWORD))GetProcAddress(
                                                                                            hLibModule,
                                                                                            "InternetWriteFile");
              if ( InternetWriteFile )
              {
                InternetCloseHandle = (BOOL (__stdcall *)(HINTERNET))GetProcAddress(hLibModule, "InternetCloseHandle");
                if ( InternetCloseHandle )
                {
                  FtpGetFileA = (BOOL (__stdcall *)(HINTERNET, LPCSTR, LPCSTR, BOOL, DWORD, DWORD, DWORD_PTR))GetProcAddress(hLibModule, "FtpGetFileA");
                  if ( FtpGetFileA )
                  {
                    FtpPutFileA = (BOOL (__stdcall *)(HINTERNET, LPCSTR, LPCSTR, DWORD, DWORD_PTR))GetProcAddress(
                                                                                                     hLibModule,
                                                                                                     "FtpPutFileA");
                    if ( FtpPutFileA )
                    {
                      FtpDeleteFileA = (BOOL (__stdcall *)(HINTERNET, LPCSTR))GetProcAddress(
                                                                                hLibModule,
                                                                                "FtpDeleteFileA");
                      if ( FtpDeleteFileA )
                      {
                        FtpFindFirstFileA = (HINTERNET (__stdcall *)(HINTERNET, LPCSTR, LPWIN32_FIND_DATAA, DWORD, DWORD_PTR))GetProcAddress(hLibModule, "FtpFindFirstFileA");
                        if ( FtpFindFirstFileA )
                        {
                          InternetFindNextFileA = (BOOL (__stdcall *)(HINTERNET, LPVOID))GetProcAddress(
                                                                                           hLibModule,
                                                                                           "InternetFindNextFileA");
                          if ( InternetFindNextFileA )
                          {
                            FtpSetCurrentDirectoryA = (BOOL (__stdcall *)(HINTERNET, LPCSTR))GetProcAddress(
                                                                                               hLibModule,
                                                                                               "FtpSetCurrentDirectoryA");
                            if ( FtpSetCurrentDirectoryA )
                            {
                              InternetGetLastResponseInfoA = (BOOL (__stdcall *)(LPDWORD, LPSTR, LPDWORD))GetProcAddress(hLibModule, "InternetGetLastResponseInfoA");
                              if ( InternetGetLastResponseInfoA )
                              {
                                HttpQueryInfoA = (BOOL (__stdcall *)(HINTERNET, DWORD, LPVOID, LPDWORD, LPDWORD))GetProcAddress(hLibModule, "HttpQueryInfoA");
                                if ( HttpQueryInfoA )
                                {
                                  dword_1003AE18 = ((int (__thiscall *)(HINTERNET (__stdcall *)(LPCSTR, DWORD, LPCSTR, LPCSTR, DWORD), const char *, _DWORD, _DWORD, _DWORD, _DWORD))InternetOpenA)(
                                                     InternetOpenA,
                                                     "JET IISAM",
                                                     0,
                                                     0,
                                                     0,
                                                     0);
                                  if ( dword_1003AE18 )
                                    return 1;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    FreeLibrary(hLibModule);
    hLibModule = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x10022628  mov     edi, edi
0x1002262a  push    edi
0x1002262b  xor     edi, edi
0x1002262d  push    edi; int
0x1002262e  push    edi; hFile
0x1002262f  push    offset aWininetDll; "wininet.dll"
0x10022634  call    _JetLoadLibraryExW@12; JetLoadLibraryExW(x,x,x)
0x10022639  mov     hLibModule, eax
0x1002263e  test    eax, eax
0x10022640  jz      loc_1002282E
0x10022646  push    offset aInternetopena; "InternetOpenA"
0x1002264b  push    eax; hModule
0x1002264c  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10022652  mov     InternetOpenA, eax
0x10022657  test    eax, eax
0x10022659  jz      loc_1002281C
0x1002265f  push    offset aInternetopenur; "InternetOpenUrlA"
0x10022664  push    hLibModule; hModule
0x1002266a  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10022670  mov     InternetOpenUrlA, eax
0x10022675  test    eax, eax
0x10022677  jz      loc_1002281C
0x1002267d  push    offset aInternetcanoni; "InternetCanonicalizeUrlA"
0x10022682  push    hLibModule; hModule
0x10022688  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1002268e  mov     InternetCanonicalizeUrlA, eax
0x10022693  test    eax, eax
0x10022695  jz      loc_1002281C
0x1002269b  push    offset aInternetconnec; "InternetConnectA"
0x100226a0  push    hLibModule; hModule
0x100226a6  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100226ac  mov     InternetConnectA, eax
0x100226b1  test    eax, eax
0x100226b3  jz      loc_1002281C
0x100226b9  push    offset aInternetreadfi; "InternetReadFile"
0x100226be  push    hLibModule; hModule
0x100226c4  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100226ca  mov     InternetReadFile, eax
0x100226cf  test    eax, eax
0x100226d1  jz      loc_1002281C
0x100226d7  push    offset aInternetwritef; "InternetWriteFile"
0x100226dc  push    hLibModule; hModule
0x100226e2  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100226e8  mov     InternetWriteFile, eax
0x100226ed  test    eax, eax
0x100226ef  jz      loc_1002281C
0x100226f5  push    offset aInternetcloseh; "InternetCloseHandle"
0x100226fa  push    hLibModule; hModule
0x10022700  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10022706  mov     InternetCloseHandle, eax
0x1002270b  test    eax, eax
0x1002270d  jz      loc_1002281C
0x10022713  push    offset aFtpgetfilea; "FtpGetFileA"
0x10022718  push    hLibModule; hModule
0x1002271e  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10022724  mov     FtpGetFileA, eax
0x10022729  test    eax, eax
0x1002272b  jz      loc_1002281C
0x10022731  push    offset aFtpputfilea; "FtpPutFileA"
0x10022736  push    hLibModule; hModule
0x1002273c  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10022742  mov     FtpPutFileA, eax
0x10022747  test    eax, eax
0x10022749  jz      loc_1002281C
0x1002274f  push    offset aFtpdeletefilea; "FtpDeleteFileA"
0x10022754  push    hLibModule; hModule
0x1002275a  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10022760  mov     FtpDeleteFileA, eax
0x10022765  test    eax, eax
0x10022767  jz      loc_1002281C
0x1002276d  push    offset aFtpfindfirstfi; "FtpFindFirstFileA"
0x10022772  push    hLibModule; hModule
0x10022778  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1002277e  mov     FtpFindFirstFileA, eax
0x10022783  test    eax, eax
0x10022785  jz      loc_1002281C
0x1002278b  push    offset aInternetfindne; "InternetFindNextFileA"
0x10022790  push    hLibModule; hModule
0x10022796  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1002279c  mov     InternetFindNextFileA, eax
0x100227a1  test    eax, eax
0x100227a3  jz      short loc_1002281C
0x100227a5  push    offset aFtpsetcurrentd; "FtpSetCurrentDirectoryA"
0x100227aa  push    hLibModule; hModule
0x100227b0  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100227b6  mov     FtpSetCurrentDirectoryA, eax
0x100227bb  test    eax, eax
0x100227bd  jz      short loc_1002281C
0x100227bf  push    offset aInternetgetlas; "InternetGetLastResponseInfoA"
0x100227c4  push    hLibModule; hModule
0x100227ca  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100227d0  mov     InternetGetLastResponseInfoA, eax
0x100227d5  test    eax, eax
0x100227d7  jz      short loc_1002281C
0x100227d9  push    offset aHttpqueryinfoa; "HttpQueryInfoA"
0x100227de  push    hLibModule; hModule
0x100227e4  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100227ea  mov     HttpQueryInfoA, eax
0x100227ef  test    eax, eax
0x100227f1  jz      short loc_1002281C
0x100227f3  push    esi
0x100227f4  mov     esi, InternetOpenA
0x100227fa  mov     ecx, esi
0x100227fc  push    edi
0x100227fd  push    edi
0x100227fe  push    edi
0x100227ff  push    edi
0x10022800  push    offset aJetIisam; "JET IISAM"
0x10022805  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002280b  call    esi ; InternetOpenA
0x1002280d  mov     dword_1003AE18, eax
0x10022812  pop     esi
0x10022813  test    eax, eax
0x10022815  jz      short loc_1002281C
0x10022817  xor     eax, eax
0x10022819  inc     eax
0x1002281a  pop     edi
0x1002281b  retn
0x1002281c  push    hLibModule; hLibModule
0x10022822  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10022828  mov     hLibModule, edi
0x1002282e  xor     eax, eax
0x10022830  pop     edi
0x10022831  retn
```
