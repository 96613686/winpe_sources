# MupiCompleteProviderRegistration

- ea: `0x140012e20`
- end: `0x140012ec7`
- name: `MupiCompleteProviderRegistration`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140012750`

## callees

- `0x140002754`
- `0x140010534`
- `0x140012e20`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012e42`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012e42`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012e74`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012e74`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012e2d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012e2d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012e80`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012e80`

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
0x140012e20  push    rbx
0x140012e22  sub     rsp, 20h
0x140012e26  mov     rbx, rcx
0x140012e29  mov     [rdx+20h], rcx
0x140012e2d  call    cs:__imp_KeEnterCriticalRegion
0x140012e34  nop     dword ptr [rax+rax+00h]
0x140012e39  mov     dl, 1; Wait
0x140012e3b  lea     rcx, Resource; Resource
0x140012e42  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140012e49  nop     dword ptr [rax+rax+00h]
0x140012e4e  mov     dword ptr [rbx+44h], 3
0x140012e55  xor     r8d, r8d
0x140012e58  inc     cs:dword_14000A7EC
0x140012e5e  xor     edx, edx
0x140012e60  xor     ecx, ecx
0x140012e62  call    MupFlushKnownPrefixTable
0x140012e67  inc     cs:dword_14000A778
0x140012e6d  lea     rcx, Resource; Resource
0x140012e74  call    cs:__imp_ExReleaseResourceLite
0x140012e7b  nop     dword ptr [rax+rax+00h]
0x140012e80  call    cs:__imp_KeLeaveCriticalRegion
0x140012e87  nop     dword ptr [rax+rax+00h]
0x140012e8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012e93  lea     rax, WPP_GLOBAL_Control
0x140012e9a  cmp     rcx, rax
0x140012e9d  jz      short loc_140012EC0
0x140012e9f  test    dword ptr [rcx+2Ch], 4000000h
0x140012ea6  jz      short loc_140012EC0
0x140012ea8  mov     rcx, [rcx+18h]
0x140012eac  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x140012eb3  mov     edx, 18h
0x140012eb8  mov     r9, rbx
0x140012ebb  call    WPP_SF_q
0x140012ec0  add     rsp, 20h
0x140012ec4  pop     rbx
0x140012ec5  retn
```
