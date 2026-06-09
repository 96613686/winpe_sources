# CWMPropHandlerBase::CreateExceptionProperty(_tagpropertykey const &,CMFProperty * *)

- ea: `0x18005b960`
- end: `0x18005bbcc`
- name: `?CreateExceptionProperty@CWMPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAPEAVCMFProperty@@@Z`
- size: `620`
- prototype: `int(CWMPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct CMFProperty **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180001f90`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180056970`
- `0x18005b960`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005bb15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005bb15`

## string_xrefs

- `0x18005b97b`: `CWMPropHandlerBase::CreateExceptionProperty`
- `0x18005bb6c`: `CWMPropHandlerBase::CreateExceptionProperty`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::CreateExceptionProperty(
        CWMPropHandlerBase *this,
        const struct _tagpropertykey *a2,
        struct CMFProperty **a3)
{
  DWORD pid; // edx
  unsigned int v7; // esi
  __int64 v8; // rax
  CWMProperty *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  CWMProperty *v13; // rbx
  void **v14; // rax
  __int64 v15; // rax
  CWMProperty *v16; // rax
  __int64 v17; // rax
  CWMProperty *v18; // rax
  __int64 v19; // rax
  CWMProperty *v20; // rax
  CWMProperty *v21; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v26; // [rsp+58h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v26,
    "CWMPropHandlerBase::CreateExceptionProperty",
    978);
  pid = a2->pid;
  v7 = 0;
  if ( pid != PKEY_Media_MCDI.pid )
    goto LABEL_11;
  v8 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Media_MCDI.fmtid.Data1;
  if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Media_MCDI.fmtid.Data1 )
    v8 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Media_MCDI.fmtid.Data4;
  if ( v8 )
  {
LABEL_11:
    if ( pid != PKEY_ThumbnailStream.pid )
      goto LABEL_17;
    v15 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_ThumbnailStream.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_ThumbnailStream.fmtid.Data1 )
      v15 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_ThumbnailStream.fmtid.Data4;
    if ( v15 )
    {
LABEL_17:
      if ( pid != PKEY_Rating.pid )
        goto LABEL_23;
      v17 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Rating.fmtid.Data1;
      if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Rating.fmtid.Data1 )
        v17 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Rating.fmtid.Data4;
      if ( v17 )
      {
LABEL_23:
        if ( pid != PKEY_Media_DateEncoded.pid )
          goto LABEL_26;
        v19 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Media_DateEncoded.fmtid.Data1;
        if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Media_DateEncoded.fmtid.Data1 )
          v19 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Media_DateEncoded.fmtid.Data4;
        if ( v19 )
        {
LABEL_26:
          v21 = (CWMProperty *)operator new(0x90u);
          if ( v21 )
          {
            v13 = CWMProperty::CWMProperty(v21, a2);
            goto LABEL_29;
          }
        }
        else
        {
          v20 = (CWMProperty *)operator new(0x90u);
          v13 = v20;
          if ( v20 )
          {
            CWMProperty::CWMProperty(v20, a2);
            v14 = &CWMEncodingTimeProperty::`vftable';
            goto LABEL_7;
          }
        }
      }
      else
      {
        v18 = (CWMProperty *)operator new(0x90u);
        v13 = v18;
        if ( v18 )
        {
          CWMProperty::CWMProperty(v18, a2);
          v14 = &CWMRatingProperty::`vftable';
          goto LABEL_7;
        }
      }
    }
    else
    {
      v16 = (CWMProperty *)operator new(0x90u);
      v13 = v16;
      if ( v16 )
      {
        CWMProperty::CWMProperty(v16, a2);
        v14 = &CWMThumbnailStreamProperty::`vftable';
        goto LABEL_7;
      }
    }
  }
  else
  {
    v9 = (CWMProperty *)operator new(0x90u);
    v13 = v9;
    if ( v9 )
    {
      CWMProperty::CWMProperty(v9, a2);
      v14 = &CWMMCDIProperty::`vftable';
LABEL_7:
      *(_QWORD *)v13 = v14;
      goto LABEL_29;
    }
  }
  v13 = 0;
LABEL_29:
  *a3 = v13;
  if ( !v13 )
  {
    v22 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMPropHandlerBase::CreateExceptionProperty",
          1003,
          -2147024882);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        WPP_d497573e8d0434bb74893564de0342d6_Traceguids,
        this,
        -2147024882);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v26);
  return v7;
}

```

## disassembly

```asm
0x18005b960  mov     [rsp+arg_0], rbx
0x18005b965  mov     [rsp+arg_10], rbp
0x18005b96a  push    rsi
0x18005b96b  push    rdi
0x18005b96c  push    r14
0x18005b96e  sub     rsp, 30h
0x18005b972  mov     r14, r8
0x18005b975  mov     rdi, rdx
0x18005b978  mov     rbp, rcx
0x18005b97b  lea     rdx, aCwmprophandler_15; "CWMPropHandlerBase::CreateExceptionProp"...
0x18005b982  mov     r8d, 3D2h; int
0x18005b988  lea     rcx, [rsp+48h+arg_8]; this
0x18005b98d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005b992  mov     edx, [rdi+10h]
0x18005b995  xor     esi, esi
0x18005b997  cmp     edx, cs:PKEY_Media_MCDI.pid
0x18005b99d  jnz     short loc_18005B9EB
0x18005b99f  mov     rax, [rdi]
0x18005b9a2  sub     rax, qword ptr cs:PKEY_Media_MCDI.fmtid.Data1
0x18005b9a9  jnz     short loc_18005B9B6
0x18005b9ab  mov     rax, [rdi+8]
0x18005b9af  sub     rax, qword ptr cs:PKEY_Media_MCDI.fmtid.Data4
0x18005b9b6  test    rax, rax
0x18005b9b9  jnz     short loc_18005B9EB
0x18005b9bb  mov     ecx, 90h; Size
0x18005b9c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005b9c5  mov     rbx, rax
0x18005b9c8  test    rax, rax
0x18005b9cb  jz      loc_18005BAF6
0x18005b9d1  mov     rdx, rdi; struct _tagpropertykey *
0x18005b9d4  mov     rcx, rax; this
0x18005b9d7  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005b9dc  lea     rax, ??_7CWMMCDIProperty@@6B@; const CWMMCDIProperty::`vftable'
0x18005b9e3  mov     [rbx], rax
0x18005b9e6  jmp     loc_18005BAF8
0x18005b9eb  cmp     edx, cs:PKEY_ThumbnailStream.pid
0x18005b9f1  jnz     short loc_18005BA39
0x18005b9f3  mov     rax, [rdi]
0x18005b9f6  sub     rax, qword ptr cs:PKEY_ThumbnailStream.fmtid.Data1
0x18005b9fd  jnz     short loc_18005BA0A
0x18005b9ff  mov     rax, [rdi+8]
0x18005ba03  sub     rax, qword ptr cs:PKEY_ThumbnailStream.fmtid.Data4
0x18005ba0a  test    rax, rax
0x18005ba0d  jnz     short loc_18005BA39
0x18005ba0f  mov     ecx, 90h; Size
0x18005ba14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005ba19  mov     rbx, rax
0x18005ba1c  test    rax, rax
0x18005ba1f  jz      loc_18005BAF6
0x18005ba25  mov     rdx, rdi; struct _tagpropertykey *
0x18005ba28  mov     rcx, rax; this
0x18005ba2b  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005ba30  lea     rax, ??_7CWMThumbnailStreamProperty@@6B@; const CWMThumbnailStreamProperty::`vftable'
0x18005ba37  jmp     short loc_18005B9E3
0x18005ba39  cmp     edx, cs:PKEY_Rating.pid
0x18005ba3f  jnz     short loc_18005BA8A
0x18005ba41  mov     rax, [rdi]
0x18005ba44  sub     rax, qword ptr cs:PKEY_Rating.fmtid.Data1
0x18005ba4b  jnz     short loc_18005BA58
0x18005ba4d  mov     rax, [rdi+8]
0x18005ba51  sub     rax, qword ptr cs:PKEY_Rating.fmtid.Data4
0x18005ba58  test    rax, rax
0x18005ba5b  jnz     short loc_18005BA8A
0x18005ba5d  mov     ecx, 90h; Size
0x18005ba62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005ba67  mov     rbx, rax
0x18005ba6a  test    rax, rax
0x18005ba6d  jz      loc_18005BAF6
0x18005ba73  mov     rdx, rdi; struct _tagpropertykey *
0x18005ba76  mov     rcx, rax; this
0x18005ba79  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005ba7e  lea     rax, ??_7CWMRatingProperty@@6B@; const CWMRatingProperty::`vftable'
0x18005ba85  jmp     loc_18005B9E3
0x18005ba8a  cmp     edx, cs:PKEY_Media_DateEncoded.pid
0x18005ba90  jnz     short loc_18005BAD7
0x18005ba92  mov     rax, [rdi]
0x18005ba95  sub     rax, qword ptr cs:PKEY_Media_DateEncoded.fmtid.Data1
0x18005ba9c  jnz     short loc_18005BAA9
0x18005ba9e  mov     rax, [rdi+8]
0x18005baa2  sub     rax, qword ptr cs:PKEY_Media_DateEncoded.fmtid.Data4
0x18005baa9  test    rax, rax
0x18005baac  jnz     short loc_18005BAD7
0x18005baae  mov     ecx, 90h; Size
0x18005bab3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005bab8  mov     rbx, rax
0x18005babb  test    rax, rax
0x18005babe  jz      short loc_18005BAF6
0x18005bac0  mov     rdx, rdi; struct _tagpropertykey *
0x18005bac3  mov     rcx, rax; this
0x18005bac6  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005bacb  lea     rax, ??_7CWMEncodingTimeProperty@@6B@; const CWMEncodingTimeProperty::`vftable'
0x18005bad2  jmp     loc_18005B9E3
0x18005bad7  mov     ecx, 90h; Size
0x18005badc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005bae1  test    rax, rax
0x18005bae4  jz      short loc_18005BAF6
0x18005bae6  mov     rdx, rdi; struct _tagpropertykey *
0x18005bae9  mov     rcx, rax; this
0x18005baec  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005baf1  mov     rbx, rax
0x18005baf4  jmp     short loc_18005BAF8
0x18005baf6  xor     ebx, ebx
0x18005baf8  mov     [r14], rbx
0x18005bafb  test    rbx, rbx
0x18005bafe  jnz     loc_18005BBAD
0x18005bb04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005bb0b  mov     esi, 8007000Eh
0x18005bb10  test    rcx, rcx
0x18005bb13  jnz     short loc_18005BB56
0x18005bb15  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005bb1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005bb22  mov     rcx, rax
0x18005bb25  test    rax, rax
0x18005bb28  jz      short loc_18005BB48
0x18005bb2a  mov     rax, [rax]
0x18005bb2d  mov     edx, 7F0h
0x18005bb32  mov     rax, [rax+8]
0x18005bb36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb3b  test    eax, eax
0x18005bb3d  jz      short loc_18005BB48
0x18005bb3f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005bb46  jmp     short loc_18005BB56
0x18005bb48  lea     rcx, qword_1800D6F70; this
0x18005bb4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005bb56  cmp     byte ptr [rcx+8], 0
0x18005bb5a  jz      short loc_18005BB81
0x18005bb5c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005bb61  cmp     [rax+7CCh], esi
0x18005bb67  jz      short loc_18005BB81
0x18005bb69  mov     r9d, esi; int
0x18005bb6c  lea     rdx, aCwmprophandler_15; "CWMPropHandlerBase::CreateExceptionProp"...
0x18005bb73  mov     r8d, 3EBh; int
0x18005bb79  mov     rcx, rax; this
0x18005bb7c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005bb81  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005bb88  jb      short loc_18005BBAD
0x18005bb8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb91  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x18005bb98  mov     edx, 59h ; 'Y'
0x18005bb9d  mov     [rsp+48h+var_28], esi
0x18005bba1  mov     r9, rbp
0x18005bba4  mov     rcx, [rcx+10h]
0x18005bba8  call    WPP_SF_qD
0x18005bbad  lea     rcx, [rsp+48h+arg_8]; this
0x18005bbb2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005bbb7  mov     rbx, [rsp+48h+arg_0]
0x18005bbbc  mov     eax, esi
0x18005bbbe  mov     rbp, [rsp+48h+arg_10]
0x18005bbc3  add     rsp, 30h
0x18005bbc7  pop     r14
0x18005bbc9  pop     rdi
0x18005bbca  pop     rsi
0x18005bbcb  retn
```
