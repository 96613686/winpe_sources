# pcmWriteSample_S16

- ea: `0x1800011e0`
- end: `0x1800011fd`
- name: `pcmWriteSample_S16`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x1800011e0`

## pseudocode

```c
_DWORD *__fastcall pcmWriteSample_S16(_DWORD *a1, unsigned __int64 a2, int a3)
{
  if ( a2 <= (unsigned __int64)a1 || a2 - (unsigned __int64)a1 < 4 )
    return (_DWORD *)a2;
  *a1 = a3;
  return a1 + 1;
}

```

## disassembly

```asm
0x1800011e0  cmp     rdx, rcx
0x1800011e3  jbe     short loc_1800011F9
0x1800011e5  mov     rax, rdx
0x1800011e8  sub     rax, rcx
0x1800011eb  cmp     rax, 4
0x1800011ef  jb      short loc_1800011F9
0x1800011f1  mov     [rcx], r8d
0x1800011f4  lea     rax, [rcx+4]
0x1800011f8  retn
0x1800011f9  mov     rax, rdx
0x1800011fc  retn
```
