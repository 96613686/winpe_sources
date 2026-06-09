# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x140002618`
- end: `0x140002637`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400031d8`
- `0x140003f18`
- `0x140004198`
- `0x140016c84`

## callees

- `0x140002084`
- `0x140002618`

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
0x140002618  sub     rsp, 38h
0x14000261c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140002625  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000262a  nop
0x14000262b  jmp     short loc_140002632
0x14000262d  mov     rax, [rsp+38h+arg_10]
0x140002632  add     rsp, 38h
0x140002636  retn
```
