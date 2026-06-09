# DbgkpWerStartDeferredLiveDump

- ea: `0x14074de0c`
- end: `0x14074de9e`
- name: `DbgkpWerStartDeferredLiveDump`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140ad61a8`

## callees

- `0x14020fe90`
- `0x140211370`
- `0x1405cf8d4`
- `0x14074de0c`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x14074de2b`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x14074de2b`

## string_xrefs

- `0x14074de3d`: `DBGK: DbgkpWerStartDeferredLiveDump: WerLiveKernelOpenDumpFile failed, status 0x%X\n`

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
0x14074de0c  mov     [rsp+arg_8], rbx
0x14074de11  push    rdi
0x14074de12  sub     rsp, 20h
0x14074de16  mov     rbx, rcx
0x14074de19  mov     [rsp+28h+arg_0], 0
0x14074de22  mov     rcx, [rcx+60h]
0x14074de26  lea     rdx, [rsp+28h+arg_0]
0x14074de2b  call    cs:__imp_WerLiveKernelOpenDumpFile
0x14074de32  nop     dword ptr [rax+rax+00h]
0x14074de37  mov     edi, eax
0x14074de39  test    eax, eax
0x14074de3b  jns     short loc_14074DE55
0x14074de3d  lea     r8, aDbgkDbgkpwerst; "DBGK: DbgkpWerStartDeferredLiveDump: We"...
0x14074de44  xor     edx, edx; Level
0x14074de46  mov     r9d, edi
0x14074de49  lea     ecx, [rdx+5]; ComponentId
0x14074de4c  call    DbgPrintEx
0x14074de51  mov     eax, edi
0x14074de53  jmp     short loc_14074DE92
0x14074de55  mov     rcx, [rbx+78h]
0x14074de59  mov     rax, [rsp+28h+arg_0]
0x14074de5e  mov     [rcx+8], rax
0x14074de62  mov     rdx, [rsp+28h+arg_0]
0x14074de67  mov     rcx, [rbx+80h]
0x14074de6e  call    IoSetDeferredLiveDumpFileHandle
0x14074de73  mov     edi, eax
0x14074de75  test    eax, eax
0x14074de77  jns     short loc_14074DE82
0x14074de79  lea     r8, aDbgkDbgkpwerst_0; "DBGK: DbgkpWerStartDeferredLiveDump: Io"...
0x14074de80  jmp     short loc_14074DE44
0x14074de82  mov     rcx, [rbx+70h]; WorkItem
0x14074de86  mov     edx, 1; QueueType
0x14074de8b  call    ExQueueWorkItem
0x14074de90  xor     eax, eax
0x14074de92  mov     rbx, [rsp+28h+arg_8]
0x14074de97  add     rsp, 20h
0x14074de9b  pop     rdi
0x14074de9c  retn
```
