# tson::output_archive::write_name(bool)

- ea: `0x18001a160`
- end: `0x18001a37a`
- name: `?write_name@output_archive@tson@@AEAA_N_N@Z`
- size: `538`
- prototype: `bool __fastcall(tson::output_archive *__hidden this, bool)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x1800038f0`
- `0x180003990`
- `0x1800065b4`
- `0x18000664c`
- `0x1800066e4`
- `0x1800067e4`
- `0x1800189d0`
- `0x180018a6c`
- `0x180019060`
- `0x180019420`
- `0x180019500`

## callees

- `0x180018458`
- `0x18001873c`
- `0x18001a160`

## pseudocode

```c
char __fastcall tson::output_archive::write_name(tson::output_archive *this, char a2)
{
  __int64 v2; // rax
  char *v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // rbx
  tson::write_buffer *v8; // rbx
  char *v10; // rbx
  tson::write_buffer **v11; // r14
  tson::write_buffer *v12; // rsi
  char *v13; // rbp
  tson::write_buffer **v14; // r15
  tson::write_buffer *v15; // rsi
  char v16; // cl

  v2 = *((_QWORD *)this + 16);
  if ( v2 )
  {
    v5 = (char *)this + 4 * v2 + 24;
  }
  else
  {
    *((_BYTE *)this + 24) = 1;
    v5 = (char *)this + 28;
  }
  if ( *(_DWORD *)v5 == 2 )
  {
    *(_DWORD *)v5 = 3;
    v6 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v6 + 2072) < *(_QWORD *)(v6 + 2080)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v6 + 2072))++ = 3;
    }
    tson::write_buffer::push_back(*((tson::write_buffer **)this + 18), (char *)this + 10, 2u);
    *((_WORD *)this + 5) = 0;
  }
  else if ( !*(_DWORD *)v5 )
  {
    *(_DWORD *)v5 = 1;
    v7 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v7 + 2072) < *(_QWORD *)(v7 + 2080)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v7 + 2072))++ = 1;
    }
  }
  *((_QWORD *)this + 2) = 0;
  if ( *(_DWORD *)v5 == 3 )
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
    if ( *((_QWORD *)v12 + 259) < *((_QWORD *)v12 + 260)
      || (v13 = (char *)this + 8, v14 = (tson::write_buffer **)((char *)this + 144),
                                  tson::write_buffer::reserve(v12, 1u)) )
    {
      v13 = (char *)this + 8;
      v14 = (tson::write_buffer **)((char *)this + 144);
      *(_BYTE *)(*((_QWORD *)v12 + 259))++ = 5;
    }
    v15 = *v11;
    if ( *((_QWORD *)*v11 + 259) < *((_QWORD *)*v11 + 260) || tson::write_buffer::reserve(*v11, 1u) )
    {
      v16 = *v10;
      v11 = v14;
      v10 = v13;
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
0x18001a160  mov     [rsp+arg_0], rbx
0x18001a165  mov     [rsp+arg_8], rbp
0x18001a16a  mov     [rsp+arg_10], rsi
0x18001a16f  push    rdi
0x18001a170  push    r12
0x18001a172  push    r13
0x18001a174  push    r14
0x18001a176  push    r15
0x18001a178  sub     rsp, 20h
0x18001a17c  mov     rax, [rcx+80h]
0x18001a183  xor     r13d, r13d
0x18001a186  mov     bpl, dl
0x18001a189  mov     rdi, rcx
0x18001a18c  mov     r12d, 1
0x18001a192  test    rax, rax
0x18001a195  jz      short loc_18001A1A1
0x18001a197  lea     rsi, [rcx+18h]
0x18001a19b  lea     rsi, [rsi+rax*4]
0x18001a19f  jmp     short loc_18001A1A9
0x18001a1a1  mov     [rcx+18h], r12b
0x18001a1a5  lea     rsi, [rcx+1Ch]
0x18001a1a9  cmp     dword ptr [rsi], 2
0x18001a1ac  jnz     short loc_18001A208
0x18001a1ae  mov     dword ptr [rsi], 3
0x18001a1b4  mov     rbx, [rcx+90h]
0x18001a1bb  mov     rax, [rbx+820h]
0x18001a1c2  cmp     [rbx+818h], rax
0x18001a1c9  jb      short loc_18001A1DA
0x18001a1cb  mov     rdx, r12; unsigned __int64
0x18001a1ce  mov     rcx, rbx; this
0x18001a1d1  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001a1d6  test    al, al
0x18001a1d8  jz      short loc_18001A1EB
0x18001a1da  mov     rax, [rbx+818h]
0x18001a1e1  mov     byte ptr [rax], 3
0x18001a1e4  add     [rbx+818h], r12
0x18001a1eb  mov     rcx, [rdi+90h]; this
0x18001a1f2  lea     rdx, [rdi+0Ah]; void *
0x18001a1f6  mov     r8d, 2; unsigned __int64
0x18001a1fc  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x18001a201  mov     [rdi+0Ah], r13w
0x18001a206  jmp     short loc_18001A247
0x18001a208  cmp     [rsi], r13d
0x18001a20b  jnz     short loc_18001A247
0x18001a20d  mov     [rsi], r12d
0x18001a210  mov     rbx, [rcx+90h]
0x18001a217  mov     rax, [rbx+820h]
0x18001a21e  cmp     [rbx+818h], rax
0x18001a225  jb      short loc_18001A236
0x18001a227  mov     rdx, r12; unsigned __int64
0x18001a22a  mov     rcx, rbx; this
0x18001a22d  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001a232  test    al, al
0x18001a234  jz      short loc_18001A247
0x18001a236  mov     rax, [rbx+818h]
0x18001a23d  mov     [rax], r12b
0x18001a240  add     [rbx+818h], r12
0x18001a247  mov     [rdi+10h], r13
0x18001a24b  cmp     dword ptr [rsi], 3
0x18001a24e  jz      loc_18001A359
0x18001a254  test    bpl, bpl
0x18001a257  jz      short loc_18001A29A
0x18001a259  mov     rbx, [rdi+90h]
0x18001a260  mov     [rdi], r13
0x18001a263  mov     rax, [rbx+820h]
0x18001a26a  cmp     [rbx+818h], rax
0x18001a271  jb      short loc_18001A282
0x18001a273  mov     rdx, r12; unsigned __int64
0x18001a276  mov     rcx, rbx; this
0x18001a279  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001a27e  test    al, al
0x18001a280  jz      short loc_18001A293
0x18001a282  mov     rax, [rbx+818h]
0x18001a289  mov     byte ptr [rax], 6
0x18001a28c  add     [rbx+818h], r12
0x18001a293  xor     al, al
0x18001a295  jmp     loc_18001A35C
0x18001a29a  lea     rbx, [rdi+8]
0x18001a29e  cmp     [rdi], r13
0x18001a2a1  jnz     short loc_18001A2B0
0x18001a2a3  lea     rax, asc_180026544; "-"
0x18001a2aa  mov     [rbx], r12b
0x18001a2ad  mov     [rdi], rax
0x18001a2b0  lea     r14, [rdi+90h]
0x18001a2b7  mov     rsi, [r14]
0x18001a2ba  mov     rax, [rsi+818h]
0x18001a2c1  sub     rax, [rsi+810h]
0x18001a2c8  mov     [rdi+10h], rax
0x18001a2cc  mov     rax, [rsi+820h]
0x18001a2d3  cmp     [rsi+818h], rax
0x18001a2da  jb      short loc_18001A2F1
0x18001a2dc  mov     rdx, r12; unsigned __int64
0x18001a2df  mov     rcx, rsi; this
0x18001a2e2  mov     rbp, rbx
0x18001a2e5  mov     r15, r14
0x18001a2e8  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001a2ed  test    al, al
0x18001a2ef  jz      short loc_18001A30D
0x18001a2f1  mov     rax, [rsi+818h]
0x18001a2f8  lea     rbp, [rdi+8]
0x18001a2fc  lea     r15, [rdi+90h]
0x18001a303  mov     byte ptr [rax], 5
0x18001a306  add     [rsi+818h], r12
0x18001a30d  mov     rsi, [r14]
0x18001a310  mov     rax, [rsi+820h]
0x18001a317  cmp     [rsi+818h], rax
0x18001a31e  jb      short loc_18001A32F
0x18001a320  mov     rdx, r12; unsigned __int64
0x18001a323  mov     rcx, rsi; this
0x18001a326  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001a32b  test    al, al
0x18001a32d  jz      short loc_18001A347
0x18001a32f  mov     cl, [rbx]
0x18001a331  mov     r14, r15
0x18001a334  mov     rdx, [rsi+818h]
0x18001a33b  mov     rbx, rbp
0x18001a33e  mov     [rdx], cl
0x18001a340  add     [rsi+818h], r12
0x18001a347  movzx   r8d, byte ptr [rbx]; unsigned __int64
0x18001a34b  mov     rdx, [rdi]; void *
0x18001a34e  mov     rcx, [r14]; this
0x18001a351  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x18001a356  mov     [rdi], r13
0x18001a359  mov     al, r12b
0x18001a35c  mov     rbx, [rsp+48h+arg_0]
0x18001a361  mov     rbp, [rsp+48h+arg_8]
0x18001a366  mov     rsi, [rsp+48h+arg_10]
0x18001a36b  add     rsp, 20h
0x18001a36f  pop     r15
0x18001a371  pop     r14
0x18001a373  pop     r13
0x18001a375  pop     r12
0x18001a377  pop     rdi
0x18001a378  retn
```
