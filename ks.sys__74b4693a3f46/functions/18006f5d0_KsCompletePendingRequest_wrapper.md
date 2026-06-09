# KsCompletePendingRequest_wrapper

- ea: `0x18006f5d0`
- end: `0x18006f61e`
- name: `KsCompletePendingRequest_wrapper`
- size: `78`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180013760`
- `0x180019c60`
- `0x18006f5d0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18006f5e3`
- `ntoskrnl!KeGetCurrentIrql` at `0x18006f5e3`

## string_xrefs

- `0x18006f5fa`: `KsCompletePendingRequest should only be called at IRQL <= DISPATCH_LEVEL.`

## pseudocode

```c
void __fastcall KsCompletePendingRequest_wrapper(PIRP Irp)
{
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() > 2u )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsCompletePendingRequest should only be called at IRQL <= DISPATCH_LEVEL.",
      528393);
  KsCompletePendingRequest(Irp);
}

```

## disassembly

```asm
0x18006f5d0  push    rbx
0x18006f5d2  sub     rsp, 20h
0x18006f5d6  mov     eax, cs:KsXdvExtLevel
0x18006f5dc  mov     rbx, rcx
0x18006f5df  test    al, 8
0x18006f5e1  jz      short loc_18006F60F
0x18006f5e3  call    cs:__imp_KeGetCurrentIrql
0x18006f5ea  nop     dword ptr [rax+rax+00h]
0x18006f5ef  cmp     al, 2
0x18006f5f1  jbe     short loc_18006F60F
0x18006f5f3  mov     rax, cs:KsVerifierUtilTable
0x18006f5fa  lea     rcx, aKscompletepend; "KsCompletePendingRequest should only be"...
0x18006f601  mov     edx, 81009h
0x18006f606  mov     rax, [rax+60h]
0x18006f60a  call    _guard_dispatch_icall
0x18006f60f  mov     rcx, rbx; Irp
0x18006f612  call    KsCompletePendingRequest
0x18006f617  add     rsp, 20h
0x18006f61b  pop     rbx
0x18006f61c  retn
```
