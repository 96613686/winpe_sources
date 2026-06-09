# VmbusTlConnectTimeoutDpc

- ea: `0x140002a40`
- end: `0x140002af3`
- name: `VmbusTlConnectTimeoutDpc`
- size: `179`
- prototype: `void __fastcall(struct _KDPC *Dpc, __int64 DeferredContext, PVOID SystemArgument1, PVOID SystemArgument2)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140002a40`
- `0x140004e9c`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002ae0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ae0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002aca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002aca`

## pseudocode

```c
void __fastcall VmbusTlConnectTimeoutDpc(
        struct _KDPC *Dpc,
        __int64 DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  signed __int64 v5; // rax
  bool v6; // cc
  signed __int64 v7; // rax
  void (__fastcall *v8)(__int64); // rax

  VmbusTlAllocateAndQueueEndpointAction(DeferredContext, 8u);
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlConnectTimeoutDpc",
      859,
      DeferredContext,
      *(_QWORD *)(DeferredContext + 8),
      (const int *)"Dereference object");
  v5 = _InterlockedExchangeAdd64((volatile signed __int64 *)(DeferredContext + 8), 0xFFFFFFFFFFFFFFFFuLL);
  v6 = v5 <= 1;
  v7 = v5 - 1;
  if ( v6 )
  {
    if ( v7 )
      __fastfail(0xEu);
    v8 = *(void (__fastcall **)(__int64))(DeferredContext + 80);
    if ( v8 )
      v8(DeferredContext);
    if ( *(_DWORD *)(DeferredContext + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)DeferredContext, 0x69706E56u);
    }
    else if ( *(_DWORD *)(DeferredContext + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(DeferredContext + 96), (PVOID)DeferredContext);
    }
  }
}

```

## disassembly

```asm
0x140002a40  push    rbx
0x140002a42  sub     rsp, 30h
0x140002a46  mov     rbx, rdx
0x140002a49  xor     r8d, r8d
0x140002a4c  mov     rcx, rbx
0x140002a4f  lea     edx, [r8+8]
0x140002a53  call    VmbusTlAllocateAndQueueEndpointAction
0x140002a58  mov     eax, cs:dword_140013058
0x140002a5e  cmp     eax, 5
0x140002a61  jbe     short loc_140002A87
0x140002a63  mov     r9, [rbx+8]
0x140002a67  lea     rax, aDereferenceObj; "Dereference object"
0x140002a6e  mov     r8, rbx
0x140002a71  mov     [rsp+38h+var_18], rax
0x140002a76  mov     edx, 35Bh
0x140002a7b  lea     rcx, aVmbustlconnect_6; "VmbusTlConnectTimeoutDpc"
0x140002a82  call    HvsocketTraceReferenceCount
0x140002a87  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002a8b  lock xadd [rbx+8], rax
0x140002a91  sub     rax, 1
0x140002a95  jg      short loc_140002AEC
0x140002a97  test    rax, rax
0x140002a9a  jz      short loc_140002AA5
0x140002a9c  mov     ecx, 0Eh
0x140002aa1  int     29h; Win8: RtlFailFast(ecx)
0x140002aa3  jmp     short loc_140002AEC
0x140002aa5  mov     rax, [rbx+50h]
0x140002aa9  test    rax, rax
0x140002aac  jz      short loc_140002AB6
0x140002aae  mov     rcx, rbx
0x140002ab1  call    _guard_dispatch_icall
0x140002ab6  mov     ecx, [rbx+58h]
0x140002ab9  sub     ecx, 1
0x140002abc  jz      short loc_140002AD8
0x140002abe  cmp     ecx, 1
0x140002ac1  jnz     short loc_140002AEC
0x140002ac3  mov     rcx, [rbx+60h]; Lookaside
0x140002ac7  mov     rdx, rbx; Entry
0x140002aca  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002ad1  nop     dword ptr [rax+rax+00h]
0x140002ad6  jmp     short loc_140002AEC
0x140002ad8  mov     edx, 69706E56h; Tag
0x140002add  mov     rcx, rbx; P
0x140002ae0  call    cs:__imp_ExFreePoolWithTag
0x140002ae7  nop     dword ptr [rax+rax+00h]
0x140002aec  add     rsp, 30h
0x140002af0  pop     rbx
0x140002af1  retn
```
