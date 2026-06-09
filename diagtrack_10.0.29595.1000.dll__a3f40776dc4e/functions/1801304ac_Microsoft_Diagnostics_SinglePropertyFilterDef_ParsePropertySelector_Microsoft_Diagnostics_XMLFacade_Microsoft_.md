# Microsoft::Diagnostics::SinglePropertyFilterDef::ParsePropertySelector(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x1801304ac`
- end: `0x180130ad8`
- name: `?ParsePropertySelector@SinglePropertyFilterDef@Diagnostics@Microsoft@@AEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `1580`
- prototype: `int(Microsoft::Diagnostics::SinglePropertyFilterDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a4c80`

## callees

- `0x18002ac68`
- `0x18002b318`
- `0x18002be90`
- `0x18002cae0`
- `0x18002df00`
- `0x18002e030`
- `0x180064e8c`
- `0x1800653d0`
- `0x18008b254`
- `0x18009c8c0`
- `0x1800a6438`
- `0x1800a658c`
- `0x1800afab0`
- `0x1801304ac`
- `0x18020aac0`
- `0x1802c3390`
- `0x1802c8240`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180130531`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1801305df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180130531`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1801305df`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801307ab`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801307ab`

## string_xrefs

- `0x18013061b`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x180130665`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x180130708`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1801307d1`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x180130840`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x18013088e`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1801308dd`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x180130991`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1801309dd`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x180130a1d`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x180130a5b`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::SinglePropertyFilterDef::ParsePropertySelector(
        Microsoft::Diagnostics::SinglePropertyFilterDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  unsigned int Element; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rdx
  int v9; // ebx
  __int64 v10; // r8
  unsigned int v11; // esi
  unsigned int v12; // r14d
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // ebx
  _QWORD *v16; // rdx
  int v17; // ebx
  __int64 v18; // r8
  int v19; // eax
  unsigned int v20; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  int InnerText; // eax
  unsigned int v25; // ebx
  __int64 v26; // rax
  _QWORD *v27; // rcx
  __int64 v28; // rax
  _QWORD *v29; // rcx
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // eax
  unsigned int v33; // ebx
  int v34; // eax
  unsigned int v35; // ebx
  int v36; // [rsp+20h] [rbp-D8h] BYREF
  __int64 v37; // [rsp+28h] [rbp-D0h] BYREF
  __int128 v38; // [rsp+30h] [rbp-C8h] BYREF
  __int128 v39; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v40[16]; // [rsp+50h] [rbp-A8h] BYREF
  _QWORD v41[2]; // [rsp+60h] [rbp-98h] BYREF
  unsigned __int64 v42; // [rsp+70h] [rbp-88h]
  unsigned __int64 v43; // [rsp+78h] [rbp-80h]
  __int128 v44; // [rsp+80h] [rbp-78h] BYREF
  __int64 v45; // [rsp+90h] [rbp-68h]
  __int64 v46; // [rsp+98h] [rbp-60h]
  _QWORD v47[3]; // [rsp+A0h] [rbp-58h] BYREF
  unsigned __int64 v48; // [rsp+B8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  std::wstring::wstring(v41);
  while ( 1 )
  {
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
    v7 = Element;
    if ( Element )
      break;
    Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v41);
    v8 = v41;
    if ( v43 > 7 )
      v8 = (_QWORD *)v41[0];
    v9 = v42;
    v10 = v42;
    if ( v42 >= 0xB )
      v10 = 11;
    if ( (unsigned int)_o__wcsnicmp(L"propertykey", v8, v10) || v9 != 11 )
    {
      if ( *((_BYTE *)a3 + 152) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27B,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
          (const char *)0x87C52407LL,
          v36);
        std::wstring::_Tidy_deallocate(v41);
        return 2277843975LL;
      }
      v34 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v35 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
          (const char *)(unsigned int)v34,
          v36);
        std::wstring::_Tidy_deallocate(v41);
        return v35;
      }
    }
    else
    {
      v11 = 0;
      v12 = 0;
      v44 = 0;
      v45 = 0;
      v46 = 0;
      v13 = std::_WChar_traits<wchar_t>::length(&Src);
      std::wstring::_Construct<1,wchar_t *>(&v44, &Src, v13);
      v37 = 0;
      while ( 1 )
      {
        v14 = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
        v15 = v14;
        if ( v14 )
          break;
        Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v41);
        v16 = v41;
        if ( v43 > 7 )
          v16 = (_QWORD *)v41[0];
        v17 = v42;
        v18 = v42;
        if ( v42 >= 4 )
          v18 = 4;
        if ( (unsigned int)_o__wcsnicmp(L"name", v16, v18) || v17 != 4 )
        {
          v38 = *(_OWORD *)std::wstring::operator std::wstring_view(v41, v40);
          v39 = *(_OWORD *)&off_180386D00;
          if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v39, &v38) )
          {
            if ( *((_BYTE *)a3 + 152) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x25B,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)0x87C52407LL,
                v36);
              std::wstring::_Tidy_deallocate(&v44);
              std::wstring::_Tidy_deallocate(v41);
              return 2277843975LL;
            }
            v32 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v33 = v32;
            if ( v32 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x25E,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)(unsigned int)v32,
                v36);
              std::wstring::_Tidy_deallocate(&v44);
              std::wstring::_Tidy_deallocate(v41);
              return v33;
            }
          }
          else
          {
            std::wstring::wstring(v47);
            InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v47);
            v25 = InnerText;
            if ( InnerText < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x24B,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)(unsigned int)InnerText,
                v36);
              std::wstring::_Tidy_deallocate(v47);
              std::wstring::_Tidy_deallocate(&v44);
              std::wstring::_Tidy_deallocate(v41);
              return v25;
            }
            v26 = std::_WChar_traits<wchar_t>::length(L"*");
            v27 = v47;
            if ( v48 > 7 )
              v27 = (_QWORD *)v47[0];
            if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v27, v47[2], L"*", v26) )
            {
              v28 = -2;
            }
            else
            {
              v29 = v47;
              if ( v48 > 7 )
                v29 = (_QWORD *)v47[0];
              v28 = (int)_o__wtoi(v29);
            }
            v37 = v28;
            v30 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v31 = v30;
            if ( v30 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x254,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)(unsigned int)v30,
                v36);
              std::wstring::_Tidy_deallocate(v47);
              std::wstring::_Tidy_deallocate(&v44);
              std::wstring::_Tidy_deallocate(v41);
              return v31;
            }
            ++v12;
            std::wstring::_Tidy_deallocate(v47);
          }
        }
        else
        {
          v19 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, &v44);
          v20 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x244,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
              (const char *)(unsigned int)v19,
              v36);
            std::wstring::_Tidy_deallocate(&v44);
            std::wstring::_Tidy_deallocate(v41);
            return v20;
          }
          v22 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v23 = v22;
          if ( v22 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x245,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
              (const char *)(unsigned int)v22,
              v36);
            std::wstring::_Tidy_deallocate(&v44);
            std::wstring::_Tidy_deallocate(v41);
            return v23;
          }
          ++v11;
        }
      }
      if ( (int)(v14 + 0x80000000) >= 0 && v14 != -2147024270 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x262,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
          (const char *)v14,
          v36);
        std::wstring::_Tidy_deallocate(&v44);
        std::wstring::_Tidy_deallocate(v41);
        return v15;
      }
      if ( v11 > 1
        || v12 > 1
        || v11 == 1 && !v45
        || *((_QWORD *)this + 22) == *((_QWORD *)this + 23) && !v11
        || !v11 && !v12 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x269,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
          (const char *)0x87C52402LL,
          v36);
        std::wstring::_Tidy_deallocate(&v44);
        std::wstring::_Tidy_deallocate(v41);
        return 2277843970LL;
      }
      if ( v11 == 1 )
        std::vector<Microsoft::Diagnostics::PropertyKey>::emplace_back<std::wstring>((char *)this + 176, &v44);
      if ( v12 == 1 )
        std::vector<Microsoft::Diagnostics::PropertyKey>::emplace_back<unsigned __int64 &>((char *)this + 176, &v37);
      std::wstring::_Tidy_deallocate(&v44);
    }
  }
  if ( (int)(Element + 0x80000000) < 0 || Element == -2147024270 )
  {
    *((_WORD *)this + 38) = *(_WORD *)Microsoft::Diagnostics::ITriggerInst::DetermineSelectorRoute(
                                        &v36,
                                        (char *)this + 176);
    std::wstring::_Tidy_deallocate(v41);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x283,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
      (const char *)Element,
      v36);
    std::wstring::_Tidy_deallocate(v41);
    return v7;
  }
}

```

## disassembly

```asm
0x1801304ac  mov     [rsp+arg_10], rbx
0x1801304b1  push    rsi
0x1801304b2  push    rdi
0x1801304b3  push    r12
0x1801304b5  push    r14
0x1801304b7  push    r15
0x1801304b9  sub     rsp, 0D0h
0x1801304c0  mov     rax, cs:__security_cookie
0x1801304c7  xor     rax, rsp
0x1801304ca  mov     [rsp+0F8h+var_38], rax
0x1801304d2  mov     r12, r8
0x1801304d5  mov     rdi, rdx
0x1801304d8  mov     r15, rcx
0x1801304db  lea     rcx, [rsp+0F8h+var_98]; void *
0x1801304e0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801304e5  nop
0x1801304e6  mov     esi, 0Bh
0x1801304eb  mov     rcx, rdi; this
0x1801304ee  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x1801304f3  mov     ebx, eax
0x1801304f5  test    eax, eax
0x1801304f7  jnz     loc_180130A3D
0x1801304fd  lea     rdx, [rsp+0F8h+var_98]
0x180130502  mov     rcx, rdi
0x180130505  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x18013050a  lea     rdx, [rsp+0F8h+var_98]
0x18013050f  cmp     [rsp+0F8h+var_80], 7
0x180130515  cmova   rdx, [rsp+0F8h+var_98]
0x18013051b  mov     rbx, [rsp+0F8h+var_88]
0x180130520  mov     r8, rbx
0x180130523  cmp     rbx, rsi
0x180130526  cmovnb  r8, rsi
0x18013052a  mov     rcx, cs:off_180370630; "propertykey"
0x180130531  call    cs:__imp__o__wcsnicmp
0x180130537  test    eax, eax
0x180130539  jnz     loc_1801309C2
0x18013053f  mov     eax, esi
0x180130541  sub     eax, ebx
0x180130543  test    eax, eax
0x180130545  jnz     loc_1801309C2
0x18013054b  xor     esi, esi
0x18013054d  xor     r14d, r14d
0x180130550  xorps   xmm0, xmm0
0x180130553  movups  [rsp+0F8h+var_78], xmm0
0x18013055b  mov     [rsp+0F8h+var_68], rsi
0x180130563  mov     [rsp+0F8h+var_60], rsi
0x18013056b  lea     rcx, Src
0x180130572  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180130577  mov     r8, rax
0x18013057a  lea     rdx, Src
0x180130581  lea     rcx, [rsp+0F8h+var_78]
0x180130589  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18013058e  nop
0x18013058f  mov     [rsp+0F8h+var_D0], r14
0x180130594  mov     rcx, rdi; this
0x180130597  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x18013059c  mov     ebx, eax
0x18013059e  test    eax, eax
0x1801305a0  jnz     loc_1801308BF
0x1801305a6  lea     rdx, [rsp+0F8h+var_98]
0x1801305ab  mov     rcx, rdi
0x1801305ae  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x1801305b3  lea     rdx, [rsp+0F8h+var_98]
0x1801305b8  cmp     [rsp+0F8h+var_80], 7
0x1801305be  cmova   rdx, [rsp+0F8h+var_98]
0x1801305c4  mov     rbx, [rsp+0F8h+var_88]
0x1801305c9  mov     r8, rbx
0x1801305cc  mov     eax, 4
0x1801305d1  cmp     rbx, rax
0x1801305d4  cmovnb  r8, rax
0x1801305d8  mov     rcx, cs:off_180370620; "name"
0x1801305df  call    cs:__imp__o__wcsnicmp
0x1801305e5  test    eax, eax
0x1801305e7  jnz     loc_18013069D
0x1801305ed  mov     eax, 4
0x1801305f2  sub     eax, ebx
0x1801305f4  jnz     loc_18013069D
0x1801305fa  lea     rdx, [rsp+0F8h+var_78]
0x180130602  mov     rcx, rdi
0x180130605  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18013060a  mov     ebx, eax
0x18013060c  test    eax, eax
0x18013060e  jns     short loc_18013064C
0x180130610  mov     rcx, [rsp+0F8h]; this
0x180130618  mov     r9d, eax; char *
0x18013061b  lea     r8, aOnecoreBaseTel_252; "onecore\\base\\telemetry\\utc\\service"...
0x180130622  mov     edx, 244h; void *
0x180130627  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013062c  nop
0x18013062d  lea     rcx, [rsp+0F8h+var_78]
0x180130635  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013063a  nop
0x18013063b  lea     rcx, [rsp+0F8h+var_98]
0x180130640  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130645  mov     eax, ebx
0x180130647  jmp     loc_180130AB0
0x18013064c  mov     rcx, rdi; this
0x18013064f  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x180130654  mov     ebx, eax
0x180130656  test    eax, eax
0x180130658  jns     short loc_180130696
0x18013065a  mov     rcx, [rsp+0F8h]; this
0x180130662  mov     r9d, eax; char *
0x180130665  lea     r8, aOnecoreBaseTel_252; "onecore\\base\\telemetry\\utc\\service"...
0x18013066c  mov     edx, 245h; void *
0x180130671  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130676  nop
0x180130677  lea     rcx, [rsp+0F8h+var_78]
0x18013067f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130684  nop
0x180130685  lea     rcx, [rsp+0F8h+var_98]
0x18013068a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013068f  mov     eax, ebx
0x180130691  jmp     loc_180130AB0
0x180130696  inc     esi
0x180130698  jmp     loc_180130594
0x18013069d  lea     rdx, [rsp+0F8h+var_A8]
0x1801306a2  lea     rcx, [rsp+0F8h+var_98]
0x1801306a7  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801306ac  movups  xmm0, xmmword ptr [rax]
0x1801306af  movdqu  [rsp+0F8h+var_C8], xmm0
0x1801306b5  movups  xmm1, xmmword ptr cs:off_180386D00; "index"
0x1801306bc  movdqu  [rsp+0F8h+var_B8], xmm1
0x1801306c2  lea     rdx, [rsp+0F8h+var_C8]
0x1801306c7  lea     rcx, [rsp+0F8h+var_B8]
0x1801306cc  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1801306d1  test    eax, eax
0x1801306d3  jnz     loc_180130825
0x1801306d9  lea     rcx, [rsp+0F8h+var_58]; void *
0x1801306e1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801306e6  nop
0x1801306e7  lea     rdx, [rsp+0F8h+var_58]
0x1801306ef  mov     rcx, rdi
0x1801306f2  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1801306f7  mov     ebx, eax
0x1801306f9  test    eax, eax
0x1801306fb  jns     short loc_180130747
0x1801306fd  mov     rcx, [rsp+0F8h]; this
0x180130705  mov     r9d, eax; char *
0x180130708  lea     r8, aOnecoreBaseTel_252; "onecore\\base\\telemetry\\utc\\service"...
0x18013070f  mov     edx, 24Bh; void *
0x180130714  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130719  nop
0x18013071a  lea     rcx, [rsp+0F8h+var_58]
0x180130722  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130727  nop
0x180130728  lea     rcx, [rsp+0F8h+var_78]
0x180130730  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130735  nop
0x180130736  lea     rcx, [rsp+0F8h+var_98]
0x18013073b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130740  mov     eax, ebx
0x180130742  jmp     loc_180130AB0
0x180130747  lea     rcx, pszMore; "*"
0x18013074e  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180130753  lea     rcx, [rsp+0F8h+var_58]
0x18013075b  cmp     [rsp+0F8h+var_40], 7
0x180130764  cmova   rcx, [rsp+0F8h+var_58]
0x18013076d  mov     r9, rax
0x180130770  lea     r8, pszMore; "*"
0x180130777  mov     rdx, [rsp+0F8h+var_48]
0x18013077f  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180130784  test    al, al
0x180130786  jz      short loc_180130791
0x180130788  mov     rax, 0FFFFFFFFFFFFFFFEh
0x18013078f  jmp     short loc_1801307B3
0x180130791  lea     rcx, [rsp+0F8h+var_58]
0x180130799  cmp     [rsp+0F8h+var_40], 7
0x1801307a2  cmova   rcx, [rsp+0F8h+var_58]
0x1801307ab  call    cs:__imp__o__wtoi
0x1801307b1  cdqe
0x1801307b3  mov     [rsp+0F8h+var_D0], rax
0x1801307b8  mov     rcx, rdi; this
0x1801307bb  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1801307c0  mov     ebx, eax
0x1801307c2  test    eax, eax
0x1801307c4  jns     short loc_180130810
0x1801307c6  mov     rcx, [rsp+0F8h]; this
0x1801307ce  mov     r9d, eax; char *
0x1801307d1  lea     r8, aOnecoreBaseTel_252; "onecore\\base\\telemetry\\utc\\service"...
0x1801307d8  mov     edx, 254h; void *
0x1801307dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801307e2  nop
0x1801307e3  lea     rcx, [rsp+0F8h+var_58]
0x1801307eb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801307f0  nop
0x1801307f1  lea     rcx, [rsp+0F8h+var_78]
0x1801307f9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801307fe  nop
0x1801307ff  lea     rcx, [rsp+0F8h+var_98]
0x180130804  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130809  mov     eax, ebx
0x18013080b  jmp     loc_180130AB0
0x180130810  inc     r14d
0x180130813  lea     rcx, [rsp+0F8h+var_58]
0x18013081b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130820  jmp     loc_180130594
0x180130825  cmp     byte ptr [r12+98h], 0
0x18013082e  jz      short loc_180130871
0x180130830  mov     rcx, [rsp+0F8h]; this
0x180130838  mov     ebx, 87C52407h
0x18013083d  mov     r9d, ebx; char *
0x180130840  lea     r8, aOnecoreBaseTel_252; "onecore\\base\\telemetry\\utc\\service"...
0x180130847  mov     edx, 25Bh; void *
0x18013084c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130851  nop
0x180130852  lea     rcx, [rsp+0F8h+var_78]
0x18013085a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013085f  nop
0x180130860  lea     rcx, [rsp+0F8h+var_98]
0x180130865  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013086a  mov     eax, ebx
0x18013086c  jmp     loc_180130AB0
0x180130871  mov     rcx, rdi; this
0x180130874  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x180130879  mov     ebx, eax
0x18013087b  test    eax, eax
0x18013087d  jns     loc_180130594
0x180130883  mov     rcx, [rsp+0F8h]; this
0x18013088b  mov     r9d, eax; char *
0x18013088e  lea     r8, aOnecoreBaseTel_252; "onecore\\base\\telemetry\\utc\\service"...
0x180130895  mov     edx, 25Eh; void *
0x18013089a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013089f  nop
0x1801308a0  lea     rcx, [rsp+0F8h+var_78]
0x1801308a8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801308ad  nop
0x1801308ae  lea     rcx, [rsp+0F8h+var_98]
0x1801308b3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801308b8  mov     eax, ebx
0x1801308ba  jmp     loc_180130AB0
0x1801308bf  mov     ecx, 80000000h
0x1801308c4  add     eax, ecx
0x1801308c6  test    ecx, eax
0x1801308c8  jnz     short loc_18013090E
0x1801308ca  cmp     ebx, 80070272h
0x1801308d0  jz      short loc_18013090E
0x1801308d2  mov     rcx, [rsp+0F8h]; this
0x1801308da  mov     r9d, ebx; char *
0x1801308dd  lea     r8, aOnecoreBaseTel_252; "onecore\\base\\telemetry\\utc\\service"...
0x1801308e4  mov     edx, 262h; void *
0x1801308e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801308ee  nop
0x1801308ef  lea     rcx, [rsp+0F8h+var_78]
0x1801308f7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801308fc  nop
0x1801308fd  lea     rcx, [rsp+0F8h+var_98]
0x180130902  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130907  mov     eax, ebx
0x180130909  jmp     loc_180130AB0
0x18013090e  cmp     esi, 1
0x180130911  ja      short loc_180130981
0x180130913  cmp     r14d, 1
0x180130917  ja      short loc_180130981
0x180130919  cmp     esi, 1
0x18013091c  jnz     short loc_180130929
0x18013091e  cmp     [rsp+0F8h+var_68], 0
0x180130927  jz      short loc_180130981
0x180130929  lea     rbx, [r15+0B0h]
0x180130930  mov     rax, [rbx+8]
0x180130934  cmp     [rbx], rax
0x180130937  jnz     short loc_18013093D
0x180130939  test    esi, esi
0x18013093b  jz      short loc_180130981
0x18013093d  test    esi, esi
0x18013093f  jnz     short loc_180130946
0x180130941  test    r14d, r14d
0x180130944  jz      short loc_180130981
0x180130946  cmp     esi, 1
0x180130949  jnz     short loc_18013095B
0x18013094b  lea     rdx, [rsp+0F8h+var_78]
0x180130953  mov     rcx, rbx
0x180130956  call    ??$emplace_back@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@UPropertyKey@Diagnostics@Microsoft@@V?$allocator@UPropertyKey@Diagnostics@Microsoft@@@std@@@std@@QEAAAEAUPropertyKey@Diagnostics@Microsoft@@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::vector<Microsoft::Diagnostics::PropertyKey>::emplace_back<std::wstring>(std::wstring &&)
0x18013095b  cmp     r14d, 1
0x18013095f  jnz     short loc_18013096F
0x180130961  lea     rdx, [rsp+0F8h+var_D0]
0x180130966  mov     rcx, rbx
0x180130969  call    ??$emplace_back@AEA_K@?$vector@UPropertyKey@Diagnostics@Microsoft@@V?$allocator@UPropertyKey@Diagnostics@Microsoft@@@std@@@std@@QEAAAEAUPropertyKey@Diagnostics@Microsoft@@AEA_K@Z; std::vector<Microsoft::Diagnostics::PropertyKey>::emplace_back<unsigned __int64 &>(unsigned __int64 &)
0x18013096e  nop
0x18013096f  lea     rcx, [rsp+0F8h+var_78]
0x180130977  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013097c  jmp     loc_1801304E6
0x180130981  mov     rcx, [rsp+0F8h]; this
0x180130989  mov     ebx, 87C52402h
0x18013098e  mov     r9d, ebx; char *
0x180130991  lea     r8, aOnecoreBaseTel_252; "onecore\\base\\telemetry\\utc\\service"...
0x180130998  mov     edx, 269h; void *
0x18013099d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801309a2  nop
0x1801309a3  lea     rcx, [rsp+0F8h+var_78]
0x1801309ab  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801309b0  nop
0x1801309b1  lea     rcx, [rsp+0F8h+var_98]
0x1801309b6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801309bb  mov     eax, ebx
0x1801309bd  jmp     loc_180130AB0
0x1801309c2  cmp     byte ptr [r12+98h], 0
0x1801309cb  jz      short loc_180130A00
0x1801309cd  mov     rcx, [rsp+0F8h]; this
0x1801309d5  mov     ebx, 87C52407h
  ... truncated ...
```
