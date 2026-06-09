# std::vector<uint,std::allocator<uint>>::_Insert_n(std::_Vector_iterator<uint,std::allocator<uint>>,unsigned __int64,uint const &)

- ea: `0x180099f08`
- end: `0x18009a193`
- name: `?_Insert_n@?$vector@IV?$allocator@I@std@@@std@@IEAAXV?$_Vector_iterator@IV?$allocator@I@std@@@2@_KAEBI@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18009a240`

## callees

- `0x180004d91`
- `0x1800111d0`
- `0x1800994d4`
- `0x180099f08`
- `0x18009a29c`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x18009a093`
- `msvcrt!free` at `0x18009a093`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180099fdc`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180099fdc`
- `msvcrt!memmove_s` at `0x18009a038`
- `msvcrt!memmove_s` at `0x18009a077`
- `msvcrt!memmove_s` at `0x18009a0e1`
- `msvcrt!memmove_s` at `0x18009a138`
- `msvcrt!memmove_s` at `0x18009a162`
- `msvcrt!memmove_s` at `0x18009a038`
- `msvcrt!memmove_s` at `0x18009a077`
- `msvcrt!memmove_s` at `0x18009a0e1`
- `msvcrt!memmove_s` at `0x18009a138`
- `msvcrt!memmove_s` at `0x18009a162`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::vector<unsigned int>::_Insert_n(__int64 a1, char *a2, unsigned __int64 a3, int *a4)
{
  int v7; // r13d
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
  LODWORD(v42) = *a4;
  if ( *(_QWORD *)(a1 + 8) )
    v8 = (__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 8)) >> 2;
  else
    v8 = 0;
  if ( a3 )
  {
    if ( 0x3FFFFFFFFFFFFFFFLL - std::vector<unsigned int>::size(a1, v8) < a3 )
      std::vector<CAttachment>::_Xlen();
    v10 = std::vector<unsigned int>::size(a1, v9);
    if ( v11 >= a3 + v10 )
    {
      v31 = *(_QWORD *)(a1 + 16);
      v32 = 4 * v13;
      v33 = (v31 - (__int64)a2) >> 2;
      if ( v33 >= a3 )
      {
        v38 = 4 * (v32 >> 2);
        v39 = v38 + v31;
        if ( v32 >> 2 )
          memmove_s(*(void *const *)(a1 + 16), v38, (const void *const)(v31 - v32), 4 * (v32 >> 2));
        *(_QWORD *)(a1 + 16) = v39;
        v40 = (v31 - v32 - (__int64)a2) >> 2;
        if ( v40 > 0 )
          memmove_s((void *const)(v31 - 4 * v40), 4 * v40, a2, 4 * v40);
        v37 = &a2[v32];
      }
      else
      {
        if ( v33 )
          memmove_s(&a2[v32], 4 * v33, a2, 4 * v33);
        v34 = *(char **)(a1 + 16);
        v35 = a3 - ((v34 - a2) >> 2);
        if ( v35 )
        {
          for ( i = v35; i; --i )
          {
            *(_DWORD *)v34 = v7;
            v34 += 4;
          }
        }
        v37 = *(char **)(a1 + 16);
        *(_QWORD *)(a1 + 16) = &v37[v32];
      }
      std::fill<unsigned int *,unsigned int>(a2, v37, &v42);
    }
    else
    {
      if ( 0x3FFFFFFFFFFFFFFFLL - (v11 >> 1) >= v11 )
        v14 = (v11 >> 1) + v11;
      else
        v14 = 0;
      if ( v14 < a3 + std::vector<unsigned int>::size(v12, v11) )
      {
        v17 = std::vector<unsigned int>::size(v16, v15);
        v14 = v18 + v17;
      }
      if ( v14 )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v14 < 4 )
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
      v20 = (char *)MmAllocate(4 * v19);
      v21 = v20;
      v42 = v20;
      try
      {
        v22 = *(_BYTE **)(a1 + 8);
        v23 = (a2 - v22) >> 2;
        v24 = 4 * v23;
        if ( v23 )
          memmove_s(v20, 4 * v23, v22, 4 * v23);
        v25 = &v21[v24];
        v26 = (4 * a3) >> 2;
        v27 = &v21[v24];
        while ( v26 )
        {
          *(_DWORD *)v27 = v7;
          v27 += 4;
          --v26;
        }
        v28 = (__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)a2) >> 2;
        if ( v28 )
          memmove_s(&v25[4 * a3], 4 * v28, a2, 4 * v28);
      }
      catch ( ... )
      {
        free(v42);
        throw;
      }
      v29 = std::vector<unsigned int>::size(a1, v28) + a3;
      v30 = *(void **)(a1 + 8);
      if ( v30 )
        free(v30);
      *(_QWORD *)(a1 + 24) = &v21[4 * v14];
      *(_QWORD *)(a1 + 16) = &v21[4 * v29];
      *(_QWORD *)(a1 + 8) = v21;
    }
  }
}

```

## disassembly

```asm
0x180099f08  mov     [rsp+arg_8], rbx
0x180099f0d  mov     [rsp+arg_10], rsi
0x180099f12  push    rdi
0x180099f13  push    r12
0x180099f15  push    r13
0x180099f17  push    r14
0x180099f19  push    r15
0x180099f1b  sub     rsp, 40h
0x180099f1f  mov     r14, r8
0x180099f22  mov     rbx, rdx
0x180099f25  mov     rsi, rcx
0x180099f28  mov     r13d, [r9]
0x180099f2b  mov     dword ptr [rsp+68h+arg_0], r13d
0x180099f30  cmp     qword ptr [rcx+8], 0
0x180099f35  jnz     short loc_180099F3B
0x180099f37  xor     edx, edx
0x180099f39  jmp     short loc_180099F47
0x180099f3b  mov     rdx, [rcx+18h]
0x180099f3f  sub     rdx, [rcx+8]
0x180099f43  sar     rdx, 2
0x180099f47  test    r14, r14
0x180099f4a  jz      loc_18009A179
0x180099f50  call    ?size@?$vector@IV?$allocator@I@std@@@std@@QEBA_KXZ; std::vector<uint>::size(void)
0x180099f55  mov     rdi, 3FFFFFFFFFFFFFFFh
0x180099f5f  mov     rcx, rdi
0x180099f62  sub     rcx, rax
0x180099f65  cmp     rcx, r14
0x180099f68  jnb     short loc_180099F70
0x180099f6a  call    ?_Xlen@?$vector@VCAttachment@@V?$allocator@VCAttachment@@@std@@@std@@KAXXZ; std::vector<CAttachment>::_Xlen(void)
0x180099f70  mov     rcx, rsi
0x180099f73  call    ?size@?$vector@IV?$allocator@I@std@@@std@@QEBA_KXZ; std::vector<uint>::size(void)
0x180099f78  add     rax, r14
0x180099f7b  cmp     rdx, rax
0x180099f7e  jnb     loc_18009A0B3
0x180099f84  mov     rax, rdx
0x180099f87  shr     rax, 1
0x180099f8a  sub     rdi, rax
0x180099f8d  cmp     rdi, rdx
0x180099f90  jnb     short loc_180099F97
0x180099f92  xor     r15d, r15d
0x180099f95  jmp     short loc_180099F9B
0x180099f97  lea     r15, [rax+rdx]
0x180099f9b  call    ?size@?$vector@IV?$allocator@I@std@@@std@@QEBA_KXZ; std::vector<uint>::size(void)
0x180099fa0  add     rax, r14
0x180099fa3  cmp     r15, rax
0x180099fa6  jnb     short loc_180099FB1
0x180099fa8  call    ?size@?$vector@IV?$allocator@I@std@@@std@@QEBA_KXZ; std::vector<uint>::size(void)
0x180099fad  lea     r15, [r8+rax]
0x180099fb1  test    r15, r15
0x180099fb4  jnz     short loc_180099FBA
0x180099fb6  xor     ecx, ecx
0x180099fb8  jmp     short loc_18009A003
0x180099fba  xor     edx, edx
0x180099fbc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180099fc0  div     r15
0x180099fc3  cmp     rax, 4
0x180099fc7  jnb     short loc_18009A000
0x180099fc9  mov     [rsp+68h+arg_0], 0
0x180099fd2  lea     rdx, [rsp+68h+arg_0]
0x180099fd7  lea     rcx, [rsp+68h+pExceptionObject]
0x180099fdc  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180099fe2  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180099fe9  mov     [rsp+68h+pExceptionObject], rax
0x180099fee  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180099ff5  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180099ffa  call    _CxxThrowException_0
0x18009a000  mov     rcx, r15
0x18009a003  shl     rcx, 2; unsigned __int64
0x18009a007  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18009a00c  mov     r12, rax
0x18009a00f  mov     [rsp+68h+arg_0], rax
0x18009a014  mov     r8, [rsi+8]; Source
0x18009a018  mov     rcx, rbx
0x18009a01b  sub     rcx, r8
0x18009a01e  sar     rcx, 2
0x18009a022  lea     rdi, ds:0[rcx*4]
0x18009a02a  test    rcx, rcx
0x18009a02d  jz      short loc_18009A03E
0x18009a02f  mov     r9, rdi; SourceSize
0x18009a032  mov     rdx, rdi; DestinationSize
0x18009a035  mov     rcx, rax; Destination
0x18009a038  call    cs:__imp_memmove_s
0x18009a03e  lea     r8, [rdi+r12]
0x18009a042  lea     r9, ds:0[r14*4]
0x18009a04a  mov     rcx, r9
0x18009a04d  shr     rcx, 2
0x18009a051  mov     rax, r13
0x18009a054  mov     rdi, r8
0x18009a057  rep stosd
0x18009a059  mov     rdx, [rsi+10h]
0x18009a05d  sub     rdx, rbx
0x18009a060  sar     rdx, 2
0x18009a064  test    rdx, rdx
0x18009a067  jz      short loc_18009A07E
0x18009a069  shl     rdx, 2; DestinationSize
0x18009a06d  lea     rcx, [r8+r9]; Destination
0x18009a071  mov     r9, rdx; SourceSize
0x18009a074  mov     r8, rbx; Source
0x18009a077  call    cs:__imp_memmove_s
0x18009a07d  nop
0x18009a07e  mov     rcx, rsi
0x18009a081  call    ?size@?$vector@IV?$allocator@I@std@@@std@@QEBA_KXZ; std::vector<uint>::size(void)
0x18009a086  lea     rdi, [rax+r14]
0x18009a08a  mov     rcx, [rsi+8]; Block
0x18009a08e  test    rcx, rcx
0x18009a091  jz      short loc_18009A09A
0x18009a093  call    cs:__imp_free
0x18009a099  nop
0x18009a09a  lea     rax, [r12+r15*4]
0x18009a09e  mov     [rsi+18h], rax
0x18009a0a2  lea     rax, [r12+rdi*4]
0x18009a0a6  mov     [rsi+10h], rax
0x18009a0aa  mov     [rsi+8], r12
0x18009a0ae  jmp     loc_18009A179
0x18009a0b3  mov     r15, [rsi+10h]
0x18009a0b7  lea     r12, ds:0[r8*4]
0x18009a0bf  mov     rdx, r15
0x18009a0c2  sub     rdx, rbx
0x18009a0c5  sar     rdx, 2
0x18009a0c9  cmp     rdx, r14
0x18009a0cc  jnb     short loc_18009A111
0x18009a0ce  test    rdx, rdx
0x18009a0d1  jz      short loc_18009A0E8
0x18009a0d3  shl     rdx, 2; DestinationSize
0x18009a0d7  lea     rcx, [r12+rbx]; Destination
0x18009a0db  mov     r9, rdx; SourceSize
0x18009a0de  mov     r8, rbx; Source
0x18009a0e1  call    cs:__imp_memmove_s
0x18009a0e7  nop
0x18009a0e8  mov     rdi, [rsi+10h]
0x18009a0ec  mov     rax, rdi
0x18009a0ef  sub     rax, rbx
0x18009a0f2  sar     rax, 2
0x18009a0f6  sub     r14, rax
0x18009a0f9  jz      short loc_18009A103
0x18009a0fb  mov     rax, r13
0x18009a0fe  mov     rcx, r14
0x18009a101  rep stosd
0x18009a103  mov     rdx, [rsi+10h]
0x18009a107  lea     rax, [r12+rdx]
0x18009a10b  mov     [rsi+10h], rax
0x18009a10f  jmp     short loc_18009A16C
0x18009a111  mov     rax, r12
0x18009a114  sar     rax, 2
0x18009a118  lea     rdx, ds:0[rax*4]; DestinationSize
0x18009a120  lea     r14, [rdx+r15]
0x18009a124  mov     rdi, r15
0x18009a127  sub     rdi, r12
0x18009a12a  test    rax, rax
0x18009a12d  jz      short loc_18009A13E
0x18009a12f  mov     r9, rdx; SourceSize
0x18009a132  mov     r8, rdi; Source
0x18009a135  mov     rcx, r15; Destination
0x18009a138  call    cs:__imp_memmove_s
0x18009a13e  mov     [rsi+10h], r14
0x18009a142  sub     rdi, rbx
0x18009a145  sar     rdi, 2
0x18009a149  test    rdi, rdi
0x18009a14c  jle     short loc_18009A168
0x18009a14e  lea     rdx, ds:0[rdi*4]; DestinationSize
0x18009a156  sub     r15, rdx
0x18009a159  mov     r9, rdx; SourceSize
0x18009a15c  mov     r8, rbx; Source
0x18009a15f  mov     rcx, r15; Destination
0x18009a162  call    cs:__imp_memmove_s
0x18009a168  lea     rdx, [r12+rbx]
0x18009a16c  lea     r8, [rsp+68h+arg_0]
0x18009a171  mov     rcx, rbx
0x18009a174  call    ??$fill@PEAII@std@@YAXPEAI0AEBI@Z; std::fill<uint *,uint>(uint *,uint *,uint const &)
0x18009a179  lea     r11, [rsp+68h+var_28]
0x18009a17e  mov     rbx, [r11+38h]
0x18009a182  mov     rsi, [r11+40h]
0x18009a186  mov     rsp, r11
0x18009a189  pop     r15
0x18009a18b  pop     r14
0x18009a18d  pop     r13
0x18009a18f  pop     r12
0x18009a191  pop     rdi
0x18009a192  retn
```
