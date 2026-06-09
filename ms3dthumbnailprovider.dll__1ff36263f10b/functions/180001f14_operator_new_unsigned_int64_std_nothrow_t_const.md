# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001f14`
- end: `0x180001f30`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800029cc`
- `0x180002e80`
- `0x180003620`

## callees

- `0x180001f14`
- `0x1800024c0`

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
0x180001f14  sub     rsp, 38h
0x180001f18  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001f21  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001f26  jmp     short loc_180001F2A
0x180001f28  xor     eax, eax
0x180001f2a  add     rsp, 38h
0x180001f2e  retn
```
