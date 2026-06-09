# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000eb80`
- end: `0x18000eba0`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180002cdc`
- `0x18000d844`
- `0x18000d984`
- `0x18000f210`
- `0x18000f750`
- `0x180011950`
- `0x1800130f4`

## callees

- `0x180002e62`
- `0x18000dbf0`

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
0x18000eb80  sub     rsp, 48h
0x18000eb84  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000eb89  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000eb8e  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000eb95  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000eb9a  call    _CxxThrowException_0
```
