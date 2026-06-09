# PcwpIoctlNotify(PCW_IOCTL_INPUT *,void *,ulong *)

- ea: `0x14000a650`
- end: `0x14000a746`
- name: `?PcwpIoctlNotify@@YAJPEATPCW_IOCTL_INPUT@@PEAXPEAK@Z`
- size: `246`
- prototype: `__int64 __fastcall(unsigned __int64, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000a650`
- `0x14000c5e0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000a723`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a723`
- `ntoskrnl!ProbeForRead` at `0x14000a67f`
- `ntoskrnl!ProbeForRead` at `0x14000a67f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000a6c1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000a6c1`

## pseudocode

```c
__int64 __fastcall PcwpIoctlNotify(unsigned __int64 a1, void *a2, unsigned int *a3)
{
  unsigned int v6; // eax
  int v7; // edi
  PVOID v8; // rbx
  PVOID Object; // [rsp+60h] [rbp+8h] BYREF

  v6 = *(_DWORD *)(a1 + 24);
  if ( v6 )
    ProbeForRead(*(volatile void **)(a1 + 16), v6, 1u);
  Object = 0;
  v7 = ObReferenceObjectByHandle(*(HANDLE *)(a1 + 8), 2u, PcwObjectType, 1, &Object, 0);
  v8 = Object;
  if ( v7 >= 0 && *(_DWORD *)Object != 2 )
    v7 = -1073741788;
  if ( v7 >= 0 )
    v7 = PCW_NOTIFIER::SendNotification(
           (const struct _LUID *)Object,
           *(_DWORD *)(a1 + 28),
           (union _LARGE_INTEGER *)(a1 & -(__int64)(*(_BYTE *)(a1 + 32) != 0)),
           *(const void **)(a1 + 16),
           *(_DWORD *)(a1 + 24),
           a2,
           *a3,
           a3);
  if ( v8 )
    ObfDereferenceObject(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000a650  mov     [rsp+arg_8], rbx
0x14000a655  mov     [rsp+arg_10], rsi
0x14000a65a  push    rdi
0x14000a65b  push    r14
0x14000a65d  push    r15
0x14000a65f  sub     rsp, 40h
0x14000a663  mov     r14, r8
0x14000a666  mov     r15, rdx
0x14000a669  mov     rsi, rcx
0x14000a66c  mov     eax, [rcx+18h]
0x14000a66f  test    eax, eax
0x14000a671  jz      short loc_14000A692
0x14000a673  mov     edx, eax; Length
0x14000a675  mov     r8d, 1; Alignment
0x14000a67b  mov     rcx, [rcx+10h]; Address
0x14000a67f  call    cs:__imp_ProbeForRead
0x14000a686  nop     dword ptr [rax+rax+00h]
0x14000a68b  jmp     short loc_14000A692
0x14000a68d  jmp     loc_14000A731
0x14000a692  mov     r8, cs:?PcwObjectType@@3PEAU_OBJECT_TYPE@@EA; ObjectType
0x14000a699  mov     [rsp+58h+arg_0], 0
0x14000a6a2  mov     [rsp+58h+HandleInformation], 0; HandleInformation
0x14000a6ab  lea     rax, [rsp+58h+arg_0]
0x14000a6b0  mov     [rsp+58h+Object], rax; Object
0x14000a6b5  mov     r9b, 1; AccessMode
0x14000a6b8  mov     edx, 2; DesiredAccess
0x14000a6bd  mov     rcx, [rsi+8]; Handle
0x14000a6c1  call    cs:__imp_ObReferenceObjectByHandle
0x14000a6c8  nop     dword ptr [rax+rax+00h]
0x14000a6cd  mov     edi, eax
0x14000a6cf  mov     rbx, [rsp+58h+arg_0]
0x14000a6d4  test    eax, eax
0x14000a6d6  js      short loc_14000A6E3
0x14000a6d8  mov     eax, 0C0000024h
0x14000a6dd  cmp     dword ptr [rbx], 2
0x14000a6e0  cmovnz  edi, eax
0x14000a6e3  test    edi, edi
0x14000a6e5  js      short loc_14000A71B
0x14000a6e7  mov     al, [rsi+20h]
0x14000a6ea  neg     al
0x14000a6ec  sbb     r8, r8
0x14000a6ef  and     r8, rsi; union _LARGE_INTEGER *
0x14000a6f2  mov     [rsp+58h+var_20], r14; unsigned int *
0x14000a6f7  mov     eax, [r14]
0x14000a6fa  mov     [rsp+58h+var_28], eax; unsigned int
0x14000a6fe  mov     [rsp+58h+HandleInformation], r15; void *
0x14000a703  mov     eax, [rsi+18h]
0x14000a706  mov     dword ptr [rsp+58h+Object], eax; unsigned int
0x14000a70a  mov     r9, [rsi+10h]; void *
0x14000a70e  mov     edx, [rsi+1Ch]; unsigned int
0x14000a711  mov     rcx, rbx; this
0x14000a714  call    ?SendNotification@PCW_NOTIFIER@@QEAAJKPEAT_LARGE_INTEGER@@PEBXKPEAXKPEAK@Z; PCW_NOTIFIER::SendNotification(ulong,_LARGE_INTEGER *,void const *,ulong,void *,ulong,ulong *)
0x14000a719  mov     edi, eax
0x14000a71b  test    rbx, rbx
0x14000a71e  jz      short loc_14000A72F
0x14000a720  mov     rcx, rbx; Object
0x14000a723  call    cs:__imp_ObfDereferenceObject
0x14000a72a  nop     dword ptr [rax+rax+00h]
0x14000a72f  mov     eax, edi
0x14000a731  mov     rbx, [rsp+58h+arg_8]
0x14000a736  mov     rsi, [rsp+58h+arg_10]
0x14000a73b  add     rsp, 40h
0x14000a73f  pop     r15
0x14000a741  pop     r14
0x14000a743  pop     rdi
0x14000a744  retn
```
