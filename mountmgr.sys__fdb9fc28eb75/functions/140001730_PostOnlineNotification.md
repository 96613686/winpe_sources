# PostOnlineNotification

- ea: `0x140001730`
- end: `0x140001950`
- name: `PostOnlineNotification`
- size: `544`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000be4c`
- `0x14000e340`
- `0x14000f680`
- `0x1400119a0`

## callees

- `0x140001730`
- `0x140001b30`
- `0x140002f80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001861`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001861`
- `ntoskrnl!ExQueueWorkItem` at `0x14000188e`
- `ntoskrnl!ExQueueWorkItem` at `0x14000188e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400018a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001900`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400018a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001900`
- `ntoskrnl!ExAllocatePool2` at `0x140001755`
- `ntoskrnl!ExAllocatePool2` at `0x1400017d5`
- `ntoskrnl!ExAllocatePool2` at `0x140001755`
- `ntoskrnl!ExAllocatePool2` at `0x1400017d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400017ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400017ef`

## pseudocode

```c
__int64 __fastcall PostOnlineNotification(__int64 a1, __int16 *a2)
{
  _QWORD *Pool2; // rax
  _QWORD *v5; // rbx
  __int64 result; // rax
  unsigned __int16 v7; // ax
  void *v8; // rax
  KSPIN_LOCK *v9; // rsi
  KIRQL v10; // al
  KIRQL v11; // bp
  PDEVICE_OBJECT v12; // rcx
  unsigned __int16 v13; // dx
  __int64 v14; // rdi
  _QWORD *v15; // rax

  Pool2 = (_QWORD *)ExAllocatePool2(66, 56, 1098149453);
  v5 = Pool2;
  if ( !Pool2 )
  {
    result = (__int64)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 4) != 0 )
        return WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0x160u);
    }
    return result;
  }
  Pool2[3] = Pool2;
  Pool2[2] = SendOnlineNotificationWorker;
  *Pool2 = 0;
  Pool2[4] = a1;
  v7 = *a2;
  *((_WORD *)v5 + 20) = *a2;
  v7 += 2;
  *((_WORD *)v5 + 21) = v7;
  v8 = (void *)ExAllocatePool2(66, v7, 1098149453);
  v5[6] = v8;
  if ( !v8 )
  {
    ExFreePoolWithTag(v5, 0);
    result = (__int64)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 4) != 0 )
        return WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0x161u);
    }
    return result;
  }
  memmove(v8, *((const void **)a2 + 1), *((unsigned __int16 *)v5 + 20));
  v9 = (KSPIN_LOCK *)(a1 + 256);
  *(_WORD *)(v5[6] + 2 * ((unsigned __int64)*((unsigned __int16 *)v5 + 20) >> 1)) = 0;
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 256));
  ++*(_DWORD *)(a1 + 308);
  v11 = v10;
  if ( !*(_BYTE *)(a1 + 304) )
  {
    *(_BYTE *)(a1 + 304) = 1;
    ExQueueWorkItem((PWORK_QUEUE_ITEM)v5, DelayedWorkQueue);
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 256), v11);
    v12 = WPP_GLOBAL_Control;
    result = (__int64)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return result;
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return result;
    v13 = 354;
    return WPP_SF_((__int64)v12->AttachedDevice, v13);
  }
  v14 = a1 + 288;
  v15 = *(_QWORD **)(v14 + 8);
  if ( *v15 != v14 )
    __fastfail(3u);
  *v5 = v14;
  v5[1] = v15;
  *v15 = v5;
  *(_QWORD *)(v14 + 8) = v5;
  KeReleaseSpinLock(v9, v11);
  v12 = WPP_GLOBAL_Control;
  result = (__int64)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v13 = 355;
      return WPP_SF_((__int64)v12->AttachedDevice, v13);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140001730  mov     [rsp+arg_8], rbx
0x140001735  mov     [rsp+arg_10], rsi
0x14000173a  push    rdi
0x14000173b  sub     rsp, 20h
0x14000173f  mov     rsi, rdx
0x140001742  mov     rdi, rcx
0x140001745  mov     edx, 38h ; '8'
0x14000174a  mov     ecx, 42h ; 'B'
0x14000174f  mov     r8d, 41746E4Dh
0x140001755  call    cs:__imp_ExAllocatePool2
0x14000175c  nop     dword ptr [rax+rax+00h]
0x140001761  mov     rbx, rax
0x140001764  test    rax, rax
0x140001767  jnz     short loc_14000179E
0x140001769  mov     rcx, cs:WPP_GLOBAL_Control
0x140001770  lea     rax, WPP_GLOBAL_Control
0x140001777  cmp     rcx, rax
0x14000177a  jz      loc_14000193F
0x140001780  mov     eax, [rcx+2Ch]
0x140001783  test    al, 4
0x140001785  jz      loc_14000193F
0x14000178b  mov     rcx, [rcx+18h]
0x14000178f  mov     edx, 160h
0x140001794  call    WPP_SF_
0x140001799  jmp     loc_14000193F
0x14000179e  mov     [rbx+18h], rbx
0x1400017a2  lea     rax, SendOnlineNotificationWorker
0x1400017a9  mov     [rbx+10h], rax
0x1400017ad  mov     ecx, 42h ; 'B'
0x1400017b2  mov     qword ptr [rbx], 0
0x1400017b9  mov     r8d, 41746E4Dh
0x1400017bf  mov     [rbx+20h], rdi
0x1400017c3  movzx   eax, word ptr [rsi]
0x1400017c6  mov     [rbx+28h], ax
0x1400017ca  add     ax, 2
0x1400017ce  movzx   edx, ax
0x1400017d1  mov     [rbx+2Ah], dx
0x1400017d5  call    cs:__imp_ExAllocatePool2
0x1400017dc  nop     dword ptr [rax+rax+00h]
0x1400017e1  mov     [rbx+30h], rax
0x1400017e5  test    rax, rax
0x1400017e8  jnz     short loc_140001830
0x1400017ea  xor     edx, edx; Tag
0x1400017ec  mov     rcx, rbx; P
0x1400017ef  call    cs:__imp_ExFreePoolWithTag
0x1400017f6  nop     dword ptr [rax+rax+00h]
0x1400017fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140001802  lea     rax, WPP_GLOBAL_Control
0x140001809  cmp     rcx, rax
0x14000180c  jz      loc_14000193F
0x140001812  mov     eax, [rcx+2Ch]
0x140001815  test    al, 4
0x140001817  jz      loc_14000193F
0x14000181d  mov     rcx, [rcx+18h]
0x140001821  mov     edx, 161h
0x140001826  call    WPP_SF_
0x14000182b  jmp     loc_14000193F
0x140001830  movzx   r8d, word ptr [rbx+28h]; Size
0x140001835  mov     rcx, rax; void *
0x140001838  mov     rdx, [rsi+8]; Src
0x14000183c  mov     [rsp+28h+arg_0], rbp
0x140001841  call    memmove
0x140001846  movzx   edx, word ptr [rbx+28h]
0x14000184a  lea     rsi, [rdi+100h]
0x140001851  mov     rcx, [rbx+30h]
0x140001855  xor     eax, eax
0x140001857  shr     rdx, 1
0x14000185a  mov     [rcx+rdx*2], ax
0x14000185e  mov     rcx, rsi; SpinLock
0x140001861  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001868  nop     dword ptr [rax+rax+00h]
0x14000186d  inc     dword ptr [rdi+134h]
0x140001873  movzx   ebp, al
0x140001876  cmp     byte ptr [rdi+130h], 0
0x14000187d  jnz     short loc_1400018D4
0x14000187f  mov     edx, 1; QueueType
0x140001884  mov     byte ptr [rdi+130h], 1
0x14000188b  mov     rcx, rbx; WorkItem
0x14000188e  call    cs:__imp_ExQueueWorkItem
0x140001895  nop     dword ptr [rax+rax+00h]
0x14000189a  movzx   edx, bpl; NewIrql
0x14000189e  mov     rcx, rsi; SpinLock
0x1400018a1  call    cs:__imp_KeReleaseSpinLock
0x1400018a8  nop     dword ptr [rax+rax+00h]
0x1400018ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400018b4  lea     rax, WPP_GLOBAL_Control
0x1400018bb  cmp     rcx, rax
0x1400018be  jz      short loc_14000193A
0x1400018c0  mov     eax, [rcx+2Ch]
0x1400018c3  test    al, 1
0x1400018c5  jz      short loc_14000193A
0x1400018c7  cmp     byte ptr [rcx+29h], 2
0x1400018cb  jb      short loc_14000193A
0x1400018cd  mov     edx, 162h
0x1400018d2  jmp     short loc_140001931
0x1400018d4  add     rdi, 120h
0x1400018db  mov     rax, [rdi+8]
0x1400018df  cmp     [rax], rdi
0x1400018e2  jz      short loc_1400018EB
0x1400018e4  mov     ecx, 3
0x1400018e9  int     29h; Win8: RtlFailFast(ecx)
0x1400018eb  mov     [rbx], rdi
0x1400018ee  movzx   edx, bpl; NewIrql
0x1400018f2  mov     [rbx+8], rax
0x1400018f6  mov     rcx, rsi; SpinLock
0x1400018f9  mov     [rax], rbx
0x1400018fc  mov     [rdi+8], rbx
0x140001900  call    cs:__imp_KeReleaseSpinLock
0x140001907  nop     dword ptr [rax+rax+00h]
0x14000190c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001913  lea     rax, WPP_GLOBAL_Control
0x14000191a  cmp     rcx, rax
0x14000191d  jz      short loc_14000193A
0x14000191f  mov     eax, [rcx+2Ch]
0x140001922  test    al, 1
0x140001924  jz      short loc_14000193A
0x140001926  cmp     byte ptr [rcx+29h], 2
0x14000192a  jb      short loc_14000193A
0x14000192c  mov     edx, 163h
0x140001931  mov     rcx, [rcx+18h]
0x140001935  call    WPP_SF_
0x14000193a  mov     rbp, [rsp+28h+arg_0]
0x14000193f  mov     rbx, [rsp+28h+arg_8]
0x140001944  mov     rsi, [rsp+28h+arg_10]
0x140001949  add     rsp, 20h
0x14000194d  pop     rdi
0x14000194e  retn
```
