# CngSiloTerminateNotify

- ea: `0x180067030`
- end: `0x180067091`
- name: `CngSiloTerminateNotify`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180067030`
- `0x180076ab0`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18006703d`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18006703d`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180067079`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180067079`
- `ntoskrnl!PsIsHostSilo` at `0x180067054`
- `ntoskrnl!PsIsHostSilo` at `0x180067054`
- `ntoskrnl!PsFreeSiloContextSlot` at `0x18006706a`
- `ntoskrnl!PsFreeSiloContextSlot` at `0x18006706a`

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
0x180067030  mov     [rsp+arg_0], rbx
0x180067035  push    rdi
0x180067036  sub     rsp, 20h
0x18006703a  mov     rbx, rcx
0x18006703d  call    cs:__imp_PsAttachSiloToCurrentThread
0x180067044  nop     dword ptr [rax+rax+00h]
0x180067049  mov     rdi, rax
0x18006704c  call    UninitializeConfig
0x180067051  mov     rcx, rbx
0x180067054  call    cs:__imp_PsIsHostSilo
0x18006705b  nop     dword ptr [rax+rax+00h]
0x180067060  test    al, al
0x180067062  jz      short loc_180067076
0x180067064  mov     ecx, cs:?g_tlsCtxtSlot@@3KA; ulong g_tlsCtxtSlot
0x18006706a  call    cs:__imp_PsFreeSiloContextSlot
0x180067071  nop     dword ptr [rax+rax+00h]
0x180067076  mov     rcx, rdi
0x180067079  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180067080  nop     dword ptr [rax+rax+00h]
0x180067085  mov     rbx, [rsp+28h+arg_0]
0x18006708a  add     rsp, 20h
0x18006708e  pop     rdi
0x18006708f  retn
```
