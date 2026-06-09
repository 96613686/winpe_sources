# HIDSM_CompletingIdleCallbackDuringTransientPowerDown

- ea: `0x180018080`
- end: `0x1800180ae`
- name: `HIDSM_CompletingIdleCallbackDuringTransientPowerDown`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x180018097`
- `ntoskrnl!KeSetEvent` at `0x180018097`

## pseudocode

```c
__int64 __fastcall HIDSM_CompletingIdleCallbackDuringTransientPowerDown(__int64 a1)
{
  KeSetEvent((PRKEVENT)(*(_QWORD *)(a1 + 960) + 440LL), 0, 0);
  return 2013;
}

```

## disassembly

```asm
0x180018080  sub     rsp, 28h
0x180018084  mov     rcx, [rcx+3C0h]
0x18001808b  xor     r8d, r8d; Wait
0x18001808e  add     rcx, 1B8h; Event
0x180018095  xor     edx, edx; Increment
0x180018097  call    cs:__imp_KeSetEvent
0x18001809e  nop     dword ptr [rax+rax+00h]
0x1800180a3  mov     eax, 7DDh
0x1800180a8  add     rsp, 28h
0x1800180ac  retn
```
