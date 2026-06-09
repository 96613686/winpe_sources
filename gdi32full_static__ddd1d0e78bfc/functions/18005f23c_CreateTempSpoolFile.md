# CreateTempSpoolFile

- ea: `0x18005f23c`
- end: `0x18005f326`
- name: `CreateTempSpoolFile`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18005ebd0`
- `0x18005f1ac`

## callees

- `0x18005f23c`
- `0x18007f800`
- `0x180080604`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18005f29e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18005f29e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f2da`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f2da`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005f2f7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005f2f7`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18005f273`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18005f273`

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
0x18005f23c  push    rbx
0x18005f23e  sub     rsp, 470h
0x18005f245  mov     rax, cs:__security_cookie
0x18005f24c  xor     rax, rsp
0x18005f24f  mov     [rsp+478h+var_18], rax
0x18005f257  xor     edx, edx; Val
0x18005f259  lea     rcx, [rsp+478h+PathName]; void *
0x18005f25e  mov     r8d, 208h; Size
0x18005f264  call    memset_0
0x18005f269  lea     rdx, [rsp+478h+PathName]
0x18005f26e  mov     ecx, 104h
0x18005f273  call    cs:__imp_GetTempPath2W
0x18005f27a  nop     dword ptr [rax+rax+00h]
0x18005f27f  test    eax, eax
0x18005f281  jz      loc_18005F308
0x18005f287  lea     r9, [rsp+478h+TempFileName]; lpTempFileName
0x18005f28f  xor     r8d, r8d; uUnique
0x18005f292  lea     rdx, PrefixString; "SPL"
0x18005f299  lea     rcx, [rsp+478h+PathName]; lpPathName
0x18005f29e  call    cs:__imp_GetTempFileNameW
0x18005f2a5  nop     dword ptr [rax+rax+00h]
0x18005f2aa  test    eax, eax
0x18005f2ac  jz      short loc_18005F308
0x18005f2ae  mov     [rsp+478h+hTemplateFile], 0; hTemplateFile
0x18005f2b7  lea     rcx, [rsp+478h+TempFileName]; lpFileName
0x18005f2bf  mov     [rsp+478h+dwFlagsAndAttributes], 0C002100h; dwFlagsAndAttributes
0x18005f2c7  xor     r9d, r9d; lpSecurityAttributes
0x18005f2ca  xor     r8d, r8d; dwShareMode
0x18005f2cd  mov     [rsp+478h+dwCreationDisposition], 2; dwCreationDisposition
0x18005f2d5  mov     edx, 0C0000000h; dwDesiredAccess
0x18005f2da  call    cs:__imp_CreateFileW
0x18005f2e1  nop     dword ptr [rax+rax+00h]
0x18005f2e6  mov     rbx, rax
0x18005f2e9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005f2ed  jnz     short loc_18005F303
0x18005f2ef  lea     rcx, [rsp+478h+TempFileName]; lpFileName
0x18005f2f7  call    cs:__imp_DeleteFileW
0x18005f2fe  nop     dword ptr [rax+rax+00h]
0x18005f303  mov     rax, rbx
0x18005f306  jmp     short loc_18005F30C
0x18005f308  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005f30c  mov     rcx, [rsp+478h+var_18]
0x18005f314  xor     rcx, rsp; StackCookie
0x18005f317  call    __security_check_cookie
0x18005f31c  add     rsp, 470h
0x18005f323  pop     rbx
0x18005f324  retn
```
