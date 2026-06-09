# MkvReader::AsyncReadContinue(IMFAsyncCallback *)

- ea: `0x1800427c4`
- end: `0x180042dac`
- name: `?AsyncReadContinue@MkvReader@@QEAAJPEAUIMFAsyncCallback@@@Z`
- size: `1512`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, struct IMFAsyncCallback *)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180014ff0`
- `0x180042db4`

## callees

- `0x1800023e0`
- `0x180002e14`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180041fb0`
- `0x1800427c4`
- `0x180042e5c`
- `0x180044780`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042ad3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042ba1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042cea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042ad3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042ba1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042cea`

## string_xrefs

- `0x18004280a`: `MkvReader::AsyncReadContinue`
- `0x180042b38`: `MkvReader::AsyncReadContinue`
- `0x180042c05`: `MkvReader::AsyncReadContinue`
- `0x180042d4e`: `MkvReader::AsyncReadContinue`

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
  __int64 *v8; // r8
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rdx
  __int64 **v12; // rax
  __int64 *v13; // r15
  __int64 *v14; // r13
  __int64 v15; // rdx
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
  __int64 *v52; // [rsp+58h] [rbp-A8h]
  __int64 *v53; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+68h] [rbp-98h]
  __int64 *v55; // [rsp+70h] [rbp-90h]
  struct IMFAsyncCallback *v56; // [rsp+78h] [rbp-88h]
  MkvReader *v57; // [rsp+80h] [rbp-80h]
  int *v58; // [rsp+88h] [rbp-78h]
  __int64 *v59; // [rsp+90h] [rbp-70h] BYREF
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
        v8 = (__int64 *)*((_QWORD *)this + 17),
        *v4 >= *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 15)
                                                 + 8 * ((*((_QWORD *)this + 16) - 1LL) & ((unsigned __int64)v8 >> 1)))
                                     + 8LL * ((unsigned __int8)v8 & 1))
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
      v11 = (__int64 *)*v9;
    }
    v51 = 0;
    v50 = v10;
    v52 = (__int64 *)((char *)v8 + v5);
    v54 = 0;
    v53 = v11;
    v55 = v8;
    v12 = std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(
            &v59,
            &v53,
            (__int64)&v50,
            (_QWORD *)this + 27);
    v13 = *v12;
    v14 = v12[2];
    if ( *v12 )
      v15 = *v13;
    else
      v15 = 0;
    v16 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 8)
                                + 8 * ((*(_QWORD *)(v15 + 16) - 1LL) & (((unsigned __int64)v14 - 1) >> 1)))
                    + 8 * (((unsigned __int64)v14 - 1) & 1));
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
    v13 = (__int64 *)((char *)this + 112);
    v14 = (__int64 *)*((_QWORD *)this + 17);
    if ( this != (MkvReader *)-112LL )
      v13 = (__int64 *)*v13;
    v7 = (char *)this + 136;
  }
  v48 = v7;
LABEL_17:
  while ( *v3 > 0 )
  {
    if ( v14 == (__int64 *)(*(_QWORD *)v7 + *((_QWORD *)this + 18))
      || (!v13 ? (v18 = 0) : (v18 = *v13),
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v18 + 8)
                                            + 8 * (((unsigned __int64)v14 >> 1) & (*(_QWORD *)(v18 + 16) - 1LL)))
                                + 8LL * ((unsigned __int8)v14 & 1))
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
            v27 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v13 = (__int64 *)v50;
      if ( v50 )
        v26 = *(_QWORD *)v50;
      else
        v26 = 0;
      if ( v22 == 1 )
        goto LABEL_82;
      v14 = v52;
      v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v26 + 8)
                                  + 8 * ((*(_QWORD *)(v26 + 16) - 1LL) & ((unsigned __int64)v52 >> 1)))
                      + 8LL * ((unsigned __int8)v52 & 1));
      v21 = (_DWORD)this + 224;
    }
    else
    {
      if ( v13 )
        v19 = *v13;
      else
        v19 = 0;
      v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v19 + 8)
                                  + 8 * (((unsigned __int64)v14 >> 1) & (*(_QWORD *)(v19 + 16) - 1LL)))
                      + 8LL * ((unsigned __int8)v14 & 1));
      v21 = (int)v3;
    }
    MkvReader::Read((_DWORD)this, v20, (_DWORD)this + 216, v21, 0);
    v17 = *(_QWORD *)(v20 + 8) + *(unsigned int *)(v20 + 16);
    v14 = (__int64 *)((char *)v14 + 1);
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
        v34 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v42 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x1800427c4  mov     [rsp-8+arg_10], rbx
0x1800427c9  push    rbp
0x1800427ca  push    rsi
0x1800427cb  push    rdi
0x1800427cc  push    r12
0x1800427ce  push    r13
0x1800427d0  push    r14
0x1800427d2  push    r15
0x1800427d4  lea     rbp, [rsp-3C0h]
0x1800427dc  sub     rsp, 4C0h
0x1800427e3  mov     rax, cs:__security_cookie
0x1800427ea  xor     rax, rsp
0x1800427ed  mov     [rbp+3F0h+var_40], rax
0x1800427f4  mov     [rsp+4F0h+var_478], rdx
0x1800427f9  mov     rdi, rcx
0x1800427fc  xor     r14d, r14d
0x1800427ff  mov     [rsp+4F0h+var_4C0], r14d
0x180042804  mov     r8d, 33Ch; int
0x18004280a  lea     rdx, aMkvreaderAsync_2; "MkvReader::AsyncReadContinue"
0x180042811  lea     rcx, [rsp+4F0h+var_4BC]; this
0x180042816  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004281b  nop
0x18004281c  mov     [rbp+3F0h+var_470], rdi
0x180042820  lea     rax, [rsp+4F0h+var_4C0]
0x180042825  mov     [rbp+3F0h+var_468], rax
0x180042829  lea     r11, [rdi+0E0h]
0x180042830  lea     r12, [rdi+0D8h]
0x180042837  mov     r9, [rdi+90h]
0x18004283e  lea     esi, [r14+1]
0x180042842  test    r9, r9
0x180042845  jz      loc_180042955
0x18004284b  lea     rbx, [rdi+88h]
0x180042852  mov     [rsp+4F0h+var_4B8], rbx
0x180042857  mov     r8, [rbx]
0x18004285a  mov     r10, [r12]
0x18004285e  mov     rdx, r8
0x180042861  shr     rdx, 1
0x180042864  mov     rax, [rdi+80h]
0x18004286b  sub     rax, rsi
0x18004286e  and     rdx, rax
0x180042871  mov     rax, [rdi+78h]
0x180042875  mov     rcx, r8
0x180042878  and     rcx, rsi
0x18004287b  mov     rax, [rax+rdx*8]
0x18004287f  mov     rcx, [rax+rcx*8]
0x180042883  cmp     r10, [rcx+8]
0x180042887  jl      loc_180042955
0x18004288d  lea     rax, [rdi+70h]
0x180042891  test    rax, rax
0x180042894  jz      short loc_18004289E
0x180042896  mov     rcx, [rax]
0x180042899  mov     rdx, rcx
0x18004289c  jmp     short loc_1800428A4
0x18004289e  mov     rcx, r14
0x1800428a1  mov     rdx, r14
0x1800428a4  lea     rax, [r8+r9]
0x1800428a8  mov     [rsp+4F0h+var_4A0], r14
0x1800428ad  mov     [rsp+4F0h+var_4A8], rcx
0x1800428b2  mov     [rsp+4F0h+var_498], rax
0x1800428b7  mov     [rsp+4F0h+var_488], r14
0x1800428bc  mov     [rsp+4F0h+var_490], rdx
0x1800428c1  mov     [rsp+4F0h+var_480], r8
0x1800428c6  mov     r9, r12
0x1800428c9  lea     r8, [rsp+4F0h+var_4A8]
0x1800428ce  lea     rdx, [rsp+4F0h+var_490]
0x1800428d3  lea     rcx, [rbp+3F0h+var_460]
0x1800428d7  call    ??$upper_bound@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@_JUPageLess@MkvReader@@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@0@V10@0AEB_JUPageLess@MkvReader@@@Z; std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64 const &,MkvReader::PageLess)
0x1800428dc  mov     r15, [rax]
0x1800428df  mov     r13, [rax+10h]
0x1800428e3  lea     r8, [r13-1]
0x1800428e7  test    r15, r15
0x1800428ea  jz      short loc_1800428F1
0x1800428ec  mov     rdx, [r15]
0x1800428ef  jmp     short loc_1800428F4
0x1800428f1  mov     rdx, r14
0x1800428f4  mov     rcx, r8
0x1800428f7  shr     rcx, 1
0x1800428fa  mov     rax, [rdx+10h]
0x1800428fe  sub     rax, rsi
0x180042901  and     rcx, rax
0x180042904  mov     rdx, [rdx+8]
0x180042908  and     r8, rsi
0x18004290b  mov     rdx, [rdx+rcx*8]
0x18004290f  mov     rdx, [rdx+r8*8]
0x180042913  mov     r14d, [rdx+10h]
0x180042917  add     r14, [rdx+8]
0x18004291b  cmp     [r12], r14
0x18004291f  jge     short loc_18004293C
0x180042921  mov     [rsp+4F0h+var_4D0], 0
0x18004292a  lea     r9, [rdi+0E0h]
0x180042931  mov     r8, r12
0x180042934  mov     rcx, rdi
0x180042937  call    ?Read@MkvReader@@AEBAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@AEA_JAEAJPEAPEAE@Z; MkvReader::Read(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,__int64 &,long &,uchar * *)
0x18004293c  lea     r11, [rdi+0E0h]
0x180042943  cmp     r14, [rdi+0D0h]
0x18004294a  jle     short loc_180042970
0x18004294c  mov     [rdi+0D0h], r14
0x180042953  jmp     short loc_180042975
0x180042955  or      r14, 0FFFFFFFFFFFFFFFFh
0x180042959  lea     r15, [rdi+70h]
0x18004295d  mov     r13, [r15+18h]
0x180042961  test    r15, r15
0x180042964  jz      short loc_180042969
0x180042966  mov     r15, [r15]
0x180042969  lea     rbx, [rdi+88h]
0x180042970  mov     [rsp+4F0h+var_4B8], rbx
0x180042975  cmp     dword ptr [r11], 0
0x180042979  jle     loc_180042B5E
0x18004297f  mov     rax, [rdi+90h]
0x180042986  add     rax, [rbx]
0x180042989  xor     r14d, r14d
0x18004298c  cmp     r13, rax
0x18004298f  jz      short loc_1800429F5
0x180042991  test    r15, r15
0x180042994  jz      short loc_18004299B
0x180042996  mov     rax, [r15]
0x180042999  jmp     short loc_18004299E
0x18004299b  mov     rax, r14
0x18004299e  mov     r8, r13
0x1800429a1  shr     r8, 1
0x1800429a4  mov     r9, r13
0x1800429a7  and     r9, rsi
0x1800429aa  mov     rcx, [rax+10h]
0x1800429ae  sub     rcx, rsi
0x1800429b1  and     rcx, r8
0x1800429b4  mov     rax, [rax+8]
0x1800429b8  mov     rcx, [rax+rcx*8]
0x1800429bc  mov     rdx, [rcx+r9*8]
0x1800429c0  mov     rax, [r12]
0x1800429c4  cmp     [rdx+8], rax
0x1800429c8  jg      short loc_1800429F5
0x1800429ca  test    r15, r15
0x1800429cd  jz      short loc_1800429D4
0x1800429cf  mov     rax, [r15]
0x1800429d2  jmp     short loc_1800429D7
0x1800429d4  mov     rax, r14
0x1800429d7  mov     rbx, [rax+10h]
0x1800429db  sub     rbx, rsi
0x1800429de  and     rbx, r8
0x1800429e1  mov     rax, [rax+8]
0x1800429e5  mov     rbx, [rax+rbx*8]
0x1800429e9  mov     rbx, [rbx+r9*8]
0x1800429ed  mov     r9, r11
0x1800429f0  jmp     loc_180042A83
0x1800429f5  mov     [rsp+4F0h+var_4A0], r14
0x1800429fa  mov     [rsp+4F0h+var_498], r14
0x1800429ff  mov     [rsp+4F0h+var_4A8], r14
0x180042a04  mov     [rsp+4F0h+var_488], r14
0x180042a09  mov     [rsp+4F0h+var_490], r15
0x180042a0e  mov     [rsp+4F0h+var_480], r13
0x180042a13  lea     rax, [rsp+4F0h+var_4A8]
0x180042a18  mov     [rsp+4F0h+var_4D0], rax; __int64
0x180042a1d  mov     r9, [rsp+4F0h+var_478]
0x180042a22  mov     r8, [r12]
0x180042a26  lea     rdx, [rsp+4F0h+var_490]
0x180042a2b  mov     rcx, rdi; this
0x180042a2e  call    ?AsyncReadPage@MkvReader@@AEAAJV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@_JPEAUIMFAsyncCallback@@AEAV23@@Z; MkvReader::AsyncReadPage(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,IMFAsyncCallback *,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>> &)
0x180042a33  mov     [rsp+4F0h+var_4C0], eax
0x180042a37  test    eax, eax
0x180042a39  js      loc_180042AC7
0x180042a3f  mov     r15, [rsp+4F0h+var_4A8]
0x180042a44  test    r15, r15
0x180042a47  jz      short loc_180042A4E
0x180042a49  mov     rbx, [r15]
0x180042a4c  jmp     short loc_180042A51
0x180042a4e  mov     rbx, r14
0x180042a51  cmp     eax, esi
0x180042a53  jz      short loc_180042AC2
0x180042a55  mov     r13, [rsp+4F0h+var_498]
0x180042a5a  mov     rcx, r13
0x180042a5d  shr     rcx, 1
0x180042a60  mov     rax, [rbx+10h]
0x180042a64  sub     rax, rsi
0x180042a67  and     rcx, rax
0x180042a6a  mov     rbx, [rbx+8]
0x180042a6e  mov     rax, r13
0x180042a71  and     rax, rsi
0x180042a74  mov     rbx, [rbx+rcx*8]
0x180042a78  mov     rbx, [rbx+rax*8]
0x180042a7c  lea     r9, [rdi+0E0h]
0x180042a83  mov     [rsp+4F0h+var_4D0], r14
0x180042a88  mov     r8, r12
0x180042a8b  mov     rdx, rbx
0x180042a8e  mov     rcx, rdi
0x180042a91  call    ?Read@MkvReader@@AEBAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@AEA_JAEAJPEAPEAE@Z; MkvReader::Read(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,__int64 &,long &,uchar * *)
0x180042a96  mov     r14d, [rbx+10h]
0x180042a9a  add     r14, [rbx+8]
0x180042a9e  inc     r13
0x180042aa1  cmp     r14, [rdi+0D0h]
0x180042aa8  jle     short loc_180042AB1
0x180042aaa  mov     [rdi+0D0h], r14
0x180042ab1  mov     rbx, [rsp+4F0h+var_4B8]
0x180042ab6  lea     r11, [rdi+0E0h]
0x180042abd  jmp     loc_180042975
0x180042ac2  jmp     loc_180042D76
0x180042ac7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ace  test    rcx, rcx
0x180042ad1  jnz     short loc_180042B14
0x180042ad3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042ad9  mov     rcx, rax
0x180042adc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ae3  test    rax, rax
0x180042ae6  jz      short loc_180042B06
0x180042ae8  mov     rax, [rax]
0x180042aeb  mov     edx, 7F0h
0x180042af0  mov     rax, [rax+8]
0x180042af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042af9  test    eax, eax
0x180042afb  jz      short loc_180042B06
0x180042afd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042b04  jmp     short loc_180042B14
0x180042b06  lea     rcx, qword_1800D6F70; this
0x180042b0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042b14  cmp     [rcx+8], r14b
0x180042b18  jz      short loc_180042B47
0x180042b1a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042b1f  mov     r9d, [rsp+4F0h+var_4C0]; int
0x180042b24  test    r9d, r9d
0x180042b27  jns     short loc_180042B47
0x180042b29  cmp     [rax+7CCh], r9d
0x180042b30  jz      short loc_180042B47
0x180042b32  mov     r8d, 375h; int
0x180042b38  lea     rdx, aMkvreaderAsync_2; "MkvReader::AsyncReadContinue"
0x180042b3f  mov     rcx, rax; this
0x180042b42  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042b47  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180042b4e  jb      loc_180042C45
0x180042b54  mov     edx, 25h ; '%'
0x180042b59  jmp     loc_180042C22
0x180042b5e  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180042b66  mov     dword ptr [r11], 0FFFFFFFFh
0x180042b6d  xor     ebx, ebx
0x180042b6f  mov     [rsp+4F0h+var_4B0], rbx
0x180042b74  mov     rcx, [rdi+10h]
0x180042b78  mov     rax, [rcx]
0x180042b7b  lea     rdx, [rsp+4F0h+var_4B0]
0x180042b80  mov     rax, [rax+30h]
0x180042b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b89  mov     [rsp+4F0h+var_4C0], eax
0x180042b8d  test    eax, eax
0x180042b8f  jns     loc_180042C4E
0x180042b95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042b9c  test    rcx, rcx
0x180042b9f  jnz     short loc_180042BE2
0x180042ba1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042ba7  mov     rcx, rax
0x180042baa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042bb1  test    rax, rax
0x180042bb4  jz      short loc_180042BD4
0x180042bb6  mov     rax, [rax]
0x180042bb9  mov     edx, 7F0h
0x180042bbe  mov     rax, [rax+8]
0x180042bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bc7  test    eax, eax
0x180042bc9  jz      short loc_180042BD4
0x180042bcb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042bd2  jmp     short loc_180042BE2
0x180042bd4  lea     rcx, qword_1800D6F70; this
0x180042bdb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042be2  cmp     [rcx+8], bl
0x180042be5  jz      short loc_180042C14
0x180042be7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042bec  mov     r9d, [rsp+4F0h+var_4C0]; int
0x180042bf1  test    r9d, r9d
0x180042bf4  jns     short loc_180042C14
0x180042bf6  cmp     [rax+7CCh], r9d
0x180042bfd  jz      short loc_180042C14
0x180042bff  mov     r8d, 3AAh; int
0x180042c05  lea     rdx, aMkvreaderAsync_2; "MkvReader::AsyncReadContinue"
0x180042c0c  mov     rcx, rax; this
0x180042c0f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042c14  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180042c1b  jb      short loc_180042C45
0x180042c1d  mov     edx, 26h ; '&'
0x180042c22  mov     eax, [rsp+4F0h+var_4C0]
0x180042c26  mov     dword ptr [rsp+4F0h+var_4D0], eax
0x180042c2a  mov     r9, rdi
0x180042c2d  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180042c34  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c3b  mov     rcx, [rcx+10h]
0x180042c3f  call    WPP_SF_qD
0x180042c44  nop
0x180042c45  mov     esi, [rsp+4F0h+var_4C0]
0x180042c49  jmp     loc_180042D76
0x180042c4e  cmp     r14, [rsp+4F0h+var_4B0]
0x180042c53  jbe     loc_180042D74
0x180042c59  mov     rcx, [rdi+10h]
0x180042c5d  mov     rax, [rcx]
0x180042c60  mov     rdx, r14
0x180042c63  mov     rax, [rax+38h]
0x180042c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c6c  test    eax, eax
0x180042c6e  jns     loc_180042D74
0x180042c74  mov     r15d, 400h
0x180042c7a  mov     r8d, r15d; Size
0x180042c7d  xor     edx, edx; Val
0x180042c7f  lea     rcx, [rbp+3F0h+var_440]; void *
0x180042c83  call    memset_0
0x180042c88  mov     rcx, [rsp+4F0h+var_4B0]
0x180042c8d  cmp     rcx, r14
  ... truncated ...
```
