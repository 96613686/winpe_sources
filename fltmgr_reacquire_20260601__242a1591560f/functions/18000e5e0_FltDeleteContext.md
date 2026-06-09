# FltDeleteContext

- ea: `0x18000e5e0`
- end: `0x18000eb6e`
- name: `FltDeleteContext`
- size: `1422`
- prototype: `void __stdcall(PFLT_CONTEXT Context)`
- caller_count: `6`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180054680`
- `0x180055500`
- `0x180055960`
- `0x18006c670`
- `0x18006f880`
- `0x18007dfb0`

## callees

- `0x18000d2c0`
- `0x18000d600`
- `0x18000e5e0`
- `0x18000f5b0`
- `0x18000f9d0`
- `0x180010540`
- `0x180014c10`
- `0x18005dcc0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x18000eb61`
- `ntoskrnl!KeBugCheckEx` at `0x18000eb61`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000e942`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000e958`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000e942`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000e958`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18000e623`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18000e840`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180025b54`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18000e623`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18000e840`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180025b54`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000e69a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000e702`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000e79a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000e8ae`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000e8e1`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000e9ed`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180025ba4`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000e69a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000e702`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000e79a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000e8ae`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000e8e1`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000e9ed`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180025ba4`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000e7c0`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000e7c0`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18000e635`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18000e852`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x180025b69`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18000e635`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18000e852`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x180025b69`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000e68e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000e6f6`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000e78e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000e8a2`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000e8d5`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000e9e1`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180025b98`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000e68e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000e6f6`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000e78e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000e8a2`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000e8d5`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000e9e1`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180025b98`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000e8f6`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000e909`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000e8f6`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000e909`
- `ntoskrnl!IoUninitializeWorkItem` at `0x18000e928`
- `ntoskrnl!IoUninitializeWorkItem` at `0x18000e928`
- `ntoskrnl!RtlDelete` at `0x18000e668`
- `ntoskrnl!RtlDelete` at `0x18000e87c`
- `ntoskrnl!RtlDelete` at `0x18000e668`
- `ntoskrnl!RtlDelete` at `0x18000e87c`

## pseudocode

```c
void __stdcall FltDeleteContext(PFLT_CONTEXT Context)
{
  __int64 v1; // rax
  char *v2; // rsi
  signed __int64 v3; // rbp
  PRTL_SPLAY_LINKS *v4; // rdi
  int v5; // ecx
  ULONG_PTR v6; // rdi
  __int64 v7; // rcx
  _QWORD *v8; // rdx
  signed __int64 v9; // rax
  char *v10; // rbp
  __int64 v11; // rdi
  PRTL_SPLAY_LINKS *v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 v15; // rax
  _QWORD *v16; // rdx
  signed __int64 v17; // rax
  void *v18; // rbp
  signed __int64 v19; // rax
  void *v20; // rbp
  signed __int64 v21; // rax
  signed __int64 v22; // rbp
  signed __int64 v23; // rdx
  signed __int64 v24; // rcx
  signed __int64 v25; // rax
  signed __int64 v26; // rbp

  v1 = *((_QWORD *)Context - 11);
  v2 = (char *)Context - 96;
  if ( *(_WORD *)(v1 + 24) == 16 )
  {
    v3 = _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 2, 0, *((_QWORD *)v2 + 2));
    if ( v3 )
    {
      KeEnterGuardedRegion();
      ExAcquireAutoExpandPushLockExclusive(v3 + 72, 0);
      if ( FltpVelocity
        && (*((_QWORD *)v2 + 6) != 51918 || v2 != *((char **)v2 + 5) ? (v7 = 0) : (v7 = *((_QWORD *)v2 + 3)),
            v7 == v3 + 224 && (v8 = (_QWORD *)*((_QWORD *)v2 + 4)) != 0) )
      {
        do
          _m_prefetchw(v8);
        while ( (_InterlockedOr64(v8, 1u) & 1) != 0 );
        v6 = v8[1];
        v8[1] = 0;
        _InterlockedAnd64(v8, 0);
        *(_DWORD *)(v6 + 72) &= ~0x10000u;
        *(_QWORD *)(v6 + 48) = 0;
        *(_OWORD *)(v6 + 24) = 0;
        *(_QWORD *)(v6 + 40) = 0;
        ExReleaseAutoExpandPushLockExclusive(v3 + 72, 0);
        KeLeaveGuardedRegion();
      }
      else if ( (*((_DWORD *)v2 + 18) & 0x10000) != 0 )
      {
        v4 = (PRTL_SPLAY_LINKS *)*((_QWORD *)v2 + 6);
        *v4 = RtlDelete((PRTL_SPLAY_LINKS)v2 + 1);
        if ( (*((_DWORD *)v2 + 18) & 0x10000) != 0 )
          _InterlockedAnd((volatile signed __int32 *)v2 + 18, 0xFFFEFFFF);
        ExReleaseAutoExpandPushLockExclusive(v3 + 72, 0);
        KeLeaveGuardedRegion();
        v6 = (ULONG_PTR)v2;
      }
      else
      {
        ExReleaseAutoExpandPushLockExclusive(v3 + 72, 0);
        KeLeaveGuardedRegion();
        v6 = 0;
      }
      if ( (byte_1800404C2 & 1) != 0 )
        McTemplateU0spdd_EtwWriteTransfer(
          v5,
          (unsigned int)StreamListCtrlSup_c754,
          (unsigned int)"FltpReleaseStreamListCtrl",
          v3,
          *(_DWORD *)(v3 + 64),
          *(_DWORD *)(v3 + 68));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 68), 0xFFFFFFFF) == 1 )
      {
        ExCleanupAutoExpandPushLock(v3 + 72);
        ExCleanupAutoExpandPushLock(v3 + 368);
        v13 = *(_QWORD *)(v3 + 360);
        if ( v13 )
        {
          IoUninitializeWorkItem(*(PIO_WORKITEM *)(v13 + 320));
          ExFreeToNPagedLookasideList(&stru_18003F1C0, *(PVOID *)(v3 + 360));
        }
        ExFreeToNPagedLookasideList(&stru_18003EB40, (PVOID)v3);
      }
LABEL_11:
      if ( v6 && _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 80), 0xFFFFFFFF) == 1 )
      {
        if ( (*(_DWORD *)(v6 + 72) & 0x10000) != 0 )
          KeBugCheckEx(0xF5u, 0x6Du, v6 + 96, v6, 0);
        if ( KeGetCurrentIrql() >= 2u )
        {
          *(_DWORD *)(v6 + 72) |= 2u;
          *(_WORD *)(v6 + 24) = -3804;
          *(_WORD *)(v6 + 26) = 40;
          *(_QWORD *)(v6 + 48) = DoFreeContext;
          *(_QWORD *)(v6 + 56) = v6;
          *(_QWORD *)(v6 + 32) = 0;
          FltpQueueThrottledWorkItem(v6 + 24, 1);
        }
        else
        {
          DoFreeContext((PVOID)v6);
        }
      }
    }
  }
  else
  {
    switch ( *(_WORD *)(v1 + 24) )
    {
      case 1:
        v25 = _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 2, 0, *((_QWORD *)v2 + 2));
        v22 = v25;
        if ( v25 )
        {
          v23 = v25 + 1320;
          v24 = v25 + 1336;
          goto LABEL_53;
        }
        break;
      case 2:
        v26 = _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 2, 0, *((_QWORD *)v2 + 2));
        if ( v26 )
        {
          v6 = 0;
          KeEnterGuardedRegion();
          ExAcquireAutoExpandPushLockExclusive(v26 + 136, 0);
          if ( (*((_DWORD *)v2 + 18) & 0x10000) != 0 )
          {
            *(_QWORD *)(v26 + 152) = 0;
            v6 = (ULONG_PTR)v2;
            *((_DWORD *)v2 + 18) &= ~0x10000u;
          }
          ExReleaseAutoExpandPushLockExclusive(v26 + 136, 0);
          KeLeaveGuardedRegion();
          FltpObjectPointerDereference(v26);
          goto LABEL_11;
        }
        break;
      case 4:
        v17 = _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 2, 0, *((_QWORD *)v2 + 2));
        v18 = (void *)v17;
        if ( v17 )
        {
          v6 = FltpDeleteContextNodeFromList(v17 + 88, v17 + 72, v2);
          FltpReleaseFileListCtrl(v18);
          goto LABEL_11;
        }
        break;
      case 8:
        v19 = _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 2, 0, *((_QWORD *)v2 + 2));
        v20 = (void *)v19;
        if ( v19 )
        {
          v6 = FltpDeleteContextNodeFromList(v19 + 88, v19 + 72, v2);
          FltpReleaseStreamListCtrl(v20);
          goto LABEL_11;
        }
        break;
      case 0x20:
        v21 = _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 2, 0, *((_QWORD *)v2 + 2));
        v22 = v21;
        if ( v21 )
        {
          v23 = v21 + 136;
          v24 = v21 + 160;
LABEL_53:
          v6 = FltpDeleteContextNodeFromList(v24, v23, v2);
          FltpObjectPointerDereference(v22);
          goto LABEL_11;
        }
        break;
      case 0x40:
        v9 = _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 2, 0, *((_QWORD *)v2 + 2));
        v10 = (char *)v9;
        if ( v9 )
        {
          v11 = *(_QWORD *)(v9 + 360);
          KeEnterGuardedRegion();
          ExAcquireAutoExpandPushLockExclusive(v10 + 72, 0);
          if ( FltpVelocity
            && ((v14 = v11 + 40, *((_QWORD *)v2 + 6) != 51918) || v2 != *((char **)v2 + 5)
              ? (v15 = 0)
              : (v15 = *((_QWORD *)v2 + 3)),
                v15 == v14 && (v16 = (_QWORD *)*((_QWORD *)v2 + 4)) != 0) )
          {
            do
              _m_prefetchw(v16);
            while ( (_InterlockedOr64(v16, 1u) & 1) != 0 );
            v6 = v16[1];
            v16[1] = 0;
            _InterlockedAnd64(v16, 0);
            *(_DWORD *)(v6 + 72) &= ~0x10000u;
            *(_QWORD *)(v6 + 48) = 0;
            *(_OWORD *)(v6 + 24) = 0;
            *(_QWORD *)(v6 + 40) = 0;
            ExReleaseAutoExpandPushLockExclusive(v10 + 72, 0);
            KeLeaveGuardedRegion();
            FltpReleaseStreamListCtrl(v10);
          }
          else
          {
            if ( (*((_DWORD *)v2 + 18) & 0x10000) != 0 )
            {
              v12 = (PRTL_SPLAY_LINKS *)*((_QWORD *)v2 + 6);
              *v12 = RtlDelete((PRTL_SPLAY_LINKS)v2 + 1);
              if ( (*((_DWORD *)v2 + 18) & 0x10000) != 0 )
                _InterlockedAnd((volatile signed __int32 *)v2 + 18, 0xFFFEFFFF);
              ExReleaseAutoExpandPushLockExclusive(v10 + 72, 0);
              KeLeaveGuardedRegion();
              v6 = (ULONG_PTR)v2;
            }
            else
            {
              ExReleaseAutoExpandPushLockExclusive(v10 + 72, 0);
              KeLeaveGuardedRegion();
              v6 = 0;
            }
            FltpReleaseStreamListCtrl(v10);
          }
          goto LABEL_11;
        }
        break;
      default:
        return;
    }
  }
}

```

## disassembly

```asm
0x18000e5e0  mov     [rsp+arg_18], rbx
0x18000e5e5  push    rbp
0x18000e5e6  push    rsi
0x18000e5e7  push    rdi
0x18000e5e8  push    r14
0x18000e5ea  push    r15
0x18000e5ec  sub     rsp, 30h
0x18000e5f0  mov     rax, [rcx-58h]
0x18000e5f4  lea     rsi, [rcx-60h]
0x18000e5f8  mov     ebx, 0FFFFFFFFh
0x18000e5fd  movzx   ecx, word ptr [rax+18h]
0x18000e601  cmp     ecx, 10h
0x18000e604  jnz     loc_18000E7EE
0x18000e60a  mov     rax, [rsi+10h]
0x18000e60e  xor     r15d, r15d
0x18000e611  lock cmpxchg [rsi+10h], r15
0x18000e617  mov     rbp, rax
0x18000e61a  test    rax, rax
0x18000e61d  jz      def_18000E815; jumptable 000000018000E815 default case, cases 3,5-7,9-31,33-63
0x18000e623  call    cs:__imp_KeEnterGuardedRegion
0x18000e62a  nop     dword ptr [rax+rax+00h]
0x18000e62f  xor     edx, edx
0x18000e631  lea     rcx, [rbp+48h]
0x18000e635  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x18000e63c  nop     dword ptr [rax+rax+00h]
0x18000e641  cmp     cs:FltpVelocity, r15b
0x18000e648  jnz     loc_18000E713
0x18000e64e  test    dword ptr [rsi+48h], 10000h
0x18000e655  jz      loc_18000E6F0
0x18000e65b  mov     rdi, [rsi+30h]
0x18000e65f  lea     rcx, [rsi+18h]; Links
0x18000e663  mov     [rsp+58h+arg_10], r13
0x18000e668  call    cs:__imp_RtlDelete
0x18000e66f  nop     dword ptr [rax+rax+00h]
0x18000e674  mov     [rdi], rax
0x18000e677  mov     eax, [rsi+48h]
0x18000e67a  bt      eax, 10h
0x18000e67e  jnb     short loc_18000E688
0x18000e680  lock and dword ptr [rsi+48h], 0FFFEFFFFh
0x18000e688  xor     edx, edx
0x18000e68a  lea     rcx, [rbp+48h]
0x18000e68e  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x18000e695  nop     dword ptr [rax+rax+00h]
0x18000e69a  call    cs:__imp_KeLeaveGuardedRegion
0x18000e6a1  nop     dword ptr [rax+rax+00h]
0x18000e6a6  mov     r13, [rsp+58h+arg_10]
0x18000e6ab  mov     rdi, rsi
0x18000e6ae  test    cs:byte_1800404C2, 1
0x18000e6b5  jnz     loc_18000EB22
0x18000e6bb  mov     eax, ebx
0x18000e6bd  lock xadd [rbp+44h], eax
0x18000e6c2  cmp     eax, 1
0x18000e6c5  jz      loc_18000E8F2
0x18000e6cb  test    rdi, rdi
0x18000e6ce  jz      short def_18000E815; jumptable 000000018000E815 default case, cases 3,5-7,9-31,33-63
0x18000e6d0  lock xadd [rdi+50h], ebx
0x18000e6d5  cmp     ebx, 1
0x18000e6d8  jz      loc_18000E7B3
0x18000e6de  mov     rbx, [rsp+58h+arg_18]; jumptable 000000018000E815 default case, cases 3,5-7,9-31,33-63
0x18000e6e3  add     rsp, 30h
0x18000e6e7  pop     r15
0x18000e6e9  pop     r14
0x18000e6eb  pop     rdi
0x18000e6ec  pop     rsi
0x18000e6ed  pop     rbp
0x18000e6ee  retn
0x18000e6f0  xor     edx, edx
0x18000e6f2  lea     rcx, [rbp+48h]
0x18000e6f6  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x18000e6fd  nop     dword ptr [rax+rax+00h]
0x18000e702  call    cs:__imp_KeLeaveGuardedRegion
0x18000e709  nop     dword ptr [rax+rax+00h]
0x18000e70e  mov     rdi, r15
0x18000e711  jmp     short loc_18000E6AE
0x18000e713  cmp     qword ptr [rsi+30h], 0CACEh
0x18000e71b  jnz     loc_18000E7AB
0x18000e721  cmp     rsi, [rsi+28h]
0x18000e725  jnz     loc_18000E7AB
0x18000e72b  mov     rcx, [rsi+18h]
0x18000e72f  lea     rax, [rbp+0E0h]
0x18000e736  cmp     rcx, rax
0x18000e739  jnz     loc_18000E64E
0x18000e73f  mov     rdx, [rsi+20h]
0x18000e743  test    rdx, rdx
0x18000e746  jz      loc_18000E64E
0x18000e74c  prefetchw byte ptr [rdx]
0x18000e74f  mov     rax, [rdx]
0x18000e752  mov     rcx, rax
0x18000e755  or      rcx, 1
0x18000e759  lock cmpxchg [rdx], rcx
0x18000e75e  jnz     short loc_18000E752
0x18000e760  test    al, 1
0x18000e762  jnz     short loc_18000E74C
0x18000e764  mov     rdi, [rdx+8]
0x18000e768  mov     [rdx+8], r15
0x18000e76c  lock and [rdx], r15
0x18000e770  and     dword ptr [rdi+48h], 0FFFEFFFFh
0x18000e777  lea     rcx, [rbp+48h]
0x18000e77b  xorps   xmm0, xmm0
0x18000e77e  mov     [rdi+30h], r15
0x18000e782  xor     eax, eax
0x18000e784  xor     edx, edx
0x18000e786  movups  xmmword ptr [rdi+18h], xmm0
0x18000e78a  mov     [rdi+28h], rax
0x18000e78e  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x18000e795  nop     dword ptr [rax+rax+00h]
0x18000e79a  call    cs:__imp_KeLeaveGuardedRegion
0x18000e7a1  nop     dword ptr [rax+rax+00h]
0x18000e7a6  jmp     loc_18000E6AE
0x18000e7ab  mov     rcx, r15
0x18000e7ae  jmp     loc_18000E72F
0x18000e7b3  test    dword ptr [rdi+48h], 10000h
0x18000e7ba  jnz     loc_18000EB4B
0x18000e7c0  call    cs:__imp_KeGetCurrentIrql
0x18000e7c7  nop     dword ptr [rax+rax+00h]
0x18000e7cc  cmp     al, 2
0x18000e7ce  jnb     loc_18000EA13
0x18000e7d4  mov     rcx, rdi; P
0x18000e7d7  call    DoFreeContext
0x18000e7dc  mov     rbx, [rsp+58h+arg_18]
0x18000e7e1  add     rsp, 30h
0x18000e7e5  pop     r15
0x18000e7e7  pop     r14
0x18000e7e9  pop     rdi
0x18000e7ea  pop     rsi
0x18000e7eb  pop     rbp
0x18000e7ec  retn
0x18000e7ee  dec     ecx; switch 64 cases
0x18000e7f0  cmp     ecx, 3Fh
0x18000e7f3  ja      def_18000E815; jumptable 000000018000E815 default case, cases 3,5-7,9-31,33-63
0x18000e7f9  movsxd  rax, ecx
0x18000e7fc  lea     rdx, cs:180000000h
0x18000e803  movzx   eax, ds:(byte_18003182C - 180000000h)[rdx+rax]
0x18000e80b  mov     ecx, ds:(jpt_18000E815 - 180000000h)[rdx+rax*4]
0x18000e812  add     rcx, rdx
0x18000e815  jmp     rcx; switch jump
0x18000e81b  mov     rax, [rsi+10h]; jumptable 000000018000E815 case 64
0x18000e81f  xor     r15d, r15d
0x18000e822  lock cmpxchg [rsi+10h], r15
0x18000e828  mov     rbp, rax
0x18000e82b  test    rax, rax
0x18000e82e  jz      def_18000E815; jumptable 000000018000E815 default case, cases 3,5-7,9-31,33-63
0x18000e834  mov     rdi, [rax+168h]
0x18000e83b  mov     [rsp+58h+arg_8], r12
0x18000e840  call    cs:__imp_KeEnterGuardedRegion
0x18000e847  nop     dword ptr [rax+rax+00h]
0x18000e84c  xor     edx, edx
0x18000e84e  lea     rcx, [rbp+48h]
0x18000e852  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x18000e859  nop     dword ptr [rax+rax+00h]
0x18000e85e  cmp     cs:FltpVelocity, r15b
0x18000e865  jnz     loc_18000E969
0x18000e86b  test    dword ptr [rsi+48h], 10000h
0x18000e872  jz      short loc_18000E8CF
0x18000e874  mov     rdi, [rsi+30h]
0x18000e878  lea     rcx, [rsi+18h]; Links
0x18000e87c  call    cs:__imp_RtlDelete
0x18000e883  nop     dword ptr [rax+rax+00h]
0x18000e888  mov     [rdi], rax
0x18000e88b  mov     eax, [rsi+48h]
0x18000e88e  bt      eax, 10h
0x18000e892  jnb     short loc_18000E89C
0x18000e894  lock and dword ptr [rsi+48h], 0FFFEFFFFh
0x18000e89c  xor     edx, edx
0x18000e89e  lea     rcx, [rbp+48h]
0x18000e8a2  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x18000e8a9  nop     dword ptr [rax+rax+00h]
0x18000e8ae  call    cs:__imp_KeLeaveGuardedRegion
0x18000e8b5  nop     dword ptr [rax+rax+00h]
0x18000e8ba  mov     rdi, rsi
0x18000e8bd  mov     rcx, rbp; Entry
0x18000e8c0  call    FltpReleaseStreamListCtrl
0x18000e8c5  mov     r12, [rsp+58h+arg_8]
0x18000e8ca  jmp     loc_18000E6CB
0x18000e8cf  xor     edx, edx
0x18000e8d1  lea     rcx, [rbp+48h]
0x18000e8d5  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x18000e8dc  nop     dword ptr [rax+rax+00h]
0x18000e8e1  call    cs:__imp_KeLeaveGuardedRegion
0x18000e8e8  nop     dword ptr [rax+rax+00h]
0x18000e8ed  mov     rdi, r15
0x18000e8f0  jmp     short loc_18000E8BD
0x18000e8f2  lea     rcx, [rbp+48h]
0x18000e8f6  call    cs:__imp_ExCleanupAutoExpandPushLock
0x18000e8fd  nop     dword ptr [rax+rax+00h]
0x18000e902  lea     rcx, [rbp+170h]
0x18000e909  call    cs:__imp_ExCleanupAutoExpandPushLock
0x18000e910  nop     dword ptr [rax+rax+00h]
0x18000e915  mov     rcx, [rbp+168h]
0x18000e91c  test    rcx, rcx
0x18000e91f  jz      short loc_18000E94E
0x18000e921  mov     rcx, [rcx+140h]; IoWorkItem
0x18000e928  call    cs:__imp_IoUninitializeWorkItem
0x18000e92f  nop     dword ptr [rax+rax+00h]
0x18000e934  mov     rdx, [rbp+168h]; Entry
0x18000e93b  lea     rcx, stru_18003F1C0; Lookaside
0x18000e942  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000e949  nop     dword ptr [rax+rax+00h]
0x18000e94e  mov     rdx, rbp; Entry
0x18000e951  lea     rcx, stru_18003EB40; Lookaside
0x18000e958  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000e95f  nop     dword ptr [rax+rax+00h]
0x18000e964  jmp     loc_18000E6CB
0x18000e969  add     rdi, 28h ; '('
0x18000e96d  cmp     qword ptr [rsi+30h], 0CACEh
0x18000e975  jnz     loc_18000EA0B
0x18000e97b  cmp     rsi, [rsi+28h]
0x18000e97f  jnz     loc_18000EA0B
0x18000e985  mov     rax, [rsi+18h]
0x18000e989  cmp     rax, rdi
0x18000e98c  jnz     loc_18000E86B
0x18000e992  mov     rdx, [rsi+20h]
0x18000e996  test    rdx, rdx
0x18000e999  jz      loc_18000E86B
0x18000e99f  prefetchw byte ptr [rdx]
0x18000e9a2  mov     rax, [rdx]
0x18000e9a5  mov     rcx, rax
0x18000e9a8  or      rcx, 1
0x18000e9ac  lock cmpxchg [rdx], rcx
0x18000e9b1  jnz     short loc_18000E9A5
0x18000e9b3  test    al, 1
0x18000e9b5  jnz     short loc_18000E99F
0x18000e9b7  mov     rdi, [rdx+8]
0x18000e9bb  mov     [rdx+8], r15
0x18000e9bf  lock and [rdx], r15
0x18000e9c3  and     dword ptr [rdi+48h], 0FFFEFFFFh
0x18000e9ca  lea     rcx, [rbp+48h]
0x18000e9ce  xorps   xmm0, xmm0
0x18000e9d1  mov     [rdi+30h], r15
0x18000e9d5  xor     eax, eax
0x18000e9d7  xor     edx, edx
0x18000e9d9  movups  xmmword ptr [rdi+18h], xmm0
0x18000e9dd  mov     [rdi+28h], rax
0x18000e9e1  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x18000e9e8  nop     dword ptr [rax+rax+00h]
0x18000e9ed  call    cs:__imp_KeLeaveGuardedRegion
0x18000e9f4  nop     dword ptr [rax+rax+00h]
0x18000e9f9  mov     rcx, rbp; Entry
0x18000e9fc  call    FltpReleaseStreamListCtrl
0x18000ea01  mov     r12, [rsp+58h+arg_8]
0x18000ea06  jmp     loc_18000E6CB
0x18000ea0b  mov     rax, r15
0x18000ea0e  jmp     loc_18000E989
0x18000ea13  or      dword ptr [rdi+48h], 2
0x18000ea17  lea     rcx, [rdi+18h]
0x18000ea1b  mov     word ptr [rcx], 0F124h
0x18000ea20  lea     rax, DoFreeContext
0x18000ea27  mov     word ptr [rdi+1Ah], 28h ; '('
0x18000ea2d  mov     edx, 1
0x18000ea32  mov     [rdi+30h], rax
0x18000ea36  mov     [rdi+38h], rdi
0x18000ea3a  mov     [rdi+20h], r15
0x18000ea3e  call    FltpQueueThrottledWorkItem
0x18000ea43  jmp     def_18000E815; jumptable 000000018000E815 default case, cases 3,5-7,9-31,33-63
0x18000ea48  mov     rax, [rsi+10h]; jumptable 000000018000E815 case 4
0x18000ea4c  xor     r15d, r15d
0x18000ea4f  lock cmpxchg [rsi+10h], r15
0x18000ea55  mov     rbp, rax
0x18000ea58  test    rax, rax
0x18000ea5b  jz      def_18000E815; jumptable 000000018000E815 default case, cases 3,5-7,9-31,33-63
0x18000ea61  lea     rdx, [rax+48h]
0x18000ea65  mov     r8, rsi
0x18000ea68  lea     rcx, [rax+58h]
0x18000ea6c  call    FltpDeleteContextNodeFromList
0x18000ea71  mov     rcx, rbp; Entry
0x18000ea74  mov     rdi, rax
0x18000ea77  call    FltpReleaseFileListCtrl
0x18000ea7c  jmp     loc_18000E6CB
0x18000ea81  mov     rax, [rsi+10h]; jumptable 000000018000E815 case 8
0x18000ea85  xor     r15d, r15d
0x18000ea88  lock cmpxchg [rsi+10h], r15
0x18000ea8e  mov     rbp, rax
0x18000ea91  test    rax, rax
0x18000ea94  jz      def_18000E815; jumptable 000000018000E815 default case, cases 3,5-7,9-31,33-63
0x18000ea9a  lea     rdx, [rax+48h]
0x18000ea9e  mov     r8, rsi
0x18000eaa1  lea     rcx, [rax+58h]
0x18000eaa5  call    FltpDeleteContextNodeFromList
0x18000eaaa  mov     rcx, rbp; Entry
0x18000eaad  mov     rdi, rax
0x18000eab0  call    FltpReleaseStreamListCtrl
0x18000eab5  jmp     loc_18000E6CB
0x18000eaba  mov     rax, [rsi+10h]; jumptable 000000018000E815 case 32
0x18000eabe  xor     r15d, r15d
0x18000eac1  lock cmpxchg [rsi+10h], r15
0x18000eac7  mov     rbp, rax
0x18000eaca  test    rax, rax
0x18000eacd  jz      def_18000E815; jumptable 000000018000E815 default case, cases 3,5-7,9-31,33-63
0x18000ead3  lea     rdx, [rax+88h]
0x18000eada  lea     rcx, [rax+0A0h]
0x18000eae1  mov     r8, rsi
0x18000eae4  call    FltpDeleteContextNodeFromList
0x18000eae9  mov     rcx, rbp
0x18000eaec  mov     rdi, rax
0x18000eaef  call    FltpObjectPointerDereference
0x18000eaf4  jmp     loc_18000E6CB
0x18000eaf9  mov     rax, [rsi+10h]; jumptable 000000018000E815 case 1
0x18000eafd  xor     r15d, r15d
0x18000eb00  lock cmpxchg [rsi+10h], r15
0x18000eb06  mov     rbp, rax
  ... truncated ...
```
