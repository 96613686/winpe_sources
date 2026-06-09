# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x180006764`
- end: `0x180006784`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180001570`
- `0x180002ddc`
- `0x180003030`
- `0x180007b64`
- `0x18000ab80`
- `0x18000acb0`
- `0x18000adf0`
- `0x18000c7a4`
- `0x18000da00`

## callees

- `0x180001fe2`
- `0x180003478`

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
0x180006764  sub     rsp, 48h
0x180006768  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000676d  call    ??0bad_array_new_length@std@@QEAA@XZ
0x180006772  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180006779  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000677e  call    _CxxThrowException_0
```
