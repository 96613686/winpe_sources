# CWMPropHandlerBase::CreateExceptionProperty(_tagpropertykey const &,CMFProperty * *)

- ea: `0x18005e090`
- end: `0x18005e303`
- name: `?CreateExceptionProperty@CWMPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAPEAVCMFProperty@@@Z`
- size: `627`
- prototype: `int(CWMPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct CMFProperty **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180001fb0`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180058e58`
- `0x18005e090`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e245`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e245`

## string_xrefs

- `0x18005e0ab`: `CWMPropHandlerBase::CreateExceptionProperty`
- `0x18005e2a2`: `CWMPropHandlerBase::CreateExceptionProperty`

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
        v22 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        &WPP_d497573e8d0434bb74893564de0342d6_Traceguids,
        this,
        -2147024882);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v26);
  return v7;
}

```

## disassembly

```asm
0x18005e090  mov     [rsp+arg_0], rbx
0x18005e095  mov     [rsp+arg_10], rbp
0x18005e09a  push    rsi
0x18005e09b  push    rdi
0x18005e09c  push    r14
0x18005e09e  sub     rsp, 30h
0x18005e0a2  mov     r14, r8
0x18005e0a5  mov     rdi, rdx
0x18005e0a8  mov     rbp, rcx
0x18005e0ab  lea     rdx, aCwmprophandler_15; "CWMPropHandlerBase::CreateExceptionProp"...
0x18005e0b2  mov     r8d, 3D2h; int
0x18005e0b8  lea     rcx, [rsp+48h+arg_8]; this
0x18005e0bd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005e0c2  mov     edx, [rdi+10h]
0x18005e0c5  xor     esi, esi
0x18005e0c7  cmp     edx, cs:PKEY_Media_MCDI.pid
0x18005e0cd  jnz     short loc_18005E11B
0x18005e0cf  mov     rax, [rdi]
0x18005e0d2  sub     rax, qword ptr cs:PKEY_Media_MCDI.fmtid.Data1
0x18005e0d9  jnz     short loc_18005E0E6
0x18005e0db  mov     rax, [rdi+8]
0x18005e0df  sub     rax, qword ptr cs:PKEY_Media_MCDI.fmtid.Data4
0x18005e0e6  test    rax, rax
0x18005e0e9  jnz     short loc_18005E11B
0x18005e0eb  mov     ecx, 90h; Size
0x18005e0f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e0f5  mov     rbx, rax
0x18005e0f8  test    rax, rax
0x18005e0fb  jz      loc_18005E226
0x18005e101  mov     rdx, rdi; struct _tagpropertykey *
0x18005e104  mov     rcx, rax; this
0x18005e107  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005e10c  lea     rax, ??_7CWMMCDIProperty@@6B@; const CWMMCDIProperty::`vftable'
0x18005e113  mov     [rbx], rax
0x18005e116  jmp     loc_18005E228
0x18005e11b  cmp     edx, cs:PKEY_ThumbnailStream.pid
0x18005e121  jnz     short loc_18005E169
0x18005e123  mov     rax, [rdi]
0x18005e126  sub     rax, qword ptr cs:PKEY_ThumbnailStream.fmtid.Data1
0x18005e12d  jnz     short loc_18005E13A
0x18005e12f  mov     rax, [rdi+8]
0x18005e133  sub     rax, qword ptr cs:PKEY_ThumbnailStream.fmtid.Data4
0x18005e13a  test    rax, rax
0x18005e13d  jnz     short loc_18005E169
0x18005e13f  mov     ecx, 90h; Size
0x18005e144  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e149  mov     rbx, rax
0x18005e14c  test    rax, rax
0x18005e14f  jz      loc_18005E226
0x18005e155  mov     rdx, rdi; struct _tagpropertykey *
0x18005e158  mov     rcx, rax; this
0x18005e15b  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005e160  lea     rax, ??_7CWMThumbnailStreamProperty@@6B@; const CWMThumbnailStreamProperty::`vftable'
0x18005e167  jmp     short loc_18005E113
0x18005e169  cmp     edx, cs:PKEY_Rating.pid
0x18005e16f  jnz     short loc_18005E1BA
0x18005e171  mov     rax, [rdi]
0x18005e174  sub     rax, qword ptr cs:PKEY_Rating.fmtid.Data1
0x18005e17b  jnz     short loc_18005E188
0x18005e17d  mov     rax, [rdi+8]
0x18005e181  sub     rax, qword ptr cs:PKEY_Rating.fmtid.Data4
0x18005e188  test    rax, rax
0x18005e18b  jnz     short loc_18005E1BA
0x18005e18d  mov     ecx, 90h; Size
0x18005e192  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e197  mov     rbx, rax
0x18005e19a  test    rax, rax
0x18005e19d  jz      loc_18005E226
0x18005e1a3  mov     rdx, rdi; struct _tagpropertykey *
0x18005e1a6  mov     rcx, rax; this
0x18005e1a9  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005e1ae  lea     rax, ??_7CWMRatingProperty@@6B@; const CWMRatingProperty::`vftable'
0x18005e1b5  jmp     loc_18005E113
0x18005e1ba  cmp     edx, cs:PKEY_Media_DateEncoded.pid
0x18005e1c0  jnz     short loc_18005E207
0x18005e1c2  mov     rax, [rdi]
0x18005e1c5  sub     rax, qword ptr cs:PKEY_Media_DateEncoded.fmtid.Data1
0x18005e1cc  jnz     short loc_18005E1D9
0x18005e1ce  mov     rax, [rdi+8]
0x18005e1d2  sub     rax, qword ptr cs:PKEY_Media_DateEncoded.fmtid.Data4
0x18005e1d9  test    rax, rax
0x18005e1dc  jnz     short loc_18005E207
0x18005e1de  mov     ecx, 90h; Size
0x18005e1e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e1e8  mov     rbx, rax
0x18005e1eb  test    rax, rax
0x18005e1ee  jz      short loc_18005E226
0x18005e1f0  mov     rdx, rdi; struct _tagpropertykey *
0x18005e1f3  mov     rcx, rax; this
0x18005e1f6  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005e1fb  lea     rax, ??_7CWMEncodingTimeProperty@@6B@; const CWMEncodingTimeProperty::`vftable'
0x18005e202  jmp     loc_18005E113
0x18005e207  mov     ecx, 90h; Size
0x18005e20c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e211  test    rax, rax
0x18005e214  jz      short loc_18005E226
0x18005e216  mov     rdx, rdi; struct _tagpropertykey *
0x18005e219  mov     rcx, rax; this
0x18005e21c  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18005e221  mov     rbx, rax
0x18005e224  jmp     short loc_18005E228
0x18005e226  xor     ebx, ebx
0x18005e228  mov     [r14], rbx
0x18005e22b  test    rbx, rbx
0x18005e22e  jnz     loc_18005E2E3
0x18005e234  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e23b  mov     esi, 8007000Eh
0x18005e240  test    rcx, rcx
0x18005e243  jnz     short loc_18005E28C
0x18005e245  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005e24c  nop     dword ptr [rax+rax+00h]
0x18005e251  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e258  mov     rcx, rax
0x18005e25b  test    rax, rax
0x18005e25e  jz      short loc_18005E27E
0x18005e260  mov     rax, [rax]
0x18005e263  mov     edx, 7F0h
0x18005e268  mov     rax, [rax+8]
0x18005e26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e271  test    eax, eax
0x18005e273  jz      short loc_18005E27E
0x18005e275  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e27c  jmp     short loc_18005E28C
0x18005e27e  lea     rcx, qword_1800DBF70; this
0x18005e285  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e28c  cmp     byte ptr [rcx+8], 0
0x18005e290  jz      short loc_18005E2B7
0x18005e292  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e297  cmp     [rax+7CCh], esi
0x18005e29d  jz      short loc_18005E2B7
0x18005e29f  mov     r9d, esi; int
0x18005e2a2  lea     rdx, aCwmprophandler_15; "CWMPropHandlerBase::CreateExceptionProp"...
0x18005e2a9  mov     r8d, 3EBh; int
0x18005e2af  mov     rcx, rax; this
0x18005e2b2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e2b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e2be  jb      short loc_18005E2E3
0x18005e2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e2c7  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x18005e2ce  mov     edx, 59h ; 'Y'
0x18005e2d3  mov     [rsp+48h+var_28], esi
0x18005e2d7  mov     r9, rbp
0x18005e2da  mov     rcx, [rcx+10h]
0x18005e2de  call    WPP_SF_qD
0x18005e2e3  lea     rcx, [rsp+48h+arg_8]; this
0x18005e2e8  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005e2ed  mov     rbx, [rsp+48h+arg_0]
0x18005e2f2  mov     eax, esi
0x18005e2f4  mov     rbp, [rsp+48h+arg_10]
0x18005e2f9  add     rsp, 30h
0x18005e2fd  pop     r14
0x18005e2ff  pop     rdi
0x18005e300  pop     rsi
0x18005e301  retn
```
