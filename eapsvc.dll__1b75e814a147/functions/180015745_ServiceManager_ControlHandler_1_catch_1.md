# _ServiceManager::ControlHandler_::_1_::catch$1

- ea: `0x180015745`
- end: `0x180015776`
- name: `_ServiceManager::ControlHandler_::_1_::catch$1`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180017010`

## pseudocode

```c
__int64 __fastcall ServiceManager::ControlHandler_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 40) + 16LL))(*(_QWORD *)(a2 + 40));
  return 0;
}

```

## disassembly

```asm
0x180015745  mov     [rsp+arg_8], rdx
0x18001574a  push    rbp
0x18001574b  sub     rsp, 20h
0x18001574f  mov     rbp, rdx
0x180015752  mov     rcx, [rbp+28h]
0x180015756  mov     rax, [rcx]
0x180015759  mov     rax, [rax+10h]
0x18001575d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015762  mov     [rbp+48h], eax
0x180015765  mov     rax, 0
0x18001576f  add     rsp, 20h
0x180015773  pop     rbp
0x180015774  retn
```
