# SetPFsTerminalNodeKeyValue

- ea: `0x18002d258`
- end: `0x18002d2ab`
- name: `SetPFsTerminalNodeKeyValue`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002bb5c`
- `0x18002cf98`

## callees

- `0x18002d258`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18002d2a0`
- `ADVAPI32!RegSetValueExW` at `0x18002d2a0`
- `CLUSAPI!ClusterRegSetValue` at `0x18002d27d`
- `CLUSAPI!ClusterRegSetValue` at `0x18002d27d`

## pseudocode

```c
LSTATUS __fastcall SetPFsTerminalNodeKeyValue(HKEY a1, char a2, int a3)
{
  int Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  if ( a2 )
    return ClusterRegSetValue(a1, L"TerminalNode", 4u, (const BYTE *)&Data, 4u);
  else
    return RegSetValueExW(a1, L"TerminalNode", 0, 4u, (const BYTE *)&Data, 4u);
}

```

## disassembly

```asm
0x18002d258  mov     [rsp+Data], r8d
0x18002d25d  sub     rsp, 38h
0x18002d261  mov     eax, 4
0x18002d266  test    dl, dl
0x18002d268  jz      short loc_18002D285
0x18002d26a  lea     r9, [rsp+38h+Data]; lpData
0x18002d26f  mov     [rsp+38h+cbData], eax; cbData
0x18002d273  mov     r8d, eax; dwType
0x18002d276  lea     rdx, aTerminalnode; "TerminalNode"
0x18002d27d  call    cs:__imp_ClusterRegSetValue
0x18002d283  jmp     short loc_18002D2A6
0x18002d285  lea     rdx, [rsp+38h+Data]
0x18002d28a  mov     [rsp+38h+var_10], eax; cbData
0x18002d28e  mov     qword ptr [rsp+38h+cbData], rdx; lpData
0x18002d293  mov     r9d, eax; dwType
0x18002d296  lea     rdx, aTerminalnode; "TerminalNode"
0x18002d29d  xor     r8d, r8d; Reserved
0x18002d2a0  call    cs:__imp_RegSetValueExW
0x18002d2a6  add     rsp, 38h
0x18002d2aa  retn
```
