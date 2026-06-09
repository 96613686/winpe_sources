# CWMMCDIProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x180052340`
- end: `0x1800526df`
- name: `?SetNativeValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `927`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ef50`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180052340`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180052428`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180052428`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800524cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800524cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052358`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052386`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052358`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052386`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800523a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052444`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800524f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052597`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052634`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800523a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052444`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800524f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052597`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052634`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // edi
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  char v28; // [rsp+70h] [rbp+8h] BYREF

  PropVariantClear(this + 4);
  if ( a2->vt == 65 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v28, "CWMMCDIProperty::SetNativeValue", 423);
    v5 = PropVariantClear(this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy(this + 5, a2);
      if ( v5 >= 0 )
      {
        this[4].vt = 31;
        v14 = (unsigned __int16 *)CoTaskMemAlloc(a2->ulVal);
        this[4].hVal.QuadPart = (LONGLONG)v14;
        if ( v14 )
        {
          v5 = StringCchCopyW(v14, (unsigned __int64)a2->ulVal >> 1, a2->caui.pElems);
          if ( v5 < 0 )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
              CallStackTracing::s_wpInstance = v21;
              if ( v21
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
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
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetNativeValue", 446, v5);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v9 = 38;
              goto LABEL_56;
            }
          }
        }
        else
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
          v5 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
            CallStackTracing::s_wpInstance = v17;
            if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
            {
              v16 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v16 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v16 + 8) )
          {
            v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
            if ( *((_DWORD *)v18 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v18, "CWMMCDIProperty::SetNativeValue", 438, -2147024882);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 37;
            goto LABEL_56;
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
            CallStackContext::TraceFailure(v13, "CWMMCDIProperty::SetNativeValue", 425, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 36;
          goto LABEL_56;
        }
      }
    }
    else
    {
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
        if ( *((_DWORD *)v8 + 499) != v5 )
          CallStackContext::TraceFailure(v8, "CWMMCDIProperty::SetNativeValue", 423, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 35;
LABEL_56:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v28, "CWMMCDIProperty::SetNativeValue", 451);
    v24 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v26 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v26, "CWMMCDIProperty::SetNativeValue", 451, -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 39;
      goto LABEL_56;
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180052340  push    rbp
0x180052342  push    rsi
0x180052343  push    rdi
0x180052344  push    r12
0x180052346  push    r14
0x180052348  push    r15
0x18005234a  sub     rsp, 38h
0x18005234e  mov     rbp, rcx
0x180052351  mov     rsi, rdx
0x180052354  add     rcx, 60h ; '`'; pvar
0x180052358  call    cs:__imp_PropVariantClear
0x18005235e  cmp     word ptr [rsi], 41h ; 'A'
0x180052362  lea     r14, aCwmmcdipropert_0; "CWMMCDIProperty::SetNativeValue"
0x180052369  mov     rdx, r14; char *
0x18005236c  lea     rcx, [rsp+68h+arg_0]; this
0x180052371  jnz     loc_180052616
0x180052377  mov     r8d, 1A7h; int
0x18005237d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180052382  lea     rcx, [rbp+78h]; pvar
0x180052386  call    cs:__imp_PropVariantClear
0x18005238c  mov     edi, eax
0x18005238e  test    eax, eax
0x180052390  jns     loc_180052421
0x180052396  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005239d  test    rcx, rcx
0x1800523a0  jnz     short loc_1800523E3
0x1800523a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800523a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800523af  mov     rcx, rax
0x1800523b2  test    rax, rax
0x1800523b5  jz      short loc_1800523D5
0x1800523b7  mov     rax, [rax]
0x1800523ba  mov     edx, 7F0h
0x1800523bf  mov     rax, [rax+8]
0x1800523c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523c8  test    eax, eax
0x1800523ca  jz      short loc_1800523D5
0x1800523cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800523d3  jmp     short loc_1800523E3
0x1800523d5  lea     rcx, qword_18006EB20; this
0x1800523dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800523e3  cmp     byte ptr [rcx+8], 0
0x1800523e7  jz      short loc_18005240A
0x1800523e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800523ee  cmp     [rax+7CCh], edi
0x1800523f4  jz      short loc_18005240A
0x1800523f6  mov     r9d, edi; int
0x1800523f9  mov     r8d, 1A7h; int
0x1800523ff  mov     rdx, r14; char *
0x180052402  mov     rcx, rax; this
0x180052405  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005240a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005240f  cmp     al, 1
0x180052411  jb      loc_1800526C5
0x180052417  mov     edx, 23h ; '#'
0x18005241c  jmp     loc_1800526A7
0x180052421  mov     rdx, rsi; pvarSrc
0x180052424  lea     rcx, [rbp+78h]; pvarDest
0x180052428  call    cs:__imp_PropVariantCopy
0x18005242e  mov     edi, eax
0x180052430  test    eax, eax
0x180052432  jns     loc_1800524C3
0x180052438  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005243f  test    rcx, rcx
0x180052442  jnz     short loc_180052485
0x180052444  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005244a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052451  mov     rcx, rax
0x180052454  test    rax, rax
0x180052457  jz      short loc_180052477
0x180052459  mov     rax, [rax]
0x18005245c  mov     edx, 7F0h
0x180052461  mov     rax, [rax+8]
0x180052465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005246a  test    eax, eax
0x18005246c  jz      short loc_180052477
0x18005246e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052475  jmp     short loc_180052485
0x180052477  lea     rcx, qword_18006EB20; this
0x18005247e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052485  cmp     byte ptr [rcx+8], 0
0x180052489  jz      short loc_1800524AC
0x18005248b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052490  cmp     [rax+7CCh], edi
0x180052496  jz      short loc_1800524AC
0x180052498  mov     r9d, edi; int
0x18005249b  mov     r8d, 1A9h; int
0x1800524a1  mov     rdx, r14; char *
0x1800524a4  mov     rcx, rax; this
0x1800524a7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800524ac  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800524b1  cmp     al, 1
0x1800524b3  jb      loc_1800526C5
0x1800524b9  mov     edx, 24h ; '$'
0x1800524be  jmp     loc_1800526A7
0x1800524c3  mov     word ptr [rbp+60h], 1Fh
0x1800524c9  mov     ecx, [rsi+8]; cb
0x1800524cc  call    cs:__imp_CoTaskMemAlloc
0x1800524d2  mov     [rbp+68h], rax
0x1800524d6  test    rax, rax
0x1800524d9  jnz     loc_18005256F
0x1800524df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800524e6  mov     edi, 8007000Eh
0x1800524eb  test    rcx, rcx
0x1800524ee  jnz     short loc_180052531
0x1800524f0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800524f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800524fd  mov     rcx, rax
0x180052500  test    rax, rax
0x180052503  jz      short loc_180052523
0x180052505  mov     rax, [rax]
0x180052508  mov     edx, 7F0h
0x18005250d  mov     rax, [rax+8]
0x180052511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052516  test    eax, eax
0x180052518  jz      short loc_180052523
0x18005251a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052521  jmp     short loc_180052531
0x180052523  lea     rcx, qword_18006EB20; this
0x18005252a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052531  cmp     byte ptr [rcx+8], 0
0x180052535  jz      short loc_180052558
0x180052537  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005253c  cmp     [rax+7CCh], edi
0x180052542  jz      short loc_180052558
0x180052544  mov     r9d, edi; int
0x180052547  mov     r8d, 1B6h; int
0x18005254d  mov     rdx, r14; char *
0x180052550  mov     rcx, rax; this
0x180052553  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052558  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005255d  cmp     al, 1
0x18005255f  jb      loc_1800526C5
0x180052565  mov     edx, 25h ; '%'
0x18005256a  jmp     loc_1800526A7
0x18005256f  mov     edx, [rsi+8]
0x180052572  mov     rcx, rax; unsigned __int16 *
0x180052575  mov     r8, [rsi+10h]; unsigned __int16 *
0x180052579  shr     rdx, 1; unsigned __int64
0x18005257c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180052581  mov     edi, eax
0x180052583  test    eax, eax
0x180052585  jns     loc_1800526C5
0x18005258b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052592  test    rcx, rcx
0x180052595  jnz     short loc_1800525D8
0x180052597  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005259d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800525a4  mov     rcx, rax
0x1800525a7  test    rax, rax
0x1800525aa  jz      short loc_1800525CA
0x1800525ac  mov     rax, [rax]
0x1800525af  mov     edx, 7F0h
0x1800525b4  mov     rax, [rax+8]
0x1800525b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525bd  test    eax, eax
0x1800525bf  jz      short loc_1800525CA
0x1800525c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800525c8  jmp     short loc_1800525D8
0x1800525ca  lea     rcx, qword_18006EB20; this
0x1800525d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800525d8  cmp     byte ptr [rcx+8], 0
0x1800525dc  jz      short loc_1800525FF
0x1800525de  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800525e3  cmp     [rax+7CCh], edi
0x1800525e9  jz      short loc_1800525FF
0x1800525eb  mov     r9d, edi; int
0x1800525ee  mov     r8d, 1BEh; int
0x1800525f4  mov     rdx, r14; char *
0x1800525f7  mov     rcx, rax; this
0x1800525fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800525ff  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180052604  cmp     al, 1
0x180052606  jb      loc_1800526C5
0x18005260c  mov     edx, 26h ; '&'
0x180052611  jmp     loc_1800526A7
0x180052616  mov     esi, 1C3h
0x18005261b  mov     r8d, esi; int
0x18005261e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180052623  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005262a  mov     edi, 8000FFFFh
0x18005262f  test    rcx, rcx
0x180052632  jnz     short loc_180052675
0x180052634  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005263a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052641  mov     rcx, rax
0x180052644  test    rax, rax
0x180052647  jz      short loc_180052667
0x180052649  mov     rax, [rax]
0x18005264c  mov     edx, 7F0h
0x180052651  mov     rax, [rax+8]
0x180052655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005265a  test    eax, eax
0x18005265c  jz      short loc_180052667
0x18005265e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052665  jmp     short loc_180052675
0x180052667  lea     rcx, qword_18006EB20; this
0x18005266e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052675  cmp     byte ptr [rcx+8], 0
0x180052679  jz      short loc_180052699
0x18005267b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052680  cmp     [rax+7CCh], edi
0x180052686  jz      short loc_180052699
0x180052688  mov     r9d, edi; int
0x18005268b  mov     r8d, esi; int
0x18005268e  mov     rdx, r14; char *
0x180052691  mov     rcx, rax; this
0x180052694  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052699  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005269e  cmp     al, 1
0x1800526a0  jb      short loc_1800526C5
0x1800526a2  mov     edx, 27h ; '''
0x1800526a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800526ae  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x1800526b5  mov     r9, rbp
0x1800526b8  mov     [rsp+68h+var_48], edi
0x1800526bc  mov     rcx, [rcx+10h]
0x1800526c0  call    WPP_SF_qd
0x1800526c5  lea     rcx, [rsp+68h+arg_0]; this
0x1800526ca  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800526cf  mov     eax, edi
0x1800526d1  add     rsp, 38h
0x1800526d5  pop     r15
0x1800526d7  pop     r14
0x1800526d9  pop     r12
0x1800526db  pop     rdi
0x1800526dc  pop     rsi
0x1800526dd  pop     rbp
0x1800526de  retn
```
