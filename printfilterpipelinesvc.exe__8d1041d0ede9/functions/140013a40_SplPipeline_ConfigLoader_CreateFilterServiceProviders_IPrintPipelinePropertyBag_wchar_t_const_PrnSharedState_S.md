# SplPipeline::ConfigLoader::CreateFilterServiceProviders(IPrintPipelinePropertyBag *,wchar_t const *,PrnSharedState::SharedState *,wchar_t const *,void *,NCoreLibrary::TList<PrnExcept::PropertyBagElement> &)

- ea: `0x140013a40`
- end: `0x140013c85`
- name: `?CreateFilterServiceProviders@ConfigLoader@SplPipeline@@QEAAXPEAUIPrintPipelinePropertyBag@@PEB_WPEAVSharedState@PrnSharedState@@1PEAXAEAV?$TList@VPropertyBagElement@PrnExcept@@@NCoreLibrary@@@Z`
- size: `581`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, __int64, HANDLE hPrinter, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x140012404`

## callees

- `0x140002058`
- `0x14000fa68`
- `0x1400123d8`
- `0x140013170`
- `0x140013250`
- `0x140013580`
- `0x1400135ac`
- `0x140013a40`
- `0x140014148`
- `0x14004650c`
- `0x140059a5c`
- `0x140063010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140013bb5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140013bb5`

## string_xrefs

- `0x140013bae`: `PrintConfig.dll`
- `0x140013c31`: `PrintConfig.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SplPipeline::ConfigLoader::CreateFilterServiceProviders(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        HANDLE hPrinter,
        __int64 a7)
{
  int PrinterDriver3; // eax
  int v10; // edx
  const char *v11; // r8
  unsigned int v12; // r9d
  int v13; // r15d
  const wchar_t *v14; // rdx
  const char *v15; // r8
  unsigned int v16; // r9d
  bool v17; // di
  unsigned int i; // esi
  __int64 v19; // rbx
  wchar_t *v20; // rax
  int v21; // eax
  int v22; // edx
  const char *v23; // r8
  unsigned int v24; // r9d
  void *v25; // rbx
  __int64 v26; // rcx
  NCoreLibrary::TString *v27; // rcx
  __int64 result; // rax
  int v29; // [rsp+38h] [rbp-48h]
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-30h] BYREF
  __int64 v31; // [rsp+58h] [rbp-28h] BYREF
  __int64 v32; // [rsp+60h] [rbp-20h] BYREF
  void *Block; // [rsp+68h] [rbp-18h] BYREF
  void *v34; // [rsp+70h] [rbp-10h] BYREF
  __int64 v35; // [rsp+78h] [rbp-8h]

  Block = 0;
  PrinterDriver3 = PrivateGetPrinterDriver3(hPrinter, (struct _DRIVER_INFO_3W **)&Block);
  if ( PrinterDriver3 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)PrinterDriver3, v10, v11, v12);
  v13 = *(_DWORD *)Block;
  operator delete(Block);
  v17 = 0;
  for ( i = 0; i < 2; ++i )
  {
    Block = 0;
    v32 = 0;
    v19 = 16LL * i;
    v35 = v19;
    v20 = PrnExcept::SysAllocString(*(PrnExcept **)((char *)&off_1400668C0 + v19), v14, v15, v16);
    NCoreLibrary::TAutoPtrBSTR::operator=(&Block, v20);
    (*(void (__fastcall **)(_QWORD, void *, __int64 *))(*(_QWORD *)*a1 + 288LL))(*a1, Block, &v32);
    v30 = 0;
    while ( !(*(unsigned int (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v32 + 72LL))(
               v32,
               &v30) )
    {
      v31 = 0;
      v21 = (**v30)(v30, &IID_IXMLDOMElement, &v31);
      if ( v21 < 0 )
        SplException::RealThrowFromHR((SplException *)(unsigned int)v21, v22, v23, v24);
      v34 = &NCoreLibrary::TString::gszNullState;
      PrnExcept::GetStringAttribute(v31, L"dll", &v34, 1);
      LOBYTE(v29) = *((_BYTE *)&off_1400668C0 + v19 + 8);
      v25 = v34;
      SplPipeline::ConfigLoader::AddSingleFilterServiceProvider(v26, a2, a3, a4, a5, hPrinter, v34, v29, a7);
      if ( v13 == 4 && !v17 )
        v17 = (unsigned int)_o__wcsicmp(L"PrintConfig.dll", v25) == 0;
      NCoreLibrary::TString::vFree(v27, v25);
      PrnExcept::SmartRelease<IPartResourceDictionary>(&v31);
      PrnExcept::SmartRelease<IPartResourceDictionary>(&v30);
      v19 = v35;
    }
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v30);
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v32);
    result = NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&Block);
  }
  if ( v13 == 4 && !v17 )
  {
    LOBYTE(v29) = 1;
    return SplPipeline::ConfigLoader::AddSingleFilterServiceProvider(
             1,
             a2,
             a3,
             a4,
             a5,
             hPrinter,
             L"PrintConfig.dll",
             v29,
             a7);
  }
  return result;
}

```

## disassembly

```asm
0x140013a40  mov     [rsp-38h+arg_10], rbx
0x140013a45  mov     [rsp-38h+arg_8], rdx
0x140013a4a  mov     [rsp-38h+arg_0], rcx
0x140013a4f  push    rbp
0x140013a50  push    rsi
0x140013a51  push    rdi
0x140013a52  push    r12
0x140013a54  push    r13
0x140013a56  push    r14
0x140013a58  push    r15
0x140013a5a  mov     rbp, rsp
0x140013a5d  sub     rsp, 80h
0x140013a64  mov     r12, r9
0x140013a67  mov     r13, r8
0x140013a6a  mov     [rbp+Block], 0
0x140013a72  lea     rdx, [rbp+Block]; struct _DRIVER_INFO_3W **
0x140013a76  mov     r14, [rbp+hPrinter]
0x140013a7a  mov     rcx, r14; hPrinter
0x140013a7d  call    ?PrivateGetPrinterDriver3@@YAJPEAXPEAPEAU_DRIVER_INFO_3W@@@Z; PrivateGetPrinterDriver3(void *,_DRIVER_INFO_3W * *)
0x140013a82  test    eax, eax
0x140013a84  js      loc_140013C7D
0x140013a8a  mov     rcx, [rbp+Block]; Block
0x140013a8e  mov     r15d, [rcx]
0x140013a91  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140013a96  xor     dil, dil
0x140013a99  xor     esi, esi
0x140013a9b  lea     rax, off_1400668C0; "FilterServiceProvider"
0x140013aa2  mov     [rbp+Block], 0
0x140013aaa  mov     [rbp+var_20], 0
0x140013ab2  mov     ebx, esi
0x140013ab4  shl     rbx, 4
0x140013ab8  mov     [rbp+var_8], rbx
0x140013abc  mov     rcx, [rbx+rax]; this
0x140013ac0  call    ?SysAllocString@PrnExcept@@YAPEA_WPEB_WPEBDK@Z; PrnExcept::SysAllocString(wchar_t const *,char const *,ulong)
0x140013ac5  mov     rdx, rax
0x140013ac8  lea     rcx, [rbp+Block]
0x140013acc  call    ??4TAutoPtrBSTR@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrBSTR::operator=(wchar_t *)
0x140013ad1  mov     rax, [rbp+arg_0]
0x140013ad5  mov     rcx, [rax]
0x140013ad8  mov     rax, [rcx]
0x140013adb  lea     r8, [rbp+var_20]
0x140013adf  mov     rdx, [rbp+Block]
0x140013ae3  mov     rax, [rax+120h]
0x140013aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013aef  mov     [rbp+var_30], 0
0x140013af7  mov     rcx, [rbp+var_20]
0x140013afb  mov     rax, [rcx]
0x140013afe  lea     rdx, [rbp+var_30]
0x140013b02  mov     rax, [rax+48h]
0x140013b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b0b  test    eax, eax
0x140013b0d  jnz     loc_140013BEC
0x140013b13  mov     [rbp+var_28], 0
0x140013b1b  mov     rcx, [rbp+var_30]
0x140013b1f  mov     rax, [rcx]
0x140013b22  lea     r8, [rbp+var_28]
0x140013b26  lea     rdx, IID_IXMLDOMElement
0x140013b2d  mov     rax, [rax]
0x140013b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b35  test    eax, eax
0x140013b37  js      loc_140013C75
0x140013b3d  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PA_WA; wchar_t near * NCoreLibrary::TString::gszNullState
0x140013b44  mov     [rbp+var_10], rax
0x140013b48  mov     r9d, 1
0x140013b4e  lea     r8, [rbp+var_10]
0x140013b52  lea     rdx, aDll; "dll"
0x140013b59  mov     rcx, [rbp+var_28]
0x140013b5d  call    ?GetStringAttribute@PrnExcept@@YAXPEAUIXMLDOMElement@@PEB_WPEAVTString@NCoreLibrary@@W4EGetAttrOpt@1@@Z; PrnExcept::GetStringAttribute(IXMLDOMElement *,wchar_t const *,NCoreLibrary::TString *,PrnExcept::EGetAttrOpt)
0x140013b62  mov     rax, [rbp+arg_30]
0x140013b66  mov     [rsp+80h+var_40], rax
0x140013b6b  lea     rax, off_1400668C0; "FilterServiceProvider"
0x140013b72  mov     al, [rbx+rax+8]
0x140013b76  mov     [rsp+80h+var_48], al
0x140013b7a  mov     rbx, [rbp+var_10]
0x140013b7e  mov     [rsp+80h+var_50], rbx
0x140013b83  mov     [rsp+80h+var_58], r14
0x140013b88  mov     rax, [rbp+arg_20]
0x140013b8c  mov     [rsp+80h+var_60], rax
0x140013b91  mov     r9, r12
0x140013b94  mov     r8, r13
0x140013b97  mov     rdx, [rbp+arg_8]
0x140013b9b  call    ?AddSingleFilterServiceProvider@ConfigLoader@SplPipeline@@AEAAXPEAUIPrintPipelinePropertyBag@@PEB_WPEAVSharedState@PrnSharedState@@1PEAX1_NAEAV?$TList@VPropertyBagElement@PrnExcept@@@NCoreLibrary@@@Z; SplPipeline::ConfigLoader::AddSingleFilterServiceProvider(IPrintPipelinePropertyBag *,wchar_t const *,PrnSharedState::SharedState *,wchar_t const *,void *,wchar_t const *,bool,NCoreLibrary::TList<PrnExcept::PropertyBagElement> &)
0x140013ba0  cmp     r15d, 4
0x140013ba4  jnz     short loc_140013BC8
0x140013ba6  test    dil, dil
0x140013ba9  jnz     short loc_140013BC8
0x140013bab  mov     rdx, rbx
0x140013bae  lea     rcx, aPrintconfigDll; "PrintConfig.dll"
0x140013bb5  call    cs:__imp__o__wcsicmp
0x140013bbb  movzx   edi, dil
0x140013bbf  test    eax, eax
0x140013bc1  lea     eax, [r15-3]
0x140013bc5  cmovz   edi, eax
0x140013bc8  mov     rdx, rbx; void *
0x140013bcb  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x140013bd0  nop
0x140013bd1  lea     rcx, [rbp+var_28]
0x140013bd5  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140013bda  lea     rcx, [rbp+var_30]
0x140013bde  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140013be3  mov     rbx, [rbp+var_8]
0x140013be7  jmp     loc_140013AF7
0x140013bec  lea     rcx, [rbp+var_30]
0x140013bf0  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140013bf5  nop
0x140013bf6  lea     rcx, [rbp+var_20]
0x140013bfa  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140013bff  nop
0x140013c00  lea     rcx, [rbp+Block]
0x140013c04  call    ?Reset@?$TGenericSP@PEA_WVTAutoPtrBSTR@NCoreLibrary@@PEA_W$0A@PEBQEA_W@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(void)
0x140013c09  mov     ecx, 1
0x140013c0e  add     esi, ecx
0x140013c10  cmp     esi, 2
0x140013c13  jb      loc_140013A9B
0x140013c19  cmp     r15d, 4
0x140013c1d  jnz     short loc_140013C5A
0x140013c1f  test    dil, dil
0x140013c22  jnz     short loc_140013C5A
0x140013c24  mov     rax, [rbp+arg_30]
0x140013c28  mov     [rsp+80h+var_40], rax
0x140013c2d  mov     [rsp+80h+var_48], cl
0x140013c31  lea     rax, aPrintconfigDll; "PrintConfig.dll"
0x140013c38  mov     [rsp+80h+var_50], rax
0x140013c3d  mov     [rsp+80h+var_58], r14
0x140013c42  mov     rax, [rbp+arg_20]
0x140013c46  mov     [rsp+80h+var_60], rax
0x140013c4b  mov     r9, r12
0x140013c4e  mov     r8, r13
0x140013c51  mov     rdx, [rbp+arg_8]
0x140013c55  call    ?AddSingleFilterServiceProvider@ConfigLoader@SplPipeline@@AEAAXPEAUIPrintPipelinePropertyBag@@PEB_WPEAVSharedState@PrnSharedState@@1PEAX1_NAEAV?$TList@VPropertyBagElement@PrnExcept@@@NCoreLibrary@@@Z; SplPipeline::ConfigLoader::AddSingleFilterServiceProvider(IPrintPipelinePropertyBag *,wchar_t const *,PrnSharedState::SharedState *,wchar_t const *,void *,wchar_t const *,bool,NCoreLibrary::TList<PrnExcept::PropertyBagElement> &)
0x140013c5a  mov     rbx, [rsp+80h+arg_10]
0x140013c62  add     rsp, 80h
0x140013c69  pop     r15
0x140013c6b  pop     r14
0x140013c6d  pop     r13
0x140013c6f  pop     r12
0x140013c71  pop     rdi
0x140013c72  pop     rsi
0x140013c73  pop     rbp
0x140013c74  retn
0x140013c75  mov     ecx, eax; this
0x140013c77  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140013c7d  mov     ecx, eax; this
0x140013c7f  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
```
