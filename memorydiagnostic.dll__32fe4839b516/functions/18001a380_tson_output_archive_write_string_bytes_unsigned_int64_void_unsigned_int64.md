# tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)

- ea: `0x18001a380`
- end: `0x18001a4c3`
- name: `?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z`
- size: `323`
- prototype: `void(tson::output_archive *__hidden this, unsigned __int64, void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800038f0`
- `0x1800189d0`

## callees

- `0x180018458`
- `0x18001873c`
- `0x18001a380`

## pseudocode

```c
void __fastcall tson::output_archive::write_string_bytes(tson::output_archive *this, __int64 a2, void *a3, rsize_t a4)
{
  unsigned __int64 v4; // rsi
  tson::write_buffer **v7; // r14
  tson::write_buffer *v8; // rbx
  char v9; // bp
  __int16 v10; // si
  __int64 v11; // rbp
  tson::write_buffer **v12; // r15

  v4 = a2 + 1;
  if ( (unsigned __int64)(a2 + 1) > 0x7F )
  {
    if ( v4 > 0x7FFF && *((int *)this + 34) >= 0 )
      *((_DWORD *)this + 34) = -2147483637;
    v10 = v4 | 0x8000;
    v7 = (tson::write_buffer **)((char *)this + 144);
    v11 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v11 + 2072) < *(_QWORD *)(v11 + 2080)
      || (v12 = (tson::write_buffer **)((char *)this + 144),
          tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u)) )
    {
      v12 = (tson::write_buffer **)((char *)this + 144);
      *(_BYTE *)(*(_QWORD *)(v11 + 2072))++ = HIBYTE(v10);
    }
    v8 = *v7;
    if ( *((_QWORD *)*v7 + 259) < *((_QWORD *)*v7 + 260) || tson::write_buffer::reserve(*v7, 1u) )
    {
      v7 = v12;
      **((_BYTE **)v8 + 259) = v10;
      goto LABEL_14;
    }
  }
  else
  {
    v7 = (tson::write_buffer **)((char *)this + 144);
    v8 = (tson::write_buffer *)*((_QWORD *)this + 18);
    v9 = a3 != 0 ? v4 : 0;
    if ( *((_QWORD *)v8 + 259) < *((_QWORD *)v8 + 260)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      **((_BYTE **)v8 + 259) = v9;
LABEL_14:
      ++*((_QWORD *)v8 + 259);
    }
  }
  tson::write_buffer::push_back((void **)*v7, a3, a4);
}

```

## disassembly

```asm
0x18001a380  mov     [rsp+arg_0], rbx
0x18001a385  mov     [rsp+arg_8], rbp
0x18001a38a  mov     [rsp+arg_18], r9
0x18001a38f  push    rsi
0x18001a390  push    r12
0x18001a392  push    r13
0x18001a394  push    r14
0x18001a396  push    r15
0x18001a398  sub     rsp, 20h
0x18001a39c  lea     rsi, [rdx+1]
0x18001a3a0  mov     r13, r8
0x18001a3a3  mov     rbx, rcx
0x18001a3a6  cmp     rsi, 7Fh
0x18001a3aa  ja      short loc_18001A3F6
0x18001a3ac  mov     rax, r8
0x18001a3af  lea     r14, [rcx+90h]
0x18001a3b6  mov     rbx, [r14]
0x18001a3b9  neg     rax
0x18001a3bc  sbb     bpl, bpl
0x18001a3bf  and     bpl, sil
0x18001a3c2  mov     rax, [rbx+820h]
0x18001a3c9  cmp     [rbx+818h], rax
0x18001a3d0  jb      short loc_18001A3E7
0x18001a3d2  mov     edx, 1; unsigned __int64
0x18001a3d7  mov     rcx, rbx; this
0x18001a3da  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001a3df  test    al, al
0x18001a3e1  jz      loc_18001A49C
0x18001a3e7  mov     rax, [rbx+818h]
0x18001a3ee  mov     [rax], bpl
0x18001a3f1  jmp     loc_18001A495
0x18001a3f6  cmp     rsi, 7FFFh
0x18001a3fd  jbe     short loc_18001A412
0x18001a3ff  cmp     dword ptr [rcx+88h], 0
0x18001a406  jl      short loc_18001A412
0x18001a408  mov     dword ptr [rcx+88h], 8000000Bh
0x18001a412  bts     rsi, 0Fh
0x18001a417  lea     r14, [rcx+90h]
0x18001a41e  mov     rbp, [r14]
0x18001a421  mov     r12, rsi
0x18001a424  shr     r12, 8
0x18001a428  mov     rax, [rbp+820h]
0x18001a42f  cmp     [rbp+818h], rax
0x18001a436  jb      short loc_18001A44C
0x18001a438  mov     edx, 1; unsigned __int64
0x18001a43d  mov     rcx, rbp; this
0x18001a440  mov     r15, r14
0x18001a443  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001a448  test    al, al
0x18001a44a  jz      short loc_18001A464
0x18001a44c  mov     rax, [rbp+818h]
0x18001a453  lea     r15, [rbx+90h]
0x18001a45a  mov     [rax], r12b
0x18001a45d  inc     qword ptr [rbp+818h]
0x18001a464  mov     rbx, [r14]
0x18001a467  mov     rax, [rbx+820h]
0x18001a46e  cmp     [rbx+818h], rax
0x18001a475  jb      short loc_18001A488
0x18001a477  mov     edx, 1; unsigned __int64
0x18001a47c  mov     rcx, rbx; this
0x18001a47f  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001a484  test    al, al
0x18001a486  jz      short loc_18001A49C
0x18001a488  mov     rax, [rbx+818h]
0x18001a48f  mov     r14, r15
0x18001a492  mov     [rax], sil
0x18001a495  inc     qword ptr [rbx+818h]
0x18001a49c  mov     r8, [rsp+48h+arg_18]; unsigned __int64
0x18001a4a1  mov     rdx, r13; void *
0x18001a4a4  mov     rcx, [r14]; this
0x18001a4a7  mov     rbx, [rsp+48h+arg_0]
0x18001a4ac  mov     rbp, [rsp+48h+arg_8]
0x18001a4b1  add     rsp, 20h
0x18001a4b5  pop     r15
0x18001a4b7  pop     r14
0x18001a4b9  pop     r13
0x18001a4bb  pop     r12
0x18001a4bd  pop     rsi
0x18001a4be  jmp     ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
```
