# MkvMfSourceLib::MkvTimedText::RemoveTrack(ulong)

- ea: `0x1800416b0`
- end: `0x180041996`
- name: `?RemoveTrack@MkvTimedText@MkvMfSourceLib@@UEAAJK@Z`
- size: `742`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvTimedText *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18003cde0`
- `0x18003ce38`
- `0x1800416b0`
- `0x180042df8`
- `0x180042eb8`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800416dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800416dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800418a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041974`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800418a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041974`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800416ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800418ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800416ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800418ce`

## string_xrefs

- `0x1800416be`: `MkvMfSourceLib::MkvTimedText::RemoveTrack`
- `0x180041761`: `MkvMfSourceLib::MkvTimedText::RemoveTrack`
- `0x180041930`: `MkvMfSourceLib::MkvTimedText::RemoveTrack`

## pseudocode

```c
__int64 __fastcall MkvMfSourceLib::MkvTimedText::RemoveTrack(MkvMfSourceLib::MkvTimedText *this, unsigned int a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  unsigned int v9; // esi
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // r8
  __int64 *v13; // rdx
  __int64 *v14; // rax
  __int64 *j; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 *v19; // r8
  __int64 *v20; // rdx
  __int64 *v21; // rax
  __int64 *i; // rcx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v27; // [rsp+30h] [rbp-38h] BYREF
  __int64 *v28; // [rsp+38h] [rbp-30h]
  char v29; // [rsp+70h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v29,
    "MkvMfSourceLib::MkvTimedText::RemoveTrack",
    252);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_DWORD *)this + 30) )
  {
    if ( (int)MkvMfSourceLib::MkvTimedText::CheckSubtitleTrackExists(this, a2) < 0 )
    {
      if ( (int)MkvMfSourceLib::MkvTimedText::CheckChapterTrackExists(this, a2) < 0 )
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        v9 = -2147483637;
        if ( *((_BYTE *)v24 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147483637 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "MkvMfSourceLib::MkvTimedText::RemoveTrack",
              267,
              -2147483637);
        }
        if ( !g_wppLevels )
          goto LABEL_56;
        v11 = 53;
        goto LABEL_55;
      }
      v19 = (__int64 *)*((_QWORD *)this + 22);
      v20 = v19;
      v21 = (__int64 *)v19[1];
      for ( i = v21; !*((_BYTE *)i + 25); i = (__int64 *)*i )
      {
        if ( *((_DWORD *)i + 8) >= a2 )
        {
          if ( *((_BYTE *)v20 + 25) && a2 < *((_DWORD *)i + 8) )
            v20 = i;
          v19 = i;
        }
        else
        {
          i += 2;
        }
      }
      if ( !*((_BYTE *)v20 + 25) )
        v21 = (__int64 *)*v20;
      while ( !*((_BYTE *)v21 + 25) )
      {
        if ( a2 >= *((_DWORD *)v21 + 8) )
        {
          v21 = (__int64 *)v21[2];
        }
        else
        {
          v20 = v21;
          v21 = (__int64 *)*v21;
        }
      }
      v28 = v20;
      v27 = v19;
      std::_Tree<std::_Tmap_traits<unsigned long,MkvMfSourceLib::MkvTimedText::ChapterTrackData,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>,0>>::_Erase(
        (char *)this + 176,
        &v27);
    }
    else
    {
      v12 = (__int64 *)*((_QWORD *)this + 17);
      v13 = v12;
      v14 = (__int64 *)v12[1];
      for ( j = v14; !*((_BYTE *)j + 25); j = (__int64 *)*j )
      {
        if ( *((_DWORD *)j + 8) >= a2 )
        {
          if ( *((_BYTE *)v13 + 25) && a2 < *((_DWORD *)j + 8) )
            v13 = j;
          v12 = j;
        }
        else
        {
          j += 2;
        }
      }
      if ( !*((_BYTE *)v13 + 25) )
        v14 = (__int64 *)*v13;
      while ( !*((_BYTE *)v14 + 25) )
      {
        if ( a2 >= *((_DWORD *)v14 + 8) )
        {
          v14 = (__int64 *)v14[2];
        }
        else
        {
          v13 = v14;
          v14 = (__int64 *)*v14;
        }
      }
      v28 = v13;
      v27 = v12;
      std::_Tree<std::_Tmap_traits<unsigned long,MkvMfSourceLib::MkvTimedText::TrackData,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,MkvMfSourceLib::MkvTimedText::TrackData>>,0>>::_Erase(
        (char *)this + 136,
        &v27);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v29);
    return 0;
  }
  v7 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
    CallStackTracing::s_wpInstance = v8;
    if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
    {
      v7 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v7 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  v9 = -1072875854;
  if ( *((_BYTE *)v7 + 8) )
  {
    v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
    if ( *((_DWORD *)v10 + 499) != -1072875854 )
      CallStackContext::TraceFailure(v10, "MkvMfSourceLib::MkvTimedText::RemoveTrack", 255, -1072875854);
  }
  if ( !g_wppLevels )
    goto LABEL_56;
  v11 = 52;
LABEL_55:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids, this, v9);
LABEL_56:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v29);
  return v9;
}

```

## disassembly

```asm
0x1800416b0  push    rbx
0x1800416b2  push    rbp
0x1800416b3  push    rsi
0x1800416b4  push    rdi
0x1800416b5  sub     rsp, 48h
0x1800416b9  mov     esi, edx
0x1800416bb  mov     rdi, rcx
0x1800416be  lea     rdx, aMkvmfsourcelib_120; "MkvMfSourceLib::MkvTimedText::RemoveTra"...
0x1800416c5  mov     r8d, 0FCh; int
0x1800416cb  lea     rcx, [rsp+68h+arg_0]; this
0x1800416d0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800416d5  lea     rbx, [rdi+30h]
0x1800416d9  mov     rcx, rbx; lpCriticalSection
0x1800416dc  call    cs:__imp_EnterCriticalSection
0x1800416e3  nop     dword ptr [rax+rax+00h]
0x1800416e8  xor     ebp, ebp
0x1800416ea  cmp     [rdi+78h], ebp
0x1800416ed  jnz     loc_18004178D
0x1800416f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800416fa  test    rcx, rcx
0x1800416fd  jnz     short loc_180041746
0x1800416ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041706  nop     dword ptr [rax+rax+00h]
0x18004170b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041712  mov     rcx, rax
0x180041715  test    rax, rax
0x180041718  jz      short loc_180041738
0x18004171a  mov     rax, [rax]
0x18004171d  mov     edx, 7F0h
0x180041722  mov     rax, [rax+8]
0x180041726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004172b  test    eax, eax
0x18004172d  jz      short loc_180041738
0x18004172f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041736  jmp     short loc_180041746
0x180041738  lea     rcx, qword_1800DBF70; this
0x18004173f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180041746  mov     esi, 0C00D36B2h
0x18004174b  cmp     [rcx+8], bpl
0x18004174f  jz      short loc_180041776
0x180041751  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180041756  cmp     [rax+7CCh], esi
0x18004175c  jz      short loc_180041776
0x18004175e  mov     r9d, esi; int
0x180041761  lea     rdx, aMkvmfsourcelib_120; "MkvMfSourceLib::MkvTimedText::RemoveTra"...
0x180041768  mov     r8d, 0FFh; int
0x18004176e  mov     rcx, rax; this
0x180041771  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180041776  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004177d  jb      loc_180041971
0x180041783  mov     edx, 34h ; '4'
0x180041788  jmp     loc_180041953
0x18004178d  mov     edx, esi; unsigned int
0x18004178f  mov     rcx, rdi; this
0x180041792  call    ?CheckSubtitleTrackExists@MkvTimedText@MkvMfSourceLib@@AEAAJK@Z; MkvMfSourceLib::MkvTimedText::CheckSubtitleTrackExists(ulong)
0x180041797  test    eax, eax
0x180041799  js      short loc_180041818
0x18004179b  mov     r8, [rdi+88h]
0x1800417a2  mov     rdx, r8
0x1800417a5  mov     rax, [r8+8]
0x1800417a9  mov     rcx, rax
0x1800417ac  cmp     [rax+19h], bpl
0x1800417b0  jnz     short loc_1800417D6
0x1800417b2  cmp     [rcx+20h], esi
0x1800417b5  jnb     short loc_1800417BD
0x1800417b7  add     rcx, 10h
0x1800417bb  jmp     short loc_1800417CD
0x1800417bd  cmp     [rdx+19h], bpl
0x1800417c1  jz      short loc_1800417CA
0x1800417c3  cmp     esi, [rcx+20h]
0x1800417c6  cmovb   rdx, rcx
0x1800417ca  mov     r8, rcx
0x1800417cd  mov     rcx, [rcx]
0x1800417d0  cmp     [rcx+19h], bpl
0x1800417d4  jz      short loc_1800417B2
0x1800417d6  cmp     [rdx+19h], bpl
0x1800417da  jnz     short loc_1800417F2
0x1800417dc  mov     rax, [rdx]
0x1800417df  jmp     short loc_1800417F2
0x1800417e1  cmp     esi, [rax+20h]
0x1800417e4  jnb     short loc_1800417EE
0x1800417e6  mov     rdx, rax
0x1800417e9  mov     rax, [rax]
0x1800417ec  jmp     short loc_1800417F2
0x1800417ee  mov     rax, [rax+10h]
0x1800417f2  cmp     [rax+19h], bpl
0x1800417f6  jz      short loc_1800417E1
0x1800417f8  mov     [rsp+68h+var_30], rdx
0x1800417fd  lea     rcx, [rdi+88h]
0x180041804  lea     rdx, [rsp+68h+var_38]
0x180041809  mov     [rsp+68h+var_38], r8
0x18004180e  call    ?_Erase@?$_Tree@V?$_Tmap_traits@KVTrackData@MkvTimedText@MkvMfSourceLib@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVTrackData@MkvTimedText@MkvMfSourceLib@@@std@@@5@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVTrackData@MkvTimedText@MkvMfSourceLib@@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,MkvMfSourceLib::MkvTimedText::TrackData,std::less<ulong>,std::allocator<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::TrackData>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::TrackData>,void *> *,std::_Tree_node<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::TrackData>,void *> *>)
0x180041813  jmp     loc_1800418A2
0x180041818  mov     edx, esi; unsigned int
0x18004181a  mov     rcx, rdi; this
0x18004181d  call    ?CheckChapterTrackExists@MkvTimedText@MkvMfSourceLib@@AEAAJK@Z; MkvMfSourceLib::MkvTimedText::CheckChapterTrackExists(ulong)
0x180041822  test    eax, eax
0x180041824  js      loc_1800418C2
0x18004182a  mov     r8, [rdi+0B0h]
0x180041831  mov     rdx, r8
0x180041834  mov     rax, [r8+8]
0x180041838  mov     rcx, rax
0x18004183b  cmp     [rax+19h], bpl
0x18004183f  jnz     short loc_180041865
0x180041841  cmp     [rcx+20h], esi
0x180041844  jnb     short loc_18004184C
0x180041846  add     rcx, 10h
0x18004184a  jmp     short loc_18004185C
0x18004184c  cmp     [rdx+19h], bpl
0x180041850  jz      short loc_180041859
0x180041852  cmp     esi, [rcx+20h]
0x180041855  cmovb   rdx, rcx
0x180041859  mov     r8, rcx
0x18004185c  mov     rcx, [rcx]
0x18004185f  cmp     [rcx+19h], bpl
0x180041863  jz      short loc_180041841
0x180041865  cmp     [rdx+19h], bpl
0x180041869  jnz     short loc_180041881
0x18004186b  mov     rax, [rdx]
0x18004186e  jmp     short loc_180041881
0x180041870  cmp     esi, [rax+20h]
0x180041873  jnb     short loc_18004187D
0x180041875  mov     rdx, rax
0x180041878  mov     rax, [rax]
0x18004187b  jmp     short loc_180041881
0x18004187d  mov     rax, [rax+10h]
0x180041881  cmp     [rax+19h], bpl
0x180041885  jz      short loc_180041870
0x180041887  mov     [rsp+68h+var_30], rdx
0x18004188c  lea     rcx, [rdi+0B0h]
0x180041893  lea     rdx, [rsp+68h+var_38]
0x180041898  mov     [rsp+68h+var_38], r8
0x18004189d  call    ?_Erase@?$_Tree@V?$_Tmap_traits@KVChapterTrackData@MkvTimedText@MkvMfSourceLib@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@std@@@5@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,MkvMfSourceLib::MkvTimedText::ChapterTrackData,std::less<ulong>,std::allocator<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>,void *> *,std::_Tree_node<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>,void *> *>)
0x1800418a2  mov     rcx, rbx; lpCriticalSection
0x1800418a5  call    cs:__imp_LeaveCriticalSection
0x1800418ac  nop     dword ptr [rax+rax+00h]
0x1800418b1  lea     rcx, [rsp+68h+arg_0]; this
0x1800418b6  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800418bb  xor     eax, eax
0x1800418bd  jmp     loc_18004198C
0x1800418c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800418c9  test    rcx, rcx
0x1800418cc  jnz     short loc_180041915
0x1800418ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800418d5  nop     dword ptr [rax+rax+00h]
0x1800418da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800418e1  mov     rcx, rax
0x1800418e4  test    rax, rax
0x1800418e7  jz      short loc_180041907
0x1800418e9  mov     rax, [rax]
0x1800418ec  mov     edx, 7F0h
0x1800418f1  mov     rax, [rax+8]
0x1800418f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418fa  test    eax, eax
0x1800418fc  jz      short loc_180041907
0x1800418fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041905  jmp     short loc_180041915
0x180041907  lea     rcx, qword_1800DBF70; this
0x18004190e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180041915  mov     esi, 8000000Bh
0x18004191a  cmp     [rcx+8], bpl
0x18004191e  jz      short loc_180041945
0x180041920  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180041925  cmp     [rax+7CCh], esi
0x18004192b  jz      short loc_180041945
0x18004192d  mov     r9d, esi; int
0x180041930  lea     rdx, aMkvmfsourcelib_120; "MkvMfSourceLib::MkvTimedText::RemoveTra"...
0x180041937  mov     r8d, 10Bh; int
0x18004193d  mov     rcx, rax; this
0x180041940  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180041945  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004194c  jb      short loc_180041971
0x18004194e  mov     edx, 35h ; '5'
0x180041953  mov     rcx, cs:WPP_GLOBAL_Control
0x18004195a  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x180041961  mov     r9, rdi
0x180041964  mov     [rsp+68h+var_48], esi
0x180041968  mov     rcx, [rcx+10h]
0x18004196c  call    WPP_SF_qD
0x180041971  mov     rcx, rbx; lpCriticalSection
0x180041974  call    cs:__imp_LeaveCriticalSection
0x18004197b  nop     dword ptr [rax+rax+00h]
0x180041980  lea     rcx, [rsp+68h+arg_0]; this
0x180041985  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004198a  mov     eax, esi
0x18004198c  add     rsp, 48h
0x180041990  pop     rdi
0x180041991  pop     rsi
0x180041992  pop     rbp
0x180041993  pop     rbx
0x180041994  retn
```
