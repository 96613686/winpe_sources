# NcaRegCloseKey

- ea: `0x1800037b0`
- end: `0x1800037c2`
- name: `NcaRegCloseKey`
- size: `18`
- prototype: `LSTATUS __fastcall(HKEY)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005770`
- `0x18000ff30`
- `0x180014058`
- `0x180014188`
- `0x180014d20`
- `0x180019f50`
- `0x18001a564`
- `0x18001a654`
- `0x18001a95c`
- `0x18001ab04`
- `0x18001ac78`

## callees

- `0x1800037b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037b5`

## pseudocode

```c
LSTATUS __fastcall NcaRegCloseKey(HKEY a1)
{
  LSTATUS result; // eax

  if ( a1 )
    return RegCloseKey(a1);
  return result;
}

```

## disassembly

```asm
0x1800037b0  test    rcx, rcx
0x1800037b3  jz      short locret_1800037C1
0x1800037b5  jmp     cs:__imp_RegCloseKey
0x1800037c1  retn
```
