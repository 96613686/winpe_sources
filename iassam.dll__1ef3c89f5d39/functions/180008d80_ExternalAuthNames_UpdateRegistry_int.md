# ExternalAuthNames::UpdateRegistry(int)

- ea: `0x180008d80`
- end: `0x180008dd1`
- name: `?UpdateRegistry@ExternalAuthNames@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180008dc6`
- `iassvcs!IASRegisterComponent` at `0x180008dc6`

## pseudocode

```c
__int64 __fastcall ExternalAuthNames::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc096db_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"ExternalAuthNames",
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008d80  sub     rsp, 58h
0x180008d84  mov     [rsp+58h+var_18], ecx
0x180008d88  lea     r9, aExternalauthna; "ExternalAuthNames"
0x180008d8f  mov     rcx, cs:hInstance
0x180008d96  lea     r8, aIas; "IAS"
0x180008d9d  xor     eax, eax
0x180008d9f  lea     rdx, _GUID_6bc096db_0ce6_11d1_baae_00c04fc2e20d
0x180008da6  mov     [rsp+58h+var_20], ax
0x180008dab  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180008db2  mov     [rsp+58h+var_28], 1
0x180008db9  mov     [rsp+58h+var_30], rax
0x180008dbe  mov     [rsp+58h+var_38], 0
0x180008dc6  call    cs:__imp_IASRegisterComponent
0x180008dcc  add     rsp, 58h
0x180008dd0  retn
```
