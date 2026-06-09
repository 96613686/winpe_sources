# ___DllXcptFilter

- ea: `0x1002e492`
- end: `0x1002e4b7`
- name: `___DllXcptFilter`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1002e384`

## callees

- `0x1002e1ef`
- `0x1002e492`
- `0x100344da`

## pseudocode

```c
int __cdecl __DllXcptFilter(int a1, int a2, int a3, int a4, int a5)
{
  if ( a2 == 1 )
    _CRT_INIT(a1, 0, a3);
  return __CppXcptFilter(a4, a5);
}

```

## disassembly

```asm
0x1002e492  push    ebp
0x1002e493  mov     ebp, esp
0x1002e495  cmp     [ebp+arg_4], 1
0x1002e499  jnz     short loc_1002E4A8
0x1002e49b  push    [ebp+arg_8]
0x1002e49e  push    0
0x1002e4a0  push    [ebp+arg_0]
0x1002e4a3  call    __CRT_INIT@12
0x1002e4a8  push    [ebp+arg_10]
0x1002e4ab  push    [ebp+arg_C]
0x1002e4ae  call    ___CppXcptFilter
0x1002e4b3  pop     ecx
0x1002e4b4  pop     ecx
0x1002e4b5  pop     ebp
0x1002e4b6  retn
```
