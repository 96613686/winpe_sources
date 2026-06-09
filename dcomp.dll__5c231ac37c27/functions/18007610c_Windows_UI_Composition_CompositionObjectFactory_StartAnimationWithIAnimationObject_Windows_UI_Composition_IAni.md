# Windows::UI::Composition::CompositionObjectFactory::StartAnimationWithIAnimationObject(Windows::UI::Composition::IAnimationObject *,HSTRING__ *,Windows::UI::Composition::CompositionAnimation *,Windows::UI::Composition::CompositionPropertyAnimator * *)

- ea: `0x18007610c`
- end: `0x1800764a0`
- name: `?StartAnimationWithIAnimationObject@CompositionObjectFactory@Composition@UI@Windows@@SAJPEAUIAnimationObject@234@PEAUHSTRING__@@PEAVCompositionAnimation@234@PEAPEAVCompositionPropertyAnimator@234@@Z`
- size: `916`
- prototype: `__int64 __fastcall(struct IUnknown *, HSTRING this, struct Windows::UI::Composition::CompositionAnimation *, struct Windows::UI::Composition::CompositionPropertyAnimator **)`
- caller_count: `3`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180074300`
- `0x18008e4b4`
- `0x180117970`

## callees

- `0x1800092fc`
- `0x18000a68c`
- `0x18000bc00`
- `0x18000f810`
- `0x18001358c`
- `0x180033bb4`
- `0x180048980`
- `0x1800751ec`
- `0x1800752c8`
- `0x180075980`
- `0x18007610c`
- `0x1800764d4`
- `0x180076d4c`
- `0x180077e2c`
- `0x1800781f0`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007619d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007619d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076286`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076286`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007618a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076259`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007640f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076461`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007618a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076259`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007640f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076461`

## string_xrefs

- `0x180076236`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionobject.cpp`
- `0x1800763e3`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionobject.cpp`
- `0x180076448`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionobject.cpp`
- `0x180076475`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionobject.cpp`
- `0x18007621e`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtanimationhelper.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionObjectFactory::StartAnimationWithIAnimationObject(
        struct IUnknown *a1,
        Windows::UI::Composition::AnimationHelper *this,
        struct Windows::UI::Composition::CompositionAnimation *a3,
        struct Windows::UI::Composition::CompositionPropertyAnimator **a4)
{
  struct Microsoft::WRL2::ContextSession *v8; // rcx
  int v9; // eax
  Microsoft::WRL2::NestableRuntimeClass *v10; // rbx
  HSTRING v11; // rdx
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rax
  int v15; // eax
  unsigned int v16; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // rbx
  _QWORD *v20; // rdi
  Microsoft::WRL2::NestableRuntimeClass *v21; // rsi
  __int64 (__fastcall *v22)(Microsoft::WRL2::NestableRuntimeClass *, _QWORD, struct Windows::UI::Composition::CompositionAnimation *, _BYTE *); // rbx
  int v23; // eax
  Microsoft::WRL2::NestableRuntimeClass *v24; // rcx
  int v25; // eax
  Microsoft::WRL2::NestableRuntimeClass *v26; // rcx
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  Microsoft::WRL2::NestableRuntimeClass *v29; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-C8h] BYREF
  Microsoft::WRL2::NestableRuntimeClass *v31[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct Windows::UI::Composition::CompositionAnimation *v32; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v33[72]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v34[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v35[8]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v29 = 0;
  v31[0] = 0;
  Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(v31);
  v8 = (struct Microsoft::WRL2::ContextSession *)*((_QWORD *)a3 + 3);
  v31[0] = 0;
  v9 = Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
         v8,
         a1,
         (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::CompositionObject::s_InterfaceType,
         v31);
  v10 = v31[0];
  if ( v9 >= 0 )
  {
    v25 = (*(__int64 (__fastcall **)(Microsoft::WRL2::NestableRuntimeClass *, Windows::UI::Composition::AnimationHelper *, struct Windows::UI::Composition::CompositionAnimation *, _QWORD))(*(_QWORD *)v31[0] + 152LL))(
            v31[0],
            this,
            a3,
            0);
    v13 = v25;
    if ( v25 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53B,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionobject.cpp",
        (const char *)(unsigned int)v25,
        (int)a4);
    goto LABEL_16;
  }
  WindowsDeleteString(0);
  newString = 0;
  WindowsDuplicateString((HSTRING)this, &newString);
  v12 = Windows::UI::Composition::AnimationHelper::IAnimationObjectPropertyNameCheck(this, v11);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x542,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionobject.cpp",
      (const char *)(unsigned int)v12,
      v27);
    WindowsDeleteString(newString);
    newString = 0;
LABEL_16:
    if ( v10 )
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v10);
    return v13;
  }
  Windows::UI::Composition::CompositionAnimation::TryPopulateAnimationObjectParametersInfo(a3, 1);
  v14 = std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>(v35);
  v32 = a3;
  std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(
    v33,
    v14);
  std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(v35);
  v34[0] = 1;
  v34[1] = &newString;
  v35[0] = 1;
  v35[1] = &v32;
  v15 = Windows::UI::Composition::AnimationHelper::ResolveProperties_Callback_Base(v35, 0, a1, v34);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtanimationhelper.cpp",
      (const char *)(unsigned int)v15,
      v27);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55A,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionobject.cpp",
      (const char *)v16,
      v28);
    std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(v33);
    WindowsDeleteString(newString);
    newString = 0;
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(v31);
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v29);
    return v16;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(newString, 0);
  std::wstring::wstring(v35, StringRawBuffer);
  std::wstring::wstring(v34, L"this.target");
  v19 = std::unordered_map<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo>::at(v33, v34);
  std::wstring::_Tidy_deallocate(v34);
  v20 = (_QWORD *)std::unordered_map<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo>::at(v19 + 8, v35);
  Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionObject>::operator=(v31, v20[2]);
  v21 = v31[0];
  v22 = *(__int64 (__fastcall **)(Microsoft::WRL2::NestableRuntimeClass *, _QWORD, struct Windows::UI::Composition::CompositionAnimation *, _BYTE *))(*(_QWORD *)v31[0] + 152LL);
  Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v29);
  v23 = v22(v21, *v20, a3, v33);
  v16 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56F,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionobject.cpp",
      (const char *)(unsigned int)v23,
      (int)&v29);
    std::wstring::_Tidy_deallocate(v35);
    std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(v33);
    WindowsDeleteString(newString);
    newString = 0;
    if ( v21 )
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v21);
    v26 = v29;
    if ( v29 )
    {
      v29 = 0;
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v26);
    }
    return v16;
  }
  if ( a4 )
  {
    *a4 = v29;
    v29 = 0;
  }
  std::wstring::_Tidy_deallocate(v35);
  std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(v33);
  WindowsDeleteString(newString);
  newString = 0;
  if ( v21 )
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v21);
  v24 = v29;
  if ( v29 )
  {
    v29 = 0;
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v24);
  }
  return 0;
}

```

## disassembly

```asm
0x18007610c  push    rbp
0x18007610e  push    rbx
0x18007610f  push    rsi
0x180076110  push    rdi
0x180076111  push    r12
0x180076113  push    r14
0x180076115  push    r15
0x180076117  lea     rbp, [rsp-10h]
0x18007611c  sub     rsp, 110h
0x180076123  mov     rax, cs:__security_cookie
0x18007612a  xor     rax, rsp
0x18007612d  mov     [rbp+40h+var_40], rax
0x180076131  mov     rsi, rcx
0x180076134  xor     r12d, r12d
0x180076137  lea     rcx, [rsp+140h+var_100]; void *
0x18007613c  mov     [rsp+140h+var_110], r12
0x180076141  mov     [rsp+140h+var_100], r12
0x180076146  mov     r14, r9
0x180076149  mov     r15, r8
0x18007614c  mov     rdi, rdx
0x18007614f  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180076154  mov     rcx, [r15+18h]; struct Microsoft::WRL2::ContextSession *
0x180076158  lea     r9, [rsp+140h+var_100]; struct Microsoft::WRL2::ContextRuntimeClass **
0x18007615d  lea     r8, ?s_InterfaceType@CompositionObject@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x180076164  mov     [rsp+140h+var_100], r12
0x180076169  mov     rdx, rsi; struct IUnknown *
0x18007616c  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x180076171  mov     rbx, [rsp+140h+var_100]
0x180076176  mov     [rsp+140h+var_100], rbx
0x18007617b  test    eax, eax
0x18007617d  jns     loc_180076390
0x180076183  xor     ecx, ecx; string
0x180076185  mov     [rsp+140h+newString], r12
0x18007618a  call    cs:__imp_WindowsDeleteString
0x180076190  lea     rdx, [rsp+140h+newString]; newString
0x180076195  mov     [rsp+140h+newString], r12
0x18007619a  mov     rcx, rdi; string
0x18007619d  call    cs:__imp_WindowsDuplicateString
0x1800761a3  mov     rcx, rdi; this
0x1800761a6  call    ?IAnimationObjectPropertyNameCheck@AnimationHelper@Composition@UI@Windows@@YAJPEAUHSTRING__@@@Z; Windows::UI::Composition::AnimationHelper::IAnimationObjectPropertyNameCheck(HSTRING__ *)
0x1800761ab  mov     edi, eax
0x1800761ad  test    eax, eax
0x1800761af  js      loc_180076444
0x1800761b5  lea     ebx, [r12+1]
0x1800761ba  mov     rcx, r15; this
0x1800761bd  mov     dl, bl; bool
0x1800761bf  call    ?TryPopulateAnimationObjectParametersInfo@CompositionAnimation@Composition@UI@Windows@@QEAAX_N@Z; Windows::UI::Composition::CompositionAnimation::TryPopulateAnimationObjectParametersInfo(bool)
0x1800761c4  lea     rcx, [rbp+40h+var_80]
0x1800761c8  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>(void)
0x1800761cd  mov     rdx, rax
0x1800761d0  mov     [rsp+140h+var_F0], r15
0x1800761d5  lea     rcx, [rsp+140h+var_E8]
0x1800761da  call    ??0?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@IEAA@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>> &&)
0x1800761df  lea     rcx, [rbp+40h+var_80]
0x1800761e3  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(void)
0x1800761e8  lea     rax, [rsp+140h+newString]
0x1800761ed  mov     [rbp+40h+var_A0], rbx
0x1800761f1  mov     [rbp+40h+var_98], rax
0x1800761f5  lea     r9, [rbp+40h+var_A0]
0x1800761f9  lea     rax, [rsp+140h+var_F0]
0x1800761fe  mov     [rbp+40h+var_80], rbx
0x180076202  mov     r8, rsi
0x180076205  mov     [rbp+40h+var_78], rax
0x180076209  xor     edx, edx
0x18007620b  lea     rcx, [rbp+40h+var_80]
0x18007620f  call    ?ResolveProperties_Callback_Base@AnimationHelper@Composition@UI@Windows@@YAJV?$span@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@$0?0@gsl@@PEAVCompositionObject@234@PEAUIAnimationObject@234@V?$span@VHString@Wrappers@WRL@Microsoft@@$0?0@6@@Z; Windows::UI::Composition::AnimationHelper::ResolveProperties_Callback_Base(gsl::span<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>,-1>,Windows::UI::Composition::CompositionObject *,Windows::UI::Composition::IAnimationObject *,gsl::span<Microsoft::WRL::Wrappers::HString,-1>)
0x180076214  mov     ebx, eax
0x180076216  test    eax, eax
0x180076218  jns     short loc_18007627F
0x18007621a  mov     rcx, [rbp+48h]; this
0x18007621e  lea     r8, aOnecoreuapWind_275; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180076225  mov     r9d, eax; char *
0x180076228  mov     edx, 90h; void *
0x18007622d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076232  mov     rcx, [rbp+48h]; this
0x180076236  lea     r8, aOnecoreuapWind_78; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18007623d  mov     r9d, ebx; char *
0x180076240  mov     edx, 55Ah; void *
0x180076245  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007624a  lea     rcx, [rsp+140h+var_E8]
0x18007624f  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(void)
0x180076254  mov     rcx, [rsp+140h+newString]; string
0x180076259  call    cs:__imp_WindowsDeleteString
0x18007625f  lea     rcx, [rsp+140h+var_100]; void *
0x180076264  mov     [rsp+140h+newString], r12
0x180076269  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18007626e  lea     rcx, [rsp+140h+var_110]; void *
0x180076273  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180076278  mov     eax, ebx
0x18007627a  jmp     loc_180076372
0x18007627f  mov     rcx, [rsp+140h+newString]; string
0x180076284  xor     edx, edx; length
0x180076286  call    cs:__imp_WindowsGetStringRawBuffer
0x18007628c  mov     rdx, rax
0x18007628f  lea     rcx, [rbp+40h+var_80]
0x180076293  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076298  lea     rdx, aThisTarget; "this.target"
0x18007629f  lea     rcx, [rbp+40h+var_A0]
0x1800762a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800762a8  lea     rdx, [rbp+40h+var_A0]
0x1800762ac  lea     rcx, [rsp+140h+var_E8]
0x1800762b1  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@@std@@@2@@std@@QEBAAEBURedirectedPropertyInfo@Composition@UI@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::unordered_map<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo>::at(std::wstring const &)
0x1800762b6  lea     rcx, [rbp+40h+var_A0]
0x1800762ba  mov     rbx, rax
0x1800762bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800762c2  lea     rcx, [rbx+8]
0x1800762c6  lea     rdx, [rbp+40h+var_80]
0x1800762ca  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@@std@@@2@@std@@QEBAAEBURedirectedPropertyInfo@Composition@UI@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::unordered_map<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo>::at(std::wstring const &)
0x1800762cf  lea     rcx, [rsp+140h+var_100]
0x1800762d4  mov     rdi, rax
0x1800762d7  mov     rdx, [rax+10h]
0x1800762db  call    ??4?$RefPtr@VCompositionObject@Composition@UI@Windows@@@WRL2@Microsoft@@QEAAAEAV012@PEAVCompositionObject@Composition@UI@Windows@@@Z; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionObject>::operator=(Windows::UI::Composition::CompositionObject *)
0x1800762e0  mov     rsi, [rsp+140h+var_100]
0x1800762e5  mov     rcx, [rsi]
0x1800762e8  mov     rbx, [rcx+98h]
0x1800762ef  lea     rcx, [rsp+140h+var_110]; void *
0x1800762f4  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x1800762f9  mov     rdx, [rdi]
0x1800762fc  lea     rax, [rsp+140h+var_110]
0x180076301  mov     qword ptr [rsp+140h+var_120], rax; int
0x180076306  lea     r9, [rsp+140h+var_E8]
0x18007630b  mov     rax, rbx
0x18007630e  mov     r8, r15
0x180076311  mov     rcx, rsi
0x180076314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076319  mov     ebx, eax
0x18007631b  test    eax, eax
0x18007631d  js      loc_1800763DF
0x180076323  test    r14, r14
0x180076326  jnz     loc_18007648E
0x18007632c  lea     rcx, [rbp+40h+var_80]
0x180076330  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076335  lea     rcx, [rsp+140h+var_E8]
0x18007633a  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(void)
0x18007633f  mov     rcx, [rsp+140h+newString]; string
0x180076344  call    cs:__imp_WindowsDeleteString
0x18007634a  mov     [rsp+140h+newString], r12
0x18007634f  test    rsi, rsi
0x180076352  jz      short loc_18007635C
0x180076354  mov     rcx, rsi; this
0x180076357  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x18007635c  mov     rcx, [rsp+140h+var_110]; this
0x180076361  test    rcx, rcx
0x180076364  jz      short loc_180076370
0x180076366  mov     [rsp+140h+var_110], r12
0x18007636b  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180076370  xor     eax, eax
0x180076372  mov     rcx, [rbp+40h+var_40]
0x180076376  xor     rcx, rsp; StackCookie
0x180076379  call    __security_check_cookie
0x18007637e  add     rsp, 110h
0x180076385  pop     r15
0x180076387  pop     r14
0x180076389  pop     r12
0x18007638b  pop     rdi
0x18007638c  pop     rsi
0x18007638d  pop     rbx
0x18007638e  pop     rbp
0x18007638f  retn
0x180076390  mov     rax, [rbx]
0x180076393  xor     r9d, r9d
0x180076396  mov     r8, r15
0x180076399  mov     qword ptr [rsp+140h+var_120], r14; int
0x18007639e  mov     rdx, rdi
0x1800763a1  mov     rcx, rbx
0x1800763a4  mov     rax, [rax+98h]
0x1800763ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800763b0  mov     edi, eax
0x1800763b2  test    eax, eax
0x1800763b4  js      loc_180076471
0x1800763ba  test    rbx, rbx
0x1800763bd  jz      short loc_1800763C7
0x1800763bf  mov     rcx, rbx; this
0x1800763c2  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x1800763c7  mov     rcx, [rsp+140h+var_110]; this
0x1800763cc  test    rcx, rcx
0x1800763cf  jz      short loc_1800763DB
0x1800763d1  mov     [rsp+140h+var_110], r12
0x1800763d6  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x1800763db  mov     eax, edi
0x1800763dd  jmp     short loc_180076372
0x1800763df  mov     rcx, [rbp+48h]; this
0x1800763e3  lea     r8, aOnecoreuapWind_78; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800763ea  mov     r9d, ebx; char *
0x1800763ed  mov     edx, 56Fh; void *
0x1800763f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800763f7  lea     rcx, [rbp+40h+var_80]
0x1800763fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076400  lea     rcx, [rsp+140h+var_E8]
0x180076405  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(void)
0x18007640a  mov     rcx, [rsp+140h+newString]; string
0x18007640f  call    cs:__imp_WindowsDeleteString
0x180076415  mov     [rsp+140h+newString], r12
0x18007641a  test    rsi, rsi
0x18007641d  jz      short loc_180076427
0x18007641f  mov     rcx, rsi; this
0x180076422  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180076427  mov     rcx, [rsp+140h+var_110]; this
0x18007642c  test    rcx, rcx
0x18007642f  jz      loc_180076278
0x180076435  mov     [rsp+140h+var_110], r12
0x18007643a  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x18007643f  jmp     loc_180076278
0x180076444  mov     rcx, [rbp+48h]; this
0x180076448  lea     r8, aOnecoreuapWind_78; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18007644f  mov     r9d, edi; char *
0x180076452  mov     edx, 542h; void *
0x180076457  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007645c  mov     rcx, [rsp+140h+newString]; string
0x180076461  call    cs:__imp_WindowsDeleteString
0x180076467  mov     [rsp+140h+newString], r12
0x18007646c  jmp     loc_1800763BA
0x180076471  mov     rcx, [rbp+48h]; this
0x180076475  lea     r8, aOnecoreuapWind_78; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18007647c  mov     r9d, edi; char *
0x18007647f  mov     edx, 53Bh; void *
0x180076484  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076489  jmp     loc_1800763BA
0x18007648e  mov     rax, [rsp+140h+var_110]
0x180076493  mov     [r14], rax
0x180076496  mov     [rsp+140h+var_110], r12
0x18007649b  jmp     loc_18007632C
```
