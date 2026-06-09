# std::_Xbad_alloc(void)

- ea: `0x1400016b8`
- end: `0x1400016d8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001510`
- `0x140002f5c`
- `0x1400117c7`

## callees

- `0x140001570`
- `0x140001fcc`

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
0x1400016b8  sub     rsp, 48h
0x1400016bc  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1400016c1  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1400016c6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1400016cd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1400016d2  call    _CxxThrowException_0
```
