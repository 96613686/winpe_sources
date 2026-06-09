# MkvReader::AsyncReadCompletion(IMFAsyncResult *)

- ea: `0x18004411c`
- end: `0x180044568`
- name: `?AsyncReadCompletion@MkvReader@@QEAAJPEAUIMFAsyncResult@@@Z`
- size: `1100`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180016520`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180043d14`
- `0x180043d40`
- `0x18004411c`
- `0x1800465d0`
- `0x180047750`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004419f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004446f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004419f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004446f`

## string_xrefs

- `0x180044142`: `MkvReader::AsyncReadCompletion`
- `0x18004420c`: `MkvReader::AsyncReadCompletion`
- `0x1800444dd`: `MkvReader::AsyncReadCompletion`

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
  int *v24; // r14
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
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
    v24 = (int *)((char *)this + 224);
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
    v24 = (int *)((char *)this + 224);
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
          v30 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
  MkvReader::Read((_DWORD)this, v20, (_DWORD)this + 216, (_DWORD)v24, 0);
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
0x18004411c  mov     rax, rsp
0x18004411f  push    rbx
0x180044120  push    rsi
0x180044121  push    rdi
0x180044122  push    r12
0x180044124  push    r13
0x180044126  push    r14
0x180044128  push    r15
0x18004412a  sub     rsp, 90h
0x180044131  mov     r13, rdx
0x180044134  mov     rdi, rcx
0x180044137  xor     ebx, ebx
0x180044139  mov     [rax+18h], ebx
0x18004413c  mov     r8d, 3D0h; int
0x180044142  lea     rdx, aMkvreaderAsync_1; "MkvReader::AsyncReadCompletion"
0x180044149  lea     rcx, [rax+8]; this
0x18004414d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180044152  nop
0x180044153  mov     [rsp+0C8h+var_48], rdi
0x18004415b  lea     rax, [rsp+0C8h+arg_10]
0x180044163  mov     [rsp+0C8h+var_40], rax
0x18004416b  mov     al, [rdi+8]
0x18004416e  mov     [rsp+0C8h+arg_0], al
0x180044175  mov     [rdi+8], bl
0x180044178  lea     r15, [rdi+0D8h]
0x18004417f  cmp     [r15], rbx
0x180044182  jge     loc_18004425A
0x180044188  mov     [rsp+0C8h+arg_10], 8000FFFFh
0x180044193  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004419a  test    rcx, rcx
0x18004419d  jnz     short loc_1800441E6
0x18004419f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800441a6  nop     dword ptr [rax+rax+00h]
0x1800441ab  mov     rcx, rax
0x1800441ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800441b5  test    rax, rax
0x1800441b8  jz      short loc_1800441D8
0x1800441ba  mov     rax, [rax]
0x1800441bd  mov     edx, 7F0h
0x1800441c2  mov     rax, [rax+8]
0x1800441c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441cb  test    eax, eax
0x1800441cd  jz      short loc_1800441D8
0x1800441cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800441d6  jmp     short loc_1800441E6
0x1800441d8  lea     rcx, qword_1800DBF70; this
0x1800441df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800441e6  cmp     [rcx+8], bl
0x1800441e9  jz      short loc_18004421B
0x1800441eb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800441f0  mov     r9d, [rsp+0C8h+arg_10]; int
0x1800441f8  test    r9d, r9d
0x1800441fb  jns     short loc_18004421B
0x1800441fd  cmp     [rax+7CCh], r9d
0x180044204  jz      short loc_18004421B
0x180044206  mov     r8d, 3DAh; int
0x18004420c  lea     rdx, aMkvreaderAsync_1; "MkvReader::AsyncReadCompletion"
0x180044213  mov     rcx, rax; this
0x180044216  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004421b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044222  jb      short loc_18004424E
0x180044224  mov     edx, 2Ah ; '*'
0x180044229  mov     eax, [rsp+0C8h+arg_10]
0x180044230  mov     dword ptr [rsp+0C8h+var_A8], eax
0x180044234  mov     r9, rdi
0x180044237  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x18004423e  mov     rcx, cs:WPP_GLOBAL_Control
0x180044245  mov     rcx, [rcx+10h]
0x180044249  call    WPP_SF_qD
0x18004424e  mov     ebx, [rsp+0C8h+arg_10]
0x180044255  jmp     loc_1800443E9
0x18004425a  lea     rsi, [rdi+70h]
0x18004425e  mov     rdx, [rsi+18h]
0x180044262  test    rsi, rsi
0x180044265  jz      short loc_18004426C
0x180044267  mov     rcx, [rsi]
0x18004426a  jmp     short loc_18004426F
0x18004426c  mov     rcx, rbx
0x18004426f  mov     r8, [rsi+20h]
0x180044273  add     r8, rdx
0x180044276  test    rsi, rsi
0x180044279  jz      short loc_180044280
0x18004427b  mov     rax, [rsi]
0x18004427e  jmp     short loc_180044283
0x180044280  mov     rax, rbx
0x180044283  mov     [rsp+0C8h+var_70], rbx
0x180044288  mov     [rsp+0C8h+var_78], rax
0x18004428d  mov     [rsp+0C8h+var_68], r8
0x180044292  mov     [rsp+0C8h+var_88], rbx
0x180044297  mov     [rsp+0C8h+var_90], rcx
0x18004429c  mov     [rsp+0C8h+var_80], rdx
0x1800442a1  mov     r9, r15
0x1800442a4  lea     r8, [rsp+0C8h+var_78]
0x1800442a9  lea     rdx, [rsp+0C8h+var_90]
0x1800442ae  lea     rcx, [rsp+0C8h+var_60]
0x1800442b3  call    ??$upper_bound@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@_JUPageLess@MkvReader@@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@0@V10@0AEB_JUPageLess@MkvReader@@@Z; std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64 const &,MkvReader::PageLess)
0x1800442b8  mov     r14, [rsp+0C8h+var_60]
0x1800442bd  mov     r12, [rsp+0C8h+var_50]
0x1800442c2  dec     r12
0x1800442c5  test    r14, r14
0x1800442c8  jz      short loc_1800442CD
0x1800442ca  mov     rbx, [r14]
0x1800442cd  mov     rcx, r12
0x1800442d0  shr     rcx, 1
0x1800442d3  mov     rax, [rbx+10h]
0x1800442d7  dec     rax
0x1800442da  and     rcx, rax
0x1800442dd  mov     rbx, [rbx+8]
0x1800442e1  mov     rax, r12
0x1800442e4  and     eax, 1
0x1800442e7  mov     rbx, [rbx+rcx*8]
0x1800442eb  mov     rbx, [rbx+rax*8]
0x1800442ef  mov     dword ptr [rbx], 0
0x1800442f5  mov     [rsp+0C8h+arg_18], 0
0x180044300  mov     rcx, [rdi+10h]
0x180044304  mov     rax, [rcx]
0x180044307  lea     r8, [rsp+0C8h+arg_18]
0x18004430f  mov     rdx, r13
0x180044312  mov     rax, [rax+58h]
0x180044316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004431b  mov     [rsp+0C8h+arg_10], eax
0x180044322  xor     r13d, r13d
0x180044325  test    eax, eax
0x180044327  js      short loc_180044381
0x180044329  mov     eax, [rsp+0C8h+arg_18]
0x180044330  mov     [rbx+10h], eax
0x180044333  cmp     eax, [rdi+9Ch]
0x180044339  jnb     short loc_180044381
0x18004433b  mov     rdx, [rbx+8]
0x18004433f  add     rdx, rax
0x180044342  mov     rax, [rdi+0C8h]
0x180044349  test    rax, rax
0x18004434c  js      short loc_180044360
0x18004434e  cmp     rdx, rax
0x180044351  jge     short loc_180044381
0x180044353  mov     [rsp+0C8h+arg_10], 0C00D36BBh
0x18004435e  jmp     short loc_180044381
0x180044360  mov     [rdi+0C8h], rdx
0x180044367  movsxd  rax, dword ptr [rdi+0E0h]
0x18004436e  add     rax, [r15]
0x180044371  cmp     rax, rdx
0x180044374  jle     short loc_180044381
0x180044376  mov     eax, edx
0x180044378  sub     eax, [r15]
0x18004437b  mov     [rdi+0E0h], eax
0x180044381  cmp     [rsp+0C8h+arg_10], r13d
0x180044389  jl      short loc_1800443FD
0x18004438b  cmp     [rsp+0C8h+arg_18], r13d
0x180044393  jz      short loc_1800443FD
0x180044395  lea     r14, [rdi+0E0h]
0x18004439c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800443a0  mov     edx, [rbx+10h]
0x1800443a3  add     rdx, [rbx+8]
0x1800443a7  cmp     rdx, [rdi+0D0h]
0x1800443ae  jle     short loc_1800443B7
0x1800443b0  mov     [rdi+0D0h], rdx
0x1800443b7  mov     [rsp+0C8h+var_A8], r13
0x1800443bc  mov     r9, r14
0x1800443bf  mov     r8, r15
0x1800443c2  mov     rdx, rbx
0x1800443c5  mov     rcx, rdi
0x1800443c8  call    ?Read@MkvReader@@AEBAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@AEA_JAEAJPEAPEAE@Z; MkvReader::Read(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,__int64 &,long &,uchar * *)
0x1800443cd  cmp     [r14], r13d
0x1800443d0  jle     loc_18004452C
0x1800443d6  cmp     [rsp+0C8h+arg_0], r13b
0x1800443de  jnz     loc_18004452C
0x1800443e4  mov     ebx, 1
0x1800443e9  lea     rcx, [rsp+0C8h+arg_0]; this
0x1800443f1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800443f6  mov     eax, ebx
0x1800443f8  jmp     loc_180044554
0x1800443fd  mov     [rsp+0C8h+var_88], r13
0x180044402  mov     [rsp+0C8h+var_90], r14
0x180044407  mov     [rsp+0C8h+var_80], r12
0x18004440c  lea     r8, [rsp+0C8h+var_90]
0x180044411  lea     rdx, [rsp+0C8h+var_60]
0x180044416  mov     rcx, rsi
0x180044419  call    ?erase@?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@QEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@2@V?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@2@@Z; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::erase(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>)
0x18004441e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180044422  mov     [rbx+8], rsi
0x180044426  mov     [rbx+10h], r13d
0x18004442a  mov     [rsp+0C8h+var_78], rsi
0x18004442f  mov     [rsp+0C8h+var_70], rbx
0x180044434  lea     rcx, [rdi+60h]
0x180044438  lea     r8, [rsp+0C8h+var_78]
0x18004443d  lea     rdx, [rsp+0C8h+var_98]
0x180044442  call    ??$insert@$00$0A@@?$_Tree@V?$_Tmap_traits@_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@@1@AEBU?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<__int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>,1>>::insert<1,0>(std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>> const &)
0x180044447  nop
0x180044448  lea     r14, [rdi+0E0h]
0x18004444f  mov     [r14], esi
0x180044452  mov     [r15], rsi
0x180044455  cmp     [rsp+0C8h+arg_10], r13d
0x18004445d  jge     loc_1800443A0
0x180044463  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004446a  test    rcx, rcx
0x18004446d  jnz     short loc_1800444B6
0x18004446f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044476  nop     dword ptr [rax+rax+00h]
0x18004447b  mov     rcx, rax
0x18004447e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044485  test    rax, rax
0x180044488  jz      short loc_1800444A8
0x18004448a  mov     rax, [rax]
0x18004448d  mov     edx, 7F0h
0x180044492  mov     rax, [rax+8]
0x180044496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004449b  test    eax, eax
0x18004449d  jz      short loc_1800444A8
0x18004449f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800444a6  jmp     short loc_1800444B6
0x1800444a8  lea     rcx, qword_1800DBF70; this
0x1800444af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800444b6  cmp     [rcx+8], r13b
0x1800444ba  jz      short loc_1800444EC
0x1800444bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800444c1  mov     r9d, [rsp+0C8h+arg_10]; int
0x1800444c9  test    r9d, r9d
0x1800444cc  jns     short loc_1800444EC
0x1800444ce  cmp     [rax+7CCh], r9d
0x1800444d5  jz      short loc_1800444EC
0x1800444d7  mov     r8d, 429h; int
0x1800444dd  lea     rdx, aMkvreaderAsync_1; "MkvReader::AsyncReadCompletion"
0x1800444e4  mov     rcx, rax; this
0x1800444e7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800444ec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800444f3  jb      short loc_180044520
0x1800444f5  mov     edx, 2Bh ; '+'
0x1800444fa  mov     eax, [rsp+0C8h+arg_10]
0x180044501  mov     dword ptr [rsp+0C8h+var_A8], eax
0x180044505  mov     r9, rdi
0x180044508  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x18004450f  mov     rcx, cs:WPP_GLOBAL_Control
0x180044516  mov     rcx, [rcx+10h]
0x18004451a  call    WPP_SF_qD
0x18004451f  nop
0x180044520  mov     ebx, [rsp+0C8h+arg_10]
0x180044527  jmp     loc_1800443E9
0x18004452c  mov     [r15], rsi
0x18004452f  mov     [r14], esi
0x180044532  lea     rcx, [rsp+0C8h+arg_0]; this
0x18004453a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004453f  xor     eax, eax
0x180044541  jmp     short loc_180044554
0x180044543  lea     rcx, [rsp+0C8h+arg_0]; this
0x18004454b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180044550  mov     eax, [rsp+0C8h+var_98]
0x180044554  add     rsp, 90h
0x18004455b  pop     r15
0x18004455d  pop     r14
0x18004455f  pop     r13
0x180044561  pop     r12
0x180044563  pop     rdi
0x180044564  pop     rsi
0x180044565  pop     rbx
0x180044566  retn
```
