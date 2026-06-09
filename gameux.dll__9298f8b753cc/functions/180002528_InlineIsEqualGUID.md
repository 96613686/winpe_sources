# InlineIsEqualGUID

- ea: `0x180002528`
- end: `0x18000254f`
- name: `InlineIsEqualGUID`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e28`
- `0x180002db8`

## callees

- `0x180002528`

## pseudocode

```c
_BOOL8 __fastcall InlineIsEqualGUID(_DWORD *a1, _DWORD *a2)
{
  return *a1 == *a2 && a1[1] == a2[1] && a1[2] == a2[2] && a1[3] == a2[3];
}

```

## disassembly

```asm
0x180002528  mov     eax, [rdx]
0x18000252a  cmp     [rcx], eax
0x18000252c  jnz     short loc_18000254C
0x18000252e  mov     eax, [rdx+4]
0x180002531  cmp     [rcx+4], eax
0x180002534  jnz     short loc_18000254C
0x180002536  mov     eax, [rdx+8]
0x180002539  cmp     [rcx+8], eax
0x18000253c  jnz     short loc_18000254C
0x18000253e  mov     eax, [rdx+0Ch]
0x180002541  cmp     [rcx+0Ch], eax
0x180002544  jnz     short loc_18000254C
0x180002546  mov     eax, 1
0x18000254b  retn
0x18000254c  xor     eax, eax
0x18000254e  retn
```
