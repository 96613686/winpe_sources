# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::MatchToken(ushort const * *,int)

- ea: `0x180016698`
- end: `0x1800166b4`
- name: `?MatchToken@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGH@Z`
- size: `28`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180016d70`
- `0x180016f60`
- `0x1800170fc`
- `0x180017238`
- `0x18001763c`
- `0x180017ab8`

## callees

- `0x180016698`

## pseudocode

```c
__int64 __fastcall ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::MatchToken(__int64 a1, _QWORD *a2, int a3)
{
  if ( *(unsigned __int16 *)*a2 != a3 )
    return 0;
  *a2 += 2LL;
  return 1;
}

```

## disassembly

```asm
0x180016698  mov     rcx, [rdx]
0x18001669b  movzx   eax, word ptr [rcx]
0x18001669e  cmp     eax, r8d
0x1800166a1  jz      short loc_1800166A7
0x1800166a3  xor     eax, eax
0x1800166a5  retn
0x1800166a7  lea     rax, [rcx+2]
0x1800166ab  mov     [rdx], rax
0x1800166ae  mov     eax, 1
0x1800166b3  retn
```
