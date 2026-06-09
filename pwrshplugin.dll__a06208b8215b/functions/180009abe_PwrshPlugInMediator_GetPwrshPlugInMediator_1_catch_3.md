# _PwrshPlugInMediator::GetPwrshPlugInMediator_::_1_::catch$3

- ea: `0x180009abe`
- end: `0x180009af1`
- name: `_PwrshPlugInMediator::GetPwrshPlugInMediator_::_1_::catch$3`
- size: `51`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001dfc`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009ad2`
- `KERNEL32!LeaveCriticalSection` at `0x180009ad2`

## pseudocode

```c
void __fastcall __noreturn PwrshPlugInMediator::GetPwrshPlugInMediator_::_1_::catch_3(__int64 a1, __int64 a2)
{
  LeaveCriticalSection(&CriticalSection);
  *(_QWORD *)(a2 + 40) = *(_QWORD *)(a2 + 48);
  throw (PlugInException **)(a2 + 40);
}

```

## disassembly

```asm
0x180009abe  mov     [rsp+arg_8], rdx
0x180009ac3  push    rbp
0x180009ac4  sub     rsp, 20h
0x180009ac8  mov     rbp, rdx
0x180009acb  lea     rcx, CriticalSection; lpCriticalSection
0x180009ad2  call    cs:__imp_LeaveCriticalSection
0x180009ad8  mov     rax, [rbp+30h]
0x180009adc  mov     [rbp+28h], rax
0x180009ae0  lea     rdx, _TI2PEAVPlugInException@@; pThrowInfo
0x180009ae7  lea     rcx, [rbp+28h]; pExceptionObject
0x180009aeb  call    _CxxThrowException_0
```
