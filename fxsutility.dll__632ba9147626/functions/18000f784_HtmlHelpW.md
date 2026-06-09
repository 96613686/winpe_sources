# HtmlHelpW

- ea: `0x18000f784`
- end: `0x18000f88f`
- name: `HtmlHelpW`
- size: `267`
- prototype: `HWND __stdcall(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ea20`

## callees

- `0x18000f65c`
- `0x18000f784`
- `0x180015cbe`
- `0x180015cf0`
- `0x180017010`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x18000f7eb`
- `KERNEL32!LoadLibraryExA` at `0x18000f812`
- `KERNEL32!LoadLibraryExA` at `0x18000f7eb`
- `KERNEL32!LoadLibraryExA` at `0x18000f812`
- `KERNEL32!GetProcAddress` at `0x18000f837`
- `KERNEL32!GetProcAddress` at `0x18000f837`

## pseudocode

```c
HWND __stdcall HtmlHelpW(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)
{
  HMODULE Library; // rax
  unsigned __int16 *v6; // rdi
  HWND (*v7)(HWND, const unsigned __int16 *, unsigned int, unsigned __int64); // r10
  CHAR LibFileName[272]; // [rsp+30h] [rbp-128h] BYREF

  Library = hModule;
  v6 = g_tszHelpTopic;
  if ( hModule
    || dword_18001F278
    || ((memset_0(LibFileName, 0, 0x104u), !(unsigned int)GetRegisteredLocation(LibFileName))
      ? (Library = hModule)
      : (Library = LoadLibraryExA(LibFileName, 0, 0), hModule = Library),
        Library || (Library = LoadLibraryExA("hhctrl.ocx", 0, 0), (hModule = Library) != 0)) )
  {
    v7 = pHtmlHelpW;
    if ( pHtmlHelpW )
      return (HWND)((__int64 (__fastcall *)(HWND, unsigned __int16 *, _QWORD, _QWORD))v7)(hwndCaller, v6, 0, 0);
    pHtmlHelpW = (HWND (*)(HWND, const unsigned __int16 *, unsigned int, unsigned __int64))GetProcAddress(
                                                                                             Library,
                                                                                             (LPCSTR)0xF);
    v7 = pHtmlHelpW;
    if ( pHtmlHelpW )
      return (HWND)((__int64 (__fastcall *)(HWND, unsigned __int16 *, _QWORD, _QWORD))v7)(hwndCaller, v6, 0, 0);
  }
  dword_18001F278 = 1;
  return 0;
}

```

## disassembly

```asm
0x18000f784  mov     [rsp+arg_8], rbx
0x18000f789  push    rdi
0x18000f78a  sub     rsp, 150h
0x18000f791  mov     rax, cs:__security_cookie
0x18000f798  xor     rax, rsp
0x18000f79b  mov     [rsp+158h+var_18], rax
0x18000f7a3  mov     rax, cs:hModule
0x18000f7aa  mov     rbx, rcx
0x18000f7ad  mov     rdi, cs:?g_tszHelpTopic@@3PEAGEA; ushort * g_tszHelpTopic
0x18000f7b4  test    rax, rax
0x18000f7b7  jnz     short loc_18000F824
0x18000f7b9  cmp     cs:dword_18001F278, eax
0x18000f7bf  jnz     short loc_18000F824
0x18000f7c1  xor     edx, edx; Val
0x18000f7c3  lea     rcx, [rsp+158h+LibFileName]; void *
0x18000f7c8  mov     r8d, 104h; Size
0x18000f7ce  call    memset_0
0x18000f7d3  lea     rcx, [rsp+158h+LibFileName]; lpDst
0x18000f7d8  call    GetRegisteredLocation
0x18000f7dd  test    eax, eax
0x18000f7df  jz      short loc_18000F7FA
0x18000f7e1  xor     r8d, r8d; dwFlags
0x18000f7e4  lea     rcx, [rsp+158h+LibFileName]; lpLibFileName
0x18000f7e9  xor     edx, edx; hFile
0x18000f7eb  call    cs:__imp_LoadLibraryExA
0x18000f7f1  mov     cs:hModule, rax
0x18000f7f8  jmp     short loc_18000F801
0x18000f7fa  mov     rax, cs:hModule
0x18000f801  test    rax, rax
0x18000f804  jnz     short loc_18000F824
0x18000f806  xor     r8d, r8d; dwFlags
0x18000f809  lea     rcx, aHhctrlOcx; "hhctrl.ocx"
0x18000f810  xor     edx, edx; hFile
0x18000f812  call    cs:__imp_LoadLibraryExA
0x18000f818  mov     cs:hModule, rax
0x18000f81f  test    rax, rax
0x18000f822  jz      short loc_18000F84C
0x18000f824  mov     r10, cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x18000f82b  test    r10, r10
0x18000f82e  jnz     short loc_18000F85A
0x18000f830  lea     edx, [r10+0Fh]; lpProcName
0x18000f834  mov     rcx, rax; hModule
0x18000f837  call    cs:__imp_GetProcAddress
0x18000f83d  mov     cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA, rax; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x18000f844  mov     r10, rax
0x18000f847  test    rax, rax
0x18000f84a  jnz     short loc_18000F85A
0x18000f84c  mov     cs:dword_18001F278, 1
0x18000f856  xor     eax, eax
0x18000f858  jmp     short loc_18000F86E
0x18000f85a  xor     r9d, r9d
0x18000f85d  xor     r8d, r8d
0x18000f860  mov     rdx, rdi
0x18000f863  mov     rcx, rbx
0x18000f866  mov     rax, r10
0x18000f869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f86e  mov     rcx, [rsp+158h+var_18]
0x18000f876  xor     rcx, rsp; StackCookie
0x18000f879  call    __security_check_cookie
0x18000f87e  mov     rbx, [rsp+158h+arg_8]
0x18000f886  add     rsp, 150h
0x18000f88d  pop     rdi
0x18000f88e  retn
```
