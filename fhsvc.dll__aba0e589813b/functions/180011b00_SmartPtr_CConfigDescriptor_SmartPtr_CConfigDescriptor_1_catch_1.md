# _SmartPtr_CConfigDescriptor_::SmartPtr_CConfigDescriptor__::_1_::catch$1

- ea: `0x180011b00`
- end: `0x180011b17`
- name: `_SmartPtr_CConfigDescriptor_::SmartPtr_CConfigDescriptor__::_1_::catch$1`
- size: `23`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000d258`

## pseudocode

```c
void __noreturn SmartPtr_CConfigDescriptor_::SmartPtr_CConfigDescriptor__::_1_::catch_1()
{
  throw;
}

```

## disassembly

```asm
0x180011b00  mov     [rsp+arg_8], rdx
0x180011b05  push    rbp
0x180011b06  sub     rsp, 20h
0x180011b0a  mov     rbp, rdx
0x180011b0d  xor     edx, edx; pThrowInfo
0x180011b0f  xor     ecx, ecx; pExceptionObject
0x180011b11  call    _CxxThrowException_0
```
