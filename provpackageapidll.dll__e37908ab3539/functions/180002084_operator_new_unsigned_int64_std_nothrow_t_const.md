# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180002084`
- end: `0x1800020a0`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180005b70`
- `0x180005c30`
- `0x180005cc0`
- `0x180005e10`
- `0x180006790`
- `0x180006dd0`
- `0x180006f10`
- `0x18000d350`
- `0x18001176c`
- `0x180015530`
- `0x1800157d0`

## callees

- `0x180002084`
- `0x180002110`

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
0x180002084  sub     rsp, 38h
0x180002088  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002091  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002096  jmp     short loc_18000209A
0x180002098  xor     eax, eax
0x18000209a  add     rsp, 38h
0x18000209e  retn
```
