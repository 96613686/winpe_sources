# CDfwEngWriter::JunctionCacheInitialize(void)

- ea: `0x1800b0700`
- end: `0x1800b0bba`
- name: `?JunctionCacheInitialize@CDfwEngWriter@@AEAAJXZ`
- size: `1210`
- prototype: `__int64 __fastcall(CDfwEngWriter *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800af160`

## callees

- `0x1800089bc`
- `0x180010384`
- `0x18001275c`
- `0x180012840`
- `0x180015310`
- `0x1800192e0`
- `0x1800424c0`
- `0x18005ba68`
- `0x180070420`
- `0x1800729c0`
- `0x1800a81f0`
- `0x1800ad498`
- `0x1800ae234`
- `0x1800ae5f4`
- `0x1800b0700`
- `0x1800b0e84`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b09bf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b09bf`
- `fwbase!FwRegQueryNumValues` at `0x1800b07e2`
- `fwbase!FwRegQueryNumValues` at `0x1800b07e2`
- `fwbase!FwRegEnumValueNameAndValueData` at `0x1800b0897`
- `fwbase!FwRegEnumValueNameAndValueData` at `0x1800b0897`
- `fwbase!FwRegOpenKey` at `0x1800b0798`
- `fwbase!FwRegOpenKey` at `0x1800b0798`
- `fwbase!FwFree` at `0x1800b08da`
- `fwbase!FwFree` at `0x1800b08f3`
- `fwbase!FwFree` at `0x1800b0b8c`
- `fwbase!FwFree` at `0x1800b0ba5`
- `fwbase!FwFree` at `0x1800b08da`
- `fwbase!FwFree` at `0x1800b08f3`
- `fwbase!FwFree` at `0x1800b0b8c`
- `fwbase!FwFree` at `0x1800b0ba5`

## string_xrefs

- `0x1800b07b3`: `onecore\net\mpssvc\lics\fw\fw_dfwengwriter.cpp`
- `0x1800b07fd`: `onecore\net\mpssvc\lics\fw\fw_dfwengwriter.cpp`
- `0x1800b08b2`: `onecore\net\mpssvc\lics\fw\fw_dfwengwriter.cpp`
- `0x1800b078a`: `System\WCOSJunctions`

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
  __int64 v9; // rdx
  __int128 *v10; // rax
  __int128 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int lpString2; // [rsp+20h] [rbp-F8h]
  _BYTE v18[32]; // [rsp+60h] [rbp-B8h] BYREF
  _BYTE v19[32]; // [rsp+80h] [rbp-98h] BYREF
  PCNZWCH lpString1; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v21; // [rsp+A8h] [rbp-70h] BYREF
  int v22; // [rsp+B0h] [rbp-68h] BYREF
  unsigned int v23; // [rsp+B4h] [rbp-64h] BYREF
  __int64 v24; // [rsp+B8h] [rbp-60h] BYREF
  __int128 v25; // [rsp+C0h] [rbp-58h] BYREF
  __int128 v26; // [rsp+D0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v22 = 0;
  v23 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 166, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
  v24 = 0;
  v2 = FwRegOpenKey(-2147483646, L"System\\WCOSJunctions", 131097, &v24, &v22);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xE15,
        (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_dfwengwriter.cpp",
        (const char *)(unsigned int)v2,
        lpString2);
    if ( v22 )
    {
      v3 = FwRegQueryNumValues(v24, &v23);
      if ( v3 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xE19,
          (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_dfwengwriter.cpp",
          (const char *)(unsigned int)v3,
          lpString2);
      for ( i = 0; ; ++i )
      {
        if ( i >= v23 )
        {
LABEL_19:
          *((_BYTE *)this + 592) = *((_QWORD *)this + 71) != *((_QWORD *)this + 72);
          goto LABEL_20;
        }
        v21 = 0;
        lpString1 = 0;
        v22 = 0;
        v5 = FwRegEnumValueNameAndValueData(v24, i, &v21, &lpString1);
        if ( v5 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xE24,
            (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_dfwengwriter.cpp",
            (const char *)(unsigned int)v5,
            (int)&v22);
        if ( !v22 )
        {
          if ( v21 )
            FwFree(v21);
          if ( lpString1 )
            FwFree(lpString1);
          goto LABEL_19;
        }
        std::wstring::wstring(&v25, lpString1);
        v9 = v26;
        if ( !(_QWORD)v26 )
          goto LABEL_27;
        v10 = &v25;
        if ( *((_QWORD *)&v26 + 1) > 7u )
          v10 = (__int128 *)v25;
        if ( *((_WORD *)v10 + v26 - 1) == 58 && CompareStringW(0x7Fu, 1u, lpString1, 12, L"\\DosDevices\\", 12) == 2 )
          break;
        v16 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          WPP_SF_SS(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            167,
            (unsigned int)WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
            v21,
            (__int64)lpString1);
        MicrosoftTelemetryAssertTriggeredNoArgs(v16);
LABEL_43:
        std::wstring::~wstring(&v25);
        if ( v21 )
          FwFree(v21);
        if ( lpString1 )
          FwFree(lpString1);
      }
      v9 = v26;
LABEL_27:
      v11 = &v25;
      if ( *((_QWORD *)&v26 + 1) > 7u )
        v11 = (__int128 *)v25;
      v12 = std::_Traits_find_last_of<std::char_traits<unsigned short>>(v11, v9, v8, L"\\", 1);
      if ( v12 != -1 )
      {
        v13 = std::wstring::substr(&v25, v18, v12 + 1);
        if ( &v25 != (__int128 *)v13 )
        {
          std::wstring::_Tidy_deallocate(&v25);
          v25 = *(_OWORD *)v13;
          v26 = *(_OWORD *)(v13 + 16);
          *(_QWORD *)(v13 + 16) = 0;
          *(_QWORD *)(v13 + 24) = 7;
          *(_WORD *)v13 = 0;
        }
        std::wstring::~wstring(v18);
      }
      std::wstring::wstring(v18, v21);
      std::wstring::wstring(v19, &v25);
      v14 = *((_QWORD *)this + 72);
      if ( v14 == *((_QWORD *)this + 73) )
      {
        std::vector<std::pair<std::wstring,std::wstring>>::_Emplace_reallocate<std::pair<std::wstring,std::wstring>>(
          (char *)this + 568,
          *((_QWORD *)this + 72),
          v18);
      }
      else
      {
        std::wstring::wstring(v14, v18);
        std::wstring::wstring(v15 + 32, v19);
        *((_QWORD *)this + 72) += 64LL;
      }
      std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v18);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_SS(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          168,
          (unsigned int)WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
          v21,
          (__int64)lpString1);
      goto LABEL_43;
    }
LABEL_20:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v24);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xE4B,
                           (unsigned int)"onecore\\net\\mpssvc\\lics\\fw\\fw_dfwengwriter.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800b0700  mov     r11, rsp
0x1800b0703  push    rbx
0x1800b0704  push    rsi
0x1800b0705  push    rdi
0x1800b0706  push    r15
0x1800b0708  sub     rsp, 0F8h
0x1800b070f  mov     rax, cs:__security_cookie
0x1800b0716  xor     rax, rsp
0x1800b0719  mov     [rsp+118h+var_38], rax
0x1800b0721  mov     rdi, rcx
0x1800b0724  mov     dword ptr [r11-68h], 0
0x1800b072c  mov     dword ptr [r11-64h], 0
0x1800b0734  lea     r15, WPP_GLOBAL_Control
0x1800b073b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0742  cmp     rcx, r15
0x1800b0745  jz      short loc_1800B0763
0x1800b0747  test    byte ptr [rcx+1Ch], 8
0x1800b074b  jz      short loc_1800B0763
0x1800b074d  mov     edx, 0A6h
0x1800b0752  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800b0759  mov     rcx, [rcx+10h]
0x1800b075d  call    WPP_SF_
0x1800b0762  nop
0x1800b0763  mov     [rsp+118h+var_60], 0
0x1800b076f  lea     rax, [rsp+118h+var_68]
0x1800b0777  mov     [rsp+118h+lpString2], rax; int
0x1800b077c  lea     r9, [rsp+118h+var_60]
0x1800b0784  mov     r8d, 20019h
0x1800b078a  lea     rdx, aSystemWcosjunc; "System\\WCOSJunctions"
0x1800b0791  mov     rcx, 0FFFFFFFF80000002h
0x1800b0798  call    cs:__imp_FwRegOpenKey
0x1800b079f  nop     dword ptr [rax+rax+00h]
0x1800b07a4  mov     rcx, [rsp+118h]; this
0x1800b07ac  test    eax, eax
0x1800b07ae  jns     short loc_1800B07C4
0x1800b07b0  mov     r9d, eax; char *
0x1800b07b3  lea     r8, aOnecoreNetMpss_6; "onecore\\net\\mpssvc\\lics\\fw\\fw_dfwe"...
0x1800b07ba  mov     edx, 0E15h; void *
0x1800b07bf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800b07c4  cmp     [rsp+118h+var_68], 0
0x1800b07cc  jz      loc_1800B0916
0x1800b07d2  lea     rdx, [rsp+118h+var_64]
0x1800b07da  mov     rcx, [rsp+118h+var_60]
0x1800b07e2  call    cs:__imp_FwRegQueryNumValues
0x1800b07e9  nop     dword ptr [rax+rax+00h]
0x1800b07ee  mov     rcx, [rsp+118h]; this
0x1800b07f6  test    eax, eax
0x1800b07f8  jns     short loc_1800B080E
0x1800b07fa  mov     r9d, eax; char *
0x1800b07fd  lea     r8, aOnecoreNetMpss_6; "onecore\\net\\mpssvc\\lics\\fw\\fw_dfwe"...
0x1800b0804  mov     edx, 0E19h; void *
0x1800b0809  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800b080e  xor     esi, esi
0x1800b0810  cmp     esi, [rsp+118h+var_64]
0x1800b0817  jnb     loc_1800B08FF
0x1800b081d  mov     [rsp+118h+var_70], 0
0x1800b0829  mov     [rsp+118h+lpString1], 0
0x1800b0835  lea     rax, [rsp+118h+var_70]
0x1800b083d  mov     [rsp+118h+var_D8], rax
0x1800b0842  lea     rax, [rsp+118h+lpString1]
0x1800b084a  mov     [rsp+118h+var_D0], rax
0x1800b084f  mov     [rsp+118h+var_C8], 1
0x1800b0854  mov     [rsp+118h+var_68], 0
0x1800b085f  mov     [rsp+118h+var_E8], 0
0x1800b0868  mov     [rsp+118h+cchCount2], 1
0x1800b0870  lea     rax, [rsp+118h+var_68]
0x1800b0878  mov     [rsp+118h+lpString2], rax; int
0x1800b087d  lea     r9, [rsp+118h+lpString1]
0x1800b0885  lea     r8, [rsp+118h+var_70]
0x1800b088d  mov     edx, esi
0x1800b088f  mov     rcx, [rsp+118h+var_60]
0x1800b0897  call    cs:__imp_FwRegEnumValueNameAndValueData
0x1800b089e  nop     dword ptr [rax+rax+00h]
0x1800b08a3  mov     rcx, [rsp+118h]; this
0x1800b08ab  test    eax, eax
0x1800b08ad  jns     short loc_1800B08C3
0x1800b08af  mov     r9d, eax; char *
0x1800b08b2  lea     r8, aOnecoreNetMpss_6; "onecore\\net\\mpssvc\\lics\\fw\\fw_dfwe"...
0x1800b08b9  mov     edx, 0E24h; void *
0x1800b08be  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800b08c3  cmp     [rsp+118h+var_68], 0
0x1800b08cb  jnz     short loc_1800B094C
0x1800b08cd  mov     rcx, [rsp+118h+var_70]
0x1800b08d5  test    rcx, rcx
0x1800b08d8  jz      short loc_1800B08E6
0x1800b08da  call    cs:__imp_FwFree
0x1800b08e1  nop     dword ptr [rax+rax+00h]
0x1800b08e6  mov     rcx, [rsp+118h+lpString1]
0x1800b08ee  test    rcx, rcx
0x1800b08f1  jz      short loc_1800B08FF
0x1800b08f3  call    cs:__imp_FwFree
0x1800b08fa  nop     dword ptr [rax+rax+00h]
0x1800b08ff  mov     rax, [rdi+240h]
0x1800b0906  cmp     [rdi+238h], rax
0x1800b090d  setnz   al
0x1800b0910  mov     [rdi+250h], al
0x1800b0916  lea     rcx, [rsp+118h+var_60]
0x1800b091e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b0923  xor     eax, eax
0x1800b0925  jmp     short loc_1800B092E
0x1800b0927  mov     eax, [rsp+118h+var_64]
0x1800b092e  mov     rcx, [rsp+118h+var_38]
0x1800b0936  xor     rcx, rsp; StackCookie
0x1800b0939  call    __security_check_cookie
0x1800b093e  add     rsp, 0F8h
0x1800b0945  pop     r15
0x1800b0947  pop     rdi
0x1800b0948  pop     rsi
0x1800b0949  pop     rbx
0x1800b094a  retn
0x1800b094c  mov     rdx, [rsp+118h+lpString1]
0x1800b0954  lea     rcx, [rsp+118h+var_58]
0x1800b095c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b0961  nop
0x1800b0962  mov     rdx, qword ptr [rsp+118h+var_48]
0x1800b096a  test    rdx, rdx
0x1800b096d  jz      short loc_1800B09DC
0x1800b096f  lea     rax, [rsp+118h+var_58]
0x1800b0977  cmp     qword ptr [rsp+118h+var_48+8], 7
0x1800b0980  cmova   rax, qword ptr [rsp+118h+var_58]
0x1800b0989  mov     ecx, 3Ah ; ':'
0x1800b098e  cmp     cx, [rax+rdx*2-2]
0x1800b0993  jnz     loc_1800B0AD6
0x1800b0999  mov     [rsp+118h+cchCount2], 0Ch; cchCount2
0x1800b09a1  lea     rax, aDosdevices; "\\DosDevices\\"
0x1800b09a8  mov     [rsp+118h+lpString2], rax; lpString2
0x1800b09ad  lea     r9d, [rcx-2Eh]; cchCount1
0x1800b09b1  mov     r8, [rsp+118h+lpString1]; lpString1
0x1800b09b9  lea     edx, [rcx-39h]; dwCmpFlags
0x1800b09bc  lea     ecx, [rdx+7Eh]; Locale
0x1800b09bf  call    cs:__imp_CompareStringW
0x1800b09c6  nop     dword ptr [rax+rax+00h]
0x1800b09cb  cmp     eax, 2
0x1800b09ce  jnz     loc_1800B0AD6
0x1800b09d4  mov     rdx, qword ptr [rsp+118h+var_48]
0x1800b09dc  lea     rcx, [rsp+118h+var_58]
0x1800b09e4  cmp     qword ptr [rsp+118h+var_48+8], 7
0x1800b09ed  cmova   rcx, qword ptr [rsp+118h+var_58]
0x1800b09f6  mov     [rsp+118h+lpString2], 1
0x1800b09ff  lea     r9, asc_1800FE138; "\\"
0x1800b0a06  call    ??$_Traits_find_last_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x1800b0a0b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b0a0f  jz      short loc_1800B0A7A
0x1800b0a11  lea     r8, [rax+1]
0x1800b0a15  lea     rdx, [rsp+118h+var_B8]
0x1800b0a1a  lea     rcx, [rsp+118h+var_58]
0x1800b0a22  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800b0a27  mov     rbx, rax
0x1800b0a2a  lea     rax, [rsp+118h+var_58]
0x1800b0a32  cmp     rax, rbx
0x1800b0a35  jz      short loc_1800B0A70
0x1800b0a37  lea     rcx, [rsp+118h+var_58]
0x1800b0a3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b0a44  movups  xmm0, xmmword ptr [rbx]
0x1800b0a47  movups  [rsp+118h+var_58], xmm0
0x1800b0a4f  movups  xmm1, xmmword ptr [rbx+10h]
0x1800b0a53  movups  [rsp+118h+var_48], xmm1
0x1800b0a5b  mov     qword ptr [rbx+10h], 0
0x1800b0a63  mov     qword ptr [rbx+18h], 7
0x1800b0a6b  xor     eax, eax
0x1800b0a6d  mov     [rbx], ax
0x1800b0a70  lea     rcx, [rsp+118h+var_B8]; void *
0x1800b0a75  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b0a7a  lea     rbx, [rdi+238h]
0x1800b0a81  mov     rdx, [rsp+118h+var_70]
0x1800b0a89  lea     rcx, [rsp+118h+var_B8]
0x1800b0a8e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b0a93  nop
0x1800b0a94  lea     rdx, [rsp+118h+var_58]
0x1800b0a9c  lea     rcx, [rsp+118h+var_98]
0x1800b0aa4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b0aa9  nop
0x1800b0aaa  mov     rcx, [rbx+8]
0x1800b0aae  cmp     rcx, [rbx+10h]
0x1800b0ab2  jz      short loc_1800B0B19
0x1800b0ab4  lea     rdx, [rsp+118h+var_B8]
0x1800b0ab9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800b0abe  add     rcx, 20h ; ' '
0x1800b0ac2  lea     rdx, [rsp+118h+var_98]
0x1800b0aca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800b0acf  add     qword ptr [rbx+8], 40h ; '@'
0x1800b0ad4  jmp     short loc_1800B0B2A
0x1800b0ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0add  cmp     rcx, r15
0x1800b0ae0  jz      short loc_1800B0B12
0x1800b0ae2  test    byte ptr [rcx+1Ch], 2
0x1800b0ae6  jz      short loc_1800B0B12
0x1800b0ae8  mov     edx, 0A7h
0x1800b0aed  mov     rax, [rsp+118h+lpString1]
0x1800b0af5  mov     [rsp+118h+lpString2], rax
0x1800b0afa  mov     r9, [rsp+118h+var_70]
0x1800b0b02  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800b0b09  mov     rcx, [rcx+10h]
0x1800b0b0d  call    WPP_SF_SS
0x1800b0b12  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false", "Failed to validate WCOSJunction Mapping")
0x1800b0b17  jmp     short loc_1800B0B71
0x1800b0b19  lea     r8, [rsp+118h+var_B8]
0x1800b0b1e  mov     rdx, rcx
0x1800b0b21  mov     rcx, rbx
0x1800b0b24  call    ??$_Emplace_reallocate@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<std::wstring,std::wstring>>::_Emplace_reallocate<std::pair<std::wstring,std::wstring>>(std::pair<std::wstring,std::wstring> * const,std::pair<std::wstring,std::wstring> &&)
0x1800b0b29  nop
0x1800b0b2a  lea     rcx, [rsp+118h+var_B8]
0x1800b0b2f  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(void)
0x1800b0b34  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0b3b  cmp     rcx, r15
0x1800b0b3e  jz      short loc_1800B0B71
0x1800b0b40  test    byte ptr [rcx+1Ch], 4
0x1800b0b44  jz      short loc_1800B0B71
0x1800b0b46  mov     edx, 0A8h
0x1800b0b4b  mov     rax, [rsp+118h+lpString1]
0x1800b0b53  mov     [rsp+118h+lpString2], rax
0x1800b0b58  mov     r9, [rsp+118h+var_70]
0x1800b0b60  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800b0b67  mov     rcx, [rcx+10h]
0x1800b0b6b  call    WPP_SF_SS
0x1800b0b70  nop
0x1800b0b71  lea     rcx, [rsp+118h+var_58]; void *
0x1800b0b79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b0b7e  nop
0x1800b0b7f  mov     rcx, [rsp+118h+var_70]
0x1800b0b87  test    rcx, rcx
0x1800b0b8a  jz      short loc_1800B0B98
0x1800b0b8c  call    cs:__imp_FwFree
0x1800b0b93  nop     dword ptr [rax+rax+00h]
0x1800b0b98  mov     rcx, [rsp+118h+lpString1]
0x1800b0ba0  test    rcx, rcx
0x1800b0ba3  jz      short loc_1800B0BB1
0x1800b0ba5  call    cs:__imp_FwFree
0x1800b0bac  nop     dword ptr [rax+rax+00h]
0x1800b0bb1  inc     esi
0x1800b0bb3  jmp     loc_1800B0810
```
