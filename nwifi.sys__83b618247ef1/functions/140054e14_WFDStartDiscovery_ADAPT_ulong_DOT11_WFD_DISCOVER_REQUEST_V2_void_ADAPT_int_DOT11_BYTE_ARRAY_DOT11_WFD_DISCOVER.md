# WFDStartDiscovery(_ADAPT *,ulong,_DOT11_WFD_DISCOVER_REQUEST_V2 *,void (*)(_ADAPT *,int,DOT11_BYTE_ARRAY *,_DOT11_WFD_DISCOVER_REQUEST_V2 *,void *,void *),void *,void *)

- ea: `0x140054e14`
- end: `0x14005508c`
- name: `?WFDStartDiscovery@@YAHPEAU_ADAPT@@KPEAU_DOT11_WFD_DISCOVER_REQUEST_V2@@P6AX0HPEAUDOT11_BYTE_ARRAY@@1PEAX3@Z33@Z`
- size: `632`
- prototype: `__int64 __usercall@<rax>(struct _ADAPT *@<rcx>, unsigned int@<edx>, struct _DOT11_WFD_DISCOVER_REQUEST_V2 *@<r8>, void (*)(struct _ADAPT *, int, struct DOT11_BYTE_ARRAY *, struct _DOT11_WFD_DISCOVER_REQUEST_V2 *, void *, void *)@<r9>, void *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140086670`

## callees

- `0x14000d22c`
- `0x1400208f0`
- `0x140020dc0`
- `0x140054c14`
- `0x140054e14`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140054e8a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140054e8a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054f30`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140055061`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054f30`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140055061`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054f44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055072`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054f44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055072`
- `ntoskrnl!KeReleaseSpinLock` at `0x140054f19`
- `ntoskrnl!KeReleaseSpinLock` at `0x140054fbf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140054f19`
- `ntoskrnl!KeReleaseSpinLock` at `0x140054fbf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140054ef9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140054ef9`
- `NDIS!NdisWaitEvent` at `0x140054ffb`
- `NDIS!NdisWaitEvent` at `0x140054ffb`

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
0x140054e14  push    rbx
0x140054e16  push    rbp
0x140054e17  push    rsi
0x140054e18  push    rdi
0x140054e19  push    r14
0x140054e1b  sub     rsp, 40h
0x140054e1f  xorps   xmm0, xmm0
0x140054e22  mov     dword ptr [rsp+68h+Event.Event.Header.___u0], 0
0x140054e2a  xor     eax, eax
0x140054e2c  mov     rbp, r8
0x140054e2f  movups  xmmword ptr [rsp+68h+Event.Event.Header.SignalState], xmm0
0x140054e34  mov     dword ptr [rsp+68h+Event.Event.Header.WaitListHead.Blink+4], eax
0x140054e38  mov     r14d, edx
0x140054e3b  mov     rsi, rcx
0x140054e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140054e45  lea     rax, WPP_GLOBAL_Control
0x140054e4c  cmp     rcx, rax
0x140054e4f  jz      short loc_140054E73
0x140054e51  cmp     byte ptr [rcx+29h], 3
0x140054e55  jb      short loc_140054E73
0x140054e57  mov     eax, [rcx+2Ch]
0x140054e5a  test    al, 10h
0x140054e5c  jz      short loc_140054E73
0x140054e5e  mov     rcx, [rcx+18h]
0x140054e62  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x140054e69  mov     edx, 1Dh
0x140054e6e  call    WPP_SF_
0x140054e73  cmp     dword ptr [rsi+88h], 0
0x140054e7a  jz      loc_14005500B
0x140054e80  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140054e87  mov     rcx, rdi; Lookaside
0x140054e8a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140054e91  nop     dword ptr [rax+rax+00h]
0x140054e96  mov     rbx, rax
0x140054e99  test    rax, rax
0x140054e9c  jnz     short loc_140054EA8
0x140054e9e  mov     ebx, 0C000009Ah
0x140054ea3  jmp     loc_140055010
0x140054ea8  mov     [rax], rdi
0x140054eab  lea     rdi, [rax+10h]
0x140054eaf  mov     dword ptr [rax+8], 34697377h
0x140054eb6  lea     rax, WFDIoctlDiscoverCompletion
0x140054ebd  mov     [rdi+8], rdi
0x140054ec1  mov     [rdi], rdi
0x140054ec4  mov     [rdi+18h], rax
0x140054ec8  mov     rax, [rsp+68h+arg_20]
0x140054ed0  mov     [rdi+10h], r14d
0x140054ed4  mov     dword ptr [rdi+14h], 1
0x140054edb  mov     [rdi+20h], rbp
0x140054edf  lea     rbp, [rsi+90h]
0x140054ee6  mov     [rdi+28h], rax
0x140054eea  mov     rcx, rbp; SpinLock
0x140054eed  mov     rax, [rsp+68h+arg_28]
0x140054ef5  mov     [rdi+30h], rax
0x140054ef9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140054f00  nop     dword ptr [rax+rax+00h]
0x140054f05  cmp     dword ptr [rsi+8Ch], 0
0x140054f0c  mov     [rsi+98h], al
0x140054f12  jz      short loc_140054F5A
0x140054f14  mov     dl, al; NewIrql
0x140054f16  mov     rcx, rbp; SpinLock
0x140054f19  call    cs:__imp_KeReleaseSpinLock
0x140054f20  nop     dword ptr [rax+rax+00h]
0x140054f25  mov     rcx, [rbx]; Lookaside
0x140054f28  test    rcx, rcx
0x140054f2b  jz      short loc_140054F3E
0x140054f2d  mov     rdx, rbx; Entry
0x140054f30  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054f37  nop     dword ptr [rax+rax+00h]
0x140054f3c  jmp     short loc_140054F50
0x140054f3e  mov     edx, [rbx+8]; Tag
0x140054f41  mov     rcx, rbx; P
0x140054f44  call    cs:__imp_ExFreePoolWithTag
0x140054f4b  nop     dword ptr [rax+rax+00h]
0x140054f50  mov     ebx, 0C001000Ch
0x140054f55  jmp     loc_140055010
0x140054f5a  mov     r9, [rsi+0A8h]
0x140054f61  test    r9, r9
0x140054f64  jnz     short loc_140054F7C
0x140054f66  mov     rdx, rdi; struct DOT11_WIFI_WFD_DISCOVER_REQUEST *
0x140054f69  mov     rcx, rsi; struct _ADAPT *
0x140054f6c  call    ?WFDIssueDiscoverToNic@@YAHPEAU_ADAPT@@PEAUDOT11_WIFI_WFD_DISCOVER_REQUEST@@@Z; WFDIssueDiscoverToNic(_ADAPT *,DOT11_WIFI_WFD_DISCOVER_REQUEST *)
0x140054f71  mov     ebx, eax
0x140054f73  lea     r14, WPP_GLOBAL_Control
0x140054f7a  jmp     short loc_140054FB6
0x140054f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140054f83  lea     r14, WPP_GLOBAL_Control
0x140054f8a  cmp     rcx, r14
0x140054f8d  jz      short loc_140054FB1
0x140054f8f  cmp     byte ptr [rcx+29h], 1
0x140054f93  jb      short loc_140054FB1
0x140054f95  mov     eax, [rcx+2Ch]
0x140054f98  test    al, 10h
0x140054f9a  jz      short loc_140054FB1
0x140054f9c  mov     rcx, [rcx+18h]
0x140054fa0  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x140054fa7  mov     edx, 1Eh
0x140054fac  call    WPP_SF_q
0x140054fb1  mov     ebx, 40010011h
0x140054fb6  mov     dl, [rsi+98h]; NewIrql
0x140054fbc  mov     rcx, rbp; SpinLock
0x140054fbf  call    cs:__imp_KeReleaseSpinLock
0x140054fc6  nop     dword ptr [rax+rax+00h]
0x140054fcb  cmp     ebx, 103h
0x140054fd1  jz      short loc_140054FDD
0x140054fd3  test    ebx, ebx
0x140054fd5  jz      loc_14005507E
0x140054fdb  jmp     short loc_140055019
0x140054fdd  lea     rax, WFDInternalDiscoverCompletion
0x140054fe4  lea     rcx, WFDIoctlDiscoverCompletion
0x140054feb  cmp     rax, rcx
0x140054fee  jnz     loc_14005507E
0x140054ff4  xor     edx, edx; MsToWait
0x140054ff6  lea     rcx, [rsp+68h+Event]; Event
0x140054ffb  call    cs:__imp_NdisWaitEvent
0x140055002  nop     dword ptr [rax+rax+00h]
0x140055007  xor     ebx, ebx
0x140055009  jmp     short loc_14005507E
0x14005500b  mov     ebx, 0C0000001h
0x140055010  xor     edi, edi
0x140055012  lea     r14, WPP_GLOBAL_Control
0x140055019  mov     rcx, cs:WPP_GLOBAL_Control
0x140055020  cmp     rcx, r14
0x140055023  jz      short loc_14005504A
0x140055025  cmp     byte ptr [rcx+29h], 1
0x140055029  jb      short loc_14005504A
0x14005502b  mov     eax, [rcx+2Ch]
0x14005502e  test    al, 10h
0x140055030  jz      short loc_14005504A
0x140055032  mov     rcx, [rcx+18h]
0x140055036  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x14005503d  mov     edx, 1Fh
0x140055042  mov     r9d, ebx
0x140055045  call    WPP_SF_d
0x14005504a  test    rdi, rdi
0x14005504d  jz      short loc_14005507E
0x14005504f  lea     rcx, [rdi-10h]; P
0x140055053  mov     rax, [rcx]
0x140055056  test    rax, rax
0x140055059  jz      short loc_14005506F
0x14005505b  mov     rdx, rcx; Entry
0x14005505e  mov     rcx, rax; Lookaside
0x140055061  call    cs:__imp_ExFreeToNPagedLookasideList
0x140055068  nop     dword ptr [rax+rax+00h]
0x14005506d  jmp     short loc_14005507E
0x14005506f  mov     edx, [rcx+8]; Tag
0x140055072  call    cs:__imp_ExFreePoolWithTag
0x140055079  nop     dword ptr [rax+rax+00h]
0x14005507e  mov     eax, ebx
0x140055080  add     rsp, 40h
0x140055084  pop     r14
0x140055086  pop     rdi
0x140055087  pop     rsi
0x140055088  pop     rbp
0x140055089  pop     rbx
0x14005508a  retn
```
