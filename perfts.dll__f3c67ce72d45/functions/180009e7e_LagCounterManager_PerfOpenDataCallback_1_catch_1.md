# _LagCounterManager::PerfOpenDataCallback_::_1_::catch$1

- ea: `0x180009e7e`
- end: `0x180009eae`
- name: `_LagCounterManager::PerfOpenDataCallback_::_1_::catch$1`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006c30`

## pseudocode

```c
__int64 __fastcall LagCounterManager::PerfOpenDataCallback_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(*(wil::details::in1diag3 **)(a2 + 1224), (void *)0x3FD, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x180009e7e  mov     [rsp+arg_8], rdx
0x180009e83  push    rbp
0x180009e84  sub     rsp, 30h
0x180009e88  mov     rbp, rdx
0x180009e8b  mov     rcx, [rbp+4C8h]; this
0x180009e92  mov     edx, 3FDh; void *
0x180009e97  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180009e9c  nop
0x180009e9d  mov     rax, 0
0x180009ea7  add     rsp, 30h
0x180009eab  pop     rbp
0x180009eac  retn
```
