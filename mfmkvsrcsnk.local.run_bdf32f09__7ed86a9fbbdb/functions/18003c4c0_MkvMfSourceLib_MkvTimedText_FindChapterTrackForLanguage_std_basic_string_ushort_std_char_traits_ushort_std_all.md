# MkvMfSourceLib::MkvTimedText::FindChapterTrackForLanguage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,IMFTimedTextTrack * *)

- ea: `0x18003c4c0`
- end: `0x18003c67f`
- name: `?FindChapterTrackForLanguage@MkvTimedText@MkvMfSourceLib@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIMFTimedTextTrack@@@Z`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003bea0`

## callees

- `0x1800097f0`
- `0x1800098b8`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180028730`
- `0x18003b1d4`
- `0x18003c4c0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c580`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c661`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c580`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c661`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c5ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c5ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvMfSourceLib::MkvTimedText::FindChapterTrackForLanguage(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rax
  _QWORD *v7; // rsi
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r9
  _QWORD *v13; // rcx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v18; // [rsp+80h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+50h] BYREF
  __int64 v20; // [rsp+98h] [rbp+58h] BYREF

  *a3 = 0;
  v6 = **(_QWORD **)(a1 + 176);
  v20 = v6;
  while ( v6 != *(_QWORD *)(a1 + 176) )
  {
    pv = 0;
    v7 = (_QWORD *)(v6 + 40);
    v8 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**(_QWORD **)(v6 + 40) + 48LL))(*(_QWORD *)(v6 + 40), &pv);
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v18,
      "MkvMfSourceLib::MkvTimedText::FindChapterTrackForLanguage",
      685);
    if ( v8 < 0 )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "MkvMfSourceLib::MkvTimedText::FindChapterTrackForLanguage",
            685,
            v8);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids, a1, v8);
      goto LABEL_22;
    }
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)pv + v12) );
    if ( a2[3] <= 7u )
      v13 = a2;
    else
      v13 = (_QWORD *)*a2;
    if ( !(unsigned int)std::_Traits_compare<std::char_traits<unsigned short>>(v13, a2[2], pv) )
    {
      Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(v7);
      *a3 = *v7;
      v8 = 0;
LABEL_22:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v18);
      CoTaskMemFree(pv);
      return (unsigned int)v8;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v18);
    CoTaskMemFree(pv);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,MkvMfSourceLib::MkvTimedText::TrackData>>>,std::_Iterator_base0>::operator++(&v20);
    v6 = v20;
  }
  return 3222091477LL;
}

```

## disassembly

```asm
0x18003c4c0  push    rbp
0x18003c4c2  push    rbx
0x18003c4c3  push    rsi
0x18003c4c4  push    rdi
0x18003c4c5  push    r12
0x18003c4c7  push    r14
0x18003c4c9  push    r15
0x18003c4cb  mov     rbp, rsp
0x18003c4ce  sub     rsp, 40h
0x18003c4d2  mov     r15, r8
0x18003c4d5  mov     rdi, rdx
0x18003c4d8  mov     r14, rcx
0x18003c4db  xor     r12d, r12d
0x18003c4de  mov     [r8], r12
0x18003c4e1  mov     rax, [rcx+0B0h]
0x18003c4e8  mov     rax, [rax]
0x18003c4eb  mov     [rbp+arg_18], rax
0x18003c4ef  cmp     rax, [r14+0B0h]
0x18003c4f6  jz      loc_18003C66B
0x18003c4fc  mov     [rbp+pv], r12
0x18003c500  lea     rcx, [rbp+pv]
0x18003c504  mov     [rbp+var_10], rcx
0x18003c508  mov     [rbp+var_8], 1
0x18003c50c  lea     rsi, [rax+28h]
0x18003c510  mov     rcx, [rsi]
0x18003c513  mov     rax, [rcx]
0x18003c516  lea     rdx, [rbp+pv]
0x18003c51a  mov     rax, [rax+30h]
0x18003c51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c523  mov     ebx, eax
0x18003c525  mov     r8d, 2ADh; int
0x18003c52b  lea     rdx, aMkvmfsourcelib_95; "MkvMfSourceLib::MkvTimedText::FindChapt"...
0x18003c532  lea     rcx, [rbp+arg_0]; this
0x18003c536  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003c53b  nop
0x18003c53c  test    ebx, ebx
0x18003c53e  js      short loc_18003C5AE
0x18003c540  mov     r8, [rbp+pv]
0x18003c544  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003c548  inc     r9
0x18003c54b  cmp     [r8+r9*2], r12w
0x18003c550  jnz     short loc_18003C548
0x18003c552  cmp     qword ptr [rdi+18h], 7
0x18003c557  jbe     short loc_18003C55E
0x18003c559  mov     rcx, [rdi]
0x18003c55c  jmp     short loc_18003C561
0x18003c55e  mov     rcx, rdi
0x18003c561  mov     rdx, [rdi+10h]
0x18003c565  call    ??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z; std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18003c56a  test    eax, eax
0x18003c56c  jz      short loc_18003C598
0x18003c56e  lea     rcx, [rbp+arg_0]; this
0x18003c572  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c577  nop
0x18003c578  mov     [rbp+var_8], r12b
0x18003c57c  mov     rcx, [rbp+pv]; pv
0x18003c580  call    cs:__imp_CoTaskMemFree
0x18003c586  lea     rcx, [rbp+arg_18]
0x18003c58a  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKVTrackData@MkvTimedText@MkvMfSourceLib@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::TrackData>>>,std::_Iterator_base0>::operator++(void)
0x18003c58f  mov     rax, [rbp+arg_18]
0x18003c593  jmp     loc_18003C4EF
0x18003c598  mov     rcx, rsi
0x18003c59b  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x18003c5a0  mov     rax, [rsi]
0x18003c5a3  mov     [r15], rax
0x18003c5a6  mov     ebx, r12d
0x18003c5a9  jmp     loc_18003C653
0x18003c5ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c5b5  test    rcx, rcx
0x18003c5b8  jnz     short loc_18003C5FB
0x18003c5ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003c5c0  mov     rcx, rax
0x18003c5c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c5ca  test    rax, rax
0x18003c5cd  jz      short loc_18003C5ED
0x18003c5cf  mov     rax, [rax]
0x18003c5d2  mov     edx, 7F0h
0x18003c5d7  mov     rax, [rax+8]
0x18003c5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5e0  test    eax, eax
0x18003c5e2  jz      short loc_18003C5ED
0x18003c5e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c5eb  jmp     short loc_18003C5FB
0x18003c5ed  lea     rcx, qword_1800D6F70; this
0x18003c5f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c5fb  cmp     [rcx+8], r12b
0x18003c5ff  jz      short loc_18003C626
0x18003c601  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c606  cmp     [rax+7CCh], ebx
0x18003c60c  jz      short loc_18003C626
0x18003c60e  mov     r9d, ebx; int
0x18003c611  mov     r8d, 2ADh; int
0x18003c617  lea     rdx, aMkvmfsourcelib_95; "MkvMfSourceLib::MkvTimedText::FindChapt"...
0x18003c61e  mov     rcx, rax; this
0x18003c621  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c626  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c62d  jb      short loc_18003C653
0x18003c62f  mov     edx, 62h ; 'b'
0x18003c634  mov     [rsp+40h+var_20], ebx
0x18003c638  mov     r9, r14
0x18003c63b  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003c642  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c649  mov     rcx, [rcx+10h]
0x18003c64d  call    WPP_SF_qD
0x18003c652  nop
0x18003c653  lea     rcx, [rbp+arg_0]; this
0x18003c657  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c65c  nop
0x18003c65d  mov     rcx, [rbp+pv]; pv
0x18003c661  call    cs:__imp_CoTaskMemFree
0x18003c667  mov     eax, ebx
0x18003c669  jmp     short loc_18003C670
0x18003c66b  mov     eax, 0C00D36D5h
0x18003c670  add     rsp, 40h
0x18003c674  pop     r15
0x18003c676  pop     r14
0x18003c678  pop     r12
0x18003c67a  pop     rdi
0x18003c67b  pop     rsi
0x18003c67c  pop     rbx
0x18003c67d  pop     rbp
0x18003c67e  retn
```
