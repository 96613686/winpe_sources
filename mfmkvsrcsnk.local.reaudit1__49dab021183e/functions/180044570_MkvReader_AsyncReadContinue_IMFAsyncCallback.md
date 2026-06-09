# MkvReader::AsyncReadContinue(IMFAsyncCallback *)

- ea: `0x180044570`
- end: `0x180044b6b`
- name: `?AsyncReadContinue@MkvReader@@QEAAJPEAUIMFAsyncCallback@@@Z`
- size: `1531`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, struct IMFAsyncCallback *)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800159e8`
- `0x180044b74`

## callees

- `0x180002400`
- `0x180002e54`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180043d40`
- `0x180044570`
- `0x180044c20`
- `0x1800465d0`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004487f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044953`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044aa2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004487f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044953`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044aa2`

## string_xrefs

- `0x1800445b6`: `MkvReader::AsyncReadContinue`
- `0x1800448ea`: `MkvReader::AsyncReadContinue`
- `0x1800449bd`: `MkvReader::AsyncReadContinue`
- `0x180044b0c`: `MkvReader::AsyncReadContinue`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvReader::AsyncReadContinue(MkvReader *this, struct IMFAsyncCallback *a2)
{
  int *v3; // r11
  __int64 *v4; // r12
  __int64 v5; // r9
  unsigned int v6; // esi
  char *v7; // rbx
  unsigned __int64 v8; // r8
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  _QWORD *v13; // r15
  unsigned __int64 v14; // r13
  _QWORD *v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r14
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rbx
  int v21; // r9d
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rbx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  unsigned __int64 i; // rcx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  int v46; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v47[4]; // [rsp+34h] [rbp-CCh] BYREF
  char *v48; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v49; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v50; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v52; // [rsp+58h] [rbp-A8h]
  _QWORD *v53; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+68h] [rbp-98h]
  unsigned __int64 v55; // [rsp+70h] [rbp-90h]
  struct IMFAsyncCallback *v56; // [rsp+78h] [rbp-88h]
  MkvReader *v57; // [rsp+80h] [rbp-80h]
  int *v58; // [rsp+88h] [rbp-78h]
  _BYTE v59[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v60[1024]; // [rsp+B0h] [rbp-50h] BYREF

  v56 = a2;
  v46 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v47, "MkvReader::AsyncReadContinue", 828);
  v57 = this;
  v58 = &v46;
  v3 = (int *)((char *)this + 224);
  v4 = (__int64 *)((char *)this + 216);
  v5 = *((_QWORD *)this + 18);
  v6 = 1;
  if ( v5
    && (v7 = (char *)this + 136,
        v48 = (char *)this + 136,
        v8 = *((_QWORD *)this + 17),
        *v4 >= *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 15)
                                                 + 8 * ((*((_QWORD *)this + 16) - 1LL) & (v8 >> 1)))
                                     + 8 * (v8 & 1))
                         + 8LL)) )
  {
    v9 = (__int64 *)((char *)this + 112);
    if ( this == (MkvReader *)-112LL )
    {
      v10 = 0;
      v11 = 0;
    }
    else
    {
      v10 = *v9;
      v11 = *v9;
    }
    v51 = 0;
    v50 = v10;
    v52 = v8 + v5;
    v54 = 0;
    v53 = (_QWORD *)v11;
    v55 = v8;
    v12 = std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(
            v59,
            &v53,
            &v50,
            (char *)this + 216);
    v13 = *(_QWORD **)v12;
    v14 = *(_QWORD *)(v12 + 16);
    if ( *(_QWORD *)v12 )
      v15 = (_QWORD *)*v13;
    else
      v15 = 0;
    v16 = *(_QWORD *)(*(_QWORD *)(v15[1] + 8 * ((v15[2] - 1LL) & ((v14 - 1) >> 1))) + 8 * ((v14 - 1) & 1));
    v17 = *(_QWORD *)(v16 + 8) + *(unsigned int *)(v16 + 16);
    if ( *v4 < v17 )
      MkvReader::Read((_DWORD)this, v16, (_DWORD)this + 216, (_DWORD)this + 224, 0);
    v3 = (int *)((char *)this + 224);
    if ( v17 > *((_QWORD *)this + 26) )
    {
      *((_QWORD *)this + 26) = v17;
      goto LABEL_17;
    }
  }
  else
  {
    v17 = -1;
    v13 = (_QWORD *)((char *)this + 112);
    v14 = *((_QWORD *)this + 17);
    if ( this != (MkvReader *)-112LL )
      v13 = (_QWORD *)*v13;
    v7 = (char *)this + 136;
  }
  v48 = v7;
LABEL_17:
  while ( *v3 > 0 )
  {
    if ( v14 == *(_QWORD *)v7 + *((_QWORD *)this + 18)
      || (!v13 ? (v18 = 0) : (v18 = *v13),
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v18 + 8) + 8 * ((v14 >> 1) & (*(_QWORD *)(v18 + 16) - 1LL)))
                                + 8 * (v14 & 1))
                    + 8LL) > *v4) )
    {
      v51 = 0;
      v52 = 0;
      v50 = 0;
      v54 = 0;
      v53 = v13;
      v55 = v14;
      v22 = MkvReader::AsyncReadPage(this, (__int64 *)&v53, *v4, (__int64)v56, &v50);
      v46 = v22;
      if ( v22 < 0 )
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( v46 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v46 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "MkvReader::AsyncReadContinue", 885, v46);
        }
        if ( g_wppLevels )
        {
          v30 = 37;
          goto LABEL_60;
        }
        goto LABEL_61;
      }
      v13 = (_QWORD *)v50;
      if ( v50 )
        v26 = *(_QWORD *)v50;
      else
        v26 = 0;
      if ( v22 == 1 )
        goto LABEL_82;
      v14 = v52;
      v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v26 + 8) + 8 * ((*(_QWORD *)(v26 + 16) - 1LL) & (v52 >> 1)))
                      + 8 * (v52 & 1));
      v21 = (_DWORD)this + 224;
    }
    else
    {
      if ( v13 )
        v19 = *v13;
      else
        v19 = 0;
      v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v19 + 8) + 8 * ((v14 >> 1) & (*(_QWORD *)(v19 + 16) - 1LL)))
                      + 8 * (v14 & 1));
      v21 = (int)v3;
    }
    MkvReader::Read((_DWORD)this, v20, (_DWORD)this + 216, v21, 0);
    v17 = *(_QWORD *)(v20 + 8) + *(unsigned int *)(v20 + 16);
    ++v14;
    if ( v17 > *((_QWORD *)this + 26) )
      *((_QWORD *)this + 26) = v17;
    v7 = v48;
    v3 = (int *)((char *)this + 224);
  }
  *v4 = -1;
  *v3 = -1;
  v49 = 0;
  v46 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 2) + 48LL))(
          *((_QWORD *)this + 2),
          &v49);
  if ( v46 < 0 )
  {
    v34 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
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
      if ( v46 < 0 && *((_DWORD *)v36 + 499) != v46 )
        CallStackContext::TraceFailure(v36, "MkvReader::AsyncReadContinue", 938, v46);
    }
    if ( g_wppLevels )
    {
      v30 = 38;
LABEL_60:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids, this, v46);
    }
LABEL_61:
    v6 = v46;
    goto LABEL_82;
  }
  if ( v17 > v49
    && (*(int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 56LL))(*((_QWORD *)this + 2), v17) < 0 )
  {
    memset_0(v60, 0, sizeof(v60));
    for ( i = v49; i < v17; v49 = i )
    {
      LODWORD(v48) = 0;
      v38 = 1024;
      if ( v17 - i < 0x400 )
        v38 = v17 - i;
      v46 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64, char **))(**((_QWORD **)this + 2) + 72LL))(
              *((_QWORD *)this + 2),
              v60,
              v38,
              &v48);
      if ( v46 < 0 )
      {
        v42 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
          if ( v46 < 0 && *((_DWORD *)v44 + 499) != v46 )
            CallStackContext::TraceFailure(v44, "MkvReader::AsyncReadContinue", 951, v46);
        }
        if ( g_wppLevels )
        {
          v30 = 39;
          goto LABEL_60;
        }
        goto LABEL_61;
      }
      i = (unsigned int)v48 + v49;
    }
  }
  v6 = 0;
LABEL_82:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v47);
  return v6;
}

```

## disassembly

```asm
0x180044570  mov     [rsp-8+arg_10], rbx
0x180044575  push    rbp
0x180044576  push    rsi
0x180044577  push    rdi
0x180044578  push    r12
0x18004457a  push    r13
0x18004457c  push    r14
0x18004457e  push    r15
0x180044580  lea     rbp, [rsp-3C0h]
0x180044588  sub     rsp, 4C0h
0x18004458f  mov     rax, cs:__security_cookie
0x180044596  xor     rax, rsp
0x180044599  mov     [rbp+3F0h+var_40], rax
0x1800445a0  mov     [rsp+4F0h+var_478], rdx
0x1800445a5  mov     rdi, rcx
0x1800445a8  xor     r14d, r14d
0x1800445ab  mov     [rsp+4F0h+var_4C0], r14d
0x1800445b0  mov     r8d, 33Ch; int
0x1800445b6  lea     rdx, aMkvreaderAsync_2; "MkvReader::AsyncReadContinue"
0x1800445bd  lea     rcx, [rsp+4F0h+var_4BC]; this
0x1800445c2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800445c7  nop
0x1800445c8  mov     [rbp+3F0h+var_470], rdi
0x1800445cc  lea     rax, [rsp+4F0h+var_4C0]
0x1800445d1  mov     [rbp+3F0h+var_468], rax
0x1800445d5  lea     r11, [rdi+0E0h]
0x1800445dc  lea     r12, [rdi+0D8h]
0x1800445e3  mov     r9, [rdi+90h]
0x1800445ea  lea     esi, [r14+1]
0x1800445ee  test    r9, r9
0x1800445f1  jz      loc_180044701
0x1800445f7  lea     rbx, [rdi+88h]
0x1800445fe  mov     [rsp+4F0h+var_4B8], rbx
0x180044603  mov     r8, [rbx]
0x180044606  mov     r10, [r12]
0x18004460a  mov     rdx, r8
0x18004460d  shr     rdx, 1
0x180044610  mov     rax, [rdi+80h]
0x180044617  sub     rax, rsi
0x18004461a  and     rdx, rax
0x18004461d  mov     rax, [rdi+78h]
0x180044621  mov     rcx, r8
0x180044624  and     rcx, rsi
0x180044627  mov     rax, [rax+rdx*8]
0x18004462b  mov     rcx, [rax+rcx*8]
0x18004462f  cmp     r10, [rcx+8]
0x180044633  jl      loc_180044701
0x180044639  lea     rax, [rdi+70h]
0x18004463d  test    rax, rax
0x180044640  jz      short loc_18004464A
0x180044642  mov     rcx, [rax]
0x180044645  mov     rdx, rcx
0x180044648  jmp     short loc_180044650
0x18004464a  mov     rcx, r14
0x18004464d  mov     rdx, r14
0x180044650  lea     rax, [r8+r9]
0x180044654  mov     [rsp+4F0h+var_4A0], r14
0x180044659  mov     [rsp+4F0h+var_4A8], rcx
0x18004465e  mov     [rsp+4F0h+var_498], rax
0x180044663  mov     [rsp+4F0h+var_488], r14
0x180044668  mov     [rsp+4F0h+var_490], rdx
0x18004466d  mov     [rsp+4F0h+var_480], r8
0x180044672  mov     r9, r12
0x180044675  lea     r8, [rsp+4F0h+var_4A8]
0x18004467a  lea     rdx, [rsp+4F0h+var_490]
0x18004467f  lea     rcx, [rbp+3F0h+var_460]
0x180044683  call    ??$upper_bound@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@_JUPageLess@MkvReader@@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@0@V10@0AEB_JUPageLess@MkvReader@@@Z; std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64 const &,MkvReader::PageLess)
0x180044688  mov     r15, [rax]
0x18004468b  mov     r13, [rax+10h]
0x18004468f  lea     r8, [r13-1]
0x180044693  test    r15, r15
0x180044696  jz      short loc_18004469D
0x180044698  mov     rdx, [r15]
0x18004469b  jmp     short loc_1800446A0
0x18004469d  mov     rdx, r14
0x1800446a0  mov     rcx, r8
0x1800446a3  shr     rcx, 1
0x1800446a6  mov     rax, [rdx+10h]
0x1800446aa  sub     rax, rsi
0x1800446ad  and     rcx, rax
0x1800446b0  mov     rdx, [rdx+8]
0x1800446b4  and     r8, rsi
0x1800446b7  mov     rdx, [rdx+rcx*8]
0x1800446bb  mov     rdx, [rdx+r8*8]
0x1800446bf  mov     r14d, [rdx+10h]
0x1800446c3  add     r14, [rdx+8]
0x1800446c7  cmp     [r12], r14
0x1800446cb  jge     short loc_1800446E8
0x1800446cd  mov     [rsp+4F0h+var_4D0], 0
0x1800446d6  lea     r9, [rdi+0E0h]
0x1800446dd  mov     r8, r12
0x1800446e0  mov     rcx, rdi
0x1800446e3  call    ?Read@MkvReader@@AEBAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@AEA_JAEAJPEAPEAE@Z; MkvReader::Read(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,__int64 &,long &,uchar * *)
0x1800446e8  lea     r11, [rdi+0E0h]
0x1800446ef  cmp     r14, [rdi+0D0h]
0x1800446f6  jle     short loc_18004471C
0x1800446f8  mov     [rdi+0D0h], r14
0x1800446ff  jmp     short loc_180044721
0x180044701  or      r14, 0FFFFFFFFFFFFFFFFh
0x180044705  lea     r15, [rdi+70h]
0x180044709  mov     r13, [r15+18h]
0x18004470d  test    r15, r15
0x180044710  jz      short loc_180044715
0x180044712  mov     r15, [r15]
0x180044715  lea     rbx, [rdi+88h]
0x18004471c  mov     [rsp+4F0h+var_4B8], rbx
0x180044721  cmp     dword ptr [r11], 0
0x180044725  jle     loc_180044910
0x18004472b  mov     rax, [rdi+90h]
0x180044732  add     rax, [rbx]
0x180044735  xor     r14d, r14d
0x180044738  cmp     r13, rax
0x18004473b  jz      short loc_1800447A1
0x18004473d  test    r15, r15
0x180044740  jz      short loc_180044747
0x180044742  mov     rax, [r15]
0x180044745  jmp     short loc_18004474A
0x180044747  mov     rax, r14
0x18004474a  mov     r8, r13
0x18004474d  shr     r8, 1
0x180044750  mov     r9, r13
0x180044753  and     r9, rsi
0x180044756  mov     rcx, [rax+10h]
0x18004475a  sub     rcx, rsi
0x18004475d  and     rcx, r8
0x180044760  mov     rax, [rax+8]
0x180044764  mov     rcx, [rax+rcx*8]
0x180044768  mov     rdx, [rcx+r9*8]
0x18004476c  mov     rax, [r12]
0x180044770  cmp     [rdx+8], rax
0x180044774  jg      short loc_1800447A1
0x180044776  test    r15, r15
0x180044779  jz      short loc_180044780
0x18004477b  mov     rax, [r15]
0x18004477e  jmp     short loc_180044783
0x180044780  mov     rax, r14
0x180044783  mov     rbx, [rax+10h]
0x180044787  sub     rbx, rsi
0x18004478a  and     rbx, r8
0x18004478d  mov     rax, [rax+8]
0x180044791  mov     rbx, [rax+rbx*8]
0x180044795  mov     rbx, [rbx+r9*8]
0x180044799  mov     r9, r11
0x18004479c  jmp     loc_18004482F
0x1800447a1  mov     [rsp+4F0h+var_4A0], r14
0x1800447a6  mov     [rsp+4F0h+var_498], r14
0x1800447ab  mov     [rsp+4F0h+var_4A8], r14
0x1800447b0  mov     [rsp+4F0h+var_488], r14
0x1800447b5  mov     [rsp+4F0h+var_490], r15
0x1800447ba  mov     [rsp+4F0h+var_480], r13
0x1800447bf  lea     rax, [rsp+4F0h+var_4A8]
0x1800447c4  mov     [rsp+4F0h+var_4D0], rax; __int64
0x1800447c9  mov     r9, [rsp+4F0h+var_478]
0x1800447ce  mov     r8, [r12]
0x1800447d2  lea     rdx, [rsp+4F0h+var_490]
0x1800447d7  mov     rcx, rdi; this
0x1800447da  call    ?AsyncReadPage@MkvReader@@AEAAJV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@_JPEAUIMFAsyncCallback@@AEAV23@@Z; MkvReader::AsyncReadPage(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,IMFAsyncCallback *,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>> &)
0x1800447df  mov     [rsp+4F0h+var_4C0], eax
0x1800447e3  test    eax, eax
0x1800447e5  js      loc_180044873
0x1800447eb  mov     r15, [rsp+4F0h+var_4A8]
0x1800447f0  test    r15, r15
0x1800447f3  jz      short loc_1800447FA
0x1800447f5  mov     rbx, [r15]
0x1800447f8  jmp     short loc_1800447FD
0x1800447fa  mov     rbx, r14
0x1800447fd  cmp     eax, esi
0x1800447ff  jz      short loc_18004486E
0x180044801  mov     r13, [rsp+4F0h+var_498]
0x180044806  mov     rcx, r13
0x180044809  shr     rcx, 1
0x18004480c  mov     rax, [rbx+10h]
0x180044810  sub     rax, rsi
0x180044813  and     rcx, rax
0x180044816  mov     rbx, [rbx+8]
0x18004481a  mov     rax, r13
0x18004481d  and     rax, rsi
0x180044820  mov     rbx, [rbx+rcx*8]
0x180044824  mov     rbx, [rbx+rax*8]
0x180044828  lea     r9, [rdi+0E0h]
0x18004482f  mov     [rsp+4F0h+var_4D0], r14
0x180044834  mov     r8, r12
0x180044837  mov     rdx, rbx
0x18004483a  mov     rcx, rdi
0x18004483d  call    ?Read@MkvReader@@AEBAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@AEA_JAEAJPEAPEAE@Z; MkvReader::Read(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,__int64 &,long &,uchar * *)
0x180044842  mov     r14d, [rbx+10h]
0x180044846  add     r14, [rbx+8]
0x18004484a  inc     r13
0x18004484d  cmp     r14, [rdi+0D0h]
0x180044854  jle     short loc_18004485D
0x180044856  mov     [rdi+0D0h], r14
0x18004485d  mov     rbx, [rsp+4F0h+var_4B8]
0x180044862  lea     r11, [rdi+0E0h]
0x180044869  jmp     loc_180044721
0x18004486e  jmp     loc_180044B34
0x180044873  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004487a  test    rcx, rcx
0x18004487d  jnz     short loc_1800448C6
0x18004487f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044886  nop     dword ptr [rax+rax+00h]
0x18004488b  mov     rcx, rax
0x18004488e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044895  test    rax, rax
0x180044898  jz      short loc_1800448B8
0x18004489a  mov     rax, [rax]
0x18004489d  mov     edx, 7F0h
0x1800448a2  mov     rax, [rax+8]
0x1800448a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448ab  test    eax, eax
0x1800448ad  jz      short loc_1800448B8
0x1800448af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800448b6  jmp     short loc_1800448C6
0x1800448b8  lea     rcx, qword_1800DBF70; this
0x1800448bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800448c6  cmp     [rcx+8], r14b
0x1800448ca  jz      short loc_1800448F9
0x1800448cc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800448d1  mov     r9d, [rsp+4F0h+var_4C0]; int
0x1800448d6  test    r9d, r9d
0x1800448d9  jns     short loc_1800448F9
0x1800448db  cmp     [rax+7CCh], r9d
0x1800448e2  jz      short loc_1800448F9
0x1800448e4  mov     r8d, 375h; int
0x1800448ea  lea     rdx, aMkvreaderAsync_2; "MkvReader::AsyncReadContinue"
0x1800448f1  mov     rcx, rax; this
0x1800448f4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800448f9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180044900  jb      loc_1800449FD
0x180044906  mov     edx, 25h ; '%'
0x18004490b  jmp     loc_1800449DA
0x180044910  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180044918  mov     dword ptr [r11], 0FFFFFFFFh
0x18004491f  xor     ebx, ebx
0x180044921  mov     [rsp+4F0h+var_4B0], rbx
0x180044926  mov     rcx, [rdi+10h]
0x18004492a  mov     rax, [rcx]
0x18004492d  lea     rdx, [rsp+4F0h+var_4B0]
0x180044932  mov     rax, [rax+30h]
0x180044936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004493b  mov     [rsp+4F0h+var_4C0], eax
0x18004493f  test    eax, eax
0x180044941  jns     loc_180044A06
0x180044947  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004494e  test    rcx, rcx
0x180044951  jnz     short loc_18004499A
0x180044953  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004495a  nop     dword ptr [rax+rax+00h]
0x18004495f  mov     rcx, rax
0x180044962  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044969  test    rax, rax
0x18004496c  jz      short loc_18004498C
0x18004496e  mov     rax, [rax]
0x180044971  mov     edx, 7F0h
0x180044976  mov     rax, [rax+8]
0x18004497a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004497f  test    eax, eax
0x180044981  jz      short loc_18004498C
0x180044983  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004498a  jmp     short loc_18004499A
0x18004498c  lea     rcx, qword_1800DBF70; this
0x180044993  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004499a  cmp     [rcx+8], bl
0x18004499d  jz      short loc_1800449CC
0x18004499f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800449a4  mov     r9d, [rsp+4F0h+var_4C0]; int
0x1800449a9  test    r9d, r9d
0x1800449ac  jns     short loc_1800449CC
0x1800449ae  cmp     [rax+7CCh], r9d
0x1800449b5  jz      short loc_1800449CC
0x1800449b7  mov     r8d, 3AAh; int
0x1800449bd  lea     rdx, aMkvreaderAsync_2; "MkvReader::AsyncReadContinue"
0x1800449c4  mov     rcx, rax; this
0x1800449c7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800449cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800449d3  jb      short loc_1800449FD
0x1800449d5  mov     edx, 26h ; '&'
0x1800449da  mov     eax, [rsp+4F0h+var_4C0]
0x1800449de  mov     dword ptr [rsp+4F0h+var_4D0], eax
0x1800449e2  mov     r9, rdi
0x1800449e5  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x1800449ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800449f3  mov     rcx, [rcx+10h]
0x1800449f7  call    WPP_SF_qD
0x1800449fc  nop
0x1800449fd  mov     esi, [rsp+4F0h+var_4C0]
0x180044a01  jmp     loc_180044B34
0x180044a06  cmp     r14, [rsp+4F0h+var_4B0]
0x180044a0b  jbe     loc_180044B32
0x180044a11  mov     rcx, [rdi+10h]
0x180044a15  mov     rax, [rcx]
0x180044a18  mov     rdx, r14
0x180044a1b  mov     rax, [rax+38h]
0x180044a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a24  test    eax, eax
0x180044a26  jns     loc_180044B32
0x180044a2c  mov     r15d, 400h
0x180044a32  mov     r8d, r15d; Size
0x180044a35  xor     edx, edx; Val
0x180044a37  lea     rcx, [rbp+3F0h+var_440]; void *
0x180044a3b  call    memset_0
  ... truncated ...
```
