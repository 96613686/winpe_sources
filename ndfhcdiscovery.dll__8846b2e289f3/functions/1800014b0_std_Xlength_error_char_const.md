# std::_Xlength_error(char const *)

- ea: `0x1800014b0`
- end: `0x1800014d3`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800036b4`
- `0x180003fb0`
- `0x180004234`
- `0x18000bf6c`
- `0x18001120c`

## callees

- `0x1800013b0`
- `0x180001f9c`

## pseudocode

```c
void __fastcall __noreturn std::_Xlength_error(const char *a1)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::length_error::length_error((std::length_error *)pExceptionObject, a1);
  throw (std::length_error *)pExceptionObject;
}

```

## disassembly

```asm
0x1800014b0  sub     rsp, 48h
0x1800014b4  mov     rdx, rcx; char *
0x1800014b7  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800014bc  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x1800014c1  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x1800014c8  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800014cd  call    _CxxThrowException_0
```
