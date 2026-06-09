# SuffixArrayJobIteratorMakeValid

- ea: `0x18001a714`
- end: `0x18001a75e`
- name: `SuffixArrayJobIteratorMakeValid`
- size: `74`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180017ba0`
- `0x180019e74`
- `0x18001a20c`

## callees

- `0x18001a714`

## pseudocode

```c
__int64 __fastcall SuffixArrayJobIteratorMakeValid(int *a1)
{
  __int64 v1; // r10
  __int64 v2; // r11
  __int64 result; // rax
  int v4; // r8d

  v1 = *((_QWORD *)a1 + 1);
  v2 = *a1;
  result = (unsigned int)(*(_DWORD *)(v1 + 4 * v2 + 36) - *(_DWORD *)(v1 + 4 * v2 + 1060));
  if ( a1[1] >= (int)result )
  {
    do
    {
      LODWORD(v2) = ((int)v2 + 1) % 256;
      *a1 = v2;
      v4 = *(_DWORD *)(v1 + 4LL * (int)v2 + 32);
      a1[1] = v4;
      result = (unsigned int)(*(_DWORD *)(v1 + 4LL * (int)v2 + 36) - *(_DWORD *)(v1 + 4LL * (int)v2 + 1060));
    }
    while ( v4 >= (int)result );
  }
  return result;
}

```

## disassembly

```asm
0x18001a714  mov     r10, [rcx+8]
0x18001a718  mov     r9, rcx
0x18001a71b  movsxd  r11, dword ptr [rcx]
0x18001a71e  mov     eax, [r10+r11*4+24h]
0x18001a723  sub     eax, [r10+r11*4+424h]
0x18001a72b  cmp     [rcx+4], eax
0x18001a72e  jl      short locret_18001A75D
0x18001a730  lea     eax, [r11+1]
0x18001a734  mov     ecx, 100h
0x18001a739  cdq
0x18001a73a  idiv    ecx
0x18001a73c  movsxd  r11, edx
0x18001a73f  mov     [r9], r11d
0x18001a742  mov     r8d, [r10+r11*4+20h]
0x18001a747  mov     [r9+4], r8d
0x18001a74b  mov     eax, [r10+r11*4+24h]
0x18001a750  sub     eax, [r10+r11*4+424h]
0x18001a758  cmp     r8d, eax
0x18001a75b  jge     short loc_18001A730
0x18001a75d  retn
```
