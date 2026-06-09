# std::vector<wchar_t,std::allocator<wchar_t>>::_Insert_n(std::_Vector_iterator<wchar_t,std::allocator<wchar_t>>,unsigned __int64,wchar_t const &)

- ea: `0x1800cf16c`
- end: `0x1800cf3d6`
- name: `?_Insert_n@?$vector@_WV?$allocator@_W@std@@@std@@IEAAXV?$_Vector_iterator@_WV?$allocator@_W@std@@@2@_KAEB_W@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800cf488`

## callees

- `0x180004d91`
- `0x1800111d0`
- `0x18009bd1c`
- `0x1800cf0fc`
- `0x1800cf16c`
- `0x1800cf5a0`

## import_xrefs

- `msvcrt!free` at `0x1800cf2e6`
- `msvcrt!free` at `0x1800cf2e6`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800cf241`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800cf241`
- `msvcrt!memmove_s` at `0x1800cf294`
- `msvcrt!memmove_s` at `0x1800cf2ca`
- `msvcrt!memmove_s` at `0x1800cf32e`
- `msvcrt!memmove_s` at `0x1800cf380`
- `msvcrt!memmove_s` at `0x1800cf3a5`
- `msvcrt!memmove_s` at `0x1800cf294`
- `msvcrt!memmove_s` at `0x1800cf2ca`
- `msvcrt!memmove_s` at `0x1800cf32e`
- `msvcrt!memmove_s` at `0x1800cf380`
- `msvcrt!memmove_s` at `0x1800cf3a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::vector<wchar_t>::_Insert_n(__int64 a1, char *a2, unsigned __int64 a3, __int16 *a4)
{
  __int16 v7; // r13
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned __int64 v14; // r15
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // r8
  unsigned __int64 v19; // rcx
  char *v20; // rax
  char *v21; // r12
  _BYTE *v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rdi
  char *v25; // r8
  unsigned __int64 v26; // rcx
  char *v27; // rdi
  __int64 v28; // rdx
  unsigned __int64 v29; // rdi
  void *v30; // rcx
  __int64 v31; // r15
  __int64 v32; // r12
  unsigned __int64 v33; // rdx
  char *v34; // rdi
  unsigned __int64 v35; // r14
  unsigned __int64 i; // rcx
  char *v37; // rdx
  rsize_t v38; // rdx
  rsize_t v39; // r14
  __int64 v40; // rdi
  _QWORD pExceptionObject[4]; // [rsp+20h] [rbp-48h] BYREF
  char *v42; // [rsp+70h] [rbp+8h] BYREF

  v7 = *a4;
  LOWORD(v42) = *a4;
  if ( *(_QWORD *)(a1 + 8) )
    v8 = (__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 8)) >> 1;
  else
    v8 = 0;
  if ( a3 )
  {
    if ( 0x7FFFFFFFFFFFFFFFLL - std::vector<wchar_t>::size(a1, v8) < a3 )
      std::vector<CAttachment>::_Xlen();
    v10 = std::vector<wchar_t>::size(a1, v9);
    if ( v11 >= a3 + v10 )
    {
      v31 = *(_QWORD *)(a1 + 16);
      v32 = 2 * v13;
      v33 = (v31 - (__int64)a2) >> 1;
      if ( v33 >= a3 )
      {
        v38 = 2 * (v32 >> 1);
        v39 = v38 + v31;
        if ( v32 >> 1 )
          memmove_s(*(void *const *)(a1 + 16), v38, (const void *const)(v31 - v32), 2 * (v32 >> 1));
        *(_QWORD *)(a1 + 16) = v39;
        v40 = (v31 - v32 - (__int64)a2) >> 1;
        if ( v40 > 0 )
          memmove_s((void *const)(v31 - 2 * v40), 2 * v40, a2, 2 * v40);
        v37 = &a2[v32];
      }
      else
      {
        if ( v33 )
          memmove_s(&a2[v32], 2 * v33, a2, 2 * v33);
        v34 = *(char **)(a1 + 16);
        v35 = a3 - ((v34 - a2) >> 1);
        if ( v35 )
        {
          for ( i = v35; i; --i )
          {
            *(_WORD *)v34 = v7;
            v34 += 2;
          }
        }
        v37 = *(char **)(a1 + 16);
        *(_QWORD *)(a1 + 16) = &v37[v32];
      }
      std::fill<wchar_t *,wchar_t>(a2, v37, &v42);
    }
    else
    {
      if ( 0x7FFFFFFFFFFFFFFFLL - (v11 >> 1) >= v11 )
        v14 = (v11 >> 1) + v11;
      else
        v14 = 0;
      if ( v14 < a3 + std::vector<wchar_t>::size(v12, v11) )
      {
        v17 = std::vector<wchar_t>::size(v16, v15);
        v14 = v18 + v17;
      }
      if ( v14 )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v14 < 2 )
        {
          v42 = 0;
          exception::exception((exception *)pExceptionObject, (const char *const *)&v42);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v19 = v14;
      }
      else
      {
        v19 = 0;
      }
      v20 = (char *)MmAllocate(2 * v19);
      v21 = v20;
      v42 = v20;
      try
      {
        v22 = *(_BYTE **)(a1 + 8);
        v23 = (a2 - v22) >> 1;
        v24 = 2 * v23;
        if ( v23 )
          memmove_s(v20, 2 * v23, v22, 2 * v23);
        v25 = &v21[v24];
        v26 = (2 * a3) >> 1;
        v27 = &v21[v24];
        while ( v26 )
        {
          *(_WORD *)v27 = v7;
          v27 += 2;
          --v26;
        }
        v28 = (__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)a2) >> 1;
        if ( v28 )
          memmove_s(&v25[2 * a3], 2 * v28, a2, 2 * v28);
      }
      catch ( ... )
      {
        free(v42);
        throw;
      }
      v29 = std::vector<wchar_t>::size(a1, v28) + a3;
      v30 = *(void **)(a1 + 8);
      if ( v30 )
        free(v30);
      *(_QWORD *)(a1 + 24) = &v21[2 * v14];
      *(_QWORD *)(a1 + 16) = &v21[2 * v29];
      *(_QWORD *)(a1 + 8) = v21;
    }
  }
}

```

## disassembly

```asm
0x1800cf16c  mov     [rsp+arg_8], rbx
0x1800cf171  mov     [rsp+arg_10], rsi
0x1800cf176  push    rdi
0x1800cf177  push    r12
0x1800cf179  push    r13
0x1800cf17b  push    r14
0x1800cf17d  push    r15
0x1800cf17f  sub     rsp, 40h
0x1800cf183  mov     r14, r8
0x1800cf186  mov     rbx, rdx
0x1800cf189  mov     rsi, rcx
0x1800cf18c  movzx   r13d, word ptr [r9]
0x1800cf190  mov     word ptr [rsp+68h+arg_0], r13w
0x1800cf196  cmp     qword ptr [rcx+8], 0
0x1800cf19b  jnz     short loc_1800CF1A1
0x1800cf19d  xor     edx, edx
0x1800cf19f  jmp     short loc_1800CF1AC
0x1800cf1a1  mov     rdx, [rcx+18h]
0x1800cf1a5  sub     rdx, [rcx+8]
0x1800cf1a9  sar     rdx, 1
0x1800cf1ac  test    r14, r14
0x1800cf1af  jz      loc_1800CF3BC
0x1800cf1b5  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x1800cf1ba  mov     rdi, 7FFFFFFFFFFFFFFFh
0x1800cf1c4  mov     rcx, rdi
0x1800cf1c7  sub     rcx, rax
0x1800cf1ca  cmp     rcx, r14
0x1800cf1cd  jnb     short loc_1800CF1D5
0x1800cf1cf  call    ?_Xlen@?$vector@VCAttachment@@V?$allocator@VCAttachment@@@std@@@std@@KAXXZ; std::vector<CAttachment>::_Xlen(void)
0x1800cf1d5  mov     rcx, rsi
0x1800cf1d8  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x1800cf1dd  add     rax, r14
0x1800cf1e0  cmp     rdx, rax
0x1800cf1e3  jnb     loc_1800CF306
0x1800cf1e9  mov     rax, rdx
0x1800cf1ec  shr     rax, 1
0x1800cf1ef  sub     rdi, rax
0x1800cf1f2  cmp     rdi, rdx
0x1800cf1f5  jnb     short loc_1800CF1FC
0x1800cf1f7  xor     r15d, r15d
0x1800cf1fa  jmp     short loc_1800CF200
0x1800cf1fc  lea     r15, [rax+rdx]
0x1800cf200  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x1800cf205  add     rax, r14
0x1800cf208  cmp     r15, rax
0x1800cf20b  jnb     short loc_1800CF216
0x1800cf20d  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x1800cf212  lea     r15, [r8+rax]
0x1800cf216  test    r15, r15
0x1800cf219  jnz     short loc_1800CF21F
0x1800cf21b  xor     ecx, ecx
0x1800cf21d  jmp     short loc_1800CF268
0x1800cf21f  xor     edx, edx
0x1800cf221  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800cf225  div     r15
0x1800cf228  cmp     rax, 2
0x1800cf22c  jnb     short loc_1800CF265
0x1800cf22e  mov     [rsp+68h+arg_0], 0
0x1800cf237  lea     rdx, [rsp+68h+arg_0]
0x1800cf23c  lea     rcx, [rsp+68h+pExceptionObject]
0x1800cf241  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x1800cf247  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800cf24e  mov     [rsp+68h+pExceptionObject], rax
0x1800cf253  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800cf25a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800cf25f  call    _CxxThrowException_0
0x1800cf265  mov     rcx, r15
0x1800cf268  add     rcx, rcx; unsigned __int64
0x1800cf26b  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800cf270  mov     r12, rax
0x1800cf273  mov     [rsp+68h+arg_0], rax
0x1800cf278  mov     r8, [rsi+8]; Source
0x1800cf27c  mov     rcx, rbx
0x1800cf27f  sub     rcx, r8
0x1800cf282  sar     rcx, 1
0x1800cf285  lea     rdi, [rcx+rcx]
0x1800cf289  jz      short loc_1800CF29A
0x1800cf28b  mov     r9, rdi; SourceSize
0x1800cf28e  mov     rdx, rdi; DestinationSize
0x1800cf291  mov     rcx, rax; Destination
0x1800cf294  call    cs:__imp_memmove_s
0x1800cf29a  lea     r8, [rdi+r12]
0x1800cf29e  lea     r9, [r14+r14]
0x1800cf2a2  mov     rcx, r9
0x1800cf2a5  shr     rcx, 1
0x1800cf2a8  mov     rax, r13
0x1800cf2ab  mov     rdi, r8
0x1800cf2ae  rep stosw
0x1800cf2b1  mov     rdx, [rsi+10h]
0x1800cf2b5  sub     rdx, rbx
0x1800cf2b8  sar     rdx, 1
0x1800cf2bb  jz      short loc_1800CF2D1
0x1800cf2bd  add     rdx, rdx; DestinationSize
0x1800cf2c0  lea     rcx, [r8+r9]; Destination
0x1800cf2c4  mov     r9, rdx; SourceSize
0x1800cf2c7  mov     r8, rbx; Source
0x1800cf2ca  call    cs:__imp_memmove_s
0x1800cf2d0  nop
0x1800cf2d1  mov     rcx, rsi
0x1800cf2d4  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x1800cf2d9  lea     rdi, [rax+r14]
0x1800cf2dd  mov     rcx, [rsi+8]; Block
0x1800cf2e1  test    rcx, rcx
0x1800cf2e4  jz      short loc_1800CF2ED
0x1800cf2e6  call    cs:__imp_free
0x1800cf2ec  nop
0x1800cf2ed  lea     rax, [r12+r15*2]
0x1800cf2f1  mov     [rsi+18h], rax
0x1800cf2f5  lea     rax, [r12+rdi*2]
0x1800cf2f9  mov     [rsi+10h], rax
0x1800cf2fd  mov     [rsi+8], r12
0x1800cf301  jmp     loc_1800CF3BC
0x1800cf306  mov     r15, [rsi+10h]
0x1800cf30a  lea     r12, [r8+r8]
0x1800cf30e  mov     rdx, r15
0x1800cf311  sub     rdx, rbx
0x1800cf314  sar     rdx, 1
0x1800cf317  cmp     rdx, r14
0x1800cf31a  jnb     short loc_1800CF35E
0x1800cf31c  test    rdx, rdx
0x1800cf31f  jz      short loc_1800CF335
0x1800cf321  add     rdx, rdx; DestinationSize
0x1800cf324  lea     rcx, [r12+rbx]; Destination
0x1800cf328  mov     r9, rdx; SourceSize
0x1800cf32b  mov     r8, rbx; Source
0x1800cf32e  call    cs:__imp_memmove_s
0x1800cf334  nop
0x1800cf335  mov     rdi, [rsi+10h]
0x1800cf339  mov     rax, rdi
0x1800cf33c  sub     rax, rbx
0x1800cf33f  sar     rax, 1
0x1800cf342  sub     r14, rax
0x1800cf345  jz      short loc_1800CF350
0x1800cf347  mov     rax, r13
0x1800cf34a  mov     rcx, r14
0x1800cf34d  rep stosw
0x1800cf350  mov     rdx, [rsi+10h]
0x1800cf354  lea     rax, [r12+rdx]
0x1800cf358  mov     [rsi+10h], rax
0x1800cf35c  jmp     short loc_1800CF3AF
0x1800cf35e  mov     rax, r12
0x1800cf361  sar     rax, 1
0x1800cf364  lea     rdx, [rax+rax]; DestinationSize
0x1800cf368  lea     r14, [rdx+r15]
0x1800cf36c  mov     rdi, r15
0x1800cf36f  sub     rdi, r12
0x1800cf372  test    rax, rax
0x1800cf375  jz      short loc_1800CF386
0x1800cf377  mov     r9, rdx; SourceSize
0x1800cf37a  mov     r8, rdi; Source
0x1800cf37d  mov     rcx, r15; Destination
0x1800cf380  call    cs:__imp_memmove_s
0x1800cf386  mov     [rsi+10h], r14
0x1800cf38a  sub     rdi, rbx
0x1800cf38d  sar     rdi, 1
0x1800cf390  test    rdi, rdi
0x1800cf393  jle     short loc_1800CF3AB
0x1800cf395  lea     rdx, [rdi+rdi]; DestinationSize
0x1800cf399  sub     r15, rdx
0x1800cf39c  mov     r9, rdx; SourceSize
0x1800cf39f  mov     r8, rbx; Source
0x1800cf3a2  mov     rcx, r15; Destination
0x1800cf3a5  call    cs:__imp_memmove_s
0x1800cf3ab  lea     rdx, [r12+rbx]
0x1800cf3af  lea     r8, [rsp+68h+arg_0]
0x1800cf3b4  mov     rcx, rbx
0x1800cf3b7  call    ??$fill@PEA_W_W@std@@YAXPEA_W0AEB_W@Z; std::fill<wchar_t *,wchar_t>(wchar_t *,wchar_t *,wchar_t const &)
0x1800cf3bc  lea     r11, [rsp+68h+var_28]
0x1800cf3c1  mov     rbx, [r11+38h]
0x1800cf3c5  mov     rsi, [r11+40h]
0x1800cf3c9  mov     rsp, r11
0x1800cf3cc  pop     r15
0x1800cf3ce  pop     r14
0x1800cf3d0  pop     r13
0x1800cf3d2  pop     r12
0x1800cf3d4  pop     rdi
0x1800cf3d5  retn
```
