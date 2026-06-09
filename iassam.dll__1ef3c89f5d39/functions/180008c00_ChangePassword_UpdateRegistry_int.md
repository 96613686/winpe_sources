# ChangePassword::UpdateRegistry(int)

- ea: `0x180008c00`
- end: `0x180008c51`
- name: `?UpdateRegistry@ChangePassword@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180008c46`
- `iassvcs!IASRegisterComponent` at `0x180008c46`

## pseudocode

```c
__int64 __fastcall ChangePassword::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc0989b_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"ChangePassword",
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008c00  sub     rsp, 58h
0x180008c04  mov     [rsp+58h+var_18], ecx
0x180008c08  lea     r9, aChangepassword; "ChangePassword"
0x180008c0f  mov     rcx, cs:hInstance
0x180008c16  lea     r8, aIas; "IAS"
0x180008c1d  xor     eax, eax
0x180008c1f  lea     rdx, _GUID_6bc0989b_0ce6_11d1_baae_00c04fc2e20d
0x180008c26  mov     [rsp+58h+var_20], ax
0x180008c2b  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180008c32  mov     [rsp+58h+var_28], 1
0x180008c39  mov     [rsp+58h+var_30], rax
0x180008c3e  mov     [rsp+58h+var_38], 0
0x180008c46  call    cs:__imp_IASRegisterComponent
0x180008c4c  add     rsp, 58h
0x180008c50  retn
```
