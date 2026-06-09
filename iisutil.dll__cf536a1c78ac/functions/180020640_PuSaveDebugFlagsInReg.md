# PuSaveDebugFlagsInReg

- ea: `0x180020640`
- end: `0x180020683`
- name: `PuSaveDebugFlagsInReg`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180020640`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180020671`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180020671`

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
0x180020640  mov     [rsp+Data], edx
0x180020644  sub     rsp, 38h
0x180020648  test    rcx, rcx
0x18002064b  jnz     short loc_180020652
0x18002064d  lea     eax, [rcx+57h]
0x180020650  jmp     short loc_18002067D
0x180020652  mov     r9d, 4; dwType
0x180020658  lea     rax, [rsp+38h+Data]
0x18002065d  mov     [rsp+38h+cbData], r9d; cbData
0x180020662  lea     rdx, ValueName; "DebugFlags"
0x180020669  xor     r8d, r8d; Reserved
0x18002066c  mov     [rsp+38h+lpData], rax; lpData
0x180020671  call    cs:__imp_RegSetValueExA
0x180020678  nop     dword ptr [rax+rax+00h]
0x18002067d  add     rsp, 38h
0x180020681  retn
```
