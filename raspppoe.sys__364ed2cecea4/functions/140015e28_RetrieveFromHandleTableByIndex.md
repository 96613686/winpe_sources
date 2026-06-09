# RetrieveFromHandleTableByIndex

- ea: `0x140015e28`
- end: `0x140015e4f`
- name: `RetrieveFromHandleTableByIndex`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001608`
- `0x140003d18`

## callees

- `0x140015e28`

## pseudocode

```c
__int64 __fastcall RetrieveFromHandleTableByIndex(__int64 a1, unsigned __int16 a2)
{
  if ( a1 && (unsigned int)a2 < *(_DWORD *)(a1 + 8) && *(_BYTE *)(*(_QWORD *)a1 + 24LL * a2) )
    return *(_QWORD *)(*(_QWORD *)a1 + 24LL * a2 + 8);
  else
    return 0;
}

```

## disassembly

```asm
0x140015e28  test    rcx, rcx
0x140015e2b  jz      short loc_140015E4C
0x140015e2d  movzx   eax, dx
0x140015e30  cmp     eax, [rcx+8]
0x140015e33  jnb     short loc_140015E4C
0x140015e35  movzx   eax, dx
0x140015e38  mov     rdx, [rcx]
0x140015e3b  lea     rax, [rax+rax*2]
0x140015e3f  cmp     byte ptr [rdx+rax*8], 0
0x140015e43  jz      short loc_140015E4C
0x140015e45  mov     rax, [rdx+rax*8+8]
0x140015e4a  retn
0x140015e4c  xor     eax, eax
0x140015e4e  retn
```
