# _fwrite_nolock

- ea: `0x180051c28`
- end: `0x180051dc7`
- name: `_fwrite_nolock`
- size: `415`
- prototype: `size_t __cdecl(const void *Buffer, size_t ElementSize, size_t ElementCount, FILE *Stream)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180050f80`
- `0x180051dd0`
- `0x1800520d0`

## callees

- `0x180007f00`
- `0x180023210`
- `0x18002f050`
- `0x18004a7c0`
- `0x18004a800`
- `0x18004a9c8`
- `0x180051c28`
- `0x180079c80`

## pseudocode

```c
size_t __cdecl fwrite_nolock(const void *Buffer, size_t ElementSize, size_t ElementCount, FILE *Stream)
{
  char *v6; // r14
  unsigned __int64 v8; // rdx
  size_t v9; // rdi
  size_t v10; // rbp
  unsigned int bufsiz; // r13d
  size_t cnt; // r12
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // eax
  size_t v16; // [rsp+90h] [rbp+18h]

  v16 = ElementCount;
  v6 = (char *)Buffer;
  if ( !ElementSize || !ElementCount )
    return 0;
  if ( !Stream
    || !Buffer
    || (v8 = 0xFFFFFFFFFFFFFFFFuLL % ElementSize, ElementCount > 0xFFFFFFFFFFFFFFFFuLL / ElementSize) )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  v9 = ElementCount * ElementSize;
  v10 = ElementCount * ElementSize;
  if ( (Stream->_flag & 0x10C) != 0 )
    bufsiz = Stream->_bufsiz;
  else
    bufsiz = 4096;
  if ( !v9 )
    return ElementCount;
  while ( (Stream->_flag & 0x108) != 0 )
  {
    cnt = (unsigned int)Stream->_cnt;
    if ( !(_DWORD)cnt )
      break;
    if ( (cnt & 0x80000000) != 0LL )
    {
      Stream->_flag |= 0x20u;
      return (v9 - v10) / ElementSize;
    }
    if ( v10 < cnt )
      LODWORD(cnt) = v10;
    memmove(Stream->_ptr, v6, (unsigned int)cnt);
    Stream->_cnt -= cnt;
    v10 -= (unsigned int)cnt;
    Stream->_ptr += (unsigned int)cnt;
    v6 += (unsigned int)cnt;
LABEL_32:
    if ( !v10 )
      return v16;
  }
  if ( v10 < bufsiz )
  {
    if ( flsbuf(*v6, Stream) == -1 )
      return (v9 - v10) / ElementSize;
    ++v6;
    --v10;
    bufsiz = 1;
    if ( Stream->_bufsiz > 0 )
      bufsiz = Stream->_bufsiz;
    goto LABEL_32;
  }
  if ( (Stream->_flag & 0x108) != 0 && (unsigned int)flush(Stream, v8) )
    return (v9 - v10) / ElementSize;
  if ( bufsiz )
    v13 = v10 - v10 % bufsiz;
  else
    v13 = v10;
  v14 = fileno(Stream);
  v15 = write(v14, v6, v13);
  if ( v15 != -1 )
  {
    v8 = v15;
    if ( v15 > v13 )
      v8 = v13;
    v10 -= v8;
    if ( v15 >= v13 )
    {
      v6 += v8;
      goto LABEL_32;
    }
  }
  Stream->_flag |= 0x20u;
  return (v9 - v10) / ElementSize;
}

```

## disassembly

```asm
0x180051c28  mov     [rsp+arg_10], r8
0x180051c2d  push    rbx
0x180051c2e  push    rbp
0x180051c2f  push    rsi
0x180051c30  push    rdi
0x180051c31  push    r12
0x180051c33  push    r13
0x180051c35  push    r14
0x180051c37  push    r15
0x180051c39  sub     rsp, 38h
0x180051c3d  mov     rsi, r9
0x180051c40  mov     r15, rdx
0x180051c43  mov     r14, rcx
0x180051c46  test    rdx, rdx
0x180051c49  jz      short loc_180051C78
0x180051c4b  test    r8, r8
0x180051c4e  jz      short loc_180051C78
0x180051c50  test    r9, r9
0x180051c53  jnz     short loc_180051C8B
0x180051c55  call    _errno
0x180051c5a  xor     r9d, r9d; LineNo
0x180051c5d  mov     [rsp+78h+Reserved], 0; Reserved
0x180051c66  xor     r8d, r8d; FileName
0x180051c69  xor     edx, edx; FunctionName
0x180051c6b  xor     ecx, ecx; Expression
0x180051c6d  mov     dword ptr [rax], 16h
0x180051c73  call    _invalid_parameter
0x180051c78  xor     eax, eax
0x180051c7a  add     rsp, 38h
0x180051c7e  pop     r15
0x180051c80  pop     r14
0x180051c82  pop     r13
0x180051c84  pop     r12
0x180051c86  pop     rdi
0x180051c87  pop     rsi
0x180051c88  pop     rbp
0x180051c89  pop     rbx
0x180051c8a  retn
0x180051c8b  test    rcx, rcx
0x180051c8e  jz      short loc_180051C55
0x180051c90  xor     edx, edx
0x180051c92  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051c96  div     r15
0x180051c99  cmp     r8, rax
0x180051c9c  ja      short loc_180051C55
0x180051c9e  mov     rdi, r15
0x180051ca1  imul    rdi, r8
0x180051ca5  test    dword ptr [r9+18h], 10Ch
0x180051cad  mov     rbp, rdi
0x180051cb0  jz      short loc_180051CB8
0x180051cb2  mov     r13d, [r9+24h]
0x180051cb6  jmp     short loc_180051CBE
0x180051cb8  mov     r13d, 1000h
0x180051cbe  test    rdi, rdi
0x180051cc1  jz      loc_180051DA3
0x180051cc7  mov     eax, [rsi+18h]
0x180051cca  mov     ecx, eax
0x180051ccc  and     ecx, 108h
0x180051cd2  jz      short loc_180051D0E
0x180051cd4  mov     r12d, [rsi+8]
0x180051cd8  test    r12d, r12d
0x180051cdb  jz      short loc_180051D0E
0x180051cdd  js      loc_180051DAB
0x180051ce3  cmp     rbp, r12
0x180051ce6  jnb     short loc_180051CEB
0x180051ce8  mov     r12d, ebp
0x180051ceb  mov     rcx, [rsi]; void *
0x180051cee  mov     rdx, r14; Src
0x180051cf1  mov     r8d, r12d; Size
0x180051cf4  mov     ebx, r12d
0x180051cf7  call    memmove
0x180051cfc  sub     [rsi+8], r12d
0x180051d00  sub     rbp, rbx
0x180051d03  add     [rsi], rbx
0x180051d06  add     r14, rbx
0x180051d09  jmp     loc_180051D92
0x180051d0e  mov     ebx, r13d
0x180051d11  cmp     rbp, rbx
0x180051d14  jb      short loc_180051D6C
0x180051d16  test    ecx, ecx
0x180051d18  jz      short loc_180051D2A
0x180051d1a  mov     rcx, rsi
0x180051d1d  call    _flush
0x180051d22  test    eax, eax
0x180051d24  jnz     loc_180051DB1
0x180051d2a  test    r13d, r13d
0x180051d2d  jz      short loc_180051D3D
0x180051d2f  xor     edx, edx
0x180051d31  mov     rax, rbp
0x180051d34  div     rbx
0x180051d37  mov     ebx, ebp
0x180051d39  sub     ebx, edx
0x180051d3b  jmp     short loc_180051D3F
0x180051d3d  mov     ebx, ebp
0x180051d3f  mov     rcx, rsi; Stream
0x180051d42  call    _fileno
0x180051d47  mov     ecx, eax; FileHandle
0x180051d49  mov     r8d, ebx; MaxCharCount
0x180051d4c  mov     rdx, r14; Buf
0x180051d4f  call    _write
0x180051d54  cmp     eax, 0FFFFFFFFh
0x180051d57  jz      short loc_180051DC1
0x180051d59  cmp     eax, ebx
0x180051d5b  mov     edx, eax
0x180051d5d  cmova   edx, ebx
0x180051d60  sub     rbp, rdx
0x180051d63  cmp     eax, ebx
0x180051d65  jb      short loc_180051DC1
0x180051d67  add     r14, rdx
0x180051d6a  jmp     short loc_180051D92
0x180051d6c  movsx   ecx, byte ptr [r14]; Ch
0x180051d70  mov     rdx, rsi; File
0x180051d73  call    _flsbuf
0x180051d78  cmp     eax, 0FFFFFFFFh
0x180051d7b  jz      short loc_180051DB1
0x180051d7d  inc     r14
0x180051d80  dec     rbp
0x180051d83  cmp     dword ptr [rsi+24h], 0
0x180051d87  mov     r13d, 1
0x180051d8d  cmovg   r13d, [rsi+24h]
0x180051d92  test    rbp, rbp
0x180051d95  jnz     loc_180051CC7
0x180051d9b  mov     r8, [rsp+78h+arg_10]
0x180051da3  mov     rax, r8
0x180051da6  jmp     loc_180051C7A
0x180051dab  or      eax, 20h
0x180051dae  mov     [rsi+18h], eax
0x180051db1  sub     rdi, rbp
0x180051db4  xor     edx, edx
0x180051db6  mov     rax, rdi
0x180051db9  div     r15
0x180051dbc  jmp     loc_180051C7A
0x180051dc1  or      dword ptr [rsi+18h], 20h
0x180051dc5  jmp     short loc_180051DB1
```
