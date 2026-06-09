# _SmartPtr_CConfigDescriptor_::operator__::_1_::catch$1

- ea: `0x180012500`
- end: `0x180012520`
- name: `_SmartPtr_CConfigDescriptor_::operator__::_1_::catch$1`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000d258`
- `0x18000ef64`

## pseudocode

```c
void __fastcall __noreturn SmartPtr_CConfigDescriptor_::operator__::_1_::catch_1(__int64 a1, __int64 a2)
{
  CConfigDescriptor::`scalar deleting destructor'(*(CConfigDescriptor **)(a2 + 56));
  throw;
}

```

## disassembly

```asm
0x180012500  mov     [rsp+arg_8], rdx
0x180012505  push    rbp
0x180012506  sub     rsp, 20h
0x18001250a  mov     rbp, rdx
0x18001250d  mov     rcx, [rbp+38h]; this
0x180012511  call    ??_GCConfigDescriptor@@QEAAPEAXI@Z; CConfigDescriptor::`scalar deleting destructor'(uint)
0x180012516  xor     edx, edx; pThrowInfo
0x180012518  xor     ecx, ecx; pExceptionObject
0x18001251a  call    _CxxThrowException_0
```
