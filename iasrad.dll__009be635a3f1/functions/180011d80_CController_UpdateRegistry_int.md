# CController::UpdateRegistry(int)

- ea: `0x180011d80`
- end: `0x180011dd1`
- name: `?UpdateRegistry@CController@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180011dc6`
- `iassvcs!IASRegisterComponent` at `0x180011dc6`

## string_xrefs

- `0x180011d88`: `RadiusProtocol`

## pseudocode

```c
__int64 __fastcall CController::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc09894_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"RadiusProtocol",
           0,
           &GUID_6bc09890_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180011d80  sub     rsp, 58h
0x180011d84  mov     [rsp+58h+var_18], ecx
0x180011d88  lea     r9, aRadiusprotocol; "RadiusProtocol"
0x180011d8f  mov     rcx, cs:hInstance
0x180011d96  lea     r8, aIas; "IAS"
0x180011d9d  xor     eax, eax
0x180011d9f  lea     rdx, _GUID_6bc09894_0ce6_11d1_baae_00c04fc2e20d
0x180011da6  mov     [rsp+58h+var_20], ax
0x180011dab  lea     rax, _GUID_6bc09890_0ce6_11d1_baae_00c04fc2e20d
0x180011db2  mov     [rsp+58h+var_28], 1
0x180011db9  mov     [rsp+58h+var_30], rax
0x180011dbe  mov     [rsp+58h+var_38], 0
0x180011dc6  call    cs:__imp_IASRegisterComponent
0x180011dcc  add     rsp, 58h
0x180011dd0  retn
```
