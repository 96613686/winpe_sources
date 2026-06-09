# tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)

- ea: `0x18001951c`
- end: `0x180019637`
- name: `?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z`
- size: `283`
- prototype: `void __fastcall(tson::output_archive *this, __int64, void *, rsize_t)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800041cc`
- `0x1800067d4`
- `0x180006954`
- `0x1800179fc`
- `0x18001807c`

## callees

- `0x180017780`
- `0x180017944`
- `0x18001951c`

## pseudocode

```c
void __fastcall tson::output_archive::write_string_bytes(tson::output_archive *this, __int64 a2, void *a3, rsize_t a4)
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
  tson::write_buffer::push_back((void **)*v7, a3, a4);
}

```

## disassembly

```asm
0x18001951c  push    rbx
0x18001951e  push    rbp
0x18001951f  push    rdi
0x180019520  push    r12
0x180019522  push    r14
0x180019524  push    r15
0x180019526  sub     rsp, 28h
0x18001952a  lea     rdi, [rdx+1]
0x18001952e  mov     r12, r9
0x180019531  mov     r15, r8
0x180019534  cmp     rdi, 7Fh
0x180019538  ja      short loc_180019584
0x18001953a  mov     rax, r8
0x18001953d  lea     r14, [rcx+90h]
0x180019544  mov     rbx, [r14]
0x180019547  neg     rax
0x18001954a  sbb     bpl, bpl
0x18001954d  and     bpl, dil
0x180019550  mov     rax, [rbx+820h]
0x180019557  cmp     [rbx+818h], rax
0x18001955e  jb      short loc_180019575
0x180019560  mov     edx, 1; unsigned __int64
0x180019565  mov     rcx, rbx; this
0x180019568  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001956d  test    al, al
0x18001956f  jz      loc_18001961C
0x180019575  mov     rax, [rbx+818h]
0x18001957c  mov     [rax], bpl
0x18001957f  jmp     loc_180019615
0x180019584  cmp     rdi, 7FFFh
0x18001958b  jbe     short loc_1800195A0
0x18001958d  cmp     dword ptr [rcx+88h], 0
0x180019594  jl      short loc_1800195A0
0x180019596  mov     dword ptr [rcx+88h], 8000000Bh
0x1800195a0  lea     r14, [rcx+90h]
0x1800195a7  bts     rdi, 0Fh
0x1800195ac  mov     rbx, [r14]
0x1800195af  mov     rax, [rbx+820h]
0x1800195b6  cmp     [rbx+818h], rax
0x1800195bd  jb      short loc_1800195D0
0x1800195bf  mov     edx, 1; unsigned __int64
0x1800195c4  mov     rcx, rbx; this
0x1800195c7  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800195cc  test    al, al
0x1800195ce  jz      short loc_1800195E7
0x1800195d0  mov     rax, [rbx+818h]
0x1800195d7  mov     rcx, rdi
0x1800195da  shr     rcx, 8
0x1800195de  mov     [rax], cl
0x1800195e0  inc     qword ptr [rbx+818h]
0x1800195e7  mov     rbx, [r14]
0x1800195ea  mov     rax, [rbx+820h]
0x1800195f1  cmp     [rbx+818h], rax
0x1800195f8  jb      short loc_18001960B
0x1800195fa  mov     edx, 1; unsigned __int64
0x1800195ff  mov     rcx, rbx; this
0x180019602  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180019607  test    al, al
0x180019609  jz      short loc_18001961C
0x18001960b  mov     rax, [rbx+818h]
0x180019612  mov     [rax], dil
0x180019615  inc     qword ptr [rbx+818h]
0x18001961c  mov     rcx, [r14]; this
0x18001961f  mov     r8, r12; unsigned __int64
0x180019622  mov     rdx, r15; void *
0x180019625  add     rsp, 28h
0x180019629  pop     r15
0x18001962b  pop     r14
0x18001962d  pop     r12
0x18001962f  pop     rdi
0x180019630  pop     rbp
0x180019631  pop     rbx
0x180019632  jmp     ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
```
