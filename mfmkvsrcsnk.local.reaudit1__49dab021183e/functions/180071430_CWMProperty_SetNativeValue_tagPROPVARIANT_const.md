# CWMProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x180071430`
- end: `0x1800719dc`
- name: `?SetNativeValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1452`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180070ca0`
- `0x1800719f0`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180071430`
- `0x180073704`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800715bf`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800717e1`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800715bf`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800717e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180071467`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180071512`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180071467`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180071512`
- `PROPSYS!StgDeserializePropVariant` at `0x1800717ad`
- `PROPSYS!StgDeserializePropVariant` at `0x1800717ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071489`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071534`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800715e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800716c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071803`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071894`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071925`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071489`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071534`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800715e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800716c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071803`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071894`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071925`

## pseudocode

```c
__int64 __fastcall CWMProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 ulVal; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  struct _GUID v43; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v44; // [rsp+40h] [rbp-48h] BYREF
  char v45; // [rsp+90h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v45, "CWMProperty::SetNativeValue", 145);
  v5 = PropVariantClear(this + 4);
  if ( v5 >= 0 )
  {
    v5 = PropVariantClear(this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy(this + 5, a2);
      if ( v5 >= 0 )
      {
        if ( (a2->vt & 0xEFFF) == 8
          || (a2->vt & 0xEFFF) == 0xB
          || (a2->vt & 0xEFFF) == 0x12
          || (a2->vt & 0xEFFF) == 0x13
          || (a2->vt & 0xEFFF) == 0x15
          || (a2->vt & 0xEFFF) == 0x1F
          || (a2->vt & 0xEFFF) == 0x41
          || (a2->vt & 0xEFFF) == 0x48 )
        {
          v43 = (struct _GUID)MF_MD_SHELLMULTI;
          v44 = (struct _GUID)MF_MD_SHELLTYPE;
          v5 = CWMProperty::TranslateValue((CWMProperty *)this, this + 5, this + 4, &v44, &v43);
          if ( v5 < 0 )
          {
            if ( a2->vt == 65 && (ulVal = a2->ulVal, (_DWORD)ulVal) )
            {
              if ( (unsigned int)ulVal < 8
                || (v5 = StgDeserializePropVariant(
                           (const SERIALIZEDPROPERTYVALUE *)a2->bstrblobVal.pData,
                           ulVal,
                           this + 4),
                    v5 < 0) )
              {
                if ( v5 == -2147024882 || v5 == -2147287035 )
                {
                  v36 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, ulVal, v28, v29);
                    CallStackTracing::s_wpInstance = v37;
                    if ( v37
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                    {
                      v36 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v36 = &qword_1800DBF70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                    }
                  }
                  if ( *((_BYTE *)v36 + 8) )
                  {
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                      CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::SetNativeValue", 177, v5);
                  }
                  if ( g_wppLevels )
                  {
                    v11 = 21;
                    goto LABEL_90;
                  }
                }
                else
                {
                  v5 = PropVariantCopy(this + 4, a2);
                  if ( v5 < 0 )
                  {
                    v33 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
                      CallStackTracing::s_wpInstance = v34;
                      if ( v34
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(
                             v34,
                             2032) )
                      {
                        v33 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v33 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    if ( *((_BYTE *)v33 + 8) )
                    {
                      v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                      if ( *((_DWORD *)v35 + 499) != v5 )
                        CallStackContext::TraceFailure(v35, "CWMProperty::SetNativeValue", 175, v5);
                    }
                    if ( g_wppLevels )
                    {
                      v11 = 20;
                      goto LABEL_90;
                    }
                  }
                }
              }
            }
            else
            {
              v39 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, ulVal, v28, v29);
                CallStackTracing::s_wpInstance = v40;
                if ( v40
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
                {
                  v39 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v39 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( *((_BYTE *)v39 + 8) )
              {
                v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
                if ( *((_DWORD *)v41 + 499) != v5 )
                  CallStackContext::TraceFailure(v41, "CWMProperty::SetNativeValue", 181, v5);
              }
              if ( g_wppLevels )
              {
                v11 = 22;
                goto LABEL_90;
              }
            }
          }
        }
        else
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
          v5 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
            CallStackTracing::s_wpInstance = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
            if ( *((_DWORD *)v26 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v26, "CWMProperty::SetNativeValue", 189, -2147418113);
          }
          if ( g_wppLevels )
          {
            v11 = 23;
            goto LABEL_90;
          }
        }
      }
      else
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != v5 )
            CallStackContext::TraceFailure(v23, "CWMProperty::SetNativeValue", 148, v5);
        }
        if ( g_wppLevels )
        {
          v11 = 19;
          goto LABEL_90;
        }
      }
    }
    else
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != v5 )
          CallStackContext::TraceFailure(v17, "CWMProperty::SetNativeValue", 146, v5);
      }
      if ( g_wppLevels )
      {
        v11 = 18;
        goto LABEL_90;
      }
    }
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
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
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v10 + 499) != v5 )
        CallStackContext::TraceFailure(v10, "CWMProperty::SetNativeValue", 145, v5);
    }
    if ( g_wppLevels )
    {
      v11 = 17;
LABEL_90:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v45);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180071430  mov     rax, rsp
0x180071433  push    rbx
0x180071434  push    rbp
0x180071435  push    rsi
0x180071436  push    rdi
0x180071437  push    r12
0x180071439  push    r14
0x18007143b  sub     rsp, 58h
0x18007143f  mov     rdi, rdx
0x180071442  lea     r12, aCwmpropertySet; "CWMProperty::SetNativeValue"
0x180071449  mov     rsi, rcx
0x18007144c  mov     ebp, 91h
0x180071451  mov     r8d, ebp; int
0x180071454  lea     rcx, [rax+8]; this
0x180071458  mov     rdx, r12; char *
0x18007145b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180071460  lea     r14, [rsi+60h]
0x180071464  mov     rcx, r14; pvar
0x180071467  call    cs:__imp_PropVariantClear
0x18007146e  nop     dword ptr [rax+rax+00h]
0x180071473  mov     ebx, eax
0x180071475  test    eax, eax
0x180071477  jns     loc_18007150B
0x18007147d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071484  test    rcx, rcx
0x180071487  jnz     short loc_1800714D0
0x180071489  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071490  nop     dword ptr [rax+rax+00h]
0x180071495  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007149c  mov     rcx, rax
0x18007149f  test    rax, rax
0x1800714a2  jz      short loc_1800714C2
0x1800714a4  mov     rax, [rax]
0x1800714a7  mov     edx, 7F0h
0x1800714ac  mov     rax, [rax+8]
0x1800714b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800714b5  test    eax, eax
0x1800714b7  jz      short loc_1800714C2
0x1800714b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800714c0  jmp     short loc_1800714D0
0x1800714c2  lea     rcx, qword_1800DBF70; this
0x1800714c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800714d0  cmp     byte ptr [rcx+8], 0
0x1800714d4  jz      short loc_1800714F4
0x1800714d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800714db  cmp     [rax+7CCh], ebx
0x1800714e1  jz      short loc_1800714F4
0x1800714e3  mov     r9d, ebx; int
0x1800714e6  mov     r8d, ebp; int
0x1800714e9  mov     rdx, r12; char *
0x1800714ec  mov     rcx, rax; this
0x1800714ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800714f4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800714fb  jb      loc_1800719BF
0x180071501  mov     edx, 11h
0x180071506  jmp     loc_1800719A1
0x18007150b  lea     rbp, [rsi+78h]
0x18007150f  mov     rcx, rbp; pvar
0x180071512  call    cs:__imp_PropVariantClear
0x180071519  nop     dword ptr [rax+rax+00h]
0x18007151e  mov     ebx, eax
0x180071520  test    eax, eax
0x180071522  jns     loc_1800715B9
0x180071528  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007152f  test    rcx, rcx
0x180071532  jnz     short loc_18007157B
0x180071534  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007153b  nop     dword ptr [rax+rax+00h]
0x180071540  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071547  mov     rcx, rax
0x18007154a  test    rax, rax
0x18007154d  jz      short loc_18007156D
0x18007154f  mov     rax, [rax]
0x180071552  mov     edx, 7F0h
0x180071557  mov     rax, [rax+8]
0x18007155b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071560  test    eax, eax
0x180071562  jz      short loc_18007156D
0x180071564  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007156b  jmp     short loc_18007157B
0x18007156d  lea     rcx, qword_1800DBF70; this
0x180071574  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007157b  cmp     byte ptr [rcx+8], 0
0x18007157f  jz      short loc_1800715A2
0x180071581  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071586  cmp     [rax+7CCh], ebx
0x18007158c  jz      short loc_1800715A2
0x18007158e  mov     r9d, ebx; int
0x180071591  mov     r8d, 92h; int
0x180071597  mov     rdx, r12; char *
0x18007159a  mov     rcx, rax; this
0x18007159d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800715a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800715a9  jb      loc_1800719BF
0x1800715af  mov     edx, 12h
0x1800715b4  jmp     loc_1800719A1
0x1800715b9  mov     rdx, rdi; pvarSrc
0x1800715bc  mov     rcx, rbp; pvarDest
0x1800715bf  call    cs:__imp_PropVariantCopy
0x1800715c6  nop     dword ptr [rax+rax+00h]
0x1800715cb  mov     ebx, eax
0x1800715cd  test    eax, eax
0x1800715cf  jns     loc_180071666
0x1800715d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800715dc  test    rcx, rcx
0x1800715df  jnz     short loc_180071628
0x1800715e1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800715e8  nop     dword ptr [rax+rax+00h]
0x1800715ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800715f4  mov     rcx, rax
0x1800715f7  test    rax, rax
0x1800715fa  jz      short loc_18007161A
0x1800715fc  mov     rax, [rax]
0x1800715ff  mov     edx, 7F0h
0x180071604  mov     rax, [rax+8]
0x180071608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007160d  test    eax, eax
0x18007160f  jz      short loc_18007161A
0x180071611  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071618  jmp     short loc_180071628
0x18007161a  lea     rcx, qword_1800DBF70; this
0x180071621  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071628  cmp     byte ptr [rcx+8], 0
0x18007162c  jz      short loc_18007164F
0x18007162e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071633  cmp     [rax+7CCh], ebx
0x180071639  jz      short loc_18007164F
0x18007163b  mov     r9d, ebx; int
0x18007163e  mov     r8d, 94h; int
0x180071644  mov     rdx, r12; char *
0x180071647  mov     rcx, rax; this
0x18007164a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007164f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071656  jb      loc_1800719BF
0x18007165c  mov     edx, 13h
0x180071661  jmp     loc_1800719A1
0x180071666  movzx   ecx, word ptr [rdi]
0x180071669  btr     ecx, 0Ch
0x18007166d  sub     ecx, 8
0x180071670  jz      loc_18007174B
0x180071676  sub     ecx, 3
0x180071679  jz      loc_18007174B
0x18007167f  sub     ecx, 7
0x180071682  jz      loc_18007174B
0x180071688  sub     ecx, 1
0x18007168b  jz      loc_18007174B
0x180071691  sub     ecx, 2
0x180071694  jz      loc_18007174B
0x18007169a  sub     ecx, 0Ah
0x18007169d  jz      loc_18007174B
0x1800716a3  sub     ecx, 22h ; '"'
0x1800716a6  jz      loc_18007174B
0x1800716ac  cmp     ecx, 7
0x1800716af  jz      loc_18007174B
0x1800716b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800716bc  mov     ebx, 8000FFFFh
0x1800716c1  test    rcx, rcx
0x1800716c4  jnz     short loc_18007170D
0x1800716c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800716cd  nop     dword ptr [rax+rax+00h]
0x1800716d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800716d9  mov     rcx, rax
0x1800716dc  test    rax, rax
0x1800716df  jz      short loc_1800716FF
0x1800716e1  mov     rax, [rax]
0x1800716e4  mov     edx, 7F0h
0x1800716e9  mov     rax, [rax+8]
0x1800716ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800716f2  test    eax, eax
0x1800716f4  jz      short loc_1800716FF
0x1800716f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800716fd  jmp     short loc_18007170D
0x1800716ff  lea     rcx, qword_1800DBF70; this
0x180071706  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007170d  cmp     byte ptr [rcx+8], 0
0x180071711  jz      short loc_180071734
0x180071713  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071718  cmp     [rax+7CCh], ebx
0x18007171e  jz      short loc_180071734
0x180071720  mov     r9d, ebx; int
0x180071723  mov     r8d, 0BDh; int
0x180071729  mov     rdx, r12; char *
0x18007172c  mov     rcx, rax; this
0x18007172f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071734  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007173b  jb      loc_1800719BF
0x180071741  mov     edx, 17h
0x180071746  jmp     loc_1800719A1
0x18007174b  movups  xmm0, cs:MF_MD_SHELLMULTI
0x180071752  lea     rax, [rsp+88h+var_58]
0x180071757  mov     r8, r14; struct tagPROPVARIANT *
0x18007175a  movups  xmm1, cs:MF_MD_SHELLTYPE
0x180071761  lea     r9, [rsp+88h+var_48]; struct _GUID
0x180071766  mov     [rsp+88h+var_68], rax; struct _GUID
0x18007176b  mov     rdx, rbp; struct tagPROPVARIANT *
0x18007176e  mov     rcx, rsi; this
0x180071771  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x180071777  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x18007177d  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x180071782  mov     ebx, eax
0x180071784  test    eax, eax
0x180071786  jns     loc_1800719BF
0x18007178c  cmp     word ptr [rdi], 41h ; 'A'
0x180071790  jnz     loc_180071919
0x180071796  mov     edx, [rdi+8]; cbMax
0x180071799  test    edx, edx
0x18007179b  jz      loc_180071919
0x1800717a1  cmp     edx, 8
0x1800717a4  jb      short loc_1800717C3
0x1800717a6  mov     rcx, [rdi+10h]; pprop
0x1800717aa  mov     r8, r14; ppropvar
0x1800717ad  call    cs:__imp_StgDeserializePropVariant
0x1800717b4  nop     dword ptr [rax+rax+00h]
0x1800717b9  mov     ebx, eax
0x1800717bb  test    eax, eax
0x1800717bd  jns     loc_1800719BF
0x1800717c3  cmp     ebx, 8007000Eh
0x1800717c9  jz      loc_180071888
0x1800717cf  cmp     ebx, 80030005h
0x1800717d5  jz      loc_180071888
0x1800717db  mov     rdx, rdi; pvarSrc
0x1800717de  mov     rcx, r14; pvarDest
0x1800717e1  call    cs:__imp_PropVariantCopy
0x1800717e8  nop     dword ptr [rax+rax+00h]
0x1800717ed  mov     ebx, eax
0x1800717ef  test    eax, eax
0x1800717f1  jns     loc_1800719BF
0x1800717f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800717fe  test    rcx, rcx
0x180071801  jnz     short loc_18007184A
0x180071803  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007180a  nop     dword ptr [rax+rax+00h]
0x18007180f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071816  mov     rcx, rax
0x180071819  test    rax, rax
0x18007181c  jz      short loc_18007183C
0x18007181e  mov     rax, [rax]
0x180071821  mov     edx, 7F0h
0x180071826  mov     rax, [rax+8]
0x18007182a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007182f  test    eax, eax
0x180071831  jz      short loc_18007183C
0x180071833  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007183a  jmp     short loc_18007184A
0x18007183c  lea     rcx, qword_1800DBF70; this
0x180071843  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007184a  cmp     byte ptr [rcx+8], 0
0x18007184e  jz      short loc_180071871
0x180071850  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071855  cmp     [rax+7CCh], ebx
0x18007185b  jz      short loc_180071871
0x18007185d  mov     r9d, ebx; int
0x180071860  mov     r8d, 0AFh; int
0x180071866  mov     rdx, r12; char *
0x180071869  mov     rcx, rax; this
0x18007186c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071871  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071878  jb      loc_1800719BF
0x18007187e  mov     edx, 14h
0x180071883  jmp     loc_1800719A1
0x180071888  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007188f  test    rcx, rcx
0x180071892  jnz     short loc_1800718DB
0x180071894  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007189b  nop     dword ptr [rax+rax+00h]
0x1800718a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800718a7  mov     rcx, rax
0x1800718aa  test    rax, rax
0x1800718ad  jz      short loc_1800718CD
0x1800718af  mov     rax, [rax]
0x1800718b2  mov     edx, 7F0h
0x1800718b7  mov     rax, [rax+8]
0x1800718bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800718c0  test    eax, eax
0x1800718c2  jz      short loc_1800718CD
0x1800718c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800718cb  jmp     short loc_1800718DB
0x1800718cd  lea     rcx, qword_1800DBF70; this
0x1800718d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800718db  cmp     byte ptr [rcx+8], 0
0x1800718df  jz      short loc_180071902
0x1800718e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800718e6  cmp     [rax+7CCh], ebx
0x1800718ec  jz      short loc_180071902
0x1800718ee  mov     r9d, ebx; int
0x1800718f1  mov     r8d, 0B1h; int
0x1800718f7  mov     rdx, r12; char *
0x1800718fa  mov     rcx, rax; this
0x1800718fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071902  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071909  jb      loc_1800719BF
0x18007190f  mov     edx, 15h
0x180071914  jmp     loc_1800719A1
0x180071919  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071920  test    rcx, rcx
0x180071923  jnz     short loc_18007196C
0x180071925  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007192c  nop     dword ptr [rax+rax+00h]
0x180071931  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071938  mov     rcx, rax
  ... truncated ...
```
