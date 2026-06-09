# NTSamPerUser::UpdateRegistry(int)

- ea: `0x180008fc0`
- end: `0x180009011`
- name: `?UpdateRegistry@NTSamPerUser@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180009006`
- `iassvcs!IASRegisterComponent` at `0x180009006`

## pseudocode

```c
__int64 __fastcall NTSamPerUser::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc0989c_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"NTSamPerUser",
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008fc0  sub     rsp, 58h
0x180008fc4  mov     [rsp+58h+var_18], ecx
0x180008fc8  lea     r9, aNtsamperuser; "NTSamPerUser"
0x180008fcf  mov     rcx, cs:hInstance
0x180008fd6  lea     r8, aIas; "IAS"
0x180008fdd  xor     eax, eax
0x180008fdf  lea     rdx, _GUID_6bc0989c_0ce6_11d1_baae_00c04fc2e20d
0x180008fe6  mov     [rsp+58h+var_20], ax
0x180008feb  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180008ff2  mov     [rsp+58h+var_28], 1
0x180008ff9  mov     [rsp+58h+var_30], rax
0x180008ffe  mov     [rsp+58h+var_38], 0
0x180009006  call    cs:__imp_IASRegisterComponent
0x18000900c  add     rsp, 58h
0x180009010  retn
```
