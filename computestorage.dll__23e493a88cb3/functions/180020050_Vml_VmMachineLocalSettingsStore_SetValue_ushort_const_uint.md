# Vml::VmMachineLocalSettingsStore::SetValue(ushort const *,uint)

- ea: `0x180020050`
- end: `0x1800200c0`
- name: `?SetValue@VmMachineLocalSettingsStore@Vml@@UEAAXPEBGI@Z`
- size: `112`
- prototype: `void __fastcall(Vml::VmMachineLocalSettingsStore *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002690`
- `0x180012818`
- `0x180020050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020083`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020083`

## string_xrefs

- `0x1800200ab`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
void __fastcall Vml::VmMachineLocalSettingsStore::SetValue(
        Vml::VmMachineLocalSettingsStore *this,
        const unsigned __int16 *a2,
        int a3)
{
  HKEY v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // [rsp+20h] [rbp-28h]
  BYTE v6[8]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = (HKEY)*((_QWORD *)this + 1);
  *(_DWORD *)v6 = a3;
  v4 = RegSetValueExW(v3, a2, 0, 4u, v6, 4u);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x353,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)v4,
      v5);
}

```

## disassembly

```asm
0x180020050  mov     r11, rsp
0x180020053  sub     rsp, 48h
0x180020057  mov     rax, cs:__security_cookie
0x18002005e  xor     rax, rsp
0x180020061  mov     [rsp+48h+var_10], rax
0x180020066  mov     rcx, [rcx+8]; hKey
0x18002006a  lea     rax, [r11-18h]
0x18002006e  mov     r9d, 4; dwType
0x180020074  mov     [r11-18h], r8d
0x180020078  mov     [r11-20h], r9d
0x18002007c  xor     r8d, r8d; Reserved
0x18002007f  mov     [r11-28h], rax
0x180020083  call    cs:__imp_RegSetValueExW
0x18002008a  nop     dword ptr [rax+rax+00h]
0x18002008f  test    eax, eax
0x180020091  jnz     short loc_1800200A6
0x180020093  mov     rcx, [rsp+48h+var_10]
0x180020098  xor     rcx, rsp; StackCookie
0x18002009b  call    __security_check_cookie
0x1800200a0  add     rsp, 48h
0x1800200a4  retn
0x1800200a6  mov     rcx, [rsp+48h]; this
0x1800200ab  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x1800200b2  mov     r9d, eax; char *
0x1800200b5  mov     edx, 353h; void *
0x1800200ba  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
