# CFileStream::MakeFileStub(void)

- ea: `0x18003995c`
- end: `0x1800399bc`
- name: `?MakeFileStub@CFileStream@@AEAAJXZ`
- size: `96`
- prototype: `__int64 __fastcall(CFileStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001e718`

## callees

- `0x180026bc4`
- `0x18003995c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003998e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003998e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003997a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800399a9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003997a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800399a9`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180039984`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180039984`

## pseudocode

```c
__int64 __fastcall CFileStream::MakeFileStub(HANDLE *this)
{
  unsigned int v2; // ebx
  DWORD LastError; // eax

  v2 = 0;
  SetFilePointer(this[8], 512, 0, 0);
  if ( !SetEndOfFile(this[8]) )
  {
    LastError = GetLastError();
    v2 = Win32ErrorToScode(LastError);
  }
  SetFilePointer(this[8], 0, 0, 0);
  return v2;
}

```

## disassembly

```asm
0x18003995c  mov     [rsp+arg_0], rbx
0x180039961  push    rdi
0x180039962  sub     rsp, 20h
0x180039966  mov     rdi, rcx
0x180039969  xor     r9d, r9d; dwMoveMethod
0x18003996c  mov     rcx, [rcx+40h]; hFile
0x180039970  xor     r8d, r8d; lpDistanceToMoveHigh
0x180039973  mov     edx, 200h; lDistanceToMove
0x180039978  xor     ebx, ebx
0x18003997a  call    cs:__imp_SetFilePointer
0x180039980  mov     rcx, [rdi+40h]; hFile
0x180039984  call    cs:__imp_SetEndOfFile
0x18003998a  test    eax, eax
0x18003998c  jnz     short loc_18003999D
0x18003998e  call    cs:__imp_GetLastError
0x180039994  mov     ecx, eax; unsigned int
0x180039996  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18003999b  mov     ebx, eax
0x18003999d  mov     rcx, [rdi+40h]; hFile
0x1800399a1  xor     r9d, r9d; dwMoveMethod
0x1800399a4  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800399a7  xor     edx, edx; lDistanceToMove
0x1800399a9  call    cs:__imp_SetFilePointer
0x1800399af  mov     eax, ebx
0x1800399b1  mov     rbx, [rsp+28h+arg_0]
0x1800399b6  add     rsp, 20h
0x1800399ba  pop     rdi
0x1800399bb  retn
```
