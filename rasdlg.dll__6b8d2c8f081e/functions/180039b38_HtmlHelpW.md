# HtmlHelpW

- ea: `0x180039b38`
- end: `0x180039c34`
- name: `HtmlHelpW`
- size: `252`
- prototype: `HWND __stdcall(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030000`

## callees

- `0x180039a10`
- `0x180039b38`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180039b94`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180039bbb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180039b94`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180039bbb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039be0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039be0`

## pseudocode

```c
HWND __stdcall HtmlHelpW(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)
{
  HMODULE Library; // rax
  HWND (*v6)(HWND, const unsigned __int16 *, unsigned int, unsigned __int64); // r10
  CHAR LibFileName[272]; // [rsp+30h] [rbp-128h] BYREF

  Library = qword_180064878;
  if ( qword_180064878
    || dword_180064874
    || ((memset_0(LibFileName, 0, 0x104u), !(unsigned int)GetRegisteredLocation(LibFileName))
      ? (Library = qword_180064878)
      : (Library = LoadLibraryExA(LibFileName, 0, 0), qword_180064878 = Library),
        Library || (Library = LoadLibraryExA("hhctrl.ocx", 0, 0), (qword_180064878 = Library) != 0)) )
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
  dword_180064874 = 1;
  return 0;
}

```

## disassembly

```asm
0x180039b38  push    rbx
0x180039b3a  sub     rsp, 150h
0x180039b41  mov     rax, cs:__security_cookie
0x180039b48  xor     rax, rsp
0x180039b4b  mov     [rsp+158h+var_18], rax
0x180039b53  mov     rax, cs:qword_180064878
0x180039b5a  mov     rbx, rcx
0x180039b5d  test    rax, rax
0x180039b60  jnz     short loc_180039BCD
0x180039b62  cmp     cs:dword_180064874, eax
0x180039b68  jnz     short loc_180039BCD
0x180039b6a  xor     edx, edx; Val
0x180039b6c  lea     rcx, [rsp+158h+LibFileName]; void *
0x180039b71  mov     r8d, 104h; Size
0x180039b77  call    memset_0
0x180039b7c  lea     rcx, [rsp+158h+LibFileName]; lpDst
0x180039b81  call    GetRegisteredLocation
0x180039b86  test    eax, eax
0x180039b88  jz      short loc_180039BA3
0x180039b8a  xor     r8d, r8d; dwFlags
0x180039b8d  lea     rcx, [rsp+158h+LibFileName]; lpLibFileName
0x180039b92  xor     edx, edx; hFile
0x180039b94  call    cs:__imp_LoadLibraryExA
0x180039b9a  mov     cs:qword_180064878, rax
0x180039ba1  jmp     short loc_180039BAA
0x180039ba3  mov     rax, cs:qword_180064878
0x180039baa  test    rax, rax
0x180039bad  jnz     short loc_180039BCD
0x180039baf  xor     r8d, r8d; dwFlags
0x180039bb2  lea     rcx, aHhctrlOcx; "hhctrl.ocx"
0x180039bb9  xor     edx, edx; hFile
0x180039bbb  call    cs:__imp_LoadLibraryExA
0x180039bc1  mov     cs:qword_180064878, rax
0x180039bc8  test    rax, rax
0x180039bcb  jz      short loc_180039BF5
0x180039bcd  mov     r10, cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x180039bd4  test    r10, r10
0x180039bd7  jnz     short loc_180039C03
0x180039bd9  lea     edx, [r10+0Fh]; lpProcName
0x180039bdd  mov     rcx, rax; hModule
0x180039be0  call    cs:__imp_GetProcAddress
0x180039be6  mov     cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA, rax; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x180039bed  mov     r10, rax
0x180039bf0  test    rax, rax
0x180039bf3  jnz     short loc_180039C03
0x180039bf5  mov     cs:dword_180064874, 1
0x180039bff  xor     eax, eax
0x180039c01  jmp     short loc_180039C1B
0x180039c03  xor     r9d, r9d
0x180039c06  lea     rdx, aPasswordChmDat; "password.chm::/datalos.htm"
0x180039c0d  xor     r8d, r8d
0x180039c10  mov     rcx, rbx
0x180039c13  mov     rax, r10
0x180039c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c1b  mov     rcx, [rsp+158h+var_18]
0x180039c23  xor     rcx, rsp; StackCookie
0x180039c26  call    __security_check_cookie
0x180039c2b  add     rsp, 150h
0x180039c32  pop     rbx
0x180039c33  retn
```
