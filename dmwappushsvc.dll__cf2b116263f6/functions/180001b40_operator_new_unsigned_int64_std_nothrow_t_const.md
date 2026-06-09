# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001b40`
- end: `0x180001b5c`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001580`
- `0x180004ab4`
- `0x18000df4c`
- `0x18000f960`
- `0x18000faf0`

## callees

- `0x180001afc`
- `0x180001b40`

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
0x180001b40  sub     rsp, 38h
0x180001b44  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001b4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001b52  jmp     short loc_180001B56
0x180001b54  xor     eax, eax
0x180001b56  add     rsp, 38h
0x180001b5a  retn
```
