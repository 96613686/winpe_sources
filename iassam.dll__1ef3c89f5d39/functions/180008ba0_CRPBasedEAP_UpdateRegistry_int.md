# CRPBasedEAP::UpdateRegistry(int)

- ea: `0x180008ba0`
- end: `0x180008bf1`
- name: `?UpdateRegistry@CRPBasedEAP@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180008be6`
- `iassvcs!IASRegisterComponent` at `0x180008be6`

## pseudocode

```c
__int64 __fastcall CRPBasedEAP::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc096e5_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"CRPBasedEAP",
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008ba0  sub     rsp, 58h
0x180008ba4  mov     [rsp+58h+var_18], ecx
0x180008ba8  lea     r9, aCrpbasedeap; "CRPBasedEAP"
0x180008baf  mov     rcx, cs:hInstance
0x180008bb6  lea     r8, aIas; "IAS"
0x180008bbd  xor     eax, eax
0x180008bbf  lea     rdx, _GUID_6bc096e5_0ce6_11d1_baae_00c04fc2e20d
0x180008bc6  mov     [rsp+58h+var_20], ax
0x180008bcb  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180008bd2  mov     [rsp+58h+var_28], 1
0x180008bd9  mov     [rsp+58h+var_30], rax
0x180008bde  mov     [rsp+58h+var_38], 0
0x180008be6  call    cs:__imp_IASRegisterComponent
0x180008bec  add     rsp, 58h
0x180008bf0  retn
```
