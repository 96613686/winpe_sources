# CKsFilterFactory::Init(_KSDEVICE_EXT *,_LIST_ENTRY *,_KSFILTER_DESCRIPTOR const *,ushort *,void *,ulong,void (*)(_KSFILTERFACTORY *,_DEVICE_POWER_STATE),void (*)(_KSFILTERFACTORY *,_DEVICE_POWER_STATE),_KSFILTERFACTORY * *)

- ea: `0x18004dccc`
- end: `0x18004e505`
- name: `?Init@CKsFilterFactory@@QEAAJPEAU_KSDEVICE_EXT@@PEAU_LIST_ENTRY@@PEBU_KSFILTER_DESCRIPTOR@@PEAGPEAXKP6AXPEAU_KSFILTERFACTORY@@W4_DEVICE_POWER_STATE@@@Z7PEAPEAU5@@Z`
- size: `2105`
- prototype: `__int64 __fastcall(CKsFilterFactory *this, struct _KSDEVICE_EXT *, struct _LIST_ENTRY *, const struct _KSFILTER_DESCRIPTOR *, PCWSTR SourceString, void *, unsigned int, void (*)(struct _KSFILTERFACTORY *, enum _DEVICE_POWER_STATE), void (*)(struct _KSFILTERFACTORY *, enum _DEVICE_POWER_STATE), struct _KSFILTERFACTORY **)`
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180061214`

## callees

- `0x18000abec`
- `0x18000b7bc`
- `0x18000c630`
- `0x18000d5a8`
- `0x18000e238`
- `0x180019bd0`
- `0x180019cb0`
- `0x1800332f4`
- `0x18003bdf0`
- `0x18003c0fc`
- `0x1800469a4`
- `0x18004d8b8`
- `0x18004dccc`
- `0x18004e510`
- `0x18004eb40`
- `0x18004eb9c`
- `0x18004f3c8`
- `0x18004f968`
- `0x18004fbbc`
- `0x18004feec`
- `0x1800500b0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18004e4e7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18004e4e7`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004e0cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004e0cd`
- `ntoskrnl!RtlStringFromGUID` at `0x18004de6e`
- `ntoskrnl!RtlStringFromGUID` at `0x18004de6e`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18004df88`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18004df88`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x18004e09d`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x18004e09d`
- `ntoskrnl!SeExports` at `0x18004e31c`
- `HAL!KeQueryPerformanceCounter` at `0x18004dd3a`
- `HAL!KeQueryPerformanceCounter` at `0x18004dd3a`

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
  struct _UNICODE_STRING *v41; // rax
  const WCHAR *v42; // rdx
  IKsDevice *Device; // rcx
  KSAUTOMATION_TABLE_ **p_m_FilterAutomationTable; // rcx
  struct KSAUTOMATION_TABLE_ *AutomationTable; // rdx
  const GUID *v46; // rcx
  int v47; // r8d
  __int64 Notification; // rax
  UNICODE_STRING *ProfileSymbolicName; // rbx
  _KSDEVICE *v50; // rax
  __int64 v51; // rdx
  __int64 SystemCompatFlags; // rax
  int v53; // r10d
  unsigned int i; // edx
  PSID SeLocalServiceSid; // rbx
  _KSDEVICE *v56; // rax
  int v57; // eax
  int v58; // edx
  GUID *ReferenceGuid; // rcx
  IKsProfiles *Profiles; // rax
  PVOID Data; // [rsp+28h] [rbp-69h]
  UNICODE_STRING GuidString; // [rsp+40h] [rbp-51h] BYREF
  ULONG Type; // [rsp+50h] [rbp-41h] BYREF
  ULONG RequiredSize; // [rsp+54h] [rbp-3Dh] BYREF
  void *v65; // [rsp+58h] [rbp-39h]
  struct _KSDEVICE_EXT *v66; // [rsp+60h] [rbp-31h]
  struct _KSFILTERFACTORY **v67; // [rsp+68h] [rbp-29h]
  GUID v68; // [rsp+70h] [rbp-21h] BYREF

  v65 = a6;
  v67 = a10;
  v66 = a2;
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
    ReferenceGuid = (GUID *)a4->ReferenceGuid;
    if ( !ReferenceGuid || IsEqualGUIDAligned(ReferenceGuid, &GUID_9b365890_165f_11d0_a195_0020afd156e4) )
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
            v42 = SourceString;
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
            v42 = (const WCHAR *)&qword_18007AC58;
          }
          RtlInitUnicodeString(&GuidString, v42);
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
              Notification = KspGetNotification();
              if ( Notification )
                AutomationTableTable = (*(__int64 (__fastcall **)(__int64, _KSCAMERA_FRAMESERVER_UNIQUEID *))(*(_QWORD *)Notification + 48LL))(
                                         Notification,
                                         &this->m_Ext.UniqueDeviceId);
              ProfileSymbolicName = CKsFilterFactory::GetProfileSymbolicName(this);
              v50 = this->m_Ext.Device->GetStruct(this->m_Ext.Device);
              SystemCompatFlags = CameraQuerySystemCompatFlags(ProfileSymbolicName, v51, v50->PhysicalDeviceObject);
              if ( SystemCompatFlags )
              {
                v53 = 0;
                for ( i = 0; i < 4; ++i )
                {
                  if ( *((unsigned __int16 *)qword_180022798 + 2 * (int)i) == SystemCompatFlags )
                  {
                    v53 = *((unsigned __int16 *)qword_180022798 + 2 * (int)i + 1);
                    break;
                  }
                }
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LODWORD(Data) = v53;
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
              AutomationTableTable = CKsFilterFactory::AddCreateItem(this, &GuidString, v65, a7);
            goto LABEL_31;
          }
          CategoriesCount = a4->CategoriesCount;
          for ( j = 0; j < CategoriesCount; j = v47 + 1 )
          {
            v46 = &a4->Categories[j];
            if ( v46->Data1 == -449693833
              && *(_DWORD *)&v46->Data2 == *(_DWORD *)&GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data2
              && *(_DWORD *)v46->Data4 == *(_DWORD *)GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data4
              && *(_DWORD *)&v46->Data4[4] == *(_DWORD *)&GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data4[4]
              || InlineIsEqualGUID(v46, &GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca) )
            {
              SeLocalServiceSid = SeExports->SeLocalServiceSid;
              v56 = this->m_Ext.Device->GetStruct(this->m_Ext.Device);
              v57 = AddSidToDevice(v56->PhysicalDeviceObject, SeLocalServiceSid);
              if ( v57 < 0
                && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                && LOWORD(WPP_GLOBAL_Control->DeviceType) )
              {
                LODWORD(Data) = v57;
                LOBYTE(v58) = 5;
                WPP_RECORDER_SF_D(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v58,
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
            v68 = GUID_00000000_0000_0000_0000_000000000000;
            RequiredSize = 0;
            Type = 0;
            v34 = (__int64)v32->GetStruct(v32);
            if ( IoGetDevicePropertyData(
                   *(PDEVICE_OBJECT *)(v34 + 32),
                   &DEVPKEY_Device_ClassGuid,
                   0,
                   0,
                   0x10u,
                   &v68,
                   &RequiredSize,
                   &Type) >= 0
              && (v68.Data1 != 1809653702
               || *(_QWORD *)&v68.Data2 != 0x8C7BE11D0810FLL
               || *(_DWORD *)&v68.Data4[4] != 789176875) )
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
            v66->Device->AddPowerEntry(v66->Device, &this->m_PowerEntry, &this->IKsPowerNotify);
            if ( v67 )
              *v67 = p_Public;
            if ( this->m_Profiles )
              CKsFilterFactory::StoreReferenceGuidWithSymbolicName(this);
            v41 = CKsFilterFactory::GetProfileSymbolicName(this);
            if ( v41 )
              IoSetDeviceInterfacePropertyData(v41, DEVPKEY_DeviceInterface_CameraProfiles, 0, 1);
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
0x18004dccc  push    rbp
0x18004dcce  push    rbx
0x18004dccf  push    rsi
0x18004dcd0  push    rdi
0x18004dcd1  push    r12
0x18004dcd3  push    r13
0x18004dcd5  push    r14
0x18004dcd7  push    r15
0x18004dcd9  lea     rbp, [rsp-7]
0x18004dcde  sub     rsp, 98h
0x18004dce5  mov     rax, cs:__security_cookie
0x18004dcec  xor     rax, rsp
0x18004dcef  mov     [rbp+3Fh+var_50], rax
0x18004dcf3  mov     rax, [rbp+3Fh+arg_28]
0x18004dcf7  mov     r14, r9
0x18004dcfa  mov     r12, [rbp+3Fh+SourceString]
0x18004dcfe  mov     rsi, r8
0x18004dd01  mov     [rbp+3Fh+var_78], rax
0x18004dd05  mov     r15, rdx
0x18004dd08  mov     rax, [rbp+3Fh+arg_48]
0x18004dd0f  mov     rdi, rcx
0x18004dd12  mov     [rbp+3Fh+var_68], rax
0x18004dd16  mov     [rbp+3Fh+var_70], rdx
0x18004dd1a  lea     rax, WPP_RECORDER_INITIALIZED
0x18004dd21  xor     r13d, r13d
0x18004dd24  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004dd2b  lea     rdx, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18004dd32  jnz     loc_18004E3A3
0x18004dd38  xor     ecx, ecx; PerformanceFrequency
0x18004dd3a  call    cs:__imp_KeQueryPerformanceCounter
0x18004dd41  nop     dword ptr [rax+rax+00h]
0x18004dd46  mov     [rdi+1D8h], r13b
0x18004dd4d  mov     rbx, rax
0x18004dd50  cmp     dword ptr [r14+10h], 0FFFFFFFFh
0x18004dd55  jnz     short loc_18004DD98
0x18004dd57  mov     eax, [r14+14h]
0x18004dd5b  test    al, 10h
0x18004dd5d  jnz     loc_18004E401
0x18004dd63  movups  xmm0, xmmword ptr cs:_GUID_9b365890_165f_11d0_a195_0020afd156e4.Data1
0x18004dd6a  mov     [rdi+1C0h], r13
0x18004dd71  movdqu  xmmword ptr [rdi+1ACh], xmm0
0x18004dd79  lea     rax, [rdi+40h]
0x18004dd7d  mov     [rax+8], rax
0x18004dd81  mov     [rax], rax
0x18004dd84  mov     rcx, [rsi+8]
0x18004dd88  cmp     [rcx], rsi
0x18004dd8b  jz      loc_18004E0DE
0x18004dd91  mov     ecx, 3
0x18004dd96  int     29h; Win8: RtlFailFast(ecx)
0x18004dd98  lea     rcx, WPP_RECORDER_INITIALIZED
0x18004dd9f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18004dda6  jnz     loc_18004E3D4
0x18004ddac  mov     eax, 0C0000001h
0x18004ddb1  jmp     short loc_18004DDCE
0x18004ddb3  mov     r9, [rdi+0C8h]; Bag
0x18004ddba  lea     r8, ?FilterAutomationTable@@3UKSAUTOMATION_TABLE_@@B; AutomationTableB
0x18004ddc1  call    KsMergeAutomationTables
0x18004ddc6  mov     esi, eax
0x18004ddc8  test    eax, eax
0x18004ddca  jns     short loc_18004DDFB
0x18004ddcc  mov     eax, esi
0x18004ddce  mov     rcx, [rbp+3Fh+var_50]
0x18004ddd2  xor     rcx, rsp; StackCookie
0x18004ddd5  call    __security_check_cookie
0x18004ddda  add     rsp, 98h
0x18004dde1  pop     r15
0x18004dde3  pop     r14
0x18004dde5  pop     r13
0x18004dde7  pop     r12
0x18004dde9  pop     rdi
0x18004ddea  pop     rsi
0x18004ddeb  pop     rbx
0x18004ddec  pop     rbp
0x18004dded  retn
0x18004ddef  lea     rax, ?FilterAutomationTable@@3UKSAUTOMATION_TABLE_@@B; KSAUTOMATION_TABLE_ const FilterAutomationTable
0x18004ddf6  mov     esi, ebx
0x18004ddf8  mov     [rcx], rax
0x18004ddfb  mov     edx, [r14+20h]; int
0x18004ddff  lea     rcx, [rdi+140h]; int
0x18004de06  test    edx, edx
0x18004de08  jnz     loc_18004E1FC
0x18004de0e  mov     [rcx], rbx
0x18004de11  mov     edx, [r14+40h]; int
0x18004de15  lea     rcx, [rdi+148h]; int
0x18004de1c  mov     [rdi+150h], edx
0x18004de22  test    edx, edx
0x18004de24  jz      loc_18004E2F7
0x18004de2a  mov     rax, [rdi+0C8h]
0x18004de31  mov     r9, [r14+48h]; int
0x18004de35  mov     r8d, [r14+44h]; int
0x18004de39  mov     [rsp+0D0h+Data], rax; ObjectBag
0x18004de3e  mov     qword ptr [rsp+0D0h+Size], rbx; AutomationTableB
0x18004de43  call    KspCreateAutomationTableTable
0x18004de48  mov     esi, eax
0x18004de4a  test    eax, eax
0x18004de4c  js      loc_18004DDCC
0x18004de52  xorps   xmm0, xmm0
0x18004de55  movups  xmmword ptr [rbp+3Fh+GuidString.Length], xmm0
0x18004de59  cmp     [rdi+1C0h], rbx
0x18004de60  jz      loc_18004E0BA
0x18004de66  mov     rcx, [r14+18h]; Guid
0x18004de6a  lea     rdx, [rbp+3Fh+GuidString]; GuidString
0x18004de6e  call    cs:__imp_RtlStringFromGUID
0x18004de75  nop     dword ptr [rax+rax+00h]
0x18004de7a  mov     r15d, eax
0x18004de7d  mov     esi, eax
0x18004de7f  shr     r15d, 1Fh
0x18004de83  xor     r15b, 1
0x18004de87  test    eax, eax
0x18004de89  js      loc_18004E0AE
0x18004de8f  mov     rcx, [rdi+88h]
0x18004de96  mov     rax, [rcx]
0x18004de99  mov     rax, [rax+18h]
0x18004de9d  call    _guard_dispatch_icall
0x18004dea2  mov     rcx, [rax+18h]
0x18004dea6  mov     rcx, [rcx+40h]
0x18004deaa  mov     rcx, [rcx]; BugCheckParameter2
0x18004dead  call    KsiGetBusInterface
0x18004deb2  cmp     eax, 0C00000BBh
0x18004deb7  jnz     loc_18004DFE8
0x18004debd  mov     r9d, [r14+30h]
0x18004dec1  mov     r8d, ebx
0x18004dec4  cmp     r8d, r9d
0x18004dec7  jb      loc_18004E234
0x18004decd  mov     rcx, [rdi+88h]
0x18004ded4  mov     rax, [rcx]
0x18004ded7  mov     rax, [rax+18h]
0x18004dedb  call    _guard_dispatch_icall
0x18004dee0  mov     rdx, [r14+38h]
0x18004dee4  lea     r9, [rbp+3Fh+GuidString]
0x18004dee8  mov     ecx, [r14+30h]
0x18004deec  mov     [rsp+0D0h+Data], r13
0x18004def1  mov     r8, [rax+20h]
0x18004def5  lea     rax, [rdi+0E0h]
0x18004defc  mov     qword ptr [rsp+0D0h+Size], rax
0x18004df01  call    KspRegisterDeviceInterfaces
0x18004df06  mov     esi, eax
0x18004df08  test    eax, eax
0x18004df0a  js      loc_18004E0AE
0x18004df10  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004df17  mov     rcx, [rdi+88h]
0x18004df1e  xor     r14b, r14b
0x18004df21  mov     ebx, cs:dword_18001D61C
0x18004df27  mov     r12d, cs:dword_18001D620
0x18004df2e  mov     r13d, cs:dword_18001D624
0x18004df35  movdqu  [rbp+3Fh+var_60], xmm0
0x18004df3a  mov     [rbp+3Fh+var_7C], 0
0x18004df41  mov     [rbp+3Fh+var_80], 0
0x18004df48  mov     rax, [rcx]
0x18004df4b  mov     rax, [rax+18h]
0x18004df4f  call    _guard_dispatch_icall
0x18004df54  lea     rcx, [rbp+3Fh+var_80]
0x18004df58  xor     r9d, r9d; Flags
0x18004df5b  mov     [rsp+0D0h+Type], rcx; Type
0x18004df60  lea     rdx, DEVPKEY_Device_ClassGuid; PropertyKey
0x18004df67  lea     rcx, [rbp+3Fh+var_7C]
0x18004df6b  xor     r8d, r8d; Lcid
0x18004df6e  mov     [rsp+0D0h+RequiredSize], rcx; RequiredSize
0x18004df73  lea     rcx, [rbp+3Fh+var_60]
0x18004df77  mov     [rsp+0D0h+Data], rcx; Data
0x18004df7c  mov     rcx, [rax+20h]; Pdo
0x18004df80  mov     [rsp+0D0h+Size], 10h; Size
0x18004df88  call    cs:__imp_IoGetDevicePropertyData
0x18004df8f  nop     dword ptr [rax+rax+00h]
0x18004df94  test    eax, eax
0x18004df96  js      short loc_18004DFA8
0x18004df98  cmp     dword ptr [rbp+3Fh+var_60], 6BDD1FC6h
0x18004df9f  jz      loc_18004E464
0x18004dfa5  mov     r14b, 1
0x18004dfa8  mov     rcx, rdi; this
0x18004dfab  call    ?GetProfileSymbolicName@CKsFilterFactory@@QEAAPEAU_UNICODE_STRING@@XZ; CKsFilterFactory::GetProfileSymbolicName(void)
0x18004dfb0  mov     rdx, [rdi+88h]
0x18004dfb7  mov     rbx, rax
0x18004dfba  mov     rcx, [rdx]
0x18004dfbd  mov     rax, [rcx+18h]
0x18004dfc1  mov     rcx, rdx
0x18004dfc4  call    _guard_dispatch_icall
0x18004dfc9  mov     rcx, rbx
0x18004dfcc  mov     r8, [rax+20h]
0x18004dfd0  call    ?CameraQueryDeviceCompatFlags@@YA?ATCAMERA_DEVICE_FLAGS@@PEAU_UNICODE_STRING@@W4CAMERA_COMPAT_CLASS@@PEAU_DEVICE_OBJECT@@@Z; CameraQueryDeviceCompatFlags(_UNICODE_STRING *,CAMERA_COMPAT_CLASS,_DEVICE_OBJECT *)
0x18004dfd5  xor     ebx, ebx
0x18004dfd7  test    r14b, r14b
0x18004dfda  jz      loc_18004E486
0x18004dfe0  test    al, 1
0x18004dfe2  jnz     loc_18004E486
0x18004dfe8  lea     r14, [rdi+0C0h]
0x18004dfef  mov     rcx, [r14]
0x18004dff2  call    IsVideoCameraFilter
0x18004dff7  mov     [rdi+1D8h], al
0x18004dffd  test    al, al
0x18004dfff  jnz     loc_18004E288
0x18004e005  test    esi, esi
0x18004e007  js      short loc_18004E01F
0x18004e009  mov     r9d, [rbp+3Fh+arg_30]; unsigned int
0x18004e00d  lea     rdx, [rbp+3Fh+GuidString]; struct _UNICODE_STRING *
0x18004e011  mov     r8, [rbp+3Fh+var_78]; void *
0x18004e015  mov     rcx, rdi; this
0x18004e018  call    ?AddCreateItem@CKsFilterFactory@@QEAAJPEAU_UNICODE_STRING@@PEAXK@Z; CKsFilterFactory::AddCreateItem(_UNICODE_STRING *,void *,ulong)
0x18004e01d  mov     esi, eax
0x18004e01f  test    r15b, r15b
0x18004e022  jnz     loc_18004E4E3
0x18004e028  test    esi, esi
0x18004e02a  js      loc_18004DDCC
0x18004e030  mov     rcx, [rbp+3Fh+var_70]
0x18004e034  lea     r8, [rdi+8]
0x18004e038  lea     rdx, [rdi+170h]
0x18004e03f  mov     rcx, [rcx+48h]
0x18004e043  mov     rax, [rcx]
0x18004e046  mov     rax, [rax+40h]
0x18004e04a  call    _guard_dispatch_icall
0x18004e04f  mov     rax, [rbp+3Fh+var_68]
0x18004e053  test    rax, rax
0x18004e056  jz      short loc_18004E05B
0x18004e058  mov     [rax], r14
0x18004e05b  cmp     [rdi+1C0h], rbx
0x18004e062  jnz     loc_18004E4F8
0x18004e068  mov     rcx, rdi; this
0x18004e06b  call    ?GetProfileSymbolicName@CKsFilterFactory@@QEAAPEAU_UNICODE_STRING@@XZ; CKsFilterFactory::GetProfileSymbolicName(void)
0x18004e070  test    rax, rax
0x18004e073  jz      loc_18004DDCC
0x18004e079  mov     [rsp+0D0h+RequiredSize], rbx
0x18004e07e  lea     rdx, DEVPKEY_DeviceInterface_CameraProfiles
0x18004e085  mov     dword ptr [rsp+0D0h+Data], ebx
0x18004e089  mov     r9d, 1
0x18004e08f  xor     r8d, r8d
0x18004e092  mov     [rsp+0D0h+Size], 1003h
0x18004e09a  mov     rcx, rax
0x18004e09d  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x18004e0a4  nop     dword ptr [rax+rax+00h]
0x18004e0a9  jmp     loc_18004DDCC
0x18004e0ae  lea     r14, [rdi+0C0h]
0x18004e0b5  jmp     loc_18004E01F
0x18004e0ba  mov     r15b, bl
0x18004e0bd  test    r12, r12
0x18004e0c0  jz      loc_18004E44B
0x18004e0c6  mov     rdx, r12; SourceString
0x18004e0c9  lea     rcx, [rbp+3Fh+GuidString]; DestinationString
0x18004e0cd  call    cs:__imp_RtlInitUnicodeString
0x18004e0d4  nop     dword ptr [rax+rax+00h]
0x18004e0d9  jmp     loc_18004DE8F
0x18004e0de  lea     rax, [rdi+50h]
0x18004e0e2  xor     r8d, r8d
0x18004e0e5  mov     [rax], rsi
0x18004e0e8  lea     r13, [rdi+158h]
0x18004e0ef  mov     [rax+8], rcx
0x18004e0f3  lea     rdx, [rdi+100h]
0x18004e0fa  mov     [rcx], rax
0x18004e0fd  mov     [rsi+8], rax
0x18004e101  mov     [rdi+60h], rsi
0x18004e105  mov     [rdi+68h], r15
0x18004e109  mov     dword ptr [rdi+70h], 1
0x18004e110  mov     [rdi+78h], rdi
0x18004e114  mov     rax, [r15+48h]
0x18004e118  mov     [rdi+88h], rax
0x18004e11f  lea     rax, [rdi+128h]
0x18004e126  mov     [rdi+0D8h], r15
0x18004e12d  mov     [r13+8], r13
0x18004e131  mov     [r13+0], r13
0x18004e135  mov     [rax+8], rax
0x18004e139  mov     [rax], rax
0x18004e13c  mov     rcx, [rdi+88h]
0x18004e143  mov     [rdi+0C0h], r14
0x18004e14a  mov     rax, [r15+90h]
0x18004e151  mov     [rdi+0D0h], rax
0x18004e158  mov     [rdi+0C8h], rdx
0x18004e15f  mov     rax, [rcx]
0x18004e162  mov     rax, [rax+20h]
0x18004e166  call    _guard_dispatch_icall
0x18004e16b  mov     rax, [rbp+3Fh+arg_38]
0x18004e172  lea     rcx, [rdi+138h]; AutomationTableAB
0x18004e179  mov     [rdi+0E8h], rbx
0x18004e180  xor     ebx, ebx
0x18004e182  mov     [rdi+0E0h], rdi
0x18004e189  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004e190  mov     [rdi+188h], rax
0x18004e197  mov     rax, [rbp+3Fh+arg_40]
0x18004e19e  mov     [rdi+190h], rax
0x18004e1a5  movdqu  xmmword ptr [rdi+0F0h], xmm0
0x18004e1ad  mov     dword ptr [rdi+198h], 0E5323777h
0x18004e1b7  mov     eax, dword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data2
0x18004e1bd  mov     [rdi+19Ch], eax
0x18004e1c3  mov     eax, dword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data4
0x18004e1c9  mov     [rdi+1A0h], eax
0x18004e1cf  mov     eax, dword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data4+4
0x18004e1d5  mov     [rdi+1A4h], eax
0x18004e1db  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004e1e2  movdqu  xmmword ptr [rdi+1C8h], xmm0
0x18004e1ea  mov     rdx, [r14+8]; AutomationTableA
0x18004e1ee  test    rdx, rdx
0x18004e1f1  jnz     loc_18004DDB3
0x18004e1f7  jmp     loc_18004DDEF
0x18004e1fc  mov     rax, [rdi+0C8h]
0x18004e203  mov     r9, [r14+28h]
0x18004e207  mov     r8d, [r14+24h]; int
0x18004e20b  add     r9, 8; int
0x18004e20f  mov     [rsp+0D0h+Data], rax; ObjectBag
0x18004e214  lea     rax, ?PinAutomationTable@@3UKSAUTOMATION_TABLE_@@B; KSAUTOMATION_TABLE_ const PinAutomationTable
0x18004e21b  mov     qword ptr [rsp+0D0h+Size], rax; AutomationTableB
0x18004e220  call    KspCreateAutomationTableTable
0x18004e225  mov     esi, eax
  ... truncated ...
```
