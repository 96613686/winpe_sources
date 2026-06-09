# AcknowledgePauseRequest

- ea: `0x140017a08`
- end: `0x140017aa6`
- name: `AcknowledgePauseRequest`
- size: `158`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400140b4`
- `0x14001e720`
- `0x14001ea10`

## callees

- `0x140017a08`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140017a7d`
- `ntoskrnl!KeSetEvent` at `0x140017a7d`
- `ntoskrnl!ObfDereferenceObject` at `0x140017a1e`
- `ntoskrnl!ObfDereferenceObject` at `0x140017a1e`
- `FLTMGR!FltReleasePushLockEx` at `0x140017a8e`
- `FLTMGR!FltReleasePushLockEx` at `0x140017a8e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140017a5b`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140017a5b`
- `FLTMGR!FltClose` at `0x140017a3b`
- `FLTMGR!FltClose` at `0x140017a3b`

## pseudocode

```c
__int64 __fastcall AcknowledgePauseRequest(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = *(void **)(a1 + 64);
  if ( v2 )
  {
    ObfDereferenceObject(v2);
    *(_QWORD *)(a1 + 64) = 0;
  }
  v3 = *(void **)(a1 + 56);
  if ( v3 )
  {
    FltClose(v3);
    *(_QWORD *)(a1 + 56) = 0;
  }
  FltAcquirePushLockExclusiveEx(a1 + 264, 0);
  *(_DWORD *)(a1 + 832) = 3;
  KeSetEvent((PRKEVENT)(a1 + 160), 0, 0);
  return FltReleasePushLockEx(a1 + 264, 0);
}

```

## disassembly

```asm
0x140017a08  mov     [rsp+arg_0], rbx
0x140017a0d  push    rdi
0x140017a0e  sub     rsp, 20h
0x140017a12  mov     rdi, rcx
0x140017a15  mov     rcx, [rcx+40h]; Object
0x140017a19  test    rcx, rcx
0x140017a1c  jz      short loc_140017A32
0x140017a1e  call    cs:__imp_ObfDereferenceObject
0x140017a25  nop     dword ptr [rax+rax+00h]
0x140017a2a  mov     qword ptr [rdi+40h], 0
0x140017a32  mov     rcx, [rdi+38h]; FileHandle
0x140017a36  test    rcx, rcx
0x140017a39  jz      short loc_140017A4F
0x140017a3b  call    cs:__imp_FltClose
0x140017a42  nop     dword ptr [rax+rax+00h]
0x140017a47  mov     qword ptr [rdi+38h], 0
0x140017a4f  lea     rbx, [rdi+108h]
0x140017a56  xor     edx, edx
0x140017a58  mov     rcx, rbx
0x140017a5b  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140017a62  nop     dword ptr [rax+rax+00h]
0x140017a67  lea     rcx, [rdi+0A0h]; Event
0x140017a6e  mov     dword ptr [rdi+340h], 3
0x140017a78  xor     r8d, r8d; Wait
0x140017a7b  xor     edx, edx; Increment
0x140017a7d  call    cs:__imp_KeSetEvent
0x140017a84  nop     dword ptr [rax+rax+00h]
0x140017a89  xor     edx, edx
0x140017a8b  mov     rcx, rbx
0x140017a8e  call    cs:__imp_FltReleasePushLockEx
0x140017a95  nop     dword ptr [rax+rax+00h]
0x140017a9a  mov     rbx, [rsp+28h+arg_0]
0x140017a9f  add     rsp, 20h
0x140017aa3  pop     rdi
0x140017aa4  retn
```
