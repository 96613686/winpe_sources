# DfscGetDomainCache

- ea: `0x14001c2e4`
- end: `0x14001c2fa`
- name: `DfscGetDomainCache`
- size: `22`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140015050`
- `0x1400172ec`
- `0x14001c270`
- `0x140022cd8`
- `0x1400282f4`

## callees

- `0x14001c2e4`

## pseudocode

```c
__int64 __fastcall DfscGetDomainCache(__int64 a1)
{
  if ( a1 )
    return *(_QWORD *)(a1 + 128);
  else
    return *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount;
}

```

## disassembly

```asm
0x14001c2e4  test    rcx, rcx
0x14001c2e7  jnz     short loc_14001C2F2
0x14001c2e9  mov     rax, qword ptr cs:WPP_MAIN_CB.ActiveThreadCount
0x14001c2f0  retn
0x14001c2f2  mov     rax, [rcx+80h]
0x14001c2f9  retn
```
