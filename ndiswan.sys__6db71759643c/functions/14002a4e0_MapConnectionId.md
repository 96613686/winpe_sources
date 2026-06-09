# MapConnectionId

- ea: `0x14002a4e0`
- end: `0x14002a836`
- name: `MapConnectionId`
- size: `854`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400359f4`

## callees

- `0x1400084d8`
- `0x14000a290`
- `0x14000a5f4`
- `0x14000a648`
- `0x140016400`
- `0x14002a4e0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002a641`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002a743`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002a641`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002a743`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002a656`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002a730`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002a78b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002a656`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002a730`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002a78b`
- `ntoskrnl!KeSetTimer` at `0x14002a778`
- `ntoskrnl!KeSetTimer` at `0x14002a778`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a7ca`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a7ca`
- `NDIS!NdisAcquireRWLockRead` at `0x14002a5cc`
- `NDIS!NdisAcquireRWLockRead` at `0x14002a5cc`
- `NDIS!NdisReleaseRWLock` at `0x14002a66e`
- `NDIS!NdisReleaseRWLock` at `0x14002a7a3`
- `NDIS!NdisReleaseRWLock` at `0x14002a66e`
- `NDIS!NdisReleaseRWLock` at `0x14002a7a3`

## pseudocode

```c
__int64 __fastcall MapConnectionId(__int64 a1, unsigned int a2, _QWORD *a3, unsigned int a4, _DWORD *a5)
{
  _DWORD *v9; // r14
  int v10; // eax
  unsigned int v11; // eax
  __int64 result; // rax
  _QWORD *v13; // rdx
  unsigned int v14; // eax
  _QWORD *v15; // rbx
  _QWORD *i; // rcx
  int v17; // eax
  __int64 v18; // rcx
  unsigned int v19; // ecx
  __int64 v20; // rdi
  struct _LOCK_STATE_EX LockState; // [rsp+78h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  v9 = a5;
  *a5 = 48;
  if ( a2 < 0x30 || a4 < 0x30 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a4, 48);
    }
    return 3221225476LL;
  }
  else
  {
    if ( !*(_QWORD *)(a1 + 24) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
      }
      if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
        v10 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
      else
        v10 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline();
      v11 = v10 != 0 ? 0xBFFFFDAF : 0;
      return v11 + 601;
    }
    NdisAcquireRWLockRead(ConnTableLock, &LockState, 0);
    v13 = ConnectionTable;
    v14 = *(_DWORD *)(a1 + 16);
    if ( v14 >= *((_DWORD *)ConnectionTable + 1)
      || (_mm_lfence(), v13 = ConnectionTable, (v15 = *(_QWORD **)(*((_QWORD *)ConnectionTable + 7) + 8LL * v14)) == 0)
      || v15[6] )
    {
      for ( i = (_QWORD *)v13[6]; i != v13 + 5; i = (_QWORD *)i[1] )
      {
        v15 = i - 32;
        if ( i != (_QWORD *)256 && *(_QWORD *)(a1 + 16) == v15[8] && !v15[6] )
          goto LABEL_26;
      }
      goto LABEL_28;
    }
LABEL_26:
    KeAcquireSpinLockAtDpcLevel(v15 + 92);
    if ( *((_DWORD *)v15 + 5) != 2 )
    {
      KeReleaseSpinLockFromDpcLevel(v15 + 92);
LABEL_28:
      NdisReleaseRWLock(ConnTableLock, &LockState);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          WPP_5659416b879e33cc7e241cd80588418e_Traceguids,
          *(_QWORD *)(a1 + 16));
      }
      *v9 = 0;
      if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
        v17 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
      else
        v17 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline();
      v11 = v17 != 0 ? 0xBFFFFFCC : 0;
      return v11 + 601;
    }
    v18 = v15[10];
    *a3 = v15[5];
    a3[1] = *(_QWORD *)(v18 + 32);
    v15[6] = *(_QWORD *)(a1 + 24);
    *(_QWORD *)(v18 + 40) = *(_QWORD *)(a1 + 32);
    ++*((_DWORD *)v15 + 7);
    *((_DWORD *)v15 + 9) |= 2u;
    v19 = *(_DWORD *)(a1 + 40);
    if ( a2 - 44 <= v19 )
      v19 = a2 - 44;
    if ( v19 > 0x100 )
      v19 = 256;
    memmove((char *)v15 + 324, (const void *)(a1 + 44), v19);
    v20 = v15[9];
    *((_BYTE *)v15 + 579) = 0;
    KeReleaseSpinLockFromDpcLevel(v15 + 92);
    KeAcquireSpinLockAtDpcLevel(&SpinLock);
    if ( *((_DWORD *)v15 + 24) && !byte_14001E3C8 )
    {
      byte_14001E3C8 = 1;
      KeSetTimer(&Timer, (LARGE_INTEGER)15LL, &Dpc);
    }
    KeReleaseSpinLockFromDpcLevel(&SpinLock);
    NdisReleaseRWLock(ConnTableLock, &LockState);
    result = 0;
    if ( v20 )
    {
      KeWaitForSingleObject((PVOID)(v20 + 480), Executive, 0, 1u, 0);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002a4e0  push    rbx
0x14002a4e2  push    rbp
0x14002a4e3  push    rsi
0x14002a4e4  push    rdi
0x14002a4e5  push    r14
0x14002a4e7  push    r15
0x14002a4e9  sub     rsp, 38h
0x14002a4ed  xor     eax, eax
0x14002a4ef  mov     ebx, r9d
0x14002a4f2  mov     word ptr [rsp+68h+LockState.OldIrql], ax
0x14002a4f7  mov     r15, r8
0x14002a4fa  mov     [rsp+68h+LockState.Flags], al
0x14002a4fe  mov     ebp, edx
0x14002a500  mov     rdi, rcx
0x14002a503  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a50a  lea     rax, WPP_GLOBAL_Control
0x14002a511  cmp     rcx, rax
0x14002a514  jz      short loc_14002A53F
0x14002a516  mov     eax, [rcx+2Ch]
0x14002a519  test    al, 20h
0x14002a51b  jz      short loc_14002A538
0x14002a51d  cmp     byte ptr [rcx+29h], 5
0x14002a521  jb      short loc_14002A538
0x14002a523  mov     rcx, [rcx+18h]
0x14002a527  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14002a52e  mov     edx, 13h
0x14002a533  call    WPP_SF_
0x14002a538  lea     rax, WPP_GLOBAL_Control
0x14002a53f  mov     r14, [rsp+68h+arg_20]
0x14002a547  mov     r8d, 30h ; '0'
0x14002a54d  mov     [r14], r8d
0x14002a550  cmp     ebp, r8d
0x14002a553  jb      loc_14002A7ED
0x14002a559  cmp     ebx, r8d
0x14002a55c  jb      loc_14002A7ED
0x14002a562  cmp     qword ptr [rdi+18h], 0
0x14002a567  jnz     short loc_14002A5BD
0x14002a569  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a570  cmp     rcx, rax
0x14002a573  jz      short loc_14002A596
0x14002a575  mov     eax, [rcx+2Ch]
0x14002a578  test    al, 20h
0x14002a57a  jz      short loc_14002A596
0x14002a57c  cmp     byte ptr [rcx+29h], 3
0x14002a580  jb      short loc_14002A596
0x14002a582  mov     rcx, [rcx+18h]
0x14002a586  lea     edx, [r8-1Bh]
0x14002a58a  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14002a591  call    WPP_SF_
0x14002a596  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x14002a59c  test    al, 10h
0x14002a59e  jz      short loc_14002A5A5
0x14002a5a0  and     eax, 1
0x14002a5a3  jmp     short loc_14002A5AA
0x14002a5a5  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x14002a5aa  neg     eax
0x14002a5ac  sbb     eax, eax
0x14002a5ae  and     eax, 0BFFFFDAFh
0x14002a5b3  add     eax, 259h
0x14002a5b8  jmp     loc_14002A828
0x14002a5bd  mov     rcx, cs:ConnTableLock; Lock
0x14002a5c4  lea     rdx, [rsp+68h+LockState]; LockState
0x14002a5c9  xor     r8d, r8d; Flags
0x14002a5cc  call    cs:__imp_NdisAcquireRWLockRead
0x14002a5d3  nop     dword ptr [rax+rax+00h]
0x14002a5d8  mov     rdx, cs:ConnectionTable
0x14002a5df  mov     eax, [rdi+10h]
0x14002a5e2  cmp     eax, [rdx+4]
0x14002a5e5  jnb     short loc_14002A607
0x14002a5e7  lfence
0x14002a5ea  mov     rdx, cs:ConnectionTable
0x14002a5f1  mov     ecx, eax
0x14002a5f3  mov     rax, [rdx+38h]
0x14002a5f7  mov     rbx, [rax+rcx*8]
0x14002a5fb  test    rbx, rbx
0x14002a5fe  jz      short loc_14002A607
0x14002a600  cmp     qword ptr [rbx+30h], 0
0x14002a605  jz      short loc_14002A637
0x14002a607  mov     rcx, [rdx+30h]
0x14002a60b  lea     rax, [rdx+28h]
0x14002a60f  cmp     rcx, rax
0x14002a612  jz      short loc_14002A662
0x14002a614  lea     rbx, [rcx-100h]
0x14002a61b  test    rbx, rbx
0x14002a61e  jz      short loc_14002A631
0x14002a620  mov     rax, [rbx+40h]
0x14002a624  cmp     [rdi+10h], rax
0x14002a628  jnz     short loc_14002A631
0x14002a62a  cmp     qword ptr [rbx+30h], 0
0x14002a62f  jz      short loc_14002A637
0x14002a631  mov     rcx, [rcx+8]
0x14002a635  jmp     short loc_14002A60B
0x14002a637  lea     rsi, [rbx+2E0h]
0x14002a63e  mov     rcx, rsi; SpinLock
0x14002a641  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14002a648  nop     dword ptr [rax+rax+00h]
0x14002a64d  cmp     dword ptr [rbx+14h], 2
0x14002a651  jz      short loc_14002A6D0
0x14002a653  mov     rcx, rsi; SpinLock
0x14002a656  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14002a65d  nop     dword ptr [rax+rax+00h]
0x14002a662  mov     rcx, cs:ConnTableLock; Lock
0x14002a669  lea     rdx, [rsp+68h+LockState]; LockState
0x14002a66e  call    cs:__imp_NdisReleaseRWLock
0x14002a675  nop     dword ptr [rax+rax+00h]
0x14002a67a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a681  lea     rax, WPP_GLOBAL_Control
0x14002a688  cmp     rcx, rax
0x14002a68b  jz      short loc_14002A6B3
0x14002a68d  mov     eax, [rcx+2Ch]
0x14002a690  test    al, 20h
0x14002a692  jz      short loc_14002A6B3
0x14002a694  cmp     byte ptr [rcx+29h], 3
0x14002a698  jb      short loc_14002A6B3
0x14002a69a  mov     r9, [rdi+10h]
0x14002a69e  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14002a6a5  mov     rcx, [rcx+18h]
0x14002a6a9  mov     edx, 16h
0x14002a6ae  call    WPP_SF_q
0x14002a6b3  mov     dword ptr [r14], 0
0x14002a6ba  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x14002a6c0  test    al, 10h
0x14002a6c2  jz      loc_14002A7DA
0x14002a6c8  and     eax, 1
0x14002a6cb  jmp     loc_14002A7DF
0x14002a6d0  mov     rcx, [rbx+50h]
0x14002a6d4  lea     rdx, [rdi+2Ch]; Src
0x14002a6d8  mov     rax, [rbx+28h]
0x14002a6dc  mov     [r15], rax
0x14002a6df  mov     rax, [rcx+20h]
0x14002a6e3  mov     [r15+8], rax
0x14002a6e7  mov     rax, [rdi+18h]
0x14002a6eb  mov     [rbx+30h], rax
0x14002a6ef  mov     rax, [rdi+20h]
0x14002a6f3  mov     [rcx+28h], rax
0x14002a6f7  lea     eax, [rbp-2Ch]
0x14002a6fa  inc     dword ptr [rbx+1Ch]
0x14002a6fd  or      dword ptr [rbx+24h], 2
0x14002a701  mov     ecx, [rdi+28h]
0x14002a704  cmp     eax, ecx
0x14002a706  cmovbe  ecx, eax
0x14002a709  mov     eax, 100h
0x14002a70e  cmp     ecx, eax
0x14002a710  cmova   ecx, eax
0x14002a713  mov     r8d, ecx; Size
0x14002a716  lea     rcx, [rbx+144h]; void *
0x14002a71d  call    memmove
0x14002a722  mov     rdi, [rbx+48h]
0x14002a726  mov     rcx, rsi; SpinLock
0x14002a729  mov     byte ptr [rbx+243h], 0
0x14002a730  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14002a737  nop     dword ptr [rax+rax+00h]
0x14002a73c  lea     rcx, SpinLock; SpinLock
0x14002a743  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14002a74a  nop     dword ptr [rax+rax+00h]
0x14002a74f  cmp     dword ptr [rbx+60h], 0
0x14002a753  jz      short loc_14002A784
0x14002a755  cmp     cs:byte_14001E3C8, 0
0x14002a75c  jnz     short loc_14002A784
0x14002a75e  lea     r8, Dpc; Dpc
0x14002a765  mov     cs:byte_14001E3C8, 1
0x14002a76c  mov     edx, 0Fh; DueTime
0x14002a771  lea     rcx, Timer; Timer
0x14002a778  call    cs:__imp_KeSetTimer
0x14002a77f  nop     dword ptr [rax+rax+00h]
0x14002a784  lea     rcx, SpinLock; SpinLock
0x14002a78b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14002a792  nop     dword ptr [rax+rax+00h]
0x14002a797  mov     rcx, cs:ConnTableLock; Lock
0x14002a79e  lea     rdx, [rsp+68h+LockState]; LockState
0x14002a7a3  call    cs:__imp_NdisReleaseRWLock
0x14002a7aa  nop     dword ptr [rax+rax+00h]
0x14002a7af  xor     eax, eax
0x14002a7b1  test    rdi, rdi
0x14002a7b4  jz      short loc_14002A828
0x14002a7b6  lea     rcx, [rdi+1E0h]; Object
0x14002a7bd  mov     [rsp+68h+Timeout], rax; Timeout
0x14002a7c2  mov     r9b, 1; Alertable
0x14002a7c5  xor     r8d, r8d; WaitMode
0x14002a7c8  xor     edx, edx; WaitReason
0x14002a7ca  call    cs:__imp_KeWaitForSingleObject
0x14002a7d1  nop     dword ptr [rax+rax+00h]
0x14002a7d6  xor     eax, eax
0x14002a7d8  jmp     short loc_14002A828
0x14002a7da  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x14002a7df  neg     eax
0x14002a7e1  sbb     eax, eax
0x14002a7e3  and     eax, 0BFFFFFCCh
0x14002a7e8  jmp     loc_14002A5B3
0x14002a7ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a7f4  cmp     rcx, rax
0x14002a7f7  jz      short loc_14002A823
0x14002a7f9  mov     eax, [rcx+2Ch]
0x14002a7fc  test    al, 20h
0x14002a7fe  jz      short loc_14002A823
0x14002a800  cmp     byte ptr [rcx+29h], 3
0x14002a804  jb      short loc_14002A823
0x14002a806  mov     rcx, [rcx+18h]
0x14002a80a  mov     edx, 14h
0x14002a80f  mov     dword ptr [rsp+68h+Timeout], r8d
0x14002a814  mov     r9d, ebx
0x14002a817  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14002a81e  call    WPP_SF_dd
0x14002a823  mov     eax, 0C0000004h
0x14002a828  add     rsp, 38h
0x14002a82c  pop     r15
0x14002a82e  pop     r14
0x14002a830  pop     rdi
0x14002a831  pop     rsi
0x14002a832  pop     rbp
0x14002a833  pop     rbx
0x14002a834  retn
```
