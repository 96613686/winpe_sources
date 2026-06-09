# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800039bc`
- end: `0x180003a9a`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `222`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, rsize_t)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003d50`

## callees

- `0x180002dbc`
- `0x1800039bc`
- `0x18000417c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003a63`
- `msvcrt!memcpy_s` at `0x180003a63`

## pseudocode

```c
__int64 __fastcall std::string::_Copy(__int64 a1, unsigned __int64 a2, rsize_t a3)
{
  rsize_t v3; // r14
  unsigned __int64 v4; // rbx
  __int64 v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  void *v10; // r15
  const void **v11; // rsi
  const void *v12; // r8
  __int64 v13; // rdx
  __int64 result; // rax
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-48h] BYREF
  __int64 v24; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = *(_QWORD *)(a1 + 32);
    v8 = v7 >> 1;
    v9 = v6 / 3;
    if ( v9 < v7 >> 1 && v7 <= -2LL - v8 )
      v4 = v8 + v7;
  }
  try
  {
    v10 = (void *)std::_Allocate<char>(v4 + 1, 0);
  }
  catch ( ... )
  {
    try
    {
      v24 = std::_Allocate<char>(a2 + 1, 0);
    }
    catch ( ... )
    {
      v15 = &v16;
      LOBYTE(v15) = 1;
      std::string::_Tidy(a1, v15, 0);
      throw;
    }
    v5 = a1;
    v3 = a3;
    v4 = a2;
    v10 = (void *)v24;
  }
  v11 = (const void **)(v5 + 8);
  if ( v3 )
  {
    if ( *(_QWORD *)(v5 + 32) < 0x10u )
      v12 = (const void *)(v5 + 8);
    else
      v12 = *v11;
    memcpy_s(v10, v4 + 1, v12, v3);
  }
  LOBYTE(v13) = 1;
  result = std::string::_Tidy(v5, v13, 0);
  *v11 = v10;
  *(_QWORD *)(v5 + 32) = v4;
  if ( v4 >= 0x10 )
    v11 = (const void **)v10;
  *(_QWORD *)(v5 + 24) = v3;
  *((_BYTE *)v11 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x1800039bc  mov     [rsp+arg_10], r8
0x1800039c1  mov     [rsp+arg_8], rdx
0x1800039c6  mov     [rsp+arg_0], rcx
0x1800039cb  push    rbx
0x1800039cc  push    rsi
0x1800039cd  push    rdi
0x1800039ce  push    r14
0x1800039d0  push    r15
0x1800039d2  sub     rsp, 20h
0x1800039d6  mov     r14, r8
0x1800039d9  mov     rbx, rdx
0x1800039dc  mov     rdi, rcx
0x1800039df  or      rdx, 0Fh
0x1800039e3  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800039ea  cmp     rdx, r9
0x1800039ed  ja      short loc_180003A1D
0x1800039ef  mov     rbx, rdx
0x1800039f2  mov     r8, [rcx+20h]
0x1800039f6  mov     rcx, r8
0x1800039f9  shr     rcx, 1
0x1800039fc  mov     rax, 0AAAAAAAAAAAAAAABh
0x180003a06  mul     rdx
0x180003a09  shr     rdx, 1
0x180003a0c  cmp     rdx, rcx
0x180003a0f  jnb     short loc_180003A1D
0x180003a11  sub     r9, rcx
0x180003a14  cmp     r8, r9
0x180003a17  ja      short loc_180003A1D
0x180003a19  lea     rbx, [rcx+r8]
0x180003a1d  lea     rcx, [rbx+1]
0x180003a21  xor     edx, edx
0x180003a23  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x180003a28  mov     r15, rax
0x180003a2b  jmp     short loc_180003A41
0x180003a2d  mov     rdi, [rsp+48h+arg_0]
0x180003a32  mov     r14, [rsp+48h+arg_10]
0x180003a37  mov     rbx, [rsp+48h+arg_8]
0x180003a3c  mov     r15, [rsp+48h+arg_18]
0x180003a41  lea     rsi, [rdi+8]
0x180003a45  test    r14, r14
0x180003a48  jz      short loc_180003A69
0x180003a4a  cmp     qword ptr [rdi+20h], 10h
0x180003a4f  jb      short loc_180003A56
0x180003a51  mov     r8, [rsi]
0x180003a54  jmp     short loc_180003A59
0x180003a56  mov     r8, rsi; Source
0x180003a59  lea     rdx, [rbx+1]; DestinationSize
0x180003a5d  mov     r9, r14; SourceSize
0x180003a60  mov     rcx, r15; Destination
0x180003a63  call    cs:__imp_memcpy_s
0x180003a69  xor     r8d, r8d
0x180003a6c  mov     dl, 1
0x180003a6e  mov     rcx, rdi
0x180003a71  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180003a76  mov     [rsi], r15
0x180003a79  mov     [rdi+20h], rbx
0x180003a7d  cmp     rbx, 10h
0x180003a81  cmovnb  rsi, r15
0x180003a85  mov     [rdi+18h], r14
0x180003a89  mov     byte ptr [rsi+r14], 0
0x180003a8e  add     rsp, 20h
0x180003a92  pop     r15
0x180003a94  pop     r14
0x180003a96  pop     rdi
0x180003a97  pop     rsi
0x180003a98  pop     rbx
0x180003a99  retn
```
