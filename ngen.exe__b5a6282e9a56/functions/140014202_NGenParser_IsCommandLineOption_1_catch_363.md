# _NGenParser::IsCommandLineOption_::_1_::catch$363

- ea: `0x140014202`
- end: `0x14001422a`
- name: `_NGenParser::IsCommandLineOption_::_1_::catch$363`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001610`
- `0x140013efe`

## pseudocode

```c
void __fastcall __noreturn NGenParser::IsCommandLineOption_::_1_::catch_363(__int64 a1, _QWORD *a2)
{
  Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)(a2 + 9));
  a2[10] = a2[15];
  throw;
}

```

## disassembly

```asm
0x140014202  mov     [rsp+arg_8], rdx
0x140014207  push    rbp
0x140014208  sub     rsp, 30h
0x14001420c  mov     rbp, rdx
0x14001420f  lea     rcx, [rbp+48h]; this
0x140014213  call    ?SetCaughtCxx@HandlerState@Exception@@QEAAXXZ; Exception::HandlerState::SetCaughtCxx(void)
0x140014218  mov     rax, [rbp+78h]
0x14001421c  mov     [rbp+50h], rax
0x140014220  xor     edx, edx; pThrowInfo
0x140014222  xor     ecx, ecx; pExceptionObject
0x140014224  call    _CxxThrowException_0
```
