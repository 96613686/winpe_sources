# std::_Xbad_alloc(void)

- ea: `0x180001588`
- end: `0x1800015a8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001250`
- `0x180001428`
- `0x18000eb94`
- `0x18000ebd4`
- `0x180011453`

## callees

- `0x1800012b0`
- `0x1800026cc`

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
0x180001588  sub     rsp, 48h
0x18000158c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001591  call    ??0bad_alloc@std@@QEAA@XZ
0x180001596  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000159d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800015a2  call    _CxxThrowException_0
```
