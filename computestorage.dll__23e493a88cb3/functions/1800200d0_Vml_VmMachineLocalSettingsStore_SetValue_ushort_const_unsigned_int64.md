# Vml::VmMachineLocalSettingsStore::SetValue(ushort const *,unsigned __int64)

- ea: `0x1800200d0`
- end: `0x180020144`
- name: `?SetValue@VmMachineLocalSettingsStore@Vml@@UEAAXPEBG_K@Z`
- size: `116`
- prototype: `void __fastcall(Vml::VmMachineLocalSettingsStore *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002690`
- `0x180012818`
- `0x1800200d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020107`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020107`

## string_xrefs

- `0x18002012f`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
void __fastcall Vml::VmMachineLocalSettingsStore::SetValue(
        Vml::VmMachineLocalSettingsStore *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  HKEY v3; // rcx
  unsigned int v4; // eax
  unsigned int lpData; // [rsp+20h] [rbp-28h]
  BYTE Data[8]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = (HKEY)*((_QWORD *)this + 1);
  *(_QWORD *)Data = a3;
  v4 = RegSetValueExW(v3, a2, 0, 0xBu, Data, 8u);
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
0x1800200d0  sub     rsp, 48h
0x1800200d4  mov     rax, cs:__security_cookie
0x1800200db  xor     rax, rsp
0x1800200de  mov     [rsp+48h+var_10], rax
0x1800200e3  mov     rcx, [rcx+8]; hKey
0x1800200e7  lea     rax, [rsp+48h+Data]
0x1800200ec  mov     qword ptr [rsp+48h+Data], r8
0x1800200f1  mov     r9d, 0Bh; dwType
0x1800200f7  xor     r8d, r8d; Reserved
0x1800200fa  mov     [rsp+48h+cbData], 8; cbData
0x180020102  mov     [rsp+48h+lpData], rax; unsigned int
0x180020107  call    cs:__imp_RegSetValueExW
0x18002010e  nop     dword ptr [rax+rax+00h]
0x180020113  test    eax, eax
0x180020115  jnz     short loc_18002012A
0x180020117  mov     rcx, [rsp+48h+var_10]
0x18002011c  xor     rcx, rsp; StackCookie
0x18002011f  call    __security_check_cookie
0x180020124  add     rsp, 48h
0x180020128  retn
0x18002012a  mov     rcx, [rsp+48h]; this
0x18002012f  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x180020136  mov     r9d, eax; char *
0x180020139  mov     edx, 353h; void *
0x18002013e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
