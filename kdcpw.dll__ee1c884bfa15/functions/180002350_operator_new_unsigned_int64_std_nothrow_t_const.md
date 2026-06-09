# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180002350`
- end: `0x18000236c`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a0fc`
- `0x18000c354`
- `0x18000c468`
- `0x18000c598`

## callees

- `0x180002074`
- `0x180002350`

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
0x180002350  sub     rsp, 38h
0x180002354  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000235d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002362  jmp     short loc_180002366
0x180002364  xor     eax, eax
0x180002366  add     rsp, 38h
0x18000236a  retn
```
