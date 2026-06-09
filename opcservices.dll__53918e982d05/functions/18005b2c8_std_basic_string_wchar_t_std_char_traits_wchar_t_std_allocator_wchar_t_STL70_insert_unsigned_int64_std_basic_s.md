# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>::insert(unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,unsigned __int64,unsigned __int64)

- ea: `0x18005b2c8`
- end: `0x18005b42a`
- name: `?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_KAEBV12@00@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180059e54`

## callees

- `0x180018fc0`
- `0x18005b2c8`
- `0x1800cded0`
- `0x1800cdf2c`

## import_xrefs

- `msvcrt!memmove_s` at `0x18005b385`
- `msvcrt!memmove_s` at `0x18005b3c2`
- `msvcrt!memmove_s` at `0x18005b385`
- `msvcrt!memmove_s` at `0x18005b3c2`
- `msvcrt!memcpy_s` at `0x18005b3fb`
- `msvcrt!memcpy_s` at `0x18005b3fb`

## pseudocode

```c
_QWORD *__fastcall std::wstring::insert(
        _QWORD *a1,
        unsigned __int64 a2,
        _QWORD *a3,
        unsigned __int64 a4,
        unsigned __int64 a5)
{
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rcx
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // r13
  _QWORD *v13; // rdi
  unsigned __int64 v14; // rdx
  __int64 v15; // r12
  _QWORD *v16; // rcx
  _QWORD *v17; // rax
  unsigned __int64 v18; // rdx
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  _QWORD *v21; // rax
  unsigned __int64 v22; // rdx
  _QWORD *v23; // rcx

  v6 = a4;
  v7 = a1[3];
  if ( v7 < a2 || a3[3] < a4 )
    std::_String_base::_Xran();
  v10 = a5;
  v11 = ~v7;
  if ( a3[3] - a4 < a5 )
    v10 = a3[3] - a4;
  if ( v11 <= v10 )
    std::_String_base::_Xlen();
  if ( v10 )
  {
    v12 = v10 + a1[3];
    if ( (unsigned __int8)std::wstring::_Grow(a1, v12, 0) )
    {
      v13 = a1 + 1;
      v14 = a1[4];
      v15 = 2 * a2;
      if ( v14 < 8 )
      {
        v16 = a1 + 1;
        v17 = a1 + 1;
      }
      else
      {
        v16 = (_QWORD *)*v13;
        v17 = (_QWORD *)*v13;
      }
      memmove_s((char *)v16 + 2 * a2 + 2 * v10, 2 * (v14 - a2 - v10), (char *)v17 + v15, 2 * (a1[3] - a2));
      if ( a1 == a3 )
      {
        if ( a2 < v6 )
          v6 += v10;
        v18 = a1[4];
        if ( v18 < 8 )
        {
          v19 = a1 + 1;
          v20 = a1 + 1;
        }
        else
        {
          v19 = (_QWORD *)*v13;
          v20 = (_QWORD *)*v13;
        }
        memmove_s((char *)v19 + v15, 2 * (v18 - a2), (char *)v20 + 2 * v6, 2 * v10);
      }
      else
      {
        v21 = a3 + 1;
        if ( a3[4] >= 8u )
          v21 = (_QWORD *)*v21;
        v22 = a1[4];
        if ( v22 < 8 )
          v23 = a1 + 1;
        else
          v23 = (_QWORD *)*v13;
        memcpy_s((char *)v23 + v15, 2 * (v22 - a2), (char *)v21 + 2 * v6, 2 * v10);
      }
      if ( a1[4] >= 8u )
        v13 = (_QWORD *)*v13;
      a1[3] = v12;
      *((_WORD *)v13 + v12) = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18005b2c8  push    rbx
0x18005b2ca  push    rbp
0x18005b2cb  push    rsi
0x18005b2cc  push    rdi
0x18005b2cd  push    r12
0x18005b2cf  push    r13
0x18005b2d1  push    r14
0x18005b2d3  push    r15
0x18005b2d5  sub     rsp, 28h
0x18005b2d9  mov     rbx, rcx
0x18005b2dc  mov     r14, r9
0x18005b2df  mov     rcx, [rcx+18h]
0x18005b2e3  mov     rbp, r8
0x18005b2e6  mov     r15, rdx
0x18005b2e9  cmp     rcx, rdx
0x18005b2ec  jb      short loc_18005B2F4
0x18005b2ee  cmp     [r8+18h], r9
0x18005b2f2  jnb     short loc_18005B2FD
0x18005b2f4  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x18005b2f9  mov     rcx, [rbx+18h]
0x18005b2fd  mov     rsi, [rsp+68h+arg_20]
0x18005b305  not     rcx
0x18005b308  mov     rax, [rbp+18h]
0x18005b30c  sub     rax, r14
0x18005b30f  cmp     rax, rsi
0x18005b312  cmovb   rsi, rax
0x18005b316  cmp     rcx, rsi
0x18005b319  ja      short loc_18005B320
0x18005b31b  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x18005b320  test    rsi, rsi
0x18005b323  jz      loc_18005B416
0x18005b329  mov     r13, [rbx+18h]
0x18005b32d  xor     r8d, r8d
0x18005b330  add     r13, rsi
0x18005b333  mov     rcx, rbx
0x18005b336  mov     rdx, r13
0x18005b339  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x18005b33e  test    al, al
0x18005b340  jz      loc_18005B416
0x18005b346  mov     r9, [rbx+18h]
0x18005b34a  lea     rdi, [rbx+8]
0x18005b34e  mov     rdx, [rbx+20h]
0x18005b352  lea     r12, [r15+r15]
0x18005b356  sub     r9, r15
0x18005b359  cmp     rdx, 8
0x18005b35d  jb      short loc_18005B367
0x18005b35f  mov     rcx, [rdi]
0x18005b362  mov     rax, rcx
0x18005b365  jmp     short loc_18005B36D
0x18005b367  mov     rcx, rdi
0x18005b36a  mov     rax, rdi
0x18005b36d  sub     rdx, r15
0x18005b370  lea     r8, [r12+rax]; Source
0x18005b374  sub     rdx, rsi
0x18005b377  lea     rax, [r15+rsi]
0x18005b37b  add     rdx, rdx; DestinationSize
0x18005b37e  lea     rcx, [rcx+rax*2]; Destination
0x18005b382  add     r9, r9; SourceSize
0x18005b385  call    cs:__imp_memmove_s
0x18005b38b  cmp     rbx, rbp
0x18005b38e  jnz     short loc_18005B3CA
0x18005b390  cmp     r15, r14
0x18005b393  jnb     short loc_18005B398
0x18005b395  add     r14, rsi
0x18005b398  mov     rdx, [rbx+20h]
0x18005b39c  cmp     rdx, 8
0x18005b3a0  jb      short loc_18005B3AA
0x18005b3a2  mov     rax, [rdi]
0x18005b3a5  mov     rcx, rax
0x18005b3a8  jmp     short loc_18005B3B0
0x18005b3aa  mov     rax, rdi
0x18005b3ad  mov     rcx, rdi
0x18005b3b0  sub     rdx, r15
0x18005b3b3  lea     r8, [rcx+r14*2]; Source
0x18005b3b7  add     rdx, rdx; DestinationSize
0x18005b3ba  lea     r9, [rsi+rsi]; SourceSize
0x18005b3be  lea     rcx, [r12+rax]; Destination
0x18005b3c2  call    cs:__imp_memmove_s
0x18005b3c8  jmp     short loc_18005B401
0x18005b3ca  cmp     qword ptr [rbp+20h], 8
0x18005b3cf  lea     rax, [rbp+8]
0x18005b3d3  jb      short loc_18005B3D8
0x18005b3d5  mov     rax, [rax]
0x18005b3d8  mov     rdx, [rbx+20h]
0x18005b3dc  cmp     rdx, 8
0x18005b3e0  jb      short loc_18005B3E7
0x18005b3e2  mov     rcx, [rdi]
0x18005b3e5  jmp     short loc_18005B3EA
0x18005b3e7  mov     rcx, rdi
0x18005b3ea  sub     rdx, r15
0x18005b3ed  lea     r9, [rsi+rsi]; SourceSize
0x18005b3f1  add     rdx, rdx; DestinationSize
0x18005b3f4  lea     r8, [rax+r14*2]; Source
0x18005b3f8  add     rcx, r12; Destination
0x18005b3fb  call    cs:__imp_memcpy_s
0x18005b401  cmp     qword ptr [rbx+20h], 8
0x18005b406  jb      short loc_18005B40B
0x18005b408  mov     rdi, [rdi]
0x18005b40b  xor     eax, eax
0x18005b40d  mov     [rbx+18h], r13
0x18005b411  mov     [rdi+r13*2], ax
0x18005b416  mov     rax, rbx
0x18005b419  add     rsp, 28h
0x18005b41d  pop     r15
0x18005b41f  pop     r14
0x18005b421  pop     r13
0x18005b423  pop     r12
0x18005b425  pop     rdi
0x18005b426  pop     rsi
0x18005b427  pop     rbp
0x18005b428  pop     rbx
0x18005b429  retn
```
