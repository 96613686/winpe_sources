# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x140001d20`
- end: `0x140001d3c`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140005bd0`
- `0x140006424`
- `0x140006c30`
- `0x1400082d0`
- `0x140008590`
- `0x140009ee0`
- `0x14000b144`

## callees

- `0x140001c74`
- `0x140001d20`

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
0x140001d20  sub     rsp, 38h
0x140001d24  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140001d2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001d32  jmp     short loc_140001D36
0x140001d34  xor     eax, eax
0x140001d36  add     rsp, 38h
0x140001d3a  retn
```
