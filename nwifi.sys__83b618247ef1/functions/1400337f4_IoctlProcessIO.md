# IoctlProcessIO

- ea: `0x1400337f4`
- end: `0x140033d08`
- name: `IoctlProcessIO`
- size: `1300`
- prototype: `__int64 __fastcall(struct _VELAN *, int, struct _IRP *)`
- caller_count: `2`
- callee_count: `25`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140020104`
- `0x1400332b0`

## callees

- `0x14000d22c`
- `0x140014960`
- `0x140014afc`
- `0x140015e34`
- `0x140019bbc`
- `0x140019e34`
- `0x14001efa8`
- `0x140032e58`
- `0x1400331e8`
- `0x140033380`
- `0x140033400`
- `0x140033478`
- `0x140033538`
- `0x1400335dc`
- `0x1400336ac`
- `0x14003377c`
- `0x1400337f4`
- `0x140033d6c`
- `0x140033e18`
- `0x140034050`
- `0x140034a0c`
- `0x14003eac4`
- `0x14004ea64`
- `0x14004ed8c`
- `0x14009a410`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14003383e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033c8f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003383e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033c8f`
- `ntoskrnl!KeSetEvent` at `0x14003388a`
- `ntoskrnl!KeSetEvent` at `0x140033cc1`
- `ntoskrnl!KeSetEvent` at `0x14003388a`
- `ntoskrnl!KeSetEvent` at `0x140033cc1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140033bf7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140033bf7`

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
                                    a3->AssociatedIrp.MasterIrp,
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
0x1400337f4  push    rbp
0x1400337f6  push    rbx
0x1400337f7  push    rsi
0x1400337f8  push    rdi
0x1400337f9  push    r12
0x1400337fb  push    r13
0x1400337fd  push    r14
0x1400337ff  push    r15
0x140033801  mov     rbp, rsp
0x140033804  sub     rsp, 48h
0x140033808  mov     r14, [r8+0B8h]
0x14003380f  lea     r13, [rcx+1F70h]
0x140033816  mov     rdi, r8
0x140033819  mov     [rsp+48h+Timeout], 0; Timeout
0x140033822  mov     r12d, edx
0x140033825  mov     rsi, rcx
0x140033828  xor     r9d, r9d; Alertable
0x14003382b  xor     r8d, r8d; WaitMode
0x14003382e  mov     ebx, [r14+10h]
0x140033832  xor     edx, edx; WaitReason
0x140033834  mov     eax, [r14+8]
0x140033838  mov     rcx, r13; Object
0x14003383b  mov     [rbp+arg_0], eax
0x14003383e  call    cs:__imp_KeWaitForSingleObject
0x140033845  nop     dword ptr [rax+rax+00h]
0x14003384a  mov     rax, gs:188h
0x140033853  mov     ecx, 1
0x140033858  mov     [r13+18h], rax
0x14003385c  mov     rax, [rsi+10h]
0x140033860  test    rax, rax
0x140033863  jz      short loc_140033877
0x140033865  cmp     dword ptr [rax+14h], 6
0x140033869  jz      short loc_140033877
0x14003386b  lock add [rsi+15ECh], ecx
0x140033872  mov     r15d, ecx
0x140033875  jmp     short loc_14003387A
0x140033877  xor     r15d, r15d
0x14003387a  mov     edx, ecx; Increment
0x14003387c  mov     qword ptr [r13+18h], 0
0x140033884  mov     rcx, r13; Event
0x140033887  xor     r8d, r8d; Wait
0x14003388a  call    cs:__imp_KeSetEvent
0x140033891  nop     dword ptr [rax+rax+00h]
0x140033896  test    r15d, r15d
0x140033899  jnz     short loc_1400338CC
0x14003389b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400338a2  lea     rax, WPP_GLOBAL_Control
0x1400338a9  cmp     rcx, rax
0x1400338ac  jz      short loc_1400338C2
0x1400338ae  mov     rcx, [rcx+18h]
0x1400338b2  lea     edx, [r15+16h]
0x1400338b6  lea     r8, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids
0x1400338bd  call    WPP_SF_
0x1400338c2  mov     ebx, 0C000000Eh
0x1400338c7  jmp     loc_140033CD5
0x1400338cc  mov     eax, [r14+18h]
0x1400338d0  mov     ecx, 12C010h
0x1400338d5  cmp     eax, ecx
0x1400338d7  ja      loc_140033A1E
0x1400338dd  jz      loc_140033A06
0x1400338e3  mov     ecx, 128358h
0x1400338e8  cmp     eax, ecx
0x1400338ea  ja      loc_140033996
0x1400338f0  jz      loc_14003397D
0x1400338f6  cmp     eax, 12400Ch
0x1400338fb  jz      short loc_140033965
0x1400338fd  cmp     eax, 124354h
0x140033902  jz      short loc_14003395B
0x140033904  cmp     eax, 124558h
0x140033909  jz      short loc_140033946
0x14003390b  cmp     eax, 124664h
0x140033910  jz      short loc_14003392D
0x140033912  cmp     eax, 128020h
0x140033917  jnz     loc_140033B07
0x14003391d  mov     rdx, rdi; struct _IRP *
0x140033920  mov     rcx, rsi; struct _VELAN *
0x140033923  call    ?IoctlReset@@YAJPEAU_VELAN@@PEAU_IRP@@@Z; IoctlReset(_VELAN *,_IRP *)
0x140033928  jmp     loc_140033C79
0x14003392d  mov     r8d, [rbp+arg_0]; unsigned int
0x140033931  lea     r9, [rbp+arg_0]; unsigned int *
0x140033935  mov     rdx, [rdi+18h]; void *
0x140033939  mov     rcx, rsi; struct _VELAN *
0x14003393c  call    ?IoctlFipsCapabilities@@YAJQEAU_VELAN@@QEAXKQEAK@Z; IoctlFipsCapabilities(_VELAN * const,void * const,ulong,ulong * const)
0x140033941  jmp     loc_140033C79
0x140033946  mov     rdx, [rdi+18h]; void *
0x14003394a  lea     r8, [rbp+arg_0]; unsigned int *
0x14003394e  mov     rcx, rsi; struct _VELAN *
0x140033951  call    ?IoctlGetSupportedDeviceServices@@YAJPEAU_VELAN@@PEAXPEAK@Z; IoctlGetSupportedDeviceServices(_VELAN *,void *,ulong *)
0x140033956  jmp     loc_140033C79
0x14003395b  mov     ebx, 0C0000002h
0x140033960  jmp     loc_140033C7B
0x140033965  mov     rdx, [rdi+18h]
0x140033969  lea     r9, [rbp+arg_0]
0x14003396d  mov     r8d, ebx
0x140033970  mov     rcx, rsi
0x140033973  call    IoctlOpModeCapability
0x140033978  jmp     loc_140033C79
0x14003397d  mov     rdx, [rdi+18h]; void *
0x140033981  lea     r9, [rbp+arg_0]; unsigned int *
0x140033985  mov     rcx, [r14+30h]; struct _FILE_OBJECT *
0x140033989  mov     r8d, ebx; unsigned int
0x14003398c  call    ?IoctlSetPMK@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z; IoctlSetPMK(_FILE_OBJECT *,void *,ulong,ulong *)
0x140033991  jmp     loc_140033C79
0x140033996  sub     eax, 128528h
0x14003399b  jz      short loc_1400339F1
0x14003399d  sub     eax, 4
0x1400339a0  jz      short loc_1400339DC
0x1400339a2  sub     eax, 4
0x1400339a5  jz      short loc_1400339C7
0x1400339a7  cmp     eax, 11Ch
0x1400339ac  jnz     loc_140033B07
0x1400339b2  mov     rdx, [rdi+18h]; void *
0x1400339b6  lea     r8, [rbp+arg_0]; unsigned int *
0x1400339ba  mov     rcx, rsi; struct _VELAN *
0x1400339bd  call    ?IoctlGetWifiCxAdapterInfo@@YAJPEAU_VELAN@@PEAXPEAK@Z; IoctlGetWifiCxAdapterInfo(_VELAN *,void *,ulong *)
0x1400339c2  jmp     loc_140033C79
0x1400339c7  mov     rdx, [rdi+18h]; void *
0x1400339cb  lea     r8, [rbp+arg_0]; unsigned int *
0x1400339cf  mov     rcx, rsi; struct _VELAN *
0x1400339d2  call    ?IoctlGetVwifiAttributes@@YAJPEAU_VELAN@@PEAXPEAK@Z; IoctlGetVwifiAttributes(_VELAN *,void *,ulong *)
0x1400339d7  jmp     loc_140033C79
0x1400339dc  mov     rdx, [rdi+18h]; void *
0x1400339e0  lea     r8, [rbp+arg_0]; unsigned int *
0x1400339e4  mov     rcx, rsi; struct _VELAN *
0x1400339e7  call    ?IoctlGetBandCapabilities@@YAJPEAU_VELAN@@PEAXPEAK@Z; IoctlGetBandCapabilities(_VELAN *,void *,ulong *)
0x1400339ec  jmp     loc_140033C79
0x1400339f1  mov     rdx, [rdi+18h]; void *
0x1400339f5  lea     r8, [rbp+arg_0]; unsigned int *
0x1400339f9  mov     rcx, rsi; struct _VELAN *
0x1400339fc  call    ?IoctlGetAdapterCapabilities@@YAJPEAU_VELAN@@PEAXPEAK@Z; IoctlGetAdapterCapabilities(_VELAN *,void *,ulong *)
0x140033a01  jmp     loc_140033C79
0x140033a06  mov     rdx, [rdi+18h]
0x140033a0a  lea     r9, [rbp+arg_0]
0x140033a0e  mov     r8d, ebx
0x140033a11  mov     rcx, rsi
0x140033a14  call    IoctlCurrentOpMode
0x140033a19  jmp     loc_140033C79
0x140033a1e  mov     ecx, 12C39Ch
0x140033a23  cmp     eax, ecx
0x140033a25  ja      loc_140033AE7
0x140033a2b  jz      loc_140033ACE
0x140033a31  sub     eax, 12C194h
0x140033a36  jz      short loc_140033AB6
0x140033a38  sub     eax, 18Ch
0x140033a3d  jz      short loc_140033A9D
0x140033a3f  sub     eax, 4
0x140033a42  jz      short loc_140033A84
0x140033a44  sub     eax, 44h ; 'D'
0x140033a47  jz      short loc_140033A6B
0x140033a49  cmp     eax, 8
0x140033a4c  jnz     loc_140033B07
0x140033a52  mov     rdx, [rdi+18h]; void *
0x140033a56  lea     r9, [rbp+arg_0]; unsigned int *
0x140033a5a  mov     rcx, [r14+30h]; struct _FILE_OBJECT *
0x140033a5e  mov     r8d, ebx; unsigned int
0x140033a61  call    ?IoctlSafeModeImplemented@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z; IoctlSafeModeImplemented(_FILE_OBJECT *,void *,ulong,ulong *)
0x140033a66  jmp     loc_140033C79
0x140033a6b  mov     rdx, [rdi+18h]; void *
0x140033a6f  lea     r9, [rbp+arg_0]; unsigned int *
0x140033a73  mov     rcx, [r14+30h]; struct _FILE_OBJECT *
0x140033a77  mov     r8d, ebx; unsigned int
0x140033a7a  call    ?IoctlSafeModeEnabled@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z; IoctlSafeModeEnabled(_FILE_OBJECT *,void *,ulong,ulong *)
0x140033a7f  jmp     loc_140033C79
0x140033a84  mov     rdx, [rdi+18h]
0x140033a88  lea     r9, [rbp+arg_0]
0x140033a8c  mov     rcx, [r14+30h]
0x140033a90  mov     r8d, ebx
0x140033a93  call    IoctlActiveSecurityProvider
0x140033a98  jmp     loc_140033C79
0x140033a9d  mov     rdx, [rdi+18h]; void *
0x140033aa1  lea     r9, [rbp+arg_0]; unsigned int *
0x140033aa5  mov     rcx, [r14+30h]; struct _FILE_OBJECT *
0x140033aa9  mov     r8d, ebx; unsigned int
0x140033aac  call    ?IoctlSecurityProviderParameters@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z; IoctlSecurityProviderParameters(_FILE_OBJECT *,void *,ulong,ulong *)
0x140033ab1  jmp     loc_140033C79
0x140033ab6  mov     rdx, [rdi+18h]
0x140033aba  lea     r9, [rbp+arg_0]
0x140033abe  mov     r8d, ebx
0x140033ac1  mov     rcx, rsi
0x140033ac4  call    IoctlNICSpecificExtension
0x140033ac9  jmp     loc_140033C79
0x140033ace  mov     rdx, [rdi+18h]; void *
0x140033ad2  lea     r9, [rbp+arg_0]; unsigned int *
0x140033ad6  mov     rcx, [r14+30h]; struct _FILE_OBJECT *
0x140033ada  mov     r8d, ebx; unsigned int
0x140033add  call    ?IoctlGetPmkIdList@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z; IoctlGetPmkIdList(_FILE_OBJECT *,void *,ulong,ulong *)
0x140033ae2  jmp     loc_140033C79
0x140033ae7  sub     eax, 12C55Ch
0x140033aec  jz      loc_140033C66
0x140033af2  sub     eax, 14h
0x140033af5  jz      loc_140033C51
0x140033afb  sub     eax, 0FCh
0x140033b00  jz      short loc_140033B3C
0x140033b02  cmp     eax, 4
0x140033b05  jz      short loc_140033B84
0x140033b07  mov     r10, [rsi+1F68h]
0x140033b0e  test    r10, r10
0x140033b11  jz      loc_140033C4A
0x140033b17  mov     eax, [r14+18h]
0x140033b1b  and     al, 3
0x140033b1d  cmp     al, 2
0x140033b1f  jnz     loc_140033C19
0x140033b25  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140033b29  test    byte ptr [rcx+0Ah], 5
0x140033b2d  jz      loc_140033BDE
0x140033b33  mov     r8, [rcx+18h]
0x140033b37  jmp     loc_140033C0D
0x140033b3c  call    Feature_WiFiDirect2_Support__private_IsEnabledDeviceUsageNoInline
0x140033b41  test    eax, eax
0x140033b43  jz      short loc_140033B84
0x140033b45  cmp     dword ptr [r14+18h], 12C66Ch
0x140033b4d  jnz     short loc_140033B84
0x140033b4f  mov     rcx, [rsi+10h]; struct _ADAPT *
0x140033b53  cmp     qword ptr [rcx+610h], 0
0x140033b5b  jnz     short loc_140033B67
0x140033b5d  mov     ebx, 0C00000BBh
0x140033b62  jmp     loc_140033C7B
0x140033b67  mov     r9, [rdi+18h]; void *
0x140033b6b  mov     edx, 1; unsigned int
0x140033b70  mov     r8d, 0E0102AAh; unsigned int
0x140033b76  mov     dword ptr [rsp+48h+Timeout], ebx; unsigned int
0x140033b7a  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140033b7f  jmp     loc_140033C79
0x140033b84  call    Feature_WiFiDirect2_Support__private_IsEnabledDeviceUsageNoInline
0x140033b89  test    eax, eax
0x140033b8b  jz      loc_140033B07
0x140033b91  cmp     dword ptr [r14+18h], 12C670h
0x140033b99  jnz     loc_140033B07
0x140033b9f  mov     rcx, [rsi+10h]; struct _ADAPT *
0x140033ba3  cmp     qword ptr [rcx+610h], 0
0x140033bab  jz      short loc_140033B5D
0x140033bad  mov     r9d, [rbp+arg_0]; unsigned int
0x140033bb1  lea     rax, [rbp+arg_0]
0x140033bb5  mov     [rsp+48h+var_18], 0; unsigned int *
0x140033bbe  mov     r8d, ebx; unsigned int
0x140033bc1  mov     qword ptr [rsp+48h+Priority], rax; unsigned int *
0x140033bc6  mov     edx, 0E0102ABh; unsigned int
0x140033bcb  mov     rax, [rdi+18h]
0x140033bcf  mov     [rsp+48h+Timeout], rax; void *
0x140033bd4  call    ?PtCallAdapterSync@@YAHPEAU_ADAPT@@KKKPEAXPEAK2@Z; PtCallAdapterSync(_ADAPT *,ulong,ulong,ulong,void *,ulong *,ulong *)
0x140033bd9  jmp     loc_140033C79
0x140033bde  xor     r9d, r9d; RequestedAddress
0x140033be1  mov     [rsp+48h+Priority], 40000010h; Priority
0x140033be9  xor     edx, edx; AccessMode
0x140033beb  mov     dword ptr [rsp+48h+Timeout], 0; BugCheckOnFailure
0x140033bf3  lea     r8d, [r9+1]; CacheType
0x140033bf7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140033bfe  nop     dword ptr [rax+rax+00h]
0x140033c03  mov     r10, [rsi+1F68h]
0x140033c0a  mov     r8, rax
0x140033c0d  mov     rcx, [rdi+8]
0x140033c11  mov     edx, [rcx+28h]
0x140033c14  mov     [rbp+arg_0], edx
0x140033c17  jmp     short loc_140033C1D
0x140033c19  mov     r8, [rdi+18h]
0x140033c1d  mov     rax, [rsi+98h]
0x140033c24  lea     rcx, [rbp+arg_0]
0x140033c28  mov     qword ptr [rsp+48h+Priority], rcx
0x140033c2d  mov     r9d, ebx
0x140033c30  mov     [rsp+48h+Timeout], r8
0x140033c35  mov     rdx, rdi
0x140033c38  mov     r8, [rdi+18h]
0x140033c3c  mov     rcx, r10
0x140033c3f  mov     rax, [rax+60h]
0x140033c43  call    _guard_dispatch_icall
0x140033c48  jmp     short loc_140033C79
0x140033c4a  mov     ebx, 0C0000184h
0x140033c4f  jmp     short loc_140033C7B
0x140033c51  mov     rdx, [rdi+18h]; void *
0x140033c55  lea     r9, [rbp+arg_0]; unsigned int *
0x140033c59  mov     r8d, ebx; unsigned int
0x140033c5c  mov     rcx, rsi; struct _VELAN *
0x140033c5f  call    ?IoctlGetBSSInfo@@YAJPEAU_VELAN@@PEAXKPEAK@Z; IoctlGetBSSInfo(_VELAN *,void *,ulong,ulong *)
0x140033c64  jmp     short loc_140033C79
0x140033c66  mov     rdx, [rdi+18h]; void *
0x140033c6a  lea     r9, [rbp+arg_0]; unsigned int *
0x140033c6e  mov     r8d, ebx; unsigned int
0x140033c71  mov     rcx, rsi; struct _VELAN *
0x140033c74  call    ?IoctlDeviceServiceCommand@@YAJPEAU_VELAN@@PEAXKPEAK@Z; IoctlDeviceServiceCommand(_VELAN *,void *,ulong,ulong *)
0x140033c79  mov     ebx, eax
0x140033c7b  xor     r9d, r9d; Alertable
0x140033c7e  mov     [rsp+48h+Timeout], 0; Timeout
0x140033c87  xor     r8d, r8d; WaitMode
0x140033c8a  xor     edx, edx; WaitReason
0x140033c8c  mov     rcx, r13; Object
0x140033c8f  call    cs:__imp_KeWaitForSingleObject
0x140033c96  nop     dword ptr [rax+rax+00h]
0x140033c9b  mov     rax, gs:188h
0x140033ca4  xor     r8d, r8d; Wait
0x140033ca7  mov     [r13+18h], rax
0x140033cab  mov     rcx, r13; Event
0x140033cae  lock dec dword ptr [rsi+15ECh]
0x140033cb5  mov     qword ptr [r13+18h], 0
0x140033cbd  lea     edx, [r8+1]; Increment
0x140033cc1  call    cs:__imp_KeSetEvent
0x140033cc8  nop     dword ptr [rax+rax+00h]
0x140033ccd  cmp     ebx, 103h
0x140033cd3  jz      short loc_140033CF4
0x140033cd5  mov     eax, [rbp+arg_0]
0x140033cd8  mov     [rdi+38h], rax
  ... truncated ...
```
