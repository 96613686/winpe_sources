# ndisMUnload(_DRIVER_OBJECT *)

- ea: `0x140172f60`
- end: `0x140173161`
- name: `?ndisMUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `513`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400d7690`

## callees

- `0x14001c050`
- `0x14001cf50`
- `0x1400233b0`
- `0x14003d920`
- `0x14004e050`
- `0x1400720e0`
- `0x1400e6240`
- `0x1401564e0`
- `0x140172f60`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x140172fc4`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140172fdd`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140172fc4`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140172fdd`
- `ntoskrnl!KeClearEvent` at `0x1401730e6`
- `ntoskrnl!KeClearEvent` at `0x1401730e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140173041`
- `ntoskrnl!KeReleaseSpinLock` at `0x140173041`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140173009`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140173009`

## pseudocode

```c
void __fastcall ndisMUnload(struct _DRIVER_OBJECT *a1)
{
  char v2; // bp
  _WORD *DriverObjectExtension; // rax
  __int16 v4; // cx
  KIRQL v5; // al
  struct _NDIS_M_DRIVER_BLOCK *i; // rdi
  void (__fastcall *UnloadHandler)(_DRIVER_OBJECT *); // rax
  _NDIS_PROTOCOL_BLOCK *AssociatedProtocol; // rax
  int v9; // edx

  v2 = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      1,
      32,
      (struct _GUID *)&WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids,
      (char)a1);
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  while ( 1 )
  {
    DriverObjectExtension = IoGetDriverObjectExtension(a1, (PVOID)0x4E4D4944);
    if ( !DriverObjectExtension )
    {
      DriverObjectExtension = IoGetDriverObjectExtension(a1, (PVOID)0x4E494944);
      if ( !DriverObjectExtension )
        goto LABEL_9;
      v2 = 1;
    }
    v4 = DriverObjectExtension[13];
    if ( (v4 & 0x10) == 0 )
      DriverObjectExtension[13] = v4 | 8;
LABEL_9:
    v5 = KeAcquireSpinLockRaiseToDpc(&ndisMiniDriverListLock);
    for ( i = ndisMiniDriverList; i && (i->DriverObject != a1 || v2 && (i->Flags & 1) == 0); i = i->NextDriver )
      ;
    KeReleaseSpinLock(&ndisMiniDriverListLock, v5);
    if ( !i )
      break;
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        4,
        1,
        33,
        (struct _GUID *)&WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids,
        (char)i);
    i->Flags |= 0x8000u;
    ndisCloseRef(&i->Ref.SpinLock);
    UnloadHandler = i->UnloadHandler;
    if ( UnloadHandler )
      UnloadHandler(a1);
    AssociatedProtocol = i->AssociatedProtocol;
    if ( AssociatedProtocol )
    {
      AssociatedProtocol->AssociatedMiniDriver = 0;
      i->AssociatedProtocol = 0;
    }
    ndisDereferenceDriver(i, 0, (enum _NDIS_MDRV_REFTAG)255);
    ndisWaitForKernelObject(&i->MiniportsRemovedEvent);
    KeClearEvent(&i->MiniportsRemovedEvent);
    if ( i == ndisDriverTrackAlloc )
      ndisDriverTrackAlloc = 0;
  }
  ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v9,
      1,
      34,
      (struct _GUID *)&WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids,
      (char)a1,
      0);
  }
}

```

## disassembly

```asm
0x140172f60  push    rbx
0x140172f62  push    rbp
0x140172f63  push    rsi
0x140172f64  push    rdi
0x140172f65  push    r12
0x140172f67  push    r13
0x140172f69  sub     rsp, 48h
0x140172f6d  mov     rsi, rcx
0x140172f70  xor     bpl, bpl
0x140172f73  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140172f7a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140172f81  lea     r13, WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids
0x140172f88  jz      short loc_140172FB0
0x140172f8a  mov     qword ptr [rsp+78h+var_50], rcx; char
0x140172f8f  mov     r9d, 20h ; ' '; int
0x140172f95  mov     rcx, cs:WPP_GLOBAL_Control
0x140172f9c  mov     dl, 4; int
0x140172f9e  mov     [rsp+78h+var_58], r13; struct _GUID *
0x140172fa3  lea     r8d, [r9-1Fh]; int
0x140172fa7  mov     rcx, [rcx+40h]; int
0x140172fab  call    WPP_RECORDER_SF_q
0x140172fb0  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140172fb7  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x140172fbc  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x140172fc1  mov     rcx, rsi; DriverObject
0x140172fc4  call    cs:__imp_IoGetDriverObjectExtension
0x140172fcb  nop     dword ptr [rax+rax+00h]
0x140172fd0  test    rax, rax
0x140172fd3  jnz     short loc_140172FF1
0x140172fd5  mov     edx, 4E494944h; ClientIdentificationAddress
0x140172fda  mov     rcx, rsi; DriverObject
0x140172fdd  call    cs:__imp_IoGetDriverObjectExtension
0x140172fe4  nop     dword ptr [rax+rax+00h]
0x140172fe9  test    rax, rax
0x140172fec  jz      short loc_140173002
0x140172fee  mov     bpl, 1
0x140172ff1  movzx   ecx, word ptr [rax+1Ah]
0x140172ff5  test    cl, 10h
0x140172ff8  jnz     short loc_140173002
0x140172ffa  or      cx, 8
0x140172ffe  mov     [rax+1Ah], cx
0x140173002  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x140173009  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140173010  nop     dword ptr [rax+rax+00h]
0x140173015  mov     rdi, cs:?ndisMiniDriverList@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA; _NDIS_M_DRIVER_BLOCK * ndisMiniDriverList
0x14017301c  jmp     short loc_140173033
0x14017301e  cmp     [rdi+28h], rsi
0x140173022  jnz     short loc_14017302F
0x140173024  test    bpl, bpl
0x140173027  jz      short loc_140173038
0x140173029  test    byte ptr [rdi+1Ah], 1
0x14017302d  jnz     short loc_140173038
0x14017302f  mov     rdi, [rdi+8]
0x140173033  test    rdi, rdi
0x140173036  jnz     short loc_14017301E
0x140173038  mov     dl, al; NewIrql
0x14017303a  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x140173041  call    cs:__imp_KeReleaseSpinLock
0x140173048  nop     dword ptr [rax+rax+00h]
0x14017304d  test    rdi, rdi
0x140173050  jz      loc_14017310F
0x140173056  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14017305d  jz      short loc_140173085
0x14017305f  mov     rcx, cs:WPP_GLOBAL_Control
0x140173066  mov     r9d, 21h ; '!'; int
0x14017306c  mov     qword ptr [rsp+78h+var_50], rdi; char
0x140173071  mov     dl, 4; int
0x140173073  mov     [rsp+78h+var_58], r13; struct _GUID *
0x140173078  mov     rcx, [rcx+40h]; int
0x14017307c  lea     r8d, [r9-20h]; int
0x140173080  call    WPP_RECORDER_SF_q
0x140173085  mov     eax, 8000h
0x14017308a  lea     rcx, [rdi+188h]; SpinLock
0x140173091  or      [rdi+1Ah], ax
0x140173095  call    ?ndisCloseRef@@YAEPEAU_REFERENCE_EX@@@Z; ndisCloseRef(_REFERENCE_EX *)
0x14017309a  mov     rax, [rdi+68h]
0x14017309e  test    rax, rax
0x1401730a1  jz      short loc_1401730AB
0x1401730a3  mov     rcx, rsi
0x1401730a6  call    _guard_dispatch_icall
0x1401730ab  mov     rax, [rdi+48h]
0x1401730af  test    rax, rax
0x1401730b2  jz      short loc_1401730C7
0x1401730b4  mov     qword ptr [rax+1C0h], 0
0x1401730bf  mov     qword ptr [rdi+48h], 0
0x1401730c7  mov     r8b, 0FFh; enum _NDIS_MDRV_REFTAG
0x1401730ca  xor     edx, edx; unsigned __int8
0x1401730cc  mov     rcx, rdi; struct _NDIS_M_DRIVER_BLOCK *
0x1401730cf  call    ?ndisDereferenceDriver@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@EW4_NDIS_MDRV_REFTAG@@@Z; ndisDereferenceDriver(_NDIS_M_DRIVER_BLOCK *,uchar,_NDIS_MDRV_REFTAG)
0x1401730d4  lea     rbx, [rdi+170h]
0x1401730db  mov     rcx, rbx; void *
0x1401730de  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x1401730e3  mov     rcx, rbx; Event
0x1401730e6  call    cs:__imp_KeClearEvent
0x1401730ed  nop     dword ptr [rax+rax+00h]
0x1401730f2  cmp     rdi, cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x1401730f9  jnz     loc_140172FBC
0x1401730ff  mov     cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, 0; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x14017310a  jmp     loc_140172FBC
0x14017310f  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140173116  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x14017311b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140173122  jz      short loc_140173153
0x140173124  mov     rcx, cs:WPP_GLOBAL_Control
0x14017312b  mov     r9d, 22h ; '"'; int
0x140173131  mov     qword ptr [rsp+78h+var_48], 0; char
0x14017313a  mov     dl, 4; int
0x14017313c  mov     qword ptr [rsp+78h+var_50], rsi; char
0x140173141  mov     [rsp+78h+var_58], r13; struct _GUID *
0x140173146  mov     rcx, [rcx+40h]; int
0x14017314a  lea     r8d, [r9-21h]; int
0x14017314e  call    WPP_RECORDER_SF_qq
0x140173153  add     rsp, 48h
0x140173157  pop     r13
0x140173159  pop     r12
0x14017315b  pop     rdi
0x14017315c  pop     rsi
0x14017315d  pop     rbp
0x14017315e  pop     rbx
0x14017315f  retn
```
