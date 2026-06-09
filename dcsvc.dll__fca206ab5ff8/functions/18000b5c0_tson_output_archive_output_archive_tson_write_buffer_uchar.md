# tson::output_archive::output_archive(tson::write_buffer &,uchar)

- ea: `0x18000b5c0`
- end: `0x18000b6aa`
- name: `??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z`
- size: `234`
- prototype: `tson::output_archive *__fastcall(tson::output_archive *this, struct tson::write_buffer *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dce4`

## callees

- `0x1800026c8`
- `0x18000b5c0`
- `0x18000d160`

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
0x18000b5c0  push    rbx
0x18000b5c2  push    rbp
0x18000b5c3  push    rsi
0x18000b5c4  push    rdi
0x18000b5c5  sub     rsp, 28h
0x18000b5c9  xor     eax, eax
0x18000b5cb  mov     qword ptr [rcx], 0
0x18000b5d2  mov     sil, r8b
0x18000b5d5  mov     byte ptr [rcx+8], 0
0x18000b5d9  mov     rdi, rdx
0x18000b5dc  mov     [rcx+0Ah], ax
0x18000b5e0  mov     rbx, rcx
0x18000b5e3  mov     [rcx+10h], rax
0x18000b5e7  mov     [rcx+18h], al
0x18000b5ea  lea     r8d, [rax+64h]; Size
0x18000b5ee  add     rcx, 1Ch; void *
0x18000b5f2  xor     edx, edx; Val
0x18000b5f4  call    memset_0
0x18000b5f9  mov     qword ptr [rbx+80h], 0
0x18000b604  mov     ebp, 1
0x18000b609  mov     dword ptr [rbx+88h], 0
0x18000b613  mov     [rbx+90h], rdi
0x18000b61a  mov     rax, [rdi+820h]
0x18000b621  cmp     [rdi+818h], rax
0x18000b628  jb      short loc_18000B638
0x18000b62a  mov     edx, ebp; unsigned __int64
0x18000b62c  mov     rcx, rdi; this
0x18000b62f  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000b634  test    al, al
0x18000b636  jz      short loc_18000B649
0x18000b638  mov     rax, [rdi+818h]
0x18000b63f  mov     byte ptr [rax], 80h
0x18000b642  add     [rdi+818h], rbp
0x18000b649  mov     rdi, [rbx+90h]
0x18000b650  mov     rax, [rdi+820h]
0x18000b657  cmp     [rdi+818h], rax
0x18000b65e  jb      short loc_18000B66F
0x18000b660  mov     rdx, rbp; unsigned __int64
0x18000b663  mov     rcx, rdi; this
0x18000b666  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000b66b  test    al, al
0x18000b66d  jz      short loc_18000B680
0x18000b66f  mov     rax, [rdi+818h]
0x18000b676  mov     [rax], sil
0x18000b679  add     [rdi+818h], rbp
0x18000b680  mov     rax, [rbx+80h]
0x18000b687  cmp     rax, 19h
0x18000b68b  jnb     short loc_18000B69A
0x18000b68d  mov     [rbx+rax*4+1Ch], ebp
0x18000b691  add     [rbx+80h], rbp
0x18000b698  jmp     short loc_18000B69E
0x18000b69a  mov     [rbx+18h], bpl
0x18000b69e  mov     rax, rbx
0x18000b6a1  add     rsp, 28h
0x18000b6a5  pop     rdi
0x18000b6a6  pop     rsi
0x18000b6a7  pop     rbp
0x18000b6a8  pop     rbx
0x18000b6a9  retn
```
