# ScriptEngine::~ScriptEngine(void)

- ea: `0x18021602c`
- end: `0x180216238`
- name: `??1ScriptEngine@@UEAA@XZ`
- size: `524`
- prototype: `void __fastcall(ScriptEngine *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180216840`

## callees

- `0x1800230d4`
- `0x180068e3c`
- `0x1801a00c8`
- `0x1801b27d4`
- `0x1801c2fe0`
- `0x18020b480`
- `0x18021602c`
- `0x1802233f8`
- `0x18035e010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1802161cb`
- `KERNEL32!FreeLibrary` at `0x1802161cb`
- `KERNEL32!DeleteCriticalSection` at `0x180216168`
- `KERNEL32!DeleteCriticalSection` at `0x180216168`
- `KERNEL32!GetProcAddress` at `0x1802161a1`
- `KERNEL32!GetProcAddress` at `0x1802161a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1802161e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1802161e4`

## string_xrefs

- `0x180216197`: `AmsiUninitialize`

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
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::__private_IsEnabledPreCheck(&`wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::GetImpl'::`2'::impl);
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
  _InterlockedDecrement(&dword_18043D818);
  MUTX::~MUTX((ScriptEngine *)((char *)this + 872));
  NamedItemList::~NamedItemList((ScriptEngine *)((char *)this + 384));
  ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>((char *)this + 296);
  JAmsi::JAmsiUninitialize((ScriptEngine *)((char *)this + 272));
  *(_QWORD *)this = &ScriptEngineBase::`vftable';
}

```

## disassembly

```asm
0x18021602c  mov     r11, rsp
0x18021602f  mov     [r11+8], rcx
0x180216033  push    rdi
0x180216034  sub     rsp, 30h
0x180216038  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x180216040  mov     [r11+10h], rbx
0x180216044  lea     rax, ??_7ScriptEngine@@6BScriptEngineBase@@@; const ScriptEngine::`vftable'{for `ScriptEngineBase'}
0x18021604b  mov     rbx, rcx
0x18021604e  mov     [rcx], rax
0x180216051  lea     rcx, [rcx+30h]; this
0x180216055  lea     rax, ??_7ScriptEngine@@6BIActiveScript@@@; const ScriptEngine::`vftable'{for `IActiveScript'}
0x18021605c  mov     [rcx], rax
0x18021605f  lea     rax, ??_7ScriptEngine@@6BIActiveScriptParse64@@@; const ScriptEngine::`vftable'{for `IActiveScriptParse64'}
0x180216066  mov     [rbx+38h], rax
0x18021606a  lea     rax, ??_7ScriptEngine@@6BIActiveScriptParseProcedure2_64@@@; const ScriptEngine::`vftable'{for `IActiveScriptParseProcedure2_64'}
0x180216071  mov     [rbx+40h], rax
0x180216075  lea     rax, ??_7ScriptEngine@@6BIActiveScriptParseUTF864@@@; const ScriptEngine::`vftable'{for `IActiveScriptParseUTF864'}
0x18021607c  mov     [rbx+48h], rax
0x180216080  lea     rax, ??_7ScriptEngine@@6BIActiveScriptStats@@@; const ScriptEngine::`vftable'{for `IActiveScriptStats'}
0x180216087  mov     [rbx+50h], rax
0x18021608b  lea     rax, ??_7ScriptEngine@@6BIActiveScriptProperty@@@; const ScriptEngine::`vftable'{for `IActiveScriptProperty'}
0x180216092  mov     [rbx+58h], rax
0x180216096  lea     rax, ??_7ScriptEngine@@6BIActiveScriptGarbageCollector@@@; const ScriptEngine::`vftable'{for `IActiveScriptGarbageCollector'}
0x18021609d  mov     [rbx+60h], rax
0x1802160a1  lea     rax, ??_7ScriptEngine@@6BIActiveScriptLifecycleEventSink@@@; const ScriptEngine::`vftable'{for `IActiveScriptLifecycleEventSink'}
0x1802160a8  mov     [rbx+68h], rax
0x1802160ac  lea     rax, ??_7ScriptEngine@@6BIActiveScriptProjection@@@; const ScriptEngine::`vftable'{for `IActiveScriptProjection'}
0x1802160b3  mov     [rbx+70h], rax
0x1802160b7  lea     rax, ??_7ScriptEngine@@6BIActiveScriptByteCode@@@; const ScriptEngine::`vftable'{for `IActiveScriptByteCode'}
0x1802160be  mov     [rbx+78h], rax
0x1802160c2  lea     rax, ??_7ScriptEngine@@6BIDiagnosticsContextHelper@@@; const ScriptEngine::`vftable'{for `IDiagnosticsContextHelper'}
0x1802160c9  mov     [rbx+80h], rax
0x1802160d0  lea     rax, ??_7ScriptEngine@@6BIActiveScriptDirectAsyncCausality@@@; const ScriptEngine::`vftable'{for `IActiveScriptDirectAsyncCausality'}
0x1802160d7  mov     [rbx+88h], rax
0x1802160de  lea     rax, ??_7ScriptEngine@@6BIActiveScriptProfilerControl5@@@; const ScriptEngine::`vftable'{for `IActiveScriptProfilerControl5'}
0x1802160e5  mov     [rbx+90h], rax
0x1802160ec  lea     rax, ??_7ScriptEngine@@6BIActiveScriptDebugAttach@@@; const ScriptEngine::`vftable'{for `IActiveScriptDebugAttach'}
0x1802160f3  mov     [rbx+98h], rax
0x1802160fa  lea     rax, ??_7ScriptEngine@@6BIHeapDumper@@@; const ScriptEngine::`vftable'{for `IHeapDumper'}
0x180216101  mov     [rbx+0A0h], rax
0x180216108  lea     rax, ??_7ScriptEngine@@6BIActiveScriptDebug64@@@; const ScriptEngine::`vftable'{for `IActiveScriptDebug64'}
0x18021610f  mov     [rbx+0A8h], rax
0x180216116  lea     rax, ??_7ScriptEngine@@6BIDebugStackFrameSnifferEx64@@@; const ScriptEngine::`vftable'{for `IDebugStackFrameSnifferEx64'}
0x18021611d  mov     [rbx+0B0h], rax
0x180216124  lea     rax, ??_7ScriptEngine@@6BIRemoteDebugApplicationEvents@@@; const ScriptEngine::`vftable'{for `IRemoteDebugApplicationEvents'}
0x18021612b  mov     [rbx+0B8h], rax
0x180216132  lea     rax, ??_7ScriptEngine@@6BIVariantChangeType@@@; const ScriptEngine::`vftable'{for `IVariantChangeType'}
0x180216139  mov     [rbx+0C0h], rax
0x180216140  lea     rax, ??_7ScriptEngine@@6BIObjectSafety@@@; const ScriptEngine::`vftable'{for `IObjectSafety'}
0x180216147  mov     [rbx+0C8h], rax
0x18021614e  lea     rax, ??_7ScriptEngine@@6BHaltCallback@Js@@@; const ScriptEngine::`vftable'{for `Js::HaltCallback'}
0x180216155  mov     [rbx+0D0h], rax
0x18021615c  call    ?Close@ScriptEngine@@UEAAJXZ; ScriptEngine::Close(void)
0x180216161  lea     rcx, [rbx+278h]; lpCriticalSection
0x180216168  call    cs:__imp_DeleteCriticalSection
0x18021616e  lea     rcx, [rbx+2A0h]; struct tagEXCEPINFO *
0x180216175  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x18021617a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScriptingEngines_AMSI@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_AMSI@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_AMSI> `wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::GetImpl(void)'::`2'::impl
0x180216181  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_AMSI@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180216186  lea     rdi, [rbx+3F0h]
0x18021618d  cmp     qword ptr [rbx+3D0h], 0
0x180216195  jz      short loc_1802161C3
0x180216197  lea     rdx, aAmsiuninitiali; "AmsiUninitialize"
0x18021619e  mov     rcx, [rdi]; hModule
0x1802161a1  call    cs:__imp_GetProcAddress
0x1802161a7  test    rax, rax
0x1802161aa  jz      short loc_1802161B8
0x1802161ac  mov     rcx, [rbx+3D0h]
0x1802161b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802161b8  mov     qword ptr [rbx+3D0h], 0
0x1802161c3  mov     rcx, [rdi]; hLibModule
0x1802161c6  test    rcx, rcx
0x1802161c9  jz      short loc_1802161D8
0x1802161cb  call    cs:__imp_FreeLibrary
0x1802161d1  mov     qword ptr [rdi], 0
0x1802161d8  mov     rcx, [rbx+3E0h]; bstrString
0x1802161df  test    rcx, rcx
0x1802161e2  jz      short loc_1802161EA
0x1802161e4  call    cs:__imp_SysFreeString
0x1802161ea  lock dec cs:dword_18043D818
0x1802161f1  lea     rcx, [rbx+368h]; this
0x1802161f8  call    ??1MUTX@@QEAA@XZ; MUTX::~MUTX(void)
0x1802161fd  lea     rcx, [rbx+180h]; this
0x180216204  call    ??1NamedItemList@@QEAA@XZ; NamedItemList::~NamedItemList(void)
0x180216209  lea     rcx, [rbx+128h]
0x180216210  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x180216215  nop
0x180216216  lea     rcx, [rbx+110h]; this
0x18021621d  call    ?JAmsiUninitialize@JAmsi@@QEAAXXZ; JAmsi::JAmsiUninitialize(void)
0x180216222  nop
0x180216223  lea     rax, ??_7ScriptEngineBase@@6B@; const ScriptEngineBase::`vftable'
0x18021622a  mov     [rbx], rax
0x18021622d  mov     rbx, [rsp+38h+arg_8]
0x180216232  add     rsp, 30h
0x180216236  pop     rdi
0x180216237  retn
```
