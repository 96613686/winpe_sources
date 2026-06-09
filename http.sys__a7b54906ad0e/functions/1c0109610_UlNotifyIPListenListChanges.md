# UlNotifyIPListenListChanges

- ea: `0x1c0109610`
- end: `0x1c01097ee`
- name: `UlNotifyIPListenListChanges`
- size: `478`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1c012bf50`
- `0x1c012c698`

## callees

- `0x1c0001ae0`
- `0x1c001a8ac`
- `0x1c001b900`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c0109610`
- `0x1c010c96c`
- `0x1c011e880`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c0109676`
- `ntoskrnl!KeInitializeEvent` at `0x1c0109676`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c010970c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c010970c`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c010977e`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c010977e`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c01096a8`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c01096a8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010978a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010978a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0109695`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0109695`

## pseudocode

```c
__int64 __fastcall UlNotifyIPListenListChanges(__int64 a1, __int64 a2)
{
  __int64 v4; // r9
  __int64 v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // rdi
  int v8; // eax
  __int64 v9; // rcx
  _BYTE BugCheckParameter2[96]; // [rsp+38h] [rbp-9h] BYREF

  memset(BugCheckParameter2, 0, sizeof(BugCheckParameter2));
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_qq(189, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, a1, a2);
  *(_QWORD *)&BugCheckParameter2[56] = 0;
  *(_DWORD *)&BugCheckParameter2[48] = 259;
  KeInitializeEvent((PRKEVENT)&BugCheckParameter2[64], NotificationEvent, 0);
  *(_QWORD *)BugCheckParameter2 = 0;
  *(_QWORD *)&BugCheckParameter2[16] = 0;
  *(_QWORD *)&BugCheckParameter2[32] = 0;
  *(_QWORD *)&BugCheckParameter2[88] = a2;
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 1360));
  if ( *(_QWORD *)BugCheckParameter2 || *(_QWORD *)&BugCheckParameter2[16] || *(_QWORD *)&BugCheckParameter2[32] )
    UlBugCheckEx(1u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)"minio\\http\\sys\\cgroup.c", 0x2369u);
  LOBYTE(v4) = 1;
  UlThreadPoolEnqueueWorkItem(2, BugCheckParameter2, UxTlUpdateListenAddressList, v4, -1, -1);
  KeWaitForSingleObject(&BugCheckParameter2[64], UserRequest, 0, 0, 0);
  UlNotifyForAllChannels(a1, UlpNotifyIPListenListChangesOfServerSession);
  v5 = *(_QWORD *)(a1 + 1312);
  v6 = 0;
  if ( *(_DWORD *)(v5 + 8) )
  {
    while ( 1 )
    {
      v7 = *(_QWORD *)(v5 + 8 * v6 + 32);
      v8 = *(_DWORD *)(v7 + 60);
      if ( v8 == 1 )
        break;
      if ( v8 == 2 )
      {
        v9 = 2147498668LL;
        goto LABEL_11;
      }
LABEL_12:
      *(_DWORD *)(v7 + 60) = 0;
      v6 = (unsigned int)(v6 + 1);
      v5 = *(_QWORD *)(a1 + 1312);
      if ( (unsigned int)v6 >= *(_DWORD *)(v5 + 8) )
        goto LABEL_13;
    }
    v9 = 2147498667LL;
LABEL_11:
    UlEventLogOneStringEntry(v9, v7 + 144, 0, 0);
    goto LABEL_12;
  }
LABEL_13:
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 1360));
  KeLeaveCriticalRegion();
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_D(190, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
  return *(unsigned int *)&BugCheckParameter2[48];
}

```

## disassembly

```asm
0x1c0109610  mov     rax, rsp
0x1c0109613  mov     [rax+8], rbx
0x1c0109617  mov     [rax+10h], rsi
0x1c010961b  mov     [rax+18h], rdi
0x1c010961f  push    rbp
0x1c0109620  lea     rbp, [rax-5Fh]
0x1c0109624  sub     rsp, 90h
0x1c010962b  mov     rdi, rdx
0x1c010962e  mov     rbx, rcx
0x1c0109631  xor     edx, edx; Val
0x1c0109633  lea     rcx, [rbp+57h+BugCheckParameter2]; void *
0x1c0109637  lea     r8d, [rdx+60h]; Size
0x1c010963b  call    memset
0x1c0109640  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0109646  test    al, 8
0x1c0109648  jz      short loc_1C0109661
0x1c010964a  mov     ecx, 0BDh
0x1c010964f  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c0109656  mov     r9, rdi
0x1c0109659  mov     r8, rbx
0x1c010965c  call    WPP_SF_qq
0x1c0109661  and     [rbp+57h+var_28], 0
0x1c0109666  lea     rcx, [rbp+57h+Event]; Event
0x1c010966a  xor     r8d, r8d; State
0x1c010966d  mov     [rbp+57h+var_30], 103h
0x1c0109674  xor     edx, edx; Type
0x1c0109676  call    cs:__imp_KeInitializeEvent
0x1c010967d  nop     dword ptr [rax+rax+00h]
0x1c0109682  and     [rbp+57h+BugCheckParameter2], 0
0x1c0109687  and     [rbp+57h+var_50], 0
0x1c010968c  and     [rbp+57h+var_40], 0
0x1c0109691  mov     [rbp+57h+var_8], rdi
0x1c0109695  call    cs:__imp_KeEnterCriticalRegion
0x1c010969c  nop     dword ptr [rax+rax+00h]
0x1c01096a1  mov     rcx, [rbx+550h]
0x1c01096a8  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c01096af  nop     dword ptr [rax+rax+00h]
0x1c01096b4  cmp     [rbp+57h+BugCheckParameter2], 0
0x1c01096b9  jnz     loc_1C01097D2
0x1c01096bf  cmp     [rbp+57h+var_50], 0
0x1c01096c4  jnz     loc_1C01097D2
0x1c01096ca  cmp     [rbp+57h+var_40], 0
0x1c01096cf  jnz     loc_1C01097D2
0x1c01096d5  or      [rsp+90h+var_68], 0FFFFFFFFh
0x1c01096da  lea     r8, UxTlUpdateListenAddressList
0x1c01096e1  or      qword ptr [rsp+90h+var_70], 0FFFFFFFFFFFFFFFFh
0x1c01096e7  lea     rdx, [rbp+57h+BugCheckParameter2]
0x1c01096eb  mov     r9b, 1
0x1c01096ee  mov     ecx, 2
0x1c01096f3  call    UlThreadPoolEnqueueWorkItem
0x1c01096f8  and     qword ptr [rsp+90h+var_70], 0
0x1c01096fe  lea     rcx, [rbp+57h+Event]; Object
0x1c0109702  xor     r9d, r9d; Alertable
0x1c0109705  xor     r8d, r8d; WaitMode
0x1c0109708  lea     edx, [r9+6]; WaitReason
0x1c010970c  call    cs:__imp_KeWaitForSingleObject
0x1c0109713  nop     dword ptr [rax+rax+00h]
0x1c0109718  lea     rdx, UlpNotifyIPListenListChangesOfServerSession
0x1c010971f  mov     rcx, rbx
0x1c0109722  call    UlNotifyForAllChannels
0x1c0109727  mov     rcx, [rbx+520h]
0x1c010972e  xor     esi, esi
0x1c0109730  cmp     [rcx+8], esi
0x1c0109733  jbe     short loc_1C0109777
0x1c0109735  mov     rdi, [rcx+rsi*8+20h]
0x1c010973a  mov     eax, [rdi+3Ch]
0x1c010973d  cmp     eax, 1
0x1c0109740  jnz     short loc_1C0109749
0x1c0109742  mov     ecx, 80003AABh
0x1c0109747  jmp     short loc_1C0109753
0x1c0109749  cmp     eax, 2
0x1c010974c  jnz     short loc_1C0109765
0x1c010974e  mov     ecx, 80003AACh
0x1c0109753  xor     r9d, r9d
0x1c0109756  lea     rdx, [rdi+90h]
0x1c010975d  xor     r8d, r8d
0x1c0109760  call    UlEventLogOneStringEntry
0x1c0109765  and     dword ptr [rdi+3Ch], 0
0x1c0109769  inc     esi
0x1c010976b  mov     rcx, [rbx+520h]
0x1c0109772  cmp     esi, [rcx+8]
0x1c0109775  jb      short loc_1C0109735
0x1c0109777  mov     rcx, [rbx+550h]
0x1c010977e  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c0109785  nop     dword ptr [rax+rax+00h]
0x1c010978a  call    cs:__imp_KeLeaveCriticalRegion
0x1c0109791  nop     dword ptr [rax+rax+00h]
0x1c0109796  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c010979c  test    al, 8
0x1c010979e  jz      short loc_1C01097B5
0x1c01097a0  mov     r8d, [rbp+57h+var_30]
0x1c01097a4  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c01097ab  mov     ecx, 0BEh
0x1c01097b0  call    WPP_SF_D
0x1c01097b5  mov     eax, [rbp+57h+var_30]
0x1c01097b8  lea     r11, [rsp+90h+var_s0]
0x1c01097c0  mov     rbx, [r11+10h]
0x1c01097c4  mov     rsi, [r11+18h]
0x1c01097c8  mov     rdi, [r11+20h]
0x1c01097cc  mov     rsp, r11
0x1c01097cf  pop     rbp
0x1c01097d0  retn
0x1c01097d2  mov     r9d, 2369h; BugCheckParameter4
0x1c01097d8  lea     r8, aMinioHttpSysCg; "minio\\http\\sys\\cgroup.c"
0x1c01097df  lea     rdx, [rbp+57h+BugCheckParameter2]; BugCheckParameter2
0x1c01097e3  mov     ecx, 1; BugCheckParameter1
0x1c01097e8  call    UlBugCheckEx
```
