# CopyEnhMetaFileW

- ea: `0x180034c10`
- end: `0x180034d77`
- name: `CopyEnhMetaFileW`
- size: `359`
- prototype: `HENHMETAFILE __stdcall(HENHMETAFILE hEnh, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800904e0`

## callees

- `0x18002c5a0`
- `0x18002e040`
- `0x180031f30`
- `0x1800343a0`
- `0x180034c10`
- `0x1800a68d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034c9d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034c9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034d08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034d17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034d08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034d17`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180034cf1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180034cf1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180034ccc`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180034ccc`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180034d5f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180034d5f`

## pseudocode

```c
HENHMETAFILE __stdcall CopyEnhMetaFileW(HENHMETAFILE hEnh, LPCWSTR lpFileName)
{
  __int64 v3; // rax
  _DWORD *v4; // rbx
  __int64 v5; // rdi
  const BYTE *v6; // rax
  const BYTE *v7; // r14
  HANDLE FileW; // rax
  void *v9; // r15
  const void *v10; // rsi
  HANDLE FileMappingW; // rax
  void *v12; // r12
  void *v13; // rax
  HENHMETAFILE result; // rax

  if ( gbDisableMetaFiles )
    return 0;
  v3 = pvClientObjGet(hEnh, 4587520);
  if ( !v3 )
    return 0;
  v4 = (_DWORD *)(v3 + 40);
  v5 = *(_QWORD *)(v3 + 48);
  if ( !v5 )
    return 0;
  v6 = (const BYTE *)EMFContainer::ObtainPtr((EMFContainer *)(v3 + 40), 0, *(_DWORD *)(v5 + 48));
  v7 = v6;
  if ( !v6 )
    return 0;
  if ( lpFileName )
  {
    FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 2u, 0x80u, 0);
    v9 = FileW;
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_12;
    v10 = 0;
    FileMappingW = CreateFileMappingW(FileW, 0, 4u, 0, *(_DWORD *)(v5 + 48), 0);
    v12 = FileMappingW;
    if ( FileMappingW )
    {
      v13 = MapViewOfFile(FileMappingW, 2u, 0, 0, 0);
      v10 = v13;
      if ( v13 )
      {
        memcpy_0(v13, v7, *(unsigned int *)(v5 + 48));
        UnmapViewOfFile(v10);
      }
      CloseHandle(v12);
    }
    CloseHandle(v9);
    if ( v10 )
      result = GetEnhMetaFileW(lpFileName);
    else
LABEL_12:
      result = 0;
  }
  else
  {
    result = SetEnhMetaFileBits(*(_DWORD *)(v5 + 48), v6);
  }
  --*v4;
  return result;
}

```

## disassembly

```asm
0x180034c10  push    rbx
0x180034c12  push    rbp
0x180034c13  push    rsi
0x180034c14  push    rdi
0x180034c15  push    r12
0x180034c17  push    r14
0x180034c19  push    r15
0x180034c1b  sub     rsp, 40h
0x180034c1f  cmp     cs:gbDisableMetaFiles, 0
0x180034c26  mov     rbp, rdx
0x180034c29  jnz     loc_180034D49
0x180034c2f  mov     edx, 460000h
0x180034c34  call    pvClientObjGet
0x180034c39  test    rax, rax
0x180034c3c  jz      loc_180034D49
0x180034c42  lea     rbx, [rax+28h]
0x180034c46  mov     rdi, [rbx+8]
0x180034c4a  test    rdi, rdi
0x180034c4d  jz      loc_180034D49
0x180034c53  mov     r8d, [rdi+30h]; unsigned int
0x180034c57  xor     edx, edx; unsigned int
0x180034c59  mov     rcx, rbx; this
0x180034c5c  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x180034c61  mov     r14, rax
0x180034c64  test    rax, rax
0x180034c67  jz      loc_180034D49
0x180034c6d  test    rbp, rbp
0x180034c70  jz      loc_180034D3C
0x180034c76  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180034c7f  xor     r9d, r9d; lpSecurityAttributes
0x180034c82  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180034c8a  xor     r8d, r8d; dwShareMode
0x180034c8d  mov     edx, 0C0000000h; dwDesiredAccess
0x180034c92  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x180034c9a  mov     rcx, rbp; lpFileName
0x180034c9d  call    cs:__imp_CreateFileW
0x180034ca4  nop     dword ptr [rax+rax+00h]
0x180034ca9  mov     r15, rax
0x180034cac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034cb0  jz      short loc_180034D28
0x180034cb2  mov     ecx, [rdi+30h]
0x180034cb5  xor     esi, esi
0x180034cb7  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rsi; lpName
0x180034cbc  xor     r9d, r9d; dwMaximumSizeHigh
0x180034cbf  mov     [rsp+78h+dwCreationDisposition], ecx; dwMaximumSizeLow
0x180034cc3  xor     edx, edx; lpFileMappingAttributes
0x180034cc5  mov     rcx, rax; hFile
0x180034cc8  lea     r8d, [rsi+4]; flProtect
0x180034ccc  call    cs:__imp_CreateFileMappingW
0x180034cd3  nop     dword ptr [rax+rax+00h]
0x180034cd8  mov     r12, rax
0x180034cdb  test    rax, rax
0x180034cde  jz      short loc_180034D14
0x180034ce0  xor     r9d, r9d; dwFileOffsetLow
0x180034ce3  mov     qword ptr [rsp+78h+dwCreationDisposition], rsi; dwNumberOfBytesToMap
0x180034ce8  xor     r8d, r8d; dwFileOffsetHigh
0x180034ceb  lea     edx, [rsi+2]; dwDesiredAccess
0x180034cee  mov     rcx, rax; hFileMappingObject
0x180034cf1  call    cs:__imp_MapViewOfFile
0x180034cf8  nop     dword ptr [rax+rax+00h]
0x180034cfd  mov     rsi, rax
0x180034d00  test    rax, rax
0x180034d03  jnz     short loc_180034D4D
0x180034d05  mov     rcx, r12; hObject
0x180034d08  call    cs:__imp_CloseHandle
0x180034d0f  nop     dword ptr [rax+rax+00h]
0x180034d14  mov     rcx, r15; hObject
0x180034d17  call    cs:__imp_CloseHandle
0x180034d1e  nop     dword ptr [rax+rax+00h]
0x180034d23  test    rsi, rsi
0x180034d26  jnz     short loc_180034D6D
0x180034d28  xor     eax, eax
0x180034d2a  dec     dword ptr [rbx]
0x180034d2c  add     rsp, 40h
0x180034d30  pop     r15
0x180034d32  pop     r14
0x180034d34  pop     r12
0x180034d36  pop     rdi
0x180034d37  pop     rsi
0x180034d38  pop     rbp
0x180034d39  pop     rbx
0x180034d3a  retn
0x180034d3c  mov     ecx, [rdi+30h]; nSize
0x180034d3f  mov     rdx, r14; pb
0x180034d42  call    SetEnhMetaFileBits
0x180034d47  jmp     short loc_180034D2A
0x180034d49  xor     eax, eax
0x180034d4b  jmp     short loc_180034D2C
0x180034d4d  mov     r8d, [rdi+30h]; Size
0x180034d51  mov     rdx, r14; Src
0x180034d54  mov     rcx, rsi; void *
0x180034d57  call    memcpy_0
0x180034d5c  mov     rcx, rsi; lpBaseAddress
0x180034d5f  call    cs:__imp_UnmapViewOfFile
0x180034d66  nop     dword ptr [rax+rax+00h]
0x180034d6b  jmp     short loc_180034D05
0x180034d6d  mov     rcx, rbp; lpName
0x180034d70  call    GetEnhMetaFileW
0x180034d75  jmp     short loc_180034D2A
```
