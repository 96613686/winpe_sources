# _ServiceManager::ControlHandler_::_1_::catch$0

- ea: `0x18001570e`
- end: `0x18001573f`
- name: `_ServiceManager::ControlHandler_::_1_::catch$0`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180017010`

## pseudocode

```c
__int64 __fastcall ServiceManager::ControlHandler_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 32) + 16LL))(*(_QWORD *)(a2 + 32));
  return 0;
}

```

## disassembly

```asm
0x18001570e  mov     [rsp+arg_8], rdx
0x180015713  push    rbp
0x180015714  sub     rsp, 20h
0x180015718  mov     rbp, rdx
0x18001571b  mov     rcx, [rbp+20h]
0x18001571f  mov     rax, [rcx]
0x180015722  mov     rax, [rax+10h]
0x180015726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001572b  mov     [rbp+48h], eax
0x18001572e  mov     rax, 0
0x180015738  add     rsp, 20h
0x18001573c  pop     rbp
0x18001573d  retn
```
