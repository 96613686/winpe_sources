# InConnection::SubmitSpecialUpdate(_GUID const &,ID_UPDATE const *,SYNC_TYPE,ulong *)

- ea: `0x14016c03c`
- end: `0x14016c550`
- name: `?SubmitSpecialUpdate@InConnection@@QEAAPEAVFrsStatus@@AEBU_GUID@@PEBVID_UPDATE@@W4SYNC_TYPE@@PEAK@Z`
- size: `1300`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14013e770`
- `0x1401914e8`
- `0x1401939c8`

## callees

- `0x1400036d0`
- `0x14000c910`
- `0x14000d980`
- `0x14000dcc0`
- `0x140024ebc`
- `0x14002c2f4`
- `0x14006a550`
- `0x1400812c8`
- `0x1400925a8`
- `0x14015cee8`
- `0x14015e3dc`
- `0x140161208`
- `0x140161300`
- `0x140164ab0`
- `0x14016c03c`
- `0x14016c558`
- `0x14018ede0`
- `0x140190104`
- `0x1401b9494`
- `0x1401bda10`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14016c48a`
- `KERNEL32!LeaveCriticalSection` at `0x14016c48a`
- `KERNEL32!EnterCriticalSection` at `0x14016c3f2`
- `KERNEL32!EnterCriticalSection` at `0x14016c3f2`
- `KERNEL32!GetCurrentThreadId` at `0x14016c256`
- `KERNEL32!GetCurrentThreadId` at `0x14016c314`
- `KERNEL32!GetCurrentThreadId` at `0x14016c4eb`
- `KERNEL32!GetCurrentThreadId` at `0x14016c256`
- `KERNEL32!GetCurrentThreadId` at `0x14016c314`
- `KERNEL32!GetCurrentThreadId` at `0x14016c4eb`

## string_xrefs

- `0x14016c444`: `Update syncInfoHistory`
- `0x14016c155`: `uid:%? gvsn:%? fileName:%? connId:%? csId:%? csName:%ws`
- `0x14016c1b4`: `No more update. connId:%? csId:%? csName:%ws`
- `0x14016c0c4`: `InConnection::SubmitSpecialUpdate`
- `0x14016c1cb`: `InConnection::SubmitSpecialUpdate`
- `0x14016c420`: `InConnection::SubmitSpecialUpdate`
- `0x14016c304`: `Received %? update when the session has already been closed. connId:%? csId:%? csName:%ws`
- `0x14016c246`: `Received slowsync update without an active session. connId:%? csId:%? csName:%ws`
- `0x14016c331`: `InConnection::SubmitSpecialUpdate`
- `0x14016c4cf`: `InConnection::SubmitSpecialUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall InConnection::SubmitSpecialUpdate(
        _DWORD *a1,
        const struct _GUID *a2,
        __int64 a3,
        unsigned int a4,
        signed __int32 *a5)
{
  __int64 v9; // r15
  unsigned int *v10; // r12
  signed __int32 *v11; // r14
  __int64 v12; // rdx
  struct InConnection::InConnectionContentSetContext *v13; // rbx
  __int64 SpecialSession; // rax
  LPCRITICAL_SECTION v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdx
  signed __int32 *v19; // r8
  const wchar_t *v20; // r9
  const wchar_t *v21; // r10
  __int64 v22; // rcx
  struct UpdateManager *v23; // r14
  signed __int32 v24; // ecx
  struct MonitorContext *v25; // rdi
  struct _RTL_CRITICAL_SECTION *v26; // rcx
  __int64 v27; // r8
  DWORD v28; // eax
  __int64 v29; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp-59h]
  DWORD v32; // [rsp+40h] [rbp-59h]
  const wchar_t *v33; // [rsp+58h] [rbp-41h] BYREF
  int v34; // [rsp+60h] [rbp-39h]
  int v35; // [rsp+64h] [rbp-35h]
  const wchar_t *v36; // [rsp+68h] [rbp-31h]
  __int64 v37; // [rsp+70h] [rbp-29h] BYREF
  __int64 v38; // [rsp+78h] [rbp-21h] BYREF
  __int64 v39; // [rsp+80h] [rbp-19h] BYREF
  const wchar_t *v40; // [rsp+88h] [rbp-11h] BYREF
  int v41; // [rsp+90h] [rbp-9h]
  int v42; // [rsp+94h] [rbp-5h]
  const wchar_t *v43; // [rsp+98h] [rbp-1h]
  struct UpdateManager *v44; // [rsp+A0h] [rbp+7h]
  _BYTE v45[64]; // [rsp+A8h] [rbp+Fh] BYREF
  struct InConnection::InConnectionContentSetContext *v46; // [rsp+F8h] [rbp+5Fh] BYREF
  __int64 v47; // [rsp+108h] [rbp+6Fh]
  unsigned int v48; // [rsp+110h] [rbp+77h]

  v48 = a4;
  v47 = a3;
  v9 = 0;
  v46 = 0;
  v10 = 0;
  v11 = a5;
  if ( a5 )
    *a5 = 0;
  ScopedLock::ScopedLock((ScopedLock *)v45, (struct ScopedCS *)(a1 + 248));
  if ( !(unsigned int)RefMap<_GUID,InConnection::InConnectionContentSetContext,std::less<_GUID>>::Find(
                        a1 + 276,
                        a2,
                        &v46) )
    goto LABEL_41;
  v12 = a4;
  v13 = v46;
  SpecialSession = InConnection::InConnectionContentSetContext::GetSpecialSession(v46, v12, 0);
  v37 = SpecialSession;
  v15 = g_DebugLog;
  if ( a3 )
  {
    if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
      goto LABEL_14;
    v40 = L"InConnection::SubmitSpecialUpdate";
    v41 = 4025;
    v42 = 4;
    v43 = L"INCO";
    v38 = *(_QWORD *)(*((_QWORD *)v13 + 4) + 200LL) + 18LL;
    dbgobj::DbgPrint<unsigned short,UID,GVSN,unsigned short [261],_GUID,_GUID,unsigned short const *>(
      (unsigned int)&v40,
      (unsigned int)L"uid:%? gvsn:%? fileName:%? connId:%? csId:%? csName:%ws",
      a3,
      a3 + 24,
      a3 + 156,
      (__int64)(a1 + 42),
      (__int64)a2,
      (__int64)&v38);
  }
  else
  {
    if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
      goto LABEL_14;
    v33 = L"InConnection::SubmitSpecialUpdate";
    v34 = 4035;
    v35 = 4;
    v36 = L"INCO";
    v38 = *(_QWORD *)(*((_QWORD *)v13 + 4) + 200LL) + 18LL;
    dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *>(
      (unsigned int)&v33,
      (unsigned int)L"No more update. connId:%? csId:%? csName:%ws",
      (_DWORD)a1 + 168,
      (_DWORD)a2,
      (__int64)&v38);
  }
  SpecialSession = v37;
  v15 = g_DebugLog;
LABEL_14:
  if ( *((_DWORD *)v13 + 55) != 5 )
    goto LABEL_41;
  if ( !*(_QWORD *)(SpecialSession + 8) )
  {
    if ( !a3 )
    {
      InConnection::ClearSlowSync((InConnection *)a1, a2);
      goto LABEL_41;
    }
    if ( v15 && LODWORD(v15[1].LockSemaphore) && SLODWORD(v15[1].OwningThread) >= 2 )
    {
      v33 = L"InConnection::SubmitSpecialUpdate";
      v34 = 4050;
      v35 = 2;
      v36 = L"INCO";
      a5 = (signed __int32 *)(*(_QWORD *)(*((_QWORD *)v13 + 4) + 200LL) + 18LL);
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *>(
        (unsigned int)&v33,
        (unsigned int)L"Received slowsync update without an active session. connId:%? csId:%? csName:%ws",
        (_DWORD)a1 + 168,
        (_DWORD)a2,
        (__int64)&a5);
    }
    CurrentThreadId = GetCurrentThreadId();
    v17 = FrsStatusList::PushNewError(
            v16,
            9031,
            0,
            3,
            "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
            "InConnection::SubmitSpecialUpdate",
            4056,
            CurrentThreadId,
            0);
    goto LABEL_29;
  }
  v39 = **(_QWORD **)SpecialSession;
  if ( !*(_DWORD *)(std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(&v39)
                  + 64) )
  {
    if ( v18 && *(_DWORD *)(v18 + 64) && *(int *)(v18 + 56) >= 2 )
    {
      v33 = v20;
      v34 = 4069;
      v35 = 2;
      v36 = v21;
      a5 = (signed __int32 *)(*(_QWORD *)(*((_QWORD *)v13 + 4) + 200LL) + 18LL);
      v39 = ContentSetManager::SyncName(v48);
      dbgobj::DbgPrint<unsigned short,unsigned short const *,_GUID,_GUID,unsigned short const *>(
        (unsigned int)&v33,
        (unsigned int)L"Received %? update when the session has already been closed. connId:%? csId:%? csName:%ws",
        (unsigned int)&v39,
        (_DWORD)a1 + 168,
        (__int64)a2,
        (__int64)&a5);
    }
    v32 = GetCurrentThreadId();
    v17 = FrsStatusList::PushNewError(
            v22,
            9031,
            0,
            3,
            "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
            "InConnection::SubmitSpecialUpdate",
            4077,
            v32,
            0);
LABEL_29:
    v10 = (unsigned int *)v17;
    goto LABEL_41;
  }
  if ( a3 )
  {
    v37 = (__int64)v19;
    if ( !*((_QWORD *)v13 + 6) )
    {
      v23 = (struct UpdateManager *)operator new(0x40u);
      v44 = v23;
      Settings::GenericDwordSetting::operator()(&Settings::UpdateWorkerThreadCount);
      *((_QWORD *)v13 + 6) = UpdateManager::UpdateManager(v23, (__int64)(a1 + 316), (__int64)v13 + 32);
      v11 = a5;
    }
    v24 = _InterlockedIncrement((volatile signed __int32 *)(std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(&v37)
                                                          + 52));
    if ( v11 )
      *v11 = v24;
    v25 = g_MonitorContext;
    EnterCriticalSection((LPCRITICAL_SECTION)g_MonitorContext + 15);
    *((_DWORD *)v25 + 148) = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v33 = L"InConnection::SubmitSpecialUpdate";
      v34 = 4103;
      v35 = 5;
      v36 = L"INCO";
      dbgobj::DbgPrint<unsigned short>(&v33, L"Update syncInfoHistory");
    }
    ++a1[181];
    StateHistory::Update((struct MonitorContext *)((char *)g_MonitorContext + 536), (struct HistoryRecord *)(a1 + 134));
    v26 = (struct _RTL_CRITICAL_SECTION *)g_MonitorContext;
    *((_DWORD *)g_MonitorContext + 148) = 0;
    LeaveCriticalSection(v26 + 15);
    UpdateManager::ProduceUpdate(*((struct UpdateManager **)v13 + 6));
  }
  else
  {
    a5 = v19;
    *(_DWORD *)(std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(&a5) + 64) = 0;
    v10 = (unsigned int *)InConnection::CommitSession((InConnection *)a1, v13, v27, v48);
  }
LABEL_41:
  ScopedLock::~ScopedLock((ScopedLock *)v45);
  if ( v10 )
  {
    v28 = GetCurrentThreadId();
    v9 = FrsStatusList::PushNewError(
           v29,
           v10[1],
           v10[2],
           *v10,
           "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
           "InConnection::SubmitSpecialUpdate",
           4129,
           v28,
           v10);
  }
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v46);
  return v9;
}

```

## disassembly

```asm
0x14016c03c  mov     rax, rsp
0x14016c03f  mov     [rax+10h], rbx
0x14016c043  mov     [rax+20h], r9d
0x14016c047  mov     [rax+18h], r8
0x14016c04b  push    rbp
0x14016c04c  push    rsi
0x14016c04d  push    rdi
0x14016c04e  push    r12
0x14016c050  push    r13
0x14016c052  push    r14
0x14016c054  push    r15
0x14016c056  lea     rbp, [rax-57h]
0x14016c05a  sub     rsp, 0B0h
0x14016c061  mov     ebx, r9d
0x14016c064  mov     rsi, r8
0x14016c067  mov     rdi, rdx
0x14016c06a  mov     r13, rcx
0x14016c06d  xor     r15d, r15d
0x14016c070  mov     [rbp+4Fh+arg_0], r15
0x14016c074  mov     r12d, r15d
0x14016c077  mov     r14, [rbp+4Fh+arg_20]
0x14016c07b  test    r14, r14
0x14016c07e  jz      short loc_14016C083
0x14016c080  mov     [r14], r15d
0x14016c083  lea     rdx, [rcx+3E0h]; struct ScopedCS *
0x14016c08a  lea     rcx, [rbp+4Fh+var_40]; this
0x14016c08e  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x14016c093  nop
0x14016c094  lea     rcx, [r13+450h]
0x14016c09b  lea     r8, [rbp+4Fh+arg_0]
0x14016c09f  mov     rdx, rdi
0x14016c0a2  call    ?Find@?$RefMap@U_GUID@@VInConnectionContentSetContext@InConnection@@U?$less@U_GUID@@@std@@@@QEAAHAEBU_GUID@@AEAPEAVInConnectionContentSetContext@InConnection@@@Z; RefMap<_GUID,InConnection::InConnectionContentSetContext,std::less<_GUID>>::Find(_GUID const &,InConnection::InConnectionContentSetContext * &)
0x14016c0a7  test    eax, eax
0x14016c0a9  jz      loc_14016C4CF
0x14016c0af  xor     r8d, r8d
0x14016c0b2  mov     edx, ebx
0x14016c0b4  mov     rbx, [rbp+4Fh+arg_0]
0x14016c0b8  mov     rcx, rbx
0x14016c0bb  call    ?GetSpecialSession@InConnectionContentSetContext@InConnection@@QEAAAEAV?$list@VSessionInfo@@V?$allocator@VSessionInfo@@@std@@@std@@W4SYNC_TYPE@@PEAK@Z; InConnection::InConnectionContentSetContext::GetSpecialSession(SYNC_TYPE,ulong *)
0x14016c0c0  mov     [rbp+4Fh+var_78], rax
0x14016c0c4  lea     r9, aInconnectionSu; "InConnection::SubmitSpecialUpdate"
0x14016c0cb  lea     r10, aInco; "INCO"
0x14016c0d2  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14016c0d9  test    rsi, rsi
0x14016c0dc  jz      loc_14016C167
0x14016c0e2  test    rdx, rdx
0x14016c0e5  jz      loc_14016C1DD
0x14016c0eb  cmp     [rdx+40h], r15d
0x14016c0ef  jz      loc_14016C1DD
0x14016c0f5  cmp     dword ptr [rdx+38h], 4
0x14016c0f9  jl      loc_14016C1DD
0x14016c0ff  mov     [rbp+4Fh+var_60], r9
0x14016c103  mov     [rbp+4Fh+var_58], 0FB9h
0x14016c10a  mov     [rbp+4Fh+var_54], 4
0x14016c111  mov     [rbp+4Fh+var_50], r10
0x14016c115  mov     rax, [rbx+20h]
0x14016c119  mov     rcx, [rax+0C8h]
0x14016c120  add     rcx, 12h
0x14016c124  mov     [rbp+4Fh+var_70], rcx
0x14016c128  lea     rax, [r13+0A8h]
0x14016c12f  lea     rcx, [rsi+9Ch]
0x14016c136  lea     r9, [rsi+18h]
0x14016c13a  lea     rdx, [rbp+4Fh+var_70]
0x14016c13e  mov     qword ptr [rsp+0E0h+var_A8], rdx
0x14016c143  mov     [rsp+0E0h+var_B0], rdi
0x14016c148  mov     [rsp+0E0h+var_B8], rax
0x14016c14d  mov     [rsp+0E0h+var_C0], rcx
0x14016c152  mov     r8, rsi
0x14016c155  lea     rdx, aUidGvsnFilenam; "uid:%? gvsn:%? fileName:%? connId:%? cs"...
0x14016c15c  lea     rcx, [rbp+4Fh+var_60]
0x14016c160  call    ??$DbgPrint@GVUID@@VGVSN@@$$BY0BAF@GU_GUID@@U3@PEBG@dbgobj@@QEAA_KPEBGAEBVUID@@AEBVGVSN@@AEAY0BAF@$$CBGAEBU_GUID@@4AEBQEBG@Z; dbgobj::DbgPrint<ushort,UID,GVSN,ushort [261],_GUID,_GUID,ushort const *>(ushort const *,UID const &,GVSN const &,ushort const (&)[261],_GUID const &,_GUID const &,ushort const * const &)
0x14016c165  jmp     short loc_14016C1C4
0x14016c167  test    rdx, rdx
0x14016c16a  jz      short loc_14016C1DD
0x14016c16c  cmp     [rdx+40h], r15d
0x14016c170  jz      short loc_14016C1DD
0x14016c172  cmp     dword ptr [rdx+38h], 4
0x14016c176  jl      short loc_14016C1DD
0x14016c178  mov     [rbp+4Fh+var_90], r9
0x14016c17c  mov     [rbp+4Fh+var_88], 0FC3h
0x14016c183  mov     [rbp+4Fh+var_84], 4
0x14016c18a  mov     [rbp+4Fh+var_80], r10
0x14016c18e  mov     rax, [rbx+20h]
0x14016c192  mov     rcx, [rax+0C8h]
0x14016c199  add     rcx, 12h
0x14016c19d  mov     [rbp+4Fh+var_70], rcx
0x14016c1a1  lea     r8, [r13+0A8h]
0x14016c1a8  lea     rax, [rbp+4Fh+var_70]
0x14016c1ac  mov     [rsp+0E0h+var_C0], rax
0x14016c1b1  mov     r9, rdi
0x14016c1b4  lea     rdx, aNoMoreUpdateCo; "No more update. connId:%? csId:%? csNam"...
0x14016c1bb  lea     rcx, [rbp+4Fh+var_90]
0x14016c1bf  call    ??$DbgPrint@GU_GUID@@U1@PEBG@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBQEBG@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,ushort const *>(ushort const *,_GUID const &,_GUID const &,ushort const * const &)
0x14016c1c4  lea     r10, aInco; "INCO"
0x14016c1cb  lea     r9, aInconnectionSu; "InConnection::SubmitSpecialUpdate"
0x14016c1d2  mov     rax, [rbp+4Fh+var_78]
0x14016c1d6  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14016c1dd  cmp     dword ptr [rbx+0DCh], 5
0x14016c1e4  jnz     loc_14016C4CF
0x14016c1ea  cmp     [rax+8], r15
0x14016c1ee  jnz     loc_14016C288
0x14016c1f4  test    rsi, rsi
0x14016c1f7  jz      short loc_14016C278
0x14016c1f9  test    rdx, rdx
0x14016c1fc  jz      short loc_14016C256
0x14016c1fe  cmp     [rdx+40h], r15d
0x14016c202  jz      short loc_14016C256
0x14016c204  cmp     dword ptr [rdx+38h], 2
0x14016c208  jl      short loc_14016C256
0x14016c20a  mov     [rbp+4Fh+var_90], r9
0x14016c20e  mov     [rbp+4Fh+var_88], 0FD2h
0x14016c215  mov     [rbp+4Fh+var_84], 2
0x14016c21c  mov     [rbp+4Fh+var_80], r10
0x14016c220  mov     rax, [rbx+20h]
0x14016c224  mov     rcx, [rax+0C8h]
0x14016c22b  add     rcx, 12h
0x14016c22f  mov     [rbp+4Fh+arg_20], rcx
0x14016c233  lea     r8, [r13+0A8h]
0x14016c23a  lea     rax, [rbp+4Fh+arg_20]
0x14016c23e  mov     [rsp+0E0h+var_C0], rax
0x14016c243  mov     r9, rdi
0x14016c246  lea     rdx, aReceivedSlowsy; "Received slowsync update without an act"...
0x14016c24d  lea     rcx, [rbp+4Fh+var_90]
0x14016c251  call    ??$DbgPrint@GU_GUID@@U1@PEBG@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBQEBG@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,ushort const *>(ushort const *,_GUID const &,_GUID const &,ushort const * const &)
0x14016c256  call    cs:__imp_GetCurrentThreadId
0x14016c25d  nop     dword ptr [rax+rax+00h]
0x14016c262  mov     qword ptr [rsp+0E0h+var_A8+8], r15
0x14016c267  mov     [rsp+0E0h+var_A8], eax
0x14016c26b  mov     dword ptr [rsp+0E0h+var_B0], 0FD8h
0x14016c273  jmp     loc_14016C331
0x14016c278  mov     rdx, rdi; struct _GUID *
0x14016c27b  mov     rcx, r13; this
0x14016c27e  call    ?ClearSlowSync@InConnection@@AEAAXAEBU_GUID@@@Z; InConnection::ClearSlowSync(_GUID const &)
0x14016c283  jmp     loc_14016C4CF
0x14016c288  mov     r8, [rax]
0x14016c28b  mov     r8, [r8]
0x14016c28e  mov     [rbp+4Fh+var_68], r8
0x14016c292  lea     rcx, [rbp+4Fh+var_68]
0x14016c296  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@UCONTENT_SET_RECORD@@@std@@@std@@@std@@QEBAPEAUCONTENT_SET_RECORD@@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(void)
0x14016c29b  cmp     [rax+40h], r15d
0x14016c29f  jnz     loc_14016C364
0x14016c2a5  test    rdx, rdx
0x14016c2a8  jz      short loc_14016C314
0x14016c2aa  cmp     [rdx+40h], r15d
0x14016c2ae  jz      short loc_14016C314
0x14016c2b0  cmp     dword ptr [rdx+38h], 2
0x14016c2b4  jl      short loc_14016C314
0x14016c2b6  mov     [rbp+4Fh+var_90], r9
0x14016c2ba  mov     [rbp+4Fh+var_88], 0FE5h
0x14016c2c1  mov     [rbp+4Fh+var_84], 2
0x14016c2c8  mov     [rbp+4Fh+var_80], r10
0x14016c2cc  mov     rax, [rbx+20h]
0x14016c2d0  mov     rcx, [rax+0C8h]
0x14016c2d7  add     rcx, 12h
0x14016c2db  mov     [rbp+4Fh+arg_20], rcx
0x14016c2df  mov     ecx, [rbp+4Fh+arg_18]
0x14016c2e2  call    ?SyncName@ContentSetManager@@SAPEBGW4SYNC_TYPE@@@Z; ContentSetManager::SyncName(SYNC_TYPE)
0x14016c2e7  mov     [rbp+4Fh+var_68], rax
0x14016c2eb  lea     r9, [r13+0A8h]
0x14016c2f2  lea     rax, [rbp+4Fh+arg_20]
0x14016c2f6  mov     [rsp+0E0h+var_B8], rax
0x14016c2fb  mov     [rsp+0E0h+var_C0], rdi
0x14016c300  lea     r8, [rbp+4Fh+var_68]
0x14016c304  lea     rdx, aReceivedUpdate; "Received %? update when the session has"...
0x14016c30b  lea     rcx, [rbp+4Fh+var_90]
0x14016c30f  call    ??$DbgPrint@GPEBGU_GUID@@U1@PEBG@dbgobj@@QEAA_KPEBGAEBQEBGAEBU_GUID@@21@Z; dbgobj::DbgPrint<ushort,ushort const *,_GUID,_GUID,ushort const *>(ushort const *,ushort const * const &,_GUID const &,_GUID const &,ushort const * const &)
0x14016c314  call    cs:__imp_GetCurrentThreadId
0x14016c31b  nop     dword ptr [rax+rax+00h]
0x14016c320  mov     qword ptr [rsp+0E0h+var_A8+8], r15
0x14016c325  mov     [rsp+0E0h+var_A8], eax
0x14016c329  mov     dword ptr [rsp+0E0h+var_B0], 0FEDh
0x14016c331  lea     rbx, aInconnectionSu_0; "InConnection::SubmitSpecialUpdate"
0x14016c338  mov     [rsp+0E0h+var_B8], rbx
0x14016c33d  lea     rdi, aBaseFsRemotefs_1; "base\\fs\\remotefs\\frs\\src\\sync\\inc"...
0x14016c344  mov     [rsp+0E0h+var_C0], rdi
0x14016c349  mov     r9d, 3
0x14016c34f  xor     r8d, r8d
0x14016c352  mov     edx, 2347h
0x14016c357  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14016c35c  mov     r12, rax
0x14016c35f  jmp     loc_14016C4DD
0x14016c364  test    rsi, rsi
0x14016c367  jz      loc_14016C4AC
0x14016c36d  mov     [rbp+4Fh+var_78], r8
0x14016c371  cmp     [rbx+30h], r15
0x14016c375  jnz     short loc_14016C3C7
0x14016c377  mov     ecx, 40h ; '@'; Size
0x14016c37c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14016c381  mov     r14, rax
0x14016c384  mov     [rbp+4Fh+var_48], rax
0x14016c388  lea     rdi, [rbx+20h]
0x14016c38c  lea     rcx, ?UpdateWorkerThreadCount@Settings@@3VCUpdateWorkerThreadCount@1@A; Settings::CUpdateWorkerThreadCount Settings::UpdateWorkerThreadCount
0x14016c393  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x14016c398  lea     rcx, [r13+4F0h]
0x14016c39f  mov     [rsp+0E0h+var_B8], rdi
0x14016c3a4  mov     [rsp+0E0h+var_C0], rcx
0x14016c3a9  lea     r9, [rbx+28h]
0x14016c3ad  mov     r8, r13
0x14016c3b0  mov     edx, eax
0x14016c3b2  mov     rcx, r14
0x14016c3b5  call    ??0UpdateManager@@QEAA@HPEAVInConnection@@AEAV?$ScopedRef@VVolumeManager@@@@AEAV?$ScopedRef@VReplicaSetManager@@@@AEAV?$ScopedRef@VContentSetManager@@@@@Z; UpdateManager::UpdateManager(int,InConnection *,ScopedRef<VolumeManager> &,ScopedRef<ReplicaSetManager> &,ScopedRef<ContentSetManager> &)
0x14016c3ba  nop
0x14016c3bb  mov     [rbx+30h], rax
0x14016c3bf  mov     rsi, [rbp+4Fh+arg_10]
0x14016c3c3  mov     r14, [rbp+4Fh+arg_20]
0x14016c3c7  lea     rcx, [rbp+4Fh+var_78]
0x14016c3cb  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@UCONTENT_SET_RECORD@@@std@@@std@@@std@@QEBAPEAUCONTENT_SET_RECORD@@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(void)
0x14016c3d0  mov     ecx, 1
0x14016c3d5  lock xadd [rax+34h], ecx
0x14016c3da  inc     ecx
0x14016c3dc  test    r14, r14
0x14016c3df  jz      short loc_14016C3E4
0x14016c3e1  mov     [r14], ecx
0x14016c3e4  mov     rdi, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14016c3eb  lea     rcx, [rdi+258h]; lpCriticalSection
0x14016c3f2  call    cs:__imp_EnterCriticalSection
0x14016c3f9  nop     dword ptr [rax+rax+00h]
0x14016c3fe  mov     dword ptr [rdi+250h], 1
0x14016c408  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14016c40f  test    rax, rax
0x14016c412  jz      short loc_14016C454
0x14016c414  cmp     [rax+40h], r15d
0x14016c418  jz      short loc_14016C454
0x14016c41a  cmp     dword ptr [rax+38h], 5
0x14016c41e  jl      short loc_14016C454
0x14016c420  lea     rax, aInconnectionSu; "InConnection::SubmitSpecialUpdate"
0x14016c427  mov     [rbp+4Fh+var_90], rax
0x14016c42b  mov     [rbp+4Fh+var_88], 1007h
0x14016c432  mov     [rbp+4Fh+var_84], 5
0x14016c439  lea     rax, aInco; "INCO"
0x14016c440  mov     [rbp+4Fh+var_80], rax
0x14016c444  lea     rdx, aUpdateSyncinfo; "Update syncInfoHistory"
0x14016c44b  lea     rcx, [rbp+4Fh+var_90]
0x14016c44f  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14016c454  inc     dword ptr [r13+2D4h]
0x14016c45b  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14016c462  add     rcx, 218h; this
0x14016c469  lea     rdx, [r13+218h]; struct HistoryRecord *
0x14016c470  call    ?Update@StateHistory@@MEAAXPEAVHistoryRecord@@@Z; StateHistory::Update(HistoryRecord *)
0x14016c475  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14016c47c  mov     [rcx+250h], r15d
0x14016c483  add     rcx, 258h; lpCriticalSection
0x14016c48a  call    cs:__imp_LeaveCriticalSection
0x14016c491  nop     dword ptr [rax+rax+00h]
0x14016c496  mov     r9d, [rbp+4Fh+arg_18]
0x14016c49a  mov     r8, [rbp+4Fh+var_78]
0x14016c49e  mov     rdx, rsi
0x14016c4a1  mov     rcx, [rbx+30h]; struct UpdateManager *
0x14016c4a5  call    ?ProduceUpdate@UpdateManager@@QEAAXAEBVID_UPDATE@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@VSessionInfo@@@std@@@std@@@std@@W4SYNC_TYPE@@@Z; UpdateManager::ProduceUpdate(ID_UPDATE const &,std::_List_iterator<std::_List_val<std::_List_simple_types<SessionInfo>>>,SYNC_TYPE)
0x14016c4aa  jmp     short loc_14016C4CF
0x14016c4ac  mov     [rbp+4Fh+arg_20], r8
0x14016c4b0  lea     rcx, [rbp+4Fh+arg_20]
0x14016c4b4  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@UCONTENT_SET_RECORD@@@std@@@std@@@std@@QEBAPEAUCONTENT_SET_RECORD@@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(void)
0x14016c4b9  mov     [rax+40h], r15d
0x14016c4bd  mov     r9d, [rbp+4Fh+arg_18]
0x14016c4c1  mov     rdx, rbx; struct InConnection::InConnectionContentSetContext *
0x14016c4c4  mov     rcx, r13; this
0x14016c4c7  call    ?CommitSession@InConnection@@AEAAPEAVFrsStatus@@PEAVInConnectionContentSetContext@1@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@VSessionInfo@@@std@@@std@@@std@@W4SYNC_TYPE@@@Z; InConnection::CommitSession(InConnection::InConnectionContentSetContext *,std::_List_iterator<std::_List_val<std::_List_simple_types<SessionInfo>>>,SYNC_TYPE)
0x14016c4cc  mov     r12, rax
0x14016c4cf  lea     rbx, aInconnectionSu_0; "InConnection::SubmitSpecialUpdate"
0x14016c4d6  lea     rdi, aBaseFsRemotefs_1; "base\\fs\\remotefs\\frs\\src\\sync\\inc"...
0x14016c4dd  lea     rcx, [rbp+4Fh+var_40]; this
0x14016c4e1  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x14016c4e6  test    r12, r12
0x14016c4e9  jz      short loc_14016C528
0x14016c4eb  call    cs:__imp_GetCurrentThreadId
0x14016c4f2  nop     dword ptr [rax+rax+00h]
0x14016c4f7  mov     qword ptr [rsp+0E0h+var_A8+8], r12
0x14016c4fc  mov     [rsp+0E0h+var_A8], eax
0x14016c500  mov     dword ptr [rsp+0E0h+var_B0], 1021h
0x14016c508  mov     [rsp+0E0h+var_B8], rbx
0x14016c50d  mov     [rsp+0E0h+var_C0], rdi
0x14016c512  mov     r9d, [r12]
0x14016c516  mov     r8d, [r12+8]
0x14016c51b  mov     edx, [r12+4]
0x14016c520  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14016c525  mov     r15, rax
0x14016c528  lea     rcx, [rbp+4Fh+arg_0]
0x14016c52c  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x14016c531  mov     rax, r15
0x14016c534  mov     rbx, [rsp+0E0h+arg_8]
0x14016c53c  add     rsp, 0B0h
0x14016c543  pop     r15
0x14016c545  pop     r14
0x14016c547  pop     r13
0x14016c549  pop     r12
0x14016c54b  pop     rdi
0x14016c54c  pop     rsi
0x14016c54d  pop     rbp
0x14016c54e  retn
```
