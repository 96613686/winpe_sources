# MupiCompleteProviderRegistration

- ea: `0x140012dd0`
- end: `0x140012e77`
- name: `MupiCompleteProviderRegistration`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140012700`

## callees

- `0x140002754`
- `0x140010534`
- `0x140012dd0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012df2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012df2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012e24`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012e24`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012ddd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012ddd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012e30`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012e30`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall MupiCompleteProviderRegistration(__int64 a1, __int64 a2)
{
  PDEVICE_OBJECT *result; // rax

  *(_QWORD *)(a2 + 32) = a1;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  *(_DWORD *)(a1 + 68) = 3;
  ++dword_14000A7EC;
  MupFlushKnownPrefixTable(0, 0, 0);
  ++dword_14000A778;
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    return (PDEVICE_OBJECT *)WPP_SF_q(
                               WPP_GLOBAL_Control->AttachedDevice,
                               24,
                               WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids,
                               a1);
  }
  return result;
}

```

## disassembly

```asm
0x140012dd0  push    rbx
0x140012dd2  sub     rsp, 20h
0x140012dd6  mov     rbx, rcx
0x140012dd9  mov     [rdx+20h], rcx
0x140012ddd  call    cs:__imp_KeEnterCriticalRegion
0x140012de4  nop     dword ptr [rax+rax+00h]
0x140012de9  mov     dl, 1; Wait
0x140012deb  lea     rcx, Resource; Resource
0x140012df2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140012df9  nop     dword ptr [rax+rax+00h]
0x140012dfe  mov     dword ptr [rbx+44h], 3
0x140012e05  xor     r8d, r8d
0x140012e08  inc     cs:dword_14000A7EC
0x140012e0e  xor     edx, edx
0x140012e10  xor     ecx, ecx
0x140012e12  call    MupFlushKnownPrefixTable
0x140012e17  inc     cs:dword_14000A778
0x140012e1d  lea     rcx, Resource; Resource
0x140012e24  call    cs:__imp_ExReleaseResourceLite
0x140012e2b  nop     dword ptr [rax+rax+00h]
0x140012e30  call    cs:__imp_KeLeaveCriticalRegion
0x140012e37  nop     dword ptr [rax+rax+00h]
0x140012e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012e43  lea     rax, WPP_GLOBAL_Control
0x140012e4a  cmp     rcx, rax
0x140012e4d  jz      short loc_140012E70
0x140012e4f  test    dword ptr [rcx+2Ch], 4000000h
0x140012e56  jz      short loc_140012E70
0x140012e58  mov     rcx, [rcx+18h]
0x140012e5c  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x140012e63  mov     edx, 18h
0x140012e68  mov     r9, rbx
0x140012e6b  call    WPP_SF_q
0x140012e70  add     rsp, 20h
0x140012e74  pop     rbx
0x140012e75  retn
```
