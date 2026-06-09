# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x180006ca8`
- end: `0x180006cc8`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000192c`
- `0x180005ad8`
- `0x180005d20`
- `0x180005e18`
- `0x180005f34`
- `0x180006f44`
- `0x180008a90`

## callees

- `0x180001faa`
- `0x180006238`

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
0x180006ca8  sub     rsp, 48h
0x180006cac  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180006cb1  call    ??0bad_array_new_length@std@@QEAA@XZ
0x180006cb6  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180006cbd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180006cc2  call    _CxxThrowException_0
```
