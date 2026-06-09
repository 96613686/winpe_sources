# DusmStore::SetMigrationCompleted(DusmConnection const &)

- ea: `0x18002c50c`
- end: `0x18002c649`
- name: `?SetMigrationCompleted@DusmStore@@SAKAEBVDusmConnection@@@Z`
- size: `317`
- prototype: `unsigned int __fastcall(const struct DusmConnection *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036b64`
- `0x18003a1e4`

## callees

- `0x180005324`
- `0x180007c90`
- `0x180013444`
- `0x18001742c`
- `0x180026fa0`
- `0x180027bf4`
- `0x18002c50c`
- `0x18002de88`
- `0x180043f48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002c5a7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002c5a7`

## string_xrefs

- `0x18002c597`: `MigrationCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DusmStore::SetMigrationCompleted(const struct DusmConnection *a1)
{
  unsigned int v2; // ebx
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // edi
  __int64 v8; // r8
  __int64 v9; // r9
  HKEY hKey; // [rsp+40h] [rbp-38h] BYREF
  __int64 v11; // [rsp+48h] [rbp-30h] BYREF
  __int64 v12; // [rsp+50h] [rbp-28h] BYREF
  __int64 v13; // [rsp+58h] [rbp-20h] BYREF
  int Data; // [rsp+60h] [rbp-18h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = DusmStore::OpenMigrationKey(a1, 1, &hKey);
  if ( v2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v2;
  }
  else
  {
    v4 = *((_DWORD *)a1 + 4);
    Data = 1;
    v5 = v4 - 1;
    if ( v4 == 1 || (v5 = v4 - 2, (unsigned int)v5 > 1) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v5);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 87;
    }
    else
    {
      v7 = RegSetKeyValueW(hKey, 0, L"MigrationCompleted", 4u, &Data, 4u);
      if ( v7 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v6);
        if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8) > 2u )
        {
          v12 = (__int64)L"MigrationCompleted";
          v13 = DusmMediaTypeToSz(v4);
          LODWORD(v11) = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
            v8,
            (int)&dword_18005859C,
            v8,
            v9,
            (__int64)&v11,
            (const WCHAR **)&v13,
            (const WCHAR **)&v12);
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v7;
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 0;
      }
    }
  }
}

```

## disassembly

```asm
0x18002c50c  push    rbp
0x18002c50e  push    rbx
0x18002c50f  push    rsi
0x18002c510  push    rdi
0x18002c511  mov     rbp, rsp
0x18002c514  sub     rsp, 78h
0x18002c518  mov     rax, cs:__security_cookie
0x18002c51f  xor     rax, rsp
0x18002c522  mov     [rbp+var_10], rax
0x18002c526  mov     rdi, rcx
0x18002c529  mov     [rbp+hKey], 0
0x18002c531  xor     edx, edx
0x18002c533  lea     rcx, [rbp+hKey]
0x18002c537  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002c53c  lea     r8, [rbp+hKey]; HKEY *
0x18002c540  mov     dl, 1; bool
0x18002c542  mov     rcx, rdi; struct DusmConnection *
0x18002c545  call    ?OpenMigrationKey@DusmStore@@SAKAEBVDusmConnection@@_NPEAPEAUHKEY__@@@Z; DusmStore::OpenMigrationKey(DusmConnection const &,bool,HKEY__ * *)
0x18002c54a  mov     ebx, eax
0x18002c54c  test    eax, eax
0x18002c54e  jz      short loc_18002C560
0x18002c550  lea     rcx, [rbp+hKey]
0x18002c554  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002c559  mov     eax, ebx
0x18002c55b  jmp     loc_18002C634
0x18002c560  mov     ebx, [rdi+10h]
0x18002c563  mov     [rbp+Data], 1
0x18002c56a  mov     ecx, ebx
0x18002c56c  sub     ecx, 1
0x18002c56f  jz      loc_18002C620
0x18002c575  sub     ecx, 1
0x18002c578  jz      short loc_18002C583
0x18002c57a  cmp     ecx, 1
0x18002c57d  jnz     loc_18002C620
0x18002c583  mov     r9d, 4; dwType
0x18002c589  mov     [rsp+78h+cbData], r9d; cbData
0x18002c58e  lea     rax, [rbp+Data]
0x18002c592  mov     [rsp+78h+lpData], rax; lpData
0x18002c597  lea     rsi, aMigrationcompl; "MigrationCompleted"
0x18002c59e  mov     r8, rsi; lpValueName
0x18002c5a1  xor     edx, edx; lpSubKey
0x18002c5a3  mov     rcx, [rbp+hKey]; hKey
0x18002c5a7  call    cs:__imp_RegSetKeyValueW
0x18002c5ad  mov     edi, eax
0x18002c5af  test    eax, eax
0x18002c5b1  jz      short loc_18002C613
0x18002c5b3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c5b8  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18002c5bd  mov     r8, [rax+8]
0x18002c5c1  mov     edx, [r8]
0x18002c5c4  cmp     edx, 2
0x18002c5c7  jbe     short loc_18002C606
0x18002c5c9  mov     [rbp+var_28], rsi
0x18002c5cd  mov     ecx, ebx
0x18002c5cf  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x18002c5d4  mov     [rbp+var_20], rax
0x18002c5d8  mov     dword ptr [rbp+var_30], edi
0x18002c5db  lea     rax, [rbp+var_28]
0x18002c5df  mov     [rsp+78h+var_48], rax; __int64
0x18002c5e4  lea     rax, [rbp+var_20]
0x18002c5e8  mov     qword ptr [rsp+78h+cbData], rax; __int64
0x18002c5ed  lea     rax, [rbp+var_30]
0x18002c5f1  mov     [rsp+78h+lpData], rax; __int64
0x18002c5f6  lea     rdx, dword_18005859C; int
0x18002c5fd  mov     rcx, r8; int
0x18002c600  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x18002c605  nop
0x18002c606  lea     rcx, [rbp+hKey]
0x18002c60a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002c60f  mov     eax, edi
0x18002c611  jmp     short loc_18002C634
0x18002c613  lea     rcx, [rbp+hKey]
0x18002c617  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002c61c  xor     eax, eax
0x18002c61e  jmp     short loc_18002C634
0x18002c620  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c625  nop
0x18002c626  lea     rcx, [rbp+hKey]
0x18002c62a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002c62f  mov     eax, 57h ; 'W'
0x18002c634  mov     rcx, [rbp+var_10]
0x18002c638  xor     rcx, rsp; StackCookie
0x18002c63b  call    __security_check_cookie
0x18002c640  add     rsp, 78h
0x18002c644  pop     rdi
0x18002c645  pop     rsi
0x18002c646  pop     rbx
0x18002c647  pop     rbp
0x18002c648  retn
```
