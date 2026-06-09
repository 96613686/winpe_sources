# SaveWlanAttributes

- ea: `0x1800682ac`
- end: `0x18006858f`
- name: `SaveWlanAttributes`
- size: `739`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180116330`
- `0x1801167c4`

## callees

- `0x180013748`
- `0x18002e688`
- `0x1800499f0`
- `0x18004bf94`
- `0x1800682ac`
- `0x1800a88a0`
- `0x180108940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006841a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006841a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068395`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800683cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068483`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068508`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068395`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800683cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068483`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068508`

## string_xrefs

- `0x180068540`: `onecore\net\netprofiles\service\src\signatures\lib\nlmsignatures.cpp`
- `0x180068554`: `onecore\net\netprofiles\service\src\signatures\lib\nlmsignatures.cpp`
- `0x180068568`: `onecore\net\netprofiles\service\src\signatures\lib\nlmsignatures.cpp`
- `0x18006857c`: `onecore\net\netprofiles\service\src\signatures\lib\nlmsignatures.cpp`

## pseudocode

```c
unsigned int __fastcall SaveWlanAttributes(HKEY hKey, unsigned __int8 a2, _QWORD *a3, int a4)
{
  const BYTE *v4; // rbx
  _QWORD *v7; // rdi
  _QWORD *v8; // rax
  __int64 v9; // rcx
  const BYTE *v10; // rsi
  DWORD cbData; // eax
  unsigned int v12; // eax
  unsigned int result; // eax
  wil *v14; // rcx
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // eax
  int v18; // r8d
  int v19; // r9d
  int lpData; // [rsp+20h] [rbp-68h]
  unsigned int lpDataa; // [rsp+20h] [rbp-68h]
  unsigned int lpDatab; // [rsp+20h] [rbp-68h]
  unsigned int lpDatac; // [rsp+20h] [rbp-68h]
  unsigned int lpDatad; // [rsp+20h] [rbp-68h]
  _QWORD *v25; // [rsp+40h] [rbp-48h] BYREF
  const BYTE *v26; // [rsp+48h] [rbp-40h] BYREF
  BYTE Data[8]; // [rsp+50h] [rbp-38h] BYREF
  BYTE v28[4]; // [rsp+58h] [rbp-30h] BYREF
  DWORD v29; // [rsp+5Ch] [rbp-2Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4 = (const BYTE *)a3;
  *(_DWORD *)Data = a4;
  v7 = a3 + 3;
  if ( (unsigned int)dword_1801BD288 > 5 )
  {
    *(_DWORD *)v28 = *(_DWORD *)Data;
    v29 = a2;
    if ( *v7 <= 7u )
      v8 = a3;
    else
      v8 = (_QWORD *)*a3;
    v25 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)hKey,
      (unsigned int)byte_1801969E3,
      (_DWORD)a3,
      a4,
      (__int64)&v25,
      (__int64)&v29,
      (__int64)v28);
  }
  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding>::__private_IsEnabled()
      && !*((_QWORD *)v4 + 2) )
    {
      v10 = (const BYTE *)&qword_180184EF0;
      v9 = 1;
    }
    else
    {
      v9 = *((_QWORD *)v4 + 2);
      if ( *v7 <= 7u )
        v10 = v4;
      else
        v10 = *(const BYTE **)v4;
    }
    if ( a2 )
    {
      cbData = wil::safe_cast<unsigned long,unsigned __int64,0>(2 * v9 + 2);
      v12 = RegSetValueExW(hKey, 0, 0, 1u, v10, cbData);
      if ( v12 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x379,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\signatures\\lib\\nlmsignatures.cpp",
          (const char *)v12,
          lpDataa);
      result = RegSetValueExW(hKey, (LPCWSTR)v10, 0, 3u, Data, 4u);
      v14 = retaddr;
      if ( result )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x37D,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\signatures\\lib\\nlmsignatures.cpp",
          (const char *)result,
          lpDatab);
    }
    else
    {
      *(_DWORD *)v28 = 0;
      v29 = 4;
      result = RegQueryValueExW(hKey, (LPCWSTR)v10, 0, 0, v28, &v29);
      if ( result )
      {
        if ( (unsigned int)dword_1801BD288 > 5 )
        {
          LODWORD(v25) = *(_DWORD *)Data;
          if ( *v7 > 7u )
            v4 = *(const BYTE **)v4;
          v26 = v4;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            (_DWORD)v14,
            (unsigned int)word_1801967EA,
            v15,
            v16,
            (__int64)&v26,
            (__int64)&v25);
        }
        result = RegSetValueExW(hKey, (LPCWSTR)v10, 0, 3u, Data, 4u);
        v14 = retaddr;
        if ( result )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x38E,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\signatures\\lib\\nlmsignatures.cpp",
            (const char *)result,
            lpDatac);
      }
      else if ( !*(_DWORD *)v28 && *(_DWORD *)Data )
      {
        if ( (unsigned int)dword_1801BD288 > 5 )
        {
          LODWORD(v25) = *(_DWORD *)Data;
          if ( *v7 > 7u )
            v4 = *(const BYTE **)v4;
          v26 = v4;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            (_DWORD)v14,
            (unsigned int)byte_180196845,
            v15,
            v16,
            (__int64)&v26,
            (__int64)&v25);
        }
        result = RegSetValueExW(hKey, (LPCWSTR)v10, 0, 3u, Data, 4u);
        v14 = retaddr;
        if ( result )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x39A,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\signatures\\lib\\nlmsignatures.cpp",
            (const char *)result,
            lpDatad);
      }
    }
  }
  catch ( ... )
  {
    v17 = wil::ResultFromCaughtException(v14);
    result = wil::details::in1diag3::Log_Hr(
               retaddr,
               (void *)0x3A0,
               (unsigned int)"onecore\\net\\netprofiles\\service\\src\\signatures\\lib\\nlmsignatures.cpp",
               (const char *)v17,
               lpData);
    if ( (unsigned int)dword_1801BD288 > 5 )
    {
      LODWORD(v25) = result;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
               dword_1801BD288,
               (unsigned int)&dword_1801968A4,
               v18,
               v19,
               (__int64)&v25);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800682ac  mov     r11, rsp
0x1800682af  mov     [r11+10h], rbx
0x1800682b3  mov     [r11+18h], rsi
0x1800682b7  push    rdi
0x1800682b8  push    r14
0x1800682ba  push    r15
0x1800682bc  sub     rsp, 70h
0x1800682c0  mov     rax, cs:__security_cookie
0x1800682c7  xor     rax, rsp
0x1800682ca  mov     [rsp+88h+var_28], rax
0x1800682cf  mov     rbx, r8
0x1800682d2  movzx   r14d, dl
0x1800682d6  mov     r15, rcx
0x1800682d9  mov     [r11-38h], r9d
0x1800682dd  mov     eax, cs:dword_1801BD288
0x1800682e3  lea     rdi, [r8+18h]
0x1800682e7  cmp     eax, 5
0x1800682ea  jbe     short loc_180068335
0x1800682ec  mov     eax, dword ptr [rsp+88h+Data]
0x1800682f0  mov     dword ptr [rsp+88h+var_30], eax
0x1800682f4  mov     [r11-2Ch], r14d
0x1800682f8  cmp     qword ptr [rdi], 7
0x1800682fc  jbe     short loc_180068303
0x1800682fe  mov     rax, [r8]
0x180068301  jmp     short loc_180068306
0x180068303  mov     rax, rbx
0x180068306  mov     [rsp+88h+var_48], rax
0x18006830b  lea     rax, [rsp+88h+var_30]
0x180068310  mov     [rsp+88h+var_58], rax
0x180068315  lea     rax, [rsp+88h+var_2C]
0x18006831a  mov     qword ptr [rsp+88h+cbData], rax
0x18006831f  lea     rax, [rsp+88h+var_48]
0x180068324  mov     [rsp+88h+lpData], rax
0x180068329  lea     rdx, byte_1801969E3
0x180068330  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180068335  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding>::GetImpl(void)'::`2'::impl
0x18006833c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding>::__private_IsEnabled(void)
0x180068341  test    al, al
0x180068343  jz      short loc_18006834C
0x180068345  cmp     qword ptr [rbx+10h], 0
0x18006834a  jz      short loc_180068360
0x18006834c  mov     rcx, [rbx+10h]
0x180068350  cmp     qword ptr [rdi], 7
0x180068354  jbe     short loc_18006835B
0x180068356  mov     rsi, [rbx]
0x180068359  jmp     short loc_18006836C
0x18006835b  mov     rsi, rbx
0x18006835e  jmp     short loc_18006836C
0x180068360  mov     rsi, cs:off_180155A80
0x180068367  mov     ecx, 1
0x18006836c  test    r14b, r14b
0x18006836f  jz      short loc_1800683E7
0x180068371  lea     rcx, ds:2[rcx*2]
0x180068379  call    ??$safe_cast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast<ulong,unsigned __int64,0>(unsigned __int64)
0x18006837e  mov     [rsp+88h+cbData], eax; cbData
0x180068382  mov     [rsp+88h+lpData], rsi; unsigned int
0x180068387  mov     r9d, 1; dwType
0x18006838d  xor     r8d, r8d; Reserved
0x180068390  xor     edx, edx; lpValueName
0x180068392  mov     rcx, r15; hKey
0x180068395  call    cs:__imp_RegSetValueExW
0x18006839b  mov     rcx, [rsp+88h]; this
0x1800683a3  test    eax, eax
0x1800683a5  jnz     loc_18006853D
0x1800683ab  mov     [rsp+88h+cbData], 4; cbData
0x1800683b3  lea     rax, [rsp+88h+Data]
0x1800683b8  mov     [rsp+88h+lpData], rax; unsigned int
0x1800683bd  mov     r9d, 3; dwType
0x1800683c3  xor     r8d, r8d; Reserved
0x1800683c6  mov     rdx, rsi; lpValueName
0x1800683c9  mov     rcx, r15; hKey
0x1800683cc  call    cs:__imp_RegSetValueExW
0x1800683d2  mov     rcx, [rsp+88h]; this
0x1800683da  test    eax, eax
0x1800683dc  jnz     loc_180068551
0x1800683e2  jmp     loc_18006851A
0x1800683e7  mov     dword ptr [rsp+88h+var_30], 0
0x1800683ef  mov     r14d, 4
0x1800683f5  mov     [rsp+88h+var_2C], r14d
0x1800683fa  lea     rax, [rsp+88h+var_2C]
0x1800683ff  mov     qword ptr [rsp+88h+cbData], rax; lpcbData
0x180068404  lea     rax, [rsp+88h+var_30]
0x180068409  mov     [rsp+88h+lpData], rax; lpData
0x18006840e  xor     r9d, r9d; lpType
0x180068411  xor     r8d, r8d; lpReserved
0x180068414  mov     rdx, rsi; lpValueName
0x180068417  mov     rcx, r15; hKey
0x18006841a  call    cs:__imp_RegQueryValueExW
0x180068420  test    eax, eax
0x180068422  jz      short loc_18006849B
0x180068424  mov     eax, cs:dword_1801BD288
0x18006842a  cmp     eax, 5
0x18006842d  jbe     short loc_180068465
0x18006842f  mov     eax, dword ptr [rsp+88h+Data]
0x180068433  mov     dword ptr [rsp+88h+var_48], eax
0x180068437  cmp     qword ptr [rdi], 7
0x18006843b  jbe     short loc_180068440
0x18006843d  mov     rbx, [rbx]
0x180068440  mov     [rsp+88h+var_40], rbx
0x180068445  lea     rax, [rsp+88h+var_48]
0x18006844a  mov     qword ptr [rsp+88h+cbData], rax
0x18006844f  lea     rax, [rsp+88h+var_40]
0x180068454  mov     [rsp+88h+lpData], rax
0x180068459  lea     rdx, word_1801967EA
0x180068460  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180068465  mov     [rsp+88h+cbData], r14d; cbData
0x18006846a  lea     rax, [rsp+88h+Data]
0x18006846f  mov     [rsp+88h+lpData], rax; unsigned int
0x180068474  mov     r9d, 3; dwType
0x18006847a  xor     r8d, r8d; Reserved
0x18006847d  mov     rdx, rsi; lpValueName
0x180068480  mov     rcx, r15; hKey
0x180068483  call    cs:__imp_RegSetValueExW
0x180068489  mov     rcx, [rsp+88h]; this
0x180068491  test    eax, eax
0x180068493  jnz     loc_180068565
0x180068499  jmp     short loc_18006851A
0x18006849b  cmp     dword ptr [rsp+88h+var_30], 0
0x1800684a0  jnz     short loc_18006851A
0x1800684a2  cmp     dword ptr [rsp+88h+Data], 0
0x1800684a7  jz      short loc_18006851A
0x1800684a9  mov     eax, cs:dword_1801BD288
0x1800684af  cmp     eax, 5
0x1800684b2  jbe     short loc_1800684EA
0x1800684b4  mov     eax, dword ptr [rsp+88h+Data]
0x1800684b8  mov     dword ptr [rsp+88h+var_48], eax
0x1800684bc  cmp     qword ptr [rdi], 7
0x1800684c0  jbe     short loc_1800684C5
0x1800684c2  mov     rbx, [rbx]
0x1800684c5  mov     [rsp+88h+var_40], rbx
0x1800684ca  lea     rax, [rsp+88h+var_48]
0x1800684cf  mov     qword ptr [rsp+88h+cbData], rax
0x1800684d4  lea     rax, [rsp+88h+var_40]
0x1800684d9  mov     [rsp+88h+lpData], rax
0x1800684de  lea     rdx, byte_180196845
0x1800684e5  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800684ea  mov     [rsp+88h+cbData], r14d; cbData
0x1800684ef  lea     rax, [rsp+88h+Data]
0x1800684f4  mov     [rsp+88h+lpData], rax; unsigned int
0x1800684f9  mov     r9d, 3; dwType
0x1800684ff  xor     r8d, r8d; Reserved
0x180068502  mov     rdx, rsi; lpValueName
0x180068505  mov     rcx, r15; hKey
0x180068508  call    cs:__imp_RegSetValueExW
0x18006850e  mov     rcx, [rsp+88h]; this
0x180068516  test    eax, eax
0x180068518  jnz     short loc_180068579
0x18006851a  mov     rcx, [rsp+88h+var_28]
0x18006851f  xor     rcx, rsp; StackCookie
0x180068522  call    __security_check_cookie
0x180068527  lea     r11, [rsp+88h+var_18]
0x18006852c  mov     rbx, [r11+28h]
0x180068530  mov     rsi, [r11+30h]
0x180068534  mov     rsp, r11
0x180068537  pop     r15
0x180068539  pop     r14
0x18006853b  pop     rdi
0x18006853c  retn
0x18006853d  mov     r9d, eax; char *
0x180068540  lea     r8, aOnecoreNetNetp_26; "onecore\\net\\netprofiles\\service\\src"...
0x180068547  mov     edx, 379h; void *
0x18006854c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180068551  mov     r9d, eax; char *
0x180068554  lea     r8, aOnecoreNetNetp_26; "onecore\\net\\netprofiles\\service\\src"...
0x18006855b  mov     edx, 37Dh; void *
0x180068560  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180068565  mov     r9d, eax; char *
0x180068568  lea     r8, aOnecoreNetNetp_26; "onecore\\net\\netprofiles\\service\\src"...
0x18006856f  mov     edx, 38Eh; void *
0x180068574  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180068579  mov     r9d, eax; char *
0x18006857c  lea     r8, aOnecoreNetNetp_26; "onecore\\net\\netprofiles\\service\\src"...
0x180068583  mov     edx, 39Ah; void *
0x180068588  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
