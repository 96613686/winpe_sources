# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x1400103f0`
- end: `0x140010410`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400022c4`
- `0x1400048b8`
- `0x1400049f8`
- `0x140004b84`
- `0x1400050cc`
- `0x140010660`

## callees

- `0x140002d58`
- `0x140005dec`

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
0x1400103f0  sub     rsp, 48h
0x1400103f4  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1400103f9  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x1400103fe  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x140010405  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14001040a  call    _CxxThrowException_0
```
