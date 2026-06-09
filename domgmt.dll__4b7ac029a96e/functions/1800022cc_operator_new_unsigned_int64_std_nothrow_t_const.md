# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800022cc`
- end: `0x1800022e8`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180006dd8`
- `0x18000b260`
- `0x18000b33c`
- `0x18000be40`
- `0x18000c2d0`
- `0x18000d0d0`

## callees

- `0x180001fb8`
- `0x1800022cc`

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
0x1800022cc  sub     rsp, 38h
0x1800022d0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800022d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800022de  jmp     short loc_1800022E2
0x1800022e0  xor     eax, eax
0x1800022e2  add     rsp, 38h
0x1800022e6  retn
```
