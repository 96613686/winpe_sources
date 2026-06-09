# TxfCreateTxfFo

- ea: `0x140245de0`
- end: `0x140245ffb`
- name: `TxfCreateTxfFo`
- size: `539`
- prototype: `_DWORD *__fastcall(__int64, __int16, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14019dc78`

## callees

- `0x1400596c0`
- `0x140245de0`

## import_xrefs

- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1402b7fb6`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1402b7fb6`
- `ntoskrnl!ObfReferenceObject` at `0x140245e90`
- `ntoskrnl!ObfReferenceObject` at `0x140245e90`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b7fcd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b7fcd`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140245e13`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140245f03`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140245e13`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140245f03`
- `ntoskrnl!KeInitializeEvent` at `0x140245e7d`
- `ntoskrnl!KeInitializeEvent` at `0x140245e7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b7f9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b7f9e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140245e4b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140245e4b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140245ec4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140245f96`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140245ec4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140245f96`
- `ntoskrnl!ExReleaseResourceLite` at `0x140245f7f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140245fb4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b7f78`
- `ntoskrnl!ExReleaseResourceLite` at `0x140245f7f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140245fb4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b7f78`

## pseudocode

```c
_DWORD *__fastcall TxfCreateTxfFo(__int64 a1, __int16 a2, __int64 a3, int a4)
{
  __int64 v7; // rdi
  _DWORD *v8; // rbx
  struct _KEVENT *PoolWithTag; // rax
  PVOID v10; // rax

  v7 = *(_QWORD *)(a1 + 400);
  v8 = ExAllocateFromLookasideListEx(&TxfFoLookasideList);
  memset(v8, 0, 0x48u);
  *v8 = 4720407;
  PoolWithTag = (struct _KEVENT *)ExAllocatePoolWithTag((POOL_TYPE)528, 0x38u, 0x6D667854u);
  *((_QWORD *)v8 + 5) = PoolWithTag;
  PoolWithTag->Header.LockNV = 1;
  PoolWithTag->Header.WaitListHead.Flink = 0;
  LODWORD(PoolWithTag->Header.WaitListHead.Blink) = 0;
  KeInitializeEvent(PoolWithTag + 1, SynchronizationEvent, 0);
  ObfReferenceObject(*(PVOID *)(v7 + 232));
  *((_QWORD *)v8 + 7) = *(_QWORD *)(v7 + 232);
  *((_QWORD *)v8 + 8) = *(_QWORD *)(v7 + 304);
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 64LL) + 136LL), 1u);
  _InterlockedAdd((volatile signed __int32 *)(a3 + 4), 1u);
  *((_QWORD *)v8 + 1) = a3;
  if ( a2 == -1 )
  {
    if ( !a4 )
      v8[1] |= 4u;
  }
  else
  {
    ++v8[9];
    ++*(_DWORD *)(*(_QWORD *)(a3 + 16) + 32LL);
    if ( !*(_QWORD *)(a3 + 24) )
    {
      v10 = ExAllocateFromLookasideListEx(&NtfsScbNonpagedLookasideList);
      *(_QWORD *)(a3 + 24) = v10;
      memset(v10, 0, 0x48u);
      **(_WORD **)(a3 + 24) = 1799;
      *(_WORD *)(*(_QWORD *)(a3 + 24) + 2LL) = 72;
      *(_QWORD *)(*(_QWORD *)(a3 + 24) + 40LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 64LL) + 40LL)
                                                           + 16LL);
      *(_DWORD *)(*(_QWORD *)(a3 + 24) + 68LL) = 0;
      *(_QWORD *)(*(_QWORD *)(a3 + 24) + 56LL) = a3;
    }
  }
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 64LL) + 136LL));
  ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v7 + 24) + 80LL), 1u);
  if ( !*(_QWORD *)(v7 + 240) && (*(_DWORD *)(v7 + 12) & 1) == 0 )
  {
    v8[1] |= 0x20u;
    ++*(_DWORD *)(v7 + 4);
    *(_DWORD *)(v7 + 12) = *(_DWORD *)(v7 + 12) & 1 | ((*(_DWORD *)(v7 + 12) & 0xFFFFFFFE) + 2);
  }
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v7 + 24) + 80LL));
  return v8;
}

```

## disassembly

```asm
0x140245de0  mov     [rsp+arg_8], rbx
0x140245de5  mov     [rsp+arg_10], r8
0x140245dea  push    rsi
0x140245deb  push    rdi
0x140245dec  push    r12
0x140245dee  push    r14
0x140245df0  push    r15
0x140245df2  sub     rsp, 30h
0x140245df6  mov     r14d, r9d
0x140245df9  mov     rsi, r8
0x140245dfc  movzx   r15d, dx
0x140245e00  mov     [rsp+58h+var_38], 0
0x140245e05  mov     rdi, [rcx+190h]
0x140245e0c  lea     rcx, TxfFoLookasideList; Lookaside
0x140245e13  call    cs:__imp_ExAllocateFromLookasideListEx
0x140245e1a  nop     dword ptr [rax+rax+00h]
0x140245e1f  mov     rbx, rax
0x140245e22  mov     [rsp+58h+arg_0], rax
0x140245e27  xor     edx, edx; Val
0x140245e29  lea     r8d, [rdx+48h]; Size
0x140245e2d  mov     rcx, rax; void *
0x140245e30  call    memset
0x140245e35  mov     dword ptr [rbx], 480717h
0x140245e3b  mov     edx, 38h ; '8'; NumberOfBytes
0x140245e40  mov     ecx, 210h; PoolType
0x140245e45  mov     r8d, 6D667854h; Tag
0x140245e4b  call    cs:__imp_ExAllocatePoolWithTag
0x140245e52  nop     dword ptr [rax+rax+00h]
0x140245e57  mov     [rbx+28h], rax
0x140245e5b  mov     r12d, 1
0x140245e61  mov     [rax], r12d
0x140245e64  mov     qword ptr [rax+8], 0
0x140245e6c  mov     dword ptr [rax+10h], 0
0x140245e73  lea     rcx, [rax+18h]; Event
0x140245e77  xor     r8d, r8d; State
0x140245e7a  mov     edx, r12d; Type
0x140245e7d  call    cs:__imp_KeInitializeEvent
0x140245e84  nop     dword ptr [rax+rax+00h]
0x140245e89  mov     rcx, [rdi+0E8h]; Object
0x140245e90  call    cs:__imp_ObfReferenceObject
0x140245e97  nop     dword ptr [rax+rax+00h]
0x140245e9c  mov     rax, [rdi+0E8h]
0x140245ea3  mov     [rbx+38h], rax
0x140245ea7  mov     rax, [rdi+130h]
0x140245eae  mov     [rbx+40h], rax
0x140245eb2  mov     rax, [rsi+10h]
0x140245eb6  mov     rcx, [rax+40h]
0x140245eba  mov     dl, r12b; Wait
0x140245ebd  mov     rcx, [rcx+88h]; Resource
0x140245ec4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140245ecb  nop     dword ptr [rax+rax+00h]
0x140245ed0  mov     [rsp+58h+var_38], r12b
0x140245ed5  lock add [rsi+4], r12d
0x140245eda  mov     [rbx+8], rsi
0x140245ede  mov     eax, 0FFFFh
0x140245ee3  cmp     r15w, ax
0x140245ee7  jz      short loc_140245F67
0x140245ee9  add     [rbx+24h], r12d
0x140245eed  mov     rax, [rsi+10h]
0x140245ef1  add     [rax+20h], r12d
0x140245ef5  cmp     qword ptr [rsi+18h], 0
0x140245efa  jnz     short loc_140245F70
0x140245efc  lea     rcx, NtfsScbNonpagedLookasideList; Lookaside
0x140245f03  call    cs:__imp_ExAllocateFromLookasideListEx
0x140245f0a  nop     dword ptr [rax+rax+00h]
0x140245f0f  mov     [rsi+18h], rax
0x140245f13  lea     r14d, [r12+47h]
0x140245f18  mov     r8d, r14d; Size
0x140245f1b  xor     edx, edx; Val
0x140245f1d  mov     rcx, rax; void *
0x140245f20  call    memset
0x140245f25  mov     rax, [rsi+18h]
0x140245f29  mov     ecx, 707h
0x140245f2e  mov     [rax], cx
0x140245f31  mov     rax, [rsi+18h]
0x140245f35  mov     [rax+2], r14w
0x140245f3a  mov     rax, [rsi+10h]
0x140245f3e  mov     rcx, [rax+40h]
0x140245f42  mov     rax, [rcx+28h]
0x140245f46  mov     rcx, [rsi+18h]
0x140245f4a  mov     rax, [rax+10h]
0x140245f4e  mov     [rcx+28h], rax
0x140245f52  mov     rax, [rsi+18h]
0x140245f56  mov     dword ptr [rax+44h], 0
0x140245f5d  mov     rax, [rsi+18h]
0x140245f61  mov     [rax+38h], rsi
0x140245f65  jmp     short loc_140245F70
0x140245f67  test    r14d, r14d
0x140245f6a  jnz     short loc_140245F70
0x140245f6c  or      dword ptr [rbx+4], 4
0x140245f70  mov     rax, [rsi+10h]
0x140245f74  mov     rcx, [rax+40h]
0x140245f78  mov     rcx, [rcx+88h]; Resource
0x140245f7f  call    cs:__imp_ExReleaseResourceLite
0x140245f86  nop     dword ptr [rax+rax+00h]
0x140245f8b  mov     rcx, [rdi+18h]
0x140245f8f  add     rcx, 50h ; 'P'; Resource
0x140245f93  mov     dl, r12b; Wait
0x140245f96  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140245f9d  nop     dword ptr [rax+rax+00h]
0x140245fa2  cmp     qword ptr [rdi+0F0h], 0
0x140245faa  jz      short loc_140245FD6
0x140245fac  mov     rcx, [rdi+18h]
0x140245fb0  add     rcx, 50h ; 'P'; Resource
0x140245fb4  call    cs:__imp_ExReleaseResourceLite
0x140245fbb  nop     dword ptr [rax+rax+00h]
0x140245fc0  mov     rax, rbx
0x140245fc3  mov     rbx, [rsp+58h+arg_8]
0x140245fc8  add     rsp, 30h
0x140245fcc  pop     r15
0x140245fce  pop     r14
0x140245fd0  pop     r12
0x140245fd2  pop     rdi
0x140245fd3  pop     rsi
0x140245fd4  retn
0x140245fd6  mov     eax, [rdi+0Ch]
0x140245fd9  test    r12b, al
0x140245fdc  jnz     short loc_140245FAC
0x140245fde  or      dword ptr [rbx+4], 20h
0x140245fe2  add     [rdi+4], r12d
0x140245fe6  mov     eax, [rdi+0Ch]
0x140245fe9  mov     ecx, eax
0x140245feb  and     ecx, 0FFFFFFFEh
0x140245fee  add     ecx, 2
0x140245ff1  and     eax, r12d
0x140245ff4  or      ecx, eax
0x140245ff6  mov     [rdi+0Ch], ecx
0x140245ff9  jmp     short loc_140245FAC
0x1402b7f1d  push    rbx
0x1402b7f1f  push    rbp
0x1402b7f20  push    rdi
0x1402b7f21  sub     rsp, 20h
0x1402b7f25  mov     rbp, rdx
0x1402b7f28  movzx   edi, cl
0x1402b7f2b  mov     rbx, [rbp+60h]
0x1402b7f2f  test    cl, cl
0x1402b7f31  jz      short loc_1402B7F5F
0x1402b7f33  mov     al, cs:NtfsStatusDebugFlags
0x1402b7f39  test    rbx, rbx
0x1402b7f3c  jz      short loc_1402B7F5F
0x1402b7f3e  cmp     qword ptr [rbx+8], 0
0x1402b7f43  jz      short loc_1402B7F5F
0x1402b7f45  mov     rdx, [rbp+70h]
0x1402b7f49  lock dec dword ptr [rdx+4]
0x1402b7f4d  cmp     dword ptr [rbx+24h], 0
0x1402b7f51  jz      short loc_1402B7F5F
0x1402b7f53  mov     rax, [rdx+10h]
0x1402b7f57  mov     ecx, [rax+20h]
0x1402b7f5a  dec     ecx
0x1402b7f5c  mov     [rax+20h], ecx
0x1402b7f5f  cmp     byte ptr [rbp+20h], 0
0x1402b7f63  jz      short loc_1402B7F85
0x1402b7f65  mov     rax, [rbp+70h]
0x1402b7f69  mov     rcx, [rax+10h]
0x1402b7f6d  mov     rcx, [rcx+40h]
0x1402b7f71  mov     rcx, [rcx+88h]; Resource
0x1402b7f78  call    cs:__imp_ExReleaseResourceLite
0x1402b7f7f  nop     dword ptr [rax+rax+00h]
0x1402b7f84  nop
0x1402b7f85  mov     eax, edi
0x1402b7f87  test    dil, dil
0x1402b7f8a  jz      short loc_1402B7FDA
0x1402b7f8c  test    rbx, rbx
0x1402b7f8f  jz      short loc_1402B7FDA
0x1402b7f91  cmp     qword ptr [rbx+28h], 0
0x1402b7f96  jz      short loc_1402B7FAB
0x1402b7f98  xor     edx, edx; Tag
0x1402b7f9a  mov     rcx, [rbx+28h]; P
0x1402b7f9e  call    cs:__imp_ExFreePoolWithTag
0x1402b7fa5  nop     dword ptr [rax+rax+00h]
0x1402b7faa  nop
0x1402b7fab  cmp     qword ptr [rbx+38h], 0
0x1402b7fb0  jz      short loc_1402B7FC3
0x1402b7fb2  mov     rcx, [rbx+38h]; Object
0x1402b7fb6  call    cs:__imp_ObDereferenceObjectDeferDelete
0x1402b7fbd  nop     dword ptr [rax+rax+00h]
0x1402b7fc2  nop
0x1402b7fc3  mov     rdx, rbx; Entry
0x1402b7fc6  lea     rcx, TxfFoLookasideList; Lookaside
0x1402b7fcd  call    cs:__imp_ExFreeToLookasideListEx
0x1402b7fd4  nop     dword ptr [rax+rax+00h]
0x1402b7fd9  nop
0x1402b7fda  add     rsp, 20h
0x1402b7fde  pop     rdi
0x1402b7fdf  pop     rbp
0x1402b7fe0  pop     rbx
0x1402b7fe1  retn
```
