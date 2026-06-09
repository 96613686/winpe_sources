# RasEapSetTimeStampWchar

- ea: `0x180029180`
- end: `0x180029401`
- name: `RasEapSetTimeStampWchar`
- size: `641`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028920`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180010140`
- `0x180029180`
- `0x180029408`
- `0x180036414`
- `0x180036468`
- `0x18003fe64`
- `0x180064a74`
- `0x180065fd0`
- `0x1800662b0`
- `0x18006666c`
- `0x180066d1c`
- `0x180067024`
- `0x1800670fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029213`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029213`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800291cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800291cb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800292b6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800292b6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180029398`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180029398`

## string_xrefs

- `0x180029205`: `SYSTEM\CurrentControlSet\Services\RasMan\Deleted-Profiles\`
- `0x1800293bf`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _EAPTLS_CONTROL_BLOCK **__fastcall RasEapSetTimeStampWchar(LPCWSTR lpValueName)
{
  HKEY *v2; // rbx
  REGSAM access_flags; // eax
  LSTATUS v4; // eax
  bool v5; // sf
  __int64 v6; // r8
  unsigned int v7; // eax
  int v8; // eax
  struct _EAPTLS_CONTROL_BLOCK **result; // rax
  __int64 v10; // rax
  int phkResult; // [rsp+20h] [rbp-68h]
  HKEY hKey; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v13[2]; // [rsp+38h] [rbp-50h] BYREF
  const std::exception *v14; // [rsp+48h] [rbp-40h] BYREF
  LPCVOID lpData[2]; // [rsp+50h] [rbp-38h] BYREF
  __int64 v16; // [rsp+60h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp+10h] BYREF
  FILETIME FileTime1; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids, lpValueName);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v20 = 0;
  v2 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v20);
  access_flags = wil::reg::reg_view_details::get_access_flags(0);
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Deleted-Profiles\\",
         0,
         access_flags,
         v2);
  v5 = v4 < 0;
  if ( v4 > 0 )
    v5 = 1;
  if ( !v5 )
  {
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(v13);
    if ( (int)wil::reg::get_value_binary_nothrow(v20, lpValueName, v6, v13) >= 0 )
    {
      FileTime1 = 0;
      v7 = DeserializeFileTime(v13, &FileTime1);
      if ( v7 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids, v7);
      }
      else if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) >= 0 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids);
      }
      else if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&FileTime1 < 0x165A0BC00uLL )
      {
        SystemTimeAsFileTime = FileTime1;
      }
    }
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(v13);
  }
  *(_OWORD *)lpData = 0;
  v16 = 0;
  v13[0] = &SystemTimeAsFileTime;
  FileTime1 = (FILETIME)&FileTime1;
  try
  {
    std::vector<unsigned char>::_Construct_n<unsigned char *,unsigned char *>();
    wil::reg::create_unique_key(&hKey);
    v8 = RegSetKeyValueW(hKey, 0, lpValueName, 3u, lpData[0], LODWORD(lpData[1]) - LODWORD(lpData[0]));
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v8,
        phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::vector<unsigned char>::_Tidy(lpData);
    result = (struct _EAPTLS_CONTROL_BLOCK **)wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
  }
  catch ( const std::exception *v14 )
  {
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v10 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v14 + 8LL))(v14);
      return (struct _EAPTLS_CONTROL_BLOCK **)WPP_SF_s(
                                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                17,
                                                WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids,
                                                v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180029180  push    rbx
0x180029182  push    rdi
0x180029183  push    r14
0x180029185  sub     rsp, 70h
0x180029189  mov     rdi, rcx
0x18002918c  lea     r14, WPP_GLOBAL_Control
0x180029193  mov     rcx, cs:WPP_GLOBAL_Control
0x18002919a  cmp     rcx, r14
0x18002919d  jz      short loc_1800291B7
0x18002919f  mov     edx, 0Eh
0x1800291a4  mov     r9, rdi
0x1800291a7  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x1800291ae  mov     rcx, [rcx+10h]
0x1800291b2  call    WPP_SF_S
0x1800291b7  mov     qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800291c3  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800291cb  call    cs:__imp_GetSystemTimeAsFileTime
0x1800291d2  nop     dword ptr [rax+rax+00h]
0x1800291d7  mov     [rsp+88h+arg_18], 0
0x1800291e3  lea     rcx, [rsp+88h+arg_18]
0x1800291eb  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800291f0  mov     rbx, rax
0x1800291f3  xor     ecx, ecx
0x1800291f5  call    ?get_access_flags@reg_view_details@reg@wil@@YAKW4key_access@23@@Z; wil::reg::reg_view_details::get_access_flags(wil::reg::key_access)
0x1800291fa  mov     [rsp+88h+phkResult], rbx; phkResult
0x1800291ff  mov     r9d, eax; samDesired
0x180029202  xor     r8d, r8d; ulOptions
0x180029205  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18002920c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029213  call    cs:__imp_RegOpenKeyExW
0x18002921a  nop     dword ptr [rax+rax+00h]
0x18002921f  test    eax, eax
0x180029221  jle     short loc_18002922D
0x180029223  movzx   eax, ax
0x180029226  or      eax, 80070000h
0x18002922b  test    eax, eax
0x18002922d  js      loc_18002931D
0x180029233  lea     rcx, [rsp+88h+var_50]
0x180029238  call    ??0?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x18002923d  lea     r9, [rsp+88h+var_50]
0x180029242  mov     rdx, rdi
0x180029245  mov     rcx, [rsp+88h+arg_18]
0x18002924d  call    ?get_value_binary_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGIAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@2@@Z; wil::reg::get_value_binary_nothrow(HKEY__ *,ushort const *,uint,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)
0x180029252  test    eax, eax
0x180029254  js      loc_180029313
0x18002925a  mov     qword ptr [rsp+88h+FileTime1.dwLowDateTime], 0
0x180029266  lea     rdx, [rsp+88h+FileTime1]
0x18002926e  lea     rcx, [rsp+88h+var_50]
0x180029273  call    ?DeserializeFileTime@@YAHAEBV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@AEAU_FILETIME@@@Z; DeserializeFileTime(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> const &,_FILETIME &)
0x180029278  test    eax, eax
0x18002927a  jz      short loc_1800292A6
0x18002927c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029283  cmp     rcx, r14
0x180029286  jz      loc_180029313
0x18002928c  mov     edx, 0Fh
0x180029291  mov     r9d, eax
0x180029294  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x18002929b  mov     rcx, [rcx+10h]
0x18002929f  call    WPP_SF_d
0x1800292a4  jmp     short loc_180029313
0x1800292a6  lea     rdx, [rsp+88h+SystemTimeAsFileTime]; lpFileTime2
0x1800292ae  lea     rcx, [rsp+88h+FileTime1]; lpFileTime1
0x1800292b6  call    cs:__imp_CompareFileTime
0x1800292bd  nop     dword ptr [rax+rax+00h]
0x1800292c2  test    eax, eax
0x1800292c4  jns     short loc_1800292F2
0x1800292c6  mov     rax, qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime]
0x1800292ce  mov     rcx, qword ptr [rsp+88h+FileTime1.dwLowDateTime]
0x1800292d6  sub     rax, rcx
0x1800292d9  mov     rdx, 165A0BC00h
0x1800292e3  cmp     rax, rdx
0x1800292e6  jnb     short loc_180029313
0x1800292e8  mov     qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1800292f0  jmp     short loc_180029313
0x1800292f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292f9  cmp     rcx, r14
0x1800292fc  jz      short loc_180029313
0x1800292fe  mov     edx, 10h
0x180029303  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x18002930a  mov     rcx, [rcx+10h]
0x18002930e  call    WPP_SF_
0x180029313  lea     rcx, [rsp+88h+var_50]
0x180029318  call    ??1?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x18002931d  xorps   xmm0, xmm0
0x180029320  movdqu  xmmword ptr [rsp+88h+lpData], xmm0
0x180029326  mov     [rsp+88h+var_28], 0
0x18002932f  lea     rax, [rsp+88h+SystemTimeAsFileTime]
0x180029337  mov     [rsp+88h+var_50], rax
0x18002933c  lea     rax, [rsp+88h+FileTime1]
0x180029344  mov     qword ptr [rsp+88h+FileTime1.dwLowDateTime], rax
0x18002934c  lea     r9, [rsp+88h+FileTime1]
0x180029354  lea     r8, [rsp+88h+var_50]
0x180029359  mov     edx, 8
0x18002935e  lea     rcx, [rsp+88h+lpData]
0x180029363  call    ??$_Construct_n@PEAEPEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K$$QEAPEAE1@Z; std::vector<uchar>::_Construct_n<uchar *,uchar *>(unsigned __int64,uchar * &&,uchar * &&)
0x180029368  nop
0x180029369  lea     rcx, [rsp+88h+hKey]
0x18002936e  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEBGW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,ushort const *,wil::reg::key_access)
0x180029373  nop
0x180029374  mov     rdx, [rsp+88h+lpData]
0x180029379  mov     eax, dword ptr [rsp+88h+lpData+8]
0x18002937d  sub     eax, edx
0x18002937f  mov     [rsp+88h+cbData], eax; cbData
0x180029383  mov     [rsp+88h+phkResult], rdx; int
0x180029388  mov     r9d, 3; dwType
0x18002938e  mov     r8, rdi; lpValueName
0x180029391  xor     edx, edx; lpSubKey
0x180029393  mov     rcx, [rsp+88h+hKey]; hKey
0x180029398  call    cs:__imp_RegSetKeyValueW
0x18002939f  nop     dword ptr [rax+rax+00h]
0x1800293a4  test    eax, eax
0x1800293a6  jle     short loc_1800293B0
0x1800293a8  movzx   eax, ax
0x1800293ab  or      eax, 80070000h
0x1800293b0  mov     rcx, [rsp+88h]; this
0x1800293b8  test    eax, eax
0x1800293ba  jns     short loc_1800293D1
0x1800293bc  mov     r9d, eax; char *
0x1800293bf  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800293c6  mov     edx, 1CBEh; void *
0x1800293cb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800293d1  lea     rcx, [rsp+88h+hKey]
0x1800293d6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800293db  nop
0x1800293dc  lea     rcx, [rsp+88h+lpData]
0x1800293e1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800293e6  nop
0x1800293e7  lea     rcx, [rsp+88h+arg_18]
0x1800293ef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800293f4  nop
0x1800293f5  jmp     short $+2
0x1800293f7  add     rsp, 70h
0x1800293fb  pop     r14
0x1800293fd  pop     rdi
0x1800293fe  pop     rbx
0x1800293ff  retn
```
