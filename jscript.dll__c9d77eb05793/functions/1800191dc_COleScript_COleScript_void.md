# COleScript::~COleScript(void)

- ea: `0x1800191dc`
- end: `0x180019418`
- name: `??1COleScript@@UEAA@XZ`
- size: `572`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180019ce0`
- `0x18001a950`

## callees

- `0x18000f65c`
- `0x1800191dc`
- `0x180019420`
- `0x18001970c`
- `0x18001a2dc`
- `0x18001a334`
- `0x180057694`
- `0x180076cbc`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001940d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001940d`
- `KERNEL32!FreeLibrary` at `0x180019372`
- `KERNEL32!FreeLibrary` at `0x180019372`
- `KERNEL32!GetProcAddress` at `0x180019349`
- `KERNEL32!GetProcAddress` at `0x180019349`
- `KERNEL32!DeleteCriticalSection` at `0x1800192ff`
- `KERNEL32!DeleteCriticalSection` at `0x1800192ff`

## string_xrefs

- `0x180019342`: `AmsiUninitialize`

## pseudocode

```c
void __fastcall COleScript::~COleScript(COleScript *this)
{
  bool v1; // zf
  __int64 v3; // rcx
  void *v4; // rdi
  FARPROC ProcAddress; // rax
  HMODULE v6; // rcx
  OLECHAR *v7; // rcx

  v1 = *((_DWORD *)this + 71) == 0;
  *(_QWORD *)this = &COleScript::`vftable'{for `IActiveScript'};
  *((_QWORD *)this + 1) = &COleScript::`vftable'{for `IActiveScriptParse64'};
  *((_QWORD *)this + 2) = &COleScript::`vftable'{for `IActiveScriptProperty'};
  *((_QWORD *)this + 3) = &COleScript::`vftable'{for `IActiveScriptEncode'};
  *((_QWORD *)this + 4) = &COleScript::`vftable'{for `IActiveScriptProfilerControl'};
  *((_QWORD *)this + 5) = &COleScript::`vftable'{for `IActiveScriptDebug64'};
  *((_QWORD *)this + 6) = &COleScript::`vftable'{for `IDebugStackFrameSnifferEx64'};
  *((_QWORD *)this + 7) = &COleScript::`vftable'{for `IProvideExpressionContexts'};
  *((_QWORD *)this + 8) = &COleScript::`vftable'{for `IRemoteDebugApplicationEvents'};
  *((_QWORD *)this + 9) = &COleScript::`vftable'{for `IActiveScriptParseProcedure2_64'};
  *((_QWORD *)this + 10) = &COleScript::`vftable'{for `IHostInfoUpdate'};
  *((_QWORD *)this + 11) = &COleScript::`vftable'{for `IWrapTypeLibs'};
  *((_QWORD *)this + 12) = &COleScript::`vftable'{for `IScriptHelper'};
  *((_QWORD *)this + 13) = &COleScript::`vftable'{for `IObjectSafety'};
  *((_QWORD *)this + 14) = &COleScript::`vftable'{for `IVariantChangeType'};
  *((_QWORD *)this + 15) = &COleScript::`vftable'{for `IActiveScriptGarbageCollector'};
  *((_QWORD *)this + 16) = &COleScript::`vftable'{for `IActiveScriptStats'};
  *((_QWORD *)this + 17) = &COleScript::`vftable'{for `ITrackingService'};
  *((_QWORD *)this + 18) = &COleScript::`vftable'{for `IActiveScriptTraceInfo'};
  *((_QWORD *)this + 19) = &COleScript::`vftable'{for `IActiveScriptSIPInfo'};
  if ( !v1 )
    _InterlockedIncrement((volatile signed __int32 *)this + 40);
  COleScript::CloseInternal(this);
  if ( *((_DWORD *)this + 71) )
    _InterlockedDecrement((volatile signed __int32 *)this + 40);
  if ( *((_DWORD *)this + 140) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  FreeExcepInfo((struct tagEXCEPINFO *)((char *)this + 608));
  v3 = *((_QWORD *)this + 117);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 117) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 85);
  if ( v4 )
  {
    TrackerClientRootList::~TrackerClientRootList(*((TrackerClientRootList **)this + 85));
    operator delete(v4);
  }
  if ( *((_QWORD *)this + 121) )
  {
    ProcAddress = GetProcAddress(*((HMODULE *)this + 125), "AmsiUninitialize");
    ((void (__fastcall *)(_QWORD))ProcAddress)(*((_QWORD *)this + 121));
    *((_QWORD *)this + 121) = 0;
  }
  v6 = (HMODULE)*((_QWORD *)this + 125);
  if ( v6 )
  {
    FreeLibrary(v6);
    *((_QWORD *)this + 125) = 0;
  }
  v7 = (OLECHAR *)*((_QWORD *)this + 123);
  if ( v7 )
    SysFreeString(v7);
  _InterlockedDecrement(&g_cLibRef);
  MUTX::~MUTX((COleScript *)((char *)this + 856));
  NamedItemList::~NamedItemList((COleScript *)((char *)this + 312));
  JAmsi::~JAmsi((COleScript *)((char *)this + 216));
}

```

## disassembly

```asm
0x1800191dc  mov     [rsp+arg_0], rbx
0x1800191e1  push    rdi
0x1800191e2  sub     rsp, 20h
0x1800191e6  cmp     dword ptr [rcx+11Ch], 0
0x1800191ed  lea     rax, ??_7COleScript@@6BIActiveScript@@@; const COleScript::`vftable'{for `IActiveScript'}
0x1800191f4  mov     [rcx], rax
0x1800191f7  mov     rbx, rcx
0x1800191fa  lea     rax, ??_7COleScript@@6BIActiveScriptParse64@@@; const COleScript::`vftable'{for `IActiveScriptParse64'}
0x180019201  mov     [rcx+8], rax
0x180019205  lea     rax, ??_7COleScript@@6BIActiveScriptProperty@@@; const COleScript::`vftable'{for `IActiveScriptProperty'}
0x18001920c  mov     [rcx+10h], rax
0x180019210  lea     rax, ??_7COleScript@@6BIActiveScriptEncode@@@; const COleScript::`vftable'{for `IActiveScriptEncode'}
0x180019217  mov     [rcx+18h], rax
0x18001921b  lea     rax, ??_7COleScript@@6BIActiveScriptProfilerControl@@@; const COleScript::`vftable'{for `IActiveScriptProfilerControl'}
0x180019222  mov     [rcx+20h], rax
0x180019226  lea     rax, ??_7COleScript@@6BIActiveScriptDebug64@@@; const COleScript::`vftable'{for `IActiveScriptDebug64'}
0x18001922d  mov     [rcx+28h], rax
0x180019231  lea     rax, ??_7COleScript@@6BIDebugStackFrameSnifferEx64@@@; const COleScript::`vftable'{for `IDebugStackFrameSnifferEx64'}
0x180019238  mov     [rcx+30h], rax
0x18001923c  lea     rax, ??_7COleScript@@6BIProvideExpressionContexts@@@; const COleScript::`vftable'{for `IProvideExpressionContexts'}
0x180019243  mov     [rcx+38h], rax
0x180019247  lea     rax, ??_7COleScript@@6BIRemoteDebugApplicationEvents@@@; const COleScript::`vftable'{for `IRemoteDebugApplicationEvents'}
0x18001924e  mov     [rcx+40h], rax
0x180019252  lea     rax, ??_7COleScript@@6BIActiveScriptParseProcedure2_64@@@; const COleScript::`vftable'{for `IActiveScriptParseProcedure2_64'}
0x180019259  mov     [rcx+48h], rax
0x18001925d  lea     rax, ??_7COleScript@@6BIHostInfoUpdate@@@; const COleScript::`vftable'{for `IHostInfoUpdate'}
0x180019264  mov     [rcx+50h], rax
0x180019268  lea     rax, ??_7COleScript@@6BIWrapTypeLibs@@@; const COleScript::`vftable'{for `IWrapTypeLibs'}
0x18001926f  mov     [rcx+58h], rax
0x180019273  lea     rax, ??_7COleScript@@6BIScriptHelper@@@; const COleScript::`vftable'{for `IScriptHelper'}
0x18001927a  mov     [rcx+60h], rax
0x18001927e  lea     rax, ??_7COleScript@@6BIObjectSafety@@@; const COleScript::`vftable'{for `IObjectSafety'}
0x180019285  mov     [rcx+68h], rax
0x180019289  lea     rax, ??_7COleScript@@6BIVariantChangeType@@@; const COleScript::`vftable'{for `IVariantChangeType'}
0x180019290  mov     [rcx+70h], rax
0x180019294  lea     rax, ??_7COleScript@@6BIActiveScriptGarbageCollector@@@; const COleScript::`vftable'{for `IActiveScriptGarbageCollector'}
0x18001929b  mov     [rcx+78h], rax
0x18001929f  lea     rax, ??_7COleScript@@6BIActiveScriptStats@@@; const COleScript::`vftable'{for `IActiveScriptStats'}
0x1800192a6  mov     [rcx+80h], rax
0x1800192ad  lea     rax, ??_7COleScript@@6BITrackingService@@@; const COleScript::`vftable'{for `ITrackingService'}
0x1800192b4  mov     [rcx+88h], rax
0x1800192bb  lea     rax, ??_7COleScript@@6BIActiveScriptTraceInfo@@@; const COleScript::`vftable'{for `IActiveScriptTraceInfo'}
0x1800192c2  mov     [rcx+90h], rax
0x1800192c9  lea     rax, ??_7COleScript@@6BIActiveScriptSIPInfo@@@; const COleScript::`vftable'{for `IActiveScriptSIPInfo'}
0x1800192d0  mov     [rcx+98h], rax
0x1800192d7  jnz     loc_1800193C4
0x1800192dd  call    ?CloseInternal@COleScript@@QEAAJXZ; COleScript::CloseInternal(void)
0x1800192e2  cmp     dword ptr [rbx+11Ch], 0
0x1800192e9  jnz     loc_1800193D0
0x1800192ef  cmp     dword ptr [rbx+230h], 0
0x1800192f6  jz      short loc_180019305
0x1800192f8  lea     rcx, [rbx+238h]; lpCriticalSection
0x1800192ff  call    cs:__imp_DeleteCriticalSection
0x180019305  lea     rcx, [rbx+260h]; struct tagEXCEPINFO *
0x18001930c  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x180019311  mov     rcx, [rbx+3A8h]
0x180019318  test    rcx, rcx
0x18001931b  jnz     loc_1800193DC
0x180019321  mov     rdi, [rbx+2A8h]
0x180019328  test    rdi, rdi
0x18001932b  jnz     loc_1800193F8
0x180019331  cmp     qword ptr [rbx+3C8h], 0
0x180019339  jz      short loc_180019366
0x18001933b  mov     rcx, [rbx+3E8h]; hModule
0x180019342  lea     rdx, ProcName; "AmsiUninitialize"
0x180019349  call    cs:__imp_GetProcAddress
0x18001934f  mov     rcx, [rbx+3C8h]
0x180019356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001935b  mov     qword ptr [rbx+3C8h], 0
0x180019366  mov     rcx, [rbx+3E8h]; hLibModule
0x18001936d  test    rcx, rcx
0x180019370  jz      short loc_180019383
0x180019372  call    cs:__imp_FreeLibrary
0x180019378  mov     qword ptr [rbx+3E8h], 0
0x180019383  mov     rcx, [rbx+3D8h]; bstrString
0x18001938a  test    rcx, rcx
0x18001938d  jnz     short loc_18001940D
0x18001938f  lock dec cs:?g_cLibRef@@3JA; long g_cLibRef
0x180019396  lea     rcx, [rbx+358h]; this
0x18001939d  call    ??1MUTX@@QEAA@XZ; MUTX::~MUTX(void)
0x1800193a2  lea     rcx, [rbx+138h]; this
0x1800193a9  call    ??1NamedItemList@@QEAA@XZ; NamedItemList::~NamedItemList(void)
0x1800193ae  lea     rcx, [rbx+0D8h]; this
0x1800193b5  mov     rbx, [rsp+28h+arg_0]
0x1800193ba  add     rsp, 20h
0x1800193be  pop     rdi
0x1800193bf  jmp     ??1JAmsi@@QEAA@XZ; JAmsi::~JAmsi(void)
0x1800193c4  lock inc dword ptr [rcx+0A0h]
0x1800193cb  jmp     loc_1800192DD
0x1800193d0  lock dec dword ptr [rbx+0A0h]
0x1800193d7  jmp     loc_1800192EF
0x1800193dc  mov     rax, [rcx]
0x1800193df  mov     rax, [rax+10h]
0x1800193e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193e8  mov     qword ptr [rbx+3A8h], 0
0x1800193f3  jmp     loc_180019321
0x1800193f8  mov     rcx, rdi; this
0x1800193fb  call    ??1TrackerClientRootList@@QEAA@XZ; TrackerClientRootList::~TrackerClientRootList(void)
0x180019400  mov     rcx, rdi; Block
0x180019403  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019408  jmp     loc_180019331
0x18001940d  call    cs:__imp_SysFreeString
0x180019413  jmp     loc_18001938F
```
