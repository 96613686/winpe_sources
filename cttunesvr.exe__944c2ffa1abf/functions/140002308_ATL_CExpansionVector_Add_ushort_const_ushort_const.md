# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x140002308`
- end: `0x1400024db`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `467`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140002570`
- `0x140004f48`

## callees

- `0x1400011ec`
- `0x1400011f8`
- `0x140001640`
- `0x140002308`
- `0x140002c14`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400023b1`
- `msvcrt!memcpy_s` at `0x1400023eb`
- `msvcrt!memcpy_s` at `0x1400023b1`
- `msvcrt!memcpy_s` at `0x1400023eb`

## pseudocode

```c
_BOOL8 __fastcall ATL::CExpansionVector::Add(void **this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v6; // rax
  __int64 v7; // r12
  void *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // r15
  void *v11; // rax
  void *v12; // rbx
  errno_t v13; // eax
  errno_t v14; // eax
  void *v15; // rax
  void *v16; // rcx
  void *v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  int v21; // esi

  if ( a2 && a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = 2 * v6 + 2;
    v8 = operator new[](saturated_mul(v7, 2u));
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = 2LL * ((int)v9 + 1);
    v11 = operator new[](saturated_mul(v10, 2u));
    v12 = v11;
    if ( !v8 || !v11 )
      goto LABEL_26;
    v13 = memcpy_s(v8, v7, a2, v7);
    if ( v13 )
    {
      if ( v13 == 12 )
        goto LABEL_29;
      if ( v13 == 22 || v13 == 34 )
        goto LABEL_31;
      if ( v13 != 80 )
        goto LABEL_30;
    }
    v14 = memcpy_s(v12, v10, a3, v10);
    if ( !v14 )
    {
LABEL_19:
      v15 = _recalloc(*this, *((_DWORD *)this + 4) + 1, 8u);
      if ( v15 )
      {
        v16 = this[1];
        *this = v15;
        v17 = _recalloc(v16, *((_DWORD *)this + 4) + 1, 8u);
        if ( v17 )
        {
          v18 = *((int *)this + 4);
          this[1] = v17;
          v19 = (char *)*this + 8 * v18;
          if ( v19 )
            *v19 = v8;
          v20 = (char *)this[1] + 8 * v18;
          if ( v20 )
            *v20 = v12;
          ++*((_DWORD *)this + 4);
          v8 = 0;
          v21 = 0;
          v12 = 0;
          goto LABEL_27;
        }
      }
LABEL_26:
      v21 = -2147024882;
LABEL_27:
      operator delete[](v12);
      operator delete[](v8);
      return v21 >= 0;
    }
    if ( v14 != 12 )
    {
      if ( v14 != 22 && v14 != 34 )
      {
        if ( v14 == 80 )
          goto LABEL_19;
LABEL_30:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_31:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_29:
    ATL::AtlThrowImpl(-2147024882);
  }
  return 0;
}

```

## disassembly

```asm
0x140002308  push    rbx
0x14000230a  push    rbp
0x14000230b  push    rsi
0x14000230c  push    rdi
0x14000230d  push    r12
0x14000230f  push    r13
0x140002311  push    r14
0x140002313  push    r15
0x140002315  sub     rsp, 28h
0x140002319  xor     r13d, r13d
0x14000231c  mov     r14, r8
0x14000231f  mov     rbp, rdx
0x140002322  mov     rsi, rcx
0x140002325  test    rdx, rdx
0x140002328  jz      loc_1400024A7
0x14000232e  test    r8, r8
0x140002331  jz      loc_1400024A7
0x140002337  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000233b  mov     rax, rbx
0x14000233e  inc     rax
0x140002341  cmp     [rdx+rax*2], r13w
0x140002346  jnz     short loc_14000233E
0x140002348  lea     r12, ds:2[rax*2]
0x140002350  mov     eax, 2
0x140002355  mul     r12
0x140002358  cmovb   rax, rbx
0x14000235c  mov     rcx, rax; unsigned __int64
0x14000235f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140002364  mov     rdi, rax
0x140002367  mov     rcx, rbx
0x14000236a  inc     rcx
0x14000236d  cmp     [r14+rcx*2], r13w
0x140002372  jnz     short loc_14000236A
0x140002374  inc     ecx
0x140002376  mov     eax, 2
0x14000237b  movsxd  r15, ecx
0x14000237e  add     r15, r15
0x140002381  mul     r15
0x140002384  cmovb   rax, rbx
0x140002388  mov     rcx, rax; unsigned __int64
0x14000238b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140002390  mov     rbx, rax
0x140002393  test    rdi, rdi
0x140002396  jz      loc_140002489
0x14000239c  test    rax, rax
0x14000239f  jz      loc_140002489
0x1400023a5  mov     r9, r12; SourceSize
0x1400023a8  mov     r8, rbp; Source
0x1400023ab  mov     rdx, r12; DestinationSize
0x1400023ae  mov     rcx, rdi; Destination
0x1400023b1  call    cs:__imp_memcpy_s
0x1400023b7  test    eax, eax
0x1400023b9  jz      short loc_1400023DF
0x1400023bb  cmp     eax, 0Ch
0x1400023be  jz      loc_1400024BA
0x1400023c4  cmp     eax, 16h
0x1400023c7  jz      loc_1400024D0
0x1400023cd  cmp     eax, 22h ; '"'
0x1400023d0  jz      loc_1400024D0
0x1400023d6  cmp     eax, 50h ; 'P'
0x1400023d9  jnz     loc_1400024C5
0x1400023df  mov     r9, r15; SourceSize
0x1400023e2  mov     r8, r14; Source
0x1400023e5  mov     rdx, r15; DestinationSize
0x1400023e8  mov     rcx, rbx; Destination
0x1400023eb  call    cs:__imp_memcpy_s
0x1400023f1  test    eax, eax
0x1400023f3  jz      short loc_140002419
0x1400023f5  cmp     eax, 0Ch
0x1400023f8  jz      loc_1400024BA
0x1400023fe  cmp     eax, 16h
0x140002401  jz      loc_1400024D0
0x140002407  cmp     eax, 22h ; '"'
0x14000240a  jz      loc_1400024D0
0x140002410  cmp     eax, 50h ; 'P'
0x140002413  jnz     loc_1400024C5
0x140002419  mov     eax, [rsi+10h]
0x14000241c  mov     ebp, 8
0x140002421  mov     rcx, [rsi]; Block
0x140002424  inc     eax
0x140002426  movsxd  rdx, eax; Count
0x140002429  mov     r8d, ebp; Size
0x14000242c  call    cs:__imp__recalloc
0x140002432  test    rax, rax
0x140002435  jz      short loc_140002489
0x140002437  mov     rcx, [rsi+8]; Block
0x14000243b  mov     r8d, ebp; Size
0x14000243e  mov     [rsi], rax
0x140002441  mov     eax, [rsi+10h]
0x140002444  inc     eax
0x140002446  movsxd  rdx, eax; Count
0x140002449  call    cs:__imp__recalloc
0x14000244f  test    rax, rax
0x140002452  jz      short loc_140002489
0x140002454  movsxd  rdx, dword ptr [rsi+10h]
0x140002458  mov     [rsi+8], rax
0x14000245c  mov     rax, [rsi]
0x14000245f  lea     rcx, [rax+rdx*8]
0x140002463  test    rcx, rcx
0x140002466  jz      short loc_14000246B
0x140002468  mov     [rcx], rdi
0x14000246b  mov     rax, [rsi+8]
0x14000246f  lea     rcx, [rax+rdx*8]
0x140002473  test    rcx, rcx
0x140002476  jz      short loc_14000247B
0x140002478  mov     [rcx], rbx
0x14000247b  inc     dword ptr [rsi+10h]
0x14000247e  mov     rdi, r13
0x140002481  mov     esi, r13d
0x140002484  mov     rbx, r13
0x140002487  jmp     short loc_14000248E
0x140002489  mov     esi, 8007000Eh
0x14000248e  not     esi
0x140002490  mov     rcx, rbx; Block
0x140002493  shr     esi, 1Fh
0x140002496  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x14000249b  mov     rcx, rdi; Block
0x14000249e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1400024a3  mov     eax, esi
0x1400024a5  jmp     short loc_1400024A9
0x1400024a7  xor     eax, eax
0x1400024a9  add     rsp, 28h
0x1400024ad  pop     r15
0x1400024af  pop     r14
0x1400024b1  pop     r13
0x1400024b3  pop     r12
0x1400024b5  pop     rdi
0x1400024b6  pop     rsi
0x1400024b7  pop     rbp
0x1400024b8  pop     rbx
0x1400024b9  retn
0x1400024ba  mov     ecx, 8007000Eh; int
0x1400024bf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400024c5  mov     ecx, 80004005h; int
0x1400024ca  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400024d0  mov     ecx, 80070057h; int
0x1400024d5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
