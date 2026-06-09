# MapMUIFile

- ea: `0x14010eb10`
- end: `0x14010ebf4`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x14010ec3c`
- `0x14010ed50`

## callees

- `0x14010eb10`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14010eb53`
- `KERNEL32!CreateFileW` at `0x14010eb53`
- `KERNEL32!MapViewOfFile` at `0x14010ebb0`
- `KERNEL32!MapViewOfFile` at `0x14010ebb0`
- `KERNEL32!CreateFileMappingW` at `0x14010eb83`
- `KERNEL32!CreateFileMappingW` at `0x14010eb83`
- `KERNEL32!LoadLibraryExW` at `0x14010ebdf`
- `KERNEL32!LoadLibraryExW` at `0x14010ebdf`
- `KERNEL32!CloseHandle` at `0x14010eb8f`
- `KERNEL32!CloseHandle` at `0x14010ebbc`
- `KERNEL32!CloseHandle` at `0x14010eb8f`
- `KERNEL32!CloseHandle` at `0x14010ebbc`

## pseudocode

```c
HMODULE __fastcall MapMUIFile(const WCHAR *a1, int a2, int a3)
{
  HANDLE FileW; // rax
  void *v4; // rbx
  HANDLE FileMappingW; // rdi
  unsigned __int64 v6; // rbx

  if ( a1 )
  {
    if ( !a2 )
      return LoadLibraryExW(a1, 0, a3 != 0);
    FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 8u, 0, 0, 0);
      CloseHandle(v4);
      if ( FileMappingW )
      {
        v6 = (unsigned __int64)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
        CloseHandle(FileMappingW);
        return (HMODULE)((v6 | 1) & -(__int64)(v6 != 0));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14010eb10  mov     [rsp+arg_0], rbx
0x14010eb15  push    rdi
0x14010eb16  sub     rsp, 40h
0x14010eb1a  mov     eax, r8d
0x14010eb1d  test    rcx, rcx
0x14010eb20  jz      loc_14010EBE7
0x14010eb26  test    edx, edx
0x14010eb28  jz      loc_14010EBD4
0x14010eb2e  xor     r9d, r9d; lpSecurityAttributes
0x14010eb31  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14010eb3a  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14010eb42  mov     edx, 80000000h; dwDesiredAccess
0x14010eb47  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14010eb4f  lea     r8d, [r9+5]; dwShareMode
0x14010eb53  call    cs:__imp_CreateFileW
0x14010eb59  mov     rbx, rax
0x14010eb5c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14010eb60  jz      loc_14010EBE7
0x14010eb66  xor     r9d, r9d; dwMaximumSizeHigh
0x14010eb69  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x14010eb72  xor     edx, edx; lpFileMappingAttributes
0x14010eb74  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x14010eb7c  mov     rcx, rax; hFile
0x14010eb7f  lea     r8d, [r9+8]; flProtect
0x14010eb83  call    cs:__imp_CreateFileMappingW
0x14010eb89  mov     rcx, rbx; hObject
0x14010eb8c  mov     rdi, rax
0x14010eb8f  call    cs:__imp_CloseHandle
0x14010eb95  test    rdi, rdi
0x14010eb98  jz      short loc_14010EBE7
0x14010eb9a  xor     r9d, r9d; dwFileOffsetLow
0x14010eb9d  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x14010eba6  xor     r8d, r8d; dwFileOffsetHigh
0x14010eba9  mov     rcx, rdi; hFileMappingObject
0x14010ebac  lea     edx, [r9+1]; dwDesiredAccess
0x14010ebb0  call    cs:__imp_MapViewOfFile
0x14010ebb6  mov     rcx, rdi; hObject
0x14010ebb9  mov     rbx, rax
0x14010ebbc  call    cs:__imp_CloseHandle
0x14010ebc2  mov     rcx, rbx
0x14010ebc5  or      rcx, 1; lpLibFileName
0x14010ebc9  neg     rbx
0x14010ebcc  sbb     rax, rax
0x14010ebcf  and     rax, rcx
0x14010ebd2  jmp     short loc_14010EBE9
0x14010ebd4  xor     r8d, r8d
0x14010ebd7  test    eax, eax
0x14010ebd9  setnz   r8b; dwFlags
0x14010ebdd  xor     edx, edx; hFile
0x14010ebdf  call    cs:__imp_LoadLibraryExW
0x14010ebe5  jmp     short loc_14010EBE9
0x14010ebe7  xor     eax, eax
0x14010ebe9  mov     rbx, [rsp+48h+arg_0]
0x14010ebee  add     rsp, 40h
0x14010ebf2  pop     rdi
0x14010ebf3  retn
```
