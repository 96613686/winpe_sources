# DllInitialize

- ea: `0x1800ed3a0`
- end: `0x1800ed3b4`
- name: `DllInitialize`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800f37f0`
- `0x18010a078`

## pseudocode

```c
__int64 DllInitialize()
{
  sub_1800F37F0();
  return sub_18010A078();
}

```

## disassembly

```asm
0x1800ed3a0  sub     rsp, 28h
0x1800ed3a4  call    sub_1800F37F0
0x1800ed3a9  call    sub_18010A078
0x1800ed3ae  add     rsp, 28h
0x1800ed3b2  retn
```
