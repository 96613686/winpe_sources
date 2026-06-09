# CPnpCleanTaskHandler::Stop(long *)

- ea: `0x180003ce0`
- end: `0x180003cf3`
- name: `?Stop@CPnpCleanTaskHandler@@UEAAJPEAJ@Z`
- size: `19`
- prototype: `__int64 __fastcall(CPnpCleanTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CPnpCleanTaskHandler::Stop(CPnpCleanTaskHandler *this, int *a2)
{
  __int64 v2; // rax

  v2 = *(_QWORD *)this;
  *((_DWORD *)this + 16) = 1;
  return (*(__int64 (__fastcall **)(CPnpCleanTaskHandler *, int *))(v2 + 80))(this, a2);
}

```

## disassembly

```asm
0x180003ce0  mov     rax, [rcx]
0x180003ce3  mov     dword ptr [rcx+40h], 1
0x180003cea  mov     rax, [rax+50h]
0x180003cee  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
