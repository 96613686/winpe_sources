# DusmStore::OpenMigrationKey(DusmConnection const &,bool,HKEY__ * *)

- ea: `0x180027bf4`
- end: `0x180027eb0`
- name: `?OpenMigrationKey@DusmStore@@SAKAEBVDusmConnection@@_NPEAPEAUHKEY__@@@Z`
- size: `700`
- prototype: `__int64 __fastcall(const struct DusmConnection *, char, HKEY *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029cec`
- `0x18002c50c`

## callees

- `0x180001234`
- `0x180005324`
- `0x180007c90`
- `0x180012fcc`
- `0x180013114`
- `0x180013444`
- `0x18001742c`
- `0x180026fa0`
- `0x180027bf4`
- `0x18002da30`
- `0x18002da58`
- `0x18002de88`
- `0x180043f48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027ce7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027ce7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027d99`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027d99`

## pseudocode

```c
__int64 __fastcall DusmStore::OpenMigrationKey(const struct DusmConnection *a1, char a2, HKEY *a3)
{
  unsigned int v6; // edi
  __int64 v7; // rcx
  REGSAM samDesired; // esi
  const WCHAR *v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  int v12; // r8d
  const WCHAR *v13; // rax
  __int64 v14; // rcx
  _DWORD *v15; // rcx
  int v16; // r8d
  int v17; // r9d
  int v19; // r8d
  HKEY v20; // rax
  __int64 v21; // [rsp+50h] [rbp-9h] BYREF
  __int64 v22; // [rsp+58h] [rbp-1h] BYREF
  __int64 v23; // [rsp+60h] [rbp+7h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+Fh] BYREF
  _OWORD v25[2]; // [rsp+70h] [rbp+17h] BYREF

  *a3 = 0;
  v6 = *((_DWORD *)a1 + 4);
  v25[0] = 0;
  v25[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v25[0]) = 0;
  v7 = v6 - 1;
  if ( v6 == 1 )
    goto LABEL_17;
  v7 = v6 - 2;
  if ( v6 == 2 )
  {
    std::wstring::append(v25, qword_180068EC0);
    goto LABEL_6;
  }
  if ( v6 != 3 )
  {
LABEL_17:
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
    std::wstring::_Tidy_deallocate(v25);
    return 87;
  }
  std::wstring::append(v25, qword_180068EC8);
  std::wstring::append(v25, L"\\");
  std::wstring::append(v25, (char *)a1 + 144);
LABEL_6:
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  samDesired = a2 != 0 ? 131078 : 131097;
  v9 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25);
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, samDesired, &phkResult);
  if ( v11 == 2 )
  {
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8) > 3u )
    {
      v22 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25);
      v23 = DusmMediaTypeToSz(v6);
      LODWORD(v21) = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v12,
        (int)&byte_180058781,
        (__int64)&v21,
        (__int64)&v23,
        (__int64)&v22);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25);
    v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v13, 0, 0, 0, samDesired, 0, &phkResult, 0);
    if ( v11 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v14);
      v15 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
      if ( *v15 > 2u )
      {
        LODWORD(v21) = v11;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v15,
          (unsigned int)&unk_180058728,
          v16,
          v17,
          (__int64)&v21);
      }
LABEL_12:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      std::wstring::_Tidy_deallocate(v25);
      return v11;
    }
  }
  else if ( v11 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8) > 2u )
    {
      v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25);
      v22 = DusmMediaTypeToSz(v6);
      LODWORD(v21) = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v19,
        (int)&word_1800586AA,
        (__int64)&v21,
        (__int64)&v22,
        (__int64)&v23);
    }
    goto LABEL_12;
  }
  v20 = phkResult;
  phkResult = 0;
  *a3 = v20;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  std::wstring::_Tidy_deallocate(v25);
  return 0;
}

```

## disassembly

```asm
0x180027bf4  mov     [rsp-8+arg_8], rbx
0x180027bf9  mov     [rsp-8+arg_18], rsi
0x180027bfe  push    rbp
0x180027bff  push    rdi
0x180027c00  push    r14
0x180027c02  lea     rbp, [rsp-47h]
0x180027c07  sub     rsp, 0A0h
0x180027c0e  mov     rax, cs:__security_cookie
0x180027c15  xor     rax, rsp
0x180027c18  mov     [rbp+57h+var_20], rax
0x180027c1c  mov     r14, r8
0x180027c1f  mov     sil, dl
0x180027c22  mov     rbx, rcx
0x180027c25  mov     qword ptr [r8], 0
0x180027c2c  mov     edi, [rcx+10h]
0x180027c2f  xorps   xmm0, xmm0
0x180027c32  movups  [rbp+57h+var_40], xmm0
0x180027c36  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180027c3e  movdqu  [rbp+57h+var_30], xmm1
0x180027c43  xor     eax, eax
0x180027c45  mov     word ptr [rbp+57h+var_40], ax
0x180027c49  mov     ecx, edi
0x180027c4b  sub     ecx, 1
0x180027c4e  jz      loc_180027E78
0x180027c54  sub     ecx, 1
0x180027c57  jz      short loc_180027C94
0x180027c59  cmp     ecx, 1
0x180027c5c  jnz     loc_180027E78
0x180027c62  mov     rdx, cs:qword_180068EC8
0x180027c69  lea     rcx, [rbp+57h+var_40]
0x180027c6d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180027c72  lea     rdx, asc_18004F678; "\\"
0x180027c79  lea     rcx, [rbp+57h+var_40]
0x180027c7d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180027c82  lea     rdx, [rbx+90h]
0x180027c89  lea     rcx, [rbp+57h+var_40]
0x180027c8d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180027c92  jmp     short loc_180027CA4
0x180027c94  mov     rdx, cs:qword_180068EC0
0x180027c9b  lea     rcx, [rbp+57h+var_40]
0x180027c9f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180027ca4  mov     [rbp+57h+var_48], 0
0x180027cac  xor     edx, edx
0x180027cae  lea     rcx, [rbp+57h+var_48]
0x180027cb2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180027cb7  neg     sil
0x180027cba  sbb     esi, esi
0x180027cbc  and     esi, 0FFFFFFEDh
0x180027cbf  add     esi, 20019h
0x180027cc5  lea     rcx, [rbp+57h+var_40]
0x180027cc9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180027cce  mov     rdx, rax; lpSubKey
0x180027cd1  lea     rax, [rbp+57h+var_48]
0x180027cd5  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180027cda  mov     r9d, esi; samDesired
0x180027cdd  xor     r8d, r8d; ulOptions
0x180027ce0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027ce7  call    cs:__imp_RegOpenKeyExW
0x180027ced  mov     ebx, eax
0x180027cef  cmp     eax, 2
0x180027cf2  jnz     loc_180027DF1
0x180027cf8  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180027cfd  mov     r8, [rax+8]
0x180027d01  mov     eax, [r8]
0x180027d04  cmp     eax, 3
0x180027d07  jbe     short loc_180027D4E
0x180027d09  lea     rcx, [rbp+57h+var_40]
0x180027d0d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180027d12  mov     [rbp+57h+var_58], rax
0x180027d16  mov     ecx, edi
0x180027d18  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x180027d1d  mov     [rbp+57h+var_50], rax
0x180027d21  mov     dword ptr [rbp+57h+var_60], ebx
0x180027d24  lea     rax, [rbp+57h+var_58]
0x180027d28  mov     [rsp+0B0h+lpSecurityAttributes], rax; __int64
0x180027d2d  lea     rax, [rbp+57h+var_50]
0x180027d31  mov     qword ptr [rsp+0B0h+samDesired], rax; __int64
0x180027d36  lea     rax, [rbp+57h+var_60]
0x180027d3a  mov     [rsp+0B0h+phkResult], rax; __int64
0x180027d3f  lea     rdx, byte_180058781; int
0x180027d46  mov     rcx, r8; int
0x180027d49  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180027d4e  xor     edx, edx
0x180027d50  lea     rcx, [rbp+57h+var_48]
0x180027d54  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180027d59  lea     rcx, [rbp+57h+var_40]
0x180027d5d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180027d62  mov     rdx, rax; lpSubKey
0x180027d65  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x180027d6e  lea     rax, [rbp+57h+var_48]
0x180027d72  mov     [rsp+0B0h+var_78], rax; phkResult
0x180027d77  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180027d80  mov     [rsp+0B0h+samDesired], esi; samDesired
0x180027d84  mov     dword ptr [rsp+0B0h+phkResult], 0; dwOptions
0x180027d8c  xor     r9d, r9d; lpClass
0x180027d8f  xor     r8d, r8d; Reserved
0x180027d92  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027d99  call    cs:__imp_RegCreateKeyExW
0x180027d9f  mov     ebx, eax
0x180027da1  test    eax, eax
0x180027da3  jz      loc_180027E52
0x180027da9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180027dae  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180027db3  mov     rcx, [rax+8]
0x180027db7  mov     edx, [rcx]
0x180027db9  cmp     edx, 2
0x180027dbc  jbe     short loc_180027DD7
0x180027dbe  mov     dword ptr [rbp+57h+var_60], ebx
0x180027dc1  lea     rax, [rbp+57h+var_60]
0x180027dc5  mov     [rsp+0B0h+phkResult], rax
0x180027dca  lea     rdx, unk_180058728
0x180027dd1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180027dd6  nop
0x180027dd7  lea     rcx, [rbp+57h+var_48]
0x180027ddb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180027de0  nop
0x180027de1  lea     rcx, [rbp+57h+var_40]
0x180027de5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027dea  mov     eax, ebx
0x180027dec  jmp     loc_180027E8C
0x180027df1  test    ebx, ebx
0x180027df3  jz      short loc_180027E52
0x180027df5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180027dfa  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180027dff  mov     r8, [rax+8]
0x180027e03  mov     eax, [r8]
0x180027e06  cmp     eax, 2
0x180027e09  jbe     short loc_180027DD7
0x180027e0b  lea     rcx, [rbp+57h+var_40]
0x180027e0f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180027e14  mov     [rbp+57h+var_50], rax
0x180027e18  mov     ecx, edi
0x180027e1a  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x180027e1f  mov     [rbp+57h+var_58], rax
0x180027e23  mov     dword ptr [rbp+57h+var_60], ebx
0x180027e26  lea     rax, [rbp+57h+var_50]
0x180027e2a  mov     [rsp+0B0h+lpSecurityAttributes], rax; __int64
0x180027e2f  lea     rax, [rbp+57h+var_58]
0x180027e33  mov     qword ptr [rsp+0B0h+samDesired], rax; __int64
0x180027e38  lea     rax, [rbp+57h+var_60]
0x180027e3c  mov     [rsp+0B0h+phkResult], rax; __int64
0x180027e41  lea     rdx, word_1800586AA; int
0x180027e48  mov     rcx, r8; int
0x180027e4b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180027e50  jmp     short loc_180027DD7
0x180027e52  mov     rax, [rbp+57h+var_48]
0x180027e56  mov     [rbp+57h+var_48], 0
0x180027e5e  mov     [r14], rax
0x180027e61  lea     rcx, [rbp+57h+var_48]
0x180027e65  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180027e6a  nop
0x180027e6b  lea     rcx, [rbp+57h+var_40]
0x180027e6f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027e74  xor     eax, eax
0x180027e76  jmp     short loc_180027E8C
0x180027e78  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180027e7d  nop
0x180027e7e  lea     rcx, [rbp+57h+var_40]
0x180027e82  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027e87  mov     eax, 57h ; 'W'
0x180027e8c  mov     rcx, [rbp+57h+var_20]
0x180027e90  xor     rcx, rsp; StackCookie
0x180027e93  call    __security_check_cookie
0x180027e98  lea     r11, [rsp+0B0h+var_10]
0x180027ea0  mov     rbx, [r11+28h]
0x180027ea4  mov     rsi, [r11+38h]
0x180027ea8  mov     rsp, r11
0x180027eab  pop     r14
0x180027ead  pop     rdi
0x180027eae  pop     rbp
0x180027eaf  retn
```
