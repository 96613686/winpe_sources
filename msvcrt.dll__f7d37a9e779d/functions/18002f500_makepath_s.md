# _makepath_s

- ea: `0x18002f500`
- end: `0x18002f648`
- name: `_makepath_s`
- size: `328`
- prototype: `errno_t __cdecl(char *Buffer, size_t BufferCount, const char *Drive, const char *Dir, const char *Filename, const char *Ext)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002f4d0`

## callees

- `0x180007f00`
- `0x180026cc0`
- `0x18002f050`
- `0x18002f500`

## pseudocode

```c
errno_t __cdecl makepath_s(
        char *Buffer,
        size_t BufferCount,
        const char *Drive,
        const char *Dir,
        const char *Filename,
        const char *Ext)
{
  __int64 v8; // rbx
  char *v9; // rdi
  const unsigned __int8 *v10; // rdx
  char v11; // al
  unsigned __int8 *v12; // rax
  const char *v13; // rcx
  const char *v14; // rcx
  int *v15; // rax
  int v16; // ebx

  if ( !Buffer || !BufferCount )
  {
    v15 = errno();
    v16 = 22;
LABEL_32:
    *v15 = v16;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  v8 = 0;
  v9 = Buffer;
  if ( Drive && *Drive )
  {
    v8 = 2;
    if ( BufferCount <= 2 )
      goto LABEL_29;
    *Buffer = *Drive;
    v9 = Buffer + 2;
    Buffer[1] = 58;
  }
  if ( Dir )
  {
    v10 = (const unsigned __int8 *)Dir;
    if ( *Dir )
    {
      do
      {
        if ( ++v8 >= BufferCount )
          goto LABEL_29;
        v11 = *v10++;
        *v9++ = v11;
      }
      while ( *v10 );
      v12 = mbsdec((const unsigned __int8 *)Dir, v10);
      if ( *v12 != 47 && *v12 != 92 )
      {
        if ( ++v8 >= BufferCount )
          goto LABEL_29;
        *v9++ = 92;
      }
    }
  }
  v13 = Filename;
  if ( Filename )
  {
    while ( *v13 )
    {
      if ( ++v8 >= BufferCount )
        goto LABEL_29;
      *v9++ = *v13++;
    }
  }
  v14 = Ext;
  if ( Ext )
  {
    if ( *Ext && *Ext != 46 )
    {
      if ( ++v8 < BufferCount )
      {
        *v9++ = 46;
        goto LABEL_27;
      }
      goto LABEL_29;
    }
LABEL_27:
    while ( *v14 )
    {
      if ( ++v8 >= BufferCount )
        goto LABEL_29;
      *v9++ = *v14++;
    }
  }
  if ( v8 + 1 > BufferCount )
  {
LABEL_29:
    *Buffer = 0;
    v15 = errno();
    v16 = 34;
    goto LABEL_32;
  }
  *v9 = 0;
  return 0;
}

```

## disassembly

```asm
0x18002f500  push    rbx
0x18002f502  push    rsi
0x18002f503  push    rdi
0x18002f504  push    r14
0x18002f506  sub     rsp, 38h
0x18002f50a  mov     rsi, rdx
0x18002f50d  mov     r14, rcx
0x18002f510  test    rcx, rcx
0x18002f513  jz      loc_18002F618
0x18002f519  test    rdx, rdx
0x18002f51c  jz      loc_18002F618
0x18002f522  xor     ebx, ebx
0x18002f524  mov     rdi, rcx
0x18002f527  test    r8, r8
0x18002f52a  jz      short loc_18002F54B
0x18002f52c  mov     al, [r8]
0x18002f52f  test    al, al
0x18002f531  jz      short loc_18002F54B
0x18002f533  mov     ebx, 2
0x18002f538  cmp     rdx, rbx
0x18002f53b  jbe     loc_18002F601
0x18002f541  mov     [rcx], al
0x18002f543  lea     rdi, [rcx+2]
0x18002f547  mov     byte ptr [rcx+1], 3Ah ; ':'
0x18002f54b  test    r9, r9
0x18002f54e  jz      short loc_18002F594
0x18002f550  cmp     byte ptr [r9], 0
0x18002f554  mov     rdx, r9
0x18002f557  jz      short loc_18002F594
0x18002f559  inc     rbx
0x18002f55c  cmp     rbx, rsi
0x18002f55f  jnb     loc_18002F601
0x18002f565  mov     al, [rdx]
0x18002f567  inc     rdx; Pos
0x18002f56a  mov     [rdi], al
0x18002f56c  inc     rdi
0x18002f56f  cmp     byte ptr [rdx], 0
0x18002f572  jnz     short loc_18002F559
0x18002f574  mov     rcx, r9; Start
0x18002f577  call    _mbsdec
0x18002f57c  cmp     byte ptr [rax], 2Fh ; '/'
0x18002f57f  jz      short loc_18002F594
0x18002f581  cmp     byte ptr [rax], 5Ch ; '\'
0x18002f584  jz      short loc_18002F594
0x18002f586  inc     rbx
0x18002f589  cmp     rbx, rsi
0x18002f58c  jnb     short loc_18002F601
0x18002f58e  mov     byte ptr [rdi], 5Ch ; '\'
0x18002f591  inc     rdi
0x18002f594  mov     rcx, [rsp+58h+Filename]
0x18002f59c  test    rcx, rcx
0x18002f59f  jz      short loc_18002F5BA
0x18002f5a1  jmp     short loc_18002F5B5
0x18002f5a3  inc     rbx
0x18002f5a6  cmp     rbx, rsi
0x18002f5a9  jnb     short loc_18002F601
0x18002f5ab  mov     al, [rcx]
0x18002f5ad  mov     [rdi], al
0x18002f5af  inc     rdi
0x18002f5b2  inc     rcx
0x18002f5b5  cmp     byte ptr [rcx], 0
0x18002f5b8  jnz     short loc_18002F5A3
0x18002f5ba  mov     rcx, [rsp+58h+Ext]
0x18002f5c2  test    rcx, rcx
0x18002f5c5  jz      short loc_18002F5F8
0x18002f5c7  mov     al, [rcx]
0x18002f5c9  test    al, al
0x18002f5cb  jz      short loc_18002F5F3
0x18002f5cd  cmp     al, 2Eh ; '.'
0x18002f5cf  jz      short loc_18002F5F3
0x18002f5d1  inc     rbx
0x18002f5d4  cmp     rbx, rsi
0x18002f5d7  jnb     short loc_18002F601
0x18002f5d9  mov     byte ptr [rdi], 2Eh ; '.'
0x18002f5dc  inc     rdi
0x18002f5df  jmp     short loc_18002F5F3
0x18002f5e1  inc     rbx
0x18002f5e4  cmp     rbx, rsi
0x18002f5e7  jnb     short loc_18002F601
0x18002f5e9  mov     al, [rcx]
0x18002f5eb  mov     [rdi], al
0x18002f5ed  inc     rdi
0x18002f5f0  inc     rcx
0x18002f5f3  cmp     byte ptr [rcx], 0
0x18002f5f6  jnz     short loc_18002F5E1
0x18002f5f8  lea     rax, [rbx+1]
0x18002f5fc  cmp     rax, rsi
0x18002f5ff  jbe     short loc_18002F611
0x18002f601  mov     byte ptr [r14], 0
0x18002f605  call    _errno
0x18002f60a  mov     ebx, 22h ; '"'
0x18002f60f  jmp     short loc_18002F622
0x18002f611  mov     byte ptr [rdi], 0
0x18002f614  xor     eax, eax
0x18002f616  jmp     short loc_18002F63E
0x18002f618  call    _errno
0x18002f61d  mov     ebx, 16h
0x18002f622  xor     r9d, r9d; LineNo
0x18002f625  mov     [rsp+58h+Reserved], 0; Reserved
0x18002f62e  xor     r8d, r8d; FileName
0x18002f631  mov     [rax], ebx
0x18002f633  xor     edx, edx; FunctionName
0x18002f635  xor     ecx, ecx; Expression
0x18002f637  call    _invalid_parameter
0x18002f63c  mov     eax, ebx
0x18002f63e  add     rsp, 38h
0x18002f642  pop     r14
0x18002f644  pop     rdi
0x18002f645  pop     rsi
0x18002f646  pop     rbx
0x18002f647  retn
```
