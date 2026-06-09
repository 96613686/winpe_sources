# LayerHasHiveIntegratedLayout(ushort const *)

- ea: `0x180027c64`
- end: `0x180027e83`
- name: `?LayerHasHiveIntegratedLayout@@YA_NPEBG@Z`
- size: `543`
- prototype: `bool __fastcall(PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027e8c`

## callees

- `0x180002690`
- `0x180003ba9`
- `0x180006d1c`
- `0x180008f44`
- `0x180008fac`
- `0x18000a578`
- `0x180012818`
- `0x1800136f8`
- `0x180027c64`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027cd9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027cd9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180027d62`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180027d62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027d21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027dff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027d21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027dff`

## string_xrefs

- `0x180027e4a`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x180027e5c`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x180027e71`: `onecore\vm\compute\shared\storage\layerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall LayerHasHiveIntegratedLayout(PCWSTR pszPathIn)
{
  const WCHAR *v1; // rcx
  char *FileW; // rbx
  const char *v3; // r9
  const char *v5; // r9
  void **v6; // rdx
  size_t v7; // r8
  void **v8; // rcx
  bool v9; // di
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  void *Buf1[2]; // [rsp+40h] [rbp-C0h] BYREF
  size_t Size[2]; // [rsp+50h] [rbp-B0h]
  char *v13; // [rsp+60h] [rbp-A0h]
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Buffer[256]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  Vml::CombineFilePath(lpFileName, pszPathIn, L"layout");
  v1 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v1 = lpFileName[0];
  FileW = (char *)CreateFileW(v1, 0x80000000, 1u, 0, 3u, 0, 0);
  v13 = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, Buffer, 0x100u, &NumberOfBytesRead, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        v5);
    *(_OWORD *)Buf1 = 0;
    *(_OWORD *)Size = 0;
    std::string::_Construct<1,char const *>(Buf1, Buffer, NumberOfBytesRead);
    v6 = &Buf2;
    if ( (unsigned __int64)qword_18005FFD8 > 0xF )
      v6 = (void **)Buf2;
    v7 = Size[0];
    v8 = Buf1;
    if ( Size[1] > 0xF )
      v8 = (void **)Buf1[0];
    v9 = Size[0] != qword_18005FFD0 || Size[0] && memcmp_0(v8, v6, Size[0]);
    std::string::~string(Buf1, v6, v7);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        (const char *)0xC0370112LL,
        dwCreationDisposition);
    CloseHandle(FileW);
    std::wstring::~wstring((char **)lpFileName);
    return 1;
  }
  else
  {
    if ( GetLastError() != 2 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        v3);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    std::wstring::~wstring((char **)lpFileName);
    return 0;
  }
}

```

## disassembly

```asm
0x180027c64  mov     [rsp-8+arg_8], rbx
0x180027c69  mov     [rsp-8+arg_10], rdi
0x180027c6e  push    rbp
0x180027c6f  lea     rbp, [rsp-0A0h]
0x180027c77  sub     rsp, 1A0h
0x180027c7e  mov     rax, cs:__security_cookie
0x180027c85  xor     rax, rsp
0x180027c88  mov     [rbp+0A0h+var_10], rax
0x180027c8f  lea     r8, aLayout; "layout"
0x180027c96  mov     rdx, rcx; pszPathIn
0x180027c99  lea     rcx, [rsp+1A0h+lpFileName]; Src
0x180027c9e  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180027ca3  nop
0x180027ca4  lea     rcx, [rsp+1A0h+lpFileName]
0x180027ca9  cmp     [rbp+0A0h+var_118], 7
0x180027cae  cmova   rcx, [rsp+1A0h+lpFileName]; lpFileName
0x180027cb4  mov     [rsp+1A0h+hTemplateFile], 0; hTemplateFile
0x180027cbd  mov     [rsp+1A0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180027cc5  mov     [rsp+1A0h+dwCreationDisposition], 3; dwCreationDisposition
0x180027ccd  xor     r9d, r9d; lpSecurityAttributes
0x180027cd0  mov     edx, 80000000h; dwDesiredAccess
0x180027cd5  lea     r8d, [r9+1]; dwShareMode
0x180027cd9  call    cs:__imp_CreateFileW
0x180027ce0  nop     dword ptr [rax+rax+00h]
0x180027ce5  mov     rbx, rax
0x180027ce8  mov     [rsp+1A0h+var_140], rax
0x180027ced  inc     rax
0x180027cf0  test    rax, 0FFFFFFFFFFFFFFFEh
0x180027cf6  jnz     short loc_180027D3F
0x180027cf8  mov     rdi, [rbp+0A8h]
0x180027cff  call    cs:__imp_GetLastError
0x180027d06  nop     dword ptr [rax+rax+00h]
0x180027d0b  cmp     eax, 2
0x180027d0e  jnz     loc_180027E5C
0x180027d14  lea     rax, [rbx-1]
0x180027d18  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180027d1c  ja      short loc_180027D2E
0x180027d1e  mov     rcx, rbx; hObject
0x180027d21  call    cs:__imp_CloseHandle
0x180027d28  nop     dword ptr [rax+rax+00h]
0x180027d2d  nop
0x180027d2e  lea     rcx, [rsp+1A0h+lpFileName]
0x180027d33  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027d38  xor     al, al
0x180027d3a  jmp     loc_180027E18
0x180027d3f  mov     [rsp+1A0h+NumberOfBytesRead], 0
0x180027d47  mov     qword ptr [rsp+1A0h+dwCreationDisposition], 0; unsigned int
0x180027d50  lea     r9, [rsp+1A0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180027d55  mov     r8d, 100h; nNumberOfBytesToRead
0x180027d5b  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180027d5f  mov     rcx, rbx; hFile
0x180027d62  call    cs:__imp_ReadFile
0x180027d69  nop     dword ptr [rax+rax+00h]
0x180027d6e  mov     rcx, [rbp+0A8h]; this
0x180027d75  test    eax, eax
0x180027d77  jz      loc_180027E71
0x180027d7d  xorps   xmm0, xmm0
0x180027d80  movups  xmmword ptr [rsp+1A0h+Buf1], xmm0
0x180027d85  xorps   xmm1, xmm1
0x180027d88  movdqu  xmmword ptr [rsp+1A0h+Size], xmm1
0x180027d8e  mov     r8d, [rsp+1A0h+NumberOfBytesRead]
0x180027d93  lea     rdx, [rbp+0A0h+Buffer]
0x180027d97  lea     rcx, [rsp+1A0h+Buf1]
0x180027d9c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180027da1  lea     rdx, Buf2
0x180027da8  cmp     cs:qword_18005FFD8, 0Fh
0x180027db0  cmova   rdx, cs:Buf2; Buf2
0x180027db8  mov     r8, [rsp+1A0h+Size]; Size
0x180027dbd  lea     rcx, [rsp+1A0h+Buf1]
0x180027dc2  cmp     [rsp+1A0h+Size+8], 0Fh
0x180027dc8  cmova   rcx, [rsp+1A0h+Buf1]; Buf1
0x180027dce  cmp     r8, cs:qword_18005FFD0
0x180027dd5  jnz     short loc_180027DEA
0x180027dd7  test    r8, r8
0x180027dda  jz      short loc_180027DE5
0x180027ddc  call    memcmp_0
0x180027de1  test    eax, eax
0x180027de3  jnz     short loc_180027DEA
0x180027de5  xor     dil, dil
0x180027de8  jmp     short loc_180027DED
0x180027dea  mov     dil, 1
0x180027ded  lea     rcx, [rsp+1A0h+Buf1]
0x180027df2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180027df7  test    dil, dil
0x180027dfa  jnz     short loc_180027E3D
0x180027dfc  mov     rcx, rbx; hObject
0x180027dff  call    cs:__imp_CloseHandle
0x180027e06  nop     dword ptr [rax+rax+00h]
0x180027e0b  nop
0x180027e0c  lea     rcx, [rsp+1A0h+lpFileName]
0x180027e11  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027e16  mov     al, 1
0x180027e18  mov     rcx, [rbp+0A0h+var_10]
0x180027e1f  xor     rcx, rsp; StackCookie
0x180027e22  call    __security_check_cookie
0x180027e27  lea     r11, [rsp+1A0h+var_s0]
0x180027e2f  mov     rbx, [r11+18h]
0x180027e33  mov     rdi, [r11+20h]
0x180027e37  mov     rsp, r11
0x180027e3a  pop     rbp
0x180027e3b  retn
0x180027e3d  mov     rcx, [rbp+0A8h]; this
0x180027e44  mov     r9d, 0C0370112h; char *
0x180027e4a  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\shared\\storage\\"...
0x180027e51  mov     edx, 96h; void *
0x180027e56  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180027e5c  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\shared\\storage\\"...
0x180027e63  mov     edx, 8Ch; void *
0x180027e68  mov     rcx, rdi; this
0x180027e6b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180027e71  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\shared\\storage\\"...
0x180027e78  mov     edx, 92h; void *
0x180027e7d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
