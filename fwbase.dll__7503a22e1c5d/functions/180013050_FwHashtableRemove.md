# FwHashtableRemove

- ea: `0x180013050`
- end: `0x18001306b`
- name: `FwHashtableRemove`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012f90`
- `0x180014130`

## callees

- `0x180013050`
- `0x18002f43c`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180013057`
- `ntdll!RtlRemoveEntryHashTable` at `0x180013057`

## pseudocode

```c
__int64 __fastcall FwHashtableRemove(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = RtlRemoveEntryHashTable(a1, a2, 0);
  if ( !(_BYTE)result )
    return MicrosoftTelemetryAssertTriggeredNoArgs();
  return result;
}

```

## disassembly

```asm
0x180013050  sub     rsp, 28h
0x180013054  xor     r8d, r8d
0x180013057  call    cs:__imp_RtlRemoveEntryHashTable
0x18001305d  test    al, al
0x18001305f  jnz     short loc_180013066
0x180013061  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "success")
0x180013066  add     rsp, 28h
0x18001306a  retn
```
