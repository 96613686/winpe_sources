# IsTapiDeviceValid

- ea: `0x140011194`
- end: `0x1400112cf`
- name: `IsTapiDeviceValid`
- size: `315`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140012590`
- `0x1400130a0`
- `0x1400146c0`

## callees

- `0x140001b54`
- `0x140001b84`
- `0x140011194`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140011272`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140011272`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001125f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001125f`
- `NDIS!NdisReleaseRWLock` at `0x14001128a`
- `NDIS!NdisReleaseRWLock` at `0x14001128a`
- `NDIS!NdisAcquireRWLockRead` at `0x1400111f5`
- `NDIS!NdisAcquireRWLockRead` at `0x1400111f5`

## pseudocode

```c
bool __fastcall IsTapiDeviceValid(unsigned int a1, struct _SINGLE_LIST_ENTRY **a2)
{
  struct _NDIS_RW_LOCK_EX *ProcessorHistory; // rcx
  __int64 v5; // rdx
  struct _SINGLE_LIST_ENTRY *Next; // rdi
  __int64 Next_low; // r9
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 151, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids, a1);
  ProcessorHistory = (struct _NDIS_RW_LOCK_EX *)WPP_MAIN_CB.Dpc.ProcessorHistory;
  *a2 = 0;
  NdisAcquireRWLockRead(ProcessorHistory, &LockState, 0);
  v5 = 0;
  if ( *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1) )
  {
    while ( 1 )
    {
      Next = WPP_MAIN_CB.Dpc.DpcListEntry.Next[v5].Next;
      if ( Next )
      {
        Next_low = LODWORD(Next[4].Next);
        if ( (_DWORD)Next_low == a1 )
          break;
      }
      v5 = (unsigned int)(v5 + 1);
      if ( (unsigned int)v5 >= *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1) )
        goto LABEL_13;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 152, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids, Next_low);
    *a2 = Next;
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&Next[15]);
    ++LODWORD(Next[2].Next);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&Next[15]);
  }
LABEL_13:
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 153, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
  return *a2 != 0;
}

```

## disassembly

```asm
0x140011194  push    rbx
0x140011196  push    rsi
0x140011197  push    rdi
0x140011198  push    r14
0x14001119a  sub     rsp, 28h
0x14001119e  xor     eax, eax
0x1400111a0  mov     rsi, rdx
0x1400111a3  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x1400111a8  mov     ebx, ecx
0x1400111aa  mov     [rsp+48h+LockState.Flags], al
0x1400111ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400111b5  lea     r14, WPP_GLOBAL_Control
0x1400111bc  cmp     rcx, r14
0x1400111bf  jz      short loc_1400111DF
0x1400111c1  cmp     byte ptr [rcx+29h], 5
0x1400111c5  jb      short loc_1400111DF
0x1400111c7  mov     rcx, [rcx+18h]
0x1400111cb  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x1400111d2  mov     edx, 97h
0x1400111d7  mov     r9d, ebx
0x1400111da  call    WPP_SF_d
0x1400111df  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x1400111e6  lea     rdx, [rsp+48h+LockState]; LockState
0x1400111eb  xor     r8d, r8d; Flags
0x1400111ee  mov     qword ptr [rsi], 0
0x1400111f5  call    cs:__imp_NdisAcquireRWLockRead
0x1400111fc  nop     dword ptr [rax+rax+00h]
0x140011201  mov     r8d, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4
0x140011208  xor     edx, edx
0x14001120a  test    r8d, r8d
0x14001120d  jz      short loc_14001127E
0x14001120f  mov     rax, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x140011216  mov     rdi, [rax+rdx*8]
0x14001121a  test    rdi, rdi
0x14001121d  jz      short loc_140011228
0x14001121f  mov     r9d, [rdi+20h]
0x140011223  cmp     r9d, ebx
0x140011226  jz      short loc_140011231
0x140011228  inc     edx
0x14001122a  cmp     edx, r8d
0x14001122d  jb      short loc_14001120F
0x14001122f  jmp     short loc_14001127E
0x140011231  mov     rcx, cs:WPP_GLOBAL_Control
0x140011238  cmp     rcx, r14
0x14001123b  jz      short loc_140011258
0x14001123d  cmp     byte ptr [rcx+29h], 5
0x140011241  jb      short loc_140011258
0x140011243  mov     rcx, [rcx+18h]
0x140011247  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x14001124e  mov     edx, 98h
0x140011253  call    WPP_SF_d
0x140011258  lea     rcx, [rdi+78h]; SpinLock
0x14001125c  mov     [rsi], rdi
0x14001125f  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140011266  nop     dword ptr [rax+rax+00h]
0x14001126b  inc     dword ptr [rdi+10h]
0x14001126e  lea     rcx, [rdi+78h]; SpinLock
0x140011272  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140011279  nop     dword ptr [rax+rax+00h]
0x14001127e  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x140011285  lea     rdx, [rsp+48h+LockState]; LockState
0x14001128a  call    cs:__imp_NdisReleaseRWLock
0x140011291  nop     dword ptr [rax+rax+00h]
0x140011296  mov     rcx, cs:WPP_GLOBAL_Control
0x14001129d  cmp     rcx, r14
0x1400112a0  jz      short loc_1400112BD
0x1400112a2  cmp     byte ptr [rcx+29h], 5
0x1400112a6  jb      short loc_1400112BD
0x1400112a8  mov     rcx, [rcx+18h]
0x1400112ac  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x1400112b3  mov     edx, 99h
0x1400112b8  call    WPP_SF_
0x1400112bd  cmp     qword ptr [rsi], 0
0x1400112c1  setnz   al
0x1400112c4  add     rsp, 28h
0x1400112c8  pop     r14
0x1400112ca  pop     rdi
0x1400112cb  pop     rsi
0x1400112cc  pop     rbx
0x1400112cd  retn
```
