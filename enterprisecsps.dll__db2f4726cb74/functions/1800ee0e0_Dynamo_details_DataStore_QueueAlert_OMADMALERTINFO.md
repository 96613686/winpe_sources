# Dynamo::details::DataStore::QueueAlert(OMADMALERTINFO *)

- ea: `0x1800ee0e0`
- end: `0x1800ee2bb`
- name: `?QueueAlert@DataStore@details@Dynamo@@UEAAXPEAUOMADMALERTINFO@@@Z`
- size: `475`
- prototype: `void __fastcall(Dynamo::details::DataStore *__hidden this, struct OMADMALERTINFO *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180023874`
- `0x180025ac0`
- `0x18002dcc8`
- `0x1800eaa40`
- `0x1800eb6a0`
- `0x1800ee0e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ee199`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ee199`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x1800ee228`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x1800ee228`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800ee254`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800ee254`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Dynamo::details::DataStore::QueueAlert(Dynamo::details::DataStore *this, struct OMADMALERTINFO *a2)
{
  const unsigned __int16 *v4; // r9
  int DynamicManagementRegistryKey; // eax
  unsigned int v6; // eax
  unsigned int i; // ebx
  const unsigned __int16 *v8; // r9
  int v9; // eax
  int v10; // eax
  int dwOptions; // [rsp+20h] [rbp-19h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-19h]
  HKEY *samDesired; // [rsp+28h] [rbp-11h]
  _QWORD v14[4]; // [rsp+50h] [rbp+17h]
  _QWORD v15[4]; // [rsp+70h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]
  HKEY phkResult; // [rsp+A0h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+77h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  LOBYTE(v4) = 1;
  DynamicManagementRegistryKey = dmstd::GetDynamicManagementRegistryKey(
                                   *((dmstd **)this + 1),
                                   *((const unsigned __int16 **)this + 2),
                                   L"Alerts",
                                   v4,
                                   &hKey,
                                   samDesired);
  if ( DynamicManagementRegistryKey < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF1,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
      (const char *)(unsigned int)DynamicManagementRegistryKey,
      dwOptions);
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v6 = RegCreateKeyExW(hKey, *((LPCWSTR *)a2 + 3), 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
      (const char *)v6,
      dwOptionsa);
  v15[0] = L"AlertData";
  v15[1] = L"Source";
  v15[2] = L"Target";
  v15[3] = L"AlertType";
  v14[0] = *((_QWORD *)a2 + 3);
  v14[1] = *((_QWORD *)a2 + 2);
  v14[2] = *((_QWORD *)a2 + 7);
  v14[3] = *((_QWORD *)a2 + 1);
  for ( i = 0; i < 4; ++i )
  {
    v8 = (const unsigned __int16 *)v14[i];
    if ( v8 )
    {
      v9 = OmaDmRegistrySetString(phkResult, 0, (const unsigned __int16 *)v15[i], v8);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
          (const char *)(unsigned int)v9,
          dwOptionsa);
    }
  }
  v10 = OmaDmRegistrySetDWORD(phkResult, 0, L"EventType", *((_DWORD *)a2 + 1));
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
      (const char *)(unsigned int)v10,
      dwOptionsa);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800ee0e0  mov     [rsp-8+arg_8], rbx
0x1800ee0e5  mov     [rsp-8+arg_18], rdi
0x1800ee0ea  push    rbp
0x1800ee0eb  lea     rbp, [rsp-57h]
0x1800ee0f0  sub     rsp, 90h
0x1800ee0f7  mov     rdi, rdx
0x1800ee0fa  mov     rbx, rcx
0x1800ee0fd  mov     [rbp+57h+hKey], 0
0x1800ee105  xor     edx, edx
0x1800ee107  lea     rcx, [rbp+57h+hKey]
0x1800ee10b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ee110  lea     rax, [rbp+57h+hKey]
0x1800ee114  mov     qword ptr [rsp+90h+dwOptions], rax; int
0x1800ee119  mov     r9b, 1; unsigned __int16 *
0x1800ee11c  lea     r8, aAlerts; "Alerts"
0x1800ee123  mov     rdx, [rbx+10h]; unsigned __int16 *
0x1800ee127  mov     rcx, [rbx+8]; this
0x1800ee12b  call    ?GetDynamicManagementRegistryKey@dmstd@@YAJPEBG00_NPEAPEAUHKEY__@@@Z; dmstd::GetDynamicManagementRegistryKey(ushort const *,ushort const *,ushort const *,bool,HKEY__ * *)
0x1800ee130  mov     rcx, [rbp+5Fh]; this
0x1800ee134  test    eax, eax
0x1800ee136  jns     short loc_1800EE14D
0x1800ee138  mov     r9d, eax; char *
0x1800ee13b  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800ee142  mov     edx, 0F1h; void *
0x1800ee147  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ee14d  mov     [rbp+57h+arg_0], 0
0x1800ee155  xor     edx, edx
0x1800ee157  lea     rcx, [rbp+57h+arg_0]
0x1800ee15b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ee160  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x1800ee169  lea     rax, [rbp+57h+arg_0]
0x1800ee16d  mov     [rsp+90h+phkResult], rax; phkResult
0x1800ee172  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800ee17b  mov     dword ptr [rsp+90h+samDesired], 2001Fh; samDesired
0x1800ee183  mov     [rsp+90h+dwOptions], 0; int
0x1800ee18b  xor     r9d, r9d; lpClass
0x1800ee18e  xor     r8d, r8d; Reserved
0x1800ee191  mov     rdx, [rdi+18h]; lpSubKey
0x1800ee195  mov     rcx, [rbp+57h+hKey]; hKey
0x1800ee199  call    cs:__imp_RegCreateKeyExW
0x1800ee1a0  nop     dword ptr [rax+rax+00h]
0x1800ee1a5  mov     rcx, [rbp+5Fh]; this
0x1800ee1a9  test    eax, eax
0x1800ee1ab  jz      short loc_1800EE1C2
0x1800ee1ad  mov     r9d, eax; char *
0x1800ee1b0  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800ee1b7  mov     edx, 0F6h; void *
0x1800ee1bc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ee1c2  lea     rax, aAlertdata; "AlertData"
0x1800ee1c9  mov     [rbp+57h+var_20], rax
0x1800ee1cd  lea     rax, aSource; "Source"
0x1800ee1d4  mov     [rbp+57h+var_18], rax
0x1800ee1d8  lea     rax, aTarget; "Target"
0x1800ee1df  mov     [rbp+57h+var_10], rax
0x1800ee1e3  lea     rax, aAlerttype; "AlertType"
0x1800ee1ea  mov     [rbp+57h+var_8], rax
0x1800ee1ee  mov     rax, [rdi+18h]
0x1800ee1f2  mov     [rbp+57h+var_40], rax
0x1800ee1f6  mov     rax, [rdi+10h]
0x1800ee1fa  mov     [rbp+57h+var_38], rax
0x1800ee1fe  mov     rax, [rdi+38h]
0x1800ee202  mov     [rbp+57h+var_30], rax
0x1800ee206  mov     rax, [rdi+8]
0x1800ee20a  mov     [rbp+57h+var_28], rax
0x1800ee20e  xor     ebx, ebx
0x1800ee210  movsxd  r8, ebx
0x1800ee213  mov     r9, [rbp+r8*8+57h+var_40]
0x1800ee218  test    r9, r9
0x1800ee21b  jz      short loc_1800EE23C
0x1800ee21d  mov     r8, [rbp+r8*8+57h+var_20]
0x1800ee222  xor     edx, edx
0x1800ee224  mov     rcx, [rbp+57h+arg_0]
0x1800ee228  call    cs:__imp_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800ee22f  nop     dword ptr [rax+rax+00h]
0x1800ee234  mov     rcx, [rbp+5Fh]; this
0x1800ee238  test    eax, eax
0x1800ee23a  js      short loc_1800EE27D
0x1800ee23c  inc     ebx
0x1800ee23e  cmp     ebx, 4
0x1800ee241  jb      short loc_1800EE210
0x1800ee243  mov     r9d, [rdi+4]
0x1800ee247  lea     r8, aEventtype; "EventType"
0x1800ee24e  xor     edx, edx
0x1800ee250  mov     rcx, [rbp+57h+arg_0]
0x1800ee254  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800ee25b  nop     dword ptr [rax+rax+00h]
0x1800ee260  mov     rcx, [rbp+5Fh]; this
0x1800ee264  test    eax, eax
0x1800ee266  jns     short loc_1800EE292
0x1800ee268  mov     r9d, eax; char *
0x1800ee26b  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800ee272  mov     edx, 105h; void *
0x1800ee277  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ee27d  mov     r9d, eax; char *
0x1800ee280  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800ee287  mov     edx, 101h; void *
0x1800ee28c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ee292  lea     rcx, [rbp+57h+arg_0]
0x1800ee296  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ee29b  nop
0x1800ee29c  lea     rcx, [rbp+57h+hKey]
0x1800ee2a0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ee2a5  lea     r11, [rsp+90h+var_s0]
0x1800ee2ad  mov     rbx, [r11+18h]
0x1800ee2b1  mov     rdi, [r11+28h]
0x1800ee2b5  mov     rsp, r11
0x1800ee2b8  pop     rbp
0x1800ee2b9  retn
```
