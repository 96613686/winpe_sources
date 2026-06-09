# ExtSTAScan

- ea: `0x14001e830`
- end: `0x14001ecaf`
- name: `ExtSTAScan`
- size: `1151`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006a440`

## callees

- `0x14000a82c`
- `0x14000d22c`
- `0x140019bbc`
- `0x14001e830`
- `0x14001ecb8`
- `0x1400208f0`
- `0x140020dc0`
- `0x14005419c`
- `0x14005e4f8`
- `0x14006a950`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001e892`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001e892`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e930`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e930`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ec17`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ec17`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001ead7`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001ead7`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001eaf6`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001ebdb`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001eaf6`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001ebdb`
- `NDIS!NdisGetSystemUpTimeEx` at `0x14001e96b`
- `NDIS!NdisGetSystemUpTimeEx` at `0x14001e96b`

## pseudocode

```c
__int64 __fastcall ExtSTAScan(struct EXTSTA_VELAN *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  char *v9; // rax
  int v10; // r12d
  __int64 v11; // r15
  _LIST_ENTRY *v12; // r14
  int v13; // edi
  BOOL v14; // edi
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  int v17; // esi
  int started; // edi
  int v19; // ecx
  union _LARGE_INTEGER pSystemUpTime; // [rsp+70h] [rbp+18h] BYREF
  KIRQL Irql; // [rsp+78h] [rbp+20h] BYREF

  Irql = 0;
  if ( a4 < 4 || *(_DWORD *)a3 != 1 )
    return 3221225485LL;
  if ( a1->pGenVElan->MPDevicePowerState > NdisDeviceStateD0 )
    return 3223527426LL;
  v9 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue);
  if ( !v9 )
  {
    v13 = -1073741670;
LABEL_61:
    v19 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids,
        (unsigned int)v13);
    }
    if ( (Microsoft_Windows_NWiFiEnableBits & 0x40) != 0 )
      McTemplateK0pjq_EtwWriteTransfer(
        v19,
        (unsigned int)RejectScanRequest,
        &a1->pGenVElan->gDeviceId,
        a1->pGenVElan,
        (__int64)&a1->pGenVElan->gDeviceId,
        v13);
    return (unsigned int)v13;
  }
  *(_QWORD *)v9 = &WPP_MAIN_CB.DeviceQueue;
  v10 = a4 - 4;
  v11 = a3 + 4;
  *((_DWORD *)v9 + 2) = 1751741303;
  v12 = (_LIST_ENTRY *)(v9 + 16);
  v13 = Dot11ValidateV2ScanRequest((const struct _DOT11_SCAN_REQUEST_V2 *)(a3 + 4), a4 - 4);
  if ( v13 < 0 )
  {
LABEL_13:
    if ( v12 )
    {
      if ( v12[-1].Flink )
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v12[-1].Flink, &v12[-1]);
      else
        ExFreePoolWithTag(&v12[-1], (ULONG)v12[-1].Blink);
    }
    goto LABEL_61;
  }
  if ( a1->AssocMgr.bResumeRoamInProgress )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids);
    }
LABEL_12:
    v13 = -1071439871;
    goto LABEL_13;
  }
  if ( a1->bWaitingForIPv4Address )
  {
    if ( a1->bWaitingForIPv6Address )
    {
      pSystemUpTime.QuadPart = 0;
      NdisGetSystemUpTimeEx(&pSystemUpTime);
      if ( pSystemUpTime.QuadPart < a1->ullWaitingForIPTimeLimitMs )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids,
            a1->ullWaitingForIPTimeLimitMs - pSystemUpTime.QuadPart);
        }
        goto LABEL_12;
      }
    }
  }
  v14 = 0;
  _InterlockedExchange(&a1->bWaitingForIPv4Address, 0);
  _InterlockedExchange(&a1->bWaitingForIPv6Address, 0);
  if ( *(int *)(v11 + 12) < 0 )
  {
    if ( !_InterlockedExchange(&a1->AssocMgr.bResumeFailedRoamNotScan, 0) )
    {
      if ( !_InterlockedExchange(&a1->AssocMgr.bResumeNotAssocNotScan, 0) )
        goto LABEL_44;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids);
      }
      goto LABEL_51;
    }
    if ( (unsigned int)ExtSTACheckForDifferentLocationResume(a1) || a1->RoD.bAutoPowerSaveMode )
    {
      if ( *(_DWORD *)(v11 + 24) <= 1u )
      {
        v17 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids);
        }
        v14 = 1;
LABEL_43:
        _InterlockedExchange(&a1->AssocMgr.bResumeNotAssocNotScan, 0);
        if ( !v17 )
          goto LABEL_44;
LABEL_51:
        PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xE01017Au, 0, 0);
        goto LABEL_44;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
      {
LABEL_37:
        v17 = 1;
        goto LABEL_43;
      }
      v16 = 14;
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
      {
        goto LABEL_37;
      }
      v16 = 16;
    }
    WPP_SF_(v15->AttachedDevice, v16, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids);
    goto LABEL_37;
  }
  v14 = _InterlockedExchange(&a1->AssocMgr.Ignore1stAutoScanAfterResume, 0) != 0;
LABEL_44:
  IoAcquireCancelSpinLock(&Irql);
  if ( *(_BYTE *)(a2 + 68) )
  {
    v13 = -1073741536;
    IoReleaseCancelSpinLock(Irql);
    goto LABEL_13;
  }
  *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  v12->Flink = (_LIST_ENTRY *)a2;
  *(_QWORD *)(a2 + 120) = v12;
  _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)&ExtSTACancelIoctlScan);
  if ( v14 )
    started = 0;
  else
    started = Dot11StartScanV2(
                a1->pGenVElan->pAdapt,
                v10,
                (_LIST_ENTRY *)v11,
                (void (*)(struct _ADAPT *, int, struct _DOT11_SCAN_REQUEST_V2 *, void *, void *))ExtSTAIoctlScanCompletion,
                (struct _NDIS_EVENT *)a1,
                v12);
  IoReleaseCancelSpinLock(Irql);
  if ( started != 259 )
    ExtSTAIoctlScanCompletion(a1->pGenVElan->pAdapt, started, (struct _DOT11_SCAN_REQUEST_V2 *)v11, a1, (char *)v12);
  return 259;
}

```

## disassembly

```asm
0x14001e830  mov     [rsp+arg_0], rbx
0x14001e835  mov     [rsp+arg_8], rbp
0x14001e83a  push    rsi
0x14001e83b  push    rdi
0x14001e83c  push    r12
0x14001e83e  push    r14
0x14001e840  push    r15
0x14001e842  sub     rsp, 30h
0x14001e846  mov     [rsp+58h+Irql], 0
0x14001e84b  mov     esi, r9d
0x14001e84e  mov     rdi, r8
0x14001e851  mov     rbp, rdx
0x14001e854  mov     rbx, rcx
0x14001e857  cmp     r9d, 4
0x14001e85b  jb      loc_14001EC92
0x14001e861  mov     ecx, 1
0x14001e866  cmp     [r8], ecx
0x14001e869  jnz     loc_14001EC92
0x14001e86f  mov     rax, [rbx+0A38h]
0x14001e876  cmp     [rax+13F4h], ecx
0x14001e87c  jle     short loc_14001E888
0x14001e87e  mov     eax, 0C0232002h
0x14001e883  jmp     loc_14001EC97
0x14001e888  lea     r14, WPP_MAIN_CB.DeviceQueue
0x14001e88f  mov     rcx, r14; Lookaside
0x14001e892  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001e899  nop     dword ptr [rax+rax+00h]
0x14001e89e  test    rax, rax
0x14001e8a1  jz      loc_14001EC25
0x14001e8a7  mov     [rax], r14
0x14001e8aa  lea     r12d, [rsi-4]
0x14001e8ae  lea     r15, [rdi+4]
0x14001e8b2  mov     dword ptr [rax+8], 68697377h
0x14001e8b9  mov     edx, r12d; unsigned int
0x14001e8bc  lea     r14, [rax+10h]
0x14001e8c0  mov     rcx, r15; struct _DOT11_SCAN_REQUEST_V2 *
0x14001e8c3  call    ?Dot11ValidateV2ScanRequest@@YAJPEBU_DOT11_SCAN_REQUEST_V2@@K@Z; Dot11ValidateV2ScanRequest(_DOT11_SCAN_REQUEST_V2 const *,ulong)
0x14001e8c8  mov     edi, eax
0x14001e8ca  test    eax, eax
0x14001e8cc  js      short loc_14001E911
0x14001e8ce  cmp     dword ptr [rbx+328h], 0
0x14001e8d5  jz      short loc_14001E941
0x14001e8d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e8de  lea     rdx, WPP_GLOBAL_Control
0x14001e8e5  cmp     rcx, rdx
0x14001e8e8  jz      short loc_14001E90C
0x14001e8ea  cmp     byte ptr [rcx+29h], 2
0x14001e8ee  jb      short loc_14001E90C
0x14001e8f0  mov     eax, [rcx+2Ch]
0x14001e8f3  test    al, 10h
0x14001e8f5  jz      short loc_14001E90C
0x14001e8f7  mov     rcx, [rcx+18h]
0x14001e8fb  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14001e902  mov     edx, 0Ch
0x14001e907  call    WPP_SF_
0x14001e90c  mov     edi, 0C0232001h
0x14001e911  test    r14, r14
0x14001e914  jz      loc_14001EC2A
0x14001e91a  lea     rcx, [r14-10h]; P
0x14001e91e  mov     rax, [rcx]
0x14001e921  test    rax, rax
0x14001e924  jz      loc_14001EC14
0x14001e92a  mov     rdx, rcx; Entry
0x14001e92d  mov     rcx, rax; Lookaside
0x14001e930  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001e937  nop     dword ptr [rax+rax+00h]
0x14001e93c  jmp     loc_14001EC2A
0x14001e941  mov     eax, [rbx+0A60h]
0x14001e947  test    eax, eax
0x14001e949  jz      loc_14001E9DE
0x14001e94f  mov     eax, [rbx+0A64h]
0x14001e955  test    eax, eax
0x14001e957  jz      loc_14001E9DE
0x14001e95d  lea     rcx, [rsp+58h+pSystemUpTime]; pSystemUpTime
0x14001e962  mov     qword ptr [rsp+58h+pSystemUpTime], 0
0x14001e96b  call    cs:__imp_NdisGetSystemUpTimeEx
0x14001e972  nop     dword ptr [rax+rax+00h]
0x14001e977  mov     rax, [rbx+0A58h]
0x14001e97e  cmp     qword ptr [rsp+58h+pSystemUpTime], rax
0x14001e983  jnb     short loc_14001E9DE
0x14001e985  mov     rax, cs:WPP_GLOBAL_Control
0x14001e98c  lea     rdx, WPP_GLOBAL_Control
0x14001e993  cmp     rax, rdx
0x14001e996  jz      loc_14001E90C
0x14001e99c  cmp     byte ptr [rax+29h], 2
0x14001e9a0  jb      loc_14001E90C
0x14001e9a6  mov     eax, [rax+2Ch]
0x14001e9a9  test    al, 10h
0x14001e9ab  jz      loc_14001E90C
0x14001e9b1  mov     r9, [rbx+0A58h]
0x14001e9b8  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14001e9bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e9c6  mov     edx, 0Dh
0x14001e9cb  sub     r9, qword ptr [rsp+58h+pSystemUpTime]
0x14001e9d0  mov     rcx, [rcx+18h]
0x14001e9d4  call    WPP_SF_q
0x14001e9d9  jmp     loc_14001E90C
0x14001e9de  xor     eax, eax
0x14001e9e0  xor     edi, edi
0x14001e9e2  xchg    eax, [rbx+0A60h]
0x14001e9e8  xor     eax, eax
0x14001e9ea  xchg    eax, [rbx+0A64h]
0x14001e9f0  xor     eax, eax
0x14001e9f2  cmp     [r15+0Ch], edi
0x14001e9f6  jge     loc_14001EB74
0x14001e9fc  xchg    eax, [rbx+320h]
0x14001ea02  test    eax, eax
0x14001ea04  jz      loc_14001EB07
0x14001ea0a  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14001ea0d  call    ?ExtSTACheckForDifferentLocationResume@@YAHPEAUEXTSTA_VELAN@@@Z; ExtSTACheckForDifferentLocationResume(EXTSTA_VELAN *)
0x14001ea12  test    eax, eax
0x14001ea14  jnz     short loc_14001EA44
0x14001ea16  cmp     [rbx+6A8h], dil
0x14001ea1d  jnz     short loc_14001EA44
0x14001ea1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ea26  lea     rdx, WPP_GLOBAL_Control
0x14001ea2d  cmp     rcx, rdx
0x14001ea30  jz      short loc_14001EA80
0x14001ea32  cmp     byte ptr [rcx+29h], 2
0x14001ea36  jb      short loc_14001EA80
0x14001ea38  mov     eax, [rcx+2Ch]
0x14001ea3b  test    al, 10h
0x14001ea3d  jz      short loc_14001EA80
0x14001ea3f  lea     edx, [rdi+10h]
0x14001ea42  jmp     short loc_14001EA70
0x14001ea44  cmp     dword ptr [r15+18h], 1
0x14001ea49  jbe     short loc_14001EA87
0x14001ea4b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ea52  lea     rdx, WPP_GLOBAL_Control
0x14001ea59  cmp     rcx, rdx
0x14001ea5c  jz      short loc_14001EA80
0x14001ea5e  cmp     byte ptr [rcx+29h], 2
0x14001ea62  jb      short loc_14001EA80
0x14001ea64  mov     eax, [rcx+2Ch]
0x14001ea67  test    al, 10h
0x14001ea69  jz      short loc_14001EA80
0x14001ea6b  mov     edx, 0Eh
0x14001ea70  mov     rcx, [rcx+18h]
0x14001ea74  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14001ea7b  call    WPP_SF_
0x14001ea80  mov     esi, 1
0x14001ea85  jmp     short loc_14001EAC1
0x14001ea87  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ea8e  lea     rdx, WPP_GLOBAL_Control
0x14001ea95  xor     esi, esi
0x14001ea97  cmp     rcx, rdx
0x14001ea9a  jz      short loc_14001EABC
0x14001ea9c  cmp     byte ptr [rcx+29h], 2
0x14001eaa0  jb      short loc_14001EABC
0x14001eaa2  mov     eax, [rcx+2Ch]
0x14001eaa5  test    al, 10h
0x14001eaa7  jz      short loc_14001EABC
0x14001eaa9  mov     rcx, [rcx+18h]
0x14001eaad  lea     edx, [rsi+0Fh]
0x14001eab0  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14001eab7  call    WPP_SF_
0x14001eabc  mov     edi, 1
0x14001eac1  xor     eax, eax
0x14001eac3  xchg    eax, [rbx+324h]
0x14001eac9  test    esi, esi
0x14001eacb  jnz     short loc_14001EB48
0x14001eacd  mov     esi, 1
0x14001ead2  lea     rcx, [rsp+58h+Irql]; Irql
0x14001ead7  call    cs:__imp_IoAcquireCancelSpinLock
0x14001eade  nop     dword ptr [rax+rax+00h]
0x14001eae3  cmp     byte ptr [rbp+44h], 0
0x14001eae7  jz      loc_14001EB89
0x14001eaed  mov     edi, 0C0000120h
0x14001eaf2  mov     cl, [rsp+58h+Irql]; Irql
0x14001eaf6  call    cs:__imp_IoReleaseCancelSpinLock
0x14001eafd  nop     dword ptr [rax+rax+00h]
0x14001eb02  jmp     loc_14001E911
0x14001eb07  xor     eax, eax
0x14001eb09  xchg    eax, [rbx+324h]
0x14001eb0f  test    eax, eax
0x14001eb11  jz      short loc_14001EACD
0x14001eb13  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb1a  lea     rdx, WPP_GLOBAL_Control
0x14001eb21  cmp     rcx, rdx
0x14001eb24  jz      short loc_14001EB48
0x14001eb26  cmp     byte ptr [rcx+29h], 2
0x14001eb2a  jb      short loc_14001EB48
0x14001eb2c  mov     eax, [rcx+2Ch]
0x14001eb2f  test    al, 10h
0x14001eb31  jz      short loc_14001EB48
0x14001eb33  mov     rcx, [rcx+18h]
0x14001eb37  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14001eb3e  mov     edx, 11h
0x14001eb43  call    WPP_SF_
0x14001eb48  mov     rcx, [rbx+0A38h]
0x14001eb4f  xor     r9d, r9d; void *
0x14001eb52  mov     r8d, 0E01017Ah; unsigned int
0x14001eb58  mov     dword ptr [rsp+58h+var_38], 0; unsigned int
0x14001eb60  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14001eb64  lea     esi, [r9+1]
0x14001eb68  mov     edx, esi; unsigned int
0x14001eb6a  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14001eb6f  jmp     loc_14001EAD2
0x14001eb74  xchg    eax, [rbx+334h]
0x14001eb7a  test    eax, eax
0x14001eb7c  mov     esi, 1
0x14001eb81  cmovnz  edi, esi
0x14001eb84  jmp     loc_14001EAD2
0x14001eb89  mov     rax, [rbp+0B8h]
0x14001eb90  or      [rax+3], sil
0x14001eb94  lea     rax, ExtSTACancelIoctlScan
0x14001eb9b  mov     [r14], rbp
0x14001eb9e  mov     [rbp+78h], r14
0x14001eba2  xchg    rax, [rbp+68h]
0x14001eba6  test    edi, edi
0x14001eba8  jnz     short loc_14001EBD5
0x14001ebaa  mov     rcx, [rbx+0A38h]
0x14001ebb1  lea     r9, ExtSTAIoctlScanCompletion; void (*)(struct _ADAPT *, int, struct _DOT11_SCAN_REQUEST_V2 *, void *, void *)
0x14001ebb8  mov     [rsp+58h+var_30], r14; void *
0x14001ebbd  mov     r8, r15; struct _DOT11_SCAN_REQUEST_V2 *
0x14001ebc0  mov     edx, r12d; unsigned int
0x14001ebc3  mov     [rsp+58h+var_38], rbx; void *
0x14001ebc8  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14001ebcc  call    ?Dot11StartScanV2@@YAHPEAU_ADAPT@@KPEAU_DOT11_SCAN_REQUEST_V2@@P6AX0H1PEAX2@Z22@Z; Dot11StartScanV2(_ADAPT *,ulong,_DOT11_SCAN_REQUEST_V2 *,void (*)(_ADAPT *,int,_DOT11_SCAN_REQUEST_V2 *,void *,void *),void *,void *)
0x14001ebd1  mov     edi, eax
0x14001ebd3  jmp     short loc_14001EBD7
0x14001ebd5  xor     edi, edi
0x14001ebd7  mov     cl, [rsp+58h+Irql]; Irql
0x14001ebdb  call    cs:__imp_IoReleaseCancelSpinLock
0x14001ebe2  nop     dword ptr [rax+rax+00h]
0x14001ebe7  mov     esi, 103h
0x14001ebec  cmp     edi, esi
0x14001ebee  jz      short loc_14001EC0D
0x14001ebf0  mov     rcx, [rbx+0A38h]
0x14001ebf7  mov     r9, rbx; void *
0x14001ebfa  mov     r8, r15; struct _DOT11_SCAN_REQUEST_V2 *
0x14001ebfd  mov     [rsp+58h+var_38], r14; void *
0x14001ec02  mov     edx, edi; int
0x14001ec04  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14001ec08  call    ExtSTAIoctlScanCompletion
0x14001ec0d  mov     eax, esi
0x14001ec0f  jmp     loc_14001EC97
0x14001ec14  mov     edx, [rcx+8]; Tag
0x14001ec17  call    cs:__imp_ExFreePoolWithTag
0x14001ec1e  nop     dword ptr [rax+rax+00h]
0x14001ec23  jmp     short loc_14001EC2A
0x14001ec25  mov     edi, 0C000009Ah
0x14001ec2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ec31  lea     rax, WPP_GLOBAL_Control
0x14001ec38  cmp     rcx, rax
0x14001ec3b  jz      short loc_14001EC62
0x14001ec3d  cmp     byte ptr [rcx+29h], 2
0x14001ec41  jb      short loc_14001EC62
0x14001ec43  mov     eax, [rcx+2Ch]
0x14001ec46  test    al, 10h
0x14001ec48  jz      short loc_14001EC62
0x14001ec4a  mov     rcx, [rcx+18h]
0x14001ec4e  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14001ec55  mov     edx, 12h
0x14001ec5a  mov     r9d, edi
0x14001ec5d  call    WPP_SF_d
0x14001ec62  test    cs:Microsoft_Windows_NWiFiEnableBits, 40h
0x14001ec69  jz      short loc_14001EC8E
0x14001ec6b  mov     r9, [rbx+0A38h]
0x14001ec72  lea     rdx, RejectScanRequest
0x14001ec79  mov     dword ptr [rsp+58h+var_30], edi
0x14001ec7d  lea     r8, [r9+1338h]
0x14001ec84  mov     [rsp+58h+var_38], r8
0x14001ec89  call    McTemplateK0pjq_EtwWriteTransfer
0x14001ec8e  mov     eax, edi
0x14001ec90  jmp     short loc_14001EC97
0x14001ec92  mov     eax, 0C000000Dh
0x14001ec97  mov     rbx, [rsp+58h+arg_0]
0x14001ec9c  mov     rbp, [rsp+58h+arg_8]
0x14001eca1  add     rsp, 30h
0x14001eca5  pop     r15
0x14001eca7  pop     r14
0x14001eca9  pop     r12
0x14001ecab  pop     rdi
0x14001ecac  pop     rsi
0x14001ecad  retn
```
