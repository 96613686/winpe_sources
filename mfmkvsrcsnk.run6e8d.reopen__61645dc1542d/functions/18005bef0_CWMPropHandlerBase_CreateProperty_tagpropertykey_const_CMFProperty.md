# CWMPropHandlerBase::CreateProperty(_tagpropertykey const &,CMFProperty * *)

- ea: `0x18005bef0`
- end: `0x18005c326`
- name: `?CreateProperty@CWMPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAPEAVCMFProperty@@@Z`
- size: `1078`
- prototype: `int(CWMPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct CMFProperty **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180001f90`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x1800530e4`
- `0x180056970`
- `0x18005bef0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005bf91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c050`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c10b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c1b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c275`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005bf91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c050`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c10b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c1b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c275`

## string_xrefs

- `0x18005bf03`: `CWMPropHandlerBase::CreateProperty`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::CreateProperty(
        CWMPropHandlerBase *this,
        const struct _tagpropertykey *a2,
        struct CMFProperty **a3)
{
  __int64 v6; // r14
  __int64 v7; // rdx
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  CWMProperty *v21; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  CWMProperty *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  struct CMFProperty *v36; // rax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v41[56]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v42; // [rsp+70h] [rbp+8h] BYREF
  int v43; // [rsp+88h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v42, "CWMPropHandlerBase::CreateProperty", 937);
  v42 = 0;
  v43 = 0;
  if ( !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find((char *)this + 1304, a2, &v42, v41) )
  {
    v32 = (CWMProperty *)operator new(0x90u);
    if ( v32 )
    {
      v8 = 0;
      v36 = CWMProperty::CWMProperty(v32, a2);
      *a3 = v36;
      if ( v36 )
        goto LABEL_66;
    }
    else
    {
      *a3 = 0;
    }
    v37 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
      CallStackTracing::s_wpInstance = v38;
      if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v37 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v37 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMPropHandlerBase::CreateProperty", 966, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_66;
    v25 = 88;
    goto LABEL_65;
  }
  v6 = v42;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, int *))(*(_QWORD *)v42 + 56LL))(v42, MF_MD_PKEY_EXCEPTIONAL, &v43);
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
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != v8 )
        CallStackContext::TraceFailure(v13, "CWMPropHandlerBase::CreateProperty", 945, v8);
    }
    if ( g_wppLevels )
    {
      v14 = 84;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, v8);
      goto LABEL_66;
    }
    goto LABEL_66;
  }
  if ( !v43 )
  {
    v21 = (CWMProperty *)operator new(0x90u);
    if ( v21 )
      v21 = CWMProperty::CWMProperty(v21, a2);
    *a3 = v21;
    goto LABEL_29;
  }
  v8 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const struct _tagpropertykey *, struct CMFProperty **))(*(_QWORD *)this + 160LL))(
         this,
         a2,
         a3);
  if ( v8 >= 0 )
  {
LABEL_29:
    if ( *a3 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 256LL))(v6);
      if ( v8 < 0 )
      {
        v29 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
          CallStackTracing::s_wpInstance = v30;
          if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          {
            v29 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v29 + 8) )
        {
          v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
          if ( *((_DWORD *)v31 + 499) != v8 )
            CallStackContext::TraceFailure(v31, "CWMPropHandlerBase::CreateProperty", 961, v8);
        }
        if ( g_wppLevels )
        {
          v14 = 87;
          goto LABEL_13;
        }
      }
      goto LABEL_66;
    }
    v22 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0, v16, v17);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v22 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
      if ( *((_DWORD *)v24 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v24, "CWMPropHandlerBase::CreateProperty", 955, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_66;
    v25 = 86;
LABEL_65:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v25,
      WPP_d497573e8d0434bb74893564de0342d6_Traceguids,
      this,
      -2147024882);
    goto LABEL_66;
  }
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
      CallStackContext::TraceFailure(v20, "CWMPropHandlerBase::CreateProperty", 948, v8);
  }
  if ( g_wppLevels )
  {
    v14 = 85;
    goto LABEL_13;
  }
LABEL_66:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v42);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005bef0  mov     [rsp+arg_8], rbx
0x18005bef5  push    rbp
0x18005bef6  push    rsi
0x18005bef7  push    rdi
0x18005bef8  push    r12
0x18005befa  push    r14
0x18005befc  sub     rsp, 40h
0x18005bf00  mov     rdi, r8
0x18005bf03  lea     r12, aCwmprophandler_10; "CWMPropHandlerBase::CreateProperty"
0x18005bf0a  mov     rbp, rdx
0x18005bf0d  mov     rsi, rcx
0x18005bf10  mov     rdx, r12; char *
0x18005bf13  lea     rcx, [rsp+68h+arg_0]; this
0x18005bf18  mov     r8d, 3A9h; int
0x18005bf1e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005bf23  lea     rcx, [rsi+518h]
0x18005bf2a  mov     [rsp+68h+arg_0], 0
0x18005bf33  lea     r9, [rsp+68h+var_38]
0x18005bf38  mov     [rsp+68h+arg_18], 0
0x18005bf43  lea     r8, [rsp+68h+arg_0]
0x18005bf48  mov     rdx, rbp
0x18005bf4b  call    ?Find@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Find(_tagpropertykey const &,CMFProperty * &,CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x18005bf50  test    eax, eax
0x18005bf52  jz      loc_18005C231
0x18005bf58  mov     r14, [rsp+68h+arg_0]
0x18005bf5d  lea     r8, [rsp+68h+arg_18]
0x18005bf65  lea     rdx, MF_MD_PKEY_EXCEPTIONAL
0x18005bf6c  mov     rcx, r14
0x18005bf6f  mov     rax, [r14]
0x18005bf72  mov     rax, [rax+38h]
0x18005bf76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf7b  mov     ebx, eax
0x18005bf7d  test    eax, eax
0x18005bf7f  jns     loc_18005C014
0x18005bf85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005bf8c  test    rcx, rcx
0x18005bf8f  jnz     short loc_18005BFD2
0x18005bf91  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005bf97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005bf9e  mov     rcx, rax
0x18005bfa1  test    rax, rax
0x18005bfa4  jz      short loc_18005BFC4
0x18005bfa6  mov     rax, [rax]
0x18005bfa9  mov     edx, 7F0h
0x18005bfae  mov     rax, [rax+8]
0x18005bfb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bfb7  test    eax, eax
0x18005bfb9  jz      short loc_18005BFC4
0x18005bfbb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005bfc2  jmp     short loc_18005BFD2
0x18005bfc4  lea     rcx, qword_1800D6F70; this
0x18005bfcb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005bfd2  cmp     byte ptr [rcx+8], 0
0x18005bfd6  jz      short loc_18005BFF9
0x18005bfd8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005bfdd  cmp     [rax+7CCh], ebx
0x18005bfe3  jz      short loc_18005BFF9
0x18005bfe5  mov     r9d, ebx; int
0x18005bfe8  mov     r8d, 3B1h; int
0x18005bfee  mov     rdx, r12; char *
0x18005bff1  mov     rcx, rax; this
0x18005bff4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005bff9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005c000  jb      loc_18005C309
0x18005c006  mov     edx, 54h ; 'T'
0x18005c00b  mov     [rsp+68h+var_48], ebx
0x18005c00f  jmp     loc_18005C2EF
0x18005c014  cmp     [rsp+68h+arg_18], 0
0x18005c01c  jz      loc_18005C0CF
0x18005c022  mov     rax, [rsi]
0x18005c025  mov     r8, rdi
0x18005c028  mov     rdx, rbp
0x18005c02b  mov     rcx, rsi
0x18005c02e  mov     rax, [rax+0A0h]
0x18005c035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c03a  mov     ebx, eax
0x18005c03c  test    eax, eax
0x18005c03e  jns     loc_18005C0EC
0x18005c044  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c04b  test    rcx, rcx
0x18005c04e  jnz     short loc_18005C091
0x18005c050  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005c056  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c05d  mov     rcx, rax
0x18005c060  test    rax, rax
0x18005c063  jz      short loc_18005C083
0x18005c065  mov     rax, [rax]
0x18005c068  mov     edx, 7F0h
0x18005c06d  mov     rax, [rax+8]
0x18005c071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c076  test    eax, eax
0x18005c078  jz      short loc_18005C083
0x18005c07a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c081  jmp     short loc_18005C091
0x18005c083  lea     rcx, qword_1800D6F70; this
0x18005c08a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c091  cmp     byte ptr [rcx+8], 0
0x18005c095  jz      short loc_18005C0B8
0x18005c097  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005c09c  cmp     [rax+7CCh], ebx
0x18005c0a2  jz      short loc_18005C0B8
0x18005c0a4  mov     r9d, ebx; int
0x18005c0a7  mov     r8d, 3B4h; int
0x18005c0ad  mov     rdx, r12; char *
0x18005c0b0  mov     rcx, rax; this
0x18005c0b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005c0b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005c0bf  jb      loc_18005C309
0x18005c0c5  mov     edx, 55h ; 'U'
0x18005c0ca  jmp     loc_18005C00B
0x18005c0cf  mov     ecx, 90h; Size
0x18005c0d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005c0d9  test    rax, rax
0x18005c0dc  jz      short loc_18005C0E9
0x18005c0de  mov     rdx, rbp; struct _tagpropertykey *
0x18005c0e1  mov     rcx, rax; this
0x18005c0e4  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005c0e9  mov     [rdi], rax
0x18005c0ec  mov     rdx, [rdi]
0x18005c0ef  test    rdx, rdx
0x18005c0f2  jnz     loc_18005C18A
0x18005c0f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c0ff  mov     edi, 8007000Eh
0x18005c104  mov     ebx, edi
0x18005c106  test    rcx, rcx
0x18005c109  jnz     short loc_18005C14C
0x18005c10b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005c111  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c118  mov     rcx, rax
0x18005c11b  test    rax, rax
0x18005c11e  jz      short loc_18005C13E
0x18005c120  mov     rax, [rax]
0x18005c123  mov     edx, 7F0h
0x18005c128  mov     rax, [rax+8]
0x18005c12c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c131  test    eax, eax
0x18005c133  jz      short loc_18005C13E
0x18005c135  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c13c  jmp     short loc_18005C14C
0x18005c13e  lea     rcx, qword_1800D6F70; this
0x18005c145  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c14c  cmp     byte ptr [rcx+8], 0
0x18005c150  jz      short loc_18005C173
0x18005c152  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005c157  cmp     [rax+7CCh], edi
0x18005c15d  jz      short loc_18005C173
0x18005c15f  mov     r9d, edi; int
0x18005c162  mov     r8d, 3BBh; int
0x18005c168  mov     rdx, r12; char *
0x18005c16b  mov     rcx, rax; this
0x18005c16e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005c173  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005c17a  jb      loc_18005C309
0x18005c180  mov     edx, 56h ; 'V'
0x18005c185  jmp     loc_18005C2EB
0x18005c18a  mov     rax, [r14]
0x18005c18d  mov     rcx, r14
0x18005c190  mov     rax, [rax+100h]
0x18005c197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c19c  mov     ebx, eax
0x18005c19e  test    eax, eax
0x18005c1a0  jns     loc_18005C309
0x18005c1a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c1ad  test    rcx, rcx
0x18005c1b0  jnz     short loc_18005C1F3
0x18005c1b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005c1b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c1bf  mov     rcx, rax
0x18005c1c2  test    rax, rax
0x18005c1c5  jz      short loc_18005C1E5
0x18005c1c7  mov     rax, [rax]
0x18005c1ca  mov     edx, 7F0h
0x18005c1cf  mov     rax, [rax+8]
0x18005c1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c1d8  test    eax, eax
0x18005c1da  jz      short loc_18005C1E5
0x18005c1dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c1e3  jmp     short loc_18005C1F3
0x18005c1e5  lea     rcx, qword_1800D6F70; this
0x18005c1ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c1f3  cmp     byte ptr [rcx+8], 0
0x18005c1f7  jz      short loc_18005C21A
0x18005c1f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005c1fe  cmp     [rax+7CCh], ebx
0x18005c204  jz      short loc_18005C21A
0x18005c206  mov     r9d, ebx; int
0x18005c209  mov     r8d, 3C1h; int
0x18005c20f  mov     rdx, r12; char *
0x18005c212  mov     rcx, rax; this
0x18005c215  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005c21a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005c221  jb      loc_18005C309
0x18005c227  mov     edx, 57h ; 'W'
0x18005c22c  jmp     loc_18005C00B
0x18005c231  mov     ecx, 90h; Size
0x18005c236  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005c23b  test    rax, rax
0x18005c23e  jz      short loc_18005C25B
0x18005c240  mov     rdx, rbp; struct _tagpropertykey *
0x18005c243  mov     rcx, rax; this
0x18005c246  xor     ebx, ebx
0x18005c248  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005c24d  mov     [rdi], rax
0x18005c250  test    rax, rax
0x18005c253  jnz     loc_18005C309
0x18005c259  jmp     short loc_18005C262
0x18005c25b  mov     qword ptr [rdi], 0
0x18005c262  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c269  mov     edi, 8007000Eh
0x18005c26e  mov     ebx, edi
0x18005c270  test    rcx, rcx
0x18005c273  jnz     short loc_18005C2B6
0x18005c275  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005c27b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c282  mov     rcx, rax
0x18005c285  test    rax, rax
0x18005c288  jz      short loc_18005C2A8
0x18005c28a  mov     rax, [rax]
0x18005c28d  mov     edx, 7F0h
0x18005c292  mov     rax, [rax+8]
0x18005c296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c29b  test    eax, eax
0x18005c29d  jz      short loc_18005C2A8
0x18005c29f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c2a6  jmp     short loc_18005C2B6
0x18005c2a8  lea     rcx, qword_1800D6F70; this
0x18005c2af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c2b6  cmp     byte ptr [rcx+8], 0
0x18005c2ba  jz      short loc_18005C2DD
0x18005c2bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005c2c1  cmp     [rax+7CCh], edi
0x18005c2c7  jz      short loc_18005C2DD
0x18005c2c9  mov     r9d, edi; int
0x18005c2cc  mov     r8d, 3C6h; int
0x18005c2d2  mov     rdx, r12; char *
0x18005c2d5  mov     rcx, rax; this
0x18005c2d8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005c2dd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005c2e4  jb      short loc_18005C309
0x18005c2e6  mov     edx, 58h ; 'X'
0x18005c2eb  mov     [rsp+68h+var_48], edi
0x18005c2ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c2f6  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x18005c2fd  mov     r9, rsi
0x18005c300  mov     rcx, [rcx+10h]
0x18005c304  call    WPP_SF_qD
0x18005c309  lea     rcx, [rsp+68h+arg_0]; this
0x18005c30e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005c313  mov     eax, ebx
0x18005c315  mov     rbx, [rsp+68h+arg_8]
0x18005c31a  add     rsp, 40h
0x18005c31e  pop     r14
0x18005c320  pop     r12
0x18005c322  pop     rdi
0x18005c323  pop     rsi
0x18005c324  pop     rbp
0x18005c325  retn
```
