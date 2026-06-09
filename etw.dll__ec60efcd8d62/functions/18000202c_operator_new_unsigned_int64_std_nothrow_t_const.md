# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x18000202c`
- end: `0x180002048`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000485c`
- `0x1800049dc`
- `0x180005cc8`
- `0x180008f30`
- `0x18000d780`
- `0x180013084`

## callees

- `0x18000202c`
- `0x180002094`

## pseudocode

```c
void *__fastcall operator new[](unsigned __int64 a1, const struct std::nothrow_t *a2)
{
  void *result; // rax

  try
  {
    result = operator new[](a1);
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
0x18000202c  sub     rsp, 38h
0x180002030  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002039  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000203e  jmp     short loc_180002042
0x180002040  xor     eax, eax
0x180002042  add     rsp, 38h
0x180002046  retn
```
