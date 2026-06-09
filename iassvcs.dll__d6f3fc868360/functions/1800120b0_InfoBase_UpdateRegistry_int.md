# InfoBase::UpdateRegistry(int)

- ea: `0x1800120b0`
- end: `0x180012100`
- name: `?UpdateRegistry@InfoBase@@SAJH@Z`
- size: `80`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000c470`

## pseudocode

```c
__int64 __fastcall InfoBase::UpdateRegistry(int a1)
{
  return IASRegisterComponent(
           hModule,
           &GUID_6bc096a0_0ce6_11d1_baae_00c04fc2e20d,
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           1,
           0,
           a1);
}

```

## disassembly

```asm
0x1800120b0  sub     rsp, 58h
0x1800120b4  mov     [rsp+58h+var_18], ecx; int
0x1800120b8  lea     r9, aInfobase; "InfoBase"
0x1800120bf  mov     rcx, cs:hModule; hModule
0x1800120c6  lea     r8, ServiceName; "IAS"
0x1800120cd  xor     eax, eax
0x1800120cf  lea     rdx, _GUID_6bc096a0_0ce6_11d1_baae_00c04fc2e20d; rguid
0x1800120d6  mov     [rsp+58h+var_20], ax; __int16
0x1800120db  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x1800120e2  mov     [rsp+58h+var_28], 1; __int16
0x1800120e9  mov     [rsp+58h+var_30], rax; GUID *
0x1800120ee  mov     [rsp+58h+var_38], 0; int
0x1800120f6  call    IASRegisterComponent
0x1800120fb  add     rsp, 58h
0x1800120ff  retn
```
