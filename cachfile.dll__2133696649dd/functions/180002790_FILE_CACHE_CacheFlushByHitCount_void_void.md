# FILE_CACHE::CacheFlushByHitCount(void *,void *)

- ea: `0x180002790`
- end: `0x1800027cb`
- name: `?CacheFlushByHitCount@FILE_CACHE@@CAHPEAX0@Z`
- size: `59`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002790`

## pseudocode

```c
_BOOL8 __fastcall FILE_CACHE::CacheFlushByHitCount(_BYTE *a1, void *a2)
{
  char v2; // al
  unsigned int v4; // r8d

  v2 = a1[321];
  a1[321] = 0;
  if ( v2 )
    return 0;
  v4 = *((_DWORD *)a1 + 66);
  *((_DWORD *)a1 + 66) = v4 >> 1;
  return !v4 || v4 < (unsigned int)a2;
}

```

## disassembly

```asm
0x180002790  movzx   eax, byte ptr [rcx+141h]
0x180002797  mov     byte ptr [rcx+141h], 0
0x18000279e  test    al, al
0x1800027a0  jz      short loc_1800027A5
0x1800027a2  xor     eax, eax
0x1800027a4  retn
0x1800027a5  mov     r8d, [rcx+108h]
0x1800027ac  mov     eax, r8d
0x1800027af  shr     eax, 1
0x1800027b1  mov     [rcx+108h], eax
0x1800027b7  test    r8d, r8d
0x1800027ba  jnz     short loc_1800027C2
0x1800027bc  mov     eax, 1
0x1800027c1  retn
0x1800027c2  xor     eax, eax
0x1800027c4  cmp     r8d, edx
0x1800027c7  setb    al
0x1800027ca  retn
```
