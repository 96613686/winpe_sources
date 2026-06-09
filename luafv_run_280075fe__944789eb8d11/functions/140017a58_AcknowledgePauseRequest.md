# AcknowledgePauseRequest

- ea: `0x140017a58`
- end: `0x140017af6`
- name: `AcknowledgePauseRequest`
- size: `158`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400140b4`
- `0x14001e770`
- `0x14001ea60`

## callees

- `0x140017a58`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140017acd`
- `ntoskrnl!KeSetEvent` at `0x140017acd`
- `ntoskrnl!ObfDereferenceObject` at `0x140017a6e`
- `ntoskrnl!ObfDereferenceObject` at `0x140017a6e`
- `FLTMGR!FltReleasePushLockEx` at `0x140017ade`
- `FLTMGR!FltReleasePushLockEx` at `0x140017ade`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140017aab`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140017aab`
- `FLTMGR!FltClose` at `0x140017a8b`
- `FLTMGR!FltClose` at `0x140017a8b`

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
0x140017a58  mov     [rsp+arg_0], rbx
0x140017a5d  push    rdi
0x140017a5e  sub     rsp, 20h
0x140017a62  mov     rdi, rcx
0x140017a65  mov     rcx, [rcx+40h]; Object
0x140017a69  test    rcx, rcx
0x140017a6c  jz      short loc_140017A82
0x140017a6e  call    cs:__imp_ObfDereferenceObject
0x140017a75  nop     dword ptr [rax+rax+00h]
0x140017a7a  mov     qword ptr [rdi+40h], 0
0x140017a82  mov     rcx, [rdi+38h]; FileHandle
0x140017a86  test    rcx, rcx
0x140017a89  jz      short loc_140017A9F
0x140017a8b  call    cs:__imp_FltClose
0x140017a92  nop     dword ptr [rax+rax+00h]
0x140017a97  mov     qword ptr [rdi+38h], 0
0x140017a9f  lea     rbx, [rdi+108h]
0x140017aa6  xor     edx, edx
0x140017aa8  mov     rcx, rbx
0x140017aab  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140017ab2  nop     dword ptr [rax+rax+00h]
0x140017ab7  lea     rcx, [rdi+0A0h]; Event
0x140017abe  mov     dword ptr [rdi+340h], 3
0x140017ac8  xor     r8d, r8d; Wait
0x140017acb  xor     edx, edx; Increment
0x140017acd  call    cs:__imp_KeSetEvent
0x140017ad4  nop     dword ptr [rax+rax+00h]
0x140017ad9  xor     edx, edx
0x140017adb  mov     rcx, rbx
0x140017ade  call    cs:__imp_FltReleasePushLockEx
0x140017ae5  nop     dword ptr [rax+rax+00h]
0x140017aea  mov     rbx, [rsp+28h+arg_0]
0x140017aef  add     rsp, 20h
0x140017af3  pop     rdi
0x140017af4  retn
```
