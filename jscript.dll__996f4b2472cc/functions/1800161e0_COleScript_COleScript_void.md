# COleScript::~COleScript(void)

- ea: `0x1800161e0`
- end: `0x180016434`
- name: `??1COleScript@@UEAA@XZ`
- size: `596`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180016d00`
- `0x1800179d0`

## callees

- `0x18000c8f4`
- `0x1800161e0`
- `0x18001643c`
- `0x180016728`
- `0x180017330`
- `0x180017398`
- `0x1800585c4`
- `0x180078264`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016423`
- `OLEAUT32!__imp_SysFreeString` at `0x180016423`
- `KERNEL32!FreeLibrary` at `0x180016382`
- `KERNEL32!FreeLibrary` at `0x180016382`
- `KERNEL32!GetProcAddress` at `0x180016353`
- `KERNEL32!GetProcAddress` at `0x180016353`
- `KERNEL32!DeleteCriticalSection` at `0x180016303`
- `KERNEL32!DeleteCriticalSection` at `0x180016303`

## string_xrefs

- `0x18001634c`: `AmsiUninitialize`

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
0x1800161e0  mov     [rsp+arg_0], rbx
0x1800161e5  push    rdi
0x1800161e6  sub     rsp, 20h
0x1800161ea  cmp     dword ptr [rcx+11Ch], 0
0x1800161f1  lea     rax, ??_7COleScript@@6BIActiveScript@@@; const COleScript::`vftable'{for `IActiveScript'}
0x1800161f8  mov     [rcx], rax
0x1800161fb  mov     rbx, rcx
0x1800161fe  lea     rax, ??_7COleScript@@6BIActiveScriptParse64@@@; const COleScript::`vftable'{for `IActiveScriptParse64'}
0x180016205  mov     [rcx+8], rax
0x180016209  lea     rax, ??_7COleScript@@6BIActiveScriptProperty@@@; const COleScript::`vftable'{for `IActiveScriptProperty'}
0x180016210  mov     [rcx+10h], rax
0x180016214  lea     rax, ??_7COleScript@@6BIActiveScriptEncode@@@; const COleScript::`vftable'{for `IActiveScriptEncode'}
0x18001621b  mov     [rcx+18h], rax
0x18001621f  lea     rax, ??_7COleScript@@6BIActiveScriptProfilerControl@@@; const COleScript::`vftable'{for `IActiveScriptProfilerControl'}
0x180016226  mov     [rcx+20h], rax
0x18001622a  lea     rax, ??_7COleScript@@6BIActiveScriptDebug64@@@; const COleScript::`vftable'{for `IActiveScriptDebug64'}
0x180016231  mov     [rcx+28h], rax
0x180016235  lea     rax, ??_7COleScript@@6BIDebugStackFrameSnifferEx64@@@; const COleScript::`vftable'{for `IDebugStackFrameSnifferEx64'}
0x18001623c  mov     [rcx+30h], rax
0x180016240  lea     rax, ??_7COleScript@@6BIProvideExpressionContexts@@@; const COleScript::`vftable'{for `IProvideExpressionContexts'}
0x180016247  mov     [rcx+38h], rax
0x18001624b  lea     rax, ??_7COleScript@@6BIRemoteDebugApplicationEvents@@@; const COleScript::`vftable'{for `IRemoteDebugApplicationEvents'}
0x180016252  mov     [rcx+40h], rax
0x180016256  lea     rax, ??_7COleScript@@6BIActiveScriptParseProcedure2_64@@@; const COleScript::`vftable'{for `IActiveScriptParseProcedure2_64'}
0x18001625d  mov     [rcx+48h], rax
0x180016261  lea     rax, ??_7COleScript@@6BIHostInfoUpdate@@@; const COleScript::`vftable'{for `IHostInfoUpdate'}
0x180016268  mov     [rcx+50h], rax
0x18001626c  lea     rax, ??_7COleScript@@6BIWrapTypeLibs@@@; const COleScript::`vftable'{for `IWrapTypeLibs'}
0x180016273  mov     [rcx+58h], rax
0x180016277  lea     rax, ??_7COleScript@@6BIScriptHelper@@@; const COleScript::`vftable'{for `IScriptHelper'}
0x18001627e  mov     [rcx+60h], rax
0x180016282  lea     rax, ??_7COleScript@@6BIObjectSafety@@@; const COleScript::`vftable'{for `IObjectSafety'}
0x180016289  mov     [rcx+68h], rax
0x18001628d  lea     rax, ??_7COleScript@@6BIVariantChangeType@@@; const COleScript::`vftable'{for `IVariantChangeType'}
0x180016294  mov     [rcx+70h], rax
0x180016298  lea     rax, ??_7COleScript@@6BIActiveScriptGarbageCollector@@@; const COleScript::`vftable'{for `IActiveScriptGarbageCollector'}
0x18001629f  mov     [rcx+78h], rax
0x1800162a3  lea     rax, ??_7COleScript@@6BIActiveScriptStats@@@; const COleScript::`vftable'{for `IActiveScriptStats'}
0x1800162aa  mov     [rcx+80h], rax
0x1800162b1  lea     rax, ??_7COleScript@@6BITrackingService@@@; const COleScript::`vftable'{for `ITrackingService'}
0x1800162b8  mov     [rcx+88h], rax
0x1800162bf  lea     rax, ??_7COleScript@@6BIActiveScriptTraceInfo@@@; const COleScript::`vftable'{for `IActiveScriptTraceInfo'}
0x1800162c6  mov     [rcx+90h], rax
0x1800162cd  lea     rax, ??_7COleScript@@6BIActiveScriptSIPInfo@@@; const COleScript::`vftable'{for `IActiveScriptSIPInfo'}
0x1800162d4  mov     [rcx+98h], rax
0x1800162db  jnz     loc_1800163DA
0x1800162e1  call    ?CloseInternal@COleScript@@QEAAJXZ; COleScript::CloseInternal(void)
0x1800162e6  cmp     dword ptr [rbx+11Ch], 0
0x1800162ed  jnz     loc_1800163E6
0x1800162f3  cmp     dword ptr [rbx+230h], 0
0x1800162fa  jz      short loc_18001630F
0x1800162fc  lea     rcx, [rbx+238h]; lpCriticalSection
0x180016303  call    cs:__imp_DeleteCriticalSection
0x18001630a  nop     dword ptr [rax+rax+00h]
0x18001630f  lea     rcx, [rbx+260h]; struct tagEXCEPINFO *
0x180016316  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x18001631b  mov     rcx, [rbx+3A8h]
0x180016322  test    rcx, rcx
0x180016325  jnz     loc_1800163F2
0x18001632b  mov     rdi, [rbx+2A8h]
0x180016332  test    rdi, rdi
0x180016335  jnz     loc_18001640E
0x18001633b  cmp     qword ptr [rbx+3C8h], 0
0x180016343  jz      short loc_180016376
0x180016345  mov     rcx, [rbx+3E8h]; hModule
0x18001634c  lea     rdx, ProcName; "AmsiUninitialize"
0x180016353  call    cs:__imp_GetProcAddress
0x18001635a  nop     dword ptr [rax+rax+00h]
0x18001635f  mov     rcx, [rbx+3C8h]
0x180016366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001636b  mov     qword ptr [rbx+3C8h], 0
0x180016376  mov     rcx, [rbx+3E8h]; hLibModule
0x18001637d  test    rcx, rcx
0x180016380  jz      short loc_180016399
0x180016382  call    cs:__imp_FreeLibrary
0x180016389  nop     dword ptr [rax+rax+00h]
0x18001638e  mov     qword ptr [rbx+3E8h], 0
0x180016399  mov     rcx, [rbx+3D8h]; bstrString
0x1800163a0  test    rcx, rcx
0x1800163a3  jnz     short loc_180016423
0x1800163a5  lock dec cs:?g_cLibRef@@3JA; long g_cLibRef
0x1800163ac  lea     rcx, [rbx+358h]; this
0x1800163b3  call    ??1MUTX@@QEAA@XZ; MUTX::~MUTX(void)
0x1800163b8  lea     rcx, [rbx+138h]; this
0x1800163bf  call    ??1NamedItemList@@QEAA@XZ; NamedItemList::~NamedItemList(void)
0x1800163c4  lea     rcx, [rbx+0D8h]; this
0x1800163cb  mov     rbx, [rsp+28h+arg_0]
0x1800163d0  add     rsp, 20h
0x1800163d4  pop     rdi
0x1800163d5  jmp     ??1JAmsi@@QEAA@XZ; JAmsi::~JAmsi(void)
0x1800163da  lock inc dword ptr [rcx+0A0h]
0x1800163e1  jmp     loc_1800162E1
0x1800163e6  lock dec dword ptr [rbx+0A0h]
0x1800163ed  jmp     loc_1800162F3
0x1800163f2  mov     rax, [rcx]
0x1800163f5  mov     rax, [rax+10h]
0x1800163f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163fe  mov     qword ptr [rbx+3A8h], 0
0x180016409  jmp     loc_18001632B
0x18001640e  mov     rcx, rdi; this
0x180016411  call    ??1TrackerClientRootList@@QEAA@XZ; TrackerClientRootList::~TrackerClientRootList(void)
0x180016416  mov     rcx, rdi; Block
0x180016419  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001641e  jmp     loc_18001633B
0x180016423  call    cs:__imp_SysFreeString
0x18001642a  nop     dword ptr [rax+rax+00h]
0x18001642f  jmp     loc_1800163A5
```
