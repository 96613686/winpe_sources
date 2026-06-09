# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x18000d0a8`
- end: `0x18000d0c7`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a360`
- `0x18000aa08`
- `0x18000c7b0`
- `0x18000d0dc`

## callees

- `0x18000cadc`
- `0x18000d0a8`

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
0x18000d0a8  sub     rsp, 38h
0x18000d0ac  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000d0b5  call    ??2@YAPEAX_K@Z
0x18000d0ba  nop
0x18000d0bb  jmp     short loc_18000D0C2
0x18000d0bd  mov     rax, [rsp+38h+arg_10]
0x18000d0c2  add     rsp, 38h
0x18000d0c6  retn
```
