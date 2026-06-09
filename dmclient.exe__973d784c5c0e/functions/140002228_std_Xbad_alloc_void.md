# std::_Xbad_alloc(void)

- ea: `0x140002228`
- end: `0x140002248`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140002084`
- `0x14000be28`
- `0x14000be68`
- `0x14000ff24`
- `0x14000ff70`
- `0x1400199ac`
- `0x140019a9d`

## callees

- `0x1400020e4`
- `0x1400027bc`

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
0x140002228  sub     rsp, 48h
0x14000222c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140002231  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140002236  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000223d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140002242  call    _CxxThrowException_0
```
