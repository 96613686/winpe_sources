# MRxSmbStop

- ea: `0x1400329b0`
- end: `0x140032a28`
- name: `MRxSmbStop`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140011bc0`
- `0x1400329b0`
- `0x14003f98c`

## import_xrefs

- `ntoskrnl!KeFlushQueuedDpcs` at `0x1400329fd`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1400329fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400329c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400329c6`
- `mrxsmb!MRxSmbShutdownRecurrentService` at `0x1400329ec`
- `mrxsmb!MRxSmbShutdownRecurrentService` at `0x1400329ec`

## pseudocode

```c
__int64 MRxSmbStop()
{
  if ( stru_140020320.Buffer )
  {
    ExFreePoolWithTag(stru_140020320.Buffer - 6, 0);
    stru_140020320.Buffer = 0;
    *(_DWORD *)&stru_140020320.Length = 0;
  }
  MRxSmbShutdownRecurrentService(MRxSmbEchoProbeServiceContext);
  MRxSmbTearDownEchoProbeService();
  KeFlushQueuedDpcs();
  SmbCeDbStop();
  *((_QWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceObject + 13) = MRxSmbUnload;
  return 0;
}

```

## disassembly

```asm
0x1400329b0  sub     rsp, 28h
0x1400329b4  mov     rcx, cs:stru_140020320.Buffer
0x1400329bb  test    rcx, rcx
0x1400329be  jz      short loc_1400329E5
0x1400329c0  add     rcx, 0FFFFFFFFFFFFFFF4h; P
0x1400329c4  xor     edx, edx; Tag
0x1400329c6  call    cs:__imp_ExFreePoolWithTag
0x1400329cd  nop     dword ptr [rax+rax+00h]
0x1400329d2  xor     eax, eax
0x1400329d4  mov     cs:stru_140020320.Buffer, 0
0x1400329df  mov     dword ptr cs:stru_140020320.Length, eax
0x1400329e5  lea     rcx, MRxSmbEchoProbeServiceContext
0x1400329ec  call    cs:__imp_MRxSmbShutdownRecurrentService
0x1400329f3  nop     dword ptr [rax+rax+00h]
0x1400329f8  call    MRxSmbTearDownEchoProbeService
0x1400329fd  call    cs:__imp_KeFlushQueuedDpcs
0x140032a04  nop     dword ptr [rax+rax+00h]
0x140032a09  call    SmbCeDbStop
0x140032a0e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140032a15  lea     rcx, MRxSmbUnload
0x140032a1c  mov     [rax+68h], rcx
0x140032a20  xor     eax, eax
0x140032a22  add     rsp, 28h
0x140032a26  retn
```
