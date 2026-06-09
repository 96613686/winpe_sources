# PcwpIoctlReadNotificationData(PCW_IOCTL_INPUT *,void *,ulong *)

- ea: `0x14000a750`
- end: `0x14000a7d9`
- name: `?PcwpIoctlReadNotificationData@@YAJPEATPCW_IOCTL_INPUT@@PEAXPEAK@Z`
- size: `137`
- prototype: `__int64 __fastcall(union PCW_IOCTL_INPUT *, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400098b8`
- `0x14000a750`
- `0x14000c308`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000a78a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a7ba`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a78a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a7ba`

## pseudocode

```c
__int64 __fastcall PcwpIoctlReadNotificationData(union PCW_IOCTL_INPUT *a1, void *a2, unsigned int *a3)
{
  int v5; // ebx
  PVOID v7; // rbx
  unsigned int v8; // edi
  PVOID Object; // [rsp+30h] [rbp+8h] BYREF

  Object = 0;
  v5 = PcwpReferenceObjectByHandle_PCW_USER_REGISTRATION_(&Object, *(_QWORD *)a1, a3);
  if ( v5 >= 0 )
  {
    v7 = Object;
    v8 = PCW_USER_REGISTRATION::ReadInFlightNotificationBuffer((PCW_USER_REGISTRATION *)Object, a2, *a3, a3);
    if ( v7 )
      ObfDereferenceObject(v7);
    return v8;
  }
  else
  {
    if ( Object )
      ObfDereferenceObject(Object);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x14000a750  mov     rax, rsp
0x14000a753  mov     [rax+10h], rbx
0x14000a757  mov     [rax+18h], rsi
0x14000a75b  push    rdi
0x14000a75c  sub     rsp, 20h
0x14000a760  mov     rsi, rdx
0x14000a763  mov     qword ptr [rax+8], 0
0x14000a76b  mov     rdx, [rcx]
0x14000a76e  mov     rdi, r8
0x14000a771  lea     rcx, [rax+8]
0x14000a775  call    PcwpReferenceObjectByHandle_PCW_USER_REGISTRATION_
0x14000a77a  mov     ebx, eax
0x14000a77c  test    eax, eax
0x14000a77e  jns     short loc_14000A79A
0x14000a780  mov     rcx, [rsp+28h+Object]; Object
0x14000a785  test    rcx, rcx
0x14000a788  jz      short loc_14000A796
0x14000a78a  call    cs:__imp_ObfDereferenceObject
0x14000a791  nop     dword ptr [rax+rax+00h]
0x14000a796  mov     eax, ebx
0x14000a798  jmp     short loc_14000A7C8
0x14000a79a  mov     rbx, [rsp+28h+Object]
0x14000a79f  mov     r9, rdi; unsigned int *
0x14000a7a2  mov     r8d, [rdi]; unsigned int
0x14000a7a5  mov     rcx, rbx; this
0x14000a7a8  mov     rdx, rsi; void *
0x14000a7ab  call    ?ReadInFlightNotificationBuffer@PCW_USER_REGISTRATION@@QEAAJPEAXKPEAK@Z; PCW_USER_REGISTRATION::ReadInFlightNotificationBuffer(void *,ulong,ulong *)
0x14000a7b0  mov     edi, eax
0x14000a7b2  test    rbx, rbx
0x14000a7b5  jz      short loc_14000A7C6
0x14000a7b7  mov     rcx, rbx; Object
0x14000a7ba  call    cs:__imp_ObfDereferenceObject
0x14000a7c1  nop     dword ptr [rax+rax+00h]
0x14000a7c6  mov     eax, edi
0x14000a7c8  mov     rbx, [rsp+28h+arg_8]
0x14000a7cd  mov     rsi, [rsp+28h+arg_10]
0x14000a7d2  add     rsp, 20h
0x14000a7d6  pop     rdi
0x14000a7d7  retn
```
