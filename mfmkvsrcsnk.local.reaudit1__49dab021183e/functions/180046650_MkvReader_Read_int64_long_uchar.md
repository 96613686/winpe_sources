# MkvReader::Read(__int64,long,uchar *)

- ea: `0x180046650`
- end: `0x180046bbb`
- name: `?Read@MkvReader@@UEAAJ_JJPEAE@Z`
- size: `1387`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, __int64, int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180043d40`
- `0x1800465d0`
- `0x180046650`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800466ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046795`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046882`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046957`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800466ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046795`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046882`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046957`

## string_xrefs

- `0x180046690`: `MkvReader::Read`
- `0x180046712`: `MkvReader::Read`
- `0x180046778`: `MkvReader::Read`
- `0x1800467fa`: `MkvReader::Read`
- `0x180046865`: `MkvReader::Read`
- `0x1800468e7`: `MkvReader::Read`
- `0x180046931`: `MkvReader::Read`
- `0x1800469bc`: `MkvReader::Read`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvReader::Read(MkvReader *this, __int64 a2, int a3, unsigned __int8 *a4)
{
  int v5; // r14d
  signed __int64 v6; // rsi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  unsigned int v13; // ebx
  struct CallStackContext *v14; // rax
  CallStackScopeTrace *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v36; // r8
  _QWORD *v37; // r12
  unsigned __int64 v38; // r9
  __int64 *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rax
  _QWORD *v43; // rbx
  unsigned __int64 v44; // r15
  _QWORD *v45; // rdx
  __int64 v46; // rdx
  _QWORD *v47; // rax
  unsigned __int64 v48; // r8
  __int64 v49; // r10
  _QWORD *v50; // rax
  _BYTE v51[8]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v52[3]; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v53[3]; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v54[24]; // [rsp+68h] [rbp-18h] BYREF
  signed __int64 v55; // [rsp+C8h] [rbp+48h] BYREF
  int v56; // [rsp+D0h] [rbp+50h] BYREF
  unsigned __int8 *v57; // [rsp+D8h] [rbp+58h] BYREF

  v57 = a4;
  v56 = a3;
  v55 = a2;
  v5 = a3;
  v6 = a2;
  if ( a2 >= 0 )
  {
    v16 = *((_QWORD *)this + 25);
    if ( v16 < 0 || a2 <= v16 )
    {
      if ( a3 <= 0 )
        return 0;
      if ( v16 < 0 || a2 + a3 <= v16 )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v51, "MkvReader::Read", 226);
        if ( a4 )
        {
          v36 = *((_QWORD *)this + 18);
          if ( !v36
            || (v37 = (_QWORD *)((char *)this + 136),
                v38 = *((_QWORD *)this + 17),
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 15)
                                                  + 8 * ((*((_QWORD *)this + 16) - 1LL) & (v38 >> 1)))
                                      + 8 * (v38 & 1))
                          + 8LL) > v6) )
          {
            v43 = (_QWORD *)((char *)this + 112);
            v44 = *((_QWORD *)this + 17);
            if ( this != (MkvReader *)-112LL )
              v43 = (_QWORD *)*v43;
            v37 = (_QWORD *)((char *)this + 136);
            goto LABEL_65;
          }
          v39 = (__int64 *)((char *)this + 112);
          if ( this == (MkvReader *)-112LL )
          {
            v40 = 0;
            v41 = 0;
          }
          else
          {
            v40 = *v39;
            v41 = *v39;
          }
          v52[1] = 0;
          v52[0] = v40;
          v52[2] = v38 + v36;
          v53[1] = 0;
          v53[0] = v41;
          v53[2] = v38;
          v42 = std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(
                  v54,
                  v53,
                  v52,
                  &v55);
          v43 = *(_QWORD **)v42;
          v44 = *(_QWORD *)(v42 + 16);
          if ( *(_QWORD *)v42 )
            v45 = (_QWORD *)*v43;
          else
            v45 = 0;
          v46 = *(_QWORD *)(*(_QWORD *)(v45[1] + 8 * ((v45[2] - 1LL) & ((v44 - 1) >> 1))) + 8LL
                                                                                          * (((_DWORD)v44 - 1) & 1));
          if ( v6 >= *(_QWORD *)(v46 + 8) + *(unsigned int *)(v46 + 16) )
            goto LABEL_65;
          while ( 1 )
          {
            MkvReader::Read((_DWORD)this, v46, (unsigned int)&v55, (unsigned int)&v56, (__int64)&v57);
            v5 = v56;
            v6 = v55;
LABEL_65:
            if ( v5 <= 0 )
              break;
            if ( v44 == *((_QWORD *)this + 18) + *v37
              || (!v43 ? (v47 = 0) : (v47 = (_QWORD *)*v43),
                  v48 = v44 >> 1,
                  v49 = v44 & 1,
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v47[1] + 8 * ((v44 >> 1) & (v47[2] - 1LL))) + 8 * v49) + 8LL) > v6) )
            {
              v13 = -1072863856;
              goto LABEL_78;
            }
            ++v44;
            if ( v43 )
              v50 = (_QWORD *)*v43;
            else
              v50 = 0;
            v46 = *(_QWORD *)(*(_QWORD *)(v50[1] + 8 * (v48 & (v50[2] - 1LL))) + 8 * v49);
          }
          v13 = 0;
        }
        else
        {
          v33 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
            CallStackTracing::s_wpInstance = v34;
            if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
            {
              v33 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v33 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          v13 = -2147467261;
          if ( *((_BYTE *)v33 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "MkvReader::Read", 226, -2147467261);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids,
              this,
              -2147467261);
        }
LABEL_78:
        v15 = (CallStackScopeTrace *)v51;
        goto LABEL_79;
      }
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v55, "MkvReader::Read", 223);
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
      v13 = -1072875803;
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != -1072875803 )
          CallStackContext::TraceFailure(v29, "MkvReader::Read", 223, -1072875803);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids,
          this,
          -1072875803);
    }
    else
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v55, "MkvReader::Read", 213);
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      v13 = -1072875803;
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != -1072875803 )
          CallStackContext::TraceFailure(v22, "MkvReader::Read", 213, -1072875803);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids,
          this,
          -1072875803);
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v55, "MkvReader::Read", 208);
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v13 = -2147024809;
    if ( *((_BYTE *)v11 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v14 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v14, "MkvReader::Read", 208, -2147024809);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids,
        this,
        -2147024809);
  }
  v15 = (CallStackScopeTrace *)&v55;
LABEL_79:
  CallStackScopeTrace::~CallStackScopeTrace(v15);
  return v13;
}

```

## disassembly

```asm
0x180046650  mov     [rsp-38h+arg_18], r9
0x180046655  mov     [rsp-38h+arg_10], r8d
0x18004665a  mov     [rsp-38h+arg_8], rdx
0x18004665f  push    rbp
0x180046660  push    rbx
0x180046661  push    rsi
0x180046662  push    rdi
0x180046663  push    r12
0x180046665  push    r14
0x180046667  push    r15
0x180046669  mov     rbp, rsp
0x18004666c  sub     rsp, 80h
0x180046673  mov     rbx, r9
0x180046676  movsxd  r14, r8d
0x180046679  mov     rsi, rdx
0x18004667c  mov     rdi, rcx
0x18004667f  test    rdx, rdx
0x180046682  jns     loc_180046757
0x180046688  mov     esi, 0D0h
0x18004668d  mov     r8d, esi; int
0x180046690  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x180046697  lea     rcx, [rbp+arg_8]; this
0x18004669b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800466a0  nop
0x1800466a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800466a8  test    rcx, rcx
0x1800466ab  jnz     short loc_1800466F4
0x1800466ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800466b4  nop     dword ptr [rax+rax+00h]
0x1800466b9  mov     rcx, rax
0x1800466bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800466c3  test    rax, rax
0x1800466c6  jz      short loc_1800466E6
0x1800466c8  mov     rax, [rax]
0x1800466cb  mov     edx, 7F0h
0x1800466d0  mov     rax, [rax+8]
0x1800466d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466d9  test    eax, eax
0x1800466db  jz      short loc_1800466E6
0x1800466dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800466e4  jmp     short loc_1800466F4
0x1800466e6  lea     rcx, qword_1800DBF70; this
0x1800466ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800466f4  mov     ebx, 80070057h
0x1800466f9  cmp     byte ptr [rcx+8], 0
0x1800466fd  jz      short loc_180046721
0x1800466ff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046704  cmp     [rax+7CCh], ebx
0x18004670a  jz      short loc_180046721
0x18004670c  mov     r9d, ebx; int
0x18004670f  mov     r8d, esi; int
0x180046712  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x180046719  mov     rcx, rax; this
0x18004671c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046721  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180046728  jb      short loc_18004674E
0x18004672a  mov     edx, 12h
0x18004672f  mov     dword ptr [rsp+80h+var_60], ebx
0x180046733  mov     r9, rdi
0x180046736  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x18004673d  mov     rcx, cs:WPP_GLOBAL_Control
0x180046744  mov     rcx, [rcx+10h]
0x180046748  call    WPP_SF_qD
0x18004674d  nop
0x18004674e  lea     rcx, [rbp+arg_8]
0x180046752  jmp     loc_180046BA1
0x180046757  mov     rcx, [rcx+0C8h]
0x18004675e  test    rcx, rcx
0x180046761  js      loc_18004683B
0x180046767  cmp     rsi, rcx
0x18004676a  jle     loc_18004683B
0x180046770  mov     esi, 0D5h
0x180046775  mov     r8d, esi; int
0x180046778  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x18004677f  lea     rcx, [rbp+arg_8]; this
0x180046783  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180046788  nop
0x180046789  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046790  test    rcx, rcx
0x180046793  jnz     short loc_1800467DC
0x180046795  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004679c  nop     dword ptr [rax+rax+00h]
0x1800467a1  mov     rcx, rax
0x1800467a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800467ab  test    rax, rax
0x1800467ae  jz      short loc_1800467CE
0x1800467b0  mov     rax, [rax]
0x1800467b3  mov     edx, 7F0h
0x1800467b8  mov     rax, [rax+8]
0x1800467bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467c1  test    eax, eax
0x1800467c3  jz      short loc_1800467CE
0x1800467c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800467cc  jmp     short loc_1800467DC
0x1800467ce  lea     rcx, qword_1800DBF70; this
0x1800467d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800467dc  mov     ebx, 0C00D36E5h
0x1800467e1  cmp     byte ptr [rcx+8], 0
0x1800467e5  jz      short loc_180046809
0x1800467e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800467ec  cmp     [rax+7CCh], ebx
0x1800467f2  jz      short loc_180046809
0x1800467f4  mov     r9d, ebx; int
0x1800467f7  mov     r8d, esi; int
0x1800467fa  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x180046801  mov     rcx, rax; this
0x180046804  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046809  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180046810  jb      short loc_180046836
0x180046812  mov     edx, 13h
0x180046817  mov     dword ptr [rsp+80h+var_60], ebx
0x18004681b  mov     r9, rdi
0x18004681e  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180046825  mov     rcx, cs:WPP_GLOBAL_Control
0x18004682c  mov     rcx, [rcx+10h]
0x180046830  call    WPP_SF_qD
0x180046835  nop
0x180046836  jmp     loc_18004674E
0x18004683b  test    r8d, r8d
0x18004683e  jg      short loc_180046847
0x180046840  xor     eax, eax
0x180046842  jmp     loc_180046BA8
0x180046847  test    rcx, rcx
0x18004684a  js      loc_180046928
0x180046850  lea     rax, [rdx+r14]
0x180046854  cmp     rax, rcx
0x180046857  jle     loc_180046928
0x18004685d  mov     esi, 0DFh
0x180046862  mov     r8d, esi; int
0x180046865  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x18004686c  lea     rcx, [rbp+arg_8]; this
0x180046870  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180046875  nop
0x180046876  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004687d  test    rcx, rcx
0x180046880  jnz     short loc_1800468C9
0x180046882  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046889  nop     dword ptr [rax+rax+00h]
0x18004688e  mov     rcx, rax
0x180046891  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046898  test    rax, rax
0x18004689b  jz      short loc_1800468BB
0x18004689d  mov     rax, [rax]
0x1800468a0  mov     edx, 7F0h
0x1800468a5  mov     rax, [rax+8]
0x1800468a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468ae  test    eax, eax
0x1800468b0  jz      short loc_1800468BB
0x1800468b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800468b9  jmp     short loc_1800468C9
0x1800468bb  lea     rcx, qword_1800DBF70; this
0x1800468c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800468c9  mov     ebx, 0C00D36E5h
0x1800468ce  cmp     byte ptr [rcx+8], 0
0x1800468d2  jz      short loc_1800468F6
0x1800468d4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800468d9  cmp     [rax+7CCh], ebx
0x1800468df  jz      short loc_1800468F6
0x1800468e1  mov     r9d, ebx; int
0x1800468e4  mov     r8d, esi; int
0x1800468e7  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x1800468ee  mov     rcx, rax; this
0x1800468f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800468f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800468fd  jb      short loc_180046923
0x1800468ff  mov     edx, 14h
0x180046904  mov     dword ptr [rsp+80h+var_60], ebx
0x180046908  mov     r9, rdi
0x18004690b  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180046912  mov     rcx, cs:WPP_GLOBAL_Control
0x180046919  mov     rcx, [rcx+10h]
0x18004691d  call    WPP_SF_qD
0x180046922  nop
0x180046923  jmp     loc_18004674E
0x180046928  mov     r15d, 0E2h
0x18004692e  mov     r8d, r15d; int
0x180046931  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x180046938  lea     rcx, [rbp+var_50]; this
0x18004693c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180046941  nop
0x180046942  test    rbx, rbx
0x180046945  jnz     loc_180046A00
0x18004694b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046952  test    rcx, rcx
0x180046955  jnz     short loc_18004699E
0x180046957  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004695e  nop     dword ptr [rax+rax+00h]
0x180046963  mov     rcx, rax
0x180046966  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004696d  test    rax, rax
0x180046970  jz      short loc_180046990
0x180046972  mov     rax, [rax]
0x180046975  mov     edx, 7F0h
0x18004697a  mov     rax, [rax+8]
0x18004697e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046983  test    eax, eax
0x180046985  jz      short loc_180046990
0x180046987  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004698e  jmp     short loc_18004699E
0x180046990  lea     rcx, qword_1800DBF70; this
0x180046997  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004699e  mov     ebx, 80004003h
0x1800469a3  cmp     byte ptr [rcx+8], 0
0x1800469a7  jz      short loc_1800469CB
0x1800469a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800469ae  cmp     [rax+7CCh], ebx
0x1800469b4  jz      short loc_1800469CB
0x1800469b6  mov     r9d, ebx; int
0x1800469b9  mov     r8d, r15d; int
0x1800469bc  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x1800469c3  mov     rcx, rax; this
0x1800469c6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800469cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800469d2  jb      loc_180046B9D
0x1800469d8  mov     edx, 15h
0x1800469dd  mov     dword ptr [rsp+80h+var_60], ebx
0x1800469e1  mov     r9, rdi
0x1800469e4  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x1800469eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800469f2  mov     rcx, [rcx+10h]
0x1800469f6  call    WPP_SF_qD
0x1800469fb  jmp     loc_180046B9D
0x180046a00  mov     r8, [rdi+90h]
0x180046a07  test    r8, r8
0x180046a0a  jz      loc_180046AE0
0x180046a10  lea     r12, [rdi+88h]
0x180046a17  mov     r9, [r12]
0x180046a1b  mov     rdx, r9
0x180046a1e  shr     rdx, 1
0x180046a21  mov     rax, [rdi+80h]
0x180046a28  dec     rax
0x180046a2b  and     rdx, rax
0x180046a2e  mov     rax, [rdi+78h]
0x180046a32  mov     rcx, r9
0x180046a35  and     ecx, 1
0x180046a38  mov     rax, [rax+rdx*8]
0x180046a3c  mov     rcx, [rax+rcx*8]
0x180046a40  cmp     [rcx+8], rsi
0x180046a44  jg      loc_180046AE0
0x180046a4a  lea     rax, [rdi+70h]
0x180046a4e  test    rax, rax
0x180046a51  jz      short loc_180046A5B
0x180046a53  mov     rcx, [rax]
0x180046a56  mov     rdx, rcx
0x180046a59  jmp     short loc_180046A5F
0x180046a5b  xor     ecx, ecx
0x180046a5d  xor     edx, edx
0x180046a5f  lea     rax, [r9+r8]
0x180046a63  mov     [rbp+var_40], 0
0x180046a6b  mov     [rbp+var_48], rcx
0x180046a6f  mov     [rbp+var_38], rax
0x180046a73  mov     [rbp+var_28], 0
0x180046a7b  mov     [rbp+var_30], rdx
0x180046a7f  mov     [rbp+var_20], r9
0x180046a83  lea     r9, [rbp+arg_8]
0x180046a87  lea     r8, [rbp+var_48]
0x180046a8b  lea     rdx, [rbp+var_30]
0x180046a8f  lea     rcx, [rbp+var_18]
0x180046a93  call    ??$upper_bound@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@_JUPageLess@MkvReader@@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@0@V10@0AEB_JUPageLess@MkvReader@@@Z; std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64 const &,MkvReader::PageLess)
0x180046a98  mov     rbx, [rax]
0x180046a9b  mov     r15, [rax+10h]
0x180046a9f  lea     r8, [r15-1]
0x180046aa3  test    rbx, rbx
0x180046aa6  jz      short loc_180046AAD
0x180046aa8  mov     rdx, [rbx]
0x180046aab  jmp     short loc_180046AAF
0x180046aad  xor     edx, edx
0x180046aaf  mov     rcx, r8
0x180046ab2  shr     rcx, 1
0x180046ab5  mov     rax, [rdx+10h]
0x180046ab9  dec     rax
0x180046abc  and     rcx, rax
0x180046abf  mov     rdx, [rdx+8]
0x180046ac3  and     r8d, 1
0x180046ac7  mov     rdx, [rdx+rcx*8]
0x180046acb  mov     rdx, [rdx+r8*8]
0x180046acf  mov     eax, [rdx+10h]
0x180046ad2  add     rax, [rdx+8]
0x180046ad6  cmp     rsi, rax
0x180046ad9  jge     short loc_180046AF7
0x180046adb  jmp     loc_180046B6E
0x180046ae0  lea     rbx, [rdi+70h]
0x180046ae4  mov     r15, [rbx+18h]
0x180046ae8  test    rbx, rbx
0x180046aeb  jz      short loc_180046AF0
0x180046aed  mov     rbx, [rbx]
0x180046af0  lea     r12, [rdi+88h]
0x180046af7  test    r14d, r14d
0x180046afa  jle     loc_180046B9B
0x180046b00  mov     rax, [r12]
0x180046b04  add     rax, [rdi+90h]
0x180046b0b  cmp     r15, rax
0x180046b0e  jz      loc_180046B94
0x180046b14  test    rbx, rbx
0x180046b17  jz      short loc_180046B1E
0x180046b19  mov     rax, [rbx]
0x180046b1c  jmp     short loc_180046B20
0x180046b1e  xor     eax, eax
0x180046b20  mov     r8, r15
0x180046b23  shr     r8, 1
  ... truncated ...
```
