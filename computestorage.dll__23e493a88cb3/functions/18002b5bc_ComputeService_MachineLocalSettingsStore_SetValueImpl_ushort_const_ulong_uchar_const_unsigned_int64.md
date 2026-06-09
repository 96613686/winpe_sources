# ComputeService::MachineLocalSettingsStore::SetValueImpl(ushort const *,ulong,uchar * const,unsigned __int64)

- ea: `0x18002b5bc`
- end: `0x18002b607`
- name: `?SetValueImpl@MachineLocalSettingsStore@ComputeService@@AEBAXPEBGKQEAE_K@Z`
- size: `75`
- prototype: `void(ComputeService::MachineLocalSettingsStore *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int8 *const, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b340`
- `0x18002b370`
- `0x18002b3b0`
- `0x18002b520`
- `0x18002b570`

## callees

- `0x180012818`
- `0x18002b5bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b5d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b5d7`

## string_xrefs

- `0x18002b5f2`: `onecore\vm\compute\management\shared\compute\machinelocalsettingsstore.cpp`

## pseudocode

```c
void __fastcall ComputeService::MachineLocalSettingsStore::SetValueImpl(
        HKEY *this,
        const unsigned __int16 *a2,
        DWORD a3,
        unsigned __int8 *const a4,
        unsigned __int64 cbData)
{
  unsigned int v5; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = RegSetValueExW(this[1], a2, 0, a3, a4, cbData);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1C0,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\machinelocalsettingsstore.cpp",
      (const char *)v5,
      lpData);
}

```

## disassembly

```asm
0x18002b5bc  sub     rsp, 38h
0x18002b5c0  mov     eax, [rsp+38h+arg_20]
0x18002b5c4  mov     rcx, [rcx+8]; hKey
0x18002b5c8  mov     [rsp+38h+cbData], eax; cbData
0x18002b5cc  mov     [rsp+38h+lpData], r9; unsigned int
0x18002b5d1  mov     r9d, r8d; dwType
0x18002b5d4  xor     r8d, r8d; Reserved
0x18002b5d7  call    cs:__imp_RegSetValueExW
0x18002b5de  nop     dword ptr [rax+rax+00h]
0x18002b5e3  test    eax, eax
0x18002b5e5  jnz     short loc_18002B5ED
0x18002b5e7  add     rsp, 38h
0x18002b5eb  retn
0x18002b5ed  mov     rcx, [rsp+38h]; this
0x18002b5f2  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\management\\share"...
0x18002b5f9  mov     r9d, eax; char *
0x18002b5fc  mov     edx, 1C0h; void *
0x18002b601  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
