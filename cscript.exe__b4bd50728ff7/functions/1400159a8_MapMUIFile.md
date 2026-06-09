# MapMUIFile

- ea: `0x1400159a8`
- end: `0x140015a8c`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x140015ad4`
- `0x140015be8`

## callees

- `0x1400159a8`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x140015a48`
- `KERNEL32!MapViewOfFile` at `0x140015a48`
- `KERNEL32!CloseHandle` at `0x140015a27`
- `KERNEL32!CloseHandle` at `0x140015a54`
- `KERNEL32!CloseHandle` at `0x140015a27`
- `KERNEL32!CloseHandle` at `0x140015a54`
- `KERNEL32!LoadLibraryExW` at `0x140015a77`
- `KERNEL32!LoadLibraryExW` at `0x140015a77`
- `KERNEL32!CreateFileMappingW` at `0x140015a1b`
- `KERNEL32!CreateFileMappingW` at `0x140015a1b`
- `KERNEL32!CreateFileW` at `0x1400159eb`
- `KERNEL32!CreateFileW` at `0x1400159eb`

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
0x1400159a8  mov     [rsp+arg_0], rbx
0x1400159ad  push    rdi
0x1400159ae  sub     rsp, 40h
0x1400159b2  mov     eax, r8d
0x1400159b5  test    rcx, rcx
0x1400159b8  jz      loc_140015A7F
0x1400159be  test    edx, edx
0x1400159c0  jz      loc_140015A6C
0x1400159c6  xor     r9d, r9d; lpSecurityAttributes
0x1400159c9  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1400159d2  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1400159da  mov     edx, 80000000h; dwDesiredAccess
0x1400159df  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1400159e7  lea     r8d, [r9+5]; dwShareMode
0x1400159eb  call    cs:__imp_CreateFileW
0x1400159f1  mov     rbx, rax
0x1400159f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400159f8  jz      loc_140015A7F
0x1400159fe  xor     r9d, r9d; dwMaximumSizeHigh
0x140015a01  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x140015a0a  xor     edx, edx; lpFileMappingAttributes
0x140015a0c  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x140015a14  mov     rcx, rax; hFile
0x140015a17  lea     r8d, [r9+8]; flProtect
0x140015a1b  call    cs:__imp_CreateFileMappingW
0x140015a21  mov     rcx, rbx; hObject
0x140015a24  mov     rdi, rax
0x140015a27  call    cs:__imp_CloseHandle
0x140015a2d  test    rdi, rdi
0x140015a30  jz      short loc_140015A7F
0x140015a32  xor     r9d, r9d; dwFileOffsetLow
0x140015a35  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x140015a3e  xor     r8d, r8d; dwFileOffsetHigh
0x140015a41  mov     rcx, rdi; hFileMappingObject
0x140015a44  lea     edx, [r9+1]; dwDesiredAccess
0x140015a48  call    cs:__imp_MapViewOfFile
0x140015a4e  mov     rcx, rdi; hObject
0x140015a51  mov     rbx, rax
0x140015a54  call    cs:__imp_CloseHandle
0x140015a5a  mov     rcx, rbx
0x140015a5d  or      rcx, 1; lpLibFileName
0x140015a61  neg     rbx
0x140015a64  sbb     rax, rax
0x140015a67  and     rax, rcx
0x140015a6a  jmp     short loc_140015A81
0x140015a6c  xor     r8d, r8d
0x140015a6f  test    eax, eax
0x140015a71  setnz   r8b; dwFlags
0x140015a75  xor     edx, edx; hFile
0x140015a77  call    cs:__imp_LoadLibraryExW
0x140015a7d  jmp     short loc_140015A81
0x140015a7f  xor     eax, eax
0x140015a81  mov     rbx, [rsp+48h+arg_0]
0x140015a86  add     rsp, 40h
0x140015a8a  pop     rdi
0x140015a8b  retn
```
