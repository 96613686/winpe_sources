# AuditChannel::UpdateRegistry(int)

- ea: `0x180012050`
- end: `0x1800120a0`
- name: `?UpdateRegistry@AuditChannel@@SAJH@Z`
- size: `80`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000c470`

## pseudocode

```c
__int64 __fastcall AuditChannel::UpdateRegistry(int a1)
{
  return IASRegisterComponent(
           hModule,
           &GUID_6bc0969d_0ce6_11d1_baae_00c04fc2e20d,
           0,
           &GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,
           1,
           0,
           a1);
}

```

## disassembly

```asm
0x180012050  sub     rsp, 58h
0x180012054  mov     [rsp+58h+var_18], ecx; int
0x180012058  lea     r9, aAuditchannel; "AuditChannel"
0x18001205f  mov     rcx, cs:hModule; hModule
0x180012066  lea     r8, ServiceName; "IAS"
0x18001206d  xor     eax, eax
0x18001206f  lea     rdx, _GUID_6bc0969d_0ce6_11d1_baae_00c04fc2e20d; rguid
0x180012076  mov     [rsp+58h+var_20], ax; __int16
0x18001207b  lea     rax, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d
0x180012082  mov     [rsp+58h+var_28], 1; __int16
0x180012089  mov     [rsp+58h+var_30], rax; GUID *
0x18001208e  mov     [rsp+58h+var_38], 0; int
0x180012096  call    IASRegisterComponent
0x18001209b  add     rsp, 58h
0x18001209f  retn
```
