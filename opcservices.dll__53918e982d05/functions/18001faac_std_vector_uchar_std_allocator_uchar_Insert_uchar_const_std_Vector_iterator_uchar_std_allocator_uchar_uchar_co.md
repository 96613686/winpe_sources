# std::vector<uchar,std::allocator<uchar>>::_Insert<uchar const *>(std::_Vector_iterator<uchar,std::allocator<uchar>>,uchar const *,uchar const *,std::forward_iterator_tag)

- ea: `0x18001faac`
- end: `0x18001fd3f`
- name: `??$_Insert@PEBE@?$vector@EV?$allocator@E@std@@@std@@QEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@1@PEBE1Uforward_iterator_tag@1@@Z`
- size: `659`
- prototype: `char *__fastcall(__int64, _BYTE *, char *, __int64)`
- caller_count: `11`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001d7d8`
- `0x180020c18`
- `0x18005a584`
- `0x18006a6fc`
- `0x18006bbb4`
- `0x18006c4a0`
- `0x18006f29c`
- `0x180084e3c`
- `0x1800851fc`
- `0x1800b3e64`
- `0x180117794`

## callees

- `0x18000171c`
- `0x18001faac`
- `0x1800761c0`
- `0x1800b3d2c`
- `0x1800cd178`
- `0x1800cd1c4`
- `0x1800cd6fc`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001fbd3`
- `msvcrt!memmove_s` at `0x18001fbea`
- `msvcrt!memmove_s` at `0x18001fc02`
- `msvcrt!memmove_s` at `0x18001fc86`
- `msvcrt!memmove_s` at `0x18001fca6`
- `msvcrt!memmove_s` at `0x18001fcd2`
- `msvcrt!memmove_s` at `0x18001fbd3`
- `msvcrt!memmove_s` at `0x18001fbea`
- `msvcrt!memmove_s` at `0x18001fc02`
- `msvcrt!memmove_s` at `0x18001fc86`
- `msvcrt!memmove_s` at `0x18001fca6`
- `msvcrt!memmove_s` at `0x18001fcd2`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001fd1b`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001fd1b`

## pseudocode

```c
char *__fastcall std::vector<unsigned char>::_Insert<unsigned char const *>(
        __int64 a1,
        _BYTE *a2,
        char *a3,
        __int64 a4)
{
  char *result; // rax
  rsize_t v9; // rdi
  __int64 v10; // rdx
  unsigned __int64 v11; // r10
  void **v12; // rsi
  unsigned __int64 v13; // rax
  char *v14; // rax
  size_t v15; // r14
  char *v16; // rax
  char *v17; // rax
  size_t v18; // rcx
  char *v19; // rax
  char *v20; // r15
  _BYTE *v21; // r8
  char *v22; // r12
  _BYTE *v23; // rcx
  signed __int64 v24; // rbx
  char *v25; // r15
  rsize_t v26; // rdx
  rsize_t v27; // r14
  _QWORD pExceptionObject[3]; // [rsp+28h] [rbp-40h] BYREF
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF
  void *Source; // [rsp+80h] [rbp+18h] BYREF

  result = (char *)&retaddr;
  Source = a3;
  v9 = a4 - (_QWORD)a3;
  v10 = *(_QWORD *)(a1 + 8);
  if ( v10 )
    v11 = *(_QWORD *)(a1 + 24) - v10;
  else
    v11 = 0;
  if ( v9 )
  {
    v12 = (void **)(a1 + 16);
    if ( v10 )
      v13 = (unsigned __int64)*v12 - v10;
    else
      v13 = 0;
    if ( ~v13 < v9 )
      std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(a1);
    if ( v10 )
      v14 = (char *)*v12 - v10;
    else
      v14 = 0;
    if ( v11 >= (unsigned __int64)&v14[v9] )
    {
      v25 = (char *)*v12;
      v26 = (_BYTE *)*v12 - a2;
      if ( v26 >= v9 )
      {
        memmove_s(*v12, v9, &v25[-v9], v9);
        *v12 = &v25[v9];
        std::copy_backward<unsigned char *,unsigned char *>(a2);
      }
      else
      {
        if ( v26 )
          memmove_s(&a2[v9], v26, a2, (_BYTE *)*v12 - a2);
        v27 = a4 - (_QWORD)&a3[(_BYTE *)*v12 - a2];
        if ( v27 )
          memmove_s(*v12, v27, &a3[(_BYTE *)*v12 - a2], v27);
        *v12 = (char *)*v12 + v9;
      }
      return (char *)std::copy<unsigned char const *,unsigned char *>(a3);
    }
    else
    {
      if ( ~(v11 >> 1) >= v11 )
        v15 = (v11 >> 1) + v11;
      else
        v15 = 0;
      if ( v10 )
        v16 = (char *)*v12 - v10;
      else
        v16 = 0;
      if ( v15 < (unsigned __int64)&v16[v9] )
      {
        if ( v10 )
          v17 = (char *)*v12 - v10;
        else
          v17 = 0;
        v15 = (size_t)&v17[v9];
      }
      if ( v15 )
      {
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v15) )
        {
          Source = 0;
          exception::exception((exception *)pExceptionObject, (const char *const *)&Source);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v18 = v15;
      }
      else
      {
        v18 = 0;
      }
      v19 = (char *)operator new(v18);
      v20 = v19;
      v21 = *(_BYTE **)(a1 + 8);
      v22 = &v19[a2 - v21];
      if ( a2 != v21 )
        memmove_s(v19, a2 - v21, v21, a2 - v21);
      memmove_s(v22, v9, Source, v9);
      if ( *v12 != a2 )
        memmove_s(&v22[v9], (_BYTE *)*v12 - a2, a2, (_BYTE *)*v12 - a2);
      v23 = *(_BYTE **)(a1 + 8);
      if ( v23 )
      {
        v24 = (_BYTE *)*v12 - v23;
        operator delete(v23);
      }
      else
      {
        v24 = 0;
      }
      *(_QWORD *)(a1 + 24) = &v20[v15];
      result = &v20[v9 + v24];
      *v12 = result;
      *(_QWORD *)(a1 + 8) = v20;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001faac  mov     rax, rsp
0x18001faaf  mov     [rax+18h], r8
0x18001fab3  push    rdi
0x18001fab4  push    r12
0x18001fab6  push    r13
0x18001fab8  push    r14
0x18001faba  push    r15
0x18001fabc  sub     rsp, 40h
0x18001fac0  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18001fac8  mov     [rax+10h], rbx
0x18001facc  mov     [rax+20h], rsi
0x18001fad0  mov     r14, r9
0x18001fad3  mov     r12, r8
0x18001fad6  mov     rbx, rdx
0x18001fad9  mov     r13, rcx
0x18001fadc  mov     rdi, r9
0x18001fadf  sub     rdi, r8
0x18001fae2  mov     rdx, [rcx+8]
0x18001fae6  test    rdx, rdx
0x18001fae9  jz      loc_18001FC38
0x18001faef  mov     r10, [rcx+18h]
0x18001faf3  sub     r10, rdx
0x18001faf6  test    rdi, rdi
0x18001faf9  jnz     short loc_18001FB15
0x18001fafb  lea     r11, [rsp+68h+var_28]
0x18001fb00  mov     rbx, [r11+38h]
0x18001fb04  mov     rsi, [r11+48h]
0x18001fb08  mov     rsp, r11
0x18001fb0b  pop     r15
0x18001fb0d  pop     r14
0x18001fb0f  pop     r13
0x18001fb11  pop     r12
0x18001fb13  pop     rdi
0x18001fb14  retn
0x18001fb15  lea     rsi, [rcx+10h]
0x18001fb19  test    rdx, rdx
0x18001fb1c  jz      loc_18001FC49
0x18001fb22  mov     rax, [rsi]
0x18001fb25  sub     rax, rdx
0x18001fb28  not     rax
0x18001fb2b  cmp     rax, rdi
0x18001fb2e  jb      loc_18001FCF5
0x18001fb34  test    rdx, rdx
0x18001fb37  jz      loc_18001FC50
0x18001fb3d  mov     rax, [rsi]
0x18001fb40  sub     rax, rdx
0x18001fb43  add     rax, rdi
0x18001fb46  cmp     r10, rax
0x18001fb49  jnb     loc_18001FC69
0x18001fb4f  mov     rcx, r10
0x18001fb52  shr     rcx, 1
0x18001fb55  mov     rax, rcx
0x18001fb58  not     rax
0x18001fb5b  cmp     rax, r10
0x18001fb5e  jnb     loc_18001FC40
0x18001fb64  xor     r14d, r14d
0x18001fb67  test    rdx, rdx
0x18001fb6a  jz      loc_18001FC57
0x18001fb70  mov     rax, [rsi]
0x18001fb73  sub     rax, rdx
0x18001fb76  add     rax, rdi
0x18001fb79  cmp     r14, rax
0x18001fb7c  jnb     short loc_18001FB91
0x18001fb7e  test    rdx, rdx
0x18001fb81  jz      loc_18001FC62
0x18001fb87  mov     rax, [rsi]
0x18001fb8a  sub     rax, rdx
0x18001fb8d  lea     r14, [rdi+rax]
0x18001fb91  test    r14, r14
0x18001fb94  jz      loc_18001FCFB
0x18001fb9a  xor     edx, edx
0x18001fb9c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fba0  div     r14
0x18001fba3  cmp     rax, 1
0x18001fba7  jb      loc_18001FD02
0x18001fbad  mov     rcx, r14; Size
0x18001fbb0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fbb5  mov     r15, rax
0x18001fbb8  mov     [rsp+68h+arg_0], rax
0x18001fbbd  mov     r8, [r13+8]; Source
0x18001fbc1  mov     rdx, rbx
0x18001fbc4  sub     rdx, r8; DestinationSize
0x18001fbc7  lea     r12, [rdx+rax]
0x18001fbcb  jz      short loc_18001FBD9
0x18001fbcd  mov     r9, rdx; SourceSize
0x18001fbd0  mov     rcx, rax; Destination
0x18001fbd3  call    cs:__imp_memmove_s
0x18001fbd9  mov     r9, rdi; SourceSize
0x18001fbdc  mov     r8, [rsp+68h+Source]; Source
0x18001fbe4  mov     rdx, rdi; DestinationSize
0x18001fbe7  mov     rcx, r12; Destination
0x18001fbea  call    cs:__imp_memmove_s
0x18001fbf0  mov     rdx, [rsi]
0x18001fbf3  sub     rdx, rbx; DestinationSize
0x18001fbf6  jz      short loc_18001FC09
0x18001fbf8  lea     rcx, [r12+rdi]; Destination
0x18001fbfc  mov     r9, rdx; SourceSize
0x18001fbff  mov     r8, rbx; Source
0x18001fc02  call    cs:__imp_memmove_s
0x18001fc08  nop
0x18001fc09  mov     rcx, [r13+8]; Block
0x18001fc0d  test    rcx, rcx
0x18001fc10  jz      short loc_18001FC5E
0x18001fc12  mov     rbx, [rsi]
0x18001fc15  sub     rbx, rcx
0x18001fc18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001fc1d  lea     rax, [r15+r14]
0x18001fc21  mov     [r13+18h], rax
0x18001fc25  lea     rax, [rdi+rbx]
0x18001fc29  add     rax, r15
0x18001fc2c  mov     [rsi], rax
0x18001fc2f  mov     [r13+8], r15
0x18001fc33  jmp     loc_18001FAFB
0x18001fc38  xor     r10d, r10d
0x18001fc3b  jmp     loc_18001FAF6
0x18001fc40  lea     r14, [rcx+r10]
0x18001fc44  jmp     loc_18001FB67
0x18001fc49  xor     eax, eax
0x18001fc4b  jmp     loc_18001FB28
0x18001fc50  xor     eax, eax
0x18001fc52  jmp     loc_18001FB43
0x18001fc57  xor     eax, eax
0x18001fc59  jmp     loc_18001FB76
0x18001fc5e  xor     ebx, ebx
0x18001fc60  jmp     short loc_18001FC1D
0x18001fc62  xor     eax, eax
0x18001fc64  jmp     loc_18001FB8D
0x18001fc69  mov     r15, [rsi]
0x18001fc6c  mov     rdx, r15
0x18001fc6f  sub     rdx, rbx; DestinationSize
0x18001fc72  cmp     rdx, rdi
0x18001fc75  jnb     short loc_18001FCC3
0x18001fc77  test    rdx, rdx
0x18001fc7a  jz      short loc_18001FC8C
0x18001fc7c  lea     rcx, [rdi+rbx]; Destination
0x18001fc80  mov     r9, rdx; SourceSize
0x18001fc83  mov     r8, rbx; Source
0x18001fc86  call    cs:__imp_memmove_s
0x18001fc8c  mov     r15, [rsi]
0x18001fc8f  sub     r15, rbx
0x18001fc92  add     r15, r12
0x18001fc95  sub     r14, r15
0x18001fc98  jz      short loc_18001FCAD
0x18001fc9a  mov     r9, r14; SourceSize
0x18001fc9d  mov     r8, r15; Source
0x18001fca0  mov     rdx, r14; DestinationSize
0x18001fca3  mov     rcx, [rsi]; Destination
0x18001fca6  call    cs:__imp_memmove_s
0x18001fcac  nop
0x18001fcad  add     [rsi], rdi
0x18001fcb0  mov     rdx, r15
0x18001fcb3  mov     r8, rbx
0x18001fcb6  mov     rcx, r12; Source
0x18001fcb9  call    ??$copy@PEBEPEAE@std@@YAPEAEPEBE0PEAE@Z; std::copy<uchar const *,uchar *>(uchar const *,uchar const *,uchar *)
0x18001fcbe  jmp     loc_18001FAFB
0x18001fcc3  mov     r8, r15
0x18001fcc6  sub     r8, rdi; Source
0x18001fcc9  mov     r9, rdi; SourceSize
0x18001fccc  mov     rdx, rdi; DestinationSize
0x18001fccf  mov     rcx, r15; Destination
0x18001fcd2  call    cs:__imp_memmove_s
0x18001fcd8  lea     rax, [rdi+r15]
0x18001fcdc  mov     [rsi], rax
0x18001fcdf  mov     rdx, r15
0x18001fce2  sub     rdx, rdi
0x18001fce5  mov     r8, r15
0x18001fce8  mov     rcx, rbx; Source
0x18001fceb  call    ??$copy_backward@PEAEPEAE@std@@YAPEAEPEAE00@Z; std::copy_backward<uchar *,uchar *>(uchar *,uchar *,uchar *)
0x18001fcf0  mov     rdx, r14
0x18001fcf3  jmp     short loc_18001FCB3
0x18001fcf5  call    ?_Xlen@?$vector@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@V?$allocator@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@@3@@std@@KAXXZ; std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(void)
0x18001fcfb  xor     ecx, ecx
0x18001fcfd  jmp     loc_18001FBB0
0x18001fd02  mov     [rsp+68h+Source], 0
0x18001fd0e  lea     rdx, [rsp+68h+Source]
0x18001fd16  lea     rcx, [rsp+68h+pExceptionObject]
0x18001fd1b  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18001fd21  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001fd28  mov     [rsp+68h+pExceptionObject], rax
0x18001fd2d  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001fd34  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001fd39  call    _CxxThrowException_0
```
