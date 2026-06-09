# LfsFlushToLsn

- ea: `0x140209910`
- end: `0x140209fbc`
- name: `LfsFlushToLsn`
- size: `1708`
- prototype: ``
- caller_count: `15`
- callee_count: `5`
- tags: ``

## callers

- `0x1400450dc`
- `0x1400cc78c`
- `0x1400cf580`
- `0x140138b18`
- `0x1401d5ad0`
- `0x1401d60b8`
- `0x1401da21c`
- `0x140208f3c`
- `0x1402096ac`
- `0x140209fc4`
- `0x14020a724`
- `0x14021ebd0`
- `0x140230888`
- `0x14026dc7c`
- `0x14027e3c8`

## callees

- `0x1400240c0`
- `0x140027f08`
- `0x14002f140`
- `0x14002f7e8`
- `0x140209910`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140209d3a`
- `ntoskrnl!KeSetEvent` at `0x140209eb0`
- `ntoskrnl!KeSetEvent` at `0x140209d3a`
- `ntoskrnl!KeSetEvent` at `0x140209eb0`
- `ntoskrnl!KeSetPriorityThread` at `0x140209b0c`
- `ntoskrnl!KeSetPriorityThread` at `0x140209b80`
- `ntoskrnl!KeSetPriorityThread` at `0x140209dc2`
- `ntoskrnl!KeSetPriorityThread` at `0x140209e2d`
- `ntoskrnl!KeSetPriorityThread` at `0x140209b0c`
- `ntoskrnl!KeSetPriorityThread` at `0x140209b80`
- `ntoskrnl!KeSetPriorityThread` at `0x140209dc2`
- `ntoskrnl!KeSetPriorityThread` at `0x140209e2d`
- `ntoskrnl!PsEnterPriorityRegion` at `0x140209b1f`
- `ntoskrnl!PsEnterPriorityRegion` at `0x140209dd2`
- `ntoskrnl!PsEnterPriorityRegion` at `0x140209b1f`
- `ntoskrnl!PsEnterPriorityRegion` at `0x140209dd2`
- `ntoskrnl!PsLeavePriorityRegion` at `0x140209b5e`
- `ntoskrnl!PsLeavePriorityRegion` at `0x140209e0b`
- `ntoskrnl!PsLeavePriorityRegion` at `0x140209b5e`
- `ntoskrnl!PsLeavePriorityRegion` at `0x140209e0b`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140209ba0`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140209f73`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140209ba0`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140209f73`
- `ntoskrnl!KeWaitForSingleObject` at `0x140209bdc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140209e61`
- `ntoskrnl!KeWaitForSingleObject` at `0x140209bdc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140209e61`
- `ntoskrnl!KeInitializeEvent` at `0x140209a37`
- `ntoskrnl!KeInitializeEvent` at `0x140209c8e`
- `ntoskrnl!KeInitializeEvent` at `0x140209a37`
- `ntoskrnl!KeInitializeEvent` at `0x140209c8e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209a90`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209b36`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209ce8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209de9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209a90`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209b36`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209ce8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209de9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140209a70`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140209cc4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140209a70`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140209cc4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140209975`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140209bff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140209e7b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140209975`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140209bff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140209e7b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140209bb7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140209f87`
- `ntoskrnl!ExReleaseResourceLite` at `0x140209bb7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140209f87`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140209a52`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140209ca9`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140209a52`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140209ca9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140209d79`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140209ebe`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140209d79`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140209ebe`
- `ntoskrnl!ExRaiseStatus` at `0x140209f62`
- `ntoskrnl!ExRaiseStatus` at `0x140209faf`
- `ntoskrnl!ExRaiseStatus` at `0x140209f62`
- `ntoskrnl!ExRaiseStatus` at `0x140209faf`

## pseudocode

```c
__int64 __fastcall LfsFlushToLsn(__int64 a1, __int64 a2)
{
  unsigned int v4; // r15d
  bool v5; // r12
  __int64 v6; // r14
  KPRIORITY v7; // r13d
  __int64 *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rdi
  struct _ERESOURCE *v12; // rcx
  __int64 *v13; // rax
  BOOLEAN v14; // r12
  __int64 v15; // rax
  int v16; // eax
  struct _KEVENT *v17; // rcx
  _QWORD *i; // rax
  _QWORD *v19; // rcx
  char v20; // r13
  struct _ERESOURCE *v21; // rcx
  struct _KEVENT *v22; // rcx
  _QWORD *j; // rax
  _QWORD *v24; // rcx
  KPRIORITY Priority; // [rsp+30h] [rbp-D8h]
  __int128 v27; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE Object[32]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+88h] [rbp-80h]
  __int128 v30; // [rsp+90h] [rbp-78h] BYREF
  _BYTE Event[32]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-48h]
  char v33; // [rsp+110h] [rbp+8h]
  BOOLEAN IsResourceAcquiredExclusiveLite; // [rsp+120h] [rbp+18h]

  if ( !a1 || (v4 = 0, *(_WORD *)a1 != 2049) )
    ExRaiseStatus(-1073741790);
  v5 = qword_140094AF8 == 0;
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 56), 1u);
  v6 = *(_QWORD *)(a1 + 24);
  if ( v6 )
  {
    if ( (*(_DWORD *)(v6 + 428) & 0x400) == 0 )
    {
      if ( *(_WORD *)(a1 + 34) >= *(_WORD *)(*(_QWORD *)(v6 + 200) + 8LL)
        || *(_WORD *)(a1 + 32) != *(_WORD *)(*(unsigned int *)(a1 + 48) + *(_QWORD *)(v6 + 208) + 20LL) )
      {
        ExRaiseStatus(-1073741790);
      }
      v30 = 0;
      memset(Event, 0, sizeof(Event));
      v32 = 0;
      v7 = 0;
      v8 = *(__int64 **)(v6 + 200);
      v9 = a2;
      if ( a2 > *v8 )
        v9 = *v8;
      KeInitializeEvent((PRKEVENT)Event, SynchronizationEvent, 0);
      *(_QWORD *)&Event[24] = v9;
      IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v6 + 456));
      while ( 1 )
      {
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v6 + 456) + 120LL));
        v10 = *(_QWORD *)(v6 + 456);
        if ( v9 <= *(_QWORD *)(v6 + 280) )
        {
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v10 + 120));
          goto LABEL_12;
        }
        if ( *(_DWORD *)(v10 + 176) )
        {
          for ( i = *(_QWORD **)(v6 + 472); i != (_QWORD *)(v6 + 472) && i[5] <= v9; i = (_QWORD *)*i )
            ;
          v19 = (_QWORD *)i[1];
          if ( (_QWORD *)*v19 != i )
LABEL_42:
            __fastfail(3u);
          v33 = 0;
          *(_QWORD *)&v30 = i;
          *((_QWORD *)&v30 + 1) = v19;
          *v19 = &v30;
          i[1] = &v30;
        }
        else
        {
          *(_DWORD *)(v10 + 176) = 1;
          *(_QWORD *)(v6 + 504) = KeGetCurrentThread();
          v33 = 1;
          v7 = KeSetPriorityThread(KeGetCurrentThread(), 16);
          PsEnterPriorityRegion();
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v6 + 456) + 120LL));
        if ( v33 )
          break;
        _InterlockedIncrement((volatile signed __int32 *)(v6 + 464));
        if ( ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(v6 + 456)) )
          ExReleaseResourceLite(*(PERESOURCE *)(v6 + 456));
        KeWaitForSingleObject(Event, Executive, 0, 0, 0);
        v12 = *(struct _ERESOURCE **)(v6 + 456);
        if ( IsResourceAcquiredExclusiveLite )
          ExAcquireResourceExclusiveLite(v12, 1u);
        else
          ExAcquireResourceSharedLite(v12, 1u);
        if ( !_InterlockedDecrement((volatile signed __int32 *)(v6 + 464)) )
        {
          v17 = *(struct _KEVENT **)(v6 + 608);
          if ( v17 )
            KeSetEvent(v17, 0, 0);
        }
      }
      LfsFlushLfcbOnNewStack(v6, v9, 0, v5);
      PsLeavePriorityRegion();
      if ( v7 != 16 )
        KeSetPriorityThread(KeGetCurrentThread(), v7);
LABEL_12:
      v11 = 0x7FFFFFFFFFFFFFFFLL;
      if ( a2 == 0x7FFFFFFFFFFFFFFFLL )
        a2 = *(_QWORD *)(v6 + 280);
      if ( a2 > *(_QWORD *)(v6 + 296) )
      {
        if ( v5 )
        {
          *(_QWORD *)(v6 + 296) = *(_QWORD *)(v6 + 280);
        }
        else
        {
          v27 = 0;
          memset(Object, 0, sizeof(Object));
          v29 = 0;
          Priority = 0;
          v13 = *(__int64 **)(v6 + 200);
          if ( *v13 != 0x7FFFFFFFFFFFFFFFLL )
            v11 = *v13;
          KeInitializeEvent((PRKEVENT)Object, SynchronizationEvent, 0);
          *(_QWORD *)&Object[24] = v11;
          v14 = ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v6 + 456));
          while ( 1 )
          {
            ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v6 + 456) + 120LL));
            v15 = *(_QWORD *)(v6 + 456);
            if ( v11 <= *(_QWORD *)(v6 + 280) )
            {
              ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v15 + 120));
              goto LABEL_34;
            }
            if ( *(_DWORD *)(v15 + 176) )
            {
              for ( j = *(_QWORD **)(v6 + 472); j != (_QWORD *)(v6 + 472) && j[5] <= v11; j = (_QWORD *)*j )
                ;
              v24 = (_QWORD *)j[1];
              if ( (_QWORD *)*v24 != j )
                goto LABEL_42;
              v20 = 0;
              *(_QWORD *)&v27 = j;
              *((_QWORD *)&v27 + 1) = v24;
              *v24 = &v27;
              j[1] = &v27;
            }
            else
            {
              *(_DWORD *)(v15 + 176) = 1;
              *(_QWORD *)(v6 + 504) = KeGetCurrentThread();
              v20 = 1;
              Priority = KeSetPriorityThread(KeGetCurrentThread(), 16);
              PsEnterPriorityRegion();
            }
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v6 + 456) + 120LL));
            if ( v20 )
              break;
            _InterlockedIncrement((volatile signed __int32 *)(v6 + 464));
            LfsReleaseLfcb(v6);
            KeWaitForSingleObject(Object, Executive, 0, 0, 0);
            v21 = *(struct _ERESOURCE **)(v6 + 456);
            if ( v14 )
              ExAcquireResourceExclusiveLite(v21, 1u);
            else
              ExAcquireResourceSharedLite(v21, 1u);
            if ( !_InterlockedDecrement((volatile signed __int32 *)(v6 + 464)) )
            {
              v22 = *(struct _KEVENT **)(v6 + 608);
              if ( v22 )
                KeSetEvent(v22, 0, 0);
            }
          }
          LfsFlushLfcbOnNewStack(v6, v11, 0, 0);
          PsLeavePriorityRegion();
          if ( Priority != 16 )
            KeSetPriorityThread(KeGetCurrentThread(), Priority);
LABEL_34:
          v16 = LfsFlushDiskCache(a1, a2);
          v6 = *(_QWORD *)(a1 + 24);
          if ( v16 < 0 )
          {
            if ( !v6 )
              goto LABEL_67;
            ++*(_DWORD *)(v6 + 364);
          }
        }
      }
    }
    if ( v6 )
      v4 = *(_DWORD *)(v6 + 560);
  }
LABEL_67:
  if ( ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(a1 + 56)) )
    ExReleaseResourceLite(*(PERESOURCE *)(a1 + 56));
  return v4;
}

```

## disassembly

```asm
0x140209910  mov     rax, rsp
0x140209913  push    rbx
0x140209914  push    rsi
0x140209915  push    rdi
0x140209916  push    r12
0x140209918  push    r13
0x14020991a  push    r14
0x14020991c  push    r15
0x14020991e  sub     rsp, 0D0h
0x140209925  mov     rbx, rdx
0x140209928  mov     rsi, rcx
0x14020992b  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x140209932  mov     dword ptr [rax+24h], 7FFFFFFFh
0x140209939  test    rcx, rcx
0x14020993c  jz      loc_140209FAA
0x140209942  xor     r15d, r15d
0x140209945  xor     cl, cl
0x140209947  mov     [rsp+108h+var_B8], rsi
0x14020994c  mov     eax, 801h
0x140209951  cmp     [rsi], ax
0x140209954  jnz     loc_140209FAA
0x14020995a  movzx   r12d, cl
0x14020995e  mov     eax, 1
0x140209963  cmp     cs:qword_140094AF8, r15
0x14020996a  cmovz   r12d, eax
0x14020996e  movzx   edx, al; Wait
0x140209971  mov     rcx, [rsi+38h]; Resource
0x140209975  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14020997c  nop     dword ptr [rax+rax+00h]
0x140209981  mov     r14, [rsi+18h]
0x140209985  mov     [rsp+108h+var_C0], r14
0x14020998a  test    r14, r14
0x14020998d  jz      loc_140209F6F
0x140209993  mov     eax, [r14+1ACh]
0x14020999a  bt      eax, 0Ah
0x14020999e  jb      loc_140209ABA
0x1402099a4  mov     rax, [r14+0C8h]
0x1402099ab  movzx   ecx, word ptr [rax+8]
0x1402099af  cmp     [rsi+22h], cx
0x1402099b3  jnb     loc_140209F5D
0x1402099b9  mov     ecx, [rsi+30h]
0x1402099bc  mov     rax, [r14+0D0h]
0x1402099c3  movzx   ecx, word ptr [rcx+rax+14h]
0x1402099c8  cmp     [rsi+20h], cx
0x1402099cc  jnz     loc_140209F5D
0x1402099d2  mov     [rsp+108h+var_D0], rbx
0x1402099d7  xorps   xmm0, xmm0
0x1402099da  xor     eax, eax
0x1402099dc  movups  [rsp+108h+var_78], xmm0
0x1402099e4  movups  xmmword ptr [rsp+108h+Event], xmm0
0x1402099ec  movups  xmmword ptr [rsp+108h+Event+10h], xmm0
0x1402099f4  mov     [rsp+108h+var_48], rax
0x1402099fc  xor     r13d, r13d
0x1402099ff  mov     [rsp+108h+var_D4], r13d
0x140209a04  mov     rax, ds:0FFFFF78000000320h
0x140209a0e  mov     rax, [r14+0C8h]
0x140209a15  mov     rcx, [rax]
0x140209a18  mov     rdi, rbx
0x140209a1b  cmp     rbx, rcx
0x140209a1e  cmovg   rdi, rcx
0x140209a22  mov     [rsp+108h+var_D0], rdi
0x140209a27  xor     r8d, r8d; State
0x140209a2a  mov     edx, 1; Type
0x140209a2f  lea     rcx, [rsp+108h+Event]; Event
0x140209a37  call    cs:__imp_KeInitializeEvent
0x140209a3e  nop     dword ptr [rax+rax+00h]
0x140209a43  mov     qword ptr [rsp+108h+Event+18h], rdi
0x140209a4b  mov     rcx, [r14+1C8h]; Resource
0x140209a52  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140209a59  nop     dword ptr [rax+rax+00h]
0x140209a5e  mov     [rsp+108h+arg_10], al
0x140209a65  mov     rcx, [r14+1C8h]
0x140209a6c  add     rcx, 78h ; 'x'; FastMutex
0x140209a70  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140209a77  nop     dword ptr [rax+rax+00h]
0x140209a7c  mov     rax, [r14+1C8h]
0x140209a83  cmp     rdi, [r14+118h]
0x140209a8a  jg      short loc_140209ACF
0x140209a8c  lea     rcx, [rax+78h]; FastMutex
0x140209a90  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140209a97  nop     dword ptr [rax+rax+00h]
0x140209a9c  mov     rdi, [rsp+108h+arg_18]
0x140209aa4  cmp     rbx, rdi
0x140209aa7  jz      loc_140209C27
0x140209aad  cmp     rbx, [r14+128h]
0x140209ab4  jg      loc_140209C33
0x140209aba  test    r14, r14
0x140209abd  jz      loc_140209F6F
0x140209ac3  mov     r15d, [r14+230h]
0x140209aca  jmp     loc_140209F6F
0x140209acf  cmp     dword ptr [rax+0B0h], 0
0x140209ad6  jnz     loc_140209D4B
0x140209adc  mov     dword ptr [rax+0B0h], 1
0x140209ae6  mov     rax, gs:188h
0x140209aef  mov     [r14+1F8h], rax
0x140209af6  mov     [rsp+108h+arg_0], 1
0x140209afe  mov     rcx, gs:188h; Thread
0x140209b07  mov     edx, 10h; Priority
0x140209b0c  call    cs:__imp_KeSetPriorityThread
0x140209b13  nop     dword ptr [rax+rax+00h]
0x140209b18  mov     r13d, eax
0x140209b1b  mov     [rsp+108h+var_D4], eax
0x140209b1f  call    cs:__imp_PsEnterPriorityRegion
0x140209b26  nop     dword ptr [rax+rax+00h]
0x140209b2b  mov     rcx, [r14+1C8h]
0x140209b32  add     rcx, 78h ; 'x'; FastMutex
0x140209b36  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140209b3d  nop     dword ptr [rax+rax+00h]
0x140209b42  cmp     [rsp+108h+arg_0], 0
0x140209b4a  jz      short loc_140209B91
0x140209b4c  movzx   r9d, r12b
0x140209b50  xor     r8d, r8d
0x140209b53  mov     rdx, rdi
0x140209b56  mov     rcx, r14
0x140209b59  call    LfsFlushLfcbOnNewStack
0x140209b5e  call    cs:__imp_PsLeavePriorityRegion
0x140209b65  nop     dword ptr [rax+rax+00h]
0x140209b6a  cmp     r13d, 10h
0x140209b6e  jz      loc_140209A9C
0x140209b74  mov     rcx, gs:188h; Thread
0x140209b7d  mov     edx, r13d; Priority
0x140209b80  call    cs:__imp_KeSetPriorityThread
0x140209b87  nop     dword ptr [rax+rax+00h]
0x140209b8c  jmp     loc_140209A9C
0x140209b91  lock inc dword ptr [r14+1D0h]
0x140209b99  mov     rcx, [r14+1C8h]; Resource
0x140209ba0  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140209ba7  nop     dword ptr [rax+rax+00h]
0x140209bac  test    eax, eax
0x140209bae  jz      short loc_140209BC3
0x140209bb0  mov     rcx, [r14+1C8h]; Resource
0x140209bb7  call    cs:__imp_ExReleaseResourceLite
0x140209bbe  nop     dword ptr [rax+rax+00h]
0x140209bc3  mov     [rsp+108h+Timeout], 0; Timeout
0x140209bcc  xor     r9d, r9d; Alertable
0x140209bcf  xor     r8d, r8d; WaitMode
0x140209bd2  xor     edx, edx; WaitReason
0x140209bd4  lea     rcx, [rsp+108h+Event]; Object
0x140209bdc  call    cs:__imp_KeWaitForSingleObject
0x140209be3  nop     dword ptr [rax+rax+00h]
0x140209be8  mov     rcx, [r14+1C8h]; Resource
0x140209bef  mov     dl, 1; Wait
0x140209bf1  cmp     [rsp+108h+arg_10], 0
0x140209bf9  jz      loc_140209D79
0x140209bff  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140209c06  nop     dword ptr [rax+rax+00h]
0x140209c0b  mov     eax, 0FFFFFFFFh
0x140209c10  lock xadd [r14+1D0h], eax
0x140209c19  sub     eax, 1
0x140209c1c  jz      loc_140209D25
0x140209c22  jmp     loc_140209A65
0x140209c27  mov     rbx, [r14+118h]
0x140209c2e  jmp     loc_140209AAD
0x140209c33  test    r12b, r12b
0x140209c36  jnz     loc_140209F4A
0x140209c3c  mov     [rsp+108h+var_C8], rdi
0x140209c41  xorps   xmm0, xmm0
0x140209c44  xor     eax, eax
0x140209c46  movups  [rsp+108h+var_B0], xmm0
0x140209c4b  movups  xmmword ptr [rsp+108h+Object], xmm0
0x140209c50  movups  xmmword ptr [rsp+108h+Object+10h], xmm0
0x140209c55  mov     [rsp+108h+var_80], rax
0x140209c5d  mov     [rsp+108h+Priority], eax
0x140209c61  mov     rax, ds:0FFFFF78000000320h
0x140209c6b  mov     rax, [r14+0C8h]
0x140209c72  mov     rcx, [rax]
0x140209c75  cmp     rdi, rcx
0x140209c78  cmovg   rdi, rcx
0x140209c7c  mov     [rsp+108h+var_C8], rdi
0x140209c81  xor     r8d, r8d; State
0x140209c84  mov     edx, 1; Type
0x140209c89  lea     rcx, [rsp+108h+Object]; Event
0x140209c8e  call    cs:__imp_KeInitializeEvent
0x140209c95  nop     dword ptr [rax+rax+00h]
0x140209c9a  mov     qword ptr [rsp+108h+Object+18h], rdi
0x140209ca2  mov     rcx, [r14+1C8h]; Resource
0x140209ca9  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140209cb0  nop     dword ptr [rax+rax+00h]
0x140209cb5  movzx   r12d, al
0x140209cb9  mov     rcx, [r14+1C8h]
0x140209cc0  add     rcx, 78h ; 'x'; FastMutex
0x140209cc4  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140209ccb  nop     dword ptr [rax+rax+00h]
0x140209cd0  mov     rax, [r14+1C8h]
0x140209cd7  cmp     rdi, [r14+118h]
0x140209cde  jg      loc_140209D8A
0x140209ce4  lea     rcx, [rax+78h]; FastMutex
0x140209ce8  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140209cef  nop     dword ptr [rax+rax+00h]
0x140209cf4  mov     rdx, rbx
0x140209cf7  mov     rcx, rsi
0x140209cfa  call    LfsFlushDiskCache
0x140209cff  mov     r14, [rsi+18h]
0x140209d03  mov     [rsp+108h+var_C0], r14
0x140209d08  test    eax, eax
0x140209d0a  jns     loc_140209ABA
0x140209d10  test    r14, r14
0x140209d13  jz      loc_140209F6F
0x140209d19  inc     dword ptr [r14+16Ch]
0x140209d20  jmp     loc_140209ABA
0x140209d25  mov     rcx, [r14+260h]; Event
0x140209d2c  test    rcx, rcx
0x140209d2f  jz      loc_140209C22
0x140209d35  xor     r8d, r8d; Wait
0x140209d38  xor     edx, edx; Increment
0x140209d3a  call    cs:__imp_KeSetEvent
0x140209d41  nop     dword ptr [rax+rax+00h]
0x140209d46  jmp     loc_140209C22
0x140209d4b  lea     rcx, [r14+1D8h]
0x140209d52  mov     rax, [rcx]
0x140209d55  cmp     rax, rcx
0x140209d58  jnz     short loc_140209D6E
0x140209d5a  mov     rcx, [rax+8]
0x140209d5e  cmp     [rcx], rax
0x140209d61  jz      loc_140209F16
0x140209d67  mov     ecx, 3
0x140209d6c  int     29h; Win8: RtlFailFast(ecx)
0x140209d6e  cmp     [rax+28h], rdi
0x140209d72  jg      short loc_140209D5A
0x140209d74  mov     rax, [rax]
0x140209d77  jmp     short loc_140209D55
0x140209d79  call    cs:__imp_ExAcquireResourceSharedLite
0x140209d80  nop     dword ptr [rax+rax+00h]
0x140209d85  jmp     loc_140209C0B
0x140209d8a  cmp     dword ptr [rax+0B0h], 0
0x140209d91  jnz     loc_140209ECC
0x140209d97  mov     dword ptr [rax+0B0h], 1
0x140209da1  mov     rax, gs:188h
0x140209daa  mov     [r14+1F8h], rax
0x140209db1  mov     r13b, 1
0x140209db4  mov     rcx, gs:188h; Thread
0x140209dbd  mov     edx, 10h; Priority
0x140209dc2  call    cs:__imp_KeSetPriorityThread
0x140209dc9  nop     dword ptr [rax+rax+00h]
0x140209dce  mov     [rsp+108h+Priority], eax
0x140209dd2  call    cs:__imp_PsEnterPriorityRegion
0x140209dd9  nop     dword ptr [rax+rax+00h]
0x140209dde  mov     rcx, [r14+1C8h]
0x140209de5  add     rcx, 78h ; 'x'; FastMutex
0x140209de9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140209df0  nop     dword ptr [rax+rax+00h]
0x140209df5  mov     rcx, r14
0x140209df8  test    r13b, r13b
0x140209dfb  jz      short loc_140209E3E
0x140209dfd  xor     r9d, r9d
0x140209e00  xor     r8d, r8d
0x140209e03  mov     rdx, rdi
0x140209e06  call    LfsFlushLfcbOnNewStack
0x140209e0b  call    cs:__imp_PsLeavePriorityRegion
0x140209e12  nop     dword ptr [rax+rax+00h]
0x140209e17  mov     edx, [rsp+108h+Priority]; Priority
0x140209e1b  cmp     edx, 10h
0x140209e1e  jz      loc_140209CF4
0x140209e24  mov     rcx, gs:188h; Thread
0x140209e2d  call    cs:__imp_KeSetPriorityThread
0x140209e34  nop     dword ptr [rax+rax+00h]
0x140209e39  jmp     loc_140209CF4
0x140209e3e  lock inc dword ptr [r14+1D0h]
0x140209e46  call    LfsReleaseLfcb
0x140209e4b  mov     [rsp+108h+Timeout], 0; Timeout
0x140209e54  xor     r9d, r9d; Alertable
0x140209e57  xor     r8d, r8d; WaitMode
0x140209e5a  xor     edx, edx; WaitReason
0x140209e5c  lea     rcx, [rsp+108h+Object]; Object
0x140209e61  call    cs:__imp_KeWaitForSingleObject
0x140209e68  nop     dword ptr [rax+rax+00h]
0x140209e6d  mov     rcx, [r14+1C8h]; Resource
0x140209e74  mov     dl, 1; Wait
0x140209e76  test    r12b, r12b
0x140209e79  jz      short loc_140209EBE
0x140209e7b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140209e82  nop     dword ptr [rax+rax+00h]
0x140209e87  mov     eax, 0FFFFFFFFh
0x140209e8c  lock xadd [r14+1D0h], eax
0x140209e95  sub     eax, 1
0x140209e98  jz      short loc_140209E9F
0x140209e9a  jmp     loc_140209CB9
0x140209e9f  mov     rcx, [r14+260h]; Event
0x140209ea6  test    rcx, rcx
0x140209ea9  jz      short loc_140209E9A
0x140209eab  xor     r8d, r8d; Wait
0x140209eae  xor     edx, edx; Increment
0x140209eb0  call    cs:__imp_KeSetEvent
0x140209eb7  nop     dword ptr [rax+rax+00h]
0x140209ebc  jmp     short loc_140209E9A
0x140209ebe  call    cs:__imp_ExAcquireResourceSharedLite
0x140209ec5  nop     dword ptr [rax+rax+00h]
0x140209eca  jmp     short loc_140209E87
0x140209ecc  lea     rcx, [r14+1D8h]
0x140209ed3  mov     rax, [rcx]
0x140209ed6  cmp     rax, rcx
0x140209ed9  jnz     short loc_140209F0B
0x140209edb  mov     rcx, [rax+8]
0x140209edf  cmp     [rcx], rax
0x140209ee2  jnz     loc_140209D67
0x140209ee8  xor     r13b, r13b
0x140209eeb  mov     qword ptr [rsp+108h+var_B0], rax
0x140209ef0  mov     qword ptr [rsp+108h+var_B0+8], rcx
0x140209ef5  lea     rdx, [rsp+108h+var_B0]
0x140209efa  mov     [rcx], rdx
  ... truncated ...
```
