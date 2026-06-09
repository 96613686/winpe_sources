# CngSiloTerminateNotify

- ea: `0x18005d750`
- end: `0x18005d7b1`
- name: `CngSiloTerminateNotify`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18005d750`
- `0x18006d310`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005d75d`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005d75d`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005d799`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005d799`
- `ntoskrnl!PsIsHostSilo` at `0x18005d774`
- `ntoskrnl!PsIsHostSilo` at `0x18005d774`
- `ntoskrnl!PsFreeSiloContextSlot` at `0x18005d78a`
- `ntoskrnl!PsFreeSiloContextSlot` at `0x18005d78a`

## pseudocode

```c
__int64 __fastcall CngSiloTerminateNotify(__int64 a1)
{
  __int64 v2; // rdi

  v2 = PsAttachSiloToCurrentThread(a1);
  UninitializeConfig();
  if ( (unsigned __int8)PsIsHostSilo(a1) )
    PsFreeSiloContextSlot(g_tlsCtxtSlot);
  return PsDetachSiloFromCurrentThread(v2);
}

```

## disassembly

```asm
0x18005d750  mov     [rsp+arg_0], rbx
0x18005d755  push    rdi
0x18005d756  sub     rsp, 20h
0x18005d75a  mov     rbx, rcx
0x18005d75d  call    cs:__imp_PsAttachSiloToCurrentThread
0x18005d764  nop     dword ptr [rax+rax+00h]
0x18005d769  mov     rdi, rax
0x18005d76c  call    UninitializeConfig
0x18005d771  mov     rcx, rbx
0x18005d774  call    cs:__imp_PsIsHostSilo
0x18005d77b  nop     dword ptr [rax+rax+00h]
0x18005d780  test    al, al
0x18005d782  jz      short loc_18005D796
0x18005d784  mov     ecx, cs:?g_tlsCtxtSlot@@3KA; ulong g_tlsCtxtSlot
0x18005d78a  call    cs:__imp_PsFreeSiloContextSlot
0x18005d791  nop     dword ptr [rax+rax+00h]
0x18005d796  mov     rcx, rdi
0x18005d799  call    cs:__imp_PsDetachSiloFromCurrentThread
0x18005d7a0  nop     dword ptr [rax+rax+00h]
0x18005d7a5  mov     rbx, [rsp+28h+arg_0]
0x18005d7aa  add     rsp, 20h
0x18005d7ae  pop     rdi
0x18005d7af  retn
```
