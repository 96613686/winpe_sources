# MkvMfSourceLib::MkvTimedText::FindChapterTrackForLanguage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,IMFTimedTextTrack * *)

- ea: `0x18003defc`
- end: `0x18003e0ce`
- name: `?FindChapterTrackForLanguage@MkvTimedText@MkvMfSourceLib@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIMFTimedTextTrack@@@Z`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d8bc`

## callees

- `0x180009b04`
- `0x180009bec`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180029890`
- `0x18003cb98`
- `0x18003defc`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dfbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e0a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dfbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e0a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003dffc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003dffc`

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
          v14 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18003defc  push    rbp
0x18003defe  push    rbx
0x18003deff  push    rsi
0x18003df00  push    rdi
0x18003df01  push    r12
0x18003df03  push    r14
0x18003df05  push    r15
0x18003df07  mov     rbp, rsp
0x18003df0a  sub     rsp, 40h
0x18003df0e  mov     r15, r8
0x18003df11  mov     rdi, rdx
0x18003df14  mov     r14, rcx
0x18003df17  xor     r12d, r12d
0x18003df1a  mov     [r8], r12
0x18003df1d  mov     rax, [rcx+0B0h]
0x18003df24  mov     rax, [rax]
0x18003df27  mov     [rbp+arg_18], rax
0x18003df2b  cmp     rax, [r14+0B0h]
0x18003df32  jz      loc_18003E0B9
0x18003df38  mov     [rbp+pv], r12
0x18003df3c  lea     rcx, [rbp+pv]
0x18003df40  mov     [rbp+var_10], rcx
0x18003df44  mov     [rbp+var_8], 1
0x18003df48  lea     rsi, [rax+28h]
0x18003df4c  mov     rcx, [rsi]
0x18003df4f  mov     rax, [rcx]
0x18003df52  lea     rdx, [rbp+pv]
0x18003df56  mov     rax, [rax+30h]
0x18003df5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df5f  mov     ebx, eax
0x18003df61  mov     r8d, 2ADh; int
0x18003df67  lea     rdx, aMkvmfsourcelib_95; "MkvMfSourceLib::MkvTimedText::FindChapt"...
0x18003df6e  lea     rcx, [rbp+arg_0]; this
0x18003df72  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003df77  nop
0x18003df78  test    ebx, ebx
0x18003df7a  js      short loc_18003DFF0
0x18003df7c  mov     r8, [rbp+pv]
0x18003df80  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003df84  inc     r9
0x18003df87  cmp     [r8+r9*2], r12w
0x18003df8c  jnz     short loc_18003DF84
0x18003df8e  cmp     qword ptr [rdi+18h], 7
0x18003df93  jbe     short loc_18003DF9A
0x18003df95  mov     rcx, [rdi]
0x18003df98  jmp     short loc_18003DF9D
0x18003df9a  mov     rcx, rdi
0x18003df9d  mov     rdx, [rdi+10h]
0x18003dfa1  call    ??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z; std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18003dfa6  test    eax, eax
0x18003dfa8  jz      short loc_18003DFDA
0x18003dfaa  lea     rcx, [rbp+arg_0]; this
0x18003dfae  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003dfb3  nop
0x18003dfb4  mov     [rbp+var_8], r12b
0x18003dfb8  mov     rcx, [rbp+pv]; pv
0x18003dfbc  call    cs:__imp_CoTaskMemFree
0x18003dfc3  nop     dword ptr [rax+rax+00h]
0x18003dfc8  lea     rcx, [rbp+arg_18]
0x18003dfcc  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKVTrackData@MkvTimedText@MkvMfSourceLib@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::TrackData>>>,std::_Iterator_base0>::operator++(void)
0x18003dfd1  mov     rax, [rbp+arg_18]
0x18003dfd5  jmp     loc_18003DF2B
0x18003dfda  mov     rcx, rsi
0x18003dfdd  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x18003dfe2  mov     rax, [rsi]
0x18003dfe5  mov     [r15], rax
0x18003dfe8  mov     ebx, r12d
0x18003dfeb  jmp     loc_18003E09B
0x18003dff0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dff7  test    rcx, rcx
0x18003dffa  jnz     short loc_18003E043
0x18003dffc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e003  nop     dword ptr [rax+rax+00h]
0x18003e008  mov     rcx, rax
0x18003e00b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e012  test    rax, rax
0x18003e015  jz      short loc_18003E035
0x18003e017  mov     rax, [rax]
0x18003e01a  mov     edx, 7F0h
0x18003e01f  mov     rax, [rax+8]
0x18003e023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e028  test    eax, eax
0x18003e02a  jz      short loc_18003E035
0x18003e02c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e033  jmp     short loc_18003E043
0x18003e035  lea     rcx, qword_1800DBF70; this
0x18003e03c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e043  cmp     [rcx+8], r12b
0x18003e047  jz      short loc_18003E06E
0x18003e049  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003e04e  cmp     [rax+7CCh], ebx
0x18003e054  jz      short loc_18003E06E
0x18003e056  mov     r9d, ebx; int
0x18003e059  mov     r8d, 2ADh; int
0x18003e05f  lea     rdx, aMkvmfsourcelib_95; "MkvMfSourceLib::MkvTimedText::FindChapt"...
0x18003e066  mov     rcx, rax; this
0x18003e069  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003e06e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e075  jb      short loc_18003E09B
0x18003e077  mov     edx, 62h ; 'b'
0x18003e07c  mov     [rsp+40h+var_20], ebx
0x18003e080  mov     r9, r14
0x18003e083  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003e08a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e091  mov     rcx, [rcx+10h]
0x18003e095  call    WPP_SF_qD
0x18003e09a  nop
0x18003e09b  lea     rcx, [rbp+arg_0]; this
0x18003e09f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003e0a4  nop
0x18003e0a5  mov     rcx, [rbp+pv]; pv
0x18003e0a9  call    cs:__imp_CoTaskMemFree
0x18003e0b0  nop     dword ptr [rax+rax+00h]
0x18003e0b5  mov     eax, ebx
0x18003e0b7  jmp     short loc_18003E0BE
0x18003e0b9  mov     eax, 0C00D36D5h
0x18003e0be  add     rsp, 40h
0x18003e0c2  pop     r15
0x18003e0c4  pop     r14
0x18003e0c6  pop     r12
0x18003e0c8  pop     rdi
0x18003e0c9  pop     rsi
0x18003e0ca  pop     rbx
0x18003e0cb  pop     rbp
0x18003e0cc  retn
```
