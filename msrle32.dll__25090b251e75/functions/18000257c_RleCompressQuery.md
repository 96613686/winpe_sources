# RleCompressQuery

- ea: `0x18000257c`
- end: `0x1800025bd`
- name: `RleCompressQuery`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001cd0`
- `0x18000241c`

## callees

- `0x18000257c`

## pseudocode

```c
__int64 __fastcall RleCompressQuery(__int64 a1, __int64 a2, __int64 a3)
{
  if ( a2
    && *(_WORD *)(a2 + 14) == 8
    && !*(_DWORD *)(a2 + 16)
    && (!a3
     || *(_DWORD *)(a3 + 16) == 1
     && *(_WORD *)(a3 + 14) == 8
     && *(_DWORD *)(a3 + 4) == *(_DWORD *)(a2 + 4)
     && *(_DWORD *)(a3 + 8) == *(_DWORD *)(a2 + 8)) )
  {
    return 0;
  }
  else
  {
    return 4294967294LL;
  }
}

```

## disassembly

```asm
0x18000257c  test    rdx, rdx
0x18000257f  jz      short loc_1800025B7
0x180002581  cmp     word ptr [rdx+0Eh], 8
0x180002586  jnz     short loc_1800025B7
0x180002588  cmp     dword ptr [rdx+10h], 0
0x18000258c  jnz     short loc_1800025B7
0x18000258e  test    r8, r8
0x180002591  jnz     short loc_180002596
0x180002593  xor     eax, eax
0x180002595  retn
0x180002596  cmp     dword ptr [r8+10h], 1
0x18000259b  jnz     short loc_1800025B7
0x18000259d  cmp     word ptr [r8+0Eh], 8
0x1800025a3  jnz     short loc_1800025B7
0x1800025a5  mov     eax, [rdx+4]
0x1800025a8  cmp     [r8+4], eax
0x1800025ac  jnz     short loc_1800025B7
0x1800025ae  mov     eax, [rdx+8]
0x1800025b1  cmp     [r8+8], eax
0x1800025b5  jz      short loc_180002593
0x1800025b7  mov     eax, 0FFFFFFFEh
0x1800025bc  retn
```
