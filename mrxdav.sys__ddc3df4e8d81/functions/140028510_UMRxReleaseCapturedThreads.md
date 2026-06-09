# UMRxReleaseCapturedThreads

- ea: `0x140028510`
- end: `0x1400286e7`
- name: `UMRxReleaseCapturedThreads`
- size: `471`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000f120`
- `0x14000f780`

## callees

- `0x14000163c`
- `0x1400017e4`
- `0x140028510`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140028542`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002857e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400285fb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400286b3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028542`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002857e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400285fb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400286b3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400285be`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400285be`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400285d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140028636`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400285d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140028636`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400285a6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400285a6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002861e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002868e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002861e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002868e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140028682`
- `ntoskrnl!KeWaitForSingleObject` at `0x140028682`
- `ntoskrnl!KeInsertQueue` at `0x140028650`
- `ntoskrnl!KeInsertQueue` at `0x140028650`

## pseudocode

```c
void __fastcall UMRxReleaseCapturedThreads(__int64 a1)
{
  __int64 v2; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v4; // rbx
  HANDLE v5; // rax
  struct _ERESOURCE *v6; // rcx
  __int64 v7; // rbx
  HANDLE v8; // rax
  __int64 v9; // rbx
  HANDLE v10; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v2 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v2, 103, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v5 = PsGetCurrentThreadId();
      WPP_SF_qq(v4, 104, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v5, a1);
    }
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 1456), 1u);
  v6 = (struct _ERESOURCE *)(a1 + 1456);
  if ( *(_BYTE *)(a1 + 1616) )
  {
    *(_BYTE *)(a1 + 1616) = 0;
    ExReleaseResourceLite(v6);
    KeInsertQueue((PRKQUEUE)(a1 + 1392), (PLIST_ENTRY)(a1 + 1568));
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 1608), 0, 0) )
      KeWaitForSingleObject((PVOID)(a1 + 1584), Executive, 1, 0, 0);
    KeLeaveCriticalRegion();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v10 = PsGetCurrentThreadId();
      WPP_SF_q(v9, 106, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v10);
    }
  }
  else
  {
    ExReleaseResourceLite(v6);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v8 = PsGetCurrentThreadId();
      WPP_SF_q(v7, 105, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v8);
    }
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x140028510  mov     [rsp+arg_8], rbx
0x140028515  mov     [rsp+arg_10], rsi
0x14002851a  push    rdi
0x14002851b  sub     rsp, 30h
0x14002851f  mov     rdi, rcx
0x140028522  mov     rbx, cs:WPP_GLOBAL_Control
0x140028529  lea     rsi, WPP_GLOBAL_Control
0x140028530  cmp     rbx, rsi
0x140028533  jz      short loc_1400285A6
0x140028535  test    dword ptr [rbx+2Ch], 800h
0x14002853c  jz      short loc_140028565
0x14002853e  mov     rbx, [rbx+18h]
0x140028542  call    cs:__imp_PsGetCurrentThreadId
0x140028549  nop     dword ptr [rax+rax+00h]
0x14002854e  mov     edx, 67h ; 'g'
0x140028553  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x14002855a  mov     r9, rax
0x14002855d  mov     rcx, rbx
0x140028560  call    WPP_SF_q
0x140028565  mov     rbx, cs:WPP_GLOBAL_Control
0x14002856c  cmp     rbx, rsi
0x14002856f  jz      short loc_1400285A6
0x140028571  test    dword ptr [rbx+2Ch], 200h
0x140028578  jz      short loc_1400285A6
0x14002857a  mov     rbx, [rbx+18h]
0x14002857e  call    cs:__imp_PsGetCurrentThreadId
0x140028585  nop     dword ptr [rax+rax+00h]
0x14002858a  mov     edx, 68h ; 'h'
0x14002858f  mov     [rsp+38h+Timeout], rdi
0x140028594  mov     r9, rax
0x140028597  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x14002859e  mov     rcx, rbx
0x1400285a1  call    WPP_SF_qq
0x1400285a6  call    cs:__imp_KeEnterCriticalRegion
0x1400285ad  nop     dword ptr [rax+rax+00h]
0x1400285b2  lea     rbx, [rdi+5B0h]
0x1400285b9  mov     dl, 1; Wait
0x1400285bb  mov     rcx, rbx; Resource
0x1400285be  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400285c5  nop     dword ptr [rax+rax+00h]
0x1400285ca  cmp     byte ptr [rdi+650h], 0
0x1400285d1  mov     rcx, rbx; Resource
0x1400285d4  jnz     short loc_14002862F
0x1400285d6  call    cs:__imp_ExReleaseResourceLite
0x1400285dd  nop     dword ptr [rax+rax+00h]
0x1400285e2  mov     rbx, cs:WPP_GLOBAL_Control
0x1400285e9  cmp     rbx, rsi
0x1400285ec  jz      short loc_14002861E
0x1400285ee  test    dword ptr [rbx+2Ch], 400h
0x1400285f5  jz      short loc_14002861E
0x1400285f7  mov     rbx, [rbx+18h]
0x1400285fb  call    cs:__imp_PsGetCurrentThreadId
0x140028602  nop     dword ptr [rax+rax+00h]
0x140028607  mov     edx, 69h ; 'i'
0x14002860c  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028613  mov     r9, rax
0x140028616  mov     rcx, rbx
0x140028619  call    WPP_SF_q
0x14002861e  call    cs:__imp_KeLeaveCriticalRegion
0x140028625  nop     dword ptr [rax+rax+00h]
0x14002862a  jmp     loc_1400286D6
0x14002862f  mov     byte ptr [rdi+650h], 0
0x140028636  call    cs:__imp_ExReleaseResourceLite
0x14002863d  nop     dword ptr [rax+rax+00h]
0x140028642  lea     rdx, [rdi+620h]; Entry
0x140028649  lea     rcx, [rdi+570h]; Queue
0x140028650  call    cs:__imp_KeInsertQueue
0x140028657  nop     dword ptr [rax+rax+00h]
0x14002865c  xor     ecx, ecx
0x14002865e  xor     eax, eax
0x140028660  lock cmpxchg [rdi+648h], ecx
0x140028668  jz      short loc_14002868E
0x14002866a  lea     rcx, [rdi+630h]; Object
0x140028671  mov     [rsp+38h+Timeout], 0; Timeout
0x14002867a  xor     r9d, r9d; Alertable
0x14002867d  mov     r8b, 1; WaitMode
0x140028680  xor     edx, edx; WaitReason
0x140028682  call    cs:__imp_KeWaitForSingleObject
0x140028689  nop     dword ptr [rax+rax+00h]
0x14002868e  call    cs:__imp_KeLeaveCriticalRegion
0x140028695  nop     dword ptr [rax+rax+00h]
0x14002869a  mov     rbx, cs:WPP_GLOBAL_Control
0x1400286a1  cmp     rbx, rsi
0x1400286a4  jz      short loc_1400286D6
0x1400286a6  test    dword ptr [rbx+2Ch], 800h
0x1400286ad  jz      short loc_1400286D6
0x1400286af  mov     rbx, [rbx+18h]
0x1400286b3  call    cs:__imp_PsGetCurrentThreadId
0x1400286ba  nop     dword ptr [rax+rax+00h]
0x1400286bf  mov     edx, 6Ah ; 'j'
0x1400286c4  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400286cb  mov     r9, rax
0x1400286ce  mov     rcx, rbx
0x1400286d1  call    WPP_SF_q
0x1400286d6  mov     rbx, [rsp+38h+arg_8]
0x1400286db  mov     rsi, [rsp+38h+arg_10]
0x1400286e0  add     rsp, 30h
0x1400286e4  pop     rdi
0x1400286e5  retn
```
