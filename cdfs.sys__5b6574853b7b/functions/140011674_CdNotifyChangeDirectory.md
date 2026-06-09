# CdNotifyChangeDirectory

- ea: `0x140011674`
- end: `0x14001173b`
- name: `CdNotifyChangeDirectory`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010ee0`

## callees

- `0x140001160`
- `0x1400181a4`
- `0x14001a400`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140011712`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b828`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011712`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b828`
- `ntoskrnl!FsRtlNotifyFullChangeDirectory` at `0x1400116fd`
- `ntoskrnl!FsRtlNotifyFullChangeDirectory` at `0x1400116fd`

## pseudocode

```c
__int64 __fastcall CdNotifyChangeDirectory(__int64 a1, IRP *a2, __int64 a3, void *a4)
{
  *(_DWORD *)(a1 + 32) |= 4u;
  CdAcquireResource(a1, *(_QWORD *)(a1 + 16) + 128LL, 0, 1);
  CdVerifyVcb(a1, *(_QWORD *)(a1 + 16));
  FsRtlNotifyFullChangeDirectory(
    *(PNOTIFY_SYNC *)(*(_QWORD *)(a1 + 16) + 400LL),
    (PLIST_ENTRY)(*(_QWORD *)(a1 + 16) + 408LL),
    a4,
    (PSTRING)(*(_QWORD *)(a3 + 48) + 88LL),
    *(_BYTE *)(a3 + 2) & 1,
    0,
    *(_DWORD *)(a3 + 16),
    a2,
    0,
    0);
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 16) + 128LL));
  CdCompleteRequest((void *)a1, 0, 0);
  return 259;
}

```

## disassembly

```asm
0x140011674  mov     [rsp+arg_0], rcx
0x140011679  push    rbx
0x14001167a  push    rsi
0x14001167b  push    rdi
0x14001167c  push    r14
0x14001167e  sub     rsp, 58h
0x140011682  mov     rsi, r9
0x140011685  mov     rdi, r8
0x140011688  mov     r14, rdx
0x14001168b  mov     rbx, rcx
0x14001168e  or      dword ptr [rcx+20h], 4
0x140011692  mov     rdx, [rcx+10h]
0x140011696  sub     rdx, 0FFFFFFFFFFFFFF80h
0x14001169a  mov     r9d, 1
0x1400116a0  xor     r8d, r8d
0x1400116a3  call    CdAcquireResource
0x1400116a8  nop
0x1400116a9  mov     rdx, [rbx+10h]
0x1400116ad  mov     rcx, rbx
0x1400116b0  call    CdVerifyVcb
0x1400116b5  mov     rcx, [rbx+10h]
0x1400116b9  mov     r8b, [rdi+2]
0x1400116bd  and     r8b, 1
0x1400116c1  mov     r9, [rdi+30h]
0x1400116c5  add     r9, 58h ; 'X'; FullDirectoryName
0x1400116c9  lea     rdx, [rcx+198h]; NotifyList
0x1400116d0  xor     r10d, r10d
0x1400116d3  mov     [rsp+78h+SubjectContext], r10; SubjectContext
0x1400116d8  mov     [rsp+78h+TraverseCallback], r10; TraverseCallback
0x1400116dd  mov     [rsp+78h+NotifyIrp], r14; NotifyIrp
0x1400116e2  mov     eax, [rdi+10h]
0x1400116e5  mov     [rsp+78h+CompletionFilter], eax; CompletionFilter
0x1400116e9  mov     [rsp+78h+IgnoreBuffer], r10b; IgnoreBuffer
0x1400116ee  mov     [rsp+78h+WatchTree], r8b; WatchTree
0x1400116f3  mov     r8, rsi; FsContext
0x1400116f6  mov     rcx, [rcx+190h]; NotifySync
0x1400116fd  call    cs:__imp_FsRtlNotifyFullChangeDirectory
0x140011704  nop     dword ptr [rax+rax+00h]
0x140011709  nop
0x14001170a  mov     rcx, [rbx+10h]
0x14001170e  sub     rcx, 0FFFFFFFFFFFFFF80h; Resource
0x140011712  call    cs:__imp_ExReleaseResourceLite
0x140011719  nop     dword ptr [rax+rax+00h]
0x14001171e  xor     r8d, r8d
0x140011721  xor     edx, edx
0x140011723  mov     rcx, rbx
0x140011726  call    CdCompleteRequest
0x14001172b  mov     eax, 103h
0x140011730  add     rsp, 58h
0x140011734  pop     r14
0x140011736  pop     rdi
0x140011737  pop     rsi
0x140011738  pop     rbx
0x140011739  retn
0x14001b810  push    rbp
0x14001b812  sub     rsp, 50h
0x14001b816  mov     rbp, rdx
0x14001b819  mov     rax, [rbp+80h]
0x14001b820  mov     rcx, [rax+10h]
0x14001b824  sub     rcx, 0FFFFFFFFFFFFFF80h; Resource
0x14001b828  call    cs:__imp_ExReleaseResourceLite
0x14001b82f  nop     dword ptr [rax+rax+00h]
0x14001b834  nop
0x14001b835  add     rsp, 50h
0x14001b839  pop     rbp
0x14001b83a  retn
```
