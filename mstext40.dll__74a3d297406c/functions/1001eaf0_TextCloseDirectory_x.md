# TextCloseDirectory(x)

- ea: `0x1001eaf0`
- end: `0x1001eb03`
- name: `_TextCloseDirectory@4`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x10011310`
- `0x10011d90`

## callees

- `0x1000b200`
- `0x1001eaf0`

## pseudocode

```c
int __stdcall TextCloseDirectory(_DWORD *a1)
{
  if ( a1 )
    MemFree(a1);
  return 0;
}

```

## disassembly

```asm
0x1001eaf0  mov     eax, [esp+arg_0]
0x1001eaf4  test    eax, eax
0x1001eaf6  jz      short loc_1001EAFE
0x1001eaf8  push    eax
0x1001eaf9  call    _MemFree@4; MemFree(x)
0x1001eafe  xor     eax, eax
0x1001eb00  retn    4
```
