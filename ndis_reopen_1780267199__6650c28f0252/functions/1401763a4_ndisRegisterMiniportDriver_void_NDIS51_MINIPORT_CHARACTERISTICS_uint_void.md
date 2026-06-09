# ndisRegisterMiniportDriver(void *,_NDIS51_MINIPORT_CHARACTERISTICS *,uint,void * *)

- ea: `0x1401763a4`
- end: `0x1401767b3`
- name: `?ndisRegisterMiniportDriver@@_Y2PAGENPNP@@AHPEAXPEAU_NDIS51_MINIPORT_CHARACTERISTICS@@IPEAPEAX@Z`
- size: `1039`
- prototype: `__int64 __fastcall(void *, struct _NDIS51_MINIPORT_CHARACTERISTICS *Src, unsigned int, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140092e30`
- `0x1400942f0`

## callees

- `0x1400110b0`
- `0x1400400d0`
- `0x140053280`
- `0x140053480`
- `0x14007a840`
- `0x1400eb4c0`
- `0x1400eb7c0`
- `0x1401701a0`
- `0x1401763a4`

## import_xrefs

- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1401764ae`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1401764ae`
- `ntoskrnl!MmIsDriverVerifying` at `0x14017655b`
- `ntoskrnl!MmIsDriverVerifying` at `0x14017655b`
- `ntoskrnl!ObfReferenceObject` at `0x140176729`
- `ntoskrnl!ObfReferenceObject` at `0x140176729`
- `ntoskrnl!KeInitializeEvent` at `0x140176664`
- `ntoskrnl!KeInitializeEvent` at `0x140176664`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017673e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017673e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401766fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401766fa`

## pseudocode

```c
__int64 __fastcall ndisRegisterMiniportDriver(
        char *a1,
        struct _NDIS51_MINIPORT_CHARACTERISTICS *Src,
        unsigned int a3,
        void **a4)
{
  struct _NDIS51_MINIPORT_CHARACTERISTICS *v6; // rbx
  unsigned int v8; // ebx
  unsigned __int8 MinorNdisVersion; // dl
  unsigned __int8 MajorNdisVersion; // al
  size_t v11; // rdi
  _QWORD *v12; // rcx
  struct _NDIS_M_DRIVER_BLOCK *v13; // rax
  __int64 i; // rcx
  _QWORD *v15; // rax
  KIRQL v16; // bl
  PVOID v17; // rcx
  PVOID DriverObjectExtension; // [rsp+70h] [rbp+38h] BYREF

  DriverObjectExtension = 0;
  v6 = Src;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(Src) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)Src,
      1,
      14,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)a1);
  }
  if ( !a1 )
  {
    v8 = -1073741823;
    goto LABEL_37;
  }
  MinorNdisVersion = v6->Ndis50Chars.MinorNdisVersion;
  if ( MinorNdisVersion )
  {
    if ( MinorNdisVersion == 1 )
    {
      MajorNdisVersion = v6->Ndis50Chars.MajorNdisVersion;
      if ( v6->Ndis50Chars.MajorNdisVersion == 5 )
      {
        v11 = 240;
        goto LABEL_15;
      }
    }
    goto LABEL_36;
  }
  MajorNdisVersion = v6->Ndis50Chars.MajorNdisVersion;
  if ( v6->Ndis50Chars.MajorNdisVersion != 3 )
  {
    if ( MajorNdisVersion == 4 )
    {
      v11 = 136;
      goto LABEL_15;
    }
    if ( MajorNdisVersion == 5 )
    {
      v11 = 184;
      goto LABEL_15;
    }
LABEL_36:
    v8 = -1073676284;
    goto LABEL_37;
  }
  v11 = 112;
LABEL_15:
  if ( a3 < (unsigned int)v11
    || MajorNdisVersion == 5
    && (v6->Ndis50Chars.CoSendPacketsHandler && !v6->Ndis50Chars.CoRequestHandler
     || MinorNdisVersion && !v6->AdapterShutdownHandler) )
  {
    v8 = -1073676283;
  }
  else if ( IoAllocateDriverObjectExtension(*(PDRIVER_OBJECT *)a1, (PVOID)0x4E4D4944, 0x4A8u, &DriverObjectExtension) >= 0 )
  {
    memset(DriverObjectExtension, 0, 0x4A8u);
    *((_BYTE *)DriverObjectExtension + 24) = v6->Ndis50Chars.MajorNdisVersion;
    *((_BYTE *)DriverObjectExtension + 25) = v6->Ndis50Chars.MinorNdisVersion;
    memmove((char *)DriverObjectExtension + 112, v6, v11);
    if ( v6->Ndis50Chars.MajorNdisVersion == 5 )
    {
      *((_QWORD *)DriverObjectExtension + 63) = v6->Ndis50Chars.CoCreateVcHandler;
      *((_QWORD *)DriverObjectExtension + 64) = v6->Ndis50Chars.CoDeleteVcHandler;
      *((_QWORD *)DriverObjectExtension + 65) = v6->Ndis50Chars.CoActivateVcHandler;
      *((_QWORD *)DriverObjectExtension + 66) = v6->Ndis50Chars.CoDeactivateVcHandler;
      *((_QWORD *)DriverObjectExtension + 68) = v6->Ndis50Chars.CoRequestHandler;
    }
    if ( MmIsDriverVerifying(*(struct _DRIVER_OBJECT **)a1)
      && (*((_WORD *)DriverObjectExtension + 13) |= 2u, (ndisFlags & 0x400) != 0) )
    {
      v12 = DriverObjectExtension;
      v13 = 0;
      if ( !ndisDriverTrackAlloc )
        v13 = (struct _NDIS_M_DRIVER_BLOCK *)DriverObjectExtension;
      ndisDriverTrackAlloc = v13;
    }
    else
    {
      v12 = DriverObjectExtension;
    }
    v12[2] = 0;
    for ( i = 0; i != 28; ++i )
      *(_QWORD *)(*(_QWORD *)a1 + 8 * i + 112) = ndisDummyIrpHandler;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 48LL) + 8LL) = ndisWdmPnPAddDevice;
    *(_QWORD *)(*(_QWORD *)a1 + 104LL) = ndisMUnload;
    *(_QWORD *)(*(_QWORD *)a1 + 112LL) = ndisCreateIrpHandler;
    *(_QWORD *)(*(_QWORD *)a1 + 224LL) = ndisDeviceControlIrpHandler;
    *(_QWORD *)(*(_QWORD *)a1 + 232LL) = ndisDeviceInternalIrpDispatch;
    *(_QWORD *)(*(_QWORD *)a1 + 128LL) = ndisCloseIrpHandler;
    *(_QWORD *)(*(_QWORD *)a1 + 328LL) = ndisPnPDispatch;
    *(_QWORD *)(*(_QWORD *)a1 + 288LL) = ndisPowerDispatch;
    *(_QWORD *)(*(_QWORD *)a1 + 296LL) = ndisWMIIrpDispatch;
    KeInitializeEvent((PRKEVENT)((char *)DriverObjectExtension + 368), NotificationEvent, 0);
    *((_QWORD *)DriverObjectExtension + 4) = a1;
    *((_QWORD *)DriverObjectExtension + 5) = *(_QWORD *)a1;
    v15 = (char *)DriverObjectExtension + 80;
    *((_QWORD *)DriverObjectExtension + 11) = (char *)DriverObjectExtension + 80;
    *v15 = v15;
    ndisInitializeRef((struct _REFERENCE_EX *)((char *)DriverObjectExtension + 392), 0xDu);
    *(_BYTE *)DriverObjectExtension = 2;
    *((_WORD *)DriverObjectExtension + 1) = 1192;
    *((_BYTE *)DriverObjectExtension + 1) = 1;
    ndisGetServiceNameFromRegPath(
      (struct _UNICODE_STRING *)(a1 + 8),
      (struct _UNICODE_STRING *)((char *)DriverObjectExtension + 488));
    ndisQueryDriverImageName(
      (struct _UNICODE_STRING *)((char *)DriverObjectExtension + 488),
      (struct _UNICODE_STRING *)((char *)DriverObjectExtension + 872));
    ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
    v16 = KeAcquireSpinLockRaiseToDpc(&ndisMiniDriverListLock);
    v17 = ndisDriverObject;
    *((_QWORD *)DriverObjectExtension + 1) = ndisMiniDriverList;
    ndisMiniDriverList = (struct _NDIS_M_DRIVER_BLOCK *)DriverObjectExtension;
    ObfReferenceObject(v17);
    KeReleaseSpinLock(&ndisMiniDriverListLock, v16);
    ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
    v8 = 0;
    *a4 = DriverObjectExtension;
  }
  else
  {
    v8 = -1073741670;
  }
LABEL_37:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(Src) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)Src,
      1,
      15,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)DriverObjectExtension);
  }
  return v8;
}

```

## disassembly

```asm
0x1401763a4  push    rbp
0x1401763a6  push    rbx
0x1401763a7  push    rsi
0x1401763a8  push    rdi
0x1401763a9  push    r14
0x1401763ab  push    r15
0x1401763ad  mov     rbp, rsp
0x1401763b0  sub     rsp, 38h
0x1401763b4  mov     r15, r9
0x1401763b7  mov     [rbp+DriverObjectExtension], 0
0x1401763bf  mov     r14d, r8d
0x1401763c2  mov     rbx, rdx
0x1401763c5  mov     rsi, rcx
0x1401763c8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1401763cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401763d6  lea     rdi, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x1401763dd  jz      short loc_140176405
0x1401763df  mov     qword ptr [rsp+38h+var_10], rcx; char
0x1401763e4  mov     r9d, 0Eh; int
0x1401763ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1401763f1  mov     dl, 4; int
0x1401763f3  mov     [rsp+38h+var_18], rdi; struct _GUID *
0x1401763f8  lea     r8d, [r9-0Dh]; int
0x1401763fc  mov     rcx, [rcx+40h]; int
0x140176400  call    WPP_RECORDER_SF_q
0x140176405  test    rsi, rsi
0x140176408  jnz     short loc_140176414
0x14017640a  mov     ebx, 0C0000001h
0x14017640f  jmp     loc_140176769
0x140176414  mov     dl, [rbx+1]
0x140176417  test    dl, dl
0x140176419  jnz     short loc_140176442
0x14017641b  mov     al, [rbx]
0x14017641d  cmp     al, 3
0x14017641f  jnz     short loc_140176428
0x140176421  mov     edi, 70h ; 'p'
0x140176426  jmp     short loc_14017645A
0x140176428  cmp     al, 4
0x14017642a  jnz     short loc_140176433
0x14017642c  mov     edi, 88h
0x140176431  jmp     short loc_14017645A
0x140176433  cmp     al, 5
0x140176435  jnz     loc_140176764
0x14017643b  mov     edi, 0B8h
0x140176440  jmp     short loc_14017645A
0x140176442  cmp     dl, 1
0x140176445  jnz     loc_140176764
0x14017644b  mov     al, [rbx]
0x14017644d  cmp     al, 5
0x14017644f  jnz     loc_140176764
0x140176455  mov     edi, 0F0h
0x14017645a  mov     ecx, edi
0x14017645c  cmp     r14d, ecx
0x14017645f  jnb     short loc_140176472
0x140176461  mov     ebx, 0C0010005h
0x140176466  lea     rdi, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14017646d  jmp     loc_140176769
0x140176472  cmp     al, 5
0x140176474  jnz     short loc_140176499
0x140176476  cmp     qword ptr [rbx+0A8h], 0
0x14017647e  jz      short loc_14017648A
0x140176480  cmp     qword ptr [rbx+0B0h], 0
0x140176488  jz      short loc_140176461
0x14017648a  cmp     dl, 1
0x14017648d  jb      short loc_140176499
0x14017648f  cmp     qword ptr [rbx+0C8h], 0
0x140176497  jz      short loc_140176461
0x140176499  mov     rcx, [rsi]; DriverObject
0x14017649c  lea     r9, [rbp+DriverObjectExtension]; DriverObjectExtension
0x1401764a0  mov     r14d, 4A8h
0x1401764a6  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x1401764ab  mov     r8d, r14d; DriverObjectExtensionSize
0x1401764ae  call    cs:__imp_IoAllocateDriverObjectExtension
0x1401764b5  nop     dword ptr [rax+rax+00h]
0x1401764ba  test    eax, eax
0x1401764bc  jns     short loc_1401764C5
0x1401764be  mov     ebx, 0C000009Ah
0x1401764c3  jmp     short loc_140176466
0x1401764c5  mov     rcx, [rbp+DriverObjectExtension]; void *
0x1401764c9  mov     r8, r14; Size
0x1401764cc  xor     edx, edx; Val
0x1401764ce  call    memset
0x1401764d3  mov     cl, [rbx]
0x1401764d5  mov     r8, rdi; Size
0x1401764d8  mov     rax, [rbp+DriverObjectExtension]
0x1401764dc  mov     rdx, rbx; Src
0x1401764df  mov     [rax+18h], cl
0x1401764e2  mov     cl, [rbx+1]
0x1401764e5  mov     rax, [rbp+DriverObjectExtension]
0x1401764e9  mov     [rax+19h], cl
0x1401764ec  mov     rcx, [rbp+DriverObjectExtension]
0x1401764f0  add     rcx, 70h ; 'p'; void *
0x1401764f4  call    memmove
0x1401764f9  cmp     byte ptr [rbx], 5
0x1401764fc  jnz     short loc_140176558
0x1401764fe  mov     rax, [rbp+DriverObjectExtension]
0x140176502  mov     rcx, [rbx+88h]
0x140176509  mov     [rax+1F8h], rcx
0x140176510  mov     rax, [rbp+DriverObjectExtension]
0x140176514  mov     rcx, [rbx+90h]
0x14017651b  mov     [rax+200h], rcx
0x140176522  mov     rax, [rbp+DriverObjectExtension]
0x140176526  mov     rcx, [rbx+98h]
0x14017652d  mov     [rax+208h], rcx
0x140176534  mov     rax, [rbp+DriverObjectExtension]
0x140176538  mov     rcx, [rbx+0A0h]
0x14017653f  mov     [rax+210h], rcx
0x140176546  mov     rax, [rbp+DriverObjectExtension]
0x14017654a  mov     rcx, [rbx+0B0h]
0x140176551  mov     [rax+220h], rcx
0x140176558  mov     rcx, [rsi]; DriverObject
0x14017655b  call    cs:__imp_MmIsDriverVerifying
0x140176562  nop     dword ptr [rax+rax+00h]
0x140176567  test    eax, eax
0x140176569  jz      short loc_14017659A
0x14017656b  mov     rax, [rbp+DriverObjectExtension]
0x14017656f  or      word ptr [rax+1Ah], 2
0x140176574  test    cs:?ndisFlags@@3JA, 400h; long ndisFlags
0x14017657e  jz      short loc_14017659A
0x140176580  mov     rcx, [rbp+DriverObjectExtension]
0x140176584  xor     eax, eax
0x140176586  cmp     cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, rax; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x14017658d  cmovz   rax, rcx
0x140176591  mov     cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, rax; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x140176598  jmp     short loc_14017659E
0x14017659a  mov     rcx, [rbp+DriverObjectExtension]
0x14017659e  mov     qword ptr [rcx+10h], 0
0x1401765a6  xor     ecx, ecx
0x1401765a8  mov     rax, [rsi]
0x1401765ab  lea     rdx, ?ndisDummyIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDummyIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x1401765b2  mov     [rax+rcx*8+70h], rdx
0x1401765b7  inc     rcx
0x1401765ba  cmp     rcx, 1Ch
0x1401765be  jnz     short loc_1401765A8
0x1401765c0  mov     rax, [rsi]
0x1401765c3  xor     r8d, r8d; State
0x1401765c6  xor     edx, edx; Type
0x1401765c8  mov     rcx, [rax+30h]
0x1401765cc  lea     rax, ?ndisWdmPnPAddDevice@@YAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z; ndisWdmPnPAddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)
0x1401765d3  mov     [rcx+8], rax
0x1401765d7  lea     rcx, ?ndisMUnload@@YAXPEAU_DRIVER_OBJECT@@@Z; ndisMUnload(_DRIVER_OBJECT *)
0x1401765de  mov     rax, [rsi]
0x1401765e1  mov     [rax+68h], rcx
0x1401765e5  lea     rcx, ?ndisCreateIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisCreateIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x1401765ec  mov     rax, [rsi]
0x1401765ef  mov     [rax+70h], rcx
0x1401765f3  lea     rcx, ?ndisDeviceControlIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDeviceControlIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x1401765fa  mov     rax, [rsi]
0x1401765fd  mov     [rax+0E0h], rcx
0x140176604  lea     rcx, ?ndisDeviceInternalIrpDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDeviceInternalIrpDispatch(_DEVICE_OBJECT *,_IRP *)
0x14017660b  mov     rax, [rsi]
0x14017660e  mov     [rax+0E8h], rcx
0x140176615  lea     rcx, ?ndisCloseIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisCloseIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x14017661c  mov     rax, [rsi]
0x14017661f  mov     [rax+80h], rcx
0x140176626  lea     rcx, ?ndisPnPDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisPnPDispatch(_DEVICE_OBJECT *,_IRP *)
0x14017662d  mov     rax, [rsi]
0x140176630  mov     [rax+148h], rcx
0x140176637  lea     rcx, ?ndisPowerDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisPowerDispatch(_DEVICE_OBJECT *,_IRP *)
0x14017663e  mov     rax, [rsi]
0x140176641  mov     [rax+120h], rcx
0x140176648  lea     rcx, ?ndisWMIIrpDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisWMIIrpDispatch(_DEVICE_OBJECT *,_IRP *)
0x14017664f  mov     rax, [rsi]
0x140176652  mov     [rax+128h], rcx
0x140176659  mov     rcx, [rbp+DriverObjectExtension]
0x14017665d  add     rcx, 170h; Event
0x140176664  call    cs:__imp_KeInitializeEvent
0x14017666b  nop     dword ptr [rax+rax+00h]
0x140176670  mov     rax, [rbp+DriverObjectExtension]
0x140176674  mov     dl, 0Dh; unsigned __int8
0x140176676  mov     [rax+20h], rsi
0x14017667a  mov     rax, [rbp+DriverObjectExtension]
0x14017667e  mov     rcx, [rsi]
0x140176681  mov     [rax+28h], rcx
0x140176685  mov     rax, [rbp+DriverObjectExtension]
0x140176689  add     rax, 50h ; 'P'
0x14017668d  mov     [rax+8], rax
0x140176691  mov     [rax], rax
0x140176694  mov     rcx, [rbp+DriverObjectExtension]
0x140176698  add     rcx, 188h; struct _REFERENCE_EX *
0x14017669f  call    ?ndisInitializeRef@@YAXPEAU_REFERENCE_EX@@E@Z; ndisInitializeRef(_REFERENCE_EX *,uchar)
0x1401766a4  mov     rax, [rbp+DriverObjectExtension]
0x1401766a8  lea     rcx, [rsi+8]; struct _UNICODE_STRING *
0x1401766ac  mov     byte ptr [rax], 2
0x1401766af  mov     rax, [rbp+DriverObjectExtension]
0x1401766b3  mov     [rax+2], r14w
0x1401766b8  mov     rax, [rbp+DriverObjectExtension]
0x1401766bc  mov     byte ptr [rax+1], 1
0x1401766c0  mov     rdx, [rbp+DriverObjectExtension]
0x1401766c4  add     rdx, 1E8h; struct _UNICODE_STRING *
0x1401766cb  call    ?ndisGetServiceNameFromRegPath@@YAXPEAU_UNICODE_STRING@@0@Z; ndisGetServiceNameFromRegPath(_UNICODE_STRING *,_UNICODE_STRING *)
0x1401766d0  mov     rcx, [rbp+DriverObjectExtension]
0x1401766d4  lea     rdx, [rcx+368h]; struct _UNICODE_STRING *
0x1401766db  add     rcx, 1E8h; struct _UNICODE_STRING *
0x1401766e2  call    ?ndisQueryDriverImageName@@YAXPEAU_UNICODE_STRING@@0@Z; ndisQueryDriverImageName(_UNICODE_STRING *,_UNICODE_STRING *)
0x1401766e7  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x1401766ee  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x1401766f3  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x1401766fa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140176701  nop     dword ptr [rax+rax+00h]
0x140176706  mov     rdx, cs:?ndisMiniDriverList@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA; _NDIS_M_DRIVER_BLOCK * ndisMiniDriverList
0x14017670d  mov     bl, al
0x14017670f  mov     r8, [rbp+DriverObjectExtension]
0x140176713  mov     rcx, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; Object
0x14017671a  mov     [r8+8], rdx
0x14017671e  mov     rdx, [rbp+DriverObjectExtension]
0x140176722  mov     cs:?ndisMiniDriverList@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, rdx; _NDIS_M_DRIVER_BLOCK * ndisMiniDriverList
0x140176729  call    cs:__imp_ObfReferenceObject
0x140176730  nop     dword ptr [rax+rax+00h]
0x140176735  mov     dl, bl; NewIrql
0x140176737  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x14017673e  call    cs:__imp_KeReleaseSpinLock
0x140176745  nop     dword ptr [rax+rax+00h]
0x14017674a  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140176751  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x140176756  mov     rax, [rbp+DriverObjectExtension]
0x14017675a  xor     ebx, ebx
0x14017675c  mov     [r15], rax
0x14017675f  jmp     loc_140176466
0x140176764  mov     ebx, 0C0010004h
0x140176769  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140176770  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140176777  jz      short loc_1401767A3
0x140176779  mov     rcx, [rbp+DriverObjectExtension]
0x14017677d  mov     r9d, 0Fh; int
0x140176783  mov     qword ptr [rsp+38h+var_10], rcx; char
0x140176788  mov     dl, 4; int
0x14017678a  mov     rcx, cs:WPP_GLOBAL_Control
0x140176791  mov     [rsp+38h+var_18], rdi; struct _GUID *
0x140176796  lea     r8d, [r9-0Eh]; int
0x14017679a  mov     rcx, [rcx+40h]; int
0x14017679e  call    WPP_RECORDER_SF_q
0x1401767a3  mov     eax, ebx
0x1401767a5  add     rsp, 38h
0x1401767a9  pop     r15
0x1401767ab  pop     r14
0x1401767ad  pop     rdi
0x1401767ae  pop     rsi
0x1401767af  pop     rbx
0x1401767b0  pop     rbp
0x1401767b1  retn
```
