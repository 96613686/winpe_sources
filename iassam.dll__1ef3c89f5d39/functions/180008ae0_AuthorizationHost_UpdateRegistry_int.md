# AuthorizationHost::UpdateRegistry(int)

- ea: `0x180008ae0`
- end: `0x180008b31`
- name: `?UpdateRegistry@AuthorizationHost@@SAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## import_xrefs

- `iassvcs!IASRegisterComponent` at `0x180008b26`
- `iassvcs!IASRegisterComponent` at `0x180008b26`

## pseudocode

```c
__int64 __fastcall AuthorizationHost::UpdateRegistry(int a1)
{
  __int16 v2; // [rsp+30h] [rbp-28h]
  __int16 v3; // [rsp+38h] [rbp-20h]

  v3 = 0;
  v2 = 1;
  return IASRegisterComponent(
           hInstance,
           &GUID_6bc09899_0ce6_11d1_baae_00c04fc2e20d,
           L"IAS",
           L"AuthorizationHost",
           8,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           v2,
           v3,
           a1);
}

```

## disassembly

```asm
0x180008ae0  sub     rsp, 58h
0x180008ae4  mov     [rsp+58h+var_18], ecx
0x180008ae8  lea     r9, aAuthorizationh; "AuthorizationHost"
0x180008aef  mov     rcx, cs:hInstance
0x180008af6  lea     r8, aIas; "IAS"
0x180008afd  xor     eax, eax
0x180008aff  lea     rdx, _GUID_6bc09899_0ce6_11d1_baae_00c04fc2e20d
0x180008b06  mov     [rsp+58h+var_20], ax
0x180008b0b  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180008b12  mov     [rsp+58h+var_28], 1
0x180008b19  mov     [rsp+58h+var_30], rax
0x180008b1e  mov     [rsp+58h+var_38], 8
0x180008b26  call    cs:__imp_IASRegisterComponent
0x180008b2c  add     rsp, 58h
0x180008b30  retn
```
