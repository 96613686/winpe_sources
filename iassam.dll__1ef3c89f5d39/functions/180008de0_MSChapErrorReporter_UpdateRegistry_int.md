# MSChapErrorReporter::UpdateRegistry(int)

- ea: `0x180008de0`
- end: `0x180008e31`
- name: `?UpdateRegistry@MSChapErrorReporter@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180008e26`
- `iassvcs!IASRegisterComponent` at `0x180008e26`

## pseudocode

```c
__int64 __fastcall MSChapErrorReporter::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc09897_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"MSChapErrorReporter",
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008de0  sub     rsp, 58h
0x180008de4  mov     [rsp+58h+var_18], ecx
0x180008de8  lea     r9, aMschaperrorrep; "MSChapErrorReporter"
0x180008def  mov     rcx, cs:hInstance
0x180008df6  lea     r8, aIas; "IAS"
0x180008dfd  xor     eax, eax
0x180008dff  lea     rdx, _GUID_6bc09897_0ce6_11d1_baae_00c04fc2e20d
0x180008e06  mov     [rsp+58h+var_20], ax
0x180008e0b  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180008e12  mov     [rsp+58h+var_28], 1
0x180008e19  mov     [rsp+58h+var_30], rax
0x180008e1e  mov     [rsp+58h+var_38], 0
0x180008e26  call    cs:__imp_IASRegisterComponent
0x180008e2c  add     rsp, 58h
0x180008e30  retn
```
