# CKsFilterFactory::Init(_KSDEVICE_EXT *,_LIST_ENTRY *,_KSFILTER_DESCRIPTOR const *,ushort *,void *,ulong,void (*)(_KSFILTERFACTORY *,_DEVICE_POWER_STATE),void (*)(_KSFILTERFACTORY *,_DEVICE_POWER_STATE),_KSFILTERFACTORY * *)

- ea: `0x18004db2c`
- end: `0x18004e365`
- name: `?Init@CKsFilterFactory@@QEAAJPEAU_KSDEVICE_EXT@@PEAU_LIST_ENTRY@@PEBU_KSFILTER_DESCRIPTOR@@PEAGPEAXKP6AXPEAU_KSFILTERFACTORY@@W4_DEVICE_POWER_STATE@@@Z7PEAPEAU5@@Z`
- size: `2105`
- prototype: `__int64 __usercall@<rax>(CKsFilterFactory *__hidden this@<rcx>, struct _KSDEVICE_EXT *@<rdx>, struct _LIST_ENTRY *@<r8>, const struct _KSFILTER_DESCRIPTOR *@<r9>, PCWSTR SourceString, void *, unsigned int, void (*)(struct _KSFILTERFACTORY *, enum _DEVICE_POWER_STATE), void (*)(struct _KSFILTERFACTORY *, enum _DEVICE_POWER_STATE), struct _KSFILTERFACTORY **)`
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180061074`

## callees

- `0x18000abec`
- `0x18000b7bc`
- `0x18000c630`
- `0x18000d5a8`
- `0x18000e238`
- `0x180019b80`
- `0x180019c60`
- `0x1800332f4`
- `0x18003be00`
- `0x18003c10c`
- `0x1800469a4`
- `0x18004d718`
- `0x18004db2c`
- `0x18004e370`
- `0x18004e9a0`
- `0x18004e9fc`
- `0x18004f228`
- `0x18004f7c8`
- `0x18004fa1c`
- `0x18004fd4c`
- `0x18004ff10`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18004e347`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18004e347`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004df2d`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004df2d`
- `ntoskrnl!RtlStringFromGUID` at `0x18004dcce`
- `ntoskrnl!RtlStringFromGUID` at `0x18004dcce`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18004dde8`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18004dde8`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x18004defd`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x18004defd`
- `ntoskrnl!SeExports` at `0x18004e17c`
- `HAL!KeQueryPerformanceCounter` at `0x18004db9a`
- `HAL!KeQueryPerformanceCounter` at `0x18004db9a`

## pseudocode

```c
__int64 __fastcall CKsFilterFactory::Init(
        CKsFilterFactory *this,
        struct _KSDEVICE_EXT *a2,
        struct _LIST_ENTRY *a3,
        const struct _KSFILTER_DESCRIPTOR *a4,
        PCWSTR SourceString,
        void *a6,
        unsigned int a7,
        void (*a8)(struct _KSFILTERFACTORY *, enum _DEVICE_POWER_STATE),
        void (*a9)(struct _KSFILTERFACTORY *, enum _DEVICE_POWER_STATE),
        struct _KSFILTERFACTORY **a10)
{
  __int64 *v14; // rdx
  LARGE_INTEGER PerformanceCounter; // rax
  int v16; // edx
  __int64 QuadPart; // rbx
  _GUID v18; // xmm0
  struct _LIST_ENTRY *Blink; // rcx
  NTSTATUS AutomationTableTable; // esi
  ULONG PinDescriptorsCount; // edx
  KSAUTOMATION_TABLE_ ***p_m_PinAutomationTables; // rcx
  ULONG NodeDescriptorsCount; // edx
  KSAUTOMATION_TABLE_ ***p_m_NodeAutomationTables; // rcx
  const GUID *v26; // rcx
  bool v27; // r15
  _KSDEVICE *v28; // rax
  ULONG CategoriesCount; // r9d
  ULONG j; // r8d
  _KSDEVICE *v31; // rax
  IKsDevice *v32; // rcx
  char v33; // r14
  __int64 v34; // rax
  struct _UNICODE_STRING *v35; // rbx
  _KSDEVICE *v36; // rax
  __int64 v37; // rdx
  char DeviceCompatFlags; // al
  _KSFILTERFACTORY *p_Public; // r14
  unsigned __int8 v40; // al
  __int64 v41; // rdx
  __int64 v42; // rcx
  struct _UNICODE_STRING *v43; // rax
  const WCHAR *v44; // rdx
  IKsDevice *Device; // rcx
  KSAUTOMATION_TABLE_ **p_m_FilterAutomationTable; // rcx
  struct KSAUTOMATION_TABLE_ *AutomationTable; // rdx
  const GUID *v48; // rcx
  int v49; // r8d
  __int64 Notification; // rax
  UNICODE_STRING *ProfileSymbolicName; // rbx
  _KSDEVICE *v52; // rax
  __int64 v53; // rdx
  __int64 SystemCompatFlags; // rax
  int v55; // r10d
  unsigned int i; // edx
  PSID SeLocalServiceSid; // rbx
  _KSDEVICE *v58; // rax
  int v59; // eax
  int v60; // edx
  const GUID *ReferenceGuid; // rcx
  IKsProfiles *Profiles; // rax
  PVOID Data; // [rsp+28h] [rbp-69h]
  UNICODE_STRING GuidString; // [rsp+40h] [rbp-51h] BYREF
  ULONG Type; // [rsp+50h] [rbp-41h] BYREF
  ULONG RequiredSize; // [rsp+54h] [rbp-3Dh] BYREF
  void *v67; // [rsp+58h] [rbp-39h]
  struct _KSDEVICE_EXT *v68; // [rsp+60h] [rbp-31h]
  struct _KSFILTERFACTORY **v69; // [rsp+68h] [rbp-29h]
  GUID v70; // [rsp+70h] [rbp-21h] BYREF

  v67 = a6;
  v69 = a10;
  v68 = a2;
  v14 = WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v14) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v14,
      1,
      14,
      (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids);
  }
  PerformanceCounter = KeQueryPerformanceCounter(0);
  this->m_fVideoCameraFilter = 0;
  QuadPart = PerformanceCounter.QuadPart;
  if ( a4->Version == -1 )
  {
    if ( (a4->Flags & 0x10) == 0 )
    {
      v18 = GUID_9b365890_165f_11d0_a195_0020afd156e4;
      this->m_Profiles = 0;
      goto LABEL_5;
    }
    ReferenceGuid = a4->ReferenceGuid;
    if ( !ReferenceGuid || (unsigned int)IsEqualGUIDAligned(ReferenceGuid, &GUID_9b365890_165f_11d0_a195_0020afd156e4) )
    {
      return 3221225858LL;
    }
    else
    {
      Profiles = (IKsProfiles *)KspCreateProfiles();
      this->m_Profiles = Profiles;
      if ( Profiles )
      {
        v18 = *a4->ReferenceGuid;
LABEL_5:
        this->m_ReferenceGUID = v18;
        this->m_Ext.ChildList.Blink = &this->m_Ext.ChildList;
        this->m_Ext.ChildList.Flink = &this->m_Ext.ChildList;
        Blink = a3->Blink;
        if ( Blink->Flink != a3 )
          __fastfail(3u);
        this->m_Ext.SiblingListEntry.Flink = a3;
        this->m_Ext.SiblingListEntry.Blink = Blink;
        Blink->Flink = &this->m_Ext.SiblingListEntry;
        a3->Blink = &this->m_Ext.SiblingListEntry;
        this->m_Ext.SiblingListHead = a3;
        this->m_Ext.Parent = a2;
        this->m_Ext.ObjectType = KsObjectTypeFilterFactory;
        this->m_Ext.Interface = this;
        this->m_Ext.Device = a2->Device;
        this->m_Ext.ParentDevice = a2;
        this->m_DeviceClasses.Blink = &this->m_DeviceClasses;
        this->m_DeviceClasses.Flink = &this->m_DeviceClasses;
        this->m_ChildFilterList.Blink = &this->m_ChildFilterList;
        this->m_ChildFilterList.Flink = &this->m_ChildFilterList;
        Device = this->m_Ext.Device;
        this->m_Ext.Public.FilterDescriptor = a4;
        this->m_Ext.Public.Context = a2->Public.Context;
        this->m_Ext.Public.Bag = &this->m_ObjectBag;
        Device->InitializeObjectBag(Device, &this->m_ObjectBag, 0);
        p_m_FilterAutomationTable = &this->m_FilterAutomationTable;
        this->m_Ext.UniqueDeviceId.QPCOnCreation = QuadPart;
        this->m_Ext.UniqueDeviceId.FilterFactory = (unsigned __int64)this;
        this->m_DispatchSleep = (void (__fastcall *)(_KSFILTERFACTORY *, _DEVICE_POWER_STATE))a8;
        this->m_DispatchWake = (void (__fastcall *)(_KSFILTERFACTORY *, _DEVICE_POWER_STATE))a9;
        this->m_Ext.UniqueDeviceId.KSCategory = GUID_00000000_0000_0000_0000_000000000000;
        this->m_GuidVideoCamera.Data1 = -449693833;
        *(_DWORD *)&this->m_GuidVideoCamera.Data2 = *(_DWORD *)&GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data2;
        *(_DWORD *)this->m_GuidVideoCamera.Data4 = *(_DWORD *)GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data4;
        *(_DWORD *)&this->m_GuidVideoCamera.Data4[4] = *(_DWORD *)&GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data4[4];
        this->m_profileGUID = GUID_00000000_0000_0000_0000_000000000000;
        AutomationTable = (struct KSAUTOMATION_TABLE_ *)a4->AutomationTable;
        if ( AutomationTable )
        {
          AutomationTableTable = KsMergeAutomationTables(
                                   p_m_FilterAutomationTable,
                                   AutomationTable,
                                   (PKSAUTOMATION_TABLE)&FilterAutomationTable,
                                   this->m_Ext.Public.Bag);
          if ( AutomationTableTable < 0 )
            return (unsigned int)AutomationTableTable;
        }
        else
        {
          AutomationTableTable = 0;
          *p_m_FilterAutomationTable = (KSAUTOMATION_TABLE_ *)&FilterAutomationTable;
        }
        PinDescriptorsCount = a4->PinDescriptorsCount;
        p_m_PinAutomationTables = &this->m_PinAutomationTables;
        if ( PinDescriptorsCount )
        {
          AutomationTableTable = KspCreateAutomationTableTable(
                                   (int)p_m_PinAutomationTables,
                                   PinDescriptorsCount,
                                   a4->PinDescriptorSize,
                                   (unsigned int)a4->PinDescriptors + 8,
                                   (PKSAUTOMATION_TABLE)&PinAutomationTable,
                                   this->m_Ext.Public.Bag);
          if ( AutomationTableTable < 0 )
            return (unsigned int)AutomationTableTable;
        }
        else
        {
          *p_m_PinAutomationTables = 0;
        }
        NodeDescriptorsCount = a4->NodeDescriptorsCount;
        p_m_NodeAutomationTables = &this->m_NodeAutomationTables;
        this->m_NodesCount = NodeDescriptorsCount;
        if ( !NodeDescriptorsCount )
        {
          *p_m_NodeAutomationTables = 0;
LABEL_16:
          GuidString = 0;
          if ( this->m_Profiles )
          {
            v26 = a4->ReferenceGuid;
            goto LABEL_18;
          }
          v27 = 0;
          if ( SourceString )
          {
            v44 = SourceString;
          }
          else
          {
            v26 = a4->ReferenceGuid;
            if ( v26 )
            {
LABEL_18:
              AutomationTableTable = RtlStringFromGUID(v26, &GuidString);
              v27 = AutomationTableTable >= 0;
              if ( AutomationTableTable < 0 )
                goto LABEL_40;
              goto LABEL_19;
            }
            v44 = (const WCHAR *)&qword_18007AC58;
          }
          RtlInitUnicodeString(&GuidString, v44);
LABEL_19:
          v28 = this->m_Ext.Device->GetStruct(this->m_Ext.Device);
          if ( (unsigned int)KsiGetBusInterface(*(_QWORD *)v28->FunctionalDeviceObject->DeviceExtension) != -1073741637 )
          {
LABEL_28:
            p_Public = &this->m_Ext.Public;
            v40 = IsVideoCameraFilter(this->m_Ext.Public.FilterDescriptor);
            this->m_fVideoCameraFilter = v40;
            if ( v40 )
            {
              Notification = KspGetNotification(v42, v41);
              if ( Notification )
                AutomationTableTable = (*(__int64 (__fastcall **)(__int64, _KSCAMERA_FRAMESERVER_UNIQUEID *))(*(_QWORD *)Notification + 48LL))(
                                         Notification,
                                         &this->m_Ext.UniqueDeviceId);
              ProfileSymbolicName = CKsFilterFactory::GetProfileSymbolicName(this);
              v52 = this->m_Ext.Device->GetStruct(this->m_Ext.Device);
              SystemCompatFlags = CameraQuerySystemCompatFlags(ProfileSymbolicName, v53, v52->PhysicalDeviceObject);
              if ( SystemCompatFlags )
              {
                v55 = 0;
                for ( i = 0; i < 4; ++i )
                {
                  if ( *((unsigned __int16 *)qword_1800226C0 + 2 * (int)i) == SystemCompatFlags )
                  {
                    v55 = *((unsigned __int16 *)qword_1800226C0 + 2 * (int)i + 1);
                    break;
                  }
                }
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LODWORD(Data) = v55;
                  LOBYTE(i) = 4;
                  WPP_RECORDER_SF_D(
                    WPP_GLOBAL_Control->DeviceExtension,
                    i,
                    1,
                    17,
                    (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
                    Data);
                }
              }
            }
            if ( AutomationTableTable >= 0 )
              AutomationTableTable = CKsFilterFactory::AddCreateItem(this, &GuidString, v67, a7);
            goto LABEL_31;
          }
          CategoriesCount = a4->CategoriesCount;
          for ( j = 0; j < CategoriesCount; j = v49 + 1 )
          {
            v48 = &a4->Categories[j];
            if ( v48->Data1 == -449693833
              && *(_DWORD *)&v48->Data2 == *(_DWORD *)&GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data2
              && *(_DWORD *)v48->Data4 == *(_DWORD *)GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data4
              && *(_DWORD *)&v48->Data4[4] == *(_DWORD *)&GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data4[4]
              || (unsigned int)InlineIsEqualGUID(v48, &GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca) )
            {
              SeLocalServiceSid = SeExports->SeLocalServiceSid;
              v58 = this->m_Ext.Device->GetStruct(this->m_Ext.Device);
              v59 = AddSidToDevice(v58->PhysicalDeviceObject, SeLocalServiceSid);
              if ( v59 < 0
                && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                && LOWORD(WPP_GLOBAL_Control->DeviceType) )
              {
                LODWORD(Data) = v59;
                LOBYTE(v60) = 5;
                WPP_RECORDER_SF_D(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v60,
                  1,
                  16,
                  (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
                  Data);
              }
              break;
            }
          }
          v31 = this->m_Ext.Device->GetStruct(this->m_Ext.Device);
          AutomationTableTable = KspRegisterDeviceInterfaces(
                                   a4->CategoriesCount,
                                   a4->Categories,
                                   v31->PhysicalDeviceObject,
                                   &GuidString,
                                   &this->m_Ext.UniqueDeviceId,
                                   &this->m_DeviceClasses);
          if ( AutomationTableTable >= 0 )
          {
            v32 = this->m_Ext.Device;
            v33 = 0;
            v70 = GUID_00000000_0000_0000_0000_000000000000;
            RequiredSize = 0;
            Type = 0;
            v34 = (__int64)v32->GetStruct(v32);
            if ( IoGetDevicePropertyData(
                   *(PDEVICE_OBJECT *)(v34 + 32),
                   &DEVPKEY_Device_ClassGuid,
                   0,
                   0,
                   0x10u,
                   &v70,
                   &RequiredSize,
                   &Type) >= 0
              && (v70.Data1 != 1809653702
               || *(_QWORD *)&v70.Data2 != 0x8C7BE11D0810FLL
               || *(_DWORD *)&v70.Data4[4] != 789176875) )
            {
              v33 = 1;
            }
            v35 = CKsFilterFactory::GetProfileSymbolicName(this);
            v36 = this->m_Ext.Device->GetStruct(this->m_Ext.Device);
            DeviceCompatFlags = CameraQueryDeviceCompatFlags(v35, v37, v36->PhysicalDeviceObject);
            if ( !v33 || (DeviceCompatFlags & 1) != 0 )
              CKsFilterFactory::RegisterInVideoCameraCategory(this, &GuidString);
            goto LABEL_28;
          }
LABEL_40:
          p_Public = &this->m_Ext.Public;
LABEL_31:
          if ( v27 )
            RtlFreeUnicodeString(&GuidString);
          if ( AutomationTableTable >= 0 )
          {
            v68->Device->AddPowerEntry(v68->Device, &this->m_PowerEntry, &this->IKsPowerNotify);
            if ( v69 )
              *v69 = p_Public;
            if ( this->m_Profiles )
              CKsFilterFactory::StoreReferenceGuidWithSymbolicName(this);
            v43 = CKsFilterFactory::GetProfileSymbolicName(this);
            if ( v43 )
              IoSetDeviceInterfacePropertyData(v43, DEVPKEY_DeviceInterface_CameraProfiles, 0, 1, 4099, 0, 0);
          }
          return (unsigned int)AutomationTableTable;
        }
        AutomationTableTable = KspCreateAutomationTableTable(
                                 (int)p_m_NodeAutomationTables,
                                 NodeDescriptorsCount,
                                 a4->NodeDescriptorSize,
                                 (int)a4->NodeDescriptors,
                                 0,
                                 this->m_Ext.Public.Bag);
        if ( AutomationTableTable >= 0 )
          goto LABEL_16;
        return (unsigned int)AutomationTableTable;
      }
      return 3221225626LL;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        1,
        15,
        (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids);
    }
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x18004db2c  push    rbp
0x18004db2e  push    rbx
0x18004db2f  push    rsi
0x18004db30  push    rdi
0x18004db31  push    r12
0x18004db33  push    r13
0x18004db35  push    r14
0x18004db37  push    r15
0x18004db39  lea     rbp, [rsp-7]
0x18004db3e  sub     rsp, 98h
0x18004db45  mov     rax, cs:__security_cookie
0x18004db4c  xor     rax, rsp
0x18004db4f  mov     [rbp+3Fh+var_50], rax
0x18004db53  mov     rax, [rbp+3Fh+arg_28]
0x18004db57  mov     r14, r9
0x18004db5a  mov     r12, [rbp+3Fh+SourceString]
0x18004db5e  mov     rsi, r8
0x18004db61  mov     [rbp+3Fh+var_78], rax
0x18004db65  mov     r15, rdx
0x18004db68  mov     rax, [rbp+3Fh+arg_48]
0x18004db6f  mov     rdi, rcx
0x18004db72  mov     [rbp+3Fh+var_68], rax
0x18004db76  mov     [rbp+3Fh+var_70], rdx
0x18004db7a  lea     rax, WPP_RECORDER_INITIALIZED
0x18004db81  xor     r13d, r13d
0x18004db84  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004db8b  lea     rdx, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18004db92  jnz     loc_18004E203
0x18004db98  xor     ecx, ecx; PerformanceFrequency
0x18004db9a  call    cs:__imp_KeQueryPerformanceCounter
0x18004dba1  nop     dword ptr [rax+rax+00h]
0x18004dba6  mov     [rdi+1D8h], r13b
0x18004dbad  mov     rbx, rax
0x18004dbb0  cmp     dword ptr [r14+10h], 0FFFFFFFFh
0x18004dbb5  jnz     short loc_18004DBF8
0x18004dbb7  mov     eax, [r14+14h]
0x18004dbbb  test    al, 10h
0x18004dbbd  jnz     loc_18004E261
0x18004dbc3  movups  xmm0, xmmword ptr cs:_GUID_9b365890_165f_11d0_a195_0020afd156e4.Data1
0x18004dbca  mov     [rdi+1C0h], r13
0x18004dbd1  movdqu  xmmword ptr [rdi+1ACh], xmm0
0x18004dbd9  lea     rax, [rdi+40h]
0x18004dbdd  mov     [rax+8], rax
0x18004dbe1  mov     [rax], rax
0x18004dbe4  mov     rcx, [rsi+8]
0x18004dbe8  cmp     [rcx], rsi
0x18004dbeb  jz      loc_18004DF3E
0x18004dbf1  mov     ecx, 3
0x18004dbf6  int     29h; Win8: RtlFailFast(ecx)
0x18004dbf8  lea     rcx, WPP_RECORDER_INITIALIZED
0x18004dbff  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18004dc06  jnz     loc_18004E234
0x18004dc0c  mov     eax, 0C0000001h
0x18004dc11  jmp     short loc_18004DC2E
0x18004dc13  mov     r9, [rdi+0C8h]; Bag
0x18004dc1a  lea     r8, ?FilterAutomationTable@@3UKSAUTOMATION_TABLE_@@B; AutomationTableB
0x18004dc21  call    KsMergeAutomationTables
0x18004dc26  mov     esi, eax
0x18004dc28  test    eax, eax
0x18004dc2a  jns     short loc_18004DC5B
0x18004dc2c  mov     eax, esi
0x18004dc2e  mov     rcx, [rbp+3Fh+var_50]
0x18004dc32  xor     rcx, rsp; StackCookie
0x18004dc35  call    __security_check_cookie
0x18004dc3a  add     rsp, 98h
0x18004dc41  pop     r15
0x18004dc43  pop     r14
0x18004dc45  pop     r13
0x18004dc47  pop     r12
0x18004dc49  pop     rdi
0x18004dc4a  pop     rsi
0x18004dc4b  pop     rbx
0x18004dc4c  pop     rbp
0x18004dc4d  retn
0x18004dc4f  lea     rax, ?FilterAutomationTable@@3UKSAUTOMATION_TABLE_@@B; KSAUTOMATION_TABLE_ const FilterAutomationTable
0x18004dc56  mov     esi, ebx
0x18004dc58  mov     [rcx], rax
0x18004dc5b  mov     edx, [r14+20h]; int
0x18004dc5f  lea     rcx, [rdi+140h]; int
0x18004dc66  test    edx, edx
0x18004dc68  jnz     loc_18004E05C
0x18004dc6e  mov     [rcx], rbx
0x18004dc71  mov     edx, [r14+40h]; int
0x18004dc75  lea     rcx, [rdi+148h]; int
0x18004dc7c  mov     [rdi+150h], edx
0x18004dc82  test    edx, edx
0x18004dc84  jz      loc_18004E157
0x18004dc8a  mov     rax, [rdi+0C8h]
0x18004dc91  mov     r9, [r14+48h]; int
0x18004dc95  mov     r8d, [r14+44h]; int
0x18004dc99  mov     [rsp+0D0h+Data], rax; ObjectBag
0x18004dc9e  mov     qword ptr [rsp+0D0h+Size], rbx; AutomationTableB
0x18004dca3  call    KspCreateAutomationTableTable
0x18004dca8  mov     esi, eax
0x18004dcaa  test    eax, eax
0x18004dcac  js      loc_18004DC2C
0x18004dcb2  xorps   xmm0, xmm0
0x18004dcb5  movups  xmmword ptr [rbp+3Fh+GuidString.Length], xmm0
0x18004dcb9  cmp     [rdi+1C0h], rbx
0x18004dcc0  jz      loc_18004DF1A
0x18004dcc6  mov     rcx, [r14+18h]; Guid
0x18004dcca  lea     rdx, [rbp+3Fh+GuidString]; GuidString
0x18004dcce  call    cs:__imp_RtlStringFromGUID
0x18004dcd5  nop     dword ptr [rax+rax+00h]
0x18004dcda  mov     r15d, eax
0x18004dcdd  mov     esi, eax
0x18004dcdf  shr     r15d, 1Fh
0x18004dce3  xor     r15b, 1
0x18004dce7  test    eax, eax
0x18004dce9  js      loc_18004DF0E
0x18004dcef  mov     rcx, [rdi+88h]
0x18004dcf6  mov     rax, [rcx]
0x18004dcf9  mov     rax, [rax+18h]
0x18004dcfd  call    _guard_dispatch_icall
0x18004dd02  mov     rcx, [rax+18h]
0x18004dd06  mov     rcx, [rcx+40h]
0x18004dd0a  mov     rcx, [rcx]; BugCheckParameter2
0x18004dd0d  call    KsiGetBusInterface
0x18004dd12  cmp     eax, 0C00000BBh
0x18004dd17  jnz     loc_18004DE48
0x18004dd1d  mov     r9d, [r14+30h]
0x18004dd21  mov     r8d, ebx
0x18004dd24  cmp     r8d, r9d
0x18004dd27  jb      loc_18004E094
0x18004dd2d  mov     rcx, [rdi+88h]
0x18004dd34  mov     rax, [rcx]
0x18004dd37  mov     rax, [rax+18h]
0x18004dd3b  call    _guard_dispatch_icall
0x18004dd40  mov     rdx, [r14+38h]
0x18004dd44  lea     r9, [rbp+3Fh+GuidString]
0x18004dd48  mov     ecx, [r14+30h]
0x18004dd4c  mov     [rsp+0D0h+Data], r13
0x18004dd51  mov     r8, [rax+20h]
0x18004dd55  lea     rax, [rdi+0E0h]
0x18004dd5c  mov     qword ptr [rsp+0D0h+Size], rax
0x18004dd61  call    KspRegisterDeviceInterfaces
0x18004dd66  mov     esi, eax
0x18004dd68  test    eax, eax
0x18004dd6a  js      loc_18004DF0E
0x18004dd70  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004dd77  mov     rcx, [rdi+88h]
0x18004dd7e  xor     r14b, r14b
0x18004dd81  mov     ebx, cs:dword_18001D5CC
0x18004dd87  mov     r12d, cs:dword_18001D5D0
0x18004dd8e  mov     r13d, cs:dword_18001D5D4
0x18004dd95  movdqu  [rbp+3Fh+var_60], xmm0
0x18004dd9a  mov     [rbp+3Fh+var_7C], 0
0x18004dda1  mov     [rbp+3Fh+var_80], 0
0x18004dda8  mov     rax, [rcx]
0x18004ddab  mov     rax, [rax+18h]
0x18004ddaf  call    _guard_dispatch_icall
0x18004ddb4  lea     rcx, [rbp+3Fh+var_80]
0x18004ddb8  xor     r9d, r9d; Flags
0x18004ddbb  mov     [rsp+0D0h+Type], rcx; Type
0x18004ddc0  lea     rdx, DEVPKEY_Device_ClassGuid; PropertyKey
0x18004ddc7  lea     rcx, [rbp+3Fh+var_7C]
0x18004ddcb  xor     r8d, r8d; Lcid
0x18004ddce  mov     [rsp+0D0h+RequiredSize], rcx; RequiredSize
0x18004ddd3  lea     rcx, [rbp+3Fh+var_60]
0x18004ddd7  mov     [rsp+0D0h+Data], rcx; Data
0x18004dddc  mov     rcx, [rax+20h]; Pdo
0x18004dde0  mov     [rsp+0D0h+Size], 10h; Size
0x18004dde8  call    cs:__imp_IoGetDevicePropertyData
0x18004ddef  nop     dword ptr [rax+rax+00h]
0x18004ddf4  test    eax, eax
0x18004ddf6  js      short loc_18004DE08
0x18004ddf8  cmp     dword ptr [rbp+3Fh+var_60], 6BDD1FC6h
0x18004ddff  jz      loc_18004E2C4
0x18004de05  mov     r14b, 1
0x18004de08  mov     rcx, rdi; this
0x18004de0b  call    ?GetProfileSymbolicName@CKsFilterFactory@@QEAAPEAU_UNICODE_STRING@@XZ; CKsFilterFactory::GetProfileSymbolicName(void)
0x18004de10  mov     rdx, [rdi+88h]
0x18004de17  mov     rbx, rax
0x18004de1a  mov     rcx, [rdx]
0x18004de1d  mov     rax, [rcx+18h]
0x18004de21  mov     rcx, rdx
0x18004de24  call    _guard_dispatch_icall
0x18004de29  mov     rcx, rbx
0x18004de2c  mov     r8, [rax+20h]
0x18004de30  call    ?CameraQueryDeviceCompatFlags@@YA?ATCAMERA_DEVICE_FLAGS@@PEAU_UNICODE_STRING@@W4CAMERA_COMPAT_CLASS@@PEAU_DEVICE_OBJECT@@@Z; CameraQueryDeviceCompatFlags(_UNICODE_STRING *,CAMERA_COMPAT_CLASS,_DEVICE_OBJECT *)
0x18004de35  xor     ebx, ebx
0x18004de37  test    r14b, r14b
0x18004de3a  jz      loc_18004E2E6
0x18004de40  test    al, 1
0x18004de42  jnz     loc_18004E2E6
0x18004de48  lea     r14, [rdi+0C0h]
0x18004de4f  mov     rcx, [r14]
0x18004de52  call    IsVideoCameraFilter
0x18004de57  mov     [rdi+1D8h], al
0x18004de5d  test    al, al
0x18004de5f  jnz     loc_18004E0E8
0x18004de65  test    esi, esi
0x18004de67  js      short loc_18004DE7F
0x18004de69  mov     r9d, [rbp+3Fh+arg_30]; unsigned int
0x18004de6d  lea     rdx, [rbp+3Fh+GuidString]; struct _UNICODE_STRING *
0x18004de71  mov     r8, [rbp+3Fh+var_78]; void *
0x18004de75  mov     rcx, rdi; this
0x18004de78  call    ?AddCreateItem@CKsFilterFactory@@QEAAJPEAU_UNICODE_STRING@@PEAXK@Z; CKsFilterFactory::AddCreateItem(_UNICODE_STRING *,void *,ulong)
0x18004de7d  mov     esi, eax
0x18004de7f  test    r15b, r15b
0x18004de82  jnz     loc_18004E343
0x18004de88  test    esi, esi
0x18004de8a  js      loc_18004DC2C
0x18004de90  mov     rcx, [rbp+3Fh+var_70]
0x18004de94  lea     r8, [rdi+8]
0x18004de98  lea     rdx, [rdi+170h]
0x18004de9f  mov     rcx, [rcx+48h]
0x18004dea3  mov     rax, [rcx]
0x18004dea6  mov     rax, [rax+40h]
0x18004deaa  call    _guard_dispatch_icall
0x18004deaf  mov     rax, [rbp+3Fh+var_68]
0x18004deb3  test    rax, rax
0x18004deb6  jz      short loc_18004DEBB
0x18004deb8  mov     [rax], r14
0x18004debb  cmp     [rdi+1C0h], rbx
0x18004dec2  jnz     loc_18004E358
0x18004dec8  mov     rcx, rdi; this
0x18004decb  call    ?GetProfileSymbolicName@CKsFilterFactory@@QEAAPEAU_UNICODE_STRING@@XZ; CKsFilterFactory::GetProfileSymbolicName(void)
0x18004ded0  test    rax, rax
0x18004ded3  jz      loc_18004DC2C
0x18004ded9  mov     [rsp+0D0h+RequiredSize], rbx
0x18004dede  lea     rdx, DEVPKEY_DeviceInterface_CameraProfiles
0x18004dee5  mov     dword ptr [rsp+0D0h+Data], ebx
0x18004dee9  mov     r9d, 1
0x18004deef  xor     r8d, r8d
0x18004def2  mov     [rsp+0D0h+Size], 1003h
0x18004defa  mov     rcx, rax
0x18004defd  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x18004df04  nop     dword ptr [rax+rax+00h]
0x18004df09  jmp     loc_18004DC2C
0x18004df0e  lea     r14, [rdi+0C0h]
0x18004df15  jmp     loc_18004DE7F
0x18004df1a  mov     r15b, bl
0x18004df1d  test    r12, r12
0x18004df20  jz      loc_18004E2AB
0x18004df26  mov     rdx, r12; SourceString
0x18004df29  lea     rcx, [rbp+3Fh+GuidString]; DestinationString
0x18004df2d  call    cs:__imp_RtlInitUnicodeString
0x18004df34  nop     dword ptr [rax+rax+00h]
0x18004df39  jmp     loc_18004DCEF
0x18004df3e  lea     rax, [rdi+50h]
0x18004df42  xor     r8d, r8d
0x18004df45  mov     [rax], rsi
0x18004df48  lea     r13, [rdi+158h]
0x18004df4f  mov     [rax+8], rcx
0x18004df53  lea     rdx, [rdi+100h]
0x18004df5a  mov     [rcx], rax
0x18004df5d  mov     [rsi+8], rax
0x18004df61  mov     [rdi+60h], rsi
0x18004df65  mov     [rdi+68h], r15
0x18004df69  mov     dword ptr [rdi+70h], 1
0x18004df70  mov     [rdi+78h], rdi
0x18004df74  mov     rax, [r15+48h]
0x18004df78  mov     [rdi+88h], rax
0x18004df7f  lea     rax, [rdi+128h]
0x18004df86  mov     [rdi+0D8h], r15
0x18004df8d  mov     [r13+8], r13
0x18004df91  mov     [r13+0], r13
0x18004df95  mov     [rax+8], rax
0x18004df99  mov     [rax], rax
0x18004df9c  mov     rcx, [rdi+88h]
0x18004dfa3  mov     [rdi+0C0h], r14
0x18004dfaa  mov     rax, [r15+90h]
0x18004dfb1  mov     [rdi+0D0h], rax
0x18004dfb8  mov     [rdi+0C8h], rdx
0x18004dfbf  mov     rax, [rcx]
0x18004dfc2  mov     rax, [rax+20h]
0x18004dfc6  call    _guard_dispatch_icall
0x18004dfcb  mov     rax, [rbp+3Fh+arg_38]
0x18004dfd2  lea     rcx, [rdi+138h]; AutomationTableAB
0x18004dfd9  mov     [rdi+0E8h], rbx
0x18004dfe0  xor     ebx, ebx
0x18004dfe2  mov     [rdi+0E0h], rdi
0x18004dfe9  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004dff0  mov     [rdi+188h], rax
0x18004dff7  mov     rax, [rbp+3Fh+arg_40]
0x18004dffe  mov     [rdi+190h], rax
0x18004e005  movdqu  xmmword ptr [rdi+0F0h], xmm0
0x18004e00d  mov     dword ptr [rdi+198h], 0E5323777h
0x18004e017  mov     eax, dword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data2
0x18004e01d  mov     [rdi+19Ch], eax
0x18004e023  mov     eax, dword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data4
0x18004e029  mov     [rdi+1A0h], eax
0x18004e02f  mov     eax, dword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data4+4
0x18004e035  mov     [rdi+1A4h], eax
0x18004e03b  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004e042  movdqu  xmmword ptr [rdi+1C8h], xmm0
0x18004e04a  mov     rdx, [r14+8]; AutomationTableA
0x18004e04e  test    rdx, rdx
0x18004e051  jnz     loc_18004DC13
0x18004e057  jmp     loc_18004DC4F
0x18004e05c  mov     rax, [rdi+0C8h]
0x18004e063  mov     r9, [r14+28h]
0x18004e067  mov     r8d, [r14+24h]; int
0x18004e06b  add     r9, 8; int
0x18004e06f  mov     [rsp+0D0h+Data], rax; ObjectBag
0x18004e074  lea     rax, ?PinAutomationTable@@3UKSAUTOMATION_TABLE_@@B; KSAUTOMATION_TABLE_ const PinAutomationTable
0x18004e07b  mov     qword ptr [rsp+0D0h+Size], rax; AutomationTableB
0x18004e080  call    KspCreateAutomationTableTable
0x18004e085  mov     esi, eax
  ... truncated ...
```
