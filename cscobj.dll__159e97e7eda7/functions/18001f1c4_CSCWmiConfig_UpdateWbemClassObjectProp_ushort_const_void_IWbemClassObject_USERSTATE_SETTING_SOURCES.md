# CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)

- ea: `0x18001f1c4`
- end: `0x18001f223`
- name: `?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z`
- size: `95`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ee5c`
- `0x180021b60`
- `0x180022030`
- `0x1800221f0`
- `0x1800223f0`

## callees

- `0x18001ce64`
- `0x18001d78c`
- `0x18001f1c4`
- `0x18002938c`

## pseudocode

```c
__int64 __fastcall CSCWmiConfig::UpdateWbemClassObjectProp(const WCHAR *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int PropertyWMISettingDescriptor; // edi
  int v9; // eax
  __int64 v10; // rcx
  struct USERSTATE_SETTING_DESCRIPTOR *v12; // [rsp+30h] [rbp-38h] BYREF

  v12 = 0;
  PropertyWMISettingDescriptor = FindPropertyWMISettingDescriptor(a1, &v12);
  v9 = CSCWmiConfig::AddSettingAuthorityFlag(a4);
  if ( PropertyWMISettingDescriptor >= 0 )
    return (unsigned int)UpdateWbemClassObjectProp(v10, v12, a1, a2, a3, v9);
  return (unsigned int)PropertyWMISettingDescriptor;
}

```

## disassembly

```asm
0x18001f1c4  push    rbx
0x18001f1c6  push    rbp
0x18001f1c7  push    rsi
0x18001f1c8  push    rdi
0x18001f1c9  push    r14
0x18001f1cb  sub     rsp, 40h
0x18001f1cf  mov     r14, rdx
0x18001f1d2  mov     [rsp+68h+var_38], 0
0x18001f1db  lea     rdx, [rsp+68h+var_38]; struct USERSTATE_SETTING_DESCRIPTOR **
0x18001f1e0  mov     ebx, r9d
0x18001f1e3  mov     rbp, r8
0x18001f1e6  mov     rsi, rcx
0x18001f1e9  call    ?FindPropertyWMISettingDescriptor@@YAJPEBGPEAPEBUUSERSTATE_SETTING_DESCRIPTOR@@@Z; FindPropertyWMISettingDescriptor(ushort const *,USERSTATE_SETTING_DESCRIPTOR const * *)
0x18001f1ee  mov     ecx, ebx
0x18001f1f0  mov     edi, eax
0x18001f1f2  call    ?AddSettingAuthorityFlag@CSCWmiConfig@@YA?AW4USERSTATE_SETTING_SOURCES@@W42@@Z; CSCWmiConfig::AddSettingAuthorityFlag(USERSTATE_SETTING_SOURCES)
0x18001f1f7  test    edi, edi
0x18001f1f9  js      short loc_18001F216
0x18001f1fb  mov     rdx, [rsp+68h+var_38]
0x18001f200  mov     r9, r14
0x18001f203  mov     [rsp+68h+var_40], eax
0x18001f207  mov     r8, rsi
0x18001f20a  mov     [rsp+68h+var_48], rbp
0x18001f20f  call    ?UpdateWbemClassObjectProp@@YAJW4UST_COMPONENT_ID@@PEBUUSERSTATE_SETTING_DESCRIPTOR@@PEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; UpdateWbemClassObjectProp(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const *,ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001f214  mov     edi, eax
0x18001f216  mov     eax, edi
0x18001f218  add     rsp, 40h
0x18001f21c  pop     r14
0x18001f21e  pop     rdi
0x18001f21f  pop     rsi
0x18001f220  pop     rbp
0x18001f221  pop     rbx
0x18001f222  retn
```
