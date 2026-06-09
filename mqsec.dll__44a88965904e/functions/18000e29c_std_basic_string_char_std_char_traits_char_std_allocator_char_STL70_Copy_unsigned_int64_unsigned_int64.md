# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000e29c`
- end: `0x18000e37a`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `222`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e78c`
- `0x180019e5c`

## callees

- `0x18000c598`
- `0x18000e29c`
- `0x18000ead8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e343`
- `msvcrt!memcpy_s` at `0x18000e343`

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
0x18000e29c  mov     [rsp+arg_10], r8
0x18000e2a1  mov     [rsp+arg_8], rdx
0x18000e2a6  mov     [rsp+arg_0], rcx
0x18000e2ab  push    rbx
0x18000e2ac  push    rsi
0x18000e2ad  push    rdi
0x18000e2ae  push    r14
0x18000e2b0  push    r15
0x18000e2b2  sub     rsp, 20h
0x18000e2b6  mov     r14, r8
0x18000e2b9  mov     rbx, rdx
0x18000e2bc  mov     rdi, rcx
0x18000e2bf  or      rdx, 0Fh
0x18000e2c3  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000e2ca  cmp     rdx, r9
0x18000e2cd  ja      short loc_18000E2FD
0x18000e2cf  mov     rbx, rdx
0x18000e2d2  mov     r8, [rcx+20h]
0x18000e2d6  mov     rcx, r8
0x18000e2d9  shr     rcx, 1
0x18000e2dc  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000e2e6  mul     rdx
0x18000e2e9  shr     rdx, 1
0x18000e2ec  cmp     rdx, rcx
0x18000e2ef  jnb     short loc_18000E2FD
0x18000e2f1  sub     r9, rcx
0x18000e2f4  cmp     r8, r9
0x18000e2f7  ja      short loc_18000E2FD
0x18000e2f9  lea     rbx, [rcx+r8]
0x18000e2fd  lea     rcx, [rbx+1]
0x18000e301  xor     edx, edx
0x18000e303  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x18000e308  mov     r15, rax
0x18000e30b  jmp     short loc_18000E321
0x18000e30d  mov     rdi, [rsp+48h+arg_0]
0x18000e312  mov     r14, [rsp+48h+arg_10]
0x18000e317  mov     rbx, [rsp+48h+arg_8]
0x18000e31c  mov     r15, [rsp+48h+arg_18]
0x18000e321  lea     rsi, [rdi+8]
0x18000e325  test    r14, r14
0x18000e328  jz      short loc_18000E349
0x18000e32a  cmp     qword ptr [rdi+20h], 10h
0x18000e32f  jb      short loc_18000E336
0x18000e331  mov     r8, [rsi]
0x18000e334  jmp     short loc_18000E339
0x18000e336  mov     r8, rsi; Source
0x18000e339  lea     rdx, [rbx+1]; DestinationSize
0x18000e33d  mov     r9, r14; SourceSize
0x18000e340  mov     rcx, r15; Destination
0x18000e343  call    cs:__imp_memcpy_s
0x18000e349  xor     r8d, r8d
0x18000e34c  mov     dl, 1
0x18000e34e  mov     rcx, rdi
0x18000e351  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18000e356  mov     [rsi], r15
0x18000e359  mov     [rdi+20h], rbx
0x18000e35d  cmp     rbx, 10h
0x18000e361  cmovnb  rsi, r15
0x18000e365  mov     [rdi+18h], r14
0x18000e369  mov     byte ptr [rsi+r14], 0
0x18000e36e  add     rsp, 20h
0x18000e372  pop     r15
0x18000e374  pop     r14
0x18000e376  pop     rdi
0x18000e377  pop     rsi
0x18000e378  pop     rbx
0x18000e379  retn
```
