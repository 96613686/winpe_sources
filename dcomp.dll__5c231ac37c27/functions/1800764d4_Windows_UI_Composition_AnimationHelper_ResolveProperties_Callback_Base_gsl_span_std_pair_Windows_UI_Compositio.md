# Windows::UI::Composition::AnimationHelper::ResolveProperties_Callback_Base(gsl::span<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Windows::UI::Composition::ParameterOverrideEntry,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Windows::UI::Composition::ParameterOverrideEntry>>>>,-1>,Windows::UI::Composition::CompositionObject *,Windows::UI::Composition::IAnimationObject *,gsl::span<Microsoft::WRL::Wrappers::HString,-1>)

- ea: `0x1800764d4`
- end: `0x1800767fb`
- name: `?ResolveProperties_Callback_Base@AnimationHelper@Composition@UI@Windows@@YAJV?$span@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@$0?0@gsl@@PEAVCompositionObject@234@PEAUIAnimationObject@234@V?$span@VHString@Wrappers@WRL@Microsoft@@$0?0@6@@Z`
- size: `807`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007610c`
- `0x1800add48`
- `0x1800bc75c`

## callees

- `0x18000f810`
- `0x18000f850`
- `0x18001358c`
- `0x180033bb4`
- `0x180075ac4`
- `0x180075ec4`
- `0x1800764d4`
- `0x180076804`
- `0x180076d4c`
- `0x180077e2c`
- `0x180077f9c`
- `0x18007810c`
- `0x18007817c`
- `0x1800781f0`
- `0x18008f00c`
- `0x1800dee2c`
- `0x1800e77ac`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800766b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800766b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800765f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800765f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800766a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800766a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076704`

## string_xrefs

- `0x180076789`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtanimationhelper.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::AnimationHelper::ResolveProperties_Callback_Base(
        unsigned __int64 *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 *a4)
{
  Microsoft::WRL2::NestableRuntimeClass **v6; // rax
  Microsoft::WRL2::NestableRuntimeClass *v7; // r14
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // rdi
  __int64 v12; // r15
  Microsoft::WRL2::NestableRuntimeClass *v13; // rcx
  unsigned __int64 i; // rdi
  __int64 v15; // r12
  __int64 v16; // rbx
  HSTRING *v17; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  const char *v21; // rcx
  HSTRING v22; // rax
  int v23; // ecx
  HSTRING v24; // rbx
  Microsoft::WRL2::NestableRuntimeClass *v25; // rbx
  Microsoft::WRL2::NestableRuntimeClass *v26; // rcx
  Microsoft::WRL2::NestableRuntimeClass *v28; // rcx
  int string; // [rsp+20h] [rbp-89h]
  HSTRING newString; // [rsp+30h] [rbp-79h] BYREF
  Microsoft::WRL2::NestableRuntimeClass *v31; // [rsp+38h] [rbp-71h] BYREF
  Microsoft::WRL2::NestableRuntimeClass *v32; // [rsp+40h] [rbp-69h] BYREF
  __int128 v33; // [rsp+48h] [rbp-61h] BYREF
  __int64 v34; // [rsp+58h] [rbp-51h]
  __int64 v35; // [rsp+60h] [rbp-49h]
  int v36[2]; // [rsp+68h] [rbp-41h]
  _QWORD v37[4]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v38[32]; // [rsp+90h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  __int64 v40; // [rsp+120h] [rbp+77h] BYREF

  v40 = a3;
  v35 = a2;
  v34 = 0;
  v33 = 0;
  v31 = 0;
  if ( !*a1 )
    ((void (*)(void))`gsl::details::get_terminate_handler'::`2'::handler)();
  v6 = (Microsoft::WRL2::NestableRuntimeClass **)a1[1];
  v7 = *v6;
  if ( *v6 )
    Microsoft::WRL2::NestableRuntimeClass::InternalAddRef(*v6);
  v32 = (Microsoft::WRL2::NestableRuntimeClass *)*((_QWORD *)v7 + 3);
  v8 = Microsoft::WRL2::Details::MakeAndInitialize2<Windows::UI::Composition::AnimationPropertyInfo,Windows::UI::Composition::AnimationPropertyInfo,Windows::UI::Composition::Compositor *>(
         &v31,
         &v32);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtanimationhelper.cpp",
      (const char *)(unsigned int)v8,
      string);
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v7);
    v28 = v31;
    if ( v31 )
    {
      v31 = 0;
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v28);
    }
    std::vector<unsigned int>::_Tidy(&v33);
    return v9;
  }
  else
  {
    v10 = a1[1];
    v11 = v10 + 72 * *a1;
    while ( v10 != v11 )
    {
      v23 = *(_DWORD *)(*(_QWORD *)v10 + 356LL);
      LODWORD(newString) = v23;
      if ( *((_QWORD *)&v33 + 1) == v34 )
      {
        std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(&v33, *((_QWORD *)&v33 + 1), &newString);
      }
      else
      {
        **((_DWORD **)&v33 + 1) = v23;
        *((_QWORD *)&v33 + 1) += 4LL;
      }
      v10 += 72LL;
    }
    v12 = *((_QWORD *)v7 + 3);
    if ( *(int *)(v12 + 72) > 0 && !*(_BYTE *)(v12 + 81) )
      Microsoft::WRL2::FailFast::Unexpected(0);
    ++*(_DWORD *)(v12 + 76);
    v13 = (Microsoft::WRL2::NestableRuntimeClass *)*((_QWORD *)v7 + 3);
    v37[2] = &v40;
    v37[3] = &v31;
    v37[0] = a1;
    v37[1] = a4;
    Microsoft::WRL2::ContextSession::LeaveSession_Callback__Windows::UI::Composition::AnimationHelper::ResolveProperties_Callback_Base_::_2_::_lambda_1___(v13);
    for ( i = 0; i < *a1; ++i )
    {
      v32 = 0;
      v15 = *(_QWORD *)gsl::span<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>,-1>::operator[](
                         a1,
                         i);
      v16 = gsl::span<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>,-1>::operator[](
              a1,
              i)
          + 8;
      *(_QWORD *)v36 = v16;
      if ( v40 )
      {
        v17 = (HSTRING *)gsl::span<Windows::UI::Composition::Interactions::ICompositionConditionalValue *,-1>::operator[](
                           a4,
                           i);
        StringRawBuffer = WindowsGetStringRawBuffer(*v17, 0);
        std::wstring::wstring(v38, StringRawBuffer);
        std::wstring::wstring(v37, L"this.target");
        v19 = std::unordered_map<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo>::at(v16, v37);
        std::wstring::_Tidy_deallocate(v37);
        v20 = std::unordered_map<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo>::at(v19 + 8, v38);
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionObject>::operator=(&v32, *(_QWORD *)(v20 + 16));
        std::wstring::_Tidy_deallocate(v38);
      }
      else
      {
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionObject>::operator=(&v32, v35);
      }
      v22 = 0;
      newString = 0;
      if ( *a4 )
      {
        if ( i >= *a4 )
        {
          ((void (*)(void))`gsl::details::get_terminate_handler'::`2'::handler)();
          __debugbreak();
        }
        v24 = *(HSTRING *)(a4[1] + 8 * i);
        WindowsDeleteString(0);
        newString = 0;
        WindowsDuplicateString(v24, &newString);
        v22 = newString;
      }
      if ( (__int64)(*((_QWORD *)&v33 + 1) - v33) >> 2 <= i )
        std::_Dwm_Xlength_error(v21);
      v25 = v32;
      Windows::UI::Composition::AnimationHelper::VerifyStateAfterExternalQuery(
        v15,
        v36[0],
        *(_DWORD *)(v33 + 4 * i),
        *(_DWORD *)(v15 + 356),
        v22,
        (__int64)v32);
      WindowsDeleteString(newString);
      newString = 0;
      if ( v25 )
        Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v25);
    }
    --*(_DWORD *)(v12 + 76);
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v7);
    v26 = v31;
    if ( v31 )
    {
      v31 = 0;
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v26);
    }
    std::vector<unsigned int>::_Tidy(&v33);
    return 0;
  }
}

```

## disassembly

```asm
0x1800764d4  mov     [rsp-8+arg_10], r8
0x1800764d9  push    rbp
0x1800764da  push    rbx
0x1800764db  push    rsi
0x1800764dc  push    rdi
0x1800764dd  push    r12
0x1800764df  push    r13
0x1800764e1  push    r14
0x1800764e3  push    r15
0x1800764e5  lea     rbp, [rsp-1Fh]
0x1800764ea  sub     rsp, 0C8h
0x1800764f1  mov     rax, cs:__security_cookie
0x1800764f8  xor     rax, rsp
0x1800764fb  mov     [rbp+57h+var_50], rax
0x1800764ff  xor     r12d, r12d
0x180076502  mov     [rbp+57h+var_A0], rdx
0x180076506  xorps   xmm0, xmm0
0x180076509  mov     r13, r9
0x18007650c  mov     rsi, rcx
0x18007650f  mov     [rbp+57h+var_A8], r12
0x180076513  movdqu  [rbp+57h+var_B8], xmm0
0x180076518  mov     [rbp+57h+var_C8], r12
0x18007651c  cmp     [rcx], r12
0x18007651f  jbe     loc_1800767EE
0x180076525  mov     rax, [rcx+8]
0x180076529  mov     r14, [rax]
0x18007652c  test    r14, r14
0x18007652f  jz      short loc_180076539
0x180076531  mov     rcx, r14; this
0x180076534  call    ?InternalAddRef@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalAddRef(void)
0x180076539  mov     rax, [r14+18h]
0x18007653d  lea     rdx, [rbp+57h+var_C0]
0x180076541  lea     rcx, [rbp+57h+var_C8]
0x180076545  mov     [rbp+57h+var_C0], rax
0x180076549  call    ??$MakeAndInitialize2@VAnimationPropertyInfo@Composition@UI@Windows@@V1234@PEAVCompositor@234@@Details@WRL2@Microsoft@@YAJPEAPEAVAnimationPropertyInfo@Composition@UI@Windows@@$$QEAPEAVCompositor@456@@Z; Microsoft::WRL2::Details::MakeAndInitialize2<Windows::UI::Composition::AnimationPropertyInfo,Windows::UI::Composition::AnimationPropertyInfo,Windows::UI::Composition::Compositor *>(Windows::UI::Composition::AnimationPropertyInfo * *,Windows::UI::Composition::Compositor * &&)
0x18007654e  mov     ebx, eax
0x180076550  test    eax, eax
0x180076552  js      loc_180076785
0x180076558  mov     rax, [rsi]
0x18007655b  mov     rbx, [rsi+8]
0x18007655f  lea     rcx, [rax+rax*8]
0x180076563  lea     rdi, [rbx+rcx*8]
0x180076567  cmp     rbx, rdi
0x18007656a  jnz     loc_18007666F
0x180076570  mov     r15, [r14+18h]
0x180076574  cmp     [r15+48h], r12d
0x180076578  jg      loc_1800767D6
0x18007657e  inc     dword ptr [r15+4Ch]
0x180076582  lea     rax, [rbp+57h+arg_10]
0x180076586  mov     rcx, [r14+18h]; this
0x18007658a  lea     rdx, [rbp+57h+var_90]
0x18007658e  mov     [rbp+57h+var_80], rax
0x180076592  lea     rax, [rbp+57h+var_C8]
0x180076596  mov     [rbp+57h+var_78], rax
0x18007659a  mov     [rbp+57h+var_90], rsi
0x18007659e  mov     [rbp+57h+var_88], r13
0x1800765a2  call    Microsoft__WRL2__ContextSession__LeaveSession_Callback__Windows__UI__Composition__AnimationHelper__ResolveProperties_Callback_Base____2____lambda_1___
0x1800765a7  mov     rdi, r12
0x1800765aa  cmp     [rsi], r12
0x1800765ad  jbe     loc_18007672A
0x1800765b3  mov     rdx, rdi
0x1800765b6  mov     [rbp+57h+var_C0], r12
0x1800765ba  mov     rcx, rsi
0x1800765bd  call    ??A?$span@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@$0?0@gsl@@QEBAAEAU?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@_K@Z; gsl::span<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>,-1>::operator[](unsigned __int64)
0x1800765c2  mov     rdx, rdi
0x1800765c5  mov     rcx, rsi
0x1800765c8  mov     r12, [rax]
0x1800765cb  call    ??A?$span@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@$0?0@gsl@@QEBAAEAU?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@_K@Z; gsl::span<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>,-1>::operator[](unsigned __int64)
0x1800765d0  cmp     [rbp+57h+arg_10], 0
0x1800765d5  lea     rbx, [rax+8]
0x1800765d9  mov     qword ptr [rbp+57h+var_98], rbx
0x1800765dd  jz      loc_180076773
0x1800765e3  mov     rdx, rdi
0x1800765e6  mov     rcx, r13
0x1800765e9  call    ??A?$span@PEAUICompositionConditionalValue@Interactions@Composition@UI@Windows@@$0?0@gsl@@QEBAAEAPEAUICompositionConditionalValue@Interactions@Composition@UI@Windows@@_K@Z; gsl::span<Windows::UI::Composition::Interactions::ICompositionConditionalValue *,-1>::operator[](unsigned __int64)
0x1800765ee  xor     edx, edx; length
0x1800765f0  mov     rcx, [rax]; string
0x1800765f3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800765f9  mov     rdx, rax
0x1800765fc  lea     rcx, [rbp+57h+var_70]
0x180076600  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076605  lea     rdx, aThisTarget; "this.target"
0x18007660c  lea     rcx, [rbp+57h+var_90]
0x180076610  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076615  lea     rdx, [rbp+57h+var_90]
0x180076619  mov     rcx, rbx
0x18007661c  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@@std@@@2@@std@@QEBAAEBURedirectedPropertyInfo@Composition@UI@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::unordered_map<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo>::at(std::wstring const &)
0x180076621  lea     rcx, [rbp+57h+var_90]
0x180076625  mov     rbx, rax
0x180076628  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007662d  lea     rcx, [rbx+8]
0x180076631  lea     rdx, [rbp+57h+var_70]
0x180076635  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@@std@@@2@@std@@QEBAAEBURedirectedPropertyInfo@Composition@UI@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::unordered_map<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo>::at(std::wstring const &)
0x18007663a  lea     rcx, [rbp+57h+var_C0]
0x18007663e  mov     rdx, [rax+10h]
0x180076642  call    ??4?$RefPtr@VCompositionObject@Composition@UI@Windows@@@WRL2@Microsoft@@QEAAAEAV012@PEAVCompositionObject@Composition@UI@Windows@@@Z; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionObject>::operator=(Windows::UI::Composition::CompositionObject *)
0x180076647  lea     rcx, [rbp+57h+var_70]
0x18007664b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076650  xor     eax, eax
0x180076652  mov     [rbp+57h+newString], rax
0x180076656  cmp     [r13+0], rax
0x18007665a  jz      short loc_1800766C2
0x18007665c  cmp     rdi, [r13+0]
0x180076660  jb      short loc_180076699
0x180076662  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x180076669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007666e  int     3; Trap to Debugger
0x18007666f  mov     rax, [rbx]
0x180076672  mov     rdx, qword ptr [rbp+57h+var_B8+8]
0x180076676  mov     ecx, [rax+164h]
0x18007667c  mov     dword ptr [rbp+57h+newString], ecx
0x18007667f  cmp     rdx, [rbp+57h+var_A8]
0x180076683  jz      loc_1800767C4
0x180076689  mov     [rdx], ecx
0x18007668b  add     qword ptr [rbp+57h+var_B8+8], 4
0x180076690  add     rbx, 48h ; 'H'
0x180076694  jmp     loc_180076567
0x180076699  mov     rax, [r13+8]
0x18007669d  xor     ecx, ecx; string
0x18007669f  mov     rbx, [rax+rdi*8]
0x1800766a3  call    cs:__imp_WindowsDeleteString
0x1800766a9  lea     rdx, [rbp+57h+newString]; newString
0x1800766ad  mov     [rbp+57h+newString], 0
0x1800766b5  mov     rcx, rbx; string
0x1800766b8  call    cs:__imp_WindowsDuplicateString
0x1800766be  mov     rax, [rbp+57h+newString]
0x1800766c2  mov     r9, qword ptr [rbp+57h+var_B8+8]
0x1800766c6  mov     r8, qword ptr [rbp+57h+var_B8]
0x1800766ca  sub     r9, r8
0x1800766cd  sar     r9, 2
0x1800766d1  cmp     r9, rdi
0x1800766d4  jbe     loc_1800767E8
0x1800766da  mov     rbx, [rbp+57h+var_C0]
0x1800766de  mov     rcx, r12; int
0x1800766e1  mov     r9d, [r12+164h]; int
0x1800766e9  mov     r8d, [r8+rdi*4]; int
0x1800766ed  mov     rdx, qword ptr [rbp+57h+var_98]; int
0x1800766f1  mov     [rsp+100h+var_D8], rbx; __int64
0x1800766f6  mov     [rsp+100h+string], rax; string
0x1800766fb  call    ?VerifyStateAfterExternalQuery@AnimationHelper@Composition@UI@Windows@@YAJPEAVCompositionAnimation@234@PEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@IIPEAUHSTRING__@@PEAVCompositionObject@234@@Z; Windows::UI::Composition::AnimationHelper::VerifyStateAfterExternalQuery(Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry> *,uint,uint,HSTRING__ *,Windows::UI::Composition::CompositionObject *)
0x180076700  mov     rcx, [rbp+57h+newString]; string
0x180076704  call    cs:__imp_WindowsDeleteString
0x18007670a  xor     r12d, r12d
0x18007670d  mov     [rbp+57h+newString], r12
0x180076711  test    rbx, rbx
0x180076714  jz      short loc_18007671E
0x180076716  mov     rcx, rbx; this
0x180076719  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x18007671e  inc     rdi
0x180076721  cmp     rdi, [rsi]
0x180076724  jb      loc_1800765B3
0x18007672a  dec     dword ptr [r15+4Ch]
0x18007672e  mov     rcx, r14; this
0x180076731  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180076736  mov     rcx, [rbp+57h+var_C8]; this
0x18007673a  test    rcx, rcx
0x18007673d  jz      short loc_180076748
0x18007673f  mov     [rbp+57h+var_C8], r12
0x180076743  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180076748  lea     rcx, [rbp+57h+var_B8]
0x18007674c  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180076751  xor     eax, eax
0x180076753  mov     rcx, [rbp+57h+var_50]
0x180076757  xor     rcx, rsp; StackCookie
0x18007675a  call    __security_check_cookie
0x18007675f  add     rsp, 0C8h
0x180076766  pop     r15
0x180076768  pop     r14
0x18007676a  pop     r13
0x18007676c  pop     r12
0x18007676e  pop     rdi
0x18007676f  pop     rsi
0x180076770  pop     rbx
0x180076771  pop     rbp
0x180076772  retn
0x180076773  mov     rdx, [rbp+57h+var_A0]
0x180076777  lea     rcx, [rbp+57h+var_C0]
0x18007677b  call    ??4?$RefPtr@VCompositionObject@Composition@UI@Windows@@@WRL2@Microsoft@@QEAAAEAV012@PEAVCompositionObject@Composition@UI@Windows@@@Z; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionObject>::operator=(Windows::UI::Composition::CompositionObject *)
0x180076780  jmp     loc_180076650
0x180076785  mov     rcx, [rbp+5Fh]; this
0x180076789  lea     r8, aOnecoreuapWind_275; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180076790  mov     r9d, ebx; char *
0x180076793  mov     edx, 0BDh; void *
0x180076798  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007679d  mov     rcx, r14; this
0x1800767a0  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x1800767a5  mov     rcx, [rbp+57h+var_C8]; this
0x1800767a9  test    rcx, rcx
0x1800767ac  jz      short loc_1800767B7
0x1800767ae  mov     [rbp+57h+var_C8], r12
0x1800767b2  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x1800767b7  lea     rcx, [rbp+57h+var_B8]
0x1800767bb  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x1800767c0  mov     eax, ebx
0x1800767c2  jmp     short loc_180076753
0x1800767c4  lea     r8, [rbp+57h+newString]
0x1800767c8  lea     rcx, [rbp+57h+var_B8]
0x1800767cc  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1800767d1  jmp     loc_180076690
0x1800767d6  cmp     [r15+51h], r12b
0x1800767da  jnz     loc_18007657E
0x1800767e0  xor     ecx, ecx; char *
0x1800767e2  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x1800767e8  call    ?_Dwm_Xlength_error@std@@YAXPEBD@Z; std::_Dwm_Xlength_error(char const *)
0x1800767ee  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x1800767f5  call    _guard_dispatch_icall$thunk$10345483385596137414
```
