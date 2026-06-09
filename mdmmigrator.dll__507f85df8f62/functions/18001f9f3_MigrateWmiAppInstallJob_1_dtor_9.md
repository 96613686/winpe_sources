# _MigrateWmiAppInstallJob_::_1_::dtor$9

- ea: `0x18001f9f3`
- end: `0x18001f9ff`
- name: `_MigrateWmiAppInstallJob_::_1_::dtor$9`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callees

- `0x18000da88`

## pseudocode

```c
void __fastcall MigrateWmiAppInstallJob_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  ErmRevertImpersonate::~ErmRevertImpersonate((ErmRevertImpersonate *)(a2 + 240));
}

```

## disassembly

```asm
0x18001f9f3  lea     rcx, [rdx+0F0h]; this
0x18001f9fa  jmp     ??1ErmRevertImpersonate@@QEAA@XZ; ErmRevertImpersonate::~ErmRevertImpersonate(void)
```
