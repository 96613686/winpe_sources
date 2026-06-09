# CWMPropHandlerBase::CreateProperty(_tagpropertykey const &,CMFProperty * *)

- ea: `0x180044a90`
- end: `0x180044ec6`
- name: `?CreateProperty@CWMPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAPEAVCMFProperty@@@Z`
- size: `1078`
- prototype: `int(CWMPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct CMFProperty **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x1800018a4`
- `0x180020398`
- `0x180020484`
- `0x18002b460`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003f518`
- `0x180044a90`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044b31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044bf0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044cab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044d52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044e15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044b31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044bf0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044cab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044d52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044e15`

## string_xrefs

- `0x180044aa3`: `CWMPropHandlerBase::CreateProperty`

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
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  CWMProperty *v17; // rax
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  CWMProperty *v26; // rax
  __int64 v27; // rdx
  struct CMFProperty *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v33[56]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v34; // [rsp+70h] [rbp+8h] BYREF
  int v35; // [rsp+88h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v34, "CWMPropHandlerBase::CreateProperty", 937);
  v34 = 0;
  v35 = 0;
  if ( !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find((char *)this + 1304, a2, &v34, v33) )
  {
    v26 = (CWMProperty *)operator new(0x90u);
    if ( v26 )
    {
      v8 = 0;
      v28 = CWMProperty::CWMProperty(v26, a2);
      *a3 = v28;
      if ( v28 )
        goto LABEL_66;
    }
    else
    {
      *a3 = 0;
    }
    v29 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMPropHandlerBase::CreateProperty", 966, -2147024882);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_66;
    v21 = 88;
    goto LABEL_65;
  }
  v6 = v34;
  v8 = (*(__int64 (__fastcall **)(__int64, void *, int *))(*(_QWORD *)v34 + 56LL))(v34, &MF_MD_PKEY_EXCEPTIONAL, &v35);
  if ( v8 < 0 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != v8 )
        CallStackContext::TraceFailure(v11, "CWMPropHandlerBase::CreateProperty", 945, v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 84;
LABEL_13:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, v8);
      goto LABEL_66;
    }
    goto LABEL_66;
  }
  if ( !v35 )
  {
    v17 = (CWMProperty *)operator new(0x90u);
    if ( v17 )
      v17 = CWMProperty::CWMProperty(v17, a2);
    *a3 = v17;
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
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != v8 )
            CallStackContext::TraceFailure(v25, "CWMPropHandlerBase::CreateProperty", 961, v8);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v12 = 87;
          goto LABEL_13;
        }
      }
      goto LABEL_66;
    }
    v18 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v20 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v20, "CWMPropHandlerBase::CreateProperty", 955, -2147024882);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_66;
    v21 = 86;
LABEL_65:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v21,
      &WPP_d497573e8d0434bb74893564de0342d6_Traceguids,
      this,
      -2147024882);
    goto LABEL_66;
  }
  v14 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
    CallStackTracing::s_wpInstance = v15;
    if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v14 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v14 + 8) )
  {
    v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
    if ( *((_DWORD *)v16 + 499) != v8 )
      CallStackContext::TraceFailure(v16, "CWMPropHandlerBase::CreateProperty", 948, v8);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v12 = 85;
    goto LABEL_13;
  }
LABEL_66:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v34);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180044a90  mov     [rsp+arg_8], rbx
0x180044a95  push    rbp
0x180044a96  push    rsi
0x180044a97  push    rdi
0x180044a98  push    r12
0x180044a9a  push    r14
0x180044a9c  sub     rsp, 40h
0x180044aa0  mov     rdi, r8
0x180044aa3  lea     r12, aCwmprophandler_10; "CWMPropHandlerBase::CreateProperty"
0x180044aaa  mov     rbp, rdx
0x180044aad  mov     rsi, rcx
0x180044ab0  mov     rdx, r12; char *
0x180044ab3  lea     rcx, [rsp+68h+arg_0]; this
0x180044ab8  mov     r8d, 3A9h; int
0x180044abe  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180044ac3  lea     rcx, [rsi+518h]
0x180044aca  mov     [rsp+68h+arg_0], 0
0x180044ad3  lea     r9, [rsp+68h+var_38]
0x180044ad8  mov     [rsp+68h+arg_18], 0
0x180044ae3  lea     r8, [rsp+68h+arg_0]
0x180044ae8  mov     rdx, rbp
0x180044aeb  call    ?Find@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Find(_tagpropertykey const &,CMFProperty * &,CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x180044af0  test    eax, eax
0x180044af2  jz      loc_180044DD1
0x180044af8  mov     r14, [rsp+68h+arg_0]
0x180044afd  lea     r8, [rsp+68h+arg_18]
0x180044b05  lea     rdx, MF_MD_PKEY_EXCEPTIONAL
0x180044b0c  mov     rcx, r14
0x180044b0f  mov     rax, [r14]
0x180044b12  mov     rax, [rax+38h]
0x180044b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b1b  mov     ebx, eax
0x180044b1d  test    eax, eax
0x180044b1f  jns     loc_180044BB4
0x180044b25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044b2c  test    rcx, rcx
0x180044b2f  jnz     short loc_180044B72
0x180044b31  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044b37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044b3e  mov     rcx, rax
0x180044b41  test    rax, rax
0x180044b44  jz      short loc_180044B64
0x180044b46  mov     rax, [rax]
0x180044b49  mov     edx, 7F0h
0x180044b4e  mov     rax, [rax+8]
0x180044b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b57  test    eax, eax
0x180044b59  jz      short loc_180044B64
0x180044b5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044b62  jmp     short loc_180044B72
0x180044b64  lea     rcx, qword_18006EB20; this
0x180044b6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044b72  cmp     byte ptr [rcx+8], 0
0x180044b76  jz      short loc_180044B99
0x180044b78  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044b7d  cmp     [rax+7CCh], ebx
0x180044b83  jz      short loc_180044B99
0x180044b85  mov     r9d, ebx; int
0x180044b88  mov     r8d, 3B1h; int
0x180044b8e  mov     rdx, r12; char *
0x180044b91  mov     rcx, rax; this
0x180044b94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044b99  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180044b9e  cmp     al, 1
0x180044ba0  jb      loc_180044EA9
0x180044ba6  mov     edx, 54h ; 'T'
0x180044bab  mov     [rsp+68h+var_48], ebx
0x180044baf  jmp     loc_180044E8F
0x180044bb4  cmp     [rsp+68h+arg_18], 0
0x180044bbc  jz      loc_180044C6F
0x180044bc2  mov     rax, [rsi]
0x180044bc5  mov     r8, rdi
0x180044bc8  mov     rdx, rbp
0x180044bcb  mov     rcx, rsi
0x180044bce  mov     rax, [rax+0A0h]
0x180044bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bda  mov     ebx, eax
0x180044bdc  test    eax, eax
0x180044bde  jns     loc_180044C8C
0x180044be4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044beb  test    rcx, rcx
0x180044bee  jnz     short loc_180044C31
0x180044bf0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044bf6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044bfd  mov     rcx, rax
0x180044c00  test    rax, rax
0x180044c03  jz      short loc_180044C23
0x180044c05  mov     rax, [rax]
0x180044c08  mov     edx, 7F0h
0x180044c0d  mov     rax, [rax+8]
0x180044c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c16  test    eax, eax
0x180044c18  jz      short loc_180044C23
0x180044c1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044c21  jmp     short loc_180044C31
0x180044c23  lea     rcx, qword_18006EB20; this
0x180044c2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044c31  cmp     byte ptr [rcx+8], 0
0x180044c35  jz      short loc_180044C58
0x180044c37  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044c3c  cmp     [rax+7CCh], ebx
0x180044c42  jz      short loc_180044C58
0x180044c44  mov     r9d, ebx; int
0x180044c47  mov     r8d, 3B4h; int
0x180044c4d  mov     rdx, r12; char *
0x180044c50  mov     rcx, rax; this
0x180044c53  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044c58  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180044c5d  cmp     al, 1
0x180044c5f  jb      loc_180044EA9
0x180044c65  mov     edx, 55h ; 'U'
0x180044c6a  jmp     loc_180044BAB
0x180044c6f  mov     ecx, 90h; Size
0x180044c74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044c79  test    rax, rax
0x180044c7c  jz      short loc_180044C89
0x180044c7e  mov     rdx, rbp; struct _tagpropertykey *
0x180044c81  mov     rcx, rax; this
0x180044c84  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x180044c89  mov     [rdi], rax
0x180044c8c  mov     rdx, [rdi]
0x180044c8f  test    rdx, rdx
0x180044c92  jnz     loc_180044D2A
0x180044c98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044c9f  mov     edi, 8007000Eh
0x180044ca4  mov     ebx, edi
0x180044ca6  test    rcx, rcx
0x180044ca9  jnz     short loc_180044CEC
0x180044cab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044cb1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044cb8  mov     rcx, rax
0x180044cbb  test    rax, rax
0x180044cbe  jz      short loc_180044CDE
0x180044cc0  mov     rax, [rax]
0x180044cc3  mov     edx, 7F0h
0x180044cc8  mov     rax, [rax+8]
0x180044ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044cd1  test    eax, eax
0x180044cd3  jz      short loc_180044CDE
0x180044cd5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044cdc  jmp     short loc_180044CEC
0x180044cde  lea     rcx, qword_18006EB20; this
0x180044ce5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044cec  cmp     byte ptr [rcx+8], 0
0x180044cf0  jz      short loc_180044D13
0x180044cf2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044cf7  cmp     [rax+7CCh], edi
0x180044cfd  jz      short loc_180044D13
0x180044cff  mov     r9d, edi; int
0x180044d02  mov     r8d, 3BBh; int
0x180044d08  mov     rdx, r12; char *
0x180044d0b  mov     rcx, rax; this
0x180044d0e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044d13  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180044d18  cmp     al, 1
0x180044d1a  jb      loc_180044EA9
0x180044d20  mov     edx, 56h ; 'V'
0x180044d25  jmp     loc_180044E8B
0x180044d2a  mov     rax, [r14]
0x180044d2d  mov     rcx, r14
0x180044d30  mov     rax, [rax+100h]
0x180044d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d3c  mov     ebx, eax
0x180044d3e  test    eax, eax
0x180044d40  jns     loc_180044EA9
0x180044d46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044d4d  test    rcx, rcx
0x180044d50  jnz     short loc_180044D93
0x180044d52  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044d58  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044d5f  mov     rcx, rax
0x180044d62  test    rax, rax
0x180044d65  jz      short loc_180044D85
0x180044d67  mov     rax, [rax]
0x180044d6a  mov     edx, 7F0h
0x180044d6f  mov     rax, [rax+8]
0x180044d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d78  test    eax, eax
0x180044d7a  jz      short loc_180044D85
0x180044d7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044d83  jmp     short loc_180044D93
0x180044d85  lea     rcx, qword_18006EB20; this
0x180044d8c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044d93  cmp     byte ptr [rcx+8], 0
0x180044d97  jz      short loc_180044DBA
0x180044d99  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044d9e  cmp     [rax+7CCh], ebx
0x180044da4  jz      short loc_180044DBA
0x180044da6  mov     r9d, ebx; int
0x180044da9  mov     r8d, 3C1h; int
0x180044daf  mov     rdx, r12; char *
0x180044db2  mov     rcx, rax; this
0x180044db5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044dba  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180044dbf  cmp     al, 1
0x180044dc1  jb      loc_180044EA9
0x180044dc7  mov     edx, 57h ; 'W'
0x180044dcc  jmp     loc_180044BAB
0x180044dd1  mov     ecx, 90h; Size
0x180044dd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044ddb  test    rax, rax
0x180044dde  jz      short loc_180044DFB
0x180044de0  mov     rdx, rbp; struct _tagpropertykey *
0x180044de3  mov     rcx, rax; this
0x180044de6  xor     ebx, ebx
0x180044de8  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x180044ded  mov     [rdi], rax
0x180044df0  test    rax, rax
0x180044df3  jnz     loc_180044EA9
0x180044df9  jmp     short loc_180044E02
0x180044dfb  mov     qword ptr [rdi], 0
0x180044e02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044e09  mov     edi, 8007000Eh
0x180044e0e  mov     ebx, edi
0x180044e10  test    rcx, rcx
0x180044e13  jnz     short loc_180044E56
0x180044e15  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044e1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044e22  mov     rcx, rax
0x180044e25  test    rax, rax
0x180044e28  jz      short loc_180044E48
0x180044e2a  mov     rax, [rax]
0x180044e2d  mov     edx, 7F0h
0x180044e32  mov     rax, [rax+8]
0x180044e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e3b  test    eax, eax
0x180044e3d  jz      short loc_180044E48
0x180044e3f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044e46  jmp     short loc_180044E56
0x180044e48  lea     rcx, qword_18006EB20; this
0x180044e4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044e56  cmp     byte ptr [rcx+8], 0
0x180044e5a  jz      short loc_180044E7D
0x180044e5c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044e61  cmp     [rax+7CCh], edi
0x180044e67  jz      short loc_180044E7D
0x180044e69  mov     r9d, edi; int
0x180044e6c  mov     r8d, 3C6h; int
0x180044e72  mov     rdx, r12; char *
0x180044e75  mov     rcx, rax; this
0x180044e78  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044e7d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180044e82  cmp     al, 1
0x180044e84  jb      short loc_180044EA9
0x180044e86  mov     edx, 58h ; 'X'
0x180044e8b  mov     [rsp+68h+var_48], edi
0x180044e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180044e96  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x180044e9d  mov     r9, rsi
0x180044ea0  mov     rcx, [rcx+10h]
0x180044ea4  call    WPP_SF_qd
0x180044ea9  lea     rcx, [rsp+68h+arg_0]; this
0x180044eae  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180044eb3  mov     eax, ebx
0x180044eb5  mov     rbx, [rsp+68h+arg_8]
0x180044eba  add     rsp, 40h
0x180044ebe  pop     r14
0x180044ec0  pop     r12
0x180044ec2  pop     rdi
0x180044ec3  pop     rsi
0x180044ec4  pop     rbp
0x180044ec5  retn
```
