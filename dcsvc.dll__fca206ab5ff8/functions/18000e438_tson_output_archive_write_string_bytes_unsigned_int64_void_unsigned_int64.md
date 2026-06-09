# tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)

- ea: `0x18000e438`
- end: `0x18000e553`
- name: `?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z`
- size: `283`
- prototype: `void __fastcall(tson::output_archive *this, __int64, void *, size_t)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b104`
- `0x18000b194`
- `0x18000d260`
- `0x18000d8fc`
- `0x18000dce4`

## callees

- `0x18000d0b0`
- `0x18000d160`
- `0x18000e438`

## pseudocode

```c
void __fastcall tson::output_archive::write_string_bytes(tson::output_archive *this, __int64 a2, void *a3, size_t a4)
{
  unsigned __int64 v4; // rdi
  tson::write_buffer **v7; // r14
  tson::write_buffer *v8; // rbx
  char v9; // bp
  __int16 v10; // di
  __int64 v11; // rbx

  v4 = a2 + 1;
  if ( (unsigned __int64)(a2 + 1) > 0x7F )
  {
    if ( v4 > 0x7FFF && *((int *)this + 34) >= 0 )
      *((_DWORD *)this + 34) = -2147483637;
    v7 = (tson::write_buffer **)((char *)this + 144);
    v10 = v4 | 0x8000;
    v11 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v11 + 2072) < *(_QWORD *)(v11 + 2080)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v11 + 2072))++ = HIBYTE(v10);
    }
    v8 = *v7;
    if ( *((_QWORD *)*v7 + 259) < *((_QWORD *)*v7 + 260) || tson::write_buffer::reserve(*v7, 1u) )
    {
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
  tson::write_buffer::push_back(*v7, a3, a4);
}

```

## disassembly

```asm
0x18000e438  push    rbx
0x18000e43a  push    rbp
0x18000e43b  push    rdi
0x18000e43c  push    r12
0x18000e43e  push    r14
0x18000e440  push    r15
0x18000e442  sub     rsp, 28h
0x18000e446  lea     rdi, [rdx+1]
0x18000e44a  mov     r12, r9
0x18000e44d  mov     r15, r8
0x18000e450  cmp     rdi, 7Fh
0x18000e454  ja      short loc_18000E4A0
0x18000e456  mov     rax, r8
0x18000e459  lea     r14, [rcx+90h]
0x18000e460  mov     rbx, [r14]
0x18000e463  neg     rax
0x18000e466  sbb     bpl, bpl
0x18000e469  and     bpl, dil
0x18000e46c  mov     rax, [rbx+820h]
0x18000e473  cmp     [rbx+818h], rax
0x18000e47a  jb      short loc_18000E491
0x18000e47c  mov     edx, 1; unsigned __int64
0x18000e481  mov     rcx, rbx; this
0x18000e484  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000e489  test    al, al
0x18000e48b  jz      loc_18000E538
0x18000e491  mov     rax, [rbx+818h]
0x18000e498  mov     [rax], bpl
0x18000e49b  jmp     loc_18000E531
0x18000e4a0  cmp     rdi, 7FFFh
0x18000e4a7  jbe     short loc_18000E4BC
0x18000e4a9  cmp     dword ptr [rcx+88h], 0
0x18000e4b0  jl      short loc_18000E4BC
0x18000e4b2  mov     dword ptr [rcx+88h], 8000000Bh
0x18000e4bc  lea     r14, [rcx+90h]
0x18000e4c3  bts     rdi, 0Fh
0x18000e4c8  mov     rbx, [r14]
0x18000e4cb  mov     rax, [rbx+820h]
0x18000e4d2  cmp     [rbx+818h], rax
0x18000e4d9  jb      short loc_18000E4EC
0x18000e4db  mov     edx, 1; unsigned __int64
0x18000e4e0  mov     rcx, rbx; this
0x18000e4e3  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000e4e8  test    al, al
0x18000e4ea  jz      short loc_18000E503
0x18000e4ec  mov     rax, [rbx+818h]
0x18000e4f3  mov     rcx, rdi
0x18000e4f6  shr     rcx, 8
0x18000e4fa  mov     [rax], cl
0x18000e4fc  inc     qword ptr [rbx+818h]
0x18000e503  mov     rbx, [r14]
0x18000e506  mov     rax, [rbx+820h]
0x18000e50d  cmp     [rbx+818h], rax
0x18000e514  jb      short loc_18000E527
0x18000e516  mov     edx, 1; unsigned __int64
0x18000e51b  mov     rcx, rbx; this
0x18000e51e  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000e523  test    al, al
0x18000e525  jz      short loc_18000E538
0x18000e527  mov     rax, [rbx+818h]
0x18000e52e  mov     [rax], dil
0x18000e531  inc     qword ptr [rbx+818h]
0x18000e538  mov     rcx, [r14]; this
0x18000e53b  mov     r8, r12; unsigned __int64
0x18000e53e  mov     rdx, r15; void *
0x18000e541  add     rsp, 28h
0x18000e545  pop     r15
0x18000e547  pop     r14
0x18000e549  pop     r12
0x18000e54b  pop     rdi
0x18000e54c  pop     rbp
0x18000e54d  pop     rbx
0x18000e54e  jmp     ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
```
