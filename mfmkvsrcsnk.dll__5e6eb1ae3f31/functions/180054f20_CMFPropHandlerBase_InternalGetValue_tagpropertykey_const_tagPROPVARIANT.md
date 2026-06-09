# CMFPropHandlerBase::InternalGetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180054f20`
- end: `0x180055170`
- name: `?InternalGetValue@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `592`
- prototype: `int(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x1800530e4`
- `0x180054f20`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180054fb5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180054fb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054fd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800550b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054fd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800550b1`

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
          v11 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids, this, v8);
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
          v18 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180054f20  mov     [rsp-18h+arg_18], rbx
0x180054f25  push    rbp
0x180054f26  push    rsi
0x180054f27  push    rdi
0x180054f28  mov     rbp, rsp
0x180054f2b  sub     rsp, 70h
0x180054f2f  mov     rax, cs:__security_cookie
0x180054f36  xor     rax, rsp
0x180054f39  mov     [rbp+var_8], rax
0x180054f3d  mov     rsi, r8
0x180054f40  mov     rbx, rdx
0x180054f43  mov     rdi, rcx
0x180054f46  lea     rdx, aCmfprophandler_18; "CMFPropHandlerBase::InternalGetValue"
0x180054f4d  mov     r8d, 2DFh; int
0x180054f53  lea     rcx, [rbp+var_40]; this
0x180054f57  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180054f5c  xor     eax, eax
0x180054f5e  mov     [rbp+var_38], 0
0x180054f66  mov     [rbp+var_10], eax
0x180054f69  lea     r8, [rbp+var_20]
0x180054f6d  mov     rax, [rdi]
0x180054f70  xorps   xmm0, xmm0
0x180054f73  mov     rdx, rbx
0x180054f76  mov     [rbp+var_3C], 0
0x180054f7d  mov     rcx, rdi
0x180054f80  movups  [rbp+var_20], xmm0
0x180054f84  mov     rax, [rax+60h]
0x180054f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f8d  lea     rcx, [rdi+30h]
0x180054f91  lea     r9, [rbp+var_30]
0x180054f95  lea     r8, [rbp+var_38]
0x180054f99  lea     rdx, [rbp+var_20]
0x180054f9d  call    ?Find@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Find(_tagpropertykey const &,CMFProperty * &,CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x180054fa2  test    eax, eax
0x180054fa4  jz      loc_180055054
0x180054faa  mov     rdx, [rbp+var_38]
0x180054fae  mov     rcx, rsi; pvarDest
0x180054fb1  add     rdx, 60h ; '`'; pvarSrc
0x180054fb5  call    cs:__imp_PropVariantCopy
0x180054fbb  mov     ebx, eax
0x180054fbd  test    eax, eax
0x180054fbf  jns     loc_180055149
0x180054fc5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054fcc  test    rcx, rcx
0x180054fcf  jnz     short loc_180055012
0x180054fd1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054fd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054fde  mov     rcx, rax
0x180054fe1  test    rax, rax
0x180054fe4  jz      short loc_180055004
0x180054fe6  mov     rax, [rax]
0x180054fe9  mov     edx, 7F0h
0x180054fee  mov     rax, [rax+8]
0x180054ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ff7  test    eax, eax
0x180054ff9  jz      short loc_180055004
0x180054ffb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180055002  jmp     short loc_180055012
0x180055004  lea     rcx, qword_1800D6F70; this
0x18005500b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180055012  cmp     byte ptr [rcx+8], 0
0x180055016  jz      short loc_18005503D
0x180055018  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005501d  cmp     [rax+7CCh], ebx
0x180055023  jz      short loc_18005503D
0x180055025  mov     r9d, ebx; int
0x180055028  lea     rdx, aCmfprophandler_18; "CMFPropHandlerBase::InternalGetValue"
0x18005502f  mov     r8d, 2EBh; int
0x180055035  mov     rcx, rax; this
0x180055038  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005503d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180055044  jb      loc_180055149
0x18005504a  mov     edx, 3Bh ; ';'
0x18005504f  jmp     loc_18005512B
0x180055054  mov     rax, [rdi]
0x180055057  lea     r9, [rbp+var_3C]
0x18005505b  mov     r8, rsi
0x18005505e  lea     rdx, [rbp+var_20]
0x180055062  mov     rcx, rdi
0x180055065  mov     rax, [rax+68h]
0x180055069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005506e  test    eax, eax
0x180055070  jns     short loc_180055079
0x180055072  xor     ebx, ebx
0x180055074  jmp     loc_180055149
0x180055079  mov     rax, [rdi]
0x18005507c  lea     rdx, [rbp+var_20]
0x180055080  mov     r9d, [rbp+var_3C]
0x180055084  mov     r8, rsi
0x180055087  mov     rcx, rdi
0x18005508a  mov     [rsp+70h+var_50], 0
0x180055092  mov     rax, [rax+28h]
0x180055096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005509b  mov     ebx, eax
0x18005509d  test    eax, eax
0x18005509f  jns     loc_180055149
0x1800550a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800550ac  test    rcx, rcx
0x1800550af  jnz     short loc_1800550F2
0x1800550b1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800550b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800550be  mov     rcx, rax
0x1800550c1  test    rax, rax
0x1800550c4  jz      short loc_1800550E4
0x1800550c6  mov     rax, [rax]
0x1800550c9  mov     edx, 7F0h
0x1800550ce  mov     rax, [rax+8]
0x1800550d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800550d7  test    eax, eax
0x1800550d9  jz      short loc_1800550E4
0x1800550db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800550e2  jmp     short loc_1800550F2
0x1800550e4  lea     rcx, qword_1800D6F70; this
0x1800550eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800550f2  cmp     byte ptr [rcx+8], 0
0x1800550f6  jz      short loc_18005511D
0x1800550f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800550fd  cmp     [rax+7CCh], ebx
0x180055103  jz      short loc_18005511D
0x180055105  mov     r9d, ebx; int
0x180055108  lea     rdx, aCmfprophandler_18; "CMFPropHandlerBase::InternalGetValue"
0x18005510f  mov     r8d, 2FAh; int
0x180055115  mov     rcx, rax; this
0x180055118  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005511d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180055124  jb      short loc_180055149
0x180055126  mov     edx, 3Ch ; '<'
0x18005512b  mov     rcx, cs:WPP_GLOBAL_Control
0x180055132  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x180055139  mov     r9, rdi
0x18005513c  mov     [rsp+70h+var_50], ebx
0x180055140  mov     rcx, [rcx+10h]
0x180055144  call    WPP_SF_qD
0x180055149  lea     rcx, [rbp+var_40]; this
0x18005514d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180055152  mov     eax, ebx
0x180055154  mov     rcx, [rbp+var_8]
0x180055158  xor     rcx, rsp; StackCookie
0x18005515b  call    __security_check_cookie
0x180055160  mov     rbx, [rsp+70h+arg_18]
0x180055168  add     rsp, 70h
0x18005516c  pop     rdi
0x18005516d  pop     rsi
0x18005516e  pop     rbp
0x18005516f  retn
```
