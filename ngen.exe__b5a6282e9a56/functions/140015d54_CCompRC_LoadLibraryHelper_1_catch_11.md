# _CCompRC::LoadLibraryHelper_::_1_::catch$11

- ea: `0x140015d54`
- end: `0x140015d85`
- name: `_CCompRC::LoadLibraryHelper_::_1_::catch$11`
- size: `49`
- prototype: `void __fastcall __noreturn(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001610`
- `0x140013efe`

## pseudocode

```c
void __fastcall __noreturn CCompRC::LoadLibraryHelper_::_1_::catch_11(__int64 a1, _QWORD *a2)
{
  Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)(a2 + 19));
  a2[20] = a2[34];
  throw;
}

```

## disassembly

```asm
0x140015d54  mov     [rsp+arg_8], rdx
0x140015d59  push    rbp
0x140015d5a  sub     rsp, 50h
0x140015d5e  mov     rbp, rdx
0x140015d61  lea     rcx, [rbp+98h]; this
0x140015d68  call    ?SetCaughtCxx@HandlerState@Exception@@QEAAXXZ; Exception::HandlerState::SetCaughtCxx(void)
0x140015d6d  mov     rax, [rbp+110h]
0x140015d74  mov     [rbp+0A0h], rax
0x140015d7b  xor     edx, edx; pThrowInfo
0x140015d7d  xor     ecx, ecx; pExceptionObject
0x140015d7f  call    _CxxThrowException_0
```
