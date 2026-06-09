# ScriptEngine::~ScriptEngine(void)

- ea: `0x180219870`
- end: `0x180219a95`
- name: `??1ScriptEngine@@UEAA@XZ`
- size: `549`
- prototype: `void __fastcall(ScriptEngine *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18021a0c0`

## callees

- `0x18002e2a8`
- `0x1800e0af8`
- `0x1801a2420`
- `0x1801b3e68`
- `0x1801c5960`
- `0x18020eabc`
- `0x180219870`
- `0x1802271ec`
- `0x180364010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180219a1b`
- `KERNEL32!FreeLibrary` at `0x180219a1b`
- `KERNEL32!DeleteCriticalSection` at `0x1802199ac`
- `KERNEL32!DeleteCriticalSection` at `0x1802199ac`
- `KERNEL32!GetProcAddress` at `0x1802199eb`
- `KERNEL32!GetProcAddress` at `0x1802199eb`
- `OLEAUT32!__imp_SysFreeString` at `0x180219a3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180219a3a`

## string_xrefs

- `0x1802199e1`: `AmsiUninitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ScriptEngine::~ScriptEngine(ScriptEngine *this)
{
  ScriptEngine *v2; // rcx
  HMODULE *v3; // rdi
  FARPROC ProcAddress; // rax
  OLECHAR *v5; // rcx

  *(_QWORD *)this = &ScriptEngine::`vftable'{for `ScriptEngineBase'};
  v2 = (ScriptEngine *)((char *)this + 48);
  *(_QWORD *)v2 = &ScriptEngine::`vftable'{for `IActiveScript'};
  *((_QWORD *)this + 7) = &ScriptEngine::`vftable'{for `IActiveScriptParse64'};
  *((_QWORD *)this + 8) = &ScriptEngine::`vftable'{for `IActiveScriptParseProcedure2_64'};
  *((_QWORD *)this + 9) = &ScriptEngine::`vftable'{for `IActiveScriptParseUTF864'};
  *((_QWORD *)this + 10) = &ScriptEngine::`vftable'{for `IActiveScriptStats'};
  *((_QWORD *)this + 11) = &ScriptEngine::`vftable'{for `IActiveScriptProperty'};
  *((_QWORD *)this + 12) = &ScriptEngine::`vftable'{for `IActiveScriptGarbageCollector'};
  *((_QWORD *)this + 13) = &ScriptEngine::`vftable'{for `IActiveScriptLifecycleEventSink'};
  *((_QWORD *)this + 14) = &ScriptEngine::`vftable'{for `IActiveScriptProjection'};
  *((_QWORD *)this + 15) = &ScriptEngine::`vftable'{for `IActiveScriptByteCode'};
  *((_QWORD *)this + 16) = &ScriptEngine::`vftable'{for `IDiagnosticsContextHelper'};
  *((_QWORD *)this + 17) = &ScriptEngine::`vftable'{for `IActiveScriptDirectAsyncCausality'};
  *((_QWORD *)this + 18) = &ScriptEngine::`vftable'{for `IActiveScriptProfilerControl5'};
  *((_QWORD *)this + 19) = &ScriptEngine::`vftable'{for `IActiveScriptDebugAttach'};
  *((_QWORD *)this + 20) = &ScriptEngine::`vftable'{for `IHeapDumper'};
  *((_QWORD *)this + 21) = &ScriptEngine::`vftable'{for `IActiveScriptDebug64'};
  *((_QWORD *)this + 22) = &ScriptEngine::`vftable'{for `IDebugStackFrameSnifferEx64'};
  *((_QWORD *)this + 23) = &ScriptEngine::`vftable'{for `IRemoteDebugApplicationEvents'};
  *((_QWORD *)this + 24) = &ScriptEngine::`vftable'{for `IVariantChangeType'};
  *((_QWORD *)this + 25) = &ScriptEngine::`vftable'{for `IObjectSafety'};
  *((_QWORD *)this + 26) = &ScriptEngine::`vftable'{for `Js::HaltCallback'};
  ScriptEngine::Close(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 632));
  FreeExcepInfo((struct tagEXCEPINFO *)((char *)this + 672));
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::GetImpl'::`2'::impl);
  v3 = (HMODULE *)((char *)this + 1008);
  if ( *((_QWORD *)this + 122) )
  {
    ProcAddress = GetProcAddress(*v3, "AmsiUninitialize");
    if ( ProcAddress )
      ((void (__fastcall *)(_QWORD))ProcAddress)(*((_QWORD *)this + 122));
    *((_QWORD *)this + 122) = 0;
  }
  if ( *v3 )
  {
    FreeLibrary(*v3);
    *v3 = 0;
  }
  v5 = (OLECHAR *)*((_QWORD *)this + 124);
  if ( v5 )
    SysFreeString(v5);
  _InterlockedDecrement(&dword_180443818);
  MUTX::~MUTX((ScriptEngine *)((char *)this + 872));
  NamedItemList::~NamedItemList((ScriptEngine *)((char *)this + 384));
  ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>((char *)this + 296);
  JAmsi::JAmsiUninitialize((ScriptEngine *)((char *)this + 272));
  *(_QWORD *)this = &ScriptEngineBase::`vftable';
}

```

## disassembly

```asm
0x180219870  mov     r11, rsp
0x180219873  mov     [r11+8], rcx
0x180219877  push    rdi
0x180219878  sub     rsp, 30h
0x18021987c  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x180219884  mov     [r11+10h], rbx
0x180219888  lea     rax, ??_7ScriptEngine@@6BScriptEngineBase@@@; const ScriptEngine::`vftable'{for `ScriptEngineBase'}
0x18021988f  mov     rbx, rcx
0x180219892  mov     [rcx], rax
0x180219895  lea     rcx, [rcx+30h]; this
0x180219899  lea     rax, ??_7ScriptEngine@@6BIActiveScript@@@; const ScriptEngine::`vftable'{for `IActiveScript'}
0x1802198a0  mov     [rcx], rax
0x1802198a3  lea     rax, ??_7ScriptEngine@@6BIActiveScriptParse64@@@; const ScriptEngine::`vftable'{for `IActiveScriptParse64'}
0x1802198aa  mov     [rbx+38h], rax
0x1802198ae  lea     rax, ??_7ScriptEngine@@6BIActiveScriptParseProcedure2_64@@@; const ScriptEngine::`vftable'{for `IActiveScriptParseProcedure2_64'}
0x1802198b5  mov     [rbx+40h], rax
0x1802198b9  lea     rax, ??_7ScriptEngine@@6BIActiveScriptParseUTF864@@@; const ScriptEngine::`vftable'{for `IActiveScriptParseUTF864'}
0x1802198c0  mov     [rbx+48h], rax
0x1802198c4  lea     rax, ??_7ScriptEngine@@6BIActiveScriptStats@@@; const ScriptEngine::`vftable'{for `IActiveScriptStats'}
0x1802198cb  mov     [rbx+50h], rax
0x1802198cf  lea     rax, ??_7ScriptEngine@@6BIActiveScriptProperty@@@; const ScriptEngine::`vftable'{for `IActiveScriptProperty'}
0x1802198d6  mov     [rbx+58h], rax
0x1802198da  lea     rax, ??_7ScriptEngine@@6BIActiveScriptGarbageCollector@@@; const ScriptEngine::`vftable'{for `IActiveScriptGarbageCollector'}
0x1802198e1  mov     [rbx+60h], rax
0x1802198e5  lea     rax, ??_7ScriptEngine@@6BIActiveScriptLifecycleEventSink@@@; const ScriptEngine::`vftable'{for `IActiveScriptLifecycleEventSink'}
0x1802198ec  mov     [rbx+68h], rax
0x1802198f0  lea     rax, ??_7ScriptEngine@@6BIActiveScriptProjection@@@; const ScriptEngine::`vftable'{for `IActiveScriptProjection'}
0x1802198f7  mov     [rbx+70h], rax
0x1802198fb  lea     rax, ??_7ScriptEngine@@6BIActiveScriptByteCode@@@; const ScriptEngine::`vftable'{for `IActiveScriptByteCode'}
0x180219902  mov     [rbx+78h], rax
0x180219906  lea     rax, ??_7ScriptEngine@@6BIDiagnosticsContextHelper@@@; const ScriptEngine::`vftable'{for `IDiagnosticsContextHelper'}
0x18021990d  mov     [rbx+80h], rax
0x180219914  lea     rax, ??_7ScriptEngine@@6BIActiveScriptDirectAsyncCausality@@@; const ScriptEngine::`vftable'{for `IActiveScriptDirectAsyncCausality'}
0x18021991b  mov     [rbx+88h], rax
0x180219922  lea     rax, ??_7ScriptEngine@@6BIActiveScriptProfilerControl5@@@; const ScriptEngine::`vftable'{for `IActiveScriptProfilerControl5'}
0x180219929  mov     [rbx+90h], rax
0x180219930  lea     rax, ??_7ScriptEngine@@6BIActiveScriptDebugAttach@@@; const ScriptEngine::`vftable'{for `IActiveScriptDebugAttach'}
0x180219937  mov     [rbx+98h], rax
0x18021993e  lea     rax, ??_7ScriptEngine@@6BIHeapDumper@@@; const ScriptEngine::`vftable'{for `IHeapDumper'}
0x180219945  mov     [rbx+0A0h], rax
0x18021994c  lea     rax, ??_7ScriptEngine@@6BIActiveScriptDebug64@@@; const ScriptEngine::`vftable'{for `IActiveScriptDebug64'}
0x180219953  mov     [rbx+0A8h], rax
0x18021995a  lea     rax, ??_7ScriptEngine@@6BIDebugStackFrameSnifferEx64@@@; const ScriptEngine::`vftable'{for `IDebugStackFrameSnifferEx64'}
0x180219961  mov     [rbx+0B0h], rax
0x180219968  lea     rax, ??_7ScriptEngine@@6BIRemoteDebugApplicationEvents@@@; const ScriptEngine::`vftable'{for `IRemoteDebugApplicationEvents'}
0x18021996f  mov     [rbx+0B8h], rax
0x180219976  lea     rax, ??_7ScriptEngine@@6BIVariantChangeType@@@; const ScriptEngine::`vftable'{for `IVariantChangeType'}
0x18021997d  mov     [rbx+0C0h], rax
0x180219984  lea     rax, ??_7ScriptEngine@@6BIObjectSafety@@@; const ScriptEngine::`vftable'{for `IObjectSafety'}
0x18021998b  mov     [rbx+0C8h], rax
0x180219992  lea     rax, ??_7ScriptEngine@@6BHaltCallback@Js@@@; const ScriptEngine::`vftable'{for `Js::HaltCallback'}
0x180219999  mov     [rbx+0D0h], rax
0x1802199a0  call    ?Close@ScriptEngine@@UEAAJXZ; ScriptEngine::Close(void)
0x1802199a5  lea     rcx, [rbx+278h]; lpCriticalSection
0x1802199ac  call    cs:__imp_DeleteCriticalSection
0x1802199b3  nop     dword ptr [rax+rax+00h]
0x1802199b8  lea     rcx, [rbx+2A0h]; struct tagEXCEPINFO *
0x1802199bf  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x1802199c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScriptingEngines_AMSI@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_AMSI@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_AMSI> `wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::GetImpl(void)'::`2'::impl
0x1802199cb  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_AMSI@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1802199d0  lea     rdi, [rbx+3F0h]
0x1802199d7  cmp     qword ptr [rbx+3D0h], 0
0x1802199df  jz      short loc_180219A13
0x1802199e1  lea     rdx, aAmsiuninitiali; "AmsiUninitialize"
0x1802199e8  mov     rcx, [rdi]; hModule
0x1802199eb  call    cs:__imp_GetProcAddress
0x1802199f2  nop     dword ptr [rax+rax+00h]
0x1802199f7  test    rax, rax
0x1802199fa  jz      short loc_180219A08
0x1802199fc  mov     rcx, [rbx+3D0h]
0x180219a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180219a08  mov     qword ptr [rbx+3D0h], 0
0x180219a13  mov     rcx, [rdi]; hLibModule
0x180219a16  test    rcx, rcx
0x180219a19  jz      short loc_180219A2E
0x180219a1b  call    cs:__imp_FreeLibrary
0x180219a22  nop     dword ptr [rax+rax+00h]
0x180219a27  mov     qword ptr [rdi], 0
0x180219a2e  mov     rcx, [rbx+3E0h]; bstrString
0x180219a35  test    rcx, rcx
0x180219a38  jz      short loc_180219A46
0x180219a3a  call    cs:__imp_SysFreeString
0x180219a41  nop     dword ptr [rax+rax+00h]
0x180219a46  lock dec cs:dword_180443818
0x180219a4d  lea     rcx, [rbx+368h]; this
0x180219a54  call    ??1MUTX@@QEAA@XZ; MUTX::~MUTX(void)
0x180219a59  lea     rcx, [rbx+180h]; this
0x180219a60  call    ??1NamedItemList@@QEAA@XZ; NamedItemList::~NamedItemList(void)
0x180219a65  lea     rcx, [rbx+128h]
0x180219a6c  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x180219a71  nop
0x180219a72  lea     rcx, [rbx+110h]; this
0x180219a79  call    ?JAmsiUninitialize@JAmsi@@QEAAXXZ; JAmsi::JAmsiUninitialize(void)
0x180219a7e  nop
0x180219a7f  lea     rax, ??_7ScriptEngineBase@@6B@; const ScriptEngineBase::`vftable'
0x180219a86  mov     [rbx], rax
0x180219a89  mov     rbx, [rsp+38h+arg_8]
0x180219a8e  add     rsp, 30h
0x180219a92  pop     rdi
0x180219a93  retn
```
