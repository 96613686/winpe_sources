# VolumeManager::~VolumeManager(void)

- ea: `0x1400f4084`
- end: `0x1400f4369`
- name: `??1VolumeManager@@MEAA@XZ`
- size: `741`
- prototype: `void __fastcall(VolumeManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x1400f44a0`

## callees

- `0x14000c910`
- `0x140012440`
- `0x14002c2f4`
- `0x14002c4f4`
- `0x140069770`
- `0x1400f1628`
- `0x1400f3f94`
- `0x1400f3fc0`
- `0x1400f4084`
- `0x140109724`
- `0x1401b8920`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1400f41c2`
- `KERNEL32!LeaveCriticalSection` at `0x1400f41c2`
- `KERNEL32!EnterCriticalSection` at `0x1400f413f`
- `KERNEL32!EnterCriticalSection` at `0x1400f413f`
- `KERNEL32!DeleteCriticalSection` at `0x1400f41e1`
- `KERNEL32!DeleteCriticalSection` at `0x1400f420c`
- `KERNEL32!DeleteCriticalSection` at `0x1400f422b`
- `KERNEL32!DeleteCriticalSection` at `0x1400f424a`
- `KERNEL32!DeleteCriticalSection` at `0x1400f4275`
- `KERNEL32!DeleteCriticalSection` at `0x1400f4294`
- `KERNEL32!DeleteCriticalSection` at `0x1400f42b3`
- `KERNEL32!DeleteCriticalSection` at `0x1400f42d2`
- `KERNEL32!DeleteCriticalSection` at `0x1400f42f1`
- `KERNEL32!DeleteCriticalSection` at `0x1400f41e1`
- `KERNEL32!DeleteCriticalSection` at `0x1400f420c`
- `KERNEL32!DeleteCriticalSection` at `0x1400f422b`
- `KERNEL32!DeleteCriticalSection` at `0x1400f424a`
- `KERNEL32!DeleteCriticalSection` at `0x1400f4275`
- `KERNEL32!DeleteCriticalSection` at `0x1400f4294`
- `KERNEL32!DeleteCriticalSection` at `0x1400f42b3`
- `KERNEL32!DeleteCriticalSection` at `0x1400f42d2`
- `KERNEL32!DeleteCriticalSection` at `0x1400f42f1`

## string_xrefs

- `0x1400f4183`: `Update volumeInfoHistory`
- `0x1400f4121`: ` volId:%? volPath:%? volState:%?`

## pseudocode

```c
void __fastcall VolumeManager::~VolumeManager(VolumeManager *this)
{
  struct MonitorContext *v2; // rbx
  struct MonitorContext *v3; // rcx
  const wchar_t *v4; // [rsp+30h] [rbp-30h] BYREF
  int v5; // [rsp+38h] [rbp-28h]
  int v6; // [rsp+3Ch] [rbp-24h]
  const wchar_t *v7; // [rsp+40h] [rbp-20h]
  const wchar_t *v8; // [rsp+48h] [rbp-18h] BYREF
  int v9; // [rsp+50h] [rbp-10h]
  int v10; // [rsp+54h] [rbp-Ch]
  const wchar_t *v11; // [rsp+58h] [rbp-8h]
  int v12; // [rsp+80h] [rbp+20h] BYREF
  __int64 v13; // [rsp+88h] [rbp+28h] BYREF

  *(_QWORD *)this = &VolumeManager::`vftable'{for `RefCountObject'};
  *((_QWORD *)this + 4) = &VolumeManager::`vftable'{for `ShutdownObject'};
  _InterlockedIncrement(&RefTrace_VolumeManager::numDestructorCalls);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v4 = L"VolumeManager::~VolumeManager";
    v5 = 5600;
    v6 = 5;
    v7 = L"VLMG";
    v12 = *((_DWORD *)this + 108);
    v13 = *((_QWORD *)this + 22) + 18LL;
    dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
      (unsigned int)&v4,
      (unsigned int)L" volId:%? volPath:%? volState:%?",
      (_DWORD)this + 184,
      (unsigned int)&v13,
      (__int64)&v12);
  }
  v2 = g_MonitorContext;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 288));
  *((_DWORD *)v2 + 70) = 1;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v8 = L"VolumeManager::~VolumeManager";
    v9 = 5616;
    v10 = 5;
    v11 = L"VLMG";
    dbgobj::DbgPrint<unsigned short>(&v8, L"Update volumeInfoHistory");
  }
  StateHistory::Delete((struct MonitorContext *)((char *)g_MonitorContext + 224), (VolumeManager *)((char *)this + 296));
  v3 = g_MonitorContext;
  *((_DWORD *)g_MonitorContext + 70) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 288));
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1664);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
  CREWLock::~CREWLock((VolumeManager *)((char *)this + 1480));
  std::list<Filter::FilterToken>::~list<Filter::FilterToken>((char *)this + 1464);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1408));
  std::list<Filter::FilterToken>::~list<Filter::FilterToken>((char *)this + 1392);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1336));
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1328);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1272));
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1264);
  std::list<ContentSetDeleteRequest>::~list<ContentSetDeleteRequest>((char *)this + 1248);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1192));
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1184);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1128));
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1120);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1064));
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 1056);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 25);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 992);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 936));
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 928);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 920);
  CREWLock::~CREWLock((VolumeManager *)((char *)this + 816));
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>((char *)this + 784);
  scoped_any<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,null_t,4>::~scoped_any<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,null_t,4>((char *)this + 768);
  ContentSetManagerMap::~ContentSetManagerMap((VolumeManager *)((char *)this + 648));
  _InterlockedIncrement(&RefTrace_VolumeManager::numDestructorCalls);
  BaseVolumeManager::~BaseVolumeManager(this);
}

```

## disassembly

```asm
0x1400f4084  mov     [rsp-18h+arg_10], rbx
0x1400f4089  mov     [rsp-18h+arg_18], rdi
0x1400f408e  push    rbp
0x1400f408f  push    r12
0x1400f4091  push    r15
0x1400f4093  mov     rbp, rsp
0x1400f4096  sub     rsp, 60h
0x1400f409a  mov     rdi, rcx
0x1400f409d  lea     rax, ??_7VolumeManager@@6BRefCountObject@@@; const VolumeManager::`vftable'{for `RefCountObject'}
0x1400f40a4  mov     [rcx], rax
0x1400f40a7  lea     rax, ??_7VolumeManager@@6BShutdownObject@@@; const VolumeManager::`vftable'{for `ShutdownObject'}
0x1400f40ae  mov     [rcx+20h], rax
0x1400f40b2  lock inc cs:?numDestructorCalls@RefTrace_VolumeManager@@1JC; long volatile RefTrace_VolumeManager::numDestructorCalls
0x1400f40b9  lea     r15, aVolumemanagerV_9; "VolumeManager::~VolumeManager"
0x1400f40c0  lea     r12, aVlmg; "VLMG"
0x1400f40c7  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400f40ce  test    rax, rax
0x1400f40d1  jz      short loc_1400F4131
0x1400f40d3  cmp     dword ptr [rax+40h], 0
0x1400f40d7  jz      short loc_1400F4131
0x1400f40d9  cmp     dword ptr [rax+38h], 5
0x1400f40dd  jl      short loc_1400F4131
0x1400f40df  mov     [rbp+var_30], r15
0x1400f40e3  mov     [rbp+var_28], 15E0h
0x1400f40ea  mov     [rbp+var_24], 5
0x1400f40f1  mov     [rbp+var_20], r12
0x1400f40f5  mov     eax, [rcx+1B0h]
0x1400f40fb  mov     [rbp+arg_0], eax
0x1400f40fe  mov     rax, [rcx+0B0h]
0x1400f4105  add     rax, 12h
0x1400f4109  mov     [rbp+arg_8], rax
0x1400f410d  lea     r8, [rcx+0B8h]
0x1400f4114  lea     rax, [rbp+arg_0]
0x1400f4118  mov     [rsp+60h+var_40], rax
0x1400f411d  lea     r9, [rbp+arg_8]
0x1400f4121  lea     rdx, aVolidVolpathVo_0; " volId:%? volPath:%? volState:%?"
0x1400f4128  lea     rcx, [rbp+var_30]
0x1400f412c  call    ??$DbgPrint@GU_GUID@@PEBGW4VOLUME_STATE@BaseVolumeManager@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBQEBGAEBW4VOLUME_STATE@BaseVolumeManager@@@Z; dbgobj::DbgPrint<ushort,_GUID,ushort const *,BaseVolumeManager::VOLUME_STATE>(ushort const *,_GUID const &,ushort const * const &,BaseVolumeManager::VOLUME_STATE const &)
0x1400f4131  mov     rbx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x1400f4138  lea     rcx, [rbx+120h]; lpCriticalSection
0x1400f413f  call    cs:__imp_EnterCriticalSection
0x1400f4146  nop     dword ptr [rax+rax+00h]
0x1400f414b  mov     dword ptr [rbx+118h], 1
0x1400f4155  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400f415c  test    rax, rax
0x1400f415f  jz      short loc_1400F4193
0x1400f4161  cmp     dword ptr [rax+40h], 0
0x1400f4165  jz      short loc_1400F4193
0x1400f4167  cmp     dword ptr [rax+38h], 5
0x1400f416b  jl      short loc_1400F4193
0x1400f416d  mov     [rbp+var_18], r15
0x1400f4171  mov     [rbp+var_10], 15F0h
0x1400f4178  mov     [rbp+var_C], 5
0x1400f417f  mov     [rbp+var_8], r12
0x1400f4183  lea     rdx, aUpdateVolumein; "Update volumeInfoHistory"
0x1400f418a  lea     rcx, [rbp+var_18]
0x1400f418e  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400f4193  lea     rdx, [rdi+128h]; struct HistoryRecord *
0x1400f419a  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x1400f41a1  add     rcx, 0E0h; this
0x1400f41a8  call    ?Delete@StateHistory@@MEAAXPEAVHistoryRecord@@@Z; StateHistory::Delete(HistoryRecord *)
0x1400f41ad  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x1400f41b4  and     dword ptr [rcx+118h], 0
0x1400f41bb  add     rcx, 120h; lpCriticalSection
0x1400f41c2  call    cs:__imp_LeaveCriticalSection
0x1400f41c9  nop     dword ptr [rax+rax+00h]
0x1400f41ce  lea     rcx, [rdi+680h]
0x1400f41d5  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400f41da  lea     rcx, [rdi+630h]; lpCriticalSection
0x1400f41e1  call    cs:__imp_DeleteCriticalSection
0x1400f41e8  nop     dword ptr [rax+rax+00h]
0x1400f41ed  lea     rcx, [rdi+5C8h]; this
0x1400f41f4  call    ??1CREWLock@@QEAA@XZ; CREWLock::~CREWLock(void)
0x1400f41f9  lea     rcx, [rdi+5B8h]
0x1400f4200  call    ??1?$list@UFilterToken@Filter@@V?$allocator@UFilterToken@Filter@@@std@@@std@@QEAA@XZ; std::list<Filter::FilterToken>::~list<Filter::FilterToken>(void)
0x1400f4205  lea     rcx, [rdi+580h]; lpCriticalSection
0x1400f420c  call    cs:__imp_DeleteCriticalSection
0x1400f4213  nop     dword ptr [rax+rax+00h]
0x1400f4218  lea     rcx, [rdi+570h]
0x1400f421f  call    ??1?$list@UFilterToken@Filter@@V?$allocator@UFilterToken@Filter@@@std@@@std@@QEAA@XZ; std::list<Filter::FilterToken>::~list<Filter::FilterToken>(void)
0x1400f4224  lea     rcx, [rdi+538h]; lpCriticalSection
0x1400f422b  call    cs:__imp_DeleteCriticalSection
0x1400f4232  nop     dword ptr [rax+rax+00h]
0x1400f4237  lea     rcx, [rdi+530h]
0x1400f423e  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400f4243  lea     rcx, [rdi+4F8h]; lpCriticalSection
0x1400f424a  call    cs:__imp_DeleteCriticalSection
0x1400f4251  nop     dword ptr [rax+rax+00h]
0x1400f4256  lea     rcx, [rdi+4F0h]
0x1400f425d  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400f4262  lea     rcx, [rdi+4E0h]
0x1400f4269  call    ??1?$list@VContentSetDeleteRequest@@V?$allocator@VContentSetDeleteRequest@@@std@@@std@@QEAA@XZ; std::list<ContentSetDeleteRequest>::~list<ContentSetDeleteRequest>(void)
0x1400f426e  lea     rcx, [rdi+4A8h]; lpCriticalSection
0x1400f4275  call    cs:__imp_DeleteCriticalSection
0x1400f427c  nop     dword ptr [rax+rax+00h]
0x1400f4281  lea     rcx, [rdi+4A0h]
0x1400f4288  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400f428d  lea     rcx, [rdi+468h]; lpCriticalSection
0x1400f4294  call    cs:__imp_DeleteCriticalSection
0x1400f429b  nop     dword ptr [rax+rax+00h]
0x1400f42a0  lea     rcx, [rdi+460h]
0x1400f42a7  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400f42ac  lea     rcx, [rdi+428h]; lpCriticalSection
0x1400f42b3  call    cs:__imp_DeleteCriticalSection
0x1400f42ba  nop     dword ptr [rax+rax+00h]
0x1400f42bf  lea     rcx, [rdi+420h]
0x1400f42c6  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400f42cb  lea     rcx, [rdi+3E8h]; lpCriticalSection
0x1400f42d2  call    cs:__imp_DeleteCriticalSection
0x1400f42d9  nop     dword ptr [rax+rax+00h]
0x1400f42de  lea     rcx, [rdi+3E0h]
0x1400f42e5  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400f42ea  lea     rcx, [rdi+3A8h]; lpCriticalSection
0x1400f42f1  call    cs:__imp_DeleteCriticalSection
0x1400f42f8  nop     dword ptr [rax+rax+00h]
0x1400f42fd  lea     rcx, [rdi+3A0h]
0x1400f4304  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400f4309  lea     rcx, [rdi+398h]
0x1400f4310  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400f4315  lea     rcx, [rdi+330h]; this
0x1400f431c  call    ??1CREWLock@@QEAA@XZ; CREWLock::~CREWLock(void)
0x1400f4321  lea     rcx, [rdi+310h]
0x1400f4328  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400f432d  lea     rcx, [rdi+300h]
0x1400f4334  call    ??1?$scoped_any@PEAXU?$close_fun@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@@Unull_t@@$03@@QEAA@XZ; scoped_any<void *,close_fun<int (*)(void *),&CloseHandle(void *)>,null_t,4>::~scoped_any<void *,close_fun<int (*)(void *),&CloseHandle(void *)>,null_t,4>(void)
0x1400f4339  lea     rcx, [rdi+288h]; this
0x1400f4340  call    ??1ContentSetManagerMap@@QEAA@XZ; ContentSetManagerMap::~ContentSetManagerMap(void)
0x1400f4345  lock inc cs:?numDestructorCalls@RefTrace_VolumeManager@@1JC; long volatile RefTrace_VolumeManager::numDestructorCalls
0x1400f434c  mov     rcx, rdi; this
0x1400f434f  lea     r11, [rsp+60h+var_s0]
0x1400f4354  mov     rbx, [r11+30h]
0x1400f4358  mov     rdi, [r11+38h]
0x1400f435c  mov     rsp, r11
0x1400f435f  pop     r15
0x1400f4361  pop     r12
0x1400f4363  pop     rbp
0x1400f4364  jmp     ??1BaseVolumeManager@@UEAA@XZ; BaseVolumeManager::~BaseVolumeManager(void)
```
