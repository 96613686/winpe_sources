# CompareFunction

- ea: `0x1800425f0`
- end: `0x180042611`
- name: `CompareFunction`
- size: `33`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800425f0`

## pseudocode

```c
__int64 __fastcall CompareFunction(_QWORD *a1, _QWORD *a2)
{
  unsigned __int64 v2; // r8
  unsigned __int64 v3; // rdx

  v2 = a2[287];
  v3 = a1[287];
  if ( v3 <= v2 )
    return v3 < v2;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800425f0  mov     r8, [rdx+8F8h]
0x1800425f7  mov     rdx, [rcx+8F8h]
0x1800425fe  cmp     rdx, r8
0x180042601  jbe     short loc_180042608
0x180042603  or      eax, 0FFFFFFFFh
0x180042606  retn
0x180042608  xor     eax, eax
0x18004260a  cmp     rdx, r8
0x18004260d  setb    al
0x180042610  retn
```
