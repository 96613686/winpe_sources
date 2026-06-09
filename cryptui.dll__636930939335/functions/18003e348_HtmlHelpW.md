# HtmlHelpW

- ea: `0x18003e348`
- end: `0x18003e44f`
- name: `HtmlHelpW`
- size: `263`
- prototype: `HWND __stdcall(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800323e0`

## callees

- `0x18003e22c`
- `0x18003e348`
- `0x18003e582`
- `0x18003e5c0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18003e3ab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18003e3d2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18003e3ab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18003e3d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003e3f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003e3f7`

## pseudocode

```c
HWND __stdcall HtmlHelpW(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)
{
  HMODULE Library; // rax
  HWND (*v7)(HWND, const unsigned __int16 *, unsigned int, unsigned __int64); // r10
  CHAR LibFileName[272]; // [rsp+30h] [rbp-128h] BYREF

  Library = hModule;
  if ( hModule
    || dword_180050EF0
    || ((memset_0(LibFileName, 0, 0x104u), !(unsigned int)GetRegisteredLocation(LibFileName))
      ? (Library = hModule)
      : (Library = LoadLibraryExA(LibFileName, 0, 0), hModule = Library),
        Library || (Library = LoadLibraryExA("hhctrl.ocx", 0, 0), (hModule = Library) != 0)) )
  {
    v7 = pHtmlHelpW;
    if ( pHtmlHelpW )
      return (HWND)((__int64 (__fastcall *)(HWND, LPCWSTR, _QWORD, _QWORD))v7)(hwndCaller, pszFile, 0, 0);
    pHtmlHelpW = (HWND (*)(HWND, const unsigned __int16 *, unsigned int, unsigned __int64))GetProcAddress(
                                                                                             Library,
                                                                                             (LPCSTR)0xF);
    v7 = pHtmlHelpW;
    if ( pHtmlHelpW )
      return (HWND)((__int64 (__fastcall *)(HWND, LPCWSTR, _QWORD, _QWORD))v7)(hwndCaller, pszFile, 0, 0);
  }
  dword_180050EF0 = 1;
  return 0;
}

```

## disassembly

```asm
0x18003e348  mov     [rsp+arg_10], rbx
0x18003e34d  push    rdi
0x18003e34e  sub     rsp, 150h
0x18003e355  mov     rax, cs:__security_cookie
0x18003e35c  xor     rax, rsp
0x18003e35f  mov     [rsp+158h+var_18], rax
0x18003e367  mov     rax, cs:hModule
0x18003e36e  mov     rdi, rdx
0x18003e371  mov     rbx, rcx
0x18003e374  test    rax, rax
0x18003e377  jnz     short loc_18003E3E4
0x18003e379  cmp     cs:dword_180050EF0, eax
0x18003e37f  jnz     short loc_18003E3E4
0x18003e381  xor     edx, edx; Val
0x18003e383  lea     rcx, [rsp+158h+LibFileName]; void *
0x18003e388  mov     r8d, 104h; Size
0x18003e38e  call    memset_0
0x18003e393  lea     rcx, [rsp+158h+LibFileName]; char *
0x18003e398  call    GetRegisteredLocation
0x18003e39d  test    eax, eax
0x18003e39f  jz      short loc_18003E3BA
0x18003e3a1  xor     r8d, r8d; dwFlags
0x18003e3a4  lea     rcx, [rsp+158h+LibFileName]; lpLibFileName
0x18003e3a9  xor     edx, edx; hFile
0x18003e3ab  call    cs:__imp_LoadLibraryExA
0x18003e3b1  mov     cs:hModule, rax
0x18003e3b8  jmp     short loc_18003E3C1
0x18003e3ba  mov     rax, cs:hModule
0x18003e3c1  test    rax, rax
0x18003e3c4  jnz     short loc_18003E3E4
0x18003e3c6  xor     r8d, r8d; dwFlags
0x18003e3c9  lea     rcx, aHhctrlOcx; "hhctrl.ocx"
0x18003e3d0  xor     edx, edx; hFile
0x18003e3d2  call    cs:__imp_LoadLibraryExA
0x18003e3d8  mov     cs:hModule, rax
0x18003e3df  test    rax, rax
0x18003e3e2  jz      short loc_18003E40C
0x18003e3e4  mov     r10, cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x18003e3eb  test    r10, r10
0x18003e3ee  jnz     short loc_18003E41A
0x18003e3f0  lea     edx, [r10+0Fh]; lpProcName
0x18003e3f4  mov     rcx, rax; hModule
0x18003e3f7  call    cs:__imp_GetProcAddress
0x18003e3fd  mov     cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA, rax; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x18003e404  mov     r10, rax
0x18003e407  test    rax, rax
0x18003e40a  jnz     short loc_18003E41A
0x18003e40c  mov     cs:dword_180050EF0, 1
0x18003e416  xor     eax, eax
0x18003e418  jmp     short loc_18003E42E
0x18003e41a  xor     r9d, r9d
0x18003e41d  xor     r8d, r8d
0x18003e420  mov     rdx, rdi
0x18003e423  mov     rcx, rbx
0x18003e426  mov     rax, r10
0x18003e429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e42e  mov     rcx, [rsp+158h+var_18]
0x18003e436  xor     rcx, rsp; StackCookie
0x18003e439  call    __security_check_cookie
0x18003e43e  mov     rbx, [rsp+158h+arg_10]
0x18003e446  add     rsp, 150h
0x18003e44d  pop     rdi
0x18003e44e  retn
```
