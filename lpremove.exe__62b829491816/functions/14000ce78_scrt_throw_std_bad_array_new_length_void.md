# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x14000ce78`
- end: `0x14000ce98`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1400021c0`
- `0x14000422c`
- `0x140004390`
- `0x14000e3b8`
- `0x14000f8d0`

## callees

- `0x140002c38`
- `0x140004d2c`

## pseudocode

```c
void __noreturn __scrt_throw_std_bad_array_new_length(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::bad_array_new_length::bad_array_new_length((std::bad_array_new_length *)pExceptionObject);
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x14000ce78  sub     rsp, 48h
0x14000ce7c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000ce81  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x14000ce86  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x14000ce8d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000ce92  call    _CxxThrowException_0
```
