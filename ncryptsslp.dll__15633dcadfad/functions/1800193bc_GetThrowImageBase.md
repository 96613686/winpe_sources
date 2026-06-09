# _GetThrowImageBase

- ea: `0x1800193bc`
- end: `0x1800193ce`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180019794`
- `0x180019964`
- `0x180019b08`
- `0x18001a204`
- `0x18001a31c`
- `0x18001ab28`

## callees

- `0x1800194ec`

## pseudocode

```c
__int64 GetThrowImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 104);
}

```

## disassembly

```asm
0x1800193bc  sub     rsp, 28h
0x1800193c0  call    __vcrt_getptd
0x1800193c5  mov     rax, [rax+68h]
0x1800193c9  add     rsp, 28h
0x1800193cd  retn
```
