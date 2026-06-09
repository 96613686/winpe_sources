# NTEventLog::UpdateRegistry(int)

- ea: `0x180012110`
- end: `0x180012160`
- name: `?UpdateRegistry@NTEventLog@@SAJH@Z`
- size: `80`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000c470`

## pseudocode

```c
__int64 __fastcall NTEventLog::UpdateRegistry(int a1)
{
  return IASRegisterComponent(
           hModule,
           &GUID_6bc0969f_0ce6_11d1_baae_00c04fc2e20d,
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           1,
           0,
           a1);
}

```

## disassembly

```asm
0x180012110  sub     rsp, 58h
0x180012114  mov     [rsp+58h+var_18], ecx; int
0x180012118  lea     r9, aNteventlog; "NTEventLog"
0x18001211f  mov     rcx, cs:hModule; hModule
0x180012126  lea     r8, ServiceName; "IAS"
0x18001212d  xor     eax, eax
0x18001212f  lea     rdx, _GUID_6bc0969f_0ce6_11d1_baae_00c04fc2e20d; rguid
0x180012136  mov     [rsp+58h+var_20], ax; __int16
0x18001213b  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180012142  mov     [rsp+58h+var_28], 1; __int16
0x180012149  mov     [rsp+58h+var_30], rax; GUID *
0x18001214e  mov     [rsp+58h+var_38], 0; int
0x180012156  call    IASRegisterComponent
0x18001215b  add     rsp, 58h
0x18001215f  retn
```
