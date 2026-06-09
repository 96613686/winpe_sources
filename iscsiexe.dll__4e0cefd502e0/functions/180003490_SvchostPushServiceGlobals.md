# SvchostPushServiceGlobals

- ea: `0x180003490`
- end: `0x180003498`
- name: `SvchostPushServiceGlobals`
- size: `8`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(__int64 a1)
{
  SvchostSharedGlobals = a1;
}

```

## disassembly

```asm
0x180003490  mov     cs:SvchostSharedGlobals, rcx
0x180003497  retn
```
