# CreateFileForWrite

- ea: `0x180146ea4`
- end: `0x180146f88`
- name: `CreateFileForWrite`
- size: `228`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180146f90`

## callees

- `0x180019fe8`
- `0x180146ea4`
- `0x180148334`
- `0x1801484d8`
- `0x18015c080`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180146f31`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180146f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146f43`

## pseudocode

```c
__int64 __fastcall CreateFileForWrite(LPCWSTR lpFileName, _QWORD *a2)
{
  void *v2; // rdi
  int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  int Directory; // eax
  __int64 v9; // rdx
  HANDLE FileW; // rax
  signed int LastError; // eax
  void *Block; // [rsp+70h] [rbp+8h] BYREF

  v2 = 0;
  Block = 0;
  if ( !lpFileName || !a2 )
  {
    v7 = -2147024809;
    goto LABEL_13;
  }
  v5 = PathDecompose(lpFileName, &Block);
  v7 = v5;
  if ( v5 >= 0 )
  {
    v2 = Block;
    if ( Block )
    {
      Directory = PathCreateDirectory(Block);
      v7 = Directory;
      if ( Directory < 0 )
      {
        v9 = (unsigned int)Directory;
LABEL_14:
        LogErrorFxn(lpFileName, v9);
        goto LABEL_15;
      }
    }
    FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 1u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      *a2 = FileW;
      v7 = 0;
      goto LABEL_15;
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
    v9 = v7;
    goto LABEL_14;
  }
  LogErrorFxn(v6, (unsigned int)v5);
  v2 = Block;
LABEL_15:
  free(v2);
  return v7;
}

```

## disassembly

```asm
0x180146ea4  push    rbx
0x180146ea6  push    rsi
0x180146ea7  push    rdi
0x180146ea8  push    r14
0x180146eaa  sub     rsp, 48h
0x180146eae  xor     edi, edi
0x180146eb0  mov     r14, rdx
0x180146eb3  mov     [rsp+68h+Block], rdi
0x180146eb8  mov     rsi, rcx
0x180146ebb  test    rcx, rcx
0x180146ebe  jz      loc_180146F67
0x180146ec4  test    rdx, rdx
0x180146ec7  jz      loc_180146F67
0x180146ecd  lea     rdx, [rsp+68h+Block]
0x180146ed2  call    PathDecompose
0x180146ed7  mov     ebx, eax
0x180146ed9  test    eax, eax
0x180146edb  jns     short loc_180146EEE
0x180146edd  mov     edx, eax
0x180146edf  call    LogErrorFxn
0x180146ee4  mov     rdi, [rsp+68h+Block]
0x180146ee9  jmp     loc_180146F73
0x180146eee  mov     rdi, [rsp+68h+Block]
0x180146ef3  test    rdi, rdi
0x180146ef6  jz      short loc_180146F0A
0x180146ef8  mov     rcx, rdi
0x180146efb  call    PathCreateDirectory
0x180146f00  mov     ebx, eax
0x180146f02  test    eax, eax
0x180146f04  jns     short loc_180146F0A
0x180146f06  mov     edx, eax
0x180146f08  jmp     short loc_180146F6E
0x180146f0a  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180146f13  xor     r9d, r9d; lpSecurityAttributes
0x180146f16  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180146f1e  xor     r8d, r8d; dwShareMode
0x180146f21  mov     edx, 0C0000000h; dwDesiredAccess
0x180146f26  mov     [rsp+68h+dwCreationDisposition], 1; dwCreationDisposition
0x180146f2e  mov     rcx, rsi; lpFileName
0x180146f31  call    cs:__imp_CreateFileW
0x180146f38  nop     dword ptr [rax+rax+00h]
0x180146f3d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180146f41  jnz     short loc_180146F60
0x180146f43  call    cs:__imp_GetLastError
0x180146f4a  nop     dword ptr [rax+rax+00h]
0x180146f4f  mov     ebx, eax
0x180146f51  test    eax, eax
0x180146f53  jle     short loc_180146F6C
0x180146f55  movzx   ebx, ax
0x180146f58  or      ebx, 80070000h
0x180146f5e  jmp     short loc_180146F6C
0x180146f60  mov     [r14], rax
0x180146f63  xor     ebx, ebx
0x180146f65  jmp     short loc_180146F73
0x180146f67  mov     ebx, 80070057h
0x180146f6c  mov     edx, ebx
0x180146f6e  call    LogErrorFxn
0x180146f73  mov     rcx, rdi; Block
0x180146f76  call    free
0x180146f7b  mov     eax, ebx
0x180146f7d  add     rsp, 48h
0x180146f81  pop     r14
0x180146f83  pop     rdi
0x180146f84  pop     rsi
0x180146f85  pop     rbx
0x180146f86  retn
```
