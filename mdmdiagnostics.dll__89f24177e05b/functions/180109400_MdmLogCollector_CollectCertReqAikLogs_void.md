# MdmLogCollector::CollectCertReqAikLogs(void)

- ea: `0x180109400`
- end: `0x1801095a8`
- name: `?CollectCertReqAikLogs@MdmLogCollector@@AEAAJXZ`
- size: `424`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18010a670`

## callees

- `0x180019000`
- `0x18001a0a0`
- `0x1800e6664`
- `0x1800e66b8`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x180104e60`
- `0x180107ecc`
- `0x180109400`
- `0x18010f704`
- `0x1801100e4`
- `0x180110584`
- `0x180110dd8`

## string_xrefs

- `0x180109448`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x1801094a1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109502`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x1801094e7`: `"%s" -enrollaik -config "" -q`
- `0x180109488`: `%WINDIR%\System32\certreq.exe`
- `0x180109521`: `Collecting TPM AIK configuration information.  This may take up to two minutes...\n`

## pseudocode

```c
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
  TemporaryOutputPath = MdmLogCollector::GetTemporaryOutputPath(v2, v14);
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
        v7 = 1897;
      }
      else
      {
        v7 = 1894;
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
        (void *)0x761,
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
      (void *)0x75B,
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
0x180109400  mov     [rsp-8+arg_8], rbx
0x180109405  mov     [rsp-8+arg_10], rdi
0x18010940a  push    rbp
0x18010940b  lea     rbp, [rsp-57h]
0x180109410  sub     rsp, 0A0h
0x180109417  mov     rax, cs:__security_cookie
0x18010941e  xor     rax, rsp
0x180109421  mov     [rbp+57h+var_10], rax
0x180109425  mov     rdi, rcx
0x180109428  lea     rcx, [rbp+57h+var_30]
0x18010942c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180109431  nop
0x180109432  lea     rdx, [rbp+57h+var_30]
0x180109436  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x18010943b  mov     ebx, eax
0x18010943d  test    eax, eax
0x18010943f  jns     short loc_18010945E
0x180109441  mov     rcx, [rbp+5Fh]; this
0x180109445  mov     r9d, eax; char *
0x180109448  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010944f  mov     edx, 75Bh; void *
0x180109454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109459  jmp     loc_18010957C
0x18010945e  lea     rdx, [rbp+57h+var_30]
0x180109462  lea     rcx, [rbp+57h+var_50]
0x180109466  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18010946b  nop
0x18010946c  lea     rdx, aCertreqEnrolla; "\\CertReq_enrollaik_Output.txt"
0x180109473  lea     rcx, [rbp+57h+var_50]
0x180109477  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010947c  mov     [rbp+57h+var_70], 0
0x180109484  lea     rdx, [rbp+57h+var_70]
0x180109488  lea     rcx, aWindirSystem32_16; "%WINDIR%\\System32\\certreq.exe"
0x18010948f  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180109494  mov     ebx, eax
0x180109496  test    eax, eax
0x180109498  jns     short loc_1801094CB
0x18010949a  mov     rcx, [rbp+5Fh]; this
0x18010949e  mov     r9d, eax; char *
0x1801094a1  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801094a8  mov     edx, 761h; void *
0x1801094ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801094b2  nop
0x1801094b3  lea     rcx, [rbp+57h+var_70]
0x1801094b7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801094bc  nop
0x1801094bd  lea     rcx, [rbp+57h+var_50]
0x1801094c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801094c6  jmp     loc_18010957C
0x1801094cb  mov     [rbp+57h+var_68], 0
0x1801094d3  mov     [rbp+57h+var_60], 0
0x1801094db  mov     [rbp+57h+var_58], 0
0x1801094e3  mov     r8, [rbp+57h+var_70]
0x1801094e7  lea     rdx, aSEnrollaikConf; "\"%s\" -enrollaik -config \"\" -q"
0x1801094ee  lea     rcx, [rbp+57h+var_68]
0x1801094f2  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801094f7  mov     ebx, eax
0x1801094f9  test    eax, eax
0x1801094fb  jns     short loc_180109521
0x1801094fd  mov     edx, 766h; void *
0x180109502  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109509  mov     r9d, eax; char *
0x18010950c  mov     rcx, [rbp+5Fh]; this
0x180109510  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109515  nop
0x180109516  lea     rcx, [rbp+57h+var_68]
0x18010951a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18010951f  jmp     short loc_1801094B3
0x180109521  lea     rcx, aCollectingTpmA; "Collecting TPM AIK configuration inform"...
0x180109528  call    wprintf
0x18010952d  lea     rcx, [rbp+57h+var_50]
0x180109531  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180109536  mov     r8, rax; unsigned __int16 *
0x180109539  mov     [rsp+0A0h+var_80], 1D4C0h; unsigned int
0x180109541  xor     r9d, r9d; unsigned __int16 *
0x180109544  mov     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x180109548  mov     rcx, rdi; this
0x18010954b  call    ?RunDynamicApp@MdmLogCollector@@AEAAJPEAGPEBG1K@Z; MdmLogCollector::RunDynamicApp(ushort *,ushort const *,ushort const *,ulong)
0x180109550  mov     ebx, eax
0x180109552  test    eax, eax
0x180109554  jns     short loc_18010955D
0x180109556  mov     edx, 769h
0x18010955b  jmp     short loc_180109502
0x18010955d  lea     rcx, [rbp+57h+var_68]
0x180109561  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180109566  nop
0x180109567  lea     rcx, [rbp+57h+var_70]
0x18010956b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180109570  nop
0x180109571  lea     rcx, [rbp+57h+var_50]
0x180109575  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010957a  xor     ebx, ebx
0x18010957c  lea     rcx, [rbp+57h+var_30]
0x180109580  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109585  mov     eax, ebx
0x180109587  mov     rcx, [rbp+57h+var_10]
0x18010958b  xor     rcx, rsp; StackCookie
0x18010958e  call    __security_check_cookie
0x180109593  lea     r11, [rsp+0A0h+var_s0]
0x18010959b  mov     rbx, [r11+18h]
0x18010959f  mov     rdi, [r11+20h]
0x1801095a3  mov     rsp, r11
0x1801095a6  pop     rbp
0x1801095a7  retn
```
