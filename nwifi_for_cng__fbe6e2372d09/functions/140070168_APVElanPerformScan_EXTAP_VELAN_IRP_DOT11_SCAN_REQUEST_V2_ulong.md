# APVElanPerformScan(_EXTAP_VELAN *,_IRP *,_DOT11_SCAN_REQUEST_V2 *,ulong)

- ea: `0x140070168`
- end: `0x1400703cc`
- name: `?APVElanPerformScan@@YAHPEAU_EXTAP_VELAN@@PEAU_IRP@@PEAU_DOT11_SCAN_REQUEST_V2@@K@Z`
- size: `612`
- prototype: `__int64 __fastcall(struct _EXTAP_VELAN *, struct _IRP *, struct _DOT11_SCAN_REQUEST_V2 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400746a0`

## callees

- `0x14000d21c`
- `0x14001ecb8`
- `0x140020dc0`
- `0x1400559bc`
- `0x140070168`
- `0x140072700`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140070226`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140070226`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400702cb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400702cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400702e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400702e2`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140070259`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140070259`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400702ab`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14007033c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400702ab`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14007033c`

## pseudocode

```c
__int64 __fastcall APVElanPerformScan(
        struct _NDIS_EVENT *a1,
        _LIST_ENTRY *a2,
        struct _DOT11_SCAN_REQUEST_V2 *a3,
        unsigned int a4)
{
  unsigned int started; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  char *v12; // rax
  ULONG *v13; // rdi
  _LIST_ENTRY *v14; // rsi
  KIRQL Irql; // [rsp+80h] [rbp+8h] BYREF

  Irql = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids);
  if ( *(int *)(*(_QWORD *)&a1->Event.Header.Lock + 5108LL) <= 1 )
  {
    v11 = Dot11ValidateV2ScanRequest(a3, a4);
    started = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return started;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids, v11);
      goto LABEL_24;
    }
    v12 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue);
    v13 = (ULONG *)v12;
    if ( v12 )
    {
      *(_QWORD *)v12 = &WPP_MAIN_CB.DeviceQueue;
      v14 = (_LIST_ENTRY *)(v12 + 16);
      *((_DWORD *)v12 + 2) = 1751741303;
      *((_QWORD *)v12 + 2) = 0;
      IoAcquireCancelSpinLock(&Irql);
      if ( BYTE4(a2[4].Flink) )
      {
        started = -1073741536;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 115, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids);
        }
        IoReleaseCancelSpinLock(Irql);
        if ( v14 )
        {
          if ( *(_QWORD *)v13 )
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v13, v13);
          else
            ExFreePoolWithTag(v13, v13[2]);
        }
      }
      else
      {
        BYTE3(a2[11].Blink->Flink) |= 1u;
        v14->Flink = a2;
        a2[7].Blink = v14;
        _InterlockedExchange64((volatile __int64 *)&a2[6].Blink, (__int64)ExtAPCancelIoctlScan);
        started = Dot11StartScanV2(
                    *(struct _ADAPT **)(*(_QWORD *)&a1->Event.Header.Lock + 16LL),
                    a4,
                    (_LIST_ENTRY *)a3,
                    (void (*)(struct _ADAPT *, int, struct _DOT11_SCAN_REQUEST_V2 *, void *, void *))ExtAPScanCompletion,
                    a1,
                    v14);
        IoReleaseCancelSpinLock(Irql);
        if ( started != 259 )
        {
          ExtAPScanCompletion(
            *(struct _ADAPT **)(*(_QWORD *)&a1->Event.Header.Lock + 16LL),
            started,
            a3,
            (struct _EXTAP_VELAN *)a1,
            (PNPAGED_LOOKASIDE_LIST *)v14);
          started = 259;
        }
      }
      goto LABEL_24;
    }
    started = -1073741670;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return started;
    v10 = 114;
  }
  else
  {
    started = -1071439870;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return started;
    v10 = 112;
  }
  WPP_SF_(v9->AttachedDevice, v10, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids);
LABEL_24:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 116, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids, started);
  return started;
}

```

## disassembly

```asm
0x140070168  mov     rax, rsp
0x14007016b  push    rbx
0x14007016c  push    rbp
0x14007016d  push    rsi
0x14007016e  push    rdi
0x14007016f  push    r12
0x140070171  push    r13
0x140070173  push    r14
0x140070175  push    r15
0x140070177  sub     rsp, 38h
0x14007017b  mov     r12d, r9d
0x14007017e  mov     byte ptr [rax+8], 0
0x140070182  mov     r15, r8
0x140070185  mov     rbp, rdx
0x140070188  mov     r14, rcx
0x14007018b  mov     rcx, cs:WPP_GLOBAL_Control
0x140070192  lea     r13, WPP_GLOBAL_Control
0x140070199  cmp     rcx, r13
0x14007019c  jz      short loc_1400701B3
0x14007019e  mov     rcx, [rcx+18h]
0x1400701a2  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x1400701a9  mov     edx, 6Fh ; 'o'
0x1400701ae  call    WPP_SF_
0x1400701b3  mov     rax, [r14]
0x1400701b6  cmp     dword ptr [rax+13F4h], 1
0x1400701bd  jle     short loc_1400701DE
0x1400701bf  mov     ebx, 0C0232002h
0x1400701c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400701cb  cmp     rcx, r13
0x1400701ce  jz      loc_1400703B8
0x1400701d4  mov     edx, 70h ; 'p'
0x1400701d9  jmp     loc_140070384
0x1400701de  mov     edx, r12d; unsigned int
0x1400701e1  mov     rcx, r15; struct _DOT11_SCAN_REQUEST_V2 *
0x1400701e4  call    ?Dot11ValidateV2ScanRequest@@YAJPEBU_DOT11_SCAN_REQUEST_V2@@K@Z; Dot11ValidateV2ScanRequest(_DOT11_SCAN_REQUEST_V2 const *,ulong)
0x1400701e9  mov     ebx, eax
0x1400701eb  test    eax, eax
0x1400701ed  jz      short loc_14007021C
0x1400701ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400701f6  cmp     rcx, r13
0x1400701f9  jz      loc_1400703B8
0x1400701ff  mov     rcx, [rcx+18h]
0x140070203  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14007020a  mov     edx, 71h ; 'q'
0x14007020f  mov     r9d, eax
0x140070212  call    WPP_SF_d
0x140070217  jmp     loc_140070394
0x14007021c  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140070223  mov     rcx, rbx; Lookaside
0x140070226  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007022d  nop     dword ptr [rax+rax+00h]
0x140070232  mov     rdi, rax
0x140070235  test    rax, rax
0x140070238  jz      loc_14007036E
0x14007023e  mov     [rax], rbx
0x140070241  lea     rsi, [rax+10h]
0x140070245  mov     dword ptr [rax+8], 68697377h
0x14007024c  lea     rcx, [rsp+78h+Irql]; Irql
0x140070254  xor     eax, eax
0x140070256  mov     [rsi], rax
0x140070259  call    cs:__imp_IoAcquireCancelSpinLock
0x140070260  nop     dword ptr [rax+rax+00h]
0x140070265  cmp     byte ptr [rbp+44h], 0
0x140070269  jz      loc_1400702F3
0x14007026f  mov     ebx, 0C0000120h
0x140070274  mov     rcx, cs:WPP_GLOBAL_Control
0x14007027b  cmp     rcx, r13
0x14007027e  jz      short loc_1400702A4
0x140070280  cmp     byte ptr [rcx+29h], 3
0x140070284  jb      short loc_1400702A4
0x140070286  test    dword ptr [rcx+2Ch], 100000h
0x14007028d  jz      short loc_1400702A4
0x14007028f  mov     rcx, [rcx+18h]
0x140070293  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14007029a  mov     edx, 73h ; 's'
0x14007029f  call    WPP_SF_
0x1400702a4  mov     cl, [rsp+78h+Irql]; Irql
0x1400702ab  call    cs:__imp_IoReleaseCancelSpinLock
0x1400702b2  nop     dword ptr [rax+rax+00h]
0x1400702b7  test    rsi, rsi
0x1400702ba  jz      loc_140070394
0x1400702c0  mov     rcx, [rdi]; Lookaside
0x1400702c3  test    rcx, rcx
0x1400702c6  jz      short loc_1400702DC
0x1400702c8  mov     rdx, rdi; Entry
0x1400702cb  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400702d2  nop     dword ptr [rax+rax+00h]
0x1400702d7  jmp     loc_140070394
0x1400702dc  mov     edx, [rdi+8]; Tag
0x1400702df  mov     rcx, rdi; P
0x1400702e2  call    cs:__imp_ExFreePoolWithTag
0x1400702e9  nop     dword ptr [rax+rax+00h]
0x1400702ee  jmp     loc_140070394
0x1400702f3  mov     rax, [rbp+0B8h]
0x1400702fa  lea     r9, ?ExtAPScanCompletion@@YAXPEAU_ADAPT@@HPEAXPEAU_EXTAP_VELAN@@PEAU_EXTAP_SCAN_CONTEXT@@@Z; void (*)(struct _ADAPT *, int, struct _DOT11_SCAN_REQUEST_V2 *, void *, void *)
0x140070301  mov     [rsp+78h+var_50], rsi; void *
0x140070306  mov     r8, r15; struct _DOT11_SCAN_REQUEST_V2 *
0x140070309  mov     edx, r12d; unsigned int
0x14007030c  mov     [rsp+78h+var_58], r14; void *
0x140070311  or      byte ptr [rax+3], 1
0x140070315  lea     rax, ?ExtAPCancelIoctlScan@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ExtAPCancelIoctlScan(_DEVICE_OBJECT *,_IRP *)
0x14007031c  mov     [rsi], rbp
0x14007031f  mov     [rbp+78h], rsi
0x140070323  xchg    rax, [rbp+68h]
0x140070327  mov     rcx, [r14]
0x14007032a  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14007032e  call    ?Dot11StartScanV2@@YAHPEAU_ADAPT@@KPEAU_DOT11_SCAN_REQUEST_V2@@P6AX0H1PEAX2@Z22@Z; Dot11StartScanV2(_ADAPT *,ulong,_DOT11_SCAN_REQUEST_V2 *,void (*)(_ADAPT *,int,_DOT11_SCAN_REQUEST_V2 *,void *,void *),void *,void *)
0x140070333  mov     cl, [rsp+78h+Irql]; Irql
0x14007033a  mov     ebx, eax
0x14007033c  call    cs:__imp_IoReleaseCancelSpinLock
0x140070343  nop     dword ptr [rax+rax+00h]
0x140070348  mov     edi, 103h
0x14007034d  cmp     ebx, edi
0x14007034f  jz      short loc_140070394
0x140070351  mov     rcx, [r14]
0x140070354  mov     r9, r14; struct _EXTAP_VELAN *
0x140070357  mov     r8, r15; void *
0x14007035a  mov     [rsp+78h+var_58], rsi; struct _EXTAP_SCAN_CONTEXT *
0x14007035f  mov     edx, ebx; int
0x140070361  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140070365  call    ?ExtAPScanCompletion@@YAXPEAU_ADAPT@@HPEAXPEAU_EXTAP_VELAN@@PEAU_EXTAP_SCAN_CONTEXT@@@Z; ExtAPScanCompletion(_ADAPT *,int,void *,_EXTAP_VELAN *,_EXTAP_SCAN_CONTEXT *)
0x14007036a  mov     ebx, edi
0x14007036c  jmp     short loc_140070394
0x14007036e  mov     ebx, 0C000009Ah
0x140070373  mov     rcx, cs:WPP_GLOBAL_Control
0x14007037a  cmp     rcx, r13
0x14007037d  jz      short loc_1400703B8
0x14007037f  mov     edx, 72h ; 'r'
0x140070384  mov     rcx, [rcx+18h]
0x140070388  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14007038f  call    WPP_SF_
0x140070394  mov     rcx, cs:WPP_GLOBAL_Control
0x14007039b  cmp     rcx, r13
0x14007039e  jz      short loc_1400703B8
0x1400703a0  mov     rcx, [rcx+18h]
0x1400703a4  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x1400703ab  mov     edx, 74h ; 't'
0x1400703b0  mov     r9d, ebx
0x1400703b3  call    WPP_SF_d
0x1400703b8  mov     eax, ebx
0x1400703ba  add     rsp, 38h
0x1400703be  pop     r15
0x1400703c0  pop     r14
0x1400703c2  pop     r13
0x1400703c4  pop     r12
0x1400703c6  pop     rdi
0x1400703c7  pop     rsi
0x1400703c8  pop     rbp
0x1400703c9  pop     rbx
0x1400703ca  retn
```
