# std::_Xbad_alloc(void)

- ea: `0x180001238`
- end: `0x180001258`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180012814`
- `0x180014904`
- `0x180016634`
- `0x180016674`
- `0x180017050`
- `0x180018a25`
- `0x180018a9d`

## callees

- `0x180001e0e`
- `0x18000d5c0`

## pseudocode

```c
void __noreturn std::_Xbad_alloc(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
  throw (std::bad_alloc *)pExceptionObject;
}

```

## disassembly

```asm
0x180001238  sub     rsp, 48h
0x18000123c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001241  call    ??0bad_alloc@std@@QEAA@XZ
0x180001246  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000124d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001252  call    _CxxThrowException_0
```
