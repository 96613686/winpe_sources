# KsCopyObjectBagItems_wrapper

- ea: `0x18006f630`
- end: `0x18006f68d`
- name: `KsCopyObjectBagItems_wrapper`
- size: `93`
- prototype: `__int64 __fastcall(KSOBJECT_BAG ObjectBagDestination, KSOBJECT_BAG ObjectBagSource)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019c60`
- `0x18003d950`
- `0x18006f630`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18006f64a`
- `ntoskrnl!KeGetCurrentIrql` at `0x18006f64a`

## string_xrefs

- `0x18006f661`: `KsCopyObjectBagItems should only be called at IRQL == PASSIVE_LEVEL.`

## pseudocode

```c
NTSTATUS __fastcall KsCopyObjectBagItems_wrapper(KSOBJECT_BAG ObjectBagDestination, KSOBJECT_BAG ObjectBagSource)
{
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsCopyObjectBagItems should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  return KsCopyObjectBagItems(ObjectBagDestination, ObjectBagSource);
}

```

## disassembly

```asm
0x18006f630  mov     [rsp+arg_0], rbx
0x18006f635  push    rdi
0x18006f636  sub     rsp, 20h
0x18006f63a  mov     eax, cs:KsXdvExtLevel
0x18006f640  mov     rbx, rdx
0x18006f643  mov     rdi, rcx
0x18006f646  test    al, 8
0x18006f648  jz      short loc_18006F676
0x18006f64a  call    cs:__imp_KeGetCurrentIrql
0x18006f651  nop     dword ptr [rax+rax+00h]
0x18006f656  test    al, al
0x18006f658  jz      short loc_18006F676
0x18006f65a  mov     rax, cs:KsVerifierUtilTable
0x18006f661  lea     rcx, aKscopyobjectba; "KsCopyObjectBagItems should only be cal"...
0x18006f668  mov     edx, 81009h
0x18006f66d  mov     rax, [rax+60h]
0x18006f671  call    _guard_dispatch_icall
0x18006f676  mov     rdx, rbx; ObjectBagSource
0x18006f679  mov     rcx, rdi; ObjectBagDestination
0x18006f67c  call    KsCopyObjectBagItems
0x18006f681  mov     rbx, [rsp+28h+arg_0]
0x18006f686  add     rsp, 20h
0x18006f68a  pop     rdi
0x18006f68b  retn
```
