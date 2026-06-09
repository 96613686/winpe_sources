# PuSaveDebugFlagsInReg

- ea: `0x18001f3b0`
- end: `0x18001f3ec`
- name: `PuSaveDebugFlagsInReg`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18001f3b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18001f3e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18001f3e1`

## pseudocode

```c
LSTATUS __fastcall PuSaveDebugFlagsInReg(HKEY a1, int a2)
{
  int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = a2;
  if ( a1 )
    return RegSetValueExA(a1, "DebugFlags", 0, 4u, (const BYTE *)&Data, 4u);
  else
    return 87;
}

```

## disassembly

```asm
0x18001f3b0  mov     [rsp+Data], edx
0x18001f3b4  sub     rsp, 38h
0x18001f3b8  test    rcx, rcx
0x18001f3bb  jnz     short loc_18001F3C2
0x18001f3bd  lea     eax, [rcx+57h]
0x18001f3c0  jmp     short loc_18001F3E7
0x18001f3c2  mov     r9d, 4; dwType
0x18001f3c8  lea     rax, [rsp+38h+Data]
0x18001f3cd  mov     [rsp+38h+cbData], r9d; cbData
0x18001f3d2  lea     rdx, ValueName; "DebugFlags"
0x18001f3d9  xor     r8d, r8d; Reserved
0x18001f3dc  mov     [rsp+38h+lpData], rax; lpData
0x18001f3e1  call    cs:__imp_RegSetValueExA
0x18001f3e7  add     rsp, 38h
0x18001f3eb  retn
```
