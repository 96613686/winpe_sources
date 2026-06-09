# MupFindMatchingChar

- ea: `0x140001040`
- end: `0x140001069`
- name: `MupFindMatchingChar`
- size: `41`
- prototype: `_WORD *__fastcall(_WORD *, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140012fbc`
- `0x14001a128`
- `0x14001a920`
- `0x14001ca50`
- `0x14001cb10`

## callees

- `0x140001040`

## pseudocode

```c
_WORD *__fastcall MupFindMatchingChar(_WORD *a1, __int64 a2, __int64 a3)
{
  if ( a3 )
  {
    while ( a3 && *a1 )
    {
      if ( *a1 == 92 )
        return a1;
      --a3;
      ++a1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140001040  test    r8, r8
0x140001043  jz      short loc_140001061
0x140001045  test    r8, r8
0x140001048  jz      short loc_140001061
0x14000104a  movzx   eax, word ptr [rcx]
0x14000104d  test    ax, ax
0x140001050  jz      short loc_140001061
0x140001052  cmp     ax, 5Ch ; '\'
0x140001056  jz      short loc_140001065
0x140001058  dec     r8
0x14000105b  add     rcx, 2
0x14000105f  jmp     short loc_140001045
0x140001061  xor     eax, eax
0x140001063  retn
0x140001065  mov     rax, rcx
0x140001068  retn
```
