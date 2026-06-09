# MkvReader::Read(__int64,long,uchar *)

- ea: `0x180044800`
- end: `0x180044d52`
- name: `?Read@MkvReader@@UEAAJ_JJPEAE@Z`
- size: `1362`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, __int64, int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180041fb0`
- `0x180044780`
- `0x180044800`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004485d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004493f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044a26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044af5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004485d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004493f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044a26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044af5`

## string_xrefs

- `0x180044840`: `MkvReader::Read`
- `0x1800448bc`: `MkvReader::Read`
- `0x180044922`: `MkvReader::Read`
- `0x18004499e`: `MkvReader::Read`
- `0x180044a09`: `MkvReader::Read`
- `0x180044a85`: `MkvReader::Read`
- `0x180044acf`: `MkvReader::Read`
- `0x180044b54`: `MkvReader::Read`

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
  __int64 *v38; // r9
  __int64 **v39; // rax
  __int64 *v40; // rcx
  __int64 *v41; // rdx
  __int64 **v42; // rax
  __int64 *v43; // rbx
  __int64 *v44; // r15
  __int64 *v45; // rdx
  __int64 v46; // rdx
  __int64 *v47; // rax
  unsigned __int64 v48; // r8
  __int64 v49; // r10
  __int64 *v50; // rax
  char v51[8]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v52[3]; // [rsp+38h] [rbp-48h] BYREF
  __int64 *v53[3]; // [rsp+50h] [rbp-30h] BYREF
  __int64 *v54; // [rsp+68h] [rbp-18h] BYREF
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
                v38 = (__int64 *)*((_QWORD *)this + 17),
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 15)
                                                  + 8 * ((*((_QWORD *)this + 16) - 1LL) & ((unsigned __int64)v38 >> 1)))
                                      + 8LL * ((unsigned __int8)v38 & 1))
                          + 8LL) > v6) )
          {
            v43 = (__int64 *)((char *)this + 112);
            v44 = (__int64 *)*((_QWORD *)this + 17);
            if ( this != (MkvReader *)-112LL )
              v43 = (__int64 *)*v43;
            v37 = (_QWORD *)((char *)this + 136);
            goto LABEL_65;
          }
          v39 = (__int64 **)((char *)this + 112);
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
          v52[2] = (char *)v38 + v36;
          v53[1] = 0;
          v53[0] = v41;
          v53[2] = v38;
          v42 = std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(
                  &v54,
                  v53,
                  (__int64)v52,
                  &v55);
          v43 = *v42;
          v44 = v42[2];
          if ( *v42 )
            v45 = (__int64 *)*v43;
          else
            v45 = 0;
          v46 = *(_QWORD *)(*(_QWORD *)(v45[1] + 8 * ((v45[2] - 1) & (((unsigned __int64)v44 - 1) >> 1)))
                          + 8LL * (((_DWORD)v44 - 1) & 1));
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
            if ( v44 == (__int64 *)(*((_QWORD *)this + 18) + *v37)
              || (!v43 ? (v47 = 0) : (v47 = (__int64 *)*v43),
                  v48 = (unsigned __int64)v44 >> 1,
                  v49 = (unsigned __int8)v44 & 1,
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v47[1] + 8 * (((unsigned __int64)v44 >> 1) & (v47[2] - 1)))
                                        + 8 * v49)
                            + 8LL) > v6) )
            {
              v13 = -1072863856;
              goto LABEL_78;
            }
            v44 = (__int64 *)((char *)v44 + 1);
            if ( v43 )
              v50 = (__int64 *)*v43;
            else
              v50 = 0;
            v46 = *(_QWORD *)(*(_QWORD *)(v50[1] + 8 * (v48 & (v50[2] - 1))) + 8 * v49);
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
              v33 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v27 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v20 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180044800  mov     [rsp-38h+arg_18], r9
0x180044805  mov     [rsp-38h+arg_10], r8d
0x18004480a  mov     [rsp-38h+arg_8], rdx
0x18004480f  push    rbp
0x180044810  push    rbx
0x180044811  push    rsi
0x180044812  push    rdi
0x180044813  push    r12
0x180044815  push    r14
0x180044817  push    r15
0x180044819  mov     rbp, rsp
0x18004481c  sub     rsp, 80h
0x180044823  mov     rbx, r9
0x180044826  movsxd  r14, r8d
0x180044829  mov     rsi, rdx
0x18004482c  mov     rdi, rcx
0x18004482f  test    rdx, rdx
0x180044832  jns     loc_180044901
0x180044838  mov     esi, 0D0h
0x18004483d  mov     r8d, esi; int
0x180044840  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x180044847  lea     rcx, [rbp+arg_8]; this
0x18004484b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180044850  nop
0x180044851  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044858  test    rcx, rcx
0x18004485b  jnz     short loc_18004489E
0x18004485d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044863  mov     rcx, rax
0x180044866  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004486d  test    rax, rax
0x180044870  jz      short loc_180044890
0x180044872  mov     rax, [rax]
0x180044875  mov     edx, 7F0h
0x18004487a  mov     rax, [rax+8]
0x18004487e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044883  test    eax, eax
0x180044885  jz      short loc_180044890
0x180044887  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004488e  jmp     short loc_18004489E
0x180044890  lea     rcx, qword_1800D6F70; this
0x180044897  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004489e  mov     ebx, 80070057h
0x1800448a3  cmp     byte ptr [rcx+8], 0
0x1800448a7  jz      short loc_1800448CB
0x1800448a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800448ae  cmp     [rax+7CCh], ebx
0x1800448b4  jz      short loc_1800448CB
0x1800448b6  mov     r9d, ebx; int
0x1800448b9  mov     r8d, esi; int
0x1800448bc  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x1800448c3  mov     rcx, rax; this
0x1800448c6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800448cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800448d2  jb      short loc_1800448F8
0x1800448d4  mov     edx, 12h
0x1800448d9  mov     dword ptr [rsp+80h+var_60], ebx
0x1800448dd  mov     r9, rdi
0x1800448e0  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x1800448e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800448ee  mov     rcx, [rcx+10h]
0x1800448f2  call    WPP_SF_qD
0x1800448f7  nop
0x1800448f8  lea     rcx, [rbp+arg_8]
0x1800448fc  jmp     loc_180044D39
0x180044901  mov     rcx, [rcx+0C8h]
0x180044908  test    rcx, rcx
0x18004490b  js      loc_1800449DF
0x180044911  cmp     rsi, rcx
0x180044914  jle     loc_1800449DF
0x18004491a  mov     esi, 0D5h
0x18004491f  mov     r8d, esi; int
0x180044922  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x180044929  lea     rcx, [rbp+arg_8]; this
0x18004492d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180044932  nop
0x180044933  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004493a  test    rcx, rcx
0x18004493d  jnz     short loc_180044980
0x18004493f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044945  mov     rcx, rax
0x180044948  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004494f  test    rax, rax
0x180044952  jz      short loc_180044972
0x180044954  mov     rax, [rax]
0x180044957  mov     edx, 7F0h
0x18004495c  mov     rax, [rax+8]
0x180044960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044965  test    eax, eax
0x180044967  jz      short loc_180044972
0x180044969  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044970  jmp     short loc_180044980
0x180044972  lea     rcx, qword_1800D6F70; this
0x180044979  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044980  mov     ebx, 0C00D36E5h
0x180044985  cmp     byte ptr [rcx+8], 0
0x180044989  jz      short loc_1800449AD
0x18004498b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044990  cmp     [rax+7CCh], ebx
0x180044996  jz      short loc_1800449AD
0x180044998  mov     r9d, ebx; int
0x18004499b  mov     r8d, esi; int
0x18004499e  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x1800449a5  mov     rcx, rax; this
0x1800449a8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800449ad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800449b4  jb      short loc_1800449DA
0x1800449b6  mov     edx, 13h
0x1800449bb  mov     dword ptr [rsp+80h+var_60], ebx
0x1800449bf  mov     r9, rdi
0x1800449c2  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x1800449c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800449d0  mov     rcx, [rcx+10h]
0x1800449d4  call    WPP_SF_qD
0x1800449d9  nop
0x1800449da  jmp     loc_1800448F8
0x1800449df  test    r8d, r8d
0x1800449e2  jg      short loc_1800449EB
0x1800449e4  xor     eax, eax
0x1800449e6  jmp     loc_180044D40
0x1800449eb  test    rcx, rcx
0x1800449ee  js      loc_180044AC6
0x1800449f4  lea     rax, [rdx+r14]
0x1800449f8  cmp     rax, rcx
0x1800449fb  jle     loc_180044AC6
0x180044a01  mov     esi, 0DFh
0x180044a06  mov     r8d, esi; int
0x180044a09  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x180044a10  lea     rcx, [rbp+arg_8]; this
0x180044a14  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180044a19  nop
0x180044a1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044a21  test    rcx, rcx
0x180044a24  jnz     short loc_180044A67
0x180044a26  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044a2c  mov     rcx, rax
0x180044a2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044a36  test    rax, rax
0x180044a39  jz      short loc_180044A59
0x180044a3b  mov     rax, [rax]
0x180044a3e  mov     edx, 7F0h
0x180044a43  mov     rax, [rax+8]
0x180044a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a4c  test    eax, eax
0x180044a4e  jz      short loc_180044A59
0x180044a50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044a57  jmp     short loc_180044A67
0x180044a59  lea     rcx, qword_1800D6F70; this
0x180044a60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044a67  mov     ebx, 0C00D36E5h
0x180044a6c  cmp     byte ptr [rcx+8], 0
0x180044a70  jz      short loc_180044A94
0x180044a72  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044a77  cmp     [rax+7CCh], ebx
0x180044a7d  jz      short loc_180044A94
0x180044a7f  mov     r9d, ebx; int
0x180044a82  mov     r8d, esi; int
0x180044a85  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x180044a8c  mov     rcx, rax; this
0x180044a8f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044a94  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044a9b  jb      short loc_180044AC1
0x180044a9d  mov     edx, 14h
0x180044aa2  mov     dword ptr [rsp+80h+var_60], ebx
0x180044aa6  mov     r9, rdi
0x180044aa9  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180044ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x180044ab7  mov     rcx, [rcx+10h]
0x180044abb  call    WPP_SF_qD
0x180044ac0  nop
0x180044ac1  jmp     loc_1800448F8
0x180044ac6  mov     r15d, 0E2h
0x180044acc  mov     r8d, r15d; int
0x180044acf  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x180044ad6  lea     rcx, [rbp+var_50]; this
0x180044ada  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180044adf  nop
0x180044ae0  test    rbx, rbx
0x180044ae3  jnz     loc_180044B98
0x180044ae9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044af0  test    rcx, rcx
0x180044af3  jnz     short loc_180044B36
0x180044af5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044afb  mov     rcx, rax
0x180044afe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044b05  test    rax, rax
0x180044b08  jz      short loc_180044B28
0x180044b0a  mov     rax, [rax]
0x180044b0d  mov     edx, 7F0h
0x180044b12  mov     rax, [rax+8]
0x180044b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b1b  test    eax, eax
0x180044b1d  jz      short loc_180044B28
0x180044b1f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044b26  jmp     short loc_180044B36
0x180044b28  lea     rcx, qword_1800D6F70; this
0x180044b2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044b36  mov     ebx, 80004003h
0x180044b3b  cmp     byte ptr [rcx+8], 0
0x180044b3f  jz      short loc_180044B63
0x180044b41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044b46  cmp     [rax+7CCh], ebx
0x180044b4c  jz      short loc_180044B63
0x180044b4e  mov     r9d, ebx; int
0x180044b51  mov     r8d, r15d; int
0x180044b54  lea     rdx, aMkvreaderRead; "MkvReader::Read"
0x180044b5b  mov     rcx, rax; this
0x180044b5e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044b63  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044b6a  jb      loc_180044D35
0x180044b70  mov     edx, 15h
0x180044b75  mov     dword ptr [rsp+80h+var_60], ebx
0x180044b79  mov     r9, rdi
0x180044b7c  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180044b83  mov     rcx, cs:WPP_GLOBAL_Control
0x180044b8a  mov     rcx, [rcx+10h]
0x180044b8e  call    WPP_SF_qD
0x180044b93  jmp     loc_180044D35
0x180044b98  mov     r8, [rdi+90h]
0x180044b9f  test    r8, r8
0x180044ba2  jz      loc_180044C78
0x180044ba8  lea     r12, [rdi+88h]
0x180044baf  mov     r9, [r12]
0x180044bb3  mov     rdx, r9
0x180044bb6  shr     rdx, 1
0x180044bb9  mov     rax, [rdi+80h]
0x180044bc0  dec     rax
0x180044bc3  and     rdx, rax
0x180044bc6  mov     rax, [rdi+78h]
0x180044bca  mov     rcx, r9
0x180044bcd  and     ecx, 1
0x180044bd0  mov     rax, [rax+rdx*8]
0x180044bd4  mov     rcx, [rax+rcx*8]
0x180044bd8  cmp     [rcx+8], rsi
0x180044bdc  jg      loc_180044C78
0x180044be2  lea     rax, [rdi+70h]
0x180044be6  test    rax, rax
0x180044be9  jz      short loc_180044BF3
0x180044beb  mov     rcx, [rax]
0x180044bee  mov     rdx, rcx
0x180044bf1  jmp     short loc_180044BF7
0x180044bf3  xor     ecx, ecx
0x180044bf5  xor     edx, edx
0x180044bf7  lea     rax, [r9+r8]
0x180044bfb  mov     [rbp+var_40], 0
0x180044c03  mov     [rbp+var_48], rcx
0x180044c07  mov     [rbp+var_38], rax
0x180044c0b  mov     [rbp+var_28], 0
0x180044c13  mov     [rbp+var_30], rdx
0x180044c17  mov     [rbp+var_20], r9
0x180044c1b  lea     r9, [rbp+arg_8]
0x180044c1f  lea     r8, [rbp+var_48]
0x180044c23  lea     rdx, [rbp+var_30]
0x180044c27  lea     rcx, [rbp+var_18]
0x180044c2b  call    ??$upper_bound@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@_JUPageLess@MkvReader@@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@0@V10@0AEB_JUPageLess@MkvReader@@@Z; std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64 const &,MkvReader::PageLess)
0x180044c30  mov     rbx, [rax]
0x180044c33  mov     r15, [rax+10h]
0x180044c37  lea     r8, [r15-1]
0x180044c3b  test    rbx, rbx
0x180044c3e  jz      short loc_180044C45
0x180044c40  mov     rdx, [rbx]
0x180044c43  jmp     short loc_180044C47
0x180044c45  xor     edx, edx
0x180044c47  mov     rcx, r8
0x180044c4a  shr     rcx, 1
0x180044c4d  mov     rax, [rdx+10h]
0x180044c51  dec     rax
0x180044c54  and     rcx, rax
0x180044c57  mov     rdx, [rdx+8]
0x180044c5b  and     r8d, 1
0x180044c5f  mov     rdx, [rdx+rcx*8]
0x180044c63  mov     rdx, [rdx+r8*8]
0x180044c67  mov     eax, [rdx+10h]
0x180044c6a  add     rax, [rdx+8]
0x180044c6e  cmp     rsi, rax
0x180044c71  jge     short loc_180044C8F
0x180044c73  jmp     loc_180044D06
0x180044c78  lea     rbx, [rdi+70h]
0x180044c7c  mov     r15, [rbx+18h]
0x180044c80  test    rbx, rbx
0x180044c83  jz      short loc_180044C88
0x180044c85  mov     rbx, [rbx]
0x180044c88  lea     r12, [rdi+88h]
0x180044c8f  test    r14d, r14d
0x180044c92  jle     loc_180044D33
0x180044c98  mov     rax, [r12]
0x180044c9c  add     rax, [rdi+90h]
0x180044ca3  cmp     r15, rax
0x180044ca6  jz      loc_180044D2C
0x180044cac  test    rbx, rbx
0x180044caf  jz      short loc_180044CB6
0x180044cb1  mov     rax, [rbx]
0x180044cb4  jmp     short loc_180044CB8
0x180044cb6  xor     eax, eax
0x180044cb8  mov     r8, r15
0x180044cbb  shr     r8, 1
0x180044cbe  mov     r10, r15
0x180044cc1  and     r10d, 1
0x180044cc5  mov     rcx, [rax+10h]
0x180044cc9  dec     rcx
  ... truncated ...
```
