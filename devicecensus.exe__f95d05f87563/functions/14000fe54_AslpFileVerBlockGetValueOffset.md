# AslpFileVerBlockGetValueOffset

- ea: `0x14000fe54`
- end: `0x14000fee2`
- name: `AslpFileVerBlockGetValueOffset`
- size: `142`
- prototype: `__int64 __fastcall(unsigned __int64 *, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f3a8`
- `0x14000fee8`
- `0x140010108`

## callees

- `0x14000fe54`

## pseudocode

```c
__int64 __fastcall AslpFileVerBlockGetValueOffset(unsigned __int64 *a1, __int64 a2, __int64 a3)
{
  _WORD *v4; // rax
  unsigned __int64 v5; // rdx
  __int64 result; // rax
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx

  *a1 = 0;
  if ( (unsigned __int64)(a3 - 8) > 0x7FF7 )
    return 3221225485LL;
  v4 = (_WORD *)(a2 + 6);
  if ( a2 == -6 )
    return 3221225485LL;
  v5 = (unsigned __int64)(a3 - 6) >> 1;
  if ( v5 > 0x7FFFFFFF )
    return 3221225485LL;
  for ( ; v5; --v5 )
  {
    if ( !*v4 )
      break;
    ++v4;
  }
  result = v5 == 0 ? 0xC000000D : 0;
  if ( v5 )
    v7 = ((unsigned __int64)(a3 - 6) >> 1) - v5;
  else
    v7 = 0;
  if ( v5 )
  {
    v8 = 2 * v7;
    v9 = 2 * v7 + 8;
    if ( v9 < v8 )
    {
      return 3221225621LL;
    }
    else
    {
      *a1 = (v9 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000fe54  xor     r10d, r10d
0x14000fe57  lea     rax, [r8-8]
0x14000fe5b  mov     [rcx], r10
0x14000fe5e  mov     r9, rcx
0x14000fe61  cmp     rax, 7FF7h
0x14000fe67  ja      short loc_14000FEDC
0x14000fe69  lea     rax, [rdx+6]
0x14000fe6d  test    rax, rax
0x14000fe70  jz      short loc_14000FEDC
0x14000fe72  lea     rdx, [r8-6]
0x14000fe76  shr     rdx, 1
0x14000fe79  cmp     rdx, 7FFFFFFFh
0x14000fe80  ja      short loc_14000FEDC
0x14000fe82  mov     rcx, rdx
0x14000fe85  test    rdx, rdx
0x14000fe88  jz      short loc_14000FE9A
0x14000fe8a  cmp     [rax], r10w
0x14000fe8e  jz      short loc_14000FE9A
0x14000fe90  add     rax, 2
0x14000fe94  sub     rdx, 1
0x14000fe98  jnz     short loc_14000FE8A
0x14000fe9a  mov     rax, rdx
0x14000fe9d  neg     rax
0x14000fea0  sbb     eax, eax
0x14000fea2  not     eax
0x14000fea4  and     eax, 0C000000Dh
0x14000fea9  test    rdx, rdx
0x14000feac  jz      short loc_14000FEB3
0x14000feae  sub     rcx, rdx
0x14000feb1  jmp     short loc_14000FEB6
0x14000feb3  mov     rcx, r10
0x14000feb6  test    rdx, rdx
0x14000feb9  jz      short locret_14000FEE1
0x14000febb  lea     rax, [rcx+rcx]
0x14000febf  lea     rcx, [rax+8]
0x14000fec3  cmp     rcx, rax
0x14000fec6  jb      short loc_14000FED6
0x14000fec8  lea     rax, [rcx+3]
0x14000fecc  and     rax, 0FFFFFFFFFFFFFFFCh
0x14000fed0  mov     [r9], rax
0x14000fed3  xor     eax, eax
0x14000fed5  retn
0x14000fed6  mov     eax, 0C0000095h
0x14000fedb  retn
0x14000fedc  mov     eax, 0C000000Dh
0x14000fee1  retn
```
