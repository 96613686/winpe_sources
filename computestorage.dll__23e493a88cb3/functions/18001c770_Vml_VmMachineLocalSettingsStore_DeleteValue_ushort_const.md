# Vml::VmMachineLocalSettingsStore::DeleteValue(ushort const *)

- ea: `0x18001c770`
- end: `0x18001c7ab`
- name: `?DeleteValue@VmMachineLocalSettingsStore@Vml@@UEAAXPEBG@Z`
- size: `59`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012818`
- `0x18001c770`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001c778`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001c778`

## string_xrefs

- `0x18001c796`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Vml::VmMachineLocalSettingsStore::DeleteValue(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v2; // eax
  unsigned int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = RegDeleteValueW(this[1], a2);
  if ( (v2 & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x3D2,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)v2,
      v3);
}

```

## disassembly

```asm
0x18001c770  sub     rsp, 28h
0x18001c774  mov     rcx, [rcx+8]; hKey
0x18001c778  call    cs:__imp_RegDeleteValueW
0x18001c77f  nop     dword ptr [rax+rax+00h]
0x18001c784  test    eax, 0FFFFFFFDh
0x18001c789  jnz     short loc_18001C791
0x18001c78b  add     rsp, 28h
0x18001c78f  retn
0x18001c791  mov     rcx, [rsp+28h]; this
0x18001c796  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x18001c79d  mov     r9d, eax; char *
0x18001c7a0  mov     edx, 3D2h; void *
0x18001c7a5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
