# pcmWriteSample_M08

- ea: `0x1800124b0`
- end: `0x1800124c1`
- name: `pcmWriteSample_M08`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x1800124b0`

## pseudocode

```c
_BYTE *__fastcall pcmWriteSample_M08(_BYTE *a1, unsigned __int64 a2, char a3)
{
  if ( a2 <= (unsigned __int64)a1 )
    return (_BYTE *)a2;
  *a1 = a3;
  return a1 + 1;
}

```

## disassembly

```asm
0x1800124b0  cmp     rdx, rcx
0x1800124b3  jbe     short loc_1800124BD
0x1800124b5  mov     [rcx], r8b
0x1800124b8  lea     rax, [rcx+1]
0x1800124bc  retn
0x1800124bd  mov     rax, rdx
0x1800124c0  retn
```
