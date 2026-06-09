# LoadFile(ushort const *,ulong *,void * *,void * *)

- ea: `0x18008ac10`
- end: `0x18008acf9`
- name: `?LoadFile@@YAHPEBGPEAKPEAPEAX2@Z`
- size: `233`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, void **, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180070738`

## callees

- `0x18008ac10`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18008acca`
- `KERNEL32!CloseHandle` at `0x18008ace5`
- `KERNEL32!CloseHandle` at `0x18008acca`
- `KERNEL32!CloseHandle` at `0x18008ace5`
- `KERNEL32!CreateFileW` at `0x18008ac58`
- `KERNEL32!CreateFileW` at `0x18008ac58`
- `KERNEL32!GetFileSize` at `0x18008ac70`
- `KERNEL32!GetFileSize` at `0x18008ac70`
- `KERNEL32!CreateFileMappingW` at `0x18008ac9a`
- `KERNEL32!CreateFileMappingW` at `0x18008ac9a`
- `KERNEL32!MapViewOfFile` at `0x18008acbe`
- `KERNEL32!MapViewOfFile` at `0x18008acbe`

## pseudocode

```c
__int64 __fastcall LoadFile(const unsigned __int16 *a1, unsigned int *a2, void **a3, void **a4)
{
  HANDLE FileW; // rax
  void *v8; // rbx
  DWORD FileSize; // eax
  HANDLE FileMappingW; // rax
  void *v11; // rdi
  void *v12; // rsi
  __int64 result; // rax

  *a4 = 0;
  *a3 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v8 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    FileSize = GetFileSize(FileW, 0);
    if ( a2 )
      *a2 = FileSize;
    FileMappingW = CreateFileMappingW(v8, 0, 2u, 0, 0, 0);
    v11 = FileMappingW;
    if ( FileMappingW )
    {
      v12 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      CloseHandle(v11);
      if ( v12 )
      {
        *a4 = v8;
        result = 1;
        *a3 = v12;
        return result;
      }
    }
    CloseHandle(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18008ac10  push    rbx
0x18008ac12  push    rsi
0x18008ac13  push    rdi
0x18008ac14  push    r14
0x18008ac16  push    r15
0x18008ac18  sub     rsp, 40h
0x18008ac1c  mov     r14, r9
0x18008ac1f  mov     qword ptr [r9], 0
0x18008ac26  xor     r9d, r9d; lpSecurityAttributes
0x18008ac29  mov     qword ptr [r8], 0
0x18008ac30  mov     r15, r8
0x18008ac33  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18008ac3c  mov     rdi, rdx
0x18008ac3f  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008ac47  mov     edx, 80000000h; dwDesiredAccess
0x18008ac4c  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18008ac54  lea     r8d, [r9+1]; dwShareMode
0x18008ac58  call    cs:__imp_CreateFileW
0x18008ac5e  mov     rbx, rax
0x18008ac61  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008ac65  jz      loc_18008ACEB
0x18008ac6b  xor     edx, edx; lpFileSizeHigh
0x18008ac6d  mov     rcx, rax; hFile
0x18008ac70  call    cs:__imp_GetFileSize
0x18008ac76  test    rdi, rdi
0x18008ac79  jz      short loc_18008AC7D
0x18008ac7b  mov     [rdi], eax
0x18008ac7d  xor     r9d, r9d; dwMaximumSizeHigh
0x18008ac80  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x18008ac89  xor     edx, edx; lpFileMappingAttributes
0x18008ac8b  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18008ac93  mov     rcx, rbx; hFile
0x18008ac96  lea     r8d, [r9+2]; flProtect
0x18008ac9a  call    cs:__imp_CreateFileMappingW
0x18008aca0  mov     rdi, rax
0x18008aca3  test    rax, rax
0x18008aca6  jz      short loc_18008ACE2
0x18008aca8  xor     r9d, r9d; dwFileOffsetLow
0x18008acab  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18008acb4  xor     r8d, r8d; dwFileOffsetHigh
0x18008acb7  mov     rcx, rax; hFileMappingObject
0x18008acba  lea     edx, [r9+4]; dwDesiredAccess
0x18008acbe  call    cs:__imp_MapViewOfFile
0x18008acc4  mov     rcx, rdi; hObject
0x18008acc7  mov     rsi, rax
0x18008acca  call    cs:__imp_CloseHandle
0x18008acd0  test    rsi, rsi
0x18008acd3  jz      short loc_18008ACE2
0x18008acd5  mov     [r14], rbx
0x18008acd8  mov     eax, 1
0x18008acdd  mov     [r15], rsi
0x18008ace0  jmp     short loc_18008ACED
0x18008ace2  mov     rcx, rbx; hObject
0x18008ace5  call    cs:__imp_CloseHandle
0x18008aceb  xor     eax, eax
0x18008aced  add     rsp, 40h
0x18008acf1  pop     r15
0x18008acf3  pop     r14
0x18008acf5  pop     rdi
0x18008acf6  pop     rsi
0x18008acf7  pop     rbx
0x18008acf8  retn
```
