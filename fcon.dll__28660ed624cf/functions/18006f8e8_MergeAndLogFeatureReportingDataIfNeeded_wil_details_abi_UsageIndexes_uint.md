# MergeAndLogFeatureReportingDataIfNeeded(wil::details_abi::UsageIndexes &,uint)

- ea: `0x18006f8e8`
- end: `0x18006fbef`
- name: `?MergeAndLogFeatureReportingDataIfNeeded@@YAXAEAUUsageIndexes@details_abi@wil@@I@Z`
- size: `775`
- prototype: `void __fastcall(struct wil::details_abi::UsageIndexes *, int)`
- caller_count: `2`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006f3f4`
- `0x18006fbf8`

## callees

- `0x180003244`
- `0x180004b80`
- `0x180005fe8`
- `0x180006ae8`
- `0x1800109ac`
- `0x18002a9a0`
- `0x180034644`
- `0x18004b4dc`
- `0x18005d990`
- `0x18006f180`
- `0x18006f8e8`
- `0x18006fcec`
- `0x180070e90`
- `0x180070f24`
- `0x1800711a0`
- `0x180071a94`
- `0x180071c90`
- `0x180071d44`
- `0x180071eac`
- `0x18007213c`
- `0x18007255c`

## import_xrefs

- `ntdll!NtCreateMutant` at `0x18006f98c`
- `ntdll!NtCreateMutant` at `0x18006f98c`
- `ntdll!RtlInitUnicodeString` at `0x18006f93a`
- `ntdll!RtlInitUnicodeString` at `0x18006f93a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006f9b9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006f9b9`

## string_xrefs

- `0x18006fbc8`: `onecore\base\flighting\featuremanagement\libs\usagereporting\clientconfiguration.cpp`

## pseudocode

```c
void __fastcall MergeAndLogFeatureReportingDataIfNeeded(struct wil::details_abi::UsageIndexes *a1, int a2)
{
  NTSTATUS v4; // eax
  const char *v5; // r9
  unsigned int i; // ebx
  unsigned int v7; // edi
  ClientConfiguration *v8; // r15
  _OWORD *v9; // r14
  wil::filetime *v10; // rcx
  unsigned __int64 v11; // rsi
  struct _FILETIME system_time; // rbx
  struct _FILETIME LastLoggedTime; // rax
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  ClientConfiguration *v21; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v22; // [rsp+38h] [rbp-C8h]
  void *v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[16]; // [rsp+48h] [rbp-B8h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v27[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v28[24]; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD v29[39]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]
  void *MutantHandle; // [rsp+350h] [rbp+250h] BYREF
  struct _FILETIME v32; // [rsp+358h] [rbp+258h] BYREF

  MutantHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\FeatureUsageReportingMutex");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 128;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &MutantHandle,
    0);
  v4 = NtCreateMutant(&MutantHandle, 0x100000u, &ObjectAttributes, 0);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\usagereporting\\usagereportingmanager.cpp",
      (const char *)(unsigned int)v4,
      v19);
  if ( WaitForSingleObject(MutantHandle, 0xFFFFFFFF) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\usagereporting\\usagereportingmanager.cpp",
      v5);
  v23 = MutantHandle;
  MakeClientConfiguration(&v21);
  `eh vector constructor iterator'(
    v29,
    0x120u,
    2u,
    (void (*)(void *))LoadedUsageIndexes::LoadedUsageIndexes,
    (void (*)(void *))LoadedUsageIndexes::~LoadedUsageIndexes);
  for ( i = 0; i < 2; ++i )
  {
    std::shared_ptr<unsigned char>::shared_ptr<unsigned char>(v24, &v21);
    UsageReporting::LoadReportingData((wil::details_abi::RawUsageIndex *)&v29[18 * (int)i]);
  }
  v7 = 0;
  v8 = v21;
  do
  {
    v9 = &v29[18 * (int)v7];
    UsageReporting::MergeUsageIndexes(v9, a1, v7);
    if ( ((unsigned int)UsageReporting::FeatureReportingCadenceToFlag(v7) & a2) != 0 )
    {
      v11 = 0;
      system_time = wil::filetime::get_system_time(v10);
      v32 = system_time;
      LastLoggedTime = ClientConfiguration::GetLastLoggedTime(v8);
      v14 = *(unsigned int *)LastLoggedTime.dwLowDateTime
          + ((unsigned __int64)*(unsigned int *)(*(_QWORD *)&LastLoggedTime + 4LL) << 32);
      if ( v14 )
      {
        v15 = system_time.dwLowDateTime + ((unsigned __int64)v32.dwHighDateTime << 32);
        if ( v15 > v14 )
          v11 = (v15 - v14) / 0x2710;
      }
      UsageReporting::LogData(v9, v11, v7);
      v32 = system_time;
      v16 = RegValet::SetValue::_Set(*(HKEY *)v8, L"TimeSinceLastLog", 0xBu, &v32, 8u);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2A,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\usagereporting\\clientconfiguration.cpp",
          (const char *)(unsigned int)v16,
          v20);
      v17 = std::shared_ptr<unsigned char>::shared_ptr<unsigned char>(v27, &v21);
      UsageReporting::ClearReportingData(v7, v17);
    }
    else
    {
      v18 = std::shared_ptr<unsigned char>::shared_ptr<unsigned char>(v28, &v21);
      UsageReporting::SaveReportingData(v9, v7, v18);
    }
    ++v7;
  }
  while ( v7 < 2 );
  `eh vector destructor iterator'(v29, 0x120u, 2u, (void (*)(void *))LoadedUsageIndexes::~LoadedUsageIndexes);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&MutantHandle);
}

```

## disassembly

```asm
0x18006f8e8  mov     [rsp-8+arg_0], rbx
0x18006f8ed  push    rbp
0x18006f8ee  push    rsi
0x18006f8ef  push    rdi
0x18006f8f0  push    r12
0x18006f8f2  push    r13
0x18006f8f4  push    r14
0x18006f8f6  push    r15
0x18006f8f8  lea     rbp, [rsp-200h]
0x18006f900  sub     rsp, 300h
0x18006f907  mov     r12d, edx
0x18006f90a  mov     r13, rcx
0x18006f90d  mov     [rbp+230h+MutantHandle], 0
0x18006f918  xorps   xmm0, xmm0
0x18006f91b  movups  xmmword ptr [rsp+330h+ObjectAttributes.Length], xmm0
0x18006f920  movups  xmmword ptr [rsp+330h+ObjectAttributes.ObjectName], xmm0
0x18006f925  movups  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006f929  movups  xmmword ptr [rsp+330h+DestinationString.Length], xmm0
0x18006f92e  lea     rdx, SourceString; "\\FeatureUsageReportingMutex"
0x18006f935  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x18006f93a  call    cs:__imp_RtlInitUnicodeString
0x18006f940  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x18006f948  mov     [rsp+330h+ObjectAttributes.RootDirectory], 0
0x18006f951  mov     [rbp+230h+ObjectAttributes.Attributes], 80h
0x18006f958  lea     rax, [rsp+330h+DestinationString]
0x18006f95d  mov     [rsp+330h+ObjectAttributes.ObjectName], rax
0x18006f962  xorps   xmm0, xmm0
0x18006f965  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006f96a  xor     edx, edx
0x18006f96c  lea     rcx, [rbp+230h+MutantHandle]
0x18006f973  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006f978  xor     r9d, r9d; InitialOwner
0x18006f97b  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x18006f980  mov     edx, 100000h; DesiredAccess
0x18006f985  lea     rcx, [rbp+230h+MutantHandle]; MutantHandle
0x18006f98c  call    cs:__imp_NtCreateMutant
0x18006f992  cmp     eax, 40000000h
0x18006f997  jz      short loc_18006F9A8
0x18006f999  mov     rcx, [rbp+238h]; this
0x18006f9a0  test    eax, eax
0x18006f9a2  js      loc_18006FBDA
0x18006f9a8  mov     rbx, [rbp+238h]
0x18006f9af  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18006f9b2  mov     rcx, [rbp+230h+MutantHandle]; hHandle
0x18006f9b9  call    cs:__imp_WaitForSingleObject
0x18006f9bf  test    eax, eax
0x18006f9c1  jnz     loc_18006FBB0
0x18006f9c7  mov     rax, [rbp+230h+MutantHandle]
0x18006f9ce  mov     [rsp+330h+var_2F0], rax
0x18006f9d3  lea     rcx, [rsp+330h+var_300]
0x18006f9d8  call    ?MakeClientConfiguration@@YA?AV?$shared_ptr@VClientConfiguration@@@std@@XZ; MakeClientConfiguration(void)
0x18006f9dd  nop
0x18006f9de  lea     rax, ??1LoadedUsageIndexes@@QEAA@XZ; LoadedUsageIndexes::~LoadedUsageIndexes(void)
0x18006f9e5  mov     qword ptr [rsp+330h+var_310], rax; void (*)(void *)
0x18006f9ea  lea     r9, ??0LoadedUsageIndexes@@QEAA@XZ; void (*)(void *)
0x18006f9f1  mov     edx, 120h; unsigned __int64
0x18006f9f6  mov     r8d, 2; unsigned __int64
0x18006f9fc  lea     rcx, [rbp+230h+var_270]; void *
0x18006fa00  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18006fa05  nop
0x18006fa06  xor     ebx, ebx
0x18006fa08  lea     rdx, [rsp+330h+var_300]
0x18006fa0d  lea     rcx, [rsp+330h+var_2E8]
0x18006fa12  call    ??0?$shared_ptr@E@std@@QEAA@AEBV01@@Z; std::shared_ptr<uchar>::shared_ptr<uchar>(std::shared_ptr<uchar> const &)
0x18006fa17  movsxd  rcx, ebx
0x18006fa1a  lea     rdx, [rcx+rcx*8]
0x18006fa1e  shl     rdx, 5
0x18006fa22  lea     rcx, [rbp+230h+var_270]
0x18006fa26  add     rcx, rdx; wil::details_abi::RawUsageIndex *
0x18006fa29  mov     r8, rax
0x18006fa2c  mov     edx, ebx
0x18006fa2e  call    ?LoadReportingData@UsageReporting@@SAXAEAULoadedUsageIndexes@@W4FeatureReportingCadence@@V?$shared_ptr@VClientConfiguration@@@std@@@Z; UsageReporting::LoadReportingData(LoadedUsageIndexes &,FeatureReportingCadence,std::shared_ptr<ClientConfiguration>)
0x18006fa33  inc     ebx
0x18006fa35  cmp     ebx, 2
0x18006fa38  jb      short loc_18006FA08
0x18006fa3a  xor     edi, edi
0x18006fa3c  mov     r15, [rsp+330h+var_300]
0x18006fa41  movsxd  rax, edi
0x18006fa44  lea     rcx, [rax+rax*8]
0x18006fa48  shl     rcx, 5
0x18006fa4c  lea     r14, [rbp+230h+var_270]
0x18006fa50  add     r14, rcx
0x18006fa53  mov     r8d, edi
0x18006fa56  mov     rdx, r13
0x18006fa59  mov     rcx, r14
0x18006fa5c  call    ?MergeUsageIndexes@UsageReporting@@SAXAEAUUsageIndexes@details_abi@wil@@AEBU234@W4FeatureReportingCadence@@@Z; UsageReporting::MergeUsageIndexes(wil::details_abi::UsageIndexes &,wil::details_abi::UsageIndexes const &,FeatureReportingCadence)
0x18006fa61  mov     ecx, edi
0x18006fa63  call    ?FeatureReportingCadenceToFlag@UsageReporting@@SAIW4FeatureReportingCadence@@@Z; UsageReporting::FeatureReportingCadenceToFlag(FeatureReportingCadence)
0x18006fa68  test    r12d, eax
0x18006fa6b  jz      loc_18006FB2C
0x18006fa71  xor     esi, esi
0x18006fa73  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x18006fa78  mov     rbx, rax
0x18006fa7b  mov     [rbp+230h+arg_18], rax
0x18006fa82  lea     rdx, [rsp+330h+var_2E8]
0x18006fa87  mov     rcx, r15; this
0x18006fa8a  call    ?GetLastLoggedTime@ClientConfiguration@@QEBA?AU_FILETIME@@XZ; ClientConfiguration::GetLastLoggedTime(void)
0x18006fa8f  mov     r8d, [rax+4]
0x18006fa93  shl     r8, 20h
0x18006fa97  mov     eax, [rax]
0x18006fa99  add     r8, rax
0x18006fa9c  jz      short loc_18006FAC9
0x18006fa9e  mov     edx, dword ptr [rbp+230h+arg_18+4]
0x18006faa4  shl     rdx, 20h
0x18006faa8  mov     eax, ebx
0x18006faaa  add     rdx, rax
0x18006faad  cmp     rdx, r8
0x18006fab0  jbe     short loc_18006FAC9
0x18006fab2  sub     rdx, r8
0x18006fab5  mov     rax, 346DC5D63886594Bh
0x18006fabf  mul     rdx
0x18006fac2  mov     rsi, rdx
0x18006fac5  shr     rsi, 0Bh
0x18006fac9  mov     r8d, edi
0x18006facc  mov     rdx, rsi
0x18006facf  mov     rcx, r14
0x18006fad2  call    ?LogData@UsageReporting@@SAXAEBUUsageIndexes@details_abi@wil@@_KW4FeatureReportingCadence@@@Z; UsageReporting::LogData(wil::details_abi::UsageIndexes const &,unsigned __int64,FeatureReportingCadence)
0x18006fad7  mov     [rbp+230h+arg_18], rbx
0x18006fade  mov     qword ptr [rsp+330h+var_310], 8; int
0x18006fae7  lea     r9, [rbp+230h+arg_18]; void *
0x18006faee  mov     r8d, 0Bh; unsigned int
0x18006faf4  lea     rdx, ?c_regvalTimeSinceLastLog@ClientConfiguration@@0QBGB; "TimeSinceLastLog"
0x18006fafb  mov     rcx, [r15]; HKEY
0x18006fafe  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18006fb03  mov     rcx, [rbp+238h]; this
0x18006fb0a  test    eax, eax
0x18006fb0c  js      loc_18006FBC5
0x18006fb12  lea     rdx, [rsp+330h+var_300]
0x18006fb17  lea     rcx, [rbp+230h+var_298]
0x18006fb1b  call    ??0?$shared_ptr@E@std@@QEAA@AEBV01@@Z; std::shared_ptr<uchar>::shared_ptr<uchar>(std::shared_ptr<uchar> const &)
0x18006fb20  mov     rdx, rax
0x18006fb23  mov     ecx, edi
0x18006fb25  call    ?ClearReportingData@UsageReporting@@SAXW4FeatureReportingCadence@@V?$shared_ptr@VClientConfiguration@@@std@@@Z; UsageReporting::ClearReportingData(FeatureReportingCadence,std::shared_ptr<ClientConfiguration>)
0x18006fb2a  jmp     short loc_18006FB47
0x18006fb2c  lea     rdx, [rsp+330h+var_300]
0x18006fb31  lea     rcx, [rbp+230h+var_288]
0x18006fb35  call    ??0?$shared_ptr@E@std@@QEAA@AEBV01@@Z; std::shared_ptr<uchar>::shared_ptr<uchar>(std::shared_ptr<uchar> const &)
0x18006fb3a  mov     r8, rax
0x18006fb3d  mov     edx, edi
0x18006fb3f  mov     rcx, r14
0x18006fb42  call    ?SaveReportingData@UsageReporting@@SAXAEBUUsageIndexes@details_abi@wil@@W4FeatureReportingCadence@@V?$shared_ptr@VClientConfiguration@@@std@@@Z; UsageReporting::SaveReportingData(wil::details_abi::UsageIndexes const &,FeatureReportingCadence,std::shared_ptr<ClientConfiguration>)
0x18006fb47  inc     edi
0x18006fb49  cmp     edi, 2
0x18006fb4c  jb      loc_18006FA41
0x18006fb52  lea     r9, ??1LoadedUsageIndexes@@QEAA@XZ; void (*)(void *)
0x18006fb59  mov     edx, 120h; unsigned __int64
0x18006fb5e  mov     r8d, 2; unsigned __int64
0x18006fb64  lea     rcx, [rbp+230h+var_270]; void *
0x18006fb68  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18006fb6d  nop
0x18006fb6e  mov     rcx, [rsp+330h+var_2F8]; this
0x18006fb73  test    rcx, rcx
0x18006fb76  jz      short loc_18006FB7E
0x18006fb78  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006fb7d  nop
0x18006fb7e  lea     rcx, [rsp+330h+var_2F0]
0x18006fb83  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006fb88  nop
0x18006fb89  lea     rcx, [rbp+230h+MutantHandle]
0x18006fb90  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006fb95  mov     rbx, [rsp+330h+arg_0]
0x18006fb9d  add     rsp, 300h
0x18006fba4  pop     r15
0x18006fba6  pop     r14
0x18006fba8  pop     r13
0x18006fbaa  pop     r12
0x18006fbac  pop     rdi
0x18006fbad  pop     rsi
0x18006fbae  pop     rbp
0x18006fbaf  retn
0x18006fbb0  lea     r8, aOnecoreBaseFli_28; "onecore\\base\\flighting\\featuremanage"...
0x18006fbb7  mov     edx, 2Ah ; '*'; void *
0x18006fbbc  mov     rcx, rbx; this
0x18006fbbf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18006fbc5  mov     r9d, eax; char *
0x18006fbc8  lea     r8, aOnecoreBaseFli_51; "onecore\\base\\flighting\\featuremanage"...
0x18006fbcf  mov     edx, 2Ah ; '*'; void *
0x18006fbd4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fbda  mov     r9d, eax; char *
0x18006fbdd  lea     r8, aOnecoreBaseFli_28; "onecore\\base\\flighting\\featuremanage"...
0x18006fbe4  mov     edx, 25h ; '%'; void *
0x18006fbe9  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
