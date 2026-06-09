# EvtDriverUnload

- ea: `0x140063360`
- end: `0x1400633a9`
- name: `EvtDriverUnload`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140027d54`
- `0x14003e9c0`
- `0x14003ee80`

## import_xrefs

- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140063396`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140063396`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140063375`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140063375`
- `ntoskrnl!PsGetHostSilo` at `0x140063366`
- `ntoskrnl!PsGetHostSilo` at `0x140063366`

## pseudocode

```c
__int64 EvtDriverUnload()
{
  __int64 HostSilo; // rax
  __int64 v1; // rbx

  HostSilo = PsGetHostSilo();
  v1 = PsAttachSiloToCurrentThread(HostSilo);
  MsQuicDeregisterNmrProvider();
  MsQuicPcwCleanup();
  MsQuicLibraryUnload();
  return PsDetachSiloFromCurrentThread(v1);
}

```

## disassembly

```asm
0x140063360  push    rbx
0x140063362  sub     rsp, 20h
0x140063366  call    cs:__imp_PsGetHostSilo
0x14006336d  nop     dword ptr [rax+rax+00h]
0x140063372  mov     rcx, rax
0x140063375  call    cs:__imp_PsAttachSiloToCurrentThread
0x14006337c  nop     dword ptr [rax+rax+00h]
0x140063381  mov     rbx, rax
0x140063384  call    MsQuicDeregisterNmrProvider
0x140063389  call    MsQuicPcwCleanup
0x14006338e  call    MsQuicLibraryUnload
0x140063393  mov     rcx, rbx
0x140063396  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14006339d  nop     dword ptr [rax+rax+00h]
0x1400633a2  add     rsp, 20h
0x1400633a6  pop     rbx
0x1400633a7  retn
```
