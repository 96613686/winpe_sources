# std::_Xout_of_range(char const *)

- ea: `0x180002154`
- end: `0x180002177`
- name: `?_Xout_of_range@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002180`
- `0x18000915c`

## callees

- `0x180001e78`
- `0x1800027ec`

## pseudocode

```c
void __fastcall __noreturn std::_Xout_of_range(const char *a1)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::length_error::length_error((std::length_error *)pExceptionObject, a1);
  throw (std::out_of_range *)pExceptionObject;
}

```

## disassembly

```asm
0x180002154  sub     rsp, 48h
0x180002158  mov     rdx, rcx; char *
0x18000215b  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002160  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180002165  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x18000216c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002171  call    _CxxThrowException_0
```
