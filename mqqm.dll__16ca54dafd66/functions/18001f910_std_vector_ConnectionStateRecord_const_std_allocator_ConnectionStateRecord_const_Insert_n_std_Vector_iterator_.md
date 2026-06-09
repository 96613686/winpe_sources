# std::vector<ConnectionStateRecord const *,std::allocator<ConnectionStateRecord const *>>::_Insert_n(std::_Vector_iterator<ConnectionStateRecord const *,std::allocator<ConnectionStateRecord const *>>,unsigned __int64,ConnectionStateRecord const * const &)

- ea: `0x18001f910`
- end: `0x18001fba0`
- name: `?_Insert_n@?$vector@PEBVConnectionStateRecord@@V?$allocator@PEBVConnectionStateRecord@@@std@@@std@@IEAAXV?$_Vector_iterator@PEBVConnectionStateRecord@@V?$allocator@PEBVConnectionStateRecord@@@std@@@2@_KAEBQEBVConnectionStateRecord@@@Z`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001d880`

## callees

- `0x180004d91`
- `0x1800111d0`
- `0x180011540`
- `0x18001d810`
- `0x18001f910`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x18001fa9f`
- `msvcrt!free` at `0x18001fa9f`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001f9e7`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001f9e7`
- `msvcrt!memmove_s` at `0x18001fa43`
- `msvcrt!memmove_s` at `0x18001fa83`
- `msvcrt!memmove_s` at `0x18001faed`
- `msvcrt!memmove_s` at `0x18001fb45`
- `msvcrt!memmove_s` at `0x18001fb6f`
- `msvcrt!memmove_s` at `0x18001fa43`
- `msvcrt!memmove_s` at `0x18001fa83`
- `msvcrt!memmove_s` at `0x18001faed`
- `msvcrt!memmove_s` at `0x18001fb45`
- `msvcrt!memmove_s` at `0x18001fb6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::vector<ConnectionStateRecord const *>::_Insert_n(
        __int64 a1,
        char *a2,
        unsigned __int64 a3,
        const char **a4)
{
  const char *v7; // r13
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
  __int64 v25; // rdx
  unsigned __int64 v26; // rdi
  void *v27; // rcx
  __int64 v28; // r15
  __int64 v29; // r12
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // r14
  char *v32; // rdx
  rsize_t v33; // rdx
  rsize_t v34; // r14
  __int64 v35; // rdi
  _QWORD pExceptionObject[4]; // [rsp+20h] [rbp-48h] BYREF
  char *v37; // [rsp+70h] [rbp+8h] BYREF

  v7 = *a4;
  v37 = (char *)*a4;
  if ( *(_QWORD *)(a1 + 8) )
    v8 = (__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 8)) >> 3;
  else
    v8 = 0;
  if ( a3 )
  {
    if ( 0x1FFFFFFFFFFFFFFFLL - std::vector<CXdsReferenceValidateInfo *>::size(a1, v8) < a3 )
      std::vector<CAttachment>::_Xlen();
    v10 = std::vector<CXdsReferenceValidateInfo *>::size(a1, v9);
    if ( v11 >= a3 + v10 )
    {
      v28 = *(_QWORD *)(a1 + 16);
      v29 = 8 * v13;
      v30 = (v28 - (__int64)a2) >> 3;
      if ( v30 >= a3 )
      {
        v33 = 8 * (v29 >> 3);
        v34 = v33 + v28;
        if ( v29 >> 3 )
          memmove_s(*(void *const *)(a1 + 16), v33, (const void *const)(v28 - v29), 8 * (v29 >> 3));
        *(_QWORD *)(a1 + 16) = v34;
        v35 = (v28 - v29 - (__int64)a2) >> 3;
        if ( v35 > 0 )
          memmove_s((void *const)(v28 - 8 * v35), 8 * v35, a2, 8 * v35);
        v32 = &a2[v29];
      }
      else
      {
        if ( v30 )
          memmove_s(&a2[v29], 8 * v30, a2, 8 * v30);
        v31 = a3 - ((__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)a2) >> 3);
        if ( v31 )
          memset64(*(void **)(a1 + 16), (unsigned __int64)v7, v31);
        v32 = *(char **)(a1 + 16);
        *(_QWORD *)(a1 + 16) = &v32[v29];
      }
      std::fill<COldRemoteRead * *,COldRemoteRead *>(a2, v32, &v37);
    }
    else
    {
      if ( 0x1FFFFFFFFFFFFFFFLL - (v11 >> 1) >= v11 )
        v14 = (v11 >> 1) + v11;
      else
        v14 = 0;
      if ( v14 < a3 + std::vector<CXdsReferenceValidateInfo *>::size(v12, v11) )
      {
        v17 = std::vector<CXdsReferenceValidateInfo *>::size(v16, v15);
        v14 = v18 + v17;
      }
      if ( v14 )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v14 < 8 )
        {
          v37 = 0;
          exception::exception((exception *)pExceptionObject, (const char *const *)&v37);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v19 = v14;
      }
      else
      {
        v19 = 0;
      }
      v20 = (char *)MmAllocate(8 * v19);
      v21 = v20;
      v37 = v20;
      try
      {
        v22 = *(_BYTE **)(a1 + 8);
        v23 = (a2 - v22) >> 3;
        v24 = 8 * v23;
        if ( v23 )
          memmove_s(v20, 8 * v23, v22, 8 * v23);
        memset64(&v21[v24], (unsigned __int64)v7, a3 & 0x1FFFFFFFFFFFFFFFLL);
        v25 = (__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)a2) >> 3;
        if ( v25 )
          memmove_s(&v21[8 * a3 + v24], 8 * v25, a2, 8 * v25);
      }
      catch ( ... )
      {
        free(v37);
        throw;
      }
      v26 = std::vector<CXdsReferenceValidateInfo *>::size(a1, v25) + a3;
      v27 = *(void **)(a1 + 8);
      if ( v27 )
        free(v27);
      *(_QWORD *)(a1 + 24) = &v21[8 * v14];
      *(_QWORD *)(a1 + 16) = &v21[8 * v26];
      *(_QWORD *)(a1 + 8) = v21;
    }
  }
}

```

## disassembly

```asm
0x18001f910  mov     [rsp+arg_8], rbx
0x18001f915  mov     [rsp+arg_10], rsi
0x18001f91a  push    rdi
0x18001f91b  push    r12
0x18001f91d  push    r13
0x18001f91f  push    r14
0x18001f921  push    r15
0x18001f923  sub     rsp, 40h
0x18001f927  mov     r14, r8
0x18001f92a  mov     rbx, rdx
0x18001f92d  mov     rsi, rcx
0x18001f930  mov     r13, [r9]
0x18001f933  mov     [rsp+68h+arg_0], r13
0x18001f938  cmp     qword ptr [rcx+8], 0
0x18001f93d  jnz     short loc_18001F943
0x18001f93f  xor     edx, edx
0x18001f941  jmp     short loc_18001F94F
0x18001f943  mov     rdx, [rcx+18h]
0x18001f947  sub     rdx, [rcx+8]
0x18001f94b  sar     rdx, 3
0x18001f94f  test    r14, r14
0x18001f952  jz      loc_18001FB86
0x18001f958  call    ?size@?$vector@PEAVCXdsReferenceValidateInfo@@V?$allocator@PEAVCXdsReferenceValidateInfo@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceValidateInfo *>::size(void)
0x18001f95d  mov     rcx, rax
0x18001f960  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18001f96a  mov     rax, rdi
0x18001f96d  sub     rax, rcx
0x18001f970  cmp     rax, r14
0x18001f973  jnb     short loc_18001F97B
0x18001f975  call    ?_Xlen@?$vector@VCAttachment@@V?$allocator@VCAttachment@@@std@@@std@@KAXXZ; std::vector<CAttachment>::_Xlen(void)
0x18001f97b  mov     rcx, rsi
0x18001f97e  call    ?size@?$vector@PEAVCXdsReferenceValidateInfo@@V?$allocator@PEAVCXdsReferenceValidateInfo@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceValidateInfo *>::size(void)
0x18001f983  add     rax, r14
0x18001f986  cmp     rdx, rax
0x18001f989  jnb     loc_18001FABF
0x18001f98f  mov     rax, rdx
0x18001f992  shr     rax, 1
0x18001f995  sub     rdi, rax
0x18001f998  cmp     rdi, rdx
0x18001f99b  jnb     short loc_18001F9A2
0x18001f99d  xor     r15d, r15d
0x18001f9a0  jmp     short loc_18001F9A6
0x18001f9a2  lea     r15, [rax+rdx]
0x18001f9a6  call    ?size@?$vector@PEAVCXdsReferenceValidateInfo@@V?$allocator@PEAVCXdsReferenceValidateInfo@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceValidateInfo *>::size(void)
0x18001f9ab  add     rax, r14
0x18001f9ae  cmp     r15, rax
0x18001f9b1  jnb     short loc_18001F9BC
0x18001f9b3  call    ?size@?$vector@PEAVCXdsReferenceValidateInfo@@V?$allocator@PEAVCXdsReferenceValidateInfo@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceValidateInfo *>::size(void)
0x18001f9b8  lea     r15, [r8+rax]
0x18001f9bc  test    r15, r15
0x18001f9bf  jnz     short loc_18001F9C5
0x18001f9c1  xor     ecx, ecx
0x18001f9c3  jmp     short loc_18001FA0E
0x18001f9c5  xor     edx, edx
0x18001f9c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f9cb  div     r15
0x18001f9ce  cmp     rax, 8
0x18001f9d2  jnb     short loc_18001FA0B
0x18001f9d4  mov     [rsp+68h+arg_0], 0
0x18001f9dd  lea     rdx, [rsp+68h+arg_0]
0x18001f9e2  lea     rcx, [rsp+68h+pExceptionObject]
0x18001f9e7  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18001f9ed  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001f9f4  mov     [rsp+68h+pExceptionObject], rax
0x18001f9f9  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001fa00  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001fa05  call    _CxxThrowException_0
0x18001fa0b  mov     rcx, r15
0x18001fa0e  shl     rcx, 3; unsigned __int64
0x18001fa12  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001fa17  mov     r12, rax
0x18001fa1a  mov     [rsp+68h+arg_0], rax
0x18001fa1f  mov     r8, [rsi+8]; Source
0x18001fa23  mov     rcx, rbx
0x18001fa26  sub     rcx, r8
0x18001fa29  sar     rcx, 3
0x18001fa2d  lea     rdi, ds:0[rcx*8]
0x18001fa35  test    rcx, rcx
0x18001fa38  jz      short loc_18001FA49
0x18001fa3a  mov     r9, rdi; SourceSize
0x18001fa3d  mov     rdx, rdi; DestinationSize
0x18001fa40  mov     rcx, rax; Destination
0x18001fa43  call    cs:__imp_memmove_s
0x18001fa49  lea     r8, [rdi+r12]
0x18001fa4d  lea     r9, ds:0[r14*8]
0x18001fa55  mov     rcx, r9
0x18001fa58  shr     rcx, 3
0x18001fa5c  mov     rdi, r8
0x18001fa5f  mov     rax, r13
0x18001fa62  rep stosq
0x18001fa65  mov     rdx, [rsi+10h]
0x18001fa69  sub     rdx, rbx
0x18001fa6c  sar     rdx, 3
0x18001fa70  test    rdx, rdx
0x18001fa73  jz      short loc_18001FA8A
0x18001fa75  shl     rdx, 3; DestinationSize
0x18001fa79  lea     rcx, [r8+r9]; Destination
0x18001fa7d  mov     r9, rdx; SourceSize
0x18001fa80  mov     r8, rbx; Source
0x18001fa83  call    cs:__imp_memmove_s
0x18001fa89  nop
0x18001fa8a  mov     rcx, rsi
0x18001fa8d  call    ?size@?$vector@PEAVCXdsReferenceValidateInfo@@V?$allocator@PEAVCXdsReferenceValidateInfo@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceValidateInfo *>::size(void)
0x18001fa92  lea     rdi, [rax+r14]
0x18001fa96  mov     rcx, [rsi+8]; Block
0x18001fa9a  test    rcx, rcx
0x18001fa9d  jz      short loc_18001FAA6
0x18001fa9f  call    cs:__imp_free
0x18001faa5  nop
0x18001faa6  lea     rax, [r12+r15*8]
0x18001faaa  mov     [rsi+18h], rax
0x18001faae  lea     rax, [r12+rdi*8]
0x18001fab2  mov     [rsi+10h], rax
0x18001fab6  mov     [rsi+8], r12
0x18001faba  jmp     loc_18001FB86
0x18001fabf  mov     r15, [rsi+10h]
0x18001fac3  lea     r12, ds:0[r8*8]
0x18001facb  mov     rdx, r15
0x18001face  sub     rdx, rbx
0x18001fad1  sar     rdx, 3
0x18001fad5  cmp     rdx, r14
0x18001fad8  jnb     short loc_18001FB1E
0x18001fada  test    rdx, rdx
0x18001fadd  jz      short loc_18001FAF4
0x18001fadf  shl     rdx, 3; DestinationSize
0x18001fae3  lea     rcx, [r12+rbx]; Destination
0x18001fae7  mov     r9, rdx; SourceSize
0x18001faea  mov     r8, rbx; Source
0x18001faed  call    cs:__imp_memmove_s
0x18001faf3  nop
0x18001faf4  mov     rdi, [rsi+10h]
0x18001faf8  mov     rax, rdi
0x18001fafb  sub     rax, rbx
0x18001fafe  sar     rax, 3
0x18001fb02  sub     r14, rax
0x18001fb05  jz      short loc_18001FB10
0x18001fb07  mov     rax, r13
0x18001fb0a  mov     rcx, r14
0x18001fb0d  rep stosq
0x18001fb10  mov     rdx, [rsi+10h]
0x18001fb14  lea     rax, [r12+rdx]
0x18001fb18  mov     [rsi+10h], rax
0x18001fb1c  jmp     short loc_18001FB79
0x18001fb1e  mov     rax, r12
0x18001fb21  sar     rax, 3
0x18001fb25  lea     rdx, ds:0[rax*8]; DestinationSize
0x18001fb2d  lea     r14, [rdx+r15]
0x18001fb31  mov     rdi, r15
0x18001fb34  sub     rdi, r12
0x18001fb37  test    rax, rax
0x18001fb3a  jz      short loc_18001FB4B
0x18001fb3c  mov     r9, rdx; SourceSize
0x18001fb3f  mov     r8, rdi; Source
0x18001fb42  mov     rcx, r15; Destination
0x18001fb45  call    cs:__imp_memmove_s
0x18001fb4b  mov     [rsi+10h], r14
0x18001fb4f  sub     rdi, rbx
0x18001fb52  sar     rdi, 3
0x18001fb56  test    rdi, rdi
0x18001fb59  jle     short loc_18001FB75
0x18001fb5b  lea     rdx, ds:0[rdi*8]; DestinationSize
0x18001fb63  sub     r15, rdx
0x18001fb66  mov     r9, rdx; SourceSize
0x18001fb69  mov     r8, rbx; Source
0x18001fb6c  mov     rcx, r15; Destination
0x18001fb6f  call    cs:__imp_memmove_s
0x18001fb75  lea     rdx, [r12+rbx]
0x18001fb79  lea     r8, [rsp+68h+arg_0]
0x18001fb7e  mov     rcx, rbx
0x18001fb81  call    ??$fill@PEAPEAVCOldRemoteRead@@PEAV1@@std@@YAXPEAPEAVCOldRemoteRead@@0AEBQEAV1@@Z; std::fill<COldRemoteRead * *,COldRemoteRead *>(COldRemoteRead * *,COldRemoteRead * *,COldRemoteRead * const &)
0x18001fb86  lea     r11, [rsp+68h+var_28]
0x18001fb8b  mov     rbx, [r11+38h]
0x18001fb8f  mov     rsi, [r11+40h]
0x18001fb93  mov     rsp, r11
0x18001fb96  pop     r15
0x18001fb98  pop     r14
0x18001fb9a  pop     r13
0x18001fb9c  pop     r12
0x18001fb9e  pop     rdi
0x18001fb9f  retn
```
