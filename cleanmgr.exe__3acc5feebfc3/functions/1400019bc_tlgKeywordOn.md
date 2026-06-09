# _tlgKeywordOn

- ea: `0x1400019bc`
- end: `0x1400019e2`
- name: `_tlgKeywordOn`
- size: `38`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bae4`
- `0x14000e17c`
- `0x14000f214`
- `0x14000f314`
- `0x14000f788`
- `0x14000fc94`
- `0x14000fd68`
- `0x14000fe8c`
- `0x140010030`
- `0x140010e00`
- `0x140011030`
- `0x140011260`
- `0x140011490`
- `0x1400116c0`
- `0x1400118f0`
- `0x140011b20`
- `0x140012a7c`
- `0x140013530`
- `0x140014fe0`

## callees

- `0x1400019bc`

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
0x1400019bc  mov     rax, rcx
0x1400019bf  test    rdx, rdx
0x1400019c2  jz      short loc_1400019DC
0x1400019c4  mov     rcx, [rcx+18h]
0x1400019c8  mov     rax, [rax+10h]
0x1400019cc  test    rdx, rax
0x1400019cf  jz      short loc_1400019DF
0x1400019d1  mov     rax, rcx
0x1400019d4  and     rax, rdx
0x1400019d7  cmp     rax, rcx
0x1400019da  jnz     short loc_1400019DF
0x1400019dc  mov     al, 1
0x1400019de  retn
0x1400019df  xor     al, al
0x1400019e1  retn
```
