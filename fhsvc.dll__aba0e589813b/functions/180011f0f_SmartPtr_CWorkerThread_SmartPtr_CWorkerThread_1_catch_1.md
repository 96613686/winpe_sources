# _SmartPtr_CWorkerThread_::SmartPtr_CWorkerThread__::_1_::catch$1

- ea: `0x180011f0f`
- end: `0x180011f26`
- name: `_SmartPtr_CWorkerThread_::SmartPtr_CWorkerThread__::_1_::catch$1`
- size: `23`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d258`

## pseudocode

```c
void __noreturn SmartPtr_CWorkerThread_::SmartPtr_CWorkerThread__::_1_::catch_1()
{
  throw;
}

```

## disassembly

```asm
0x180011f0f  mov     [rsp+arg_8], rdx
0x180011f14  push    rbp
0x180011f15  sub     rsp, 20h
0x180011f19  mov     rbp, rdx
0x180011f1c  xor     edx, edx; pThrowInfo
0x180011f1e  xor     ecx, ecx; pExceptionObject
0x180011f20  call    _CxxThrowException_0
```
