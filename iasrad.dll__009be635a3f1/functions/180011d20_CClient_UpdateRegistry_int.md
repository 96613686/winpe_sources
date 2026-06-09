# CClient::UpdateRegistry(int)

- ea: `0x180011d20`
- end: `0x180011d71`
- name: `?UpdateRegistry@CClient@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180011d66`
- `iassvcs!IASRegisterComponent` at `0x180011d66`

## pseudocode

```c
__int64 __fastcall CClient::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc096da_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"CClient",
           0,
           &GUID_6bc09890_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180011d20  sub     rsp, 58h
0x180011d24  mov     [rsp+58h+var_18], ecx
0x180011d28  lea     r9, aCclient; "CClient"
0x180011d2f  mov     rcx, cs:hInstance
0x180011d36  lea     r8, aIas; "IAS"
0x180011d3d  xor     eax, eax
0x180011d3f  lea     rdx, _GUID_6bc096da_0ce6_11d1_baae_00c04fc2e20d
0x180011d46  mov     [rsp+58h+var_20], ax
0x180011d4b  lea     rax, _GUID_6bc09890_0ce6_11d1_baae_00c04fc2e20d
0x180011d52  mov     [rsp+58h+var_28], 1
0x180011d59  mov     [rsp+58h+var_30], rax
0x180011d5e  mov     [rsp+58h+var_38], 0
0x180011d66  call    cs:__imp_IASRegisterComponent
0x180011d6c  add     rsp, 58h
0x180011d70  retn
```
