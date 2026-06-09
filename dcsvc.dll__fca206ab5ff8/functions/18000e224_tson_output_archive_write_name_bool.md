# tson::output_archive::write_name(bool)

- ea: `0x18000e224`
- end: `0x18000e430`
- name: `?write_name@output_archive@tson@@AEAA_N_N@Z`
- size: `524`
- prototype: `char __fastcall(tson::output_archive *this, char)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ae80`
- `0x18000af44`
- `0x18000afdc`
- `0x18000b070`
- `0x18000b104`
- `0x18000b194`
- `0x18000d260`
- `0x18000d8fc`
- `0x18000dbb0`
- `0x18000dce4`

## callees

- `0x18000d0b0`
- `0x18000d160`
- `0x18000e224`

## pseudocode

```c
char __fastcall tson::output_archive::write_name(tson::output_archive *this, char a2)
{
  char *v2; // rsi
  __int64 v4; // rax
  __int64 v6; // rbx
  __int64 v7; // rbx
  tson::write_buffer *v8; // rbx
  char *v10; // rsi
  tson::write_buffer **v11; // r14
  tson::write_buffer *v12; // rbx
  tson::write_buffer **v13; // rbp
  char *v14; // r15
  tson::write_buffer *v15; // rbx
  char v16; // cl

  v2 = (char *)this + 24;
  v4 = *((_QWORD *)this + 16);
  if ( v4 )
    v2 = &v2[4 * v4 - 4];
  else
    *v2 = 1;
  if ( *((_DWORD *)v2 + 1) == 2 )
  {
    *((_DWORD *)v2 + 1) = 3;
    v6 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v6 + 2072) < *(_QWORD *)(v6 + 2080)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v6 + 2072))++ = 3;
    }
    tson::write_buffer::push_back(*((tson::write_buffer **)this + 18), (char *)this + 10, 2u);
    *((_WORD *)this + 5) = 0;
  }
  else if ( !*((_DWORD *)v2 + 1) )
  {
    *((_DWORD *)v2 + 1) = 1;
    v7 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v7 + 2072) < *(_QWORD *)(v7 + 2080)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v7 + 2072))++ = 1;
    }
  }
  *((_QWORD *)this + 2) = 0;
  if ( *((_DWORD *)v2 + 1) == 3 )
    return 1;
  if ( !a2 )
  {
    v10 = (char *)this + 8;
    if ( !*(_QWORD *)this )
    {
      *v10 = 1;
      *(_QWORD *)this = "-";
    }
    v11 = (tson::write_buffer **)((char *)this + 144);
    v12 = (tson::write_buffer *)*((_QWORD *)this + 18);
    *((_QWORD *)this + 2) = *((_QWORD *)v12 + 259) - *((_QWORD *)v12 + 258);
    if ( *((_QWORD *)v12 + 259) < *((_QWORD *)v12 + 260) || tson::write_buffer::reserve(v12, 1u) )
    {
      v14 = (char *)this + 8;
      v13 = (tson::write_buffer **)((char *)this + 144);
      *(_BYTE *)(*((_QWORD *)v12 + 259))++ = 5;
    }
    else
    {
      v13 = (tson::write_buffer **)((char *)this + 144);
      v14 = (char *)this + 8;
    }
    v15 = *v11;
    if ( *((_QWORD *)*v11 + 259) < *((_QWORD *)*v11 + 260) || tson::write_buffer::reserve(*v11, 1u) )
    {
      v16 = *v10;
      v11 = v13;
      v10 = v14;
      *(_BYTE *)(*((_QWORD *)v15 + 259))++ = v16;
    }
    tson::write_buffer::push_back(*v11, *(const void **)this, (unsigned __int8)*v10);
    *(_QWORD *)this = 0;
    return 1;
  }
  v8 = (tson::write_buffer *)*((_QWORD *)this + 18);
  *(_QWORD *)this = 0;
  if ( *((_QWORD *)v8 + 259) < *((_QWORD *)v8 + 260) || tson::write_buffer::reserve(v8, 1u) )
    *(_BYTE *)(*((_QWORD *)v8 + 259))++ = 6;
  return 0;
}

```

## disassembly

```asm
0x18000e224  push    rbx
0x18000e226  push    rbp
0x18000e227  push    rsi
0x18000e228  push    rdi
0x18000e229  push    r12
0x18000e22b  push    r14
0x18000e22d  push    r15
0x18000e22f  sub     rsp, 20h
0x18000e233  lea     rsi, [rcx+18h]
0x18000e237  mov     bpl, dl
0x18000e23a  mov     rax, [rsi+68h]
0x18000e23e  mov     rdi, rcx
0x18000e241  mov     r12d, 1
0x18000e247  test    rax, rax
0x18000e24a  jz      short loc_18000E256
0x18000e24c  lea     rsi, [rsi+rax*4]
0x18000e250  add     rsi, 0FFFFFFFFFFFFFFFCh
0x18000e254  jmp     short loc_18000E259
0x18000e256  mov     [rsi], r12b
0x18000e259  cmp     dword ptr [rsi+4], 2
0x18000e25d  jnz     short loc_18000E2BB
0x18000e25f  mov     dword ptr [rsi+4], 3
0x18000e266  mov     rbx, [rcx+90h]
0x18000e26d  mov     rax, [rbx+820h]
0x18000e274  cmp     [rbx+818h], rax
0x18000e27b  jb      short loc_18000E28C
0x18000e27d  mov     rdx, r12; unsigned __int64
0x18000e280  mov     rcx, rbx; this
0x18000e283  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000e288  test    al, al
0x18000e28a  jz      short loc_18000E29D
0x18000e28c  mov     rax, [rbx+818h]
0x18000e293  mov     byte ptr [rax], 3
0x18000e296  add     [rbx+818h], r12
0x18000e29d  mov     rcx, [rdi+90h]; this
0x18000e2a4  lea     rdx, [rdi+0Ah]; void *
0x18000e2a8  mov     r8d, 2; unsigned __int64
0x18000e2ae  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x18000e2b3  xor     eax, eax
0x18000e2b5  mov     [rdi+0Ah], ax
0x18000e2b9  jmp     short loc_18000E2FC
0x18000e2bb  cmp     dword ptr [rsi+4], 0
0x18000e2bf  jnz     short loc_18000E2FC
0x18000e2c1  mov     [rsi+4], r12d
0x18000e2c5  mov     rbx, [rcx+90h]
0x18000e2cc  mov     rax, [rbx+820h]
0x18000e2d3  cmp     [rbx+818h], rax
0x18000e2da  jb      short loc_18000E2EB
0x18000e2dc  mov     rdx, r12; unsigned __int64
0x18000e2df  mov     rcx, rbx; this
0x18000e2e2  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000e2e7  test    al, al
0x18000e2e9  jz      short loc_18000E2FC
0x18000e2eb  mov     rax, [rbx+818h]
0x18000e2f2  mov     [rax], r12b
0x18000e2f5  add     [rbx+818h], r12
0x18000e2fc  mov     qword ptr [rdi+10h], 0
0x18000e304  cmp     dword ptr [rsi+4], 3
0x18000e308  jz      loc_18000E41E
0x18000e30e  test    bpl, bpl
0x18000e311  jz      short loc_18000E358
0x18000e313  mov     rbx, [rdi+90h]
0x18000e31a  mov     qword ptr [rdi], 0
0x18000e321  mov     rax, [rbx+820h]
0x18000e328  cmp     [rbx+818h], rax
0x18000e32f  jb      short loc_18000E340
0x18000e331  mov     rdx, r12; unsigned __int64
0x18000e334  mov     rcx, rbx; this
0x18000e337  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000e33c  test    al, al
0x18000e33e  jz      short loc_18000E351
0x18000e340  mov     rax, [rbx+818h]
0x18000e347  mov     byte ptr [rax], 6
0x18000e34a  add     [rbx+818h], r12
0x18000e351  xor     al, al
0x18000e353  jmp     loc_18000E421
0x18000e358  cmp     qword ptr [rdi], 0
0x18000e35c  lea     rsi, [rdi+8]
0x18000e360  jnz     short loc_18000E36F
0x18000e362  lea     rax, asc_180016378; "-"
0x18000e369  mov     [rsi], r12b
0x18000e36c  mov     [rdi], rax
0x18000e36f  lea     r14, [rdi+90h]
0x18000e376  mov     rbx, [r14]
0x18000e379  mov     rax, [rbx+818h]
0x18000e380  sub     rax, [rbx+810h]
0x18000e387  mov     [rdi+10h], rax
0x18000e38b  mov     rax, [rbx+820h]
0x18000e392  cmp     [rbx+818h], rax
0x18000e399  jb      short loc_18000E3B2
0x18000e39b  mov     rdx, r12; unsigned __int64
0x18000e39e  mov     rcx, rbx; this
0x18000e3a1  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000e3a6  test    al, al
0x18000e3a8  jnz     short loc_18000E3B2
0x18000e3aa  mov     rbp, r14
0x18000e3ad  mov     r15, rsi
0x18000e3b0  jmp     short loc_18000E3CE
0x18000e3b2  mov     rax, [rbx+818h]
0x18000e3b9  lea     r15, [rdi+8]
0x18000e3bd  lea     rbp, [rdi+90h]
0x18000e3c4  mov     byte ptr [rax], 5
0x18000e3c7  add     [rbx+818h], r12
0x18000e3ce  mov     rbx, [r14]
0x18000e3d1  mov     rax, [rbx+820h]
0x18000e3d8  cmp     [rbx+818h], rax
0x18000e3df  jb      short loc_18000E3F0
0x18000e3e1  mov     rdx, r12; unsigned __int64
0x18000e3e4  mov     rcx, rbx; this
0x18000e3e7  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000e3ec  test    al, al
0x18000e3ee  jz      short loc_18000E408
0x18000e3f0  mov     cl, [rsi]
0x18000e3f2  mov     r14, rbp
0x18000e3f5  mov     rdx, [rbx+818h]
0x18000e3fc  mov     rsi, r15
0x18000e3ff  mov     [rdx], cl
0x18000e401  add     [rbx+818h], r12
0x18000e408  movzx   r8d, byte ptr [rsi]; unsigned __int64
0x18000e40c  mov     rdx, [rdi]; void *
0x18000e40f  mov     rcx, [r14]; this
0x18000e412  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x18000e417  mov     qword ptr [rdi], 0
0x18000e41e  mov     al, r12b
0x18000e421  add     rsp, 20h
0x18000e425  pop     r15
0x18000e427  pop     r14
0x18000e429  pop     r12
0x18000e42b  pop     rdi
0x18000e42c  pop     rsi
0x18000e42d  pop     rbp
0x18000e42e  pop     rbx
0x18000e42f  retn
```
