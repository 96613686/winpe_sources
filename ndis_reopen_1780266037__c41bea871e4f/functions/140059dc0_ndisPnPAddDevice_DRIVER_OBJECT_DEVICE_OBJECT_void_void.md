# ndisPnPAddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *,void *,void * *)

- ea: `0x140059dc0`
- end: `0x14005a1fa`
- name: `?ndisPnPAddDevice@@YAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@PEAXPEAPEAX@Z`
- size: `1082`
- prototype: `__int64 __fastcall(struct _DRIVER_OBJECT *, struct _DEVICE_OBJECT *, void *, void **)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140059da0`
- `0x140094ef0`

## callees

- `0x1400100f0`
- `0x1400114b0`
- `0x14002ab60`
- `0x140059dc0`
- `0x14005a200`
- `0x14005a250`
- `0x140070990`
- `0x140072df0`
- `0x140078fa0`
- `0x1400eb380`
- `0x14013d010`
- `0x14013d600`
- `0x14013e660`
- `0x14013e800`
- `0x140164f60`
- `0x1401687d0`
- `0x14016a580`
- `0x14016a790`
- `0x14016e1f0`
- `0x1401704a0`
- `0x140170560`
- `0x1401721f0`
- `0x140185810`

## import_xrefs

- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140059e50`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140059e50`
- `ntoskrnl!ZwClose` at `0x140059ebc`
- `ntoskrnl!ZwClose` at `0x140059fcd`
- `ntoskrnl!ZwClose` at `0x140059ebc`
- `ntoskrnl!ZwClose` at `0x140059fcd`
- `ntoskrnl!RtlGUIDFromString` at `0x14005a01c`
- `ntoskrnl!RtlGUIDFromString` at `0x14005a01c`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140059f58`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140059f58`

## string_xrefs

- `0x14005a116`: `ComponentID`

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
0x140059dc0  push    rbp
0x140059dc2  push    rbx
0x140059dc3  push    rsi
0x140059dc4  push    rdi
0x140059dc5  push    r12
0x140059dc7  push    r13
0x140059dc9  push    r14
0x140059dcb  push    r15
0x140059dcd  lea     rbp, [rsp-1Fh]
0x140059dd2  sub     rsp, 0F8h
0x140059dd9  mov     rax, cs:__security_cookie
0x140059de0  xor     rax, rsp
0x140059de3  mov     [rbp+57h+var_50], rax
0x140059de7  xor     r13d, r13d
0x140059dea  mov     r15, r9
0x140059ded  mov     [rbp+57h+DeviceRegKey], r13
0x140059df1  mov     rsi, r8
0x140059df4  mov     rdi, rdx
0x140059df7  mov     r14, rcx
0x140059dfa  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140059e01  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140059e08  lea     rax, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x140059e0f  jz      short loc_140059E3E
0x140059e11  mov     qword ptr [rsp+130h+var_100], rdx; char
0x140059e16  mov     r9d, 3Dh ; '='; int
0x140059e1c  mov     qword ptr [rsp+130h+var_108], rcx; char
0x140059e21  mov     r8d, 0Dh; int
0x140059e27  mov     rcx, cs:WPP_GLOBAL_Control
0x140059e2e  mov     dl, 4; int
0x140059e30  mov     [rsp+130h+var_110], rax; struct _GUID *
0x140059e35  mov     rcx, [rcx+40h]; int
0x140059e39  call    WPP_RECORDER_SF_qq
0x140059e3e  lea     r9, [rbp+57h+DeviceRegKey]; DeviceRegKey
0x140059e42  mov     edx, 2; DevInstKeyType
0x140059e47  mov     r8d, 0C2000000h; DesiredAccess
0x140059e4d  mov     rcx, rdi; DeviceObject
0x140059e50  call    cs:__imp_IoOpenDeviceRegistryKey
0x140059e57  nop     dword ptr [rax+rax+00h]
0x140059e5c  mov     ebx, eax
0x140059e5e  test    eax, eax
0x140059e60  js      loc_14005A19B
0x140059e66  mov     rdx, [rbp+57h+DeviceRegKey]
0x140059e6a  lea     rcx, [rsp+130h+Handle]
0x140059e6f  mov     [rsp+130h+Handle], r13
0x140059e74  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x140059e79  lea     r8, [rsp+130h+var_F0]
0x140059e7e  mov     [rsp+130h+var_F0], r13b
0x140059e83  lea     rdx, [rsp+130h+GuidString]
0x140059e88  mov     [rsp+130h+var_EF], r13b
0x140059e8d  lea     rcx, [rsp+130h+Handle]
0x140059e92  mov     [rsp+130h+GuidString], r13
0x140059e97  call    ?ndisCheckIfDeviceNeedsInstallation@@YAJAEAVKRegKey@@AEAV?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@AEA_N@Z; ndisCheckIfDeviceNeedsInstallation(KRegKey &,wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>> &,bool &)
0x140059e9c  mov     ebx, eax
0x140059e9e  test    eax, eax
0x140059ea0  jns     short loc_140059ECD
0x140059ea2  xor     edx, edx
0x140059ea4  lea     rcx, [rsp+130h+GuidString]
0x140059ea9  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140059eae  mov     rcx, [rsp+130h+Handle]; Handle
0x140059eb3  test    rcx, rcx
0x140059eb6  jz      loc_14005A19B
0x140059ebc  call    cs:__imp_ZwClose
0x140059ec3  nop     dword ptr [rax+rax+00h]
0x140059ec8  jmp     loc_14005A19B
0x140059ecd  cmp     [rsp+130h+var_F0], r13b
0x140059ed2  jnz     short loc_140059F3A
0x140059ed4  lea     r8, [rsp+130h+var_F0]
0x140059ed9  lea     rdx, [rsp+130h+GuidString]
0x140059ede  lea     rcx, [rsp+130h+Handle]; this
0x140059ee3  call    ?ndisCheckIfDeviceNeedsPseudoMigration@@YAJAEAVKRegKey@@AEAV?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@AEA_N@Z; ndisCheckIfDeviceNeedsPseudoMigration(KRegKey &,wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>> &,bool &)
0x140059ee8  mov     ebx, eax
0x140059eea  test    eax, eax
0x140059eec  js      short loc_140059EA2
0x140059eee  cmp     [rsp+130h+var_F0], r13b
0x140059ef3  jnz     short loc_140059F3A
0x140059ef5  lea     r8, [rsp+130h+var_F0]
0x140059efa  lea     rdx, [rsp+130h+GuidString]
0x140059eff  lea     rcx, [rsp+130h+Handle]
0x140059f04  call    ?ndisCheckIfDeviceNeedsFullMigration@@YAJAEAVKRegKey@@AEAV?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@AEA_N@Z; ndisCheckIfDeviceNeedsFullMigration(KRegKey &,wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>> &,bool &)
0x140059f09  mov     ebx, eax
0x140059f0b  test    eax, eax
0x140059f0d  js      short loc_140059EA2
0x140059f0f  cmp     [rsp+130h+var_F0], r13b
0x140059f14  jnz     short loc_140059F3A
0x140059f16  lea     rdx, [rsp+130h+var_F0]; bool *
0x140059f1b  lea     rcx, [rsp+130h+Handle]; this
0x140059f20  call    ?ndisCheckIfDeviceNeedsUpdates@@YAJAEAVKRegKey@@AEA_N@Z; ndisCheckIfDeviceNeedsUpdates(KRegKey &,bool &)
0x140059f25  mov     ebx, eax
0x140059f27  test    eax, eax
0x140059f29  js      loc_140059EA2
0x140059f2f  cmp     [rsp+130h+var_F0], r13b
0x140059f34  jz      loc_140059FE3
0x140059f3a  mov     dword ptr [rsp+130h+var_100], r13d
0x140059f3f  lea     rcx, WNF_NDIS_ADAPTER_ARRIVAL
0x140059f46  mov     dword ptr [rsp+130h+var_108], r13d
0x140059f4b  xor     r9d, r9d
0x140059f4e  xor     r8d, r8d
0x140059f51  mov     [rsp+130h+var_110], r13
0x140059f56  xor     edx, edx
0x140059f58  call    cs:__imp_ZwUpdateWnfStateData
0x140059f5f  nop     dword ptr [rax+rax+00h]
0x140059f64  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140059f6b  jz      short loc_140059F97
0x140059f6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140059f74  lea     rax, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x140059f7b  mov     r9d, 3Eh ; '>'; int
0x140059f81  mov     [rsp+130h+var_110], rax; struct _GUID *
0x140059f86  mov     r8d, 0Dh; int
0x140059f8c  mov     dl, 4; int
0x140059f8e  mov     rcx, [rcx+40h]; int
0x140059f92  call    WPP_RECORDER_SF_
0x140059f97  lea     rdx, [rsp+130h+var_EF]; bool *
0x140059f9c  lea     rcx, [rsp+130h+Handle]; this
0x140059fa1  call    ?ndisCheckAlwaysStartFlag@@YAJAEAVKRegKey@@AEA_N@Z; ndisCheckAlwaysStartFlag(KRegKey &,bool &)
0x140059fa6  mov     ebx, eax
0x140059fa8  test    eax, eax
0x140059faa  js      loc_140059EA2
0x140059fb0  cmp     [rsp+130h+var_EF], r13b
0x140059fb5  jnz     short loc_140059FE3
0x140059fb7  xor     edx, edx
0x140059fb9  lea     rcx, [rsp+130h+GuidString]
0x140059fbe  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140059fc3  mov     rcx, [rsp+130h+Handle]; Handle
0x140059fc8  test    rcx, rcx
0x140059fcb  jz      short loc_140059FD9
0x140059fcd  call    cs:__imp_ZwClose
0x140059fd4  nop     dword ptr [rax+rax+00h]
0x140059fd9  mov     eax, 0C0000495h
0x140059fde  jmp     loc_14005A1D9
0x140059fe3  mov     rcx, [rsp+130h+GuidString]; GuidString
0x140059fe8  lea     rdx, [rbp+57h+Guid]; Guid
0x140059fec  xor     eax, eax
0x140059fee  mov     [rbp+57h+var_A8], r13
0x140059ff2  xorps   xmm0, xmm0
0x140059ff5  mov     qword ptr [rbp+57h+var_B0], rax
0x140059ff9  mov     [rbp+57h+var_98], al
0x140059ffc  movdqa  [rbp+57h+var_90], xmm0
0x14005a001  mov     [rbp+57h+var_78], eax
0x14005a004  mov     word ptr [rbp+57h+var_68], ax
0x14005a008  mov     [rbp+57h+var_A0], r13
0x14005a00c  mov     [rbp+57h+var_94], r13d
0x14005a010  mov     [rbp+57h+var_80], r13
0x14005a014  mov     [rbp+57h+var_60], r13
0x14005a018  mov     [rbp+57h+var_70], rsi
0x14005a01c  call    cs:__imp_RtlGUIDFromString
0x14005a023  nop     dword ptr [rax+rax+00h]
0x14005a028  mov     ebx, eax
0x14005a02a  test    eax, eax
0x14005a02c  jns     short loc_14005A03C
0x14005a02e  lea     rcx, [rbp+57h+Guid]; this
0x14005a032  call    ??1NDIS_MINIPORT_CREATION_CONFIG@@QEAA@XZ; NDIS_MINIPORT_CREATION_CONFIG::~NDIS_MINIPORT_CREATION_CONFIG(void)
0x14005a037  jmp     loc_140059EA2
0x14005a03c  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14005a043  jz      short loc_14005A078
0x14005a045  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a04c  lea     rax, [rbp+57h+Guid]
0x14005a050  mov     qword ptr [rsp+130h+var_108], rax; __int64
0x14005a055  mov     r9d, 3Fh ; '?'; int
0x14005a05b  lea     rax, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14005a062  mov     r8d, 0Dh; int
0x14005a068  mov     dl, 4; int
0x14005a06a  mov     [rsp+130h+var_110], rax; struct _GUID *
0x14005a06f  mov     rcx, [rcx+40h]; int
0x14005a073  call    WPP_RECORDER_SF__guid_
0x14005a078  test    rsi, rsi
0x14005a07b  jz      short loc_14005A0C4
0x14005a07d  xor     r9d, r9d; enum KRegKey::BooleanDisposition
0x14005a080  lea     r8, [rbp+57h+var_68]; unsigned __int8 *
0x14005a084  lea     rdx, aHardwareloopba; "HardwareLoopback"
0x14005a08b  lea     rcx, [rsp+130h+Handle]; this
0x14005a090  call    ?QueryValueBoolean@KRegKey@@QEAAJPEB_WPEAEW4BooleanDisposition@1@@Z; KRegKey::QueryValueBoolean(wchar_t const *,uchar *,KRegKey::BooleanDisposition)
0x14005a095  movzx   edx, [rbp+57h+var_68]
0x14005a099  lea     rcx, [rsp+130h+Handle]; struct KRegKey *
0x14005a09e  test    eax, eax
0x14005a0a0  cmovs   edx, r13d
0x14005a0a4  mov     [rbp+57h+var_68], dl
0x14005a0a7  lea     rdx, [rbp+57h+Guid]; struct NDIS_MINIPORT_CREATION_CONFIG *
0x14005a0ab  call    ?ndisWdfUpdateAddDeviceParameters@@YAJAEAVKRegKey@@AEAUNDIS_MINIPORT_CREATION_CONFIG@@@Z; ndisWdfUpdateAddDeviceParameters(KRegKey &,NDIS_MINIPORT_CREATION_CONFIG &)
0x14005a0b0  mov     ebx, eax
0x14005a0b2  test    eax, eax
0x14005a0b4  jns     short loc_14005A0C4
0x14005a0b6  lea     rcx, [rbp+57h+Guid]; this
0x14005a0ba  call    ??1NDIS_MINIPORT_CREATION_CONFIG@@QEAA@XZ; NDIS_MINIPORT_CREATION_CONFIG::~NDIS_MINIPORT_CREATION_CONFIG(void)
0x14005a0bf  jmp     loc_140059EA2
0x14005a0c4  mov     rdx, rdi; struct _DEVICE_OBJECT *
0x14005a0c7  lea     rcx, [rbp+57h+Guid]; struct NDIS_MINIPORT_CREATION_CONFIG *
0x14005a0cb  call    ?ndisIfReadInterfaceAddDeviceParameters@@YAJAEAUNDIS_MINIPORT_CREATION_CONFIG@@PEAU_DEVICE_OBJECT@@@Z; ndisIfReadInterfaceAddDeviceParameters(NDIS_MINIPORT_CREATION_CONFIG &,_DEVICE_OBJECT *)
0x14005a0d0  test    eax, eax
0x14005a0d2  jz      short loc_14005A0E7
0x14005a0d4  lea     rcx, [rbp+57h+Guid]; this
0x14005a0d8  mov     ebx, 0C0000001h
0x14005a0dd  call    ??1NDIS_MINIPORT_CREATION_CONFIG@@QEAA@XZ; NDIS_MINIPORT_CREATION_CONFIG::~NDIS_MINIPORT_CREATION_CONFIG(void)
0x14005a0e2  jmp     loc_140059EA2
0x14005a0e7  lea     r8, [rsp+130h+var_D8]; unsigned int *
0x14005a0ec  mov     [rsp+130h+var_D8], r13d
0x14005a0f1  lea     rdx, aImminiport; "IMMiniport"
0x14005a0f8  lea     rcx, [rsp+130h+Handle]; this
0x14005a0fd  call    ?QueryValueUlong@KRegKey@@QEAAJPEB_WPEAK@Z; KRegKey::QueryValueUlong(wchar_t const *,ulong *)
0x14005a102  test    eax, eax
0x14005a104  jns     short loc_14005A10A
0x14005a106  xor     bl, bl
0x14005a108  jmp     short loc_14005A112
0x14005a10a  movzx   ebx, byte ptr [rsp+130h+var_D8]
0x14005a10f  and     bl, 1
0x14005a112  lea     r8, [rbp+57h+var_90]
0x14005a116  lea     rdx, aComponentid; "ComponentID"
0x14005a11d  lea     rcx, [rsp+130h+Handle]
0x14005a122  call    ?QueryValueString@KRegKey@@QEAAJPEB_WAEAV?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@@Z; KRegKey::QueryValueString(wchar_t const *,wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>> &)
0x14005a127  test    rsi, rsi
0x14005a12a  jnz     short loc_14005A13A
0x14005a12c  lea     rdx, [rbp+57h+var_B0]; union _NET_LUID_LH *
0x14005a130  lea     rcx, [rsp+130h+Handle]; this
0x14005a135  call    ?ndisTemporarilyScribbleNetLuidIndex@@YAXAEAVKRegKey@@AEAT_NET_LUID_LH@@@Z; ndisTemporarilyScribbleNetLuidIndex(KRegKey &,_NET_LUID_LH &)
0x14005a13a  cmp     cs:Microsoft_Windows_NDISEnableBits, r13b
0x14005a141  jge     short loc_14005A157
0x14005a143  mov     r9, qword ptr [rbp+57h+var_90+8]
0x14005a147  lea     rdx, AddPnPDevice
0x14005a14e  mov     r9, [r9+8]
0x14005a152  call    McTemplateK0z_EtwWriteTransfer
0x14005a157  movzx   edx, bl
0x14005a15a  mov     rcx, r14; DriverObject
0x14005a15d  call    ndisMiniBlockFromDriverObject
0x14005a162  mov     rdx, [rsp+130h+Handle]
0x14005a167  lea     rcx, [rbp+57h+var_A8]
0x14005a16b  mov     [rbp+57h+var_60], rax
0x14005a16f  mov     [rbp+57h+var_A0], rdi
0x14005a173  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14005a178  mov     rdx, r15; void **
0x14005a17b  lea     rcx, [rbp+57h+Guid]; struct _GUID *
0x14005a17f  call    ?ndisAddDevice@@_Y2PAGENPNP@@AJPEAUNDIS_MINIPORT_CREATION_CONFIG@@PEAPEAX@Z; ndisAddDevice(NDIS_MINIPORT_CREATION_CONFIG *,void * *)
0x14005a184  lea     rcx, [rbp+57h+Guid]; this
0x14005a188  mov     ebx, eax
0x14005a18a  call    ??1NDIS_MINIPORT_CREATION_CONFIG@@QEAA@XZ; NDIS_MINIPORT_CREATION_CONFIG::~NDIS_MINIPORT_CREATION_CONFIG(void)
0x14005a18f  xor     edx, edx
0x14005a191  lea     rcx, [rsp+130h+GuidString]
0x14005a196  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x14005a19b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14005a1a2  jz      short loc_14005A1D7
0x14005a1a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a1ab  lea     rax, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14005a1b2  mov     dword ptr [rsp+130h+var_100], ebx; char
0x14005a1b6  mov     r9d, 40h ; '@'; int
0x14005a1bc  mov     qword ptr [rsp+130h+var_108], rdi; char
0x14005a1c1  mov     r8d, 0Dh; int
0x14005a1c7  mov     dl, 4; int
0x14005a1c9  mov     [rsp+130h+var_110], rax; struct _GUID *
0x14005a1ce  mov     rcx, [rcx+40h]; int
0x14005a1d2  call    WPP_RECORDER_SF_qL
0x14005a1d7  mov     eax, ebx
0x14005a1d9  mov     rcx, [rbp+57h+var_50]
0x14005a1dd  xor     rcx, rsp; StackCookie
0x14005a1e0  call    __security_check_cookie
0x14005a1e5  add     rsp, 0F8h
0x14005a1ec  pop     r15
0x14005a1ee  pop     r14
0x14005a1f0  pop     r13
0x14005a1f2  pop     r12
0x14005a1f4  pop     rdi
0x14005a1f5  pop     rsi
0x14005a1f6  pop     rbx
0x14005a1f7  pop     rbp
0x14005a1f8  retn
```
