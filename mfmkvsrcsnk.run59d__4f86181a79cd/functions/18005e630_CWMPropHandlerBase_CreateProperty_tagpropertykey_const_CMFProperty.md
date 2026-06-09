# CWMPropHandlerBase::CreateProperty(_tagpropertykey const &,CMFProperty * *)

- ea: `0x18005e630`
- end: `0x18005ea85`
- name: `?CreateProperty@CWMPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAPEAVCMFProperty@@@Z`
- size: `1109`
- prototype: `int(CWMPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct CMFProperty **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180001fb0`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180055474`
- `0x180058e58`
- `0x18005e630`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e6d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e796`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e857`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e904`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e9cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e6d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e796`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e857`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e904`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e9cd`

## string_xrefs

- `0x18005e643`: `CWMPropHandlerBase::CreateProperty`

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
        v37 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v29 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v22 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v18 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18005e630  mov     [rsp+arg_8], rbx
0x18005e635  push    rbp
0x18005e636  push    rsi
0x18005e637  push    rdi
0x18005e638  push    r12
0x18005e63a  push    r14
0x18005e63c  sub     rsp, 40h
0x18005e640  mov     rdi, r8
0x18005e643  lea     r12, aCwmprophandler_10; "CWMPropHandlerBase::CreateProperty"
0x18005e64a  mov     rbp, rdx
0x18005e64d  mov     rsi, rcx
0x18005e650  mov     rdx, r12; char *
0x18005e653  lea     rcx, [rsp+68h+arg_0]; this
0x18005e658  mov     r8d, 3A9h; int
0x18005e65e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005e663  lea     rcx, [rsi+518h]
0x18005e66a  mov     [rsp+68h+arg_0], 0
0x18005e673  lea     r9, [rsp+68h+var_38]
0x18005e678  mov     [rsp+68h+arg_18], 0
0x18005e683  lea     r8, [rsp+68h+arg_0]
0x18005e688  mov     rdx, rbp
0x18005e68b  call    ?Find@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Find(_tagpropertykey const &,CMFProperty * &,CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x18005e690  test    eax, eax
0x18005e692  jz      loc_18005E989
0x18005e698  mov     r14, [rsp+68h+arg_0]
0x18005e69d  lea     r8, [rsp+68h+arg_18]
0x18005e6a5  lea     rdx, MF_MD_PKEY_EXCEPTIONAL
0x18005e6ac  mov     rcx, r14
0x18005e6af  mov     rax, [r14]
0x18005e6b2  mov     rax, [rax+38h]
0x18005e6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e6bb  mov     ebx, eax
0x18005e6bd  test    eax, eax
0x18005e6bf  jns     loc_18005E75A
0x18005e6c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e6cc  test    rcx, rcx
0x18005e6cf  jnz     short loc_18005E718
0x18005e6d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005e6d8  nop     dword ptr [rax+rax+00h]
0x18005e6dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e6e4  mov     rcx, rax
0x18005e6e7  test    rax, rax
0x18005e6ea  jz      short loc_18005E70A
0x18005e6ec  mov     rax, [rax]
0x18005e6ef  mov     edx, 7F0h
0x18005e6f4  mov     rax, [rax+8]
0x18005e6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e6fd  test    eax, eax
0x18005e6ff  jz      short loc_18005E70A
0x18005e701  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e708  jmp     short loc_18005E718
0x18005e70a  lea     rcx, qword_1800DBF70; this
0x18005e711  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e718  cmp     byte ptr [rcx+8], 0
0x18005e71c  jz      short loc_18005E73F
0x18005e71e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e723  cmp     [rax+7CCh], ebx
0x18005e729  jz      short loc_18005E73F
0x18005e72b  mov     r9d, ebx; int
0x18005e72e  mov     r8d, 3B1h; int
0x18005e734  mov     rdx, r12; char *
0x18005e737  mov     rcx, rax; this
0x18005e73a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e73f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e746  jb      loc_18005EA67
0x18005e74c  mov     edx, 54h ; 'T'
0x18005e751  mov     [rsp+68h+var_48], ebx
0x18005e755  jmp     loc_18005EA4D
0x18005e75a  cmp     [rsp+68h+arg_18], 0
0x18005e762  jz      loc_18005E81B
0x18005e768  mov     rax, [rsi]
0x18005e76b  mov     r8, rdi
0x18005e76e  mov     rdx, rbp
0x18005e771  mov     rcx, rsi
0x18005e774  mov     rax, [rax+0A0h]
0x18005e77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e780  mov     ebx, eax
0x18005e782  test    eax, eax
0x18005e784  jns     loc_18005E838
0x18005e78a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e791  test    rcx, rcx
0x18005e794  jnz     short loc_18005E7DD
0x18005e796  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005e79d  nop     dword ptr [rax+rax+00h]
0x18005e7a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e7a9  mov     rcx, rax
0x18005e7ac  test    rax, rax
0x18005e7af  jz      short loc_18005E7CF
0x18005e7b1  mov     rax, [rax]
0x18005e7b4  mov     edx, 7F0h
0x18005e7b9  mov     rax, [rax+8]
0x18005e7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e7c2  test    eax, eax
0x18005e7c4  jz      short loc_18005E7CF
0x18005e7c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e7cd  jmp     short loc_18005E7DD
0x18005e7cf  lea     rcx, qword_1800DBF70; this
0x18005e7d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e7dd  cmp     byte ptr [rcx+8], 0
0x18005e7e1  jz      short loc_18005E804
0x18005e7e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e7e8  cmp     [rax+7CCh], ebx
0x18005e7ee  jz      short loc_18005E804
0x18005e7f0  mov     r9d, ebx; int
0x18005e7f3  mov     r8d, 3B4h; int
0x18005e7f9  mov     rdx, r12; char *
0x18005e7fc  mov     rcx, rax; this
0x18005e7ff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e804  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e80b  jb      loc_18005EA67
0x18005e811  mov     edx, 55h ; 'U'
0x18005e816  jmp     loc_18005E751
0x18005e81b  mov     ecx, 90h; Size
0x18005e820  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e825  test    rax, rax
0x18005e828  jz      short loc_18005E835
0x18005e82a  mov     rdx, rbp; struct _tagpropertykey *
0x18005e82d  mov     rcx, rax; this
0x18005e830  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005e835  mov     [rdi], rax
0x18005e838  mov     rdx, [rdi]
0x18005e83b  test    rdx, rdx
0x18005e83e  jnz     loc_18005E8DC
0x18005e844  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e84b  mov     edi, 8007000Eh
0x18005e850  mov     ebx, edi
0x18005e852  test    rcx, rcx
0x18005e855  jnz     short loc_18005E89E
0x18005e857  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005e85e  nop     dword ptr [rax+rax+00h]
0x18005e863  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e86a  mov     rcx, rax
0x18005e86d  test    rax, rax
0x18005e870  jz      short loc_18005E890
0x18005e872  mov     rax, [rax]
0x18005e875  mov     edx, 7F0h
0x18005e87a  mov     rax, [rax+8]
0x18005e87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e883  test    eax, eax
0x18005e885  jz      short loc_18005E890
0x18005e887  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e88e  jmp     short loc_18005E89E
0x18005e890  lea     rcx, qword_1800DBF70; this
0x18005e897  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e89e  cmp     byte ptr [rcx+8], 0
0x18005e8a2  jz      short loc_18005E8C5
0x18005e8a4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e8a9  cmp     [rax+7CCh], edi
0x18005e8af  jz      short loc_18005E8C5
0x18005e8b1  mov     r9d, edi; int
0x18005e8b4  mov     r8d, 3BBh; int
0x18005e8ba  mov     rdx, r12; char *
0x18005e8bd  mov     rcx, rax; this
0x18005e8c0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e8c5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e8cc  jb      loc_18005EA67
0x18005e8d2  mov     edx, 56h ; 'V'
0x18005e8d7  jmp     loc_18005EA49
0x18005e8dc  mov     rax, [r14]
0x18005e8df  mov     rcx, r14
0x18005e8e2  mov     rax, [rax+100h]
0x18005e8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8ee  mov     ebx, eax
0x18005e8f0  test    eax, eax
0x18005e8f2  jns     loc_18005EA67
0x18005e8f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e8ff  test    rcx, rcx
0x18005e902  jnz     short loc_18005E94B
0x18005e904  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005e90b  nop     dword ptr [rax+rax+00h]
0x18005e910  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e917  mov     rcx, rax
0x18005e91a  test    rax, rax
0x18005e91d  jz      short loc_18005E93D
0x18005e91f  mov     rax, [rax]
0x18005e922  mov     edx, 7F0h
0x18005e927  mov     rax, [rax+8]
0x18005e92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e930  test    eax, eax
0x18005e932  jz      short loc_18005E93D
0x18005e934  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e93b  jmp     short loc_18005E94B
0x18005e93d  lea     rcx, qword_1800DBF70; this
0x18005e944  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e94b  cmp     byte ptr [rcx+8], 0
0x18005e94f  jz      short loc_18005E972
0x18005e951  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e956  cmp     [rax+7CCh], ebx
0x18005e95c  jz      short loc_18005E972
0x18005e95e  mov     r9d, ebx; int
0x18005e961  mov     r8d, 3C1h; int
0x18005e967  mov     rdx, r12; char *
0x18005e96a  mov     rcx, rax; this
0x18005e96d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e972  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e979  jb      loc_18005EA67
0x18005e97f  mov     edx, 57h ; 'W'
0x18005e984  jmp     loc_18005E751
0x18005e989  mov     ecx, 90h; Size
0x18005e98e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e993  test    rax, rax
0x18005e996  jz      short loc_18005E9B3
0x18005e998  mov     rdx, rbp; struct _tagpropertykey *
0x18005e99b  mov     rcx, rax; this
0x18005e99e  xor     ebx, ebx
0x18005e9a0  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005e9a5  mov     [rdi], rax
0x18005e9a8  test    rax, rax
0x18005e9ab  jnz     loc_18005EA67
0x18005e9b1  jmp     short loc_18005E9BA
0x18005e9b3  mov     qword ptr [rdi], 0
0x18005e9ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e9c1  mov     edi, 8007000Eh
0x18005e9c6  mov     ebx, edi
0x18005e9c8  test    rcx, rcx
0x18005e9cb  jnz     short loc_18005EA14
0x18005e9cd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005e9d4  nop     dword ptr [rax+rax+00h]
0x18005e9d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e9e0  mov     rcx, rax
0x18005e9e3  test    rax, rax
0x18005e9e6  jz      short loc_18005EA06
0x18005e9e8  mov     rax, [rax]
0x18005e9eb  mov     edx, 7F0h
0x18005e9f0  mov     rax, [rax+8]
0x18005e9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9f9  test    eax, eax
0x18005e9fb  jz      short loc_18005EA06
0x18005e9fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ea04  jmp     short loc_18005EA14
0x18005ea06  lea     rcx, qword_1800DBF70; this
0x18005ea0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ea14  cmp     byte ptr [rcx+8], 0
0x18005ea18  jz      short loc_18005EA3B
0x18005ea1a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005ea1f  cmp     [rax+7CCh], edi
0x18005ea25  jz      short loc_18005EA3B
0x18005ea27  mov     r9d, edi; int
0x18005ea2a  mov     r8d, 3C6h; int
0x18005ea30  mov     rdx, r12; char *
0x18005ea33  mov     rcx, rax; this
0x18005ea36  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005ea3b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005ea42  jb      short loc_18005EA67
0x18005ea44  mov     edx, 58h ; 'X'
0x18005ea49  mov     [rsp+68h+var_48], edi
0x18005ea4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ea54  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x18005ea5b  mov     r9, rsi
0x18005ea5e  mov     rcx, [rcx+10h]
0x18005ea62  call    WPP_SF_qD
0x18005ea67  lea     rcx, [rsp+68h+arg_0]; this
0x18005ea6c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005ea71  mov     eax, ebx
0x18005ea73  mov     rbx, [rsp+68h+arg_8]
0x18005ea78  add     rsp, 40h
0x18005ea7c  pop     r14
0x18005ea7e  pop     r12
0x18005ea80  pop     rdi
0x18005ea81  pop     rsi
0x18005ea82  pop     rbp
0x18005ea83  retn
```
