# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x18000187c`
- end: `0x18000189b`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018a4`
- `0x18000a7e0`
- `0x18000aec0`
- `0x18000be70`
- `0x18000d500`

## callees

- `0x18000187c`
- `0x180001cec`

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
0x18000187c  sub     rsp, 38h
0x180001880  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001889  call    ??2@YAPEAX_K@Z
0x18000188e  nop
0x18000188f  jmp     short loc_180001896
0x180001891  mov     rax, [rsp+38h+arg_10]
0x180001896  add     rsp, 38h
0x18000189a  retn
```
