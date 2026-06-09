# ndisRegisterMiniportDriver(void *,_NDIS51_MINIPORT_CHARACTERISTICS *,uint,void * *)

- ea: `0x1401703a4`
- end: `0x1401707b3`
- name: `?ndisRegisterMiniportDriver@@_Y2PAGENPNP@@AHPEAXPEAU_NDIS51_MINIPORT_CHARACTERISTICS@@IPEAPEAX@Z`
- size: `1039`
- prototype: `__int64 __fastcall(void *, struct _NDIS51_MINIPORT_CHARACTERISTICS *Src, unsigned int, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x14008e3f0`
- `0x14008f8b0`

## callees

- `0x14001cf50`
- `0x14003d920`
- `0x14004e050`
- `0x14004e250`
- `0x140075160`
- `0x1400e62c0`
- `0x1400e65c0`
- `0x1401692b0`
- `0x1401703a4`

## import_xrefs

- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1401704ae`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1401704ae`
- `ntoskrnl!MmIsDriverVerifying` at `0x14017055b`
- `ntoskrnl!MmIsDriverVerifying` at `0x14017055b`
- `ntoskrnl!ObfReferenceObject` at `0x140170729`
- `ntoskrnl!ObfReferenceObject` at `0x140170729`
- `ntoskrnl!KeInitializeEvent` at `0x140170664`
- `ntoskrnl!KeInitializeEvent` at `0x140170664`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017073e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017073e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401706fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401706fa`

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
0x1401703a4  push    rbp
0x1401703a6  push    rbx
0x1401703a7  push    rsi
0x1401703a8  push    rdi
0x1401703a9  push    r14
0x1401703ab  push    r15
0x1401703ad  mov     rbp, rsp
0x1401703b0  sub     rsp, 38h
0x1401703b4  mov     r15, r9
0x1401703b7  mov     [rbp+DriverObjectExtension], 0
0x1401703bf  mov     r14d, r8d
0x1401703c2  mov     rbx, rdx
0x1401703c5  mov     rsi, rcx
0x1401703c8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1401703cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401703d6  lea     rdi, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x1401703dd  jz      short loc_140170405
0x1401703df  mov     qword ptr [rsp+38h+var_10], rcx; char
0x1401703e4  mov     r9d, 0Eh; int
0x1401703ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1401703f1  mov     dl, 4; int
0x1401703f3  mov     [rsp+38h+var_18], rdi; struct _GUID *
0x1401703f8  lea     r8d, [r9-0Dh]; int
0x1401703fc  mov     rcx, [rcx+40h]; int
0x140170400  call    WPP_RECORDER_SF_q
0x140170405  test    rsi, rsi
0x140170408  jnz     short loc_140170414
0x14017040a  mov     ebx, 0C0000001h
0x14017040f  jmp     loc_140170769
0x140170414  mov     dl, [rbx+1]
0x140170417  test    dl, dl
0x140170419  jnz     short loc_140170442
0x14017041b  mov     al, [rbx]
0x14017041d  cmp     al, 3
0x14017041f  jnz     short loc_140170428
0x140170421  mov     edi, 70h ; 'p'
0x140170426  jmp     short loc_14017045A
0x140170428  cmp     al, 4
0x14017042a  jnz     short loc_140170433
0x14017042c  mov     edi, 88h
0x140170431  jmp     short loc_14017045A
0x140170433  cmp     al, 5
0x140170435  jnz     loc_140170764
0x14017043b  mov     edi, 0B8h
0x140170440  jmp     short loc_14017045A
0x140170442  cmp     dl, 1
0x140170445  jnz     loc_140170764
0x14017044b  mov     al, [rbx]
0x14017044d  cmp     al, 5
0x14017044f  jnz     loc_140170764
0x140170455  mov     edi, 0F0h
0x14017045a  mov     ecx, edi
0x14017045c  cmp     r14d, ecx
0x14017045f  jnb     short loc_140170472
0x140170461  mov     ebx, 0C0010005h
0x140170466  lea     rdi, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14017046d  jmp     loc_140170769
0x140170472  cmp     al, 5
0x140170474  jnz     short loc_140170499
0x140170476  cmp     qword ptr [rbx+0A8h], 0
0x14017047e  jz      short loc_14017048A
0x140170480  cmp     qword ptr [rbx+0B0h], 0
0x140170488  jz      short loc_140170461
0x14017048a  cmp     dl, 1
0x14017048d  jb      short loc_140170499
0x14017048f  cmp     qword ptr [rbx+0C8h], 0
0x140170497  jz      short loc_140170461
0x140170499  mov     rcx, [rsi]; DriverObject
0x14017049c  lea     r9, [rbp+DriverObjectExtension]; DriverObjectExtension
0x1401704a0  mov     r14d, 4A8h
0x1401704a6  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x1401704ab  mov     r8d, r14d; DriverObjectExtensionSize
0x1401704ae  call    cs:__imp_IoAllocateDriverObjectExtension
0x1401704b5  nop     dword ptr [rax+rax+00h]
0x1401704ba  test    eax, eax
0x1401704bc  jns     short loc_1401704C5
0x1401704be  mov     ebx, 0C000009Ah
0x1401704c3  jmp     short loc_140170466
0x1401704c5  mov     rcx, [rbp+DriverObjectExtension]; void *
0x1401704c9  mov     r8, r14; Size
0x1401704cc  xor     edx, edx; Val
0x1401704ce  call    memset
0x1401704d3  mov     cl, [rbx]
0x1401704d5  mov     r8, rdi; Size
0x1401704d8  mov     rax, [rbp+DriverObjectExtension]
0x1401704dc  mov     rdx, rbx; Src
0x1401704df  mov     [rax+18h], cl
0x1401704e2  mov     cl, [rbx+1]
0x1401704e5  mov     rax, [rbp+DriverObjectExtension]
0x1401704e9  mov     [rax+19h], cl
0x1401704ec  mov     rcx, [rbp+DriverObjectExtension]
0x1401704f0  add     rcx, 70h ; 'p'; void *
0x1401704f4  call    memmove
0x1401704f9  cmp     byte ptr [rbx], 5
0x1401704fc  jnz     short loc_140170558
0x1401704fe  mov     rax, [rbp+DriverObjectExtension]
0x140170502  mov     rcx, [rbx+88h]
0x140170509  mov     [rax+1F8h], rcx
0x140170510  mov     rax, [rbp+DriverObjectExtension]
0x140170514  mov     rcx, [rbx+90h]
0x14017051b  mov     [rax+200h], rcx
0x140170522  mov     rax, [rbp+DriverObjectExtension]
0x140170526  mov     rcx, [rbx+98h]
0x14017052d  mov     [rax+208h], rcx
0x140170534  mov     rax, [rbp+DriverObjectExtension]
0x140170538  mov     rcx, [rbx+0A0h]
0x14017053f  mov     [rax+210h], rcx
0x140170546  mov     rax, [rbp+DriverObjectExtension]
0x14017054a  mov     rcx, [rbx+0B0h]
0x140170551  mov     [rax+220h], rcx
0x140170558  mov     rcx, [rsi]; DriverObject
0x14017055b  call    cs:__imp_MmIsDriverVerifying
0x140170562  nop     dword ptr [rax+rax+00h]
0x140170567  test    eax, eax
0x140170569  jz      short loc_14017059A
0x14017056b  mov     rax, [rbp+DriverObjectExtension]
0x14017056f  or      word ptr [rax+1Ah], 2
0x140170574  test    cs:?ndisFlags@@3JA, 400h; long ndisFlags
0x14017057e  jz      short loc_14017059A
0x140170580  mov     rcx, [rbp+DriverObjectExtension]
0x140170584  xor     eax, eax
0x140170586  cmp     cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, rax; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x14017058d  cmovz   rax, rcx
0x140170591  mov     cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, rax; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x140170598  jmp     short loc_14017059E
0x14017059a  mov     rcx, [rbp+DriverObjectExtension]
0x14017059e  mov     qword ptr [rcx+10h], 0
0x1401705a6  xor     ecx, ecx
0x1401705a8  mov     rax, [rsi]
0x1401705ab  lea     rdx, ?ndisDummyIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDummyIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x1401705b2  mov     [rax+rcx*8+70h], rdx
0x1401705b7  inc     rcx
0x1401705ba  cmp     rcx, 1Ch
0x1401705be  jnz     short loc_1401705A8
0x1401705c0  mov     rax, [rsi]
0x1401705c3  xor     r8d, r8d; State
0x1401705c6  xor     edx, edx; Type
0x1401705c8  mov     rcx, [rax+30h]
0x1401705cc  lea     rax, ?ndisWdmPnPAddDevice@@YAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z; ndisWdmPnPAddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)
0x1401705d3  mov     [rcx+8], rax
0x1401705d7  lea     rcx, ?ndisMUnload@@YAXPEAU_DRIVER_OBJECT@@@Z; ndisMUnload(_DRIVER_OBJECT *)
0x1401705de  mov     rax, [rsi]
0x1401705e1  mov     [rax+68h], rcx
0x1401705e5  lea     rcx, ?ndisCreateIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisCreateIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x1401705ec  mov     rax, [rsi]
0x1401705ef  mov     [rax+70h], rcx
0x1401705f3  lea     rcx, ?ndisDeviceControlIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDeviceControlIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x1401705fa  mov     rax, [rsi]
0x1401705fd  mov     [rax+0E0h], rcx
0x140170604  lea     rcx, ?ndisDeviceInternalIrpDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDeviceInternalIrpDispatch(_DEVICE_OBJECT *,_IRP *)
0x14017060b  mov     rax, [rsi]
0x14017060e  mov     [rax+0E8h], rcx
0x140170615  lea     rcx, ?ndisCloseIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisCloseIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x14017061c  mov     rax, [rsi]
0x14017061f  mov     [rax+80h], rcx
0x140170626  lea     rcx, ?ndisPnPDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisPnPDispatch(_DEVICE_OBJECT *,_IRP *)
0x14017062d  mov     rax, [rsi]
0x140170630  mov     [rax+148h], rcx
0x140170637  lea     rcx, ?ndisPowerDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisPowerDispatch(_DEVICE_OBJECT *,_IRP *)
0x14017063e  mov     rax, [rsi]
0x140170641  mov     [rax+120h], rcx
0x140170648  lea     rcx, ?ndisWMIIrpDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisWMIIrpDispatch(_DEVICE_OBJECT *,_IRP *)
0x14017064f  mov     rax, [rsi]
0x140170652  mov     [rax+128h], rcx
0x140170659  mov     rcx, [rbp+DriverObjectExtension]
0x14017065d  add     rcx, 170h; Event
0x140170664  call    cs:__imp_KeInitializeEvent
0x14017066b  nop     dword ptr [rax+rax+00h]
0x140170670  mov     rax, [rbp+DriverObjectExtension]
0x140170674  mov     dl, 0Dh; unsigned __int8
0x140170676  mov     [rax+20h], rsi
0x14017067a  mov     rax, [rbp+DriverObjectExtension]
0x14017067e  mov     rcx, [rsi]
0x140170681  mov     [rax+28h], rcx
0x140170685  mov     rax, [rbp+DriverObjectExtension]
0x140170689  add     rax, 50h ; 'P'
0x14017068d  mov     [rax+8], rax
0x140170691  mov     [rax], rax
0x140170694  mov     rcx, [rbp+DriverObjectExtension]
0x140170698  add     rcx, 188h; struct _REFERENCE_EX *
0x14017069f  call    ?ndisInitializeRef@@YAXPEAU_REFERENCE_EX@@E@Z; ndisInitializeRef(_REFERENCE_EX *,uchar)
0x1401706a4  mov     rax, [rbp+DriverObjectExtension]
0x1401706a8  lea     rcx, [rsi+8]; struct _UNICODE_STRING *
0x1401706ac  mov     byte ptr [rax], 2
0x1401706af  mov     rax, [rbp+DriverObjectExtension]
0x1401706b3  mov     [rax+2], r14w
0x1401706b8  mov     rax, [rbp+DriverObjectExtension]
0x1401706bc  mov     byte ptr [rax+1], 1
0x1401706c0  mov     rdx, [rbp+DriverObjectExtension]
0x1401706c4  add     rdx, 1E8h; struct _UNICODE_STRING *
0x1401706cb  call    ?ndisGetServiceNameFromRegPath@@YAXPEAU_UNICODE_STRING@@0@Z; ndisGetServiceNameFromRegPath(_UNICODE_STRING *,_UNICODE_STRING *)
0x1401706d0  mov     rcx, [rbp+DriverObjectExtension]
0x1401706d4  lea     rdx, [rcx+368h]; struct _UNICODE_STRING *
0x1401706db  add     rcx, 1E8h; struct _UNICODE_STRING *
0x1401706e2  call    ?ndisQueryDriverImageName@@YAXPEAU_UNICODE_STRING@@0@Z; ndisQueryDriverImageName(_UNICODE_STRING *,_UNICODE_STRING *)
0x1401706e7  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x1401706ee  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x1401706f3  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x1401706fa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140170701  nop     dword ptr [rax+rax+00h]
0x140170706  mov     rdx, cs:?ndisMiniDriverList@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA; _NDIS_M_DRIVER_BLOCK * ndisMiniDriverList
0x14017070d  mov     bl, al
0x14017070f  mov     r8, [rbp+DriverObjectExtension]
0x140170713  mov     rcx, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; Object
0x14017071a  mov     [r8+8], rdx
0x14017071e  mov     rdx, [rbp+DriverObjectExtension]
0x140170722  mov     cs:?ndisMiniDriverList@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, rdx; _NDIS_M_DRIVER_BLOCK * ndisMiniDriverList
0x140170729  call    cs:__imp_ObfReferenceObject
0x140170730  nop     dword ptr [rax+rax+00h]
0x140170735  mov     dl, bl; NewIrql
0x140170737  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x14017073e  call    cs:__imp_KeReleaseSpinLock
0x140170745  nop     dword ptr [rax+rax+00h]
0x14017074a  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140170751  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x140170756  mov     rax, [rbp+DriverObjectExtension]
0x14017075a  xor     ebx, ebx
0x14017075c  mov     [r15], rax
0x14017075f  jmp     loc_140170466
0x140170764  mov     ebx, 0C0010004h
0x140170769  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140170770  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140170777  jz      short loc_1401707A3
0x140170779  mov     rcx, [rbp+DriverObjectExtension]
0x14017077d  mov     r9d, 0Fh; int
0x140170783  mov     qword ptr [rsp+38h+var_10], rcx; char
0x140170788  mov     dl, 4; int
0x14017078a  mov     rcx, cs:WPP_GLOBAL_Control
0x140170791  mov     [rsp+38h+var_18], rdi; struct _GUID *
0x140170796  lea     r8d, [r9-0Eh]; int
0x14017079a  mov     rcx, [rcx+40h]; int
0x14017079e  call    WPP_RECORDER_SF_q
0x1401707a3  mov     eax, ebx
0x1401707a5  add     rsp, 38h
0x1401707a9  pop     r15
0x1401707ab  pop     r14
0x1401707ad  pop     rdi
0x1401707ae  pop     rsi
0x1401707af  pop     rbx
0x1401707b0  pop     rbp
0x1401707b1  retn
```
