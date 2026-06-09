# MkvMfSourceLib::MkvTimedText::RemoveTrack(ulong)

- ea: `0x18003fa50`
- end: `0x18003fd17`
- name: `?RemoveTrack@MkvTimedText@MkvMfSourceLib@@UEAAJK@Z`
- size: `711`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvTimedText *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18003b410`
- `0x18003b464`
- `0x18003fa50`
- `0x18004109c`
- `0x180041158`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003fa7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003fa7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003fc39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003fcfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003fc39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003fcfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fa99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fc5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fa99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fc5c`

## string_xrefs

- `0x18003fa5e`: `MkvMfSourceLib::MkvTimedText::RemoveTrack`
- `0x18003faf5`: `MkvMfSourceLib::MkvTimedText::RemoveTrack`
- `0x18003fcb8`: `MkvMfSourceLib::MkvTimedText::RemoveTrack`

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
            v24 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v7 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18003fa50  push    rbx
0x18003fa52  push    rbp
0x18003fa53  push    rsi
0x18003fa54  push    rdi
0x18003fa55  sub     rsp, 48h
0x18003fa59  mov     esi, edx
0x18003fa5b  mov     rdi, rcx
0x18003fa5e  lea     rdx, aMkvmfsourcelib_120; "MkvMfSourceLib::MkvTimedText::RemoveTra"...
0x18003fa65  mov     r8d, 0FCh; int
0x18003fa6b  lea     rcx, [rsp+68h+arg_0]; this
0x18003fa70  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003fa75  lea     rbx, [rdi+30h]
0x18003fa79  mov     rcx, rbx; lpCriticalSection
0x18003fa7c  call    cs:__imp_EnterCriticalSection
0x18003fa82  xor     ebp, ebp
0x18003fa84  cmp     [rdi+78h], ebp
0x18003fa87  jnz     loc_18003FB21
0x18003fa8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fa94  test    rcx, rcx
0x18003fa97  jnz     short loc_18003FADA
0x18003fa99  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003fa9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003faa6  mov     rcx, rax
0x18003faa9  test    rax, rax
0x18003faac  jz      short loc_18003FACC
0x18003faae  mov     rax, [rax]
0x18003fab1  mov     edx, 7F0h
0x18003fab6  mov     rax, [rax+8]
0x18003faba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fabf  test    eax, eax
0x18003fac1  jz      short loc_18003FACC
0x18003fac3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003faca  jmp     short loc_18003FADA
0x18003facc  lea     rcx, qword_1800D6F70; this
0x18003fad3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fada  mov     esi, 0C00D36B2h
0x18003fadf  cmp     [rcx+8], bpl
0x18003fae3  jz      short loc_18003FB0A
0x18003fae5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003faea  cmp     [rax+7CCh], esi
0x18003faf0  jz      short loc_18003FB0A
0x18003faf2  mov     r9d, esi; int
0x18003faf5  lea     rdx, aMkvmfsourcelib_120; "MkvMfSourceLib::MkvTimedText::RemoveTra"...
0x18003fafc  mov     r8d, 0FFh; int
0x18003fb02  mov     rcx, rax; this
0x18003fb05  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003fb0a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003fb11  jb      loc_18003FCF9
0x18003fb17  mov     edx, 34h ; '4'
0x18003fb1c  jmp     loc_18003FCDB
0x18003fb21  mov     edx, esi; unsigned int
0x18003fb23  mov     rcx, rdi; this
0x18003fb26  call    ?CheckSubtitleTrackExists@MkvTimedText@MkvMfSourceLib@@AEAAJK@Z; MkvMfSourceLib::MkvTimedText::CheckSubtitleTrackExists(ulong)
0x18003fb2b  test    eax, eax
0x18003fb2d  js      short loc_18003FBAC
0x18003fb2f  mov     r8, [rdi+88h]
0x18003fb36  mov     rdx, r8
0x18003fb39  mov     rax, [r8+8]
0x18003fb3d  mov     rcx, rax
0x18003fb40  cmp     [rax+19h], bpl
0x18003fb44  jnz     short loc_18003FB6A
0x18003fb46  cmp     [rcx+20h], esi
0x18003fb49  jnb     short loc_18003FB51
0x18003fb4b  add     rcx, 10h
0x18003fb4f  jmp     short loc_18003FB61
0x18003fb51  cmp     [rdx+19h], bpl
0x18003fb55  jz      short loc_18003FB5E
0x18003fb57  cmp     esi, [rcx+20h]
0x18003fb5a  cmovb   rdx, rcx
0x18003fb5e  mov     r8, rcx
0x18003fb61  mov     rcx, [rcx]
0x18003fb64  cmp     [rcx+19h], bpl
0x18003fb68  jz      short loc_18003FB46
0x18003fb6a  cmp     [rdx+19h], bpl
0x18003fb6e  jnz     short loc_18003FB86
0x18003fb70  mov     rax, [rdx]
0x18003fb73  jmp     short loc_18003FB86
0x18003fb75  cmp     esi, [rax+20h]
0x18003fb78  jnb     short loc_18003FB82
0x18003fb7a  mov     rdx, rax
0x18003fb7d  mov     rax, [rax]
0x18003fb80  jmp     short loc_18003FB86
0x18003fb82  mov     rax, [rax+10h]
0x18003fb86  cmp     [rax+19h], bpl
0x18003fb8a  jz      short loc_18003FB75
0x18003fb8c  mov     [rsp+68h+var_30], rdx
0x18003fb91  lea     rcx, [rdi+88h]
0x18003fb98  lea     rdx, [rsp+68h+var_38]
0x18003fb9d  mov     [rsp+68h+var_38], r8
0x18003fba2  call    ?_Erase@?$_Tree@V?$_Tmap_traits@KVTrackData@MkvTimedText@MkvMfSourceLib@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVTrackData@MkvTimedText@MkvMfSourceLib@@@std@@@5@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVTrackData@MkvTimedText@MkvMfSourceLib@@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,MkvMfSourceLib::MkvTimedText::TrackData,std::less<ulong>,std::allocator<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::TrackData>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::TrackData>,void *> *,std::_Tree_node<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::TrackData>,void *> *>)
0x18003fba7  jmp     loc_18003FC36
0x18003fbac  mov     edx, esi; unsigned int
0x18003fbae  mov     rcx, rdi; this
0x18003fbb1  call    ?CheckChapterTrackExists@MkvTimedText@MkvMfSourceLib@@AEAAJK@Z; MkvMfSourceLib::MkvTimedText::CheckChapterTrackExists(ulong)
0x18003fbb6  test    eax, eax
0x18003fbb8  js      loc_18003FC50
0x18003fbbe  mov     r8, [rdi+0B0h]
0x18003fbc5  mov     rdx, r8
0x18003fbc8  mov     rax, [r8+8]
0x18003fbcc  mov     rcx, rax
0x18003fbcf  cmp     [rax+19h], bpl
0x18003fbd3  jnz     short loc_18003FBF9
0x18003fbd5  cmp     [rcx+20h], esi
0x18003fbd8  jnb     short loc_18003FBE0
0x18003fbda  add     rcx, 10h
0x18003fbde  jmp     short loc_18003FBF0
0x18003fbe0  cmp     [rdx+19h], bpl
0x18003fbe4  jz      short loc_18003FBED
0x18003fbe6  cmp     esi, [rcx+20h]
0x18003fbe9  cmovb   rdx, rcx
0x18003fbed  mov     r8, rcx
0x18003fbf0  mov     rcx, [rcx]
0x18003fbf3  cmp     [rcx+19h], bpl
0x18003fbf7  jz      short loc_18003FBD5
0x18003fbf9  cmp     [rdx+19h], bpl
0x18003fbfd  jnz     short loc_18003FC15
0x18003fbff  mov     rax, [rdx]
0x18003fc02  jmp     short loc_18003FC15
0x18003fc04  cmp     esi, [rax+20h]
0x18003fc07  jnb     short loc_18003FC11
0x18003fc09  mov     rdx, rax
0x18003fc0c  mov     rax, [rax]
0x18003fc0f  jmp     short loc_18003FC15
0x18003fc11  mov     rax, [rax+10h]
0x18003fc15  cmp     [rax+19h], bpl
0x18003fc19  jz      short loc_18003FC04
0x18003fc1b  mov     [rsp+68h+var_30], rdx
0x18003fc20  lea     rcx, [rdi+0B0h]
0x18003fc27  lea     rdx, [rsp+68h+var_38]
0x18003fc2c  mov     [rsp+68h+var_38], r8
0x18003fc31  call    ?_Erase@?$_Tree@V?$_Tmap_traits@KVChapterTrackData@MkvTimedText@MkvMfSourceLib@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@std@@@5@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,MkvMfSourceLib::MkvTimedText::ChapterTrackData,std::less<ulong>,std::allocator<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>,void *> *,std::_Tree_node<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>,void *> *>)
0x18003fc36  mov     rcx, rbx; lpCriticalSection
0x18003fc39  call    cs:__imp_LeaveCriticalSection
0x18003fc3f  lea     rcx, [rsp+68h+arg_0]; this
0x18003fc44  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003fc49  xor     eax, eax
0x18003fc4b  jmp     loc_18003FD0E
0x18003fc50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fc57  test    rcx, rcx
0x18003fc5a  jnz     short loc_18003FC9D
0x18003fc5c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003fc62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fc69  mov     rcx, rax
0x18003fc6c  test    rax, rax
0x18003fc6f  jz      short loc_18003FC8F
0x18003fc71  mov     rax, [rax]
0x18003fc74  mov     edx, 7F0h
0x18003fc79  mov     rax, [rax+8]
0x18003fc7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc82  test    eax, eax
0x18003fc84  jz      short loc_18003FC8F
0x18003fc86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fc8d  jmp     short loc_18003FC9D
0x18003fc8f  lea     rcx, qword_1800D6F70; this
0x18003fc96  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fc9d  mov     esi, 8000000Bh
0x18003fca2  cmp     [rcx+8], bpl
0x18003fca6  jz      short loc_18003FCCD
0x18003fca8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003fcad  cmp     [rax+7CCh], esi
0x18003fcb3  jz      short loc_18003FCCD
0x18003fcb5  mov     r9d, esi; int
0x18003fcb8  lea     rdx, aMkvmfsourcelib_120; "MkvMfSourceLib::MkvTimedText::RemoveTra"...
0x18003fcbf  mov     r8d, 10Bh; int
0x18003fcc5  mov     rcx, rax; this
0x18003fcc8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003fccd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003fcd4  jb      short loc_18003FCF9
0x18003fcd6  mov     edx, 35h ; '5'
0x18003fcdb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fce2  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003fce9  mov     r9, rdi
0x18003fcec  mov     [rsp+68h+var_48], esi
0x18003fcf0  mov     rcx, [rcx+10h]
0x18003fcf4  call    WPP_SF_qD
0x18003fcf9  mov     rcx, rbx; lpCriticalSection
0x18003fcfc  call    cs:__imp_LeaveCriticalSection
0x18003fd02  lea     rcx, [rsp+68h+arg_0]; this
0x18003fd07  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003fd0c  mov     eax, esi
0x18003fd0e  add     rsp, 48h
0x18003fd12  pop     rdi
0x18003fd13  pop     rsi
0x18003fd14  pop     rbp
0x18003fd15  pop     rbx
0x18003fd16  retn
```
