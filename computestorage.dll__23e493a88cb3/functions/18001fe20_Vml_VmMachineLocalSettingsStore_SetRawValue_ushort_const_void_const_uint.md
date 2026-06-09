# Vml::VmMachineLocalSettingsStore::SetRawValue(ushort const *,void const *,uint)

- ea: `0x18001fe20`
- end: `0x18001fe6b`
- name: `?SetRawValue@VmMachineLocalSettingsStore@Vml@@UEAAXPEBGPEBXI@Z`
- size: `75`
- prototype: `void(Vml::VmMachineLocalSettingsStore *__hidden this, const unsigned __int16 *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012818`
- `0x18001fe20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fe3b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fe3b`

## string_xrefs

- `0x18001fe56`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
void __fastcall Vml::VmMachineLocalSettingsStore::SetRawValue(
        HKEY *this,
        const unsigned __int16 *a2,
        const BYTE *a3,
        DWORD cbData)
{
  unsigned int v4; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = RegSetValueExW(this[1], a2, 0, 3u, a3, cbData);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x353,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)v4,
      lpData);
}

```

## disassembly

```asm
0x18001fe20  sub     rsp, 38h
0x18001fe24  mov     rcx, [rcx+8]; hKey
0x18001fe28  mov     [rsp+38h+cbData], r9d; cbData
0x18001fe2d  mov     r9d, 3; dwType
0x18001fe33  mov     [rsp+38h+lpData], r8; unsigned int
0x18001fe38  xor     r8d, r8d; Reserved
0x18001fe3b  call    cs:__imp_RegSetValueExW
0x18001fe42  nop     dword ptr [rax+rax+00h]
0x18001fe47  test    eax, eax
0x18001fe49  jnz     short loc_18001FE51
0x18001fe4b  add     rsp, 38h
0x18001fe4f  retn
0x18001fe51  mov     rcx, [rsp+38h]; this
0x18001fe56  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x18001fe5d  mov     r9d, eax; char *
0x18001fe60  mov     edx, 353h; void *
0x18001fe65  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
