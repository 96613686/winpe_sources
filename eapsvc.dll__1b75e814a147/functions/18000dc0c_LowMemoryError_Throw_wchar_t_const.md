# LowMemoryError::Throw(wchar_t const *)

- ea: `0x18000dc0c`
- end: `0x18000dc4c`
- name: `?Throw@LowMemoryError@@SAXPEB_W@Z`
- size: `64`
- prototype: `void __fastcall __noreturn(const wchar_t *)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x18000aafc`
- `0x18000c7b8`
- `0x18000d3b8`
- `0x18000dc54`
- `0x18000de8c`
- `0x18000e4ac`
- `0x18001140c`
- `0x180015590`

## callees

- `0x18000d920`
- `0x18000d960`
- `0x18000dcb0`
- `0x180014e74`

## pseudocode

```c
void __fastcall __noreturn LowMemoryError::Throw(const wchar_t *a1)
{
  _BYTE v1[48]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+50h] [rbp-38h] BYREF

  LowMemoryError::LowMemoryError((LowMemoryError *)v1, a1);
  anonymous_namespace_::Trace(v1);
  LowMemoryError::LowMemoryError((LowMemoryError *)pExceptionObject, (const struct LowMemoryError *)v1);
  throw (LowMemoryError *)pExceptionObject;
}

```

## disassembly

```asm
0x18000dc0c  sub     rsp, 88h
0x18000dc13  mov     rdx, rcx; wchar_t *
0x18000dc16  lea     rcx, [rsp+88h+var_68]; this
0x18000dc1b  call    ??0LowMemoryError@@AEAA@PEB_W@Z; LowMemoryError::LowMemoryError(wchar_t const *)
0x18000dc20  nop
0x18000dc21  lea     rcx, [rsp+88h+var_68]
0x18000dc26  call    _anonymous_namespace___Trace
0x18000dc2b  lea     rdx, [rsp+88h+var_68]; struct LowMemoryError *
0x18000dc30  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18000dc35  call    ??0LowMemoryError@@QEAA@AEBV0@@Z; LowMemoryError::LowMemoryError(LowMemoryError const &)
0x18000dc3a  lea     rdx, _TI5?AVLowMemoryError@@; pThrowInfo
0x18000dc41  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000dc46  call    _CxxThrowException_0
```
