# std::_Xbad_alloc(void)

- ea: `0x1800020e8`
- end: `0x180002108`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001da8`
- `0x180001f88`
- `0x180008e9c`
- `0x180008edc`
- `0x180009d27`

## callees

- `0x180001e08`
- `0x1800027ec`

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
0x1800020e8  sub     rsp, 48h
0x1800020ec  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800020f1  call    ??0bad_alloc@std@@QEAA@XZ
0x1800020f6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800020fd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002102  call    _CxxThrowException_0
```
