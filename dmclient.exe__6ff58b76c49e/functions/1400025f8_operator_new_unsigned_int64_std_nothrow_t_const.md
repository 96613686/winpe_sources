# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1400025f8`
- end: `0x140002617`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003198`
- `0x140003e98`
- `0x140004110`
- `0x140017d90`

## callees

- `0x140002060`
- `0x1400025f8`

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
0x1400025f8  sub     rsp, 38h
0x1400025fc  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140002605  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000260a  nop
0x14000260b  jmp     short loc_140002612
0x14000260d  mov     rax, [rsp+38h+arg_10]
0x140002612  add     rsp, 38h
0x140002616  retn
```
