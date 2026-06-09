# MachineNameMapper::UpdateRegistry(int)

- ea: `0x180008ea0`
- end: `0x180008ef1`
- name: `?UpdateRegistry@MachineNameMapper@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180008ee6`
- `iassvcs!IASRegisterComponent` at `0x180008ee6`

## pseudocode

```c
__int64 __fastcall MachineNameMapper::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc096dc_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"MachineNameMapper",
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008ea0  sub     rsp, 58h
0x180008ea4  mov     [rsp+58h+var_18], ecx
0x180008ea8  lea     r9, aMachinenamemap; "MachineNameMapper"
0x180008eaf  mov     rcx, cs:hInstance
0x180008eb6  lea     r8, aIas; "IAS"
0x180008ebd  xor     eax, eax
0x180008ebf  lea     rdx, _GUID_6bc096dc_0ce6_11d1_baae_00c04fc2e20d
0x180008ec6  mov     [rsp+58h+var_20], ax
0x180008ecb  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180008ed2  mov     [rsp+58h+var_28], 1
0x180008ed9  mov     [rsp+58h+var_30], rax
0x180008ede  mov     [rsp+58h+var_38], 0
0x180008ee6  call    cs:__imp_IASRegisterComponent
0x180008eec  add     rsp, 58h
0x180008ef0  retn
```
