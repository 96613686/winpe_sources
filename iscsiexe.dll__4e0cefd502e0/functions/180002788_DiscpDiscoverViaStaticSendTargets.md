# DiscpDiscoverViaStaticSendTargets

- ea: `0x180002788`
- end: `0x1800027c6`
- name: `DiscpDiscoverViaStaticSendTargets`
- size: `62`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009358`
- `0x180013a1c`

## import_xrefs

- `ISCSIUM!DiscpEnumerateRegistryValues` at `0x1800027bb`
- `ISCSIUM!DiscpEnumerateRegistryValues` at `0x1800027bb`

## pseudocode

```c
__int64 DiscpDiscoverViaStaticSendTargets()
{
  char v1; // [rsp+20h] [rbp-28h]

  v1 = 1;
  return DiscpEnumerateRegistryValues(
           0,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Send Targets",
           3,
           1608,
           v1,
           &DiscpEnumStaticSendTarget,
           0);
}

```

## disassembly

```asm
0x180002788  sub     rsp, 48h
0x18000278c  lea     rax, DiscpEnumStaticSendTarget
0x180002793  mov     [rsp+48h+var_18], 0
0x18000279c  mov     [rsp+48h+var_20], rax
0x1800027a1  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800027a8  mov     r9d, 648h
0x1800027ae  mov     [rsp+48h+var_28], 1
0x1800027b3  mov     r8d, 3
0x1800027b9  xor     ecx, ecx
0x1800027bb  call    cs:__imp_DiscpEnumerateRegistryValues
0x1800027c1  add     rsp, 48h
0x1800027c5  retn
```
