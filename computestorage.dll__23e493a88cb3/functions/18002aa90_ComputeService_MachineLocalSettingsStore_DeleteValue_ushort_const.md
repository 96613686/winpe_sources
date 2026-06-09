# ComputeService::MachineLocalSettingsStore::DeleteValue(ushort const *)

- ea: `0x18002aa90`
- end: `0x18002aacb`
- name: `?DeleteValue@MachineLocalSettingsStore@ComputeService@@UEAAXPEBG@Z`
- size: `59`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180012818`
- `0x18002aa90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002aa98`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002aa98`

## string_xrefs

- `0x18002aab6`: `onecore\vm\compute\management\shared\compute\machinelocalsettingsstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeService::MachineLocalSettingsStore::DeleteValue(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v2; // eax
  unsigned int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = RegDeleteValueW(this[1], a2);
  if ( (v2 & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x151,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\machinelocalsettingsstore.cpp",
      (const char *)v2,
      v3);
}

```

## disassembly

```asm
0x18002aa90  sub     rsp, 28h
0x18002aa94  mov     rcx, [rcx+8]; hKey
0x18002aa98  call    cs:__imp_RegDeleteValueW
0x18002aa9f  nop     dword ptr [rax+rax+00h]
0x18002aaa4  test    eax, 0FFFFFFFDh
0x18002aaa9  jnz     short loc_18002AAB1
0x18002aaab  add     rsp, 28h
0x18002aaaf  retn
0x18002aab1  mov     rcx, [rsp+28h]; this
0x18002aab6  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\management\\share"...
0x18002aabd  mov     r9d, eax; char *
0x18002aac0  mov     edx, 151h; void *
0x18002aac5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
