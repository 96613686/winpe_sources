# HtmlHelpW

- ea: `0x18007e42c`
- end: `0x18007e53a`
- name: `HtmlHelpW`
- size: `270`
- prototype: `HWND __stdcall(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050fb4`

## callees

- `0x18007e310`
- `0x18007e42c`
- `0x18007e6ca`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x18007e48f`
- `KERNEL32!LoadLibraryExA` at `0x18007e4b6`
- `KERNEL32!LoadLibraryExA` at `0x18007e48f`
- `KERNEL32!LoadLibraryExA` at `0x18007e4b6`
- `KERNEL32!GetProcAddress` at `0x18007e4db`
- `KERNEL32!GetProcAddress` at `0x18007e4db`

## pseudocode

```c
HWND __stdcall HtmlHelpW(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)
{
  HMODULE Library; // rax
  HWND (*v7)(HWND, const unsigned __int16 *, unsigned int, unsigned __int64); // r10
  CHAR LibFileName[272]; // [rsp+30h] [rbp-128h] BYREF

  Library = qword_1800C0660;
  if ( qword_1800C0660
    || dword_1800C0658
    || ((memset_0(LibFileName, 0, 0x104u), !(unsigned int)GetRegisteredLocation(LibFileName))
      ? (Library = qword_1800C0660)
      : (Library = LoadLibraryExA(LibFileName, 0, 0), qword_1800C0660 = Library),
        Library || (Library = LoadLibraryExA("hhctrl.ocx", 0, 0), (qword_1800C0660 = Library) != 0)) )
  {
    v7 = pHtmlHelpW;
    if ( pHtmlHelpW )
      return (HWND)((__int64 (__fastcall *)(HWND, const wchar_t *, __int64, DWORD_PTR))v7)(
                     hwndCaller,
                     L"MSDASC.CHM",
                     15,
                     dwData);
    pHtmlHelpW = (HWND (*)(HWND, const unsigned __int16 *, unsigned int, unsigned __int64))GetProcAddress(
                                                                                             Library,
                                                                                             (LPCSTR)0xF);
    v7 = pHtmlHelpW;
    if ( pHtmlHelpW )
      return (HWND)((__int64 (__fastcall *)(HWND, const wchar_t *, __int64, DWORD_PTR))v7)(
                     hwndCaller,
                     L"MSDASC.CHM",
                     15,
                     dwData);
  }
  dword_1800C0658 = 1;
  return 0;
}

```

## disassembly

```asm
0x18007e42c  mov     [rsp+arg_8], rbx
0x18007e431  push    rdi
0x18007e432  sub     rsp, 150h
0x18007e439  mov     rax, cs:__security_cookie
0x18007e440  xor     rax, rsp
0x18007e443  mov     [rsp+158h+var_18], rax
0x18007e44b  mov     rax, cs:qword_1800C0660
0x18007e452  mov     rdi, r9
0x18007e455  mov     rbx, rcx
0x18007e458  test    rax, rax
0x18007e45b  jnz     short loc_18007E4C8
0x18007e45d  cmp     cs:dword_1800C0658, eax
0x18007e463  jnz     short loc_18007E4C8
0x18007e465  xor     edx, edx; Val
0x18007e467  lea     rcx, [rsp+158h+LibFileName]; void *
0x18007e46c  mov     r8d, 104h; Size
0x18007e472  call    memset_0
0x18007e477  lea     rcx, [rsp+158h+LibFileName]; char *
0x18007e47c  call    GetRegisteredLocation
0x18007e481  test    eax, eax
0x18007e483  jz      short loc_18007E49E
0x18007e485  xor     r8d, r8d; dwFlags
0x18007e488  lea     rcx, [rsp+158h+LibFileName]; lpLibFileName
0x18007e48d  xor     edx, edx; hFile
0x18007e48f  call    cs:__imp_LoadLibraryExA
0x18007e495  mov     cs:qword_1800C0660, rax
0x18007e49c  jmp     short loc_18007E4A5
0x18007e49e  mov     rax, cs:qword_1800C0660
0x18007e4a5  test    rax, rax
0x18007e4a8  jnz     short loc_18007E4C8
0x18007e4aa  xor     r8d, r8d; dwFlags
0x18007e4ad  lea     rcx, aHhctrlOcx; "hhctrl.ocx"
0x18007e4b4  xor     edx, edx; hFile
0x18007e4b6  call    cs:__imp_LoadLibraryExA
0x18007e4bc  mov     cs:qword_1800C0660, rax
0x18007e4c3  test    rax, rax
0x18007e4c6  jz      short loc_18007E4F0
0x18007e4c8  mov     r10, cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x18007e4cf  test    r10, r10
0x18007e4d2  jnz     short loc_18007E4FE
0x18007e4d4  lea     edx, [r10+0Fh]; lpProcName
0x18007e4d8  mov     rcx, rax; hModule
0x18007e4db  call    cs:__imp_GetProcAddress
0x18007e4e1  mov     cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA, rax; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x18007e4e8  mov     r10, rax
0x18007e4eb  test    rax, rax
0x18007e4ee  jnz     short loc_18007E4FE
0x18007e4f0  mov     cs:dword_1800C0658, 1
0x18007e4fa  xor     eax, eax
0x18007e4fc  jmp     short loc_18007E519
0x18007e4fe  mov     r9, rdi
0x18007e501  lea     rdx, aMsdascChm; "MSDASC.CHM"
0x18007e508  mov     r8d, 0Fh
0x18007e50e  mov     rcx, rbx
0x18007e511  mov     rax, r10
0x18007e514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e519  mov     rcx, [rsp+158h+var_18]
0x18007e521  xor     rcx, rsp; StackCookie
0x18007e524  call    __security_check_cookie
0x18007e529  mov     rbx, [rsp+158h+arg_8]
0x18007e531  add     rsp, 150h
0x18007e538  pop     rdi
0x18007e539  retn
```
