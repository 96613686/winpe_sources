# CWMThumbnailStreamProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x180070200`
- end: `0x180070645`
- name: `?SetShellValue@CWMThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1093`
- prototype: `__int64 __fastcall(CWMThumbnailStreamProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18004f47c`
- `0x18006cf30`
- `0x180070200`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18007041a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18007041a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800702d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180070378`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800702d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180070378`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070256`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800702f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070394`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070436`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800704dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070588`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070256`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800702f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070394`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070436`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800704dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070588`

## pseudocode

```c
__int64 __fastcall CWMThumbnailStreamProperty::SetShellValue(PROPVARIANT *this, PROPVARIANT *pvarSrc)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  bool v7; // zf
  __int64 *v8; // rcx
  int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v44; // [rsp+58h] [rbp+10h] BYREF
  struct IStream *v45; // [rsp+60h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v44,
    "CWMThumbnailStreamProperty::SetShellValue",
    516);
  v7 = pvarSrc->vt == 66;
  v45 = 0;
  if ( v7 )
  {
    v9 = PropVariantClear(this + 4);
    if ( v9 >= 0 )
    {
      v9 = PropVariantClear(this + 5);
      if ( v9 >= 0 )
      {
        v9 = PropVariantCopy(this + 4, pvarSrc);
        if ( v9 >= 0 )
        {
          v9 = CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(
                 (CWMThumbnailStreamProperty *)this,
                 pvarSrc->pStream,
                 &v45);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(PROPVARIANT *, struct IStream *))(*(_QWORD *)&this->vt + 312LL))(this, v45);
            if ( v9 < 0 )
            {
              v40 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
                CallStackTracing::s_wpInstance = v41;
                if ( v41
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
                {
                  v40 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v40 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                }
              }
              if ( *((_BYTE *)v40 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CWMThumbnailStreamProperty::SetShellValue",
                    534,
                    v9);
              }
              if ( g_wppLevels )
              {
                v12 = 51;
                goto LABEL_67;
              }
            }
          }
          else
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
              CallStackTracing::s_wpInstance = v35;
              if ( v35
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
              {
                v34 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v34 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v34 + 8) )
            {
              v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
              if ( *((_DWORD *)v36 + 499) != v9 )
                CallStackContext::TraceFailure(v36, "CWMThumbnailStreamProperty::SetShellValue", 532, v9);
            }
            if ( g_wppLevels )
            {
              v12 = 50;
              goto LABEL_67;
            }
          }
        }
        else
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)v30 + 499) != v9 )
              CallStackContext::TraceFailure(v30, "CWMThumbnailStreamProperty::SetShellValue", 530, v9);
          }
          if ( g_wppLevels )
          {
            v12 = 49;
            goto LABEL_67;
          }
        }
      }
      else
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
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
          if ( *((_DWORD *)v24 + 499) != v9 )
            CallStackContext::TraceFailure(v24, "CWMThumbnailStreamProperty::SetShellValue", 528, v9);
        }
        if ( g_wppLevels )
        {
          v12 = 48;
          goto LABEL_67;
        }
      }
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != v9 )
          CallStackContext::TraceFailure(v18, "CWMThumbnailStreamProperty::SetShellValue", 527, v9);
      }
      if ( g_wppLevels )
      {
        v12 = 47;
        goto LABEL_67;
      }
    }
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v11 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v11, "CWMThumbnailStreamProperty::SetShellValue", 524, -2147024809);
    }
    if ( g_wppLevels )
    {
      v12 = 46;
LABEL_67:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v9);
    }
  }
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v45);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180070200  mov     [rsp+arg_0], rbx
0x180070205  mov     [rsp+arg_18], rbp
0x18007020a  push    rsi
0x18007020b  push    rdi
0x18007020c  push    r15
0x18007020e  sub     rsp, 30h
0x180070212  mov     rsi, rdx
0x180070215  lea     r15, aCwmthumbnailst_0; "CWMThumbnailStreamProperty::SetShellVal"...
0x18007021c  mov     rdi, rcx
0x18007021f  mov     rdx, r15; char *
0x180070222  mov     r8d, 204h; int
0x180070228  lea     rcx, [rsp+48h+arg_8]; this
0x18007022d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180070232  cmp     word ptr [rsi], 42h ; 'B'
0x180070236  mov     [rsp+48h+arg_10], 0
0x18007023f  jz      loc_1800702D5
0x180070245  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007024c  mov     ebx, 80070057h
0x180070251  test    rcx, rcx
0x180070254  jnz     short loc_180070297
0x180070256  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007025c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180070263  mov     rcx, rax
0x180070266  test    rax, rax
0x180070269  jz      short loc_180070289
0x18007026b  mov     rax, [rax]
0x18007026e  mov     edx, 7F0h
0x180070273  mov     rax, [rax+8]
0x180070277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007027c  test    eax, eax
0x18007027e  jz      short loc_180070289
0x180070280  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070287  jmp     short loc_180070297
0x180070289  lea     rcx, qword_1800D6F70; this
0x180070290  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070297  cmp     byte ptr [rcx+8], 0
0x18007029b  jz      short loc_1800702BE
0x18007029d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800702a2  cmp     [rax+7CCh], ebx
0x1800702a8  jz      short loc_1800702BE
0x1800702aa  mov     r9d, ebx; int
0x1800702ad  mov     r8d, 20Ch; int
0x1800702b3  mov     rdx, r15; char *
0x1800702b6  mov     rcx, rax; this
0x1800702b9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800702be  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800702c5  jb      loc_18007061C
0x1800702cb  mov     edx, 2Eh ; '.'
0x1800702d0  jmp     loc_1800705FE
0x1800702d5  lea     rcx, [rdi+60h]; pvar
0x1800702d9  call    cs:__imp_PropVariantClear
0x1800702df  mov     ebx, eax
0x1800702e1  test    eax, eax
0x1800702e3  jns     loc_180070374
0x1800702e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800702f0  test    rcx, rcx
0x1800702f3  jnz     short loc_180070336
0x1800702f5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800702fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180070302  mov     rcx, rax
0x180070305  test    rax, rax
0x180070308  jz      short loc_180070328
0x18007030a  mov     rax, [rax]
0x18007030d  mov     edx, 7F0h
0x180070312  mov     rax, [rax+8]
0x180070316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007031b  test    eax, eax
0x18007031d  jz      short loc_180070328
0x18007031f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070326  jmp     short loc_180070336
0x180070328  lea     rcx, qword_1800D6F70; this
0x18007032f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070336  cmp     byte ptr [rcx+8], 0
0x18007033a  jz      short loc_18007035D
0x18007033c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070341  cmp     [rax+7CCh], ebx
0x180070347  jz      short loc_18007035D
0x180070349  mov     r9d, ebx; int
0x18007034c  mov     r8d, 20Fh; int
0x180070352  mov     rdx, r15; char *
0x180070355  mov     rcx, rax; this
0x180070358  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007035d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070364  jb      loc_18007061C
0x18007036a  mov     edx, 2Fh ; '/'
0x18007036f  jmp     loc_1800705FE
0x180070374  lea     rcx, [rdi+78h]; pvar
0x180070378  call    cs:__imp_PropVariantClear
0x18007037e  mov     ebx, eax
0x180070380  test    eax, eax
0x180070382  jns     loc_180070413
0x180070388  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007038f  test    rcx, rcx
0x180070392  jnz     short loc_1800703D5
0x180070394  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007039a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800703a1  mov     rcx, rax
0x1800703a4  test    rax, rax
0x1800703a7  jz      short loc_1800703C7
0x1800703a9  mov     rax, [rax]
0x1800703ac  mov     edx, 7F0h
0x1800703b1  mov     rax, [rax+8]
0x1800703b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800703ba  test    eax, eax
0x1800703bc  jz      short loc_1800703C7
0x1800703be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800703c5  jmp     short loc_1800703D5
0x1800703c7  lea     rcx, qword_1800D6F70; this
0x1800703ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800703d5  cmp     byte ptr [rcx+8], 0
0x1800703d9  jz      short loc_1800703FC
0x1800703db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800703e0  cmp     [rax+7CCh], ebx
0x1800703e6  jz      short loc_1800703FC
0x1800703e8  mov     r9d, ebx; int
0x1800703eb  mov     r8d, 210h; int
0x1800703f1  mov     rdx, r15; char *
0x1800703f4  mov     rcx, rax; this
0x1800703f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800703fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070403  jb      loc_18007061C
0x180070409  mov     edx, 30h ; '0'
0x18007040e  jmp     loc_1800705FE
0x180070413  mov     rdx, rsi; pvarSrc
0x180070416  lea     rcx, [rdi+60h]; pvarDest
0x18007041a  call    cs:__imp_PropVariantCopy
0x180070420  mov     ebx, eax
0x180070422  test    eax, eax
0x180070424  jns     loc_1800704B5
0x18007042a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070431  test    rcx, rcx
0x180070434  jnz     short loc_180070477
0x180070436  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007043c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180070443  mov     rcx, rax
0x180070446  test    rax, rax
0x180070449  jz      short loc_180070469
0x18007044b  mov     rax, [rax]
0x18007044e  mov     edx, 7F0h
0x180070453  mov     rax, [rax+8]
0x180070457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007045c  test    eax, eax
0x18007045e  jz      short loc_180070469
0x180070460  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070467  jmp     short loc_180070477
0x180070469  lea     rcx, qword_1800D6F70; this
0x180070470  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070477  cmp     byte ptr [rcx+8], 0
0x18007047b  jz      short loc_18007049E
0x18007047d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070482  cmp     [rax+7CCh], ebx
0x180070488  jz      short loc_18007049E
0x18007048a  mov     r9d, ebx; int
0x18007048d  mov     r8d, 212h; int
0x180070493  mov     rdx, r15; char *
0x180070496  mov     rcx, rax; this
0x180070499  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007049e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800704a5  jb      loc_18007061C
0x1800704ab  mov     edx, 31h ; '1'
0x1800704b0  jmp     loc_1800705FE
0x1800704b5  mov     rdx, [rsi+8]; struct IStream *
0x1800704b9  lea     r8, [rsp+48h+arg_10]; struct IStream **
0x1800704be  mov     rcx, rdi; this
0x1800704c1  call    ?ReencodeThumbnailIfNeeded@CWMThumbnailStreamProperty@@AEAAJPEAUIStream@@PEAPEAU2@@Z; CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(IStream *,IStream * *)
0x1800704c6  mov     ebx, eax
0x1800704c8  test    eax, eax
0x1800704ca  jns     loc_18007055B
0x1800704d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800704d7  test    rcx, rcx
0x1800704da  jnz     short loc_18007051D
0x1800704dc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800704e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800704e9  mov     rcx, rax
0x1800704ec  test    rax, rax
0x1800704ef  jz      short loc_18007050F
0x1800704f1  mov     rax, [rax]
0x1800704f4  mov     edx, 7F0h
0x1800704f9  mov     rax, [rax+8]
0x1800704fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070502  test    eax, eax
0x180070504  jz      short loc_18007050F
0x180070506  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007050d  jmp     short loc_18007051D
0x18007050f  lea     rcx, qword_1800D6F70; this
0x180070516  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007051d  cmp     byte ptr [rcx+8], 0
0x180070521  jz      short loc_180070544
0x180070523  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070528  cmp     [rax+7CCh], ebx
0x18007052e  jz      short loc_180070544
0x180070530  mov     r9d, ebx; int
0x180070533  mov     r8d, 214h; int
0x180070539  mov     rdx, r15; char *
0x18007053c  mov     rcx, rax; this
0x18007053f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180070544  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007054b  jb      loc_18007061C
0x180070551  mov     edx, 32h ; '2'
0x180070556  jmp     loc_1800705FE
0x18007055b  mov     rax, [rdi]
0x18007055e  mov     rcx, rdi
0x180070561  mov     rdx, [rsp+48h+arg_10]
0x180070566  mov     rax, [rax+138h]
0x18007056d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070572  mov     ebx, eax
0x180070574  test    eax, eax
0x180070576  jns     loc_18007061C
0x18007057c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070583  test    rcx, rcx
0x180070586  jnz     short loc_1800705C9
0x180070588  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007058e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180070595  mov     rcx, rax
0x180070598  test    rax, rax
0x18007059b  jz      short loc_1800705BB
0x18007059d  mov     rax, [rax]
0x1800705a0  mov     edx, 7F0h
0x1800705a5  mov     rax, [rax+8]
0x1800705a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800705ae  test    eax, eax
0x1800705b0  jz      short loc_1800705BB
0x1800705b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800705b9  jmp     short loc_1800705C9
0x1800705bb  lea     rcx, qword_1800D6F70; this
0x1800705c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800705c9  cmp     byte ptr [rcx+8], 0
0x1800705cd  jz      short loc_1800705F0
0x1800705cf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800705d4  cmp     [rax+7CCh], ebx
0x1800705da  jz      short loc_1800705F0
0x1800705dc  mov     r9d, ebx; int
0x1800705df  mov     r8d, 216h; int
0x1800705e5  mov     rdx, r15; char *
0x1800705e8  mov     rcx, rax; this
0x1800705eb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800705f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800705f7  jb      short loc_18007061C
0x1800705f9  mov     edx, 33h ; '3'
0x1800705fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180070605  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x18007060c  mov     r9, rdi
0x18007060f  mov     [rsp+48h+var_28], ebx
0x180070613  mov     rcx, [rcx+10h]
0x180070617  call    WPP_SF_qD
0x18007061c  lea     rcx, [rsp+48h+arg_10]
0x180070621  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180070626  lea     rcx, [rsp+48h+arg_8]; this
0x18007062b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180070630  mov     rbp, [rsp+48h+arg_18]
0x180070635  mov     eax, ebx
0x180070637  mov     rbx, [rsp+48h+arg_0]
0x18007063c  add     rsp, 30h
0x180070640  pop     r15
0x180070642  pop     rdi
0x180070643  pop     rsi
0x180070644  retn
```
