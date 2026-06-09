# Dot11StartScanV2(_ADAPT *,ulong,_DOT11_SCAN_REQUEST_V2 *,void (*)(_ADAPT *,int,_DOT11_SCAN_REQUEST_V2 *,void *,void *),void *,void *)

- ea: `0x1400559bc`
- end: `0x140055cc7`
- name: `?Dot11StartScanV2@@YAHPEAU_ADAPT@@KPEAU_DOT11_SCAN_REQUEST_V2@@P6AX0H1PEAX2@Z22@Z`
- size: `779`
- prototype: `__int64 __usercall@<rax>(struct _ADAPT *@<rcx>, unsigned int@<edx>, struct _DOT11_SCAN_REQUEST_V2 *@<r8>, void (*)(struct _ADAPT *, int, struct _DOT11_SCAN_REQUEST_V2 *, void *, void *)@<r9>, void *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001e830`
- `0x140070168`

## callees

- `0x14000d21c`
- `0x140016310`
- `0x140020dc0`
- `0x140055930`
- `0x1400559bc`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140055a36`
- `ntoskrnl!KeGetCurrentIrql` at `0x140055a36`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140055a81`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140055a81`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140055b3f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140055c8e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140055b3f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140055c8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055b53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055c9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055b53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055c9f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140055b28`
- `ntoskrnl!KeReleaseSpinLock` at `0x140055bf8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140055b28`
- `ntoskrnl!KeReleaseSpinLock` at `0x140055bf8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140055b08`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140055b08`
- `NDIS!NdisGetSystemUpTimeEx` at `0x140055bc7`
- `NDIS!NdisGetSystemUpTimeEx` at `0x140055bc7`
- `NDIS!NdisWaitEvent` at `0x140055c2a`
- `NDIS!NdisWaitEvent` at `0x140055c2a`
- `NDIS!NdisInitializeEvent` at `0x140055a57`
- `NDIS!NdisInitializeEvent` at `0x140055a57`

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
0x1400559bc  mov     [rsp+arg_8], rbx
0x1400559c1  mov     [rsp+arg_10], rbp
0x1400559c6  push    rsi
0x1400559c7  push    rdi
0x1400559c8  push    r12
0x1400559ca  push    r14
0x1400559cc  push    r15
0x1400559ce  sub     rsp, 40h
0x1400559d2  xor     edi, edi
0x1400559d4  xorps   xmm0, xmm0
0x1400559d7  xor     eax, eax
0x1400559d9  mov     dword ptr [rsp+68h+Event.Event.Header.___u0], edi
0x1400559dd  mov     dword ptr [rsp+68h+Event.Event.Header.WaitListHead.Blink+4], eax
0x1400559e1  mov     rbp, r9
0x1400559e4  mov     r15, r8
0x1400559e7  mov     r12d, edx
0x1400559ea  mov     rsi, rcx
0x1400559ed  movups  xmmword ptr [rsp+68h+Event.Event.Header.SignalState], xmm0
0x1400559f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400559f9  lea     rax, WPP_GLOBAL_Control
0x140055a00  cmp     rcx, rax
0x140055a03  jz      short loc_140055A25
0x140055a05  cmp     byte ptr [rcx+29h], 3
0x140055a09  jb      short loc_140055A25
0x140055a0b  mov     eax, [rcx+2Ch]
0x140055a0e  test    al, 10h
0x140055a10  jz      short loc_140055A25
0x140055a12  mov     rcx, [rcx+18h]
0x140055a16  lea     edx, [rdi+10h]
0x140055a19  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x140055a20  call    WPP_SF_
0x140055a25  cmp     [rsi+88h], edi
0x140055a2b  jz      loc_140055C3A
0x140055a31  test    rbp, rbp
0x140055a34  jnz     short loc_140055A6F
0x140055a36  call    cs:__imp_KeGetCurrentIrql
0x140055a3d  nop     dword ptr [rax+rax+00h]
0x140055a42  test    al, al
0x140055a44  jnz     short loc_140055A65
0x140055a46  lea     rcx, [rsp+68h+Event]; Event
0x140055a4b  lea     rbp, Dot11InternalScanCompletion
0x140055a52  lea     r14, [rsp+68h+Event]
0x140055a57  call    cs:__imp_NdisInitializeEvent
0x140055a5e  nop     dword ptr [rax+rax+00h]
0x140055a63  jmp     short loc_140055A77
0x140055a65  mov     ebx, 0C0000010h
0x140055a6a  jmp     loc_140055C3F
0x140055a6f  mov     r14, [rsp+68h+arg_20]
0x140055a77  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140055a7e  mov     rcx, rdi; Lookaside
0x140055a81  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140055a88  nop     dword ptr [rax+rax+00h]
0x140055a8d  mov     rbx, rax
0x140055a90  test    rax, rax
0x140055a93  jnz     short loc_140055AA1
0x140055a95  xor     edi, edi
0x140055a97  mov     ebx, 0C000009Ah
0x140055a9c  jmp     loc_140055C3F
0x140055aa1  mov     [rax], rdi
0x140055aa4  xorps   xmm0, xmm0
0x140055aa7  mov     dword ptr [rax+8], 68697377h
0x140055aae  lea     rdi, [rax+10h]
0x140055ab2  movups  xmmword ptr [rdi], xmm0
0x140055ab5  xor     eax, eax
0x140055ab7  movups  xmmword ptr [rdi+10h], xmm0
0x140055abb  movups  xmmword ptr [rdi+20h], xmm0
0x140055abf  mov     [rdi+30h], rax
0x140055ac3  mov     eax, 2
0x140055ac8  cmp     cs:?g_WlanScanMode@@3KA, 1F4h; ulong g_WlanScanMode
0x140055ad2  jnz     short loc_140055AD8
0x140055ad4  mov     [r15+0Ch], eax
0x140055ad8  mov     [rdi+8], rdi
0x140055adc  mov     [rdi], rdi
0x140055adf  mov     [rdi+18h], rbp
0x140055ae3  mov     [rdi+10h], r12d
0x140055ae7  mov     [rdi+14h], eax
0x140055aea  mov     rax, [rsp+68h+arg_28]
0x140055af2  mov     [rdi+20h], r15
0x140055af6  mov     [rdi+28h], r14
0x140055afa  lea     r14, [rsi+90h]
0x140055b01  mov     rcx, r14; SpinLock
0x140055b04  mov     [rdi+30h], rax
0x140055b08  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140055b0f  nop     dword ptr [rax+rax+00h]
0x140055b14  cmp     dword ptr [rsi+8Ch], 0
0x140055b1b  mov     [rsi+98h], al
0x140055b21  jz      short loc_140055B6B
0x140055b23  mov     dl, al; NewIrql
0x140055b25  mov     rcx, r14; SpinLock
0x140055b28  call    cs:__imp_KeReleaseSpinLock
0x140055b2f  nop     dword ptr [rax+rax+00h]
0x140055b34  mov     rcx, [rbx]; Lookaside
0x140055b37  test    rcx, rcx
0x140055b3a  jz      short loc_140055B4D
0x140055b3c  mov     rdx, rbx; Entry
0x140055b3f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140055b46  nop     dword ptr [rax+rax+00h]
0x140055b4b  jmp     short loc_140055B5F
0x140055b4d  mov     edx, [rbx+8]; Tag
0x140055b50  mov     rcx, rbx; P
0x140055b53  call    cs:__imp_ExFreePoolWithTag
0x140055b5a  nop     dword ptr [rax+rax+00h]
0x140055b5f  xor     edi, edi
0x140055b61  mov     ebx, 0C001000Ch
0x140055b66  jmp     loc_140055C3F
0x140055b6b  cmp     qword ptr [rsi+0A8h], 0
0x140055b73  mov     r15d, 103h
0x140055b79  jnz     short loc_140055B8A
0x140055b7b  mov     rdx, rdi; struct DOT11_WIFI_SCAN_REQUEST *
0x140055b7e  mov     rcx, rsi; struct _ADAPT *
0x140055b81  call    ?Dot11IssueScanToNic@@YAHPEAU_ADAPT@@PEAUDOT11_WIFI_SCAN_REQUEST@@@Z; Dot11IssueScanToNic(_ADAPT *,DOT11_WIFI_SCAN_REQUEST *)
0x140055b86  mov     ebx, eax
0x140055b88  jmp     short loc_140055BEF
0x140055b8a  mov     qword ptr [rsp+68h+pSystemUpTime], 0
0x140055b93  lock inc dword ptr [rsi+0B0h]
0x140055b9a  lea     rax, [rsi+0B8h]
0x140055ba1  mov     rdx, [rax+8]
0x140055ba5  cmp     [rdx], rax
0x140055ba8  jz      short loc_140055BB1
0x140055baa  mov     ecx, 3
0x140055baf  int     29h; Win8: RtlFailFast(ecx)
0x140055bb1  mov     [rdi], rax
0x140055bb4  lea     rcx, [rsp+68h+pSystemUpTime]; pSystemUpTime
0x140055bb9  mov     [rdi+8], rdx
0x140055bbd  mov     ebx, r15d
0x140055bc0  mov     [rdx], rdi
0x140055bc3  mov     [rax+8], rdi
0x140055bc7  call    cs:__imp_NdisGetSystemUpTimeEx
0x140055bce  nop     dword ptr [rax+rax+00h]
0x140055bd3  mov     rax, qword ptr [rsp+68h+pSystemUpTime]
0x140055bd8  sub     rax, [rsi+0C8h]
0x140055bdf  cmp     rax, 0EA60h
0x140055be5  jl      short loc_140055BEF
0x140055be7  mov     rcx, rsi; Context
0x140055bea  call    ?Dot11ScanReset@@YAXPEAU_ADAPT@@@Z; Dot11ScanReset(_ADAPT *)
0x140055bef  mov     dl, [rsi+98h]; NewIrql
0x140055bf5  mov     rcx, r14; SpinLock
0x140055bf8  call    cs:__imp_KeReleaseSpinLock
0x140055bff  nop     dword ptr [rax+rax+00h]
0x140055c04  cmp     ebx, r15d
0x140055c07  jz      short loc_140055C13
0x140055c09  test    ebx, ebx
0x140055c0b  jz      loc_140055CAB
0x140055c11  jmp     short loc_140055C3F
0x140055c13  lea     rax, Dot11InternalScanCompletion
0x140055c1a  cmp     rax, rbp
0x140055c1d  jnz     loc_140055CAB
0x140055c23  xor     edx, edx; MsToWait
0x140055c25  lea     rcx, [rsp+68h+Event]; Event
0x140055c2a  call    cs:__imp_NdisWaitEvent
0x140055c31  nop     dword ptr [rax+rax+00h]
0x140055c36  xor     ebx, ebx
0x140055c38  jmp     short loc_140055CAB
0x140055c3a  mov     ebx, 0C0000001h
0x140055c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140055c46  lea     rax, WPP_GLOBAL_Control
0x140055c4d  cmp     rcx, rax
0x140055c50  jz      short loc_140055C77
0x140055c52  cmp     byte ptr [rcx+29h], 1
0x140055c56  jb      short loc_140055C77
0x140055c58  mov     eax, [rcx+2Ch]
0x140055c5b  test    al, 10h
0x140055c5d  jz      short loc_140055C77
0x140055c5f  mov     rcx, [rcx+18h]
0x140055c63  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x140055c6a  mov     edx, 11h
0x140055c6f  mov     r9d, ebx
0x140055c72  call    WPP_SF_d
0x140055c77  test    rdi, rdi
0x140055c7a  jz      short loc_140055CAB
0x140055c7c  lea     rcx, [rdi-10h]; P
0x140055c80  mov     rax, [rcx]
0x140055c83  test    rax, rax
0x140055c86  jz      short loc_140055C9C
0x140055c88  mov     rdx, rcx; Entry
0x140055c8b  mov     rcx, rax; Lookaside
0x140055c8e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140055c95  nop     dword ptr [rax+rax+00h]
0x140055c9a  jmp     short loc_140055CAB
0x140055c9c  mov     edx, [rcx+8]; Tag
0x140055c9f  call    cs:__imp_ExFreePoolWithTag
0x140055ca6  nop     dword ptr [rax+rax+00h]
0x140055cab  lea     r11, [rsp+68h+var_28]
0x140055cb0  mov     eax, ebx
0x140055cb2  mov     rbx, [r11+38h]
0x140055cb6  mov     rbp, [r11+40h]
0x140055cba  mov     rsp, r11
0x140055cbd  pop     r15
0x140055cbf  pop     r14
0x140055cc1  pop     r12
0x140055cc3  pop     rdi
0x140055cc4  pop     rsi
0x140055cc5  retn
```
