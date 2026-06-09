# SetPFsIdSequenceNumberDuplicateCheck

- ea: `0x18002d1f8`
- end: `0x18002d252`
- name: `SetPFsIdSequenceNumberDuplicateCheck`
- size: `90`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002bd00`
- `0x18002cd8c`
- `0x18002d2b4`

## callees

- `0x18002d1f8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18002d247`
- `ADVAPI32!RegSetValueExW` at `0x18002d247`
- `CLUSAPI!ClusterRegSetValue` at `0x18002d224`
- `CLUSAPI!ClusterRegSetValue` at `0x18002d224`

## string_xrefs

- `0x18002d21d`: `PFsIdDuplicateCheck`
- `0x18002d23d`: `PFsIdDuplicateCheck`

## pseudocode

```c
LSTATUS __fastcall SetPFsIdSequenceNumberDuplicateCheck(HKEY a1, char a2, char a3)
{
  BOOL Data; // [rsp+48h] [rbp+10h] BYREF

  Data = a3 != 0;
  if ( a2 )
    return ClusterRegSetValue(a1, L"PFsIdDuplicateCheck", 4u, (const BYTE *)&Data, 4u);
  else
    return RegSetValueExW(a1, L"PFsIdDuplicateCheck", 0, 4u, (const BYTE *)&Data, 4u);
}

```

## disassembly

```asm
0x18002d1f8  sub     rsp, 38h
0x18002d1fc  xor     eax, eax
0x18002d1fe  test    r8b, r8b
0x18002d201  setnz   al
0x18002d204  mov     [rsp+38h+Data], eax
0x18002d208  mov     eax, 4
0x18002d20d  test    dl, dl
0x18002d20f  jz      short loc_18002D22C
0x18002d211  lea     r9, [rsp+38h+Data]; lpData
0x18002d216  mov     [rsp+38h+cbData], eax; cbData
0x18002d21a  mov     r8d, eax; dwType
0x18002d21d  lea     rdx, aPfsidduplicate; "PFsIdDuplicateCheck"
0x18002d224  call    cs:__imp_ClusterRegSetValue
0x18002d22a  jmp     short loc_18002D24D
0x18002d22c  lea     rdx, [rsp+38h+Data]
0x18002d231  mov     [rsp+38h+var_10], eax; cbData
0x18002d235  mov     qword ptr [rsp+38h+cbData], rdx; lpData
0x18002d23a  mov     r9d, eax; dwType
0x18002d23d  lea     rdx, aPfsidduplicate; "PFsIdDuplicateCheck"
0x18002d244  xor     r8d, r8d; Reserved
0x18002d247  call    cs:__imp_RegSetValueExW
0x18002d24d  add     rsp, 38h
0x18002d251  retn
```
