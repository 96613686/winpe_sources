# CWMThumbnailStreamProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x180073280`
- end: `0x1800736fc`
- name: `?SetShellValue@CWMThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1148`
- prototype: `__int64 __fastcall(CWMThumbnailStreamProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800516a4`
- `0x18006fda4`
- `0x180073280`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800734b8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800734b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007335f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007340a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007335f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007340a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800732d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073381`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007342c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800734da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073586`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073638`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800732d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073381`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007342c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800734da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073586`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073638`

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
                  v40 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v34 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v28 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v22 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v16 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v9);
    }
  }
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v45);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180073280  mov     [rsp+arg_0], rbx
0x180073285  mov     [rsp+arg_18], rbp
0x18007328a  push    rsi
0x18007328b  push    rdi
0x18007328c  push    r15
0x18007328e  sub     rsp, 30h
0x180073292  mov     rsi, rdx
0x180073295  lea     r15, aCwmthumbnailst_0; "CWMThumbnailStreamProperty::SetShellVal"...
0x18007329c  mov     rdi, rcx
0x18007329f  mov     rdx, r15; char *
0x1800732a2  mov     r8d, 204h; int
0x1800732a8  lea     rcx, [rsp+48h+arg_8]; this
0x1800732ad  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800732b2  cmp     word ptr [rsi], 42h ; 'B'
0x1800732b6  mov     [rsp+48h+arg_10], 0
0x1800732bf  jz      loc_18007335B
0x1800732c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800732cc  mov     ebx, 80070057h
0x1800732d1  test    rcx, rcx
0x1800732d4  jnz     short loc_18007331D
0x1800732d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800732dd  nop     dword ptr [rax+rax+00h]
0x1800732e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800732e9  mov     rcx, rax
0x1800732ec  test    rax, rax
0x1800732ef  jz      short loc_18007330F
0x1800732f1  mov     rax, [rax]
0x1800732f4  mov     edx, 7F0h
0x1800732f9  mov     rax, [rax+8]
0x1800732fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073302  test    eax, eax
0x180073304  jz      short loc_18007330F
0x180073306  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007330d  jmp     short loc_18007331D
0x18007330f  lea     rcx, qword_1800DBF70; this
0x180073316  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007331d  cmp     byte ptr [rcx+8], 0
0x180073321  jz      short loc_180073344
0x180073323  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073328  cmp     [rax+7CCh], ebx
0x18007332e  jz      short loc_180073344
0x180073330  mov     r9d, ebx; int
0x180073333  mov     r8d, 20Ch; int
0x180073339  mov     rdx, r15; char *
0x18007333c  mov     rcx, rax; this
0x18007333f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073344  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007334b  jb      loc_1800736D2
0x180073351  mov     edx, 2Eh ; '.'
0x180073356  jmp     loc_1800736B4
0x18007335b  lea     rcx, [rdi+60h]; pvar
0x18007335f  call    cs:__imp_PropVariantClear
0x180073366  nop     dword ptr [rax+rax+00h]
0x18007336b  mov     ebx, eax
0x18007336d  test    eax, eax
0x18007336f  jns     loc_180073406
0x180073375  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007337c  test    rcx, rcx
0x18007337f  jnz     short loc_1800733C8
0x180073381  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073388  nop     dword ptr [rax+rax+00h]
0x18007338d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073394  mov     rcx, rax
0x180073397  test    rax, rax
0x18007339a  jz      short loc_1800733BA
0x18007339c  mov     rax, [rax]
0x18007339f  mov     edx, 7F0h
0x1800733a4  mov     rax, [rax+8]
0x1800733a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800733ad  test    eax, eax
0x1800733af  jz      short loc_1800733BA
0x1800733b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800733b8  jmp     short loc_1800733C8
0x1800733ba  lea     rcx, qword_1800DBF70; this
0x1800733c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800733c8  cmp     byte ptr [rcx+8], 0
0x1800733cc  jz      short loc_1800733EF
0x1800733ce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800733d3  cmp     [rax+7CCh], ebx
0x1800733d9  jz      short loc_1800733EF
0x1800733db  mov     r9d, ebx; int
0x1800733de  mov     r8d, 20Fh; int
0x1800733e4  mov     rdx, r15; char *
0x1800733e7  mov     rcx, rax; this
0x1800733ea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800733ef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800733f6  jb      loc_1800736D2
0x1800733fc  mov     edx, 2Fh ; '/'
0x180073401  jmp     loc_1800736B4
0x180073406  lea     rcx, [rdi+78h]; pvar
0x18007340a  call    cs:__imp_PropVariantClear
0x180073411  nop     dword ptr [rax+rax+00h]
0x180073416  mov     ebx, eax
0x180073418  test    eax, eax
0x18007341a  jns     loc_1800734B1
0x180073420  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073427  test    rcx, rcx
0x18007342a  jnz     short loc_180073473
0x18007342c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073433  nop     dword ptr [rax+rax+00h]
0x180073438  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007343f  mov     rcx, rax
0x180073442  test    rax, rax
0x180073445  jz      short loc_180073465
0x180073447  mov     rax, [rax]
0x18007344a  mov     edx, 7F0h
0x18007344f  mov     rax, [rax+8]
0x180073453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073458  test    eax, eax
0x18007345a  jz      short loc_180073465
0x18007345c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073463  jmp     short loc_180073473
0x180073465  lea     rcx, qword_1800DBF70; this
0x18007346c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073473  cmp     byte ptr [rcx+8], 0
0x180073477  jz      short loc_18007349A
0x180073479  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007347e  cmp     [rax+7CCh], ebx
0x180073484  jz      short loc_18007349A
0x180073486  mov     r9d, ebx; int
0x180073489  mov     r8d, 210h; int
0x18007348f  mov     rdx, r15; char *
0x180073492  mov     rcx, rax; this
0x180073495  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007349a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800734a1  jb      loc_1800736D2
0x1800734a7  mov     edx, 30h ; '0'
0x1800734ac  jmp     loc_1800736B4
0x1800734b1  mov     rdx, rsi; pvarSrc
0x1800734b4  lea     rcx, [rdi+60h]; pvarDest
0x1800734b8  call    cs:__imp_PropVariantCopy
0x1800734bf  nop     dword ptr [rax+rax+00h]
0x1800734c4  mov     ebx, eax
0x1800734c6  test    eax, eax
0x1800734c8  jns     loc_18007355F
0x1800734ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800734d5  test    rcx, rcx
0x1800734d8  jnz     short loc_180073521
0x1800734da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800734e1  nop     dword ptr [rax+rax+00h]
0x1800734e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800734ed  mov     rcx, rax
0x1800734f0  test    rax, rax
0x1800734f3  jz      short loc_180073513
0x1800734f5  mov     rax, [rax]
0x1800734f8  mov     edx, 7F0h
0x1800734fd  mov     rax, [rax+8]
0x180073501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073506  test    eax, eax
0x180073508  jz      short loc_180073513
0x18007350a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073511  jmp     short loc_180073521
0x180073513  lea     rcx, qword_1800DBF70; this
0x18007351a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073521  cmp     byte ptr [rcx+8], 0
0x180073525  jz      short loc_180073548
0x180073527  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007352c  cmp     [rax+7CCh], ebx
0x180073532  jz      short loc_180073548
0x180073534  mov     r9d, ebx; int
0x180073537  mov     r8d, 212h; int
0x18007353d  mov     rdx, r15; char *
0x180073540  mov     rcx, rax; this
0x180073543  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073548  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007354f  jb      loc_1800736D2
0x180073555  mov     edx, 31h ; '1'
0x18007355a  jmp     loc_1800736B4
0x18007355f  mov     rdx, [rsi+8]; struct IStream *
0x180073563  lea     r8, [rsp+48h+arg_10]; struct IStream **
0x180073568  mov     rcx, rdi; this
0x18007356b  call    ?ReencodeThumbnailIfNeeded@CWMThumbnailStreamProperty@@AEAAJPEAUIStream@@PEAPEAU2@@Z; CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(IStream *,IStream * *)
0x180073570  mov     ebx, eax
0x180073572  test    eax, eax
0x180073574  jns     loc_18007360B
0x18007357a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073581  test    rcx, rcx
0x180073584  jnz     short loc_1800735CD
0x180073586  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007358d  nop     dword ptr [rax+rax+00h]
0x180073592  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073599  mov     rcx, rax
0x18007359c  test    rax, rax
0x18007359f  jz      short loc_1800735BF
0x1800735a1  mov     rax, [rax]
0x1800735a4  mov     edx, 7F0h
0x1800735a9  mov     rax, [rax+8]
0x1800735ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800735b2  test    eax, eax
0x1800735b4  jz      short loc_1800735BF
0x1800735b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800735bd  jmp     short loc_1800735CD
0x1800735bf  lea     rcx, qword_1800DBF70; this
0x1800735c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800735cd  cmp     byte ptr [rcx+8], 0
0x1800735d1  jz      short loc_1800735F4
0x1800735d3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800735d8  cmp     [rax+7CCh], ebx
0x1800735de  jz      short loc_1800735F4
0x1800735e0  mov     r9d, ebx; int
0x1800735e3  mov     r8d, 214h; int
0x1800735e9  mov     rdx, r15; char *
0x1800735ec  mov     rcx, rax; this
0x1800735ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800735f4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800735fb  jb      loc_1800736D2
0x180073601  mov     edx, 32h ; '2'
0x180073606  jmp     loc_1800736B4
0x18007360b  mov     rax, [rdi]
0x18007360e  mov     rcx, rdi
0x180073611  mov     rdx, [rsp+48h+arg_10]
0x180073616  mov     rax, [rax+138h]
0x18007361d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073622  mov     ebx, eax
0x180073624  test    eax, eax
0x180073626  jns     loc_1800736D2
0x18007362c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073633  test    rcx, rcx
0x180073636  jnz     short loc_18007367F
0x180073638  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007363f  nop     dword ptr [rax+rax+00h]
0x180073644  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007364b  mov     rcx, rax
0x18007364e  test    rax, rax
0x180073651  jz      short loc_180073671
0x180073653  mov     rax, [rax]
0x180073656  mov     edx, 7F0h
0x18007365b  mov     rax, [rax+8]
0x18007365f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073664  test    eax, eax
0x180073666  jz      short loc_180073671
0x180073668  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007366f  jmp     short loc_18007367F
0x180073671  lea     rcx, qword_1800DBF70; this
0x180073678  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007367f  cmp     byte ptr [rcx+8], 0
0x180073683  jz      short loc_1800736A6
0x180073685  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007368a  cmp     [rax+7CCh], ebx
0x180073690  jz      short loc_1800736A6
0x180073692  mov     r9d, ebx; int
0x180073695  mov     r8d, 216h; int
0x18007369b  mov     rdx, r15; char *
0x18007369e  mov     rcx, rax; this
0x1800736a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800736a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800736ad  jb      short loc_1800736D2
0x1800736af  mov     edx, 33h ; '3'
0x1800736b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800736bb  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x1800736c2  mov     r9, rdi
0x1800736c5  mov     [rsp+48h+var_28], ebx
0x1800736c9  mov     rcx, [rcx+10h]
0x1800736cd  call    WPP_SF_qD
0x1800736d2  lea     rcx, [rsp+48h+arg_10]
0x1800736d7  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x1800736dc  lea     rcx, [rsp+48h+arg_8]; this
0x1800736e1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800736e6  mov     rbp, [rsp+48h+arg_18]
0x1800736eb  mov     eax, ebx
0x1800736ed  mov     rbx, [rsp+48h+arg_0]
0x1800736f2  add     rsp, 30h
0x1800736f6  pop     r15
0x1800736f8  pop     rdi
0x1800736f9  pop     rsi
0x1800736fa  retn
```
