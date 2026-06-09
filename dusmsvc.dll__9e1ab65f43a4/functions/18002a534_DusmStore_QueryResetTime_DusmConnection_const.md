# DusmStore::QueryResetTime(DusmConnection const &)

- ea: `0x18002a534`
- end: `0x18002a85a`
- name: `?QueryResetTime@DusmStore@@SA?AU_FILETIME@@AEBVDusmConnection@@@Z`
- size: `806`
- prototype: `struct _FILETIME __fastcall(const struct DusmConnection *)`
- caller_count: `7`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18001ea28`
- `0x18001f54c`
- `0x18002051c`
- `0x180022d90`
- `0x1800235e4`
- `0x180023b48`
- `0x180024074`

## callees

- `0x1800044e0`
- `0x180005998`
- `0x180007c90`
- `0x18000e828`
- `0x18000f094`
- `0x18000f648`
- `0x180012fcc`
- `0x180013114`
- `0x180013444`
- `0x18001742c`
- `0x180017cec`
- `0x1800259f0`
- `0x180025a24`
- `0x180026fa0`
- `0x18002a534`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a564`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a564`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a6ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a6ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a7ac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a7ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct _FILETIME __fastcall DusmStore::QueryResetTime(const struct DusmConnection *a1)
{
  LPCRITICAL_SECTION v2; // rbx
  unsigned int v3; // edi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r8
  const WCHAR *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  LSTATUS v16; // esi
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int v19; // edi
  unsigned int v20; // edi
  __int64 v21; // r8
  const wchar_t *v22; // rdx
  const WCHAR *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  LSTATUS ValueW; // edi
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  LPCRITICAL_SECTION v33; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v34[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v35[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v36[32]; // [rsp+A0h] [rbp-60h] BYREF
  HKEY hkey; // [rsp+C0h] [rbp-40h] BYREF
  DWORD pcbData; // [rsp+C8h] [rbp-38h] BYREF
  __int64 pvData; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v40[2]; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD v41[2]; // [rsp+F8h] [rbp-8h] BYREF

  v2 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v33 = v2;
  v3 = *((_DWORD *)a1 + 4);
  if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v5, v4) + 8) > 5u )
  {
    v30 = DusmMediaTypeToSz(v3);
    v31 = (__int64)a1 + 32;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>>(
      v6,
      (int)byte_180057F5B,
      v6,
      v7,
      &v31,
      (const WCHAR **)&v30);
  }
  v8 = 0;
  if ( v3 - 1 <= 2 )
  {
    v40[0] = 0;
    v40[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v40[0]) = 0;
    if ( v3 == 1 || v3 == 2 )
    {
      v12 = -1;
      do
        ++v12;
      while ( *((_WORD *)qword_180068EB8 + v12) );
      std::wstring::_Assign<wchar_t>(v40, qword_180068EB8, v12);
    }
    else if ( v3 == 3 )
    {
      v9 = std::wstring::wstring((__int64)v36, (__int64)qword_180068EC8);
      v10 = std::operator+<wchar_t>((__int64)v35, v9, (__int64)L"\\");
      v11 = std::operator+<wchar_t>((__int64)v34, v10, (__int64)a1 + 144);
      std::wstring::operator=(v40, v11);
      std::wstring::_Tidy_deallocate(v34);
      std::wstring::_Tidy_deallocate(v35);
      std::wstring::_Tidy_deallocate(v36);
    }
    hkey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v40);
    v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v13, 0, 0x20019u, &hkey);
    if ( v16 )
    {
      if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v15, v14) + 8) > 5u )
      {
        v31 = (__int64)hkey;
        v32 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v40);
        LODWORD(v30) = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(
          v17,
          (int)&dword_180057EF4,
          v17,
          v18,
          (__int64)&v30,
          (const WCHAR **)&v32,
          (__int64)&v31);
      }
LABEL_26:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      std::wstring::_Tidy_deallocate(v40);
      goto LABEL_27;
    }
    v41[0] = 0;
    v41[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v41[0]) = 0;
    v19 = v3 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        if ( v20 != 1 )
        {
LABEL_21:
          pvData = 0;
          pcbData = 8;
          v23 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v41);
          ValueW = RegGetValueW(hkey, 0, v23, 0x48u, 0, &pvData, &pcbData);
          if ( ValueW )
          {
            if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v25, v24) + 8) > 5u )
            {
              v32 = (__int64)hkey;
              v31 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v40);
              LODWORD(v30) = ValueW;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(
                v27,
                (int)&word_180057E8E,
                v27,
                v28,
                (__int64)&v30,
                (const WCHAR **)&v31,
                (__int64)&v32);
            }
          }
          else
          {
            v8 = pvData;
          }
          std::wstring::_Tidy_deallocate(v41);
          goto LABEL_26;
        }
        v21 = 13;
        v22 = L"WwanResetTime";
      }
      else
      {
        v21 = 13;
        v22 = L"WlanResetTime";
      }
    }
    else
    {
      v21 = 17;
      v22 = L"EthernetResetTime";
    }
    std::wstring::_Assign<wchar_t>(v41, v22, v21);
    goto LABEL_21;
  }
LABEL_27:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
  return (struct _FILETIME)v8;
}

```

## disassembly

```asm
0x18002a534  push    rbp
0x18002a536  push    rbx
0x18002a537  push    rsi
0x18002a538  push    rdi
0x18002a539  lea     rbp, [rsp-28h]
0x18002a53e  sub     rsp, 128h
0x18002a545  mov     rax, cs:__security_cookie
0x18002a54c  xor     rax, rsp
0x18002a54f  mov     [rbp+40h+var_28], rax
0x18002a553  mov     rsi, rcx
0x18002a556  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002a55d  add     rbx, 28h ; '('
0x18002a561  mov     rcx, rbx; lpCriticalSection
0x18002a564  call    cs:__imp_EnterCriticalSection
0x18002a56a  mov     [rsp+140h+var_E8], rbx
0x18002a56f  mov     edi, [rsi+10h]
0x18002a572  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18002a577  mov     r8, [rax+8]
0x18002a57b  mov     eax, [r8]
0x18002a57e  cmp     eax, 5
0x18002a581  jbe     short loc_18002A5BB
0x18002a583  mov     ecx, edi
0x18002a585  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x18002a58a  mov     [rsp+140h+var_100], rax
0x18002a58f  lea     rax, [rsi+20h]
0x18002a593  mov     [rsp+140h+var_F8], rax
0x18002a598  lea     rax, [rsp+140h+var_100]
0x18002a59d  mov     [rsp+140h+pvData], rax; __int64
0x18002a5a2  lea     rax, [rsp+140h+var_F8]
0x18002a5a7  mov     [rsp+140h+phkResult], rax; __int64
0x18002a5ac  lea     rdx, byte_180057F5B
0x18002a5b3  mov     rcx, r8; int
0x18002a5b6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &)
0x18002a5bb  lea     eax, [rdi-1]
0x18002a5be  xor     ebx, ebx
0x18002a5c0  cmp     eax, 2
0x18002a5c3  ja      loc_18002A835
0x18002a5c9  xorps   xmm0, xmm0
0x18002a5cc  movups  [rbp+40h+var_68], xmm0
0x18002a5d0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002a5d8  movdqu  [rbp+40h+var_58], xmm1
0x18002a5dd  mov     word ptr [rbp+40h+var_68], bx
0x18002a5e1  mov     ecx, edi
0x18002a5e3  sub     ecx, 1
0x18002a5e6  jz      short loc_18002A65B
0x18002a5e8  sub     ecx, 1
0x18002a5eb  jz      short loc_18002A65B
0x18002a5ed  cmp     ecx, 1
0x18002a5f0  jnz     loc_18002A679
0x18002a5f6  mov     rdx, cs:qword_180068EC8
0x18002a5fd  lea     rcx, [rbp+40h+var_A0]
0x18002a601  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002a606  nop
0x18002a607  lea     r8, asc_18004F678; "\\"
0x18002a60e  mov     rdx, rax
0x18002a611  lea     rcx, [rbp+40h+var_C0]
0x18002a615  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002a61a  nop
0x18002a61b  lea     r8, [rsi+90h]
0x18002a622  mov     rdx, rax
0x18002a625  lea     rcx, [rsp+140h+var_E0]
0x18002a62a  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18002a62f  mov     rdx, rax
0x18002a632  lea     rcx, [rbp+40h+var_68]
0x18002a636  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002a63b  lea     rcx, [rsp+140h+var_E0]
0x18002a640  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a645  nop
0x18002a646  lea     rcx, [rbp+40h+var_C0]
0x18002a64a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a64f  nop
0x18002a650  lea     rcx, [rbp+40h+var_A0]
0x18002a654  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a659  jmp     short loc_18002A679
0x18002a65b  mov     rdx, cs:qword_180068EB8
0x18002a662  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a666  inc     r8
0x18002a669  cmp     [rdx+r8*2], bx
0x18002a66e  jnz     short loc_18002A666
0x18002a670  lea     rcx, [rbp+40h+var_68]
0x18002a674  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18002a679  mov     [rbp+40h+hkey], rbx
0x18002a67d  xor     edx, edx
0x18002a67f  lea     rcx, [rbp+40h+hkey]
0x18002a683  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002a688  lea     rcx, [rbp+40h+var_68]
0x18002a68c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002a691  mov     rdx, rax; lpSubKey
0x18002a694  lea     rax, [rbp+40h+hkey]
0x18002a698  mov     [rsp+140h+phkResult], rax; phkResult
0x18002a69d  mov     r9d, 20019h; samDesired
0x18002a6a3  xor     r8d, r8d; ulOptions
0x18002a6a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a6ad  call    cs:__imp_RegOpenKeyExW
0x18002a6b3  mov     esi, eax
0x18002a6b5  test    eax, eax
0x18002a6b7  jz      short loc_18002A71B
0x18002a6b9  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18002a6be  mov     r8, [rax+8]
0x18002a6c2  mov     ecx, [r8]
0x18002a6c5  cmp     ecx, 5
0x18002a6c8  jbe     loc_18002A821
0x18002a6ce  mov     rdx, [rbp+40h+hkey]
0x18002a6d2  mov     [rsp+140h+var_F8], rdx
0x18002a6d7  lea     rcx, [rbp+40h+var_68]
0x18002a6db  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002a6e0  mov     [rsp+140h+var_F0], rax
0x18002a6e5  mov     dword ptr [rsp+140h+var_100], esi
0x18002a6e9  lea     rax, [rsp+140h+var_F8]
0x18002a6ee  mov     [rsp+140h+pcbData], rax; __int64
0x18002a6f3  lea     rax, [rsp+140h+var_F0]
0x18002a6f8  mov     [rsp+140h+pvData], rax; __int64
0x18002a6fd  lea     rax, [rsp+140h+var_100]
0x18002a702  mov     [rsp+140h+phkResult], rax; __int64
0x18002a707  lea     rdx, dword_180057EF4
0x18002a70e  mov     rcx, r8; int
0x18002a711  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &)
0x18002a716  jmp     loc_18002A821
0x18002a71b  xorps   xmm0, xmm0
0x18002a71e  movups  [rbp+40h+var_48], xmm0
0x18002a722  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002a72a  movdqu  [rbp+40h+var_38], xmm1
0x18002a72f  mov     word ptr [rbp+40h+var_48], bx
0x18002a733  sub     edi, 1
0x18002a736  jz      short loc_18002A75E
0x18002a738  sub     edi, 1
0x18002a73b  jz      short loc_18002A74F
0x18002a73d  cmp     edi, 1
0x18002a740  jnz     short loc_18002A774
0x18002a742  lea     r8d, [rdi+0Ch]
0x18002a746  lea     rdx, aWwanresettime; "WwanResetTime"
0x18002a74d  jmp     short loc_18002A76B
0x18002a74f  mov     r8d, 0Dh
0x18002a755  lea     rdx, aWlanresettime; "WlanResetTime"
0x18002a75c  jmp     short loc_18002A76B
0x18002a75e  mov     r8d, 11h
0x18002a764  lea     rdx, aEthernetresett; "EthernetResetTime"
0x18002a76b  lea     rcx, [rbp+40h+var_48]
0x18002a76f  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18002a774  mov     [rbp+40h+var_70], rbx
0x18002a778  mov     [rbp+40h+var_78], 8
0x18002a77f  lea     rcx, [rbp+40h+var_48]
0x18002a783  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002a788  mov     r8, rax; lpValue
0x18002a78b  lea     rax, [rbp+40h+var_78]
0x18002a78f  mov     [rsp+140h+pcbData], rax; pcbData
0x18002a794  lea     rax, [rbp+40h+var_70]
0x18002a798  mov     [rsp+140h+pvData], rax; pvData
0x18002a79d  mov     [rsp+140h+phkResult], rbx; pdwType
0x18002a7a2  xor     edx, edx; lpSubKey
0x18002a7a4  lea     r9d, [rdx+48h]; dwFlags
0x18002a7a8  mov     rcx, [rbp+40h+hkey]; hkey
0x18002a7ac  call    cs:__imp_RegGetValueW
0x18002a7b2  mov     edi, eax
0x18002a7b4  test    eax, eax
0x18002a7b6  jz      short loc_18002A813
0x18002a7b8  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18002a7bd  mov     r8, [rax+8]
0x18002a7c1  mov     ecx, [r8]
0x18002a7c4  cmp     ecx, 5
0x18002a7c7  jbe     short loc_18002A817
0x18002a7c9  mov     rdx, [rbp+40h+hkey]
0x18002a7cd  mov     [rsp+140h+var_F0], rdx
0x18002a7d2  lea     rcx, [rbp+40h+var_68]
0x18002a7d6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002a7db  mov     [rsp+140h+var_F8], rax
0x18002a7e0  mov     dword ptr [rsp+140h+var_100], edi
0x18002a7e4  lea     rax, [rsp+140h+var_F0]
0x18002a7e9  mov     [rsp+140h+pcbData], rax; __int64
0x18002a7ee  lea     rax, [rsp+140h+var_F8]
0x18002a7f3  mov     [rsp+140h+pvData], rax; __int64
0x18002a7f8  lea     rax, [rsp+140h+var_100]
0x18002a7fd  mov     [rsp+140h+phkResult], rax; __int64
0x18002a802  lea     rdx, word_180057E8E
0x18002a809  mov     rcx, r8; int
0x18002a80c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &)
0x18002a811  jmp     short loc_18002A817
0x18002a813  mov     rbx, [rbp+40h+var_70]
0x18002a817  lea     rcx, [rbp+40h+var_48]
0x18002a81b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a820  nop
0x18002a821  lea     rcx, [rbp+40h+hkey]
0x18002a825  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a82a  nop
0x18002a82b  lea     rcx, [rbp+40h+var_68]
0x18002a82f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a834  nop
0x18002a835  lea     rcx, [rsp+140h+var_E8]
0x18002a83a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002a83f  mov     rax, rbx
0x18002a842  mov     rcx, [rbp+40h+var_28]
0x18002a846  xor     rcx, rsp; StackCookie
0x18002a849  call    __security_check_cookie
0x18002a84e  add     rsp, 128h
0x18002a855  pop     rdi
0x18002a856  pop     rsi
0x18002a857  pop     rbx
0x18002a858  pop     rbp
0x18002a859  retn
```
