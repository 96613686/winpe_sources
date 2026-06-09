# Windows::UI::Composition::ProxyObject::ConnectAnimation(HSTRING__ *,Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Windows::UI::Composition::ParameterOverrideEntry,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Windows::UI::Composition::ParameterOverrideEntry>>> *,Windows::UI::Composition::CompositionPropertyAnimator * *)

- ea: `0x180008bc0`
- end: `0x1800092f3`
- name: `?ConnectAnimation@ProxyObject@Composition@UI@Windows@@UEAAJPEAUHSTRING__@@PEAVCompositionAnimation@234@PEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@PEAPEAVCompositionPropertyAnimator@234@@Z`
- size: `1843`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006590`
- `0x1800078a4`
- `0x180008034`
- `0x180008bc0`
- `0x1800092fc`
- `0x18000a68c`
- `0x18000f810`
- `0x18001358c`
- `0x18001603c`
- `0x180016a08`
- `0x18002edf0`
- `0x180032ff0`
- `0x180056610`
- `0x18006c5b0`
- `0x1800751ec`
- `0x1800752c8`
- `0x1800add48`
- `0x1800c0590`
- `0x1800ce320`
- `0x1800e77ac`
- `0x1800ebd74`
- `0x1800f6f34`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180008faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180009002`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180008faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180009002`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180008d1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180008d1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008f36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008fca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000915d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008f36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008fca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000915d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008cef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008eb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008cef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008eb4`

## string_xrefs

- `0x180009190`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtanimationbindingmanager.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ProxyObject::ConnectAnimation(
        _QWORD *a1,
        HSTRING a2,
        __int64 a3,
        _BYTE *a4,
        Microsoft::WRL2::NestableRuntimeClass **a5)
{
  Windows::UI::Composition::CompositorCommon *v6; // rcx
  void *v10; // rsi
  __int64 v11; // rax
  void *v12; // r14
  __int64 (__fastcall *v13)(_QWORD *, HSTRING, int *, __int64 *); // rax
  unsigned __int8 v14; // al
  signed int i; // r15d
  PCWSTR StringRawBuffer; // rdi
  unsigned int v17; // edi
  HRESULT v18; // eax
  void *v19; // r15
  _WORD *v20; // rcx
  void *v21; // rdi
  unsigned int v22; // r15d
  int v23; // eax
  int *v24; // rcx
  Microsoft::WRL2::NestableRuntimeClass *v25; // rdi
  struct CSparseStorage::DataInfo *Slot; // rax
  __int64 v27; // r10
  int v28; // eax
  Microsoft::WRL2::NestableRuntimeClass *v29; // rcx
  _WORD *v31; // rax
  unsigned __int64 v32; // rcx
  const unsigned __int16 *v33; // r14
  unsigned __int64 v34; // rcx
  unsigned __int8 v35; // al
  __int64 v36; // rax
  int v37; // eax
  struct Windows::UI::Composition::ExpressionErrorInfo *v38; // rax
  const unsigned __int16 *v39; // r8
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 *v42; // [rsp+28h] [rbp-E0h]
  UINT32 length; // [rsp+48h] [rbp-C0h] BYREF
  int v44; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v45; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A8h]
  void *lpMem; // [rsp+68h] [rbp-A0h]
  Microsoft::WRL2::NestableRuntimeClass *v49; // [rsp+70h] [rbp-98h] BYREF
  HSTRING string; // [rsp+78h] [rbp-90h] BYREF
  int v51; // [rsp+80h] [rbp-88h]
  void *v52; // [rsp+88h] [rbp-80h]
  void *v53; // [rsp+90h] [rbp-78h]
  HSTRING newString[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v55; // [rsp+A8h] [rbp-60h] BYREF
  __int64 *v56; // [rsp+B0h] [rbp-58h]
  void *v57; // [rsp+B8h] [rbp-50h] BYREF
  int v58; // [rsp+C0h] [rbp-48h]
  struct Windows::UI::Composition::AnimationBindingManager *BindingManager; // [rsp+C8h] [rbp-40h]
  __int64 v60; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v61[72]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v62[64]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v63[112]; // [rsp+168h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E0h] [rbp+D8h]
  _BYTE *v66; // [rsp+200h] [rbp+F8h]

  v66 = a4;
  v6 = (Windows::UI::Composition::CompositorCommon *)a1[3];
  v49 = 0;
  newString[0] = 0;
  BindingManager = Windows::UI::Composition::CompositorCommon::GetBindingManager(v6);
  v10 = 0;
  v57 = 0;
  std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>(v62);
  if ( !a4 )
  {
    Windows::UI::Composition::CompositionAnimation::TryPopulateAnimationObjectParametersInfo(
      (Windows::UI::Composition::CompositionAnimation *)a3,
      0);
    if ( -858993459 * (unsigned int)((__int64)(*(_QWORD *)(a3 + 336) - *(_QWORD *)(a3 + 328)) >> 3) )
    {
      v36 = std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>(v63);
      v60 = a3;
      std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(
        v61,
        v36);
      std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(v63);
      v55 = 1;
      v56 = &v60;
      v37 = Windows::UI::Composition::AnimationHelper::ResolvePropertiesWithoutIAnimationObjectTarget_Callback(&v55, a1);
      v17 = v37;
      if ( v37 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1801B0FA0, 3u, v37, 0x1C9u, 0);
        std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(v61);
        goto LABEL_72;
      }
      std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::operator=(
        v62,
        v61);
      v66 = v62;
      std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(v61);
    }
  }
  v46 = 1;
  v53 = 0;
  v52 = 0;
  v11 = *a1;
  v42 = &v45;
  LODWORD(v47) = 0;
  v12 = 0;
  lpMem = 0;
  v13 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, int *, __int64 *))(v11 + 200);
  v55 = 0;
  LODWORD(v56) = 2;
  LODWORD(v45) = 18;
  v51 = 0;
  string = 0;
  length = 0;
  v44 = 0;
  v14 = v13(a1, a2, &v44, &v55);
  if ( ((unsigned __int8)-((v44 & 2) != 0) & v14) != 0 )
  {
    i = -1;
    StringRawBuffer = 0;
    LODWORD(v46) = 0;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, &length);
    for ( i = length - 1; ; --i )
    {
      if ( i < 0 )
      {
        LODWORD(v10) = 19;
        i = -1;
        goto LABEL_49;
      }
      if ( StringRawBuffer[i] == 46 )
        break;
    }
    if ( WindowsSubstringWithSpecifiedLength(a2, 0, i, &string) < 0 )
      Microsoft::WRL2::FailFast::OutOfMemory(v34);
    v42 = &v45;
    v35 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, int *, __int64 *))(*a1 + 200LL))(a1, string, &v44, &v55);
    LODWORD(v10) = (v35 & (unsigned __int8)-((v44 & 2) != 0)) == 0 ? 0x13 : 0;
LABEL_49:
    LODWORD(v46) = (_DWORD)v10;
  }
  if ( string )
    WindowsDeleteString(string);
  if ( (_DWORD)v10 )
  {
    LODWORD(v47) = length;
    if ( StringRawBuffer )
    {
      v31 = operator new[](0xF2u);
      lpMem = v31;
      v12 = v31;
      if ( !v31 )
        Microsoft::WRL2::FailFast::OutOfMemory(v32);
      *v31 = 0;
      v40 = 2147483646;
      v41 = 120;
      do
      {
        if ( !v40 )
          break;
        if ( !*StringRawBuffer )
          break;
        *v31++ = *StringRawBuffer++;
        --v40;
        --v41;
      }
      while ( v41 );
      v20 = v31 - 1;
      if ( v41 )
        v20 = v31;
      *v20 = 0;
    }
    v17 = -2147024809;
    v53 = 0;
    MilInstrumentationCheckHR_MaybeFailFast(
      4u,
      &Windows::UI::Composition::ExpressionAnimationParser::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      -2147024809,
      0xBCDu,
      0);
LABEL_20:
    if ( (_DWORD)v10 )
    {
      v38 = (struct Windows::UI::Composition::ExpressionErrorInfo *)WindowsGetStringRawBuffer(a2, 0);
      if ( (_DWORD)v10 == 4 || (_DWORD)v10 == 20 )
        Microsoft::WRL2::FailFast::Unexpected(0);
      Windows::UI::Composition::OriginateExpressionErrorInfo((Windows::UI::Composition *)&v46, v38, v39);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtanimationbindingmanager.cpp",
        (const char *)0x80070057LL,
        (int)v42);
      if ( lpMem )
        operator delete(lpMem);
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1801B0FA0, 3u, -2147024809, 0x1DAu, 0);
      v10 = v57;
      goto LABEL_72;
    }
    goto LABEL_21;
  }
  v17 = -2147024809;
  if ( i <= -1 )
  {
    v18 = WindowsDuplicateString(a2, newString);
    goto LABEL_10;
  }
  v53 = 0;
  length = 0;
  v33 = WindowsGetStringRawBuffer(a2, &length);
  v42 = &v46;
  Windows::UI::Composition::ExpressionAnimationParser::ParseSwizzle(&v33[i + 1], length - i, (unsigned int)v45, 0);
  LODWORD(v10) = v46;
  if ( (_DWORD)v46 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(
      4u,
      &Windows::UI::Composition::ExpressionAnimationParser::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      -2147024809,
      0xBE4u,
      0);
LABEL_51:
    v12 = lpMem;
    v19 = v52;
LABEL_13:
    if ( v19 )
      operator delete(v19, 8u);
    goto LABEL_20;
  }
  if ( length - i - 1 != v51 )
  {
    LODWORD(v47) = v51;
    LODWORD(v46) = 17;
    HIDWORD(v46) = length - i - 1;
    Windows::UI::Composition::ExpressionErrorInfo::SetErrorContext(
      (Windows::UI::Composition::ExpressionErrorInfo *)&v46,
      v33);
    MilInstrumentationCheckHR_MaybeFailFast(
      4u,
      &Windows::UI::Composition::ExpressionAnimationParser::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      -2147024809,
      0xBF9u,
      0);
    LODWORD(v10) = v46;
    goto LABEL_51;
  }
  v18 = WindowsSubstringWithSpecifiedLength(a2, 0, i, newString);
  v12 = lpMem;
  v53 = v52;
LABEL_10:
  if ( v18 < 0 )
    Microsoft::WRL2::FailFast::OutOfMemory(0);
  v46 = 0;
  v19 = 0;
  LODWORD(v47) = 0;
  LODWORD(v10) = 0;
  if ( v12 )
  {
    operator delete(v12);
    v12 = 0;
    lpMem = 0;
    goto LABEL_13;
  }
LABEL_21:
  v21 = v53;
  v10 = v53;
  v22 = v45;
  v57 = (void *)v55;
  string = (HSTRING)v53;
  v58 = (int)v56;
  if ( v12 )
    operator delete(v12);
  v23 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, HSTRING, void *, _BYTE *, Microsoft::WRL2::NestableRuntimeClass **))(*(_QWORD *)a3 + 256LL))(
          a3,
          a3,
          a1,
          newString[0],
          v21,
          v66,
          &v49);
  v17 = v23;
  if ( v23 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1801B0FA0, 3u, v23, 0x1E6u, 0);
  }
  else
  {
    v24 = *(int **)(a3 + 128);
    v25 = v49;
    if ( v24[1] < 0 )
    {
      Slot = CSparseStorage::AllocatedStorage::FindSlot((CSparseStorage::AllocatedStorage *)v24, 1u);
      (*(void (__fastcall **)(Microsoft::WRL2::NestableRuntimeClass *, _QWORD))(v27 + 240))(
        v25,
        *(_QWORD *)((char *)Slot + 4));
    }
    if ( *(_DWORD *)(a3 + 316) )
      Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(v25, 4, *(unsigned int *)(a3 + 316));
    v28 = Windows::UI::Composition::AnimationBindingManager::RegisterAnimationTarget(
            BindingManager,
            a1,
            &v57,
            v22,
            &string,
            v49);
    v17 = v28;
    if ( v28 >= 0 )
    {
      if ( a5 )
      {
        *a5 = v49;
        v49 = 0;
      }
      v17 = 0;
      goto LABEL_32;
    }
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1801B0FA0, 3u, v28, 0x1FBu, 0);
    v10 = string;
  }
LABEL_72:
  if ( v10 )
    operator delete(v10, 8u);
LABEL_32:
  if ( newString[0] )
    WindowsDeleteString(newString[0]);
  std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(v62);
  v29 = v49;
  if ( v49 )
  {
    v49 = 0;
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v29);
  }
  return v17;
}

```

## disassembly

```asm
0x180008bc0  mov     rax, rsp
0x180008bc3  mov     [rax+10h], rbx
0x180008bc7  mov     [rax+20h], r9
0x180008bcb  mov     [rax+8], rcx
0x180008bcf  push    rbp
0x180008bd0  push    rsi
0x180008bd1  push    rdi
0x180008bd2  push    r12
0x180008bd4  push    r13
0x180008bd6  push    r14
0x180008bd8  push    r15
0x180008bda  lea     rbp, [rax-0D8h]
0x180008be1  sub     rsp, 1A0h
0x180008be8  mov     rbx, rcx
0x180008beb  xor     r15d, r15d
0x180008bee  mov     rcx, [rcx+18h]; this
0x180008bf2  mov     rdi, r9
0x180008bf5  mov     [rsp+1D0h+var_168], r15
0x180008bfa  mov     r12, r8
0x180008bfd  mov     [rbp+0D0h+newString], r15
0x180008c01  mov     r13, rdx
0x180008c04  call    ?GetBindingManager@CompositorCommon@Composition@UI@Windows@@QEAAPEAVAnimationBindingManager@234@XZ; Windows::UI::Composition::CompositorCommon::GetBindingManager(void)
0x180008c09  lea     rcx, [rbp+0D0h+var_B0]
0x180008c0d  mov     [rbp+0D0h+var_110], rax
0x180008c11  mov     esi, r15d
0x180008c14  mov     [rbp+0D0h+var_120], r15
0x180008c18  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>(void)
0x180008c1d  lea     r14d, [r15+1]
0x180008c21  test    rdi, rdi
0x180008c24  jnz     short loc_180008C5A
0x180008c26  xor     edx, edx; bool
0x180008c28  mov     rcx, r12; this
0x180008c2b  call    ?TryPopulateAnimationObjectParametersInfo@CompositionAnimation@Composition@UI@Windows@@QEAAX_N@Z; Windows::UI::Composition::CompositionAnimation::TryPopulateAnimationObjectParametersInfo(bool)
0x180008c30  mov     rcx, [r12+150h]
0x180008c38  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008c42  sub     rcx, [r12+148h]
0x180008c4a  sar     rcx, 3
0x180008c4e  imul    rcx, rax
0x180008c52  test    ecx, ecx
0x180008c54  jnz     loc_1800090E0
0x180008c5a  mov     rax, r15
0x180008c5d  mov     [rsp+1D0h+var_180], r14
0x180008c62  mov     [rbp+0D0h+var_148], rax
0x180008c66  lea     rcx, [rsp+1D0h+var_188]
0x180008c6b  mov     [rbp+0D0h+var_150], rax
0x180008c6f  lea     r9, [rbp+0D0h+var_130]
0x180008c73  mov     rax, [rbx]
0x180008c76  lea     r8, [rsp+1D0h+var_18C]
0x180008c7b  mov     qword ptr [rsp+1D0h+var_1B0], rcx
0x180008c80  mov     rdx, r13
0x180008c83  mov     rcx, rbx
0x180008c86  mov     dword ptr [rsp+1D0h+var_178], r15d
0x180008c8b  mov     r14, r15
0x180008c8e  mov     [rsp+1D0h+lpMem], r15
0x180008c93  mov     rax, [rax+0C8h]
0x180008c9a  mov     [rbp+0D0h+var_130], r15
0x180008c9e  mov     dword ptr [rbp+0D0h+var_128], 2
0x180008ca5  mov     dword ptr [rsp+1D0h+var_188], 12h
0x180008cad  mov     [rsp+1D0h+var_158], r15d
0x180008cb2  mov     [rsp+1D0h+string], r15
0x180008cb7  mov     [rsp+1D0h+length], r15d
0x180008cbc  mov     [rsp+1D0h+var_18C], r15d
0x180008cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc6  mov     ecx, [rsp+1D0h+var_18C]
0x180008cca  and     cl, 2
0x180008ccd  neg     cl
0x180008ccf  sbb     cl, cl
0x180008cd1  test    al, cl
0x180008cd3  jz      loc_180008FC2
0x180008cd9  or      r15d, 0FFFFFFFFh
0x180008cdd  xor     eax, eax
0x180008cdf  mov     edi, eax
0x180008ce1  mov     dword ptr [rsp+1D0h+var_180], eax
0x180008ce5  mov     rcx, [rsp+1D0h+string]; string
0x180008cea  test    rcx, rcx
0x180008ced  jz      short loc_180008CF7
0x180008cef  call    cs:__imp_WindowsDeleteString
0x180008cf5  xor     eax, eax
0x180008cf7  mov     ebx, 4
0x180008cfc  test    esi, esi
0x180008cfe  jnz     loc_180008EF4
0x180008d04  mov     edi, 80070057h
0x180008d09  mov     rcx, r13; string
0x180008d0c  cmp     r15d, 0FFFFFFFFh
0x180008d10  jg      loc_180008F29
0x180008d16  lea     rdx, [rbp+0D0h+newString]; newString
0x180008d1a  call    cs:__imp_WindowsDuplicateString
0x180008d20  xor     ecx, ecx; unsigned __int64
0x180008d22  test    eax, eax
0x180008d24  js      loc_1800090AA
0x180008d2a  mov     [rsp+1D0h+var_180], rcx
0x180008d2f  mov     r15d, ecx
0x180008d32  mov     dword ptr [rsp+1D0h+var_178], ecx
0x180008d36  mov     esi, ecx
0x180008d38  test    r14, r14
0x180008d3b  jz      short loc_180008D9F
0x180008d3d  mov     rcx, r14; lpMem
0x180008d40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008d45  xor     r14d, r14d
0x180008d48  mov     [rsp+1D0h+lpMem], r14
0x180008d4d  test    r15, r15
0x180008d50  jnz     loc_18000905B
0x180008d56  xor     r15d, r15d
0x180008d59  jmp     short loc_180008D97
0x180008d5b  test    rdx, rdx
0x180008d5e  lea     rcx, [rax-2]
0x180008d62  cmovnz  rcx, rax
0x180008d66  mov     [rcx], r15w
0x180008d6a  mov     edi, 80070057h
0x180008d6f  mov     [rsp+1D0h+var_1A8], r15; void *
0x180008d74  mov     r9d, edi; int
0x180008d77  mov     [rbp+0D0h+var_148], r15
0x180008d7b  mov     r8d, 2; unsigned int
0x180008d81  mov     [rsp+1D0h+var_1B0], 0BCDh; int
0x180008d89  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@ExpressionAnimationParser@Composition@UI@Windows@@0QBJB; int *
0x180008d90  mov     ecx, ebx; unsigned int
0x180008d92  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180008d97  test    esi, esi
0x180008d99  jnz     loc_180009158
0x180008d9f  mov     rdi, [rbp+0D0h+var_148]
0x180008da3  movsd   xmm0, [rbp+0D0h+var_130]
0x180008da8  mov     rsi, rdi
0x180008dab  mov     eax, dword ptr [rbp+0D0h+var_128]
0x180008dae  mov     r15d, dword ptr [rsp+1D0h+var_188]
0x180008db3  movsd   [rbp+0D0h+var_120], xmm0
0x180008db8  mov     [rsp+1D0h+string], rdi
0x180008dbd  mov     [rbp+0D0h+var_118], eax
0x180008dc0  test    r14, r14
0x180008dc3  jz      short loc_180008DCD
0x180008dc5  mov     rcx, r14; lpMem
0x180008dc8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008dcd  mov     rax, [r12]
0x180008dd1  lea     rcx, [rsp+1D0h+var_168]
0x180008dd6  mov     r14, [rbp+0D0h+arg_0]
0x180008ddd  mov     rdx, r12
0x180008de0  mov     r9, [rbp+0D0h+newString]
0x180008de4  mov     r8, r14
0x180008de7  mov     [rsp+30h], rcx
0x180008dec  mov     rcx, [rbp+0D0h+arg_18]
0x180008df3  mov     rax, [rax+100h]
0x180008dfa  mov     [rsp+1D0h+var_1A8], rcx
0x180008dff  mov     rcx, r12
0x180008e02  mov     qword ptr [rsp+1D0h+var_1B0], rdi
0x180008e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e0c  xor     r13d, r13d
0x180008e0f  mov     edi, eax
0x180008e11  test    eax, eax
0x180008e13  js      loc_1800090B6
0x180008e19  mov     rcx, [r12+80h]; this
0x180008e21  mov     rdi, [rsp+1D0h+var_168]
0x180008e26  cmp     [rcx+4], r13d
0x180008e2a  jge     short loc_180008E4B
0x180008e2c  mov     r10, [rdi]
0x180008e2f  lea     edx, [r13+1]; unsigned int
0x180008e33  call    ?FindSlot@AllocatedStorage@CSparseStorage@@AEBAPEAVDataInfo@2@I@Z; CSparseStorage::AllocatedStorage::FindSlot(uint)
0x180008e38  mov     rcx, rdi
0x180008e3b  mov     rdx, [rax+4]
0x180008e3f  mov     rax, [r10+0F0h]
0x180008e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e4b  mov     eax, [r12+13Ch]
0x180008e53  test    eax, eax
0x180008e55  jnz     loc_18000929D
0x180008e5b  mov     rax, [rsp+1D0h+var_168]
0x180008e60  lea     r8, [rbp+0D0h+var_120]
0x180008e64  mov     rcx, [rbp+0D0h+var_110]
0x180008e68  mov     r9d, r15d
0x180008e6b  mov     [rsp+1D0h+var_1A8], rax
0x180008e70  mov     rdx, r14
0x180008e73  lea     rax, [rsp+1D0h+string]
0x180008e78  mov     qword ptr [rsp+1D0h+var_1B0], rax
0x180008e7d  call    ?RegisterAnimationTarget@AnimationBindingManager@Composition@UI@Windows@@QEAAJPEAVProxyObject@234@PEAVExpressionObjectPropertyInfo@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEAPEAVSubchannelMaskInfo@@PEAVCompositionPropertyAnimator@234@@Z; Windows::UI::Composition::AnimationBindingManager::RegisterAnimationTarget(Windows::UI::Composition::ProxyObject *,ExpressionObjectPropertyInfo *,DCOMPOSITION_EXPRESSION_TYPE,SubchannelMaskInfo * *,Windows::UI::Composition::CompositionPropertyAnimator *)
0x180008e82  xor     r15d, r15d
0x180008e85  mov     edi, eax
0x180008e87  test    eax, eax
0x180008e89  js      loc_1800092AF
0x180008e8f  mov     rcx, [rbp+0D0h+arg_20]
0x180008e96  test    rcx, rcx
0x180008e99  jz      short loc_180008EA8
0x180008e9b  mov     rax, [rsp+1D0h+var_168]
0x180008ea0  mov     [rcx], rax
0x180008ea3  mov     [rsp+1D0h+var_168], r15
0x180008ea8  mov     edi, r15d
0x180008eab  mov     rcx, [rbp+0D0h+newString]; string
0x180008eaf  test    rcx, rcx
0x180008eb2  jz      short loc_180008EBA
0x180008eb4  call    cs:__imp_WindowsDeleteString
0x180008eba  lea     rcx, [rbp+0D0h+var_B0]
0x180008ebe  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(void)
0x180008ec3  mov     rcx, [rsp+1D0h+var_168]; this
0x180008ec8  test    rcx, rcx
0x180008ecb  jz      short loc_180008ED7
0x180008ecd  mov     [rsp+1D0h+var_168], r15
0x180008ed2  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180008ed7  mov     rbx, [rsp+1D0h+arg_8]
0x180008edf  mov     eax, edi
0x180008ee1  add     rsp, 1A0h
0x180008ee8  pop     r15
0x180008eea  pop     r14
0x180008eec  pop     r13
0x180008eee  pop     r12
0x180008ef0  pop     rdi
0x180008ef1  pop     rsi
0x180008ef2  pop     rbp
0x180008ef3  retn
0x180008ef4  mov     eax, [rsp+1D0h+length]
0x180008ef8  xor     r15d, r15d
0x180008efb  mov     dword ptr [rsp+1D0h+var_178], eax
0x180008eff  test    rdi, rdi
0x180008f02  jz      loc_180008D6A
0x180008f08  mov     ecx, 0F2h; dwBytes
0x180008f0d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008f12  mov     [rsp+1D0h+lpMem], rax
0x180008f17  mov     r14, rax
0x180008f1a  test    rax, rax
0x180008f1d  jnz     loc_180009285
0x180008f23  call    ?OutOfMemory@FailFast@WRL2@Microsoft@@SAX_K@Z; Microsoft::WRL2::FailFast::OutOfMemory(unsigned __int64)
0x180008f29  lea     rdx, [rsp+1D0h+length]; length
0x180008f2e  mov     [rbp+0D0h+var_148], rax
0x180008f32  mov     [rsp+1D0h+length], eax
0x180008f36  call    cs:__imp_WindowsGetStringRawBuffer
0x180008f3c  mov     edx, [rsp+1D0h+length]
0x180008f40  xor     r9d, r9d
0x180008f43  mov     r8d, dword ptr [rsp+1D0h+var_188]
0x180008f48  mov     r14, rax
0x180008f4b  add     rax, 2
0x180008f4f  movsxd  rcx, r15d
0x180008f52  sub     edx, r15d
0x180008f55  lea     rcx, [rax+rcx*2]
0x180008f59  lea     rax, [rsp+1D0h+var_158]
0x180008f5e  mov     [rsp+30h], rax
0x180008f63  lea     rax, [rbp+0D0h+var_150]
0x180008f67  mov     [rsp+1D0h+var_1A8], rax
0x180008f6c  lea     rax, [rsp+1D0h+var_180]
0x180008f71  mov     qword ptr [rsp+1D0h+var_1B0], rax
0x180008f76  call    ?ParseSwizzle@ExpressionAnimationParser@Composition@UI@Windows@@CAXPEBGIW4DCOMPOSITION_EXPRESSION_TYPE@@_NPEAUExpressionErrorInfo@234@PEAPEAVSubchannelMaskInfo@@PEAI@Z; Windows::UI::Composition::ExpressionAnimationParser::ParseSwizzle(ushort const *,uint,DCOMPOSITION_EXPRESSION_TYPE,bool,Windows::UI::Composition::ExpressionErrorInfo *,SubchannelMaskInfo * *,uint *)
0x180008f7b  mov     esi, dword ptr [rsp+1D0h+var_180]
0x180008f7f  xor     eax, eax
0x180008f81  test    esi, esi
0x180008f83  jnz     loc_18000906D
0x180008f89  mov     eax, [rsp+1D0h+length]
0x180008f8d  mov     ecx, [rsp+1D0h+var_158]
0x180008f91  sub     eax, r15d
0x180008f94  dec     eax
0x180008f96  cmp     eax, ecx
0x180008f98  jnz     loc_180009206
0x180008f9e  lea     r9, [rbp+0D0h+newString]; newString
0x180008fa2  mov     r8d, r15d; length
0x180008fa5  xor     edx, edx; startIndex
0x180008fa7  mov     rcx, r13; string
0x180008faa  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x180008fb0  mov     rcx, [rbp+0D0h+var_150]
0x180008fb4  mov     r14, [rsp+1D0h+lpMem]
0x180008fb9  mov     [rbp+0D0h+var_148], rcx
0x180008fbd  jmp     loc_180008D20
0x180008fc2  lea     rdx, [rsp+1D0h+length]; length
0x180008fc7  mov     rcx, r13; string
0x180008fca  call    cs:__imp_WindowsGetStringRawBuffer
0x180008fd0  mov     r15d, [rsp+1D0h+length]
0x180008fd5  mov     rdi, rax
0x180008fd8  dec     r15d
0x180008fdb  xor     eax, eax
0x180008fdd  test    r15d, r15d
0x180008fe0  js      loc_18000909F
0x180008fe6  movsxd  rcx, r15d
0x180008fe9  cmp     word ptr [rdi+rcx*2], 2Eh ; '.'
0x180008fee  jz      short loc_180008FF5
0x180008ff0  dec     r15d
0x180008ff3  jmp     short loc_180008FDD
0x180008ff5  lea     r9, [rsp+1D0h+string]; newString
0x180008ffa  mov     r8d, r15d; length
0x180008ffd  xor     edx, edx; startIndex
0x180008fff  mov     rcx, r13; string
0x180009002  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x180009008  test    eax, eax
0x18000900a  js      loc_1800090B0
0x180009010  mov     rax, [rbx]
0x180009013  lea     rcx, [rsp+1D0h+var_188]
0x180009018  mov     rdx, [rsp+1D0h+string]
0x18000901d  lea     r9, [rbp+0D0h+var_130]
0x180009021  mov     qword ptr [rsp+1D0h+var_1B0], rcx
0x180009026  lea     r8, [rsp+1D0h+var_18C]
0x18000902b  mov     rcx, rbx
0x18000902e  mov     rax, [rax+0C8h]
0x180009035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000903a  mov     cl, byte ptr [rsp+1D0h+var_18C]
0x18000903e  and     cl, 2
0x180009041  neg     cl
0x180009043  sbb     dl, dl
0x180009045  and     dl, al
0x180009047  neg     dl
0x180009049  sbb     esi, esi
0x18000904b  not     esi
0x18000904d  and     esi, 13h
0x180009050  xor     eax, eax
0x180009052  mov     dword ptr [rsp+1D0h+var_180], esi
0x180009056  jmp     loc_180008CE5
0x18000905b  mov     edx, 8; unsigned __int64
0x180009060  mov     rcx, r15; void *
0x180009063  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009068  jmp     loc_180008D56
  ... truncated ...
```
