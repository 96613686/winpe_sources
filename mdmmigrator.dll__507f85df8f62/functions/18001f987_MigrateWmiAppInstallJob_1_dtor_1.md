# _MigrateWmiAppInstallJob_::_1_::dtor$1

- ea: `0x18001f987`
- end: `0x18001f993`
- name: `_MigrateWmiAppInstallJob_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000d9d0`

## pseudocode

```c
void __fastcall MigrateWmiAppInstallJob_::_1_::dtor_1(__int64 a1, void **a2)
{
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(a2 + 17, (const struct std::nothrow_t *)a2);
}

```

## disassembly

```asm
0x18001f987  lea     rcx, [rdx+88h]
0x18001f98e  jmp     ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
```
