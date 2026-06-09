# NTSamNames::UpdateRegistry(int)

- ea: `0x180008f60`
- end: `0x180008fb1`
- name: `?UpdateRegistry@NTSamNames@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180008fa6`
- `iassvcs!IASRegisterComponent` at `0x180008fa6`

## pseudocode

```c
__int64 __fastcall NTSamNames::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc0989d_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"NTSamNames",
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008f60  sub     rsp, 58h
0x180008f64  mov     [rsp+58h+var_18], ecx
0x180008f68  lea     r9, aNtsamnames; "NTSamNames"
0x180008f6f  mov     rcx, cs:hInstance
0x180008f76  lea     r8, aIas; "IAS"
0x180008f7d  xor     eax, eax
0x180008f7f  lea     rdx, _GUID_6bc0989d_0ce6_11d1_baae_00c04fc2e20d
0x180008f86  mov     [rsp+58h+var_20], ax
0x180008f8b  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180008f92  mov     [rsp+58h+var_28], 1
0x180008f99  mov     [rsp+58h+var_30], rax
0x180008f9e  mov     [rsp+58h+var_38], 0
0x180008fa6  call    cs:__imp_IASRegisterComponent
0x180008fac  add     rsp, 58h
0x180008fb0  retn
```
