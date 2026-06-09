# InlineIsEqualGUID

- ea: `0x180001fa0`
- end: `0x180001fc7`
- name: `InlineIsEqualGUID`
- size: `39`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d40`
- `0x180002020`
- `0x180003ff0`

## callees

- `0x180001fa0`

## pseudocode

```c
_BOOL8 __fastcall InlineIsEqualGUID(_DWORD *a1, _DWORD *a2)
{
  return *a1 == *a2 && a1[1] == a2[1] && a1[2] == a2[2] && a1[3] == a2[3];
}

```

## disassembly

```asm
0x180001fa0  mov     eax, [rdx]
0x180001fa2  cmp     [rcx], eax
0x180001fa4  jz      short loc_180001FA9
0x180001fa6  xor     eax, eax
0x180001fa8  retn
0x180001fa9  mov     eax, [rdx+4]
0x180001fac  cmp     [rcx+4], eax
0x180001faf  jnz     short loc_180001FA6
0x180001fb1  mov     eax, [rdx+8]
0x180001fb4  cmp     [rcx+8], eax
0x180001fb7  jnz     short loc_180001FA6
0x180001fb9  mov     eax, [rdx+0Ch]
0x180001fbc  cmp     [rcx+0Ch], eax
0x180001fbf  jnz     short loc_180001FA6
0x180001fc1  mov     eax, 1
0x180001fc6  retn
```
