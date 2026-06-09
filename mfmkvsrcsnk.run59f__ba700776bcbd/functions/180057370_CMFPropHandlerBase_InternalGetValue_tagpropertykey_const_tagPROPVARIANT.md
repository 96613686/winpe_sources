# CMFPropHandlerBase::InternalGetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180057370`
- end: `0x1800575d3`
- name: `?InternalGetValue@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `611`
- prototype: `int(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180055474`
- `0x180057370`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180057405`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180057405`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057427`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005750d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057427`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005750d`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::InternalGetValue(
        CMFPropHandlerBase *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  HRESULT v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  _BYTE v22[4]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-3Ch] BYREF
  const PROPVARIANT *v24; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v25[16]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v26; // [rsp+50h] [rbp-20h] BYREF
  int v27; // [rsp+60h] [rbp-10h]

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v22, "CMFPropHandlerBase::InternalGetValue", 735);
  v24 = 0;
  v27 = 0;
  v6 = *(_QWORD *)this;
  v23 = 0;
  v26 = 0;
  (*(void (__fastcall **)(CMFPropHandlerBase *, const struct _tagpropertykey *, __int128 *))(v6 + 96))(this, a2, &v26);
  if ( (unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find((char *)this + 48, &v26, &v24, v25) )
  {
    v8 = PropVariantCopy(a3, v24 + 4);
    if ( v8 < 0 )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v9, v10);
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
      if ( *((_BYTE *)v11 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::InternalGetValue", 747, v8);
      }
      if ( g_wppLevels )
      {
        v14 = 59;
LABEL_26:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids, this, v8);
      }
    }
  }
  else if ( (*(int (__fastcall **)(CMFPropHandlerBase *, __int128 *, struct tagPROPVARIANT *, unsigned int *))(*(_QWORD *)this + 104LL))(
              this,
              &v26,
              a3,
              &v23) >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(CMFPropHandlerBase *, __int128 *, struct tagPROPVARIANT *, _QWORD, _DWORD))(*(_QWORD *)this + 40LL))(
           this,
           &v26,
           a3,
           v23,
           0);
    if ( v8 < 0 )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != v8 )
          CallStackContext::TraceFailure(v20, "CMFPropHandlerBase::InternalGetValue", 762, v8);
      }
      if ( g_wppLevels )
      {
        v14 = 60;
        goto LABEL_26;
      }
    }
  }
  else
  {
    v8 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180057370  mov     [rsp-18h+arg_18], rbx
0x180057375  push    rbp
0x180057376  push    rsi
0x180057377  push    rdi
0x180057378  mov     rbp, rsp
0x18005737b  sub     rsp, 70h
0x18005737f  mov     rax, cs:__security_cookie
0x180057386  xor     rax, rsp
0x180057389  mov     [rbp+var_8], rax
0x18005738d  mov     rsi, r8
0x180057390  mov     rbx, rdx
0x180057393  mov     rdi, rcx
0x180057396  lea     rdx, aCmfprophandler_18; "CMFPropHandlerBase::InternalGetValue"
0x18005739d  mov     r8d, 2DFh; int
0x1800573a3  lea     rcx, [rbp+var_40]; this
0x1800573a7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800573ac  xor     eax, eax
0x1800573ae  mov     [rbp+var_38], 0
0x1800573b6  mov     [rbp+var_10], eax
0x1800573b9  lea     r8, [rbp+var_20]
0x1800573bd  mov     rax, [rdi]
0x1800573c0  xorps   xmm0, xmm0
0x1800573c3  mov     rdx, rbx
0x1800573c6  mov     [rbp+var_3C], 0
0x1800573cd  mov     rcx, rdi
0x1800573d0  movups  [rbp+var_20], xmm0
0x1800573d4  mov     rax, [rax+60h]
0x1800573d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800573dd  lea     rcx, [rdi+30h]
0x1800573e1  lea     r9, [rbp+var_30]
0x1800573e5  lea     r8, [rbp+var_38]
0x1800573e9  lea     rdx, [rbp+var_20]
0x1800573ed  call    ?Find@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Find(_tagpropertykey const &,CMFProperty * &,CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x1800573f2  test    eax, eax
0x1800573f4  jz      loc_1800574B0
0x1800573fa  mov     rdx, [rbp+var_38]
0x1800573fe  mov     rcx, rsi; pvarDest
0x180057401  add     rdx, 60h ; '`'; pvarSrc
0x180057405  call    cs:__imp_PropVariantCopy
0x18005740c  nop     dword ptr [rax+rax+00h]
0x180057411  mov     ebx, eax
0x180057413  test    eax, eax
0x180057415  jns     loc_1800575AB
0x18005741b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057422  test    rcx, rcx
0x180057425  jnz     short loc_18005746E
0x180057427  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005742e  nop     dword ptr [rax+rax+00h]
0x180057433  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005743a  mov     rcx, rax
0x18005743d  test    rax, rax
0x180057440  jz      short loc_180057460
0x180057442  mov     rax, [rax]
0x180057445  mov     edx, 7F0h
0x18005744a  mov     rax, [rax+8]
0x18005744e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057453  test    eax, eax
0x180057455  jz      short loc_180057460
0x180057457  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005745e  jmp     short loc_18005746E
0x180057460  lea     rcx, qword_1800DBF70; this
0x180057467  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005746e  cmp     byte ptr [rcx+8], 0
0x180057472  jz      short loc_180057499
0x180057474  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057479  cmp     [rax+7CCh], ebx
0x18005747f  jz      short loc_180057499
0x180057481  mov     r9d, ebx; int
0x180057484  lea     rdx, aCmfprophandler_18; "CMFPropHandlerBase::InternalGetValue"
0x18005748b  mov     r8d, 2EBh; int
0x180057491  mov     rcx, rax; this
0x180057494  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057499  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800574a0  jb      loc_1800575AB
0x1800574a6  mov     edx, 3Bh ; ';'
0x1800574ab  jmp     loc_18005758D
0x1800574b0  mov     rax, [rdi]
0x1800574b3  lea     r9, [rbp+var_3C]
0x1800574b7  mov     r8, rsi
0x1800574ba  lea     rdx, [rbp+var_20]
0x1800574be  mov     rcx, rdi
0x1800574c1  mov     rax, [rax+68h]
0x1800574c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800574ca  test    eax, eax
0x1800574cc  jns     short loc_1800574D5
0x1800574ce  xor     ebx, ebx
0x1800574d0  jmp     loc_1800575AB
0x1800574d5  mov     rax, [rdi]
0x1800574d8  lea     rdx, [rbp+var_20]
0x1800574dc  mov     r9d, [rbp+var_3C]
0x1800574e0  mov     r8, rsi
0x1800574e3  mov     rcx, rdi
0x1800574e6  mov     [rsp+70h+var_50], 0
0x1800574ee  mov     rax, [rax+28h]
0x1800574f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800574f7  mov     ebx, eax
0x1800574f9  test    eax, eax
0x1800574fb  jns     loc_1800575AB
0x180057501  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057508  test    rcx, rcx
0x18005750b  jnz     short loc_180057554
0x18005750d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057514  nop     dword ptr [rax+rax+00h]
0x180057519  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057520  mov     rcx, rax
0x180057523  test    rax, rax
0x180057526  jz      short loc_180057546
0x180057528  mov     rax, [rax]
0x18005752b  mov     edx, 7F0h
0x180057530  mov     rax, [rax+8]
0x180057534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057539  test    eax, eax
0x18005753b  jz      short loc_180057546
0x18005753d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057544  jmp     short loc_180057554
0x180057546  lea     rcx, qword_1800DBF70; this
0x18005754d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180057554  cmp     byte ptr [rcx+8], 0
0x180057558  jz      short loc_18005757F
0x18005755a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005755f  cmp     [rax+7CCh], ebx
0x180057565  jz      short loc_18005757F
0x180057567  mov     r9d, ebx; int
0x18005756a  lea     rdx, aCmfprophandler_18; "CMFPropHandlerBase::InternalGetValue"
0x180057571  mov     r8d, 2FAh; int
0x180057577  mov     rcx, rax; this
0x18005757a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005757f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180057586  jb      short loc_1800575AB
0x180057588  mov     edx, 3Ch ; '<'
0x18005758d  mov     rcx, cs:WPP_GLOBAL_Control
0x180057594  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18005759b  mov     r9, rdi
0x18005759e  mov     [rsp+70h+var_50], ebx
0x1800575a2  mov     rcx, [rcx+10h]
0x1800575a6  call    WPP_SF_qD
0x1800575ab  lea     rcx, [rbp+var_40]; this
0x1800575af  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800575b4  mov     eax, ebx
0x1800575b6  mov     rcx, [rbp+var_8]
0x1800575ba  xor     rcx, rsp; StackCookie
0x1800575bd  call    __security_check_cookie
0x1800575c2  mov     rbx, [rsp+70h+arg_18]
0x1800575ca  add     rsp, 70h
0x1800575ce  pop     rdi
0x1800575cf  pop     rsi
0x1800575d0  pop     rbp
0x1800575d1  retn
```
