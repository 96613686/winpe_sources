# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x1800101e4`
- end: `0x180010204`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037dc`
- `0x18000e2bc`
- `0x18001109c`
- `0x180012b00`
- `0x1800137f0`
- `0x180013c58`
- `0x1800141e4`
- `0x1800144b4`
- `0x180015464`
- `0x1800155e8`
- `0x180015750`
- `0x1800158bc`
- `0x180016b94`
- `0x180016d94`
- `0x18002137c`
- `0x1800214ac`
- `0x1800253d0`
- `0x1800256d0`
- `0x180025808`
- `0x180025cd0`
- `0x18002aa0c`
- `0x18002b7a0`
- `0x18002c08c`
- `0x18002d488`
- `0x18002ea60`

## callees

- `0x18000395a`
- `0x18000e650`

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
0x1800101e4  sub     rsp, 48h
0x1800101e8  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800101ed  call    ??0bad_array_new_length@std@@QEAA@XZ
0x1800101f2  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x1800101f9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800101fe  call    _CxxThrowException_0
```
