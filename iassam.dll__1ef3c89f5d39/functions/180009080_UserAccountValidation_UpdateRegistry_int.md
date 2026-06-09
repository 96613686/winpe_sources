# UserAccountValidation::UpdateRegistry(int)

- ea: `0x180009080`
- end: `0x1800090d1`
- name: `?UpdateRegistry@UserAccountValidation@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x1800090c6`
- `iassvcs!IASRegisterComponent` at `0x1800090c6`

## pseudocode

```c
__int64 __fastcall UserAccountValidation::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc0989e_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"UserAccountValidation",
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180009080  sub     rsp, 58h
0x180009084  mov     [rsp+58h+var_18], ecx
0x180009088  lea     r9, aUseraccountval; "UserAccountValidation"
0x18000908f  mov     rcx, cs:hInstance
0x180009096  lea     r8, aIas; "IAS"
0x18000909d  xor     eax, eax
0x18000909f  lea     rdx, _GUID_6bc0989e_0ce6_11d1_baae_00c04fc2e20d
0x1800090a6  mov     [rsp+58h+var_20], ax
0x1800090ab  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x1800090b2  mov     [rsp+58h+var_28], 1
0x1800090b9  mov     [rsp+58h+var_30], rax
0x1800090be  mov     [rsp+58h+var_38], 0
0x1800090c6  call    cs:__imp_IASRegisterComponent
0x1800090cc  add     rsp, 58h
0x1800090d0  retn
```
