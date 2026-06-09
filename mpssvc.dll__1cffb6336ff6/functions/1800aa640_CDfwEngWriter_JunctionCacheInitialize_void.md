# CDfwEngWriter::JunctionCacheInitialize(void)

- ea: `0x1800aa640`
- end: `0x1800aaac9`
- name: `?JunctionCacheInitialize@CDfwEngWriter@@AEAAJXZ`
- size: `1161`
- prototype: `__int64 __fastcall(CDfwEngWriter *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800a9490`

## callees

- `0x1800093b0`
- `0x1800110d0`
- `0x1800111b0`
- `0x180012ed4`
- `0x180017110`
- `0x1800378f4`
- `0x180041e8c`
- `0x180056b9c`
- `0x18006d160`
- `0x18006f520`
- `0x1800a29f0`
- `0x1800a7868`
- `0x1800a85a0`
- `0x1800a894c`
- `0x1800aa640`
- `0x1800aac04`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800aa8e0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800aa8e0`
- `fwbase!FwRegEnumValueNameAndValueData` at `0x1800aa7cb`
- `fwbase!FwRegEnumValueNameAndValueData` at `0x1800aa7cb`
- `fwbase!FwRegQueryNumValues` at `0x1800aa71c`
- `fwbase!FwRegQueryNumValues` at `0x1800aa71c`
- `fwbase!FwRegOpenKey` at `0x1800aa6d8`
- `fwbase!FwRegOpenKey` at `0x1800aa6d8`
- `fwbase!FwFree` at `0x1800aa808`
- `fwbase!FwFree` at `0x1800aa81b`
- `fwbase!FwFree` at `0x1800aaaa7`
- `fwbase!FwFree` at `0x1800aaaba`
- `fwbase!FwFree` at `0x1800aa808`
- `fwbase!FwFree` at `0x1800aa81b`
- `fwbase!FwFree` at `0x1800aaaa7`
- `fwbase!FwFree` at `0x1800aaaba`

## string_xrefs

- `0x1800aa6ed`: `onecore\net\mpssvc\lics\fw\fw_dfwengwriter.cpp`
- `0x1800aa731`: `onecore\net\mpssvc\lics\fw\fw_dfwengwriter.cpp`
- `0x1800aa7e0`: `onecore\net\mpssvc\lics\fw\fw_dfwengwriter.cpp`
- `0x1800aa6ca`: `System\WCOSJunctions`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDfwEngWriter::JunctionCacheInitialize(CDfwEngWriter *this)
{
  int v2; // eax
  int v3; // eax
  unsigned int i; // esi
  int v5; // eax
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  __int128 *v11; // rax
  __int128 *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int lpString2; // [rsp+20h] [rbp-F8h]
  void *v19[4]; // [rsp+60h] [rbp-B8h] BYREF
  _BYTE v20[32]; // [rsp+80h] [rbp-98h] BYREF
  PCNZWCH lpString1; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v22; // [rsp+A8h] [rbp-70h] BYREF
  int v23; // [rsp+B0h] [rbp-68h] BYREF
  unsigned int v24; // [rsp+B4h] [rbp-64h] BYREF
  __int64 v25; // [rsp+B8h] [rbp-60h] BYREF
  __int128 v26; // [rsp+C0h] [rbp-58h] BYREF
  __int128 v27; // [rsp+D0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v23 = 0;
  v24 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 166, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
  v25 = 0;
  v2 = FwRegOpenKey(-2147483646, L"System\\WCOSJunctions", 131097, &v25, &v23);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xE06,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_dfwengwriter.cpp",
        (const char *)(unsigned int)v2,
        lpString2);
    if ( v23 )
    {
      v3 = FwRegQueryNumValues(v25, &v24);
      if ( v3 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xE0A,
          (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_dfwengwriter.cpp",
          (const char *)(unsigned int)v3,
          lpString2);
      for ( i = 0; ; ++i )
      {
        if ( i >= v24 )
        {
LABEL_19:
          *((_BYTE *)this + 592) = *((_QWORD *)this + 71) != *((_QWORD *)this + 72);
          goto LABEL_20;
        }
        v22 = 0;
        lpString1 = 0;
        v23 = 0;
        v5 = FwRegEnumValueNameAndValueData(v25, i, &v22, &lpString1);
        if ( v5 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xE15,
            (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_dfwengwriter.cpp",
            (const char *)(unsigned int)v5,
            (int)&v23);
        if ( !v23 )
        {
          if ( v22 )
            FwFree(v22);
          if ( lpString1 )
            FwFree(lpString1);
          goto LABEL_19;
        }
        std::wstring::wstring(&v26, lpString1);
        v10 = v27;
        if ( !(_QWORD)v27 )
          goto LABEL_27;
        v11 = &v26;
        if ( *((_QWORD *)&v27 + 1) > 7u )
          v11 = (__int128 *)v26;
        if ( *((_WORD *)v11 + v27 - 1) == 58 && CompareStringW(0x7Fu, 1u, lpString1, 12, L"\\DosDevices\\", 12) == 2 )
          break;
        v17 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          WPP_SF_SS(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            167,
            (unsigned int)WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
            v22,
            (__int64)lpString1);
        MicrosoftTelemetryAssertTriggeredNoArgs(v17, v10, v8, v9);
LABEL_43:
        std::wstring::~wstring((void **)&v26);
        if ( v22 )
          FwFree(v22);
        if ( lpString1 )
          FwFree(lpString1);
      }
      v10 = v27;
LABEL_27:
      v12 = &v26;
      if ( *((_QWORD *)&v27 + 1) > 7u )
        v12 = (__int128 *)v26;
      v13 = std::_Traits_find_last_of<std::char_traits<unsigned short>>(v12, v10, v8, L"\\", 1);
      if ( v13 != -1 )
      {
        v14 = std::wstring::substr(&v26, v19, v13 + 1);
        if ( &v26 != (__int128 *)v14 )
        {
          std::wstring::_Tidy_deallocate(&v26);
          v26 = *(_OWORD *)v14;
          v27 = *(_OWORD *)(v14 + 16);
          *(_QWORD *)(v14 + 16) = 0;
          *(_QWORD *)(v14 + 24) = 7;
          *(_WORD *)v14 = 0;
        }
        std::wstring::~wstring(v19);
      }
      std::wstring::wstring(v19, v22);
      std::wstring::wstring(v20, &v26);
      v15 = *((_QWORD *)this + 72);
      if ( v15 == *((_QWORD *)this + 73) )
      {
        std::vector<std::pair<std::wstring,std::wstring>>::_Emplace_reallocate<std::pair<std::wstring,std::wstring>>(
          (char *)this + 568,
          *((_QWORD *)this + 72),
          v19);
      }
      else
      {
        std::wstring::wstring(v15, v19);
        std::wstring::wstring(v16 + 32, v20);
        *((_QWORD *)this + 72) += 64LL;
      }
      std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v19);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_SS(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          168,
          (unsigned int)WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
          v22,
          (__int64)lpString1);
      goto LABEL_43;
    }
LABEL_20:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xE3C,
                           (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_dfwengwriter.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800aa640  mov     r11, rsp
0x1800aa643  push    rbx
0x1800aa644  push    rsi
0x1800aa645  push    rdi
0x1800aa646  push    r15
0x1800aa648  sub     rsp, 0F8h
0x1800aa64f  mov     rax, cs:__security_cookie
0x1800aa656  xor     rax, rsp
0x1800aa659  mov     [rsp+118h+var_38], rax
0x1800aa661  mov     rdi, rcx
0x1800aa664  mov     dword ptr [r11-68h], 0
0x1800aa66c  mov     dword ptr [r11-64h], 0
0x1800aa674  lea     r15, WPP_GLOBAL_Control
0x1800aa67b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa682  cmp     rcx, r15
0x1800aa685  jz      short loc_1800AA6A3
0x1800aa687  test    byte ptr [rcx+1Ch], 8
0x1800aa68b  jz      short loc_1800AA6A3
0x1800aa68d  mov     edx, 0A6h
0x1800aa692  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800aa699  mov     rcx, [rcx+10h]
0x1800aa69d  call    WPP_SF_
0x1800aa6a2  nop
0x1800aa6a3  mov     [rsp+118h+var_60], 0
0x1800aa6af  lea     rax, [rsp+118h+var_68]
0x1800aa6b7  mov     [rsp+118h+lpString2], rax; int
0x1800aa6bc  lea     r9, [rsp+118h+var_60]
0x1800aa6c4  mov     r8d, 20019h
0x1800aa6ca  lea     rdx, aSystemWcosjunc; "System\\WCOSJunctions"
0x1800aa6d1  mov     rcx, 0FFFFFFFF80000002h
0x1800aa6d8  call    cs:__imp_FwRegOpenKey
0x1800aa6de  mov     rcx, [rsp+118h]; this
0x1800aa6e6  test    eax, eax
0x1800aa6e8  jns     short loc_1800AA6FE
0x1800aa6ea  mov     r9d, eax; char *
0x1800aa6ed  lea     r8, aOnecoreNetMpss_6; "onecore\\net\\mpssvc\\lics\\fw\\fw_dfwe"...
0x1800aa6f4  mov     edx, 0E06h; void *
0x1800aa6f9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800aa6fe  cmp     [rsp+118h+var_68], 0
0x1800aa706  jz      loc_1800AA838
0x1800aa70c  lea     rdx, [rsp+118h+var_64]
0x1800aa714  mov     rcx, [rsp+118h+var_60]
0x1800aa71c  call    cs:__imp_FwRegQueryNumValues
0x1800aa722  mov     rcx, [rsp+118h]; this
0x1800aa72a  test    eax, eax
0x1800aa72c  jns     short loc_1800AA742
0x1800aa72e  mov     r9d, eax; char *
0x1800aa731  lea     r8, aOnecoreNetMpss_6; "onecore\\net\\mpssvc\\lics\\fw\\fw_dfwe"...
0x1800aa738  mov     edx, 0E0Ah; void *
0x1800aa73d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800aa742  xor     esi, esi
0x1800aa744  cmp     esi, [rsp+118h+var_64]
0x1800aa74b  jnb     loc_1800AA821
0x1800aa751  mov     [rsp+118h+var_70], 0
0x1800aa75d  mov     [rsp+118h+lpString1], 0
0x1800aa769  lea     rax, [rsp+118h+var_70]
0x1800aa771  mov     [rsp+118h+var_D8], rax
0x1800aa776  lea     rax, [rsp+118h+lpString1]
0x1800aa77e  mov     [rsp+118h+var_D0], rax
0x1800aa783  mov     [rsp+118h+var_C8], 1
0x1800aa788  mov     [rsp+118h+var_68], 0
0x1800aa793  mov     [rsp+118h+var_E8], 0
0x1800aa79c  mov     [rsp+118h+cchCount2], 1
0x1800aa7a4  lea     rax, [rsp+118h+var_68]
0x1800aa7ac  mov     [rsp+118h+lpString2], rax; int
0x1800aa7b1  lea     r9, [rsp+118h+lpString1]
0x1800aa7b9  lea     r8, [rsp+118h+var_70]
0x1800aa7c1  mov     edx, esi
0x1800aa7c3  mov     rcx, [rsp+118h+var_60]
0x1800aa7cb  call    cs:__imp_FwRegEnumValueNameAndValueData
0x1800aa7d1  mov     rcx, [rsp+118h]; this
0x1800aa7d9  test    eax, eax
0x1800aa7db  jns     short loc_1800AA7F1
0x1800aa7dd  mov     r9d, eax; char *
0x1800aa7e0  lea     r8, aOnecoreNetMpss_6; "onecore\\net\\mpssvc\\lics\\fw\\fw_dfwe"...
0x1800aa7e7  mov     edx, 0E15h; void *
0x1800aa7ec  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800aa7f1  cmp     [rsp+118h+var_68], 0
0x1800aa7f9  jnz     short loc_1800AA86D
0x1800aa7fb  mov     rcx, [rsp+118h+var_70]
0x1800aa803  test    rcx, rcx
0x1800aa806  jz      short loc_1800AA80E
0x1800aa808  call    cs:__imp_FwFree
0x1800aa80e  mov     rcx, [rsp+118h+lpString1]
0x1800aa816  test    rcx, rcx
0x1800aa819  jz      short loc_1800AA821
0x1800aa81b  call    cs:__imp_FwFree
0x1800aa821  mov     rax, [rdi+240h]
0x1800aa828  cmp     [rdi+238h], rax
0x1800aa82f  setnz   al
0x1800aa832  mov     [rdi+250h], al
0x1800aa838  lea     rcx, [rsp+118h+var_60]
0x1800aa840  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800aa845  xor     eax, eax
0x1800aa847  jmp     short loc_1800AA850
0x1800aa849  mov     eax, [rsp+118h+var_64]
0x1800aa850  mov     rcx, [rsp+118h+var_38]
0x1800aa858  xor     rcx, rsp; StackCookie
0x1800aa85b  call    __security_check_cookie
0x1800aa860  add     rsp, 0F8h
0x1800aa867  pop     r15
0x1800aa869  pop     rdi
0x1800aa86a  pop     rsi
0x1800aa86b  pop     rbx
0x1800aa86c  retn
0x1800aa86d  mov     rdx, [rsp+118h+lpString1]
0x1800aa875  lea     rcx, [rsp+118h+var_58]
0x1800aa87d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800aa882  nop
0x1800aa883  mov     rdx, qword ptr [rsp+118h+var_48]
0x1800aa88b  test    rdx, rdx
0x1800aa88e  jz      short loc_1800AA8F7
0x1800aa890  lea     rax, [rsp+118h+var_58]
0x1800aa898  cmp     qword ptr [rsp+118h+var_48+8], 7
0x1800aa8a1  cmova   rax, qword ptr [rsp+118h+var_58]
0x1800aa8aa  mov     ecx, 3Ah ; ':'
0x1800aa8af  cmp     cx, [rax+rdx*2-2]
0x1800aa8b4  jnz     loc_1800AA9F1
0x1800aa8ba  mov     [rsp+118h+cchCount2], 0Ch; cchCount2
0x1800aa8c2  lea     rax, aDosdevices; "\\DosDevices\\"
0x1800aa8c9  mov     [rsp+118h+lpString2], rax; lpString2
0x1800aa8ce  lea     r9d, [rcx-2Eh]; cchCount1
0x1800aa8d2  mov     r8, [rsp+118h+lpString1]; lpString1
0x1800aa8da  lea     edx, [rcx-39h]; dwCmpFlags
0x1800aa8dd  lea     ecx, [rdx+7Eh]; Locale
0x1800aa8e0  call    cs:__imp_CompareStringW
0x1800aa8e6  cmp     eax, 2
0x1800aa8e9  jnz     loc_1800AA9F1
0x1800aa8ef  mov     rdx, qword ptr [rsp+118h+var_48]
0x1800aa8f7  lea     rcx, [rsp+118h+var_58]
0x1800aa8ff  cmp     qword ptr [rsp+118h+var_48+8], 7
0x1800aa908  cmova   rcx, qword ptr [rsp+118h+var_58]
0x1800aa911  mov     [rsp+118h+lpString2], 1
0x1800aa91a  lea     r9, asc_1800F8178; "\\"
0x1800aa921  call    ??$_Traits_find_last_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x1800aa926  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800aa92a  jz      short loc_1800AA995
0x1800aa92c  lea     r8, [rax+1]
0x1800aa930  lea     rdx, [rsp+118h+var_B8]
0x1800aa935  lea     rcx, [rsp+118h+var_58]
0x1800aa93d  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800aa942  mov     rbx, rax
0x1800aa945  lea     rax, [rsp+118h+var_58]
0x1800aa94d  cmp     rax, rbx
0x1800aa950  jz      short loc_1800AA98B
0x1800aa952  lea     rcx, [rsp+118h+var_58]
0x1800aa95a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa95f  movups  xmm0, xmmword ptr [rbx]
0x1800aa962  movups  [rsp+118h+var_58], xmm0
0x1800aa96a  movups  xmm1, xmmword ptr [rbx+10h]
0x1800aa96e  movups  [rsp+118h+var_48], xmm1
0x1800aa976  mov     qword ptr [rbx+10h], 0
0x1800aa97e  mov     qword ptr [rbx+18h], 7
0x1800aa986  xor     eax, eax
0x1800aa988  mov     [rbx], ax
0x1800aa98b  lea     rcx, [rsp+118h+var_B8]; void *
0x1800aa990  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800aa995  lea     rbx, [rdi+238h]
0x1800aa99c  mov     rdx, [rsp+118h+var_70]
0x1800aa9a4  lea     rcx, [rsp+118h+var_B8]
0x1800aa9a9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800aa9ae  nop
0x1800aa9af  lea     rdx, [rsp+118h+var_58]
0x1800aa9b7  lea     rcx, [rsp+118h+var_98]
0x1800aa9bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800aa9c4  nop
0x1800aa9c5  mov     rcx, [rbx+8]
0x1800aa9c9  cmp     rcx, [rbx+10h]
0x1800aa9cd  jz      short loc_1800AAA34
0x1800aa9cf  lea     rdx, [rsp+118h+var_B8]
0x1800aa9d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800aa9d9  add     rcx, 20h ; ' '
0x1800aa9dd  lea     rdx, [rsp+118h+var_98]
0x1800aa9e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800aa9ea  add     qword ptr [rbx+8], 40h ; '@'
0x1800aa9ef  jmp     short loc_1800AAA45
0x1800aa9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa9f8  cmp     rcx, r15
0x1800aa9fb  jz      short loc_1800AAA2D
0x1800aa9fd  test    byte ptr [rcx+1Ch], 2
0x1800aaa01  jz      short loc_1800AAA2D
0x1800aaa03  mov     edx, 0A7h
0x1800aaa08  mov     rax, [rsp+118h+lpString1]
0x1800aaa10  mov     [rsp+118h+lpString2], rax
0x1800aaa15  mov     r9, [rsp+118h+var_70]
0x1800aaa1d  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800aaa24  mov     rcx, [rcx+10h]
0x1800aaa28  call    WPP_SF_SS
0x1800aaa2d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800aaa32  jmp     short loc_1800AAA8C
0x1800aaa34  lea     r8, [rsp+118h+var_B8]
0x1800aaa39  mov     rdx, rcx
0x1800aaa3c  mov     rcx, rbx
0x1800aaa3f  call    ??$_Emplace_reallocate@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<std::wstring,std::wstring>>::_Emplace_reallocate<std::pair<std::wstring,std::wstring>>(std::pair<std::wstring,std::wstring> * const,std::pair<std::wstring,std::wstring> &&)
0x1800aaa44  nop
0x1800aaa45  lea     rcx, [rsp+118h+var_B8]
0x1800aaa4a  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(void)
0x1800aaa4f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaa56  cmp     rcx, r15
0x1800aaa59  jz      short loc_1800AAA8C
0x1800aaa5b  test    byte ptr [rcx+1Ch], 4
0x1800aaa5f  jz      short loc_1800AAA8C
0x1800aaa61  mov     edx, 0A8h
0x1800aaa66  mov     rax, [rsp+118h+lpString1]
0x1800aaa6e  mov     [rsp+118h+lpString2], rax
0x1800aaa73  mov     r9, [rsp+118h+var_70]
0x1800aaa7b  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800aaa82  mov     rcx, [rcx+10h]
0x1800aaa86  call    WPP_SF_SS
0x1800aaa8b  nop
0x1800aaa8c  lea     rcx, [rsp+118h+var_58]; void *
0x1800aaa94  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800aaa99  nop
0x1800aaa9a  mov     rcx, [rsp+118h+var_70]
0x1800aaaa2  test    rcx, rcx
0x1800aaaa5  jz      short loc_1800AAAAD
0x1800aaaa7  call    cs:__imp_FwFree
0x1800aaaad  mov     rcx, [rsp+118h+lpString1]
0x1800aaab5  test    rcx, rcx
0x1800aaab8  jz      short loc_1800AAAC0
0x1800aaaba  call    cs:__imp_FwFree
0x1800aaac0  inc     esi
0x1800aaac2  jmp     loc_1800AA744
```
