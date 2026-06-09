# CngSiloTerminateNotify

- ea: `0x18005ce60`
- end: `0x18005cec1`
- name: `CngSiloTerminateNotify`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18005ce60`
- `0x18006c910`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005ce6d`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005ce6d`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005cea9`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005cea9`
- `ntoskrnl!PsIsHostSilo` at `0x18005ce84`
- `ntoskrnl!PsIsHostSilo` at `0x18005ce84`
- `ntoskrnl!PsFreeSiloContextSlot` at `0x18005ce9a`
- `ntoskrnl!PsFreeSiloContextSlot` at `0x18005ce9a`

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
0x18005ce60  mov     [rsp+arg_0], rbx
0x18005ce65  push    rdi
0x18005ce66  sub     rsp, 20h
0x18005ce6a  mov     rbx, rcx
0x18005ce6d  call    cs:__imp_PsAttachSiloToCurrentThread
0x18005ce74  nop     dword ptr [rax+rax+00h]
0x18005ce79  mov     rdi, rax
0x18005ce7c  call    UninitializeConfig
0x18005ce81  mov     rcx, rbx
0x18005ce84  call    cs:__imp_PsIsHostSilo
0x18005ce8b  nop     dword ptr [rax+rax+00h]
0x18005ce90  test    al, al
0x18005ce92  jz      short loc_18005CEA6
0x18005ce94  mov     ecx, cs:?g_tlsCtxtSlot@@3KA; ulong g_tlsCtxtSlot
0x18005ce9a  call    cs:__imp_PsFreeSiloContextSlot
0x18005cea1  nop     dword ptr [rax+rax+00h]
0x18005cea6  mov     rcx, rdi
0x18005cea9  call    cs:__imp_PsDetachSiloFromCurrentThread
0x18005ceb0  nop     dword ptr [rax+rax+00h]
0x18005ceb5  mov     rbx, [rsp+28h+arg_0]
0x18005ceba  add     rsp, 20h
0x18005cebe  pop     rdi
0x18005cebf  retn
```
