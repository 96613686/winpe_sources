# MSCryptFree

- ea: `0x18000a770`
- end: `0x18000a789`
- name: `MSCryptFree`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `52`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001e78`
- `0x180006730`
- `0x180007120`
- `0x180007ae0`
- `0x180007b80`
- `0x180007ca0`
- `0x180008a90`
- `0x180008c1c`
- `0x180008cfc`
- `0x180009830`
- `0x180009aa0`
- `0x180009ecc`
- `0x18000a7e0`
- `0x18000aa90`
- `0x18000acd0`
- `0x18000adc0`
- `0x18000b290`
- `0x18000b4f0`
- `0x18000b6c0`
- `0x18000c270`
- `0x18000c700`
- `0x18000cb50`
- `0x18000d100`
- `0x18000e170`
- `0x18000e3b0`
- `0x18000e640`
- `0x18000ed40`
- `0x18000f290`
- `0x18000f5c0`
- `0x1800102c0`
- `0x180010c90`
- `0x180011470`
- `0x1800116b0`
- `0x180011950`
- `0x180012580`
- `0x180012bb0`
- `0x180013190`
- `0x180013d38`
- `0x1800146e0`
- `0x1800147a0`
- `0x180015cd0`
- `0x180016350`
- `0x1800175f0`
- `0x180017990`
- `0x180019be0`
- `0x18001a8e0`
- `0x18001ab20`
- `0x18001ac70`
- `0x18001aef0`
- `0x18001b140`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000a782`

## pseudocode

```c
BOOLEAN __fastcall MSCryptFree(void *a1)
{
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x18000a770  mov     rax, gs:60h
0x18000a779  mov     r8, rcx
0x18000a77c  xor     edx, edx
0x18000a77e  mov     rcx, [rax+30h]
0x18000a782  jmp     cs:__imp_RtlFreeHeap
```
