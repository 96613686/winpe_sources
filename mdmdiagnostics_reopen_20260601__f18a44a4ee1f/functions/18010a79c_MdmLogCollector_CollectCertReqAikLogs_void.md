# MdmLogCollector::CollectCertReqAikLogs(void)

- ea: `0x18010a79c`
- end: `0x18010a945`
- name: `?CollectCertReqAikLogs@MdmLogCollector@@AEAAJXZ`
- size: `425`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18010ba4c`

## callees

- `0x180019080`
- `0x18001a130`
- `0x1800e6838`
- `0x1800e688c`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x18010611c`
- `0x180109198`
- `0x18010a79c`
- `0x180110d34`
- `0x18011153c`
- `0x1801119fc`
- `0x18011224c`

## string_xrefs

- `0x18010a7e4`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a83d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a89e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a883`: `"%s" -enrollaik -config "" -q`
- `0x18010a824`: `%WINDIR%\System32\certreq.exe`
- `0x18010a8bd`: `Collecting TPM AIK configuration information.  This may take up to two minutes...\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MdmLogCollector::CollectCertReqAikLogs(MdmLogCollector *this)
{
  __int64 v2; // rcx
  int TemporaryOutputPath; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // eax
  __int64 v7; // rdx
  const unsigned __int16 *v8; // rax
  unsigned int v10; // [rsp+20h] [rbp-29h]
  __int64 v11; // [rsp+30h] [rbp-19h] BYREF
  unsigned __int16 *v12[3]; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v13[32]; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v14[32]; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  std::wstring::wstring(v14);
  TemporaryOutputPath = MdmLogCollector::GetTemporaryOutputPath(v2, (__int64)v14);
  v4 = TemporaryOutputPath;
  if ( TemporaryOutputPath >= 0 )
  {
    std::wstring::wstring(v13, v14);
    std::wstring::append(v13, L"\\CertReq_enrollaik_Output.txt");
    v11 = 0;
    v5 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
           L"%WINDIR%\\System32\\certreq.exe",
           &v11);
    v4 = v5;
    if ( v5 >= 0 )
    {
      memset(v12, 0, sizeof(v12));
      v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
             v12,
             L"\"%s\" -enrollaik -config \"\" -q",
             v11);
      v4 = v6;
      if ( v6 >= 0 )
      {
        wprintf(L"Collecting TPM AIK configuration information.  This may take up to two minutes...\n");
        v8 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
        v6 = MdmLogCollector::RunDynamicApp(this, v12[0], v8, 0, 0x1D4C0u);
        v4 = v6;
        if ( v6 >= 0 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v12);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
          std::wstring::_Tidy_deallocate(v13);
          v4 = 0;
          goto LABEL_12;
        }
        v7 = 1856;
      }
      else
      {
        v7 = 1853;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)v6,
        v10);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v12);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x738,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)v5,
        v10);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
    std::wstring::_Tidy_deallocate(v13);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x732,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)TemporaryOutputPath,
      v10);
  }
LABEL_12:
  std::wstring::_Tidy_deallocate(v14);
  return v4;
}

```

## disassembly

```asm
0x18010a79c  mov     [rsp-8+arg_8], rbx
0x18010a7a1  mov     [rsp-8+arg_10], rdi
0x18010a7a6  push    rbp
0x18010a7a7  lea     rbp, [rsp-57h]
0x18010a7ac  sub     rsp, 0A0h
0x18010a7b3  mov     rax, cs:__security_cookie
0x18010a7ba  xor     rax, rsp
0x18010a7bd  mov     [rbp+57h+var_10], rax
0x18010a7c1  mov     rdi, rcx
0x18010a7c4  lea     rcx, [rbp+57h+var_30]
0x18010a7c8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010a7cd  nop
0x18010a7ce  lea     rdx, [rbp+57h+var_30]
0x18010a7d2  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x18010a7d7  mov     ebx, eax
0x18010a7d9  test    eax, eax
0x18010a7db  jns     short loc_18010A7FA
0x18010a7dd  mov     rcx, [rbp+5Fh]; this
0x18010a7e1  mov     r9d, eax; char *
0x18010a7e4  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a7eb  mov     edx, 732h; void *
0x18010a7f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a7f5  jmp     loc_18010A918
0x18010a7fa  lea     rdx, [rbp+57h+var_30]
0x18010a7fe  lea     rcx, [rbp+57h+var_50]
0x18010a802  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18010a807  nop
0x18010a808  lea     rdx, aCertreqEnrolla; "\\CertReq_enrollaik_Output.txt"
0x18010a80f  lea     rcx, [rbp+57h+var_50]
0x18010a813  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010a818  mov     [rbp+57h+var_70], 0
0x18010a820  lea     rdx, [rbp+57h+var_70]
0x18010a824  lea     rcx, aWindirSystem32_16; "%WINDIR%\\System32\\certreq.exe"
0x18010a82b  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18010a830  mov     ebx, eax
0x18010a832  test    eax, eax
0x18010a834  jns     short loc_18010A867
0x18010a836  mov     rcx, [rbp+5Fh]; this
0x18010a83a  mov     r9d, eax; char *
0x18010a83d  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a844  mov     edx, 738h; void *
0x18010a849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a84e  nop
0x18010a84f  lea     rcx, [rbp+57h+var_70]
0x18010a853  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010a858  nop
0x18010a859  lea     rcx, [rbp+57h+var_50]
0x18010a85d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010a862  jmp     loc_18010A918
0x18010a867  mov     [rbp+57h+var_68], 0
0x18010a86f  mov     [rbp+57h+var_60], 0
0x18010a877  mov     [rbp+57h+var_58], 0
0x18010a87f  mov     r8, [rbp+57h+var_70]
0x18010a883  lea     rdx, aSEnrollaikConf; "\"%s\" -enrollaik -config \"\" -q"
0x18010a88a  lea     rcx, [rbp+57h+var_68]
0x18010a88e  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18010a893  mov     ebx, eax
0x18010a895  test    eax, eax
0x18010a897  jns     short loc_18010A8BD
0x18010a899  mov     edx, 73Dh; void *
0x18010a89e  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a8a5  mov     r9d, eax; char *
0x18010a8a8  mov     rcx, [rbp+5Fh]; this
0x18010a8ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a8b1  nop
0x18010a8b2  lea     rcx, [rbp+57h+var_68]
0x18010a8b6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18010a8bb  jmp     short loc_18010A84F
0x18010a8bd  lea     rcx, aCollectingTpmA; "Collecting TPM AIK configuration inform"...
0x18010a8c4  call    wprintf
0x18010a8c9  lea     rcx, [rbp+57h+var_50]
0x18010a8cd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010a8d2  mov     r8, rax; unsigned __int16 *
0x18010a8d5  mov     [rsp+0A0h+var_80], 1D4C0h; unsigned int
0x18010a8dd  xor     r9d, r9d; unsigned __int16 *
0x18010a8e0  mov     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x18010a8e4  mov     rcx, rdi; this
0x18010a8e7  call    ?RunDynamicApp@MdmLogCollector@@AEAAJPEAGPEBG1K@Z; MdmLogCollector::RunDynamicApp(ushort *,ushort const *,ushort const *,ulong)
0x18010a8ec  mov     ebx, eax
0x18010a8ee  test    eax, eax
0x18010a8f0  jns     short loc_18010A8F9
0x18010a8f2  mov     edx, 740h
0x18010a8f7  jmp     short loc_18010A89E
0x18010a8f9  lea     rcx, [rbp+57h+var_68]
0x18010a8fd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18010a902  nop
0x18010a903  lea     rcx, [rbp+57h+var_70]
0x18010a907  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010a90c  nop
0x18010a90d  lea     rcx, [rbp+57h+var_50]
0x18010a911  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010a916  xor     ebx, ebx
0x18010a918  lea     rcx, [rbp+57h+var_30]
0x18010a91c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010a921  mov     eax, ebx
0x18010a923  mov     rcx, [rbp+57h+var_10]
0x18010a927  xor     rcx, rsp; StackCookie
0x18010a92a  call    __security_check_cookie
0x18010a92f  lea     r11, [rsp+0A0h+var_s0]
0x18010a937  mov     rbx, [r11+18h]
0x18010a93b  mov     rdi, [r11+20h]
0x18010a93f  mov     rsp, r11
0x18010a942  pop     rbp
0x18010a943  retn
```
