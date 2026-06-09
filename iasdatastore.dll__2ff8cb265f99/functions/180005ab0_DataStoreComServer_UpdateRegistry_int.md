# DataStoreComServer::UpdateRegistry(int)

- ea: `0x180005ab0`
- end: `0x180005b01`
- name: `?UpdateRegistry@DataStoreComServer@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180005af6`
- `iassvcs!IASRegisterComponent` at `0x180005af6`

## string_xrefs

- `0x180005ab8`: `DataStoreComServer`

## pseudocode

```c
__int64 __fastcall DataStoreComServer::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_48da6741_1bf0_4a44_8325_293086c79077,
           L"IAS",
           L"DataStoreComServer",
           0,
           &GUID_dfdfb4eb_32b7_4b7f_a3d4_f798f75d3a46,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180005ab0  sub     rsp, 58h
0x180005ab4  mov     [rsp+58h+var_18], ecx
0x180005ab8  lea     r9, aDatastorecomse_5; "DataStoreComServer"
0x180005abf  mov     rcx, cs:hInstance
0x180005ac6  lea     r8, aIas; "IAS"
0x180005acd  xor     eax, eax
0x180005acf  lea     rdx, _GUID_48da6741_1bf0_4a44_8325_293086c79077
0x180005ad6  mov     [rsp+58h+var_20], ax
0x180005adb  lea     rax, _GUID_dfdfb4eb_32b7_4b7f_a3d4_f798f75d3a46
0x180005ae2  mov     [rsp+58h+var_28], 1
0x180005ae9  mov     [rsp+58h+var_30], rax
0x180005aee  mov     [rsp+58h+var_38], 0
0x180005af6  call    cs:__imp_IASRegisterComponent
0x180005afc  add     rsp, 58h
0x180005b00  retn
```
