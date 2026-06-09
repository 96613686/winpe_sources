# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::CNode * &)

- ea: `0x14000f6b0`
- end: `0x14000f776`
- name: `?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VItem@TokenCache@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VItem@TokenCache@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z`
- size: `198`
- prototype: `unsigned __int16 *__fastcall(__int64 *, unsigned __int16 *, _DWORD *, unsigned int *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f2ac`
- `0x14000f5f0`
- `0x14000f8f4`
- `0x14001a28c`
- `0x14001b3f0`
- `0x14001b9fc`

## callees

- `0x140005c58`
- `0x14000f6b0`

## pseudocode

```c
unsigned __int16 *__fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<TokenCache::Item>>::GetNode(
        __int64 *a1,
        unsigned __int16 *a2,
        _DWORD *a3,
        unsigned int *a4,
        unsigned __int16 **a5)
{
  unsigned int v8; // r8d
  unsigned __int16 v9; // ax
  unsigned __int16 *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned __int16 *result; // rax
  unsigned __int16 *v14; // r11
  unsigned __int16 *v15; // rcx
  int v16; // ebx
  int v17; // edx

  if ( !a2 )
    ATL::AtlThrowImpl(0x80004005);
  v8 = 0;
  v9 = *a2;
  if ( *a2 )
  {
    v10 = a2;
    do
    {
      v8 = v9 + 33 * v8;
      v9 = *++v10;
    }
    while ( *v10 );
  }
  *a4 = v8;
  v11 = v8 % *((_DWORD *)a1 + 4);
  *a3 = v11;
  v12 = *a1;
  if ( !*a1 )
    return 0;
  *a5 = 0;
  result = *(unsigned __int16 **)(v12 + 8 * v11);
  if ( !result )
    return 0;
  v14 = 0;
  while ( 1 )
  {
    if ( *((_DWORD *)result + 10) == v8 )
    {
      v15 = *(unsigned __int16 **)result;
      do
      {
        v16 = *(unsigned __int16 *)((char *)a2 + (_QWORD)v15 - *(_QWORD *)result);
        v17 = *v15 - v16;
        if ( v17 )
          break;
        ++v15;
      }
      while ( v16 );
      if ( !v17 )
        break;
    }
    v14 = result;
    result = (unsigned __int16 *)*((_QWORD *)result + 4);
    if ( !result )
      return 0;
  }
  *a5 = v14;
  return result;
}

```

## disassembly

```asm
0x14000f6b0  mov     [rsp+arg_0], rbx
0x14000f6b5  mov     [rsp+arg_8], rsi
0x14000f6ba  push    rdi
0x14000f6bb  sub     rsp, 20h
0x14000f6bf  mov     rbx, r8
0x14000f6c2  mov     r10, rdx
0x14000f6c5  mov     r11, rcx
0x14000f6c8  xor     esi, esi
0x14000f6ca  test    rdx, rdx
0x14000f6cd  jz      loc_14000F76B
0x14000f6d3  mov     r8d, esi
0x14000f6d6  movzx   eax, word ptr [rdx]
0x14000f6d9  test    ax, ax
0x14000f6dc  jz      short loc_14000F6F7
0x14000f6de  mov     rcx, rdx
0x14000f6e1  imul    r8d, 21h ; '!'
0x14000f6e5  movzx   eax, ax
0x14000f6e8  add     r8d, eax
0x14000f6eb  lea     rcx, [rcx+2]
0x14000f6ef  movzx   eax, word ptr [rcx]
0x14000f6f2  test    ax, ax
0x14000f6f5  jnz     short loc_14000F6E1
0x14000f6f7  mov     [r9], r8d
0x14000f6fa  xor     edx, edx
0x14000f6fc  mov     eax, r8d
0x14000f6ff  div     dword ptr [r11+10h]
0x14000f703  mov     [rbx], edx
0x14000f705  mov     rcx, [r11]
0x14000f708  test    rcx, rcx
0x14000f70b  jz      short loc_14000F754
0x14000f70d  mov     rdi, [rsp+28h+arg_20]
0x14000f712  mov     [rdi], rsi
0x14000f715  mov     rax, [rcx+rdx*8]
0x14000f719  test    rax, rax
0x14000f71c  jz      short loc_14000F754
0x14000f71e  mov     r11, rsi
0x14000f721  cmp     [rax+28h], r8d
0x14000f725  jnz     short loc_14000F748
0x14000f727  mov     rcx, [rax]
0x14000f72a  mov     r9, r10
0x14000f72d  sub     r9, rcx
0x14000f730  movzx   edx, word ptr [rcx]
0x14000f733  movzx   ebx, word ptr [rcx+r9]
0x14000f738  sub     edx, ebx
0x14000f73a  jnz     short loc_14000F744
0x14000f73c  add     rcx, 2
0x14000f740  test    ebx, ebx
0x14000f742  jnz     short loc_14000F730
0x14000f744  test    edx, edx
0x14000f746  jz      short loc_14000F766
0x14000f748  mov     r11, rax
0x14000f74b  mov     rax, [rax+20h]
0x14000f74f  test    rax, rax
0x14000f752  jnz     short loc_14000F721
0x14000f754  xor     eax, eax
0x14000f756  mov     rbx, [rsp+28h+arg_0]
0x14000f75b  mov     rsi, [rsp+28h+arg_8]
0x14000f760  add     rsp, 20h
0x14000f764  pop     rdi
0x14000f765  retn
0x14000f766  mov     [rdi], r11
0x14000f769  jmp     short loc_14000F756
0x14000f76b  mov     ecx, 80004005h; unsigned int
0x14000f770  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
