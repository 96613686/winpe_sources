# ndisMUnload(_DRIVER_OBJECT *)

- ea: `0x140178f60`
- end: `0x140179161`
- name: `?ndisMUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `513`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400dc840`

## callees

- `0x1400100f0`
- `0x1400110b0`
- `0x140017510`
- `0x1400400d0`
- `0x140053280`
- `0x140077b30`
- `0x1400eb460`
- `0x14015d480`
- `0x140178f60`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x140178fc4`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140178fdd`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140178fc4`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140178fdd`
- `ntoskrnl!KeClearEvent` at `0x1401790e6`
- `ntoskrnl!KeClearEvent` at `0x1401790e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140179041`
- `ntoskrnl!KeReleaseSpinLock` at `0x140179041`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140179009`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140179009`

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
0x140178f60  push    rbx
0x140178f62  push    rbp
0x140178f63  push    rsi
0x140178f64  push    rdi
0x140178f65  push    r12
0x140178f67  push    r13
0x140178f69  sub     rsp, 48h
0x140178f6d  mov     rsi, rcx
0x140178f70  xor     bpl, bpl
0x140178f73  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140178f7a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140178f81  lea     r13, WPP_91e24223ea6635c7ede0c9cfb5715ff6_Traceguids
0x140178f88  jz      short loc_140178FB0
0x140178f8a  mov     qword ptr [rsp+78h+var_50], rcx; char
0x140178f8f  mov     r9d, 20h ; ' '; int
0x140178f95  mov     rcx, cs:WPP_GLOBAL_Control
0x140178f9c  mov     dl, 4; int
0x140178f9e  mov     [rsp+78h+var_58], r13; struct _GUID *
0x140178fa3  lea     r8d, [r9-1Fh]; int
0x140178fa7  mov     rcx, [rcx+40h]; int
0x140178fab  call    WPP_RECORDER_SF_q
0x140178fb0  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140178fb7  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x140178fbc  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x140178fc1  mov     rcx, rsi; DriverObject
0x140178fc4  call    cs:__imp_IoGetDriverObjectExtension
0x140178fcb  nop     dword ptr [rax+rax+00h]
0x140178fd0  test    rax, rax
0x140178fd3  jnz     short loc_140178FF1
0x140178fd5  mov     edx, 4E494944h; ClientIdentificationAddress
0x140178fda  mov     rcx, rsi; DriverObject
0x140178fdd  call    cs:__imp_IoGetDriverObjectExtension
0x140178fe4  nop     dword ptr [rax+rax+00h]
0x140178fe9  test    rax, rax
0x140178fec  jz      short loc_140179002
0x140178fee  mov     bpl, 1
0x140178ff1  movzx   ecx, word ptr [rax+1Ah]
0x140178ff5  test    cl, 10h
0x140178ff8  jnz     short loc_140179002
0x140178ffa  or      cx, 8
0x140178ffe  mov     [rax+1Ah], cx
0x140179002  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x140179009  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140179010  nop     dword ptr [rax+rax+00h]
0x140179015  mov     rdi, cs:?ndisMiniDriverList@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA; _NDIS_M_DRIVER_BLOCK * ndisMiniDriverList
0x14017901c  jmp     short loc_140179033
0x14017901e  cmp     [rdi+28h], rsi
0x140179022  jnz     short loc_14017902F
0x140179024  test    bpl, bpl
0x140179027  jz      short loc_140179038
0x140179029  test    byte ptr [rdi+1Ah], 1
0x14017902d  jnz     short loc_140179038
0x14017902f  mov     rdi, [rdi+8]
0x140179033  test    rdi, rdi
0x140179036  jnz     short loc_14017901E
0x140179038  mov     dl, al; NewIrql
0x14017903a  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x140179041  call    cs:__imp_KeReleaseSpinLock
0x140179048  nop     dword ptr [rax+rax+00h]
0x14017904d  test    rdi, rdi
0x140179050  jz      loc_14017910F
0x140179056  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14017905d  jz      short loc_140179085
0x14017905f  mov     rcx, cs:WPP_GLOBAL_Control
0x140179066  mov     r9d, 21h ; '!'; int
0x14017906c  mov     qword ptr [rsp+78h+var_50], rdi; char
0x140179071  mov     dl, 4; int
0x140179073  mov     [rsp+78h+var_58], r13; struct _GUID *
0x140179078  mov     rcx, [rcx+40h]; int
0x14017907c  lea     r8d, [r9-20h]; int
0x140179080  call    WPP_RECORDER_SF_q
0x140179085  mov     eax, 8000h
0x14017908a  lea     rcx, [rdi+188h]; SpinLock
0x140179091  or      [rdi+1Ah], ax
0x140179095  call    ?ndisCloseRef@@YAEPEAU_REFERENCE_EX@@@Z; ndisCloseRef(_REFERENCE_EX *)
0x14017909a  mov     rax, [rdi+68h]
0x14017909e  test    rax, rax
0x1401790a1  jz      short loc_1401790AB
0x1401790a3  mov     rcx, rsi
0x1401790a6  call    _guard_dispatch_icall
0x1401790ab  mov     rax, [rdi+48h]
0x1401790af  test    rax, rax
0x1401790b2  jz      short loc_1401790C7
0x1401790b4  mov     qword ptr [rax+1C0h], 0
0x1401790bf  mov     qword ptr [rdi+48h], 0
0x1401790c7  mov     r8b, 0FFh; enum _NDIS_MDRV_REFTAG
0x1401790ca  xor     edx, edx; unsigned __int8
0x1401790cc  mov     rcx, rdi; struct _NDIS_M_DRIVER_BLOCK *
0x1401790cf  call    ?ndisDereferenceDriver@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@EW4_NDIS_MDRV_REFTAG@@@Z; ndisDereferenceDriver(_NDIS_M_DRIVER_BLOCK *,uchar,_NDIS_MDRV_REFTAG)
0x1401790d4  lea     rbx, [rdi+170h]
0x1401790db  mov     rcx, rbx; void *
0x1401790de  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x1401790e3  mov     rcx, rbx; Event
0x1401790e6  call    cs:__imp_KeClearEvent
0x1401790ed  nop     dword ptr [rax+rax+00h]
0x1401790f2  cmp     rdi, cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x1401790f9  jnz     loc_140178FBC
0x1401790ff  mov     cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, 0; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x14017910a  jmp     loc_140178FBC
0x14017910f  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140179116  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x14017911b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140179122  jz      short loc_140179153
0x140179124  mov     rcx, cs:WPP_GLOBAL_Control
0x14017912b  mov     r9d, 22h ; '"'; int
0x140179131  mov     qword ptr [rsp+78h+var_48], 0; char
0x14017913a  mov     dl, 4; int
0x14017913c  mov     qword ptr [rsp+78h+var_50], rsi; char
0x140179141  mov     [rsp+78h+var_58], r13; struct _GUID *
0x140179146  mov     rcx, [rcx+40h]; int
0x14017914a  lea     r8d, [r9-21h]; int
0x14017914e  call    WPP_RECORDER_SF_qq
0x140179153  add     rsp, 48h
0x140179157  pop     r13
0x140179159  pop     r12
0x14017915b  pop     rdi
0x14017915c  pop     rsi
0x14017915d  pop     rbp
0x14017915e  pop     rbx
0x14017915f  retn
```
