# std::construct_at<DelegationConfig::DelegationBase,DelegationConfig::DelegationBase>(DelegationConfig::DelegationBase * const,DelegationConfig::DelegationBase &&)

- ea: `0x180014e80`
- end: `0x180014ea4`
- name: `??$construct_at@UDelegationBase@DelegationConfig@@U12@@std@@YAPEAUDelegationBase@DelegationConfig@@QEAU12@$$QEAU12@@Z`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180014ac0`
- `0x180014dc0`

## callees

- `0x180015028`

## pseudocode

```c
__int64 __fastcall std::construct_at<DelegationConfig::DelegationBase,DelegationConfig::DelegationBase>(
        _OWORD *a1,
        _OWORD *a2,
        __int64 a3)
{
  __int64 v3; // r11

  *a1 = *a2;
  DelegationConfig::PackageInfo::PackageInfo((__int64)(a1 + 1), (__int64)(a2 + 1), a3);
  return v3;
}

```

## disassembly

```asm
0x180014e80  sub     rsp, 28h
0x180014e84  movups  xmm0, xmmword ptr [rdx]
0x180014e87  mov     r11, rcx
0x180014e8a  add     rdx, 10h
0x180014e8e  movdqu  xmmword ptr [rcx], xmm0
0x180014e92  add     rcx, 10h
0x180014e96  call    ??0PackageInfo@DelegationConfig@@QEAA@$$QEAU01@@Z; DelegationConfig::PackageInfo::PackageInfo(DelegationConfig::PackageInfo &&)
0x180014e9b  mov     rax, r11
0x180014e9e  add     rsp, 28h
0x180014ea2  retn
```
