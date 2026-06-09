# ClasspEnqueueIdleRequest

- ea: `0x1400024b0`
- end: `0x14000283c`
- name: `ClasspEnqueueIdleRequest`
- size: `908`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1400029d0`

## callees

- `0x140001de0`
- `0x1400021b0`
- `0x140002450`
- `0x1400024b0`
- `0x140002d30`
- `0x14001fc38`
- `0x140029ff4`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400025e5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400025e5`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140002559`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1400026ce`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14000279e`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140002559`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1400026ce`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14000279e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400026fa`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400026fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000266b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000266b`
- `ntoskrnl!IoRecordIoAttribution` at `0x140002772`
- `ntoskrnl!IoRecordIoAttribution` at `0x140002772`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x1400025c7`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x1400025c7`
- `ntoskrnl!FsRtlIsSystemPagingFile` at `0x140002802`
- `ntoskrnl!FsRtlIsSystemPagingFile` at `0x140002802`

## pseudocode

```c
__int64 __fastcall ClasspEnqueueIdleRequest(__int64 a1, _QWORD *a2)
{
  _BYTE *v2; // rdi
  unsigned int v4; // r13d
  __int64 v5; // rbx
  ULONG64 *v6; // rdi
  ULONG64 UnbiasedInterruptTimePrecise; // rax
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  char v10; // al
  int v11; // edx
  int v12; // ecx
  char v13; // r14
  KSPIN_LOCK *v14; // rsi
  KIRQL v15; // r12
  _QWORD *v16; // rdi
  char v17; // r15
  _QWORD *v18; // rcx
  __int64 v19; // rbx
  int v21; // edx
  int v22; // ecx
  unsigned __int8 *v23; // rax
  ULONG64 v24; // rax
  __int64 v25; // [rsp+40h] [rbp-88h]
  ULONG64 v26; // [rsp+48h] [rbp-80h] BYREF
  unsigned __int64 QpcTimeStamp[2]; // [rsp+50h] [rbp-78h] BYREF
  __int128 v28; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int64 v29[2]; // [rsp+70h] [rbp-58h] BYREF

  v2 = (_BYTE *)a2[23];
  v25 = *(_QWORD *)(a1 + 64);
  v4 = 0;
  v5 = *(_QWORD *)(v25 + 1144);
  v26 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_dee7c8ca8cd5355db7ab7a1f63361bba_Traceguids, a2);
  }
  *(_BYTE *)(a2[23] + 3LL) |= 1u;
  if ( (*(_DWORD *)(v5 + 664) & 2) != 0 && *v2 == 4 && a2[24] && (unsigned int)FsRtlIsSystemPagingFile() )
    v4 = 1;
  if ( (int)ClasspGetActiveIoCount(v5) > 0 )
  {
    v6 = 0;
  }
  else
  {
    QpcTimeStamp[0] = 0;
    v6 = &v26;
    UnbiasedInterruptTimePrecise = KeQueryUnbiasedInterruptTimePrecise(QpcTimeStamp);
    v8 = *(_QWORD *)(v5 + 640);
    if ( UnbiasedInterruptTimePrecise < v8 )
      v9 = *(unsigned __int16 *)(v5 + 3856);
    else
      v9 = UnbiasedInterruptTimePrecise - v8;
    v26 = UnbiasedInterruptTimePrecise;
    if ( v9 >= *(unsigned __int16 *)(v5 + 3856) )
    {
      v10 = 1;
      goto LABEL_9;
    }
  }
  v10 = 0;
LABEL_9:
  v11 = *(_DWORD *)(v5 + 3880);
  v12 = *(unsigned __int16 *)(v5 + 3858);
  v13 = 0;
  QpcTimeStamp[0] = 0;
  if ( v11 < v12 )
    v13 = v10;
  v28 = 0;
  *(_OWORD *)v29 = 0;
  if ( (int)IoGetIoAttributionHandle(a2, QpcTimeStamp) >= 0 )
  {
    v23 = (unsigned __int8 *)a2[23];
    v28 = 0;
    LODWORD(v28) = 1;
    *(_OWORD *)v29 = 0;
    DWORD1(v28) = *v23 | 0x300;
    if ( v6 )
      v24 = *v6;
    else
      v24 = KeQueryUnbiasedInterruptTimePrecise(&v29[1]);
    v29[1] = v24;
    IoRecordIoAttribution(QpcTimeStamp[0], &v28);
  }
  v14 = (KSPIN_LOCK *)(v5 + 3672);
  v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 3672));
  v16 = (_QWORD *)(v5 + 16 * (v4 + 230LL));
  if ( (_QWORD *)*v16 == v16 )
  {
    QpcTimeStamp[0] = 0;
    *(_QWORD *)(v5 + 8LL * v4 + 3712) = KeQueryUnbiasedInterruptTimePrecise(QpcTimeStamp);
    v17 = 1;
  }
  else
  {
    v17 = 0;
  }
  v18 = (_QWORD *)v16[1];
  if ( (_QWORD *)*v18 != v16 )
    __fastfail(3u);
  a2[21] = v16;
  a2[22] = v18;
  *v18 = a2 + 21;
  v16[1] = a2 + 21;
  if ( _InterlockedIncrement((volatile signed __int32 *)(v5 + 3864)) == 1 )
    ClasspStartIdleTimer(v5);
  if ( v4 || !v17 )
    v13 = 0;
  if ( ClassPnPETWEnabled )
  {
    *(_OWORD *)QpcTimeStamp = 0;
    IoGetActivityIdIrp(a2, QpcTimeStamp);
    v19 = v25;
    if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x40) != 0 )
      McTemplateK0qdud_EtwWriteTransfer(v22, v21, (unsigned int)QpcTimeStamp, *(_DWORD *)(v25 + 588), 1, 3);
    if ( ClassPnPETWEnabled )
      ClasspWriteEnqueueIdleIOEvent(a2, v25);
  }
  else
  {
    v19 = v25;
  }
  KeReleaseSpinLock(v14, v15);
  if ( v13 )
    ClasspServiceIdleRequest(v19, 0);
  return 259;
}

```

## disassembly

```asm
0x1400024b0  mov     [rsp+arg_10], rbx
0x1400024b5  push    rbp
0x1400024b6  push    rsi
0x1400024b7  push    rdi
0x1400024b8  push    r12
0x1400024ba  push    r13
0x1400024bc  push    r14
0x1400024be  push    r15
0x1400024c0  sub     rsp, 90h
0x1400024c7  mov     rax, cs:__security_cookie
0x1400024ce  xor     rax, rsp
0x1400024d1  mov     [rsp+0C8h+var_48], rax
0x1400024d9  mov     rax, [rcx+40h]
0x1400024dd  xor     esi, esi
0x1400024df  mov     rdi, [rdx+0B8h]
0x1400024e6  mov     rbp, rdx
0x1400024e9  mov     [rsp+0C8h+var_88], rax
0x1400024ee  mov     r13d, esi
0x1400024f1  mov     rbx, [rax+478h]
0x1400024f8  mov     [rsp+0C8h+var_80], rsi
0x1400024fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140002504  lea     rax, WPP_GLOBAL_Control
0x14000250b  cmp     rcx, rax
0x14000250e  jz      short loc_14000251B
0x140002510  mov     eax, [rcx+2Ch]
0x140002513  test    al, al
0x140002515  js      loc_1400027C2
0x14000251b  mov     rax, [rbp+0B8h]
0x140002522  mov     r15d, 1
0x140002528  or      byte ptr [rax+3], 1
0x14000252c  mov     eax, [rbx+298h]
0x140002532  test    al, 2
0x140002534  jnz     loc_1400027E9
0x14000253a  mov     rcx, rbx
0x14000253d  call    ClasspGetActiveIoCount
0x140002542  test    eax, eax
0x140002544  jg      loc_1400027AC
0x14000254a  lea     rcx, [rsp+0C8h+QpcTimeStamp]; QpcTimeStamp
0x14000254f  mov     [rsp+0C8h+QpcTimeStamp], rsi
0x140002554  lea     rdi, [rsp+0C8h+var_80]
0x140002559  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140002560  nop     dword ptr [rax+rax+00h]
0x140002565  mov     rdx, [rbx+280h]
0x14000256c  cmp     rax, rdx
0x14000256f  jb      loc_1400027B6
0x140002575  mov     rcx, rax
0x140002578  sub     rcx, rdx
0x14000257b  mov     [rsp+0C8h+var_80], rax
0x140002580  movzx   eax, word ptr [rbx+0F10h]
0x140002587  cmp     rcx, rax
0x14000258a  jb      loc_1400027AF
0x140002590  movzx   eax, r15b
0x140002594  mov     edx, [rbx+0F28h]
0x14000259a  xorps   xmm0, xmm0
0x14000259d  movzx   ecx, word ptr [rbx+0F12h]
0x1400025a4  mov     r14d, esi
0x1400025a7  cmp     edx, ecx
0x1400025a9  movzx   eax, al
0x1400025ac  lea     rdx, [rsp+0C8h+QpcTimeStamp]
0x1400025b1  mov     [rsp+0C8h+QpcTimeStamp], rsi
0x1400025b6  mov     rcx, rbp
0x1400025b9  cmovl   r14d, eax
0x1400025bd  movups  [rsp+0C8h+var_68], xmm0
0x1400025c2  movups  xmmword ptr [rsp+0C8h+var_58], xmm0
0x1400025c7  call    cs:__imp_IoGetIoAttributionHandle
0x1400025ce  nop     dword ptr [rax+rax+00h]
0x1400025d3  test    eax, eax
0x1400025d5  jns     loc_140002735
0x1400025db  lea     rsi, [rbx+0E58h]
0x1400025e2  mov     rcx, rsi; SpinLock
0x1400025e5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400025ec  nop     dword ptr [rax+rax+00h]
0x1400025f1  mov     r15d, r13d
0x1400025f4  movzx   r12d, al
0x1400025f8  lea     rdi, [r15+0E6h]
0x1400025ff  shl     rdi, 4
0x140002603  add     rdi, rbx
0x140002606  cmp     [rdi], rdi
0x140002609  jz      loc_1400026C0
0x14000260f  xor     r15b, r15b
0x140002612  mov     rcx, [rdi+8]
0x140002616  cmp     [rcx], rdi
0x140002619  jnz     loc_140002792
0x14000261f  lea     rax, [rbp+0A8h]
0x140002626  mov     [rax], rdi
0x140002629  mov     [rax+8], rcx
0x14000262d  mov     [rcx], rax
0x140002630  mov     [rdi+8], rax
0x140002634  mov     eax, 1
0x140002639  lock xadd [rbx+0F18h], eax
0x140002641  inc     eax
0x140002643  cmp     eax, 1
0x140002646  jz      short loc_1400026B6
0x140002648  test    r13d, r13d
0x14000264b  jnz     short loc_1400026B1
0x14000264d  test    r15b, r15b
0x140002650  jz      short loc_1400026B1
0x140002652  cmp     cs:ClassPnPETWEnabled, 0
0x140002659  jnz     loc_1400026EA
0x14000265f  mov     rbx, [rsp+0C8h+var_88]
0x140002664  movzx   edx, r12b; NewIrql
0x140002668  mov     rcx, rsi; SpinLock
0x14000266b  call    cs:__imp_KeReleaseSpinLock
0x140002672  nop     dword ptr [rax+rax+00h]
0x140002677  test    r14b, r14b
0x14000267a  jnz     loc_140002783
0x140002680  mov     eax, 103h
0x140002685  mov     rcx, [rsp+0C8h+var_48]
0x14000268d  xor     rcx, rsp; StackCookie
0x140002690  call    __security_check_cookie
0x140002695  mov     rbx, [rsp+0C8h+arg_10]
0x14000269d  add     rsp, 90h
0x1400026a4  pop     r15
0x1400026a6  pop     r14
0x1400026a8  pop     r13
0x1400026aa  pop     r12
0x1400026ac  pop     rdi
0x1400026ad  pop     rsi
0x1400026ae  pop     rbp
0x1400026af  retn
0x1400026b1  xor     r14b, r14b
0x1400026b4  jmp     short loc_140002652
0x1400026b6  mov     rcx, rbx
0x1400026b9  call    ClasspStartIdleTimer
0x1400026be  jmp     short loc_140002648
0x1400026c0  lea     rcx, [rsp+0C8h+QpcTimeStamp]; QpcTimeStamp
0x1400026c5  mov     [rsp+0C8h+QpcTimeStamp], 0
0x1400026ce  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x1400026d5  nop     dword ptr [rax+rax+00h]
0x1400026da  mov     [rbx+r15*8+0E80h], rax
0x1400026e2  mov     r15b, 1
0x1400026e5  jmp     loc_140002612
0x1400026ea  xorps   xmm0, xmm0
0x1400026ed  lea     rdx, [rsp+0C8h+QpcTimeStamp]
0x1400026f2  mov     rcx, rbp
0x1400026f5  movups  xmmword ptr [rsp+0C8h+QpcTimeStamp], xmm0
0x1400026fa  call    cs:__imp_IoGetActivityIdIrp
0x140002701  nop     dword ptr [rax+rax+00h]
0x140002706  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 40h
0x14000270d  mov     rbx, [rsp+0C8h+var_88]
0x140002712  jnz     loc_140002819
0x140002718  cmp     cs:ClassPnPETWEnabled, 0
0x14000271f  jz      loc_140002664
0x140002725  mov     rdx, rbx
0x140002728  mov     rcx, rbp
0x14000272b  call    ClasspWriteEnqueueIdleIOEvent
0x140002730  jmp     loc_140002664
0x140002735  mov     rax, [rbp+0B8h]
0x14000273c  xorps   xmm0, xmm0
0x14000273f  movups  [rsp+0C8h+var_68], xmm0
0x140002744  mov     dword ptr [rsp+0C8h+var_68], r15d
0x140002749  movups  xmmword ptr [rsp+0C8h+var_58], xmm0
0x14000274e  movzx   ecx, byte ptr [rax]
0x140002751  or      ecx, 300h
0x140002757  mov     dword ptr [rsp+0C8h+var_68+4], ecx
0x14000275b  test    rdi, rdi
0x14000275e  jz      short loc_140002799
0x140002760  mov     rax, [rdi]
0x140002763  mov     rcx, [rsp+0C8h+QpcTimeStamp]
0x140002768  lea     rdx, [rsp+0C8h+var_68]
0x14000276d  mov     [rsp+0C8h+var_58+8], rax
0x140002772  call    cs:__imp_IoRecordIoAttribution
0x140002779  nop     dword ptr [rax+rax+00h]
0x14000277e  jmp     loc_1400025DB
0x140002783  xor     edx, edx
0x140002785  mov     rcx, rbx
0x140002788  call    ClasspServiceIdleRequest
0x14000278d  jmp     loc_140002680
0x140002792  mov     ecx, 3
0x140002797  int     29h; Win8: RtlFailFast(ecx)
0x140002799  lea     rcx, [rsp+0C8h+var_58+8]; QpcTimeStamp
0x14000279e  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x1400027a5  nop     dword ptr [rax+rax+00h]
0x1400027aa  jmp     short loc_140002763
0x1400027ac  mov     rdi, rsi
0x1400027af  xor     al, al
0x1400027b1  jmp     loc_140002594
0x1400027b6  movzx   ecx, word ptr [rbx+0F10h]
0x1400027bd  jmp     loc_14000257B
0x1400027c2  cmp     byte ptr [rcx+29h], 4
0x1400027c6  jb      loc_14000251B
0x1400027cc  mov     rcx, [rcx+18h]
0x1400027d0  lea     r8, WPP_dee7c8ca8cd5355db7ab7a1f63361bba_Traceguids
0x1400027d7  mov     edx, 0Fh
0x1400027dc  mov     r9, rbp
0x1400027df  call    WPP_SF_q
0x1400027e4  jmp     loc_14000251B
0x1400027e9  cmp     byte ptr [rdi], 4
0x1400027ec  jnz     loc_14000253A
0x1400027f2  mov     rcx, [rbp+0C0h]
0x1400027f9  test    rcx, rcx
0x1400027fc  jz      loc_14000253A
0x140002802  call    cs:__imp_FsRtlIsSystemPagingFile
0x140002809  nop     dword ptr [rax+rax+00h]
0x14000280e  test    eax, eax
0x140002810  cmovnz  r13d, r15d
0x140002814  jmp     loc_14000253A
0x140002819  mov     r9d, [rbx+24Ch]
0x140002820  lea     r8, [rsp+0C8h+QpcTimeStamp]
0x140002825  mov     [rsp+0C8h+var_A0], 3
0x14000282a  mov     [rsp+0C8h+var_A8], 1
0x140002832  call    McTemplateK0qdud_EtwWriteTransfer
0x140002837  jmp     loc_140002718
```
