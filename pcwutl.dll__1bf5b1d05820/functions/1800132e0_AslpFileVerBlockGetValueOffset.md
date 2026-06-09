# AslpFileVerBlockGetValueOffset

- ea: `0x1800132e0`
- end: `0x18001336e`
- name: `AslpFileVerBlockGetValueOffset`
- size: `142`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180012708`
- `0x180013374`
- `0x180013594`

## callees

- `0x1800132e0`

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
0x1800132e0  xor     r10d, r10d
0x1800132e3  lea     rax, [r8-8]
0x1800132e7  mov     [rcx], r10
0x1800132ea  mov     r9, rcx
0x1800132ed  cmp     rax, 7FF7h
0x1800132f3  ja      short loc_180013368
0x1800132f5  lea     rax, [rdx+6]
0x1800132f9  test    rax, rax
0x1800132fc  jz      short loc_180013368
0x1800132fe  lea     rdx, [r8-6]
0x180013302  shr     rdx, 1
0x180013305  cmp     rdx, 7FFFFFFFh
0x18001330c  ja      short loc_180013368
0x18001330e  mov     rcx, rdx
0x180013311  test    rdx, rdx
0x180013314  jz      short loc_180013326
0x180013316  cmp     [rax], r10w
0x18001331a  jz      short loc_180013326
0x18001331c  add     rax, 2
0x180013320  sub     rdx, 1
0x180013324  jnz     short loc_180013316
0x180013326  mov     rax, rdx
0x180013329  neg     rax
0x18001332c  sbb     eax, eax
0x18001332e  not     eax
0x180013330  and     eax, 0C000000Dh
0x180013335  test    rdx, rdx
0x180013338  jz      short loc_18001333F
0x18001333a  sub     rcx, rdx
0x18001333d  jmp     short loc_180013342
0x18001333f  mov     rcx, r10
0x180013342  test    rdx, rdx
0x180013345  jz      short locret_18001336D
0x180013347  lea     rax, [rcx+rcx]
0x18001334b  lea     rcx, [rax+8]
0x18001334f  cmp     rcx, rax
0x180013352  jb      short loc_180013362
0x180013354  lea     rax, [rcx+3]
0x180013358  and     rax, 0FFFFFFFFFFFFFFFCh
0x18001335c  mov     [r9], rax
0x18001335f  xor     eax, eax
0x180013361  retn
0x180013362  mov     eax, 0C0000095h
0x180013367  retn
0x180013368  mov     eax, 0C000000Dh
0x18001336d  retn
```
