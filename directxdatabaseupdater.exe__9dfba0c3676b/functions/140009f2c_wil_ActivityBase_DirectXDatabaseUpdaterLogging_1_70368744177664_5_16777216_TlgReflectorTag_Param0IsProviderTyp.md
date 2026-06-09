# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x140009f2c`
- end: `0x140009f38`
- name: `?ReportStopActivity@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140006b80`

## callees

- `0x14001a010`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        __int64 a1)
{
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x140009f2c  mov     rax, [rcx]
0x140009f2f  mov     rax, [rax+8]
0x140009f33  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
