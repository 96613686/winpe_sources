# SetPFsIdSequenceNumber

- ea: `0x18002d19c`
- end: `0x18002d1ef`
- name: `SetPFsIdSequenceNumber`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002cd8c`
- `0x18002d2b4`

## callees

- `0x18002d19c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18002d1e4`
- `ADVAPI32!RegSetValueExW` at `0x18002d1e4`
- `CLUSAPI!ClusterRegSetValue` at `0x18002d1c1`
- `CLUSAPI!ClusterRegSetValue` at `0x18002d1c1`

## string_xrefs

- `0x18002d1ba`: `PFsIdSequenceNumber`
- `0x18002d1da`: `PFsIdSequenceNumber`

## pseudocode

```c
LSTATUS __fastcall SetPFsIdSequenceNumber(HKEY a1, char a2, int a3)
{
  int Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  if ( a2 )
    return ClusterRegSetValue(a1, L"PFsIdSequenceNumber", 4u, (const BYTE *)&Data, 4u);
  else
    return RegSetValueExW(a1, L"PFsIdSequenceNumber", 0, 4u, (const BYTE *)&Data, 4u);
}

```

## disassembly

```asm
0x18002d19c  mov     [rsp+Data], r8d
0x18002d1a1  sub     rsp, 38h
0x18002d1a5  mov     eax, 4
0x18002d1aa  test    dl, dl
0x18002d1ac  jz      short loc_18002D1C9
0x18002d1ae  lea     r9, [rsp+38h+Data]; lpData
0x18002d1b3  mov     [rsp+38h+cbData], eax; cbData
0x18002d1b7  mov     r8d, eax; dwType
0x18002d1ba  lea     rdx, aPfsidsequencen; "PFsIdSequenceNumber"
0x18002d1c1  call    cs:__imp_ClusterRegSetValue
0x18002d1c7  jmp     short loc_18002D1EA
0x18002d1c9  lea     rdx, [rsp+38h+Data]
0x18002d1ce  mov     [rsp+38h+var_10], eax; cbData
0x18002d1d2  mov     qword ptr [rsp+38h+cbData], rdx; lpData
0x18002d1d7  mov     r9d, eax; dwType
0x18002d1da  lea     rdx, aPfsidsequencen; "PFsIdSequenceNumber"
0x18002d1e1  xor     r8d, r8d; Reserved
0x18002d1e4  call    cs:__imp_RegSetValueExW
0x18002d1ea  add     rsp, 38h
0x18002d1ee  retn
```
