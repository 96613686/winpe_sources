# ConnectionTableCleanUp

- ea: `0x14002e540`
- end: `0x14002e892`
- name: `ConnectionTableCleanUp`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000bb00`

## callees

- `0x140005494`
- `0x14000550c`
- `0x14000a290`
- `0x1400254c8`
- `0x14002e540`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002e6c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e71e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e7b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e805`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e83b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e6c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e71e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e7b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e805`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e83b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e6a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e704`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e77b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e7dd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e814`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e6a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e704`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e77b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e7dd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e814`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e858`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e86e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e858`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e86e`
- `ntoskrnl!ExAllocatePool2` at `0x14002e5a1`
- `ntoskrnl!ExAllocatePool2` at `0x14002e621`
- `ntoskrnl!ExAllocatePool2` at `0x14002e5a1`
- `ntoskrnl!ExAllocatePool2` at `0x14002e621`
- `NDIS!NdisReleaseRWLock` at `0x14002e5f4`
- `NDIS!NdisReleaseRWLock` at `0x14002e674`
- `NDIS!NdisReleaseRWLock` at `0x14002e750`
- `NDIS!NdisReleaseRWLock` at `0x14002e5f4`
- `NDIS!NdisReleaseRWLock` at `0x14002e674`
- `NDIS!NdisReleaseRWLock` at `0x14002e750`
- `NDIS!NdisAcquireRWLockWrite` at `0x14002e573`
- `NDIS!NdisAcquireRWLockWrite` at `0x14002e573`

## pseudocode

```c
void ConnectionTableCleanUp()
{
  _QWORD *v0; // r14
  unsigned int v1; // ecx
  _QWORD *Pool2; // rsi
  unsigned int v3; // ecx
  char *v4; // rcx
  __int64 v5; // r12
  __int64 v6; // rbp
  char *v7; // rax
  KSPIN_LOCK *v8; // rdi
  KIRQL v9; // al
  char *v10; // rax
  char *v11; // r15
  KIRQL v12; // al
  char *v13; // rax
  __int64 i; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  bool v17; // zf
  __int64 j; // rbx
  __int64 v19; // rbp
  KIRQL v20; // al
  int v21; // ecx
  KIRQL v22; // al
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  v0 = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(ConnTableLock, &LockState, 0);
  v1 = *((_DWORD *)ConnectionTable + 2);
  if ( !v1 || (v0 = (_QWORD *)ExAllocatePool2(64, 8LL * v1, 1366188375)) != 0 )
  {
    Pool2 = 0;
    v3 = *((_DWORD *)ConnectionTable + 4);
    if ( !v3 || (Pool2 = (_QWORD *)ExAllocatePool2(64, 8LL * v3, 1366188375)) != 0 )
    {
      v4 = (char *)ConnectionTable;
      v5 = 0;
      v6 = 0;
      v7 = (char *)ConnectionTable + 24;
      v8 = (KSPIN_LOCK *)*((_QWORD *)ConnectionTable + 3);
      while ( v8 != (KSPIN_LOCK *)v7 )
      {
        v9 = KeAcquireSpinLockRaiseToDpc(v8 + 221);
        ++*((_DWORD *)v8 + 6);
        *((_BYTE *)v8 + 1776) = v9;
        *((_DWORD *)v8 + 5) = 1;
        KeReleaseSpinLock(v8 + 221, v9);
        v4 = (char *)ConnectionTable;
        Pool2[v6] = v8;
        v6 = (unsigned int)(v6 + 1);
        v8 = (KSPIN_LOCK *)*v8;
        v7 = v4 + 24;
      }
      v10 = v4 + 40;
      v11 = (char *)*((_QWORD *)v4 + 5);
      while ( v11 != v10 )
      {
        v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v11 + 60);
        ++*((_DWORD *)v11 - 57);
        v11[488] = v12;
        KeReleaseSpinLock((PKSPIN_LOCK)v11 + 60, v12);
        v13 = (char *)ConnectionTable;
        v0[v5] = v11 - 256;
        v5 = (unsigned int)(v5 + 1);
        v11 = *(char **)v11;
        v10 = v13 + 40;
      }
      NdisReleaseRWLock(ConnTableLock, &LockState);
      for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
      {
        CleanUpRoutesOnBundle((KSPIN_LOCK *)Pool2[i]);
        v15 = Pool2[i];
        if ( v15 )
        {
          *(_BYTE *)(Pool2[i] + 1776LL) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v15 + 1768));
          v16 = Pool2[i];
          v17 = (*(_DWORD *)(v16 + 24))-- == 1;
          if ( v17 )
            DoDerefBundleCBWork((PVOID)Pool2[i]);
          else
            KeReleaseSpinLock((PKSPIN_LOCK)(Pool2[i] + 1768LL), *(_BYTE *)(Pool2[i] + 1776LL));
        }
      }
      for ( j = 0; (unsigned int)j < (unsigned int)v5; j = (unsigned int)(j + 1) )
      {
        v19 = v0[j];
        v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v19 + 736));
        v21 = *(_DWORD *)(v19 + 36);
        *(_BYTE *)(v19 + 744) = v20;
        if ( (v21 & 2) != 0 )
        {
          --*(_DWORD *)(v19 + 28);
          *(_DWORD *)(v19 + 36) = v21 & 0xFFFFFFFD;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v19 + 736), v20);
        v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v19 + 736));
        v17 = (*(_DWORD *)(v19 + 28))-- == 1;
        *(_BYTE *)(v19 + 744) = v22;
        if ( v17 )
          DoDerefLinkCBWork((PVOID)v19);
        else
          KeReleaseSpinLock((PKSPIN_LOCK)(v19 + 736), v22);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids);
      }
      NdisReleaseRWLock(ConnTableLock, &LockState);
    }
    if ( v0 )
      ExFreePoolWithTag(v0, 0);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids);
    }
    NdisReleaseRWLock(ConnTableLock, &LockState);
  }
}

```

## disassembly

```asm
0x14002e540  mov     [rsp+arg_10], rbx
0x14002e545  mov     [rsp+arg_18], rbp
0x14002e54a  push    rsi
0x14002e54b  push    rdi
0x14002e54c  push    r12
0x14002e54e  push    r14
0x14002e550  push    r15
0x14002e552  sub     rsp, 20h
0x14002e556  mov     rcx, cs:ConnTableLock; Lock
0x14002e55d  lea     rdx, [rsp+48h+LockState]; LockState
0x14002e562  xor     eax, eax
0x14002e564  xor     r8d, r8d; Flags
0x14002e567  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x14002e56c  xor     r14d, r14d
0x14002e56f  mov     [rsp+48h+LockState.Flags], al
0x14002e573  call    cs:__imp_NdisAcquireRWLockWrite
0x14002e57a  nop     dword ptr [rax+rax+00h]
0x14002e57f  mov     rax, cs:ConnectionTable
0x14002e586  lea     ebx, [r14+40h]
0x14002e58a  mov     edi, 516E6157h
0x14002e58f  mov     ecx, [rax+8]
0x14002e592  test    ecx, ecx
0x14002e594  jz      short loc_14002E605
0x14002e596  mov     edx, ecx
0x14002e598  mov     r8d, edi
0x14002e59b  shl     rdx, 3
0x14002e59f  mov     ecx, ebx
0x14002e5a1  call    cs:__imp_ExAllocatePool2
0x14002e5a8  nop     dword ptr [rax+rax+00h]
0x14002e5ad  mov     r14, rax
0x14002e5b0  test    rax, rax
0x14002e5b3  jnz     short loc_14002E605
0x14002e5b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e5bc  lea     rax, WPP_GLOBAL_Control
0x14002e5c3  cmp     rcx, rax
0x14002e5c6  jz      short loc_14002E5E8
0x14002e5c8  mov     eax, [rcx+2Ch]
0x14002e5cb  test    bl, al
0x14002e5cd  jz      short loc_14002E5E8
0x14002e5cf  cmp     byte ptr [rcx+29h], 2
0x14002e5d3  jb      short loc_14002E5E8
0x14002e5d5  mov     rcx, [rcx+18h]
0x14002e5d9  lea     edx, [rbx-36h]
0x14002e5dc  lea     r8, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids
0x14002e5e3  call    WPP_SF_
0x14002e5e8  mov     rcx, cs:ConnTableLock; Lock
0x14002e5ef  lea     rdx, [rsp+48h+LockState]; LockState
0x14002e5f4  call    cs:__imp_NdisReleaseRWLock
0x14002e5fb  nop     dword ptr [rax+rax+00h]
0x14002e600  jmp     loc_14002E87A
0x14002e605  mov     rax, cs:ConnectionTable
0x14002e60c  xor     esi, esi
0x14002e60e  mov     ecx, [rax+10h]
0x14002e611  test    ecx, ecx
0x14002e613  jz      short loc_14002E685
0x14002e615  mov     edx, ecx
0x14002e617  mov     r8d, edi
0x14002e61a  shl     rdx, 3
0x14002e61e  mov     rcx, rbx
0x14002e621  call    cs:__imp_ExAllocatePool2
0x14002e628  nop     dword ptr [rax+rax+00h]
0x14002e62d  mov     rsi, rax
0x14002e630  test    rax, rax
0x14002e633  jnz     short loc_14002E685
0x14002e635  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e63c  lea     rax, WPP_GLOBAL_Control
0x14002e643  cmp     rcx, rax
0x14002e646  jz      short loc_14002E668
0x14002e648  mov     edx, [rcx+2Ch]
0x14002e64b  test    bl, dl
0x14002e64d  jz      short loc_14002E668
0x14002e64f  cmp     byte ptr [rcx+29h], 2
0x14002e653  jb      short loc_14002E668
0x14002e655  mov     rcx, [rcx+18h]
0x14002e659  lea     edx, [rsi+0Bh]
0x14002e65c  lea     r8, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids
0x14002e663  call    WPP_SF_
0x14002e668  mov     rcx, cs:ConnTableLock; Lock
0x14002e66f  lea     rdx, [rsp+48h+LockState]; LockState
0x14002e674  call    cs:__imp_NdisReleaseRWLock
0x14002e67b  nop     dword ptr [rax+rax+00h]
0x14002e680  jmp     loc_14002E84E
0x14002e685  mov     rcx, cs:ConnectionTable
0x14002e68c  xor     r12d, r12d
0x14002e68f  xor     ebp, ebp
0x14002e691  lea     rax, [rcx+18h]
0x14002e695  mov     rdi, [rax]
0x14002e698  jmp     short loc_14002E6E5
0x14002e69a  lea     rbx, [rdi+6E8h]
0x14002e6a1  mov     rcx, rbx; SpinLock
0x14002e6a4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002e6ab  nop     dword ptr [rax+rax+00h]
0x14002e6b0  inc     dword ptr [rdi+18h]
0x14002e6b3  mov     rcx, rbx; SpinLock
0x14002e6b6  mov     dl, al; NewIrql
0x14002e6b8  mov     [rdi+6F0h], al
0x14002e6be  mov     dword ptr [rdi+14h], 1
0x14002e6c5  call    cs:__imp_KeReleaseSpinLock
0x14002e6cc  nop     dword ptr [rax+rax+00h]
0x14002e6d1  mov     rcx, cs:ConnectionTable
0x14002e6d8  mov     [rsi+rbp*8], rdi
0x14002e6dc  inc     ebp
0x14002e6de  mov     rdi, [rdi]
0x14002e6e1  lea     rax, [rcx+18h]
0x14002e6e5  cmp     rdi, rax
0x14002e6e8  jnz     short loc_14002E69A
0x14002e6ea  lea     rax, [rcx+28h]
0x14002e6ee  mov     r15, [rax]
0x14002e6f1  jmp     short loc_14002E73F
0x14002e6f3  lea     rdi, [r15-100h]
0x14002e6fa  lea     rbx, [rdi+2E0h]
0x14002e701  mov     rcx, rbx; SpinLock
0x14002e704  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002e70b  nop     dword ptr [rax+rax+00h]
0x14002e710  inc     dword ptr [rdi+1Ch]
0x14002e713  mov     rcx, rbx; SpinLock
0x14002e716  mov     dl, al; NewIrql
0x14002e718  mov     [rdi+2E8h], al
0x14002e71e  call    cs:__imp_KeReleaseSpinLock
0x14002e725  nop     dword ptr [rax+rax+00h]
0x14002e72a  mov     rax, cs:ConnectionTable
0x14002e731  mov     [r14+r12*8], rdi
0x14002e735  inc     r12d
0x14002e738  mov     r15, [r15]
0x14002e73b  add     rax, 28h ; '('
0x14002e73f  cmp     r15, rax
0x14002e742  jnz     short loc_14002E6F3
0x14002e744  mov     rcx, cs:ConnTableLock; Lock
0x14002e74b  lea     rdx, [rsp+48h+LockState]; LockState
0x14002e750  call    cs:__imp_NdisReleaseRWLock
0x14002e757  nop     dword ptr [rax+rax+00h]
0x14002e75c  xor     ebx, ebx
0x14002e75e  test    ebp, ebp
0x14002e760  jz      short loc_14002E7C8
0x14002e762  mov     rcx, [rsi+rbx*8]; Entry
0x14002e766  call    CleanUpRoutesOnBundle
0x14002e76b  mov     rcx, [rsi+rbx*8]
0x14002e76f  test    rcx, rcx
0x14002e772  jz      short loc_14002E7C2
0x14002e774  add     rcx, 6E8h; SpinLock
0x14002e77b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002e782  nop     dword ptr [rax+rax+00h]
0x14002e787  mov     rcx, [rsi+rbx*8]
0x14002e78b  mov     [rcx+6F0h], al
0x14002e791  mov     rax, [rsi+rbx*8]
0x14002e795  add     dword ptr [rax+18h], 0FFFFFFFFh
0x14002e799  mov     rdx, [rsi+rbx*8]
0x14002e79d  jnz     short loc_14002E7A9
0x14002e79f  mov     rcx, rdx; Entry
0x14002e7a2  call    DoDerefBundleCBWork
0x14002e7a7  jmp     short loc_14002E7C2
0x14002e7a9  lea     rcx, [rdx+6E8h]; SpinLock
0x14002e7b0  mov     dl, [rdx+6F0h]; NewIrql
0x14002e7b6  call    cs:__imp_KeReleaseSpinLock
0x14002e7bd  nop     dword ptr [rax+rax+00h]
0x14002e7c2  inc     ebx
0x14002e7c4  cmp     ebx, ebp
0x14002e7c6  jb      short loc_14002E762
0x14002e7c8  xor     ebx, ebx
0x14002e7ca  test    r12d, r12d
0x14002e7cd  jz      short loc_14002E84E
0x14002e7cf  mov     rbp, [r14+rbx*8]
0x14002e7d3  lea     r15, [rbp+2E0h]
0x14002e7da  mov     rcx, r15; SpinLock
0x14002e7dd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002e7e4  nop     dword ptr [rax+rax+00h]
0x14002e7e9  mov     ecx, [rbp+24h]
0x14002e7ec  mov     [rbp+2E8h], al
0x14002e7f2  test    cl, 2
0x14002e7f5  jz      short loc_14002E800
0x14002e7f7  dec     dword ptr [rbp+1Ch]
0x14002e7fa  and     ecx, 0FFFFFFFDh
0x14002e7fd  mov     [rbp+24h], ecx
0x14002e800  mov     dl, al; NewIrql
0x14002e802  mov     rcx, r15; SpinLock
0x14002e805  call    cs:__imp_KeReleaseSpinLock
0x14002e80c  nop     dword ptr [rax+rax+00h]
0x14002e811  mov     rcx, r15; SpinLock
0x14002e814  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002e81b  nop     dword ptr [rax+rax+00h]
0x14002e820  add     dword ptr [rbp+1Ch], 0FFFFFFFFh
0x14002e824  mov     [rbp+2E8h], al
0x14002e82a  jnz     short loc_14002E836
0x14002e82c  mov     rcx, rbp; Entry
0x14002e82f  call    DoDerefLinkCBWork
0x14002e834  jmp     short loc_14002E847
0x14002e836  mov     dl, al; NewIrql
0x14002e838  mov     rcx, r15; SpinLock
0x14002e83b  call    cs:__imp_KeReleaseSpinLock
0x14002e842  nop     dword ptr [rax+rax+00h]
0x14002e847  inc     ebx
0x14002e849  cmp     ebx, r12d
0x14002e84c  jb      short loc_14002E7CF
0x14002e84e  test    r14, r14
0x14002e851  jz      short loc_14002E864
0x14002e853  xor     edx, edx; Tag
0x14002e855  mov     rcx, r14; P
0x14002e858  call    cs:__imp_ExFreePoolWithTag
0x14002e85f  nop     dword ptr [rax+rax+00h]
0x14002e864  test    rsi, rsi
0x14002e867  jz      short loc_14002E87A
0x14002e869  xor     edx, edx; Tag
0x14002e86b  mov     rcx, rsi; P
0x14002e86e  call    cs:__imp_ExFreePoolWithTag
0x14002e875  nop     dword ptr [rax+rax+00h]
0x14002e87a  mov     rbx, [rsp+48h+arg_10]
0x14002e87f  mov     rbp, [rsp+48h+arg_18]
0x14002e884  add     rsp, 20h
0x14002e888  pop     r15
0x14002e88a  pop     r14
0x14002e88c  pop     r12
0x14002e88e  pop     rdi
0x14002e88f  pop     rsi
0x14002e890  retn
```
