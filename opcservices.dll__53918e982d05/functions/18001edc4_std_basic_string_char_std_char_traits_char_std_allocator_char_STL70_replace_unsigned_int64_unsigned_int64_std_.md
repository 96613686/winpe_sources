# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::replace(unsigned __int64,unsigned __int64,std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70> const &,unsigned __int64,unsigned __int64)

- ea: `0x18001edc4`
- end: `0x18001f152`
- name: `?replace@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0AEBV12@00@Z`
- size: `910`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d7d8`
- `0x180080fe4`
- `0x1800bcdac`

## callees

- `0x18001d3c0`
- `0x18001edc4`
- `0x1800cded0`
- `0x1800cdf2c`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001eeb7`
- `msvcrt!memmove_s` at `0x18001ef76`
- `msvcrt!memmove_s` at `0x18001ef9b`
- `msvcrt!memmove_s` at `0x18001effd`
- `msvcrt!memmove_s` at `0x18001f04f`
- `msvcrt!memmove_s` at `0x18001f090`
- `msvcrt!memmove_s` at `0x18001f0bd`
- `msvcrt!memmove_s` at `0x18001eeb7`
- `msvcrt!memmove_s` at `0x18001ef76`
- `msvcrt!memmove_s` at `0x18001ef9b`
- `msvcrt!memmove_s` at `0x18001effd`
- `msvcrt!memmove_s` at `0x18001f04f`
- `msvcrt!memmove_s` at `0x18001f090`
- `msvcrt!memmove_s` at `0x18001f0bd`
- `msvcrt!memcpy_s` at `0x18001eeee`
- `msvcrt!memcpy_s` at `0x18001eeee`

## pseudocode

```c
_QWORD *__fastcall std::string::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        rsize_t a3,
        _QWORD *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  rsize_t v6; // r14
  unsigned __int64 v9; // rdx
  rsize_t v10; // rbp
  unsigned __int64 v11; // rdx
  rsize_t v12; // rax
  rsize_t v13; // r13
  rsize_t v14; // r12
  _QWORD *v15; // rbx
  unsigned __int64 v16; // rdx
  _QWORD *v17; // rax
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  unsigned __int64 v20; // rdx
  _QWORD *v21; // rax
  _QWORD *result; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // r8
  char *v26; // r8
  rsize_t v27; // rdx
  char *v28; // rcx
  rsize_t v29; // r9
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  unsigned __int64 v32; // rdx
  _QWORD *v33; // rax
  _QWORD *v34; // rcx
  _QWORD *v35; // rax
  _QWORD *v36; // rcx
  unsigned __int64 v37; // rdx
  _QWORD *v38; // rcx
  _QWORD *v39; // rax
  _QWORD *v40; // rcx
  _QWORD *v41; // rax
  _QWORD *v42; // rcx
  unsigned __int64 v43; // rdx
  _QWORD *v44; // rax
  _QWORD *v45; // rcx
  unsigned __int64 v46; // rdx
  _QWORD *v47; // rax
  _QWORD *v48; // rcx

  v6 = a3;
  if ( a1[3] < a2 || (v9 = a4[3], v9 < a5) )
    std::_String_base::_Xran();
  v10 = a6;
  if ( a1[3] - a2 < a3 )
    v6 = a1[3] - a2;
  v11 = v9 - a5;
  if ( v11 < a6 )
    v10 = v11;
  if ( ~v10 <= a1[3] - v6 )
    std::_String_base::_Xlen();
  v12 = a1[3];
  v13 = v12 - a2 - v6;
  v14 = v10 - v6 + v12;
  if ( v12 < v14 )
  {
    if ( v14 == -1 )
      std::_String_base::_Xlen();
    if ( a1[4] < v14 )
    {
      std::string::_Copy(a1, v10 - v6 + v12, a1[3]);
    }
    else if ( !v14 )
    {
      v23 = a1 + 1;
      if ( a1[4] >= 0x10u )
        v23 = (_QWORD *)*v23;
      a1[3] = 0;
      *(_BYTE *)v23 = 0;
    }
  }
  v15 = a1 + 1;
  v16 = a1[4];
  if ( a1 == a4 )
  {
    if ( v10 <= v6 )
    {
      if ( v16 < 0x10 )
      {
        v30 = a1 + 1;
        v31 = a1 + 1;
      }
      else
      {
        v30 = (_QWORD *)*v15;
        v31 = (_QWORD *)*v15;
      }
      memmove_s((char *)v30 + a2, v16 - a2, (char *)v31 + a5, v10);
      v32 = a1[4];
      if ( v32 < 0x10 )
      {
        v33 = a1 + 1;
        v34 = a1 + 1;
      }
      else
      {
        v33 = (_QWORD *)*v15;
        v34 = (_QWORD *)*v15;
      }
      v26 = (char *)v34 + a2 + v6;
      v27 = v32 - a2 - v10;
      v29 = v13;
      v28 = (char *)v33 + a2 + v10;
      goto LABEL_32;
    }
    if ( a5 <= a2 )
    {
      if ( v16 < 0x10 )
      {
        v35 = a1 + 1;
        v36 = a1 + 1;
      }
      else
      {
        v35 = (_QWORD *)*v15;
        v36 = (_QWORD *)*v15;
      }
      memmove_s((char *)v35 + a2 + v10, v16 - a2 - v10, (char *)v36 + a2 + v6, v13);
      v37 = a1[4];
      if ( v37 < 0x10 )
      {
        v24 = a1 + 1;
        v38 = a1 + 1;
      }
      else
      {
        v24 = (_QWORD *)*v15;
        v38 = (_QWORD *)*v15;
      }
      v26 = (char *)v38 + a5;
    }
    else
    {
      if ( a2 + v6 > a5 )
      {
        if ( v16 < 0x10 )
        {
          v41 = a1 + 1;
          v42 = a1 + 1;
        }
        else
        {
          v41 = (_QWORD *)*v15;
          v42 = (_QWORD *)*v15;
        }
        memmove_s((char *)v41 + a2, v16 - a2, (char *)v42 + a5, v6);
        v43 = a1[4];
        if ( v43 < 0x10 )
        {
          v44 = a1 + 1;
          v45 = a1 + 1;
        }
        else
        {
          v44 = (_QWORD *)*v15;
          v45 = (_QWORD *)*v15;
        }
        memmove_s((char *)v44 + a2 + v10, v43 - a2 - v10, (char *)v45 + a2 + v6, v13);
        v46 = a1[4];
        if ( v46 < 0x10 )
        {
          v47 = a1 + 1;
          v48 = a1 + 1;
        }
        else
        {
          v47 = (_QWORD *)*v15;
          v48 = (_QWORD *)*v15;
        }
        v29 = v10 - v6;
        v26 = (char *)v48 + a5 + v10;
        v27 = v46 - a2 - v6;
        v28 = (char *)v47 + a2 + v6;
        goto LABEL_32;
      }
      if ( v16 < 0x10 )
      {
        v39 = a1 + 1;
        v40 = a1 + 1;
      }
      else
      {
        v39 = (_QWORD *)*v15;
        v40 = (_QWORD *)*v15;
      }
      memmove_s((char *)v39 + a2 + v10, v16 - a2 - v10, (char *)v40 + a2 + v6, v13);
      v37 = a1[4];
      if ( v37 >= 0x10 )
      {
        v24 = (_QWORD *)*v15;
        v25 = (_QWORD *)*v15;
      }
      else
      {
        v24 = a1 + 1;
        v25 = a1 + 1;
      }
      v26 = (char *)v25 + a5 - v6 + v10;
    }
    v27 = v37 - a2;
    v28 = (char *)v24 + a2;
    v29 = v10;
LABEL_32:
    memmove_s(v28, v27, v26, v29);
    goto LABEL_20;
  }
  if ( v16 < 0x10 )
  {
    v17 = a1 + 1;
    v18 = a1 + 1;
  }
  else
  {
    v17 = (_QWORD *)*v15;
    v18 = (_QWORD *)*v15;
  }
  memmove_s((char *)v17 + a2 + v10, v16 - a2 - v10, (char *)v18 + a2 + v6, v13);
  v19 = a4 + 1;
  if ( a4[4] >= 0x10u )
    v19 = (_QWORD *)*v19;
  v20 = a1[4];
  if ( v20 < 0x10 )
    v21 = a1 + 1;
  else
    v21 = (_QWORD *)*v15;
  memcpy_s((char *)v21 + a2, v20 - a2, (char *)v19 + a5, v10);
LABEL_20:
  if ( a1[4] >= 0x10u )
    v15 = (_QWORD *)*v15;
  a1[3] = v14;
  result = a1;
  *((_BYTE *)v15 + v14) = 0;
  return result;
}

```

## disassembly

```asm
0x18001edc4  mov     [rsp+arg_18], r9
0x18001edc9  push    rbx
0x18001edca  push    rbp
0x18001edcb  push    rsi
0x18001edcc  push    rdi
0x18001edcd  push    r12
0x18001edcf  push    r13
0x18001edd1  push    r14
0x18001edd3  push    r15
0x18001edd5  sub     rsp, 28h
0x18001edd9  mov     rbx, r9
0x18001eddc  mov     r15, [rsp+68h+arg_20]
0x18001ede4  mov     r14, r8
0x18001ede7  mov     rsi, rdx
0x18001edea  mov     rdi, rcx
0x18001eded  cmp     [rcx+18h], rdx
0x18001edf1  jb      loc_18001F10C
0x18001edf7  mov     rdx, [r9+18h]
0x18001edfb  cmp     rdx, r15
0x18001edfe  jb      loc_18001F10C
0x18001ee04  mov     rcx, [rdi+18h]
0x18001ee08  mov     rbp, [rsp+68h+arg_28]
0x18001ee10  mov     rax, rcx
0x18001ee13  sub     rax, rsi
0x18001ee16  cmp     rax, r14
0x18001ee19  cmovb   r14, rax
0x18001ee1d  sub     rdx, r15
0x18001ee20  cmp     rdx, rbp
0x18001ee23  cmovb   rbp, rdx
0x18001ee27  sub     rcx, r14
0x18001ee2a  mov     rax, rbp
0x18001ee2d  not     rax
0x18001ee30  cmp     rax, rcx
0x18001ee33  jbe     loc_18001F11A
0x18001ee39  mov     rax, [rdi+18h]
0x18001ee3d  mov     rcx, rbp
0x18001ee40  sub     rcx, r14
0x18001ee43  mov     r13, rax
0x18001ee46  sub     r13, rsi
0x18001ee49  mov     [rsp+68h+arg_20], rcx
0x18001ee51  sub     r13, r14
0x18001ee54  lea     r12, [rcx+rax]
0x18001ee58  cmp     rax, r12
0x18001ee5b  jnb     short loc_18001EE7A
0x18001ee5d  cmp     r12, 0FFFFFFFFFFFFFFFEh
0x18001ee61  ja      loc_18001F124
0x18001ee67  cmp     [rdi+20h], r12
0x18001ee6b  jb      loc_18001EF2B
0x18001ee71  test    r12, r12
0x18001ee74  jz      loc_18001EF3F
0x18001ee7a  lea     rbx, [rdi+8]
0x18001ee7e  mov     rdx, [rdi+20h]
0x18001ee82  cmp     rdi, [rsp+68h+arg_18]
0x18001ee8a  jz      loc_18001F12E
0x18001ee90  cmp     rdx, 10h
0x18001ee94  jb      loc_18001EF1B
0x18001ee9a  mov     rax, [rbx]
0x18001ee9d  mov     rcx, rax
0x18001eea0  lea     r8, [rcx+rsi]
0x18001eea4  sub     rdx, rsi
0x18001eea7  lea     rcx, [rax+rsi]
0x18001eeab  add     r8, r14; Source
0x18001eeae  add     rcx, rbp; Destination
0x18001eeb1  sub     rdx, rbp; DestinationSize
0x18001eeb4  mov     r9, r13; SourceSize
0x18001eeb7  call    cs:__imp_memmove_s
0x18001eebd  mov     rax, [rsp+68h+arg_18]
0x18001eec5  cmp     qword ptr [rax+20h], 10h
0x18001eeca  lea     rcx, [rax+8]
0x18001eece  jb      short loc_18001EED3
0x18001eed0  mov     rcx, [rcx]
0x18001eed3  mov     rdx, [rdi+20h]
0x18001eed7  cmp     rdx, 10h
0x18001eedb  jb      short loc_18001EF26
0x18001eedd  mov     rax, [rbx]
0x18001eee0  lea     r8, [rcx+r15]; Source
0x18001eee4  sub     rdx, rsi; DestinationSize
0x18001eee7  lea     rcx, [rax+rsi]; Destination
0x18001eeeb  mov     r9, rbp; SourceSize
0x18001eeee  call    cs:__imp_memcpy_s
0x18001eef4  cmp     qword ptr [rdi+20h], 10h
0x18001eef9  jb      short loc_18001EEFE
0x18001eefb  mov     rbx, [rbx]
0x18001eefe  mov     [rdi+18h], r12
0x18001ef02  mov     rax, rdi
0x18001ef05  mov     byte ptr [rbx+r12], 0
0x18001ef0a  add     rsp, 28h
0x18001ef0e  pop     r15
0x18001ef10  pop     r14
0x18001ef12  pop     r13
0x18001ef14  pop     r12
0x18001ef16  pop     rdi
0x18001ef17  pop     rsi
0x18001ef18  pop     rbp
0x18001ef19  pop     rbx
0x18001ef1a  retn
0x18001ef1b  mov     rax, rbx
0x18001ef1e  mov     rcx, rbx
0x18001ef21  jmp     loc_18001EEA0
0x18001ef26  mov     rax, rbx
0x18001ef29  jmp     short loc_18001EEE0
0x18001ef2b  mov     r8, [rdi+18h]
0x18001ef2f  mov     rdx, r12
0x18001ef32  mov     rcx, rdi
0x18001ef35  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18001ef3a  jmp     loc_18001EE7A
0x18001ef3f  cmp     qword ptr [rdi+20h], 10h
0x18001ef44  lea     rax, [rdi+8]
0x18001ef48  jb      short loc_18001EF4D
0x18001ef4a  mov     rax, [rax]
0x18001ef4d  mov     qword ptr [rdi+18h], 0
0x18001ef55  mov     byte ptr [rax], 0
0x18001ef58  jmp     loc_18001EE7A
0x18001ef5d  mov     rax, [rbx]
0x18001ef60  mov     r8, rax
0x18001ef63  sub     r8, r14
0x18001ef66  add     r8, r15
0x18001ef69  add     r8, rbp; Source
0x18001ef6c  sub     rdx, rsi; DestinationSize
0x18001ef6f  lea     rcx, [rax+rsi]; Destination
0x18001ef73  mov     r9, rbp; SourceSize
0x18001ef76  call    cs:__imp_memmove_s
0x18001ef7c  jmp     loc_18001EEF4
0x18001ef81  cmp     rdx, 10h
0x18001ef85  jb      short loc_18001EFCA
0x18001ef87  mov     rax, [rbx]
0x18001ef8a  mov     rcx, rax
0x18001ef8d  lea     r8, [rcx+r15]; Source
0x18001ef91  sub     rdx, rsi; DestinationSize
0x18001ef94  lea     rcx, [rax+rsi]; Destination
0x18001ef98  mov     r9, rbp; SourceSize
0x18001ef9b  call    cs:__imp_memmove_s
0x18001efa1  mov     rdx, [rdi+20h]
0x18001efa5  cmp     rdx, 10h
0x18001efa9  jb      short loc_18001EFD2
0x18001efab  mov     rax, [rbx]
0x18001efae  mov     rcx, rax
0x18001efb1  lea     r8, [rcx+rsi]
0x18001efb5  sub     rdx, rsi
0x18001efb8  add     r8, r14
0x18001efbb  lea     rcx, [rax+rsi]
0x18001efbf  sub     rdx, rbp
0x18001efc2  mov     r9, r13
0x18001efc5  add     rcx, rbp
0x18001efc8  jmp     short loc_18001EF76
0x18001efca  mov     rax, rbx
0x18001efcd  mov     rcx, rbx
0x18001efd0  jmp     short loc_18001EF8D
0x18001efd2  mov     rax, rbx
0x18001efd5  mov     rcx, rbx
0x18001efd8  jmp     short loc_18001EFB1
0x18001efda  cmp     rdx, 10h
0x18001efde  jb      short loc_18001F01C
0x18001efe0  mov     rax, [rbx]
0x18001efe3  mov     rcx, rax
0x18001efe6  lea     r8, [rcx+rsi]
0x18001efea  sub     rdx, rsi
0x18001efed  lea     rcx, [rax+rsi]
0x18001eff1  add     r8, r14; Source
0x18001eff4  add     rcx, rbp; Destination
0x18001eff7  sub     rdx, rbp; DestinationSize
0x18001effa  mov     r9, r13; SourceSize
0x18001effd  call    cs:__imp_memmove_s
0x18001f003  mov     rdx, [rdi+20h]
0x18001f007  cmp     rdx, 10h
0x18001f00b  jb      short loc_18001F024
0x18001f00d  mov     rax, [rbx]
0x18001f010  mov     rcx, rax
0x18001f013  lea     r8, [rcx+r15]
0x18001f017  jmp     loc_18001EF6C
0x18001f01c  mov     rax, rbx
0x18001f01f  mov     rcx, rbx
0x18001f022  jmp     short loc_18001EFE6
0x18001f024  mov     rax, rbx
0x18001f027  mov     rcx, rbx
0x18001f02a  jmp     short loc_18001F013
0x18001f02c  cmp     rdx, 10h
0x18001f030  jb      short loc_18001F06E
0x18001f032  mov     rax, [rbx]
0x18001f035  mov     rcx, rax
0x18001f038  lea     r8, [rcx+rsi]
0x18001f03c  sub     rdx, rsi
0x18001f03f  lea     rcx, [rax+rsi]
0x18001f043  add     r8, r14; Source
0x18001f046  add     rcx, rbp; Destination
0x18001f049  sub     rdx, rbp; DestinationSize
0x18001f04c  mov     r9, r13; SourceSize
0x18001f04f  call    cs:__imp_memmove_s
0x18001f055  mov     rdx, [rdi+20h]
0x18001f059  cmp     rdx, 10h
0x18001f05d  jnb     loc_18001EF5D
0x18001f063  mov     rax, rbx
0x18001f066  mov     r8, rbx
0x18001f069  jmp     loc_18001EF63
0x18001f06e  mov     rax, rbx
0x18001f071  mov     rcx, rbx
0x18001f074  jmp     short loc_18001F038
0x18001f076  cmp     rdx, 10h
0x18001f07a  jb      short loc_18001F0F4
0x18001f07c  mov     rax, [rbx]
0x18001f07f  mov     rcx, rax
0x18001f082  lea     r8, [rcx+r15]; Source
0x18001f086  sub     rdx, rsi; DestinationSize
0x18001f089  lea     rcx, [rax+rsi]; Destination
0x18001f08d  mov     r9, r14; SourceSize
0x18001f090  call    cs:__imp_memmove_s
0x18001f096  mov     rdx, [rdi+20h]
0x18001f09a  cmp     rdx, 10h
0x18001f09e  jb      short loc_18001F0FC
0x18001f0a0  mov     rax, [rbx]
0x18001f0a3  mov     rcx, rax
0x18001f0a6  lea     r8, [rcx+rsi]
0x18001f0aa  sub     rdx, rsi
0x18001f0ad  lea     rcx, [rax+rsi]
0x18001f0b1  add     r8, r14; Source
0x18001f0b4  add     rcx, rbp; Destination
0x18001f0b7  sub     rdx, rbp; DestinationSize
0x18001f0ba  mov     r9, r13; SourceSize
0x18001f0bd  call    cs:__imp_memmove_s
0x18001f0c3  mov     rdx, [rdi+20h]
0x18001f0c7  cmp     rdx, 10h
0x18001f0cb  jb      short loc_18001F104
0x18001f0cd  mov     rax, [rbx]
0x18001f0d0  mov     rcx, rax
0x18001f0d3  mov     r9, [rsp+68h+arg_20]
0x18001f0db  lea     r8, [rcx+r15]
0x18001f0df  sub     rdx, rsi
0x18001f0e2  lea     rcx, [rax+rsi]
0x18001f0e6  add     r8, rbp
0x18001f0e9  sub     rdx, r14
0x18001f0ec  add     rcx, r14
0x18001f0ef  jmp     loc_18001EF76
0x18001f0f4  mov     rax, rbx
0x18001f0f7  mov     rcx, rbx
0x18001f0fa  jmp     short loc_18001F082
0x18001f0fc  mov     rax, rbx
0x18001f0ff  mov     rcx, rbx
0x18001f102  jmp     short loc_18001F0A6
0x18001f104  mov     rax, rbx
0x18001f107  mov     rcx, rbx
0x18001f10a  jmp     short loc_18001F0D3
0x18001f10c  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x18001f111  mov     rdx, [rbx+18h]
0x18001f115  jmp     loc_18001EE04
0x18001f11a  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x18001f11f  jmp     loc_18001EE39
0x18001f124  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x18001f129  jmp     loc_18001EE67
0x18001f12e  cmp     rbp, r14
0x18001f131  jbe     loc_18001EF81
0x18001f137  cmp     r15, rsi
0x18001f13a  jbe     loc_18001EFDA
0x18001f140  lea     rax, [rsi+r14]
0x18001f144  cmp     rax, r15
0x18001f147  ja      loc_18001F076
0x18001f14d  jmp     loc_18001F02C
```
