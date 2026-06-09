# tson::output_archive::write_name(bool)

- ea: `0x180019308`
- end: `0x180019514`
- name: `?write_name@output_archive@tson@@AEAA_N_N@Z`
- size: `524`
- prototype: `char __fastcall(tson::output_archive *this, char)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180003f2c`
- `0x1800041cc`
- `0x1800066a8`
- `0x180006740`
- `0x1800067d4`
- `0x180006864`
- `0x180006954`
- `0x1800179fc`
- `0x18001807c`
- `0x180018470`
- `0x180018530`

## callees

- `0x180017780`
- `0x180017944`
- `0x180019308`

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
    tson::write_buffer::push_back(*((void ***)this + 18), (char *)this + 10, 2u);
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
    tson::write_buffer::push_back((void **)*v11, *(const void **)this, (unsigned __int8)*v10);
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
0x180019308  push    rbx
0x18001930a  push    rbp
0x18001930b  push    rsi
0x18001930c  push    rdi
0x18001930d  push    r12
0x18001930f  push    r14
0x180019311  push    r15
0x180019313  sub     rsp, 20h
0x180019317  lea     rsi, [rcx+18h]
0x18001931b  mov     bpl, dl
0x18001931e  mov     rax, [rsi+68h]
0x180019322  mov     rdi, rcx
0x180019325  mov     r12d, 1
0x18001932b  test    rax, rax
0x18001932e  jz      short loc_18001933A
0x180019330  lea     rsi, [rsi+rax*4]
0x180019334  add     rsi, 0FFFFFFFFFFFFFFFCh
0x180019338  jmp     short loc_18001933D
0x18001933a  mov     [rsi], r12b
0x18001933d  cmp     dword ptr [rsi+4], 2
0x180019341  jnz     short loc_18001939F
0x180019343  mov     dword ptr [rsi+4], 3
0x18001934a  mov     rbx, [rcx+90h]
0x180019351  mov     rax, [rbx+820h]
0x180019358  cmp     [rbx+818h], rax
0x18001935f  jb      short loc_180019370
0x180019361  mov     rdx, r12; unsigned __int64
0x180019364  mov     rcx, rbx; this
0x180019367  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001936c  test    al, al
0x18001936e  jz      short loc_180019381
0x180019370  mov     rax, [rbx+818h]
0x180019377  mov     byte ptr [rax], 3
0x18001937a  add     [rbx+818h], r12
0x180019381  mov     rcx, [rdi+90h]; this
0x180019388  lea     rdx, [rdi+0Ah]; void *
0x18001938c  mov     r8d, 2; unsigned __int64
0x180019392  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x180019397  xor     eax, eax
0x180019399  mov     [rdi+0Ah], ax
0x18001939d  jmp     short loc_1800193E0
0x18001939f  cmp     dword ptr [rsi+4], 0
0x1800193a3  jnz     short loc_1800193E0
0x1800193a5  mov     [rsi+4], r12d
0x1800193a9  mov     rbx, [rcx+90h]
0x1800193b0  mov     rax, [rbx+820h]
0x1800193b7  cmp     [rbx+818h], rax
0x1800193be  jb      short loc_1800193CF
0x1800193c0  mov     rdx, r12; unsigned __int64
0x1800193c3  mov     rcx, rbx; this
0x1800193c6  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800193cb  test    al, al
0x1800193cd  jz      short loc_1800193E0
0x1800193cf  mov     rax, [rbx+818h]
0x1800193d6  mov     [rax], r12b
0x1800193d9  add     [rbx+818h], r12
0x1800193e0  mov     qword ptr [rdi+10h], 0
0x1800193e8  cmp     dword ptr [rsi+4], 3
0x1800193ec  jz      loc_180019502
0x1800193f2  test    bpl, bpl
0x1800193f5  jz      short loc_18001943C
0x1800193f7  mov     rbx, [rdi+90h]
0x1800193fe  mov     qword ptr [rdi], 0
0x180019405  mov     rax, [rbx+820h]
0x18001940c  cmp     [rbx+818h], rax
0x180019413  jb      short loc_180019424
0x180019415  mov     rdx, r12; unsigned __int64
0x180019418  mov     rcx, rbx; this
0x18001941b  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180019420  test    al, al
0x180019422  jz      short loc_180019435
0x180019424  mov     rax, [rbx+818h]
0x18001942b  mov     byte ptr [rax], 6
0x18001942e  add     [rbx+818h], r12
0x180019435  xor     al, al
0x180019437  jmp     loc_180019505
0x18001943c  cmp     qword ptr [rdi], 0
0x180019440  lea     rsi, [rdi+8]
0x180019444  jnz     short loc_180019453
0x180019446  lea     rax, asc_18002563C; "-"
0x18001944d  mov     [rsi], r12b
0x180019450  mov     [rdi], rax
0x180019453  lea     r14, [rdi+90h]
0x18001945a  mov     rbx, [r14]
0x18001945d  mov     rax, [rbx+818h]
0x180019464  sub     rax, [rbx+810h]
0x18001946b  mov     [rdi+10h], rax
0x18001946f  mov     rax, [rbx+820h]
0x180019476  cmp     [rbx+818h], rax
0x18001947d  jb      short loc_180019496
0x18001947f  mov     rdx, r12; unsigned __int64
0x180019482  mov     rcx, rbx; this
0x180019485  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001948a  test    al, al
0x18001948c  jnz     short loc_180019496
0x18001948e  mov     rbp, r14
0x180019491  mov     r15, rsi
0x180019494  jmp     short loc_1800194B2
0x180019496  mov     rax, [rbx+818h]
0x18001949d  lea     r15, [rdi+8]
0x1800194a1  lea     rbp, [rdi+90h]
0x1800194a8  mov     byte ptr [rax], 5
0x1800194ab  add     [rbx+818h], r12
0x1800194b2  mov     rbx, [r14]
0x1800194b5  mov     rax, [rbx+820h]
0x1800194bc  cmp     [rbx+818h], rax
0x1800194c3  jb      short loc_1800194D4
0x1800194c5  mov     rdx, r12; unsigned __int64
0x1800194c8  mov     rcx, rbx; this
0x1800194cb  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800194d0  test    al, al
0x1800194d2  jz      short loc_1800194EC
0x1800194d4  mov     cl, [rsi]
0x1800194d6  mov     r14, rbp
0x1800194d9  mov     rdx, [rbx+818h]
0x1800194e0  mov     rsi, r15
0x1800194e3  mov     [rdx], cl
0x1800194e5  add     [rbx+818h], r12
0x1800194ec  movzx   r8d, byte ptr [rsi]; unsigned __int64
0x1800194f0  mov     rdx, [rdi]; void *
0x1800194f3  mov     rcx, [r14]; this
0x1800194f6  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x1800194fb  mov     qword ptr [rdi], 0
0x180019502  mov     al, r12b
0x180019505  add     rsp, 20h
0x180019509  pop     r15
0x18001950b  pop     r14
0x18001950d  pop     r12
0x18001950f  pop     rdi
0x180019510  pop     rsi
0x180019511  pop     rbp
0x180019512  pop     rbx
0x180019513  retn
```
