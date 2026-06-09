# BaseCampHost::UpdateRegistry(int)

- ea: `0x180008b40`
- end: `0x180008b91`
- name: `?UpdateRegistry@BaseCampHost@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180008b86`
- `iassvcs!IASRegisterComponent` at `0x180008b86`

## pseudocode

```c
__int64 __fastcall BaseCampHost::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc09898_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"BaseCampHost",
           8,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008b40  sub     rsp, 58h
0x180008b44  mov     [rsp+58h+var_18], ecx
0x180008b48  lea     r9, aBasecamphost; "BaseCampHost"
0x180008b4f  mov     rcx, cs:hInstance
0x180008b56  lea     r8, aIas; "IAS"
0x180008b5d  xor     eax, eax
0x180008b5f  lea     rdx, _GUID_6bc09898_0ce6_11d1_baae_00c04fc2e20d
0x180008b66  mov     [rsp+58h+var_20], ax
0x180008b6b  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180008b72  mov     [rsp+58h+var_28], 1
0x180008b79  mov     [rsp+58h+var_30], rax
0x180008b7e  mov     [rsp+58h+var_38], 8
0x180008b86  call    cs:__imp_IASRegisterComponent
0x180008b8c  add     rsp, 58h
0x180008b90  retn
```
