# _dynamic_initializer_for__c_szDCRegistry__

- ea: `0x1400030d0`
- end: `0x140003101`
- name: `_dynamic_initializer_for__c_szDCRegistry__`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1400030d4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400030d4`

## string_xrefs

- `0x1400030e9`: `OSData\SOFTWARE\Microsoft\DeclaredConfiguration\HostOS\Config`
- `0x1400030e2`: `SOFTWARE\Microsoft\DeclaredConfiguration\HostOS\Config`

## pseudocode

```c
__int64 __fastcall dynamic_initializer_for__c_szDCRegistry__(__int64 a1)
{
  __int64 result; // rax
  const WCHAR *v2; // rcx

  result = RtlIsStateSeparationEnabled(a1);
  v2 = L"OSData\\SOFTWARE\\Microsoft\\DeclaredConfiguration\\HostOS\\Config";
  if ( !(_BYTE)result )
    v2 = L"SOFTWARE\\Microsoft\\DeclaredConfiguration\\HostOS\\Config";
  lpSubKey = v2;
  return result;
}

```

## disassembly

```asm
0x1400030d0  sub     rsp, 28h
0x1400030d4  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400030db  nop     dword ptr [rax+rax+00h]
0x1400030e0  test    al, al
0x1400030e2  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\DeclaredConfigurat"...
0x1400030e9  lea     rcx, aOsdataSoftware_0; "OSData\\SOFTWARE\\Microsoft\\DeclaredCo"...
0x1400030f0  cmovz   rcx, rdx
0x1400030f4  mov     cs:lpSubKey, rcx
0x1400030fb  add     rsp, 28h
0x1400030ff  retn
```
