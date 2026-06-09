# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x180009624`
- end: `0x180009644`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002110`
- `0x180010154`
- `0x180010294`
- `0x1800180ac`

## callees

- `0x1800021de`
- `0x18000627c`

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
0x180009624  sub     rsp, 48h
0x180009628  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000962d  call    ??0bad_array_new_length@std@@QEAA@XZ
0x180009632  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180009639  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000963e  call    _CxxThrowException_0
```
