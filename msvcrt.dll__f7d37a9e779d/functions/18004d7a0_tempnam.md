# _tempnam

- ea: `0x18004d7a0`
- end: `0x18004da61`
- name: `_tempnam`
- size: `705`
- prototype: `char *__cdecl(const char *DirectoryName, const char *FilePrefix)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18004da70`

## callees

- `0x180002b90`
- `0x180007f00`
- `0x1800080a0`
- `0x18001d2b0`
- `0x18001d300`
- `0x18002a520`
- `0x18002f05c`
- `0x1800328b0`
- `0x18003e6c0`
- `0x18003e790`
- `0x18003e8e0`
- `0x18004d7a0`
- `0x180060c90`

## pseudocode

```c
char *__cdecl tempnam(const char *DirectoryName, const char *FilePrefix)
{
  __int64 v5; // r14
  errno_t v6; // edi
  __int64 v7; // rsi
  __int64 v8; // rax
  size_t v9; // r13
  char *v10; // rax
  char *v11; // rdi
  __int64 v12; // rax
  unsigned __int8 *v13; // r12
  bool v14; // zf
  char *v15; // r15
  int v16; // esi
  int v17; // ebx
  unsigned int v18; // ecx
  char *Buffer; // [rsp+70h] [rbp+18h] BYREF

  Buffer = 0;
  if ( !(unsigned int)mtinitlocknum(2) )
    return 0;
  LODWORD(v5) = 0;
  v6 = dupenv_s(&Buffer, 0, "TMP");
  if ( v6 == 22 )
    invoke_watson(0, 0, 0, 0, 0);
  if ( v6 || !Buffer || access_s(Buffer, 0) )
  {
    if ( !DirectoryName || access_s(DirectoryName, 0) )
    {
      DirectoryName = "\\";
      if ( access_s("\\", 0) )
        DirectoryName = ".";
    }
  }
  else
  {
    DirectoryName = Buffer;
  }
  v7 = -1;
  if ( FilePrefix )
  {
    v5 = -1;
    do
      ++v5;
    while ( FilePrefix[v5] );
  }
  v8 = -1;
  do
    ++v8;
  while ( DirectoryName[v8] );
  v9 = (unsigned int)(v5 + v8 + 12);
  v10 = (char *)calloc(v9, 1u);
  v11 = v10;
  if ( v10 )
  {
    *v10 = 0;
    if ( strcat_s(v10, (unsigned int)v9, DirectoryName) )
      invoke_watson(0, 0, 0, 0, 0);
    v12 = -1;
    do
      ++v12;
    while ( DirectoryName[v12] );
    v13 = (unsigned __int8 *)&DirectoryName[v12 - 1];
    if ( *v13 == 92 )
      v14 = v13 == mbsrchr((const unsigned __int8 *)DirectoryName, 0x5Cu);
    else
      v14 = *v13 == 47;
    if ( !v14 && strcat_s(v11, v9, "\\") )
      invoke_watson(0, 0, 0, 0, 0);
    if ( FilePrefix && strcat_s(v11, v9, FilePrefix) )
      invoke_watson(0, 0, 0, 0, 0);
    do
      ++v7;
    while ( v11[v7] );
    v15 = &v11[v7];
    lock(2);
    if ( old_pfxlen < (unsigned int)v5 )
      tempoff = 1;
    old_pfxlen = v5;
    v16 = tempoff;
    v17 = *errno();
    while ( 1 )
    {
      v18 = tempoff + 1;
      tempoff = v18;
      if ( v18 - v16 > 0x7FFFFFFF )
        break;
      if ( ultoa_s(v18, v15, (size_t)&v11[v9 - (_QWORD)v15], 10) )
        invoke_watson(0, 0, 0, 0, 0);
      *errno() = 0;
      if ( access_s(v11, 0) && *errno() != 13 )
      {
        *errno() = v17;
        goto LABEL_43;
      }
    }
    *errno() = v17;
    free(v11);
    v11 = 0;
LABEL_43:
    unlock(2);
  }
  free(Buffer);
  free(0);
  return v11;
}

```

## disassembly

```asm
0x18004d7a0  mov     [rsp+arg_0], rbx
0x18004d7a5  mov     [rsp+arg_8], rsi
0x18004d7aa  push    rdi
0x18004d7ab  push    r12
0x18004d7ad  push    r13
0x18004d7af  push    r14
0x18004d7b1  push    r15
0x18004d7b3  sub     rsp, 30h
0x18004d7b7  mov     r15, rdx
0x18004d7ba  mov     rbx, rcx
0x18004d7bd  xor     r12d, r12d
0x18004d7c0  mov     [rsp+58h+Buffer], r12
0x18004d7c5  lea     ecx, [r12+2]
0x18004d7ca  call    _mtinitlocknum
0x18004d7cf  test    eax, eax
0x18004d7d1  jnz     short loc_18004D7DA
0x18004d7d3  xor     eax, eax
0x18004d7d5  jmp     loc_18004DA49
0x18004d7da  mov     r14d, r12d
0x18004d7dd  lea     r8, aTmp_0; "TMP"
0x18004d7e4  xor     edx, edx; BufferCount
0x18004d7e6  lea     rcx, [rsp+58h+Buffer]; Buffer
0x18004d7eb  call    _dupenv_s
0x18004d7f0  mov     edi, eax
0x18004d7f2  cmp     eax, 16h
0x18004d7f5  jnz     short loc_18004D80B
0x18004d7f7  mov     [rsp+58h+Reserved], r12; Reserved
0x18004d7fc  xor     r9d, r9d; LineNo
0x18004d7ff  xor     r8d, r8d; FileName
0x18004d802  xor     edx, edx; FunctionName
0x18004d804  xor     ecx, ecx; Expression
0x18004d806  call    _invoke_watson
0x18004d80b  test    edi, edi
0x18004d80d  jnz     short loc_18004D82B
0x18004d80f  mov     rcx, [rsp+58h+Buffer]; FileName
0x18004d814  test    rcx, rcx
0x18004d817  jz      short loc_18004D82B
0x18004d819  xor     edx, edx; AccessMode
0x18004d81b  call    _access_s
0x18004d820  test    eax, eax
0x18004d822  jnz     short loc_18004D82B
0x18004d824  mov     rbx, [rsp+58h+Buffer]
0x18004d829  jmp     short loc_18004D860
0x18004d82b  test    rbx, rbx
0x18004d82e  jz      short loc_18004D83E
0x18004d830  xor     edx, edx; AccessMode
0x18004d832  mov     rcx, rbx; FileName
0x18004d835  call    _access_s
0x18004d83a  test    eax, eax
0x18004d83c  jz      short loc_18004D860
0x18004d83e  xor     edx, edx; AccessMode
0x18004d840  lea     rcx, asc_1800823D4; "\\"
0x18004d847  call    _access_s
0x18004d84c  lea     rbx, asc_1800823D4; "\\"
0x18004d853  lea     rcx, asc_180082E34; "."
0x18004d85a  test    eax, eax
0x18004d85c  cmovnz  rbx, rcx
0x18004d860  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004d864  test    r15, r15
0x18004d867  jz      short loc_18004D875
0x18004d869  mov     r14, rsi
0x18004d86c  inc     r14
0x18004d86f  cmp     [r15+r14], r12b
0x18004d873  jnz     short loc_18004D86C
0x18004d875  mov     rax, rsi
0x18004d878  inc     rax
0x18004d87b  cmp     [rbx+rax], r12b
0x18004d87f  jnz     short loc_18004D878
0x18004d881  add     eax, 0Ch
0x18004d884  add     eax, r14d
0x18004d887  mov     r13d, eax
0x18004d88a  mov     edx, 1; Size
0x18004d88f  mov     ecx, eax; Count
0x18004d891  call    calloc
0x18004d896  mov     rdi, rax
0x18004d899  test    rax, rax
0x18004d89c  jz      loc_18004DA35
0x18004d8a2  mov     [rax], r12b
0x18004d8a5  mov     r8, rbx; Source
0x18004d8a8  mov     edx, r13d; SizeInBytes
0x18004d8ab  mov     rcx, rax; Destination
0x18004d8ae  call    strcat_s
0x18004d8b3  test    eax, eax
0x18004d8b5  jz      short loc_18004D8CB
0x18004d8b7  mov     [rsp+58h+Reserved], r12; Reserved
0x18004d8bc  xor     r9d, r9d; LineNo
0x18004d8bf  xor     r8d, r8d; FileName
0x18004d8c2  xor     edx, edx; FunctionName
0x18004d8c4  xor     ecx, ecx; Expression
0x18004d8c6  call    _invoke_watson
0x18004d8cb  mov     rax, rsi
0x18004d8ce  inc     rax
0x18004d8d1  cmp     [rbx+rax], r12b
0x18004d8d5  jnz     short loc_18004D8CE
0x18004d8d7  lea     r12, [rbx-1]
0x18004d8db  add     r12, rax
0x18004d8de  mov     edx, 5Ch ; '\'; C
0x18004d8e3  cmp     [r12], dl
0x18004d8e7  jnz     loc_18004DA12
0x18004d8ed  mov     rcx, rbx; String
0x18004d8f0  call    _mbsrchr
0x18004d8f5  cmp     r12, rax
0x18004d8f8  jz      short loc_18004D928
0x18004d8fa  lea     r8, asc_1800823D4; "\\"
0x18004d901  mov     rdx, r13; SizeInBytes
0x18004d904  mov     rcx, rdi; Destination
0x18004d907  call    strcat_s
0x18004d90c  test    eax, eax
0x18004d90e  jz      short loc_18004D928
0x18004d910  mov     [rsp+58h+Reserved], 0; Reserved
0x18004d919  xor     r9d, r9d; LineNo
0x18004d91c  xor     r8d, r8d; FileName
0x18004d91f  xor     edx, edx; FunctionName
0x18004d921  xor     ecx, ecx; Expression
0x18004d923  call    _invoke_watson
0x18004d928  test    r15, r15
0x18004d92b  jz      short loc_18004D957
0x18004d92d  mov     r8, r15; Source
0x18004d930  mov     rdx, r13; SizeInBytes
0x18004d933  mov     rcx, rdi; Destination
0x18004d936  call    strcat_s
0x18004d93b  test    eax, eax
0x18004d93d  jz      short loc_18004D957
0x18004d93f  mov     [rsp+58h+Reserved], 0; Reserved
0x18004d948  xor     r9d, r9d; LineNo
0x18004d94b  xor     r8d, r8d; FileName
0x18004d94e  xor     edx, edx; FunctionName
0x18004d950  xor     ecx, ecx; Expression
0x18004d952  call    _invoke_watson
0x18004d957  inc     rsi
0x18004d95a  cmp     byte ptr [rdi+rsi], 0
0x18004d95e  jnz     short loc_18004D957
0x18004d960  lea     r15, [rsi+rdi]
0x18004d964  mov     r12d, 2
0x18004d96a  mov     ecx, r12d
0x18004d96d  call    _lock
0x18004d972  nop
0x18004d973  cmp     cs:_old_pfxlen, r14d
0x18004d97a  jnb     short loc_18004D986
0x18004d97c  mov     cs:_tempoff, 1
0x18004d986  mov     cs:_old_pfxlen, r14d
0x18004d98d  mov     esi, cs:_tempoff
0x18004d993  call    _errno
0x18004d998  mov     ebx, [rax]
0x18004d99a  mov     ecx, cs:_tempoff
0x18004d9a0  inc     ecx; Value
0x18004d9a2  mov     cs:_tempoff, ecx
0x18004d9a8  mov     eax, ecx
0x18004d9aa  sub     eax, esi
0x18004d9ac  cmp     eax, 7FFFFFFFh
0x18004d9b1  ja      short loc_18004DA1C
0x18004d9b3  mov     r8, r13
0x18004d9b6  sub     r8, r15
0x18004d9b9  add     r8, rdi; BufferCount
0x18004d9bc  mov     r9d, 0Ah; Radix
0x18004d9c2  mov     rdx, r15; Buffer
0x18004d9c5  call    _ultoa_s
0x18004d9ca  test    eax, eax
0x18004d9cc  jz      short loc_18004D9E6
0x18004d9ce  mov     [rsp+58h+Reserved], 0; Reserved
0x18004d9d7  xor     r9d, r9d; LineNo
0x18004d9da  xor     r8d, r8d; FileName
0x18004d9dd  xor     edx, edx; FunctionName
0x18004d9df  xor     ecx, ecx; Expression
0x18004d9e1  call    _invoke_watson
0x18004d9e6  call    _errno
0x18004d9eb  mov     dword ptr [rax], 0
0x18004d9f1  xor     edx, edx; AccessMode
0x18004d9f3  mov     rcx, rdi; FileName
0x18004d9f6  call    _access_s
0x18004d9fb  test    eax, eax
0x18004d9fd  jz      short loc_18004D99A
0x18004d9ff  call    _errno
0x18004da04  cmp     dword ptr [rax], 0Dh
0x18004da07  jz      short loc_18004D99A
0x18004da09  call    _errno
0x18004da0e  mov     [rax], ebx
0x18004da10  jmp     short loc_18004DA2D
0x18004da12  cmp     byte ptr [r12], 2Fh ; '/'
0x18004da17  jmp     loc_18004D8F8
0x18004da1c  call    _errno
0x18004da21  mov     [rax], ebx
0x18004da23  mov     rcx, rdi; Block
0x18004da26  call    free
0x18004da2b  xor     edi, edi
0x18004da2d  mov     ecx, r12d
0x18004da30  call    _unlock
0x18004da35  mov     rcx, [rsp+58h+Buffer]; Block
0x18004da3a  call    free
0x18004da3f  xor     ecx, ecx; Block
0x18004da41  call    free
0x18004da46  mov     rax, rdi
0x18004da49  mov     rbx, [rsp+58h+arg_0]
0x18004da4e  mov     rsi, [rsp+58h+arg_8]
0x18004da53  add     rsp, 30h
0x18004da57  pop     r15
0x18004da59  pop     r14
0x18004da5b  pop     r13
0x18004da5d  pop     r12
0x18004da5f  pop     rdi
0x18004da60  retn
0x18007c006  push    rbp
0x18007c008  sub     rsp, 30h
0x18007c00c  mov     rbp, rdx
0x18007c00f  mov     ecx, 2
0x18007c014  call    _unlock
0x18007c019  nop
0x18007c01a  add     rsp, 30h
0x18007c01e  pop     rbp
0x18007c01f  retn
```
