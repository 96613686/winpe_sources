# std::_Xlength_error(char const *)

- ea: `0x180001540`
- end: `0x180001563`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f48`
- `0x180003838`
- `0x180003abc`
- `0x18000c7b0`
- `0x18000dba0`

## callees

- `0x180001440`
- `0x180001f3c`

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
0x180001540  sub     rsp, 48h
0x180001544  mov     rdx, rcx; char *
0x180001547  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000154c  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180001551  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x180001558  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000155d  call    _CxxThrowException_0
```
