# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18001464c`
- end: `0x18001472a`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800147d8`

## callees

- `0x180012ed4`
- `0x18001464c`
- `0x180014ae8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800146f3`
- `msvcrt!memcpy_s` at `0x1800146f3`

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
0x18001464c  mov     [rsp+arg_10], r8
0x180014651  mov     [rsp+arg_8], rdx
0x180014656  mov     [rsp+arg_0], rcx
0x18001465b  push    rbx
0x18001465c  push    rsi
0x18001465d  push    rdi
0x18001465e  push    r14
0x180014660  push    r15
0x180014662  sub     rsp, 20h
0x180014666  mov     r14, r8
0x180014669  mov     rbx, rdx
0x18001466c  mov     rdi, rcx
0x18001466f  or      rdx, 0Fh
0x180014673  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18001467a  cmp     rdx, r9
0x18001467d  ja      short loc_1800146AD
0x18001467f  mov     rbx, rdx
0x180014682  mov     r8, [rcx+20h]
0x180014686  mov     rcx, r8
0x180014689  shr     rcx, 1
0x18001468c  mov     rax, 0AAAAAAAAAAAAAAABh
0x180014696  mul     rdx
0x180014699  shr     rdx, 1
0x18001469c  cmp     rdx, rcx
0x18001469f  jnb     short loc_1800146AD
0x1800146a1  sub     r9, rcx
0x1800146a4  cmp     r8, r9
0x1800146a7  ja      short loc_1800146AD
0x1800146a9  lea     rbx, [rcx+r8]
0x1800146ad  lea     rcx, [rbx+1]
0x1800146b1  xor     edx, edx
0x1800146b3  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x1800146b8  mov     r15, rax
0x1800146bb  jmp     short loc_1800146D1
0x1800146bd  mov     rdi, [rsp+48h+arg_0]
0x1800146c2  mov     r14, [rsp+48h+arg_10]
0x1800146c7  mov     rbx, [rsp+48h+arg_8]
0x1800146cc  mov     r15, [rsp+48h+arg_18]
0x1800146d1  lea     rsi, [rdi+8]
0x1800146d5  test    r14, r14
0x1800146d8  jz      short loc_1800146F9
0x1800146da  cmp     qword ptr [rdi+20h], 10h
0x1800146df  jb      short loc_1800146E6
0x1800146e1  mov     r8, [rsi]
0x1800146e4  jmp     short loc_1800146E9
0x1800146e6  mov     r8, rsi; Source
0x1800146e9  lea     rdx, [rbx+1]; DestinationSize
0x1800146ed  mov     r9, r14; SourceSize
0x1800146f0  mov     rcx, r15; Destination
0x1800146f3  call    cs:__imp_memcpy_s
0x1800146f9  xor     r8d, r8d
0x1800146fc  mov     dl, 1
0x1800146fe  mov     rcx, rdi
0x180014701  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180014706  mov     [rsi], r15
0x180014709  mov     [rdi+20h], rbx
0x18001470d  cmp     rbx, 10h
0x180014711  cmovnb  rsi, r15
0x180014715  mov     [rdi+18h], r14
0x180014719  mov     byte ptr [rsi+r14], 0
0x18001471e  add     rsp, 20h
0x180014722  pop     r15
0x180014724  pop     r14
0x180014726  pop     rdi
0x180014727  pop     rsi
0x180014728  pop     rbx
0x180014729  retn
```
