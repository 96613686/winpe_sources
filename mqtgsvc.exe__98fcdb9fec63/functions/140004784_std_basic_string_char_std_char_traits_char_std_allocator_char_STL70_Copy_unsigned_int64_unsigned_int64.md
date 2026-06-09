# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140004784`
- end: `0x140004862`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `222`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, rsize_t)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140004b18`

## callees

- `0x140003958`
- `0x140004784`
- `0x140004f2c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000482b`
- `msvcrt!memcpy_s` at `0x14000482b`

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
0x140004784  mov     [rsp+arg_10], r8
0x140004789  mov     [rsp+arg_8], rdx
0x14000478e  mov     [rsp+arg_0], rcx
0x140004793  push    rbx
0x140004794  push    rsi
0x140004795  push    rdi
0x140004796  push    r14
0x140004798  push    r15
0x14000479a  sub     rsp, 20h
0x14000479e  mov     r14, r8
0x1400047a1  mov     rbx, rdx
0x1400047a4  mov     rdi, rcx
0x1400047a7  or      rdx, 0Fh
0x1400047ab  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1400047b2  cmp     rdx, r9
0x1400047b5  ja      short loc_1400047E5
0x1400047b7  mov     rbx, rdx
0x1400047ba  mov     r8, [rcx+20h]
0x1400047be  mov     rcx, r8
0x1400047c1  shr     rcx, 1
0x1400047c4  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400047ce  mul     rdx
0x1400047d1  shr     rdx, 1
0x1400047d4  cmp     rdx, rcx
0x1400047d7  jnb     short loc_1400047E5
0x1400047d9  sub     r9, rcx
0x1400047dc  cmp     r8, r9
0x1400047df  ja      short loc_1400047E5
0x1400047e1  lea     rbx, [rcx+r8]
0x1400047e5  lea     rcx, [rbx+1]
0x1400047e9  xor     edx, edx
0x1400047eb  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x1400047f0  mov     r15, rax
0x1400047f3  jmp     short loc_140004809
0x1400047f5  mov     rdi, [rsp+48h+arg_0]
0x1400047fa  mov     r14, [rsp+48h+arg_10]
0x1400047ff  mov     rbx, [rsp+48h+arg_8]
0x140004804  mov     r15, [rsp+48h+arg_18]
0x140004809  lea     rsi, [rdi+8]
0x14000480d  test    r14, r14
0x140004810  jz      short loc_140004831
0x140004812  cmp     qword ptr [rdi+20h], 10h
0x140004817  jb      short loc_14000481E
0x140004819  mov     r8, [rsi]
0x14000481c  jmp     short loc_140004821
0x14000481e  mov     r8, rsi; Source
0x140004821  lea     rdx, [rbx+1]; DestinationSize
0x140004825  mov     r9, r14; SourceSize
0x140004828  mov     rcx, r15; Destination
0x14000482b  call    cs:__imp_memcpy_s
0x140004831  xor     r8d, r8d
0x140004834  mov     dl, 1
0x140004836  mov     rcx, rdi
0x140004839  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x14000483e  mov     [rsi], r15
0x140004841  mov     [rdi+20h], rbx
0x140004845  cmp     rbx, 10h
0x140004849  cmovnb  rsi, r15
0x14000484d  mov     [rdi+18h], r14
0x140004851  mov     byte ptr [rsi+r14], 0
0x140004856  add     rsp, 20h
0x14000485a  pop     r15
0x14000485c  pop     r14
0x14000485e  pop     rdi
0x14000485f  pop     rsi
0x140004860  pop     rbx
0x140004861  retn
```
