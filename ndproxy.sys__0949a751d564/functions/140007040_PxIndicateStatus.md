# PxIndicateStatus

- ea: `0x140007040`
- end: `0x14000724c`
- name: `PxIndicateStatus`
- size: `524`
- prototype: `void __fastcall(_QWORD *Src)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400062c0`
- `0x14000f020`
- `0x14000f250`
- `0x14000f830`
- `0x14000fcb0`
- `0x140010600`
- `0x140013bc0`
- `0x140015290`

## callees

- `0x140001b54`
- `0x140007040`
- `0x140007354`
- `0x1400073bc`
- `0x1400081c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007107`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007107`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000705c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400070d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000705c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400070d7`
- `ntoskrnl!IofCompleteRequest` at `0x14000722f`
- `ntoskrnl!IofCompleteRequest` at `0x14000722f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000717d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000717d`

## pseudocode

```c
void __fastcall PxIndicateStatus(_QWORD *Src)
{
  KIRQL v2; // al
  KIRQL v3; // al
  struct _LIST_ENTRY *Blink; // rsi
  PVOID **v5; // rax
  PVOID **v6; // rbx
  PVOID ***v7; // rax
  struct _LIST_ENTRY *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink);
  LOBYTE(WPP_MAIN_CB.SectorSize) = v2;
  if ( LODWORD(WPP_MAIN_CB.Dpc.DpcData) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 135, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, WPP_MAIN_CB.SectorSize);
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, v2);
    v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
    Blink = WPP_MAIN_CB.Queue.ListEntry.Blink;
    LOBYTE(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) = v3;
    WPP_MAIN_CB.Queue.ListEntry.Blink = 0;
    if ( !Blink )
    {
      v5 = (PVOID **)ExAllocateFromNPagedLookasideList(&ProviderEventLookaside);
      v6 = v5;
      if ( v5 )
      {
        memmove(v5 + 2, Src, 0x30u);
        v7 = *(PVOID ****)&WPP_MAIN_CB.DeviceType;
        if ( **(struct _DEVICE_OBJECT ***)&WPP_MAIN_CB.DeviceType != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceExtension )
          __fastfail(3u);
        v6[1] = *(PVOID **)&WPP_MAIN_CB.DeviceType;
        *v6 = &WPP_MAIN_CB.DeviceExtension;
        *v7 = v6;
        *(_QWORD *)&WPP_MAIN_CB.DeviceType = v6;
        if ( ++LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink) > HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) )
          HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) = WPP_MAIN_CB.Queue.ListEntry.Flink;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, (KIRQL)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
    if ( Blink )
    {
      _InterlockedExchange64((volatile __int64 *)&Blink[6].Blink, 0);
      v8 = Blink[1].Blink;
      LODWORD(Blink[3].Flink) = 0;
      Blink[3].Blink = (struct _LIST_ENTRY *)59;
      memmove(&v8->Blink, Src, 0x30u);
      HIDWORD(v8->Flink) = 48;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_PPL(WPP_GLOBAL_Control->AttachedDevice, v9, v10, *Src, Src[1], *((_DWORD *)Src + 4));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_PPP(WPP_GLOBAL_Control->AttachedDevice, v9, v10, Src[3], Src[4], Src[5]);
      }
      IofCompleteRequest((PIRP)Blink, 2);
    }
  }
}

```

## disassembly

```asm
0x140007040  mov     [rsp+arg_0], rbx
0x140007045  mov     [rsp+arg_8], rsi
0x14000704a  push    rdi
0x14000704b  sub     rsp, 30h
0x14000704f  mov     rdi, rcx
0x140007052  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink
0x140007059  mov     rcx, rsi; SpinLock
0x14000705c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007063  nop     dword ptr [rax+rax+00h]
0x140007068  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DpcData, 0
0x14000706f  mov     byte ptr cs:WPP_MAIN_CB.SectorSize, al
0x140007075  jz      short loc_1400070BF
0x140007077  mov     rcx, cs:WPP_GLOBAL_Control
0x14000707e  lea     rbx, WPP_GLOBAL_Control
0x140007085  cmp     rcx, rbx
0x140007088  jz      short loc_1400070A5
0x14000708a  cmp     byte ptr [rcx+29h], 3
0x14000708e  jb      short loc_1400070A5
0x140007090  mov     rcx, [rcx+18h]
0x140007094  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x14000709b  mov     edx, 87h
0x1400070a0  call    WPP_SF_
0x1400070a5  mov     dl, byte ptr cs:WPP_MAIN_CB.SectorSize; NewIrql
0x1400070ab  mov     rcx, rsi; SpinLock
0x1400070ae  call    cs:__imp_KeReleaseSpinLock
0x1400070b5  nop     dword ptr [rax+rax+00h]
0x1400070ba  jmp     loc_14000723B
0x1400070bf  mov     dl, al; NewIrql
0x1400070c1  mov     rcx, rsi; SpinLock
0x1400070c4  call    cs:__imp_KeReleaseSpinLock
0x1400070cb  nop     dword ptr [rax+rax+00h]
0x1400070d0  lea     rcx, WPP_MAIN_CB.Queue+10h; SpinLock
0x1400070d7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400070de  nop     dword ptr [rax+rax+00h]
0x1400070e3  mov     rsi, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400070ea  mov     byte ptr cs:WPP_MAIN_CB.Queue+18h, al
0x1400070f0  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, 0
0x1400070fb  test    rsi, rsi
0x1400070fe  jnz     short loc_140007170
0x140007100  lea     rcx, ProviderEventLookaside; Lookaside
0x140007107  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000710e  nop     dword ptr [rax+rax+00h]
0x140007113  mov     rbx, rax
0x140007116  test    rax, rax
0x140007119  jz      short loc_140007170
0x14000711b  lea     rcx, [rax+10h]; void *
0x14000711f  mov     rdx, rdi; Src
0x140007122  lea     r8d, [rsi+30h]; Size
0x140007126  call    memmove
0x14000712b  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceType
0x140007132  lea     rcx, WPP_MAIN_CB.DeviceExtension
0x140007139  cmp     [rax], rcx
0x14000713c  jz      short loc_140007143
0x14000713e  lea     ecx, [rsi+3]
0x140007141  int     29h; Win8: RtlFailFast(ecx)
0x140007143  mov     [rbx+8], rax
0x140007147  mov     [rbx], rcx
0x14000714a  mov     [rax], rbx
0x14000714d  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x140007153  inc     eax
0x140007155  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rbx
0x14000715c  cmp     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x140007162  mov     dword ptr cs:WPP_MAIN_CB.Queue, eax
0x140007168  jbe     short loc_140007170
0x14000716a  mov     dword ptr cs:WPP_MAIN_CB.Queue+4, eax
0x140007170  mov     dl, byte ptr cs:WPP_MAIN_CB.Queue+18h; NewIrql
0x140007176  lea     rcx, WPP_MAIN_CB.Queue+10h; SpinLock
0x14000717d  call    cs:__imp_KeReleaseSpinLock
0x140007184  nop     dword ptr [rax+rax+00h]
0x140007189  test    rsi, rsi
0x14000718c  jz      loc_14000723B
0x140007192  xor     eax, eax
0x140007194  mov     r8d, 30h ; '0'; Size
0x14000719a  xchg    rax, [rsi+68h]
0x14000719e  mov     rbx, [rsi+18h]
0x1400071a2  mov     rdx, rdi; Src
0x1400071a5  mov     dword ptr [rsi+30h], 0
0x1400071ac  mov     qword ptr [rsi+38h], 3Bh ; ';'
0x1400071b4  lea     rcx, [rbx+8]; void *
0x1400071b8  call    memmove
0x1400071bd  mov     dword ptr [rbx+4], 30h ; '0'
0x1400071c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400071cb  lea     rbx, WPP_GLOBAL_Control
0x1400071d2  cmp     rcx, rbx
0x1400071d5  jz      short loc_14000722A
0x1400071d7  cmp     byte ptr [rcx+29h], 5
0x1400071db  jb      short loc_1400071F9
0x1400071dd  mov     eax, [rdi+10h]
0x1400071e0  mov     r9, [rdi]
0x1400071e3  mov     rcx, [rcx+18h]
0x1400071e7  mov     dword ptr [rsp+38h+var_10], eax
0x1400071eb  mov     rax, [rdi+8]
0x1400071ef  mov     [rsp+38h+var_18], rax
0x1400071f4  call    WPP_SF_PPL
0x1400071f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140007200  cmp     rcx, rbx
0x140007203  jz      short loc_14000722A
0x140007205  cmp     byte ptr [rcx+29h], 5
0x140007209  jb      short loc_14000722A
0x14000720b  mov     rax, [rdi+28h]
0x14000720f  mov     r9, [rdi+18h]
0x140007213  mov     rcx, [rcx+18h]
0x140007217  mov     [rsp+38h+var_10], rax
0x14000721c  mov     rax, [rdi+20h]
0x140007220  mov     [rsp+38h+var_18], rax
0x140007225  call    WPP_SF_PPP
0x14000722a  mov     dl, 2; PriorityBoost
0x14000722c  mov     rcx, rsi; Irp
0x14000722f  call    cs:__imp_IofCompleteRequest
0x140007236  nop     dword ptr [rax+rax+00h]
0x14000723b  mov     rbx, [rsp+38h+arg_0]
0x140007240  mov     rsi, [rsp+38h+arg_8]
0x140007245  add     rsp, 30h
0x140007249  pop     rdi
0x14000724a  retn
```
