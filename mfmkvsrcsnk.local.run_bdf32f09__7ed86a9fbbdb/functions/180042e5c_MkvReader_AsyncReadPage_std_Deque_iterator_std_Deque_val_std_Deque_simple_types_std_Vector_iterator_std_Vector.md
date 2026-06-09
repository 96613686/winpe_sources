# MkvReader::AsyncReadPage(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,IMFAsyncCallback *,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>> &)

- ea: `0x180042e5c`
- end: `0x180043475`
- name: `?AsyncReadPage@MkvReader@@AEAAJV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@_JPEAUIMFAsyncCallback@@AEAV23@@Z`
- size: `1561`
- prototype: `__int64 __usercall@<rax>(MkvReader *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800427c4`

## callees

- `0x1800023e0`
- `0x180002e14`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d44`
- `0x180020d84`
- `0x180041f38`
- `0x180042e5c`
- `0x18004347c`
- `0x1800458fc`
- `0x180045938`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042f27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043102`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800431f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043311`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042f27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043102`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800431f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043311`

## string_xrefs

- `0x180042ea3`: `MkvReader::AsyncReadPage`
- `0x180042f8c`: `MkvReader::AsyncReadPage`
- `0x180043167`: `MkvReader::AsyncReadPage`
- `0x18004325e`: `MkvReader::AsyncReadPage`
- `0x180043376`: `MkvReader::AsyncReadPage`

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
    if ( (unsigned __int8)byte_1800D78D3 >= 4u )
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
          v12 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v27 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v34 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
  if ( (unsigned __int8)byte_1800D78D3 >= 4u )
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
        v41 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180042e5c  push    rbx
0x180042e5e  push    rsi
0x180042e5f  push    rdi
0x180042e60  push    r12
0x180042e62  push    r13
0x180042e64  push    r14
0x180042e66  push    r15
0x180042e68  sub     rsp, 4C0h
0x180042e6f  mov     rax, cs:__security_cookie
0x180042e76  xor     rax, rsp
0x180042e79  mov     [rsp+4F8h+var_48], rax
0x180042e81  mov     [rsp+4F8h+var_4A0], r9
0x180042e86  mov     r14, r8
0x180042e89  mov     r12, rdx
0x180042e8c  mov     rsi, rcx
0x180042e8f  mov     r15, [rsp+4F8h+arg_20]
0x180042e97  xor     edi, edi
0x180042e99  mov     [rsp+4F8h+var_4B8], edi
0x180042e9d  mov     r8d, 44Ch; int
0x180042ea3  lea     rdx, aMkvreaderAsync_0; "MkvReader::AsyncReadPage"
0x180042eaa  lea     rcx, [rsp+4F8h+var_4B4]; this
0x180042eaf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180042eb4  nop
0x180042eb5  mov     [rsp+4F8h+var_470], rsi
0x180042ebd  lea     rax, [rsp+4F8h+var_4B8]
0x180042ec2  mov     [rsp+4F8h+var_468], rax
0x180042eca  mov     ebx, [rsi+9Ch]
0x180042ed0  mov     [rsp+4F8h+var_4B0], ebx
0x180042ed4  cmp     [rsi+68h], rdi
0x180042ed8  jnz     loc_180042FD4
0x180042ede  cmp     cs:byte_1800D78D3, 4
0x180042ee5  jb      short loc_180042F07
0x180042ee7  lea     edx, [rdi+2Dh]
0x180042eea  mov     r9, rsi
0x180042eed  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180042ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180042efb  mov     rcx, [rcx+88h]
0x180042f02  call    WPP_SF_q
0x180042f07  mov     rcx, rsi; this
0x180042f0a  call    ?CreateRegion@MkvReader@@AEAAJXZ; MkvReader::CreateRegion(void)
0x180042f0f  mov     [rsp+4F8h+var_4B8], eax
0x180042f13  test    eax, eax
0x180042f15  jns     loc_180042FD4
0x180042f1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042f22  test    rcx, rcx
0x180042f25  jnz     short loc_180042F68
0x180042f27  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042f2d  mov     rcx, rax
0x180042f30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042f37  test    rax, rax
0x180042f3a  jz      short loc_180042F5A
0x180042f3c  mov     rax, [rax]
0x180042f3f  mov     edx, 7F0h
0x180042f44  mov     rax, [rax+8]
0x180042f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f4d  test    eax, eax
0x180042f4f  jz      short loc_180042F5A
0x180042f51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042f58  jmp     short loc_180042F68
0x180042f5a  lea     rcx, qword_1800D6F70; this
0x180042f61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042f68  cmp     [rcx+8], dil
0x180042f6c  jz      short loc_180042F9B
0x180042f6e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042f73  mov     r9d, [rsp+4F8h+var_4B8]; int
0x180042f78  test    r9d, r9d
0x180042f7b  jns     short loc_180042F9B
0x180042f7d  cmp     [rax+7CCh], r9d
0x180042f84  jz      short loc_180042F9B
0x180042f86  mov     r8d, 456h; int
0x180042f8c  lea     rdx, aMkvreaderAsync_0; "MkvReader::AsyncReadPage"
0x180042f93  mov     rcx, rax; this
0x180042f96  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042f9b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042fa2  jb      short loc_180042FCB
0x180042fa4  mov     edx, 2Eh ; '.'
0x180042fa9  mov     eax, [rsp+4F8h+var_4B8]
0x180042fad  mov     dword ptr [rsp+4F8h+var_4D8], eax
0x180042fb1  mov     r9, rsi
0x180042fb4  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180042fbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180042fc2  mov     rcx, [rcx+10h]
0x180042fc6  call    WPP_SF_qD
0x180042fcb  mov     ebx, [rsp+4F8h+var_4B8]
0x180042fcf  jmp     loc_1800433BA
0x180042fd4  mov     [rsp+4F8h+var_478], rbx
0x180042fdc  mov     rax, r14
0x180042fdf  cqo
0x180042fe1  idiv    rbx
0x180042fe4  sub     r14, rdx
0x180042fe7  mov     rdx, [rsi+60h]
0x180042feb  mov     rcx, [rdx+8]
0x180042fef  xor     eax, eax
0x180042ff1  mov     [rsp+4F8h+var_484], eax
0x180042ff5  mov     rbx, rdx
0x180042ff8  jmp     short loc_18004300D
0x180042ffa  cmp     [rcx+20h], r14
0x180042ffe  cmovge  rbx, rcx
0x180043002  lea     rax, [rcx+10h]
0x180043006  cmovge  rax, rcx
0x18004300a  mov     rcx, [rax]
0x18004300d  cmp     [rcx+19h], dil
0x180043011  jz      short loc_180042FFA
0x180043013  cmp     [rbx+19h], dil
0x180043017  jnz     short loc_180043024
0x180043019  cmp     r14, [rbx+20h]
0x18004301d  jl      short loc_180043024
0x18004301f  cmp     rbx, rdx
0x180043022  jnz     short loc_180043027
0x180043024  mov     rbx, [rdx]
0x180043027  mov     rdi, [rbx+28h]
0x18004302b  mov     [rsp+4F8h+var_498], rdi
0x180043030  cmp     [rdi+8], r14
0x180043034  jnz     short loc_18004309D
0x180043036  mov     r8, rbx
0x180043039  lea     rdx, [rsp+4F8h+var_4A0]
0x18004303e  lea     rcx, [rsi+60h]
0x180043042  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<__int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>>)
0x180043047  nop
0x180043048  mov     qword ptr [rsp+70h], 0
0x180043051  mov     rax, [r12]
0x180043055  mov     [rsp+4F8h+var_490], rax
0x18004305a  mov     rax, [r12+10h]
0x18004305f  mov     [rsp+4F8h+var_480], rax
0x180043064  lea     rcx, [rsi+70h]
0x180043068  lea     r9, [rsp+4F8h+var_498]
0x18004306d  lea     r8, [rsp+4F8h+var_490]
0x180043072  lea     rdx, [rsp+4F8h+var_460]
0x18004307a  call    ?insert@?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@QEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@2@V?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@2@AEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@2@@Z; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::insert(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>> const &)
0x18004307f  mov     rcx, [rax]
0x180043082  mov     [r15], rcx
0x180043085  mov     rax, [rax+10h]
0x180043089  mov     [r15+10h], rax
0x18004308d  xor     ebx, ebx
0x18004308f  jmp     loc_1800433BA
0x180043094  mov     ebx, [rsp+4F8h+var_4B0]
0x180043098  jmp     loc_1800433BA
0x18004309d  mov     rcx, [rsi+10h]
0x1800430a1  mov     rax, [rcx]
0x1800430a4  mov     rdx, r14
0x1800430a7  mov     rax, [rax+38h]
0x1800430ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800430b0  xor     r13d, r13d
0x1800430b3  test    eax, eax
0x1800430b5  jns     loc_180043284
0x1800430bb  mov     [rsp+4F8h+var_4A8], r13
0x1800430c0  xor     edx, edx; Val
0x1800430c2  mov     r8d, 400h; Size
0x1800430c8  lea     rcx, [rsp+4F8h+var_448]; void *
0x1800430d0  call    memset_0
0x1800430d5  mov     rcx, [rsi+10h]
0x1800430d9  mov     rax, [rcx]
0x1800430dc  lea     rdx, [rsp+4F8h+var_4A8]
0x1800430e1  mov     rax, [rax+30h]
0x1800430e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800430ea  mov     [rsp+4F8h+var_4B8], eax
0x1800430ee  test    eax, eax
0x1800430f0  jns     loc_18004318D
0x1800430f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800430fd  test    rcx, rcx
0x180043100  jnz     short loc_180043143
0x180043102  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043108  mov     rcx, rax
0x18004310b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043112  test    rax, rax
0x180043115  jz      short loc_180043135
0x180043117  mov     rax, [rax]
0x18004311a  mov     edx, 7F0h
0x18004311f  mov     rax, [rax+8]
0x180043123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043128  test    eax, eax
0x18004312a  jz      short loc_180043135
0x18004312c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043133  jmp     short loc_180043143
0x180043135  lea     rcx, qword_1800D6F70; this
0x18004313c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043143  cmp     [rcx+8], r13b
0x180043147  jz      short loc_180043176
0x180043149  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004314e  mov     r9d, [rsp+4F8h+var_4B8]; int
0x180043153  test    r9d, r9d
0x180043156  jns     short loc_180043176
0x180043158  cmp     [rax+7CCh], r9d
0x18004315f  jz      short loc_180043176
0x180043161  mov     r8d, 485h; int
0x180043167  lea     rdx, aMkvreaderAsync_0; "MkvReader::AsyncReadPage"
0x18004316e  mov     rcx, rax; this
0x180043171  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043176  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004317d  jb      loc_1800433B6
0x180043183  mov     edx, 2Fh ; '/'
0x180043188  jmp     loc_180043393
0x18004318d  mov     rcx, [rsp+4F8h+var_4A8]
0x180043192  cmp     rcx, r14
0x180043195  jnb     loc_180043284
0x18004319b  mov     [rsp+4F8h+var_4AC], r13d
0x1800431a0  mov     rax, r14
0x1800431a3  sub     rax, rcx
0x1800431a6  mov     ecx, 400h
0x1800431ab  mov     r8d, ecx
0x1800431ae  cmp     rax, rcx
0x1800431b1  cmovb   r8, rax
0x1800431b5  mov     rcx, [rsi+10h]
0x1800431b9  mov     rax, [rcx]
0x1800431bc  lea     r9, [rsp+4F8h+var_4AC]
0x1800431c1  lea     rdx, [rsp+4F8h+var_448]
0x1800431c9  mov     rax, [rax+48h]
0x1800431cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431d2  mov     [rsp+4F8h+var_4B8], eax
0x1800431d6  test    eax, eax
0x1800431d8  js      short loc_1800431ED
0x1800431da  mov     eax, [rsp+4F8h+var_4AC]
0x1800431de  mov     rcx, [rsp+4F8h+var_4A8]
0x1800431e3  add     rcx, rax
0x1800431e6  mov     [rsp+4F8h+var_4A8], rcx
0x1800431eb  jmp     short loc_180043192
0x1800431ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800431f4  test    rcx, rcx
0x1800431f7  jnz     short loc_18004323A
0x1800431f9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800431ff  mov     rcx, rax
0x180043202  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043209  test    rax, rax
0x18004320c  jz      short loc_18004322C
0x18004320e  mov     rax, [rax]
0x180043211  mov     edx, 7F0h
0x180043216  mov     rax, [rax+8]
0x18004321a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004321f  test    eax, eax
0x180043221  jz      short loc_18004322C
0x180043223  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004322a  jmp     short loc_18004323A
0x18004322c  lea     rcx, qword_1800D6F70; this
0x180043233  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004323a  cmp     [rcx+8], r13b
0x18004323e  jz      short loc_18004326D
0x180043240  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043245  mov     r9d, [rsp+4F8h+var_4B8]; int
0x18004324a  test    r9d, r9d
0x18004324d  jns     short loc_18004326D
0x18004324f  cmp     [rax+7CCh], r9d
0x180043256  jz      short loc_18004326D
0x180043258  mov     r8d, 48Bh; int
0x18004325e  lea     rdx, aMkvreaderAsync_0; "MkvReader::AsyncReadPage"
0x180043265  mov     rcx, rax; this
0x180043268  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004326d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043274  jb      loc_1800433B6
0x18004327a  mov     edx, 30h ; '0'
0x18004327f  jmp     loc_180043393
0x180043284  mov     rax, [rdi+18h]
0x180043288  mov     r13, rdi
0x18004328b  sub     r13, [rax+8]
0x18004328f  sar     r13, 5
0x180043293  imul    r13, [rsp+4F8h+var_478]
0x18004329c  add     r13, [rax]
0x18004329f  cmp     cs:byte_1800D78D3, 4
0x1800432a6  jb      short loc_1800432D0
0x1800432a8  mov     eax, [rsp+4F8h+var_4B0]
0x1800432ac  mov     [rsp+4F8h+var_4C8], eax
0x1800432b0  mov     [rsp+4F8h+var_4D0], r13
0x1800432b5  mov     [rsp+4F8h+var_4D8], r14
0x1800432ba  mov     r9, rsi
0x1800432bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800432c4  mov     rcx, [rcx+88h]
0x1800432cb  call    WPP_SF_qiqD
0x1800432d0  mov     rcx, [rsi+10h]
0x1800432d4  mov     rax, [rcx]
0x1800432d7  mov     [rsp+4F8h+var_4D8], 0
0x1800432e0  mov     r9, [rsp+4F8h+var_4A0]
0x1800432e5  mov     r8d, [rsp+4F8h+var_4B0]
0x1800432ea  mov     rdx, r13
0x1800432ed  mov     rax, [rax+50h]
0x1800432f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432f6  mov     [rsp+4F8h+var_4B8], eax
0x1800432fa  xor     r13d, r13d
0x1800432fd  test    eax, eax
0x1800432ff  jns     loc_1800433CB
0x180043305  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004330c  test    rcx, rcx
0x18004330f  jnz     short loc_180043352
0x180043311  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043317  mov     rcx, rax
0x18004331a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043321  test    rax, rax
0x180043324  jz      short loc_180043344
0x180043326  mov     rax, [rax]
0x180043329  mov     edx, 7F0h
0x18004332e  mov     rax, [rax+8]
0x180043332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043337  test    eax, eax
0x180043339  jz      short loc_180043344
0x18004333b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043342  jmp     short loc_180043352
0x180043344  lea     rcx, qword_1800D6F70; this
0x18004334b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043352  cmp     [rcx+8], r13b
0x180043356  jz      short loc_180043385
0x180043358  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004335d  mov     r9d, [rsp+4F8h+var_4B8]; int
  ... truncated ...
```
