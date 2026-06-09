# RasEapSetTimeStampWchar

- ea: `0x1800275d0`
- end: `0x180027838`
- name: `RasEapSetTimeStampWchar`
- size: `616`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026d90`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000f350`
- `0x1800275d0`
- `0x180027840`
- `0x180029424`
- `0x180029474`
- `0x18003cf0c`
- `0x1800610d0`
- `0x180062634`
- `0x180062908`
- `0x180062cb4`
- `0x1800632f4`
- `0x1800635f0`
- `0x1800636c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002765d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002765d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002761b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002761b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800276fa`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800276fa`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800277d6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800277d6`

## string_xrefs

- `0x18002764f`: `SYSTEM\CurrentControlSet\Services\RasMan\Deleted-Profiles\`
- `0x1800277f7`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

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
0x1800275d0  push    rbx
0x1800275d2  push    rdi
0x1800275d3  push    r14
0x1800275d5  sub     rsp, 70h
0x1800275d9  mov     rdi, rcx
0x1800275dc  lea     r14, WPP_GLOBAL_Control
0x1800275e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275ea  cmp     rcx, r14
0x1800275ed  jz      short loc_180027607
0x1800275ef  mov     edx, 0Eh
0x1800275f4  mov     r9, rdi
0x1800275f7  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x1800275fe  mov     rcx, [rcx+10h]
0x180027602  call    WPP_SF_S
0x180027607  mov     qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180027613  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002761b  call    cs:__imp_GetSystemTimeAsFileTime
0x180027621  mov     [rsp+88h+arg_18], 0
0x18002762d  lea     rcx, [rsp+88h+arg_18]
0x180027635  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18002763a  mov     rbx, rax
0x18002763d  xor     ecx, ecx
0x18002763f  call    ?get_access_flags@reg_view_details@reg@wil@@YAKW4key_access@23@@Z; wil::reg::reg_view_details::get_access_flags(wil::reg::key_access)
0x180027644  mov     [rsp+88h+phkResult], rbx; phkResult
0x180027649  mov     r9d, eax; samDesired
0x18002764c  xor     r8d, r8d; ulOptions
0x18002764f  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180027656  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002765d  call    cs:__imp_RegOpenKeyExW
0x180027663  test    eax, eax
0x180027665  jle     short loc_180027671
0x180027667  movzx   eax, ax
0x18002766a  or      eax, 80070000h
0x18002766f  test    eax, eax
0x180027671  js      loc_18002775B
0x180027677  lea     rcx, [rsp+88h+var_50]
0x18002767c  call    ??0?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x180027681  lea     r9, [rsp+88h+var_50]
0x180027686  mov     rdx, rdi
0x180027689  mov     rcx, [rsp+88h+arg_18]
0x180027691  call    ?get_value_binary_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGIAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@2@@Z; wil::reg::get_value_binary_nothrow(HKEY__ *,ushort const *,uint,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)
0x180027696  test    eax, eax
0x180027698  js      loc_180027751
0x18002769e  mov     qword ptr [rsp+88h+FileTime1.dwLowDateTime], 0
0x1800276aa  lea     rdx, [rsp+88h+FileTime1]
0x1800276b2  lea     rcx, [rsp+88h+var_50]
0x1800276b7  call    ?DeserializeFileTime@@YAHAEBV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@AEAU_FILETIME@@@Z; DeserializeFileTime(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> const &,_FILETIME &)
0x1800276bc  test    eax, eax
0x1800276be  jz      short loc_1800276EA
0x1800276c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276c7  cmp     rcx, r14
0x1800276ca  jz      loc_180027751
0x1800276d0  mov     edx, 0Fh
0x1800276d5  mov     r9d, eax
0x1800276d8  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x1800276df  mov     rcx, [rcx+10h]
0x1800276e3  call    WPP_SF_d
0x1800276e8  jmp     short loc_180027751
0x1800276ea  lea     rdx, [rsp+88h+SystemTimeAsFileTime]; lpFileTime2
0x1800276f2  lea     rcx, [rsp+88h+FileTime1]; lpFileTime1
0x1800276fa  call    cs:__imp_CompareFileTime
0x180027700  test    eax, eax
0x180027702  jns     short loc_180027730
0x180027704  mov     rax, qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime]
0x18002770c  mov     rcx, qword ptr [rsp+88h+FileTime1.dwLowDateTime]
0x180027714  sub     rax, rcx
0x180027717  mov     rdx, 165A0BC00h
0x180027721  cmp     rax, rdx
0x180027724  jnb     short loc_180027751
0x180027726  mov     qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18002772e  jmp     short loc_180027751
0x180027730  mov     rcx, cs:WPP_GLOBAL_Control
0x180027737  cmp     rcx, r14
0x18002773a  jz      short loc_180027751
0x18002773c  mov     edx, 10h
0x180027741  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x180027748  mov     rcx, [rcx+10h]
0x18002774c  call    WPP_SF_
0x180027751  lea     rcx, [rsp+88h+var_50]
0x180027756  call    ??1?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x18002775b  xorps   xmm0, xmm0
0x18002775e  movdqu  xmmword ptr [rsp+88h+lpData], xmm0
0x180027764  mov     [rsp+88h+var_28], 0
0x18002776d  lea     rax, [rsp+88h+SystemTimeAsFileTime]
0x180027775  mov     [rsp+88h+var_50], rax
0x18002777a  lea     rax, [rsp+88h+FileTime1]
0x180027782  mov     qword ptr [rsp+88h+FileTime1.dwLowDateTime], rax
0x18002778a  lea     r9, [rsp+88h+FileTime1]
0x180027792  lea     r8, [rsp+88h+var_50]
0x180027797  mov     edx, 8
0x18002779c  lea     rcx, [rsp+88h+lpData]
0x1800277a1  call    ??$_Construct_n@PEAEPEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K$$QEAPEAE1@Z; std::vector<uchar>::_Construct_n<uchar *,uchar *>(unsigned __int64,uchar * &&,uchar * &&)
0x1800277a6  nop
0x1800277a7  lea     rcx, [rsp+88h+hKey]
0x1800277ac  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEBGW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,ushort const *,wil::reg::key_access)
0x1800277b1  nop
0x1800277b2  mov     rdx, [rsp+88h+lpData]
0x1800277b7  mov     eax, dword ptr [rsp+88h+lpData+8]
0x1800277bb  sub     eax, edx
0x1800277bd  mov     [rsp+88h+cbData], eax; cbData
0x1800277c1  mov     [rsp+88h+phkResult], rdx; int
0x1800277c6  mov     r9d, 3; dwType
0x1800277cc  mov     r8, rdi; lpValueName
0x1800277cf  xor     edx, edx; lpSubKey
0x1800277d1  mov     rcx, [rsp+88h+hKey]; hKey
0x1800277d6  call    cs:__imp_RegSetKeyValueW
0x1800277dc  test    eax, eax
0x1800277de  jle     short loc_1800277E8
0x1800277e0  movzx   eax, ax
0x1800277e3  or      eax, 80070000h
0x1800277e8  mov     rcx, [rsp+88h]; this
0x1800277f0  test    eax, eax
0x1800277f2  jns     short loc_180027809
0x1800277f4  mov     r9d, eax; char *
0x1800277f7  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800277fe  mov     edx, 1CBEh; void *
0x180027803  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180027809  lea     rcx, [rsp+88h+hKey]
0x18002780e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180027813  nop
0x180027814  lea     rcx, [rsp+88h+lpData]
0x180027819  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002781e  nop
0x18002781f  lea     rcx, [rsp+88h+arg_18]
0x180027827  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002782c  nop
0x18002782d  jmp     short $+2
0x18002782f  add     rsp, 70h
0x180027833  pop     r14
0x180027835  pop     rdi
0x180027836  pop     rbx
0x180027837  retn
```
