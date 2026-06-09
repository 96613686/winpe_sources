# LpacRegHelper::GetLpacSecurityCapabilities(void *,ushort const *,ushort const *,void *,std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>> &,std::vector<_SID_AND_ATTRIBUTES,std::allocator<_SID_AND_ATTRIBUTES>> &)

- ea: `0x180020ab0`
- end: `0x180020f67`
- name: `?GetLpacSecurityCapabilities@LpacRegHelper@@CAJPEAXPEBG10AEAV?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAV?$vector@U_SID_AND_ATTRIBUTES@@V?$allocator@U_SID_AND_ATTRIBUTES@@@std@@@3@@Z`
- size: `1207`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180020664`

## callees

- `0x180004594`
- `0x18000a4d8`
- `0x18000a740`
- `0x18000c7d4`
- `0x18000f5b0`
- `0x180016ddc`
- `0x18001e2b8`
- `0x18001e80c`
- `0x18001ee58`
- `0x18001f0c4`
- `0x18001f12c`
- `0x18001f214`
- `0x180020ab0`
- `0x180020f70`
- `0x18002150c`
- `0x180021564`
- `0x180021b7c`
- `0x180021f70`
- `0x1800227f2`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020d5c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020d5c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180020ccc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180020ccc`

## string_xrefs

- `0x180020f1c`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x180020b00`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x180020b83`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x180020d86`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LpacRegHelper::GetLpacSecurityCapabilities(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 v8; // rdx
  void *v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rax
  unsigned int v14; // ecx
  __int64 v15; // rdx
  const WCHAR *v16; // rcx
  const WCHAR *v17; // r8
  LSTATUS ValueW; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  const char *v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rdx
  int v24; // eax
  unsigned int v25; // r8d
  __int64 v26; // rdx
  int pdwType; // [rsp+20h] [rbp-1F8h]
  HKEY *pdwTypeb; // [rsp+20h] [rbp-1F8h]
  int pdwTypea; // [rsp+20h] [rbp-1F8h]
  PSID Sid; // [rsp+40h] [rbp-1D8h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-1D0h] BYREF
  int pvData; // [rsp+50h] [rbp-1C8h] BYREF
  HKEY hkey[2]; // [rsp+58h] [rbp-1C0h] BYREF
  int v34; // [rsp+68h] [rbp-1B0h]
  int v35; // [rsp+6Ch] [rbp-1ACh]
  _WORD v36[8]; // [rsp+70h] [rbp-1A8h] BYREF
  __int64 v37; // [rsp+80h] [rbp-198h]
  __int64 v38; // [rsp+88h] [rbp-190h]
  int v39; // [rsp+90h] [rbp-188h]
  __int64 v40; // [rsp+98h] [rbp-180h]
  int v41; // [rsp+A0h] [rbp-178h]
  __int64 v42; // [rsp+A8h] [rbp-170h]
  _BYTE v43[64]; // [rsp+B0h] [rbp-168h] BYREF
  LPCWSTR StringSid[3]; // [rsp+F0h] [rbp-128h] BYREF
  unsigned __int64 v45; // [rsp+108h] [rbp-110h]
  int v46; // [rsp+110h] [rbp-108h]
  __int64 v47; // [rsp+118h] [rbp-100h]
  unsigned int v48; // [rsp+120h] [rbp-F8h]
  _BYTE v49[40]; // [rsp+130h] [rbp-E8h] BYREF
  __int64 v50; // [rsp+158h] [rbp-C0h]
  __int64 v51; // [rsp+160h] [rbp-B8h]
  _BYTE v52[64]; // [rsp+170h] [rbp-A8h] BYREF
  _BYTE v53[64]; // [rsp+1B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  if ( !a2 )
  {
    v8 = 606;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)0x80070057LL,
      pdwType);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v8 = 607;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v8 = 608;
    goto LABEL_3;
  }
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Destroy(
    a1,
    *a5,
    a5[1]);
  a5[1] = *a5;
  a6[1] = *a6;
  hkey[0] = 0;
  pdwTypeb = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hkey);
  v11 = LpacRegHelper::OpenLpacRegistrySubKey(v10, a2, a3, L"\\LpacCapabilities", pdwTypeb);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26F,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)v11,
      pdwTypea);
    goto LABEL_30;
  }
  Sid = v36;
  memset_0(v36, 0, 0x40u);
  v38 = 7;
  v37 = 0;
  v36[0] = 0;
  v39 = 0;
  v40 = 0;
  v41 = -1;
  v42 = 0;
  v13 = wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>::iterator_t<wil::reg::value_iterator_data<std::wstring>>(
          v43,
          hkey[0]);
  wil::make_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>(v52, v13, v36);
  wil::reg::value_iterator_data<std::wstring>::value_iterator_data<std::wstring>(StringSid, v52);
  wil::reg::value_iterator_data<std::wstring>::value_iterator_data<std::wstring>(v49, v53);
  while ( 1 )
  {
    v14 = v48;
    v15 = v51;
    if ( (v48 == -1 || (_DWORD)v51 == -1 || v47 == v50) && v48 == (_DWORD)v51 )
      break;
    if ( v48 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x6FF,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
        (const char *)retaddr);
    if ( v46 == 4 )
    {
      Sid = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &Sid,
        0);
      v16 = (const WCHAR *)StringSid;
      if ( v45 >= 8 )
        v16 = StringSid[0];
      if ( ConvertStringSidToSidW(v16, &Sid) )
      {
        pvData = 0;
        v17 = (const WCHAR *)StringSid;
        if ( v45 >= 8 )
          v17 = StringSid[0];
        pcbData = 4;
        ValueW = RegGetValueW(hkey[0], 0, v17, 0x10u, 0, &pvData, &pcbData);
        v12 = ValueW;
        if ( ValueW > 0 )
          v12 = (unsigned __int16)ValueW | 0x80070000;
        if ( (v12 & 0x80000000) != 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x281,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
            (const char *)v12,
            pdwTypea);
          wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&Sid);
          LOBYTE(v19) = 1;
          std::wstring::_Tidy(v49, v19, 0);
          LOBYTE(v20) = 1;
          std::wstring::_Tidy(StringSid, v20, 0);
          wil::details::pointer_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>::~pointer_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>(v52);
          goto LABEL_30;
        }
        hkey[1] = (HKEY)Sid;
        v34 = pvData;
        v35 = 0;
        try
        {
          std::vector<_SID_AND_ATTRIBUTES>::push_back();
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::push_back(
            a5,
            &Sid);
        }
        catch ( ... )
        {
          pcbData = wil::details::in1diag3::Return_CaughtException(
                      retaddr,
                      (void *)0x286,
                      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
                      v21);
          wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&Sid);
          LOBYTE(v22) = 1;
          std::wstring::_Tidy(v49, v22, 0);
          LOBYTE(v23) = 1;
          std::wstring::_Tidy(StringSid, v23, 0);
          wil::details::pointer_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>::~pointer_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>(v52);
          v12 = pcbData;
LABEL_30:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
          return v12;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&Sid);
      v14 = v48;
    }
    if ( v14 + 1 < v14 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x72C,
        (unsigned int)retaddr,
        (const char *)0x80070057LL,
        pdwTypea);
    if ( v14 == -2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x72D,
        (unsigned int)retaddr,
        (const char *)0x80070057LL,
        pdwTypea);
    v48 = v14 + 1;
    v24 = wil::reg::value_iterator_data<std::wstring>::enumerate_current_index((LPWSTR)StringSid);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x733, v25, (const char *)(unsigned int)v24, pdwTypea);
  }
  LOBYTE(v15) = 1;
  std::wstring::_Tidy(v49, v15, 0);
  LOBYTE(v26) = 1;
  std::wstring::_Tidy(StringSid, v26, 0);
  wil::details::pointer_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>::~pointer_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>(v52);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
  return 0;
}

```

## disassembly

```asm
0x180020ab0  mov     [rsp+arg_0], rbx
0x180020ab5  push    rsi
0x180020ab6  push    rdi
0x180020ab7  push    r14
0x180020ab9  sub     rsp, 200h
0x180020ac0  mov     rax, cs:__security_cookie
0x180020ac7  xor     rax, rsp
0x180020aca  mov     [rsp+218h+var_28], rax
0x180020ad2  mov     rbx, r8
0x180020ad5  mov     rsi, rdx
0x180020ad8  mov     rdi, [rsp+218h+arg_20]
0x180020ae0  mov     r14, [rsp+218h+arg_28]
0x180020ae8  test    rdx, rdx
0x180020aeb  jnz     short loc_180020B16
0x180020aed  mov     edx, 25Eh; void *
0x180020af2  mov     rcx, [rsp+218h]; this
0x180020afa  mov     r9d, 80070057h; char *
0x180020b00  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020b07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b0c  mov     eax, 80070057h
0x180020b11  jmp     loc_180020EF7
0x180020b16  test    rbx, rbx
0x180020b19  jnz     short loc_180020B22
0x180020b1b  mov     edx, 25Fh
0x180020b20  jmp     short loc_180020AF2
0x180020b22  test    r9, r9
0x180020b25  jnz     short loc_180020B2E
0x180020b27  mov     edx, 260h
0x180020b2c  jmp     short loc_180020AF2
0x180020b2e  mov     r8, [rdi+8]
0x180020b32  mov     rdx, [rdi]
0x180020b35  call    ?_Destroy@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@IEAAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@0@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Destroy(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> *)
0x180020b3a  mov     rax, [rdi]
0x180020b3d  mov     [rdi+8], rax
0x180020b41  mov     rax, [r14]
0x180020b44  mov     [r14+8], rax
0x180020b48  mov     [rsp+218h+hkey], 0
0x180020b51  lea     rcx, [rsp+218h+hkey]
0x180020b56  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180020b5b  mov     [rsp+218h+pdwType], rax; int
0x180020b60  lea     r9, aLpaccapabiliti; "\\LpacCapabilities"
0x180020b67  mov     r8, rbx; unsigned __int16 *
0x180020b6a  mov     rdx, rsi; unsigned __int16 *
0x180020b6d  call    ?OpenLpacRegistrySubKey@LpacRegHelper@@CAJPEAXPEBG11PEAPEAUHKEY__@@@Z; LpacRegHelper::OpenLpacRegistrySubKey(void *,ushort const *,ushort const *,ushort const *,HKEY__ * *)
0x180020b72  mov     ebx, eax
0x180020b74  test    eax, eax
0x180020b76  jns     short loc_180020B99
0x180020b78  mov     rcx, [rsp+218h]; this
0x180020b80  mov     r9d, eax; char *
0x180020b83  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020b8a  mov     edx, 26Fh; void *
0x180020b8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b94  jmp     loc_180020E52
0x180020b99  lea     rax, [rsp+218h+var_1A8]
0x180020b9e  mov     [rsp+218h+Sid], rax
0x180020ba3  xor     edx, edx; Val
0x180020ba5  lea     r8d, [rdx+40h]; Size
0x180020ba9  lea     rcx, [rsp+218h+var_1A8]; void *
0x180020bae  call    memset_0
0x180020bb3  mov     [rsp+218h+var_190], 7
0x180020bbf  mov     [rsp+218h+var_198], 0
0x180020bcb  xor     eax, eax
0x180020bcd  mov     [rsp+218h+var_1A8], ax
0x180020bd2  mov     [rsp+218h+var_188], eax
0x180020bd9  mov     [rsp+218h+var_180], rax
0x180020be1  or      esi, 0FFFFFFFFh
0x180020be4  mov     [rsp+218h+var_178], esi
0x180020beb  mov     [rsp+218h+var_170], rax
0x180020bf3  mov     rdx, [rsp+218h+hkey]
0x180020bf8  lea     rcx, [rsp+218h+var_168]
0x180020c00  call    ??0?$iterator_t@V?$value_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@wil@@QEAA@PEAUHKEY__@@@Z; wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>::iterator_t<wil::reg::value_iterator_data<std::wstring>>(HKEY__ *)
0x180020c05  nop
0x180020c06  lea     r8, [rsp+218h+var_1A8]
0x180020c0b  mov     rdx, rax
0x180020c0e  lea     rcx, [rsp+218h+var_A8]
0x180020c16  call    ??$make_range@V?$iterator_t@V?$value_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@wil@@@wil@@YA?AV?$pointer_range@V?$iterator_t@V?$value_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@wil@@@details@0@V?$iterator_t@V?$value_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@0@0@Z; wil::make_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>(wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>,wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>)
0x180020c1b  nop
0x180020c1c  lea     rdx, [rsp+218h+var_A8]
0x180020c24  lea     rcx, [rsp+218h+StringSid]
0x180020c2c  call    ??0?$value_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@QEAA@AEBV012@@Z; wil::reg::value_iterator_data<std::wstring>::value_iterator_data<std::wstring>(wil::reg::value_iterator_data<std::wstring> const &)
0x180020c31  nop
0x180020c32  lea     rdx, [rsp+218h+var_68]
0x180020c3a  lea     rcx, [rsp+218h+var_E8]
0x180020c42  call    ??0?$value_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@QEAA@AEBV012@@Z; wil::reg::value_iterator_data<std::wstring>::value_iterator_data<std::wstring>(wil::reg::value_iterator_data<std::wstring> const &)
0x180020c47  nop
0x180020c48  mov     ecx, [rsp+218h+var_F8]
0x180020c4f  mov     rdx, [rsp+218h+var_B8]
0x180020c57  cmp     ecx, esi
0x180020c59  jz      short loc_180020C71
0x180020c5b  cmp     edx, esi
0x180020c5d  jz      short loc_180020C71
0x180020c5f  mov     rax, [rsp+218h+var_C0]
0x180020c67  cmp     [rsp+218h+var_100], rax
0x180020c6f  jnz     short loc_180020C79
0x180020c71  cmp     ecx, edx
0x180020c73  jz      loc_180020EB1
0x180020c79  cmp     ecx, esi
0x180020c7b  setz    al
0x180020c7e  mov     r9, [rsp+218h]; char *
0x180020c86  test    al, al
0x180020c88  jnz     loc_180020F1C
0x180020c8e  cmp     [rsp+218h+var_108], 4
0x180020c96  jnz     short loc_180020CED
0x180020c98  mov     [rsp+218h+Sid], 0
0x180020ca1  xor     edx, edx
0x180020ca3  lea     rcx, [rsp+218h+Sid]
0x180020ca8  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180020cad  lea     rcx, [rsp+218h+StringSid]
0x180020cb5  cmp     [rsp+218h+var_110], 8
0x180020cbe  cmovnb  rcx, [rsp+218h+StringSid]; StringSid
0x180020cc7  lea     rdx, [rsp+218h+Sid]; Sid
0x180020ccc  call    cs:__imp_ConvertStringSidToSidW
0x180020cd3  nop     dword ptr [rax+rax+00h]
0x180020cd8  test    eax, eax
0x180020cda  jnz     short loc_180020D0A
0x180020cdc  lea     rcx, [rsp+218h+Sid]
0x180020ce1  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x180020ce6  mov     ecx, [rsp+218h+var_F8]
0x180020ced  lea     edx, [rcx+1]
0x180020cf0  cmp     edx, ecx
0x180020cf2  setb    al
0x180020cf5  mov     r8, [rsp+218h]; unsigned int
0x180020cfd  test    al, al
0x180020cff  jnz     loc_180020F31
0x180020d05  jmp     loc_180020E63
0x180020d0a  mov     [rsp+218h+var_1C8], 0
0x180020d12  lea     r8, [rsp+218h+StringSid]
0x180020d1a  cmp     [rsp+218h+var_110], 8
0x180020d23  cmovnb  r8, [rsp+218h+StringSid]; lpValue
0x180020d2c  mov     [rsp+218h+var_1D0], 4
0x180020d34  lea     rax, [rsp+218h+var_1D0]
0x180020d39  mov     [rsp+218h+pcbData], rax; pcbData
0x180020d3e  lea     rax, [rsp+218h+var_1C8]
0x180020d43  mov     [rsp+218h+pvData], rax; pvData
0x180020d48  mov     [rsp+218h+pdwType], 0; int
0x180020d51  xor     edx, edx; lpSubKey
0x180020d53  lea     r9d, [rdx+10h]; dwFlags
0x180020d57  mov     rcx, [rsp+218h+hkey]; hkey
0x180020d5c  call    cs:__imp_RegGetValueW
0x180020d63  nop     dword ptr [rax+rax+00h]
0x180020d68  mov     ebx, eax
0x180020d6a  test    eax, eax
0x180020d6c  jle     short loc_180020D77
0x180020d6e  movzx   ebx, ax
0x180020d71  or      ebx, 80070000h
0x180020d77  test    ebx, ebx
0x180020d79  jns     short loc_180020DD8
0x180020d7b  mov     rcx, [rsp+218h]; this
0x180020d83  mov     r9d, ebx; char *
0x180020d86  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020d8d  mov     edx, 281h; void *
0x180020d92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d97  nop
0x180020d98  lea     rcx, [rsp+218h+Sid]
0x180020d9d  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x180020da2  nop
0x180020da3  xor     r8d, r8d
0x180020da6  mov     dl, 1
0x180020da8  lea     rcx, [rsp+218h+var_E8]
0x180020db0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180020db5  nop
0x180020db6  xor     r8d, r8d
0x180020db9  mov     dl, 1
0x180020dbb  lea     rcx, [rsp+218h+StringSid]
0x180020dc3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180020dc8  nop
0x180020dc9  lea     rcx, [rsp+218h+var_A8]
0x180020dd1  call    ??1?$pointer_range@V?$iterator_t@V?$value_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@wil@@@details@wil@@QEAA@XZ; wil::details::pointer_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>::~pointer_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>(void)
0x180020dd6  jmp     short loc_180020E52
0x180020dd8  mov     rax, [rsp+218h+Sid]
0x180020ddd  mov     [rsp+218h+var_1B8], rax
0x180020de2  mov     eax, [rsp+218h+var_1C8]
0x180020de6  mov     [rsp+218h+var_1B0], eax
0x180020dea  xor     eax, eax
0x180020dec  mov     [rsp+218h+var_1AC], eax
0x180020df0  lea     rdx, [rsp+218h+var_1B8]
0x180020df5  mov     rcx, r14
0x180020df8  call    ?push_back@?$vector@U_SID_AND_ATTRIBUTES@@V?$allocator@U_SID_AND_ATTRIBUTES@@@std@@@std@@QEAAX$$QEAU_SID_AND_ATTRIBUTES@@@Z; std::vector<_SID_AND_ATTRIBUTES>::push_back(_SID_AND_ATTRIBUTES &&)
0x180020dfd  lea     rdx, [rsp+218h+Sid]
0x180020e02  mov     rcx, rdi
0x180020e05  call    ?push_back@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::push_back(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x180020e0a  nop
0x180020e0b  jmp     loc_180020CDC
0x180020e10  lea     rcx, [rsp+218h+Sid]
0x180020e15  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x180020e1a  nop
0x180020e1b  xor     r8d, r8d
0x180020e1e  mov     dl, 1
0x180020e20  lea     rcx, [rsp+218h+var_E8]
0x180020e28  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180020e2d  nop
0x180020e2e  xor     r8d, r8d
0x180020e31  mov     dl, 1
0x180020e33  lea     rcx, [rsp+218h+StringSid]
0x180020e3b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180020e40  nop
0x180020e41  lea     rcx, [rsp+218h+var_A8]
0x180020e49  call    ??1?$pointer_range@V?$iterator_t@V?$value_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@wil@@@details@wil@@QEAA@XZ; wil::details::pointer_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>::~pointer_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>(void)
0x180020e4e  mov     ebx, [rsp+218h+var_1D0]
0x180020e52  lea     rcx, [rsp+218h+hkey]
0x180020e57  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020e5c  mov     eax, ebx
0x180020e5e  jmp     loc_180020EF7
0x180020e63  mov     rax, [rsp+218h]
0x180020e6b  cmp     edx, esi
0x180020e6d  jz      loc_180020F45
0x180020e73  xor     ebx, ebx
0x180020e75  inc     ecx
0x180020e77  mov     [rsp+218h+var_F8], ecx
0x180020e7e  lea     rcx, [rsp+218h+StringSid]; lpValueName
0x180020e86  call    ?enumerate_current_index@?$value_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@AEAAJXZ; wil::reg::value_iterator_data<std::wstring>::enumerate_current_index(void)
0x180020e8b  mov     rcx, [rsp+218h]; this
0x180020e93  test    eax, eax
0x180020e95  js      loc_180020F59
0x180020e9b  inc     rbx
0x180020e9e  cmp     rbx, 1
0x180020ea2  jnb     loc_180020C48
0x180020ea8  mov     ecx, [rsp+218h+var_F8]
0x180020eaf  jmp     short loc_180020E75
0x180020eb1  xor     r8d, r8d
0x180020eb4  mov     dl, 1
0x180020eb6  lea     rcx, [rsp+218h+var_E8]
0x180020ebe  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180020ec3  nop
0x180020ec4  xor     r8d, r8d
0x180020ec7  mov     dl, 1
0x180020ec9  lea     rcx, [rsp+218h+StringSid]
0x180020ed1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180020ed6  nop
0x180020ed7  lea     rcx, [rsp+218h+var_A8]
0x180020edf  call    ??1?$pointer_range@V?$iterator_t@V?$value_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@wil@@@details@wil@@QEAA@XZ; wil::details::pointer_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>::~pointer_range<wil::reg::iterator_t<wil::reg::value_iterator_data<std::wstring>>>(void)
0x180020ee4  nop
0x180020ee5  lea     rcx, [rsp+218h+hkey]
0x180020eea  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020eef  xor     eax, eax
0x180020ef1  jmp     short loc_180020EF7
0x180020ef3  mov     eax, [rsp+218h+var_1D0]
0x180020ef7  mov     rcx, [rsp+218h+var_28]
0x180020eff  xor     rcx, rsp; StackCookie
0x180020f02  call    __security_check_cookie
0x180020f07  mov     rbx, [rsp+218h+arg_0]
0x180020f0f  add     rsp, 200h
0x180020f16  pop     r14
0x180020f18  pop     rdi
0x180020f19  pop     rsi
0x180020f1a  retn
0x180020f1c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020f23  mov     edx, 6FFh; void *
0x180020f28  mov     rcx, r9; this
0x180020f2b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180020f31  mov     edx, 72Ch; void *
0x180020f36  mov     r9d, 80070057h; char *
0x180020f3c  mov     rcx, r8; this
0x180020f3f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020f45  mov     edx, 72Dh; void *
0x180020f4a  mov     r9d, 80070057h; char *
0x180020f50  mov     rcx, rax; this
0x180020f53  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020f59  mov     r9d, eax; char *
0x180020f5c  mov     edx, 733h; void *
0x180020f61  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
