# ServiceCallbacks::UpdateTokenAvailability(bool)

- ea: `0x180009bf0`
- end: `0x180009c06`
- name: `?UpdateTokenAvailability@ServiceCallbacks@@UEAAJ_N@Z`
- size: `22`
- prototype: `__int64 __fastcall(ServiceCallbacks *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ServiceCallbacks::UpdateTokenAvailability(ServiceCallbacks *this)
{
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_1800185D0 + 248LL))(qword_1800185D0);
}

```

## disassembly

```asm
0x180009bf0  mov     rcx, cs:qword_1800185D0
0x180009bf7  mov     rax, [rcx]
0x180009bfa  mov     rax, [rax+0F8h]
0x180009c01  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
