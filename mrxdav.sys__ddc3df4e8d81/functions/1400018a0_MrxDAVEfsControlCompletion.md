# MrxDAVEfsControlCompletion

- ea: `0x1400018a0`
- end: `0x1400018cb`
- name: `MrxDAVEfsControlCompletion`
- size: `43`
- prototype: `__int64 __fastcall(__int64, __int64, struct _KEVENT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400018a0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400018b4`
- `ntoskrnl!KeSetEvent` at `0x1400018b4`

## pseudocode

```c
__int64 __fastcall MrxDAVEfsControlCompletion(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  if ( a3 )
    KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400018a0  sub     rsp, 28h
0x1400018a4  mov     rax, r8
0x1400018a7  test    r8, r8
0x1400018aa  jz      short loc_1400018C0
0x1400018ac  xor     r8d, r8d; Wait
0x1400018af  xor     edx, edx; Increment
0x1400018b1  mov     rcx, rax; Event
0x1400018b4  call    cs:__imp_KeSetEvent
0x1400018bb  nop     dword ptr [rax+rax+00h]
0x1400018c0  mov     eax, 0C0000016h
0x1400018c5  add     rsp, 28h
0x1400018c9  retn
```
