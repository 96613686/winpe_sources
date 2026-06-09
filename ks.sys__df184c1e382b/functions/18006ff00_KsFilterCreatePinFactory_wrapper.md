# KsFilterCreatePinFactory_wrapper

- ea: `0x18006ff00`
- end: `0x18006ff6d`
- name: `KsFilterCreatePinFactory_wrapper`
- size: `109`
- prototype: `NTSTATUS __fastcall(PKSFILTER Filter, KSPIN_DESCRIPTOR_EX *PinDescriptor, PULONG PinID)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019cb0`
- `0x18003d290`
- `0x18006ff00`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18006ff22`
- `ntoskrnl!KeGetCurrentIrql` at `0x18006ff22`

## string_xrefs

- `0x18006ff39`: `KsFilterCreatePinFactory should only be called at IRQL == PASSIVE_LEVEL.`

## pseudocode

```c
NTSTATUS __fastcall KsFilterCreatePinFactory_wrapper(
        PKSFILTER Filter,
        KSPIN_DESCRIPTOR_EX *PinDescriptor,
        PULONG PinID)
{
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsFilterCreatePinFactory should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  return KsFilterCreatePinFactory(Filter, PinDescriptor, PinID);
}

```

## disassembly

```asm
0x18006ff00  mov     [rsp+arg_0], rbx
0x18006ff05  mov     [rsp+arg_8], rsi
0x18006ff0a  push    rdi
0x18006ff0b  sub     rsp, 20h
0x18006ff0f  mov     eax, cs:KsXdvExtLevel
0x18006ff15  mov     rbx, r8
0x18006ff18  mov     rdi, rdx
0x18006ff1b  mov     rsi, rcx
0x18006ff1e  test    al, 8
0x18006ff20  jz      short loc_18006FF4E
0x18006ff22  call    cs:__imp_KeGetCurrentIrql
0x18006ff29  nop     dword ptr [rax+rax+00h]
0x18006ff2e  test    al, al
0x18006ff30  jz      short loc_18006FF4E
0x18006ff32  mov     rax, cs:KsVerifierUtilTable
0x18006ff39  lea     rcx, aKsfiltercreate_0; "KsFilterCreatePinFactory should only be"...
0x18006ff40  mov     edx, 81009h
0x18006ff45  mov     rax, [rax+60h]
0x18006ff49  call    _guard_dispatch_icall
0x18006ff4e  mov     r8, rbx; PinID
0x18006ff51  mov     rdx, rdi; PinDescriptor
0x18006ff54  mov     rcx, rsi; Filter
0x18006ff57  call    KsFilterCreatePinFactory
0x18006ff5c  mov     rbx, [rsp+28h+arg_0]
0x18006ff61  mov     rsi, [rsp+28h+arg_8]
0x18006ff66  add     rsp, 20h
0x18006ff6a  pop     rdi
0x18006ff6b  retn
```
