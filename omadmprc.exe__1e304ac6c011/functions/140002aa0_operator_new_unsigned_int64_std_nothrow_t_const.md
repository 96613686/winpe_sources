# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x140002aa0`
- end: `0x140002abf`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000dc4c`
- `0x14000e934`
- `0x1400107ec`
- `0x1400128d4`
- `0x140013350`

## callees

- `0x140001c34`
- `0x140002aa0`

## pseudocode

```c
void *__fastcall operator new(size_t a1, const struct std::nothrow_t *a2)
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
0x140002aa0  sub     rsp, 38h
0x140002aa4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140002aad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002ab2  nop
0x140002ab3  jmp     short loc_140002ABA
0x140002ab5  mov     rax, [rsp+38h+arg_10]
0x140002aba  add     rsp, 38h
0x140002abe  retn
```
