# MkvReader::AsyncReadCompletion(IMFAsyncResult *)

- ea: `0x18004237c`
- end: `0x1800427bb`
- name: `?AsyncReadCompletion@MkvReader@@QEAAJPEAUIMFAsyncResult@@@Z`
- size: `1087`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180015ad0`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180041f88`
- `0x180041fb0`
- `0x18004237c`
- `0x180044780`
- `0x1800458a8`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800423ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800426c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800423ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800426c9`

## string_xrefs

- `0x1800423a2`: `MkvReader::AsyncReadCompletion`
- `0x180042466`: `MkvReader::AsyncReadCompletion`
- `0x180042731`: `MkvReader::AsyncReadCompletion`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvReader::AsyncReadCompletion(MkvReader *this, struct IMFAsyncResult *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  _DWORD *v8; // r15
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v12; // ebx
  __int64 *v13; // rsi
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // r14
  unsigned __int64 v19; // r12
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  signed int *v24; // r14
  __int64 v25; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  const char *v29; // r9
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  unsigned int v33; // [rsp+30h] [rbp-98h] BYREF
  __int64 v34; // [rsp+38h] [rbp-90h] BYREF
  __int64 v35; // [rsp+40h] [rbp-88h]
  unsigned __int64 v36; // [rsp+48h] [rbp-80h]
  __int64 v37; // [rsp+50h] [rbp-78h] BYREF
  __int64 v38; // [rsp+58h] [rbp-70h]
  unsigned __int64 v39; // [rsp+60h] [rbp-68h]
  _QWORD v40[12]; // [rsp+68h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  char v42; // [rsp+D0h] [rbp+8h] BYREF
  int v43; // [rsp+E0h] [rbp+18h] BYREF
  unsigned int v44; // [rsp+E8h] [rbp+20h] BYREF

  v4 = 0;
  v43 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v42, "MkvReader::AsyncReadCompletion", 976);
  v40[3] = this;
  v40[4] = &v43;
  v42 = *((_BYTE *)this + 8);
  *((_BYTE *)this + 8) = 0;
  v8 = (_DWORD *)((char *)this + 216);
  if ( *((__int64 *)this + 27) < 0 )
  {
    v43 = -2147418113;
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v6, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( v43 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v43 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MkvReader::AsyncReadCompletion", 986, v43);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids, this, v43);
    v12 = v43;
    goto LABEL_37;
  }
  v13 = (__int64 *)((char *)this + 112);
  v14 = *((_QWORD *)this + 17);
  if ( this == (MkvReader *)-112LL )
    v15 = 0;
  else
    v15 = *v13;
  v16 = v14 + *((_QWORD *)this + 18);
  if ( this == (MkvReader *)-112LL )
    v17 = 0;
  else
    v17 = *v13;
  v38 = 0;
  v37 = v17;
  v39 = v16;
  v35 = 0;
  v34 = v15;
  v36 = v14;
  std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(
    v40,
    &v34,
    &v37,
    (char *)this + 216);
  v18 = v40[0];
  v19 = v40[2] - 1LL;
  if ( v40[0] )
    v4 = *(_QWORD *)v40[0];
  v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 8) + 8 * ((*(_QWORD *)(v4 + 16) - 1LL) & (v19 >> 1))) + 8 * (v19 & 1));
  *(_DWORD *)v20 = 0;
  v44 = 0;
  v43 = (*(__int64 (__fastcall **)(_QWORD, struct IMFAsyncResult *, unsigned int *))(**((_QWORD **)this + 2) + 88LL))(
          *((_QWORD *)this + 2),
          a2,
          &v44);
  if ( v43 >= 0 )
  {
    v21 = v44;
    *(_DWORD *)(v20 + 16) = v44;
    if ( (unsigned int)v21 < *((_DWORD *)this + 39) )
    {
      v22 = v21 + *(_QWORD *)(v20 + 8);
      v23 = *((_QWORD *)this + 25);
      if ( v23 < 0 )
      {
        *((_QWORD *)this + 25) = v22;
        if ( *(_QWORD *)v8 + *((int *)this + 56) > v22 )
          *((_DWORD *)this + 56) = v22 - *v8;
      }
      else if ( v22 < v23 )
      {
        v43 = -1072875845;
      }
    }
  }
  if ( v43 >= 0 && v44 )
  {
    v24 = (signed int *)((char *)this + 224);
  }
  else
  {
    v35 = 0;
    v34 = v18;
    v36 = v19;
    std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::erase(
      (char *)this + 112,
      v40,
      &v34);
    try
    {
      *(_QWORD *)(v20 + 8) = -1;
      *(_DWORD *)(v20 + 16) = 0;
      v37 = -1;
      v38 = v20;
      std::_Tree<std::_Tmap_traits<__int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>,1>>::insert<1,0>(
        (char *)this + 96,
        &v33,
        &v37);
    }
    catch ( ... )
    {
      v33 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x424,
              (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvreader.cpp",
              v29);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v42);
      return v33;
    }
    v24 = (signed int *)((char *)this + 224);
    *((_DWORD *)this + 56) = -1;
    *(_QWORD *)v8 = -1;
    if ( v43 < 0 )
    {
      v30 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( v43 < 0 && *((_DWORD *)v32 + 499) != v43 )
          CallStackContext::TraceFailure(v32, "MkvReader::AsyncReadCompletion", 1065, v43);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids, this, v43);
      v12 = v43;
      goto LABEL_37;
    }
  }
  v25 = *(_QWORD *)(v20 + 8) + *(unsigned int *)(v20 + 16);
  if ( v25 > *((_QWORD *)this + 26) )
    *((_QWORD *)this + 26) = v25;
  MkvReader::Read((__int64)this, v20, (_DWORD *)this + 54, v24, 0);
  if ( *v24 > 0 && !v42 )
  {
    v12 = 1;
LABEL_37:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v42);
    return v12;
  }
  *(_QWORD *)v8 = -1;
  *v24 = -1;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v42);
  return 0;
}

```

## disassembly

```asm
0x18004237c  mov     rax, rsp
0x18004237f  push    rbx
0x180042380  push    rsi
0x180042381  push    rdi
0x180042382  push    r12
0x180042384  push    r13
0x180042386  push    r14
0x180042388  push    r15
0x18004238a  sub     rsp, 90h
0x180042391  mov     r13, rdx
0x180042394  mov     rdi, rcx
0x180042397  xor     ebx, ebx
0x180042399  mov     [rax+18h], ebx
0x18004239c  mov     r8d, 3D0h; int
0x1800423a2  lea     rdx, aMkvreaderAsync_1; "MkvReader::AsyncReadCompletion"
0x1800423a9  lea     rcx, [rax+8]; this
0x1800423ad  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800423b2  nop
0x1800423b3  mov     [rsp+0C8h+var_48], rdi
0x1800423bb  lea     rax, [rsp+0C8h+arg_10]
0x1800423c3  mov     [rsp+0C8h+var_40], rax
0x1800423cb  mov     al, [rdi+8]
0x1800423ce  mov     [rsp+0C8h+arg_0], al
0x1800423d5  mov     [rdi+8], bl
0x1800423d8  lea     r15, [rdi+0D8h]
0x1800423df  cmp     [r15], rbx
0x1800423e2  jge     loc_1800424B4
0x1800423e8  mov     [rsp+0C8h+arg_10], 8000FFFFh
0x1800423f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800423fa  test    rcx, rcx
0x1800423fd  jnz     short loc_180042440
0x1800423ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042405  mov     rcx, rax
0x180042408  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004240f  test    rax, rax
0x180042412  jz      short loc_180042432
0x180042414  mov     rax, [rax]
0x180042417  mov     edx, 7F0h
0x18004241c  mov     rax, [rax+8]
0x180042420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042425  test    eax, eax
0x180042427  jz      short loc_180042432
0x180042429  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042430  jmp     short loc_180042440
0x180042432  lea     rcx, qword_1800D6F70; this
0x180042439  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042440  cmp     [rcx+8], bl
0x180042443  jz      short loc_180042475
0x180042445  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004244a  mov     r9d, [rsp+0C8h+arg_10]; int
0x180042452  test    r9d, r9d
0x180042455  jns     short loc_180042475
0x180042457  cmp     [rax+7CCh], r9d
0x18004245e  jz      short loc_180042475
0x180042460  mov     r8d, 3DAh; int
0x180042466  lea     rdx, aMkvreaderAsync_1; "MkvReader::AsyncReadCompletion"
0x18004246d  mov     rcx, rax; this
0x180042470  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042475  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004247c  jb      short loc_1800424A8
0x18004247e  mov     edx, 2Ah ; '*'
0x180042483  mov     eax, [rsp+0C8h+arg_10]
0x18004248a  mov     dword ptr [rsp+0C8h+var_A8], eax
0x18004248e  mov     r9, rdi
0x180042491  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180042498  mov     rcx, cs:WPP_GLOBAL_Control
0x18004249f  mov     rcx, [rcx+10h]
0x1800424a3  call    WPP_SF_qD
0x1800424a8  mov     ebx, [rsp+0C8h+arg_10]
0x1800424af  jmp     loc_180042643
0x1800424b4  lea     rsi, [rdi+70h]
0x1800424b8  mov     rdx, [rsi+18h]
0x1800424bc  test    rsi, rsi
0x1800424bf  jz      short loc_1800424C6
0x1800424c1  mov     rcx, [rsi]
0x1800424c4  jmp     short loc_1800424C9
0x1800424c6  mov     rcx, rbx
0x1800424c9  mov     r8, [rsi+20h]
0x1800424cd  add     r8, rdx
0x1800424d0  test    rsi, rsi
0x1800424d3  jz      short loc_1800424DA
0x1800424d5  mov     rax, [rsi]
0x1800424d8  jmp     short loc_1800424DD
0x1800424da  mov     rax, rbx
0x1800424dd  mov     [rsp+0C8h+var_70], rbx
0x1800424e2  mov     [rsp+0C8h+var_78], rax
0x1800424e7  mov     [rsp+0C8h+var_68], r8
0x1800424ec  mov     [rsp+0C8h+var_88], rbx
0x1800424f1  mov     [rsp+0C8h+var_90], rcx
0x1800424f6  mov     [rsp+0C8h+var_80], rdx
0x1800424fb  mov     r9, r15
0x1800424fe  lea     r8, [rsp+0C8h+var_78]
0x180042503  lea     rdx, [rsp+0C8h+var_90]
0x180042508  lea     rcx, [rsp+0C8h+var_60]
0x18004250d  call    ??$upper_bound@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@_JUPageLess@MkvReader@@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@0@V10@0AEB_JUPageLess@MkvReader@@@Z; std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64 const &,MkvReader::PageLess)
0x180042512  mov     r14, [rsp+0C8h+var_60]
0x180042517  mov     r12, [rsp+0C8h+var_50]
0x18004251c  dec     r12
0x18004251f  test    r14, r14
0x180042522  jz      short loc_180042527
0x180042524  mov     rbx, [r14]
0x180042527  mov     rcx, r12
0x18004252a  shr     rcx, 1
0x18004252d  mov     rax, [rbx+10h]
0x180042531  dec     rax
0x180042534  and     rcx, rax
0x180042537  mov     rbx, [rbx+8]
0x18004253b  mov     rax, r12
0x18004253e  and     eax, 1
0x180042541  mov     rbx, [rbx+rcx*8]
0x180042545  mov     rbx, [rbx+rax*8]
0x180042549  mov     dword ptr [rbx], 0
0x18004254f  mov     [rsp+0C8h+arg_18], 0
0x18004255a  mov     rcx, [rdi+10h]
0x18004255e  mov     rax, [rcx]
0x180042561  lea     r8, [rsp+0C8h+arg_18]
0x180042569  mov     rdx, r13
0x18004256c  mov     rax, [rax+58h]
0x180042570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042575  mov     [rsp+0C8h+arg_10], eax
0x18004257c  xor     r13d, r13d
0x18004257f  test    eax, eax
0x180042581  js      short loc_1800425DB
0x180042583  mov     eax, [rsp+0C8h+arg_18]
0x18004258a  mov     [rbx+10h], eax
0x18004258d  cmp     eax, [rdi+9Ch]
0x180042593  jnb     short loc_1800425DB
0x180042595  mov     rdx, [rbx+8]
0x180042599  add     rdx, rax
0x18004259c  mov     rax, [rdi+0C8h]
0x1800425a3  test    rax, rax
0x1800425a6  js      short loc_1800425BA
0x1800425a8  cmp     rdx, rax
0x1800425ab  jge     short loc_1800425DB
0x1800425ad  mov     [rsp+0C8h+arg_10], 0C00D36BBh
0x1800425b8  jmp     short loc_1800425DB
0x1800425ba  mov     [rdi+0C8h], rdx
0x1800425c1  movsxd  rax, dword ptr [rdi+0E0h]
0x1800425c8  add     rax, [r15]
0x1800425cb  cmp     rax, rdx
0x1800425ce  jle     short loc_1800425DB
0x1800425d0  mov     eax, edx
0x1800425d2  sub     eax, [r15]
0x1800425d5  mov     [rdi+0E0h], eax
0x1800425db  cmp     [rsp+0C8h+arg_10], r13d
0x1800425e3  jl      short loc_180042657
0x1800425e5  cmp     [rsp+0C8h+arg_18], r13d
0x1800425ed  jz      short loc_180042657
0x1800425ef  lea     r14, [rdi+0E0h]
0x1800425f6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800425fa  mov     edx, [rbx+10h]
0x1800425fd  add     rdx, [rbx+8]
0x180042601  cmp     rdx, [rdi+0D0h]
0x180042608  jle     short loc_180042611
0x18004260a  mov     [rdi+0D0h], rdx
0x180042611  mov     [rsp+0C8h+var_A8], r13
0x180042616  mov     r9, r14
0x180042619  mov     r8, r15
0x18004261c  mov     rdx, rbx
0x18004261f  mov     rcx, rdi
0x180042622  call    ?Read@MkvReader@@AEBAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@AEA_JAEAJPEAPEAE@Z; MkvReader::Read(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,__int64 &,long &,uchar * *)
0x180042627  cmp     [r14], r13d
0x18004262a  jle     loc_180042780
0x180042630  cmp     [rsp+0C8h+arg_0], r13b
0x180042638  jnz     loc_180042780
0x18004263e  mov     ebx, 1
0x180042643  lea     rcx, [rsp+0C8h+arg_0]; this
0x18004264b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180042650  mov     eax, ebx
0x180042652  jmp     loc_1800427A8
0x180042657  mov     [rsp+0C8h+var_88], r13
0x18004265c  mov     [rsp+0C8h+var_90], r14
0x180042661  mov     [rsp+0C8h+var_80], r12
0x180042666  lea     r8, [rsp+0C8h+var_90]
0x18004266b  lea     rdx, [rsp+0C8h+var_60]
0x180042670  mov     rcx, rsi
0x180042673  call    ?erase@?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@QEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@2@V?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@2@@Z; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::erase(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>)
0x180042678  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004267c  mov     [rbx+8], rsi
0x180042680  mov     [rbx+10h], r13d
0x180042684  mov     [rsp+0C8h+var_78], rsi
0x180042689  mov     [rsp+0C8h+var_70], rbx
0x18004268e  lea     rcx, [rdi+60h]
0x180042692  lea     r8, [rsp+0C8h+var_78]
0x180042697  lea     rdx, [rsp+0C8h+var_98]
0x18004269c  call    ??$insert@$00$0A@@?$_Tree@V?$_Tmap_traits@_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@@1@AEBU?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<__int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>,1>>::insert<1,0>(std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>> const &)
0x1800426a1  nop
0x1800426a2  lea     r14, [rdi+0E0h]
0x1800426a9  mov     [r14], esi
0x1800426ac  mov     [r15], rsi
0x1800426af  cmp     [rsp+0C8h+arg_10], r13d
0x1800426b7  jge     loc_1800425FA
0x1800426bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800426c4  test    rcx, rcx
0x1800426c7  jnz     short loc_18004270A
0x1800426c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800426cf  mov     rcx, rax
0x1800426d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800426d9  test    rax, rax
0x1800426dc  jz      short loc_1800426FC
0x1800426de  mov     rax, [rax]
0x1800426e1  mov     edx, 7F0h
0x1800426e6  mov     rax, [rax+8]
0x1800426ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426ef  test    eax, eax
0x1800426f1  jz      short loc_1800426FC
0x1800426f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800426fa  jmp     short loc_18004270A
0x1800426fc  lea     rcx, qword_1800D6F70; this
0x180042703  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004270a  cmp     [rcx+8], r13b
0x18004270e  jz      short loc_180042740
0x180042710  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042715  mov     r9d, [rsp+0C8h+arg_10]; int
0x18004271d  test    r9d, r9d
0x180042720  jns     short loc_180042740
0x180042722  cmp     [rax+7CCh], r9d
0x180042729  jz      short loc_180042740
0x18004272b  mov     r8d, 429h; int
0x180042731  lea     rdx, aMkvreaderAsync_1; "MkvReader::AsyncReadCompletion"
0x180042738  mov     rcx, rax; this
0x18004273b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042740  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042747  jb      short loc_180042774
0x180042749  mov     edx, 2Bh ; '+'
0x18004274e  mov     eax, [rsp+0C8h+arg_10]
0x180042755  mov     dword ptr [rsp+0C8h+var_A8], eax
0x180042759  mov     r9, rdi
0x18004275c  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180042763  mov     rcx, cs:WPP_GLOBAL_Control
0x18004276a  mov     rcx, [rcx+10h]
0x18004276e  call    WPP_SF_qD
0x180042773  nop
0x180042774  mov     ebx, [rsp+0C8h+arg_10]
0x18004277b  jmp     loc_180042643
0x180042780  mov     [r15], rsi
0x180042783  mov     [r14], esi
0x180042786  lea     rcx, [rsp+0C8h+arg_0]; this
0x18004278e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180042793  xor     eax, eax
0x180042795  jmp     short loc_1800427A8
0x180042797  lea     rcx, [rsp+0C8h+arg_0]; this
0x18004279f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800427a4  mov     eax, [rsp+0C8h+var_98]
0x1800427a8  add     rsp, 90h
0x1800427af  pop     r15
0x1800427b1  pop     r14
0x1800427b3  pop     r13
0x1800427b5  pop     r12
0x1800427b7  pop     rdi
0x1800427b8  pop     rsi
0x1800427b9  pop     rbx
0x1800427ba  retn
```
