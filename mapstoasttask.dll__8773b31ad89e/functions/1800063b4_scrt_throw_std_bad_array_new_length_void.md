# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x1800063b4`
- end: `0x1800063d4`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800015d4`
- `0x1800020a4`
- `0x1800021e4`
- `0x1800044a8`
- `0x1800064c0`

## callees

- `0x180001fee`
- `0x180002718`

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
0x1800063b4  sub     rsp, 48h
0x1800063b8  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800063bd  call    ??0bad_array_new_length@std@@QEAA@XZ
0x1800063c2  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x1800063c9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800063ce  call    _CxxThrowException_0
```
