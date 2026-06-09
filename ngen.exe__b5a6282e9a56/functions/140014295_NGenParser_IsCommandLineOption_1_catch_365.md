# _NGenParser::IsCommandLineOption_::_1_::catch$365

- ea: `0x140014295`
- end: `0x1400142c0`
- name: `_NGenParser::IsCommandLineOption_::_1_::catch$365`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001610`
- `0x140013efe`

## pseudocode

```c
void __fastcall __noreturn NGenParser::IsCommandLineOption_::_1_::catch_365(__int64 a1, _QWORD *a2)
{
  Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)(a2 + 9));
  a2[10] = a2[16];
  throw;
}

```

## disassembly

```asm
0x140014295  mov     [rsp+arg_8], rdx
0x14001429a  push    rbp
0x14001429b  sub     rsp, 30h
0x14001429f  mov     rbp, rdx
0x1400142a2  lea     rcx, [rbp+48h]; this
0x1400142a6  call    ?SetCaughtCxx@HandlerState@Exception@@QEAAXXZ; Exception::HandlerState::SetCaughtCxx(void)
0x1400142ab  mov     rax, [rbp+80h]
0x1400142b2  mov     [rbp+50h], rax
0x1400142b6  xor     edx, edx; pThrowInfo
0x1400142b8  xor     ecx, ecx; pExceptionObject
0x1400142ba  call    _CxxThrowException_0
```
