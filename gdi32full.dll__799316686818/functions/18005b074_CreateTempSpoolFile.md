# CreateTempSpoolFile

- ea: `0x18005b074`
- end: `0x18005b141`
- name: `CreateTempSpoolFile`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18005aa70`
- `0x18005afe8`

## callees

- `0x18005b074`
- `0x18007ac50`
- `0x18007ba24`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18005b0cc`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18005b0cc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005b102`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005b102`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005b119`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005b119`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18005b0ab`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18005b0ab`

## pseudocode

```c
__int64 CreateTempSpoolFile()
{
  HANDLE FileW; // rbx
  WCHAR PathName[264]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR TempFileName[264]; // [rsp+250h] [rbp-228h] BYREF

  memset_0(PathName, 0, 0x208u);
  if ( !(unsigned int)GetTempPath2W(260, PathName) || !GetTempFileNameW(PathName, L"SPL", 0, TempFileName) )
    return -1;
  FileW = CreateFileW(TempFileName, 0xC0000000, 0, 0, 2u, 0xC002100u, 0);
  if ( FileW == (HANDLE)-1LL )
    DeleteFileW(TempFileName);
  return (__int64)FileW;
}

```

## disassembly

```asm
0x18005b074  push    rbx
0x18005b076  sub     rsp, 470h
0x18005b07d  mov     rax, cs:__security_cookie
0x18005b084  xor     rax, rsp
0x18005b087  mov     [rsp+478h+var_18], rax
0x18005b08f  xor     edx, edx; Val
0x18005b091  lea     rcx, [rsp+478h+PathName]; void *
0x18005b096  mov     r8d, 208h; Size
0x18005b09c  call    memset_0
0x18005b0a1  lea     rdx, [rsp+478h+PathName]
0x18005b0a6  mov     ecx, 104h
0x18005b0ab  call    cs:__imp_GetTempPath2W
0x18005b0b1  test    eax, eax
0x18005b0b3  jz      short loc_18005B124
0x18005b0b5  lea     r9, [rsp+478h+TempFileName]; lpTempFileName
0x18005b0bd  xor     r8d, r8d; uUnique
0x18005b0c0  lea     rdx, PrefixString; "SPL"
0x18005b0c7  lea     rcx, [rsp+478h+PathName]; lpPathName
0x18005b0cc  call    cs:__imp_GetTempFileNameW
0x18005b0d2  test    eax, eax
0x18005b0d4  jz      short loc_18005B124
0x18005b0d6  mov     [rsp+478h+hTemplateFile], 0; hTemplateFile
0x18005b0df  lea     rcx, [rsp+478h+TempFileName]; lpFileName
0x18005b0e7  mov     [rsp+478h+dwFlagsAndAttributes], 0C002100h; dwFlagsAndAttributes
0x18005b0ef  xor     r9d, r9d; lpSecurityAttributes
0x18005b0f2  xor     r8d, r8d; dwShareMode
0x18005b0f5  mov     [rsp+478h+dwCreationDisposition], 2; dwCreationDisposition
0x18005b0fd  mov     edx, 0C0000000h; dwDesiredAccess
0x18005b102  call    cs:__imp_CreateFileW
0x18005b108  mov     rbx, rax
0x18005b10b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005b10f  jnz     short loc_18005B11F
0x18005b111  lea     rcx, [rsp+478h+TempFileName]; lpFileName
0x18005b119  call    cs:__imp_DeleteFileW
0x18005b11f  mov     rax, rbx
0x18005b122  jmp     short loc_18005B128
0x18005b124  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005b128  mov     rcx, [rsp+478h+var_18]
0x18005b130  xor     rcx, rsp; StackCookie
0x18005b133  call    __security_check_cookie
0x18005b138  add     rsp, 470h
0x18005b13f  pop     rbx
0x18005b140  retn
```
