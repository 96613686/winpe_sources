# CDockInterface::DockProfileToDeviceInstancePath(_DOCK_PROFILE const &,unsigned __int64,ushort *,unsigned __int64 *)

- ea: `0x18001b22c`
- end: `0x18001b285`
- name: `?DockProfileToDeviceInstancePath@CDockInterface@@AEAAJAEBU_DOCK_PROFILE@@_KPEAGPEA_K@Z`
- size: `89`
- prototype: `__int64 __fastcall(DockingProviders **this, const struct _DOCK_PROFILE *, __int64, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b428`
- `0x18001bad0`

## callees

- `0x180016420`
- `0x18001b324`

## pseudocode

```c
__int64 __fastcall CDockInterface::DockProfileToDeviceInstancePath(
        DockingProviders **this,
        const struct _DOCK_PROFILE *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int64 *a5)
{
  const unsigned __int8 *v6; // rbx
  const unsigned __int16 *v8; // rax
  unsigned __int64 v9; // r9

  v6 = (const unsigned __int8 *)a2 + 528;
  v8 = DockingProviders::ProviderName(this[2], *((_QWORD *)a2 + 143));
  return CDockInterface::HardwareAddressToDeviceInstancePath((CDockInterface *)this, v8, v6, v9, a4, a5);
}

```

## disassembly

```asm
0x18001b22c  mov     [rsp+arg_0], rbx
0x18001b231  mov     [rsp+arg_8], rsi
0x18001b236  push    rdi
0x18001b237  sub     rsp, 30h
0x18001b23b  mov     rdi, rcx
0x18001b23e  lea     rbx, [rdx+210h]
0x18001b245  mov     rdx, [rdx+478h]; unsigned __int64
0x18001b24c  mov     rsi, r9
0x18001b24f  mov     rcx, [rcx+10h]; this
0x18001b253  call    ?ProviderName@DockingProviders@@QEAAPEBG_K@Z; DockingProviders::ProviderName(unsigned __int64)
0x18001b258  mov     rdx, rax; unsigned __int16 *
0x18001b25b  mov     r8, rbx; unsigned __int8 *
0x18001b25e  mov     rax, [rsp+38h+arg_20]
0x18001b263  mov     rcx, rdi; this
0x18001b266  mov     [rsp+38h+var_10], rax; unsigned __int64 *
0x18001b26b  mov     [rsp+38h+var_18], rsi; unsigned __int16 *
0x18001b270  call    ?HardwareAddressToDeviceInstancePath@CDockInterface@@AEAAJPEBGQEBE_KPEAGPEA_K@Z; CDockInterface::HardwareAddressToDeviceInstancePath(ushort const *,uchar const * const,unsigned __int64,ushort *,unsigned __int64 *)
0x18001b275  mov     rbx, [rsp+38h+arg_0]
0x18001b27a  mov     rsi, [rsp+38h+arg_8]
0x18001b27f  add     rsp, 30h
0x18001b283  pop     rdi
0x18001b284  retn
```
