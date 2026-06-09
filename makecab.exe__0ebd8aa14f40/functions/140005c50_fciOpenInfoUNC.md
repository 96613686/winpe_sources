# fciOpenInfoUNC

- ea: `0x140005c50`
- end: `0x140005c7a`
- name: `fciOpenInfoUNC`
- size: `42`
- prototype: `__int64 __fastcall(int, int, int, int, int *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005b10`

## pseudocode

```c
__int64 __fastcall fciOpenInfoUNC(const CHAR *a1, _WORD *a2, _WORD *a3, _WORD *a4, int *err, __int64 *a6)
{
  return fciOpenInfoEx(a1, a2, a3, a4, err, a6, 1u);
}

```

## disassembly

```asm
0x140005c50  sub     rsp, 48h
0x140005c54  mov     rax, [rsp+48h+arg_28]
0x140005c59  mov     [rsp+48h+var_18], 1; int
0x140005c61  mov     [rsp+48h+var_20], rax; void *
0x140005c66  mov     rax, [rsp+48h+arg_20]
0x140005c6b  mov     [rsp+48h+err], rax; err
0x140005c70  call    fciOpenInfoEx
0x140005c75  add     rsp, 48h
0x140005c79  retn
```
