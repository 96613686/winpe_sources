# std::_Xbad_alloc(void)

- ea: `0x180001518`
- end: `0x180001538`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180001370`
- `0x180002bb8`
- `0x180002cb0`
- `0x180004f54`
- `0x180004f94`
- `0x180004fd4`
- `0x180005020`
- `0x18000c70c`
- `0x18000e0b8`
- `0x180012f73`
- `0x180012feb`

## callees

- `0x1800013d0`
- `0x180001f3c`

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
