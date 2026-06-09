# operator new(unsigned __int64,unsigned __int64)

- ea: `0x140003188`
- end: `0x1400031ad`
- name: `??2@YAPEAX_K0@Z`
- size: `37`
- prototype: `void *__fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `37`
- callee_count: `0`
- tags: ``

## callers

- `0x140002160`
- `0x140004050`
- `0x140004120`
- `0x140004438`
- `0x140005000`
- `0x140011a2c`
- `0x140011df0`
- `0x140012330`
- `0x140015bc0`
- `0x140015c50`
- `0x140016130`
- `0x1400169f0`
- `0x140017544`
- `0x1400176bc`
- `0x140018ea4`
- `0x14001af78`
- `0x14001b608`
- `0x14001b808`
- `0x14001dd70`
- `0x14001e10c`
- `0x14001e3f0`
- `0x14001ea80`
- `0x14001eeb0`
- `0x14001f900`
- `0x140023cf0`
- `0x140024830`
- `0x140025000`
- `0x140026f90`
- `0x140029228`
- `0x1400294a0`
- `0x14002a1e0`
- `0x14002a9c0`
- `0x14002b088`
- `0x14002b120`
- `0x14002c54c`
- `0x14002ce44`
- `0x14002e078`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000319b`
- `ntoskrnl!ExAllocatePool2` at `0x14000319b`

## pseudocode

```c
__int64 __fastcall operator new(__int64 a1, __int64 a2)
{
  return ExAllocatePool2(a2, a1, 1917088324);
}

```

## disassembly

```asm
0x140003188  sub     rsp, 28h
0x14000318c  mov     rax, rdx
0x14000318f  mov     r8d, 72447244h
0x140003195  mov     rdx, rcx
0x140003198  mov     rcx, rax
0x14000319b  call    cs:__imp_ExAllocatePool2
0x1400031a2  nop     dword ptr [rax+rax+00h]
0x1400031a7  add     rsp, 28h
0x1400031ab  retn
```
