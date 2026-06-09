# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001ff0`
- end: `0x18000200c`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `27`
- callee_count: `2`
- tags: ``

## callers

- `0x18000293c`
- `0x180002a50`
- `0x180002c78`
- `0x180003fa8`
- `0x1800052b4`
- `0x1800061f4`
- `0x180006348`
- `0x180007500`
- `0x180008330`
- `0x1800099c0`
- `0x18000a300`
- `0x18000c4a0`
- `0x18000cca0`
- `0x18000de40`
- `0x18000ece4`
- `0x18000ef18`
- `0x18000f90c`
- `0x18000ff6c`
- `0x180010634`
- `0x180010d44`
- `0x180010db8`
- `0x180013084`
- `0x18001356c`
- `0x180013c30`
- `0x180013e28`
- `0x1800144f8`
- `0x1800148b8`

## callees

- `0x180001ff0`
- `0x180002050`

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
0x180001ff0  sub     rsp, 38h
0x180001ff4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001ffd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002002  jmp     short loc_180002006
0x180002004  xor     eax, eax
0x180002006  add     rsp, 38h
0x18000200a  retn
```
