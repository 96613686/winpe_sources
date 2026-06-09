# CopyEnhMetaFileW

- ea: `0x18002b050`
- end: `0x18002b192`
- name: `CopyEnhMetaFileW`
- size: `322`
- prototype: `HENHMETAFILE __stdcall(HENHMETAFILE hEnh, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18008adb0`

## callees

- `0x180023650`
- `0x180024fb8`
- `0x180028ae0`
- `0x18002a8b0`
- `0x18002b050`
- `0x1800a3514`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b0dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b0dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b13f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b13f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002b125`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002b125`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002b106`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002b106`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002b180`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002b180`

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
0x18002b050  push    rbx
0x18002b052  push    rbp
0x18002b053  push    rsi
0x18002b054  push    rdi
0x18002b055  push    r12
0x18002b057  push    r14
0x18002b059  push    r15
0x18002b05b  sub     rsp, 40h
0x18002b05f  cmp     cs:gbDisableMetaFiles, 0
0x18002b066  mov     rbp, rdx
0x18002b069  jnz     loc_18002B16A
0x18002b06f  mov     edx, 460000h
0x18002b074  call    pvClientObjGet
0x18002b079  test    rax, rax
0x18002b07c  jz      loc_18002B16A
0x18002b082  lea     rbx, [rax+28h]
0x18002b086  mov     rdi, [rbx+8]
0x18002b08a  test    rdi, rdi
0x18002b08d  jz      loc_18002B16A
0x18002b093  mov     r8d, [rdi+30h]; unsigned int
0x18002b097  xor     edx, edx; unsigned int
0x18002b099  mov     rcx, rbx; this
0x18002b09c  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x18002b0a1  mov     r14, rax
0x18002b0a4  test    rax, rax
0x18002b0a7  jz      loc_18002B16A
0x18002b0ad  test    rbp, rbp
0x18002b0b0  jz      loc_18002B15D
0x18002b0b6  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18002b0bf  xor     r9d, r9d; lpSecurityAttributes
0x18002b0c2  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002b0ca  xor     r8d, r8d; dwShareMode
0x18002b0cd  mov     edx, 0C0000000h; dwDesiredAccess
0x18002b0d2  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x18002b0da  mov     rcx, rbp; lpFileName
0x18002b0dd  call    cs:__imp_CreateFileW
0x18002b0e3  mov     r15, rax
0x18002b0e6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b0ea  jz      short loc_18002B14A
0x18002b0ec  mov     ecx, [rdi+30h]
0x18002b0ef  xor     esi, esi
0x18002b0f1  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rsi; lpName
0x18002b0f6  xor     r9d, r9d; dwMaximumSizeHigh
0x18002b0f9  mov     [rsp+78h+dwCreationDisposition], ecx; dwMaximumSizeLow
0x18002b0fd  xor     edx, edx; lpFileMappingAttributes
0x18002b0ff  mov     rcx, rax; hFile
0x18002b102  lea     r8d, [rsi+4]; flProtect
0x18002b106  call    cs:__imp_CreateFileMappingW
0x18002b10c  mov     r12, rax
0x18002b10f  test    rax, rax
0x18002b112  jz      short loc_18002B13C
0x18002b114  xor     r9d, r9d; dwFileOffsetLow
0x18002b117  mov     qword ptr [rsp+78h+dwCreationDisposition], rsi; dwNumberOfBytesToMap
0x18002b11c  xor     r8d, r8d; dwFileOffsetHigh
0x18002b11f  lea     edx, [rsi+2]; dwDesiredAccess
0x18002b122  mov     rcx, rax; hFileMappingObject
0x18002b125  call    cs:__imp_MapViewOfFile
0x18002b12b  mov     rsi, rax
0x18002b12e  test    rax, rax
0x18002b131  jnz     short loc_18002B16E
0x18002b133  mov     rcx, r12; hObject
0x18002b136  call    cs:__imp_CloseHandle
0x18002b13c  mov     rcx, r15; hObject
0x18002b13f  call    cs:__imp_CloseHandle
0x18002b145  test    rsi, rsi
0x18002b148  jnz     short loc_18002B188
0x18002b14a  xor     eax, eax
0x18002b14c  dec     dword ptr [rbx]
0x18002b14e  add     rsp, 40h
0x18002b152  pop     r15
0x18002b154  pop     r14
0x18002b156  pop     r12
0x18002b158  pop     rdi
0x18002b159  pop     rsi
0x18002b15a  pop     rbp
0x18002b15b  pop     rbx
0x18002b15c  retn
0x18002b15d  mov     ecx, [rdi+30h]; nSize
0x18002b160  mov     rdx, r14; pb
0x18002b163  call    SetEnhMetaFileBits
0x18002b168  jmp     short loc_18002B14C
0x18002b16a  xor     eax, eax
0x18002b16c  jmp     short loc_18002B14E
0x18002b16e  mov     r8d, [rdi+30h]; Size
0x18002b172  mov     rdx, r14; Src
0x18002b175  mov     rcx, rsi; void *
0x18002b178  call    memcpy_0
0x18002b17d  mov     rcx, rsi; lpBaseAddress
0x18002b180  call    cs:__imp_UnmapViewOfFile
0x18002b186  jmp     short loc_18002B133
0x18002b188  mov     rcx, rbp; lpName
0x18002b18b  call    GetEnhMetaFileW
0x18002b190  jmp     short loc_18002B14C
```
