# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000e380`
- end: `0x18000e4d7`
- name: `?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e824`

## callees

- `0x180003426`
- `0x18000e380`
- `0x18000eb48`
- `0x18001722c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18000e426`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18000e426`
- `msvcrt!memcpy_s` at `0x18000e496`
- `msvcrt!memcpy_s` at `0x18000e496`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Copy(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rbx
  __int64 v5; // rsi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  char *v12; // r12
  const void **v13; // r14
  const void *v14; // r8
  __int64 v15; // r13
  __int64 result; // rax
  unsigned __int64 v17; // rcx
  __int64 *v18; // rdx
  __int64 v19; // [rsp+0h] [rbp-88h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v21[10]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v23; // [rsp+90h] [rbp+8h]
  const char *v24; // [rsp+98h] [rbp+10h] BYREF
  __int64 v25; // [rsp+A0h] [rbp+18h]
  char *v26; // [rsp+A8h] [rbp+20h] BYREF

  v25 = a3;
  v24 = (const char *)a2;
  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = *(_QWORD *)(a1 + 32);
    v8 = v7 >> 1;
    v9 = v6 / 3;
    if ( v9 < v7 >> 1 && v7 <= 0x7FFFFFFFFFFFFFFELL - v8 )
      v4 = v8 + v7;
  }
  try
  {
    v10 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( 0xFFFFFFFFFFFFFFFFuLL / v10 < 2 )
    {
      v26 = 0;
      exception::exception((exception *)pExceptionObject, (const char *const *)&v26);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    v12 = (char *)MmAllocate(2 * v10);
  }
  catch ( ... )
  {
    v17 = (unsigned __int64)(v24 + 1);
    if ( v24 == (const char *)-1LL || 0xFFFFFFFFFFFFFFFFuLL / v17 >= 2 )
    {
      v26 = (char *)MmAllocate(2 * v17);
      v5 = a1;
      v3 = v25;
      v4 = (unsigned __int64)v24;
      v12 = v26;
      goto LABEL_10;
    }
    try
    {
      exception::exception((exception *)v21, &v24);
      v21[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)v21;
    }
    catch ( ... )
    {
      v18 = &v19;
      LOBYTE(v18) = 1;
      std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(v23, v18, 0);
      throw;
    }
  }
LABEL_10:
  v13 = (const void **)(v5 + 8);
  if ( v3 )
  {
    if ( *(_QWORD *)(v5 + 32) < 8u )
      v14 = (const void *)(v5 + 8);
    else
      v14 = *v13;
    v15 = 2 * v3;
    memcpy_s(v12, 2 * v4 + 2, v14, 2 * v3);
  }
  else
  {
    v15 = 0;
  }
  LOBYTE(v11) = 1;
  result = std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(v5, v11, 0);
  *v13 = v12;
  *(_QWORD *)(v5 + 32) = v4;
  if ( v4 >= 8 )
    v13 = (const void **)v12;
  *(_QWORD *)(v5 + 24) = v3;
  *(_WORD *)((char *)v13 + v15) = 0;
  return result;
}

```

## disassembly

```asm
0x18000e380  mov     [rsp+arg_10], r8
0x18000e385  mov     [rsp+arg_8], rdx
0x18000e38a  mov     [rsp+arg_0], rcx
0x18000e38f  push    rbx
0x18000e390  push    rsi
0x18000e391  push    rdi
0x18000e392  push    r12
0x18000e394  push    r13
0x18000e396  push    r14
0x18000e398  push    r15
0x18000e39a  sub     rsp, 50h
0x18000e39e  mov     r15, r8
0x18000e3a1  mov     rbx, rdx
0x18000e3a4  mov     rsi, rcx
0x18000e3a7  or      rdx, 7
0x18000e3ab  mov     r9, 7FFFFFFFFFFFFFFEh
0x18000e3b5  cmp     rdx, r9
0x18000e3b8  ja      short loc_18000E3E8
0x18000e3ba  mov     rbx, rdx
0x18000e3bd  mov     r8, [rcx+20h]
0x18000e3c1  mov     rcx, r8
0x18000e3c4  shr     rcx, 1
0x18000e3c7  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000e3d1  mul     rdx
0x18000e3d4  shr     rdx, 1
0x18000e3d7  cmp     rdx, rcx
0x18000e3da  jnb     short loc_18000E3E8
0x18000e3dc  sub     r9, rcx
0x18000e3df  cmp     r8, r9
0x18000e3e2  ja      short loc_18000E3E8
0x18000e3e4  lea     rbx, [rcx+r8]
0x18000e3e8  lea     rcx, [rbx+1]
0x18000e3ec  xor     edi, edi
0x18000e3ee  test    rcx, rcx
0x18000e3f1  jnz     short loc_18000E402
0x18000e3f3  mov     ecx, edi
0x18000e3f5  add     rcx, rcx; unsigned __int64
0x18000e3f8  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000e3fd  mov     r12, rax
0x18000e400  jmp     short loc_18000E46C
0x18000e402  xor     edx, edx
0x18000e404  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e408  div     rcx
0x18000e40b  cmp     rax, 2
0x18000e40f  jnb     short loc_18000E3F5
0x18000e411  mov     [rsp+88h+arg_18], rdi
0x18000e419  lea     rdx, [rsp+88h+arg_18]
0x18000e421  lea     rcx, [rsp+88h+pExceptionObject]
0x18000e426  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18000e42c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000e433  mov     [rsp+88h+pExceptionObject], rax
0x18000e438  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000e43f  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000e444  call    _CxxThrowException_0
0x18000e44a  xor     edi, edi
0x18000e44c  mov     rsi, [rsp+88h+arg_0]
0x18000e454  mov     r15, [rsp+88h+arg_10]
0x18000e45c  mov     rbx, [rsp+88h+arg_8]
0x18000e464  mov     r12, [rsp+88h+arg_18]
0x18000e46c  lea     r14, [rsi+8]
0x18000e470  test    r15, r15
0x18000e473  jz      short loc_18000E49E
0x18000e475  cmp     qword ptr [rsi+20h], 8
0x18000e47a  jb      short loc_18000E481
0x18000e47c  mov     r8, [r14]
0x18000e47f  jmp     short loc_18000E484
0x18000e481  mov     r8, r14; Source
0x18000e484  lea     r13, [r15+r15]
0x18000e488  lea     rdx, ds:2[rbx*2]; DestinationSize
0x18000e490  mov     r9, r13; SourceSize
0x18000e493  mov     rcx, r12; Destination
0x18000e496  call    cs:__imp_memcpy_s
0x18000e49c  jmp     short loc_18000E4A2
0x18000e49e  lea     r13, [r15+r15]
0x18000e4a2  xor     r8d, r8d
0x18000e4a5  mov     dl, 1
0x18000e4a7  mov     rcx, rsi
0x18000e4aa  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18000e4af  mov     [r14], r12
0x18000e4b2  mov     [rsi+20h], rbx
0x18000e4b6  cmp     rbx, 8
0x18000e4ba  cmovnb  r14, r12
0x18000e4be  mov     [rsi+18h], r15
0x18000e4c2  mov     [r14+r13], di
0x18000e4c7  add     rsp, 50h
0x18000e4cb  pop     r15
0x18000e4cd  pop     r14
0x18000e4cf  pop     r13
0x18000e4d1  pop     r12
0x18000e4d3  pop     rdi
0x18000e4d4  pop     rsi
0x18000e4d5  pop     rbx
0x18000e4d6  retn
```
