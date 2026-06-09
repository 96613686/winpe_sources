# RescanUninitialize

- ea: `0x18003676c`
- end: `0x180036853`
- name: `RescanUninitialize`
- size: `231`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180035230`
- `0x18005a890`

## callees

- `0x18003676c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800367c0`
- `ntoskrnl!ZwClose` at `0x1800367c0`
- `ntoskrnl!ExDeleteResourceLite` at `0x18003683b`
- `ntoskrnl!ExDeleteResourceLite` at `0x18003683b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18003679c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18003679c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800367ad`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800367ad`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800367fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800367fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18003680a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18003680a`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003682c`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003682c`
- `ntoskrnl!KeInitializeEvent` at `0x1800367e3`
- `ntoskrnl!KeInitializeEvent` at `0x1800367e3`

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
0x18003676c  mov     [rsp+arg_0], rbx
0x180036771  push    rdi
0x180036772  sub     rsp, 50h
0x180036776  xor     eax, eax
0x180036778  lea     rdi, [rcx+188h]
0x18003677f  xorps   xmm0, xmm0
0x180036782  mov     rbx, rcx
0x180036785  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x18003678a  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x18003678f  cmp     [rcx+168h], rax
0x180036796  jz      loc_180036838
0x18003679c  call    cs:__imp_KeEnterCriticalRegion
0x1800367a3  nop     dword ptr [rax+rax+00h]
0x1800367a8  mov     dl, 1; Wait
0x1800367aa  mov     rcx, rdi; Resource
0x1800367ad  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800367b4  nop     dword ptr [rax+rax+00h]
0x1800367b9  mov     rcx, [rbx+168h]; Handle
0x1800367c0  call    cs:__imp_ZwClose
0x1800367c7  nop     dword ptr [rax+rax+00h]
0x1800367cc  xor     r8d, r8d; State
0x1800367cf  mov     qword ptr [rbx+168h], 0
0x1800367da  lea     rcx, [rsp+58h+Event]; Event
0x1800367df  lea     edx, [r8+1]; Type
0x1800367e3  call    cs:__imp_KeInitializeEvent
0x1800367ea  nop     dword ptr [rax+rax+00h]
0x1800367ef  lea     rax, [rsp+58h+Event]
0x1800367f4  mov     rcx, rdi; Resource
0x1800367f7  mov     [rbx+180h], rax
0x1800367fe  call    cs:__imp_ExReleaseResourceLite
0x180036805  nop     dword ptr [rax+rax+00h]
0x18003680a  call    cs:__imp_KeLeaveCriticalRegion
0x180036811  nop     dword ptr [rax+rax+00h]
0x180036816  xor     r9d, r9d; Alertable
0x180036819  mov     [rsp+58h+Timeout], 0; Timeout
0x180036822  xor     r8d, r8d; WaitMode
0x180036825  lea     rcx, [rsp+58h+Event]; Object
0x18003682a  xor     edx, edx; WaitReason
0x18003682c  call    cs:__imp_KeWaitForSingleObject
0x180036833  nop     dword ptr [rax+rax+00h]
0x180036838  mov     rcx, rdi; Resource
0x18003683b  call    cs:__imp_ExDeleteResourceLite
0x180036842  nop     dword ptr [rax+rax+00h]
0x180036847  mov     rbx, [rsp+58h+arg_0]
0x18003684c  add     rsp, 50h
0x180036850  pop     rdi
0x180036851  retn
```
