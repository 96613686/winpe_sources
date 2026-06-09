# DelegationConfig::DelegationPackage::~DelegationPackage(void)

- ea: `0x180008cb0`
- end: `0x180008cb9`
- name: `??1DelegationPackage@DelegationConfig@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(DelegationConfig::DelegationPackage *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180019593`

## callees

- `0x180008cc0`

## pseudocode

```c
void __fastcall DelegationConfig::DelegationPackage::~DelegationPackage(DelegationConfig::DelegationPackage *this)
{
  DelegationConfig::PackageInfo::~PackageInfo((DelegationConfig::DelegationPackage *)((char *)this + 40));
}

```

## disassembly

```asm
0x180008cb0  add     rcx, 28h ; '('; this
0x180008cb4  jmp     ??1PackageInfo@DelegationConfig@@QEAA@XZ; DelegationConfig::PackageInfo::~PackageInfo(void)
```
