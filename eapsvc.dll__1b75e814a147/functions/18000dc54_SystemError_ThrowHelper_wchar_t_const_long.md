# SystemError::ThrowHelper(wchar_t const *,long)

- ea: `0x18000dc54`
- end: `0x18000dcaa`
- name: `?ThrowHelper@SystemError@@CAXPEB_WJ@Z`
- size: `86`
- prototype: `void __fastcall __noreturn(const wchar_t *, int)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a5ac`
- `0x18000d338`
- `0x18000d4a8`
- `0x18000d4c8`
- `0x18000eadc`

## callees

- `0x18000d9d0`
- `0x18000d9ec`
- `0x18000dc0c`
- `0x18000dc54`
- `0x18000dcb0`
- `0x180014e74`

## pseudocode

```c
void __fastcall __noreturn SystemError::ThrowHelper(const wchar_t *a1, int a2)
{
  _BYTE v2[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+38h] [rbp-20h] BYREF

  if ( a2 != -2147024882 && a2 != -2147024888 )
  {
    SystemError::SystemError((SystemError *)v2, a1, a2);
    anonymous_namespace_::Trace(v2);
    SystemError::SystemError((SystemError *)pExceptionObject, (const struct SystemError *)v2);
    throw (SystemError *)pExceptionObject;
  }
  LowMemoryError::Throw(a1);
}

```

## disassembly

```asm
0x18000dc54  sub     rsp, 58h
0x18000dc58  cmp     edx, 8007000Eh
0x18000dc5e  jz      short loc_18000DCA4
0x18000dc60  cmp     edx, 80070008h
0x18000dc66  jz      short loc_18000DCA4
0x18000dc68  mov     r8d, edx; int
0x18000dc6b  mov     rdx, rcx; wchar_t *
0x18000dc6e  lea     rcx, [rsp+58h+var_38]; this
0x18000dc73  call    ??0SystemError@@IEAA@PEB_WJ@Z; SystemError::SystemError(wchar_t const *,long)
0x18000dc78  nop
0x18000dc79  lea     rcx, [rsp+58h+var_38]
0x18000dc7e  call    _anonymous_namespace___Trace
0x18000dc83  lea     rdx, [rsp+58h+var_38]; struct SystemError *
0x18000dc88  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18000dc8d  call    ??0SystemError@@QEAA@AEBV0@@Z; SystemError::SystemError(SystemError const &)
0x18000dc92  lea     rdx, _TI2?AVSystemError@@; pThrowInfo
0x18000dc99  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000dc9e  call    _CxxThrowException_0
0x18000dca4  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
```
