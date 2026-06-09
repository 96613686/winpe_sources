# MkvReader::AsyncReadPage(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,IMFAsyncCallback *,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>> &)

- ea: `0x180044c20`
- end: `0x180045252`
- name: `?AsyncReadPage@MkvReader@@AEAAJV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@_JPEAUIMFAsyncCallback@@AEAV23@@Z`
- size: `1586`
- prototype: `__int64 __usercall@<rax>(MkvReader *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180044570`

## callees

- `0x180002400`
- `0x180002e54`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b58`
- `0x180021b9c`
- `0x180043cc4`
- `0x180044c20`
- `0x180045258`
- `0x1800477a4`
- `0x1800477e0`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044ceb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044ecc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044fc9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800450e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044ceb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044ecc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044fc9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800450e7`

## string_xrefs

- `0x180044c67`: `MkvReader::AsyncReadPage`
- `0x180044d56`: `MkvReader::AsyncReadPage`
- `0x180044f37`: `MkvReader::AsyncReadPage`
- `0x180045034`: `MkvReader::AsyncReadPage`
- `0x180045152`: `MkvReader::AsyncReadPage`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvReader::AsyncReadPage(MkvReader *this, __int64 *a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v15; // ebx
  __int64 v16; // r14
  _QWORD *v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // rbx
  __int64 *v20; // rax
  __int64 v21; // rdi
  _QWORD *v22; // rax
  const char *v23; // r9
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  unsigned __int64 i; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // r13
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 result; // rax
  _QWORD *v45; // rax
  const char *v46; // r9
  int Region; // [rsp+40h] [rbp-4B8h] BYREF
  _BYTE v48[4]; // [rsp+44h] [rbp-4B4h] BYREF
  unsigned int v49; // [rsp+48h] [rbp-4B0h]
  unsigned int v50; // [rsp+4Ch] [rbp-4ACh] BYREF
  unsigned __int64 v51; // [rsp+50h] [rbp-4A8h] BYREF
  __int64 v52; // [rsp+58h] [rbp-4A0h] BYREF
  __int64 v53; // [rsp+60h] [rbp-498h] BYREF
  __int64 v54; // [rsp+68h] [rbp-490h] BYREF
  __int64 v55; // [rsp+70h] [rbp-488h]
  __int64 v56; // [rsp+78h] [rbp-480h]
  __int64 v57; // [rsp+80h] [rbp-478h]
  MkvReader *v58; // [rsp+88h] [rbp-470h]
  int *v59; // [rsp+90h] [rbp-468h]
  _BYTE v60[24]; // [rsp+98h] [rbp-460h] BYREF
  _BYTE v61[1024]; // [rsp+B0h] [rbp-448h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+0h]

  v52 = a4;
  Region = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v48, "MkvReader::AsyncReadPage", 1100);
  v58 = this;
  v59 = &Region;
  v8 = *((unsigned int *)this + 39);
  v49 = *((_DWORD *)this + 39);
  if ( !*((_QWORD *)this + 13) )
  {
    if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 45, &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids, this);
    Region = MkvReader::CreateRegion(this);
    if ( Region < 0 )
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( Region < 0 && *((_DWORD *)ThreadRelativeContext + 499) != Region )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MkvReader::AsyncReadPage", 1110, Region);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids,
          this,
          Region);
      v15 = Region;
      goto LABEL_76;
    }
  }
  v57 = v8;
  v16 = a3 - a3 % v8;
  v17 = (_QWORD *)*((_QWORD *)this + 12);
  v18 = v17[1];
  HIDWORD(v55) = 0;
  v19 = v17;
  while ( !*(_BYTE *)(v18 + 25) )
  {
    if ( *(_QWORD *)(v18 + 32) >= v16 )
      v19 = (_QWORD *)v18;
    v20 = (__int64 *)(v18 + 16);
    if ( *(_QWORD *)(v18 + 32) >= v16 )
      v20 = (__int64 *)v18;
    v18 = *v20;
  }
  if ( *((_BYTE *)v19 + 25) || v16 < v19[4] || v19 == v17 )
    v19 = (_QWORD *)*v17;
  v21 = v19[5];
  v53 = v21;
  if ( *(_QWORD *)(v21 + 8) == v16 )
  {
    std::_Tree<std::_Tmap_traits<__int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>>,0>(
      (char *)this + 96,
      &v52,
      v19);
    try
    {
      v55 = 0;
      v54 = *a2;
      v56 = a2[2];
      v22 = (_QWORD *)std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::insert(
                        (char *)this + 112,
                        v60,
                        &v54,
                        &v53);
      *a5 = *v22;
      a5[2] = v22[2];
      v15 = 0;
    }
    catch ( ... )
    {
      v49 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x473,
              (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvreader.cpp",
              v23);
      v15 = v49;
      goto LABEL_76;
    }
    goto LABEL_76;
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 56LL))(*((_QWORD *)this + 2), v16) < 0 )
  {
    v51 = 0;
    memset_0(v61, 0, sizeof(v61));
    Region = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 2) + 48LL))(
               *((_QWORD *)this + 2),
               &v51);
    if ( Region < 0 )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( Region < 0 && *((_DWORD *)v29 + 499) != Region )
          CallStackContext::TraceFailure(v29, "MkvReader::AsyncReadPage", 1157, Region);
      }
      if ( !g_wppLevels )
        goto LABEL_75;
      v30 = 47;
LABEL_74:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v30,
        &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids,
        this,
        Region);
LABEL_75:
      v15 = Region;
LABEL_76:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v48);
      return v15;
    }
    for ( i = v51; i < v16; v51 = i )
    {
      v50 = 0;
      v32 = 1024;
      if ( v16 - i < 0x400 )
        v32 = v16 - i;
      Region = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64, unsigned int *))(**((_QWORD **)this + 2) + 72LL))(
                 *((_QWORD *)this + 2),
                 v61,
                 v32,
                 &v50);
      if ( Region < 0 )
      {
        v34 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v33);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( Region < 0 && *((_DWORD *)v36 + 499) != Region )
            CallStackContext::TraceFailure(v36, "MkvReader::AsyncReadPage", 1163, Region);
        }
        if ( g_wppLevels )
        {
          v30 = 48;
          goto LABEL_74;
        }
        goto LABEL_75;
      }
      i = v50 + v51;
    }
  }
  v37 = **(_QWORD **)(v21 + 24) + v57 * ((v21 - *(_QWORD *)(*(_QWORD *)(v21 + 24) + 8LL)) >> 5);
  if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
    WPP_SF_qiqD(*((_QWORD *)WPP_GLOBAL_Control + 17), v24, v25, this, v16, v37, v49);
  Region = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 2) + 80LL))(
             *((_QWORD *)this + 2),
             v37,
             v49,
             v52,
             0);
  if ( Region < 0 )
  {
    v41 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
      CallStackTracing::s_wpInstance = v42;
      if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
      {
        v41 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v41 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v41 + 8) )
    {
      v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
      if ( Region < 0 && *((_DWORD *)v43 + 499) != Region )
        CallStackContext::TraceFailure(v43, "MkvReader::AsyncReadPage", 1175, Region);
    }
    if ( !g_wppLevels )
      goto LABEL_75;
    v30 = 50;
    goto LABEL_74;
  }
  *(_QWORD *)(v21 + 8) = v16;
  *(_DWORD *)(v21 + 16) = 0;
  *(_DWORD *)v21 = -1;
  std::_Tree<std::_Tmap_traits<__int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>>,0>(
    (char *)this + 96,
    &v52,
    v19);
  try
  {
    v55 = 0;
    v54 = *a2;
    v56 = a2[2];
    v45 = (_QWORD *)std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::insert(
                      (char *)this + 112,
                      v60,
                      &v54,
                      &v53);
    *a5 = *v45;
    a5[2] = v45[2];
    Region = 1;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v48);
    result = 1;
  }
  catch ( ... )
  {
    v49 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x4A2,
            (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvreader.cpp",
            v46);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v48);
    return v49;
  }
  return result;
}

```

## disassembly

```asm
0x180044c20  push    rbx
0x180044c22  push    rsi
0x180044c23  push    rdi
0x180044c24  push    r12
0x180044c26  push    r13
0x180044c28  push    r14
0x180044c2a  push    r15
0x180044c2c  sub     rsp, 4C0h
0x180044c33  mov     rax, cs:__security_cookie
0x180044c3a  xor     rax, rsp
0x180044c3d  mov     [rsp+4F8h+var_48], rax
0x180044c45  mov     [rsp+4F8h+var_4A0], r9
0x180044c4a  mov     r14, r8
0x180044c4d  mov     r12, rdx
0x180044c50  mov     rsi, rcx
0x180044c53  mov     r15, [rsp+4F8h+arg_20]
0x180044c5b  xor     edi, edi
0x180044c5d  mov     [rsp+4F8h+var_4B8], edi
0x180044c61  mov     r8d, 44Ch; int
0x180044c67  lea     rdx, aMkvreaderAsync_0; "MkvReader::AsyncReadPage"
0x180044c6e  lea     rcx, [rsp+4F8h+var_4B4]; this
0x180044c73  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180044c78  nop
0x180044c79  mov     [rsp+4F8h+var_470], rsi
0x180044c81  lea     rax, [rsp+4F8h+var_4B8]
0x180044c86  mov     [rsp+4F8h+var_468], rax
0x180044c8e  mov     ebx, [rsi+9Ch]
0x180044c94  mov     [rsp+4F8h+var_4B0], ebx
0x180044c98  cmp     [rsi+68h], rdi
0x180044c9c  jnz     loc_180044D9E
0x180044ca2  cmp     cs:byte_1800DC8D3, 4
0x180044ca9  jb      short loc_180044CCB
0x180044cab  lea     edx, [rdi+2Dh]
0x180044cae  mov     r9, rsi
0x180044cb1  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180044cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180044cbf  mov     rcx, [rcx+88h]
0x180044cc6  call    WPP_SF_q
0x180044ccb  mov     rcx, rsi; this
0x180044cce  call    ?CreateRegion@MkvReader@@AEAAJXZ; MkvReader::CreateRegion(void)
0x180044cd3  mov     [rsp+4F8h+var_4B8], eax
0x180044cd7  test    eax, eax
0x180044cd9  jns     loc_180044D9E
0x180044cdf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044ce6  test    rcx, rcx
0x180044ce9  jnz     short loc_180044D32
0x180044ceb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044cf2  nop     dword ptr [rax+rax+00h]
0x180044cf7  mov     rcx, rax
0x180044cfa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044d01  test    rax, rax
0x180044d04  jz      short loc_180044D24
0x180044d06  mov     rax, [rax]
0x180044d09  mov     edx, 7F0h
0x180044d0e  mov     rax, [rax+8]
0x180044d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d17  test    eax, eax
0x180044d19  jz      short loc_180044D24
0x180044d1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044d22  jmp     short loc_180044D32
0x180044d24  lea     rcx, qword_1800DBF70; this
0x180044d2b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044d32  cmp     [rcx+8], dil
0x180044d36  jz      short loc_180044D65
0x180044d38  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044d3d  mov     r9d, [rsp+4F8h+var_4B8]; int
0x180044d42  test    r9d, r9d
0x180044d45  jns     short loc_180044D65
0x180044d47  cmp     [rax+7CCh], r9d
0x180044d4e  jz      short loc_180044D65
0x180044d50  mov     r8d, 456h; int
0x180044d56  lea     rdx, aMkvreaderAsync_0; "MkvReader::AsyncReadPage"
0x180044d5d  mov     rcx, rax; this
0x180044d60  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044d65  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044d6c  jb      short loc_180044D95
0x180044d6e  mov     edx, 2Eh ; '.'
0x180044d73  mov     eax, [rsp+4F8h+var_4B8]
0x180044d77  mov     dword ptr [rsp+4F8h+var_4D8], eax
0x180044d7b  mov     r9, rsi
0x180044d7e  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180044d85  mov     rcx, cs:WPP_GLOBAL_Control
0x180044d8c  mov     rcx, [rcx+10h]
0x180044d90  call    WPP_SF_qD
0x180044d95  mov     ebx, [rsp+4F8h+var_4B8]
0x180044d99  jmp     loc_180045196
0x180044d9e  mov     [rsp+4F8h+var_478], rbx
0x180044da6  mov     rax, r14
0x180044da9  cqo
0x180044dab  idiv    rbx
0x180044dae  sub     r14, rdx
0x180044db1  mov     rdx, [rsi+60h]
0x180044db5  mov     rcx, [rdx+8]
0x180044db9  xor     eax, eax
0x180044dbb  mov     [rsp+4F8h+var_484], eax
0x180044dbf  mov     rbx, rdx
0x180044dc2  jmp     short loc_180044DD7
0x180044dc4  cmp     [rcx+20h], r14
0x180044dc8  cmovge  rbx, rcx
0x180044dcc  lea     rax, [rcx+10h]
0x180044dd0  cmovge  rax, rcx
0x180044dd4  mov     rcx, [rax]
0x180044dd7  cmp     [rcx+19h], dil
0x180044ddb  jz      short loc_180044DC4
0x180044ddd  cmp     [rbx+19h], dil
0x180044de1  jnz     short loc_180044DEE
0x180044de3  cmp     r14, [rbx+20h]
0x180044de7  jl      short loc_180044DEE
0x180044de9  cmp     rbx, rdx
0x180044dec  jnz     short loc_180044DF1
0x180044dee  mov     rbx, [rdx]
0x180044df1  mov     rdi, [rbx+28h]
0x180044df5  mov     [rsp+4F8h+var_498], rdi
0x180044dfa  cmp     [rdi+8], r14
0x180044dfe  jnz     short loc_180044E67
0x180044e00  mov     r8, rbx
0x180044e03  lea     rdx, [rsp+4F8h+var_4A0]
0x180044e08  lea     rcx, [rsi+60h]
0x180044e0c  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<__int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>>)
0x180044e11  nop
0x180044e12  mov     qword ptr [rsp+70h], 0
0x180044e1b  mov     rax, [r12]
0x180044e1f  mov     [rsp+4F8h+var_490], rax
0x180044e24  mov     rax, [r12+10h]
0x180044e29  mov     [rsp+4F8h+var_480], rax
0x180044e2e  lea     rcx, [rsi+70h]
0x180044e32  lea     r9, [rsp+4F8h+var_498]
0x180044e37  lea     r8, [rsp+4F8h+var_490]
0x180044e3c  lea     rdx, [rsp+4F8h+var_460]
0x180044e44  call    ?insert@?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@QEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@2@V?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@2@AEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@2@@Z; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::insert(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>> const &)
0x180044e49  mov     rcx, [rax]
0x180044e4c  mov     [r15], rcx
0x180044e4f  mov     rax, [rax+10h]
0x180044e53  mov     [r15+10h], rax
0x180044e57  xor     ebx, ebx
0x180044e59  jmp     loc_180045196
0x180044e5e  mov     ebx, [rsp+4F8h+var_4B0]
0x180044e62  jmp     loc_180045196
0x180044e67  mov     rcx, [rsi+10h]
0x180044e6b  mov     rax, [rcx]
0x180044e6e  mov     rdx, r14
0x180044e71  mov     rax, [rax+38h]
0x180044e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e7a  xor     r13d, r13d
0x180044e7d  test    eax, eax
0x180044e7f  jns     loc_18004505A
0x180044e85  mov     [rsp+4F8h+var_4A8], r13
0x180044e8a  xor     edx, edx; Val
0x180044e8c  mov     r8d, 400h; Size
0x180044e92  lea     rcx, [rsp+4F8h+var_448]; void *
0x180044e9a  call    memset_0
0x180044e9f  mov     rcx, [rsi+10h]
0x180044ea3  mov     rax, [rcx]
0x180044ea6  lea     rdx, [rsp+4F8h+var_4A8]
0x180044eab  mov     rax, [rax+30h]
0x180044eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044eb4  mov     [rsp+4F8h+var_4B8], eax
0x180044eb8  test    eax, eax
0x180044eba  jns     loc_180044F5D
0x180044ec0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044ec7  test    rcx, rcx
0x180044eca  jnz     short loc_180044F13
0x180044ecc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044ed3  nop     dword ptr [rax+rax+00h]
0x180044ed8  mov     rcx, rax
0x180044edb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044ee2  test    rax, rax
0x180044ee5  jz      short loc_180044F05
0x180044ee7  mov     rax, [rax]
0x180044eea  mov     edx, 7F0h
0x180044eef  mov     rax, [rax+8]
0x180044ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ef8  test    eax, eax
0x180044efa  jz      short loc_180044F05
0x180044efc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044f03  jmp     short loc_180044F13
0x180044f05  lea     rcx, qword_1800DBF70; this
0x180044f0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044f13  cmp     [rcx+8], r13b
0x180044f17  jz      short loc_180044F46
0x180044f19  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044f1e  mov     r9d, [rsp+4F8h+var_4B8]; int
0x180044f23  test    r9d, r9d
0x180044f26  jns     short loc_180044F46
0x180044f28  cmp     [rax+7CCh], r9d
0x180044f2f  jz      short loc_180044F46
0x180044f31  mov     r8d, 485h; int
0x180044f37  lea     rdx, aMkvreaderAsync_0; "MkvReader::AsyncReadPage"
0x180044f3e  mov     rcx, rax; this
0x180044f41  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044f46  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044f4d  jb      loc_180045192
0x180044f53  mov     edx, 2Fh ; '/'
0x180044f58  jmp     loc_18004516F
0x180044f5d  mov     rcx, [rsp+4F8h+var_4A8]
0x180044f62  cmp     rcx, r14
0x180044f65  jnb     loc_18004505A
0x180044f6b  mov     [rsp+4F8h+var_4AC], r13d
0x180044f70  mov     rax, r14
0x180044f73  sub     rax, rcx
0x180044f76  mov     ecx, 400h
0x180044f7b  mov     r8d, ecx
0x180044f7e  cmp     rax, rcx
0x180044f81  cmovb   r8, rax
0x180044f85  mov     rcx, [rsi+10h]
0x180044f89  mov     rax, [rcx]
0x180044f8c  lea     r9, [rsp+4F8h+var_4AC]
0x180044f91  lea     rdx, [rsp+4F8h+var_448]
0x180044f99  mov     rax, [rax+48h]
0x180044f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044fa2  mov     [rsp+4F8h+var_4B8], eax
0x180044fa6  test    eax, eax
0x180044fa8  js      short loc_180044FBD
0x180044faa  mov     eax, [rsp+4F8h+var_4AC]
0x180044fae  mov     rcx, [rsp+4F8h+var_4A8]
0x180044fb3  add     rcx, rax
0x180044fb6  mov     [rsp+4F8h+var_4A8], rcx
0x180044fbb  jmp     short loc_180044F62
0x180044fbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044fc4  test    rcx, rcx
0x180044fc7  jnz     short loc_180045010
0x180044fc9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044fd0  nop     dword ptr [rax+rax+00h]
0x180044fd5  mov     rcx, rax
0x180044fd8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044fdf  test    rax, rax
0x180044fe2  jz      short loc_180045002
0x180044fe4  mov     rax, [rax]
0x180044fe7  mov     edx, 7F0h
0x180044fec  mov     rax, [rax+8]
0x180044ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ff5  test    eax, eax
0x180044ff7  jz      short loc_180045002
0x180044ff9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045000  jmp     short loc_180045010
0x180045002  lea     rcx, qword_1800DBF70; this
0x180045009  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045010  cmp     [rcx+8], r13b
0x180045014  jz      short loc_180045043
0x180045016  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004501b  mov     r9d, [rsp+4F8h+var_4B8]; int
0x180045020  test    r9d, r9d
0x180045023  jns     short loc_180045043
0x180045025  cmp     [rax+7CCh], r9d
0x18004502c  jz      short loc_180045043
0x18004502e  mov     r8d, 48Bh; int
0x180045034  lea     rdx, aMkvreaderAsync_0; "MkvReader::AsyncReadPage"
0x18004503b  mov     rcx, rax; this
0x18004503e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045043  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004504a  jb      loc_180045192
0x180045050  mov     edx, 30h ; '0'
0x180045055  jmp     loc_18004516F
0x18004505a  mov     rax, [rdi+18h]
0x18004505e  mov     r13, rdi
0x180045061  sub     r13, [rax+8]
0x180045065  sar     r13, 5
0x180045069  imul    r13, [rsp+4F8h+var_478]
0x180045072  add     r13, [rax]
0x180045075  cmp     cs:byte_1800DC8D3, 4
0x18004507c  jb      short loc_1800450A6
0x18004507e  mov     eax, [rsp+4F8h+var_4B0]
0x180045082  mov     [rsp+4F8h+var_4C8], eax
0x180045086  mov     [rsp+4F8h+var_4D0], r13
0x18004508b  mov     [rsp+4F8h+var_4D8], r14
0x180045090  mov     r9, rsi
0x180045093  mov     rcx, cs:WPP_GLOBAL_Control
0x18004509a  mov     rcx, [rcx+88h]
0x1800450a1  call    WPP_SF_qiqD
0x1800450a6  mov     rcx, [rsi+10h]
0x1800450aa  mov     rax, [rcx]
0x1800450ad  mov     [rsp+4F8h+var_4D8], 0
0x1800450b6  mov     r9, [rsp+4F8h+var_4A0]
0x1800450bb  mov     r8d, [rsp+4F8h+var_4B0]
0x1800450c0  mov     rdx, r13
0x1800450c3  mov     rax, [rax+50h]
0x1800450c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450cc  mov     [rsp+4F8h+var_4B8], eax
0x1800450d0  xor     r13d, r13d
0x1800450d3  test    eax, eax
0x1800450d5  jns     loc_1800451A7
0x1800450db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800450e2  test    rcx, rcx
0x1800450e5  jnz     short loc_18004512E
0x1800450e7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800450ee  nop     dword ptr [rax+rax+00h]
0x1800450f3  mov     rcx, rax
0x1800450f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800450fd  test    rax, rax
0x180045100  jz      short loc_180045120
0x180045102  mov     rax, [rax]
0x180045105  mov     edx, 7F0h
0x18004510a  mov     rax, [rax+8]
0x18004510e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045113  test    eax, eax
0x180045115  jz      short loc_180045120
0x180045117  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004511e  jmp     short loc_18004512E
0x180045120  lea     rcx, qword_1800DBF70; this
0x180045127  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
