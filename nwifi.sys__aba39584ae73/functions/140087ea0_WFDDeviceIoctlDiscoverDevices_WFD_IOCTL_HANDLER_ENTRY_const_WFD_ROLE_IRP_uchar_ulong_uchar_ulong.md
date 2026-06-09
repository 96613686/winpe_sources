# WFDDeviceIoctlDiscoverDevices(_WFD_IOCTL_HANDLER_ENTRY const *,_WFD_ROLE *,_IRP *,uchar *,ulong,uchar *,ulong *)

- ea: `0x140087ea0`
- end: `0x1400881db`
- name: `?WFDDeviceIoctlDiscoverDevices@@YAHPEBU_WFD_IOCTL_HANDLER_ENTRY@@PEAU_WFD_ROLE@@PEAU_IRP@@PEAEK3PEAK@Z`
- size: `827`
- prototype: `__int64 __fastcall(const struct _WFD_IOCTL_HANDLER_ENTRY *, struct _WFD_ROLE *, _LIST_ENTRY *, struct _DOT11_WFD_DISCOVER_REQUEST_V2 *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14000a81c`
- `0x14000d21c`
- `0x140020dc0`
- `0x140056634`
- `0x1400568b4`
- `0x14007a244`
- `0x140087ea0`
- `0x14008be10`
- `0x14008e91c`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140087f52`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140087f52`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008807f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088143`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008807f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088143`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008811d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088154`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008811d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088154`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140088025`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140088025`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140088040`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400880db`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140088040`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400880db`

## pseudocode

```c
__int64 __fastcall WFDDeviceIoctlDiscoverDevices(
        const struct _WFD_IOCTL_HANDLER_ENTRY *a1,
        struct _WFD_ROLE *a2,
        _LIST_ENTRY *a3,
        struct _DOT11_WFD_DISCOVER_REQUEST_V2 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int *a7)
{
  _VELAN *pGenVElan; // rax
  unsigned int v12; // r12d
  char *v13; // rax
  unsigned int *v14; // r13
  _LIST_ENTRY *v15; // rbx
  int v16; // edi
  struct _DOT11_WFD_DISCOVER_REQUEST_V2 *v17; // rcx
  void (*v18)(struct _ADAPT *, int, struct DOT11_BYTE_ARRAY *, struct _DOT11_WFD_DISCOVER_REQUEST_V2 *, void *, void *); // r9
  _LIST_ENTRY *Blink; // rcx
  _LIST_ENTRY *v20; // rcx
  unsigned __int8 *v21; // rax
  int v22; // edi
  int v23; // ecx
  unsigned int v24; // [rsp+50h] [rbp-18h] BYREF
  struct _DOT11_WFD_DISCOVER_REQUEST_V2 *v25; // [rsp+58h] [rbp-10h] BYREF
  KIRQL Irql; // [rsp+B8h] [rbp+50h] BYREF

  pGenVElan = a2->pGenVElan;
  v25 = 0;
  Irql = 0;
  v24 = 0;
  if ( pGenVElan->MPDevicePowerState > NdisDeviceStateD0 )
    return 3223527426LL;
  v12 = a5;
  v24 = a5;
  v25 = a4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_qDDDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      a3,
      *((_DWORD *)a4 + 1),
      *((_DWORD *)a4 + 2),
      *((_DWORD *)a4 + 3),
      *((_DWORD *)a4 + 5),
      *((_DWORD *)a4 + 7),
      *((unsigned __int8 *)a4 + 32));
  }
  v13 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue);
  if ( !v13 )
  {
    v16 = -1073741670;
LABEL_33:
    v23 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        30,
        WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
        (unsigned int)v16);
    }
    if ( (Microsoft_Windows_NWiFiEnableBits & 0x40) != 0 )
      McTemplateK0pjq_EtwWriteTransfer(
        v23,
        (unsigned int)RejectScanRequest,
        &a2->pGenVElan->gDeviceId,
        a2->pGenVElan,
        (__int64)&a2->pGenVElan->gDeviceId,
        v16);
    return (unsigned int)v16;
  }
  v14 = a7;
  v15 = (_LIST_ENTRY *)(v13 + 16);
  *(_QWORD *)v13 = &WPP_MAIN_CB.DeviceQueue;
  *((_DWORD *)v13 + 2) = 879326071;
  *((_OWORD *)v13 + 1) = 0;
  *((_OWORD *)v13 + 2) = 0;
  v16 = WFDValidateDiscoverRequest(v25, v24, v14);
  if ( v16 < 0 )
    goto LABEL_19;
  if ( *((_DWORD *)v25 + 7) )
  {
    v16 = WFDRoleAddCachedIEsToDiscoverRequestOidStructure(a2, v25, v12, &v25, &v24);
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_19;
    }
    v15[1].Blink = (_LIST_ENTRY *)v25;
    v17 = v25;
    if ( v25 )
    {
      v12 = v24;
    }
    else
    {
      v17 = a4;
      v24 = v12;
      v25 = a4;
    }
    v16 = WFDValidateDiscoverRequest(v17, v12, v14);
    if ( v16 < 0 )
    {
LABEL_19:
      if ( v15 )
      {
        Blink = v15[1].Blink;
        if ( Blink )
        {
          v20 = Blink - 1;
          if ( v20->Flink )
            ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v20->Flink, v20);
          else
            ExFreePoolWithTag(v20, (ULONG)v20->Blink);
          v15[1].Blink = 0;
        }
        if ( v15[-1].Flink )
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v15[-1].Flink, &v15[-1]);
        else
          ExFreePoolWithTag(&v15[-1], (ULONG)v15[-1].Blink);
      }
      goto LABEL_33;
    }
  }
  IoAcquireCancelSpinLock(&Irql);
  if ( BYTE4(a3[4].Flink) )
  {
    v16 = -1073741536;
    IoReleaseCancelSpinLock(Irql);
    goto LABEL_19;
  }
  BYTE3(a3[11].Blink->Flink) |= 1u;
  v21 = a6;
  v15->Flink = a3;
  v15->Blink = (_LIST_ENTRY *)v21;
  v15[1].Flink = (_LIST_ENTRY *)v14;
  a3[7].Blink = v15;
  _InterlockedExchange64((volatile __int64 *)&a3[6].Blink, (__int64)&WFDCancelIoctlDiscover);
  v22 = WFDStartDiscovery(a2->pGenVElan->pAdapt, v24, v25, v18, a2, v15);
  IoReleaseCancelSpinLock(Irql);
  if ( v22 != 259 && v22 )
    WFDIoctlDiscoverCompletion(a2->pGenVElan->pAdapt, v22, 0, (_DWORD)v25, (_DWORD)a2, (__int64)v15);
  return 259;
}

```

## disassembly

```asm
0x140087ea0  push    rbp
0x140087ea2  push    rbx
0x140087ea3  push    rsi
0x140087ea4  push    rdi
0x140087ea5  push    r12
0x140087ea7  push    r13
0x140087ea9  push    r14
0x140087eab  push    r15
0x140087ead  mov     rbp, rsp
0x140087eb0  sub     rsp, 68h
0x140087eb4  mov     rax, [rdx]
0x140087eb7  xor     ebx, ebx
0x140087eb9  mov     [rbp+var_10], rbx
0x140087ebd  mov     rsi, r9
0x140087ec0  mov     [rbp+Irql], bl
0x140087ec3  mov     r15, r8
0x140087ec6  mov     [rbp+var_18], ebx
0x140087ec9  mov     r14, rdx
0x140087ecc  cmp     dword ptr [rax+13F4h], 1
0x140087ed3  jle     short loc_140087EDF
0x140087ed5  mov     eax, 0C0232002h
0x140087eda  jmp     loc_1400881C9
0x140087edf  mov     r12d, [rbp+arg_20]
0x140087ee3  mov     [rbp+var_18], r12d
0x140087ee7  mov     [rbp+var_10], rsi
0x140087eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x140087ef2  lea     rax, WPP_GLOBAL_Control
0x140087ef9  cmp     rcx, rax
0x140087efc  jz      short loc_140087F48
0x140087efe  cmp     byte ptr [rcx+29h], 4
0x140087f02  jb      short loc_140087F48
0x140087f04  mov     eax, [rcx+2Ch]
0x140087f07  test    al, 10h
0x140087f09  jz      short loc_140087F48
0x140087f0b  movzx   eax, byte ptr [r9+20h]
0x140087f10  mov     rcx, [rcx+18h]
0x140087f14  mov     [rsp+68h+var_20], eax
0x140087f18  mov     eax, [r9+1Ch]
0x140087f1c  mov     [rsp+68h+var_28], eax
0x140087f20  mov     eax, [r9+14h]
0x140087f24  mov     [rsp+68h+var_30], eax
0x140087f28  mov     eax, [r9+0Ch]
0x140087f2c  mov     [rsp+68h+var_38], eax
0x140087f30  mov     eax, [r9+8]
0x140087f34  mov     dword ptr [rsp+68h+var_40], eax
0x140087f38  mov     eax, [r9+4]
0x140087f3c  mov     r9, r15
0x140087f3f  mov     dword ptr [rsp+68h+var_48], eax
0x140087f43  call    WPP_SF_qDDDDDD
0x140087f48  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x140087f4f  mov     rcx, rdi; Lookaside
0x140087f52  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140087f59  nop     dword ptr [rax+rax+00h]
0x140087f5e  test    rax, rax
0x140087f61  jz      loc_140088162
0x140087f67  mov     r13, [rbp+arg_30]
0x140087f6b  lea     rbx, [rax+10h]
0x140087f6f  mov     [rax], rdi
0x140087f72  xorps   xmm0, xmm0
0x140087f75  mov     dword ptr [rax+8], 34697377h
0x140087f7c  mov     r8, r13; unsigned int *
0x140087f7f  movups  xmmword ptr [rbx], xmm0
0x140087f82  movups  xmmword ptr [rbx+10h], xmm0
0x140087f86  mov     edx, [rbp+var_18]; unsigned int
0x140087f89  mov     rcx, [rbp+var_10]; struct _DOT11_WFD_DISCOVER_REQUEST_V2 *
0x140087f8d  call    ?WFDValidateDiscoverRequest@@YAJQEAU_DOT11_WFD_DISCOVER_REQUEST_V2@@KPEAK@Z; WFDValidateDiscoverRequest(_DOT11_WFD_DISCOVER_REQUEST_V2 * const,ulong,ulong *)
0x140087f92  mov     edi, eax
0x140087f94  test    eax, eax
0x140087f96  js      loc_14008804C
0x140087f9c  mov     rdx, [rbp+var_10]; struct _DOT11_WFD_DISCOVER_REQUEST_V2 *
0x140087fa0  cmp     dword ptr [rdx+1Ch], 0
0x140087fa4  jbe     short loc_140088021
0x140087fa6  lea     rax, [rbp+var_18]
0x140087faa  mov     r8d, r12d; unsigned int
0x140087fad  lea     r9, [rbp+var_10]; struct _DOT11_WFD_DISCOVER_REQUEST_V2 **
0x140087fb1  mov     [rsp+68h+var_48], rax; unsigned int *
0x140087fb6  mov     rcx, r14; struct _WFD_ROLE *
0x140087fb9  call    ?WFDRoleAddCachedIEsToDiscoverRequestOidStructure@@YAKPEAU_WFD_ROLE@@PEAU_DOT11_WFD_DISCOVER_REQUEST_V2@@KPEAPEAU2@PEAK@Z; WFDRoleAddCachedIEsToDiscoverRequestOidStructure(_WFD_ROLE *,_DOT11_WFD_DISCOVER_REQUEST_V2 *,ulong,_DOT11_WFD_DISCOVER_REQUEST_V2 * *,ulong *)
0x140087fbe  mov     edi, eax
0x140087fc0  test    eax, eax
0x140087fc2  jz      short loc_140087FEE
0x140087fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140087fcb  lea     rsi, WPP_GLOBAL_Control
0x140087fd2  cmp     rcx, rsi
0x140087fd5  jz      short loc_140088053
0x140087fd7  mov     rcx, [rcx+18h]
0x140087fdb  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140087fe2  mov     edx, 1Dh
0x140087fe7  call    WPP_SF_
0x140087fec  jmp     short loc_140088053
0x140087fee  mov     rax, [rbp+var_10]
0x140087ff2  mov     [rbx+18h], rax
0x140087ff6  mov     rcx, [rbp+var_10]; struct _DOT11_WFD_DISCOVER_REQUEST_V2 *
0x140087ffa  test    rcx, rcx
0x140087ffd  jnz     short loc_14008800C
0x140087fff  mov     rcx, rsi
0x140088002  mov     [rbp+var_18], r12d
0x140088006  mov     [rbp+var_10], rcx
0x14008800a  jmp     short loc_140088010
0x14008800c  mov     r12d, [rbp+var_18]
0x140088010  mov     r8, r13; unsigned int *
0x140088013  mov     edx, r12d; unsigned int
0x140088016  call    ?WFDValidateDiscoverRequest@@YAJQEAU_DOT11_WFD_DISCOVER_REQUEST_V2@@KPEAK@Z; WFDValidateDiscoverRequest(_DOT11_WFD_DISCOVER_REQUEST_V2 * const,ulong,ulong *)
0x14008801b  mov     edi, eax
0x14008801d  test    eax, eax
0x14008801f  js      short loc_14008804C
0x140088021  lea     rcx, [rbp+Irql]; Irql
0x140088025  call    cs:__imp_IoAcquireCancelSpinLock
0x14008802c  nop     dword ptr [rax+rax+00h]
0x140088031  cmp     byte ptr [r15+44h], 0
0x140088036  jz      short loc_140088090
0x140088038  mov     edi, 0C0000120h
0x14008803d  mov     cl, [rbp+Irql]; Irql
0x140088040  call    cs:__imp_IoReleaseCancelSpinLock
0x140088047  nop     dword ptr [rax+rax+00h]
0x14008804c  lea     rsi, WPP_GLOBAL_Control
0x140088053  test    rbx, rbx
0x140088056  jz      loc_14008816E
0x14008805c  mov     rcx, [rbx+18h]
0x140088060  test    rcx, rcx
0x140088063  jz      loc_140088131
0x140088069  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14008806d  mov     rax, [rcx]
0x140088070  test    rax, rax
0x140088073  jz      loc_14008811A
0x140088079  mov     rdx, rcx; Entry
0x14008807c  mov     rcx, rax; Lookaside
0x14008807f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140088086  nop     dword ptr [rax+rax+00h]
0x14008808b  jmp     loc_140088129
0x140088090  mov     rax, [r15+0B8h]
0x140088097  mov     [rsp+68h+var_40], rbx; void *
0x14008809c  mov     [rsp+68h+var_48], r14; void *
0x1400880a1  or      byte ptr [rax+3], 1
0x1400880a5  mov     rax, [rbp+arg_28]
0x1400880a9  mov     [rbx], r15
0x1400880ac  mov     [rbx+8], rax
0x1400880b0  lea     rax, WFDCancelIoctlDiscover
0x1400880b7  mov     [rbx+10h], r13
0x1400880bb  mov     [r15+78h], rbx
0x1400880bf  xchg    rax, [r15+68h]
0x1400880c3  mov     rcx, [r14]
0x1400880c6  mov     r8, [rbp+var_10]; struct _DOT11_WFD_DISCOVER_REQUEST_V2 *
0x1400880ca  mov     edx, [rbp+var_18]; unsigned int
0x1400880cd  mov     rcx, [rcx+10h]; struct _ADAPT *
0x1400880d1  call    ?WFDStartDiscovery@@YAHPEAU_ADAPT@@KPEAU_DOT11_WFD_DISCOVER_REQUEST_V2@@P6AX0HPEAUDOT11_BYTE_ARRAY@@1PEAX3@Z33@Z; WFDStartDiscovery(_ADAPT *,ulong,_DOT11_WFD_DISCOVER_REQUEST_V2 *,void (*)(_ADAPT *,int,DOT11_BYTE_ARRAY *,_DOT11_WFD_DISCOVER_REQUEST_V2 *,void *,void *),void *,void *)
0x1400880d6  mov     cl, [rbp+Irql]; Irql
0x1400880d9  mov     edi, eax
0x1400880db  call    cs:__imp_IoReleaseCancelSpinLock
0x1400880e2  nop     dword ptr [rax+rax+00h]
0x1400880e7  mov     esi, 103h
0x1400880ec  cmp     edi, esi
0x1400880ee  jz      short loc_140088113
0x1400880f0  test    edi, edi
0x1400880f2  jz      short loc_140088113
0x1400880f4  mov     rcx, [r14]
0x1400880f7  xor     r8d, r8d
0x1400880fa  mov     r9, [rbp+var_10]
0x1400880fe  mov     edx, edi
0x140088100  mov     [rsp+68h+var_40], rbx
0x140088105  mov     [rsp+68h+var_48], r14
0x14008810a  mov     rcx, [rcx+10h]
0x14008810e  call    WFDIoctlDiscoverCompletion
0x140088113  mov     eax, esi
0x140088115  jmp     loc_1400881C9
0x14008811a  mov     edx, [rcx+8]; Tag
0x14008811d  call    cs:__imp_ExFreePoolWithTag
0x140088124  nop     dword ptr [rax+rax+00h]
0x140088129  mov     qword ptr [rbx+18h], 0
0x140088131  lea     rcx, [rbx-10h]; P
0x140088135  mov     rax, [rcx]
0x140088138  test    rax, rax
0x14008813b  jz      short loc_140088151
0x14008813d  mov     rdx, rcx; Entry
0x140088140  mov     rcx, rax; Lookaside
0x140088143  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008814a  nop     dword ptr [rax+rax+00h]
0x14008814f  jmp     short loc_14008816E
0x140088151  mov     edx, [rcx+8]; Tag
0x140088154  call    cs:__imp_ExFreePoolWithTag
0x14008815b  nop     dword ptr [rax+rax+00h]
0x140088160  jmp     short loc_14008816E
0x140088162  mov     edi, 0C000009Ah
0x140088167  lea     rsi, WPP_GLOBAL_Control
0x14008816e  mov     rcx, cs:WPP_GLOBAL_Control
0x140088175  cmp     rcx, rsi
0x140088178  jz      short loc_14008819F
0x14008817a  cmp     byte ptr [rcx+29h], 1
0x14008817e  jb      short loc_14008819F
0x140088180  mov     eax, [rcx+2Ch]
0x140088183  test    al, 10h
0x140088185  jz      short loc_14008819F
0x140088187  mov     rcx, [rcx+18h]
0x14008818b  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140088192  mov     edx, 1Eh
0x140088197  mov     r9d, edi
0x14008819a  call    WPP_SF_d
0x14008819f  test    cs:Microsoft_Windows_NWiFiEnableBits, 40h
0x1400881a6  jz      short loc_1400881C7
0x1400881a8  mov     r9, [r14]
0x1400881ab  lea     rdx, RejectScanRequest
0x1400881b2  mov     dword ptr [rsp+68h+var_40], edi
0x1400881b6  lea     r8, [r9+1338h]
0x1400881bd  mov     [rsp+68h+var_48], r8
0x1400881c2  call    McTemplateK0pjq_EtwWriteTransfer
0x1400881c7  mov     eax, edi
0x1400881c9  add     rsp, 68h
0x1400881cd  pop     r15
0x1400881cf  pop     r14
0x1400881d1  pop     r13
0x1400881d3  pop     r12
0x1400881d5  pop     rdi
0x1400881d6  pop     rsi
0x1400881d7  pop     rbx
0x1400881d8  pop     rbp
0x1400881d9  retn
```
