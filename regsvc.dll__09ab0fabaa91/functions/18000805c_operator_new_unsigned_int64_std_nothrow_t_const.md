# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x18000805c`
- end: `0x180008078`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180002810`
- `0x180003090`
- `0x180003420`
- `0x180003b40`
- `0x180004bb0`
- `0x180005da0`
- `0x180005f20`
- `0x180012c34`
- `0x1800157d0`

## callees

- `0x18000805c`
- `0x1800080b0`

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
0x18000805c  sub     rsp, 38h
0x180008060  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180008069  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000806e  jmp     short loc_180008072
0x180008070  xor     eax, eax
0x180008072  add     rsp, 38h
0x180008076  retn
```
