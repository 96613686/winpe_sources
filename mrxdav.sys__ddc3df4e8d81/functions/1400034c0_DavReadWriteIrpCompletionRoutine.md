# DavReadWriteIrpCompletionRoutine

- ea: `0x1400034c0`
- end: `0x1400034ec`
- name: `DavReadWriteIrpCompletionRoutine`
- size: `44`
- prototype: `__int64 __fastcall(__int64, __int64, struct _KEVENT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400034c0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400034d5`
- `ntoskrnl!KeSetEvent` at `0x1400034d5`

## pseudocode

```c
__int64 __fastcall DavReadWriteIrpCompletionRoutine(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  if ( *(_BYTE *)(a2 + 65) )
    KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400034c0  sub     rsp, 28h
0x1400034c4  cmp     byte ptr [rdx+41h], 0
0x1400034c8  mov     rax, r8
0x1400034cb  jz      short loc_1400034E1
0x1400034cd  xor     r8d, r8d; Wait
0x1400034d0  xor     edx, edx; Increment
0x1400034d2  mov     rcx, rax; Event
0x1400034d5  call    cs:__imp_KeSetEvent
0x1400034dc  nop     dword ptr [rax+rax+00h]
0x1400034e1  mov     eax, 0C0000016h
0x1400034e6  add     rsp, 28h
0x1400034ea  retn
```
