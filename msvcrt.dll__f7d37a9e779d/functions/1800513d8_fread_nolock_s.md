# _fread_nolock_s

- ea: `0x1800513d8`
- end: `0x180051640`
- name: `_fread_nolock_s`
- size: `616`
- prototype: `size_t __cdecl(void *Buffer, size_t BufferSize, size_t ElementSize, size_t ElementCount, FILE *Stream)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180051674`

## callees

- `0x180007f00`
- `0x180021ae0`
- `0x18002f050`
- `0x18004a650`
- `0x18004a7c0`
- `0x1800513d8`
- `0x180060b70`
- `0x18007d030`

## pseudocode

```c
size_t __cdecl fread_nolock_s(void *Buffer, size_t BufferSize, size_t ElementSize, size_t ElementCount, FILE *Stream)
{
  size_t v10; // rbx
  rsize_t v11; // rcx
  size_t v12; // rsi
  char *v13; // r15
  unsigned int bufsiz; // r9d
  bool v15; // zf
  int flag; // eax
  size_t cnt; // r15
  __int64 v18; // rax
  char *v19; // r15
  int v20; // r15d
  unsigned __int64 v21; // rdx
  unsigned int v22; // r15d
  int v23; // eax
  unsigned int v24; // r8d
  int v25; // eax
  unsigned int v26; // [rsp+70h] [rbp+8h]
  char *Destination; // [rsp+78h] [rbp+10h]
  size_t v28; // [rsp+80h] [rbp+18h]

  if ( !ElementSize || !ElementCount )
    return 0;
  if ( !Buffer )
    goto LABEL_4;
  if ( !Stream || ElementCount > 0xFFFFFFFFFFFFFFFFuLL / ElementSize )
  {
    if ( BufferSize != -1 )
      memset_thunk_772440563353939046(Buffer, 0, BufferSize);
    if ( !Stream || ElementCount > 0xFFFFFFFFFFFFFFFFuLL / ElementSize )
    {
LABEL_4:
      *errno() = 22;
      invalid_parameter(0, 0, 0, 0, 0);
    }
  }
  Destination = (char *)Buffer;
  v10 = ElementCount * ElementSize;
  v11 = BufferSize;
  v12 = ElementCount * ElementSize;
  v28 = BufferSize;
  v13 = (char *)Buffer;
  if ( (Stream->_flag & 0x10C) != 0 )
    bufsiz = Stream->_bufsiz;
  else
    bufsiz = 4096;
  v26 = bufsiz;
  v15 = v10 == 0;
  while ( !v15 )
  {
    flag = Stream->_flag;
    if ( (flag & 0x10C) != 0 )
    {
      cnt = Stream->_cnt;
      if ( (_DWORD)cnt )
      {
        if ( (cnt & 0x80000000) != 0LL )
        {
          Stream->_flag = flag | 0x20;
          return (v10 - v12) / ElementSize;
        }
        if ( v12 < cnt )
          LODWORD(cnt) = v12;
        if ( (unsigned int)cnt > v11 )
          goto LABEL_42;
        memcpy_s(Destination, v11, Stream->_ptr, (unsigned int)cnt);
        Stream->_cnt -= cnt;
        v18 = (unsigned int)cnt;
        v19 = Destination;
        v12 -= v18;
        Stream->_ptr += v18;
LABEL_24:
        v13 = &v19[v18];
        bufsiz = v26;
        v11 = v28 - v18;
        goto LABEL_41;
      }
      v13 = Destination;
    }
    if ( v12 >= bufsiz )
    {
      if ( bufsiz )
      {
        if ( v12 <= 0x7FFFFFFF )
        {
          v20 = v12;
          v21 = v12 % bufsiz;
        }
        else
        {
          v20 = 0x7FFFFFFF;
          LODWORD(v21) = 0x7FFFFFFF % bufsiz;
        }
        v22 = v20 - v21;
      }
      else
      {
        v22 = v12;
        if ( v12 > 0x7FFFFFFF )
          v22 = 0x7FFFFFFF;
      }
      if ( v22 > v11 )
        goto LABEL_42;
      v23 = fileno(Stream);
      v24 = v22;
      v19 = Destination;
      LODWORD(v18) = read(v23, Destination, v24);
      if ( !(_DWORD)v18 )
      {
        Stream->_flag |= 0x10u;
        return (v10 - v12) / ElementSize;
      }
      if ( (_DWORD)v18 == -1 )
      {
        Stream->_flag |= 0x20u;
        return (v10 - v12) / ElementSize;
      }
      v18 = (unsigned int)v18;
      v12 -= (unsigned int)v18;
      goto LABEL_24;
    }
    v25 = filbuf(Stream);
    if ( v25 == -1 )
      return (v10 - v12) / ElementSize;
    if ( !v28 )
    {
LABEL_42:
      if ( BufferSize != -1 )
        memset_thunk_772440563353939046(Buffer, 0, BufferSize);
      *errno() = 34;
      invalid_parameter(0, 0, 0, 0, 0);
    }
    *v13 = v25;
    --v12;
    bufsiz = Stream->_bufsiz;
    ++v13;
    v11 = v28 - 1;
    v26 = bufsiz;
LABEL_41:
    Destination = v13;
    v15 = v12 == 0;
    v28 = v11;
  }
  return ElementCount;
}

```

## disassembly

```asm
0x1800513d8  mov     [rsp+arg_18], rbx
0x1800513dd  push    rbp
0x1800513de  push    rsi
0x1800513df  push    rdi
0x1800513e0  push    r12
0x1800513e2  push    r13
0x1800513e4  push    r14
0x1800513e6  push    r15
0x1800513e8  sub     rsp, 30h
0x1800513ec  xor     ebx, ebx
0x1800513ee  mov     r13, r9
0x1800513f1  mov     r14, r8
0x1800513f4  mov     rbp, rdx
0x1800513f7  mov     r12, rcx
0x1800513fa  test    r8, r8
0x1800513fd  jz      short loc_180051428
0x1800513ff  test    r9, r9
0x180051402  jz      short loc_180051428
0x180051404  test    rcx, rcx
0x180051407  jnz     short loc_180051442
0x180051409  call    _errno
0x18005140e  mov     [rsp+68h+Reserved], rbx; Reserved
0x180051413  mov     dword ptr [rax], 16h
0x180051419  xor     r9d, r9d; LineNo
0x18005141c  xor     r8d, r8d; FileName
0x18005141f  xor     edx, edx; FunctionName
0x180051421  xor     ecx, ecx; Expression
0x180051423  call    _invalid_parameter
0x180051428  xor     eax, eax
0x18005142a  mov     rbx, [rsp+68h+arg_18]
0x180051432  add     rsp, 30h
0x180051436  pop     r15
0x180051438  pop     r14
0x18005143a  pop     r13
0x18005143c  pop     r12
0x18005143e  pop     rdi
0x18005143f  pop     rsi
0x180051440  pop     rbp
0x180051441  retn
0x180051442  mov     rdi, [rsp+68h+Stream]
0x18005144a  test    rdi, rdi
0x18005144d  jz      short loc_18005145D
0x18005144f  xor     edx, edx
0x180051451  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051455  div     r14
0x180051458  cmp     r13, rax
0x18005145b  jbe     short loc_180051480
0x18005145d  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180051461  jz      short loc_18005146D
0x180051463  mov     r8, rbp; Size
0x180051466  xor     edx, edx; Val
0x180051468  call    memset$thunk$772440563353939046
0x18005146d  test    rdi, rdi
0x180051470  jz      short loc_180051409
0x180051472  xor     edx, edx
0x180051474  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051478  div     r14
0x18005147b  cmp     r13, rax
0x18005147e  ja      short loc_180051409
0x180051480  mov     rbx, r14
0x180051483  mov     [rsp+68h+Destination], r12
0x180051488  imul    rbx, r13
0x18005148c  test    dword ptr [rdi+18h], 10Ch
0x180051493  mov     rcx, rbp
0x180051496  mov     rsi, rbx
0x180051499  mov     [rsp+68h+arg_10], rcx
0x1800514a1  mov     r15, r12
0x1800514a4  jz      short loc_1800514AC
0x1800514a6  mov     r9d, [rdi+24h]
0x1800514aa  jmp     short loc_1800514B2
0x1800514ac  mov     r9d, 1000h
0x1800514b2  mov     [rsp+68h+arg_0], r9d
0x1800514b7  test    rbx, rbx
0x1800514ba  jz      loc_180051638
0x1800514c0  mov     eax, [rdi+18h]
0x1800514c3  mov     r10d, 7FFFFFFFh
0x1800514c9  test    eax, 10Ch
0x1800514ce  jz      short loc_180051532
0x1800514d0  movsxd  r15, dword ptr [rdi+8]
0x1800514d4  test    r15d, r15d
0x1800514d7  jz      short loc_18005152D
0x1800514d9  js      loc_180051616
0x1800514df  cmp     rsi, r15
0x1800514e2  jnb     short loc_1800514E7
0x1800514e4  mov     r15d, esi
0x1800514e7  mov     r9d, r15d; SourceSize
0x1800514ea  cmp     r9, rcx
0x1800514ed  ja      loc_1800515EA
0x1800514f3  mov     r8, [rdi]; Source
0x1800514f6  mov     rdx, rcx; DestinationSize
0x1800514f9  mov     rcx, [rsp+68h+Destination]; Destination
0x1800514fe  call    memcpy_s
0x180051503  sub     [rdi+8], r15d
0x180051507  mov     eax, r15d
0x18005150a  mov     r15, [rsp+68h+Destination]
0x18005150f  sub     rsi, rax
0x180051512  add     [rdi], rax
0x180051515  mov     rcx, [rsp+68h+arg_10]
0x18005151d  add     r15, rax
0x180051520  mov     r9d, [rsp+68h+arg_0]
0x180051525  sub     rcx, rax
0x180051528  jmp     loc_1800515D5
0x18005152d  mov     r15, [rsp+68h+Destination]
0x180051532  mov     r8d, r9d
0x180051535  cmp     rsi, r8
0x180051538  jb      short loc_1800515A6
0x18005153a  test    r9d, r9d
0x18005153d  jz      short loc_18005155F
0x18005153f  xor     edx, edx
0x180051541  cmp     rsi, r10
0x180051544  jbe     short loc_180051551
0x180051546  mov     eax, r10d
0x180051549  mov     r15d, r10d
0x18005154c  div     r9d
0x18005154f  jmp     short loc_18005155A
0x180051551  mov     rax, rsi
0x180051554  mov     r15d, esi
0x180051557  div     r8
0x18005155a  sub     r15d, edx
0x18005155d  jmp     short loc_180051569
0x18005155f  cmp     rsi, r10
0x180051562  mov     r15d, esi
0x180051565  cmova   r15d, r10d
0x180051569  mov     eax, r15d
0x18005156c  cmp     rax, rcx
0x18005156f  ja      short loc_1800515EA
0x180051571  mov     rcx, rdi; Stream
0x180051574  call    _fileno
0x180051579  mov     r8d, r15d; MaxCharCount
0x18005157c  mov     ecx, eax; FileHandle
0x18005157e  mov     r15, [rsp+68h+Destination]
0x180051583  mov     rdx, r15; DstBuf
0x180051586  call    _read
0x18005158b  test    eax, eax
0x18005158d  jz      loc_180051632
0x180051593  cmp     eax, 0FFFFFFFFh
0x180051596  jz      loc_18005162C
0x18005159c  mov     eax, eax
0x18005159e  sub     rsi, rax
0x1800515a1  jmp     loc_180051515
0x1800515a6  mov     rcx, rdi; File
0x1800515a9  call    _filbuf
0x1800515ae  cmp     eax, 0FFFFFFFFh
0x1800515b1  jz      short loc_18005161C
0x1800515b3  mov     rcx, [rsp+68h+arg_10]
0x1800515bb  test    rcx, rcx
0x1800515be  jz      short loc_1800515EA
0x1800515c0  mov     [r15], al
0x1800515c3  dec     rsi
0x1800515c6  mov     r9d, [rdi+24h]
0x1800515ca  inc     r15
0x1800515cd  dec     rcx
0x1800515d0  mov     [rsp+68h+arg_0], r9d
0x1800515d5  mov     [rsp+68h+Destination], r15
0x1800515da  test    rsi, rsi
0x1800515dd  mov     [rsp+68h+arg_10], rcx
0x1800515e5  jmp     loc_1800514BA
0x1800515ea  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800515ee  jz      short loc_1800515FD
0x1800515f0  mov     r8, rbp; Size
0x1800515f3  xor     edx, edx; Val
0x1800515f5  mov     rcx, r12; void *
0x1800515f8  call    memset$thunk$772440563353939046
0x1800515fd  call    _errno
0x180051602  mov     [rsp+68h+Reserved], 0
0x18005160b  mov     dword ptr [rax], 22h ; '"'
0x180051611  jmp     loc_180051419
0x180051616  or      eax, 20h
0x180051619  mov     [rdi+18h], eax
0x18005161c  sub     rbx, rsi
0x18005161f  xor     edx, edx
0x180051621  mov     rax, rbx
0x180051624  div     r14
0x180051627  jmp     loc_18005142A
0x18005162c  or      dword ptr [rdi+18h], 20h
0x180051630  jmp     short loc_18005161C
0x180051632  or      dword ptr [rdi+18h], 10h
0x180051636  jmp     short loc_18005161C
0x180051638  mov     rax, r13
0x18005163b  jmp     loc_18005142A
```
