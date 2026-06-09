# RxpProcessWorkItem

- ea: `0x14000cb20`
- end: `0x14000cd20`
- name: `RxpProcessWorkItem`
- size: `512`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000cb20`
- `0x140016fc0`
- `0x140017370`
- `0x140025d00`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x14000cb7a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000cbc1`
- `ntoskrnl!ObfDereferenceObject` at `0x14000cbc1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cc66`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cc66`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000cbb2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000cbb2`
- `ntoskrnl!ExQueueWorkItem` at `0x14000cc9b`
- `ntoskrnl!ExQueueWorkItem` at `0x14000cc9b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cc33`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cc33`

## pseudocode

```c
void __fastcall RxpProcessWorkItem(_BYTE *Entry)
{
  __int64 v1; // r14
  char v3; // bp
  void *v4; // rsi
  char *v5; // rbx
  __int64 v6; // rcx
  signed __int64 v7; // rcx
  __int64 v8; // rax
  struct _WORK_QUEUE_ITEM *v9; // rdi
  KSPIN_LOCK *v10; // rsi
  struct _WORK_QUEUE_ITEM **v11; // rbx
  KIRQL v12; // al
  struct _WORK_QUEUE_ITEM *v13; // rcx
  struct _WORK_QUEUE_ITEM *Flink; // rdx
  __int64 Parameter_low; // rdx

  v1 = (unsigned __int8)Entry[56];
  v3 = Entry[57];
  v4 = (void *)*((_QWORD *)Entry + 4);
  v5 = (char *)P + 64 * (v1 + 6LL * (*((unsigned __int16 *)Entry + 29) % (unsigned int)RxGlobalDispatcher));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqqL(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      &WPP_91b9b20a3d1f3beba865abbaf8105594_Traceguids,
      Entry,
      *((_QWORD *)Entry + 5),
      *((_QWORD *)Entry + 6),
      v1);
  }
  *((_QWORD *)Entry + 4) = MmBadPointer;
  *((_QWORD *)Entry + 2) = MmBadPointer;
  v6 = *((_QWORD *)Entry + 6);
  *((_QWORD *)Entry + 3) = MmBadPointer;
  (*((void (__fastcall **)(__int64))Entry + 5))(v6);
  if ( v3 )
    ExFreeToNPagedLookasideList(&RxWorkItemLookasideList, Entry);
  ObfDereferenceObject(v4);
  _m_prefetchw(v5 + 32);
  do
  {
    v7 = *((_QWORD *)v5 + 4);
    v8 = 0x100000001LL;
    if ( SHIDWORD(v7) <= 0 )
      v8 = 1;
  }
  while ( _InterlockedCompareExchange64((volatile signed __int64 *)v5 + 4, *((_QWORD *)v5 + 4) - v8, v7) != v7 );
  if ( v7 > 0 )
  {
    v9 = 0;
    v10 = (KSPIN_LOCK *)(v5 + 8);
    v11 = (struct _WORK_QUEUE_ITEM **)(v5 + 40);
    do
    {
      v12 = KeAcquireSpinLockRaiseToDpc(v10);
      v13 = *v11;
      if ( *v11 != (struct _WORK_QUEUE_ITEM *)v11 )
      {
        if ( (struct _WORK_QUEUE_ITEM **)v13->List.Blink != v11
          || (Flink = (struct _WORK_QUEUE_ITEM *)v13->List.Flink,
              (struct _WORK_QUEUE_ITEM *)v13->List.Flink->Blink != v13) )
        {
          __fastfail(3u);
        }
        *v11 = Flink;
        v9 = v13;
        Flink->List.Blink = (struct _LIST_ENTRY *)v11;
      }
      KeReleaseSpinLock(v10, v12);
    }
    while ( !v9 );
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 11, &WPP_91b9b20a3d1f3beba865abbaf8105594_Traceguids, v9);
    }
    Parameter_low = LOBYTE(v9[1].Parameter);
    v9->List.Flink = 0;
    ExQueueWorkItem(v9, RxWorkQueueTypeMap[Parameter_low]);
  }
}

```

## disassembly

```asm
0x14000cb20  push    rbx
0x14000cb22  push    rbp
0x14000cb23  push    rsi
0x14000cb24  push    rdi
0x14000cb25  push    r14
0x14000cb27  push    r15
0x14000cb29  sub     rsp, 48h
0x14000cb2d  movzx   eax, word ptr [rcx+3Ah]
0x14000cb31  xor     edx, edx
0x14000cb33  div     cs:RxGlobalDispatcher
0x14000cb39  movzx   r14d, byte ptr [rcx+38h]
0x14000cb3e  mov     rdi, rcx
0x14000cb41  movzx   ebp, byte ptr [rcx+39h]
0x14000cb45  mov     rsi, [rcx+20h]
0x14000cb49  lea     rdx, [rdx+rdx*2]
0x14000cb4d  lea     rbx, [r14+rdx*2]
0x14000cb51  shl     rbx, 6
0x14000cb55  add     rbx, cs:P
0x14000cb5c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb63  lea     r15, WPP_GLOBAL_Control
0x14000cb6a  cmp     rcx, r15
0x14000cb6d  jz      short loc_14000CB7A
0x14000cb6f  mov     eax, [rcx+2Ch]
0x14000cb72  test    al, 2
0x14000cb74  jnz     loc_14000CCB3
0x14000cb7a  mov     rcx, cs:MmBadPointer
0x14000cb81  mov     rax, [rcx]
0x14000cb84  mov     [rdi+20h], rax
0x14000cb88  mov     rax, [rcx]
0x14000cb8b  mov     [rdi+10h], rax
0x14000cb8f  mov     rax, [rcx]
0x14000cb92  mov     rcx, [rdi+30h]
0x14000cb96  mov     [rdi+18h], rax
0x14000cb9a  mov     rax, [rdi+28h]
0x14000cb9e  call    _guard_dispatch_icall
0x14000cba3  test    bpl, bpl
0x14000cba6  jz      short loc_14000CBBE
0x14000cba8  mov     rdx, rdi; Entry
0x14000cbab  lea     rcx, RxWorkItemLookasideList; Lookaside
0x14000cbb2  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000cbb9  nop     dword ptr [rax+rax+00h]
0x14000cbbe  mov     rcx, rsi; Object
0x14000cbc1  call    cs:__imp_ObfDereferenceObject
0x14000cbc8  nop     dword ptr [rax+rax+00h]
0x14000cbcd  prefetchw byte ptr [rbx+20h]
0x14000cbd1  mov     r9, 100000001h
0x14000cbdb  mov     r10d, 1
0x14000cbe1  mov     rcx, [rbx+20h]
0x14000cbe5  mov     rax, r9
0x14000cbe8  mov     rdx, rcx
0x14000cbeb  mov     r8, rcx
0x14000cbee  shr     rdx, 20h
0x14000cbf2  test    edx, edx
0x14000cbf4  cmovle  rax, r10
0x14000cbf8  sub     r8, rax
0x14000cbfb  mov     rax, rcx
0x14000cbfe  lock cmpxchg [rbx+20h], r8
0x14000cc04  cmp     rax, rcx
0x14000cc07  jnz     short loc_14000CBE1
0x14000cc09  test    edx, edx
0x14000cc0b  jg      short loc_14000CC1B
0x14000cc0d  add     rsp, 48h
0x14000cc11  pop     r15
0x14000cc13  pop     r14
0x14000cc15  pop     rdi
0x14000cc16  pop     rsi
0x14000cc17  pop     rbp
0x14000cc18  pop     rbx
0x14000cc19  retn
0x14000cc1b  xor     edi, edi
0x14000cc1d  lea     rsi, [rbx+8]
0x14000cc21  add     rbx, 28h ; '('
0x14000cc25  nop     word ptr [rax+rax+00000000h]
0x14000cc30  mov     rcx, rsi; SpinLock
0x14000cc33  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000cc3a  nop     dword ptr [rax+rax+00h]
0x14000cc3f  mov     rcx, [rbx]
0x14000cc42  cmp     rcx, rbx
0x14000cc45  jz      short loc_14000CC60
0x14000cc47  cmp     [rcx+8], rbx
0x14000cc4b  jnz     short loc_14000CCAC
0x14000cc4d  mov     rdx, [rcx]
0x14000cc50  cmp     [rdx+8], rcx
0x14000cc54  jnz     short loc_14000CCAC
0x14000cc56  mov     [rbx], rdx
0x14000cc59  mov     rdi, rcx
0x14000cc5c  mov     [rdx+8], rbx
0x14000cc60  movzx   edx, al; NewIrql
0x14000cc63  mov     rcx, rsi; SpinLock
0x14000cc66  call    cs:__imp_KeReleaseSpinLock
0x14000cc6d  nop     dword ptr [rax+rax+00h]
0x14000cc72  test    rdi, rdi
0x14000cc75  jz      short loc_14000CC30
0x14000cc77  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc7e  cmp     rcx, r15
0x14000cc81  jnz     short loc_14000CCF1
0x14000cc83  movzx   edx, byte ptr [rdi+38h]
0x14000cc87  lea     rax, RxWorkQueueTypeMap
0x14000cc8e  mov     rcx, rdi; WorkItem
0x14000cc91  mov     qword ptr [rdi], 0
0x14000cc98  mov     edx, [rax+rdx*4]; QueueType
0x14000cc9b  call    cs:__imp_ExQueueWorkItem
0x14000cca2  nop     dword ptr [rax+rax+00h]
0x14000cca7  jmp     loc_14000CC0D
0x14000ccac  mov     ecx, 3
0x14000ccb1  int     29h; Win8: RtlFailFast(ecx)
0x14000ccb3  cmp     byte ptr [rcx+29h], 4
0x14000ccb7  jb      loc_14000CB7A
0x14000ccbd  mov     rax, [rdi+30h]
0x14000ccc1  lea     r8, WPP_91b9b20a3d1f3beba865abbaf8105594_Traceguids
0x14000ccc8  mov     rcx, [rcx+18h]
0x14000cccc  mov     edx, 0Ah
0x14000ccd1  mov     [rsp+78h+var_48], r14d
0x14000ccd6  mov     r9, rdi
0x14000ccd9  mov     [rsp+78h+var_50], rax
0x14000ccde  mov     rax, [rdi+28h]
0x14000cce2  mov     [rsp+78h+var_58], rax
0x14000cce7  call    WPP_SF_qqqL
0x14000ccec  jmp     loc_14000CB7A
0x14000ccf1  mov     eax, [rcx+2Ch]
0x14000ccf4  test    al, 2
0x14000ccf6  jz      short loc_14000CC83
0x14000ccf8  cmp     byte ptr [rcx+29h], 4
0x14000ccfc  jb      short loc_14000CC83
0x14000ccfe  mov     rcx, [rcx+18h]
0x14000cd02  lea     r8, WPP_91b9b20a3d1f3beba865abbaf8105594_Traceguids
0x14000cd09  mov     edx, 0Bh
0x14000cd0e  mov     dword ptr [rsp+78h+var_58], r14d
0x14000cd13  mov     r9, rdi
0x14000cd16  call    WPP_SF_qD
0x14000cd1b  jmp     loc_14000CC83
```
