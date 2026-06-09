# _tlgKeywordOn

- ea: `0x180001f3c`
- end: `0x180001f62`
- name: `_tlgKeywordOn`
- size: `38`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f838`
- `0x18000ffc0`
- `0x180010790`
- `0x180010d68`
- `0x180011308`
- `0x1800113c8`
- `0x1800114fc`
- `0x1800115e0`
- `0x180011810`
- `0x180011d2c`

## callees

- `0x180001f3c`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  bool result; // al

  result = 1;
  if ( a2 )
  {
    v3 = *(_QWORD *)(a1 + 24);
    if ( (*(_QWORD *)(a1 + 16) & a2) == 0 || (a2 & v3) != v3 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001f3c  mov     rax, rcx
0x180001f3f  test    rdx, rdx
0x180001f42  jz      short loc_180001F5C
0x180001f44  mov     rcx, [rcx+18h]
0x180001f48  mov     rax, [rax+10h]
0x180001f4c  test    rdx, rax
0x180001f4f  jz      short loc_180001F5F
0x180001f51  mov     rax, rcx
0x180001f54  and     rax, rdx
0x180001f57  cmp     rax, rcx
0x180001f5a  jnz     short loc_180001F5F
0x180001f5c  mov     al, 1
0x180001f5e  retn
0x180001f5f  xor     al, al
0x180001f61  retn
```
