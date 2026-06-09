# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x1800149b0`
- end: `0x1800149cc`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ff18`
- `0x180024c04`
- `0x180024ea8`
- `0x180025030`
- `0x1800251e8`
- `0x18002594c`

## callees

- `0x1800149b0`
- `0x180014a18`

## pseudocode

```c
void *__fastcall operator new[](unsigned __int64 a1, const struct std::nothrow_t *a2)
{
  void *result; // rax

  try
  {
    result = operator new[](a1);
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800149b0  sub     rsp, 38h
0x1800149b4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800149bd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800149c2  jmp     short loc_1800149C6
0x1800149c4  xor     eax, eax
0x1800149c6  add     rsp, 38h
0x1800149ca  retn
```
