# pSetupGetPredefinedKeyPath

- ea: `0x180020e04`
- end: `0x180020e4f`
- name: `pSetupGetPredefinedKeyPath`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180020f58`

## callees

- `0x180020e04`

## string_xrefs

- `0x180020e10`: `\REGISTRY\MACHINE`
- `0x180020e21`: `\REGISTRY\MACHINE\SOFTWARE\Classes`
- `0x180020e32`: `\REGISTRY\USER`
- `0x180020e3c`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Hardware Profiles\Current`

## pseudocode

```c
const wchar_t *__fastcall pSetupGetPredefinedKeyPath(__int64 a1)
{
  const wchar_t *result; // rax

  switch ( a1 )
  {
    case -2147483646LL:
      return L"\\REGISTRY\\MACHINE";
    case -2147483648LL:
      return L"\\REGISTRY\\MACHINE\\SOFTWARE\\Classes";
    case -2147483645LL:
      return L"\\REGISTRY\\USER";
  }
  result = L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Hardware Profiles\\Current";
  if ( a1 != -2147483643 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180020e04  mov     rdx, rcx
0x180020e07  cmp     rcx, 0FFFFFFFF80000002h
0x180020e0e  jnz     short loc_180020E18
0x180020e10  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE"
0x180020e17  retn
0x180020e18  cmp     rdx, 0FFFFFFFF80000000h
0x180020e1f  jnz     short loc_180020E29
0x180020e21  lea     rax, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\SOFTWARE\\Classes"
0x180020e28  retn
0x180020e29  cmp     rdx, 0FFFFFFFF80000003h
0x180020e30  jnz     short loc_180020E3A
0x180020e32  lea     rax, aRegistryUser; "\\REGISTRY\\USER"
0x180020e39  retn
0x180020e3a  xor     ecx, ecx
0x180020e3c  lea     rax, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x180020e43  cmp     rdx, 0FFFFFFFF80000005h
0x180020e4a  cmovnz  rax, rcx
0x180020e4e  retn
```
