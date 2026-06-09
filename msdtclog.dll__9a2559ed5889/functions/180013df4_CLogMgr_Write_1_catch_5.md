# _CLogMgr::_Write_::_1_::catch$5

- ea: `0x180013df4`
- end: `0x180013e2e`
- name: `_CLogMgr::_Write_::_1_::catch$5`
- size: `58`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009d84`
- `0x18001266c`

## pseudocode

```c
void __fastcall __noreturn CLogMgr::_Write_::_1_::catch_5(__int64 a1, __int64 a2)
{
  CLogState::_RestoreLogState(*(CLogState **)(*(_QWORD *)(a2 + 192) + 400LL));
  *(_DWORD *)(a2 + 80) = *(_DWORD *)(a2 + 128);
  throw (long *)(a2 + 80);
}

```

## disassembly

```asm
0x180013df4  mov     [rsp+arg_8], rdx
0x180013df9  push    rbp
0x180013dfa  sub     rsp, 50h
0x180013dfe  mov     rbp, rdx
0x180013e01  mov     rcx, [rbp+0C0h]
0x180013e08  mov     rcx, [rcx+190h]; this
0x180013e0f  call    ?_RestoreLogState@CLogState@@AEAAXXZ; CLogState::_RestoreLogState(void)
0x180013e14  mov     ecx, [rbp+80h]
0x180013e1a  mov     [rbp+50h], ecx
0x180013e1d  lea     rdx, _TI1J; pThrowInfo
0x180013e24  lea     rcx, [rbp+50h]; pExceptionObject
0x180013e28  call    _CxxThrowException_0
```
