# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140004868`
- end: `0x1400049bf`
- name: `?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `343`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004bb0`

## callees

- `0x140001cc6`
- `0x140004868`
- `0x140004f9c`
- `0x14000ed18`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x14000490e`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x14000490e`
- `msvcrt!memcpy_s` at `0x14000497e`
- `msvcrt!memcpy_s` at `0x14000497e`

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
  __int64 v12; // r9
  char *v13; // r12
  const void **v14; // r14
  const void *v15; // r8
  __int64 v16; // r13
  __int64 result; // rax
  __int64 v18; // r9
  unsigned __int64 v19; // rcx
  __int64 *v20; // rdx
  __int64 v21; // [rsp+0h] [rbp-88h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v23[10]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v25; // [rsp+90h] [rbp+8h]
  const char *v26; // [rsp+98h] [rbp+10h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+18h]
  char *v28; // [rsp+A8h] [rbp+20h] BYREF

  v27 = a3;
  v26 = (const char *)a2;
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
      v28 = 0;
      exception::exception((exception *)pExceptionObject, (const char *const *)&v28);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    v13 = (char *)MmAllocate(2 * v10);
  }
  catch ( ... )
  {
    v19 = (unsigned __int64)(v26 + 1);
    if ( v26 == (const char *)-1LL || 0xFFFFFFFFFFFFFFFFuLL / v19 >= 2 )
    {
      v28 = (char *)MmAllocate(2 * v19);
      v5 = a1;
      v3 = v27;
      v4 = (unsigned __int64)v26;
      v13 = v28;
      goto LABEL_10;
    }
    try
    {
      exception::exception((exception *)v23, &v26);
      v23[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)v23;
    }
    catch ( ... )
    {
      v20 = &v21;
      LOBYTE(v20) = 1;
      std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
        v25,
        v20,
        0,
        v18);
      throw;
    }
  }
LABEL_10:
  v14 = (const void **)(v5 + 8);
  if ( v3 )
  {
    if ( *(_QWORD *)(v5 + 32) < 8u )
      v15 = (const void *)(v5 + 8);
    else
      v15 = *v14;
    v16 = 2 * v3;
    memcpy_s(v13, 2 * v4 + 2, v15, 2 * v3);
  }
  else
  {
    v16 = 0;
  }
  LOBYTE(v11) = 1;
  result = std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
             v5,
             v11,
             0,
             v12);
  *v14 = v13;
  *(_QWORD *)(v5 + 32) = v4;
  if ( v4 >= 8 )
    v14 = (const void **)v13;
  *(_QWORD *)(v5 + 24) = v3;
  *(_WORD *)((char *)v14 + v16) = 0;
  return result;
}

```

## disassembly

```asm
0x140004868  mov     [rsp+arg_10], r8
0x14000486d  mov     [rsp+arg_8], rdx
0x140004872  mov     [rsp+arg_0], rcx
0x140004877  push    rbx
0x140004878  push    rsi
0x140004879  push    rdi
0x14000487a  push    r12
0x14000487c  push    r13
0x14000487e  push    r14
0x140004880  push    r15
0x140004882  sub     rsp, 50h
0x140004886  mov     r15, r8
0x140004889  mov     rbx, rdx
0x14000488c  mov     rsi, rcx
0x14000488f  or      rdx, 7
0x140004893  mov     r9, 7FFFFFFFFFFFFFFEh
0x14000489d  cmp     rdx, r9
0x1400048a0  ja      short loc_1400048D0
0x1400048a2  mov     rbx, rdx
0x1400048a5  mov     r8, [rcx+20h]
0x1400048a9  mov     rcx, r8
0x1400048ac  shr     rcx, 1
0x1400048af  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400048b9  mul     rdx
0x1400048bc  shr     rdx, 1
0x1400048bf  cmp     rdx, rcx
0x1400048c2  jnb     short loc_1400048D0
0x1400048c4  sub     r9, rcx
0x1400048c7  cmp     r8, r9
0x1400048ca  ja      short loc_1400048D0
0x1400048cc  lea     rbx, [rcx+r8]
0x1400048d0  lea     rcx, [rbx+1]
0x1400048d4  xor     edi, edi
0x1400048d6  test    rcx, rcx
0x1400048d9  jnz     short loc_1400048EA
0x1400048db  mov     ecx, edi
0x1400048dd  add     rcx, rcx; unsigned __int64
0x1400048e0  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1400048e5  mov     r12, rax
0x1400048e8  jmp     short loc_140004954
0x1400048ea  xor     edx, edx
0x1400048ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400048f0  div     rcx
0x1400048f3  cmp     rax, 2
0x1400048f7  jnb     short loc_1400048DD
0x1400048f9  mov     [rsp+88h+arg_18], rdi
0x140004901  lea     rdx, [rsp+88h+arg_18]
0x140004909  lea     rcx, [rsp+88h+pExceptionObject]
0x14000490e  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x140004914  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x14000491b  mov     [rsp+88h+pExceptionObject], rax
0x140004920  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x140004927  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x14000492c  call    _CxxThrowException_0
0x140004932  xor     edi, edi
0x140004934  mov     rsi, [rsp+88h+arg_0]
0x14000493c  mov     r15, [rsp+88h+arg_10]
0x140004944  mov     rbx, [rsp+88h+arg_8]
0x14000494c  mov     r12, [rsp+88h+arg_18]
0x140004954  lea     r14, [rsi+8]
0x140004958  test    r15, r15
0x14000495b  jz      short loc_140004986
0x14000495d  cmp     qword ptr [rsi+20h], 8
0x140004962  jb      short loc_140004969
0x140004964  mov     r8, [r14]
0x140004967  jmp     short loc_14000496C
0x140004969  mov     r8, r14; Source
0x14000496c  lea     r13, [r15+r15]
0x140004970  lea     rdx, ds:2[rbx*2]; DestinationSize
0x140004978  mov     r9, r13; SourceSize
0x14000497b  mov     rcx, r12; Destination
0x14000497e  call    cs:__imp_memcpy_s
0x140004984  jmp     short loc_14000498A
0x140004986  lea     r13, [r15+r15]
0x14000498a  xor     r8d, r8d
0x14000498d  mov     dl, 1
0x14000498f  mov     rcx, rsi
0x140004992  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x140004997  mov     [r14], r12
0x14000499a  mov     [rsi+20h], rbx
0x14000499e  cmp     rbx, 8
0x1400049a2  cmovnb  r14, r12
0x1400049a6  mov     [rsi+18h], r15
0x1400049aa  mov     [r14+r13], di
0x1400049af  add     rsp, 50h
0x1400049b3  pop     r15
0x1400049b5  pop     r14
0x1400049b7  pop     r13
0x1400049b9  pop     r12
0x1400049bb  pop     rdi
0x1400049bc  pop     rsi
0x1400049bd  pop     rbx
0x1400049be  retn
```
