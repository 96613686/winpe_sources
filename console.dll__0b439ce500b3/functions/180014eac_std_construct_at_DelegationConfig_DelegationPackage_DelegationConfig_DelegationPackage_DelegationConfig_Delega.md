# std::construct_at<DelegationConfig::DelegationPackage,DelegationConfig::DelegationPackage>(DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage &&)

- ea: `0x180014eac`
- end: `0x180014edd`
- name: `??$construct_at@UDelegationPackage@DelegationConfig@@U12@@std@@YAPEAUDelegationPackage@DelegationConfig@@QEAU12@$$QEAU12@@Z`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180014c20`
- `0x180014e20`

## callees

- `0x180015028`

## pseudocode

```c
__int64 __fastcall std::construct_at<DelegationConfig::DelegationPackage,DelegationConfig::DelegationPackage>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r11

  *(_OWORD *)a1 = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
  *(_DWORD *)(a1 + 32) = *(_DWORD *)(a2 + 32);
  DelegationConfig::PackageInfo::PackageInfo(a1 + 40, a2 + 40, a3);
  return v3;
}

```

## disassembly

```asm
0x180014eac  sub     rsp, 28h
0x180014eb0  movups  xmm0, xmmword ptr [rdx]
0x180014eb3  mov     r11, rcx
0x180014eb6  movups  xmmword ptr [rcx], xmm0
0x180014eb9  movups  xmm1, xmmword ptr [rdx+10h]
0x180014ebd  movups  xmmword ptr [rcx+10h], xmm1
0x180014ec1  mov     eax, [rdx+20h]
0x180014ec4  add     rdx, 28h ; '('
0x180014ec8  mov     [rcx+20h], eax
0x180014ecb  add     rcx, 28h ; '('
0x180014ecf  call    ??0PackageInfo@DelegationConfig@@QEAA@$$QEAU01@@Z; DelegationConfig::PackageInfo::PackageInfo(DelegationConfig::PackageInfo &&)
0x180014ed4  mov     rax, r11
0x180014ed7  add     rsp, 28h
0x180014edb  retn
```
