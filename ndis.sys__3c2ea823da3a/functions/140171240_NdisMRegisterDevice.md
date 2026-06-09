# NdisMRegisterDevice

- ea: `0x140171240`
- end: `0x14017152d`
- name: `NdisMRegisterDevice`
- size: `749`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE NdisWrapperHandle, PNDIS_STRING DeviceName, PNDIS_STRING SymbolicName, PDRIVER_DISPATCH *MajorFunctions, PDEVICE_OBJECT *pDeviceObject, NDIS_HANDLE *NdisDeviceHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, loader_planting, installer_update`

## callees

- `0x14003d920`
- `0x14004e050`
- `0x1400e62c0`
- `0x1400e65c0`
- `0x140171240`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x140171286`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140171286`
- `ntoskrnl!IoCreateDevice` at `0x1401712d1`
- `ntoskrnl!IoCreateDevice` at `0x1401712d1`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1401712fa`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1401712fa`
- `ntoskrnl!IoDeleteDevice` at `0x140171314`
- `ntoskrnl!IoDeleteDevice` at `0x140171314`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401714e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401714e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401714ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401714ae`

## pseudocode

```c
NDIS_STATUS __stdcall NdisMRegisterDevice(
        NDIS_HANDLE NdisWrapperHandle,
        PNDIS_STRING DeviceName,
        PNDIS_STRING SymbolicName,
        PDRIVER_DISPATCH *MajorFunctions,
        PDEVICE_OBJECT *pDeviceObject,
        NDIS_HANDLE *NdisDeviceHandle)
{
  PDEVICE_OBJECT *v6; // r12
  NDIS_HANDLE *v7; // r13
  char *DriverObjectExtension; // rbp
  NTSTATUS SymbolicLink; // edi
  unsigned int v12; // ebx
  _WORD *DeviceExtension; // r14
  _QWORD *v14; // rbx
  PDRIVER_DISPATCH *v15; // rax
  void *v16; // rcx
  KSPIN_LOCK *v17; // rsi
  KIRQL v18; // al
  char *v19; // rbp
  __int64 v20; // rcx
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp+8h] BYREF
  PDRIVER_DISPATCH *v23; // [rsp+98h] [rbp+20h]

  v23 = MajorFunctions;
  v6 = pDeviceObject;
  v7 = NdisDeviceHandle;
  DeviceObject = 0;
  *pDeviceObject = 0;
  *v7 = 0;
  DriverObjectExtension = (char *)IoGetDriverObjectExtension(*(PDRIVER_OBJECT *)NdisWrapperHandle, (PVOID)0x4E4D4944);
  if ( !DriverObjectExtension )
    return -1073741637;
  SymbolicLink = IoCreateDevice(
                   *((PDRIVER_OBJECT *)DriverObjectExtension + 5),
                   SymbolicName->Length + 308 + DeviceName->Length,
                   DeviceName,
                   0x12u,
                   0x100u,
                   0,
                   &DeviceObject);
  if ( SymbolicLink >= 0 )
  {
    DeviceObject->Flags &= ~0x80u;
    SymbolicLink = IoCreateSymbolicLink(SymbolicName, DeviceName);
    if ( SymbolicLink >= 0 )
    {
      v12 = DeviceName->Length + 308 + SymbolicName->Length;
      DeviceExtension = DeviceObject->DeviceExtension;
      memset(DeviceExtension, 0, v12);
      DeviceExtension[1] = v12;
      *DeviceExtension = 265;
      v14 = DeviceExtension + 4;
      *((_QWORD *)DeviceExtension + 2) = DeviceExtension + 4;
      *((_QWORD *)DeviceExtension + 1) = DeviceExtension + 4;
      *((_QWORD *)DeviceExtension + 3) = DriverObjectExtension;
      *((_QWORD *)DeviceExtension + 4) = DeviceObject;
      v15 = v23;
      *((_OWORD *)DeviceExtension + 3) = *(_OWORD *)v23;
      *((_OWORD *)DeviceExtension + 4) = *((_OWORD *)v15 + 1);
      *((_OWORD *)DeviceExtension + 5) = *((_OWORD *)v15 + 2);
      *((_OWORD *)DeviceExtension + 6) = *((_OWORD *)v15 + 3);
      *((_OWORD *)DeviceExtension + 7) = *((_OWORD *)v15 + 4);
      *((_OWORD *)DeviceExtension + 8) = *((_OWORD *)v15 + 5);
      *((_OWORD *)DeviceExtension + 9) = *((_OWORD *)v15 + 6);
      *((_OWORD *)DeviceExtension + 10) = *((_OWORD *)v15 + 7);
      *((_OWORD *)DeviceExtension + 11) = *((_OWORD *)v15 + 8);
      *((_OWORD *)DeviceExtension + 12) = *((_OWORD *)v15 + 9);
      *((_OWORD *)DeviceExtension + 13) = *((_OWORD *)v15 + 10);
      *((_OWORD *)DeviceExtension + 14) = *((_OWORD *)v15 + 11);
      *((_OWORD *)DeviceExtension + 15) = *((_OWORD *)v15 + 12);
      *((_QWORD *)DeviceExtension + 32) = v15[26];
      *((_QWORD *)DeviceExtension + 35) = DeviceExtension + 152;
      DeviceExtension[136] = DeviceName->Length;
      DeviceExtension[137] = DeviceName->Length + 2;
      memmove(DeviceExtension + 152, DeviceName->Buffer, DeviceName->Length);
      v16 = (void *)(*((_QWORD *)DeviceExtension + 35) + (unsigned __int16)DeviceExtension[137]);
      *((_QWORD *)DeviceExtension + 37) = v16;
      DeviceExtension[144] = SymbolicName->Length;
      DeviceExtension[145] = SymbolicName->Length + 2;
      memmove(v16, SymbolicName->Buffer, SymbolicName->Length);
      ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
      v17 = (KSPIN_LOCK *)(DriverObjectExtension + 392);
      v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)DriverObjectExtension + 49);
      v19 = DriverObjectExtension + 80;
      v20 = *(_QWORD *)v19;
      if ( *(char **)(*(_QWORD *)v19 + 8LL) != v19 )
        __fastfail(3u);
      *v14 = v20;
      *((_QWORD *)DeviceExtension + 2) = v19;
      *(_QWORD *)(v20 + 8) = v14;
      *(_QWORD *)v19 = v14;
      KeReleaseSpinLock(v17, v18);
      ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
      *v6 = DeviceObject;
      *v7 = DeviceExtension;
    }
    else
    {
      IoDeleteDevice(DeviceObject);
    }
  }
  return SymbolicLink;
}

```

## disassembly

```asm
0x140171240  mov     rax, rsp
0x140171243  mov     [rax+10h], rbx
0x140171247  mov     [rax+20h], r9
0x14017124b  push    rbp
0x14017124c  push    rsi
0x14017124d  push    rdi
0x14017124e  push    r12
0x140171250  push    r13
0x140171252  push    r14
0x140171254  push    r15
0x140171256  sub     rsp, 40h
0x14017125a  mov     r12, [rsp+78h+pDeviceObject]
0x140171262  xor     ebx, ebx
0x140171264  mov     r13, [rsp+78h+NdisDeviceHandle]
0x14017126c  mov     rsi, rdx
0x14017126f  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x140171274  mov     [rax+8], rbx
0x140171278  mov     r15, r8
0x14017127b  mov     [r12], rbx
0x14017127f  mov     [r13+0], rbx
0x140171283  mov     rcx, [rcx]; DriverObject
0x140171286  call    cs:__imp_IoGetDriverObjectExtension
0x14017128d  nop     dword ptr [rax+rax+00h]
0x140171292  mov     rbp, rax
0x140171295  test    rax, rax
0x140171298  jz      loc_14017150D
0x14017129e  movzx   ecx, word ptr [r15]
0x1401712a2  lea     rax, [rsp+78h+arg_0]
0x1401712aa  movzx   edx, word ptr [rsi]
0x1401712ad  lea     r9d, [rbx+12h]; DeviceType
0x1401712b1  add     ecx, 134h
0x1401712b7  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x1401712bc  add     edx, ecx; DeviceExtensionSize
0x1401712be  mov     [rsp+78h+Exclusive], bl; Exclusive
0x1401712c2  mov     rcx, [rbp+28h]; DriverObject
0x1401712c6  mov     r8, rsi; DeviceName
0x1401712c9  mov     [rsp+78h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x1401712d1  call    cs:__imp_IoCreateDevice
0x1401712d8  nop     dword ptr [rax+rax+00h]
0x1401712dd  mov     edi, eax
0x1401712df  test    eax, eax
0x1401712e1  js      loc_140171512
0x1401712e7  mov     rax, [rsp+78h+arg_0]
0x1401712ef  mov     rdx, rsi; DeviceName
0x1401712f2  mov     rcx, r15; SymbolicLinkName
0x1401712f5  btr     dword ptr [rax+30h], 7
0x1401712fa  call    cs:__imp_IoCreateSymbolicLink
0x140171301  nop     dword ptr [rax+rax+00h]
0x140171306  mov     edi, eax
0x140171308  test    eax, eax
0x14017130a  jns     short loc_140171325
0x14017130c  mov     rcx, [rsp+78h+arg_0]; DeviceObject
0x140171314  call    cs:__imp_IoDeleteDevice
0x14017131b  nop     dword ptr [rax+rax+00h]
0x140171320  jmp     loc_140171512
0x140171325  movzx   ecx, word ptr [rsi]
0x140171328  xor     edx, edx; Val
0x14017132a  mov     rax, [rsp+78h+arg_0]
0x140171332  add     ecx, 134h
0x140171338  movzx   ebx, word ptr [r15]
0x14017133c  add     ebx, ecx
0x14017133e  mov     r8d, ebx; Size
0x140171341  mov     r14, [rax+40h]
0x140171345  mov     rcx, r14; void *
0x140171348  call    memset
0x14017134d  mov     [r14+2], bx
0x140171352  lea     rcx, [r14+130h]; void *
0x140171359  mov     word ptr [r14], 109h
0x14017135f  lea     rbx, [r14+8]
0x140171363  mov     [rbx+8], rbx
0x140171367  mov     [rbx], rbx
0x14017136a  mov     [r14+18h], rbp
0x14017136e  mov     rax, [rsp+78h+arg_0]
0x140171376  mov     [r14+20h], rax
0x14017137a  mov     rax, [rsp+78h+arg_18]
0x140171382  movups  xmm0, xmmword ptr [rax]
0x140171385  movups  xmmword ptr [r14+30h], xmm0
0x14017138a  movups  xmm1, xmmword ptr [rax+10h]
0x14017138e  movups  xmmword ptr [r14+40h], xmm1
0x140171393  movups  xmm0, xmmword ptr [rax+20h]
0x140171397  movups  xmmword ptr [r14+50h], xmm0
0x14017139c  movups  xmm1, xmmword ptr [rax+30h]
0x1401713a0  movups  xmmword ptr [r14+60h], xmm1
0x1401713a5  movups  xmm0, xmmword ptr [rax+40h]
0x1401713a9  movups  xmmword ptr [r14+70h], xmm0
0x1401713ae  movups  xmm1, xmmword ptr [rax+50h]
0x1401713b2  movups  xmmword ptr [r14+80h], xmm1
0x1401713ba  movups  xmm0, xmmword ptr [rax+60h]
0x1401713be  movups  xmmword ptr [r14+90h], xmm0
0x1401713c6  movups  xmm1, xmmword ptr [rax+70h]
0x1401713ca  movups  xmmword ptr [r14+0A0h], xmm1
0x1401713d2  movups  xmm0, xmmword ptr [rax+80h]
0x1401713d9  movups  xmmword ptr [r14+0B0h], xmm0
0x1401713e1  movups  xmm1, xmmword ptr [rax+90h]
0x1401713e8  movups  xmmword ptr [r14+0C0h], xmm1
0x1401713f0  movups  xmm0, xmmword ptr [rax+0A0h]
0x1401713f7  movups  xmmword ptr [r14+0D0h], xmm0
0x1401713ff  movups  xmm1, xmmword ptr [rax+0B0h]
0x140171406  movups  xmmword ptr [r14+0E0h], xmm1
0x14017140e  movups  xmm0, xmmword ptr [rax+0C0h]
0x140171415  movups  xmmword ptr [r14+0F0h], xmm0
0x14017141d  mov     rax, [rax+0D0h]
0x140171424  mov     [r14+100h], rax
0x14017142b  mov     [r14+118h], rcx
0x140171432  movzx   eax, word ptr [rsi]
0x140171435  mov     [r14+110h], ax
0x14017143d  movzx   eax, word ptr [rsi]
0x140171440  add     ax, 2
0x140171444  mov     [r14+112h], ax
0x14017144c  movzx   r8d, word ptr [rsi]; Size
0x140171450  mov     rdx, [rsi+8]; Src
0x140171454  call    memmove
0x140171459  movzx   ecx, word ptr [r14+112h]
0x140171461  add     rcx, [r14+118h]; void *
0x140171468  mov     [r14+128h], rcx
0x14017146f  movzx   eax, word ptr [r15]
0x140171473  mov     [r14+120h], ax
0x14017147b  movzx   eax, word ptr [r15]
0x14017147f  add     ax, 2
0x140171483  mov     [r14+122h], ax
0x14017148b  movzx   r8d, word ptr [r15]; Size
0x14017148f  mov     rdx, [r15+8]; Src
0x140171493  call    memmove
0x140171498  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14017149f  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x1401714a4  lea     rsi, [rbp+188h]
0x1401714ab  mov     rcx, rsi; SpinLock
0x1401714ae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1401714b5  nop     dword ptr [rax+rax+00h]
0x1401714ba  add     rbp, 50h ; 'P'
0x1401714be  mov     rcx, [rbp+0]
0x1401714c2  cmp     [rcx+8], rbp
0x1401714c6  jz      short loc_1401714CF
0x1401714c8  mov     ecx, 3
0x1401714cd  int     29h; Win8: RtlFailFast(ecx)
0x1401714cf  mov     [rbx], rcx
0x1401714d2  mov     dl, al; NewIrql
0x1401714d4  mov     [rbx+8], rbp
0x1401714d8  mov     [rcx+8], rbx
0x1401714dc  mov     rcx, rsi; SpinLock
0x1401714df  mov     [rbp+0], rbx
0x1401714e3  call    cs:__imp_KeReleaseSpinLock
0x1401714ea  nop     dword ptr [rax+rax+00h]
0x1401714ef  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x1401714f6  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x1401714fb  mov     rax, [rsp+78h+arg_0]
0x140171503  mov     [r12], rax
0x140171507  mov     [r13+0], r14
0x14017150b  jmp     short loc_140171512
0x14017150d  mov     edi, 0C00000BBh
0x140171512  mov     rbx, [rsp+78h+arg_8]
0x14017151a  mov     eax, edi
0x14017151c  add     rsp, 40h
0x140171520  pop     r15
0x140171522  pop     r14
0x140171524  pop     r13
0x140171526  pop     r12
0x140171528  pop     rdi
0x140171529  pop     rsi
0x14017152a  pop     rbp
0x14017152b  retn
```
