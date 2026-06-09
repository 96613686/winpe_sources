# std::_Xbad_alloc(void)

- ea: `0x180001348`
- end: `0x180001368`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001140`
- `0x1800024b0`
- `0x1800088d4`
- `0x18000a9fa`
- `0x18000ae6c`

## callees

- `0x180001200`
- `0x180001ce3`

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
0x180001348  sub     rsp, 48h
0x18000134c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001351  call    ??0bad_alloc@std@@QEAA@XZ
0x180001356  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000135d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001362  call    _CxxThrowException_0
```
