# PaperSizeOption::IsWCOSPlatform(void)

- ea: `0x18001e99c`
- end: `0x18001ea44`
- name: `?IsWCOSPlatform@PaperSizeOption@@QEAAHXZ`
- size: `168`
- prototype: `__int64 __fastcall(PaperSizeOption *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180022094`

## callees

- `0x18000f970`
- `0x18001e99c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001e9da`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001e9da`
- `KERNEL32!CloseHandle` at `0x18001ea1d`
- `KERNEL32!CloseHandle` at `0x18001ea1d`
- `KERNEL32!GetSystemDirectoryW` at `0x18001e9bf`
- `KERNEL32!GetSystemDirectoryW` at `0x18001e9bf`
- `KERNEL32!CreateFileW` at `0x18001ea0e`
- `KERNEL32!CreateFileW` at `0x18001ea0e`

## pseudocode

```c
__int64 __fastcall PaperSizeOption::IsWCOSPlatform(PaperSizeOption *this)
{
  HANDLE FileW; // rax
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    return 0;
  if ( (unsigned int)_o_wcscat_s(Buffer, 261, L"\\PrintScanDiscoveryManagement.exe") )
    return 0;
  FileW = CreateFileW(Buffer, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return 0;
  CloseHandle(FileW);
  return 1;
}

```

## disassembly

```asm
0x18001e99c  sub     rsp, 268h
0x18001e9a3  mov     rax, cs:__security_cookie
0x18001e9aa  xor     rax, rsp
0x18001e9ad  mov     [rsp+268h+var_18], rax
0x18001e9b5  mov     edx, 104h; uSize
0x18001e9ba  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x18001e9bf  call    cs:__imp_GetSystemDirectoryW
0x18001e9c5  test    eax, eax
0x18001e9c7  jz      short loc_18001EA2A
0x18001e9c9  lea     r8, aPrintscandisco; "\\PrintScanDiscoveryManagement.exe"
0x18001e9d0  mov     edx, 105h
0x18001e9d5  lea     rcx, [rsp+268h+Buffer]
0x18001e9da  call    cs:__imp__o_wcscat_s
0x18001e9e0  test    eax, eax
0x18001e9e2  jnz     short loc_18001EA2A
0x18001e9e4  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x18001e9ed  lea     r8d, [rax+1]; dwShareMode
0x18001e9f1  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001e9f9  lea     rcx, [rsp+268h+Buffer]; lpFileName
0x18001e9fe  xor     r9d, r9d; lpSecurityAttributes
0x18001ea01  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x18001ea09  mov     edx, 80000000h; dwDesiredAccess
0x18001ea0e  call    cs:__imp_CreateFileW
0x18001ea14  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ea18  jz      short loc_18001EA2A
0x18001ea1a  mov     rcx, rax; hObject
0x18001ea1d  call    cs:__imp_CloseHandle
0x18001ea23  mov     eax, 1
0x18001ea28  jmp     short loc_18001EA2C
0x18001ea2a  xor     eax, eax
0x18001ea2c  mov     rcx, [rsp+268h+var_18]
0x18001ea34  xor     rcx, rsp; StackCookie
0x18001ea37  call    __security_check_cookie
0x18001ea3c  add     rsp, 268h
0x18001ea43  retn
```
