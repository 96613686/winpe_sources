# NTSamAuthentication::UpdateRegistry(int)

- ea: `0x180008f00`
- end: `0x180008f51`
- name: `?UpdateRegistry@NTSamAuthentication@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180008f46`
- `iassvcs!IASRegisterComponent` at `0x180008f46`

## pseudocode

```c
__int64 __fastcall NTSamAuthentication::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc09896_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"NTSamAuthentication",
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008f00  sub     rsp, 58h
0x180008f04  mov     [rsp+58h+var_18], ecx
0x180008f08  lea     r9, aNtsamauthentic; "NTSamAuthentication"
0x180008f0f  mov     rcx, cs:hInstance
0x180008f16  lea     r8, aIas; "IAS"
0x180008f1d  xor     eax, eax
0x180008f1f  lea     rdx, _GUID_6bc09896_0ce6_11d1_baae_00c04fc2e20d
0x180008f26  mov     [rsp+58h+var_20], ax
0x180008f2b  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180008f32  mov     [rsp+58h+var_28], 1
0x180008f39  mov     [rsp+58h+var_30], rax
0x180008f3e  mov     [rsp+58h+var_38], 0
0x180008f46  call    cs:__imp_IASRegisterComponent
0x180008f4c  add     rsp, 58h
0x180008f50  retn
```
