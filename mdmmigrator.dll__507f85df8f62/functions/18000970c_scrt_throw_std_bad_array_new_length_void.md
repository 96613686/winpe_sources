# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000970c`
- end: `0x18000972c`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800034ac`
- `0x180007ac0`
- `0x18000a2a4`
- `0x18000cf04`
- `0x18000d6b8`
- `0x1800110d0`

## callees

- `0x1800035fe`
- `0x1800080fc`

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
0x18000970c  sub     rsp, 48h
0x180009710  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180009715  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000971a  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180009721  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180009726  call    _CxxThrowException_0
```
