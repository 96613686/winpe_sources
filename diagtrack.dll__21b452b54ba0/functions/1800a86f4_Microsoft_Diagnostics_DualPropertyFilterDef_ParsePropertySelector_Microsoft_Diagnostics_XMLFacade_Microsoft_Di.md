# Microsoft::Diagnostics::DualPropertyFilterDef::ParsePropertySelector(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &,ulong)

- ea: `0x1800a86f4`
- end: `0x1800a8e18`
- name: `?ParsePropertySelector@DualPropertyFilterDef@Diagnostics@Microsoft@@AEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@K@Z`
- size: `1828`
- prototype: `int(Microsoft::Diagnostics::DualPropertyFilterDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a6730`

## callees

- `0x18002ac68`
- `0x18002b318`
- `0x18002be90`
- `0x18002cae0`
- `0x18002df00`
- `0x18002df70`
- `0x18002e030`
- `0x180064e8c`
- `0x1800653d0`
- `0x18008b254`
- `0x1800a6438`
- `0x1800a658c`
- `0x1800a86f4`
- `0x18020aac0`
- `0x1802c3390`
- `0x1802c8240`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a87b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a8899`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a89b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a87b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a8899`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a89b6`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800a8a8a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800a8a8a`

## string_xrefs

- `0x1800a876c`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a883f`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a88df`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a894a`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a89fc`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a8ab0`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a8b16`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a8b61`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a8bad`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a8c46`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a8cb9`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a8d02`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a8d42`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x1800a8d83`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::DualPropertyFilterDef::ParsePropertySelector(
        Microsoft::Diagnostics::DualPropertyFilterDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3,
        int a4)
{
  unsigned int Element; // eax
  unsigned int v9; // ebx
  int CurrentElementName; // eax
  unsigned int v11; // ebx
  const char *v12; // r9
  __int64 result; // rax
  _QWORD *v14; // rdx
  int v15; // ebx
  __int64 v16; // r8
  unsigned int v17; // esi
  unsigned int v18; // r14d
  unsigned __int64 v19; // r8
  unsigned int v20; // eax
  unsigned int v21; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  _QWORD *v24; // rdx
  int v25; // ebx
  __int64 v26; // r8
  int InnerText; // eax
  unsigned int v28; // ebx
  int v29; // eax
  unsigned int v30; // ebx
  _QWORD *v31; // rdx
  int v32; // ebx
  __int64 v33; // r8
  int v34; // eax
  unsigned int v35; // ebx
  __int64 v36; // rax
  _QWORD *v37; // rcx
  __int64 v38; // rax
  _QWORD *v39; // rcx
  int v40; // eax
  unsigned int v41; // ebx
  int v42; // eax
  unsigned int v43; // ebx
  __int64 v44; // rax
  _QWORD *v45; // rbx
  int v46; // eax
  unsigned int v47; // ebx
  int v48[2]; // [rsp+20h] [rbp-98h] BYREF
  _QWORD v49[2]; // [rsp+28h] [rbp-90h] BYREF
  unsigned __int64 v50; // [rsp+38h] [rbp-80h]
  unsigned __int64 v51; // [rsp+40h] [rbp-78h]
  __int128 v52; // [rsp+48h] [rbp-70h] BYREF
  __int64 v53; // [rsp+58h] [rbp-60h]
  __int64 v54; // [rsp+60h] [rbp-58h]
  _QWORD v55[3]; // [rsp+68h] [rbp-50h] BYREF
  unsigned __int64 v56; // [rsp+80h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  std::wstring::wstring(v49);
  try
  {
    while ( 1 )
    {
LABEL_2:
      Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
      v9 = Element;
      if ( Element )
      {
        if ( (int)(Element + 0x80000000) < 0 || Element == -2147024270 )
        {
          *((_WORD *)this + 29) = *(_WORD *)Microsoft::Diagnostics::ITriggerInst::DetermineSelectorRoute(
                                              v48,
                                              (char *)this + 168);
          *((_WORD *)this + 101) = *(_WORD *)Microsoft::Diagnostics::ITriggerInst::DetermineSelectorRoute(
                                               v48,
                                               (char *)this + 312);
          std::wstring::_Tidy_deallocate(v49);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C0,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
            (const char *)Element,
            v48[0]);
          std::wstring::_Tidy_deallocate(v49);
          return v9;
        }
      }
      CurrentElementName = Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v49);
      v11 = CurrentElementName;
      if ( CurrentElementName < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x35E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
          (const char *)(unsigned int)CurrentElementName,
          v48[0]);
        std::wstring::_Tidy_deallocate(v49);
        return v11;
      }
      v14 = v49;
      if ( v51 > 7 )
        v14 = (_QWORD *)v49[0];
      v15 = v50;
      v16 = v50;
      if ( v50 >= 0xB )
        v16 = 11;
      if ( (unsigned int)_o__wcsnicmp(L"propertykey", v14, v16) || v15 != 11 )
        break;
      v17 = 0;
      v18 = 0;
      v52 = 0;
      v53 = 0;
      v54 = 0;
      v19 = std::_WChar_traits<wchar_t>::length(&Src);
      std::wstring::_Construct<1,wchar_t *>(&v52, &Src, v19);
      *(_QWORD *)v48 = 0;
      while ( 1 )
      {
        v20 = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
        v21 = v20;
        if ( v20 )
          break;
        v22 = Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v49);
        v23 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x368,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
            (const char *)(unsigned int)v22,
            v48[0]);
          std::wstring::_Tidy_deallocate(&v52);
          std::wstring::_Tidy_deallocate(v49);
          return v23;
        }
        v24 = v49;
        if ( v51 > 7 )
          v24 = (_QWORD *)v49[0];
        v25 = v50;
        v26 = v50;
        if ( v50 >= 4 )
          v26 = 4;
        if ( !(unsigned int)_o__wcsnicmp(L"name", v24, v26) && v25 == 4 )
        {
          std::wstring::wstring(v55);
          InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v55);
          v28 = InnerText;
          if ( InnerText < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x36D,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)(unsigned int)InnerText,
              v48[0]);
            std::wstring::_Tidy_deallocate(v55);
            std::wstring::_Tidy_deallocate(&v52);
            std::wstring::_Tidy_deallocate(v49);
            return v28;
          }
          std::wstring::_Tidy_deallocate(&v52);
          std::wstring::_Take_contents(&v52, v55);
          v29 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v30 = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x36F,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)(unsigned int)v29,
              v48[0]);
            std::wstring::_Tidy_deallocate(v55);
            std::wstring::_Tidy_deallocate(&v52);
            std::wstring::_Tidy_deallocate(v49);
            return v30;
          }
          ++v17;
          goto LABEL_44;
        }
        v31 = v49;
        if ( v51 > 7 )
          v31 = (_QWORD *)v49[0];
        v32 = v50;
        v33 = v50;
        if ( v50 >= 5 )
          v33 = 5;
        if ( (unsigned int)_o__wcsnicmp(L"index", v31, v33) || v32 != 5 )
        {
          if ( *((_BYTE *)a3 + 152) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x385,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)0x87C52407LL,
              v48[0]);
            std::wstring::_Tidy_deallocate(&v52);
            std::wstring::_Tidy_deallocate(v49);
            return 2277843975LL;
          }
          v42 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v43 = v42;
          if ( v42 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x388,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)(unsigned int)v42,
              v48[0]);
            std::wstring::_Tidy_deallocate(&v52);
            std::wstring::_Tidy_deallocate(v49);
            return v43;
          }
        }
        else
        {
          std::wstring::wstring(v55);
          v34 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v55);
          v35 = v34;
          if ( v34 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x375,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)(unsigned int)v34,
              v48[0]);
            std::wstring::_Tidy_deallocate(v55);
            std::wstring::_Tidy_deallocate(&v52);
            std::wstring::_Tidy_deallocate(v49);
            return v35;
          }
          v36 = std::_WChar_traits<wchar_t>::length(L"*");
          v37 = v55;
          if ( v56 > 7 )
            v37 = (_QWORD *)v55[0];
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v37, v55[2], L"*", v36) )
          {
            v38 = -2;
          }
          else
          {
            v39 = v55;
            if ( v56 > 7 )
              v39 = (_QWORD *)v55[0];
            v38 = (int)_o__wtoi(v39);
          }
          *(_QWORD *)v48 = v38;
          v40 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v41 = v40;
          if ( v40 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x37E,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)(unsigned int)v40,
              v48[0]);
            std::wstring::_Tidy_deallocate(v55);
            std::wstring::_Tidy_deallocate(&v52);
            std::wstring::_Tidy_deallocate(v49);
            return v41;
          }
          ++v18;
LABEL_44:
          std::wstring::_Tidy_deallocate(v55);
        }
      }
      if ( (int)(v20 + 0x80000000) >= 0 && v20 != -2147024270 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x38C,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
          (const char *)v20,
          v48[0]);
        std::wstring::_Tidy_deallocate(&v52);
        std::wstring::_Tidy_deallocate(v49);
        return v21;
      }
      if ( v18 > 1 || v17 > 1 || v17 == 1 && !v53 || !v17 && !v18 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x392,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
          (const char *)0x87C52402LL,
          v48[0]);
        std::wstring::_Tidy_deallocate(&v52);
        std::wstring::_Tidy_deallocate(v49);
        return 2277843970LL;
      }
      if ( !a4 )
      {
        v44 = 168;
        goto LABEL_62;
      }
      if ( a4 == 1 )
      {
        v44 = 312;
LABEL_62:
        v45 = (_QWORD *)((char *)this + v44);
        if ( (Microsoft::Diagnostics::DualPropertyFilterDef *)((char *)this + v44) )
        {
          if ( *v45 == v45[1] && !v17 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3A5,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)0x87C5243CLL,
              v48[0]);
            std::wstring::_Tidy_deallocate(&v52);
            std::wstring::_Tidy_deallocate(v49);
            return 2277844028LL;
          }
          if ( v17 == 1 )
            std::vector<Microsoft::Diagnostics::PropertyKey>::emplace_back<std::wstring>(v45, &v52);
          if ( v18 == 1 )
            std::vector<Microsoft::Diagnostics::PropertyKey>::emplace_back<unsigned __int64 &>(v45, v48);
        }
      }
      std::wstring::_Tidy_deallocate(&v52);
    }
    if ( *((_BYTE *)a3 + 152) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
        (const char *)0x87C52407LL,
        v48[0]);
      std::wstring::_Tidy_deallocate(v49);
      result = 2277843975LL;
    }
    else
    {
      v46 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v47 = v46;
      if ( v46 >= 0 )
        goto LABEL_2;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3BB,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
        (const char *)(unsigned int)v46,
        v48[0]);
      std::wstring::_Tidy_deallocate(v49);
      result = v47;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3C8,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800a86f4  mov     [rsp+arg_10], rbx
0x1800a86f9  mov     [rsp+arg_18], rsi
0x1800a86fe  push    rdi
0x1800a86ff  push    r12
0x1800a8701  push    r13
0x1800a8703  push    r14
0x1800a8705  push    r15
0x1800a8707  sub     rsp, 90h
0x1800a870e  mov     rax, cs:__security_cookie
0x1800a8715  xor     rax, rsp
0x1800a8718  mov     [rsp+0B8h+var_30], rax
0x1800a8720  mov     r13d, r9d
0x1800a8723  mov     r12, r8
0x1800a8726  mov     rdi, rdx
0x1800a8729  mov     r15, rcx
0x1800a872c  lea     rcx, [rsp+0B8h+var_90]; void *
0x1800a8731  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a8736  nop
0x1800a8737  mov     esi, 0Bh
0x1800a873c  mov     rcx, rdi; this
0x1800a873f  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x1800a8744  mov     ebx, eax
0x1800a8746  test    eax, eax
0x1800a8748  jnz     loc_1800A8D65
0x1800a874e  lea     rdx, [rsp+0B8h+var_90]
0x1800a8753  mov     rcx, rdi
0x1800a8756  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x1800a875b  mov     ebx, eax
0x1800a875d  test    eax, eax
0x1800a875f  jns     short loc_1800A878F
0x1800a8761  mov     rcx, [rsp+0B8h]; this
0x1800a8769  mov     r9d, eax; char *
0x1800a876c  lea     r8, aOnecoreBaseTel_164; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8773  mov     edx, 35Eh; void *
0x1800a8778  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a877d  nop
0x1800a877e  lea     rcx, [rsp+0B8h+var_90]
0x1800a8783  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8788  mov     eax, ebx
0x1800a878a  jmp     loc_1800A8DEA
0x1800a878f  lea     rdx, [rsp+0B8h+var_90]
0x1800a8794  cmp     [rsp+0B8h+var_78], 7
0x1800a879a  cmova   rdx, [rsp+0B8h+var_90]
0x1800a87a0  mov     rbx, [rsp+0B8h+var_80]
0x1800a87a5  mov     r8, rbx
0x1800a87a8  cmp     rbx, rsi
0x1800a87ab  cmovnb  r8, rsi
0x1800a87af  mov     rcx, cs:off_18036CEF0; "propertykey"
0x1800a87b6  call    cs:__imp__o__wcsnicmp
0x1800a87bc  test    eax, eax
0x1800a87be  jnz     loc_1800A8CE7
0x1800a87c4  mov     eax, esi
0x1800a87c6  sub     eax, ebx
0x1800a87c8  test    eax, eax
0x1800a87ca  jnz     loc_1800A8CE7
0x1800a87d0  xor     esi, esi
0x1800a87d2  xor     r14d, r14d
0x1800a87d5  xorps   xmm0, xmm0
0x1800a87d8  movups  [rsp+0B8h+var_70], xmm0
0x1800a87dd  xor     ebx, ebx
0x1800a87df  mov     [rsp+0B8h+var_60], rbx
0x1800a87e4  mov     [rsp+0B8h+var_58], rbx
0x1800a87e9  lea     rcx, Src
0x1800a87f0  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a87f5  mov     r8, rax
0x1800a87f8  lea     rdx, Src
0x1800a87ff  lea     rcx, [rsp+0B8h+var_70]
0x1800a8804  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800a8809  nop
0x1800a880a  mov     qword ptr [rsp+0B8h+var_98], rbx; int
0x1800a880f  mov     rcx, rdi; this
0x1800a8812  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x1800a8817  mov     ebx, eax
0x1800a8819  test    eax, eax
0x1800a881b  jnz     loc_1800A8B8F
0x1800a8821  lea     rdx, [rsp+0B8h+var_90]
0x1800a8826  mov     rcx, rdi
0x1800a8829  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x1800a882e  mov     ebx, eax
0x1800a8830  test    eax, eax
0x1800a8832  jns     short loc_1800A886D
0x1800a8834  mov     rcx, [rsp+0B8h]; this
0x1800a883c  mov     r9d, eax; char *
0x1800a883f  lea     r8, aOnecoreBaseTel_164; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8846  mov     edx, 368h; void *
0x1800a884b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8850  nop
0x1800a8851  lea     rcx, [rsp+0B8h+var_70]
0x1800a8856  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a885b  nop
0x1800a885c  lea     rcx, [rsp+0B8h+var_90]
0x1800a8861  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8866  mov     eax, ebx
0x1800a8868  jmp     loc_1800A8DEA
0x1800a886d  lea     rdx, [rsp+0B8h+var_90]
0x1800a8872  cmp     [rsp+0B8h+var_78], 7
0x1800a8878  cmova   rdx, [rsp+0B8h+var_90]
0x1800a887e  mov     rbx, [rsp+0B8h+var_80]
0x1800a8883  mov     r8, rbx
0x1800a8886  mov     eax, 4
0x1800a888b  cmp     rbx, rax
0x1800a888e  cmovnb  r8, rax
0x1800a8892  mov     rcx, cs:off_18036CEE0; "name"
0x1800a8899  call    cs:__imp__o__wcsnicmp
0x1800a889f  test    eax, eax
0x1800a88a1  jnz     loc_1800A898A
0x1800a88a7  mov     eax, 4
0x1800a88ac  sub     eax, ebx
0x1800a88ae  test    eax, eax
0x1800a88b0  jnz     loc_1800A898A
0x1800a88b6  lea     rcx, [rsp+0B8h+var_50]; void *
0x1800a88bb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a88c0  nop
0x1800a88c1  lea     rdx, [rsp+0B8h+var_50]
0x1800a88c6  mov     rcx, rdi
0x1800a88c9  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a88ce  mov     ebx, eax
0x1800a88d0  test    eax, eax
0x1800a88d2  jns     short loc_1800A8918
0x1800a88d4  mov     rcx, [rsp+0B8h]; this
0x1800a88dc  mov     r9d, eax; char *
0x1800a88df  lea     r8, aOnecoreBaseTel_164; "onecore\\base\\telemetry\\utc\\service"...
0x1800a88e6  mov     edx, 36Dh; void *
0x1800a88eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a88f0  nop
0x1800a88f1  lea     rcx, [rsp+0B8h+var_50]
0x1800a88f6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a88fb  nop
0x1800a88fc  lea     rcx, [rsp+0B8h+var_70]
0x1800a8901  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8906  nop
0x1800a8907  lea     rcx, [rsp+0B8h+var_90]
0x1800a890c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8911  mov     eax, ebx
0x1800a8913  jmp     loc_1800A8DEA
0x1800a8918  lea     rcx, [rsp+0B8h+var_70]
0x1800a891d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8922  lea     rdx, [rsp+0B8h+var_50]
0x1800a8927  lea     rcx, [rsp+0B8h+var_70]
0x1800a892c  call    ?_Take_contents@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXAEAV12@@Z; std::wstring::_Take_contents(std::wstring &)
0x1800a8931  mov     rcx, rdi; this
0x1800a8934  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a8939  mov     ebx, eax
0x1800a893b  test    eax, eax
0x1800a893d  jns     short loc_1800A8983
0x1800a893f  mov     rcx, [rsp+0B8h]; this
0x1800a8947  mov     r9d, eax; char *
0x1800a894a  lea     r8, aOnecoreBaseTel_164; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8951  mov     edx, 36Fh; void *
0x1800a8956  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a895b  nop
0x1800a895c  lea     rcx, [rsp+0B8h+var_50]
0x1800a8961  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8966  nop
0x1800a8967  lea     rcx, [rsp+0B8h+var_70]
0x1800a896c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8971  nop
0x1800a8972  lea     rcx, [rsp+0B8h+var_90]
0x1800a8977  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a897c  mov     eax, ebx
0x1800a897e  jmp     loc_1800A8DEA
0x1800a8983  inc     esi
0x1800a8985  jmp     loc_1800A8AEC
0x1800a898a  lea     rdx, [rsp+0B8h+var_90]
0x1800a898f  cmp     [rsp+0B8h+var_78], 7
0x1800a8995  cmova   rdx, [rsp+0B8h+var_90]
0x1800a899b  mov     rbx, [rsp+0B8h+var_80]
0x1800a89a0  mov     r8, rbx
0x1800a89a3  mov     eax, 5
0x1800a89a8  cmp     rbx, rax
0x1800a89ab  cmovnb  r8, rax
0x1800a89af  mov     rcx, cs:off_18036CF00; "index"
0x1800a89b6  call    cs:__imp__o__wcsnicmp
0x1800a89bc  test    eax, eax
0x1800a89be  jnz     loc_1800A8AFB
0x1800a89c4  mov     eax, 5
0x1800a89c9  sub     eax, ebx
0x1800a89cb  test    eax, eax
0x1800a89cd  jnz     loc_1800A8AFB
0x1800a89d3  lea     rcx, [rsp+0B8h+var_50]; void *
0x1800a89d8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a89dd  nop
0x1800a89de  lea     rdx, [rsp+0B8h+var_50]
0x1800a89e3  mov     rcx, rdi
0x1800a89e6  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a89eb  mov     ebx, eax
0x1800a89ed  test    eax, eax
0x1800a89ef  jns     short loc_1800A8A35
0x1800a89f1  mov     rcx, [rsp+0B8h]; this
0x1800a89f9  mov     r9d, eax; char *
0x1800a89fc  lea     r8, aOnecoreBaseTel_164; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8a03  mov     edx, 375h; void *
0x1800a8a08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8a0d  nop
0x1800a8a0e  lea     rcx, [rsp+0B8h+var_50]
0x1800a8a13  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8a18  nop
0x1800a8a19  lea     rcx, [rsp+0B8h+var_70]
0x1800a8a1e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8a23  nop
0x1800a8a24  lea     rcx, [rsp+0B8h+var_90]
0x1800a8a29  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8a2e  mov     eax, ebx
0x1800a8a30  jmp     loc_1800A8DEA
0x1800a8a35  lea     rcx, pszMore; "*"
0x1800a8a3c  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a8a41  lea     rcx, [rsp+0B8h+var_50]
0x1800a8a46  cmp     [rsp+0B8h+var_38], 7
0x1800a8a4f  cmova   rcx, [rsp+0B8h+var_50]
0x1800a8a55  mov     r9, rax
0x1800a8a58  lea     r8, pszMore; "*"
0x1800a8a5f  mov     rdx, [rsp+0B8h+var_40]
0x1800a8a64  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800a8a69  test    al, al
0x1800a8a6b  jz      short loc_1800A8A76
0x1800a8a6d  mov     rax, 0FFFFFFFFFFFFFFFEh
0x1800a8a74  jmp     short loc_1800A8A92
0x1800a8a76  lea     rcx, [rsp+0B8h+var_50]
0x1800a8a7b  cmp     [rsp+0B8h+var_38], 7
0x1800a8a84  cmova   rcx, [rsp+0B8h+var_50]
0x1800a8a8a  call    cs:__imp__o__wtoi
0x1800a8a90  cdqe
0x1800a8a92  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x1800a8a97  mov     rcx, rdi; this
0x1800a8a9a  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a8a9f  mov     ebx, eax
0x1800a8aa1  test    eax, eax
0x1800a8aa3  jns     short loc_1800A8AE9
0x1800a8aa5  mov     rcx, [rsp+0B8h]; this
0x1800a8aad  mov     r9d, eax; char *
0x1800a8ab0  lea     r8, aOnecoreBaseTel_164; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8ab7  mov     edx, 37Eh; void *
0x1800a8abc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8ac1  nop
0x1800a8ac2  lea     rcx, [rsp+0B8h+var_50]
0x1800a8ac7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8acc  nop
0x1800a8acd  lea     rcx, [rsp+0B8h+var_70]
0x1800a8ad2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8ad7  nop
0x1800a8ad8  lea     rcx, [rsp+0B8h+var_90]
0x1800a8add  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8ae2  mov     eax, ebx
0x1800a8ae4  jmp     loc_1800A8DEA
0x1800a8ae9  inc     r14d
0x1800a8aec  lea     rcx, [rsp+0B8h+var_50]
0x1800a8af1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8af6  jmp     loc_1800A880F
0x1800a8afb  cmp     byte ptr [r12+98h], 0
0x1800a8b04  jz      short loc_1800A8B44
0x1800a8b06  mov     rcx, [rsp+0B8h]; this
0x1800a8b0e  mov     ebx, 87C52407h
0x1800a8b13  mov     r9d, ebx; char *
0x1800a8b16  lea     r8, aOnecoreBaseTel_164; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8b1d  mov     edx, 385h; void *
0x1800a8b22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8b27  nop
0x1800a8b28  lea     rcx, [rsp+0B8h+var_70]
0x1800a8b2d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8b32  nop
0x1800a8b33  lea     rcx, [rsp+0B8h+var_90]
0x1800a8b38  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8b3d  mov     eax, ebx
0x1800a8b3f  jmp     loc_1800A8DEA
0x1800a8b44  mov     rcx, rdi; this
0x1800a8b47  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a8b4c  mov     ebx, eax
0x1800a8b4e  test    eax, eax
0x1800a8b50  jns     loc_1800A880F
0x1800a8b56  mov     rcx, [rsp+0B8h]; this
0x1800a8b5e  mov     r9d, eax; char *
0x1800a8b61  lea     r8, aOnecoreBaseTel_164; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8b68  mov     edx, 388h; void *
0x1800a8b6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8b72  nop
0x1800a8b73  lea     rcx, [rsp+0B8h+var_70]
0x1800a8b78  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8b7d  nop
0x1800a8b7e  lea     rcx, [rsp+0B8h+var_90]
0x1800a8b83  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8b88  mov     eax, ebx
0x1800a8b8a  jmp     loc_1800A8DEA
0x1800a8b8f  mov     ecx, 80000000h
0x1800a8b94  add     eax, ecx
0x1800a8b96  test    ecx, eax
0x1800a8b98  jnz     short loc_1800A8BDB
0x1800a8b9a  cmp     ebx, 80070272h
0x1800a8ba0  jz      short loc_1800A8BDB
0x1800a8ba2  mov     rcx, [rsp+0B8h]; this
0x1800a8baa  mov     r9d, ebx; char *
0x1800a8bad  lea     r8, aOnecoreBaseTel_164; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8bb4  mov     edx, 38Ch; void *
0x1800a8bb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8bbe  nop
0x1800a8bbf  lea     rcx, [rsp+0B8h+var_70]
0x1800a8bc4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8bc9  nop
0x1800a8bca  lea     rcx, [rsp+0B8h+var_90]
0x1800a8bcf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8bd4  mov     eax, ebx
  ... truncated ...
```
