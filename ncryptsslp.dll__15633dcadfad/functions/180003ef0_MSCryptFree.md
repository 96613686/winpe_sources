# MSCryptFree

- ea: `0x180003ef0`
- end: `0x180003f09`
- name: `MSCryptFree`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `53`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x180001670`
- `0x180001f00`
- `0x180001fd0`
- `0x1800022a0`
- `0x180003050`
- `0x1800037a0`
- `0x180004570`
- `0x180005240`
- `0x1800058e0`
- `0x180006070`
- `0x180006904`
- `0x180006b60`
- `0x180007990`
- `0x1800097f0`
- `0x18000ae00`
- `0x18000d2b0`
- `0x18000dea0`
- `0x1800105e0`
- `0x1800113a0`
- `0x180011f10`
- `0x1800126f0`
- `0x180012838`
- `0x180012978`
- `0x180012fa4`
- `0x180013740`
- `0x180013e6c`
- `0x180013f08`
- `0x180014024`
- `0x18001d648`
- `0x18001d6c0`
- `0x18001d8e8`
- `0x18001de24`
- `0x18001e0dc`
- `0x18001e8c0`
- `0x180020718`
- `0x180021efc`
- `0x180022164`
- `0x180022608`
- `0x180022e04`
- `0x180022fa8`
- `0x180023234`
- `0x1800234b0`
- `0x180023ac4`
- `0x180023dbc`
- `0x180023e34`
- `0x1800240f0`
- `0x18002415c`
- `0x180024190`
- `0x1800245d8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180003f02`

## pseudocode

```c
BOOLEAN __fastcall MSCryptFree(void *a1)
{
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180003ef0  mov     rax, gs:60h
0x180003ef9  mov     r8, rcx
0x180003efc  xor     edx, edx
0x180003efe  mov     rcx, [rax+30h]
0x180003f02  jmp     cs:__imp_RtlFreeHeap
```
