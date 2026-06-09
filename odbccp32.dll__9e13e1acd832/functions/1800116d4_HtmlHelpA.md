# HtmlHelpA

- ea: `0x1800116d4`
- end: `0x1800117e2`
- name: `HtmlHelpA`
- size: `270`
- prototype: `HWND __stdcall(HWND hwndCaller, LPCSTR pszFile, UINT uCommand, DWORD_PTR dwData)`
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005c00`
- `0x18000a3b0`
- `0x18000aeb0`
- `0x18000af80`
- `0x18000b9c0`
- `0x18000c440`
- `0x18000dc70`

## callees

- `0x1800115ac`
- `0x1800116d4`
- `0x180014aae`
- `0x180014ae0`
- `0x180015010`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x180011737`
- `KERNEL32!LoadLibraryExA` at `0x18001175e`
- `KERNEL32!LoadLibraryExA` at `0x180011737`
- `KERNEL32!LoadLibraryExA` at `0x18001175e`
- `KERNEL32!GetProcAddress` at `0x180011783`
- `KERNEL32!GetProcAddress` at `0x180011783`

## pseudocode

```c
HWND __stdcall HtmlHelpA(HWND hwndCaller, LPCSTR pszFile, UINT uCommand, DWORD_PTR dwData)
{
  HMODULE Library; // rax
  HWND (*v7)(HWND, const char *, unsigned int, unsigned __int64); // r10
  CHAR LibFileName[272]; // [rsp+30h] [rbp-128h] BYREF

  Library = qword_18001CE70;
  if ( qword_18001CE70
    || dword_18001CE78
    || ((memset_0(LibFileName, 0, 0x104u), !(unsigned int)GetRegisteredLocation(LibFileName))
      ? (Library = qword_18001CE70)
      : (Library = LoadLibraryExA(LibFileName, 0, 0), qword_18001CE70 = Library),
        Library || (Library = LoadLibraryExA("hhctrl.ocx", 0, 0), (qword_18001CE70 = Library) != 0)) )
  {
    v7 = pHtmlHelpA;
    if ( pHtmlHelpA )
      return (HWND)((__int64 (__fastcall *)(HWND, const char *, __int64, DWORD_PTR))v7)(
                     hwndCaller,
                     "ODBCINST.CHM",
                     15,
                     dwData);
    pHtmlHelpA = (HWND (*)(HWND, const char *, unsigned int, unsigned __int64))GetProcAddress(Library, (LPCSTR)0xE);
    v7 = pHtmlHelpA;
    if ( pHtmlHelpA )
      return (HWND)((__int64 (__fastcall *)(HWND, const char *, __int64, DWORD_PTR))v7)(
                     hwndCaller,
                     "ODBCINST.CHM",
                     15,
                     dwData);
  }
  dword_18001CE78 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800116d4  mov     [rsp+arg_8], rbx
0x1800116d9  push    rdi
0x1800116da  sub     rsp, 150h
0x1800116e1  mov     rax, cs:__security_cookie
0x1800116e8  xor     rax, rsp
0x1800116eb  mov     [rsp+158h+var_18], rax
0x1800116f3  mov     rax, cs:qword_18001CE70
0x1800116fa  mov     rdi, r9
0x1800116fd  mov     rbx, rcx
0x180011700  test    rax, rax
0x180011703  jnz     short loc_180011770
0x180011705  cmp     cs:dword_18001CE78, eax
0x18001170b  jnz     short loc_180011770
0x18001170d  xor     edx, edx; Val
0x18001170f  lea     rcx, [rsp+158h+LibFileName]; void *
0x180011714  mov     r8d, 104h; Size
0x18001171a  call    memset_0
0x18001171f  lea     rcx, [rsp+158h+LibFileName]; lpDst
0x180011724  call    GetRegisteredLocation
0x180011729  test    eax, eax
0x18001172b  jz      short loc_180011746
0x18001172d  xor     r8d, r8d; dwFlags
0x180011730  lea     rcx, [rsp+158h+LibFileName]; lpLibFileName
0x180011735  xor     edx, edx; hFile
0x180011737  call    cs:__imp_LoadLibraryExA
0x18001173d  mov     cs:qword_18001CE70, rax
0x180011744  jmp     short loc_18001174D
0x180011746  mov     rax, cs:qword_18001CE70
0x18001174d  test    rax, rax
0x180011750  jnz     short loc_180011770
0x180011752  xor     r8d, r8d; dwFlags
0x180011755  lea     rcx, aHhctrlOcx; "hhctrl.ocx"
0x18001175c  xor     edx, edx; hFile
0x18001175e  call    cs:__imp_LoadLibraryExA
0x180011764  mov     cs:qword_18001CE70, rax
0x18001176b  test    rax, rax
0x18001176e  jz      short loc_180011798
0x180011770  mov     r10, cs:?pHtmlHelpA@@3P6APEAUHWND__@@PEAU1@PEBDI_K@ZEA; HWND__ * (*pHtmlHelpA)(HWND__ *,char const *,uint,unsigned __int64)
0x180011777  test    r10, r10
0x18001177a  jnz     short loc_1800117A6
0x18001177c  lea     edx, [r10+0Eh]; lpProcName
0x180011780  mov     rcx, rax; hModule
0x180011783  call    cs:__imp_GetProcAddress
0x180011789  mov     cs:?pHtmlHelpA@@3P6APEAUHWND__@@PEAU1@PEBDI_K@ZEA, rax; HWND__ * (*pHtmlHelpA)(HWND__ *,char const *,uint,unsigned __int64)
0x180011790  mov     r10, rax
0x180011793  test    rax, rax
0x180011796  jnz     short loc_1800117A6
0x180011798  mov     cs:dword_18001CE78, 1
0x1800117a2  xor     eax, eax
0x1800117a4  jmp     short loc_1800117C1
0x1800117a6  mov     r9, rdi
0x1800117a9  lea     rdx, aOdbcinstChm; "ODBCINST.CHM"
0x1800117b0  mov     r8d, 0Fh
0x1800117b6  mov     rcx, rbx
0x1800117b9  mov     rax, r10
0x1800117bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117c1  mov     rcx, [rsp+158h+var_18]
0x1800117c9  xor     rcx, rsp; StackCookie
0x1800117cc  call    __security_check_cookie
0x1800117d1  mov     rbx, [rsp+158h+arg_8]
0x1800117d9  add     rsp, 150h
0x1800117e0  pop     rdi
0x1800117e1  retn
```
