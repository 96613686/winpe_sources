# DbgkpWerStartDeferredLiveDump

- ea: `0x14075230c`
- end: `0x14075239e`
- name: `DbgkpWerStartDeferredLiveDump`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140adbe28`

## callees

- `0x1402a2f90`
- `0x1402a4aa0`
- `0x1405d64b4`
- `0x14075230c`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x14075232b`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x14075232b`

## string_xrefs

- `0x14075233d`: `DBGK: DbgkpWerStartDeferredLiveDump: WerLiveKernelOpenDumpFile failed, status 0x%X\n`

## pseudocode

```c
__int64 __fastcall DbgkpWerStartDeferredLiveDump(__int64 a1)
{
  int v2; // edi
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  v2 = WerLiveKernelOpenDumpFile(*(_QWORD *)(a1 + 96), &v4);
  if ( v2 < 0 )
  {
    DbgPrintEx(
      5u,
      0,
      "DBGK: DbgkpWerStartDeferredLiveDump: WerLiveKernelOpenDumpFile failed, status 0x%X\n",
      (unsigned int)v2);
    return (unsigned int)v2;
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = v4;
  v2 = IoSetDeferredLiveDumpFileHandle(*(_QWORD *)(a1 + 128), v4);
  if ( v2 < 0 )
  {
    DbgPrintEx(
      5u,
      0,
      "DBGK: DbgkpWerStartDeferredLiveDump: IoSetDeferredLiveDumpFileHandle failed, status 0x%X\n",
      (unsigned int)v2);
    return (unsigned int)v2;
  }
  ExQueueWorkItem(*(PWORK_QUEUE_ITEM *)(a1 + 112), DelayedWorkQueue);
  return 0;
}

```

## disassembly

```asm
0x14075230c  mov     [rsp+arg_8], rbx
0x140752311  push    rdi
0x140752312  sub     rsp, 20h
0x140752316  mov     rbx, rcx
0x140752319  mov     [rsp+28h+arg_0], 0
0x140752322  mov     rcx, [rcx+60h]
0x140752326  lea     rdx, [rsp+28h+arg_0]
0x14075232b  call    cs:__imp_WerLiveKernelOpenDumpFile
0x140752332  nop     dword ptr [rax+rax+00h]
0x140752337  mov     edi, eax
0x140752339  test    eax, eax
0x14075233b  jns     short loc_140752355
0x14075233d  lea     r8, aDbgkDbgkpwerst; "DBGK: DbgkpWerStartDeferredLiveDump: We"...
0x140752344  xor     edx, edx; Level
0x140752346  mov     r9d, edi
0x140752349  lea     ecx, [rdx+5]; ComponentId
0x14075234c  call    DbgPrintEx
0x140752351  mov     eax, edi
0x140752353  jmp     short loc_140752392
0x140752355  mov     rcx, [rbx+78h]
0x140752359  mov     rax, [rsp+28h+arg_0]
0x14075235e  mov     [rcx+8], rax
0x140752362  mov     rdx, [rsp+28h+arg_0]
0x140752367  mov     rcx, [rbx+80h]
0x14075236e  call    IoSetDeferredLiveDumpFileHandle
0x140752373  mov     edi, eax
0x140752375  test    eax, eax
0x140752377  jns     short loc_140752382
0x140752379  lea     r8, aDbgkDbgkpwerst_0; "DBGK: DbgkpWerStartDeferredLiveDump: Io"...
0x140752380  jmp     short loc_140752344
0x140752382  mov     rcx, [rbx+70h]; WorkItem
0x140752386  mov     edx, 1; QueueType
0x14075238b  call    ExQueueWorkItem
0x140752390  xor     eax, eax
0x140752392  mov     rbx, [rsp+28h+arg_8]
0x140752397  add     rsp, 20h
0x14075239b  pop     rdi
0x14075239c  retn
```
