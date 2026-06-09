# _SmartPtr_CWorkerThread_::operator__::_1_::catch$1

- ea: `0x18001204f`
- end: `0x18001206f`
- name: `_SmartPtr_CWorkerThread_::operator__::_1_::catch$1`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d258`
- `0x18000ef8c`

## pseudocode

```c
void __fastcall __noreturn SmartPtr_CWorkerThread_::operator__::_1_::catch_1(__int64 a1, __int64 a2)
{
  CWorkerThread::`scalar deleting destructor'(*(CWorkerThread **)(a2 + 56));
  throw;
}

```

## disassembly

```asm
0x18001204f  mov     [rsp+arg_8], rdx
0x180012054  push    rbp
0x180012055  sub     rsp, 20h
0x180012059  mov     rbp, rdx
0x18001205c  mov     rcx, [rbp+38h]; this
0x180012060  call    ??_GCWorkerThread@@QEAAPEAXI@Z; CWorkerThread::`scalar deleting destructor'(uint)
0x180012065  xor     edx, edx; pThrowInfo
0x180012067  xor     ecx, ecx; pExceptionObject
0x180012069  call    _CxxThrowException_0
```
