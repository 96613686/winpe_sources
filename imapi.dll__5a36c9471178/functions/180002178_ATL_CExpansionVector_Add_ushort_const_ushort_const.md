# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180002178`
- end: `0x18000234b`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `467`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800023f0`
- `0x1800043dc`
- `0x1800093cc`

## callees

- `0x180001150`
- `0x18000119c`
- `0x1800019d0`
- `0x180002178`
- `0x180002ac4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002221`
- `msvcrt!memcpy_s` at `0x18000225b`
- `msvcrt!memcpy_s` at `0x180002221`
- `msvcrt!memcpy_s` at `0x18000225b`

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
0x180002178  push    rbx
0x18000217a  push    rbp
0x18000217b  push    rsi
0x18000217c  push    rdi
0x18000217d  push    r12
0x18000217f  push    r13
0x180002181  push    r14
0x180002183  push    r15
0x180002185  sub     rsp, 28h
0x180002189  xor     r13d, r13d
0x18000218c  mov     r14, r8
0x18000218f  mov     rbp, rdx
0x180002192  mov     rsi, rcx
0x180002195  test    rdx, rdx
0x180002198  jz      loc_180002317
0x18000219e  test    r8, r8
0x1800021a1  jz      loc_180002317
0x1800021a7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800021ab  mov     rax, rbx
0x1800021ae  inc     rax
0x1800021b1  cmp     [rdx+rax*2], r13w
0x1800021b6  jnz     short loc_1800021AE
0x1800021b8  lea     r12, ds:2[rax*2]
0x1800021c0  mov     eax, 2
0x1800021c5  mul     r12
0x1800021c8  cmovb   rax, rbx
0x1800021cc  mov     rcx, rax; unsigned __int64
0x1800021cf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800021d4  mov     rdi, rax
0x1800021d7  mov     rcx, rbx
0x1800021da  inc     rcx
0x1800021dd  cmp     [r14+rcx*2], r13w
0x1800021e2  jnz     short loc_1800021DA
0x1800021e4  inc     ecx
0x1800021e6  mov     eax, 2
0x1800021eb  movsxd  r15, ecx
0x1800021ee  add     r15, r15
0x1800021f1  mul     r15
0x1800021f4  cmovb   rax, rbx
0x1800021f8  mov     rcx, rax; unsigned __int64
0x1800021fb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002200  mov     rbx, rax
0x180002203  test    rdi, rdi
0x180002206  jz      loc_1800022F9
0x18000220c  test    rax, rax
0x18000220f  jz      loc_1800022F9
0x180002215  mov     r9, r12; SourceSize
0x180002218  mov     r8, rbp; Source
0x18000221b  mov     rdx, r12; DestinationSize
0x18000221e  mov     rcx, rdi; Destination
0x180002221  call    cs:__imp_memcpy_s
0x180002227  test    eax, eax
0x180002229  jz      short loc_18000224F
0x18000222b  cmp     eax, 0Ch
0x18000222e  jz      loc_18000232A
0x180002234  cmp     eax, 16h
0x180002237  jz      loc_180002340
0x18000223d  cmp     eax, 22h ; '"'
0x180002240  jz      loc_180002340
0x180002246  cmp     eax, 50h ; 'P'
0x180002249  jnz     loc_180002335
0x18000224f  mov     r9, r15; SourceSize
0x180002252  mov     r8, r14; Source
0x180002255  mov     rdx, r15; DestinationSize
0x180002258  mov     rcx, rbx; Destination
0x18000225b  call    cs:__imp_memcpy_s
0x180002261  test    eax, eax
0x180002263  jz      short loc_180002289
0x180002265  cmp     eax, 0Ch
0x180002268  jz      loc_18000232A
0x18000226e  cmp     eax, 16h
0x180002271  jz      loc_180002340
0x180002277  cmp     eax, 22h ; '"'
0x18000227a  jz      loc_180002340
0x180002280  cmp     eax, 50h ; 'P'
0x180002283  jnz     loc_180002335
0x180002289  mov     eax, [rsi+10h]
0x18000228c  mov     ebp, 8
0x180002291  mov     rcx, [rsi]; Block
0x180002294  inc     eax
0x180002296  movsxd  rdx, eax; Count
0x180002299  mov     r8d, ebp; Size
0x18000229c  call    cs:__imp__recalloc
0x1800022a2  test    rax, rax
0x1800022a5  jz      short loc_1800022F9
0x1800022a7  mov     rcx, [rsi+8]; Block
0x1800022ab  mov     r8d, ebp; Size
0x1800022ae  mov     [rsi], rax
0x1800022b1  mov     eax, [rsi+10h]
0x1800022b4  inc     eax
0x1800022b6  movsxd  rdx, eax; Count
0x1800022b9  call    cs:__imp__recalloc
0x1800022bf  test    rax, rax
0x1800022c2  jz      short loc_1800022F9
0x1800022c4  movsxd  rdx, dword ptr [rsi+10h]
0x1800022c8  mov     [rsi+8], rax
0x1800022cc  mov     rax, [rsi]
0x1800022cf  lea     rcx, [rax+rdx*8]
0x1800022d3  test    rcx, rcx
0x1800022d6  jz      short loc_1800022DB
0x1800022d8  mov     [rcx], rdi
0x1800022db  mov     rax, [rsi+8]
0x1800022df  lea     rcx, [rax+rdx*8]
0x1800022e3  test    rcx, rcx
0x1800022e6  jz      short loc_1800022EB
0x1800022e8  mov     [rcx], rbx
0x1800022eb  inc     dword ptr [rsi+10h]
0x1800022ee  mov     rdi, r13
0x1800022f1  mov     esi, r13d
0x1800022f4  mov     rbx, r13
0x1800022f7  jmp     short loc_1800022FE
0x1800022f9  mov     esi, 8007000Eh
0x1800022fe  not     esi
0x180002300  mov     rcx, rbx; Block
0x180002303  shr     esi, 1Fh
0x180002306  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000230b  mov     rcx, rdi; Block
0x18000230e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180002313  mov     eax, esi
0x180002315  jmp     short loc_180002319
0x180002317  xor     eax, eax
0x180002319  add     rsp, 28h
0x18000231d  pop     r15
0x18000231f  pop     r14
0x180002321  pop     r13
0x180002323  pop     r12
0x180002325  pop     rdi
0x180002326  pop     rsi
0x180002327  pop     rbp
0x180002328  pop     rbx
0x180002329  retn
0x18000232a  mov     ecx, 8007000Eh; int
0x18000232f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002335  mov     ecx, 80004005h; int
0x18000233a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002340  mov     ecx, 80070057h; int
0x180002345  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
