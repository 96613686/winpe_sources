# CWMProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x180027ce0`
- end: `0x18002832b`
- name: `?SetNativeValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1611`
- prototype: `__int64 __fastcall(CWMProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007e7f0`
- `0x1800a4d60`
- `0x1800cb6d0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180026f50`
- `0x180027ce0`
- `0x180071a44`
- `0x180073b14`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027dc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027e6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027ea9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027ee5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027f21`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027f5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027f99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027dc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027e6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027ea9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027ee5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027f21`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027f5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027f99`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180027d6f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002823b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180027d6f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002823b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180027d42`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180027d59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180027d42`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180027d59`
- `PROPSYS!StgDeserializePropVariant` at `0x18002820d`
- `PROPSYS!StgDeserializePropVariant` at `0x18002820d`

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
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  __int64 ulVal; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  struct CallStackContext *v37; // rax
  struct CallStackContext *v38; // rax
  struct CallStackContext *v39; // rax
  struct CallStackContext *v40; // rax
  struct CallStackContext *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  struct _GUID v47; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v48; // [rsp+40h] [rbp-48h] BYREF
  char v49; // [rsp+90h] [rbp+8h] BYREF

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
    v24 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
      {
        v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v36 + 499) != v9 )
        CallStackContext::TraceFailure(v36, "CWMProperty::SetNativeValue", 145, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_22;
    v43 = 17;
LABEL_98:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v43, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v9);
    goto LABEL_22;
  }
  v9 = PropVariantClear(this + 5);
  if ( v9 < 0 )
  {
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v26 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
      if ( *((_DWORD *)v37 + 499) != v9 )
        CallStackContext::TraceFailure(v37, "CWMProperty::SetNativeValue", 146, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_22;
    v43 = 18;
    goto LABEL_98;
  }
  v9 = PropVariantCopy(this + 5, pvarSrc);
  if ( v9 < 0 )
  {
    v28 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
      CallStackTracing::s_wpInstance = v29;
      if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
      {
        v28 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v28 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v28 + 8) )
    {
      v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
      if ( *((_DWORD *)v38 + 499) != v9 )
        CallStackContext::TraceFailure(v38, "CWMProperty::SetNativeValue", 148, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_22;
    v43 = 19;
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
    v47 = (struct _GUID)MF_MD_SHELLMULTI;
    v48 = (struct _GUID)MF_MD_SHELLTYPE;
    v9 = CWMProperty::TranslateValue((CWMProperty *)this, this + 5, this + 4, &v48, &v47);
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
            v32 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, ulVal, v21, v22);
              CallStackTracing::s_wpInstance = v33;
              if ( v33
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
              {
                v32 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v32 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v32 + 8) )
            {
              v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
              if ( *((_DWORD *)v41 + 499) != v9 )
                CallStackContext::TraceFailure(v41, "CWMProperty::SetNativeValue", 177, v9);
            }
            if ( g_wppLevels )
            {
              v43 = 21;
              goto LABEL_98;
            }
          }
          else
          {
            v9 = PropVariantCopy(this + 4, pvarSrc);
            if ( v9 < 0 )
            {
              v30 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44, v45, v46);
                CallStackTracing::s_wpInstance = v31;
                if ( v31
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
                {
                  v30 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v30 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v30 + 8) )
              {
                v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
                if ( *((_DWORD *)v40 + 499) != v9 )
                  CallStackContext::TraceFailure(v40, "CWMProperty::SetNativeValue", 175, v9);
              }
              if ( g_wppLevels )
              {
                v43 = 20;
                goto LABEL_98;
              }
            }
          }
        }
      }
      else
      {
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, ulVal, v21, v22);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v42 + 499) != v9 )
            CallStackContext::TraceFailure(v42, "CWMProperty::SetNativeValue", 181, v9);
        }
        if ( g_wppLevels )
        {
          v43 = 22;
          goto LABEL_98;
        }
      }
    }
  }
  else
  {
    v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    v9 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v39 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v39, "CWMProperty::SetNativeValue", 189, -2147418113);
    }
    if ( g_wppLevels )
    {
      v43 = 23;
      goto LABEL_98;
    }
  }
LABEL_22:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v49);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180027ce0  push    rbx
0x180027ce2  push    rbp
0x180027ce3  push    rsi
0x180027ce4  push    rdi
0x180027ce5  push    r13
0x180027ce7  push    r14
0x180027ce9  sub     rsp, 58h
0x180027ced  mov     rsi, rcx
0x180027cf0  mov     rdi, rdx
0x180027cf3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180027cfa  test    rcx, rcx
0x180027cfd  jz      loc_180027DEF
0x180027d03  cmp     byte ptr [rcx+8], 0
0x180027d07  lea     r13, aCwmpropertySet; "CWMProperty::SetNativeValue"
0x180027d0e  mov     r14d, 91h
0x180027d14  jz      short loc_180027D3B
0x180027d16  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027d1b  mov     ecx, [rax+7C4h]
0x180027d21  cmp     ecx, [rax+7C8h]
0x180027d27  jnb     short loc_180027D35
0x180027d29  add     rcx, rcx
0x180027d2c  mov     [rax+rcx*8], r13
0x180027d30  mov     [rax+rcx*8+8], r14d
0x180027d35  inc     dword ptr [rax+7C4h]
0x180027d3b  lea     rbp, [rsi+60h]
0x180027d3f  mov     rcx, rbp; pvar
0x180027d42  call    cs:__imp_PropVariantClear
0x180027d48  mov     ebx, eax
0x180027d4a  test    eax, eax
0x180027d4c  js      loc_180027E5D
0x180027d52  lea     r14, [rsi+78h]
0x180027d56  mov     rcx, r14; pvar
0x180027d59  call    cs:__imp_PropVariantClear
0x180027d5f  mov     ebx, eax
0x180027d61  test    eax, eax
0x180027d63  js      loc_180027E99
0x180027d69  mov     rdx, rdi; pvarSrc
0x180027d6c  mov     rcx, r14; pvarDest
0x180027d6f  call    cs:__imp_PropVariantCopy
0x180027d75  mov     ebx, eax
0x180027d77  test    eax, eax
0x180027d79  js      loc_180027ED5
0x180027d7f  movzx   ecx, word ptr [rdi]
0x180027d82  btr     ecx, 0Ch
0x180027d86  sub     ecx, 8
0x180027d89  jz      short loc_180027E00
0x180027d8b  sub     ecx, 3
0x180027d8e  jz      short loc_180027E00
0x180027d90  sub     ecx, 7
0x180027d93  jz      short loc_180027E00
0x180027d95  sub     ecx, 1
0x180027d98  jz      short loc_180027E00
0x180027d9a  sub     ecx, 2
0x180027d9d  jz      short loc_180027E00
0x180027d9f  sub     ecx, 0Ah
0x180027da2  jz      short loc_180027E00
0x180027da4  sub     ecx, 22h ; '"'
0x180027da7  jz      short loc_180027E00
0x180027da9  cmp     ecx, 7
0x180027dac  jz      short loc_180027E00
0x180027dae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027db5  mov     ebx, 8000FFFFh
0x180027dba  test    rcx, rcx
0x180027dbd  jnz     loc_1800281CB
0x180027dc3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027dc9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027dd0  mov     rcx, rax
0x180027dd3  test    rax, rax
0x180027dd6  jnz     loc_1800281AB
0x180027ddc  lea     rcx, qword_1801B07E0
0x180027de3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027dea  jmp     loc_1800281CB
0x180027def  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180027df4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027dfb  jmp     loc_180027D03
0x180027e00  movups  xmm0, cs:MF_MD_SHELLMULTI
0x180027e07  lea     rax, [rsp+88h+var_58]
0x180027e0c  mov     r8, rbp; struct tagPROPVARIANT *
0x180027e0f  movups  xmm1, cs:MF_MD_SHELLTYPE
0x180027e16  lea     r9, [rsp+88h+var_48]; struct _GUID
0x180027e1b  mov     [rsp+88h+var_68], rax; struct _GUID
0x180027e20  mov     rdx, r14; struct tagPROPVARIANT *
0x180027e23  mov     rcx, rsi; this
0x180027e26  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x180027e2c  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x180027e32  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x180027e37  mov     ebx, eax
0x180027e39  test    eax, eax
0x180027e3b  js      loc_1800281EC
0x180027e41  lea     rcx, [rsp+88h+arg_0]; this
0x180027e49  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180027e4e  mov     eax, ebx
0x180027e50  add     rsp, 58h
0x180027e54  pop     r14
0x180027e56  pop     r13
0x180027e58  pop     rdi
0x180027e59  pop     rsi
0x180027e5a  pop     rbp
0x180027e5b  pop     rbx
0x180027e5c  retn
0x180027e5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027e64  test    rcx, rcx
0x180027e67  jnz     loc_180028108
0x180027e6d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027e73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027e7a  mov     rcx, rax
0x180027e7d  test    rax, rax
0x180027e80  jnz     loc_1800280E8
0x180027e86  lea     rcx, qword_1801B07E0
0x180027e8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027e94  jmp     loc_180028108
0x180027e99  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027ea0  test    rcx, rcx
0x180027ea3  jnz     loc_180028149
0x180027ea9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027eaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027eb6  mov     rcx, rax
0x180027eb9  test    rax, rax
0x180027ebc  jnz     loc_180028129
0x180027ec2  lea     rcx, qword_1801B07E0
0x180027ec9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027ed0  jmp     loc_180028149
0x180027ed5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027edc  test    rcx, rcx
0x180027edf  jnz     loc_18002818A
0x180027ee5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027eeb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027ef2  mov     rcx, rax
0x180027ef5  test    rax, rax
0x180027ef8  jnz     loc_18002816A
0x180027efe  lea     rcx, qword_1801B07E0
0x180027f05  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027f0c  jmp     loc_18002818A
0x180027f11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027f18  test    rcx, rcx
0x180027f1b  jnz     loc_180028270
0x180027f21  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027f27  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027f2e  mov     rcx, rax
0x180027f31  test    rax, rax
0x180027f34  jnz     loc_180028250
0x180027f3a  lea     rcx, qword_1801B07E0
0x180027f41  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027f48  jmp     loc_180028270
0x180027f4d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027f54  test    rcx, rcx
0x180027f57  jnz     loc_1800282AE
0x180027f5d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027f63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027f6a  mov     rcx, rax
0x180027f6d  test    rax, rax
0x180027f70  jnz     loc_18002828E
0x180027f76  lea     rcx, qword_1801B07E0
0x180027f7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027f84  jmp     loc_1800282AE
0x180027f89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027f90  test    rcx, rcx
0x180027f93  jnz     loc_1800282EC
0x180027f99  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027f9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027fa6  mov     rcx, rax
0x180027fa9  test    rax, rax
0x180027fac  jnz     loc_1800282CC
0x180027fb2  lea     rcx, qword_1801B07E0
0x180027fb9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027fc0  jmp     loc_1800282EC
0x180027fc5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027fca  cmp     [rax+7CCh], ebx
0x180027fd0  jz      loc_180028112
0x180027fd6  mov     r9d, ebx; int
0x180027fd9  mov     r8d, r14d; int
0x180027fdc  mov     rdx, r13; char *
0x180027fdf  mov     rcx, rax; this
0x180027fe2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027fe7  jmp     loc_180028112
0x180027fec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027ff1  cmp     [rax+7CCh], ebx
0x180027ff7  jz      loc_180028153
0x180027ffd  mov     r9d, ebx; int
0x180028000  mov     r8d, 92h; int
0x180028006  mov     rdx, r13; char *
0x180028009  mov     rcx, rax; this
0x18002800c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180028011  jmp     loc_180028153
0x180028016  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002801b  cmp     [rax+7CCh], ebx
0x180028021  jz      loc_180028194
0x180028027  mov     r9d, ebx; int
0x18002802a  mov     r8d, 94h; int
0x180028030  mov     rdx, r13; char *
0x180028033  mov     rcx, rax; this
0x180028036  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002803b  jmp     loc_180028194
0x180028040  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180028045  cmp     [rax+7CCh], ebx
0x18002804b  jz      loc_1800281D5
0x180028051  mov     r9d, ebx; int
0x180028054  mov     r8d, 0BDh; int
0x18002805a  mov     rdx, r13; char *
0x18002805d  mov     rcx, rax; this
0x180028060  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180028065  jmp     loc_1800281D5
0x18002806a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002806f  cmp     [rax+7CCh], ebx
0x180028075  jz      loc_18002827A
0x18002807b  mov     r9d, ebx; int
0x18002807e  mov     r8d, 0AFh; int
0x180028084  mov     rdx, r13; char *
0x180028087  mov     rcx, rax; this
0x18002808a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002808f  jmp     loc_18002827A
0x180028094  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180028099  cmp     [rax+7CCh], ebx
0x18002809f  jz      loc_1800282B8
0x1800280a5  mov     r9d, ebx; int
0x1800280a8  mov     r8d, 0B1h; int
0x1800280ae  mov     rdx, r13; char *
0x1800280b1  mov     rcx, rax; this
0x1800280b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800280b9  jmp     loc_1800282B8
0x1800280be  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800280c3  cmp     [rax+7CCh], ebx
0x1800280c9  jz      loc_1800282F6
0x1800280cf  mov     r9d, ebx; int
0x1800280d2  mov     r8d, 0B5h; int
0x1800280d8  mov     rdx, r13; char *
0x1800280db  mov     rcx, rax; this
0x1800280de  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800280e3  jmp     loc_1800282F6
0x1800280e8  mov     rax, [rax]
0x1800280eb  mov     edx, 7F0h
0x1800280f0  mov     rax, [rax+8]
0x1800280f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280f9  test    eax, eax
0x1800280fb  jz      loc_180027E86
0x180028101  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180028108  cmp     byte ptr [rcx+8], 0
0x18002810c  jnz     loc_180027FC5
0x180028112  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180028119  jb      loc_180027E41
0x18002811f  mov     edx, 11h
0x180028124  jmp     loc_180028308
0x180028129  mov     rax, [rax]
0x18002812c  mov     edx, 7F0h
0x180028131  mov     rax, [rax+8]
0x180028135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002813a  test    eax, eax
0x18002813c  jz      loc_180027EC2
0x180028142  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180028149  cmp     byte ptr [rcx+8], 0
0x18002814d  jnz     loc_180027FEC
0x180028153  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002815a  jb      loc_180027E41
0x180028160  mov     edx, 12h
0x180028165  jmp     loc_180028308
0x18002816a  mov     rax, [rax]
0x18002816d  mov     edx, 7F0h
0x180028172  mov     rax, [rax+8]
0x180028176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002817b  test    eax, eax
0x18002817d  jz      loc_180027EFE
0x180028183  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002818a  cmp     byte ptr [rcx+8], 0
0x18002818e  jnz     loc_180028016
0x180028194  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002819b  jb      loc_180027E41
0x1800281a1  mov     edx, 13h
0x1800281a6  jmp     loc_180028308
0x1800281ab  mov     rax, [rax]
0x1800281ae  mov     edx, 7F0h
0x1800281b3  mov     rax, [rax+8]
0x1800281b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281bc  test    eax, eax
0x1800281be  jz      loc_180027DDC
0x1800281c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800281cb  cmp     byte ptr [rcx+8], 0
0x1800281cf  jnz     loc_180028040
0x1800281d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800281dc  jb      loc_180027E41
0x1800281e2  mov     edx, 17h
0x1800281e7  jmp     loc_180028308
0x1800281ec  cmp     word ptr [rdi], 41h ; 'A'
0x1800281f0  jnz     loc_180027F89
0x1800281f6  mov     edx, [rdi+8]; cbMax
0x1800281f9  test    edx, edx
0x1800281fb  jz      loc_180027F89
0x180028201  cmp     edx, 8
0x180028204  jb      short loc_18002821D
0x180028206  mov     rcx, [rdi+10h]; pprop
0x18002820a  mov     r8, rbp; ppropvar
0x18002820d  call    cs:__imp_StgDeserializePropVariant
0x180028213  mov     ebx, eax
0x180028215  test    eax, eax
0x180028217  jns     loc_180027E41
0x18002821d  cmp     ebx, 8007000Eh
0x180028223  jz      loc_180027F4D
0x180028229  cmp     ebx, 80030005h
0x18002822f  jz      loc_180027F4D
0x180028235  mov     rdx, rdi; pvarSrc
0x180028238  mov     rcx, rbp; pvarDest
  ... truncated ...
```
