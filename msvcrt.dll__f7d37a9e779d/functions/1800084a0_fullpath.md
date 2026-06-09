# _fullpath

- ea: `0x1800084a0`
- end: `0x1800085b8`
- name: `_fullpath`
- size: `280`
- prototype: `char *__cdecl(char *Buffer, const char *Path, size_t BufferCount)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x1800085c0`
- `0x180008960`
- `0x18000a0d8`
- `0x18002f9b0`

## callees

- `0x180007ea8`
- `0x180007f00`
- `0x1800084a0`
- `0x1800085d0`
- `0x18001d2b0`
- `0x18001d300`
- `0x18002f050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084e7`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800084dd`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18000855f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800084dd`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18000855f`

## pseudocode

```c
char *__cdecl fullpath(char *Buffer, const char *Path, size_t BufferCount)
{
  size_t v3; // rsi
  size_t v6; // rax
  DWORD LastError; // eax
  CHAR *v9; // rbx
  DWORD FullPathNameA; // eax
  LPSTR FilePart; // [rsp+68h] [rbp+10h] BYREF

  FilePart = 0;
  v3 = BufferCount;
  if ( !Path || !*Path )
    return getcwd(Buffer, BufferCount);
  if ( Buffer )
  {
    if ( !BufferCount )
    {
      *errno() = 22;
      invalid_parameter(0, 0, 0, 0, 0);
    }
    v9 = Buffer;
  }
  else
  {
    LODWORD(v6) = GetFullPathNameA(Path, 0, 0, 0);
    if ( !(_DWORD)v6 )
    {
LABEL_5:
      LastError = GetLastError();
      dosmaperr(LastError);
      return 0;
    }
    v6 = (unsigned int)v6;
    if ( v3 > (unsigned int)v6 )
      v6 = v3;
    v3 = v6;
    v9 = (CHAR *)calloc(v6, 1u);
    if ( !v9 )
    {
      *errno() = 12;
      return 0;
    }
  }
  FullPathNameA = GetFullPathNameA(Path, v3, v9, &FilePart);
  if ( FullPathNameA >= v3 )
  {
    if ( !Buffer )
      free(v9);
    *errno() = 34;
    return 0;
  }
  if ( !FullPathNameA )
  {
    if ( !Buffer )
      free(v9);
    goto LABEL_5;
  }
  return v9;
}

```

## disassembly

```asm
0x1800084a0  push    rbx
0x1800084a2  push    rbp
0x1800084a3  push    rsi
0x1800084a4  push    rdi
0x1800084a5  sub     rsp, 38h
0x1800084a9  mov     [rsp+58h+FilePart], 0
0x1800084b2  mov     rsi, r8
0x1800084b5  mov     rbp, rdx
0x1800084b8  mov     rdi, rcx
0x1800084bb  test    rdx, rdx
0x1800084be  jz      loc_1800085A8
0x1800084c4  cmp     byte ptr [rdx], 0
0x1800084c7  jz      loc_1800085A8
0x1800084cd  test    rcx, rcx
0x1800084d0  jnz     short loc_180008529
0x1800084d2  xor     r9d, r9d; lpFilePart
0x1800084d5  xor     r8d, r8d; lpBuffer
0x1800084d8  xor     edx, edx; nBufferLength
0x1800084da  mov     rcx, rbp; lpFileName
0x1800084dd  call    cs:__imp_GetFullPathNameA
0x1800084e3  test    eax, eax
0x1800084e5  jnz     short loc_1800084FB
0x1800084e7  call    cs:__imp_GetLastError
0x1800084ed  mov     ecx, eax
0x1800084ef  call    _dosmaperr
0x1800084f4  xor     eax, eax
0x1800084f6  jmp     loc_1800085AF
0x1800084fb  mov     eax, eax
0x1800084fd  mov     edx, 1; Size
0x180008502  cmp     rsi, rax
0x180008505  cmova   rax, rsi
0x180008509  mov     rcx, rax; Count
0x18000850c  mov     rsi, rax
0x18000850f  call    calloc
0x180008514  mov     rbx, rax
0x180008517  test    rax, rax
0x18000851a  jnz     short loc_180008552
0x18000851c  call    _errno
0x180008521  mov     dword ptr [rax], 0Ch
0x180008527  jmp     short loc_1800084F4
0x180008529  test    rsi, rsi
0x18000852c  jnz     short loc_18000854F
0x18000852e  call    _errno
0x180008533  xor     r9d, r9d; LineNo
0x180008536  mov     [rsp+58h+Reserved], rsi; Reserved
0x18000853b  xor     r8d, r8d; FileName
0x18000853e  xor     edx, edx; FunctionName
0x180008540  xor     ecx, ecx; Expression
0x180008542  mov     dword ptr [rax], 16h
0x180008548  call    _invalid_parameter
0x18000854d  jmp     short loc_1800084F4
0x18000854f  mov     rbx, rdi
0x180008552  mov     edx, esi; nBufferLength
0x180008554  lea     r9, [rsp+58h+FilePart]; lpFilePart
0x180008559  mov     r8, rbx; lpBuffer
0x18000855c  mov     rcx, rbp; lpFileName
0x18000855f  call    cs:__imp_GetFullPathNameA
0x180008565  mov     ecx, eax
0x180008567  cmp     rcx, rsi
0x18000856a  jb      short loc_180008589
0x18000856c  test    rdi, rdi
0x18000856f  jnz     short loc_180008579
0x180008571  mov     rcx, rbx; Block
0x180008574  call    free
0x180008579  call    _errno
0x18000857e  mov     dword ptr [rax], 22h ; '"'
0x180008584  jmp     loc_1800084F4
0x180008589  test    eax, eax
0x18000858b  jnz     short loc_1800085A3
0x18000858d  test    rdi, rdi
0x180008590  jnz     loc_1800084E7
0x180008596  mov     rcx, rbx; Block
0x180008599  call    free
0x18000859e  jmp     loc_1800084E7
0x1800085a3  mov     rax, rbx
0x1800085a6  jmp     short loc_1800085AF
0x1800085a8  mov     edx, esi; SizeInBytes
0x1800085aa  call    _getcwd
0x1800085af  add     rsp, 38h
0x1800085b3  pop     rdi
0x1800085b4  pop     rsi
0x1800085b5  pop     rbp
0x1800085b6  pop     rbx
0x1800085b7  retn
```
