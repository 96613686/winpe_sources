# _FindPESection

- ea: `0x180001590`
- end: `0x1800015d4`
- name: `_FindPESection`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015e0`

## callees

- `0x180001590`

## pseudocode

```c
__int64 __fastcall FindPESection(__int64 a1, unsigned __int64 a2)
{
  unsigned int v2; // r9d
  __int64 v3; // r8
  __int64 result; // rax
  unsigned __int64 v6; // rdx

  v2 = 0;
  v3 = a1 + *(int *)(a1 + 60);
  result = v3 + *(unsigned __int16 *)(v3 + 20) + 24LL;
  if ( !*(_WORD *)(v3 + 6) )
    return 0;
  while ( 1 )
  {
    v6 = *(unsigned int *)(result + 12);
    if ( a2 >= v6 && a2 < (unsigned int)(v6 + *(_DWORD *)(result + 8)) )
      break;
    ++v2;
    result += 40;
    if ( v2 >= *(unsigned __int16 *)(v3 + 6) )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001590  movsxd  r8, dword ptr [rcx+3Ch]
0x180001594  xor     r9d, r9d
0x180001597  add     r8, rcx
0x18000159a  mov     r10, rdx
0x18000159d  movzx   eax, word ptr [r8+14h]
0x1800015a2  movzx   r11d, word ptr [r8+6]
0x1800015a7  add     rax, 18h
0x1800015ab  add     rax, r8
0x1800015ae  test    r11d, r11d
0x1800015b1  jz      short loc_1800015D1
0x1800015b3  mov     edx, [rax+0Ch]
0x1800015b6  cmp     r10, rdx
0x1800015b9  jb      short loc_1800015C5
0x1800015bb  mov     ecx, [rax+8]
0x1800015be  add     ecx, edx
0x1800015c0  cmp     r10, rcx
0x1800015c3  jb      short locret_1800015D3
0x1800015c5  inc     r9d
0x1800015c8  add     rax, 28h ; '('
0x1800015cc  cmp     r9d, r11d
0x1800015cf  jb      short loc_1800015B3
0x1800015d1  xor     eax, eax
0x1800015d3  retn
```
