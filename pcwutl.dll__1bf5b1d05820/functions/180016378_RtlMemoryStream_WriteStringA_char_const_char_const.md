# RtlMemoryStream::WriteStringA(char const *,char const *)

- ea: `0x180016378`
- end: `0x180016587`
- name: `?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z`
- size: `527`
- prototype: `int(RtlMemoryStream *__hidden this, const char *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800174a4`

## callees

- `0x1800027d6`
- `0x180016378`
- `0x1800191a2`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001641b`
- `KERNEL32!HeapAlloc` at `0x1800164e7`
- `KERNEL32!HeapAlloc` at `0x18001641b`
- `KERNEL32!HeapAlloc` at `0x1800164e7`
- `KERNEL32!HeapReAlloc` at `0x18001643b`
- `KERNEL32!HeapReAlloc` at `0x180016518`
- `KERNEL32!HeapReAlloc` at `0x18001643b`
- `KERNEL32!HeapReAlloc` at `0x180016518`

## pseudocode

```c
__int64 __fastcall RtlMemoryStream::WriteStringA(RtlMemoryStream *this, const char *a2, const char *a3)
{
  size_t v6; // rdi
  size_t v7; // rsi
  size_t *v8; // r15
  size_t v9; // rax
  unsigned __int64 v10; // rcx
  __int64 v11; // r14
  unsigned __int64 v12; // rax
  void *v13; // r8
  void *v14; // rcx
  SIZE_T v15; // r14
  void *v16; // rax
  LPVOID v17; // rbp
  size_t *v19; // rax
  size_t v20; // rcx
  size_t v21; // rax
  size_t *v22; // r14
  size_t v23; // rax
  unsigned __int64 v24; // rcx
  __int64 v25; // rsi
  unsigned __int64 v26; // rax
  void *v27; // r8
  void *v28; // rcx
  SIZE_T v29; // rsi
  void *v30; // rax
  LPVOID v31; // rbp
  _QWORD *v32; // rax
  size_t v33; // rcx
  size_t v34; // rax

  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    if ( !v6 )
      v6 = 1;
  }
  else
  {
    v6 = 0;
  }
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    if ( v7 )
    {
      v8 = (size_t *)((char *)this + 32);
      v9 = *((_QWORD *)this + 4);
      v10 = v9 + v7;
      if ( v9 + v7 < v9 )
        return 160;
      if ( v10 <= *((_QWORD *)this + 2) )
      {
        v19 = v8;
      }
      else
      {
        v11 = *((_QWORD *)this + 3) - 1LL;
        v12 = v11 + v10;
        if ( v11 + v10 < v10 )
          return 534;
        v13 = (void *)*((_QWORD *)this + 5);
        v14 = *(void **)this;
        v15 = v12 & ~v11;
        if ( v13 )
        {
          v17 = HeapReAlloc(v14, 0, v13, v15);
        }
        else
        {
          v16 = HeapAlloc(v14, 0, v15);
          v17 = v16;
          if ( v16 )
            memset_0(v16, 0, v15);
        }
        if ( !v17 )
          return 14;
        *((_QWORD *)this + 5) = v17;
        v19 = (size_t *)((char *)this + 32);
        *((_QWORD *)this + 2) = v15;
      }
      memcpy_0((void *)(*v19 + *((_QWORD *)this + 5)), a2, v7);
      v20 = *v8 + v7;
      if ( v20 < *v8 )
      {
        *v8 = -1;
        return 534;
      }
      *v8 = v20;
      v21 = *((_QWORD *)this + 1);
      if ( v21 <= v20 )
        v21 = v20;
      *((_QWORD *)this + 1) = v21;
    }
  }
  if ( a3 && v6 )
  {
    v22 = (size_t *)((char *)this + 32);
    v23 = *((_QWORD *)this + 4);
    v24 = v23 + v6;
    if ( v23 + v6 >= v23 )
    {
      if ( v24 <= *((_QWORD *)this + 2) )
      {
        v32 = (_QWORD *)((char *)this + 32);
      }
      else
      {
        v25 = *((_QWORD *)this + 3) - 1LL;
        v26 = v24 + v25;
        if ( v24 + v25 < v24 )
          return 534;
        v27 = (void *)*((_QWORD *)this + 5);
        v28 = *(void **)this;
        v29 = v26 & ~v25;
        if ( v27 )
        {
          v31 = HeapReAlloc(v28, 0, v27, v29);
        }
        else
        {
          v30 = HeapAlloc(v28, 0, v29);
          v31 = v30;
          if ( v30 )
            memset_0(v30, 0, v29);
        }
        if ( !v31 )
          return 14;
        *((_QWORD *)this + 5) = v31;
        v32 = (_QWORD *)((char *)this + 32);
        *((_QWORD *)this + 2) = v29;
      }
      memcpy_0((void *)(*v32 + *((_QWORD *)this + 5)), a3, v6);
      v33 = *v22 + v6;
      if ( v33 >= *v22 )
      {
        *v22 = v33;
        v34 = *((_QWORD *)this + 1);
        if ( v34 <= v33 )
          v34 = v33;
        *((_QWORD *)this + 1) = v34;
        return 0;
      }
      *v22 = -1;
      return 534;
    }
    return 160;
  }
  return 0;
}

```

## disassembly

```asm
0x180016378  push    rbx
0x18001637a  push    rbp
0x18001637b  push    rsi
0x18001637c  push    rdi
0x18001637d  push    r12
0x18001637f  push    r13
0x180016381  push    r14
0x180016383  push    r15
0x180016385  sub     rsp, 28h
0x180016389  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001638d  mov     r13, r8
0x180016390  mov     r12, rdx
0x180016393  mov     rbx, rcx
0x180016396  test    r8, r8
0x180016399  jz      short loc_1800163B6
0x18001639b  mov     rdi, rbp
0x18001639e  inc     rdi
0x1800163a1  cmp     byte ptr [rdi+r8], 0
0x1800163a6  jnz     short loc_18001639E
0x1800163a8  mov     eax, 1
0x1800163ad  cmp     rdi, rax
0x1800163b0  cmovb   rdi, rax
0x1800163b4  jmp     short loc_1800163B8
0x1800163b6  xor     edi, edi
0x1800163b8  test    r12, r12
0x1800163bb  jz      loc_180016498
0x1800163c1  mov     rsi, rbp
0x1800163c4  inc     rsi
0x1800163c7  cmp     byte ptr [rdx+rsi], 0
0x1800163cb  jnz     short loc_1800163C4
0x1800163cd  test    rsi, rsi
0x1800163d0  jz      loc_180016498
0x1800163d6  lea     r15, [rcx+20h]
0x1800163da  mov     rax, [r15]
0x1800163dd  lea     rcx, [rax+rsi]
0x1800163e1  cmp     rcx, rax
0x1800163e4  jb      loc_18001650E
0x1800163ea  cmp     rcx, [rbx+10h]
0x1800163ee  jbe     short loc_180016465
0x1800163f0  mov     r14, [rbx+18h]
0x1800163f4  dec     r14
0x1800163f7  lea     rax, [r14+rcx]
0x1800163fb  cmp     rax, rcx
0x1800163fe  jb      loc_180016507
0x180016404  mov     r8, [rbx+28h]; lpMem
0x180016408  not     r14
0x18001640b  mov     rcx, [rbx]; hHeap
0x18001640e  and     r14, rax
0x180016411  xor     edx, edx; dwFlags
0x180016413  test    r8, r8
0x180016416  jnz     short loc_180016438
0x180016418  mov     r8, r14; dwBytes
0x18001641b  call    cs:__imp_HeapAlloc
0x180016421  mov     rbp, rax
0x180016424  test    rax, rax
0x180016427  jz      short loc_180016444
0x180016429  mov     r8, r14; Size
0x18001642c  xor     edx, edx; Val
0x18001642e  mov     rcx, rax; void *
0x180016431  call    memset_0
0x180016436  jmp     short loc_180016444
0x180016438  mov     r9, r14; dwBytes
0x18001643b  call    cs:__imp_HeapReAlloc
0x180016441  mov     rbp, rax
0x180016444  test    rbp, rbp
0x180016447  jnz     short loc_180016453
0x180016449  mov     eax, 0Eh
0x18001644e  jmp     loc_18001656D
0x180016453  mov     [rbx+28h], rbp
0x180016457  lea     rax, [rbx+20h]
0x18001645b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001645f  mov     [rbx+10h], r14
0x180016463  jmp     short loc_180016468
0x180016465  mov     rax, r15
0x180016468  mov     rcx, [rbx+28h]
0x18001646c  mov     r8, rsi; Size
0x18001646f  add     rcx, [rax]; void *
0x180016472  mov     rdx, r12; Src
0x180016475  call    memcpy_0
0x18001647a  mov     rax, [r15]
0x18001647d  lea     rcx, [rax+rsi]
0x180016481  cmp     rcx, rax
0x180016484  jb      short loc_180016504
0x180016486  mov     [r15], rcx
0x180016489  mov     rax, [rbx+8]
0x18001648d  cmp     rax, rcx
0x180016490  cmovbe  rax, rcx
0x180016494  mov     [rbx+8], rax
0x180016498  test    r13, r13
0x18001649b  jz      loc_18001656B
0x1800164a1  test    rdi, rdi
0x1800164a4  jz      loc_18001656B
0x1800164aa  lea     r14, [rbx+20h]
0x1800164ae  mov     rax, [r14]
0x1800164b1  lea     rcx, [rax+rdi]
0x1800164b5  cmp     rcx, rax
0x1800164b8  jb      short loc_18001650E
0x1800164ba  cmp     rcx, [rbx+10h]
0x1800164be  jbe     short loc_180016538
0x1800164c0  mov     rsi, [rbx+18h]
0x1800164c4  dec     rsi
0x1800164c7  lea     rax, [rcx+rsi]
0x1800164cb  cmp     rax, rcx
0x1800164ce  jb      short loc_180016507
0x1800164d0  mov     r8, [rbx+28h]; lpMem
0x1800164d4  not     rsi
0x1800164d7  mov     rcx, [rbx]; hHeap
0x1800164da  and     rsi, rax
0x1800164dd  xor     edx, edx; dwFlags
0x1800164df  test    r8, r8
0x1800164e2  jnz     short loc_180016515
0x1800164e4  mov     r8, rsi; dwBytes
0x1800164e7  call    cs:__imp_HeapAlloc
0x1800164ed  mov     rbp, rax
0x1800164f0  test    rax, rax
0x1800164f3  jz      short loc_180016521
0x1800164f5  mov     r8, rsi; Size
0x1800164f8  xor     edx, edx; Val
0x1800164fa  mov     rcx, rax; void *
0x1800164fd  call    memset_0
0x180016502  jmp     short loc_180016521
0x180016504  mov     [r15], rbp
0x180016507  mov     eax, 216h
0x18001650c  jmp     short loc_18001656D
0x18001650e  mov     eax, 0A0h
0x180016513  jmp     short loc_18001656D
0x180016515  mov     r9, rsi; dwBytes
0x180016518  call    cs:__imp_HeapReAlloc
0x18001651e  mov     rbp, rax
0x180016521  test    rbp, rbp
0x180016524  jz      loc_180016449
0x18001652a  mov     [rbx+28h], rbp
0x18001652e  lea     rax, [rbx+20h]
0x180016532  mov     [rbx+10h], rsi
0x180016536  jmp     short loc_18001653B
0x180016538  mov     rax, r14
0x18001653b  mov     rcx, [rbx+28h]
0x18001653f  mov     r8, rdi; Size
0x180016542  add     rcx, [rax]; void *
0x180016545  mov     rdx, r13; Src
0x180016548  call    memcpy_0
0x18001654d  mov     rax, [r14]
0x180016550  lea     rcx, [rax+rdi]
0x180016554  cmp     rcx, rax
0x180016557  jb      short loc_18001657E
0x180016559  mov     [r14], rcx
0x18001655c  mov     rax, [rbx+8]
0x180016560  cmp     rax, rcx
0x180016563  cmovbe  rax, rcx
0x180016567  mov     [rbx+8], rax
0x18001656b  xor     eax, eax
0x18001656d  add     rsp, 28h
0x180016571  pop     r15
0x180016573  pop     r14
0x180016575  pop     r13
0x180016577  pop     r12
0x180016579  pop     rdi
0x18001657a  pop     rsi
0x18001657b  pop     rbp
0x18001657c  pop     rbx
0x18001657d  retn
0x18001657e  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180016585  jmp     short loc_180016507
```
