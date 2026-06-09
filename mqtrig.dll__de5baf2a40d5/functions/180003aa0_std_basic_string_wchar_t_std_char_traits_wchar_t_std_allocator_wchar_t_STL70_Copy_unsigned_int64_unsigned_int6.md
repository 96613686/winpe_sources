# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180003aa0`
- end: `0x180003bf7`
- name: `?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `343`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003de8`

## callees

- `0x180001ce6`
- `0x180003aa0`
- `0x1800041ec`
- `0x180014ae8`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180003b46`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180003b46`
- `msvcrt!memcpy_s` at `0x180003bb6`
- `msvcrt!memcpy_s` at `0x180003bb6`

## pseudocode

```c
__int64 __fastcall std::wstring::_Copy(__int64 a1, unsigned __int64 a2, __int64 a3)
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
0x180003aa0  mov     [rsp+arg_10], r8
0x180003aa5  mov     [rsp+arg_8], rdx
0x180003aaa  mov     [rsp+arg_0], rcx
0x180003aaf  push    rbx
0x180003ab0  push    rsi
0x180003ab1  push    rdi
0x180003ab2  push    r12
0x180003ab4  push    r13
0x180003ab6  push    r14
0x180003ab8  push    r15
0x180003aba  sub     rsp, 50h
0x180003abe  mov     r15, r8
0x180003ac1  mov     rbx, rdx
0x180003ac4  mov     rsi, rcx
0x180003ac7  or      rdx, 7
0x180003acb  mov     r9, 7FFFFFFFFFFFFFFEh
0x180003ad5  cmp     rdx, r9
0x180003ad8  ja      short loc_180003B08
0x180003ada  mov     rbx, rdx
0x180003add  mov     r8, [rcx+20h]
0x180003ae1  mov     rcx, r8
0x180003ae4  shr     rcx, 1
0x180003ae7  mov     rax, 0AAAAAAAAAAAAAAABh
0x180003af1  mul     rdx
0x180003af4  shr     rdx, 1
0x180003af7  cmp     rdx, rcx
0x180003afa  jnb     short loc_180003B08
0x180003afc  sub     r9, rcx
0x180003aff  cmp     r8, r9
0x180003b02  ja      short loc_180003B08
0x180003b04  lea     rbx, [rcx+r8]
0x180003b08  lea     rcx, [rbx+1]
0x180003b0c  xor     edi, edi
0x180003b0e  test    rcx, rcx
0x180003b11  jnz     short loc_180003B22
0x180003b13  mov     ecx, edi
0x180003b15  add     rcx, rcx; unsigned __int64
0x180003b18  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180003b1d  mov     r12, rax
0x180003b20  jmp     short loc_180003B8C
0x180003b22  xor     edx, edx
0x180003b24  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003b28  div     rcx
0x180003b2b  cmp     rax, 2
0x180003b2f  jnb     short loc_180003B15
0x180003b31  mov     [rsp+88h+arg_18], rdi
0x180003b39  lea     rdx, [rsp+88h+arg_18]
0x180003b41  lea     rcx, [rsp+88h+pExceptionObject]
0x180003b46  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180003b4c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180003b53  mov     [rsp+88h+pExceptionObject], rax
0x180003b58  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180003b5f  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180003b64  call    _CxxThrowException_0
0x180003b6a  xor     edi, edi
0x180003b6c  mov     rsi, [rsp+88h+arg_0]
0x180003b74  mov     r15, [rsp+88h+arg_10]
0x180003b7c  mov     rbx, [rsp+88h+arg_8]
0x180003b84  mov     r12, [rsp+88h+arg_18]
0x180003b8c  lea     r14, [rsi+8]
0x180003b90  test    r15, r15
0x180003b93  jz      short loc_180003BBE
0x180003b95  cmp     qword ptr [rsi+20h], 8
0x180003b9a  jb      short loc_180003BA1
0x180003b9c  mov     r8, [r14]
0x180003b9f  jmp     short loc_180003BA4
0x180003ba1  mov     r8, r14; Source
0x180003ba4  lea     r13, [r15+r15]
0x180003ba8  lea     rdx, ds:2[rbx*2]; DestinationSize
0x180003bb0  mov     r9, r13; SourceSize
0x180003bb3  mov     rcx, r12; Destination
0x180003bb6  call    cs:__imp_memcpy_s
0x180003bbc  jmp     short loc_180003BC2
0x180003bbe  lea     r13, [r15+r15]
0x180003bc2  xor     r8d, r8d
0x180003bc5  mov     dl, 1
0x180003bc7  mov     rcx, rsi
0x180003bca  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x180003bcf  mov     [r14], r12
0x180003bd2  mov     [rsi+20h], rbx
0x180003bd6  cmp     rbx, 8
0x180003bda  cmovnb  r14, r12
0x180003bde  mov     [rsi+18h], r15
0x180003be2  mov     [r14+r13], di
0x180003be7  add     rsp, 50h
0x180003beb  pop     r15
0x180003bed  pop     r14
0x180003bef  pop     r13
0x180003bf1  pop     r12
0x180003bf3  pop     rdi
0x180003bf4  pop     rsi
0x180003bf5  pop     rbx
0x180003bf6  retn
```
