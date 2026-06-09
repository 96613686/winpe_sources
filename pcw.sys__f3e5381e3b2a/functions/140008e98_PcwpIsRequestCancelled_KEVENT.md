# PcwpIsRequestCancelled(_KEVENT *)

- ea: `0x140008e98`
- end: `0x140008edf`
- name: `?PcwpIsRequestCancelled@@YA_NPEAU_KEVENT@@@Z`
- size: `71`
- prototype: `bool __fastcall(PRKEVENT Event)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400083e4`
- `0x1400089cc`
- `0x140008b6c`
- `0x140008e08`
- `0x140009018`

## callees

- `0x140008e98`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x140008eaa`
- `ntoskrnl!PsIsThreadTerminating` at `0x140008eaa`
- `ntoskrnl!KeReadStateEvent` at `0x140008ec2`
- `ntoskrnl!KeReadStateEvent` at `0x140008ec2`

## pseudocode

```c
bool __fastcall PcwpIsRequestCancelled(PRKEVENT Event)
{
  return PsIsThreadTerminating(KeGetCurrentThread()) || Event && KeReadStateEvent(Event);
}

```

## disassembly

```asm
0x140008e98  push    rbx
0x140008e9a  sub     rsp, 20h
0x140008e9e  mov     rbx, rcx
0x140008ea1  mov     rcx, gs:188h; Thread
0x140008eaa  call    cs:__imp_PsIsThreadTerminating
0x140008eb1  nop     dword ptr [rax+rax+00h]
0x140008eb6  test    al, al
0x140008eb8  jnz     short loc_140008ED6
0x140008eba  test    rbx, rbx
0x140008ebd  jz      short loc_140008ED2
0x140008ebf  mov     rcx, rbx; Event
0x140008ec2  call    cs:__imp_KeReadStateEvent
0x140008ec9  nop     dword ptr [rax+rax+00h]
0x140008ece  test    eax, eax
0x140008ed0  jnz     short loc_140008ED6
0x140008ed2  xor     al, al
0x140008ed4  jmp     short loc_140008ED8
0x140008ed6  mov     al, 1
0x140008ed8  add     rsp, 20h
0x140008edc  pop     rbx
0x140008edd  retn
```
