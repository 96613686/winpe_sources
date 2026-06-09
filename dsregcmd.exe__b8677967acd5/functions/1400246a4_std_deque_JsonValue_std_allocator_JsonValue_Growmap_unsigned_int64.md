# std::deque<JsonValue *,std::allocator<JsonValue *>>::_Growmap(unsigned __int64)

- ea: `0x1400246a4`
- end: `0x140024873`
- name: `?_Growmap@?$deque@PEAVJsonValue@@V?$allocator@PEAVJsonValue@@@std@@@std@@AEAAX_K@Z`
- size: `463`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1400245d4`

## callees

- `0x1400017d4`
- `0x140002814`
- `0x1400028ac`
- `0x1400041a4`
- `0x1400246a4`
- `0x14002487c`
- `0x14002c40c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::deque<JsonValue *>::_Growmap(_QWORD *a1)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  size_t v5; // rcx
  _QWORD *v6; // r14
  void *v7; // rax
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rax
  __int64 v10; // r15
  __int64 v11; // rax
  unsigned __int64 v12; // rsi
  size_t v13; // rbx
  const void *v14; // rdx
  char *v15; // rbx
  size_t v16; // r8
  char *v17; // rcx
  __int64 v18; // rcx
  void *v19; // rax

  v2 = 1;
  v3 = a1[2];
  if ( v3 )
    v2 = v3;
  while ( v2 == v3 || v2 < 8 )
  {
    if ( 0xFFFFFFFFFFFFFFFLL - v2 < v2 )
      std::deque<JsonValue *>::_Xlen();
    v2 *= 2LL;
  }
  v4 = a1[3];
  if ( v2 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_28;
  v5 = 8 * v2;
  if ( !(8 * v2) )
  {
    v6 = 0;
    goto LABEL_15;
  }
  if ( v5 < 0x1000 )
  {
    v6 = operator new(v5);
    goto LABEL_15;
  }
  if ( v5 + 39 < v5 )
LABEL_28:
    std::_Throw_bad_array_new_length();
  v7 = operator new(v5 + 39);
  if ( !v7 )
    goto LABEL_24;
  v6 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v6 - 1) = v7;
LABEL_15:
  v8 = v4 >> 1;
  v9 = v2 >> 1;
  v10 = 8 * v8;
  while ( v2 <= v9 )
    v2 *= 2LL;
  v11 = a1[2];
  v12 = v2 - v11;
  v13 = 8 * v11 - v10;
  memmove_0(&v6[v8], (const void *)(a1[1] + v10), v13);
  v14 = (const void *)a1[1];
  v15 = (char *)&v6[v8] + v13;
  if ( v8 > v12 )
  {
    memmove_0(v15, v14, 8 * v12);
    memmove_0(v6, (const void *)(8 * v12 + a1[1]), v10 - 8 * v12);
    v17 = (char *)v6 + v10 - 8 * v12;
    v16 = 8 * v12;
  }
  else
  {
    memmove_0(v15, v14, 8 * v8);
    memset_0(&v15[v10], 0, 8 * (v12 - v8));
    v16 = 8 * v8;
    v17 = (char *)v6;
  }
  memset_0(v17, 0, v16);
  v18 = a1[1];
  if ( v18 )
  {
    if ( (unsigned __int64)(8LL * a1[2]) < 0x1000 )
    {
      v19 = (void *)a1[1];
    }
    else
    {
      v19 = *(void **)(v18 - 8);
      if ( (unsigned __int64)(v18 - (_QWORD)v19 - 8) > 0x1F )
LABEL_24:
        __fastfail(5u);
    }
    operator delete(v19);
  }
  a1[2] += v12;
  a1[1] = v6;
}

```

## disassembly

```asm
0x1400246a4  push    rbx
0x1400246a6  push    rbp
0x1400246a7  push    rsi
0x1400246a8  push    rdi
0x1400246a9  push    r12
0x1400246ab  push    r14
0x1400246ad  push    r15
0x1400246af  sub     rsp, 20h
0x1400246b3  mov     rbp, rcx
0x1400246b6  mov     esi, 1
0x1400246bb  mov     rcx, [rcx+10h]
0x1400246bf  test    rcx, rcx
0x1400246c2  cmovnz  rsi, rcx
0x1400246c6  mov     rax, rsi
0x1400246c9  sub     rax, rcx
0x1400246cc  cmp     rax, 1
0x1400246d0  jb      short loc_1400246D8
0x1400246d2  cmp     rsi, 8
0x1400246d6  jnb     short loc_1400246F3
0x1400246d8  mov     rax, 0FFFFFFFFFFFFFFFh
0x1400246e2  sub     rax, rsi
0x1400246e5  cmp     rax, rsi
0x1400246e8  jb      loc_14002486D
0x1400246ee  add     rsi, rsi
0x1400246f1  jmp     short loc_1400246C6
0x1400246f3  mov     rdi, [rbp+18h]
0x1400246f7  mov     rax, 1FFFFFFFFFFFFFFFh
0x140024701  cmp     rsi, rax
0x140024704  ja      loc_140024867
0x14002470a  lea     rcx, ds:0[rsi*8]; Size
0x140024712  test    rcx, rcx
0x140024715  jnz     short loc_14002471C
0x140024717  xor     r14d, r14d
0x14002471a  jmp     short loc_140024759
0x14002471c  cmp     rcx, 1000h
0x140024723  jb      short loc_140024751
0x140024725  lea     rax, [rcx+27h]
0x140024729  cmp     rax, rcx
0x14002472c  jbe     loc_140024867
0x140024732  mov     rcx, rax; Size
0x140024735  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002473a  test    rax, rax
0x14002473d  jz      loc_14002483E
0x140024743  lea     r14, [rax+27h]
0x140024747  and     r14, 0FFFFFFFFFFFFFFE0h
0x14002474b  mov     [r14-8], rax
0x14002474f  jmp     short loc_140024759
0x140024751  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140024756  mov     r14, rax
0x140024759  shr     rdi, 1
0x14002475c  mov     rax, rsi
0x14002475f  shr     rax, 1
0x140024762  lea     r15, ds:0[rdi*8]
0x14002476a  lea     r12, [r15+r14]
0x14002476e  jmp     short loc_140024773
0x140024770  add     rsi, rsi
0x140024773  cmp     rsi, rax
0x140024776  jbe     short loc_140024770
0x140024778  mov     rcx, [rbp+8]
0x14002477c  mov     rax, [rbp+10h]
0x140024780  sub     rsi, rax
0x140024783  shl     rax, 3
0x140024787  lea     rdx, [rcx+r15]; Src
0x14002478b  sub     rax, rdx
0x14002478e  lea     rbx, [rax+rcx]
0x140024792  mov     rcx, r12; void *
0x140024795  mov     r8, rbx; Size
0x140024798  call    memmove_0
0x14002479d  mov     rdx, [rbp+8]; Src
0x1400247a1  add     rbx, r12
0x1400247a4  mov     rcx, rbx; void *
0x1400247a7  cmp     rdi, rsi
0x1400247aa  ja      short loc_1400247D1
0x1400247ac  mov     r8, r15; Size
0x1400247af  call    memmove_0
0x1400247b4  mov     r8, rsi
0x1400247b7  lea     rcx, [rbx+r15]; void *
0x1400247bb  sub     r8, rdi
0x1400247be  xor     edx, edx; Val
0x1400247c0  shl     r8, 3; Size
0x1400247c4  call    memset_0
0x1400247c9  mov     r8, r15
0x1400247cc  mov     rcx, r14
0x1400247cf  jmp     short loc_140024802
0x1400247d1  lea     rdi, ds:0[rsi*8]
0x1400247d9  mov     r8, rdi; Size
0x1400247dc  call    memmove_0
0x1400247e1  mov     rax, [rbp+8]
0x1400247e5  mov     rcx, r14; void *
0x1400247e8  lea     rdx, [rdi+rax]; Src
0x1400247ec  sub     rax, rdx
0x1400247ef  lea     rbx, [rax+r15]
0x1400247f3  mov     r8, rbx; Size
0x1400247f6  call    memmove_0
0x1400247fb  lea     rcx, [rbx+r14]; void *
0x1400247ff  mov     r8, rdi; Size
0x140024802  xor     edx, edx; Val
0x140024804  call    memset_0
0x140024809  mov     rcx, [rbp+8]
0x14002480d  test    rcx, rcx
0x140024810  jz      short loc_140024850
0x140024812  mov     rax, [rbp+10h]
0x140024816  lea     rdx, ds:0[rax*8]
0x14002481e  cmp     rdx, 1000h
0x140024825  jb      short loc_140024845
0x140024827  mov     rax, [rcx-8]
0x14002482b  sub     rcx, rax
0x14002482e  sub     rcx, 8
0x140024832  cmp     rcx, 1Fh
0x140024836  ja      short loc_14002483E
0x140024838  add     rdx, 27h ; '''
0x14002483c  jmp     short loc_140024848
0x14002483e  mov     ecx, 5
0x140024843  int     29h; Win8: RtlFailFast(ecx)
0x140024845  mov     rax, rcx
0x140024848  mov     rcx, rax; Block
0x14002484b  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x140024850  add     [rbp+10h], rsi
0x140024854  mov     [rbp+8], r14
0x140024858  add     rsp, 20h
0x14002485c  pop     r15
0x14002485e  pop     r14
0x140024860  pop     r12
0x140024862  pop     rdi
0x140024863  pop     rsi
0x140024864  pop     rbp
0x140024865  pop     rbx
0x140024866  retn
0x140024867  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x14002486d  call    ?_Xlen@?$deque@PEAVJsonValue@@V?$allocator@PEAVJsonValue@@@std@@@std@@CAXXZ; std::deque<JsonValue *>::_Xlen(void)
```
