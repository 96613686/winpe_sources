# WFDStartDiscovery(_ADAPT *,ulong,_DOT11_WFD_DISCOVER_REQUEST_V2 *,void (*)(_ADAPT *,int,DOT11_BYTE_ARRAY *,_DOT11_WFD_DISCOVER_REQUEST_V2 *,void *,void *),void *,void *)

- ea: `0x140056634`
- end: `0x1400568ac`
- name: `?WFDStartDiscovery@@YAHPEAU_ADAPT@@KPEAU_DOT11_WFD_DISCOVER_REQUEST_V2@@P6AX0HPEAUDOT11_BYTE_ARRAY@@1PEAX3@Z33@Z`
- size: `632`
- prototype: `__int64 __fastcall(struct _ADAPT *, int, struct _DOT11_WFD_DISCOVER_REQUEST_V2 *, void (*)(struct _ADAPT *, int, struct DOT11_BYTE_ARRAY *, struct _DOT11_WFD_DISCOVER_REQUEST_V2 *, void *, void *), void *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140087ea0`

## callees

- `0x14000d21c`
- `0x1400208f0`
- `0x140020dc0`
- `0x140056434`
- `0x140056634`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400566aa`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400566aa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056750`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056881`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056750`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056881`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056764`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056892`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056764`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056892`
- `ntoskrnl!KeReleaseSpinLock` at `0x140056739`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400567df`
- `ntoskrnl!KeReleaseSpinLock` at `0x140056739`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400567df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140056719`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140056719`
- `NDIS!NdisWaitEvent` at `0x14005681b`
- `NDIS!NdisWaitEvent` at `0x14005681b`

## pseudocode

```c
__int64 __fastcall WFDStartDiscovery(
        struct _ADAPT *a1,
        int a2,
        struct _DOT11_WFD_DISCOVER_REQUEST_V2 *a3,
        void (*a4)(struct _ADAPT *, int, struct DOT11_BYTE_ARRAY *, struct _DOT11_WFD_DISCOVER_REQUEST_V2 *, void *, void *),
        void *a5,
        void *a6)
{
  char *v9; // rax
  ULONG *v10; // rbx
  unsigned int v11; // ebx
  struct DOT11_WIFI_WFD_DISCOVER_REQUEST *v12; // rdi
  KIRQL v13; // al
  bool v14; // zf
  struct DOT11_WIFI_SCAN_REQUEST *pOutstandingInNic; // r9
  struct _NDIS_EVENT Event; // [rsp+20h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids);
  }
  if ( !a1->ScanModule.bInited )
  {
    v11 = -1073741823;
    goto LABEL_26;
  }
  v9 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
  v10 = (ULONG *)v9;
  if ( !v9 )
  {
    v11 = -1073741670;
LABEL_26:
    v12 = 0;
LABEL_27:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids, v11);
    }
    if ( v12 )
    {
      if ( *((_QWORD *)v12 - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v12 - 2), (char *)v12 - 16);
      else
        ExFreePoolWithTag((char *)v12 - 16, *((_DWORD *)v12 - 2));
    }
    return v11;
  }
  *(_QWORD *)v9 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  v12 = (struct DOT11_WIFI_WFD_DISCOVER_REQUEST *)(v9 + 16);
  *((_DWORD *)v9 + 2) = 879326071;
  *((_QWORD *)v9 + 3) = v9 + 16;
  *((_QWORD *)v9 + 2) = v9 + 16;
  *((_QWORD *)v9 + 5) = WFDIoctlDiscoverCompletion;
  *((_DWORD *)v9 + 8) = a2;
  *((_DWORD *)v9 + 9) = 1;
  *((_QWORD *)v9 + 6) = a3;
  *((_QWORD *)v9 + 7) = a5;
  *((_QWORD *)v9 + 8) = a6;
  v13 = KeAcquireSpinLockRaiseToDpc(&a1->ScanModule.Lock.SpinLock);
  v14 = a1->ScanModule.bDeIniting == 0;
  a1->ScanModule.Lock.OldIrql = v13;
  if ( !v14 )
  {
    KeReleaseSpinLock(&a1->ScanModule.Lock.SpinLock, v13);
    if ( *(_QWORD *)v10 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v10, v10);
    else
      ExFreePoolWithTag(v10, v10[2]);
    v11 = -1073676276;
    goto LABEL_26;
  }
  pOutstandingInNic = a1->ScanModule.pOutstandingInNic;
  if ( pOutstandingInNic )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        30,
        WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids,
        pOutstandingInNic);
    }
    v11 = 1073807377;
  }
  else
  {
    v11 = WFDIssueDiscoverToNic(a1, v12);
  }
  KeReleaseSpinLock(&a1->ScanModule.Lock.SpinLock, a1->ScanModule.Lock.OldIrql);
  if ( v11 != 259 )
  {
    if ( !v11 )
      return v11;
    goto LABEL_27;
  }
  if ( (char *)WFDInternalDiscoverCompletion == (char *)WFDIoctlDiscoverCompletion )
  {
    NdisWaitEvent(&Event, 0);
    return 0;
  }
  return v11;
}

```

## disassembly

```asm
0x140056634  push    rbx
0x140056636  push    rbp
0x140056637  push    rsi
0x140056638  push    rdi
0x140056639  push    r14
0x14005663b  sub     rsp, 40h
0x14005663f  xorps   xmm0, xmm0
0x140056642  mov     dword ptr [rsp+68h+Event.Event.Header.___u0], 0
0x14005664a  xor     eax, eax
0x14005664c  mov     rbp, r8
0x14005664f  movups  xmmword ptr [rsp+68h+Event.Event.Header.SignalState], xmm0
0x140056654  mov     dword ptr [rsp+68h+Event.Event.Header.WaitListHead.Blink+4], eax
0x140056658  mov     r14d, edx
0x14005665b  mov     rsi, rcx
0x14005665e  mov     rcx, cs:WPP_GLOBAL_Control
0x140056665  lea     rax, WPP_GLOBAL_Control
0x14005666c  cmp     rcx, rax
0x14005666f  jz      short loc_140056693
0x140056671  cmp     byte ptr [rcx+29h], 3
0x140056675  jb      short loc_140056693
0x140056677  mov     eax, [rcx+2Ch]
0x14005667a  test    al, 10h
0x14005667c  jz      short loc_140056693
0x14005667e  mov     rcx, [rcx+18h]
0x140056682  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x140056689  mov     edx, 1Dh
0x14005668e  call    WPP_SF_
0x140056693  cmp     dword ptr [rsi+88h], 0
0x14005669a  jz      loc_14005682B
0x1400566a0  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400566a7  mov     rcx, rdi; Lookaside
0x1400566aa  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400566b1  nop     dword ptr [rax+rax+00h]
0x1400566b6  mov     rbx, rax
0x1400566b9  test    rax, rax
0x1400566bc  jnz     short loc_1400566C8
0x1400566be  mov     ebx, 0C000009Ah
0x1400566c3  jmp     loc_140056830
0x1400566c8  mov     [rax], rdi
0x1400566cb  lea     rdi, [rax+10h]
0x1400566cf  mov     dword ptr [rax+8], 34697377h
0x1400566d6  lea     rax, WFDIoctlDiscoverCompletion
0x1400566dd  mov     [rdi+8], rdi
0x1400566e1  mov     [rdi], rdi
0x1400566e4  mov     [rdi+18h], rax
0x1400566e8  mov     rax, [rsp+68h+arg_20]
0x1400566f0  mov     [rdi+10h], r14d
0x1400566f4  mov     dword ptr [rdi+14h], 1
0x1400566fb  mov     [rdi+20h], rbp
0x1400566ff  lea     rbp, [rsi+90h]
0x140056706  mov     [rdi+28h], rax
0x14005670a  mov     rcx, rbp; SpinLock
0x14005670d  mov     rax, [rsp+68h+arg_28]
0x140056715  mov     [rdi+30h], rax
0x140056719  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140056720  nop     dword ptr [rax+rax+00h]
0x140056725  cmp     dword ptr [rsi+8Ch], 0
0x14005672c  mov     [rsi+98h], al
0x140056732  jz      short loc_14005677A
0x140056734  mov     dl, al; NewIrql
0x140056736  mov     rcx, rbp; SpinLock
0x140056739  call    cs:__imp_KeReleaseSpinLock
0x140056740  nop     dword ptr [rax+rax+00h]
0x140056745  mov     rcx, [rbx]; Lookaside
0x140056748  test    rcx, rcx
0x14005674b  jz      short loc_14005675E
0x14005674d  mov     rdx, rbx; Entry
0x140056750  call    cs:__imp_ExFreeToNPagedLookasideList
0x140056757  nop     dword ptr [rax+rax+00h]
0x14005675c  jmp     short loc_140056770
0x14005675e  mov     edx, [rbx+8]; Tag
0x140056761  mov     rcx, rbx; P
0x140056764  call    cs:__imp_ExFreePoolWithTag
0x14005676b  nop     dword ptr [rax+rax+00h]
0x140056770  mov     ebx, 0C001000Ch
0x140056775  jmp     loc_140056830
0x14005677a  mov     r9, [rsi+0A8h]
0x140056781  test    r9, r9
0x140056784  jnz     short loc_14005679C
0x140056786  mov     rdx, rdi; struct DOT11_WIFI_WFD_DISCOVER_REQUEST *
0x140056789  mov     rcx, rsi; struct _ADAPT *
0x14005678c  call    ?WFDIssueDiscoverToNic@@YAHPEAU_ADAPT@@PEAUDOT11_WIFI_WFD_DISCOVER_REQUEST@@@Z; WFDIssueDiscoverToNic(_ADAPT *,DOT11_WIFI_WFD_DISCOVER_REQUEST *)
0x140056791  mov     ebx, eax
0x140056793  lea     r14, WPP_GLOBAL_Control
0x14005679a  jmp     short loc_1400567D6
0x14005679c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400567a3  lea     r14, WPP_GLOBAL_Control
0x1400567aa  cmp     rcx, r14
0x1400567ad  jz      short loc_1400567D1
0x1400567af  cmp     byte ptr [rcx+29h], 1
0x1400567b3  jb      short loc_1400567D1
0x1400567b5  mov     eax, [rcx+2Ch]
0x1400567b8  test    al, 10h
0x1400567ba  jz      short loc_1400567D1
0x1400567bc  mov     rcx, [rcx+18h]
0x1400567c0  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x1400567c7  mov     edx, 1Eh
0x1400567cc  call    WPP_SF_q
0x1400567d1  mov     ebx, 40010011h
0x1400567d6  mov     dl, [rsi+98h]; NewIrql
0x1400567dc  mov     rcx, rbp; SpinLock
0x1400567df  call    cs:__imp_KeReleaseSpinLock
0x1400567e6  nop     dword ptr [rax+rax+00h]
0x1400567eb  cmp     ebx, 103h
0x1400567f1  jz      short loc_1400567FD
0x1400567f3  test    ebx, ebx
0x1400567f5  jz      loc_14005689E
0x1400567fb  jmp     short loc_140056839
0x1400567fd  lea     rax, WFDInternalDiscoverCompletion
0x140056804  lea     rcx, WFDIoctlDiscoverCompletion
0x14005680b  cmp     rax, rcx
0x14005680e  jnz     loc_14005689E
0x140056814  xor     edx, edx; MsToWait
0x140056816  lea     rcx, [rsp+68h+Event]; Event
0x14005681b  call    cs:__imp_NdisWaitEvent
0x140056822  nop     dword ptr [rax+rax+00h]
0x140056827  xor     ebx, ebx
0x140056829  jmp     short loc_14005689E
0x14005682b  mov     ebx, 0C0000001h
0x140056830  xor     edi, edi
0x140056832  lea     r14, WPP_GLOBAL_Control
0x140056839  mov     rcx, cs:WPP_GLOBAL_Control
0x140056840  cmp     rcx, r14
0x140056843  jz      short loc_14005686A
0x140056845  cmp     byte ptr [rcx+29h], 1
0x140056849  jb      short loc_14005686A
0x14005684b  mov     eax, [rcx+2Ch]
0x14005684e  test    al, 10h
0x140056850  jz      short loc_14005686A
0x140056852  mov     rcx, [rcx+18h]
0x140056856  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x14005685d  mov     edx, 1Fh
0x140056862  mov     r9d, ebx
0x140056865  call    WPP_SF_d
0x14005686a  test    rdi, rdi
0x14005686d  jz      short loc_14005689E
0x14005686f  lea     rcx, [rdi-10h]; P
0x140056873  mov     rax, [rcx]
0x140056876  test    rax, rax
0x140056879  jz      short loc_14005688F
0x14005687b  mov     rdx, rcx; Entry
0x14005687e  mov     rcx, rax; Lookaside
0x140056881  call    cs:__imp_ExFreeToNPagedLookasideList
0x140056888  nop     dword ptr [rax+rax+00h]
0x14005688d  jmp     short loc_14005689E
0x14005688f  mov     edx, [rcx+8]; Tag
0x140056892  call    cs:__imp_ExFreePoolWithTag
0x140056899  nop     dword ptr [rax+rax+00h]
0x14005689e  mov     eax, ebx
0x1400568a0  add     rsp, 40h
0x1400568a4  pop     r14
0x1400568a6  pop     rdi
0x1400568a7  pop     rsi
0x1400568a8  pop     rbp
0x1400568a9  pop     rbx
0x1400568aa  retn
```
