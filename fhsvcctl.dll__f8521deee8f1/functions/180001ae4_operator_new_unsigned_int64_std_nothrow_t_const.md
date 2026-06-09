# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001ae4`
- end: `0x180001b03`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001b0c`
- `0x180003230`

## callees

- `0x180001ae4`
- `0x180001f90`

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
0x180001ae4  sub     rsp, 38h
0x180001ae8  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001af1  call    ??2@YAPEAX_K@Z
0x180001af6  nop
0x180001af7  jmp     short loc_180001AFE
0x180001af9  mov     rax, [rsp+38h+arg_10]
0x180001afe  add     rsp, 38h
0x180001b02  retn
```
