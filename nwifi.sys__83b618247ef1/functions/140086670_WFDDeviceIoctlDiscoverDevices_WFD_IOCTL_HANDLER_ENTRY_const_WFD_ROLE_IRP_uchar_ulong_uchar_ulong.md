# WFDDeviceIoctlDiscoverDevices(_WFD_IOCTL_HANDLER_ENTRY const *,_WFD_ROLE *,_IRP *,uchar *,ulong,uchar *,ulong *)

- ea: `0x140086670`
- end: `0x1400869ab`
- name: `?WFDDeviceIoctlDiscoverDevices@@YAHPEBU_WFD_IOCTL_HANDLER_ENTRY@@PEAU_WFD_ROLE@@PEAU_IRP@@PEAEK3PEAK@Z`
- size: `827`
- prototype: `__int64 __fastcall(const struct _WFD_IOCTL_HANDLER_ENTRY *, struct _WFD_ROLE *, _LIST_ENTRY *, struct _DOT11_WFD_DISCOVER_REQUEST_V2 *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14000a82c`
- `0x14000d22c`
- `0x140020dc0`
- `0x140054e14`
- `0x140055094`
- `0x140078a14`
- `0x140086670`
- `0x14008a5e0`
- `0x14008d0ec`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140086722`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140086722`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008684f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086913`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008684f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086913`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400868ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086924`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400868ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086924`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400867f5`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400867f5`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140086810`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400868ab`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140086810`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400868ab`

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
0x140086670  push    rbp
0x140086672  push    rbx
0x140086673  push    rsi
0x140086674  push    rdi
0x140086675  push    r12
0x140086677  push    r13
0x140086679  push    r14
0x14008667b  push    r15
0x14008667d  mov     rbp, rsp
0x140086680  sub     rsp, 68h
0x140086684  mov     rax, [rdx]
0x140086687  xor     ebx, ebx
0x140086689  mov     [rbp+var_10], rbx
0x14008668d  mov     rsi, r9
0x140086690  mov     [rbp+Irql], bl
0x140086693  mov     r15, r8
0x140086696  mov     [rbp+var_18], ebx
0x140086699  mov     r14, rdx
0x14008669c  cmp     dword ptr [rax+13F4h], 1
0x1400866a3  jle     short loc_1400866AF
0x1400866a5  mov     eax, 0C0232002h
0x1400866aa  jmp     loc_140086999
0x1400866af  mov     r12d, [rbp+arg_20]
0x1400866b3  mov     [rbp+var_18], r12d
0x1400866b7  mov     [rbp+var_10], rsi
0x1400866bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400866c2  lea     rax, WPP_GLOBAL_Control
0x1400866c9  cmp     rcx, rax
0x1400866cc  jz      short loc_140086718
0x1400866ce  cmp     byte ptr [rcx+29h], 4
0x1400866d2  jb      short loc_140086718
0x1400866d4  mov     eax, [rcx+2Ch]
0x1400866d7  test    al, 10h
0x1400866d9  jz      short loc_140086718
0x1400866db  movzx   eax, byte ptr [r9+20h]
0x1400866e0  mov     rcx, [rcx+18h]
0x1400866e4  mov     [rsp+68h+var_20], eax
0x1400866e8  mov     eax, [r9+1Ch]
0x1400866ec  mov     [rsp+68h+var_28], eax
0x1400866f0  mov     eax, [r9+14h]
0x1400866f4  mov     [rsp+68h+var_30], eax
0x1400866f8  mov     eax, [r9+0Ch]
0x1400866fc  mov     [rsp+68h+var_38], eax
0x140086700  mov     eax, [r9+8]
0x140086704  mov     dword ptr [rsp+68h+var_40], eax
0x140086708  mov     eax, [r9+4]
0x14008670c  mov     r9, r15
0x14008670f  mov     dword ptr [rsp+68h+var_48], eax
0x140086713  call    WPP_SF_qDDDDDD
0x140086718  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14008671f  mov     rcx, rdi; Lookaside
0x140086722  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140086729  nop     dword ptr [rax+rax+00h]
0x14008672e  test    rax, rax
0x140086731  jz      loc_140086932
0x140086737  mov     r13, [rbp+arg_30]
0x14008673b  lea     rbx, [rax+10h]
0x14008673f  mov     [rax], rdi
0x140086742  xorps   xmm0, xmm0
0x140086745  mov     dword ptr [rax+8], 34697377h
0x14008674c  mov     r8, r13; unsigned int *
0x14008674f  movups  xmmword ptr [rbx], xmm0
0x140086752  movups  xmmword ptr [rbx+10h], xmm0
0x140086756  mov     edx, [rbp+var_18]; unsigned int
0x140086759  mov     rcx, [rbp+var_10]; struct _DOT11_WFD_DISCOVER_REQUEST_V2 *
0x14008675d  call    ?WFDValidateDiscoverRequest@@YAJQEAU_DOT11_WFD_DISCOVER_REQUEST_V2@@KPEAK@Z; WFDValidateDiscoverRequest(_DOT11_WFD_DISCOVER_REQUEST_V2 * const,ulong,ulong *)
0x140086762  mov     edi, eax
0x140086764  test    eax, eax
0x140086766  js      loc_14008681C
0x14008676c  mov     rdx, [rbp+var_10]; struct _DOT11_WFD_DISCOVER_REQUEST_V2 *
0x140086770  cmp     dword ptr [rdx+1Ch], 0
0x140086774  jbe     short loc_1400867F1
0x140086776  lea     rax, [rbp+var_18]
0x14008677a  mov     r8d, r12d; unsigned int
0x14008677d  lea     r9, [rbp+var_10]; struct _DOT11_WFD_DISCOVER_REQUEST_V2 **
0x140086781  mov     [rsp+68h+var_48], rax; unsigned int *
0x140086786  mov     rcx, r14; struct _WFD_ROLE *
0x140086789  call    ?WFDRoleAddCachedIEsToDiscoverRequestOidStructure@@YAKPEAU_WFD_ROLE@@PEAU_DOT11_WFD_DISCOVER_REQUEST_V2@@KPEAPEAU2@PEAK@Z; WFDRoleAddCachedIEsToDiscoverRequestOidStructure(_WFD_ROLE *,_DOT11_WFD_DISCOVER_REQUEST_V2 *,ulong,_DOT11_WFD_DISCOVER_REQUEST_V2 * *,ulong *)
0x14008678e  mov     edi, eax
0x140086790  test    eax, eax
0x140086792  jz      short loc_1400867BE
0x140086794  mov     rcx, cs:WPP_GLOBAL_Control
0x14008679b  lea     rsi, WPP_GLOBAL_Control
0x1400867a2  cmp     rcx, rsi
0x1400867a5  jz      short loc_140086823
0x1400867a7  mov     rcx, [rcx+18h]
0x1400867ab  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400867b2  mov     edx, 1Dh
0x1400867b7  call    WPP_SF_
0x1400867bc  jmp     short loc_140086823
0x1400867be  mov     rax, [rbp+var_10]
0x1400867c2  mov     [rbx+18h], rax
0x1400867c6  mov     rcx, [rbp+var_10]; struct _DOT11_WFD_DISCOVER_REQUEST_V2 *
0x1400867ca  test    rcx, rcx
0x1400867cd  jnz     short loc_1400867DC
0x1400867cf  mov     rcx, rsi
0x1400867d2  mov     [rbp+var_18], r12d
0x1400867d6  mov     [rbp+var_10], rcx
0x1400867da  jmp     short loc_1400867E0
0x1400867dc  mov     r12d, [rbp+var_18]
0x1400867e0  mov     r8, r13; unsigned int *
0x1400867e3  mov     edx, r12d; unsigned int
0x1400867e6  call    ?WFDValidateDiscoverRequest@@YAJQEAU_DOT11_WFD_DISCOVER_REQUEST_V2@@KPEAK@Z; WFDValidateDiscoverRequest(_DOT11_WFD_DISCOVER_REQUEST_V2 * const,ulong,ulong *)
0x1400867eb  mov     edi, eax
0x1400867ed  test    eax, eax
0x1400867ef  js      short loc_14008681C
0x1400867f1  lea     rcx, [rbp+Irql]; Irql
0x1400867f5  call    cs:__imp_IoAcquireCancelSpinLock
0x1400867fc  nop     dword ptr [rax+rax+00h]
0x140086801  cmp     byte ptr [r15+44h], 0
0x140086806  jz      short loc_140086860
0x140086808  mov     edi, 0C0000120h
0x14008680d  mov     cl, [rbp+Irql]; Irql
0x140086810  call    cs:__imp_IoReleaseCancelSpinLock
0x140086817  nop     dword ptr [rax+rax+00h]
0x14008681c  lea     rsi, WPP_GLOBAL_Control
0x140086823  test    rbx, rbx
0x140086826  jz      loc_14008693E
0x14008682c  mov     rcx, [rbx+18h]
0x140086830  test    rcx, rcx
0x140086833  jz      loc_140086901
0x140086839  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14008683d  mov     rax, [rcx]
0x140086840  test    rax, rax
0x140086843  jz      loc_1400868EA
0x140086849  mov     rdx, rcx; Entry
0x14008684c  mov     rcx, rax; Lookaside
0x14008684f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140086856  nop     dword ptr [rax+rax+00h]
0x14008685b  jmp     loc_1400868F9
0x140086860  mov     rax, [r15+0B8h]
0x140086867  mov     [rsp+68h+var_40], rbx; void *
0x14008686c  mov     [rsp+68h+var_48], r14; void *
0x140086871  or      byte ptr [rax+3], 1
0x140086875  mov     rax, [rbp+arg_28]
0x140086879  mov     [rbx], r15
0x14008687c  mov     [rbx+8], rax
0x140086880  lea     rax, WFDCancelIoctlDiscover
0x140086887  mov     [rbx+10h], r13
0x14008688b  mov     [r15+78h], rbx
0x14008688f  xchg    rax, [r15+68h]
0x140086893  mov     rcx, [r14]
0x140086896  mov     r8, [rbp+var_10]; struct _DOT11_WFD_DISCOVER_REQUEST_V2 *
0x14008689a  mov     edx, [rbp+var_18]; unsigned int
0x14008689d  mov     rcx, [rcx+10h]; struct _ADAPT *
0x1400868a1  call    ?WFDStartDiscovery@@YAHPEAU_ADAPT@@KPEAU_DOT11_WFD_DISCOVER_REQUEST_V2@@P6AX0HPEAUDOT11_BYTE_ARRAY@@1PEAX3@Z33@Z; WFDStartDiscovery(_ADAPT *,ulong,_DOT11_WFD_DISCOVER_REQUEST_V2 *,void (*)(_ADAPT *,int,DOT11_BYTE_ARRAY *,_DOT11_WFD_DISCOVER_REQUEST_V2 *,void *,void *),void *,void *)
0x1400868a6  mov     cl, [rbp+Irql]; Irql
0x1400868a9  mov     edi, eax
0x1400868ab  call    cs:__imp_IoReleaseCancelSpinLock
0x1400868b2  nop     dword ptr [rax+rax+00h]
0x1400868b7  mov     esi, 103h
0x1400868bc  cmp     edi, esi
0x1400868be  jz      short loc_1400868E3
0x1400868c0  test    edi, edi
0x1400868c2  jz      short loc_1400868E3
0x1400868c4  mov     rcx, [r14]
0x1400868c7  xor     r8d, r8d
0x1400868ca  mov     r9, [rbp+var_10]
0x1400868ce  mov     edx, edi
0x1400868d0  mov     [rsp+68h+var_40], rbx
0x1400868d5  mov     [rsp+68h+var_48], r14
0x1400868da  mov     rcx, [rcx+10h]
0x1400868de  call    WFDIoctlDiscoverCompletion
0x1400868e3  mov     eax, esi
0x1400868e5  jmp     loc_140086999
0x1400868ea  mov     edx, [rcx+8]; Tag
0x1400868ed  call    cs:__imp_ExFreePoolWithTag
0x1400868f4  nop     dword ptr [rax+rax+00h]
0x1400868f9  mov     qword ptr [rbx+18h], 0
0x140086901  lea     rcx, [rbx-10h]; P
0x140086905  mov     rax, [rcx]
0x140086908  test    rax, rax
0x14008690b  jz      short loc_140086921
0x14008690d  mov     rdx, rcx; Entry
0x140086910  mov     rcx, rax; Lookaside
0x140086913  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008691a  nop     dword ptr [rax+rax+00h]
0x14008691f  jmp     short loc_14008693E
0x140086921  mov     edx, [rcx+8]; Tag
0x140086924  call    cs:__imp_ExFreePoolWithTag
0x14008692b  nop     dword ptr [rax+rax+00h]
0x140086930  jmp     short loc_14008693E
0x140086932  mov     edi, 0C000009Ah
0x140086937  lea     rsi, WPP_GLOBAL_Control
0x14008693e  mov     rcx, cs:WPP_GLOBAL_Control
0x140086945  cmp     rcx, rsi
0x140086948  jz      short loc_14008696F
0x14008694a  cmp     byte ptr [rcx+29h], 1
0x14008694e  jb      short loc_14008696F
0x140086950  mov     eax, [rcx+2Ch]
0x140086953  test    al, 10h
0x140086955  jz      short loc_14008696F
0x140086957  mov     rcx, [rcx+18h]
0x14008695b  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140086962  mov     edx, 1Eh
0x140086967  mov     r9d, edi
0x14008696a  call    WPP_SF_d
0x14008696f  test    cs:Microsoft_Windows_NWiFiEnableBits, 40h
0x140086976  jz      short loc_140086997
0x140086978  mov     r9, [r14]
0x14008697b  lea     rdx, RejectScanRequest
0x140086982  mov     dword ptr [rsp+68h+var_40], edi
0x140086986  lea     r8, [r9+1338h]
0x14008698d  mov     [rsp+68h+var_48], r8
0x140086992  call    McTemplateK0pjq_EtwWriteTransfer
0x140086997  mov     eax, edi
0x140086999  add     rsp, 68h
0x14008699d  pop     r15
0x14008699f  pop     r14
0x1400869a1  pop     r13
0x1400869a3  pop     r12
0x1400869a5  pop     rdi
0x1400869a6  pop     rsi
0x1400869a7  pop     rbx
0x1400869a8  pop     rbp
0x1400869a9  retn
```
