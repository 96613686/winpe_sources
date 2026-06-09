# std::_Xbad_alloc(void)

- ea: `0x140001e38`
- end: `0x140001e58`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140001c34`
- `0x140009d10`
- `0x1400142a8`
- `0x140015bea`
- `0x140015fa6`

## callees

- `0x140001cf4`
- `0x1400023b8`

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
0x140001e38  sub     rsp, 48h
0x140001e3c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140001e41  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140001e46  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x140001e4d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140001e52  call    _CxxThrowException_0
```
