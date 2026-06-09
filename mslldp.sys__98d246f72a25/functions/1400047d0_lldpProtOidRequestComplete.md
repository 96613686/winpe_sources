# lldpProtOidRequestComplete

- ea: `0x1400047d0`
- end: `0x1400047f9`
- name: `lldpProtOidRequestComplete`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400047e7`
- `ntoskrnl!KeSetEvent` at `0x1400047e7`

## pseudocode

```c
LONG __fastcall lldpProtOidRequestComplete(__int64 a1, __int64 a2, int a3)
{
  struct _KEVENT *v3; // rcx

  v3 = *(struct _KEVENT **)(a2 + 224);
  *(_DWORD *)(a2 + 220) = a3;
  return KeSetEvent(v3, 0, 0);
}

```

## disassembly

```asm
0x1400047d0  sub     rsp, 28h
0x1400047d4  mov     rcx, [rdx+0E0h]; Event
0x1400047db  mov     [rdx+0DCh], r8d
0x1400047e2  xor     r8d, r8d; Wait
0x1400047e5  xor     edx, edx; Increment
0x1400047e7  call    cs:__imp_KeSetEvent
0x1400047ee  nop     dword ptr [rax+rax+00h]
0x1400047f3  add     rsp, 28h
0x1400047f7  retn
```
