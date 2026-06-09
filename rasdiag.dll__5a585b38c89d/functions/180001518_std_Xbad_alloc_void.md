# std::_Xbad_alloc(void)

- ea: `0x180001518`
- end: `0x180001538`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011dc`
- `0x1800013b8`
- `0x18000e023`

## callees

- `0x18000123c`
- `0x18000265c`

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
0x180001518  sub     rsp, 48h
0x18000151c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001521  call    ??0bad_alloc@std@@QEAA@XZ
0x180001526  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000152d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001532  call    _CxxThrowException_0
```
