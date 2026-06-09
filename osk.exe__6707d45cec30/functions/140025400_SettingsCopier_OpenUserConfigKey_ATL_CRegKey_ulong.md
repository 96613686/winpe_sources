# SettingsCopier::OpenUserConfigKey(ATL::CRegKey &,ulong)

- ea: `0x140025400`
- end: `0x140025469`
- name: `?OpenUserConfigKey@SettingsCopier@@CAJAEAVCRegKey@ATL@@K@Z`
- size: `105`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140025184`

## callees

- `0x140007e90`
- `0x1400170d8`
- `0x140025400`

## string_xrefs

- `0x14002540c`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`
- `0x140025437`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`

## pseudocode

```c
__int64 __fastcall SettingsCopier::OpenUserConfigKey(struct ATL::CRegKey *this)
{
  unsigned __int16 *v2; // r9
  HKEY v4; // [rsp+30h] [rbp-18h]
  unsigned int v5; // [rsp+58h] [rbp+10h] BYREF

  if ( (unsigned int)ATL::CRegKey::Open(this, HKEY_CURRENT_USER, SettingsCopier::_ATConfigKeyString, 0x20019u) )
    return (unsigned int)ATL::CRegKey::Create(
                           this,
                           HKEY_CURRENT_USER,
                           SettingsCopier::_ATConfigKeyString,
                           v2,
                           1u,
                           0x20019u,
                           v4,
                           &v5) != 0
         ? 0x80004005
         : 0;
  else
    return 0;
}

```

## disassembly

```asm
0x140025400  push    rbx
0x140025402  sub     rsp, 40h
0x140025406  mov     r9d, 20019h; unsigned int
0x14002540c  lea     r8, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140025413  mov     rdx, 0FFFFFFFF80000001h; hKey
0x14002541a  mov     rbx, rcx
0x14002541d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140025422  test    eax, eax
0x140025424  jz      short loc_140025461
0x140025426  lea     rax, [rsp+48h+arg_8]
0x14002542b  mov     rdx, 0FFFFFFFF80000001h; hKey
0x140025432  mov     [rsp+48h+var_10], rax; unsigned int *
0x140025437  lea     r8, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14002543e  mov     [rsp+48h+var_20], 20019h; REGSAM
0x140025446  mov     rcx, rbx; this
0x140025449  mov     [rsp+48h+var_28], 1; DWORD
0x140025451  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140025456  neg     eax
0x140025458  sbb     eax, eax
0x14002545a  and     eax, 80004005h
0x14002545f  jmp     short loc_140025463
0x140025461  xor     eax, eax
0x140025463  add     rsp, 40h
0x140025467  pop     rbx
0x140025468  retn
```
