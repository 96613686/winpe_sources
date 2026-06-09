# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180006edc`
- end: `0x180006efb`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(SIZE_T, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180009e10`
- `0x18000a030`
- `0x18000a1c8`

## callees

- `0x180006edc`
- `0x180009c28`

## pseudocode

```c
void *__fastcall operator new(SIZE_T a1, const struct std::nothrow_t *a2)
{
  void *result; // rax

  try
  {
    result = operator new(a1);
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
0x180006edc  sub     rsp, 38h
0x180006ee0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180006ee9  call    ??2@YAPEAX_K@Z
0x180006eee  nop
0x180006eef  jmp     short loc_180006EF6
0x180006ef1  mov     rax, [rsp+38h+arg_10]
0x180006ef6  add     rsp, 38h
0x180006efa  retn
```
