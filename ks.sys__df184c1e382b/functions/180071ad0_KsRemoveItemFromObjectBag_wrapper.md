# KsRemoveItemFromObjectBag_wrapper

- ea: `0x180071ad0`
- end: `0x180071b3d`
- name: `KsRemoveItemFromObjectBag_wrapper`
- size: `109`
- prototype: `ULONG __fastcall(KSOBJECT_BAG ObjectBag, PVOID Item, BOOLEAN Free)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019cb0`
- `0x18004dbc0`
- `0x180071ad0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180071af2`
- `ntoskrnl!KeGetCurrentIrql` at `0x180071af2`

## string_xrefs

- `0x180071b09`: `KsRemoveItemFromObjectBag should only be called at IRQL == PASSIVE_LEVEL.`

## pseudocode

```c
ULONG __fastcall KsRemoveItemFromObjectBag_wrapper(KSOBJECT_BAG ObjectBag, PVOID Item, BOOLEAN Free)
{
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsRemoveItemFromObjectBag should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  return KsRemoveItemFromObjectBag(ObjectBag, Item, Free);
}

```

## disassembly

```asm
0x180071ad0  mov     [rsp+arg_0], rbx
0x180071ad5  mov     [rsp+arg_8], rsi
0x180071ada  push    rdi
0x180071adb  sub     rsp, 20h
0x180071adf  mov     eax, cs:KsXdvExtLevel
0x180071ae5  mov     bl, r8b
0x180071ae8  mov     rdi, rdx
0x180071aeb  mov     rsi, rcx
0x180071aee  test    al, 8
0x180071af0  jz      short loc_180071B1E
0x180071af2  call    cs:__imp_KeGetCurrentIrql
0x180071af9  nop     dword ptr [rax+rax+00h]
0x180071afe  test    al, al
0x180071b00  jz      short loc_180071B1E
0x180071b02  mov     rax, cs:KsVerifierUtilTable
0x180071b09  lea     rcx, aKsremoveitemfr; "KsRemoveItemFromObjectBag should only b"...
0x180071b10  mov     edx, 81009h
0x180071b15  mov     rax, [rax+60h]
0x180071b19  call    _guard_dispatch_icall
0x180071b1e  mov     r8b, bl; Free
0x180071b21  mov     rdx, rdi; Item
0x180071b24  mov     rcx, rsi; ObjectBag
0x180071b27  call    KsRemoveItemFromObjectBag
0x180071b2c  mov     rbx, [rsp+28h+arg_0]
0x180071b31  mov     rsi, [rsp+28h+arg_8]
0x180071b36  add     rsp, 20h
0x180071b3a  pop     rdi
0x180071b3b  retn
```
