# ndisPnPAddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *,void *,void * *)

- ea: `0x140054cc0`
- end: `0x1400550fa`
- name: `?ndisPnPAddDevice@@YAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@PEAXPEAPEAX@Z`
- size: `1082`
- prototype: `__int64 __fastcall(struct _DRIVER_OBJECT *, struct _DEVICE_OBJECT *, void *, void **)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140054ca0`
- `0x1400904b0`

## callees

- `0x14001c050`
- `0x14001d350`
- `0x140029620`
- `0x140054cc0`
- `0x140055100`
- `0x140055150`
- `0x14006b010`
- `0x14006d470`
- `0x1400738c0`
- `0x1400e6160`
- `0x140136010`
- `0x140136600`
- `0x140137660`
- `0x140137800`
- `0x14015dfd0`
- `0x140161840`
- `0x1401635f0`
- `0x140163800`
- `0x140167350`
- `0x1401695b0`
- `0x140169670`
- `0x14016b300`
- `0x14017f260`

## import_xrefs

- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140054d50`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140054d50`
- `ntoskrnl!ZwClose` at `0x140054dbc`
- `ntoskrnl!ZwClose` at `0x140054ecd`
- `ntoskrnl!ZwClose` at `0x140054dbc`
- `ntoskrnl!ZwClose` at `0x140054ecd`
- `ntoskrnl!RtlGUIDFromString` at `0x140054f1c`
- `ntoskrnl!RtlGUIDFromString` at `0x140054f1c`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140054e58`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140054e58`

## string_xrefs

- `0x140055016`: `ComponentID`

## pseudocode

```c
__int64 __fastcall ndisPnPAddDevice(struct _DRIVER_OBJECT *a1, struct _DEVICE_OBJECT *a2, void *a3, void **a4)
{
  struct _DEVICE_OBJECT *v6; // rdi
  int v8; // edx
  NTSTATUS updated; // ebx
  int v10; // edx
  int v12; // edx
  int ValueBoolean; // eax
  unsigned __int8 v14; // dl
  char v15; // bl
  __int64 v16; // rcx
  __int64 v17; // r8
  char v18; // [rsp+30h] [rbp-A9h]
  bool v19; // [rsp+40h] [rbp-99h] BYREF
  bool v20; // [rsp+41h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-91h] BYREF
  PCUNICODE_STRING GuidString; // [rsp+50h] [rbp-89h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-81h] BYREF
  void *DeviceRegKey; // [rsp+60h] [rbp-79h] BYREF
  GUID Guid; // [rsp+70h] [rbp-69h] BYREF
  union _NET_LUID_LH v26; // [rsp+80h] [rbp-59h] BYREF
  __int64 v27; // [rsp+88h] [rbp-51h] BYREF
  struct _DEVICE_OBJECT *v28; // [rsp+90h] [rbp-49h]
  char v29; // [rsp+98h] [rbp-41h]
  int v30; // [rsp+9Ch] [rbp-3Dh]
  __int128 v31; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-29h]
  int v33; // [rsp+B8h] [rbp-21h]
  void *v34; // [rsp+C0h] [rbp-19h]
  unsigned __int8 v35[8]; // [rsp+C8h] [rbp-11h] BYREF
  PVOID v36; // [rsp+D0h] [rbp-9h]

  DeviceRegKey = 0;
  v6 = a2;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v18 = (char)a2;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      13,
      61,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)a1,
      v18);
  }
  updated = IoOpenDeviceRegistryKey(v6, 2u, 0xC2000000, &DeviceRegKey);
  if ( updated < 0 )
    goto LABEL_39;
  Handle = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &Handle,
    DeviceRegKey);
  v19 = 0;
  v20 = 0;
  GuidString = 0;
  updated = ndisCheckIfDeviceNeedsInstallation(&Handle, &GuidString, &v19);
  if ( updated < 0 )
    goto LABEL_5;
  if ( !v19 )
  {
    updated = ndisCheckIfDeviceNeedsPseudoMigration((KRegKey *)&Handle);
    if ( updated < 0 )
      goto LABEL_5;
    if ( !v19 )
    {
      updated = ndisCheckIfDeviceNeedsFullMigration(&Handle, &GuidString, &v19);
      if ( updated < 0 )
        goto LABEL_5;
      if ( !v19 )
      {
        updated = ndisCheckIfDeviceNeedsUpdates((KRegKey *)&Handle, &v19);
        if ( updated < 0 )
          goto LABEL_5;
        if ( !v19 )
          goto LABEL_21;
      }
    }
  }
  ZwUpdateWnfStateData(&WNF_NDIS_ADAPTER_ARRIVAL, 0, 0, 0, 0, 0, 0);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 4;
    WPP_RECORDER_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v10,
      13,
      62,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids);
  }
  updated = ndisCheckAlwaysStartFlag((KRegKey *)&Handle, &v20);
  if ( updated < 0 )
    goto LABEL_5;
  if ( v20 )
  {
LABEL_21:
    v27 = 0;
    v26.Value = 0;
    v29 = 0;
    v31 = 0;
    v33 = 0;
    *(_WORD *)v35 = 0;
    v28 = 0;
    v30 = 0;
    v32 = 0;
    v36 = 0;
    v34 = a3;
    updated = RtlGUIDFromString(GuidString, &Guid);
    if ( updated < 0 )
      goto LABEL_22;
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF__guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v12,
        13,
        63,
        (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
        (__int64)&Guid);
    }
    if ( !a3 )
      goto LABEL_29;
    ValueBoolean = KRegKey::QueryValueBoolean((KRegKey *)&Handle, L"HardwareLoopback", v35, FailIfNotFound);
    v14 = v35[0];
    if ( ValueBoolean < 0 )
      v14 = 0;
    v35[0] = v14;
    updated = ndisWdfUpdateAddDeviceParameters((struct KRegKey *)&Handle, (struct NDIS_MINIPORT_CREATION_CONFIG *)&Guid);
    if ( updated < 0 )
    {
LABEL_22:
      NDIS_MINIPORT_CREATION_CONFIG::~NDIS_MINIPORT_CREATION_CONFIG((NDIS_MINIPORT_CREATION_CONFIG *)&Guid);
    }
    else
    {
LABEL_29:
      if ( !ndisIfReadInterfaceAddDeviceParameters((struct NDIS_MINIPORT_CREATION_CONFIG *)&Guid, v6) )
      {
        v23 = 0;
        if ( (int)KRegKey::QueryValueUlong((KRegKey *)&Handle, L"IMMiniport", &v23) >= 0 )
          v15 = v23 & 1;
        else
          v15 = 0;
        KRegKey::QueryValueString(&Handle, L"ComponentID", &v31);
        if ( !a3 )
          ndisTemporarilyScribbleNetLuidIndex((KRegKey *)&Handle, &v26);
        if ( Microsoft_Windows_NDISEnableBits < 0 )
          McTemplateK0z_EtwWriteTransfer(v16, AddPnPDevice, v17, *(_QWORD *)(*((_QWORD *)&v31 + 1) + 8LL));
        v36 = ndisMiniBlockFromDriverObject(a1, v15);
        v28 = v6;
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &v27,
          Handle);
        updated = ndisAddDevice(&Guid, a4);
        NDIS_MINIPORT_CREATION_CONFIG::~NDIS_MINIPORT_CREATION_CONFIG((NDIS_MINIPORT_CREATION_CONFIG *)&Guid);
        wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&GuidString, 0);
        goto LABEL_39;
      }
      updated = -1073741823;
      NDIS_MINIPORT_CREATION_CONFIG::~NDIS_MINIPORT_CREATION_CONFIG((NDIS_MINIPORT_CREATION_CONFIG *)&Guid);
    }
LABEL_5:
    wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&GuidString, 0);
    if ( Handle )
      ZwClose(Handle);
LABEL_39:
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_qL(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v8,
        13,
        64,
        (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
        (char)v6,
        updated);
    }
    return (unsigned int)updated;
  }
  wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&GuidString, 0);
  if ( Handle )
    ZwClose(Handle);
  return 3221226645LL;
}

```

## disassembly

```asm
0x140054cc0  push    rbp
0x140054cc2  push    rbx
0x140054cc3  push    rsi
0x140054cc4  push    rdi
0x140054cc5  push    r12
0x140054cc7  push    r13
0x140054cc9  push    r14
0x140054ccb  push    r15
0x140054ccd  lea     rbp, [rsp-1Fh]
0x140054cd2  sub     rsp, 0F8h
0x140054cd9  mov     rax, cs:__security_cookie
0x140054ce0  xor     rax, rsp
0x140054ce3  mov     [rbp+57h+var_50], rax
0x140054ce7  xor     r13d, r13d
0x140054cea  mov     r15, r9
0x140054ced  mov     [rbp+57h+DeviceRegKey], r13
0x140054cf1  mov     rsi, r8
0x140054cf4  mov     rdi, rdx
0x140054cf7  mov     r14, rcx
0x140054cfa  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140054d01  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140054d08  lea     rax, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x140054d0f  jz      short loc_140054D3E
0x140054d11  mov     qword ptr [rsp+130h+var_100], rdx; char
0x140054d16  mov     r9d, 3Dh ; '='; int
0x140054d1c  mov     qword ptr [rsp+130h+var_108], rcx; char
0x140054d21  mov     r8d, 0Dh; int
0x140054d27  mov     rcx, cs:WPP_GLOBAL_Control
0x140054d2e  mov     dl, 4; int
0x140054d30  mov     [rsp+130h+var_110], rax; struct _GUID *
0x140054d35  mov     rcx, [rcx+40h]; int
0x140054d39  call    WPP_RECORDER_SF_qq
0x140054d3e  lea     r9, [rbp+57h+DeviceRegKey]; DeviceRegKey
0x140054d42  mov     edx, 2; DevInstKeyType
0x140054d47  mov     r8d, 0C2000000h; DesiredAccess
0x140054d4d  mov     rcx, rdi; DeviceObject
0x140054d50  call    cs:__imp_IoOpenDeviceRegistryKey
0x140054d57  nop     dword ptr [rax+rax+00h]
0x140054d5c  mov     ebx, eax
0x140054d5e  test    eax, eax
0x140054d60  js      loc_14005509B
0x140054d66  mov     rdx, [rbp+57h+DeviceRegKey]
0x140054d6a  lea     rcx, [rsp+130h+Handle]
0x140054d6f  mov     [rsp+130h+Handle], r13
0x140054d74  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x140054d79  lea     r8, [rsp+130h+var_F0]
0x140054d7e  mov     [rsp+130h+var_F0], r13b
0x140054d83  lea     rdx, [rsp+130h+GuidString]
0x140054d88  mov     [rsp+130h+var_EF], r13b
0x140054d8d  lea     rcx, [rsp+130h+Handle]
0x140054d92  mov     [rsp+130h+GuidString], r13
0x140054d97  call    ?ndisCheckIfDeviceNeedsInstallation@@YAJAEAVKRegKey@@AEAV?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@AEA_N@Z; ndisCheckIfDeviceNeedsInstallation(KRegKey &,wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>> &,bool &)
0x140054d9c  mov     ebx, eax
0x140054d9e  test    eax, eax
0x140054da0  jns     short loc_140054DCD
0x140054da2  xor     edx, edx
0x140054da4  lea     rcx, [rsp+130h+GuidString]
0x140054da9  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140054dae  mov     rcx, [rsp+130h+Handle]; Handle
0x140054db3  test    rcx, rcx
0x140054db6  jz      loc_14005509B
0x140054dbc  call    cs:__imp_ZwClose
0x140054dc3  nop     dword ptr [rax+rax+00h]
0x140054dc8  jmp     loc_14005509B
0x140054dcd  cmp     [rsp+130h+var_F0], r13b
0x140054dd2  jnz     short loc_140054E3A
0x140054dd4  lea     r8, [rsp+130h+var_F0]
0x140054dd9  lea     rdx, [rsp+130h+GuidString]
0x140054dde  lea     rcx, [rsp+130h+Handle]; this
0x140054de3  call    ?ndisCheckIfDeviceNeedsPseudoMigration@@YAJAEAVKRegKey@@AEAV?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@AEA_N@Z; ndisCheckIfDeviceNeedsPseudoMigration(KRegKey &,wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>> &,bool &)
0x140054de8  mov     ebx, eax
0x140054dea  test    eax, eax
0x140054dec  js      short loc_140054DA2
0x140054dee  cmp     [rsp+130h+var_F0], r13b
0x140054df3  jnz     short loc_140054E3A
0x140054df5  lea     r8, [rsp+130h+var_F0]
0x140054dfa  lea     rdx, [rsp+130h+GuidString]
0x140054dff  lea     rcx, [rsp+130h+Handle]
0x140054e04  call    ?ndisCheckIfDeviceNeedsFullMigration@@YAJAEAVKRegKey@@AEAV?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@AEA_N@Z; ndisCheckIfDeviceNeedsFullMigration(KRegKey &,wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>> &,bool &)
0x140054e09  mov     ebx, eax
0x140054e0b  test    eax, eax
0x140054e0d  js      short loc_140054DA2
0x140054e0f  cmp     [rsp+130h+var_F0], r13b
0x140054e14  jnz     short loc_140054E3A
0x140054e16  lea     rdx, [rsp+130h+var_F0]; bool *
0x140054e1b  lea     rcx, [rsp+130h+Handle]; this
0x140054e20  call    ?ndisCheckIfDeviceNeedsUpdates@@YAJAEAVKRegKey@@AEA_N@Z; ndisCheckIfDeviceNeedsUpdates(KRegKey &,bool &)
0x140054e25  mov     ebx, eax
0x140054e27  test    eax, eax
0x140054e29  js      loc_140054DA2
0x140054e2f  cmp     [rsp+130h+var_F0], r13b
0x140054e34  jz      loc_140054EE3
0x140054e3a  mov     dword ptr [rsp+130h+var_100], r13d
0x140054e3f  lea     rcx, WNF_NDIS_ADAPTER_ARRIVAL
0x140054e46  mov     dword ptr [rsp+130h+var_108], r13d
0x140054e4b  xor     r9d, r9d
0x140054e4e  xor     r8d, r8d
0x140054e51  mov     [rsp+130h+var_110], r13
0x140054e56  xor     edx, edx
0x140054e58  call    cs:__imp_ZwUpdateWnfStateData
0x140054e5f  nop     dword ptr [rax+rax+00h]
0x140054e64  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140054e6b  jz      short loc_140054E97
0x140054e6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140054e74  lea     rax, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x140054e7b  mov     r9d, 3Eh ; '>'; int
0x140054e81  mov     [rsp+130h+var_110], rax; struct _GUID *
0x140054e86  mov     r8d, 0Dh; int
0x140054e8c  mov     dl, 4; int
0x140054e8e  mov     rcx, [rcx+40h]; int
0x140054e92  call    WPP_RECORDER_SF_
0x140054e97  lea     rdx, [rsp+130h+var_EF]; bool *
0x140054e9c  lea     rcx, [rsp+130h+Handle]; this
0x140054ea1  call    ?ndisCheckAlwaysStartFlag@@YAJAEAVKRegKey@@AEA_N@Z; ndisCheckAlwaysStartFlag(KRegKey &,bool &)
0x140054ea6  mov     ebx, eax
0x140054ea8  test    eax, eax
0x140054eaa  js      loc_140054DA2
0x140054eb0  cmp     [rsp+130h+var_EF], r13b
0x140054eb5  jnz     short loc_140054EE3
0x140054eb7  xor     edx, edx
0x140054eb9  lea     rcx, [rsp+130h+GuidString]
0x140054ebe  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140054ec3  mov     rcx, [rsp+130h+Handle]; Handle
0x140054ec8  test    rcx, rcx
0x140054ecb  jz      short loc_140054ED9
0x140054ecd  call    cs:__imp_ZwClose
0x140054ed4  nop     dword ptr [rax+rax+00h]
0x140054ed9  mov     eax, 0C0000495h
0x140054ede  jmp     loc_1400550D9
0x140054ee3  mov     rcx, [rsp+130h+GuidString]; GuidString
0x140054ee8  lea     rdx, [rbp+57h+Guid]; Guid
0x140054eec  xor     eax, eax
0x140054eee  mov     [rbp+57h+var_A8], r13
0x140054ef2  xorps   xmm0, xmm0
0x140054ef5  mov     qword ptr [rbp+57h+var_B0], rax
0x140054ef9  mov     [rbp+57h+var_98], al
0x140054efc  movdqa  [rbp+57h+var_90], xmm0
0x140054f01  mov     [rbp+57h+var_78], eax
0x140054f04  mov     word ptr [rbp+57h+var_68], ax
0x140054f08  mov     [rbp+57h+var_A0], r13
0x140054f0c  mov     [rbp+57h+var_94], r13d
0x140054f10  mov     [rbp+57h+var_80], r13
0x140054f14  mov     [rbp+57h+var_60], r13
0x140054f18  mov     [rbp+57h+var_70], rsi
0x140054f1c  call    cs:__imp_RtlGUIDFromString
0x140054f23  nop     dword ptr [rax+rax+00h]
0x140054f28  mov     ebx, eax
0x140054f2a  test    eax, eax
0x140054f2c  jns     short loc_140054F3C
0x140054f2e  lea     rcx, [rbp+57h+Guid]; this
0x140054f32  call    ??1NDIS_MINIPORT_CREATION_CONFIG@@QEAA@XZ; NDIS_MINIPORT_CREATION_CONFIG::~NDIS_MINIPORT_CREATION_CONFIG(void)
0x140054f37  jmp     loc_140054DA2
0x140054f3c  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140054f43  jz      short loc_140054F78
0x140054f45  mov     rcx, cs:WPP_GLOBAL_Control
0x140054f4c  lea     rax, [rbp+57h+Guid]
0x140054f50  mov     qword ptr [rsp+130h+var_108], rax; __int64
0x140054f55  mov     r9d, 3Fh ; '?'; int
0x140054f5b  lea     rax, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x140054f62  mov     r8d, 0Dh; int
0x140054f68  mov     dl, 4; int
0x140054f6a  mov     [rsp+130h+var_110], rax; struct _GUID *
0x140054f6f  mov     rcx, [rcx+40h]; int
0x140054f73  call    WPP_RECORDER_SF__guid_
0x140054f78  test    rsi, rsi
0x140054f7b  jz      short loc_140054FC4
0x140054f7d  xor     r9d, r9d; enum KRegKey::BooleanDisposition
0x140054f80  lea     r8, [rbp+57h+var_68]; unsigned __int8 *
0x140054f84  lea     rdx, aHardwareloopba; "HardwareLoopback"
0x140054f8b  lea     rcx, [rsp+130h+Handle]; this
0x140054f90  call    ?QueryValueBoolean@KRegKey@@QEAAJPEB_WPEAEW4BooleanDisposition@1@@Z; KRegKey::QueryValueBoolean(wchar_t const *,uchar *,KRegKey::BooleanDisposition)
0x140054f95  movzx   edx, [rbp+57h+var_68]
0x140054f99  lea     rcx, [rsp+130h+Handle]; struct KRegKey *
0x140054f9e  test    eax, eax
0x140054fa0  cmovs   edx, r13d
0x140054fa4  mov     [rbp+57h+var_68], dl
0x140054fa7  lea     rdx, [rbp+57h+Guid]; struct NDIS_MINIPORT_CREATION_CONFIG *
0x140054fab  call    ?ndisWdfUpdateAddDeviceParameters@@YAJAEAVKRegKey@@AEAUNDIS_MINIPORT_CREATION_CONFIG@@@Z; ndisWdfUpdateAddDeviceParameters(KRegKey &,NDIS_MINIPORT_CREATION_CONFIG &)
0x140054fb0  mov     ebx, eax
0x140054fb2  test    eax, eax
0x140054fb4  jns     short loc_140054FC4
0x140054fb6  lea     rcx, [rbp+57h+Guid]; this
0x140054fba  call    ??1NDIS_MINIPORT_CREATION_CONFIG@@QEAA@XZ; NDIS_MINIPORT_CREATION_CONFIG::~NDIS_MINIPORT_CREATION_CONFIG(void)
0x140054fbf  jmp     loc_140054DA2
0x140054fc4  mov     rdx, rdi; struct _DEVICE_OBJECT *
0x140054fc7  lea     rcx, [rbp+57h+Guid]; struct NDIS_MINIPORT_CREATION_CONFIG *
0x140054fcb  call    ?ndisIfReadInterfaceAddDeviceParameters@@YAJAEAUNDIS_MINIPORT_CREATION_CONFIG@@PEAU_DEVICE_OBJECT@@@Z; ndisIfReadInterfaceAddDeviceParameters(NDIS_MINIPORT_CREATION_CONFIG &,_DEVICE_OBJECT *)
0x140054fd0  test    eax, eax
0x140054fd2  jz      short loc_140054FE7
0x140054fd4  lea     rcx, [rbp+57h+Guid]; this
0x140054fd8  mov     ebx, 0C0000001h
0x140054fdd  call    ??1NDIS_MINIPORT_CREATION_CONFIG@@QEAA@XZ; NDIS_MINIPORT_CREATION_CONFIG::~NDIS_MINIPORT_CREATION_CONFIG(void)
0x140054fe2  jmp     loc_140054DA2
0x140054fe7  lea     r8, [rsp+130h+var_D8]; unsigned int *
0x140054fec  mov     [rsp+130h+var_D8], r13d
0x140054ff1  lea     rdx, aImminiport; "IMMiniport"
0x140054ff8  lea     rcx, [rsp+130h+Handle]; this
0x140054ffd  call    ?QueryValueUlong@KRegKey@@QEAAJPEB_WPEAK@Z; KRegKey::QueryValueUlong(wchar_t const *,ulong *)
0x140055002  test    eax, eax
0x140055004  jns     short loc_14005500A
0x140055006  xor     bl, bl
0x140055008  jmp     short loc_140055012
0x14005500a  movzx   ebx, byte ptr [rsp+130h+var_D8]
0x14005500f  and     bl, 1
0x140055012  lea     r8, [rbp+57h+var_90]
0x140055016  lea     rdx, aComponentid; "ComponentID"
0x14005501d  lea     rcx, [rsp+130h+Handle]
0x140055022  call    ?QueryValueString@KRegKey@@QEAAJPEB_WAEAV?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@@Z; KRegKey::QueryValueString(wchar_t const *,wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>> &)
0x140055027  test    rsi, rsi
0x14005502a  jnz     short loc_14005503A
0x14005502c  lea     rdx, [rbp+57h+var_B0]; union _NET_LUID_LH *
0x140055030  lea     rcx, [rsp+130h+Handle]; this
0x140055035  call    ?ndisTemporarilyScribbleNetLuidIndex@@YAXAEAVKRegKey@@AEAT_NET_LUID_LH@@@Z; ndisTemporarilyScribbleNetLuidIndex(KRegKey &,_NET_LUID_LH &)
0x14005503a  cmp     cs:Microsoft_Windows_NDISEnableBits, r13b
0x140055041  jge     short loc_140055057
0x140055043  mov     r9, qword ptr [rbp+57h+var_90+8]
0x140055047  lea     rdx, AddPnPDevice
0x14005504e  mov     r9, [r9+8]
0x140055052  call    McTemplateK0z_EtwWriteTransfer
0x140055057  movzx   edx, bl
0x14005505a  mov     rcx, r14; DriverObject
0x14005505d  call    ndisMiniBlockFromDriverObject
0x140055062  mov     rdx, [rsp+130h+Handle]
0x140055067  lea     rcx, [rbp+57h+var_A8]
0x14005506b  mov     [rbp+57h+var_60], rax
0x14005506f  mov     [rbp+57h+var_A0], rdi
0x140055073  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x140055078  mov     rdx, r15; void **
0x14005507b  lea     rcx, [rbp+57h+Guid]; struct _GUID *
0x14005507f  call    ?ndisAddDevice@@_Y2PAGENPNP@@AJPEAUNDIS_MINIPORT_CREATION_CONFIG@@PEAPEAX@Z; ndisAddDevice(NDIS_MINIPORT_CREATION_CONFIG *,void * *)
0x140055084  lea     rcx, [rbp+57h+Guid]; this
0x140055088  mov     ebx, eax
0x14005508a  call    ??1NDIS_MINIPORT_CREATION_CONFIG@@QEAA@XZ; NDIS_MINIPORT_CREATION_CONFIG::~NDIS_MINIPORT_CREATION_CONFIG(void)
0x14005508f  xor     edx, edx
0x140055091  lea     rcx, [rsp+130h+GuidString]
0x140055096  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x14005509b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400550a2  jz      short loc_1400550D7
0x1400550a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400550ab  lea     rax, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x1400550b2  mov     dword ptr [rsp+130h+var_100], ebx; char
0x1400550b6  mov     r9d, 40h ; '@'; int
0x1400550bc  mov     qword ptr [rsp+130h+var_108], rdi; char
0x1400550c1  mov     r8d, 0Dh; int
0x1400550c7  mov     dl, 4; int
0x1400550c9  mov     [rsp+130h+var_110], rax; struct _GUID *
0x1400550ce  mov     rcx, [rcx+40h]; int
0x1400550d2  call    WPP_RECORDER_SF_qL
0x1400550d7  mov     eax, ebx
0x1400550d9  mov     rcx, [rbp+57h+var_50]
0x1400550dd  xor     rcx, rsp; StackCookie
0x1400550e0  call    __security_check_cookie
0x1400550e5  add     rsp, 0F8h
0x1400550ec  pop     r15
0x1400550ee  pop     r14
0x1400550f0  pop     r13
0x1400550f2  pop     r12
0x1400550f4  pop     rdi
0x1400550f5  pop     rsi
0x1400550f6  pop     rbx
0x1400550f7  pop     rbp
0x1400550f8  retn
```
