# PCW_NOTIFIER::SendNotification(ulong,_LARGE_INTEGER *,void const *,ulong,void *,ulong,ulong *)

- ea: `0x14000c5e0`
- end: `0x14000c907`
- name: `?SendNotification@PCW_NOTIFIER@@QEAAJKPEAT_LARGE_INTEGER@@PEBXKPEAXKPEAK@Z`
- size: `807`
- prototype: `__int64 __fastcall(const struct _LUID *this, int, union _LARGE_INTEGER *, const void *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000a650`
- `0x14000c240`

## callees

- `0x1400080b4`
- `0x14000b3ac`
- `0x14000c5e0`
- `0x14000c910`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x14000c79f`
- `ntoskrnl!PsIsThreadTerminating` at `0x14000c79f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c6c1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c6c1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c6af`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c7e8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c6af`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c7e8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c71c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c81a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c71c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c81a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c710`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c710`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c7f9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c7f9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c80e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c80e`
- `ntoskrnl!ExAllocatePool2` at `0x14000c635`
- `ntoskrnl!ExAllocatePool2` at `0x14000c635`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c846`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c888`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c846`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c888`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8e1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c774`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c774`
- `ntoskrnl!KeInitializeEvent` at `0x14000c619`
- `ntoskrnl!KeInitializeEvent` at `0x14000c619`

## pseudocode

```c
__int64 __fastcall PCW_NOTIFIER::SendNotification(
        const struct _LUID *this,
        int a2,
        union _LARGE_INTEGER *a3,
        const void *a4,
        unsigned int a5,
        void *a6,
        unsigned int a7,
        unsigned int *a8)
{
  PCW_NOTIFICATION *Pool2; // rax
  PCW_NOTIFICATION *v13; // rdi
  unsigned int v14; // esi
  __int64 v15; // rbx
  struct _LUID v16; // rcx
  _QWORD *v17; // rax
  _QWORD *v18; // rbx
  int v19; // eax
  unsigned int v20; // ecx
  unsigned __int128 v21; // rax
  __int64 v22; // rbx
  NTSTATUS v23; // eax
  int v24; // eax
  bool v25; // sf
  unsigned int v26; // ebx
  __int64 v28; // [rsp+40h] [rbp-68h]
  _KEVENT Event; // [rsp+58h] [rbp-50h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  Pool2 = (PCW_NOTIFICATION *)ExAllocatePool2(257, 80, 1316447056);
  if ( Pool2 )
    v13 = PCW_NOTIFICATION::PCW_NOTIFICATION(Pool2, this + 3, a2, &Event, a4, a5, a6, a7);
  else
    v13 = 0;
  if ( !v13 )
    return 3221225495LL;
  *((_DWORD *)v13 + 16) = 8;
  v14 = 0;
  v15 = *(_QWORD *)(*(_QWORD *)&this[4] + 80LL);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v15 + 80, 0);
  v16 = this[4];
  v17 = (_QWORD *)(*(_QWORD *)&v16 + 128LL);
  v18 = *(_QWORD **)(*(_QWORD *)&v16 + 128LL);
  while ( v18 != v17 )
  {
    v19 = PCW_USER_REGISTRATION::SendNotificationToRegistration((PCW_USER_REGISTRATION *)(v18 - 1), v13);
    v20 = v14 + 1;
    if ( v19 < 0 )
      v20 = v14;
    v14 = v20;
    v18 = (_QWORD *)*v18;
    v16 = this[4];
    v17 = (_QWORD *)(*(_QWORD *)&v16 + 128LL);
  }
  ExReleasePushLockSharedEx(*(_QWORD *)(*(_QWORD *)&v16 + 80LL) + 80LL, 0);
  KeLeaveCriticalRegion();
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 7, v14) != -v14 )
  {
    v21 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
        * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
LABEL_12:
    v22 = *((_QWORD *)&v21 + 1);
    while ( 1 )
    {
      v23 = KeWaitForSingleObject(&Event, UserRequest, 0, 1u, a3);
      if ( !v23 )
        break;
      v24 = v23 - 257;
      if ( v24 )
      {
        if ( v24 == 1 )
          goto LABEL_21;
      }
      else if ( PsIsThreadTerminating(KeGetCurrentThread()) )
      {
        v26 = -1073741248;
        goto LABEL_23;
      }
      if ( a3 && a3->QuadPart < 0 )
      {
        *((_QWORD *)&v21 + 1) = (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
                               * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
        *(_QWORD *)&v21 = 10000 * (*((_QWORD *)&v21 + 1) - v22);
        v25 = (__int64)(v21 + a3->QuadPart) < 0;
        a3->QuadPart += v21;
        if ( v25 )
          goto LABEL_12;
LABEL_21:
        v26 = 258;
LABEL_23:
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v13, 0);
        *((_BYTE *)v13 + 68) = 1;
        ExReleasePushLockExclusiveEx(v13, 0);
        KeLeaveCriticalRegion();
        *a8 = 0;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 19, 0xFFFFFFFF) == 1 )
          ExFreePoolWithTag(v13, 0);
        return v26;
      }
    }
  }
  LODWORD(v28) = *((_DWORD *)v13 + 18);
  HIDWORD(v28) = *((_DWORD *)v13 + 16);
  *a8 = HIDWORD(v28);
  if ( HIDWORD(v28) <= a7 )
  {
    RtlWriteULong64ToUser(a6, v28);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 19, 0xFFFFFFFF) == 1 )
      ExFreePoolWithTag(v13, 0);
    return 0;
  }
  else
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 19, 0xFFFFFFFF) == 1 )
      ExFreePoolWithTag(v13, 0);
    return 2147483653LL;
  }
}

```

## disassembly

```asm
0x14000c5e0  push    rbx
0x14000c5e2  push    rsi
0x14000c5e3  push    rdi
0x14000c5e4  push    r12
0x14000c5e6  push    r13
0x14000c5e8  push    r14
0x14000c5ea  push    r15
0x14000c5ec  sub     rsp, 70h
0x14000c5f0  mov     rbx, r9
0x14000c5f3  mov     r15, r8
0x14000c5f6  mov     edi, edx
0x14000c5f8  mov     r14, rcx
0x14000c5fb  xorps   xmm0, xmm0
0x14000c5fe  xor     eax, eax
0x14000c600  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x14000c605  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x14000c60a  mov     [rsp+0A8h+var_68], rax
0x14000c60f  xor     r8d, r8d; State
0x14000c612  xor     edx, edx; Type
0x14000c614  lea     rcx, [rsp+0A8h+Event]; Event
0x14000c619  call    cs:__imp_KeInitializeEvent
0x14000c620  nop     dword ptr [rax+rax+00h]
0x14000c625  mov     edx, 50h ; 'P'
0x14000c62a  mov     ecx, 101h
0x14000c62f  mov     r8d, 4E776350h
0x14000c635  call    cs:__imp_ExAllocatePool2
0x14000c63c  nop     dword ptr [rax+rax+00h]
0x14000c641  mov     r13d, [rsp+0A8h+arg_30]
0x14000c649  mov     r12, [rsp+0A8h+arg_28]
0x14000c651  test    rax, rax
0x14000c654  jz      short loc_14000C68E
0x14000c656  lea     rdx, [r14+18h]; struct _LUID *
0x14000c65a  mov     [rsp+0A8h+var_70], r13d; unsigned int
0x14000c65f  mov     [rsp+0A8h+var_78], r12; void *
0x14000c664  mov     ecx, [rsp+0A8h+arg_20]
0x14000c66b  mov     [rsp+0A8h+var_80], ecx; unsigned int
0x14000c66f  mov     [rsp+0A8h+Timeout], rbx; void *
0x14000c674  lea     r9, [rsp+0A8h+Event]; struct _KEVENT *
0x14000c679  mov     r8d, edi; unsigned int
0x14000c67c  mov     rcx, rax; this
0x14000c67f  call    ??0PCW_NOTIFICATION@@QEAA@AEBU_LUID@@KPEAU_KEVENT@@PEBXKPEAXK@Z; PCW_NOTIFICATION::PCW_NOTIFICATION(_LUID const &,ulong,_KEVENT *,void const *,ulong,void *,ulong)
0x14000c684  mov     rdi, rax
0x14000c687  mov     [rsp+0A8h+P], rax
0x14000c68c  jmp     short loc_14000C695
0x14000c68e  xor     edi, edi
0x14000c690  mov     [rsp+0A8h+P], rdi
0x14000c695  test    rdi, rdi
0x14000c698  jz      loc_14000C8F1
0x14000c69e  mov     dword ptr [rdi+40h], 8
0x14000c6a5  xor     esi, esi
0x14000c6a7  mov     rax, [r14+20h]
0x14000c6ab  mov     rbx, [rax+50h]
0x14000c6af  call    cs:__imp_KeEnterCriticalRegion
0x14000c6b6  nop     dword ptr [rax+rax+00h]
0x14000c6bb  xor     edx, edx
0x14000c6bd  lea     rcx, [rbx+50h]
0x14000c6c1  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000c6c8  nop     dword ptr [rax+rax+00h]
0x14000c6cd  mov     rcx, [r14+20h]
0x14000c6d1  lea     rax, [rcx+80h]
0x14000c6d8  mov     rbx, [rax]
0x14000c6db  jmp     short loc_14000C701
0x14000c6dd  lea     rcx, [rbx-8]; this
0x14000c6e1  mov     rdx, rdi; struct PCW_NOTIFICATION *
0x14000c6e4  call    ?SendNotificationToRegistration@PCW_USER_REGISTRATION@@QEAAJPEAVPCW_NOTIFICATION@@@Z; PCW_USER_REGISTRATION::SendNotificationToRegistration(PCW_NOTIFICATION *)
0x14000c6e9  lea     ecx, [rsi+1]
0x14000c6ec  test    eax, eax
0x14000c6ee  cmovs   ecx, esi
0x14000c6f1  mov     esi, ecx
0x14000c6f3  mov     rbx, [rbx]
0x14000c6f6  mov     rcx, [r14+20h]
0x14000c6fa  lea     rax, [rcx+80h]
0x14000c701  cmp     rbx, rax
0x14000c704  jnz     short loc_14000C6DD
0x14000c706  mov     rcx, [rcx+50h]
0x14000c70a  add     rcx, 50h ; 'P'
0x14000c70e  xor     edx, edx
0x14000c710  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c717  nop     dword ptr [rax+rax+00h]
0x14000c71c  call    cs:__imp_KeLeaveCriticalRegion
0x14000c723  nop     dword ptr [rax+rax+00h]
0x14000c728  mov     eax, esi
0x14000c72a  lock xadd [rdi+1Ch], eax
0x14000c72f  neg     esi
0x14000c731  cmp     eax, esi
0x14000c733  jz      loc_14000C859
0x14000c739  mov     rsi, 0FFFFF78000000004h
0x14000c743  mov     ecx, [rsi]
0x14000c745  mov     r14, 0FFFFF78000000320h
0x14000c74f  mov     rax, [r14]
0x14000c752  shl     rax, 8
0x14000c756  shl     rcx, 20h
0x14000c75a  mul     rcx
0x14000c75d  mov     rbx, rdx
0x14000c760  mov     [rsp+0A8h+Timeout], r15; Timeout
0x14000c765  mov     r9b, 1; Alertable
0x14000c768  xor     r8d, r8d; WaitMode
0x14000c76b  lea     edx, [r8+6]; WaitReason
0x14000c76f  lea     rcx, [rsp+0A8h+Event]; Object
0x14000c774  call    cs:__imp_KeWaitForSingleObject
0x14000c77b  nop     dword ptr [rax+rax+00h]
0x14000c780  test    eax, eax
0x14000c782  jz      loc_14000C859
0x14000c788  sub     eax, 101h
0x14000c78d  jz      short loc_14000C796
0x14000c78f  cmp     eax, 1
0x14000c792  jz      short loc_14000C7DC
0x14000c794  jmp     short loc_14000C7AF
0x14000c796  mov     rcx, gs:188h; Thread
0x14000c79f  call    cs:__imp_PsIsThreadTerminating
0x14000c7a6  nop     dword ptr [rax+rax+00h]
0x14000c7ab  test    al, al
0x14000c7ad  jnz     short loc_14000C7E3
0x14000c7af  test    r15, r15
0x14000c7b2  jz      short loc_14000C760
0x14000c7b4  cmp     qword ptr [r15], 0
0x14000c7b8  jge     short loc_14000C760
0x14000c7ba  mov     ecx, [rsi]
0x14000c7bc  mov     rax, [r14]
0x14000c7bf  shl     rax, 8
0x14000c7c3  shl     rcx, 20h
0x14000c7c7  mul     rcx
0x14000c7ca  mov     rax, rdx
0x14000c7cd  sub     rax, rbx
0x14000c7d0  imul    rax, 2710h
0x14000c7d7  add     [r15], rax
0x14000c7da  js      short loc_14000C75D
0x14000c7dc  mov     ebx, 102h
0x14000c7e1  jmp     short loc_14000C7E8
0x14000c7e3  mov     ebx, 0C0000240h
0x14000c7e8  call    cs:__imp_KeEnterCriticalRegion
0x14000c7ef  nop     dword ptr [rax+rax+00h]
0x14000c7f4  xor     edx, edx
0x14000c7f6  mov     rcx, rdi
0x14000c7f9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c800  nop     dword ptr [rax+rax+00h]
0x14000c805  mov     byte ptr [rdi+44h], 1
0x14000c809  xor     edx, edx
0x14000c80b  mov     rcx, rdi
0x14000c80e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c815  nop     dword ptr [rax+rax+00h]
0x14000c81a  call    cs:__imp_KeLeaveCriticalRegion
0x14000c821  nop     dword ptr [rax+rax+00h]
0x14000c826  mov     rcx, [rsp+0A8h+arg_38]
0x14000c82e  mov     dword ptr [rcx], 0
0x14000c834  or      ecx, 0FFFFFFFFh
0x14000c837  lock xadd [rdi+4Ch], ecx
0x14000c83c  cmp     ecx, 1
0x14000c83f  jnz     short loc_14000C852
0x14000c841  xor     edx, edx; Tag
0x14000c843  mov     rcx, rdi; P
0x14000c846  call    cs:__imp_ExFreePoolWithTag
0x14000c84d  nop     dword ptr [rax+rax+00h]
0x14000c852  mov     eax, ebx
0x14000c854  jmp     loc_14000C8F6
0x14000c859  mov     ecx, [rdi+40h]
0x14000c85c  mov     eax, [rdi+48h]
0x14000c85f  mov     dword ptr [rsp+0A8h+var_68], eax
0x14000c863  mov     dword ptr [rsp+0A8h+var_68+4], ecx
0x14000c867  mov     rax, [rsp+0A8h+arg_38]
0x14000c86f  mov     [rax], ecx
0x14000c871  cmp     ecx, r13d
0x14000c874  jbe     short loc_14000C89B
0x14000c876  or      eax, 0FFFFFFFFh
0x14000c879  lock xadd [rdi+4Ch], eax
0x14000c87e  cmp     eax, 1
0x14000c881  jnz     short loc_14000C894
0x14000c883  xor     edx, edx; Tag
0x14000c885  mov     rcx, rdi; P
0x14000c888  call    cs:__imp_ExFreePoolWithTag
0x14000c88f  nop     dword ptr [rax+rax+00h]
0x14000c894  mov     eax, 80000005h
0x14000c899  jmp     short loc_14000C8F6
0x14000c89b  mov     rdx, [rsp+0A8h+var_68]
0x14000c8a0  mov     rcx, r12
0x14000c8a3  call    RtlWriteULong64ToUser
0x14000c8a8  nop
0x14000c8a9  or      eax, 0FFFFFFFFh
0x14000c8ac  lock xadd [rdi+4Ch], eax
0x14000c8b1  cmp     eax, 1
0x14000c8b4  jnz     short loc_14000C8C7
0x14000c8b6  xor     edx, edx; Tag
0x14000c8b8  mov     rcx, rdi; P
0x14000c8bb  call    cs:__imp_ExFreePoolWithTag
0x14000c8c2  nop     dword ptr [rax+rax+00h]
0x14000c8c7  xor     eax, eax
0x14000c8c9  jmp     short loc_14000C8F6
0x14000c8cb  mov     ebx, eax
0x14000c8cd  mov     rcx, [rsp+0A8h+P]; P
0x14000c8d2  or      edx, 0FFFFFFFFh
0x14000c8d5  lock xadd [rcx+4Ch], edx
0x14000c8da  cmp     edx, 1
0x14000c8dd  jnz     short loc_14000C8ED
0x14000c8df  xor     edx, edx; Tag
0x14000c8e1  call    cs:__imp_ExFreePoolWithTag
0x14000c8e8  nop     dword ptr [rax+rax+00h]
0x14000c8ed  mov     eax, ebx
0x14000c8ef  jmp     short loc_14000C8F6
0x14000c8f1  mov     eax, 0C0000017h
0x14000c8f6  add     rsp, 70h
0x14000c8fa  pop     r15
0x14000c8fc  pop     r14
0x14000c8fe  pop     r13
0x14000c900  pop     r12
0x14000c902  pop     rdi
0x14000c903  pop     rsi
0x14000c904  pop     rbx
0x14000c905  retn
```
