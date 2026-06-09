# Dot11StartScanV2(_ADAPT *,ulong,_DOT11_SCAN_REQUEST_V2 *,void (*)(_ADAPT *,int,_DOT11_SCAN_REQUEST_V2 *,void *,void *),void *,void *)

- ea: `0x14005419c`
- end: `0x1400544a7`
- name: `?Dot11StartScanV2@@YAHPEAU_ADAPT@@KPEAU_DOT11_SCAN_REQUEST_V2@@P6AX0H1PEAX2@Z22@Z`
- size: `779`
- prototype: `__int64 __usercall@<rax>(struct _ADAPT *@<rcx>, unsigned int@<edx>, struct _DOT11_SCAN_REQUEST_V2 *@<r8>, void (*)(struct _ADAPT *, int, struct _DOT11_SCAN_REQUEST_V2 *, void *, void *)@<r9>, void *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001e830`
- `0x14006e938`

## callees

- `0x14000d22c`
- `0x140016320`
- `0x140020dc0`
- `0x140054110`
- `0x14005419c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140054216`
- `ntoskrnl!KeGetCurrentIrql` at `0x140054216`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140054261`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140054261`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005431f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005446e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005431f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005446e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054333`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005447f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054333`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005447f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140054308`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400543d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140054308`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400543d8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400542e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400542e8`
- `NDIS!NdisGetSystemUpTimeEx` at `0x1400543a7`
- `NDIS!NdisGetSystemUpTimeEx` at `0x1400543a7`
- `NDIS!NdisWaitEvent` at `0x14005440a`
- `NDIS!NdisWaitEvent` at `0x14005440a`
- `NDIS!NdisInitializeEvent` at `0x140054237`
- `NDIS!NdisInitializeEvent` at `0x140054237`

## pseudocode

```c
__int64 __fastcall Dot11StartScanV2(
        struct _ADAPT *a1,
        int a2,
        _LIST_ENTRY *a3,
        void (*a4)(struct _ADAPT *, int, struct _DOT11_SCAN_REQUEST_V2 *, void *, void *),
        struct _NDIS_EVENT *a5,
        _LIST_ENTRY *a6)
{
  _LIST_ENTRY *v6; // rdi
  struct _NDIS_EVENT *p_Event; // r14
  unsigned int v12; // ebx
  char *v13; // rax
  ULONG *v14; // rbx
  _LIST_ENTRY *v15; // rax
  KIRQL v16; // al
  bool v17; // zf
  _LIST_ENTRY *Blink; // rdx
  struct _NDIS_EVENT Event; // [rsp+20h] [rbp-48h] BYREF
  union _LARGE_INTEGER pSystemUpTime; // [rsp+70h] [rbp+8h] BYREF

  v6 = 0;
  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids);
  }
  if ( !a1->ScanModule.bInited )
  {
    v12 = -1073741823;
LABEL_32:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids, v12);
    }
    if ( v6 )
    {
      if ( v6[-1].Flink )
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v6[-1].Flink, &v6[-1]);
      else
        ExFreePoolWithTag(&v6[-1], (ULONG)v6[-1].Blink);
    }
    return v12;
  }
  if ( a4 )
  {
    p_Event = a5;
  }
  else
  {
    if ( KeGetCurrentIrql() )
    {
      v12 = -1073741808;
      goto LABEL_32;
    }
    a4 = (void (*)(struct _ADAPT *, int, struct _DOT11_SCAN_REQUEST_V2 *, void *, void *))&Dot11InternalScanCompletion;
    p_Event = &Event;
    NdisInitializeEvent(&Event);
  }
  v13 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
  v14 = (ULONG *)v13;
  if ( !v13 )
  {
    v6 = 0;
    v12 = -1073741670;
    goto LABEL_32;
  }
  *(_QWORD *)v13 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  *((_DWORD *)v13 + 2) = 1751741303;
  v6 = (_LIST_ENTRY *)(v13 + 16);
  *((_OWORD *)v13 + 1) = 0;
  *((_OWORD *)v13 + 2) = 0;
  *((_OWORD *)v13 + 3) = 0;
  *((_QWORD *)v13 + 8) = 0;
  if ( (_DWORD)g_WlanScanMode == 500 )
    HIDWORD(a3->Blink) = 2;
  *((_QWORD *)v13 + 3) = v13 + 16;
  v6->Flink = v6;
  *((_QWORD *)v13 + 5) = a4;
  *((_DWORD *)v13 + 8) = a2;
  *((_DWORD *)v13 + 9) = 2;
  v15 = a6;
  v6[2].Flink = a3;
  v6[2].Blink = (_LIST_ENTRY *)p_Event;
  v6[3].Flink = v15;
  v16 = KeAcquireSpinLockRaiseToDpc(&a1->ScanModule.Lock.SpinLock);
  v17 = a1->ScanModule.bDeIniting == 0;
  a1->ScanModule.Lock.OldIrql = v16;
  if ( !v17 )
  {
    KeReleaseSpinLock(&a1->ScanModule.Lock.SpinLock, v16);
    if ( *(_QWORD *)v14 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v14, v14);
    else
      ExFreePoolWithTag(v14, v14[2]);
    v6 = 0;
    v12 = -1073676276;
    goto LABEL_32;
  }
  if ( a1->ScanModule.pOutstandingInNic )
  {
    pSystemUpTime.QuadPart = 0;
    _InterlockedIncrement((volatile signed __int32 *)&a1->ScanModule.uNumQueuedScanRequests);
    Blink = a1->ScanModule.QueuedScanRequestList.Blink;
    if ( Blink->Flink != &a1->ScanModule.QueuedScanRequestList )
      __fastfail(3u);
    v6->Flink = &a1->ScanModule.QueuedScanRequestList;
    v6->Blink = Blink;
    v12 = 259;
    Blink->Flink = v6;
    a1->ScanModule.QueuedScanRequestList.Blink = v6;
    NdisGetSystemUpTimeEx(&pSystemUpTime);
    if ( pSystemUpTime.QuadPart - a1->ScanModule.liScanningTimestamp.QuadPart >= 60000 )
      Dot11ScanReset(a1);
  }
  else
  {
    v12 = Dot11IssueScanToNic(a1, (struct DOT11_WIFI_SCAN_REQUEST *)v6);
  }
  KeReleaseSpinLock(&a1->ScanModule.Lock.SpinLock, a1->ScanModule.Lock.OldIrql);
  if ( v12 != 259 )
  {
    if ( !v12 )
      return v12;
    goto LABEL_32;
  }
  if ( &Dot11InternalScanCompletion == (_UNKNOWN *)a4 )
  {
    NdisWaitEvent(&Event, 0);
    return 0;
  }
  return v12;
}

```

## disassembly

```asm
0x14005419c  mov     [rsp+arg_8], rbx
0x1400541a1  mov     [rsp+arg_10], rbp
0x1400541a6  push    rsi
0x1400541a7  push    rdi
0x1400541a8  push    r12
0x1400541aa  push    r14
0x1400541ac  push    r15
0x1400541ae  sub     rsp, 40h
0x1400541b2  xor     edi, edi
0x1400541b4  xorps   xmm0, xmm0
0x1400541b7  xor     eax, eax
0x1400541b9  mov     dword ptr [rsp+68h+Event.Event.Header.___u0], edi
0x1400541bd  mov     dword ptr [rsp+68h+Event.Event.Header.WaitListHead.Blink+4], eax
0x1400541c1  mov     rbp, r9
0x1400541c4  mov     r15, r8
0x1400541c7  mov     r12d, edx
0x1400541ca  mov     rsi, rcx
0x1400541cd  movups  xmmword ptr [rsp+68h+Event.Event.Header.SignalState], xmm0
0x1400541d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400541d9  lea     rax, WPP_GLOBAL_Control
0x1400541e0  cmp     rcx, rax
0x1400541e3  jz      short loc_140054205
0x1400541e5  cmp     byte ptr [rcx+29h], 3
0x1400541e9  jb      short loc_140054205
0x1400541eb  mov     eax, [rcx+2Ch]
0x1400541ee  test    al, 10h
0x1400541f0  jz      short loc_140054205
0x1400541f2  mov     rcx, [rcx+18h]
0x1400541f6  lea     edx, [rdi+10h]
0x1400541f9  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x140054200  call    WPP_SF_
0x140054205  cmp     [rsi+88h], edi
0x14005420b  jz      loc_14005441A
0x140054211  test    rbp, rbp
0x140054214  jnz     short loc_14005424F
0x140054216  call    cs:__imp_KeGetCurrentIrql
0x14005421d  nop     dword ptr [rax+rax+00h]
0x140054222  test    al, al
0x140054224  jnz     short loc_140054245
0x140054226  lea     rcx, [rsp+68h+Event]; Event
0x14005422b  lea     rbp, Dot11InternalScanCompletion
0x140054232  lea     r14, [rsp+68h+Event]
0x140054237  call    cs:__imp_NdisInitializeEvent
0x14005423e  nop     dword ptr [rax+rax+00h]
0x140054243  jmp     short loc_140054257
0x140054245  mov     ebx, 0C0000010h
0x14005424a  jmp     loc_14005441F
0x14005424f  mov     r14, [rsp+68h+arg_20]
0x140054257  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14005425e  mov     rcx, rdi; Lookaside
0x140054261  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140054268  nop     dword ptr [rax+rax+00h]
0x14005426d  mov     rbx, rax
0x140054270  test    rax, rax
0x140054273  jnz     short loc_140054281
0x140054275  xor     edi, edi
0x140054277  mov     ebx, 0C000009Ah
0x14005427c  jmp     loc_14005441F
0x140054281  mov     [rax], rdi
0x140054284  xorps   xmm0, xmm0
0x140054287  mov     dword ptr [rax+8], 68697377h
0x14005428e  lea     rdi, [rax+10h]
0x140054292  movups  xmmword ptr [rdi], xmm0
0x140054295  xor     eax, eax
0x140054297  movups  xmmword ptr [rdi+10h], xmm0
0x14005429b  movups  xmmword ptr [rdi+20h], xmm0
0x14005429f  mov     [rdi+30h], rax
0x1400542a3  mov     eax, 2
0x1400542a8  cmp     cs:?g_WlanScanMode@@3KA, 1F4h; ulong g_WlanScanMode
0x1400542b2  jnz     short loc_1400542B8
0x1400542b4  mov     [r15+0Ch], eax
0x1400542b8  mov     [rdi+8], rdi
0x1400542bc  mov     [rdi], rdi
0x1400542bf  mov     [rdi+18h], rbp
0x1400542c3  mov     [rdi+10h], r12d
0x1400542c7  mov     [rdi+14h], eax
0x1400542ca  mov     rax, [rsp+68h+arg_28]
0x1400542d2  mov     [rdi+20h], r15
0x1400542d6  mov     [rdi+28h], r14
0x1400542da  lea     r14, [rsi+90h]
0x1400542e1  mov     rcx, r14; SpinLock
0x1400542e4  mov     [rdi+30h], rax
0x1400542e8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400542ef  nop     dword ptr [rax+rax+00h]
0x1400542f4  cmp     dword ptr [rsi+8Ch], 0
0x1400542fb  mov     [rsi+98h], al
0x140054301  jz      short loc_14005434B
0x140054303  mov     dl, al; NewIrql
0x140054305  mov     rcx, r14; SpinLock
0x140054308  call    cs:__imp_KeReleaseSpinLock
0x14005430f  nop     dword ptr [rax+rax+00h]
0x140054314  mov     rcx, [rbx]; Lookaside
0x140054317  test    rcx, rcx
0x14005431a  jz      short loc_14005432D
0x14005431c  mov     rdx, rbx; Entry
0x14005431f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054326  nop     dword ptr [rax+rax+00h]
0x14005432b  jmp     short loc_14005433F
0x14005432d  mov     edx, [rbx+8]; Tag
0x140054330  mov     rcx, rbx; P
0x140054333  call    cs:__imp_ExFreePoolWithTag
0x14005433a  nop     dword ptr [rax+rax+00h]
0x14005433f  xor     edi, edi
0x140054341  mov     ebx, 0C001000Ch
0x140054346  jmp     loc_14005441F
0x14005434b  cmp     qword ptr [rsi+0A8h], 0
0x140054353  mov     r15d, 103h
0x140054359  jnz     short loc_14005436A
0x14005435b  mov     rdx, rdi; struct DOT11_WIFI_SCAN_REQUEST *
0x14005435e  mov     rcx, rsi; struct _ADAPT *
0x140054361  call    ?Dot11IssueScanToNic@@YAHPEAU_ADAPT@@PEAUDOT11_WIFI_SCAN_REQUEST@@@Z; Dot11IssueScanToNic(_ADAPT *,DOT11_WIFI_SCAN_REQUEST *)
0x140054366  mov     ebx, eax
0x140054368  jmp     short loc_1400543CF
0x14005436a  mov     qword ptr [rsp+68h+pSystemUpTime], 0
0x140054373  lock inc dword ptr [rsi+0B0h]
0x14005437a  lea     rax, [rsi+0B8h]
0x140054381  mov     rdx, [rax+8]
0x140054385  cmp     [rdx], rax
0x140054388  jz      short loc_140054391
0x14005438a  mov     ecx, 3
0x14005438f  int     29h; Win8: RtlFailFast(ecx)
0x140054391  mov     [rdi], rax
0x140054394  lea     rcx, [rsp+68h+pSystemUpTime]; pSystemUpTime
0x140054399  mov     [rdi+8], rdx
0x14005439d  mov     ebx, r15d
0x1400543a0  mov     [rdx], rdi
0x1400543a3  mov     [rax+8], rdi
0x1400543a7  call    cs:__imp_NdisGetSystemUpTimeEx
0x1400543ae  nop     dword ptr [rax+rax+00h]
0x1400543b3  mov     rax, qword ptr [rsp+68h+pSystemUpTime]
0x1400543b8  sub     rax, [rsi+0C8h]
0x1400543bf  cmp     rax, 0EA60h
0x1400543c5  jl      short loc_1400543CF
0x1400543c7  mov     rcx, rsi; Context
0x1400543ca  call    ?Dot11ScanReset@@YAXPEAU_ADAPT@@@Z; Dot11ScanReset(_ADAPT *)
0x1400543cf  mov     dl, [rsi+98h]; NewIrql
0x1400543d5  mov     rcx, r14; SpinLock
0x1400543d8  call    cs:__imp_KeReleaseSpinLock
0x1400543df  nop     dword ptr [rax+rax+00h]
0x1400543e4  cmp     ebx, r15d
0x1400543e7  jz      short loc_1400543F3
0x1400543e9  test    ebx, ebx
0x1400543eb  jz      loc_14005448B
0x1400543f1  jmp     short loc_14005441F
0x1400543f3  lea     rax, Dot11InternalScanCompletion
0x1400543fa  cmp     rax, rbp
0x1400543fd  jnz     loc_14005448B
0x140054403  xor     edx, edx; MsToWait
0x140054405  lea     rcx, [rsp+68h+Event]; Event
0x14005440a  call    cs:__imp_NdisWaitEvent
0x140054411  nop     dword ptr [rax+rax+00h]
0x140054416  xor     ebx, ebx
0x140054418  jmp     short loc_14005448B
0x14005441a  mov     ebx, 0C0000001h
0x14005441f  mov     rcx, cs:WPP_GLOBAL_Control
0x140054426  lea     rax, WPP_GLOBAL_Control
0x14005442d  cmp     rcx, rax
0x140054430  jz      short loc_140054457
0x140054432  cmp     byte ptr [rcx+29h], 1
0x140054436  jb      short loc_140054457
0x140054438  mov     eax, [rcx+2Ch]
0x14005443b  test    al, 10h
0x14005443d  jz      short loc_140054457
0x14005443f  mov     rcx, [rcx+18h]
0x140054443  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x14005444a  mov     edx, 11h
0x14005444f  mov     r9d, ebx
0x140054452  call    WPP_SF_d
0x140054457  test    rdi, rdi
0x14005445a  jz      short loc_14005448B
0x14005445c  lea     rcx, [rdi-10h]; P
0x140054460  mov     rax, [rcx]
0x140054463  test    rax, rax
0x140054466  jz      short loc_14005447C
0x140054468  mov     rdx, rcx; Entry
0x14005446b  mov     rcx, rax; Lookaside
0x14005446e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054475  nop     dword ptr [rax+rax+00h]
0x14005447a  jmp     short loc_14005448B
0x14005447c  mov     edx, [rcx+8]; Tag
0x14005447f  call    cs:__imp_ExFreePoolWithTag
0x140054486  nop     dword ptr [rax+rax+00h]
0x14005448b  lea     r11, [rsp+68h+var_28]
0x140054490  mov     eax, ebx
0x140054492  mov     rbx, [r11+38h]
0x140054496  mov     rbp, [r11+40h]
0x14005449a  mov     rsp, r11
0x14005449d  pop     r15
0x14005449f  pop     r14
0x1400544a1  pop     r12
0x1400544a3  pop     rdi
0x1400544a4  pop     rsi
0x1400544a5  retn
```
