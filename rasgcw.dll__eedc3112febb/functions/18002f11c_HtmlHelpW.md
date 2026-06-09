# HtmlHelpW

- ea: `0x18002f11c`
- end: `0x18002f218`
- name: `HtmlHelpW`
- size: `252`
- prototype: `HWND __stdcall(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022d10`

## callees

- `0x18002f000`
- `0x18002f11c`
- `0x18002f382`
- `0x18002f3b0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f1c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f1c4`
- `KERNEL32!LoadLibraryExA` at `0x18002f178`
- `KERNEL32!LoadLibraryExA` at `0x18002f19f`
- `KERNEL32!LoadLibraryExA` at `0x18002f178`
- `KERNEL32!LoadLibraryExA` at `0x18002f19f`

## pseudocode

```c
HWND __stdcall HtmlHelpW(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)
{
  HMODULE Library; // rax
  HWND (*v6)(HWND, const unsigned __int16 *, unsigned int, unsigned __int64); // r10
  CHAR LibFileName[272]; // [rsp+30h] [rbp-128h] BYREF

  Library = qword_18004DCC0;
  if ( qword_18004DCC0
    || dword_18004DCB8
    || ((memset_0(LibFileName, 0, 0x104u), !(unsigned int)GetRegisteredLocation(LibFileName))
      ? (Library = qword_18004DCC0)
      : (Library = LoadLibraryExA(LibFileName, 0, 0), qword_18004DCC0 = Library),
        Library || (Library = LoadLibraryExA("hhctrl.ocx", 0, 0), (qword_18004DCC0 = Library) != 0)) )
  {
    v6 = pHtmlHelpW;
    if ( pHtmlHelpW )
      return (HWND)((__int64 (__fastcall *)(HWND, const wchar_t *, _QWORD, _QWORD))v6)(
                     hwndCaller,
                     L"password.chm::/datalos.htm",
                     0,
                     0);
    pHtmlHelpW = (HWND (*)(HWND, const unsigned __int16 *, unsigned int, unsigned __int64))GetProcAddress(
                                                                                             Library,
                                                                                             (LPCSTR)0xF);
    v6 = pHtmlHelpW;
    if ( pHtmlHelpW )
      return (HWND)((__int64 (__fastcall *)(HWND, const wchar_t *, _QWORD, _QWORD))v6)(
                     hwndCaller,
                     L"password.chm::/datalos.htm",
                     0,
                     0);
  }
  dword_18004DCB8 = 1;
  return 0;
}

```

## disassembly

```asm
0x18002f11c  push    rbx
0x18002f11e  sub     rsp, 150h
0x18002f125  mov     rax, cs:__security_cookie
0x18002f12c  xor     rax, rsp
0x18002f12f  mov     [rsp+158h+var_18], rax
0x18002f137  mov     rax, cs:qword_18004DCC0
0x18002f13e  mov     rbx, rcx
0x18002f141  test    rax, rax
0x18002f144  jnz     short loc_18002F1B1
0x18002f146  cmp     cs:dword_18004DCB8, eax
0x18002f14c  jnz     short loc_18002F1B1
0x18002f14e  xor     edx, edx; Val
0x18002f150  lea     rcx, [rsp+158h+LibFileName]; void *
0x18002f155  mov     r8d, 104h; Size
0x18002f15b  call    memset_0
0x18002f160  lea     rcx, [rsp+158h+LibFileName]; char *
0x18002f165  call    GetRegisteredLocation
0x18002f16a  test    eax, eax
0x18002f16c  jz      short loc_18002F187
0x18002f16e  xor     r8d, r8d; dwFlags
0x18002f171  lea     rcx, [rsp+158h+LibFileName]; lpLibFileName
0x18002f176  xor     edx, edx; hFile
0x18002f178  call    cs:__imp_LoadLibraryExA
0x18002f17e  mov     cs:qword_18004DCC0, rax
0x18002f185  jmp     short loc_18002F18E
0x18002f187  mov     rax, cs:qword_18004DCC0
0x18002f18e  test    rax, rax
0x18002f191  jnz     short loc_18002F1B1
0x18002f193  xor     r8d, r8d; dwFlags
0x18002f196  lea     rcx, aHhctrlOcx; "hhctrl.ocx"
0x18002f19d  xor     edx, edx; hFile
0x18002f19f  call    cs:__imp_LoadLibraryExA
0x18002f1a5  mov     cs:qword_18004DCC0, rax
0x18002f1ac  test    rax, rax
0x18002f1af  jz      short loc_18002F1D9
0x18002f1b1  mov     r10, cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x18002f1b8  test    r10, r10
0x18002f1bb  jnz     short loc_18002F1E7
0x18002f1bd  lea     edx, [r10+0Fh]; lpProcName
0x18002f1c1  mov     rcx, rax; hModule
0x18002f1c4  call    cs:__imp_GetProcAddress
0x18002f1ca  mov     cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA, rax; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x18002f1d1  mov     r10, rax
0x18002f1d4  test    rax, rax
0x18002f1d7  jnz     short loc_18002F1E7
0x18002f1d9  mov     cs:dword_18004DCB8, 1
0x18002f1e3  xor     eax, eax
0x18002f1e5  jmp     short loc_18002F1FF
0x18002f1e7  xor     r9d, r9d
0x18002f1ea  lea     rdx, aPasswordChmDat; "password.chm::/datalos.htm"
0x18002f1f1  xor     r8d, r8d
0x18002f1f4  mov     rcx, rbx
0x18002f1f7  mov     rax, r10
0x18002f1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1ff  mov     rcx, [rsp+158h+var_18]
0x18002f207  xor     rcx, rsp; StackCookie
0x18002f20a  call    __security_check_cookie
0x18002f20f  add     rsp, 150h
0x18002f216  pop     rbx
0x18002f217  retn
```
