# std::_Xlength_error(char const *)

- ea: `0x180001588`
- end: `0x1800015ab`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800129c4`
- `0x1800131f4`
- `0x180016ff4`
- `0x180018540`
- `0x18001884c`
- `0x18001b428`
- `0x18001be10`

## callees

- `0x180001504`
- `0x1800020bd`

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
0x180001588  sub     rsp, 48h
0x18000158c  mov     rdx, rcx; char *
0x18000158f  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001594  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180001599  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x1800015a0  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800015a5  call    _CxxThrowException_0
```
