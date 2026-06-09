# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>::insert(unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x180059e54`
- end: `0x180059f8a`
- name: `?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_KPEB_W0@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180059c90`

## callees

- `0x180018fc0`
- `0x180059e54`
- `0x180059fa0`
- `0x18005b2c8`
- `0x1800cded0`
- `0x1800cdf2c`

## import_xrefs

- `msvcrt!memmove_s` at `0x180059ef2`
- `msvcrt!memmove_s` at `0x180059ef2`
- `msvcrt!memcpy_s` at `0x180059f16`
- `msvcrt!memcpy_s` at `0x180059f16`

## pseudocode

```c
_QWORD *__fastcall std::wstring::insert(_QWORD *a1, unsigned __int64 a2, _BYTE *a3, unsigned __int64 a4)
{
  unsigned __int64 v8; // rbp
  _QWORD *v9; // rdi
  unsigned __int64 v10; // rdx
  __int64 v11; // r12
  _QWORD *v12; // rcx
  _QWORD *v13; // rax
  unsigned __int64 v14; // rdx
  _QWORD *v15; // rax
  _QWORD *v17; // rax

  if ( (unsigned __int8)std::wstring::_Inside(a1, a3) )
  {
    v17 = a1 + 1;
    if ( a1[4] >= 8u )
      v17 = (_QWORD *)*v17;
    return std::wstring::insert(a1, a2, a1, (a3 - (_BYTE *)v17) >> 1, a4);
  }
  else
  {
    if ( a1[3] < a2 )
      std::_String_base::_Xran();
    if ( ~a1[3] <= a4 )
      std::_String_base::_Xlen();
    if ( a4 )
    {
      v8 = a4 + a1[3];
      if ( (unsigned __int8)std::wstring::_Grow(a1, v8, 0) )
      {
        v9 = a1 + 1;
        v10 = a1[4];
        v11 = 2 * a2;
        if ( v10 < 8 )
        {
          v12 = a1 + 1;
          v13 = a1 + 1;
        }
        else
        {
          v12 = (_QWORD *)*v9;
          v13 = (_QWORD *)*v9;
        }
        memmove_s((char *)v12 + 2 * a2 + 2 * a4, 2 * (v10 - a2 - a4), (char *)v13 + v11, 2 * (a1[3] - a2));
        v14 = a1[4];
        if ( v14 < 8 )
          v15 = a1 + 1;
        else
          v15 = (_QWORD *)*v9;
        memcpy_s((char *)v15 + v11, 2 * (v14 - a2), a3, 2 * a4);
        if ( a1[4] >= 8u )
          v9 = (_QWORD *)*v9;
        a1[3] = v8;
        *((_WORD *)v9 + v8) = 0;
      }
    }
    return a1;
  }
}

```

## disassembly

```asm
0x180059e54  push    rbx
0x180059e56  push    rbp
0x180059e57  push    rsi
0x180059e58  push    rdi
0x180059e59  push    r12
0x180059e5b  push    r14
0x180059e5d  push    r15
0x180059e5f  sub     rsp, 30h
0x180059e63  mov     r15, rdx
0x180059e66  mov     r14, r9
0x180059e69  mov     rdx, r8
0x180059e6c  mov     rsi, r8
0x180059e6f  mov     rbx, rcx
0x180059e72  call    ?_Inside@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAA_NPEB_W@Z; std::wstring::_Inside(wchar_t const *)
0x180059e77  test    al, al
0x180059e79  jnz     loc_180059F4F
0x180059e7f  cmp     [rbx+18h], r15
0x180059e83  jb      loc_180059F7B
0x180059e89  mov     rax, [rbx+18h]
0x180059e8d  not     rax
0x180059e90  cmp     rax, r14
0x180059e93  jbe     loc_180059F85
0x180059e99  test    r14, r14
0x180059e9c  jz      loc_180059F30
0x180059ea2  mov     rbp, [rbx+18h]
0x180059ea6  xor     r8d, r8d
0x180059ea9  add     rbp, r14
0x180059eac  mov     rcx, rbx
0x180059eaf  mov     rdx, rbp
0x180059eb2  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x180059eb7  test    al, al
0x180059eb9  jz      short loc_180059F30
0x180059ebb  mov     r9, [rbx+18h]
0x180059ebf  lea     rdi, [rbx+8]
0x180059ec3  mov     rdx, [rbx+20h]
0x180059ec7  lea     r12, [r15+r15]
0x180059ecb  sub     r9, r15
0x180059ece  cmp     rdx, 8
0x180059ed2  jb      short loc_180059F42
0x180059ed4  mov     rcx, [rdi]
0x180059ed7  mov     rax, rcx
0x180059eda  sub     rdx, r15
0x180059edd  lea     r8, [r12+rax]; Source
0x180059ee1  sub     rdx, r14
0x180059ee4  lea     rax, [r15+r14]
0x180059ee8  add     rdx, rdx; DestinationSize
0x180059eeb  lea     rcx, [rcx+rax*2]; Destination
0x180059eef  add     r9, r9; SourceSize
0x180059ef2  call    cs:__imp_memmove_s
0x180059ef8  mov     rdx, [rbx+20h]
0x180059efc  cmp     rdx, 8
0x180059f00  jb      short loc_180059F4A
0x180059f02  mov     rax, [rdi]
0x180059f05  sub     rdx, r15
0x180059f08  lea     r9, [r14+r14]; SourceSize
0x180059f0c  add     rdx, rdx; DestinationSize
0x180059f0f  lea     rcx, [r12+rax]; Destination
0x180059f13  mov     r8, rsi; Source
0x180059f16  call    cs:__imp_memcpy_s
0x180059f1c  cmp     qword ptr [rbx+20h], 8
0x180059f21  jb      short loc_180059F26
0x180059f23  mov     rdi, [rdi]
0x180059f26  xor     eax, eax
0x180059f28  mov     [rbx+18h], rbp
0x180059f2c  mov     [rdi+rbp*2], ax
0x180059f30  mov     rax, rbx
0x180059f33  add     rsp, 30h
0x180059f37  pop     r15
0x180059f39  pop     r14
0x180059f3b  pop     r12
0x180059f3d  pop     rdi
0x180059f3e  pop     rsi
0x180059f3f  pop     rbp
0x180059f40  pop     rbx
0x180059f41  retn
0x180059f42  mov     rcx, rdi
0x180059f45  mov     rax, rdi
0x180059f48  jmp     short loc_180059EDA
0x180059f4a  mov     rax, rdi
0x180059f4d  jmp     short loc_180059F05
0x180059f4f  cmp     qword ptr [rbx+20h], 8
0x180059f54  lea     rax, [rbx+8]
0x180059f58  jb      short loc_180059F5D
0x180059f5a  mov     rax, [rax]
0x180059f5d  sub     rsi, rax
0x180059f60  mov     [rsp+68h+var_48], r14
0x180059f65  sar     rsi, 1
0x180059f68  mov     r8, rbx
0x180059f6b  mov     r9, rsi
0x180059f6e  mov     rdx, r15
0x180059f71  mov     rcx, rbx
0x180059f74  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_KAEBV12@00@Z; std::wstring::insert(unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x180059f79  jmp     short loc_180059F33
0x180059f7b  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x180059f80  jmp     loc_180059E89
0x180059f85  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
```
