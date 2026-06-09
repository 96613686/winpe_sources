# MachineAccountValidation::UpdateRegistry(int)

- ea: `0x180008e40`
- end: `0x180008e91`
- name: `?UpdateRegistry@MachineAccountValidation@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180008e86`
- `iassvcs!IASRegisterComponent` at `0x180008e86`

## pseudocode

```c
__int64 __fastcall MachineAccountValidation::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc096dd_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"MachineAccountValidation",
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008e40  sub     rsp, 58h
0x180008e44  mov     [rsp+58h+var_18], ecx
0x180008e48  lea     r9, aMachineaccount; "MachineAccountValidation"
0x180008e4f  mov     rcx, cs:hInstance
0x180008e56  lea     r8, aIas; "IAS"
0x180008e5d  xor     eax, eax
0x180008e5f  lea     rdx, _GUID_6bc096dd_0ce6_11d1_baae_00c04fc2e20d
0x180008e66  mov     [rsp+58h+var_20], ax
0x180008e6b  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180008e72  mov     [rsp+58h+var_28], 1
0x180008e79  mov     [rsp+58h+var_30], rax
0x180008e7e  mov     [rsp+58h+var_38], 0
0x180008e86  call    cs:__imp_IASRegisterComponent
0x180008e8c  add     rsp, 58h
0x180008e90  retn
```
