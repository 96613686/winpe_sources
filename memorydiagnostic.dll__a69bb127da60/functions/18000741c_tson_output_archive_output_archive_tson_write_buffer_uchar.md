# tson::output_archive::output_archive(tson::write_buffer &,uchar)

- ea: `0x18000741c`
- end: `0x180007506`
- name: `??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z`
- size: `234`
- prototype: `tson::output_archive *__fastcall(tson::output_archive *this, struct tson::write_buffer *, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180018680`
- `0x180018844`

## callees

- `0x180003940`
- `0x18000741c`
- `0x180017944`

## pseudocode

```c
tson::output_archive *__fastcall tson::output_archive::output_archive(
        tson::output_archive *this,
        struct tson::write_buffer *a2,
        char a3)
{
  __int64 v6; // rdi
  unsigned __int64 v7; // rax

  *(_QWORD *)this = 0;
  *((_BYTE *)this + 8) = 0;
  *((_WORD *)this + 5) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 24) = 0;
  memset_0((char *)this + 28, 0, 0x64u);
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 18) = a2;
  if ( *((_QWORD *)a2 + 259) < *((_QWORD *)a2 + 260) || tson::write_buffer::reserve(a2, 1u) )
    *(_BYTE *)(*((_QWORD *)a2 + 259))++ = 0x80;
  v6 = *((_QWORD *)this + 18);
  if ( *(_QWORD *)(v6 + 2072) < *(_QWORD *)(v6 + 2080)
    || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
  {
    *(_BYTE *)(*(_QWORD *)(v6 + 2072))++ = a3;
  }
  v7 = *((_QWORD *)this + 16);
  if ( v7 >= 0x19 )
  {
    *((_BYTE *)this + 24) = 1;
  }
  else
  {
    *((_DWORD *)this + v7 + 7) = 1;
    ++*((_QWORD *)this + 16);
  }
  return this;
}

```

## disassembly

```asm
0x18000741c  push    rbx
0x18000741e  push    rbp
0x18000741f  push    rsi
0x180007420  push    rdi
0x180007421  sub     rsp, 28h
0x180007425  xor     eax, eax
0x180007427  mov     qword ptr [rcx], 0
0x18000742e  mov     sil, r8b
0x180007431  mov     byte ptr [rcx+8], 0
0x180007435  mov     rdi, rdx
0x180007438  mov     [rcx+0Ah], ax
0x18000743c  mov     rbx, rcx
0x18000743f  mov     [rcx+10h], rax
0x180007443  mov     [rcx+18h], al
0x180007446  lea     r8d, [rax+64h]; Size
0x18000744a  add     rcx, 1Ch; void *
0x18000744e  xor     edx, edx; Val
0x180007450  call    memset_0
0x180007455  mov     qword ptr [rbx+80h], 0
0x180007460  mov     ebp, 1
0x180007465  mov     dword ptr [rbx+88h], 0
0x18000746f  mov     [rbx+90h], rdi
0x180007476  mov     rax, [rdi+820h]
0x18000747d  cmp     [rdi+818h], rax
0x180007484  jb      short loc_180007494
0x180007486  mov     edx, ebp; unsigned __int64
0x180007488  mov     rcx, rdi; this
0x18000748b  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180007490  test    al, al
0x180007492  jz      short loc_1800074A5
0x180007494  mov     rax, [rdi+818h]
0x18000749b  mov     byte ptr [rax], 80h
0x18000749e  add     [rdi+818h], rbp
0x1800074a5  mov     rdi, [rbx+90h]
0x1800074ac  mov     rax, [rdi+820h]
0x1800074b3  cmp     [rdi+818h], rax
0x1800074ba  jb      short loc_1800074CB
0x1800074bc  mov     rdx, rbp; unsigned __int64
0x1800074bf  mov     rcx, rdi; this
0x1800074c2  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800074c7  test    al, al
0x1800074c9  jz      short loc_1800074DC
0x1800074cb  mov     rax, [rdi+818h]
0x1800074d2  mov     [rax], sil
0x1800074d5  add     [rdi+818h], rbp
0x1800074dc  mov     rax, [rbx+80h]
0x1800074e3  cmp     rax, 19h
0x1800074e7  jnb     short loc_1800074F6
0x1800074e9  mov     [rbx+rax*4+1Ch], ebp
0x1800074ed  add     [rbx+80h], rbp
0x1800074f4  jmp     short loc_1800074FA
0x1800074f6  mov     [rbx+18h], bpl
0x1800074fa  mov     rax, rbx
0x1800074fd  add     rsp, 28h
0x180007501  pop     rdi
0x180007502  pop     rsi
0x180007503  pop     rbp
0x180007504  pop     rbx
0x180007505  retn
```
