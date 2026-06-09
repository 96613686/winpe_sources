# pSetupGetPredefinedKeyPath

- ea: `0x1800037cc`
- end: `0x180003817`
- name: `pSetupGetPredefinedKeyPath`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180003904`

## callees

- `0x1800037cc`

## string_xrefs

- `0x1800037d8`: `\REGISTRY\MACHINE`
- `0x1800037e9`: `\REGISTRY\MACHINE\SOFTWARE\Classes`
- `0x1800037fa`: `\REGISTRY\USER`
- `0x180003804`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Hardware Profiles\Current`

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
0x1800037cc  mov     rdx, rcx
0x1800037cf  cmp     rcx, 0FFFFFFFF80000002h
0x1800037d6  jnz     short loc_1800037E0
0x1800037d8  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE"
0x1800037df  retn
0x1800037e0  cmp     rdx, 0FFFFFFFF80000000h
0x1800037e7  jnz     short loc_1800037F1
0x1800037e9  lea     rax, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\SOFTWARE\\Classes"
0x1800037f0  retn
0x1800037f1  cmp     rdx, 0FFFFFFFF80000003h
0x1800037f8  jnz     short loc_180003802
0x1800037fa  lea     rax, aRegistryUser; "\\REGISTRY\\USER"
0x180003801  retn
0x180003802  xor     ecx, ecx
0x180003804  lea     rax, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x18000380b  cmp     rdx, 0FFFFFFFF80000005h
0x180003812  cmovnz  rax, rcx
0x180003816  retn
```
