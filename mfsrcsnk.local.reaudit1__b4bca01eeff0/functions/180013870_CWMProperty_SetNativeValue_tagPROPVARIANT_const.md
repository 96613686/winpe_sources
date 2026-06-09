# CWMProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x180013870`
- end: `0x180013f04`
- name: `?SetNativeValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1684`
- prototype: `__int64 __fastcall(CWMProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180083ed0`
- `0x1800a9d60`
- `0x1800d1370`

## callees

- `0x180005cf4`
- `0x180012a3c`
- `0x180013870`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180077708`
- `0x180079680`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013965`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013a16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013a58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013a9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013adc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013b1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013b60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013965`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013a16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013a58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013a9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013adc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013b1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013b60`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001390b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180013e0e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001390b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180013e0e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800138d2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800138ef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800138d2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800138ef`
- `PROPSYS!StgDeserializePropVariant` at `0x180013dda`
- `PROPSYS!StgDeserializePropVariant` at `0x180013dda`

## pseudocode

```c
__int64 __fastcall CWMProperty::SetNativeValue(PROPVARIANT *this, PROPVARIANT *pvarSrc)
{
  CallStackTracing *v4; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rdx
  HRESULT v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  __int64 ulVal; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  struct CallStackContext *v29; // rax
  struct CallStackContext *v30; // rax
  struct CallStackContext *v31; // rax
  struct CallStackContext *v32; // rax
  struct CallStackContext *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  struct _GUID v37; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v38; // [rsp+40h] [rbp-48h] BYREF
  char v39; // [rsp+90h] [rbp+8h] BYREF

  v4 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v4);
    v6 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v6 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v7 = 2 * v6;
      *((_QWORD *)ThreadRelativeContext + v7) = "CWMProperty::SetNativeValue";
      *((_DWORD *)ThreadRelativeContext + 2 * v7 + 2) = 145;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  v9 = PropVariantClear(this + 4);
  if ( v9 < 0 )
  {
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v28 + 499) != v9 )
        CallStackContext::TraceFailure(v28, "CWMProperty::SetNativeValue", 145, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_22;
    v35 = 17;
LABEL_98:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v9);
    goto LABEL_22;
  }
  v9 = PropVariantClear(this + 5);
  if ( v9 < 0 )
  {
    v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v29 + 499) != v9 )
        CallStackContext::TraceFailure(v29, "CWMProperty::SetNativeValue", 146, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_22;
    v35 = 18;
    goto LABEL_98;
  }
  v9 = PropVariantCopy(this + 5, pvarSrc);
  if ( v9 < 0 )
  {
    v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v30 + 499) != v9 )
        CallStackContext::TraceFailure(v30, "CWMProperty::SetNativeValue", 148, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_22;
    v35 = 19;
    goto LABEL_98;
  }
  if ( (pvarSrc->vt & 0xEFFF) == 8
    || (pvarSrc->vt & 0xEFFF) == 0xB
    || (pvarSrc->vt & 0xEFFF) == 0x12
    || (pvarSrc->vt & 0xEFFF) == 0x13
    || (pvarSrc->vt & 0xEFFF) == 0x15
    || (pvarSrc->vt & 0xEFFF) == 0x1F
    || (pvarSrc->vt & 0xEFFF) == 0x41
    || (pvarSrc->vt & 0xEFFF) == 0x48 )
  {
    v37 = (struct _GUID)MF_MD_SHELLMULTI;
    v38 = (struct _GUID)MF_MD_SHELLTYPE;
    v9 = CWMProperty::TranslateValue((CWMProperty *)this, this + 5, this + 4, &v38, &v37);
    if ( v9 < 0 )
    {
      if ( pvarSrc->vt == 65 && (ulVal = pvarSrc->ulVal, (_DWORD)ulVal) )
      {
        if ( (unsigned int)ulVal < 8
          || (v9 = StgDeserializePropVariant(
                     (const SERIALIZEDPROPERTYVALUE *)pvarSrc->bstrblobVal.pData,
                     ulVal,
                     this + 4),
              v9 < 0) )
        {
          if ( v9 == -2147024882 || v9 == -2147287035 )
          {
            v24 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, ulVal);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
              {
                v24 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v24 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v24 + 8) )
            {
              v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
              if ( *((_DWORD *)v33 + 499) != v9 )
                CallStackContext::TraceFailure(v33, "CWMProperty::SetNativeValue", 177, v9);
            }
            if ( g_wppLevels )
            {
              v35 = 21;
              goto LABEL_98;
            }
          }
          else
          {
            v9 = PropVariantCopy(this + 4, pvarSrc);
            if ( v9 < 0 )
            {
              v22 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
                CallStackTracing::s_wpInstance = v23;
                if ( v23
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
                {
                  v22 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v22 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v22 + 8) )
              {
                v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
                if ( *((_DWORD *)v32 + 499) != v9 )
                  CallStackContext::TraceFailure(v32, "CWMProperty::SetNativeValue", 175, v9);
              }
              if ( g_wppLevels )
              {
                v35 = 20;
                goto LABEL_98;
              }
            }
          }
        }
      }
      else
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, ulVal);
          CallStackTracing::s_wpInstance = v27;
          if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
          {
            v26 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v26 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v26 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
          if ( *((_DWORD *)v34 + 499) != v9 )
            CallStackContext::TraceFailure(v34, "CWMProperty::SetNativeValue", 181, v9);
        }
        if ( g_wppLevels )
        {
          v35 = 22;
          goto LABEL_98;
        }
      }
    }
  }
  else
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    v9 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v31 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v31, "CWMProperty::SetNativeValue", 189, -2147418113);
    }
    if ( g_wppLevels )
    {
      v35 = 23;
      goto LABEL_98;
    }
  }
LABEL_22:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v39);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180013870  push    rbx
0x180013872  push    rbp
0x180013873  push    rsi
0x180013874  push    rdi
0x180013875  push    r13
0x180013877  push    r14
0x180013879  sub     rsp, 58h
0x18001387d  mov     rsi, rcx
0x180013880  mov     rdi, rdx
0x180013883  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001388a  test    rcx, rcx
0x18001388d  jz      loc_180013997
0x180013893  cmp     byte ptr [rcx+8], 0
0x180013897  lea     r13, aCwmpropertySet; "CWMProperty::SetNativeValue"
0x18001389e  mov     r14d, 91h
0x1800138a4  jz      short loc_1800138CB
0x1800138a6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800138ab  mov     ecx, [rax+7C4h]
0x1800138b1  cmp     ecx, [rax+7C8h]
0x1800138b7  jnb     short loc_1800138C5
0x1800138b9  add     rcx, rcx
0x1800138bc  mov     [rax+rcx*8], r13
0x1800138c0  mov     [rax+rcx*8+8], r14d
0x1800138c5  inc     dword ptr [rax+7C4h]
0x1800138cb  lea     rbp, [rsi+60h]
0x1800138cf  mov     rcx, rbp; pvar
0x1800138d2  call    cs:__imp_PropVariantClear
0x1800138d9  nop     dword ptr [rax+rax+00h]
0x1800138de  mov     ebx, eax
0x1800138e0  test    eax, eax
0x1800138e2  js      loc_180013A06
0x1800138e8  lea     r14, [rsi+78h]
0x1800138ec  mov     rcx, r14; pvar
0x1800138ef  call    cs:__imp_PropVariantClear
0x1800138f6  nop     dword ptr [rax+rax+00h]
0x1800138fb  mov     ebx, eax
0x1800138fd  test    eax, eax
0x1800138ff  js      loc_180013A48
0x180013905  mov     rdx, rdi; pvarSrc
0x180013908  mov     rcx, r14; pvarDest
0x18001390b  call    cs:__imp_PropVariantCopy
0x180013912  nop     dword ptr [rax+rax+00h]
0x180013917  mov     ebx, eax
0x180013919  test    eax, eax
0x18001391b  js      loc_180013A8A
0x180013921  movzx   ecx, word ptr [rdi]
0x180013924  btr     ecx, 0Ch
0x180013928  sub     ecx, 8
0x18001392b  jz      short loc_1800139A8
0x18001392d  sub     ecx, 3
0x180013930  jz      short loc_1800139A8
0x180013932  sub     ecx, 7
0x180013935  jz      short loc_1800139A8
0x180013937  sub     ecx, 1
0x18001393a  jz      short loc_1800139A8
0x18001393c  sub     ecx, 2
0x18001393f  jz      short loc_1800139A8
0x180013941  sub     ecx, 0Ah
0x180013944  jz      short loc_1800139A8
0x180013946  sub     ecx, 22h ; '"'
0x180013949  jz      short loc_1800139A8
0x18001394b  cmp     ecx, 7
0x18001394e  jz      short loc_1800139A8
0x180013950  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013957  mov     ebx, 8000FFFFh
0x18001395c  test    rcx, rcx
0x18001395f  jnz     loc_180013D98
0x180013965  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001396c  nop     dword ptr [rax+rax+00h]
0x180013971  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013978  mov     rcx, rax
0x18001397b  test    rax, rax
0x18001397e  jnz     loc_180013D78
0x180013984  lea     rcx, qword_1801B97E0
0x18001398b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180013992  jmp     loc_180013D98
0x180013997  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001399c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800139a3  jmp     loc_180013893
0x1800139a8  movups  xmm0, cs:MF_MD_SHELLMULTI
0x1800139af  lea     rax, [rsp+88h+var_58]
0x1800139b4  mov     r8, rbp; struct tagPROPVARIANT *
0x1800139b7  movups  xmm1, cs:MF_MD_SHELLTYPE
0x1800139be  lea     r9, [rsp+88h+var_48]; struct _GUID
0x1800139c3  mov     [rsp+88h+var_68], rax; struct _GUID
0x1800139c8  mov     rdx, r14; struct tagPROPVARIANT *
0x1800139cb  mov     rcx, rsi; this
0x1800139ce  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x1800139d4  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x1800139da  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x1800139df  mov     ebx, eax
0x1800139e1  test    eax, eax
0x1800139e3  js      loc_180013DB9
0x1800139e9  lea     rcx, [rsp+88h+arg_0]; this
0x1800139f1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800139f6  mov     eax, ebx
0x1800139f8  add     rsp, 58h
0x1800139fc  pop     r14
0x1800139fe  pop     r13
0x180013a00  pop     rdi
0x180013a01  pop     rsi
0x180013a02  pop     rbp
0x180013a03  pop     rbx
0x180013a04  retn
0x180013a06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013a0d  test    rcx, rcx
0x180013a10  jnz     loc_180013CD5
0x180013a16  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013a1d  nop     dword ptr [rax+rax+00h]
0x180013a22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013a29  mov     rcx, rax
0x180013a2c  test    rax, rax
0x180013a2f  jnz     loc_180013CB5
0x180013a35  lea     rcx, qword_1801B97E0
0x180013a3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180013a43  jmp     loc_180013CD5
0x180013a48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013a4f  test    rcx, rcx
0x180013a52  jnz     loc_180013D16
0x180013a58  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013a5f  nop     dword ptr [rax+rax+00h]
0x180013a64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013a6b  mov     rcx, rax
0x180013a6e  test    rax, rax
0x180013a71  jnz     loc_180013CF6
0x180013a77  lea     rcx, qword_1801B97E0
0x180013a7e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180013a85  jmp     loc_180013D16
0x180013a8a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013a91  test    rcx, rcx
0x180013a94  jnz     loc_180013D57
0x180013a9a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013aa1  nop     dword ptr [rax+rax+00h]
0x180013aa6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013aad  mov     rcx, rax
0x180013ab0  test    rax, rax
0x180013ab3  jnz     loc_180013D37
0x180013ab9  lea     rcx, qword_1801B97E0
0x180013ac0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180013ac7  jmp     loc_180013D57
0x180013acc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013ad3  test    rcx, rcx
0x180013ad6  jnz     loc_180013E49
0x180013adc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013ae3  nop     dword ptr [rax+rax+00h]
0x180013ae8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013aef  mov     rcx, rax
0x180013af2  test    rax, rax
0x180013af5  jnz     loc_180013E29
0x180013afb  lea     rcx, qword_1801B97E0
0x180013b02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180013b09  jmp     loc_180013E49
0x180013b0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013b15  test    rcx, rcx
0x180013b18  jnz     loc_180013E87
0x180013b1e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013b25  nop     dword ptr [rax+rax+00h]
0x180013b2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013b31  mov     rcx, rax
0x180013b34  test    rax, rax
0x180013b37  jnz     loc_180013E67
0x180013b3d  lea     rcx, qword_1801B97E0
0x180013b44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180013b4b  jmp     loc_180013E87
0x180013b50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013b57  test    rcx, rcx
0x180013b5a  jnz     loc_180013EC5
0x180013b60  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013b67  nop     dword ptr [rax+rax+00h]
0x180013b6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013b73  mov     rcx, rax
0x180013b76  test    rax, rax
0x180013b79  jnz     loc_180013EA5
0x180013b7f  lea     rcx, qword_1801B97E0
0x180013b86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180013b8d  jmp     loc_180013EC5
0x180013b92  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013b97  cmp     [rax+7CCh], ebx
0x180013b9d  jz      loc_180013CDF
0x180013ba3  mov     r9d, ebx; int
0x180013ba6  mov     r8d, r14d; int
0x180013ba9  mov     rdx, r13; char *
0x180013bac  mov     rcx, rax; this
0x180013baf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013bb4  jmp     loc_180013CDF
0x180013bb9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013bbe  cmp     [rax+7CCh], ebx
0x180013bc4  jz      loc_180013D20
0x180013bca  mov     r9d, ebx; int
0x180013bcd  mov     r8d, 92h; int
0x180013bd3  mov     rdx, r13; char *
0x180013bd6  mov     rcx, rax; this
0x180013bd9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013bde  jmp     loc_180013D20
0x180013be3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013be8  cmp     [rax+7CCh], ebx
0x180013bee  jz      loc_180013D61
0x180013bf4  mov     r9d, ebx; int
0x180013bf7  mov     r8d, 94h; int
0x180013bfd  mov     rdx, r13; char *
0x180013c00  mov     rcx, rax; this
0x180013c03  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013c08  jmp     loc_180013D61
0x180013c0d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013c12  cmp     [rax+7CCh], ebx
0x180013c18  jz      loc_180013DA2
0x180013c1e  mov     r9d, ebx; int
0x180013c21  mov     r8d, 0BDh; int
0x180013c27  mov     rdx, r13; char *
0x180013c2a  mov     rcx, rax; this
0x180013c2d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013c32  jmp     loc_180013DA2
0x180013c37  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013c3c  cmp     [rax+7CCh], ebx
0x180013c42  jz      loc_180013E53
0x180013c48  mov     r9d, ebx; int
0x180013c4b  mov     r8d, 0AFh; int
0x180013c51  mov     rdx, r13; char *
0x180013c54  mov     rcx, rax; this
0x180013c57  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013c5c  jmp     loc_180013E53
0x180013c61  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013c66  cmp     [rax+7CCh], ebx
0x180013c6c  jz      loc_180013E91
0x180013c72  mov     r9d, ebx; int
0x180013c75  mov     r8d, 0B1h; int
0x180013c7b  mov     rdx, r13; char *
0x180013c7e  mov     rcx, rax; this
0x180013c81  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013c86  jmp     loc_180013E91
0x180013c8b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013c90  cmp     [rax+7CCh], ebx
0x180013c96  jz      loc_180013ECF
0x180013c9c  mov     r9d, ebx; int
0x180013c9f  mov     r8d, 0B5h; int
0x180013ca5  mov     rdx, r13; char *
0x180013ca8  mov     rcx, rax; this
0x180013cab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013cb0  jmp     loc_180013ECF
0x180013cb5  mov     rax, [rax]
0x180013cb8  mov     edx, 7F0h
0x180013cbd  mov     rax, [rax+8]
0x180013cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cc6  test    eax, eax
0x180013cc8  jz      loc_180013A35
0x180013cce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180013cd5  cmp     byte ptr [rcx+8], 0
0x180013cd9  jnz     loc_180013B92
0x180013cdf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180013ce6  jb      loc_1800139E9
0x180013cec  mov     edx, 11h
0x180013cf1  jmp     loc_180013EE1
0x180013cf6  mov     rax, [rax]
0x180013cf9  mov     edx, 7F0h
0x180013cfe  mov     rax, [rax+8]
0x180013d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d07  test    eax, eax
0x180013d09  jz      loc_180013A77
0x180013d0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180013d16  cmp     byte ptr [rcx+8], 0
0x180013d1a  jnz     loc_180013BB9
0x180013d20  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180013d27  jb      loc_1800139E9
0x180013d2d  mov     edx, 12h
0x180013d32  jmp     loc_180013EE1
0x180013d37  mov     rax, [rax]
0x180013d3a  mov     edx, 7F0h
0x180013d3f  mov     rax, [rax+8]
0x180013d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d48  test    eax, eax
0x180013d4a  jz      loc_180013AB9
0x180013d50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180013d57  cmp     byte ptr [rcx+8], 0
0x180013d5b  jnz     loc_180013BE3
0x180013d61  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180013d68  jb      loc_1800139E9
0x180013d6e  mov     edx, 13h
0x180013d73  jmp     loc_180013EE1
0x180013d78  mov     rax, [rax]
0x180013d7b  mov     edx, 7F0h
0x180013d80  mov     rax, [rax+8]
0x180013d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d89  test    eax, eax
0x180013d8b  jz      loc_180013984
0x180013d91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180013d98  cmp     byte ptr [rcx+8], 0
0x180013d9c  jnz     loc_180013C0D
0x180013da2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180013da9  jb      loc_1800139E9
0x180013daf  mov     edx, 17h
0x180013db4  jmp     loc_180013EE1
0x180013db9  cmp     word ptr [rdi], 41h ; 'A'
0x180013dbd  jnz     loc_180013B50
0x180013dc3  mov     edx, [rdi+8]; cbMax
0x180013dc6  test    edx, edx
0x180013dc8  jz      loc_180013B50
0x180013dce  cmp     edx, 8
0x180013dd1  jb      short loc_180013DF0
0x180013dd3  mov     rcx, [rdi+10h]; pprop
0x180013dd7  mov     r8, rbp; ppropvar
  ... truncated ...
```
