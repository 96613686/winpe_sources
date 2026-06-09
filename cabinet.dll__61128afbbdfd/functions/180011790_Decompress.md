# Decompress

- ea: `0x180011790`
- end: `0x1800117ba`
- name: `Decompress`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800117c0`

## pseudocode

```c
__int64 __fastcall Decompress(
        __int64 a1,
        __m128i *a2,
        unsigned __int64 a3,
        char *a4,
        unsigned __int64 a5,
        unsigned __int64 *a6)
{
  return CompressOrDecompress(a1, a2, a3, a4, a5, a6, 0);
}

```

## disassembly

```asm
0x180011790  sub     rsp, 48h
0x180011794  mov     rax, [rsp+48h+arg_28]
0x180011799  mov     [rsp+48h+var_18], 0
0x1800117a1  mov     [rsp+48h+var_20], rax
0x1800117a6  mov     rax, [rsp+48h+arg_20]
0x1800117ab  mov     [rsp+48h+var_28], rax
0x1800117b0  call    CompressOrDecompress
0x1800117b5  add     rsp, 48h
0x1800117b9  retn
```
