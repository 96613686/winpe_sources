# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x1800020ec`
- end: `0x180002108`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `34`
- callee_count: `2`
- tags: ``

## callers

- `0x180006014`
- `0x1800068b8`
- `0x1800078e8`
- `0x180007f78`
- `0x1800088dc`
- `0x18000907c`
- `0x180009740`
- `0x180009b30`
- `0x180009c30`
- `0x180009d40`
- `0x180009e40`
- `0x180009f40`
- `0x18000a040`
- `0x18000a1e0`
- `0x18000a2e0`
- `0x18000a3c0`
- `0x18000a5b0`
- `0x18000b7b0`
- `0x18000d0c4`
- `0x18000d350`
- `0x18000d708`
- `0x18000da5c`
- `0x18000e4b0`
- `0x18000e948`
- `0x180012444`
- `0x180014c70`
- `0x180014f8c`
- `0x180015930`
- `0x180016050`
- `0x180016710`
- `0x180016c50`
- `0x1800170d0`
- `0x180017608`
- `0x180017898`

## callees

- `0x1800020ec`
- `0x180002160`

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
0x1800020ec  sub     rsp, 38h
0x1800020f0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800020f9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800020fe  jmp     short loc_180002102
0x180002100  xor     eax, eax
0x180002102  add     rsp, 38h
0x180002106  retn
```
