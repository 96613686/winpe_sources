# DusmStore::SetResetTime(DusmConnection const &,_FILETIME const &)

- ea: `0x18002cd3c`
- end: `0x18002cfd3`
- name: `?SetResetTime@DusmStore@@SAXAEBVDusmConnection@@AEBU_FILETIME@@@Z`
- size: `663`
- prototype: `void __fastcall(const struct DusmConnection *, const struct _FILETIME *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18001d738`

## callees

- `0x180007c90`
- `0x18000e828`
- `0x18000f094`
- `0x18000f648`
- `0x180012fcc`
- `0x180013114`
- `0x180017cec`
- `0x18001d87c`
- `0x1800259f0`
- `0x180025a24`
- `0x180026fa0`
- `0x18002cd3c`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cd78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cd78`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ce80`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ce80`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002cf0b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002cf0b`

## string_xrefs

- `0x18002cfb2`: `DusmStore::SetResetTime::RegCreateKeyExW`
- `0x18002cf65`: `DusmStore::SetResetTime::RegSetKeyValueW`

## pseudocode

```c
void __fastcall DusmStore::SetResetTime(const struct DusmConnection *a1, const struct _FILETIME *a2)
{
  LPCRITICAL_SECTION v4; // rbx
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  const WCHAR *v10; // rax
  unsigned int v11; // eax
  int v12; // ebx
  int v13; // ebx
  __int64 v14; // r8
  const wchar_t *v15; // rdx
  const WCHAR *v16; // rax
  unsigned int v17; // eax
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  const char *samDesireda; // [rsp+28h] [rbp-D8h]
  const char *samDesiredb; // [rsp+28h] [rbp-D8h]
  LPCRITICAL_SECTION v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v23[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v24[32]; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v26[2]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v27[2]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  v4 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v21 = v4;
  v27[0] = 0;
  v27[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v27[0]) = 0;
  v5 = *((_DWORD *)a1 + 4);
  if ( v5 == 3 )
  {
    v7 = std::wstring::wstring(v24, qword_180068EC8);
    v8 = std::operator+<wchar_t>(v23, v7, L"\\");
    v9 = std::operator+<wchar_t>(v22, v8, (char *)a1 + 144);
    std::wstring::operator=(v27, v9);
    std::wstring::_Tidy_deallocate(v22);
    std::wstring::_Tidy_deallocate(v23);
    std::wstring::_Tidy_deallocate(v24);
  }
  else
  {
    if ( (unsigned int)(v5 - 1) > 1 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x77E,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::QueryResetTime::mediaType",
        samDesired);
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)qword_180068EB8 + v6) );
    std::wstring::_Assign<wchar_t>(v27, qword_180068EB8, v6);
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v27);
  v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v11 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x793,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v11,
      (unsigned int)"DusmStore::SetResetTime::RegCreateKeyExW",
      samDesireda);
  v26[0] = 0;
  v26[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v26[0]) = 0;
  v12 = v5 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 != 1 )
        goto LABEL_15;
      v14 = 13;
      v15 = L"WwanResetTime";
    }
    else
    {
      v14 = 13;
      v15 = L"WlanResetTime";
    }
  }
  else
  {
    v14 = 17;
    v15 = L"EthernetResetTime";
  }
  std::wstring::_Assign<wchar_t>(v26, v15, v14);
LABEL_15:
  v16 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26);
  v17 = RegSetKeyValueW(hKey, 0, v16, 0xBu, a2, 8u);
  if ( v17 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x7A9,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v17,
      (unsigned int)"DusmStore::SetResetTime::RegSetKeyValueW",
      samDesiredb);
  std::wstring::_Tidy_deallocate(v26);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(v27);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
}

```

## disassembly

```asm
0x18002cd3c  mov     [rsp-8+arg_10], rbx
0x18002cd41  mov     [rsp-8+arg_18], rsi
0x18002cd46  push    rbp
0x18002cd47  push    rdi
0x18002cd48  push    r14
0x18002cd4a  lea     rbp, [rsp-10h]
0x18002cd4f  sub     rsp, 110h
0x18002cd56  mov     rax, cs:__security_cookie
0x18002cd5d  xor     rax, rsp
0x18002cd60  mov     [rbp+20h+var_20], rax
0x18002cd64  mov     rsi, rdx
0x18002cd67  mov     rdi, rcx
0x18002cd6a  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002cd71  add     rbx, 28h ; '('
0x18002cd75  mov     rcx, rbx; lpCriticalSection
0x18002cd78  call    cs:__imp_EnterCriticalSection
0x18002cd7e  mov     [rsp+120h+var_D0], rbx
0x18002cd83  xorps   xmm0, xmm0
0x18002cd86  movups  [rbp+20h+var_40], xmm0
0x18002cd8a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002cd92  movdqu  [rbp+20h+var_30], xmm1
0x18002cd97  xor     r14d, r14d
0x18002cd9a  mov     word ptr [rbp+20h+var_40], r14w
0x18002cd9f  mov     ebx, [rdi+10h]
0x18002cda2  cmp     ebx, 3
0x18002cda5  jz      short loc_18002CDD3
0x18002cda7  lea     eax, [rbx-1]
0x18002cdaa  cmp     eax, 1
0x18002cdad  ja      loc_18002CF86
0x18002cdb3  mov     rdx, cs:qword_180068EB8
0x18002cdba  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002cdbe  inc     r8
0x18002cdc1  cmp     [rdx+r8*2], r14w
0x18002cdc6  jnz     short loc_18002CDBE
0x18002cdc8  lea     rcx, [rbp+20h+var_40]
0x18002cdcc  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18002cdd1  jmp     short loc_18002CE38
0x18002cdd3  mov     rdx, cs:qword_180068EC8
0x18002cdda  lea     rcx, [rbp+20h+var_88]
0x18002cdde  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002cde3  nop
0x18002cde4  lea     r8, asc_18004F678; "\\"
0x18002cdeb  mov     rdx, rax
0x18002cdee  lea     rcx, [rsp+120h+var_A8]
0x18002cdf3  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002cdf8  nop
0x18002cdf9  lea     r8, [rdi+90h]
0x18002ce00  mov     rdx, rax
0x18002ce03  lea     rcx, [rsp+120h+var_C8]
0x18002ce08  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18002ce0d  mov     rdx, rax
0x18002ce10  lea     rcx, [rbp+20h+var_40]
0x18002ce14  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002ce19  lea     rcx, [rsp+120h+var_C8]
0x18002ce1e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ce23  nop
0x18002ce24  lea     rcx, [rsp+120h+var_A8]
0x18002ce29  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ce2e  nop
0x18002ce2f  lea     rcx, [rbp+20h+var_88]
0x18002ce33  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ce38  mov     [rbp+20h+hKey], r14
0x18002ce3c  xor     edx, edx
0x18002ce3e  lea     rcx, [rbp+20h+hKey]
0x18002ce42  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002ce47  lea     rcx, [rbp+20h+var_40]
0x18002ce4b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002ce50  mov     rdx, rax; lpSubKey
0x18002ce53  mov     [rsp+120h+lpdwDisposition], r14; lpdwDisposition
0x18002ce58  lea     rax, [rbp+20h+hKey]
0x18002ce5c  mov     [rsp+120h+phkResult], rax; phkResult
0x18002ce61  mov     [rsp+120h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002ce66  mov     dword ptr [rsp+120h+samDesired], 20006h; char *
0x18002ce6e  mov     [rsp+120h+dwOptions], r14d; dwOptions
0x18002ce73  xor     r9d, r9d; lpClass
0x18002ce76  xor     r8d, r8d; Reserved
0x18002ce79  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ce80  call    cs:__imp_RegCreateKeyExW
0x18002ce86  test    eax, eax
0x18002ce88  jnz     loc_18002CFAE
0x18002ce8e  xorps   xmm0, xmm0
0x18002ce91  movups  [rbp+20h+var_60], xmm0
0x18002ce95  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002ce9d  movdqu  [rbp+20h+var_50], xmm1
0x18002cea2  mov     word ptr [rbp+20h+var_60], r14w
0x18002cea7  sub     ebx, 1
0x18002ceaa  jz      short loc_18002CED2
0x18002ceac  sub     ebx, 1
0x18002ceaf  jz      short loc_18002CEC3
0x18002ceb1  cmp     ebx, 1
0x18002ceb4  jnz     short loc_18002CEE8
0x18002ceb6  lea     r8d, [rax+0Dh]
0x18002ceba  lea     rdx, aWwanresettime; "WwanResetTime"
0x18002cec1  jmp     short loc_18002CEDF
0x18002cec3  mov     r8d, 0Dh
0x18002cec9  lea     rdx, aWlanresettime; "WlanResetTime"
0x18002ced0  jmp     short loc_18002CEDF
0x18002ced2  mov     r8d, 11h
0x18002ced8  lea     rdx, aEthernetresett; "EthernetResetTime"
0x18002cedf  lea     rcx, [rbp+20h+var_60]
0x18002cee3  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18002cee8  lea     rcx, [rbp+20h+var_60]
0x18002ceec  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002cef1  mov     r8, rax; lpValueName
0x18002cef4  mov     dword ptr [rsp+120h+samDesired], 8; char *
0x18002cefc  mov     qword ptr [rsp+120h+dwOptions], rsi; lpData
0x18002cf01  xor     edx, edx; lpSubKey
0x18002cf03  lea     r9d, [rdx+0Bh]; dwType
0x18002cf07  mov     rcx, [rbp+20h+hKey]; hKey
0x18002cf0b  call    cs:__imp_RegSetKeyValueW
0x18002cf11  test    eax, eax
0x18002cf13  jnz     short loc_18002CF61
0x18002cf15  lea     rcx, [rbp+20h+var_60]
0x18002cf19  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cf1e  nop
0x18002cf1f  lea     rcx, [rbp+20h+hKey]
0x18002cf23  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002cf28  nop
0x18002cf29  lea     rcx, [rbp+20h+var_40]
0x18002cf2d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cf32  nop
0x18002cf33  lea     rcx, [rsp+120h+var_D0]
0x18002cf38  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002cf3d  mov     rcx, [rbp+20h+var_20]
0x18002cf41  xor     rcx, rsp; StackCookie
0x18002cf44  call    __security_check_cookie
0x18002cf49  lea     r11, [rsp+120h+var_10]
0x18002cf51  mov     rbx, [r11+30h]
0x18002cf55  mov     rsi, [r11+38h]
0x18002cf59  mov     rsp, r11
0x18002cf5c  pop     r14
0x18002cf5e  pop     rdi
0x18002cf5f  pop     rbp
0x18002cf60  retn
0x18002cf61  mov     rcx, [rbp+28h]; this
0x18002cf65  lea     rdx, aDusmstoreSetre_0; "DusmStore::SetResetTime::RegSetKeyValue"...
0x18002cf6c  mov     qword ptr [rsp+120h+dwOptions], rdx; unsigned int
0x18002cf71  mov     r9d, eax; char *
0x18002cf74  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002cf7b  mov     edx, 7A9h; void *
0x18002cf80  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002cf86  mov     rcx, [rbp+28h]; this
0x18002cf8a  lea     rax, aDusmstoreQuery_17; "DusmStore::QueryResetTime::mediaType"
0x18002cf91  mov     qword ptr [rsp+120h+dwOptions], rax; unsigned int
0x18002cf96  mov     r9d, 57h ; 'W'; char *
0x18002cf9c  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002cfa3  mov     edx, 77Eh; void *
0x18002cfa8  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002cfae  mov     rcx, [rbp+28h]; this
0x18002cfb2  lea     rdx, aDusmstoreSetre; "DusmStore::SetResetTime::RegCreateKeyEx"...
0x18002cfb9  mov     qword ptr [rsp+120h+dwOptions], rdx; unsigned int
0x18002cfbe  mov     r9d, eax; char *
0x18002cfc1  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002cfc8  mov     edx, 793h; void *
0x18002cfcd  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
