# std::bad_alloc::_Doraise(void)

- ea: `0x1400018e0`
- end: `0x140001903`
- name: `?_Doraise@bad_alloc@std@@MEBAXXZ`
- size: `35`
- prototype: `void __fastcall __noreturn(std::bad_alloc *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001844`
- `0x140001909`

## pseudocode

```c
void __fastcall __noreturn std::bad_alloc::_Doraise(std::bad_alloc *this)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, this);
  throw (std::bad_alloc *)pExceptionObject;
}

```

## disassembly

```asm
0x1400018e0  sub     rsp, 48h
0x1400018e4  mov     rdx, rcx; struct std::bad_alloc *
0x1400018e7  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1400018ec  call    ??0bad_alloc@std@@QEAA@AEBV01@@Z; std::bad_alloc::bad_alloc(std::bad_alloc const &)
0x1400018f1  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1400018f8  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1400018fd  call    _CxxThrowException_0
```
