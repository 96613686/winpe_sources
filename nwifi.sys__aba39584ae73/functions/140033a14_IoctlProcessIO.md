# IoctlProcessIO

- ea: `0x140033a14`
- end: `0x140033f28`
- name: `IoctlProcessIO`
- size: `1300`
- prototype: `__int64 __fastcall(struct _VELAN *, int, struct _IRP *)`
- caller_count: `2`
- callee_count: `25`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140020104`
- `0x1400334d0`

## callees

- `0x14000d21c`
- `0x140014950`
- `0x140014aec`
- `0x140015e24`
- `0x140019bbc`
- `0x140019e34`
- `0x14001efa8`
- `0x140033078`
- `0x140033408`
- `0x1400335a0`
- `0x140033620`
- `0x140033698`
- `0x140033758`
- `0x1400337fc`
- `0x1400338cc`
- `0x14003399c`
- `0x140033a14`
- `0x140033f8c`
- `0x140034038`
- `0x140034270`
- `0x140034c2c`
- `0x14003ece4`
- `0x140050224`
- `0x14005054c`
- `0x14009bbf0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140033a5e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033eaf`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033a5e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033eaf`
- `ntoskrnl!KeSetEvent` at `0x140033aaa`
- `ntoskrnl!KeSetEvent` at `0x140033ee1`
- `ntoskrnl!KeSetEvent` at `0x140033aaa`
- `ntoskrnl!KeSetEvent` at `0x140033ee1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140033e17`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140033e17`

## pseudocode

```c
__int64 __fastcall IoctlProcessIO(struct _VELAN *a1, int a2, struct _IRP *a3)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  _NWF_MUTEX *p_PnPMutex; // r13
  unsigned int Options; // ebx
  _ADAPT *pAdapt; // rax
  int v10; // r15d
  unsigned int v11; // ebx
  unsigned int LowPart; // eax
  int AdapterCapabilities; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  void *pVElanExt; // r10
  _MDL *MdlAddress; // rcx
  void *MappedSystemVa; // r8
  _ADAPT *v27; // rcx
  _ADAPT *v28; // rcx
  PVOID v29; // rax
  unsigned int Length; // [rsp+90h] [rbp+48h] BYREF

  CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
  p_PnPMutex = &a1->PnPMutex;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  KeWaitForSingleObject(&a1->PnPMutex, Executive, 0, 0, 0);
  p_PnPMutex->LockOwner = KeGetCurrentThread();
  pAdapt = a1->pAdapt;
  if ( !pAdapt || pAdapt->State == PT6_CLOSING )
  {
    v10 = 0;
  }
  else
  {
    _InterlockedAdd((volatile signed __int32 *)&a1->IoctlModule.uActiveIoctlRefCount, 1u);
    v10 = 1;
  }
  p_PnPMutex->LockOwner = 0;
  KeSetEvent(&p_PnPMutex->Event, 1, 0);
  if ( v10 )
  {
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    if ( LowPart <= 0x12C010 )
    {
      if ( LowPart == 1228816 )
      {
        AdapterCapabilities = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))IoctlCurrentOpMode)(
                                a1,
                                (_IRP::<unnamed_type_AssociatedIrp>)a3->AssociatedIrp.MasterIrp,
                                Options,
                                &Length);
        goto LABEL_70;
      }
      if ( LowPart > 0x128358 )
      {
        v14 = LowPart - 1213736;
        if ( !v14 )
        {
          AdapterCapabilities = IoctlGetAdapterCapabilities(a1, a3->AssociatedIrp.MasterIrp, &Length);
          goto LABEL_70;
        }
        v15 = v14 - 4;
        if ( !v15 )
        {
          AdapterCapabilities = IoctlGetBandCapabilities(a1, a3->AssociatedIrp.MasterIrp, &Length);
          goto LABEL_70;
        }
        v16 = v15 - 4;
        if ( !v16 )
        {
          AdapterCapabilities = IoctlGetVwifiAttributes(a1, a3->AssociatedIrp.MasterIrp, &Length);
          goto LABEL_70;
        }
        if ( v16 == 284 )
        {
          AdapterCapabilities = IoctlGetWifiCxAdapterInfo(a1, a3->AssociatedIrp.MasterIrp, &Length);
          goto LABEL_70;
        }
      }
      else
      {
        switch ( LowPart )
        {
          case 0x128358u:
            AdapterCapabilities = IoctlSetPMK(
                                    CurrentStackLocation->FileObject,
                                    (char *)a3->AssociatedIrp.MasterIrp,
                                    Options,
                                    &Length);
            goto LABEL_70;
          case 0x12400Cu:
            AdapterCapabilities = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))IoctlOpModeCapability)(
                                    a1,
                                    (_IRP::<unnamed_type_AssociatedIrp>)a3->AssociatedIrp.MasterIrp,
                                    Options,
                                    &Length);
            goto LABEL_70;
          case 0x124354u:
            v11 = -1073741822;
            goto LABEL_71;
          case 0x124558u:
            AdapterCapabilities = IoctlGetSupportedDeviceServices(a1, a3->AssociatedIrp.MasterIrp, &Length);
            goto LABEL_70;
          case 0x124664u:
            AdapterCapabilities = IoctlFipsCapabilities(a1, a3->AssociatedIrp.MasterIrp, Length, &Length);
            goto LABEL_70;
          case 0x128020u:
            AdapterCapabilities = IoctlReset(a1, a3);
            goto LABEL_70;
        }
      }
LABEL_50:
      pVElanExt = a1->pVElanExt;
      if ( !pVElanExt )
      {
        v11 = -1073741436;
        goto LABEL_71;
      }
      if ( (CurrentStackLocation->Parameters.Read.ByteOffset.LowPart & 3) == 2 )
      {
        MdlAddress = a3->MdlAddress;
        if ( (MdlAddress->MdlFlags & 5) != 0 )
        {
          MappedSystemVa = MdlAddress->MappedSystemVa;
        }
        else
        {
          v29 = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
          pVElanExt = a1->pVElanExt;
          MappedSystemVa = v29;
        }
        Length = a3->MdlAddress->ByteCount;
      }
      else
      {
        MappedSystemVa = a3->AssociatedIrp.MasterIrp;
      }
      AdapterCapabilities = a1->pDot11Driver->Dot11Ioctl(
                              pVElanExt,
                              a3,
                              a3->AssociatedIrp.MasterIrp,
                              Options,
                              MappedSystemVa,
                              &Length);
LABEL_70:
      v11 = AdapterCapabilities;
LABEL_71:
      KeWaitForSingleObject(p_PnPMutex, Executive, 0, 0, 0);
      p_PnPMutex->LockOwner = KeGetCurrentThread();
      _InterlockedDecrement((volatile signed __int32 *)&a1->IoctlModule.uActiveIoctlRefCount);
      p_PnPMutex->LockOwner = 0;
      KeSetEvent(&p_PnPMutex->Event, 1, 0);
      if ( v11 == 259 )
        return v11;
      goto LABEL_72;
    }
    if ( LowPart <= 0x12C39C )
    {
      if ( LowPart == 1229724 )
      {
        AdapterCapabilities = IoctlGetPmkIdList(
                                CurrentStackLocation->FileObject,
                                a3->AssociatedIrp.MasterIrp,
                                Options,
                                &Length);
        goto LABEL_70;
      }
      v17 = LowPart - 1229204;
      if ( !v17 )
      {
        AdapterCapabilities = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))IoctlNICSpecificExtension)(
                                a1,
                                (_IRP::<unnamed_type_AssociatedIrp>)a3->AssociatedIrp.MasterIrp,
                                Options,
                                &Length);
        goto LABEL_70;
      }
      v18 = v17 - 396;
      if ( !v18 )
      {
        AdapterCapabilities = IoctlSecurityProviderParameters(
                                CurrentStackLocation->FileObject,
                                a3->AssociatedIrp.MasterIrp,
                                Options,
                                &Length);
        goto LABEL_70;
      }
      v19 = v18 - 4;
      if ( !v19 )
      {
        AdapterCapabilities = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))IoctlActiveSecurityProvider)(
                                CurrentStackLocation->FileObject,
                                (_IRP::<unnamed_type_AssociatedIrp>)a3->AssociatedIrp.MasterIrp,
                                Options,
                                &Length);
        goto LABEL_70;
      }
      v20 = v19 - 68;
      if ( !v20 )
      {
        AdapterCapabilities = IoctlSafeModeEnabled(
                                CurrentStackLocation->FileObject,
                                a3->AssociatedIrp.MasterIrp,
                                Options,
                                &Length);
        goto LABEL_70;
      }
      if ( v20 == 8 )
      {
        AdapterCapabilities = IoctlSafeModeImplemented(
                                CurrentStackLocation->FileObject,
                                a3->AssociatedIrp.MasterIrp,
                                Options,
                                &Length);
        goto LABEL_70;
      }
      goto LABEL_50;
    }
    v21 = LowPart - 1230172;
    if ( !v21 )
    {
      AdapterCapabilities = IoctlDeviceServiceCommand(a1, a3->AssociatedIrp.MasterIrp, Options, &Length);
      goto LABEL_70;
    }
    v22 = v21 - 20;
    if ( !v22 )
    {
      AdapterCapabilities = IoctlGetBSSInfo(a1, a3->AssociatedIrp.MasterIrp, Options, &Length);
      goto LABEL_70;
    }
    v23 = v22 - 252;
    if ( v23 )
    {
      if ( v23 != 4 )
        goto LABEL_50;
    }
    else if ( (unsigned int)Feature_WiFiDirect2_Support__private_IsEnabledDeviceUsageNoInline()
           && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1230444 )
    {
      v27 = a1->pAdapt;
      if ( v27->AdapterEnhancedCapabilities.uWindowsWifiCxVersion )
      {
        AdapterCapabilities = PtRequestAdapterSync(v27, 1u, 0xE0102AAu, a3->AssociatedIrp.MasterIrp, Options);
        goto LABEL_70;
      }
      goto LABEL_57;
    }
    if ( !(unsigned int)Feature_WiFiDirect2_Support__private_IsEnabledDeviceUsageNoInline()
      || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1230448 )
    {
      goto LABEL_50;
    }
    v28 = a1->pAdapt;
    if ( v28->AdapterEnhancedCapabilities.uWindowsWifiCxVersion )
    {
      AdapterCapabilities = PtCallAdapterSync(v28, 0xE0102ABu, Options, Length, a3->AssociatedIrp.MasterIrp, &Length, 0);
      goto LABEL_70;
    }
LABEL_57:
    v11 = -1073741637;
    goto LABEL_71;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids);
  v11 = -1073741810;
LABEL_72:
  a3->IoStatus.Information = Length;
  a3->IoStatus.Status = v11;
  if ( a2 )
    CurrentStackLocation->Control &= ~1u;
  NWFCompleteIrp(a1, a3);
  return v11;
}

```

## disassembly

```asm
0x140033a14  push    rbp
0x140033a16  push    rbx
0x140033a17  push    rsi
0x140033a18  push    rdi
0x140033a19  push    r12
0x140033a1b  push    r13
0x140033a1d  push    r14
0x140033a1f  push    r15
0x140033a21  mov     rbp, rsp
0x140033a24  sub     rsp, 48h
0x140033a28  mov     r14, [r8+0B8h]
0x140033a2f  lea     r13, [rcx+1F70h]
0x140033a36  mov     rdi, r8
0x140033a39  mov     [rsp+48h+Timeout], 0; Timeout
0x140033a42  mov     r12d, edx
0x140033a45  mov     rsi, rcx
0x140033a48  xor     r9d, r9d; Alertable
0x140033a4b  xor     r8d, r8d; WaitMode
0x140033a4e  mov     ebx, [r14+10h]
0x140033a52  xor     edx, edx; WaitReason
0x140033a54  mov     eax, [r14+8]
0x140033a58  mov     rcx, r13; Object
0x140033a5b  mov     [rbp+arg_0], eax
0x140033a5e  call    cs:__imp_KeWaitForSingleObject
0x140033a65  nop     dword ptr [rax+rax+00h]
0x140033a6a  mov     rax, gs:188h
0x140033a73  mov     ecx, 1
0x140033a78  mov     [r13+18h], rax
0x140033a7c  mov     rax, [rsi+10h]
0x140033a80  test    rax, rax
0x140033a83  jz      short loc_140033A97
0x140033a85  cmp     dword ptr [rax+14h], 6
0x140033a89  jz      short loc_140033A97
0x140033a8b  lock add [rsi+15ECh], ecx
0x140033a92  mov     r15d, ecx
0x140033a95  jmp     short loc_140033A9A
0x140033a97  xor     r15d, r15d
0x140033a9a  mov     edx, ecx; Increment
0x140033a9c  mov     qword ptr [r13+18h], 0
0x140033aa4  mov     rcx, r13; Event
0x140033aa7  xor     r8d, r8d; Wait
0x140033aaa  call    cs:__imp_KeSetEvent
0x140033ab1  nop     dword ptr [rax+rax+00h]
0x140033ab6  test    r15d, r15d
0x140033ab9  jnz     short loc_140033AEC
0x140033abb  mov     rcx, cs:WPP_GLOBAL_Control
0x140033ac2  lea     rax, WPP_GLOBAL_Control
0x140033ac9  cmp     rcx, rax
0x140033acc  jz      short loc_140033AE2
0x140033ace  mov     rcx, [rcx+18h]
0x140033ad2  lea     edx, [r15+16h]
0x140033ad6  lea     r8, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids
0x140033add  call    WPP_SF_
0x140033ae2  mov     ebx, 0C000000Eh
0x140033ae7  jmp     loc_140033EF5
0x140033aec  mov     eax, [r14+18h]
0x140033af0  mov     ecx, 12C010h
0x140033af5  cmp     eax, ecx
0x140033af7  ja      loc_140033C3E
0x140033afd  jz      loc_140033C26
0x140033b03  mov     ecx, 128358h
0x140033b08  cmp     eax, ecx
0x140033b0a  ja      loc_140033BB6
0x140033b10  jz      loc_140033B9D
0x140033b16  cmp     eax, 12400Ch
0x140033b1b  jz      short loc_140033B85
0x140033b1d  cmp     eax, 124354h
0x140033b22  jz      short loc_140033B7B
0x140033b24  cmp     eax, 124558h
0x140033b29  jz      short loc_140033B66
0x140033b2b  cmp     eax, 124664h
0x140033b30  jz      short loc_140033B4D
0x140033b32  cmp     eax, 128020h
0x140033b37  jnz     loc_140033D27
0x140033b3d  mov     rdx, rdi; struct _IRP *
0x140033b40  mov     rcx, rsi; struct _VELAN *
0x140033b43  call    ?IoctlReset@@YAJPEAU_VELAN@@PEAU_IRP@@@Z; IoctlReset(_VELAN *,_IRP *)
0x140033b48  jmp     loc_140033E99
0x140033b4d  mov     r8d, [rbp+arg_0]; unsigned int
0x140033b51  lea     r9, [rbp+arg_0]; unsigned int *
0x140033b55  mov     rdx, [rdi+18h]; void *
0x140033b59  mov     rcx, rsi; struct _VELAN *
0x140033b5c  call    ?IoctlFipsCapabilities@@YAJQEAU_VELAN@@QEAXKQEAK@Z; IoctlFipsCapabilities(_VELAN * const,void * const,ulong,ulong * const)
0x140033b61  jmp     loc_140033E99
0x140033b66  mov     rdx, [rdi+18h]; void *
0x140033b6a  lea     r8, [rbp+arg_0]; unsigned int *
0x140033b6e  mov     rcx, rsi; struct _VELAN *
0x140033b71  call    ?IoctlGetSupportedDeviceServices@@YAJPEAU_VELAN@@PEAXPEAK@Z; IoctlGetSupportedDeviceServices(_VELAN *,void *,ulong *)
0x140033b76  jmp     loc_140033E99
0x140033b7b  mov     ebx, 0C0000002h
0x140033b80  jmp     loc_140033E9B
0x140033b85  mov     rdx, [rdi+18h]
0x140033b89  lea     r9, [rbp+arg_0]
0x140033b8d  mov     r8d, ebx
0x140033b90  mov     rcx, rsi
0x140033b93  call    IoctlOpModeCapability
0x140033b98  jmp     loc_140033E99
0x140033b9d  mov     rdx, [rdi+18h]; void *
0x140033ba1  lea     r9, [rbp+arg_0]; unsigned int *
0x140033ba5  mov     rcx, [r14+30h]; struct _FILE_OBJECT *
0x140033ba9  mov     r8d, ebx; unsigned int
0x140033bac  call    ?IoctlSetPMK@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z; IoctlSetPMK(_FILE_OBJECT *,void *,ulong,ulong *)
0x140033bb1  jmp     loc_140033E99
0x140033bb6  sub     eax, 128528h
0x140033bbb  jz      short loc_140033C11
0x140033bbd  sub     eax, 4
0x140033bc0  jz      short loc_140033BFC
0x140033bc2  sub     eax, 4
0x140033bc5  jz      short loc_140033BE7
0x140033bc7  cmp     eax, 11Ch
0x140033bcc  jnz     loc_140033D27
0x140033bd2  mov     rdx, [rdi+18h]; void *
0x140033bd6  lea     r8, [rbp+arg_0]; unsigned int *
0x140033bda  mov     rcx, rsi; struct _VELAN *
0x140033bdd  call    ?IoctlGetWifiCxAdapterInfo@@YAJPEAU_VELAN@@PEAXPEAK@Z; IoctlGetWifiCxAdapterInfo(_VELAN *,void *,ulong *)
0x140033be2  jmp     loc_140033E99
0x140033be7  mov     rdx, [rdi+18h]; void *
0x140033beb  lea     r8, [rbp+arg_0]; unsigned int *
0x140033bef  mov     rcx, rsi; struct _VELAN *
0x140033bf2  call    ?IoctlGetVwifiAttributes@@YAJPEAU_VELAN@@PEAXPEAK@Z; IoctlGetVwifiAttributes(_VELAN *,void *,ulong *)
0x140033bf7  jmp     loc_140033E99
0x140033bfc  mov     rdx, [rdi+18h]; void *
0x140033c00  lea     r8, [rbp+arg_0]; unsigned int *
0x140033c04  mov     rcx, rsi; struct _VELAN *
0x140033c07  call    ?IoctlGetBandCapabilities@@YAJPEAU_VELAN@@PEAXPEAK@Z; IoctlGetBandCapabilities(_VELAN *,void *,ulong *)
0x140033c0c  jmp     loc_140033E99
0x140033c11  mov     rdx, [rdi+18h]; void *
0x140033c15  lea     r8, [rbp+arg_0]; unsigned int *
0x140033c19  mov     rcx, rsi; struct _VELAN *
0x140033c1c  call    ?IoctlGetAdapterCapabilities@@YAJPEAU_VELAN@@PEAXPEAK@Z; IoctlGetAdapterCapabilities(_VELAN *,void *,ulong *)
0x140033c21  jmp     loc_140033E99
0x140033c26  mov     rdx, [rdi+18h]
0x140033c2a  lea     r9, [rbp+arg_0]
0x140033c2e  mov     r8d, ebx
0x140033c31  mov     rcx, rsi
0x140033c34  call    IoctlCurrentOpMode
0x140033c39  jmp     loc_140033E99
0x140033c3e  mov     ecx, 12C39Ch
0x140033c43  cmp     eax, ecx
0x140033c45  ja      loc_140033D07
0x140033c4b  jz      loc_140033CEE
0x140033c51  sub     eax, 12C194h
0x140033c56  jz      short loc_140033CD6
0x140033c58  sub     eax, 18Ch
0x140033c5d  jz      short loc_140033CBD
0x140033c5f  sub     eax, 4
0x140033c62  jz      short loc_140033CA4
0x140033c64  sub     eax, 44h ; 'D'
0x140033c67  jz      short loc_140033C8B
0x140033c69  cmp     eax, 8
0x140033c6c  jnz     loc_140033D27
0x140033c72  mov     rdx, [rdi+18h]; void *
0x140033c76  lea     r9, [rbp+arg_0]; unsigned int *
0x140033c7a  mov     rcx, [r14+30h]; struct _FILE_OBJECT *
0x140033c7e  mov     r8d, ebx; unsigned int
0x140033c81  call    ?IoctlSafeModeImplemented@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z; IoctlSafeModeImplemented(_FILE_OBJECT *,void *,ulong,ulong *)
0x140033c86  jmp     loc_140033E99
0x140033c8b  mov     rdx, [rdi+18h]; void *
0x140033c8f  lea     r9, [rbp+arg_0]; unsigned int *
0x140033c93  mov     rcx, [r14+30h]; struct _FILE_OBJECT *
0x140033c97  mov     r8d, ebx; unsigned int
0x140033c9a  call    ?IoctlSafeModeEnabled@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z; IoctlSafeModeEnabled(_FILE_OBJECT *,void *,ulong,ulong *)
0x140033c9f  jmp     loc_140033E99
0x140033ca4  mov     rdx, [rdi+18h]
0x140033ca8  lea     r9, [rbp+arg_0]
0x140033cac  mov     rcx, [r14+30h]
0x140033cb0  mov     r8d, ebx
0x140033cb3  call    IoctlActiveSecurityProvider
0x140033cb8  jmp     loc_140033E99
0x140033cbd  mov     rdx, [rdi+18h]; void *
0x140033cc1  lea     r9, [rbp+arg_0]; unsigned int *
0x140033cc5  mov     rcx, [r14+30h]; struct _FILE_OBJECT *
0x140033cc9  mov     r8d, ebx; unsigned int
0x140033ccc  call    ?IoctlSecurityProviderParameters@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z; IoctlSecurityProviderParameters(_FILE_OBJECT *,void *,ulong,ulong *)
0x140033cd1  jmp     loc_140033E99
0x140033cd6  mov     rdx, [rdi+18h]
0x140033cda  lea     r9, [rbp+arg_0]
0x140033cde  mov     r8d, ebx
0x140033ce1  mov     rcx, rsi
0x140033ce4  call    IoctlNICSpecificExtension
0x140033ce9  jmp     loc_140033E99
0x140033cee  mov     rdx, [rdi+18h]; void *
0x140033cf2  lea     r9, [rbp+arg_0]; unsigned int *
0x140033cf6  mov     rcx, [r14+30h]; struct _FILE_OBJECT *
0x140033cfa  mov     r8d, ebx; unsigned int
0x140033cfd  call    ?IoctlGetPmkIdList@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z; IoctlGetPmkIdList(_FILE_OBJECT *,void *,ulong,ulong *)
0x140033d02  jmp     loc_140033E99
0x140033d07  sub     eax, 12C55Ch
0x140033d0c  jz      loc_140033E86
0x140033d12  sub     eax, 14h
0x140033d15  jz      loc_140033E71
0x140033d1b  sub     eax, 0FCh
0x140033d20  jz      short loc_140033D5C
0x140033d22  cmp     eax, 4
0x140033d25  jz      short loc_140033DA4
0x140033d27  mov     r10, [rsi+1F68h]
0x140033d2e  test    r10, r10
0x140033d31  jz      loc_140033E6A
0x140033d37  mov     eax, [r14+18h]
0x140033d3b  and     al, 3
0x140033d3d  cmp     al, 2
0x140033d3f  jnz     loc_140033E39
0x140033d45  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140033d49  test    byte ptr [rcx+0Ah], 5
0x140033d4d  jz      loc_140033DFE
0x140033d53  mov     r8, [rcx+18h]
0x140033d57  jmp     loc_140033E2D
0x140033d5c  call    Feature_WiFiDirect2_Support__private_IsEnabledDeviceUsageNoInline
0x140033d61  test    eax, eax
0x140033d63  jz      short loc_140033DA4
0x140033d65  cmp     dword ptr [r14+18h], 12C66Ch
0x140033d6d  jnz     short loc_140033DA4
0x140033d6f  mov     rcx, [rsi+10h]; struct _ADAPT *
0x140033d73  cmp     qword ptr [rcx+610h], 0
0x140033d7b  jnz     short loc_140033D87
0x140033d7d  mov     ebx, 0C00000BBh
0x140033d82  jmp     loc_140033E9B
0x140033d87  mov     r9, [rdi+18h]; void *
0x140033d8b  mov     edx, 1; unsigned int
0x140033d90  mov     r8d, 0E0102AAh; unsigned int
0x140033d96  mov     dword ptr [rsp+48h+Timeout], ebx; unsigned int
0x140033d9a  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140033d9f  jmp     loc_140033E99
0x140033da4  call    Feature_WiFiDirect2_Support__private_IsEnabledDeviceUsageNoInline
0x140033da9  test    eax, eax
0x140033dab  jz      loc_140033D27
0x140033db1  cmp     dword ptr [r14+18h], 12C670h
0x140033db9  jnz     loc_140033D27
0x140033dbf  mov     rcx, [rsi+10h]; struct _ADAPT *
0x140033dc3  cmp     qword ptr [rcx+610h], 0
0x140033dcb  jz      short loc_140033D7D
0x140033dcd  mov     r9d, [rbp+arg_0]; unsigned int
0x140033dd1  lea     rax, [rbp+arg_0]
0x140033dd5  mov     [rsp+48h+var_18], 0; unsigned int *
0x140033dde  mov     r8d, ebx; unsigned int
0x140033de1  mov     qword ptr [rsp+48h+Priority], rax; unsigned int *
0x140033de6  mov     edx, 0E0102ABh; unsigned int
0x140033deb  mov     rax, [rdi+18h]
0x140033def  mov     [rsp+48h+Timeout], rax; void *
0x140033df4  call    ?PtCallAdapterSync@@YAHPEAU_ADAPT@@KKKPEAXPEAK2@Z; PtCallAdapterSync(_ADAPT *,ulong,ulong,ulong,void *,ulong *,ulong *)
0x140033df9  jmp     loc_140033E99
0x140033dfe  xor     r9d, r9d; RequestedAddress
0x140033e01  mov     [rsp+48h+Priority], 40000010h; Priority
0x140033e09  xor     edx, edx; AccessMode
0x140033e0b  mov     dword ptr [rsp+48h+Timeout], 0; BugCheckOnFailure
0x140033e13  lea     r8d, [r9+1]; CacheType
0x140033e17  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140033e1e  nop     dword ptr [rax+rax+00h]
0x140033e23  mov     r10, [rsi+1F68h]
0x140033e2a  mov     r8, rax
0x140033e2d  mov     rcx, [rdi+8]
0x140033e31  mov     edx, [rcx+28h]
0x140033e34  mov     [rbp+arg_0], edx
0x140033e37  jmp     short loc_140033E3D
0x140033e39  mov     r8, [rdi+18h]
0x140033e3d  mov     rax, [rsi+98h]
0x140033e44  lea     rcx, [rbp+arg_0]
0x140033e48  mov     qword ptr [rsp+48h+Priority], rcx
0x140033e4d  mov     r9d, ebx
0x140033e50  mov     [rsp+48h+Timeout], r8
0x140033e55  mov     rdx, rdi
0x140033e58  mov     r8, [rdi+18h]
0x140033e5c  mov     rcx, r10
0x140033e5f  mov     rax, [rax+60h]
0x140033e63  call    _guard_dispatch_icall
0x140033e68  jmp     short loc_140033E99
0x140033e6a  mov     ebx, 0C0000184h
0x140033e6f  jmp     short loc_140033E9B
0x140033e71  mov     rdx, [rdi+18h]; void *
0x140033e75  lea     r9, [rbp+arg_0]; unsigned int *
0x140033e79  mov     r8d, ebx; unsigned int
0x140033e7c  mov     rcx, rsi; struct _VELAN *
0x140033e7f  call    ?IoctlGetBSSInfo@@YAJPEAU_VELAN@@PEAXKPEAK@Z; IoctlGetBSSInfo(_VELAN *,void *,ulong,ulong *)
0x140033e84  jmp     short loc_140033E99
0x140033e86  mov     rdx, [rdi+18h]; void *
0x140033e8a  lea     r9, [rbp+arg_0]; unsigned int *
0x140033e8e  mov     r8d, ebx; unsigned int
0x140033e91  mov     rcx, rsi; struct _VELAN *
0x140033e94  call    ?IoctlDeviceServiceCommand@@YAJPEAU_VELAN@@PEAXKPEAK@Z; IoctlDeviceServiceCommand(_VELAN *,void *,ulong,ulong *)
0x140033e99  mov     ebx, eax
0x140033e9b  xor     r9d, r9d; Alertable
0x140033e9e  mov     [rsp+48h+Timeout], 0; Timeout
0x140033ea7  xor     r8d, r8d; WaitMode
0x140033eaa  xor     edx, edx; WaitReason
0x140033eac  mov     rcx, r13; Object
0x140033eaf  call    cs:__imp_KeWaitForSingleObject
0x140033eb6  nop     dword ptr [rax+rax+00h]
0x140033ebb  mov     rax, gs:188h
0x140033ec4  xor     r8d, r8d; Wait
0x140033ec7  mov     [r13+18h], rax
0x140033ecb  mov     rcx, r13; Event
0x140033ece  lock dec dword ptr [rsi+15ECh]
0x140033ed5  mov     qword ptr [r13+18h], 0
0x140033edd  lea     edx, [r8+1]; Increment
0x140033ee1  call    cs:__imp_KeSetEvent
0x140033ee8  nop     dword ptr [rax+rax+00h]
0x140033eed  cmp     ebx, 103h
0x140033ef3  jz      short loc_140033F14
0x140033ef5  mov     eax, [rbp+arg_0]
0x140033ef8  mov     [rdi+38h], rax
  ... truncated ...
```
