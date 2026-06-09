# std::_Xbad_alloc(void)

- ea: `0x180001238`
- end: `0x180001258`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001098`
- `0x180004a18`
- `0x180005e70`
- `0x180009df3`
- `0x180009f4f`

## callees

- `0x1800010f8`
- `0x180001dfc`

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
