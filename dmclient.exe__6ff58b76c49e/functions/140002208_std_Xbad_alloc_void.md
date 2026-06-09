# std::_Xbad_alloc(void)

- ea: `0x140002208`
- end: `0x140002228`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140002060`
- `0x14000ba8c`
- `0x14000bacc`
- `0x14000f964`
- `0x14000f9b0`
- `0x140018b7b`
- `0x140018c6c`

## callees

- `0x1400020c0`
- `0x14000279c`

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
0x140002208  sub     rsp, 48h
0x14000220c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140002211  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140002216  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000221d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140002222  call    _CxxThrowException_0
```
