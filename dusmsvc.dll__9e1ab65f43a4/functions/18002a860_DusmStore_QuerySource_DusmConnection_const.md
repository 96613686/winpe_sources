# DusmStore::QuerySource(DusmConnection const &)

- ea: `0x18002a860`
- end: `0x18002ab1f`
- name: `?QuerySource@DusmStore@@SA?AW4_DUSM_SOURCE@@AEBVDusmConnection@@@Z`
- size: `703`
- prototype: ``
- caller_count: `7`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x180015340`
- `0x18001c23c`
- `0x18001cc38`
- `0x18002051c`
- `0x1800381b8`
- `0x18003a1e4`
- `0x18003aa18`

## callees

- `0x180001010`
- `0x180001f90`
- `0x1800020fc`
- `0x180007c90`
- `0x18000e828`
- `0x18000f094`
- `0x180010e28`
- `0x180012fcc`
- `0x180013114`
- `0x1800132f4`
- `0x180018a50`
- `0x18001d87c`
- `0x1800259f0`
- `0x180025a24`
- `0x180026fa0`
- `0x18002a860`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a896`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a896`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a9a5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a9a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a924`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a924`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a973`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a973`

## string_xrefs

- `0x18002aa8c`: `DusmStore::QuerySource::RegOpenKeyExW`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DusmStore::QuerySource(__int64 a1)
{
  LPCRITICAL_SECTION v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rax
  const WCHAR *v5; // rax
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  LSTATUS ValueW; // eax
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  const struct _tlgProvider_t *v12; // rax
  __int64 Iccid; // rax
  __int64 v14; // rax
  const WCHAR **v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  const WCHAR **v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  const char *pvData; // [rsp+28h] [rbp-51h]
  const char *pvDataa; // [rsp+28h] [rbp-51h]
  LPCRITICAL_SECTION v26; // [rsp+40h] [rbp-39h] BYREF
  __int64 v27; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v28[32]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v29[32]; // [rsp+70h] [rbp-9h] BYREF
  HKEY hkey; // [rsp+90h] [rbp+17h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+1Fh] BYREF
  char v32[4]; // [rsp+9Ch] [rbp+23h] BYREF
  _BYTE v33[32]; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v26 = v2;
  v3 = std::wstring::wstring((__int64)v29, (__int64)qword_180068EC8);
  v4 = std::operator+<wchar_t>((__int64)v28, v3, (__int64)L"\\");
  std::operator+<wchar_t>((__int64)v33, v4, a1 + 144);
  std::wstring::_Tidy_deallocate(v28);
  std::wstring::_Tidy_deallocate(v29);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v33);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x2001Fu, &hkey);
  v7 = v6;
  if ( v6 == 2 )
    goto LABEL_8;
  if ( v6 )
  {
    v12 = DusmTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0) )
    {
      Iccid = DusmConnection::GetIccid(a1);
      v14 = std::wstring::c_str(Iccid);
      v15 = (const WCHAR **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                              &v27,
                              v14);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        v16,
        (int)&word_18005822E,
        v16,
        v17,
        v15);
    }
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x3CE,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v7,
      (unsigned int)"DusmStore::QuerySource::RegOpenKeyExW",
      pvData);
  }
  *(_DWORD *)v32 = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"UseOperator", 0x10u, 0, v32, &pcbData);
  v9 = ValueW;
  if ( ValueW == 2 )
  {
LABEL_8:
    v10 = 2;
  }
  else
  {
    if ( ValueW )
    {
      v18 = DusmTraceLoggingProvider::Provider();
      if ( *(_DWORD *)v18 > 5u && (unsigned __int8)tlgKeywordOn(v18, 0) )
      {
        v19 = DusmConnection::GetIccid(a1);
        v20 = std::wstring::c_str(v19);
        v21 = (const WCHAR **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                &v27,
                                v20);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          v22,
          (int)byte_1800581F3,
          v22,
          v23,
          v21);
      }
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x3DE,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)v9,
        (unsigned int)"DusmStore::QuerySource::RegGetValueW",
        pvDataa);
    }
    if ( pcbData != 4 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x3E3,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0xD,
        (unsigned int)"DusmStore::QuerySource::RegGetValueW::cbData",
        pvDataa);
    v10 = 3;
    if ( *(_DWORD *)v32 != 3 )
    {
      RegDeleteValueW(hkey, L"UseOperator");
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      std::wstring::_Tidy_deallocate(v33);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v26);
      return 2;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  std::wstring::_Tidy_deallocate(v33);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v26);
  return v10;
}

```

## disassembly

```asm
0x18002a860  mov     [rsp-8+arg_8], rbx
0x18002a865  mov     [rsp-8+arg_10], rdi
0x18002a86a  push    rbp
0x18002a86b  lea     rbp, [rsp-57h]
0x18002a870  sub     rsp, 0D0h
0x18002a877  mov     rax, cs:__security_cookie
0x18002a87e  xor     rax, rsp
0x18002a881  mov     [rbp+57h+var_10], rax
0x18002a885  mov     rdi, rcx
0x18002a888  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002a88f  add     rbx, 28h ; '('
0x18002a893  mov     rcx, rbx; lpCriticalSection
0x18002a896  call    cs:__imp_EnterCriticalSection
0x18002a89c  mov     [rbp+57h+var_90], rbx
0x18002a8a0  mov     rdx, cs:qword_180068EC8
0x18002a8a7  lea     rcx, [rbp+57h+var_60]
0x18002a8ab  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002a8b0  nop
0x18002a8b1  lea     r8, asc_18004F678; "\\"
0x18002a8b8  mov     rdx, rax
0x18002a8bb  lea     rcx, [rbp+57h+var_80]
0x18002a8bf  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002a8c4  nop
0x18002a8c5  lea     r8, [rdi+90h]
0x18002a8cc  mov     rdx, rax
0x18002a8cf  lea     rcx, [rbp+57h+var_30]
0x18002a8d3  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18002a8d8  nop
0x18002a8d9  lea     rcx, [rbp+57h+var_80]
0x18002a8dd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a8e2  nop
0x18002a8e3  lea     rcx, [rbp+57h+var_60]
0x18002a8e7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a8ec  mov     [rbp+57h+hkey], 0
0x18002a8f4  xor     edx, edx
0x18002a8f6  lea     rcx, [rbp+57h+hkey]
0x18002a8fa  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002a8ff  lea     rcx, [rbp+57h+var_30]
0x18002a903  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002a908  mov     rdx, rax; lpSubKey
0x18002a90b  lea     rax, [rbp+57h+hkey]
0x18002a90f  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18002a914  mov     r9d, 2001Fh; samDesired
0x18002a91a  xor     r8d, r8d; ulOptions
0x18002a91d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a924  call    cs:__imp_RegOpenKeyExW
0x18002a92a  mov     ebx, eax
0x18002a92c  cmp     eax, 2
0x18002a92f  jz      loc_18002A9CE
0x18002a935  test    eax, eax
0x18002a937  jnz     loc_18002AA3B
0x18002a93d  mov     dword ptr [rbp+57h+var_34], eax
0x18002a940  mov     [rbp+57h+var_38], 4
0x18002a947  lea     rax, [rbp+57h+var_38]
0x18002a94b  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18002a950  lea     rax, [rbp+57h+var_34]
0x18002a954  mov     [rsp+0D0h+pvData], rax; char *
0x18002a959  mov     [rsp+0D0h+phkResult], 0; pdwType
0x18002a962  lea     r9d, [rbx+10h]; dwFlags
0x18002a966  lea     r8, ValueName; "UseOperator"
0x18002a96d  xor     edx, edx; lpSubKey
0x18002a96f  mov     rcx, [rbp+57h+hkey]; hkey
0x18002a973  call    cs:__imp_RegGetValueW
0x18002a979  mov     ebx, eax
0x18002a97b  cmp     eax, 2
0x18002a97e  jz      short loc_18002A9CE
0x18002a980  test    eax, eax
0x18002a982  jnz     loc_18002AAAD
0x18002a988  cmp     [rbp+57h+var_38], 4
0x18002a98c  jnz     loc_18002AA13
0x18002a992  lea     ebx, [rax+3]
0x18002a995  cmp     dword ptr [rbp+57h+var_34], ebx
0x18002a998  jz      short loc_18002A9D3
0x18002a99a  lea     rdx, ValueName; "UseOperator"
0x18002a9a1  mov     rcx, [rbp+57h+hkey]; hKey
0x18002a9a5  call    cs:__imp_RegDeleteValueW
0x18002a9ab  nop
0x18002a9ac  lea     rcx, [rbp+57h+hkey]
0x18002a9b0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a9b5  nop
0x18002a9b6  lea     rcx, [rbp+57h+var_30]
0x18002a9ba  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a9bf  nop
0x18002a9c0  lea     rcx, [rbp+57h+var_90]
0x18002a9c4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002a9c9  lea     eax, [rbx-1]
0x18002a9cc  jmp     short loc_18002A9F2
0x18002a9ce  mov     ebx, 2
0x18002a9d3  lea     rcx, [rbp+57h+hkey]
0x18002a9d7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a9dc  nop
0x18002a9dd  lea     rcx, [rbp+57h+var_30]
0x18002a9e1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a9e6  nop
0x18002a9e7  lea     rcx, [rbp+57h+var_90]
0x18002a9eb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002a9f0  mov     eax, ebx
0x18002a9f2  mov     rcx, [rbp+57h+var_10]
0x18002a9f6  xor     rcx, rsp; StackCookie
0x18002a9f9  call    __security_check_cookie
0x18002a9fe  lea     r11, [rsp+0D0h+var_s0]
0x18002aa06  mov     rbx, [r11+18h]
0x18002aa0a  mov     rdi, [r11+20h]
0x18002aa0e  mov     rsp, r11
0x18002aa11  pop     rbp
0x18002aa12  retn
0x18002aa13  mov     rcx, [rbp+5Fh]; this
0x18002aa17  lea     rax, aDusmstoreQuery_9; "DusmStore::QuerySource::RegGetValueW::c"...
0x18002aa1e  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x18002aa23  mov     r9d, 0Dh; char *
0x18002aa29  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002aa30  mov     edx, 3E3h; void *
0x18002aa35  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002aa3b  call    ?Provider@DusmTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; DusmTraceLoggingProvider::Provider(void)
0x18002aa40  mov     r8, rax
0x18002aa43  mov     edx, [rax]
0x18002aa45  cmp     edx, 5
0x18002aa48  jbe     short loc_18002AA88
0x18002aa4a  xor     edx, edx
0x18002aa4c  mov     rcx, rax
0x18002aa4f  call    _tlgKeywordOn
0x18002aa54  test    al, al
0x18002aa56  jz      short loc_18002AA88
0x18002aa58  mov     rcx, rdi
0x18002aa5b  call    ?GetIccid@DusmConnection@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; DusmConnection::GetIccid(void)
0x18002aa60  mov     rcx, rax
0x18002aa63  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002aa68  mov     rdx, rax
0x18002aa6b  lea     rcx, [rbp+57h+var_88]
0x18002aa6f  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18002aa74  mov     [rsp+0D0h+phkResult], rax
0x18002aa79  lea     rdx, word_18005822E
0x18002aa80  mov     rcx, r8
0x18002aa83  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18002aa88  mov     rcx, [rbp+5Fh]; this
0x18002aa8c  lea     rax, aDusmstoreQuery_2; "DusmStore::QuerySource::RegOpenKeyExW"
0x18002aa93  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x18002aa98  mov     r9d, ebx; char *
0x18002aa9b  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002aaa2  mov     edx, 3CEh; void *
0x18002aaa7  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002aaad  call    ?Provider@DusmTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; DusmTraceLoggingProvider::Provider(void)
0x18002aab2  mov     r8, rax
0x18002aab5  mov     ecx, [rax]
0x18002aab7  cmp     ecx, 5
0x18002aaba  jbe     short loc_18002AAFA
0x18002aabc  xor     edx, edx
0x18002aabe  mov     rcx, rax
0x18002aac1  call    _tlgKeywordOn
0x18002aac6  test    al, al
0x18002aac8  jz      short loc_18002AAFA
0x18002aaca  mov     rcx, rdi
0x18002aacd  call    ?GetIccid@DusmConnection@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; DusmConnection::GetIccid(void)
0x18002aad2  mov     rcx, rax
0x18002aad5  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002aada  mov     rdx, rax
0x18002aadd  lea     rcx, [rbp+57h+var_88]
0x18002aae1  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18002aae6  mov     [rsp+0D0h+phkResult], rax
0x18002aaeb  lea     rdx, byte_1800581F3
0x18002aaf2  mov     rcx, r8
0x18002aaf5  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18002aafa  mov     rcx, [rbp+5Fh]; this
0x18002aafe  lea     rax, aDusmstoreQuery_12; "DusmStore::QuerySource::RegGetValueW"
0x18002ab05  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x18002ab0a  mov     r9d, ebx; char *
0x18002ab0d  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002ab14  mov     edx, 3DEh; void *
0x18002ab19  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
