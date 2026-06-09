# getFileSizeUNC

- ea: `0x1400099d4`
- end: `0x140009aa3`
- name: `getFileSizeUNC`
- size: `207`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000488c`

## callees

- `0x140008620`
- `0x1400099d4`

## import_xrefs

- `KERNEL32!GetFileSize` at `0x140009a49`
- `KERNEL32!GetFileSize` at `0x140009a49`
- `KERNEL32!GetFileAttributesW` at `0x1400099f5`
- `KERNEL32!GetFileAttributesW` at `0x1400099f5`
- `KERNEL32!CloseHandle` at `0x140009a54`
- `KERNEL32!CloseHandle` at `0x140009a54`
- `KERNEL32!CreateFileW` at `0x140009a32`
- `KERNEL32!CreateFileW` at `0x140009a32`

## pseudocode

```c
__int64 __fastcall getFileSizeUNC(LPCWSTR lpFileName, __int64 a2, __int64 a3)
{
  DWORD FileAttributesW; // eax
  const char *v6; // rdx
  HANDLE FileW; // rax
  void *v8; // rsi
  DWORD FileSize; // ebx
  DWORD FileSizeHigh; // [rsp+58h] [rbp+10h] BYREF
  int v12; // [rsp+5Ch] [rbp+14h]

  v12 = HIDWORD(a2);
  FileSizeHigh = 0;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
    goto LABEL_9;
  if ( (FileAttributesW & 0x50) != 0 )
  {
    v6 = "%1 is not a file";
    goto LABEL_10;
  }
  FileW = CreateFileW(lpFileName, 0, 2u, 0, 3u, 0, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL || (FileSize = GetFileSize(FileW, &FileSizeHigh), CloseHandle(v8), FileSize == -1) )
  {
LABEL_9:
    v6 = "Could not find file: %1";
    goto LABEL_10;
  }
  if ( (int)FileSizeHigh <= 0 )
    return FileSize;
  v6 = "File is larger than the 4GB limit: %1";
LABEL_10:
  ErrSet(a3, v6, "%s", pszDest);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1400099d4  mov     rax, rsp
0x1400099d7  mov     [rax+8], rbx
0x1400099db  mov     [rax+18h], rsi
0x1400099df  mov     [rax+10h], rdx
0x1400099e3  push    rdi
0x1400099e4  sub     rsp, 40h
0x1400099e8  mov     rdi, r8
0x1400099eb  mov     dword ptr [rax+10h], 0
0x1400099f2  mov     rbx, rcx
0x1400099f5  call    cs:__imp_GetFileAttributesW
0x1400099fb  cmp     eax, 0FFFFFFFFh
0x1400099fe  jz      short loc_140009A73
0x140009a00  test    al, 50h
0x140009a02  jz      short loc_140009A0D
0x140009a04  lea     rdx, a1IsNotAFile; "%1 is not a file"
0x140009a0b  jmp     short loc_140009A7A
0x140009a0d  xor     r9d, r9d; lpSecurityAttributes
0x140009a10  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x140009a19  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140009a21  xor     edx, edx; dwDesiredAccess
0x140009a23  mov     rcx, rbx; lpFileName
0x140009a26  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x140009a2e  lea     r8d, [r9+2]; dwShareMode
0x140009a32  call    cs:__imp_CreateFileW
0x140009a38  mov     rsi, rax
0x140009a3b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140009a3f  jz      short loc_140009A73
0x140009a41  lea     rdx, [rsp+48h+FileSizeHigh]; lpFileSizeHigh
0x140009a46  mov     rcx, rax; hFile
0x140009a49  call    cs:__imp_GetFileSize
0x140009a4f  mov     rcx, rsi; hObject
0x140009a52  mov     ebx, eax
0x140009a54  call    cs:__imp_CloseHandle
0x140009a5a  cmp     ebx, 0FFFFFFFFh
0x140009a5d  jz      short loc_140009A73
0x140009a5f  cmp     [rsp+48h+FileSizeHigh], 0
0x140009a64  jle     short loc_140009A6F
0x140009a66  lea     rdx, aFileIsLargerTh; "File is larger than the 4GB limit: %1"
0x140009a6d  jmp     short loc_140009A7A
0x140009a6f  mov     eax, ebx
0x140009a71  jmp     short loc_140009A93
0x140009a73  lea     rdx, aCouldNotFindFi; "Could not find file: %1"
0x140009a7a  lea     r9, pszDest
0x140009a81  mov     rcx, rdi
0x140009a84  lea     r8, aS_4; "%s"
0x140009a8b  call    ErrSet
0x140009a90  or      eax, 0FFFFFFFFh
0x140009a93  mov     rbx, [rsp+48h+arg_0]
0x140009a98  mov     rsi, [rsp+48h+arg_10]
0x140009a9d  add     rsp, 40h
0x140009aa1  pop     rdi
0x140009aa2  retn
```
