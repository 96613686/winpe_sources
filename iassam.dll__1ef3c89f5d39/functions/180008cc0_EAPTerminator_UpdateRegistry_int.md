# EAPTerminator::UpdateRegistry(int)

- ea: `0x180008cc0`
- end: `0x180008d11`
- name: `?UpdateRegistry@EAPTerminator@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180008d06`
- `iassvcs!IASRegisterComponent` at `0x180008d06`

## pseudocode

```c
__int64 __fastcall EAPTerminator::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc096df_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"EAPTerminator",
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008cc0  sub     rsp, 58h
0x180008cc4  mov     [rsp+58h+var_18], ecx
0x180008cc8  lea     r9, aEapterminator; "EAPTerminator"
0x180008ccf  mov     rcx, cs:hInstance
0x180008cd6  lea     r8, aIas; "IAS"
0x180008cdd  xor     eax, eax
0x180008cdf  lea     rdx, _GUID_6bc096df_0ce6_11d1_baae_00c04fc2e20d
0x180008ce6  mov     [rsp+58h+var_20], ax
0x180008ceb  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180008cf2  mov     [rsp+58h+var_28], 1
0x180008cf9  mov     [rsp+58h+var_30], rax
0x180008cfe  mov     [rsp+58h+var_38], 0
0x180008d06  call    cs:__imp_IASRegisterComponent
0x180008d0c  add     rsp, 58h
0x180008d10  retn
```
