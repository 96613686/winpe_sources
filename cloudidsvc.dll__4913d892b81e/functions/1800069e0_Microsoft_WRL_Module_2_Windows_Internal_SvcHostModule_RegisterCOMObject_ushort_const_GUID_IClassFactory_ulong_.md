# Microsoft::WRL::Module<2,Windows::Internal::SvcHostModule>::RegisterCOMObject(ushort const *,_GUID *,IClassFactory * *,ulong *,uint)

- ea: `0x1800069e0`
- end: `0x1800069fb`
- name: `?RegisterCOMObject@?$Module@$01VSvcHostModule@Internal@Windows@@@WRL@Microsoft@@UEAAJPEBGPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z`
- size: `27`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002df8`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,Windows::Internal::SvcHostModule>::RegisterCOMObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6)
{
  return Microsoft::WRL::Details::RegisterCOMObject<1>(a1, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x1800069e0  mov     eax, [rsp+arg_28]
0x1800069e4  mov     r10, r9
0x1800069e7  mov     r9, [rsp+arg_20]
0x1800069ec  mov     rdx, r8
0x1800069ef  mov     r8, r10
0x1800069f2  mov     dword ptr [rsp+arg_20], eax
0x1800069f6  jmp     ??$RegisterCOMObject@$00@Details@WRL@Microsoft@@YAJPEBGPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z; Microsoft::WRL::Details::RegisterCOMObject<1>(ushort const *,_GUID *,IClassFactory * *,ulong *,uint)
```
