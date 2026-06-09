# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001ef4`
- end: `0x180001f13`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `23`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f28`
- `0x18000af40`
- `0x18000b2f0`
- `0x18000b390`
- `0x18000b470`
- `0x18000b520`
- `0x18000b5c0`
- `0x18000b660`
- `0x18000bee0`
- `0x18000ccdc`
- `0x18000ce20`
- `0x18000d230`
- `0x18000f3ec`
- `0x1800107a0`
- `0x180014030`
- `0x180015700`
- `0x1800165a4`
- `0x180016a30`
- `0x180018fc0`
- `0x180019260`
- `0x180019900`
- `0x18001b994`
- `0x18001bd38`

## callees

- `0x180001484`
- `0x180001ef4`

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
0x180001ef4  sub     rsp, 38h
0x180001ef8  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001f01  call    ??2@YAPEAX_K@Z
0x180001f06  nop
0x180001f07  jmp     short loc_180001F0E
0x180001f09  mov     rax, [rsp+38h+arg_10]
0x180001f0e  add     rsp, 38h
0x180001f12  retn
```
