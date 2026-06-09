# FWQuarantineSync::FWQuarantineSync(void)

- ea: `0x1800a2800`
- end: `0x1800a2b9d`
- name: `??0FWQuarantineSync@@QEAA@XZ`
- size: `925`
- prototype: `FWQuarantineSync *__fastcall(FWQuarantineSync *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a2708`

## callees

- `0x180002a90`
- `0x180002f14`
- `0x180002fa4`
- `0x18003b250`
- `0x18004068c`
- `0x180051184`
- `0x1800a2800`
- `0x1800a88a0`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x1800a2aba`
- `ntdll!NtDeleteWnfStateName` at `0x1800a2aba`
- `ntdll!NtCreateWnfStateName` at `0x1800a2986`
- `ntdll!NtCreateWnfStateName` at `0x1800a2986`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800a2833`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800a2833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a290d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a290d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a2a64`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a2a64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a2ae9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a2b2f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a2ae9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a2b2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2b70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2b70`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a2903`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a2903`

## pseudocode

```c
FWQuarantineSync *__fastcall FWQuarantineSync::FWQuarantineSync(FWQuarantineSync *this)
{
  DWORD LastError; // eax
  int v3; // r8d
  int v4; // r9d
  LPCWSTR *v5; // rdi
  int WnfStateName; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  const WCHAR *v10; // rdi
  LPCWSTR *v11; // rax
  const WCHAR *v12; // rdx
  LSTATUS v13; // eax
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  __int16 *v17; // rdx
  DWORD v19; // [rsp+50h] [rbp+7h] BYREF
  void *v20; // [rsp+58h] [rbp+Fh] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp+17h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp+2Fh] BYREF
  HKEY hKey; // [rsp+80h] [rbp+37h] BYREF

  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this, 0x3E8u, 0);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_BYTE *)this + 200) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  if ( (unsigned int)dword_1801BD288 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1801BD288,
      byte_18018EF5D);
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GR;;;WD)(A;;GA;;;S-1-5-80-3635958274-2059881490-2225992882-984577281-633327304)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_1801BD288 > 2 )
    {
      v5 = &qword_1801C70E0;
      v19 = LastError;
      if ( (unsigned __int64)qword_1801C70F8 > 7 )
        v5 = (LPCWSTR *)qword_1801C70E0;
      v20 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        dword_1801BD288,
        (unsigned int)&unk_18018EEE8,
        v3,
        v4,
        (__int64)&v20,
        (__int64)&v19);
    }
    goto LABEL_30;
  }
  WnfStateName = NtCreateWnfStateName((char *)this + 320, 3, 0);
  if ( WnfStateName >= 0 )
  {
    v10 = (const WCHAR *)&qword_1801C70E0;
    if ( (unsigned int)dword_1801BD288 > 4 )
    {
      v11 = &qword_1801C70E0;
      if ( (unsigned __int64)qword_1801C70F8 > 7 )
        v11 = (LPCWSTR *)qword_1801C70E0;
      v20 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        v7,
        (unsigned int)word_18018EE4A,
        v8,
        v9,
        (__int64)&v20);
    }
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v12 = (const WCHAR *)&qword_1801C70E0;
    if ( (unsigned __int64)qword_1801C70F8 > 7 )
      v12 = qword_1801C70E0;
    v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0, 1u, 0x2001Fu, &SecurityAttributes, &hKey, 0);
    if ( v13 )
    {
      v16 = dword_1801BD288;
      if ( (unsigned int)dword_1801BD288 > 2 )
      {
        v17 = word_18018EDFA;
        if ( (unsigned __int64)qword_1801C70F8 > 7 )
          v10 = qword_1801C70E0;
        goto LABEL_21;
      }
    }
    else
    {
      v10 = L"WnfStateNameData0";
      v13 = RegSetValueExW(hKey, L"WnfStateNameData0", 0, 4u, (const BYTE *)this + 320, 4u);
      if ( v13 )
      {
        v16 = dword_1801BD288;
        if ( (unsigned int)dword_1801BD288 <= 2 )
          goto LABEL_22;
        v17 = (__int16 *)&unk_18018ED58;
        goto LABEL_21;
      }
      v10 = L"WnfStateNameData1";
      v13 = RegSetValueExW(hKey, L"WnfStateNameData1", 0, 4u, (const BYTE *)this + 324, 4u);
      if ( !v13 )
      {
        qword_1801C83A8 = *((_QWORD *)this + 40);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_30;
      }
      v16 = dword_1801BD288;
      if ( (unsigned int)dword_1801BD288 > 2 )
      {
        v17 = (__int16 *)byte_18018EDA9;
LABEL_21:
        v19 = v13;
        v20 = (void *)v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v16,
          (_DWORD)v17,
          v14,
          v15,
          (__int64)&v20,
          (__int64)&v19);
      }
    }
LABEL_22:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    NtDeleteWnfStateName((char *)this + 320);
    goto LABEL_30;
  }
  if ( (unsigned int)dword_1801BD288 > 2 )
  {
    v19 = WnfStateName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      dword_1801BD288,
      (unsigned int)&unk_18018EE98,
      v8,
      v9,
      (__int64)&v19);
  }
LABEL_30:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return this;
}

```

## disassembly

```asm
0x1800a2800  mov     [rsp-8+arg_8], rbx
0x1800a2805  mov     [rsp-8+arg_10], rsi
0x1800a280a  push    rbp
0x1800a280b  push    rdi
0x1800a280c  push    r14
0x1800a280e  lea     rbp, [rsp-47h]
0x1800a2813  sub     rsp, 90h
0x1800a281a  mov     rax, cs:__security_cookie
0x1800a2821  xor     rax, rsp
0x1800a2824  mov     [rbp+57h+var_18], rax
0x1800a2828  xor     r8d, r8d; Flags
0x1800a282b  mov     edx, 3E8h; dwSpinCount
0x1800a2830  mov     rbx, rcx
0x1800a2833  call    cs:__imp_InitializeCriticalSectionEx
0x1800a2839  xor     r14d, r14d
0x1800a283c  lea     rsi, [rbx+140h]
0x1800a2843  mov     [rbx+28h], r14
0x1800a2847  xor     eax, eax
0x1800a2849  mov     [rbx+30h], r14
0x1800a284d  mov     [rbx+38h], r14
0x1800a2851  mov     [rbx+78h], r14
0x1800a2855  mov     [rbx+0B8h], r14
0x1800a285c  mov     [rbx+0C0h], r14
0x1800a2863  mov     [rbx+0C8h], r14b
0x1800a286a  mov     [rbx+0D0h], r14
0x1800a2871  mov     [rbx+0D8h], r14
0x1800a2878  mov     [rbx+0E0h], r14
0x1800a287f  mov     [rbx+0E8h], r14
0x1800a2886  mov     [rbx+0F0h], r14
0x1800a288d  mov     [rbx+0F8h], r14
0x1800a2894  mov     [rbx+100h], r14
0x1800a289b  mov     [rbx+108h], r14
0x1800a28a2  mov     [rbx+110h], r14
0x1800a28a9  mov     [rbx+118h], r14
0x1800a28b0  mov     [rbx+120h], r14
0x1800a28b7  mov     [rbx+128h], r14
0x1800a28be  mov     [rbx+130h], r14
0x1800a28c5  mov     [rbx+138h], r14
0x1800a28cc  mov     [rsi], rax
0x1800a28cf  mov     eax, cs:dword_1801BD288
0x1800a28d5  cmp     eax, 4
0x1800a28d8  jbe     short loc_1800A28ED
0x1800a28da  lea     rdx, byte_18018EF5D
0x1800a28e1  lea     rcx, dword_1801BD288
0x1800a28e8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800a28ed  xor     r9d, r9d; SecurityDescriptorSize
0x1800a28f0  mov     [rbp+57h+SecurityDescriptor], r14
0x1800a28f4  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800a28f8  lea     rcx, aDAGrWdAGaS1580; "D:(A;;GR;;;WD)(A;;GA;;;S-1-5-80-3635958"...
0x1800a28ff  lea     edx, [r9+1]; StringSDRevision
0x1800a2903  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800a2909  test    eax, eax
0x1800a290b  jnz     short loc_1800A2963
0x1800a290d  call    cs:__imp_GetLastError
0x1800a2913  mov     ecx, cs:dword_1801BD288
0x1800a2919  cmp     ecx, 2
0x1800a291c  jbe     loc_1800A2B67
0x1800a2922  cmp     cs:qword_1801C70F8, 7
0x1800a292a  lea     rdi, qword_1801C70E0
0x1800a2931  mov     [rbp+57h+var_50], eax
0x1800a2934  lea     rdx, unk_18018EEE8
0x1800a293b  cmova   rdi, cs:qword_1801C70E0
0x1800a2943  lea     rax, [rbp+57h+var_50]
0x1800a2947  mov     qword ptr [rsp+0A0h+samDesired], rax
0x1800a294c  lea     rax, [rbp+57h+var_48]
0x1800a2950  mov     qword ptr [rsp+0A0h+dwOptions], rax
0x1800a2955  mov     [rbp+57h+var_48], rdi
0x1800a2959  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800a295e  jmp     loc_1800A2B67
0x1800a2963  mov     rax, [rbp+57h+SecurityDescriptor]
0x1800a2967  xor     r9d, r9d
0x1800a296a  mov     [rsp+0A0h+lpSecurityAttributes], rax
0x1800a296f  xor     r8d, r8d
0x1800a2972  mov     [rsp+0A0h+samDesired], 1000h
0x1800a297a  mov     rcx, rsi
0x1800a297d  mov     qword ptr [rsp+0A0h+dwOptions], r14
0x1800a2982  lea     edx, [r9+3]
0x1800a2986  call    cs:__imp_NtCreateWnfStateName
0x1800a298c  test    eax, eax
0x1800a298e  jns     short loc_1800A29BC
0x1800a2990  mov     ecx, cs:dword_1801BD288
0x1800a2996  cmp     ecx, 2
0x1800a2999  jbe     loc_1800A2B67
0x1800a299f  mov     [rbp+57h+var_50], eax
0x1800a29a2  lea     rdx, unk_18018EE98
0x1800a29a9  lea     rax, [rbp+57h+var_50]
0x1800a29ad  mov     qword ptr [rsp+0A0h+dwOptions], rax
0x1800a29b2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800a29b7  jmp     loc_1800A2B67
0x1800a29bc  mov     eax, cs:dword_1801BD288
0x1800a29c2  lea     rdi, qword_1801C70E0
0x1800a29c9  cmp     eax, 4
0x1800a29cc  jbe     short loc_1800A29FA
0x1800a29ce  cmp     cs:qword_1801C70F8, 7
0x1800a29d6  lea     rdx, word_18018EE4A
0x1800a29dd  mov     rax, rdi
0x1800a29e0  cmova   rax, cs:qword_1801C70E0
0x1800a29e8  mov     [rbp+57h+var_48], rax
0x1800a29ec  lea     rax, [rbp+57h+var_48]
0x1800a29f0  mov     qword ptr [rsp+0A0h+dwOptions], rax
0x1800a29f5  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1800a29fa  mov     rax, [rbp+57h+SecurityDescriptor]
0x1800a29fe  lea     rcx, [rbp+57h+hKey]
0x1800a2a02  xor     edx, edx
0x1800a2a04  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800a2a08  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x1800a2a10  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], r14
0x1800a2a14  mov     [rbp+57h+hKey], r14
0x1800a2a18  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a2a1d  cmp     cs:qword_1801C70F8, 7
0x1800a2a25  lea     rax, [rbp+57h+hKey]
0x1800a2a29  mov     [rsp+0A0h+lpdwDisposition], r14; lpdwDisposition
0x1800a2a2e  mov     rdx, rdi
0x1800a2a31  cmova   rdx, cs:qword_1801C70E0; lpSubKey
0x1800a2a39  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a2a40  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1800a2a45  xor     r9d, r9d; lpClass
0x1800a2a48  lea     rax, [rbp+57h+SecurityAttributes]
0x1800a2a4c  xor     r8d, r8d; Reserved
0x1800a2a4f  mov     [rsp+0A0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800a2a54  mov     [rsp+0A0h+samDesired], 2001Fh; samDesired
0x1800a2a5c  mov     [rsp+0A0h+dwOptions], 1; dwOptions
0x1800a2a64  call    cs:__imp_RegCreateKeyExW
0x1800a2a6a  test    eax, eax
0x1800a2a6c  jz      short loc_1800A2AC5
0x1800a2a6e  mov     ecx, cs:dword_1801BD288
0x1800a2a74  cmp     ecx, 2
0x1800a2a77  jbe     short loc_1800A2AAE
0x1800a2a79  cmp     cs:qword_1801C70F8, 7
0x1800a2a81  lea     rdx, word_18018EDFA
0x1800a2a88  cmova   rdi, cs:qword_1801C70E0
0x1800a2a90  mov     [rbp+57h+var_50], eax
0x1800a2a93  lea     rax, [rbp+57h+var_50]
0x1800a2a97  mov     qword ptr [rsp+0A0h+samDesired], rax
0x1800a2a9c  lea     rax, [rbp+57h+var_48]
0x1800a2aa0  mov     qword ptr [rsp+0A0h+dwOptions], rax
0x1800a2aa5  mov     [rbp+57h+var_48], rdi
0x1800a2aa9  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800a2aae  lea     rcx, [rbp+57h+hKey]
0x1800a2ab2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2ab7  mov     rcx, rsi
0x1800a2aba  call    cs:__imp_NtDeleteWnfStateName
0x1800a2ac0  jmp     loc_1800A2B67
0x1800a2ac5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800a2ac9  lea     rdi, aWnfstatenameda; "WnfStateNameData0"
0x1800a2ad0  mov     rdx, rdi; lpValueName
0x1800a2ad3  mov     [rsp+0A0h+samDesired], 4; cbData
0x1800a2adb  mov     r9d, 4; dwType
0x1800a2ae1  mov     qword ptr [rsp+0A0h+dwOptions], rsi; lpData
0x1800a2ae6  xor     r8d, r8d; Reserved
0x1800a2ae9  call    cs:__imp_RegSetValueExW
0x1800a2aef  test    eax, eax
0x1800a2af1  jz      short loc_1800A2B07
0x1800a2af3  mov     ecx, cs:dword_1801BD288
0x1800a2af9  cmp     ecx, 2
0x1800a2afc  jbe     short loc_1800A2AAE
0x1800a2afe  lea     rdx, unk_18018ED58
0x1800a2b05  jmp     short loc_1800A2A90
0x1800a2b07  mov     rcx, [rbp+57h+hKey]; hKey
0x1800a2b0b  lea     rax, [rsi+4]
0x1800a2b0f  lea     rdi, aWnfstatenameda_0; "WnfStateNameData1"
0x1800a2b16  mov     [rsp+0A0h+samDesired], 4; cbData
0x1800a2b1e  mov     rdx, rdi; lpValueName
0x1800a2b21  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x1800a2b26  mov     r9d, 4; dwType
0x1800a2b2c  xor     r8d, r8d; Reserved
0x1800a2b2f  call    cs:__imp_RegSetValueExW
0x1800a2b35  test    eax, eax
0x1800a2b37  jz      short loc_1800A2B54
0x1800a2b39  mov     ecx, cs:dword_1801BD288
0x1800a2b3f  cmp     ecx, 2
0x1800a2b42  jbe     loc_1800A2AAE
0x1800a2b48  lea     rdx, byte_18018EDA9
0x1800a2b4f  jmp     loc_1800A2A90
0x1800a2b54  mov     rcx, [rsi]
0x1800a2b57  mov     cs:qword_1801C83A8, rcx
0x1800a2b5e  lea     rcx, [rbp+57h+hKey]
0x1800a2b62  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2b67  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800a2b6b  test    rcx, rcx
0x1800a2b6e  jz      short loc_1800A2B76
0x1800a2b70  call    cs:__imp_LocalFree
0x1800a2b76  mov     rax, rbx
0x1800a2b79  mov     rcx, [rbp+57h+var_18]
0x1800a2b7d  xor     rcx, rsp; StackCookie
0x1800a2b80  call    __security_check_cookie
0x1800a2b85  lea     r11, [rsp+0A0h+var_10]
0x1800a2b8d  mov     rbx, [r11+28h]
0x1800a2b91  mov     rsi, [r11+30h]
0x1800a2b95  mov     rsp, r11
0x1800a2b98  pop     r14
0x1800a2b9a  pop     rdi
0x1800a2b9b  pop     rbp
0x1800a2b9c  retn
```
