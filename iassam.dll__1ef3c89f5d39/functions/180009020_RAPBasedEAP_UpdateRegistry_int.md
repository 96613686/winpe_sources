# RAPBasedEAP::UpdateRegistry(int)

- ea: `0x180009020`
- end: `0x180009071`
- name: `?UpdateRegistry@RAPBasedEAP@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180009066`
- `iassvcs!IASRegisterComponent` at `0x180009066`

## pseudocode

```c
__int64 __fastcall RAPBasedEAP::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc0989a_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"RAPBasedEAP",
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180009020  sub     rsp, 58h
0x180009024  mov     [rsp+58h+var_18], ecx
0x180009028  lea     r9, aRapbasedeap; "RAPBasedEAP"
0x18000902f  mov     rcx, cs:hInstance
0x180009036  lea     r8, aIas; "IAS"
0x18000903d  xor     eax, eax
0x18000903f  lea     rdx, _GUID_6bc0989a_0ce6_11d1_baae_00c04fc2e20d
0x180009046  mov     [rsp+58h+var_20], ax
0x18000904b  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180009052  mov     [rsp+58h+var_28], 1
0x180009059  mov     [rsp+58h+var_30], rax
0x18000905e  mov     [rsp+58h+var_38], 0
0x180009066  call    cs:__imp_IASRegisterComponent
0x18000906c  add     rsp, 58h
0x180009070  retn
```
