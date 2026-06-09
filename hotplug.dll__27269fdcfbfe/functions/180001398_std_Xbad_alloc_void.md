# std::_Xbad_alloc(void)

- ea: `0x180001398`
- end: `0x1800013b8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001064`
- `0x180001238`
- `0x180008810`

## callees

- `0x1800010c4`
- `0x1800021dc`

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
0x180001398  sub     rsp, 48h
0x18000139c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800013a1  call    ??0bad_alloc@std@@QEAA@XZ
0x1800013a6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800013ad  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800013b2  call    _CxxThrowException_0
```
