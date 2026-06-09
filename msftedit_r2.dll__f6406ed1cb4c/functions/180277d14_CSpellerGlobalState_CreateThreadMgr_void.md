# CSpellerGlobalState::CreateThreadMgr(void)

- ea: `0x180277d14`
- end: `0x180277e5d`
- name: `?CreateThreadMgr@CSpellerGlobalState@@QEAAJXZ`
- size: `329`
- prototype: `__int64 __fastcall(CSpellerGlobalState *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x18027c494`

## callees

- `0x18013ce80`
- `0x180277d14`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180277dac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180277dac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180277d83`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180277d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180277e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180277e0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180277d41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180277d41`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180277d6a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180277d6a`

## string_xrefs

- `0x180277da2`: `TF_GetThreadMgr`
- `0x180277d5a`: `msctf.dll`

## pseudocode

```c
__int64 __fastcall CSpellerGlobalState::CreateThreadMgr(CSpellerGlobalState *this)
{
  signed int v2; // ebx
  HMODULE Library; // rax
  _QWORD *v4; // rdi
  FARPROC ProcAddress; // rax
  _QWORD *v6; // rsi
  signed int LastError; // eax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-248h] BYREF

  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 <= 0x102 )
  {
    v2 = 0;
    PathCchAppend(Buffer, 0x104u, L"msctf.dll");
    Library = LoadLibraryExW(Buffer, 0, 0x800u);
    v4 = (_QWORD *)((char *)this + 136);
    *((_QWORD *)this + 17) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "TF_GetThreadMgr");
      if ( ProcAddress )
      {
        v6 = (_QWORD *)((char *)this + 128);
        ((void (__fastcall *)(char *))ProcAddress)((char *)this + 128);
        if ( !*((_QWORD *)this + 16) )
          return (unsigned int)-2147467259;
        v2 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 16) + 24LL))(
               *((_QWORD *)this + 16),
               (char *)this + 144);
        if ( v2 < 0 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 16LL))(*v6);
          *v6 = 0;
          return (unsigned int)v2;
        }
      }
    }
    goto LABEL_11;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  v4 = (_QWORD *)((char *)this + 136);
  if ( v2 >= 0 )
  {
LABEL_11:
    if ( !*v4 )
      return (unsigned int)-2147467263;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180277d14  push    rbx
0x180277d16  push    rbp
0x180277d17  push    rsi
0x180277d18  push    rdi
0x180277d19  sub     rsp, 248h
0x180277d20  mov     rax, cs:__security_cookie
0x180277d27  xor     rax, rsp
0x180277d2a  mov     [rsp+268h+var_38], rax
0x180277d32  mov     rbp, rcx
0x180277d35  mov     edi, 104h
0x180277d3a  mov     edx, edi; uSize
0x180277d3c  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x180277d41  call    cs:__imp_GetSystemDirectoryW
0x180277d48  nop     dword ptr [rax+rax+00h]
0x180277d4d  dec     eax
0x180277d4f  cmp     eax, 102h
0x180277d54  ja      loc_180277E0C
0x180277d5a  lea     r8, pszMore; "msctf.dll"
0x180277d61  mov     edx, edi; cchPath
0x180277d63  lea     rcx, [rsp+268h+Buffer]; pszPath
0x180277d68  xor     ebx, ebx
0x180277d6a  call    cs:__imp_PathCchAppend
0x180277d71  nop     dword ptr [rax+rax+00h]
0x180277d76  xor     edx, edx; hFile
0x180277d78  lea     rcx, [rsp+268h+Buffer]; lpLibFileName
0x180277d7d  mov     r8d, 800h; dwFlags
0x180277d83  call    cs:__imp_LoadLibraryExW
0x180277d8a  nop     dword ptr [rax+rax+00h]
0x180277d8f  lea     rdi, [rbp+88h]
0x180277d96  mov     [rdi], rax
0x180277d99  test    rax, rax
0x180277d9c  jz      loc_180277E32
0x180277da2  lea     rdx, aTfGetthreadmgr; "TF_GetThreadMgr"
0x180277da9  mov     rcx, rax; hModule
0x180277dac  call    cs:__imp_GetProcAddress
0x180277db3  nop     dword ptr [rax+rax+00h]
0x180277db8  test    rax, rax
0x180277dbb  jz      short loc_180277E32
0x180277dbd  lea     rsi, [rbp+80h]
0x180277dc4  mov     rcx, rsi
0x180277dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180277dcc  mov     rcx, [rsi]
0x180277dcf  test    rcx, rcx
0x180277dd2  jz      short loc_180277E05
0x180277dd4  mov     rax, [rcx]
0x180277dd7  lea     rdx, [rbp+90h]
0x180277dde  mov     rax, [rax+18h]
0x180277de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180277de7  mov     ebx, eax
0x180277de9  test    eax, eax
0x180277deb  jns     short loc_180277E32
0x180277ded  mov     rcx, [rsi]
0x180277df0  mov     rdx, [rcx]
0x180277df3  mov     rax, [rdx+10h]
0x180277df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180277dfc  mov     qword ptr [rsi], 0
0x180277e03  jmp     short loc_180277E3E
0x180277e05  mov     ebx, 80004005h
0x180277e0a  jmp     short loc_180277E3E
0x180277e0c  call    cs:__imp_GetLastError
0x180277e13  nop     dword ptr [rax+rax+00h]
0x180277e18  mov     ebx, eax
0x180277e1a  test    eax, eax
0x180277e1c  jle     short loc_180277E27
0x180277e1e  movzx   ebx, ax
0x180277e21  or      ebx, 80070000h
0x180277e27  lea     rdi, [rbp+88h]
0x180277e2e  test    ebx, ebx
0x180277e30  js      short loc_180277E3E
0x180277e32  cmp     qword ptr [rdi], 0
0x180277e36  mov     eax, 80004001h
0x180277e3b  cmovz   ebx, eax
0x180277e3e  mov     eax, ebx
0x180277e40  mov     rcx, [rsp+268h+var_38]
0x180277e48  xor     rcx, rsp; StackCookie
0x180277e4b  call    __security_check_cookie
0x180277e50  add     rsp, 248h
0x180277e57  pop     rdi
0x180277e58  pop     rsi
0x180277e59  pop     rbp
0x180277e5a  pop     rbx
0x180277e5b  retn
```
