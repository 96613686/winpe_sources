# std::_Xlength_error(char const *)

- ea: `0x180002128`
- end: `0x18000214b`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002110`
- `0x180004220`

## callees

- `0x180001e78`
- `0x1800027ec`

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
0x180002128  sub     rsp, 48h
0x18000212c  mov     rdx, rcx; char *
0x18000212f  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002134  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180002139  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x180002140  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002145  call    _CxxThrowException_0
```
