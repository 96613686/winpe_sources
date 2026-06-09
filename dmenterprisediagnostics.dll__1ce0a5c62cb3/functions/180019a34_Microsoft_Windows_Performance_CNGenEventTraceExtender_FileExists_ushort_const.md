# Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)

- ea: `0x180019a34`
- end: `0x180019a7c`
- name: `?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z`
- size: `72`
- prototype: `bool(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001964c`

## callees

- `0x180019a34`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019a6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019a6b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019a5c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019a5c`

## pseudocode

```c
char __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        const unsigned __int16 *a2)
{
  HANDLE FileW; // rax

  FileW = CreateFileW(a2, 0, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
    return 0;
  CloseHandle(FileW);
  return 1;
}

```

## disassembly

```asm
0x180019a34  sub     rsp, 48h
0x180019a38  mov     rcx, rdx; lpFileName
0x180019a3b  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180019a44  mov     r8d, 3; dwShareMode
0x180019a4a  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180019a52  xor     edx, edx; dwDesiredAccess
0x180019a54  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180019a59  xor     r9d, r9d; lpSecurityAttributes
0x180019a5c  call    cs:__imp_CreateFileW
0x180019a62  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019a66  jz      short loc_180019A75
0x180019a68  mov     rcx, rax; hObject
0x180019a6b  call    cs:__imp_CloseHandle
0x180019a71  mov     al, 1
0x180019a73  jmp     short loc_180019A77
0x180019a75  xor     al, al
0x180019a77  add     rsp, 48h
0x180019a7b  retn
```
