# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001674`
- end: `0x180001693`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `LPVOID __fastcall(SIZE_T, const struct std::nothrow_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c74`
- `0x180005f5c`

## callees

- `0x180001674`
- `0x18000a6ec`

## pseudocode

```c
LPVOID __fastcall operator new(SIZE_T a1, const struct std::nothrow_t *a2)
{
  LPVOID result; // rax

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
0x180001674  sub     rsp, 38h
0x180001678  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001681  call    ??2@YAPEAX_K@Z
0x180001686  nop
0x180001687  jmp     short loc_18000168E
0x180001689  mov     rax, [rsp+38h+arg_10]
0x18000168e  add     rsp, 38h
0x180001692  retn
```
