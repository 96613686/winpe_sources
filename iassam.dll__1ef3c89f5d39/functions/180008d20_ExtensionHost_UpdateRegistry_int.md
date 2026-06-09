# ExtensionHost::UpdateRegistry(int)

- ea: `0x180008d20`
- end: `0x180008d71`
- name: `?UpdateRegistry@ExtensionHost@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180008d66`
- `iassvcs!IASRegisterComponent` at `0x180008d66`

## string_xrefs

- `0x180008d28`: `ExtensionHost`

## pseudocode

```c
__int64 __fastcall ExtensionHost::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_8c334a55_ddb9_491c_817e_35a6b85d2ecb,
           L"IAS",
           L"ExtensionHost",
           0,
           &GUID_73ca1716_d932_4015_a5da_0b8037c24788,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008d20  sub     rsp, 58h
0x180008d24  mov     [rsp+58h+var_18], ecx
0x180008d28  lea     r9, aExtensionhost; "ExtensionHost"
0x180008d2f  mov     rcx, cs:hInstance
0x180008d36  lea     r8, aIas; "IAS"
0x180008d3d  xor     eax, eax
0x180008d3f  lea     rdx, _GUID_8c334a55_ddb9_491c_817e_35a6b85d2ecb
0x180008d46  mov     [rsp+58h+var_20], ax
0x180008d4b  lea     rax, _GUID_73ca1716_d932_4015_a5da_0b8037c24788
0x180008d52  mov     [rsp+58h+var_28], 1
0x180008d59  mov     [rsp+58h+var_30], rax
0x180008d5e  mov     [rsp+58h+var_38], 0
0x180008d66  call    cs:__imp_IASRegisterComponent
0x180008d6c  add     rsp, 58h
0x180008d70  retn
```
