# _ServiceManager::ExecuteService_::_1_::catch$0

- ea: `0x18001577c`
- end: `0x1800157ad`
- name: `_ServiceManager::ExecuteService_::_1_::catch$0`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180017010`

## pseudocode

```c
__int64 __fastcall ServiceManager::ExecuteService_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 88) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 48) + 16LL))(*(_QWORD *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x18001577c  mov     [rsp+arg_8], rdx
0x180015781  push    rbp
0x180015782  sub     rsp, 30h
0x180015786  mov     rbp, rdx
0x180015789  mov     rcx, [rbp+30h]
0x18001578d  mov     rax, [rcx]
0x180015790  mov     rax, [rax+10h]
0x180015794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015799  mov     [rbp+58h], eax
0x18001579c  mov     rax, 0
0x1800157a6  add     rsp, 30h
0x1800157aa  pop     rbp
0x1800157ab  retn
```
