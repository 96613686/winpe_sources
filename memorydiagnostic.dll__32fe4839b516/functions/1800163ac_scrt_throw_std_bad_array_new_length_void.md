# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x1800163ac`
- end: `0x1800163cc`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800026d4`
- `0x180005c00`
- `0x180005fdc`
- `0x180006f8c`
- `0x1800210d0`

## callees

- `0x180003380`
- `0x180007430`

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
0x1800163ac  sub     rsp, 48h
0x1800163b0  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800163b5  call    ??0bad_array_new_length@std@@QEAA@XZ
0x1800163ba  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x1800163c1  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800163c6  call    _CxxThrowException_0
```
