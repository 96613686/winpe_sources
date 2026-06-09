# Vml::VmMachineLocalSettingsStore::SetValue(ushort const *,ushort const *)

- ea: `0x18001ff30`
- end: `0x18001ff94`
- name: `?SetValue@VmMachineLocalSettingsStore@Vml@@UEAAXPEBG0@Z`
- size: `100`
- prototype: `void(Vml::VmMachineLocalSettingsStore *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012818`
- `0x18001ff30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ff63`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ff63`

## string_xrefs

- `0x18001ff7f`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
void __fastcall Vml::VmMachineLocalSettingsStore::SetValue(HKEY *this, const unsigned __int16 *a2, const BYTE *a3)
{
  __int64 v3; // rax
  unsigned int v4; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&a3[2 * v3] );
  v4 = RegSetValueExW(this[1], a2, 0, 1u, a3, 2 * v3 + 2);
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
0x18001ff30  push    rbx
0x18001ff32  sub     rsp, 30h
0x18001ff36  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ff3a  xor     ebx, ebx
0x18001ff3c  inc     rax
0x18001ff3f  cmp     [r8+rax*2], bx
0x18001ff44  jnz     short loc_18001FF3C
0x18001ff46  mov     rcx, [rcx+8]; hKey
0x18001ff4a  lea     eax, ds:2[rax*2]
0x18001ff51  mov     [rsp+38h+cbData], eax; cbData
0x18001ff55  mov     r9d, 1; dwType
0x18001ff5b  mov     [rsp+38h+lpData], r8; unsigned int
0x18001ff60  xor     r8d, r8d; Reserved
0x18001ff63  call    cs:__imp_RegSetValueExW
0x18001ff6a  nop     dword ptr [rax+rax+00h]
0x18001ff6f  test    eax, eax
0x18001ff71  jnz     short loc_18001FF7A
0x18001ff73  add     rsp, 30h
0x18001ff77  pop     rbx
0x18001ff78  retn
0x18001ff7a  mov     rcx, [rsp+38h]; this
0x18001ff7f  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x18001ff86  mov     r9d, eax; char *
0x18001ff89  mov     edx, 353h; void *
0x18001ff8e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
