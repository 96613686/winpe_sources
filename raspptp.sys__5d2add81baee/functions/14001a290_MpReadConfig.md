# MpReadConfig

- ea: `0x14001a290`
- end: `0x14001a2f5`
- name: `MpReadConfig`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001af90`

## callees

- `0x14001a290`
- `0x14001a7d8`

## import_xrefs

- `NDIS!NdisOpenConfigurationEx` at `0x14001a2ba`
- `NDIS!NdisOpenConfigurationEx` at `0x14001a2ba`
- `NDIS!NdisCloseConfiguration` at `0x14001a2e0`
- `NDIS!NdisCloseConfiguration` at `0x14001a2e0`

## pseudocode

```c
__int64 __fastcall MpReadConfig(void *a1)
{
  unsigned int v1; // ebx
  _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+20h] [rbp-28h] BYREF
  PVOID ConfigurationHandle; // [rsp+50h] [rbp+8h] BYREF

  ConfigObject.NdisHandle = a1;
  ConfigurationHandle = 0;
  *(_QWORD *)&ConfigObject.Flags = 0;
  *(_QWORD *)&ConfigObject.Header.Type = 1573289;
  v1 = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
  if ( !v1 )
    OsReadConfig(ConfigurationHandle);
  if ( ConfigurationHandle )
    NdisCloseConfiguration(ConfigurationHandle);
  return v1;
}

```

## disassembly

```asm
0x14001a290  push    rbx
0x14001a292  sub     rsp, 40h
0x14001a296  xor     eax, eax
0x14001a298  mov     [rsp+48h+ConfigObject.NdisHandle], rcx
0x14001a29d  lea     rcx, [rsp+48h+ConfigObject]; ConfigObject
0x14001a2a2  mov     [rsp+48h+ConfigurationHandle], rax
0x14001a2a7  lea     rdx, [rsp+48h+ConfigurationHandle]; ConfigurationHandle
0x14001a2ac  mov     qword ptr [rsp+48h+ConfigObject.Flags], rax
0x14001a2b1  mov     qword ptr [rsp+48h+ConfigObject.Header.Type], 1801A9h
0x14001a2ba  call    cs:__imp_NdisOpenConfigurationEx
0x14001a2c1  nop     dword ptr [rax+rax+00h]
0x14001a2c6  mov     ebx, eax
0x14001a2c8  test    eax, eax
0x14001a2ca  jnz     short loc_14001A2D6
0x14001a2cc  mov     rcx, [rsp+48h+ConfigurationHandle]; ConfigurationHandle
0x14001a2d1  call    OsReadConfig
0x14001a2d6  mov     rcx, [rsp+48h+ConfigurationHandle]; ConfigurationHandle
0x14001a2db  test    rcx, rcx
0x14001a2de  jz      short loc_14001A2EC
0x14001a2e0  call    cs:__imp_NdisCloseConfiguration
0x14001a2e7  nop     dword ptr [rax+rax+00h]
0x14001a2ec  mov     eax, ebx
0x14001a2ee  add     rsp, 40h
0x14001a2f2  pop     rbx
0x14001a2f3  retn
```
