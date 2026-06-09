# _AppendCrlPreFetchEventToLogFile

- ea: `0x18001eb48`
- end: `0x18001ec12`
- name: `_AppendCrlPreFetchEventToLogFile`
- size: `202`
- prototype: `void __fastcall(const WCHAR *, _BYTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001f310`

## callees

- `0x18001eb48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ebb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ebb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eba6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ebf3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ebf3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001ebd1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001ebd1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001eb9d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001eb9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebfc`

## pseudocode

```c
void __fastcall AppendCrlPreFetchEventToLogFile(const WCHAR *a1, _BYTE *a2)
{
  __int64 v3; // rbx
  HANDLE FileW; // rdi
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+10h] BYREF

  NumberOfBytesWritten = 0;
  if ( a2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
  }
  else
  {
    LODWORD(v3) = 0;
  }
  FileW = CreateFileW(a1, 0xC0000000, 3u, 0, 4u, 0, 0);
  LastError = GetLastError();
  if ( FileW == (HANDLE)-1LL )
  {
    SetLastError(LastError);
  }
  else
  {
    if ( LastError != 183 || SetFilePointer(FileW, 0, 0, 2u) != -1 )
      WriteFile(FileW, a2, v3, &NumberOfBytesWritten, 0);
    CloseHandle(FileW);
  }
}

```

## disassembly

```asm
0x18001eb48  mov     [rsp+arg_0], rbx
0x18001eb4d  mov     [rsp+arg_10], rsi
0x18001eb52  push    rdi
0x18001eb53  sub     rsp, 40h
0x18001eb57  mov     [rsp+48h+NumberOfBytesWritten], 0
0x18001eb5f  mov     rsi, rdx
0x18001eb62  test    rdx, rdx
0x18001eb65  jz      short loc_18001EB76
0x18001eb67  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001eb6b  inc     rbx
0x18001eb6e  cmp     byte ptr [rdx+rbx], 0
0x18001eb72  jnz     short loc_18001EB6B
0x18001eb74  jmp     short loc_18001EB78
0x18001eb76  xor     ebx, ebx
0x18001eb78  xor     r9d, r9d; lpSecurityAttributes
0x18001eb7b  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001eb84  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001eb8c  mov     edx, 0C0000000h; dwDesiredAccess
0x18001eb91  mov     [rsp+48h+dwCreationDisposition], 4; dwCreationDisposition
0x18001eb99  lea     r8d, [r9+3]; dwShareMode
0x18001eb9d  call    cs:__imp_CreateFileW
0x18001eba3  mov     rdi, rax
0x18001eba6  call    cs:__imp_GetLastError
0x18001ebac  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001ebb0  jnz     short loc_18001EBBC
0x18001ebb2  mov     ecx, eax; dwErrCode
0x18001ebb4  call    cs:__imp_SetLastError
0x18001ebba  jmp     short loc_18001EC02
0x18001ebbc  cmp     eax, 0B7h
0x18001ebc1  jnz     short loc_18001EBDC
0x18001ebc3  mov     r9d, 2; dwMoveMethod
0x18001ebc9  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001ebcc  xor     edx, edx; lDistanceToMove
0x18001ebce  mov     rcx, rdi; hFile
0x18001ebd1  call    cs:__imp_SetFilePointer
0x18001ebd7  cmp     eax, 0FFFFFFFFh
0x18001ebda  jz      short loc_18001EBF9
0x18001ebdc  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ebe1  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x18001ebea  mov     r8d, ebx; nNumberOfBytesToWrite
0x18001ebed  mov     rdx, rsi; lpBuffer
0x18001ebf0  mov     rcx, rdi; hFile
0x18001ebf3  call    cs:__imp_WriteFile
0x18001ebf9  mov     rcx, rdi; hObject
0x18001ebfc  call    cs:__imp_CloseHandle
0x18001ec02  mov     rbx, [rsp+48h+arg_0]
0x18001ec07  mov     rsi, [rsp+48h+arg_10]
0x18001ec0c  add     rsp, 40h
0x18001ec10  pop     rdi
0x18001ec11  retn
```
