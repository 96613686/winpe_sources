# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000a410`
- end: `0x18000a430`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800024c4`
- `0x1800040bc`
- `0x18000b0cc`
- `0x18000b258`
- `0x180010a34`

## callees

- `0x18000332c`
- `0x1800044a4`

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
0x18000a410  sub     rsp, 48h
0x18000a414  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000a419  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000a41e  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000a425  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000a42a  call    _CxxThrowException_0
```
