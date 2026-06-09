# KsProcessPinUpdate_wrapper

- ea: `0x180071690`
- end: `0x1800716de`
- name: `KsProcessPinUpdate_wrapper`
- size: `78`
- prototype: `BOOLEAN __fastcall(PKSPROCESSPIN ProcessPin)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180015680`
- `0x180019cb0`
- `0x180071690`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800716a3`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800716a3`

## string_xrefs

- `0x1800716ba`: `KsProcessPinUpdate should only be called at IRQL == PASSIVE_LEVEL.`

## pseudocode

```c
BOOLEAN __fastcall KsProcessPinUpdate_wrapper(PKSPROCESSPIN ProcessPin)
{
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsProcessPinUpdate should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  return KsProcessPinUpdate(ProcessPin);
}

```

## disassembly

```asm
0x180071690  push    rbx
0x180071692  sub     rsp, 20h
0x180071696  mov     eax, cs:KsXdvExtLevel
0x18007169c  mov     rbx, rcx
0x18007169f  test    al, 8
0x1800716a1  jz      short loc_1800716CF
0x1800716a3  call    cs:__imp_KeGetCurrentIrql
0x1800716aa  nop     dword ptr [rax+rax+00h]
0x1800716af  test    al, al
0x1800716b1  jz      short loc_1800716CF
0x1800716b3  mov     rax, cs:KsVerifierUtilTable
0x1800716ba  lea     rcx, aKsprocesspinup; "KsProcessPinUpdate should only be calle"...
0x1800716c1  mov     edx, 81009h
0x1800716c6  mov     rax, [rax+60h]
0x1800716ca  call    _guard_dispatch_icall
0x1800716cf  mov     rcx, rbx; ProcessPin
0x1800716d2  call    KsProcessPinUpdate
0x1800716d7  add     rsp, 20h
0x1800716db  pop     rbx
0x1800716dc  retn
```
