# Etw_Trace0

- ea: `0x18000ab88`
- end: `0x18000abb2`
- name: `Etw_Trace0`
- size: `42`
- prototype: ``
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ae98`
- `0x18000aee8`
- `0x18000af38`
- `0x18000b1b8`
- `0x18000b208`
- `0x18000b518`
- `0x180019e20`
- `0x18001a720`
- `0x18001ca60`
- `0x18001d2b0`
- `0x180024fd0`
- `0x180028b00`
- `0x1800292cc`
- `0x1800297b0`
- `0x180029840`
- `0x1800298c0`
- `0x180029a00`
- `0x18002a5d0`
- `0x18002a9c0`
- `0x18002add0`
- `0x18002b210`
- `0x18002daac`

## callees

- `0x18000babc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000abab`

## pseudocode

```c
ULONG __fastcall Etw_Trace0(const EVENT_DESCRIPTOR *a1, __int64 a2, __int64 a3)
{
  EtwInitProvider(a1, a2, a3);
  return EventWrite(RegistrationHandle, a1, 0, 0);
}

```

## disassembly

```asm
0x18000ab88  push    rbx
0x18000ab8a  sub     rsp, 20h
0x18000ab8e  mov     rbx, rcx
0x18000ab91  call    EtwInitProvider
0x18000ab96  mov     rcx, cs:RegistrationHandle
0x18000ab9d  xor     r9d, r9d
0x18000aba0  xor     r8d, r8d
0x18000aba3  mov     rdx, rbx
0x18000aba6  add     rsp, 20h
0x18000abaa  pop     rbx
0x18000abab  jmp     cs:__imp_EventWrite
```
