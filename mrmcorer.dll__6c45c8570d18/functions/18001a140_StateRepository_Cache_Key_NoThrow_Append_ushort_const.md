# StateRepository::Cache::Key_NoThrow::Append(ushort const *)

- ea: `0x18001a140`
- end: `0x18001a36d`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z`
- size: `557`
- prototype: `__int64 __fastcall(StateRepository::Cache::Key_NoThrow *__hidden this, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180019694`
- `0x180019e3c`
- `0x180063500`
- `0x180063c0c`
- `0x180064204`
- `0x180064528`
- `0x1800648a4`

## callees

- `0x18001a140`
- `0x18002c8d0`
- `0x180088d45`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a340`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a340`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18001a2f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18001a2f0`

## string_xrefs

- `0x18001a251`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001a279`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001a303`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001a31f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(
        StateRepository::Cache::Key_NoThrow *this,
        const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // r14
  unsigned __int64 v4; // rbx
  const unsigned __int16 *v5; // rax
  __int64 v6; // rbp
  unsigned __int64 v7; // rdi
  __int64 v8; // r8
  __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  _WORD *v11; // rax
  unsigned int v12; // esi
  unsigned __int64 v13; // rax
  _WORD *v14; // rdx
  unsigned __int64 j; // rdi
  _WORD *v16; // rcx
  __int64 v18; // rcx
  void *v19; // rax
  void *v20; // rsi
  unsigned __int64 v21; // rdx
  _WORD *i; // rcx
  int v23; // [rsp+20h] [rbp-38h]
  int v24; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = a2;
  if ( !a2 )
    return 0;
  v4 = 0;
  v5 = a2;
  v6 = 0;
  while ( *v5 )
  {
    if ( ++v4 >= 0x7FFFFFFF )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x80070057LL,
        v23);
      return 2147942487LL;
    }
    if ( *v5 == 94 )
      ++v6;
    ++v5;
  }
  v7 = v4 + v6 + *((_QWORD *)this + 65) + 1LL;
  if ( v7 <= *((_QWORD *)this + 66) )
  {
    v7 = *((_QWORD *)this + 66);
LABEL_10:
    v8 = *((_QWORD *)this + 67);
    if ( v6 )
    {
      v21 = 0;
      for ( i = (_WORD *)(v8 + 2LL * *((_QWORD *)this + 65)); v21 < v4; ++i )
      {
        if ( *v2 == 94 )
          *i++ = 94;
        ++v21;
        *i = *v2++;
      }
      *i = 0;
    }
    else
    {
      v9 = 2147483646;
      if ( v7 - 1 > 0x7FFFFFFE )
      {
        v12 = -2147024809;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x139,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)v12,
          v23);
        return v12;
      }
      v10 = v7;
      v11 = (_WORD *)*((_QWORD *)this + 67);
      do
      {
        if ( !*v11 )
          break;
        ++v11;
        --v10;
      }
      while ( v10 );
      v12 = -2147024809;
      if ( !v10 )
        goto LABEL_23;
      v13 = v7 - v10;
      v14 = (_WORD *)(v8 + 2 * (v7 - v10));
      for ( j = v7 - v13; j; --j )
      {
        if ( !v9 )
          break;
        if ( !*v2 )
          break;
        *v14++ = *v2++;
        --v9;
      }
      v16 = v14 - 1;
      v12 = -2147024774;
      if ( j )
      {
        v16 = v14;
        v12 = 0;
      }
      *v16 = 0;
      if ( !j )
        goto LABEL_23;
    }
    *((_QWORD *)this + 65) += v4;
    return 0;
  }
  v19 = (void *)SRCache_AllocStringBuffer((unsigned int)v7);
  v20 = v19;
  if ( v19 )
  {
    memcpy_0(v19, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
    v18 = *(_QWORD *)this;
    *(_QWORD *)this = v20;
    if ( v18 )
      SRCache_Free();
    *((_QWORD *)this + 67) = *(_QWORD *)this;
    *((_QWORD *)this + 66) = v7;
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x193,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
    (const char *)0x8007000ELL,
    v23);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x136,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
    (const char *)0x8007000ELL,
    v24);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001a140  push    rbx
0x18001a142  push    rbp
0x18001a143  push    rsi
0x18001a144  push    rdi
0x18001a145  push    r14
0x18001a147  push    r15
0x18001a149  sub     rsp, 28h
0x18001a14d  mov     r14, rdx
0x18001a150  mov     r15, rcx
0x18001a153  test    rdx, rdx
0x18001a156  jz      loc_18001A2A8
0x18001a15c  xor     ebx, ebx
0x18001a15e  mov     rax, rdx
0x18001a161  xor     ebp, ebp
0x18001a163  movzx   r8d, word ptr [rax]
0x18001a167  test    r8w, r8w
0x18001a16b  jz      short loc_18001A18E
0x18001a16d  inc     rbx
0x18001a170  cmp     rbx, 7FFFFFFFh
0x18001a177  jnb     loc_18001A274
0x18001a17d  cmp     r8w, 5Eh ; '^'
0x18001a182  jz      loc_18001A2E6
0x18001a188  add     rax, 2
0x18001a18c  jmp     short loc_18001A163
0x18001a18e  mov     rdi, [rcx+208h]
0x18001a195  mov     rax, [rcx+210h]
0x18001a19c  inc     rdi
0x18001a19f  add     rdi, rbp
0x18001a1a2  add     rdi, rbx
0x18001a1a5  cmp     rdi, rax
0x18001a1a8  ja      loc_18001A2EE
0x18001a1ae  mov     rdi, rax
0x18001a1b1  mov     r8, [r15+218h]
0x18001a1b8  test    rbp, rbp
0x18001a1bb  jnz     loc_18001A352
0x18001a1c1  lea     rax, [rdi-1]
0x18001a1c5  mov     ecx, 7FFFFFFEh
0x18001a1ca  cmp     rax, rcx
0x18001a1cd  ja      loc_18001A348
0x18001a1d3  mov     rdx, rdi
0x18001a1d6  mov     rax, r8
0x18001a1d9  cmp     word ptr [rax], 0
0x18001a1dd  jz      short loc_18001A1E9
0x18001a1df  add     rax, 2
0x18001a1e3  sub     rdx, 1
0x18001a1e7  jnz     short loc_18001A1D9
0x18001a1e9  xor     eax, eax
0x18001a1eb  mov     esi, 80070057h
0x18001a1f0  test    rdx, rdx
0x18001a1f3  cmovnz  esi, eax
0x18001a1f6  jz      short loc_18001A24C
0x18001a1f8  mov     rax, rdi
0x18001a1fb  sub     rax, rdx
0x18001a1fe  test    rdx, rdx
0x18001a201  jz      short loc_18001A24C
0x18001a203  lea     rdx, [r8+rax*2]
0x18001a207  sub     rdi, rax
0x18001a20a  jz      short loc_18001A232
0x18001a20c  nop     dword ptr [rax+00h]
0x18001a210  test    rcx, rcx
0x18001a213  jz      short loc_18001A232
0x18001a215  movzx   eax, word ptr [r14]
0x18001a219  test    ax, ax
0x18001a21c  jz      short loc_18001A232
0x18001a21e  mov     [rdx], ax
0x18001a221  add     r14, 2
0x18001a225  add     rdx, 2
0x18001a229  dec     rcx
0x18001a22c  sub     rdi, 1
0x18001a230  jnz     short loc_18001A210
0x18001a232  xor     eax, eax
0x18001a234  lea     rcx, [rdx-2]
0x18001a238  test    rdi, rdi
0x18001a23b  mov     esi, 8007007Ah
0x18001a240  cmovnz  rcx, rdx
0x18001a244  cmovnz  esi, eax
0x18001a247  mov     [rcx], ax
0x18001a24a  jnz     short loc_18001A2A1
0x18001a24c  mov     rcx, [rsp+58h]; this
0x18001a251  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a258  mov     r9d, esi; char *
0x18001a25b  mov     edx, 139h; void *
0x18001a260  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a265  mov     eax, esi
0x18001a267  add     rsp, 28h
0x18001a26b  pop     r15
0x18001a26d  pop     r14
0x18001a26f  pop     rdi
0x18001a270  pop     rsi
0x18001a271  pop     rbp
0x18001a272  pop     rbx
0x18001a273  retn
0x18001a274  mov     rcx, [rsp+58h]; this
0x18001a279  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a280  mov     esi, 80070057h
0x18001a285  mov     edx, 135h; void *
0x18001a28a  mov     r9d, esi; char *
0x18001a28d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a292  mov     eax, esi
0x18001a294  add     rsp, 28h
0x18001a298  pop     r15
0x18001a29a  pop     r14
0x18001a29c  pop     rdi
0x18001a29d  pop     rsi
0x18001a29e  pop     rbp
0x18001a29f  pop     rbx
0x18001a2a0  retn
0x18001a2a1  add     [r15+208h], rbx
0x18001a2a8  xor     eax, eax
0x18001a2aa  jmp     short loc_18001A267
0x18001a2ac  mov     r8, [r15+210h]
0x18001a2b3  mov     rcx, rsi; void *
0x18001a2b6  mov     rdx, [r15+218h]; Src
0x18001a2bd  add     r8, r8; Size
0x18001a2c0  call    memcpy_0
0x18001a2c5  mov     rcx, [r15]
0x18001a2c8  mov     [r15], rsi
0x18001a2cb  test    rcx, rcx
0x18001a2ce  jnz     short loc_18001A340
0x18001a2d0  mov     rax, [r15]
0x18001a2d3  mov     [r15+218h], rax
0x18001a2da  mov     [r15+210h], rdi
0x18001a2e1  jmp     loc_18001A1B1
0x18001a2e6  inc     rbp
0x18001a2e9  jmp     loc_18001A188
0x18001a2ee  mov     ecx, edi
0x18001a2f0  call    cs:__imp_SRCache_AllocStringBuffer
0x18001a2f6  mov     rsi, rax
0x18001a2f9  test    rax, rax
0x18001a2fc  jnz     short loc_18001A2AC
0x18001a2fe  mov     rcx, [rsp+58h]; this
0x18001a303  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a30a  mov     r9d, 8007000Eh; char *
0x18001a310  mov     edx, 193h; void *
0x18001a315  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a31a  mov     rcx, [rsp+58h]; this
0x18001a31f  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a326  mov     r9d, 8007000Eh; char *
0x18001a32c  mov     edx, 136h; void *
0x18001a331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a336  mov     eax, 8007000Eh
0x18001a33b  jmp     loc_18001A267
0x18001a340  call    cs:__imp_SRCache_Free
0x18001a346  jmp     short loc_18001A2D0
0x18001a348  mov     esi, 80070057h
0x18001a34d  jmp     loc_18001A24C
0x18001a352  mov     rax, [r15+208h]
0x18001a359  xor     edx, edx
0x18001a35b  lea     rcx, [r8+rax*2]
0x18001a35f  test    rbx, rbx
0x18001a362  jnz     loc_1800C118C
0x18001a368  jmp     loc_1800C11B3
0x1800c118c  cmp     word ptr [r14], 5Eh ; '^'
0x1800c1191  jnz     short loc_1800C119C
0x1800c1193  mov     word ptr [rcx], 5Eh ; '^'
0x1800c1198  add     rcx, 2
0x1800c119c  movzx   eax, word ptr [r14]
0x1800c11a0  inc     rdx
0x1800c11a3  mov     [rcx], ax
0x1800c11a6  add     r14, 2
0x1800c11aa  add     rcx, 2
0x1800c11ae  cmp     rdx, rbx
0x1800c11b1  jb      short loc_1800C118C
0x1800c11b3  xor     eax, eax
0x1800c11b5  mov     [rcx], ax
0x1800c11b8  jmp     loc_18001A2A1
```
