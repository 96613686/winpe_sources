# tson::output_archive::output_archive(tson::write_buffer &,uchar)

- ea: `0x180007494`
- end: `0x1800075a7`
- name: `??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z`
- size: `275`
- prototype: `_QWORD(tson::output_archive *__hidden this, struct tson::write_buffer *, unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180019660`
- `0x180019820`

## callees

- `0x180003374`
- `0x180007494`
- `0x18001873c`

## pseudocode

```c
tson::output_archive *__fastcall tson::output_archive::output_archive(
        tson::output_archive *this,
        struct tson::write_buffer *a2,
        char a3)
{
  char *v3; // rbx
  char *v7; // rbp
  __int64 v8; // rdi
  unsigned __int64 v9; // rax

  v3 = (char *)this + 24;
  *(_QWORD *)this = 0;
  *((_BYTE *)this + 8) = 0;
  *((_WORD *)this + 5) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 24) = 0;
  memset_0((char *)this + 28, 0, 0x64u);
  *((_QWORD *)v3 + 13) = 0;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 18) = a2;
  if ( *((_QWORD *)a2 + 259) < *((_QWORD *)a2 + 260) || (v7 = v3, tson::write_buffer::reserve(a2, 1u)) )
  {
    v7 = (char *)this + 24;
    *(_BYTE *)(*((_QWORD *)a2 + 259))++ = 0x80;
  }
  v8 = *((_QWORD *)this + 18);
  if ( *(_QWORD *)(v8 + 2072) < *(_QWORD *)(v8 + 2080)
    || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
  {
    v3 = v7;
    *(_BYTE *)(*(_QWORD *)(v8 + 2072))++ = a3;
  }
  v9 = *((_QWORD *)v3 + 13);
  if ( v9 >= 0x19 )
  {
    *v3 = 1;
  }
  else
  {
    *(_DWORD *)&v3[4 * v9 + 4] = 1;
    ++*((_QWORD *)v3 + 13);
  }
  return this;
}

```

## disassembly

```asm
0x180007494  mov     rax, rsp
0x180007497  mov     [rax+8], rbx
0x18000749b  mov     [rax+10h], rbp
0x18000749f  mov     [rax+18h], rsi
0x1800074a3  mov     [rax+20h], rdi
0x1800074a7  push    r12
0x1800074a9  push    r14
0x1800074ab  push    r15
0x1800074ad  sub     rsp, 20h
0x1800074b1  xor     r12d, r12d
0x1800074b4  lea     rbx, [rcx+18h]
0x1800074b8  mov     r14b, r8b
0x1800074bb  mov     [rcx], r12
0x1800074be  mov     rdi, rdx
0x1800074c1  mov     [rcx+8], r12b
0x1800074c5  mov     rsi, rcx
0x1800074c8  mov     [rcx+0Ah], r12w
0x1800074cd  mov     [rcx+10h], r12
0x1800074d1  lea     r8d, [r12+64h]; Size
0x1800074d6  lea     rcx, [rbx+4]; void *
0x1800074da  mov     [rbx], r12b
0x1800074dd  xor     edx, edx; Val
0x1800074df  call    memset_0
0x1800074e4  mov     [rbx+68h], r12
0x1800074e8  lea     r15d, [r12+1]
0x1800074ed  mov     [rsi+88h], r12d
0x1800074f4  mov     [rsi+90h], rdi
0x1800074fb  mov     rax, [rdi+820h]
0x180007502  cmp     [rdi+818h], rax
0x180007509  jb      short loc_18000751D
0x18000750b  mov     edx, r15d; unsigned __int64
0x18000750e  mov     rcx, rdi; this
0x180007511  mov     rbp, rbx
0x180007514  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180007519  test    al, al
0x18000751b  jz      short loc_180007532
0x18000751d  mov     rax, [rdi+818h]
0x180007524  lea     rbp, [rsi+18h]
0x180007528  mov     byte ptr [rax], 80h
0x18000752b  add     [rdi+818h], r15
0x180007532  mov     rdi, [rsi+90h]
0x180007539  mov     rax, [rdi+820h]
0x180007540  cmp     [rdi+818h], rax
0x180007547  jb      short loc_180007558
0x180007549  mov     rdx, r15; unsigned __int64
0x18000754c  mov     rcx, rdi; this
0x18000754f  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180007554  test    al, al
0x180007556  jz      short loc_18000756C
0x180007558  mov     rax, [rdi+818h]
0x18000755f  mov     rbx, rbp
0x180007562  mov     [rax], r14b
0x180007565  add     [rdi+818h], r15
0x18000756c  mov     rax, [rbx+68h]
0x180007570  cmp     rax, 19h
0x180007574  jnb     short loc_180007581
0x180007576  mov     [rbx+rax*4+4], r15d
0x18000757b  add     [rbx+68h], r15
0x18000757f  jmp     short loc_180007584
0x180007581  mov     [rbx], r15b
0x180007584  mov     rbx, [rsp+38h+arg_0]
0x180007589  mov     rax, rsi
0x18000758c  mov     rsi, [rsp+38h+arg_10]
0x180007591  mov     rbp, [rsp+38h+arg_8]
0x180007596  mov     rdi, [rsp+38h+arg_18]
0x18000759b  add     rsp, 20h
0x18000759f  pop     r15
0x1800075a1  pop     r14
0x1800075a3  pop     r12
0x1800075a5  retn
```
