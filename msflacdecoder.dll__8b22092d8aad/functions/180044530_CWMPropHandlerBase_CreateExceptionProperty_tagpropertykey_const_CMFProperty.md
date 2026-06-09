# CWMPropHandlerBase::CreateExceptionProperty(_tagpropertykey const &,CMFProperty * *)

- ea: `0x180044530`
- end: `0x18004479c`
- name: `?CreateExceptionProperty@CWMPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAPEAVCMFProperty@@@Z`
- size: `620`
- prototype: `int(CWMPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct CMFProperty **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18002ae60`

## callees

- `0x1800018a4`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003f518`
- `0x180044530`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800446e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800446e5`

## string_xrefs

- `0x18004454b`: `CWMPropHandlerBase::CreateExceptionProperty`
- `0x18004473c`: `CWMPropHandlerBase::CreateExceptionProperty`

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
  CWMProperty *v11; // rbx
  void **v12; // rax
  __int64 v13; // rax
  CWMProperty *v14; // rax
  __int64 v15; // rax
  CWMProperty *v16; // rax
  __int64 v17; // rax
  CWMProperty *v18; // rax
  CWMProperty *v19; // rax
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v24; // [rsp+58h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v24,
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
    v13 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_ThumbnailStream.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_ThumbnailStream.fmtid.Data1 )
      v13 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_ThumbnailStream.fmtid.Data4;
    if ( v13 )
    {
LABEL_17:
      if ( pid != PKEY_Rating.pid )
        goto LABEL_23;
      v15 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Rating.fmtid.Data1;
      if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Rating.fmtid.Data1 )
        v15 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Rating.fmtid.Data4;
      if ( v15 )
      {
LABEL_23:
        if ( pid != PKEY_Media_DateEncoded.pid )
          goto LABEL_26;
        v17 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Media_DateEncoded.fmtid.Data1;
        if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Media_DateEncoded.fmtid.Data1 )
          v17 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Media_DateEncoded.fmtid.Data4;
        if ( v17 )
        {
LABEL_26:
          v19 = (CWMProperty *)operator new(0x90u);
          if ( v19 )
          {
            v11 = CWMProperty::CWMProperty(v19, a2);
            goto LABEL_29;
          }
        }
        else
        {
          v18 = (CWMProperty *)operator new(0x90u);
          v11 = v18;
          if ( v18 )
          {
            CWMProperty::CWMProperty(v18, a2);
            v12 = &CWMEncodingTimeProperty::`vftable';
            goto LABEL_7;
          }
        }
      }
      else
      {
        v16 = (CWMProperty *)operator new(0x90u);
        v11 = v16;
        if ( v16 )
        {
          CWMProperty::CWMProperty(v16, a2);
          v12 = &CWMRatingProperty::`vftable';
          goto LABEL_7;
        }
      }
    }
    else
    {
      v14 = (CWMProperty *)operator new(0x90u);
      v11 = v14;
      if ( v14 )
      {
        CWMProperty::CWMProperty(v14, a2);
        v12 = &CWMThumbnailStreamProperty::`vftable';
        goto LABEL_7;
      }
    }
  }
  else
  {
    v9 = (CWMProperty *)operator new(0x90u);
    v11 = v9;
    if ( v9 )
    {
      CWMProperty::CWMProperty(v9, a2);
      v12 = &CWMMCDIProperty::`vftable';
LABEL_7:
      *(_QWORD *)v11 = v12;
      goto LABEL_29;
    }
  }
  v11 = 0;
LABEL_29:
  *a3 = v11;
  if ( !v11 )
  {
    v20 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMPropHandlerBase::CreateExceptionProperty",
          1003,
          -2147024882);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        WPP_d497573e8d0434bb74893564de0342d6_Traceguids,
        this,
        -2147024882);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
  return v7;
}

```

## disassembly

```asm
0x180044530  mov     [rsp+arg_0], rbx
0x180044535  mov     [rsp+arg_10], rbp
0x18004453a  push    rsi
0x18004453b  push    rdi
0x18004453c  push    r14
0x18004453e  sub     rsp, 30h
0x180044542  mov     r14, r8
0x180044545  mov     rdi, rdx
0x180044548  mov     rbp, rcx
0x18004454b  lea     rdx, aCwmprophandler_15; "CWMPropHandlerBase::CreateExceptionProp"...
0x180044552  mov     r8d, 3D2h; int
0x180044558  lea     rcx, [rsp+48h+arg_8]; this
0x18004455d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180044562  mov     edx, [rdi+10h]
0x180044565  xor     esi, esi
0x180044567  cmp     edx, cs:PKEY_Media_MCDI.pid
0x18004456d  jnz     short loc_1800445BB
0x18004456f  mov     rax, [rdi]
0x180044572  sub     rax, qword ptr cs:PKEY_Media_MCDI.fmtid.Data1
0x180044579  jnz     short loc_180044586
0x18004457b  mov     rax, [rdi+8]
0x18004457f  sub     rax, qword ptr cs:PKEY_Media_MCDI.fmtid.Data4
0x180044586  test    rax, rax
0x180044589  jnz     short loc_1800445BB
0x18004458b  mov     ecx, 90h; Size
0x180044590  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044595  mov     rbx, rax
0x180044598  test    rax, rax
0x18004459b  jz      loc_1800446C6
0x1800445a1  mov     rdx, rdi; struct _tagpropertykey *
0x1800445a4  mov     rcx, rax; this
0x1800445a7  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x1800445ac  lea     rax, ??_7CWMMCDIProperty@@6B@; const CWMMCDIProperty::`vftable'
0x1800445b3  mov     [rbx], rax
0x1800445b6  jmp     loc_1800446C8
0x1800445bb  cmp     edx, cs:PKEY_ThumbnailStream.pid
0x1800445c1  jnz     short loc_180044609
0x1800445c3  mov     rax, [rdi]
0x1800445c6  sub     rax, qword ptr cs:PKEY_ThumbnailStream.fmtid.Data1
0x1800445cd  jnz     short loc_1800445DA
0x1800445cf  mov     rax, [rdi+8]
0x1800445d3  sub     rax, qword ptr cs:PKEY_ThumbnailStream.fmtid.Data4
0x1800445da  test    rax, rax
0x1800445dd  jnz     short loc_180044609
0x1800445df  mov     ecx, 90h; Size
0x1800445e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800445e9  mov     rbx, rax
0x1800445ec  test    rax, rax
0x1800445ef  jz      loc_1800446C6
0x1800445f5  mov     rdx, rdi; struct _tagpropertykey *
0x1800445f8  mov     rcx, rax; this
0x1800445fb  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x180044600  lea     rax, ??_7CWMThumbnailStreamProperty@@6B@; const CWMThumbnailStreamProperty::`vftable'
0x180044607  jmp     short loc_1800445B3
0x180044609  cmp     edx, cs:PKEY_Rating.pid
0x18004460f  jnz     short loc_18004465A
0x180044611  mov     rax, [rdi]
0x180044614  sub     rax, qword ptr cs:PKEY_Rating.fmtid.Data1
0x18004461b  jnz     short loc_180044628
0x18004461d  mov     rax, [rdi+8]
0x180044621  sub     rax, qword ptr cs:PKEY_Rating.fmtid.Data4
0x180044628  test    rax, rax
0x18004462b  jnz     short loc_18004465A
0x18004462d  mov     ecx, 90h; Size
0x180044632  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044637  mov     rbx, rax
0x18004463a  test    rax, rax
0x18004463d  jz      loc_1800446C6
0x180044643  mov     rdx, rdi; struct _tagpropertykey *
0x180044646  mov     rcx, rax; this
0x180044649  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18004464e  lea     rax, ??_7CWMRatingProperty@@6B@; const CWMRatingProperty::`vftable'
0x180044655  jmp     loc_1800445B3
0x18004465a  cmp     edx, cs:PKEY_Media_DateEncoded.pid
0x180044660  jnz     short loc_1800446A7
0x180044662  mov     rax, [rdi]
0x180044665  sub     rax, qword ptr cs:PKEY_Media_DateEncoded.fmtid.Data1
0x18004466c  jnz     short loc_180044679
0x18004466e  mov     rax, [rdi+8]
0x180044672  sub     rax, qword ptr cs:PKEY_Media_DateEncoded.fmtid.Data4
0x180044679  test    rax, rax
0x18004467c  jnz     short loc_1800446A7
0x18004467e  mov     ecx, 90h; Size
0x180044683  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044688  mov     rbx, rax
0x18004468b  test    rax, rax
0x18004468e  jz      short loc_1800446C6
0x180044690  mov     rdx, rdi; struct _tagpropertykey *
0x180044693  mov     rcx, rax; this
0x180044696  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x18004469b  lea     rax, ??_7CWMEncodingTimeProperty@@6B@; const CWMEncodingTimeProperty::`vftable'
0x1800446a2  jmp     loc_1800445B3
0x1800446a7  mov     ecx, 90h; Size
0x1800446ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800446b1  test    rax, rax
0x1800446b4  jz      short loc_1800446C6
0x1800446b6  mov     rdx, rdi; struct _tagpropertykey *
0x1800446b9  mov     rcx, rax; this
0x1800446bc  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x1800446c1  mov     rbx, rax
0x1800446c4  jmp     short loc_1800446C8
0x1800446c6  xor     ebx, ebx
0x1800446c8  mov     [r14], rbx
0x1800446cb  test    rbx, rbx
0x1800446ce  jnz     loc_18004477D
0x1800446d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800446db  mov     esi, 8007000Eh
0x1800446e0  test    rcx, rcx
0x1800446e3  jnz     short loc_180044726
0x1800446e5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800446eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800446f2  mov     rcx, rax
0x1800446f5  test    rax, rax
0x1800446f8  jz      short loc_180044718
0x1800446fa  mov     rax, [rax]
0x1800446fd  mov     edx, 7F0h
0x180044702  mov     rax, [rax+8]
0x180044706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004470b  test    eax, eax
0x18004470d  jz      short loc_180044718
0x18004470f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044716  jmp     short loc_180044726
0x180044718  lea     rcx, qword_18006EB20; this
0x18004471f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044726  cmp     byte ptr [rcx+8], 0
0x18004472a  jz      short loc_180044751
0x18004472c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044731  cmp     [rax+7CCh], esi
0x180044737  jz      short loc_180044751
0x180044739  mov     r9d, esi; int
0x18004473c  lea     rdx, aCwmprophandler_15; "CWMPropHandlerBase::CreateExceptionProp"...
0x180044743  mov     r8d, 3EBh; int
0x180044749  mov     rcx, rax; this
0x18004474c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044751  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180044756  cmp     al, 1
0x180044758  jb      short loc_18004477D
0x18004475a  mov     rcx, cs:WPP_GLOBAL_Control
0x180044761  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x180044768  mov     edx, 59h ; 'Y'
0x18004476d  mov     [rsp+48h+var_28], esi
0x180044771  mov     r9, rbp
0x180044774  mov     rcx, [rcx+10h]
0x180044778  call    WPP_SF_qd
0x18004477d  lea     rcx, [rsp+48h+arg_8]; this
0x180044782  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180044787  mov     rbx, [rsp+48h+arg_0]
0x18004478c  mov     eax, esi
0x18004478e  mov     rbp, [rsp+48h+arg_10]
0x180044793  add     rsp, 30h
0x180044797  pop     r14
0x180044799  pop     rdi
0x18004479a  pop     rsi
0x18004479b  retn
```
