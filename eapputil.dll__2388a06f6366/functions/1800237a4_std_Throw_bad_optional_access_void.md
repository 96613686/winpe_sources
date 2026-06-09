# std::_Throw_bad_optional_access(void)

- ea: `0x1800237a4`
- end: `0x1800237d3`
- name: `?_Throw_bad_optional_access@std@@YAXXZ`
- size: `47`
- prototype: `void __noreturn(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001cd90`
- `0x18001eda4`

## callees

- `0x18000395a`
- `0x180016f18`

## pseudocode

```c
void __noreturn std::_Throw_bad_optional_access(void)
{
  __int128 pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  __int64 v1; // [rsp+30h] [rbp-18h]

  pExceptionObject = 0;
  v1 = 0;
  std::bad_optional_access::bad_optional_access((std::bad_optional_access *)&pExceptionObject);
  throw (std::bad_optional_access *)&pExceptionObject;
}

```

## disassembly

```asm
0x1800237a4  sub     rsp, 48h
0x1800237a8  xorps   xmm0, xmm0
0x1800237ab  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800237b0  xor     eax, eax
0x1800237b2  movups  [rsp+48h+pExceptionObject], xmm0
0x1800237b7  mov     [rsp+48h+var_18], rax
0x1800237bc  call    ??0bad_optional_access@std@@QEAA@XZ; std::bad_optional_access::bad_optional_access(void)
0x1800237c1  lea     rdx, _TI2?AVbad_optional_access@std@@; pThrowInfo
0x1800237c8  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800237cd  call    _CxxThrowException_0
```
