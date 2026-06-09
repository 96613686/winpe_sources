# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001548`
- end: `0x180001567`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001af0`
- `0x180001bc8`
- `0x180001c84`

## callees

- `0x180001548`
- `0x180001a9c`

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
0x180001548  sub     rsp, 38h
0x18000154c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001555  call    ??2@YAPEAX_K@Z
0x18000155a  nop
0x18000155b  jmp     short loc_180001562
0x18000155d  mov     rax, [rsp+38h+arg_10]
0x180001562  add     rsp, 38h
0x180001566  retn
```
