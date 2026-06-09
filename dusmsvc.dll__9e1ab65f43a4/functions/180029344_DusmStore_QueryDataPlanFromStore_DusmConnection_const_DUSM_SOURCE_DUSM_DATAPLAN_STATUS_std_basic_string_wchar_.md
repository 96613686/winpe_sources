# DusmStore::QueryDataPlanFromStore(DusmConnection const &,_DUSM_SOURCE,_DUSM_DATAPLAN_STATUS &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180029344`
- end: `0x1800295da`
- name: `?QueryDataPlanFromStore@DusmStore@@AEAAHAEBVDusmConnection@@W4_DUSM_SOURCE@@AEAU_DUSM_DATAPLAN_STATUS@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `662`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180028f48`
- `0x18002bdf4`

## callees

- `0x180007c90`
- `0x180008704`
- `0x18000e828`
- `0x18000f094`
- `0x180012fcc`
- `0x180013114`
- `0x180017cec`
- `0x18001d87c`
- `0x1800259f0`
- `0x180025a24`
- `0x180026fa0`
- `0x180029344`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029386`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029386`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029418`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029418`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002946e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002946e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800294ba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029516`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800294ba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029516`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DusmStore::QueryDataPlanFromStore(
        struct _RTL_CRITICAL_SECTION *a1,
        __int64 a2,
        int a3,
        void *a4,
        __int64 a5)
{
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  const WCHAR *v11; // rax
  unsigned int v12; // edi
  DWORD i; // ebx
  LSTATUS v14; // eax
  __int64 v15; // r8
  const char *lpClass; // [rsp+28h] [rbp-D8h]
  struct _RTL_CRITICAL_SECTION *v18; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[32]; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp-78h] BYREF
  int pvData; // [rsp+8Ch] [rbp-74h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  DWORD cchName; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v25[32]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Name[264]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v8 = a1 + 1;
  EnterCriticalSection(a1 + 1);
  v18 = v8;
  hKey = 0;
  v9 = std::wstring::wstring((__int64)v20, (__int64)qword_180068EC8);
  v10 = std::operator+<wchar_t>((__int64)v19, v9, (__int64)L"\\");
  std::operator+<wchar_t>((__int64)v25, v10, a2 + 144);
  std::wstring::_Tidy_deallocate(v19);
  std::wstring::_Tidy_deallocate(v20);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &hKey) )
  {
LABEL_15:
    std::wstring::_Tidy_deallocate(v25);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v18);
    return 0;
  }
  else
  {
    v12 = 0;
    pvData = 0;
    pcbData = 0;
    for ( i = 0; i < 0x2710; ++i )
    {
      memset_0(Name, 0, 0x208u);
      cchName = 260;
      v14 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      if ( v14 == 259 )
        break;
      if ( !v14 )
      {
        pvData = 0;
        pcbData = 4;
        if ( !RegGetValueW(hKey, Name, L"DataPlanFlags", 0x10u, 0, &pvData, &pcbData) && (a3 == 3) == (pvData & 1) )
        {
          pcbData = 68;
          if ( RegGetValueW(hKey, Name, L"DataPlan", 8u, 0, a4, &pcbData) )
            goto LABEL_15;
          if ( pcbData != 68 )
            wil::details::in1diag3::Throw_Win32Msg(
              retaddr,
              (void *)0x36A,
              (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
              (const char *)0xD,
              (unsigned int)"DusmStore::QueryDataPlanFromStore::RegGetValueW::cbData",
              lpClass);
          v12 = 1;
          v15 = -1;
          do
            ++v15;
          while ( Name[v15] );
          std::wstring::_Assign<wchar_t>(a5, Name, v15);
          break;
        }
      }
    }
    std::wstring::_Tidy_deallocate(v25);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v18);
    return v12;
  }
}

```

## disassembly

```asm
0x180029344  push    rbp
0x180029346  push    rbx
0x180029347  push    rsi
0x180029348  push    rdi
0x180029349  push    r12
0x18002934b  push    r14
0x18002934d  push    r15
0x18002934f  lea     rbp, [rsp-1E0h]
0x180029357  sub     rsp, 2E0h
0x18002935e  mov     rax, cs:__security_cookie
0x180029365  xor     rax, rsp
0x180029368  mov     [rbp+210h+var_40], rax
0x18002936f  mov     r14, r9
0x180029372  mov     esi, r8d
0x180029375  mov     rdi, rdx
0x180029378  mov     r15, [rbp+210h+arg_20]
0x18002937f  lea     rbx, [rcx+28h]
0x180029383  mov     rcx, rbx; lpCriticalSection
0x180029386  call    cs:__imp_EnterCriticalSection
0x18002938c  mov     [rsp+310h+var_2D0], rbx
0x180029391  xor     r12d, r12d
0x180029394  mov     [rbp+210h+hKey], r12
0x180029398  mov     rdx, cs:qword_180068EC8
0x18002939f  lea     rcx, [rsp+310h+var_2A8]
0x1800293a4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800293a9  nop
0x1800293aa  lea     r8, asc_18004F678; "\\"
0x1800293b1  mov     rdx, rax
0x1800293b4  lea     rcx, [rsp+310h+var_2C8]
0x1800293b9  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1800293be  nop
0x1800293bf  lea     r8, [rdi+90h]
0x1800293c6  mov     rdx, rax
0x1800293c9  lea     rcx, [rbp+210h+var_270]
0x1800293cd  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x1800293d2  nop
0x1800293d3  lea     rcx, [rsp+310h+var_2C8]
0x1800293d8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800293dd  nop
0x1800293de  lea     rcx, [rsp+310h+var_2A8]
0x1800293e3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800293e8  xor     edx, edx
0x1800293ea  lea     rcx, [rbp+210h+hKey]
0x1800293ee  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800293f3  lea     rcx, [rbp+210h+var_270]
0x1800293f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800293fc  mov     rdx, rax; lpSubKey
0x1800293ff  lea     rax, [rbp+210h+hKey]
0x180029403  mov     [rsp+310h+phkResult], rax; phkResult
0x180029408  mov     r9d, 20019h; samDesired
0x18002940e  xor     r8d, r8d; ulOptions
0x180029411  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029418  call    cs:__imp_RegOpenKeyExW
0x18002941e  test    eax, eax
0x180029420  jnz     loc_18002956E
0x180029426  mov     edi, r12d
0x180029429  mov     [rbp+210h+pvData], r12d
0x18002942d  mov     [rbp+210h+pcbData], r12d
0x180029431  mov     ebx, r12d
0x180029434  xor     edx, edx; Val
0x180029436  mov     r8d, 208h; Size
0x18002943c  lea     rcx, [rbp+210h+Name]; void *
0x180029440  call    memset_0
0x180029445  mov     [rbp+210h+cchName], 104h
0x18002944c  mov     [rsp+310h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180029451  mov     [rsp+310h+lpcchClass], r12; lpcchClass
0x180029456  mov     [rsp+310h+lpClass], r12; lpClass
0x18002945b  mov     [rsp+310h+phkResult], r12; lpReserved
0x180029460  lea     r9, [rbp+210h+cchName]; lpcchName
0x180029464  lea     r8, [rbp+210h+Name]; lpName
0x180029468  mov     edx, ebx; dwIndex
0x18002946a  mov     rcx, [rbp+210h+hKey]; hKey
0x18002946e  call    cs:__imp_RegEnumKeyExW
0x180029474  cmp     eax, 103h
0x180029479  jz      loc_18002954C
0x18002947f  test    eax, eax
0x180029481  jnz     short loc_1800294D7
0x180029483  mov     [rbp+210h+pvData], r12d
0x180029487  mov     [rbp+210h+pcbData], 4
0x18002948e  lea     rax, [rbp+210h+pcbData]
0x180029492  mov     [rsp+310h+lpcchClass], rax; pcbData
0x180029497  lea     rax, [rbp+210h+pvData]
0x18002949b  mov     [rsp+310h+lpClass], rax; pvData
0x1800294a0  mov     [rsp+310h+phkResult], r12; pdwType
0x1800294a5  mov     r9d, 10h; dwFlags
0x1800294ab  lea     r8, aDataplanflags; "DataPlanFlags"
0x1800294b2  lea     rdx, [rbp+210h+Name]; lpSubKey
0x1800294b6  mov     rcx, [rbp+210h+hKey]; hkey
0x1800294ba  call    cs:__imp_RegGetValueW
0x1800294c0  test    eax, eax
0x1800294c2  jnz     short loc_1800294D7
0x1800294c4  mov     ecx, r12d
0x1800294c7  cmp     esi, 3
0x1800294ca  setz    cl
0x1800294cd  mov     eax, [rbp+210h+pvData]
0x1800294d0  and     eax, 1
0x1800294d3  cmp     ecx, eax
0x1800294d5  jz      short loc_1800294E7
0x1800294d7  inc     ebx
0x1800294d9  cmp     ebx, 2710h
0x1800294df  jb      loc_180029434
0x1800294e5  jmp     short loc_18002954C
0x1800294e7  mov     [rbp+210h+pcbData], 44h ; 'D'
0x1800294ee  lea     rax, [rbp+210h+pcbData]
0x1800294f2  mov     [rsp+310h+lpcchClass], rax; pcbData
0x1800294f7  mov     [rsp+310h+lpClass], r14; char *
0x1800294fc  mov     [rsp+310h+phkResult], r12; pdwType
0x180029501  mov     r9d, 8; dwFlags
0x180029507  lea     r8, aDataplan; "DataPlan"
0x18002950e  lea     rdx, [rbp+210h+Name]; lpSubKey
0x180029512  mov     rcx, [rbp+210h+hKey]; hkey
0x180029516  call    cs:__imp_RegGetValueW
0x18002951c  test    eax, eax
0x18002951e  jnz     short loc_18002956E
0x180029520  cmp     [rbp+210h+pcbData], 44h ; 'D'
0x180029524  jnz     loc_1800295AF
0x18002952a  lea     edi, [rax+1]
0x18002952d  lea     rax, [rbp+210h+Name]
0x180029531  or      r8, 0FFFFFFFFFFFFFFFFh
0x180029535  inc     r8
0x180029538  cmp     [rax+r8*2], r12w
0x18002953d  jnz     short loc_180029535
0x18002953f  lea     rdx, [rbp+210h+Name]
0x180029543  mov     rcx, r15
0x180029546  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18002954b  nop
0x18002954c  lea     rcx, [rbp+210h+var_270]
0x180029550  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029555  nop
0x180029556  lea     rcx, [rbp+210h+hKey]
0x18002955a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002955f  nop
0x180029560  lea     rcx, [rsp+310h+var_2D0]
0x180029565  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002956a  mov     eax, edi
0x18002956c  jmp     short loc_18002958E
0x18002956e  lea     rcx, [rbp+210h+var_270]
0x180029572  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029577  nop
0x180029578  lea     rcx, [rbp+210h+hKey]
0x18002957c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029581  nop
0x180029582  lea     rcx, [rsp+310h+var_2D0]
0x180029587  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002958c  xor     eax, eax
0x18002958e  mov     rcx, [rbp+210h+var_40]
0x180029595  xor     rcx, rsp; StackCookie
0x180029598  call    __security_check_cookie
0x18002959d  add     rsp, 2E0h
0x1800295a4  pop     r15
0x1800295a6  pop     r14
0x1800295a8  pop     r12
0x1800295aa  pop     rdi
0x1800295ab  pop     rsi
0x1800295ac  pop     rbx
0x1800295ad  pop     rbp
0x1800295ae  retn
0x1800295af  mov     rcx, [rbp+218h]; this
0x1800295b6  lea     rax, aDusmstoreQuery_4; "DusmStore::QueryDataPlanFromStore::RegG"...
0x1800295bd  mov     [rsp+310h+phkResult], rax; unsigned int
0x1800295c2  mov     r9d, 0Dh; char *
0x1800295c8  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x1800295cf  mov     edx, 36Ah; void *
0x1800295d4  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
