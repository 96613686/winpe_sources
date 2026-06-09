# NetInitializeInternetServices()

- ea: `0x1000ddd0`
- end: `0x1000df95`
- name: `_NetInitializeInternetServices@0`
- size: `453`
- prototype: `_DWORD __stdcall()`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1000d1c0`
- `0x1000d2c0`
- `0x1000d720`
- `0x1000d7a0`
- `0x1000d8d0`
- `0x1000db20`
- `0x1000e3b0`

## callees

- `0x1000ddd0`
- `0x1002b070`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1000ddf1`
- `KERNEL32!GetProcAddress` at `0x1000de0b`
- `KERNEL32!GetProcAddress` at `0x1000de25`
- `KERNEL32!GetProcAddress` at `0x1000de3f`
- `KERNEL32!GetProcAddress` at `0x1000de59`
- `KERNEL32!GetProcAddress` at `0x1000de73`
- `KERNEL32!GetProcAddress` at `0x1000de8d`
- `KERNEL32!GetProcAddress` at `0x1000dea7`
- `KERNEL32!GetProcAddress` at `0x1000dec1`
- `KERNEL32!GetProcAddress` at `0x1000dedb`
- `KERNEL32!GetProcAddress` at `0x1000def5`
- `KERNEL32!GetProcAddress` at `0x1000df0b`
- `KERNEL32!GetProcAddress` at `0x1000df21`
- `KERNEL32!GetProcAddress` at `0x1000df37`
- `KERNEL32!GetProcAddress` at `0x1000df4d`
- `KERNEL32!GetProcAddress` at `0x1000dde5`
- `KERNEL32!FreeLibrary` at `0x1000df81`
- `KERNEL32!FreeLibrary` at `0x1000df81`

## string_xrefs

- `0x1000ddd0`: `wininet.dll`
- `0x1000ddeb`: `InternetOpenA`
- `0x1000de00`: `InternetOpenUrlA`
- `0x1000de4e`: `InternetReadFile`
- `0x1000de68`: `InternetWriteFile`
- `0x1000ded0`: `FtpDeleteFileA`
- `0x1000df16`: `FtpSetCurrentDirectoryA`

## pseudocode

```c
HMODULE __stdcall NetInitializeInternetServices()
{
  HMODULE result; // eax

  result = (HMODULE)JetLoadLibraryW(L"wininet.dll");
  hLibModule = result;
  if ( result )
  {
    InternetOpenA = (HINTERNET (__stdcall *)(LPCSTR, DWORD, LPCSTR, LPCSTR, DWORD))GetProcAddress(
                                                                                     result,
                                                                                     "InternetOpenA");
    if ( !InternetOpenA )
      goto LABEL_19;
    InternetOpenUrlA = (HINTERNET (__stdcall *)(HINTERNET, LPCSTR, LPCSTR, DWORD, DWORD, DWORD_PTR))GetProcAddress(hLibModule, "InternetOpenUrlA");
    if ( !InternetOpenUrlA )
      goto LABEL_19;
    InternetCanonicalizeUrlA = (BOOL (__stdcall *)(LPCSTR, LPSTR, LPDWORD, DWORD))GetProcAddress(
                                                                                    hLibModule,
                                                                                    "InternetCanonicalizeUrlA");
    if ( !InternetCanonicalizeUrlA )
      goto LABEL_19;
    InternetConnectA = (HINTERNET (__stdcall *)(HINTERNET, LPCSTR, INTERNET_PORT, LPCSTR, LPCSTR, DWORD, DWORD, DWORD_PTR))GetProcAddress(hLibModule, "InternetConnectA");
    if ( !InternetConnectA )
      goto LABEL_19;
    InternetReadFile = (BOOL (__stdcall *)(HINTERNET, LPVOID, DWORD, LPDWORD))GetProcAddress(
                                                                                hLibModule,
                                                                                "InternetReadFile");
    if ( !InternetReadFile )
      goto LABEL_19;
    InternetWriteFile = (BOOL (__stdcall *)(HINTERNET, LPCVOID, DWORD, LPDWORD))GetProcAddress(
                                                                                  hLibModule,
                                                                                  "InternetWriteFile");
    if ( !InternetWriteFile )
      goto LABEL_19;
    InternetCloseHandle = (BOOL (__stdcall *)(HINTERNET))GetProcAddress(hLibModule, "InternetCloseHandle");
    if ( !InternetCloseHandle )
      goto LABEL_19;
    FtpGetFileA = (BOOL (__stdcall *)(HINTERNET, LPCSTR, LPCSTR, BOOL, DWORD, DWORD, DWORD_PTR))GetProcAddress(
                                                                                                  hLibModule,
                                                                                                  "FtpGetFileA");
    if ( !FtpGetFileA )
      goto LABEL_19;
    FtpPutFileA = (BOOL (__stdcall *)(HINTERNET, LPCSTR, LPCSTR, DWORD, DWORD_PTR))GetProcAddress(
                                                                                     hLibModule,
                                                                                     "FtpPutFileA");
    if ( !FtpPutFileA )
      goto LABEL_19;
    FtpDeleteFileA = (BOOL (__stdcall *)(HINTERNET, LPCSTR))GetProcAddress(hLibModule, "FtpDeleteFileA");
    if ( FtpDeleteFileA
      && (FtpFindFirstFileA = (HINTERNET (__stdcall *)(HINTERNET, LPCSTR, LPWIN32_FIND_DATAA, DWORD, DWORD_PTR))GetProcAddress(hLibModule, "FtpFindFirstFileA")) != 0
      && (InternetFindNextFileA = (BOOL (__stdcall *)(HINTERNET, LPVOID))GetProcAddress(
                                                                           hLibModule,
                                                                           "InternetFindNextFileA")) != 0
      && (FtpSetCurrentDirectoryA = (BOOL (__stdcall *)(HINTERNET, LPCSTR))GetProcAddress(
                                                                             hLibModule,
                                                                             "FtpSetCurrentDirectoryA")) != 0
      && (InternetGetLastResponseInfoA = (BOOL (__stdcall *)(LPDWORD, LPSTR, LPDWORD))GetProcAddress(
                                                                                        hLibModule,
                                                                                        "InternetGetLastResponseInfoA")) != 0
      && (HttpQueryInfoA = (BOOL (__stdcall *)(HINTERNET, DWORD, LPVOID, LPDWORD, LPDWORD))GetProcAddress(
                                                                                             hLibModule,
                                                                                             "HttpQueryInfoA")) != 0
      && (dword_10040FB8 = (int)InternetOpenA("JET IISAM", 0, 0, 0, 0)) != 0 )
    {
      return (HMODULE)1;
    }
    else
    {
LABEL_19:
      FreeLibrary(hLibModule);
      hLibModule = 0;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1000ddd0  push    offset aWininetDll; "wininet.dll"
0x1000ddd5  call    _JetLoadLibraryW@4; JetLoadLibraryW(x)
0x1000ddda  mov     hLibModule, eax
0x1000dddf  test    eax, eax
0x1000dde1  jnz     short loc_1000DDE4
0x1000dde3  retn
0x1000dde4  push    esi
0x1000dde5  mov     esi, ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1000ddeb  push    offset ProcName; "InternetOpenA"
0x1000ddf0  push    eax; hModule
0x1000ddf1  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000ddf3  mov     InternetOpenA, eax
0x1000ddf8  test    eax, eax
0x1000ddfa  jz      loc_1000DF7B
0x1000de00  push    offset aInternetopenur; "InternetOpenUrlA"
0x1000de05  push    hLibModule; hModule
0x1000de0b  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000de0d  mov     InternetOpenUrlA, eax
0x1000de12  test    eax, eax
0x1000de14  jz      loc_1000DF7B
0x1000de1a  push    offset aInternetcanoni; "InternetCanonicalizeUrlA"
0x1000de1f  push    hLibModule; hModule
0x1000de25  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000de27  mov     InternetCanonicalizeUrlA, eax
0x1000de2c  test    eax, eax
0x1000de2e  jz      loc_1000DF7B
0x1000de34  push    offset aInternetconnec; "InternetConnectA"
0x1000de39  push    hLibModule; hModule
0x1000de3f  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000de41  mov     InternetConnectA, eax
0x1000de46  test    eax, eax
0x1000de48  jz      loc_1000DF7B
0x1000de4e  push    offset aInternetreadfi; "InternetReadFile"
0x1000de53  push    hLibModule; hModule
0x1000de59  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000de5b  mov     InternetReadFile, eax
0x1000de60  test    eax, eax
0x1000de62  jz      loc_1000DF7B
0x1000de68  push    offset aInternetwritef; "InternetWriteFile"
0x1000de6d  push    hLibModule; hModule
0x1000de73  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000de75  mov     InternetWriteFile, eax
0x1000de7a  test    eax, eax
0x1000de7c  jz      loc_1000DF7B
0x1000de82  push    offset aInternetcloseh; "InternetCloseHandle"
0x1000de87  push    hLibModule; hModule
0x1000de8d  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000de8f  mov     InternetCloseHandle, eax
0x1000de94  test    eax, eax
0x1000de96  jz      loc_1000DF7B
0x1000de9c  push    offset aFtpgetfilea; "FtpGetFileA"
0x1000dea1  push    hLibModule; hModule
0x1000dea7  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000dea9  mov     FtpGetFileA, eax
0x1000deae  test    eax, eax
0x1000deb0  jz      loc_1000DF7B
0x1000deb6  push    offset aFtpputfilea; "FtpPutFileA"
0x1000debb  push    hLibModule; hModule
0x1000dec1  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000dec3  mov     FtpPutFileA, eax
0x1000dec8  test    eax, eax
0x1000deca  jz      loc_1000DF7B
0x1000ded0  push    offset aFtpdeletefilea; "FtpDeleteFileA"
0x1000ded5  push    hLibModule; hModule
0x1000dedb  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000dedd  mov     FtpDeleteFileA, eax
0x1000dee2  test    eax, eax
0x1000dee4  jz      loc_1000DF7B
0x1000deea  push    offset aFtpfindfirstfi; "FtpFindFirstFileA"
0x1000deef  push    hLibModule; hModule
0x1000def5  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000def7  mov     FtpFindFirstFileA, eax
0x1000defc  test    eax, eax
0x1000defe  jz      short loc_1000DF7B
0x1000df00  push    offset aInternetfindne; "InternetFindNextFileA"
0x1000df05  push    hLibModule; hModule
0x1000df0b  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000df0d  mov     InternetFindNextFileA, eax
0x1000df12  test    eax, eax
0x1000df14  jz      short loc_1000DF7B
0x1000df16  push    offset aFtpsetcurrentd; "FtpSetCurrentDirectoryA"
0x1000df1b  push    hLibModule; hModule
0x1000df21  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000df23  mov     FtpSetCurrentDirectoryA, eax
0x1000df28  test    eax, eax
0x1000df2a  jz      short loc_1000DF7B
0x1000df2c  push    offset aInternetgetlas; "InternetGetLastResponseInfoA"
0x1000df31  push    hLibModule; hModule
0x1000df37  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000df39  mov     InternetGetLastResponseInfoA, eax
0x1000df3e  test    eax, eax
0x1000df40  jz      short loc_1000DF7B
0x1000df42  push    offset aHttpqueryinfoa; "HttpQueryInfoA"
0x1000df47  push    hLibModule; hModule
0x1000df4d  call    esi ; GetProcAddress(x,x); GetProcAddress(x,x)
0x1000df4f  mov     HttpQueryInfoA, eax
0x1000df54  test    eax, eax
0x1000df56  jz      short loc_1000DF7B
0x1000df58  push    0
0x1000df5a  push    0
0x1000df5c  push    0
0x1000df5e  push    0
0x1000df60  push    offset aJetIisam; "JET IISAM"
0x1000df65  call    InternetOpenA
0x1000df6b  mov     dword_10040FB8, eax
0x1000df70  test    eax, eax
0x1000df72  jz      short loc_1000DF7B
0x1000df74  mov     eax, 1
0x1000df79  pop     esi
0x1000df7a  retn
0x1000df7b  push    hLibModule; hLibModule
0x1000df81  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1000df87  mov     hLibModule, 0
0x1000df91  xor     eax, eax
0x1000df93  pop     esi
0x1000df94  retn
```
