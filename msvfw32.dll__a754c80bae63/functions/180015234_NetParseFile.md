# NetParseFile

- ea: `0x180015234`
- end: `0x18001539d`
- name: `NetParseFile`
- size: `361`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000fe2c`

## callees

- `0x1800014b0`
- `0x180002198`
- `0x180002280`
- `0x180015234`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001531f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001534b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001531f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001534b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800152fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800152fe`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800152e8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800152e8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800152aa`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800152aa`

## string_xrefs

- `0x180015288`: `MPR.DLL`

## pseudocode

```c
__int64 __fastcall NetParseFile(STRSAFE_LPWSTR pszDest)
{
  HMODULE LibraryW; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rax
  int v6; // [rsp+20h] [rbp-E0h] BYREF
  LPWSTR FilePart; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR v8; // [rsp+30h] [rbp-D0h] BYREF
  int v9; // [rsp+32h] [rbp-CEh]
  CHAR ProcName[24]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR LibFileName[8]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDesta; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v13; // [rsp+62h] [rbp-9Eh]
  WCHAR Buffer[264]; // [rsp+160h] [rbp+60h] BYREF

  v6 = 128;
  strcpy(ProcName, "WNetGetConnectionW");
  FilePart = 0;
  Buffer[0] = 0;
  wcscpy(LibFileName, L"MPR.DLL");
  if ( !GetFullPathNameW(pszDest, 0x104u, Buffer, &FilePart) )
    return 0;
  StringCchCopyW(pszDest, 0x104u, Buffer);
  if ( pszDest[1] == 58 )
  {
    v8 = *pszDest;
    v9 = 58;
    LibraryW = LoadLibraryW(LibFileName);
    v3 = LibraryW;
    if ( !LibraryW )
      return 0;
    ProcAddress = GetProcAddress(LibraryW, ProcName);
    if ( ((unsigned int (__fastcall *)(WCHAR *, wchar_t *, int *))ProcAddress)(&v8, &pszDesta, &v6) )
    {
      FreeLibrary(v3);
      return 0;
    }
    FreeLibrary(v3);
    if ( (pszDesta == 47 || pszDesta == 92) && (v13 == 47 || v13 == 92) )
    {
      StringCchCatW(&pszDesta, 0x80u, pszDest + 2);
      StringCchCopyW(pszDest, 0x104u, &pszDesta);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180015234  mov     [rsp-8+arg_8], rbx
0x180015239  mov     [rsp-8+arg_10], rdi
0x18001523e  push    rbp
0x18001523f  lea     rbp, [rsp-280h]
0x180015247  sub     rsp, 380h
0x18001524e  mov     rax, cs:__security_cookie
0x180015255  xor     rax, rsp
0x180015258  mov     [rbp+280h+var_10], rax
0x18001525f  movups  xmm0, xmmword ptr cs:aWnetgetconnect; "WNetGetConnectionW"
0x180015266  mov     eax, dword ptr cs:aWnetgetconnect+0Fh; "onW"
0x18001526c  lea     r9, [rsp+380h+FilePart]; lpFilePart
0x180015271  lea     r8, [rbp+280h+Buffer]; lpBuffer
0x180015275  mov     [rsp+380h+var_360], 80h
0x18001527d  movups  xmmword ptr [rsp+380h+ProcName], xmm0
0x180015282  mov     dword ptr [rsp+380h+ProcName+0Fh], eax
0x180015286  xor     eax, eax
0x180015288  movups  xmm0, xmmword ptr cs:aMprDll; "MPR.DLL"
0x18001528f  mov     edx, 104h; nBufferLength
0x180015294  mov     [rsp+380h+FilePart], 0
0x18001529d  mov     rbx, rcx
0x1800152a0  mov     [rbp+280h+Buffer], ax
0x1800152a4  movdqu  xmmword ptr [rsp+380h+LibFileName], xmm0
0x1800152aa  call    cs:__imp_GetFullPathNameW
0x1800152b0  test    eax, eax
0x1800152b2  jz      short loc_180015325
0x1800152b4  lea     r8, [rbp+280h+Buffer]; pszSrc
0x1800152b8  mov     edx, 104h; cchDest
0x1800152bd  mov     rcx, rbx; pszDest
0x1800152c0  call    StringCchCopyW
0x1800152c5  mov     r11d, 3Ah ; ':'
0x1800152cb  cmp     [rbx+2], r11w
0x1800152d0  jnz     loc_180015396
0x1800152d6  movzx   eax, word ptr [rbx]
0x1800152d9  lea     rcx, [rsp+380h+LibFileName]; lpLibFileName
0x1800152de  mov     [rsp+380h+var_350], ax
0x1800152e3  mov     [rsp+380h+var_34E], r11d
0x1800152e8  call    cs:__imp_LoadLibraryW
0x1800152ee  mov     rdi, rax
0x1800152f1  test    rax, rax
0x1800152f4  jz      short loc_180015325
0x1800152f6  lea     rdx, [rsp+380h+ProcName]; lpProcName
0x1800152fb  mov     rcx, rax; hModule
0x1800152fe  call    cs:__imp_GetProcAddress
0x180015304  lea     r8, [rsp+380h+var_360]
0x180015309  lea     rdx, [rsp+380h+pszDest]
0x18001530e  lea     rcx, [rsp+380h+var_350]
0x180015313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015318  mov     rcx, rdi; hLibModule
0x18001531b  test    eax, eax
0x18001531d  jz      short loc_18001534B
0x18001531f  call    cs:__imp_FreeLibrary
0x180015325  xor     eax, eax
0x180015327  mov     rcx, [rbp+280h+var_10]
0x18001532e  xor     rcx, rsp; StackCookie
0x180015331  call    __security_check_cookie
0x180015336  lea     r11, [rsp+380h+var_s0]
0x18001533e  mov     rbx, [r11+18h]
0x180015342  mov     rdi, [r11+20h]
0x180015346  mov     rsp, r11
0x180015349  pop     rbp
0x18001534a  retn
0x18001534b  call    cs:__imp_FreeLibrary
0x180015351  cmp     [rsp+380h+pszDest], 2Fh ; '/'
0x180015357  jz      short loc_180015361
0x180015359  cmp     [rsp+380h+pszDest], 5Ch ; '\'
0x18001535f  jnz     short loc_180015396
0x180015361  cmp     [rsp+380h+var_31E], 2Fh ; '/'
0x180015367  jz      short loc_180015371
0x180015369  cmp     [rsp+380h+var_31E], 5Ch ; '\'
0x18001536f  jnz     short loc_180015396
0x180015371  lea     r8, [rbx+4]; pszSrc
0x180015375  mov     edx, 80h; cchDest
0x18001537a  lea     rcx, [rsp+380h+pszDest]; pszDest
0x18001537f  call    StringCchCatW
0x180015384  lea     r8, [rsp+380h+pszDest]; pszSrc
0x180015389  mov     edx, 104h; cchDest
0x18001538e  mov     rcx, rbx; pszDest
0x180015391  call    StringCchCopyW
0x180015396  mov     eax, 1
0x18001539b  jmp     short loc_180015327
```
