# RDPDYN_DispatchNewDevMgmtEvent

- ea: `0x1400027b0`
- end: `0x140002a32`
- name: `RDPDYN_DispatchNewDevMgmtEvent`
- size: `642`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, struct DrDevice *)`
- caller_count: `8`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1400049fc`
- `0x140011df0`
- `0x140015bc0`
- `0x14001dd70`
- `0x14001e10c`
- `0x14001e3f0`
- `0x14001ea80`
- `0x140029228`

## callees

- `0x140001660`
- `0x140001e30`
- `0x14000231c`
- `0x1400025ac`
- `0x1400027b0`
- `0x14000324c`
- `0x14000327c`
- `0x140004050`
- `0x140004168`
- `0x140004438`
- `0x140004604`
- `0x1400046b8`
- `0x14001aac4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002814`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400028bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002814`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400028bd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002854`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002927`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002979`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400029aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002854`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002927`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002979`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400029aa`
- `ntoskrnl!IofCompleteRequest` at `0x1400029ca`
- `ntoskrnl!IofCompleteRequest` at `0x1400029ca`

## pseudocode

```c
__int64 __fastcall RDPDYN_DispatchNewDevMgmtEvent(void *a1, unsigned int a2, unsigned int a3, struct DrDevice *a4)
{
  KIRQL v9; // r15
  unsigned int v10; // edi
  __int64 v11; // rcx
  __int64 NextEventRequest; // rbx
  unsigned int v13; // r12d
  KIRQL v14; // si
  int v15; // ecx
  __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned int v18; // r15d
  void *v19; // r14
  __int64 v20; // rsi
  RefCount *v21; // rcx
  int v22; // [rsp+28h] [rbp-28h]
  unsigned int v23; // [rsp+30h] [rbp-20h] BYREF
  void *v24; // [rsp+38h] [rbp-18h] BYREF
  __int64 v25; // [rsp+40h] [rbp-10h] BYREF

  v25 = 0;
  v24 = 0;
  v23 = 0;
  if ( !WPP_MAIN_CB.DeviceQueue.Lock )
  {
    if ( a1 )
      operator delete(a1);
    return 3221225860LL;
  }
  if ( a4 )
    _InterlockedIncrement((volatile signed __int32 *)a4 + 4);
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock);
  v10 = RDPDEVNTLIST_EnqueueEventEx((struct tagSESSIONLIST *)WPP_MAIN_CB.DeviceQueue.Lock, a2, a1, a4, a3, v22);
  if ( v10 )
    operator delete(a1);
  KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v9);
  if ( v10 )
  {
    if ( !a4 )
      goto LABEL_27;
    v21 = a4;
  }
  else
  {
    NextEventRequest = GetNextEventRequest(v11, a2);
    if ( !NextEventRequest )
      goto LABEL_27;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids, a2);
    v13 = *(_DWORD *)(*(_QWORD *)(NextEventRequest + 184) + 8LL);
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock);
    if ( !(unsigned int)RDPEVNTLIST_PeekNextEvent(v15, a2, (unsigned int)&v24, (unsigned int)&v23, (__int64)&v25) )
    {
      v10 = RDPEVNTLIST_EnqueueRequest(v16, a2, NextEventRequest);
      KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v14);
      if ( v10 )
      {
        *(_DWORD *)(NextEventRequest + 48) = v10;
        *(_QWORD *)(NextEventRequest + 56) = 0;
        IofCompleteRequest((PIRP)NextEventRequest, 0);
      }
      else
      {
        _InterlockedExchange64((volatile __int64 *)(NextEventRequest + 104), (__int64)DevMgmtEventRequestIRPCancel);
      }
      goto LABEL_27;
    }
    v18 = RDPDYN_DevMgmtEventSize(v24, v23);
    if ( v13 < v18 + 8 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v14);
      v10 = CompleteIRPWithResizeMsg((PIRP)NextEventRequest);
      goto LABEL_27;
    }
    RDPEVNTLIST_DequeueEvent(v17, a2, &v23, &v24, 0);
    KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v14);
    v19 = v24;
    v20 = v25;
    v10 = CompleteIRPWithDevMgmtEvent((PIRP)NextEventRequest, v18, v23, v24, v25);
    if ( v19 )
      operator delete(v19);
    if ( !v20 )
      goto LABEL_27;
    v21 = (RefCount *)v20;
  }
  RefCount::Release(v21);
LABEL_27:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids);
  return v10;
}

```

## disassembly

```asm
0x1400027b0  push    rbp
0x1400027b2  push    rbx
0x1400027b3  push    rsi
0x1400027b4  push    rdi
0x1400027b5  push    r12
0x1400027b7  push    r14
0x1400027b9  push    r15
0x1400027bb  mov     rbp, rsp
0x1400027be  sub     rsp, 50h
0x1400027c2  cmp     cs:WPP_MAIN_CB.DeviceQueue.Lock, 0
0x1400027ca  mov     rbx, r9
0x1400027cd  mov     edi, r8d
0x1400027d0  mov     [rbp+var_10], 0
0x1400027d8  mov     r14d, edx
0x1400027db  mov     [rbp+var_18], 0
0x1400027e3  mov     rsi, rcx
0x1400027e6  mov     [rbp+var_20], 0
0x1400027ed  jnz     short loc_140002803
0x1400027ef  test    rcx, rcx
0x1400027f2  jz      short loc_1400027F9
0x1400027f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400027f9  mov     eax, 0C0000184h
0x1400027fe  jmp     loc_140002A22
0x140002803  test    rbx, rbx
0x140002806  jz      short loc_14000280D
0x140002808  lock inc dword ptr [r9+10h]
0x14000280d  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140002814  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000281b  nop     dword ptr [rax+rax+00h]
0x140002820  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; struct tagSESSIONLIST *
0x140002827  mov     r9, rbx; struct DrDevice *
0x14000282a  mov     r8, rsi; void *
0x14000282d  mov     [rsp+50h+var_30], edi; unsigned int
0x140002831  mov     edx, r14d; unsigned int
0x140002834  mov     r15b, al
0x140002837  call    ?RDPDEVNTLIST_EnqueueEventEx@@YAJPEAUtagSESSIONLIST@@KPEAXPEAVDrDevice@@KH@Z; RDPDEVNTLIST_EnqueueEventEx(tagSESSIONLIST *,ulong,void *,DrDevice *,ulong,int)
0x14000283c  mov     edi, eax
0x14000283e  test    eax, eax
0x140002840  jz      short loc_14000284A
0x140002842  mov     rcx, rsi; void *
0x140002845  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000284a  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140002851  mov     dl, r15b; NewIrql
0x140002854  call    cs:__imp_KeReleaseSpinLock
0x14000285b  nop     dword ptr [rax+rax+00h]
0x140002860  test    edi, edi
0x140002862  jnz     loc_1400029E5
0x140002868  mov     edx, r14d
0x14000286b  call    GetNextEventRequest
0x140002870  mov     rbx, rax
0x140002873  test    rax, rax
0x140002876  jz      loc_1400029F2
0x14000287c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002883  lea     rax, WPP_GLOBAL_Control
0x14000288a  cmp     rcx, rax
0x14000288d  jz      short loc_1400028AB
0x14000288f  cmp     byte ptr [rcx+29h], 4
0x140002893  jb      short loc_1400028AB
0x140002895  mov     rcx, [rcx+18h]
0x140002899  lea     edx, [rdi+1Ch]
0x14000289c  mov     r9d, r14d
0x14000289f  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x1400028a6  call    WPP_SF_d
0x1400028ab  mov     rax, [rbx+0B8h]
0x1400028b2  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x1400028b9  mov     r12d, [rax+8]
0x1400028bd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400028c4  nop     dword ptr [rax+rax+00h]
0x1400028c9  lea     r9, [rbp+var_20]
0x1400028cd  mov     edx, r14d
0x1400028d0  mov     sil, al
0x1400028d3  lea     r8, [rbp+var_18]
0x1400028d7  lea     rax, [rbp+var_10]
0x1400028db  mov     qword ptr [rsp+50h+var_30], rax
0x1400028e0  call    RDPEVNTLIST_PeekNextEvent
0x1400028e5  test    eax, eax
0x1400028e7  jz      loc_140002993
0x1400028ed  mov     edx, [rbp+var_20]
0x1400028f0  mov     rcx, [rbp+var_18]
0x1400028f4  call    RDPDYN_DevMgmtEventSize
0x1400028f9  mov     r15d, eax
0x1400028fc  lea     edi, [rax+8]
0x1400028ff  cmp     r12d, edi
0x140002902  jb      short loc_14000296F
0x140002904  lea     r9, [rbp+var_18]
0x140002908  mov     qword ptr [rsp+50h+var_30], 0
0x140002911  lea     r8, [rbp+var_20]
0x140002915  mov     edx, r14d
0x140002918  call    RDPEVNTLIST_DequeueEvent
0x14000291d  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140002924  mov     dl, sil; NewIrql
0x140002927  call    cs:__imp_KeReleaseSpinLock
0x14000292e  nop     dword ptr [rax+rax+00h]
0x140002933  mov     r14, [rbp+var_18]
0x140002937  mov     edx, r15d; Size
0x14000293a  mov     rsi, [rbp+var_10]
0x14000293e  mov     r9, r14
0x140002941  mov     r8d, [rbp+var_20]
0x140002945  mov     rcx, rbx; Irp
0x140002948  mov     qword ptr [rsp+50h+var_30], rsi; __int64
0x14000294d  call    CompleteIRPWithDevMgmtEvent
0x140002952  mov     edi, eax
0x140002954  test    r14, r14
0x140002957  jz      short loc_140002961
0x140002959  mov     rcx, r14; void *
0x14000295c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002961  test    rsi, rsi
0x140002964  jz      loc_1400029F2
0x14000296a  mov     rcx, rsi
0x14000296d  jmp     short loc_1400029ED
0x14000296f  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140002976  mov     dl, sil; NewIrql
0x140002979  call    cs:__imp_KeReleaseSpinLock
0x140002980  nop     dword ptr [rax+rax+00h]
0x140002985  mov     edx, edi
0x140002987  mov     rcx, rbx; Irp
0x14000298a  call    CompleteIRPWithResizeMsg
0x14000298f  mov     edi, eax
0x140002991  jmp     short loc_1400029F2
0x140002993  mov     r8, rbx
0x140002996  mov     edx, r14d
0x140002999  call    RDPEVNTLIST_EnqueueRequest
0x14000299e  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x1400029a5  mov     dl, sil; NewIrql
0x1400029a8  mov     edi, eax
0x1400029aa  call    cs:__imp_KeReleaseSpinLock
0x1400029b1  nop     dword ptr [rax+rax+00h]
0x1400029b6  test    edi, edi
0x1400029b8  jz      short loc_1400029D8
0x1400029ba  xor     edx, edx; PriorityBoost
0x1400029bc  mov     [rbx+30h], edi
0x1400029bf  mov     rcx, rbx; Irp
0x1400029c2  mov     qword ptr [rbx+38h], 0
0x1400029ca  call    cs:__imp_IofCompleteRequest
0x1400029d1  nop     dword ptr [rax+rax+00h]
0x1400029d6  jmp     short loc_1400029F2
0x1400029d8  lea     rax, ?DevMgmtEventRequestIRPCancel@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; DevMgmtEventRequestIRPCancel(_DEVICE_OBJECT *,_IRP *)
0x1400029df  xchg    rax, [rbx+68h]
0x1400029e3  jmp     short loc_1400029F2
0x1400029e5  test    rbx, rbx
0x1400029e8  jz      short loc_1400029F2
0x1400029ea  mov     rcx, rbx; this
0x1400029ed  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x1400029f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400029f9  lea     rax, WPP_GLOBAL_Control
0x140002a00  cmp     rcx, rax
0x140002a03  jz      short loc_140002A20
0x140002a05  cmp     byte ptr [rcx+29h], 4
0x140002a09  jb      short loc_140002A20
0x140002a0b  mov     rcx, [rcx+18h]
0x140002a0f  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x140002a16  mov     edx, 1Dh
0x140002a1b  call    WPP_SF_
0x140002a20  mov     eax, edi
0x140002a22  add     rsp, 50h
0x140002a26  pop     r15
0x140002a28  pop     r14
0x140002a2a  pop     r12
0x140002a2c  pop     rdi
0x140002a2d  pop     rsi
0x140002a2e  pop     rbx
0x140002a2f  pop     rbp
0x140002a30  retn
```
