# CWMThumbnailStreamProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x1800543d0`
- end: `0x180054818`
- name: `?SetShellValue@CWMThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1096`
- prototype: `__int64 __fastcall(CWMThumbnailStreamProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180016e48`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180051560`
- `0x1800543d0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800545eb`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800545eb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800544aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054549`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800544aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054549`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054427`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800544c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054565`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054607`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800546ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054759`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054427`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800544c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054565`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054607`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800546ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054759`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWMThumbnailStreamProperty::SetShellValue(PROPVARIANT *this, PROPVARIANT *pvarSrc)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v31; // [rsp+58h] [rbp+10h] BYREF
  struct IStream *v32; // [rsp+60h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v31,
    "CWMThumbnailStreamProperty::SetShellValue",
    516);
  v32 = 0;
  if ( pvarSrc->vt == 66 )
  {
    v5 = PropVariantClear(this + 4);
    if ( v5 >= 0 )
    {
      v5 = PropVariantClear(this + 5);
      if ( v5 >= 0 )
      {
        v5 = PropVariantCopy(this + 4, pvarSrc);
        if ( v5 >= 0 )
        {
          v5 = CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(
                 (CWMThumbnailStreamProperty *)this,
                 pvarSrc->pStream,
                 &v32);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(PROPVARIANT *, struct IStream *))(*(_QWORD *)&this->vt + 312LL))(this, v32);
            if ( v5 < 0 )
            {
              v27 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
                CallStackTracing::s_wpInstance = v28;
                if ( v28
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
                {
                  v27 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v27 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v27 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CWMThumbnailStreamProperty::SetShellValue",
                    534,
                    v5);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v9 = 51;
                goto LABEL_67;
              }
            }
          }
          else
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
              CallStackTracing::s_wpInstance = v24;
              if ( v24
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
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
              if ( *((_DWORD *)v25 + 499) != v5 )
                CallStackContext::TraceFailure(v25, "CWMThumbnailStreamProperty::SetShellValue", 532, v5);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v9 = 50;
              goto LABEL_67;
            }
          }
        }
        else
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
            CallStackTracing::s_wpInstance = v20;
            if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
            {
              v19 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v19 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v19 + 8) )
          {
            v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
            if ( *((_DWORD *)v21 + 499) != v5 )
              CallStackContext::TraceFailure(v21, "CWMThumbnailStreamProperty::SetShellValue", 530, v5);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 49;
            goto LABEL_67;
          }
        }
      }
      else
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != v5 )
            CallStackContext::TraceFailure(v17, "CWMThumbnailStreamProperty::SetShellValue", 528, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 48;
          goto LABEL_67;
        }
      }
    }
    else
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != v5 )
          CallStackContext::TraceFailure(v13, "CWMThumbnailStreamProperty::SetShellValue", 527, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 47;
        goto LABEL_67;
      }
    }
  }
  else
  {
    v5 = -2147024809;
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v8 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v8, "CWMThumbnailStreamProperty::SetShellValue", 524, -2147024809);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 46;
LABEL_67:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
    }
  }
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v32);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v31);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800543d0  mov     [rsp+arg_0], rbx
0x1800543d5  mov     [rsp+arg_18], rbp
0x1800543da  push    rsi
0x1800543db  push    rdi
0x1800543dc  push    r15
0x1800543de  sub     rsp, 30h
0x1800543e2  mov     rsi, rdx
0x1800543e5  mov     rdi, rcx
0x1800543e8  mov     r8d, 204h; int
0x1800543ee  lea     r15, aCwmthumbnailst_0; "CWMThumbnailStreamProperty::SetShellVal"...
0x1800543f5  mov     rdx, r15; char *
0x1800543f8  lea     rcx, [rsp+48h+arg_8]; this
0x1800543fd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180054402  nop
0x180054403  mov     [rsp+48h+arg_10], 0
0x18005440c  cmp     word ptr [rsi], 42h ; 'B'
0x180054410  jz      loc_1800544A6
0x180054416  mov     ebx, 80070057h
0x18005441b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054422  test    rcx, rcx
0x180054425  jnz     short loc_180054468
0x180054427  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005442d  mov     rcx, rax
0x180054430  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054437  test    rax, rax
0x18005443a  jz      short loc_18005445A
0x18005443c  mov     rax, [rax]
0x18005443f  mov     edx, 7F0h
0x180054444  mov     rax, [rax+8]
0x180054448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005444d  test    eax, eax
0x18005444f  jz      short loc_18005445A
0x180054451  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054458  jmp     short loc_180054468
0x18005445a  lea     rcx, qword_18006EB20; this
0x180054461  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054468  cmp     byte ptr [rcx+8], 0
0x18005446c  jz      short loc_18005448F
0x18005446e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054473  cmp     [rax+7CCh], ebx
0x180054479  jz      short loc_18005448F
0x18005447b  mov     r9d, ebx; int
0x18005447e  mov     r8d, 20Ch; int
0x180054484  mov     rdx, r15; char *
0x180054487  mov     rcx, rax; this
0x18005448a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005448f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054494  cmp     al, 1
0x180054496  jb      loc_1800547EE
0x18005449c  mov     edx, 2Eh ; '.'
0x1800544a1  jmp     loc_1800547CF
0x1800544a6  lea     rcx, [rdi+60h]; pvar
0x1800544aa  call    cs:__imp_PropVariantClear
0x1800544b0  mov     ebx, eax
0x1800544b2  test    eax, eax
0x1800544b4  jns     loc_180054545
0x1800544ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800544c1  test    rcx, rcx
0x1800544c4  jnz     short loc_180054507
0x1800544c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800544cc  mov     rcx, rax
0x1800544cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800544d6  test    rax, rax
0x1800544d9  jz      short loc_1800544F9
0x1800544db  mov     rax, [rax]
0x1800544de  mov     edx, 7F0h
0x1800544e3  mov     rax, [rax+8]
0x1800544e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800544ec  test    eax, eax
0x1800544ee  jz      short loc_1800544F9
0x1800544f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800544f7  jmp     short loc_180054507
0x1800544f9  lea     rcx, qword_18006EB20; this
0x180054500  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054507  cmp     byte ptr [rcx+8], 0
0x18005450b  jz      short loc_18005452E
0x18005450d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054512  cmp     [rax+7CCh], ebx
0x180054518  jz      short loc_18005452E
0x18005451a  mov     r9d, ebx; int
0x18005451d  mov     r8d, 20Fh; int
0x180054523  mov     rdx, r15; char *
0x180054526  mov     rcx, rax; this
0x180054529  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005452e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054533  cmp     al, 1
0x180054535  jb      loc_1800547EE
0x18005453b  mov     edx, 2Fh ; '/'
0x180054540  jmp     loc_1800547CF
0x180054545  lea     rcx, [rdi+78h]; pvar
0x180054549  call    cs:__imp_PropVariantClear
0x18005454f  mov     ebx, eax
0x180054551  test    eax, eax
0x180054553  jns     loc_1800545E4
0x180054559  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054560  test    rcx, rcx
0x180054563  jnz     short loc_1800545A6
0x180054565  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005456b  mov     rcx, rax
0x18005456e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054575  test    rax, rax
0x180054578  jz      short loc_180054598
0x18005457a  mov     rax, [rax]
0x18005457d  mov     edx, 7F0h
0x180054582  mov     rax, [rax+8]
0x180054586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005458b  test    eax, eax
0x18005458d  jz      short loc_180054598
0x18005458f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054596  jmp     short loc_1800545A6
0x180054598  lea     rcx, qword_18006EB20; this
0x18005459f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800545a6  cmp     byte ptr [rcx+8], 0
0x1800545aa  jz      short loc_1800545CD
0x1800545ac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800545b1  cmp     [rax+7CCh], ebx
0x1800545b7  jz      short loc_1800545CD
0x1800545b9  mov     r9d, ebx; int
0x1800545bc  mov     r8d, 210h; int
0x1800545c2  mov     rdx, r15; char *
0x1800545c5  mov     rcx, rax; this
0x1800545c8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800545cd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800545d2  cmp     al, 1
0x1800545d4  jb      loc_1800547EE
0x1800545da  mov     edx, 30h ; '0'
0x1800545df  jmp     loc_1800547CF
0x1800545e4  mov     rdx, rsi; pvarSrc
0x1800545e7  lea     rcx, [rdi+60h]; pvarDest
0x1800545eb  call    cs:__imp_PropVariantCopy
0x1800545f1  mov     ebx, eax
0x1800545f3  test    eax, eax
0x1800545f5  jns     loc_180054686
0x1800545fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054602  test    rcx, rcx
0x180054605  jnz     short loc_180054648
0x180054607  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005460d  mov     rcx, rax
0x180054610  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054617  test    rax, rax
0x18005461a  jz      short loc_18005463A
0x18005461c  mov     rax, [rax]
0x18005461f  mov     edx, 7F0h
0x180054624  mov     rax, [rax+8]
0x180054628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005462d  test    eax, eax
0x18005462f  jz      short loc_18005463A
0x180054631  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054638  jmp     short loc_180054648
0x18005463a  lea     rcx, qword_18006EB20; this
0x180054641  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054648  cmp     byte ptr [rcx+8], 0
0x18005464c  jz      short loc_18005466F
0x18005464e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054653  cmp     [rax+7CCh], ebx
0x180054659  jz      short loc_18005466F
0x18005465b  mov     r9d, ebx; int
0x18005465e  mov     r8d, 212h; int
0x180054664  mov     rdx, r15; char *
0x180054667  mov     rcx, rax; this
0x18005466a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005466f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054674  cmp     al, 1
0x180054676  jb      loc_1800547EE
0x18005467c  mov     edx, 31h ; '1'
0x180054681  jmp     loc_1800547CF
0x180054686  lea     r8, [rsp+48h+arg_10]; struct IStream **
0x18005468b  mov     rdx, [rsi+8]; struct IStream *
0x18005468f  mov     rcx, rdi; this
0x180054692  call    ?ReencodeThumbnailIfNeeded@CWMThumbnailStreamProperty@@AEAAJPEAUIStream@@PEAPEAU2@@Z; CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(IStream *,IStream * *)
0x180054697  mov     ebx, eax
0x180054699  test    eax, eax
0x18005469b  jns     loc_18005472C
0x1800546a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800546a8  test    rcx, rcx
0x1800546ab  jnz     short loc_1800546EE
0x1800546ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800546b3  mov     rcx, rax
0x1800546b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800546bd  test    rax, rax
0x1800546c0  jz      short loc_1800546E0
0x1800546c2  mov     rax, [rax]
0x1800546c5  mov     edx, 7F0h
0x1800546ca  mov     rax, [rax+8]
0x1800546ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800546d3  test    eax, eax
0x1800546d5  jz      short loc_1800546E0
0x1800546d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800546de  jmp     short loc_1800546EE
0x1800546e0  lea     rcx, qword_18006EB20; this
0x1800546e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800546ee  cmp     byte ptr [rcx+8], 0
0x1800546f2  jz      short loc_180054715
0x1800546f4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800546f9  cmp     [rax+7CCh], ebx
0x1800546ff  jz      short loc_180054715
0x180054701  mov     r9d, ebx; int
0x180054704  mov     r8d, 214h; int
0x18005470a  mov     rdx, r15; char *
0x18005470d  mov     rcx, rax; this
0x180054710  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054715  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005471a  cmp     al, 1
0x18005471c  jb      loc_1800547EE
0x180054722  mov     edx, 32h ; '2'
0x180054727  jmp     loc_1800547CF
0x18005472c  mov     rax, [rdi]
0x18005472f  mov     rdx, [rsp+48h+arg_10]
0x180054734  mov     rcx, rdi
0x180054737  mov     rax, [rax+138h]
0x18005473e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054743  mov     ebx, eax
0x180054745  test    eax, eax
0x180054747  jns     loc_1800547EE
0x18005474d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054754  test    rcx, rcx
0x180054757  jnz     short loc_18005479A
0x180054759  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005475f  mov     rcx, rax
0x180054762  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054769  test    rax, rax
0x18005476c  jz      short loc_18005478C
0x18005476e  mov     rax, [rax]
0x180054771  mov     edx, 7F0h
0x180054776  mov     rax, [rax+8]
0x18005477a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005477f  test    eax, eax
0x180054781  jz      short loc_18005478C
0x180054783  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005478a  jmp     short loc_18005479A
0x18005478c  lea     rcx, qword_18006EB20; this
0x180054793  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005479a  cmp     byte ptr [rcx+8], 0
0x18005479e  jz      short loc_1800547C1
0x1800547a0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800547a5  cmp     [rax+7CCh], ebx
0x1800547ab  jz      short loc_1800547C1
0x1800547ad  mov     r9d, ebx; int
0x1800547b0  mov     r8d, 216h; int
0x1800547b6  mov     rdx, r15; char *
0x1800547b9  mov     rcx, rax; this
0x1800547bc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800547c1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800547c6  cmp     al, 1
0x1800547c8  jb      short loc_1800547EE
0x1800547ca  mov     edx, 33h ; '3'
0x1800547cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800547d6  mov     [rsp+48h+var_28], ebx
0x1800547da  mov     r9, rdi
0x1800547dd  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x1800547e4  mov     rcx, [rcx+10h]
0x1800547e8  call    WPP_SF_qd
0x1800547ed  nop
0x1800547ee  lea     rcx, [rsp+48h+arg_10]
0x1800547f3  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x1800547f8  nop
0x1800547f9  lea     rcx, [rsp+48h+arg_8]; this
0x1800547fe  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180054803  mov     eax, ebx
0x180054805  mov     rbx, [rsp+48h+arg_0]
0x18005480a  mov     rbp, [rsp+48h+arg_18]
0x18005480f  add     rsp, 30h
0x180054813  pop     r15
0x180054815  pop     rdi
0x180054816  pop     rsi
0x180054817  retn
```
