# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180024a80`
- end: `0x180024b5e`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180024be8`

## callees

- `0x180023f28`
- `0x180024a80`
- `0x180025104`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180024b27`
- `msvcrt!memcpy_s` at `0x180024b27`

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
0x180024a80  mov     [rsp+arg_10], r8
0x180024a85  mov     [rsp+arg_8], rdx
0x180024a8a  mov     [rsp+arg_0], rcx
0x180024a8f  push    rbx
0x180024a90  push    rsi
0x180024a91  push    rdi
0x180024a92  push    r14
0x180024a94  push    r15
0x180024a96  sub     rsp, 20h
0x180024a9a  mov     r14, r8
0x180024a9d  mov     rbx, rdx
0x180024aa0  mov     rdi, rcx
0x180024aa3  or      rdx, 0Fh
0x180024aa7  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180024aae  cmp     rdx, r9
0x180024ab1  ja      short loc_180024AE1
0x180024ab3  mov     rbx, rdx
0x180024ab6  mov     r8, [rcx+20h]
0x180024aba  mov     rcx, r8
0x180024abd  shr     rcx, 1
0x180024ac0  mov     rax, 0AAAAAAAAAAAAAAABh
0x180024aca  mul     rdx
0x180024acd  shr     rdx, 1
0x180024ad0  cmp     rdx, rcx
0x180024ad3  jnb     short loc_180024AE1
0x180024ad5  sub     r9, rcx
0x180024ad8  cmp     r8, r9
0x180024adb  ja      short loc_180024AE1
0x180024add  lea     rbx, [rcx+r8]
0x180024ae1  lea     rcx, [rbx+1]
0x180024ae5  xor     edx, edx
0x180024ae7  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x180024aec  mov     r15, rax
0x180024aef  jmp     short loc_180024B05
0x180024af1  mov     rdi, [rsp+48h+arg_0]
0x180024af6  mov     r14, [rsp+48h+arg_10]
0x180024afb  mov     rbx, [rsp+48h+arg_8]
0x180024b00  mov     r15, [rsp+48h+arg_18]
0x180024b05  lea     rsi, [rdi+8]
0x180024b09  test    r14, r14
0x180024b0c  jz      short loc_180024B2D
0x180024b0e  cmp     qword ptr [rdi+20h], 10h
0x180024b13  jb      short loc_180024B1A
0x180024b15  mov     r8, [rsi]
0x180024b18  jmp     short loc_180024B1D
0x180024b1a  mov     r8, rsi; Source
0x180024b1d  lea     rdx, [rbx+1]; DestinationSize
0x180024b21  mov     r9, r14; SourceSize
0x180024b24  mov     rcx, r15; Destination
0x180024b27  call    cs:__imp_memcpy_s
0x180024b2d  xor     r8d, r8d
0x180024b30  mov     dl, 1
0x180024b32  mov     rcx, rdi
0x180024b35  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180024b3a  mov     [rsi], r15
0x180024b3d  mov     [rdi+20h], rbx
0x180024b41  cmp     rbx, 10h
0x180024b45  cmovnb  rsi, r15
0x180024b49  mov     [rdi+18h], r14
0x180024b4d  mov     byte ptr [rsi+r14], 0
0x180024b52  add     rsp, 20h
0x180024b56  pop     r15
0x180024b58  pop     r14
0x180024b5a  pop     rdi
0x180024b5b  pop     rsi
0x180024b5c  pop     rbx
0x180024b5d  retn
```
