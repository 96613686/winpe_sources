# RescanUninitialize

- ea: `0x18003665c`
- end: `0x180036743`
- name: `RescanUninitialize`
- size: `231`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180035120`
- `0x18005a6f0`

## callees

- `0x18003665c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800366b0`
- `ntoskrnl!ZwClose` at `0x1800366b0`
- `ntoskrnl!ExDeleteResourceLite` at `0x18003672b`
- `ntoskrnl!ExDeleteResourceLite` at `0x18003672b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18003668c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18003668c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18003669d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18003669d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800366ee`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800366ee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800366fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800366fa`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003671c`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003671c`
- `ntoskrnl!KeInitializeEvent` at `0x1800366d3`
- `ntoskrnl!KeInitializeEvent` at `0x1800366d3`

## pseudocode

```c
NTSTATUS __fastcall RescanUninitialize(__int64 a1)
{
  struct _ERESOURCE *v1; // rdi
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF

  v1 = (struct _ERESOURCE *)(a1 + 392);
  memset(&Event, 0, sizeof(Event));
  if ( *(_QWORD *)(a1 + 360) )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(v1, 1u);
    ZwClose(*(HANDLE *)(a1 + 360));
    *(_QWORD *)(a1 + 360) = 0;
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    *(_QWORD *)(a1 + 384) = &Event;
    ExReleaseResourceLite(v1);
    KeLeaveCriticalRegion();
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  }
  return ExDeleteResourceLite(v1);
}

```

## disassembly

```asm
0x18003665c  mov     [rsp+arg_0], rbx
0x180036661  push    rdi
0x180036662  sub     rsp, 50h
0x180036666  xor     eax, eax
0x180036668  lea     rdi, [rcx+188h]
0x18003666f  xorps   xmm0, xmm0
0x180036672  mov     rbx, rcx
0x180036675  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x18003667a  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x18003667f  cmp     [rcx+168h], rax
0x180036686  jz      loc_180036728
0x18003668c  call    cs:__imp_KeEnterCriticalRegion
0x180036693  nop     dword ptr [rax+rax+00h]
0x180036698  mov     dl, 1; Wait
0x18003669a  mov     rcx, rdi; Resource
0x18003669d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800366a4  nop     dword ptr [rax+rax+00h]
0x1800366a9  mov     rcx, [rbx+168h]; Handle
0x1800366b0  call    cs:__imp_ZwClose
0x1800366b7  nop     dword ptr [rax+rax+00h]
0x1800366bc  xor     r8d, r8d; State
0x1800366bf  mov     qword ptr [rbx+168h], 0
0x1800366ca  lea     rcx, [rsp+58h+Event]; Event
0x1800366cf  lea     edx, [r8+1]; Type
0x1800366d3  call    cs:__imp_KeInitializeEvent
0x1800366da  nop     dword ptr [rax+rax+00h]
0x1800366df  lea     rax, [rsp+58h+Event]
0x1800366e4  mov     rcx, rdi; Resource
0x1800366e7  mov     [rbx+180h], rax
0x1800366ee  call    cs:__imp_ExReleaseResourceLite
0x1800366f5  nop     dword ptr [rax+rax+00h]
0x1800366fa  call    cs:__imp_KeLeaveCriticalRegion
0x180036701  nop     dword ptr [rax+rax+00h]
0x180036706  xor     r9d, r9d; Alertable
0x180036709  mov     [rsp+58h+Timeout], 0; Timeout
0x180036712  xor     r8d, r8d; WaitMode
0x180036715  lea     rcx, [rsp+58h+Event]; Object
0x18003671a  xor     edx, edx; WaitReason
0x18003671c  call    cs:__imp_KeWaitForSingleObject
0x180036723  nop     dword ptr [rax+rax+00h]
0x180036728  mov     rcx, rdi; Resource
0x18003672b  call    cs:__imp_ExDeleteResourceLite
0x180036732  nop     dword ptr [rax+rax+00h]
0x180036737  mov     rbx, [rsp+58h+arg_0]
0x18003673c  add     rsp, 50h
0x180036740  pop     rdi
0x180036741  retn
```
