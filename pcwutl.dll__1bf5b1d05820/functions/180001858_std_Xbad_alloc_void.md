# std::_Xbad_alloc(void)

- ea: `0x180001858`
- end: `0x180001878`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001524`
- `0x1800016f8`
- `0x180019303`

## callees

- `0x180001584`
- `0x1800027bc`

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
0x180001858  sub     rsp, 48h
0x18000185c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001861  call    ??0bad_alloc@std@@QEAA@XZ
0x180001866  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000186d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001872  call    _CxxThrowException_0
```
