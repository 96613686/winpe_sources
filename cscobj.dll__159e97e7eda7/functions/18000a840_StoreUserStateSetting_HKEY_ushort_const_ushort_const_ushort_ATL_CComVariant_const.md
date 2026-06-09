# StoreUserStateSetting(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant const &)

- ea: `0x18000a840`
- end: `0x18000ab37`
- name: `?StoreUserStateSetting@@YAJPEAUHKEY__@@PEBG1GAEBVCComVariant@ATL@@@Z`
- size: `759`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned __int16, VARIANTARG *pvarSrc)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a084`
- `0x180028d64`

## callees

- `0x18000a840`
- `0x18000ab40`
- `0x18000b1a8`
- `0x18000f5cc`
- `0x18000f60c`
- `0x180027fd0`
- `0x180028d64`
- `0x180029858`
- `0x180029e00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a921`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a921`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000aa2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000aad1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000aa2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000aad1`
- `OLEAUT32!__imp_VariantInit` at `0x18000a871`
- `OLEAUT32!__imp_VariantInit` at `0x18000a871`
- `OLEAUT32!__imp_VariantClear` at `0x18000a8e4`
- `OLEAUT32!__imp_VariantClear` at `0x18000a8e4`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000a8ab`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000a8ab`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000a9c9`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000a9c9`

## pseudocode

```c
__int64 __fastcall StoreUserStateSetting(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        unsigned __int16 a4,
        VARIANTARG *pvarSrc)
{
  unsigned int v5; // edi
  VARIANTARG *p_pvarg; // rdx
  HRESULT v10; // eax
  int v11; // edx
  int v12; // r8d
  const wchar_t *bstrVal; // rcx
  LSTATUS v14; // eax
  signed int v15; // ebx
  int iVal; // eax
  const BYTE *p_bVal; // rax
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  REGSAM samDesired; // [rsp+28h] [rbp-49h]
  int v22; // [rsp+50h] [rbp-21h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-11h] BYREF

  v5 = a4;
  hKeya = 0;
  VariantInit(&pvarg);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    p_pvarg = &pvarg;
    if ( pvarSrc )
      p_pvarg = pvarSrc;
    v10 = VariantChangeType(&pvarg, p_pvarg, 0, 8u);
    bstrVal = L"<undefined>";
    if ( v10 >= 0 )
      bstrVal = pvarg.bstrVal;
    WPP_SF_SSdS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      v11,
      v12,
      (_DWORD)lpSubKey,
      (__int64)lpValueName,
      v5,
      (__int64)bstrVal);
  }
  VariantClear(&pvarg);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKeya,
    0);
  v14 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKeya, 0);
  v15 = v14;
  if ( v14 > 0 )
    v15 = (unsigned __int16)v14 | 0x80070000;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      36,
      WPP_313c576492293c0704086ae70e07ed75_Traceguids,
      (unsigned int)v15);
  if ( v15 >= 0 )
  {
    if ( v5 == 11 )
    {
      iVal = pvarSrc->iVal != 0;
LABEL_16:
      v22 = iVal;
      p_bVal = (const BYTE *)&v22;
LABEL_36:
      v18 = RegSetValueExW(hKeya, lpValueName, 0, 4u, p_bVal, 4u);
LABEL_37:
      v15 = v18;
      if ( v18 > 0 )
        v15 = (unsigned __int16)v18 | 0x80070000;
      goto LABEL_39;
    }
    if ( (((_WORD)v5 - 3) & 0xFFEF) == 0 )
    {
      p_bVal = &pvarSrc->bVal;
      goto LABEL_36;
    }
    if ( (((_WORD)v5 - 2) & 0xFFEF) == 0 )
    {
      iVal = pvarSrc->iVal;
      goto LABEL_16;
    }
    if ( (unsigned __int16)(v5 - 16) <= 1u )
    {
      iVal = pvarSrc->bVal;
      goto LABEL_16;
    }
    if ( v5 == 8 )
    {
      samDesired = SysStringByteLen(pvarSrc->bstrVal) + 2;
      v18 = RegSetValueExW(hKeya, lpValueName, 0, 1u, pvarSrc->pbVal, samDesired);
      goto LABEL_37;
    }
    if ( (_WORD)v5 == 8200 )
    {
      *(_QWORD *)&pvarg.vt = 0;
      pvarg.lVal = -1;
      pvarg.pRecInfo = 0;
      v15 = UstVarLib::CscVarUtil_ConvertVariantToMULTISZ(
              (UstVarLib *)pvarSrc,
              &pvarg,
              (struct CVarCvtBuffer *)&WPP_GLOBAL_Control);
      if ( v15 >= 0 )
      {
        v19 = RegSetValueExW(hKeya, lpValueName, 0, 7u, (const BYTE *)pvarg.pRecInfo, pvarg.decVal.Hi32);
        v15 = v19;
        if ( v19 > 0 )
          v15 = (unsigned __int16)v19 | 0x80070000;
      }
      UstVarLib::CVarCvtBuffer::~CVarCvtBuffer((UstVarLib::CVarCvtBuffer *)&pvarg);
    }
    else if ( (_WORD)v5 == 8204 )
    {
      v15 = StoreUserStateMultiValueSetting(hKey, lpSubKey, (const struct ATL::CComVariant *)pvarSrc);
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 37, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v5, v15);
      v15 = -2147024809;
    }
  }
LABEL_39:
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      38,
      WPP_313c576492293c0704086ae70e07ed75_Traceguids,
      (unsigned int)v15);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000a840  push    rbp
0x18000a842  push    rbx
0x18000a843  push    rsi
0x18000a844  push    rdi
0x18000a845  push    r12
0x18000a847  push    r13
0x18000a849  push    r14
0x18000a84b  push    r15
0x18000a84d  lea     rbp, [rsp-17h]
0x18000a852  sub     rsp, 88h
0x18000a859  movzx   edi, r9w
0x18000a85d  mov     r14, r8
0x18000a860  mov     r15, rdx
0x18000a863  mov     r12, rcx
0x18000a866  xor     r13d, r13d
0x18000a869  mov     [rbp+4Fh+hKey], r13
0x18000a86d  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18000a871  call    cs:__imp_VariantInit
0x18000a877  lea     rcx, WPP_GLOBAL_Control
0x18000a87e  mov     rsi, [rbp+4Fh+pvarSrc]
0x18000a882  mov     rax, cs:WPP_GLOBAL_Control
0x18000a889  cmp     rax, rcx
0x18000a88c  jz      short loc_18000A8E0
0x18000a88e  test    byte ptr [rax+1Ch], 2
0x18000a892  jz      short loc_18000A8E0
0x18000a894  lea     rdx, [rbp+4Fh+pvarg]
0x18000a898  test    rsi, rsi
0x18000a89b  cmovnz  rdx, rsi; pvarSrc
0x18000a89f  mov     r9w, 8; vt
0x18000a8a4  xor     r8d, r8d; wFlags
0x18000a8a7  lea     rcx, [rbp+4Fh+pvarg]; pvargDest
0x18000a8ab  call    cs:__imp_VariantChangeType
0x18000a8b1  lea     rcx, aUndefined; "<undefined>"
0x18000a8b8  test    eax, eax
0x18000a8ba  cmovns  rcx, qword ptr [rbp+4Fh+pvarg+8]
0x18000a8bf  mov     [rsp+0C0h+lpSecurityAttributes], rcx
0x18000a8c4  mov     [rsp+0C0h+samDesired], edi
0x18000a8c8  mov     qword ptr [rsp+0C0h+dwOptions], r14
0x18000a8cd  mov     r9, r15
0x18000a8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8d7  mov     rcx, [rcx+10h]
0x18000a8db  call    WPP_SF_SSdS
0x18000a8e0  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18000a8e4  call    cs:__imp_VariantClear
0x18000a8ea  xor     edx, edx
0x18000a8ec  lea     rcx, [rbp+4Fh+hKey]
0x18000a8f0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000a8f5  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x18000a8fa  lea     rax, [rbp+4Fh+hKey]
0x18000a8fe  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000a903  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18000a908  mov     [rsp+0C0h+samDesired], 20006h; samDesired
0x18000a910  mov     [rsp+0C0h+dwOptions], r13d; dwOptions
0x18000a915  xor     r9d, r9d; lpClass
0x18000a918  xor     r8d, r8d; Reserved
0x18000a91b  mov     rdx, r15; lpSubKey
0x18000a91e  mov     rcx, r12; hKey
0x18000a921  call    cs:__imp_RegCreateKeyExW
0x18000a927  mov     ebx, eax
0x18000a929  test    eax, eax
0x18000a92b  jle     short loc_18000A936
0x18000a92d  movzx   ebx, ax
0x18000a930  or      ebx, 80070000h
0x18000a936  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a93d  lea     r8, WPP_GLOBAL_Control
0x18000a944  cmp     rcx, r8
0x18000a947  jz      short loc_18000A96E
0x18000a949  test    byte ptr [rcx+1Ch], 2
0x18000a94d  jz      short loc_18000A96E
0x18000a94f  mov     edx, 24h ; '$'
0x18000a954  mov     r9d, ebx
0x18000a957  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18000a95e  mov     rcx, [rcx+10h]
0x18000a962  call    WPP_SF_d
0x18000a967  lea     r8, WPP_GLOBAL_Control; struct CVarCvtBuffer *
0x18000a96e  test    ebx, ebx
0x18000a970  js      loc_18000AAE6
0x18000a976  cmp     edi, 0Bh
0x18000a979  jnz     short loc_18000A992
0x18000a97b  mov     eax, r13d
0x18000a97e  cmp     [rsi+8], r13w
0x18000a983  setnz   al
0x18000a986  mov     [rbp+4Fh+var_70], eax
0x18000a989  lea     rax, [rbp+4Fh+var_70]
0x18000a98d  jmp     loc_18000AAB7
0x18000a992  lea     eax, [rdi-3]
0x18000a995  mov     ecx, 0FFEFh
0x18000a99a  test    cx, ax
0x18000a99d  jz      loc_18000AAB3
0x18000a9a3  lea     eax, [rdi-2]
0x18000a9a6  test    cx, ax
0x18000a9a9  jz      loc_18000AAAA
0x18000a9af  lea     eax, [rdi-10h]
0x18000a9b2  mov     edx, 1
0x18000a9b7  cmp     ax, dx
0x18000a9ba  jbe     loc_18000AAA1
0x18000a9c0  cmp     edi, 8
0x18000a9c3  jnz     short loc_18000A9E3
0x18000a9c5  mov     rcx, [rsi+8]; bstr
0x18000a9c9  call    cs:__imp_SysStringByteLen
0x18000a9cf  add     eax, 2
0x18000a9d2  mov     [rsp+0C0h+samDesired], eax
0x18000a9d6  mov     rax, [rsi+8]
0x18000a9da  lea     r9d, [rdi-7]
0x18000a9de  jmp     loc_18000AAC2
0x18000a9e3  mov     eax, 2008h
0x18000a9e8  cmp     di, ax
0x18000a9eb  jnz     short loc_18000AA51
0x18000a9ed  mov     qword ptr [rbp+4Fh+pvarg], r13
0x18000a9f1  mov     dword ptr [rbp+4Fh+pvarg+8], 0FFFFFFFFh
0x18000a9f8  mov     qword ptr [rbp+4Fh+pvarg+10h], r13
0x18000a9fc  lea     rdx, [rbp+4Fh+pvarg]; struct tagVARIANT *
0x18000aa00  mov     rcx, rsi; this
0x18000aa03  call    ?CscVarUtil_ConvertVariantToMULTISZ@UstVarLib@@YAJAEBUtagVARIANT@@PEAVCVarCvtBuffer@1@@Z; UstVarLib::CscVarUtil_ConvertVariantToMULTISZ(tagVARIANT const &,UstVarLib::CVarCvtBuffer *)
0x18000aa08  mov     ebx, eax
0x18000aa0a  test    eax, eax
0x18000aa0c  js      short loc_18000AA43
0x18000aa0e  mov     eax, dword ptr [rbp+4Fh+pvarg+4]
0x18000aa11  mov     [rsp+0C0h+samDesired], eax; cbData
0x18000aa15  mov     rax, qword ptr [rbp+4Fh+pvarg+10h]
0x18000aa19  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x18000aa1e  mov     r9d, 7; dwType
0x18000aa24  xor     r8d, r8d; Reserved
0x18000aa27  mov     rdx, r14; lpValueName
0x18000aa2a  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000aa2e  call    cs:__imp_RegSetValueExW
0x18000aa34  mov     ebx, eax
0x18000aa36  test    eax, eax
0x18000aa38  jle     short loc_18000AA43
0x18000aa3a  movzx   ebx, ax
0x18000aa3d  or      ebx, 80070000h
0x18000aa43  lea     rcx, [rbp+4Fh+pvarg]; this
0x18000aa47  call    ??1CVarCvtBuffer@UstVarLib@@QEAA@XZ; UstVarLib::CVarCvtBuffer::~CVarCvtBuffer(void)
0x18000aa4c  jmp     loc_18000AAE6
0x18000aa51  mov     eax, 200Ch
0x18000aa56  cmp     di, ax
0x18000aa59  jnz     short loc_18000AA6D
0x18000aa5b  mov     r8, rsi; struct ATL::CComVariant *
0x18000aa5e  mov     rdx, r15; unsigned __int16 *
0x18000aa61  mov     rcx, r12; HKEY
0x18000aa64  call    ?StoreUserStateMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEBVCComVariant@ATL@@@Z; StoreUserStateMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant const &)
0x18000aa69  mov     ebx, eax
0x18000aa6b  jmp     short loc_18000AAE6
0x18000aa6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa74  cmp     rcx, r8
0x18000aa77  jz      short loc_18000AA9A
0x18000aa79  test    [rcx+1Ch], dl
0x18000aa7c  jz      short loc_18000AA9A
0x18000aa7e  mov     r9d, edi
0x18000aa81  mov     edx, 25h ; '%'
0x18000aa86  mov     [rsp+0C0h+dwOptions], ebx
0x18000aa8a  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18000aa91  mov     rcx, [rcx+10h]
0x18000aa95  call    WPP_SF_dd
0x18000aa9a  mov     ebx, 80070057h
0x18000aa9f  jmp     short loc_18000AAE6
0x18000aaa1  movzx   eax, byte ptr [rsi+8]
0x18000aaa5  jmp     loc_18000A986
0x18000aaaa  movsx   eax, word ptr [rsi+8]
0x18000aaae  jmp     loc_18000A986
0x18000aab3  lea     rax, [rsi+8]
0x18000aab7  mov     r9d, 4; dwType
0x18000aabd  mov     [rsp+0C0h+samDesired], r9d; cbData
0x18000aac2  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x18000aac7  xor     r8d, r8d; Reserved
0x18000aaca  mov     rdx, r14; lpValueName
0x18000aacd  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000aad1  call    cs:__imp_RegSetValueExW
0x18000aad7  mov     ebx, eax
0x18000aad9  test    eax, eax
0x18000aadb  jle     short loc_18000AAE6
0x18000aadd  movzx   ebx, ax
0x18000aae0  or      ebx, 80070000h
0x18000aae6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaed  lea     rax, WPP_GLOBAL_Control
0x18000aaf4  cmp     rcx, rax
0x18000aaf7  jz      short loc_18000AB18
0x18000aaf9  test    byte ptr [rcx+1Ch], 2
0x18000aafd  jz      short loc_18000AB18
0x18000aaff  mov     edx, 26h ; '&'
0x18000ab04  mov     r9d, ebx
0x18000ab07  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18000ab0e  mov     rcx, [rcx+10h]
0x18000ab12  call    WPP_SF_d
0x18000ab17  nop
0x18000ab18  lea     rcx, [rbp+4Fh+hKey]
0x18000ab1c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000ab21  mov     eax, ebx
0x18000ab23  add     rsp, 88h
0x18000ab2a  pop     r15
0x18000ab2c  pop     r14
0x18000ab2e  pop     r13
0x18000ab30  pop     r12
0x18000ab32  pop     rdi
0x18000ab33  pop     rsi
0x18000ab34  pop     rbx
0x18000ab35  pop     rbp
0x18000ab36  retn
```
