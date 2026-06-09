# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x1800156a0`
- end: `0x1800156c0`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e74`
- `0x180005e78`
- `0x180006210`
- `0x180006eec`
- `0x18001fa10`

## callees

- `0x180003964`
- `0x1800073bc`

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
0x1800156a0  sub     rsp, 48h
0x1800156a4  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800156a9  call    ??0bad_array_new_length@std@@QEAA@XZ
0x1800156ae  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x1800156b5  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800156ba  call    _CxxThrowException_0
```
