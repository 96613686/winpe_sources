# std::_Xbad_alloc(void)

- ea: `0x180001488`
- end: `0x1800014a8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012e0`
- `0x18000354c`
- `0x180009fcc`
- `0x18000a00c`
- `0x18000a04c`
- `0x18000a098`
- `0x18000a0e4`
- `0x18000c5d0`
- `0x180010984`
- `0x1800109c4`
- `0x180010a8c`
- `0x180010b18`
- `0x180010c18`
- `0x180010d18`
- `0x180010e0c`
- `0x180010eac`
- `0x180013af1`
- `0x180013ed8`

## callees

- `0x180001340`
- `0x180001f9c`

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
0x180001488  sub     rsp, 48h
0x18000148c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001491  call    ??0bad_alloc@std@@QEAA@XZ
0x180001496  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000149d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800014a2  call    _CxxThrowException_0
```
