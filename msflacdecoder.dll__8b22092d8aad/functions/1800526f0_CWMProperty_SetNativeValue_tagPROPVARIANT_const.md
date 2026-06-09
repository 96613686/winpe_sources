# CWMProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x1800526f0`
- end: `0x180052c53`
- name: `?SetNativeValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1379`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180051fa0`
- `0x180052c60`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x1800526f0`
- `0x180054820`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180052867`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180052a71`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180052867`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180052a71`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052727`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800527c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052727`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800527c6`
- `PROPSYS!StgDeserializePropVariant` at `0x180052a43`
- `PROPSYS!StgDeserializePropVariant` at `0x180052a43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052743`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800527e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052883`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052962`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052a8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052b18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052ba3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052743`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800527e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052883`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052962`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052a8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052b18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052ba3`

## pseudocode

```c
__int64 __fastcall CWMProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
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
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 ulVal; // rdx
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  struct _GUID v33; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v34; // [rsp+40h] [rbp-48h] BYREF
  char v35; // [rsp+90h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v35, "CWMProperty::SetNativeValue", 145);
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
          v33 = (struct _GUID)MF_MD_SHELLMULTI;
          v34 = (struct _GUID)MF_MD_SHELLTYPE;
          v5 = CWMProperty::TranslateValue((CWMProperty *)this, this + 5, this + 4, &v34, &v33);
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
                  v26 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, ulVal);
                    CallStackTracing::s_wpInstance = v27;
                    if ( v27
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
                    {
                      v26 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v26 = &qword_18006EB20;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                    }
                  }
                  if ( *((_BYTE *)v26 + 8) )
                  {
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                      CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::SetNativeValue", 177, v5);
                  }
                  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v9 = 21;
                    goto LABEL_90;
                  }
                }
                else
                {
                  v5 = PropVariantCopy(this + 4, a2);
                  if ( v5 < 0 )
                  {
                    v23 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
                      CallStackTracing::s_wpInstance = v24;
                      if ( v24
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(
                             v24,
                             2032) )
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
                        CallStackContext::TraceFailure(v25, "CWMProperty::SetNativeValue", 175, v5);
                    }
                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    {
                      v9 = 20;
                      goto LABEL_90;
                    }
                  }
                }
              }
            }
            else
            {
              v29 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, ulVal);
                CallStackTracing::s_wpInstance = v30;
                if ( v30
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
                {
                  v29 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v29 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v29 + 8) )
              {
                v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
                if ( *((_DWORD *)v31 + 499) != v5 )
                  CallStackContext::TraceFailure(v31, "CWMProperty::SetNativeValue", 181, v5);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v9 = 22;
                goto LABEL_90;
              }
            }
          }
        }
        else
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
          v5 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
            CallStackTracing::s_wpInstance = v19;
            if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
            {
              v18 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v18 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v18 + 8) )
          {
            v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
            if ( *((_DWORD *)v20 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v20, "CWMProperty::SetNativeValue", 189, -2147418113);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 23;
            goto LABEL_90;
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
            CallStackContext::TraceFailure(v17, "CWMProperty::SetNativeValue", 148, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 19;
          goto LABEL_90;
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
          CallStackContext::TraceFailure(v13, "CWMProperty::SetNativeValue", 146, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 18;
        goto LABEL_90;
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
        CallStackContext::TraceFailure(v8, "CWMProperty::SetNativeValue", 145, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 17;
LABEL_90:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v35);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800526f0  mov     rax, rsp
0x1800526f3  push    rbx
0x1800526f4  push    rbp
0x1800526f5  push    rsi
0x1800526f6  push    rdi
0x1800526f7  push    r12
0x1800526f9  push    r14
0x1800526fb  sub     rsp, 58h
0x1800526ff  mov     rdi, rdx
0x180052702  lea     r12, aCwmpropertySet; "CWMProperty::SetNativeValue"
0x180052709  mov     rsi, rcx
0x18005270c  mov     ebp, 91h
0x180052711  mov     r8d, ebp; int
0x180052714  lea     rcx, [rax+8]; this
0x180052718  mov     rdx, r12; char *
0x18005271b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180052720  lea     r14, [rsi+60h]
0x180052724  mov     rcx, r14; pvar
0x180052727  call    cs:__imp_PropVariantClear
0x18005272d  mov     ebx, eax
0x18005272f  test    eax, eax
0x180052731  jns     loc_1800527BF
0x180052737  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005273e  test    rcx, rcx
0x180052741  jnz     short loc_180052784
0x180052743  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052749  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052750  mov     rcx, rax
0x180052753  test    rax, rax
0x180052756  jz      short loc_180052776
0x180052758  mov     rax, [rax]
0x18005275b  mov     edx, 7F0h
0x180052760  mov     rax, [rax+8]
0x180052764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052769  test    eax, eax
0x18005276b  jz      short loc_180052776
0x18005276d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052774  jmp     short loc_180052784
0x180052776  lea     rcx, qword_18006EB20; this
0x18005277d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052784  cmp     byte ptr [rcx+8], 0
0x180052788  jz      short loc_1800527A8
0x18005278a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005278f  cmp     [rax+7CCh], ebx
0x180052795  jz      short loc_1800527A8
0x180052797  mov     r9d, ebx; int
0x18005279a  mov     r8d, ebp; int
0x18005279d  mov     rdx, r12; char *
0x1800527a0  mov     rcx, rax; this
0x1800527a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800527a8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800527ad  cmp     al, 1
0x1800527af  jb      loc_180052C37
0x1800527b5  mov     edx, 11h
0x1800527ba  jmp     loc_180052C19
0x1800527bf  lea     rbp, [rsi+78h]
0x1800527c3  mov     rcx, rbp; pvar
0x1800527c6  call    cs:__imp_PropVariantClear
0x1800527cc  mov     ebx, eax
0x1800527ce  test    eax, eax
0x1800527d0  jns     loc_180052861
0x1800527d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800527dd  test    rcx, rcx
0x1800527e0  jnz     short loc_180052823
0x1800527e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800527e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800527ef  mov     rcx, rax
0x1800527f2  test    rax, rax
0x1800527f5  jz      short loc_180052815
0x1800527f7  mov     rax, [rax]
0x1800527fa  mov     edx, 7F0h
0x1800527ff  mov     rax, [rax+8]
0x180052803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052808  test    eax, eax
0x18005280a  jz      short loc_180052815
0x18005280c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052813  jmp     short loc_180052823
0x180052815  lea     rcx, qword_18006EB20; this
0x18005281c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052823  cmp     byte ptr [rcx+8], 0
0x180052827  jz      short loc_18005284A
0x180052829  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005282e  cmp     [rax+7CCh], ebx
0x180052834  jz      short loc_18005284A
0x180052836  mov     r9d, ebx; int
0x180052839  mov     r8d, 92h; int
0x18005283f  mov     rdx, r12; char *
0x180052842  mov     rcx, rax; this
0x180052845  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005284a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005284f  cmp     al, 1
0x180052851  jb      loc_180052C37
0x180052857  mov     edx, 12h
0x18005285c  jmp     loc_180052C19
0x180052861  mov     rdx, rdi; pvarSrc
0x180052864  mov     rcx, rbp; pvarDest
0x180052867  call    cs:__imp_PropVariantCopy
0x18005286d  mov     ebx, eax
0x18005286f  test    eax, eax
0x180052871  jns     loc_180052902
0x180052877  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005287e  test    rcx, rcx
0x180052881  jnz     short loc_1800528C4
0x180052883  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052889  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052890  mov     rcx, rax
0x180052893  test    rax, rax
0x180052896  jz      short loc_1800528B6
0x180052898  mov     rax, [rax]
0x18005289b  mov     edx, 7F0h
0x1800528a0  mov     rax, [rax+8]
0x1800528a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528a9  test    eax, eax
0x1800528ab  jz      short loc_1800528B6
0x1800528ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800528b4  jmp     short loc_1800528C4
0x1800528b6  lea     rcx, qword_18006EB20; this
0x1800528bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800528c4  cmp     byte ptr [rcx+8], 0
0x1800528c8  jz      short loc_1800528EB
0x1800528ca  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800528cf  cmp     [rax+7CCh], ebx
0x1800528d5  jz      short loc_1800528EB
0x1800528d7  mov     r9d, ebx; int
0x1800528da  mov     r8d, 94h; int
0x1800528e0  mov     rdx, r12; char *
0x1800528e3  mov     rcx, rax; this
0x1800528e6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800528eb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800528f0  cmp     al, 1
0x1800528f2  jb      loc_180052C37
0x1800528f8  mov     edx, 13h
0x1800528fd  jmp     loc_180052C19
0x180052902  movzx   ecx, word ptr [rdi]
0x180052905  btr     ecx, 0Ch
0x180052909  sub     ecx, 8
0x18005290c  jz      loc_1800529E1
0x180052912  sub     ecx, 3
0x180052915  jz      loc_1800529E1
0x18005291b  sub     ecx, 7
0x18005291e  jz      loc_1800529E1
0x180052924  sub     ecx, 1
0x180052927  jz      loc_1800529E1
0x18005292d  sub     ecx, 2
0x180052930  jz      loc_1800529E1
0x180052936  sub     ecx, 0Ah
0x180052939  jz      loc_1800529E1
0x18005293f  sub     ecx, 22h ; '"'
0x180052942  jz      loc_1800529E1
0x180052948  cmp     ecx, 7
0x18005294b  jz      loc_1800529E1
0x180052951  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052958  mov     ebx, 8000FFFFh
0x18005295d  test    rcx, rcx
0x180052960  jnz     short loc_1800529A3
0x180052962  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052968  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005296f  mov     rcx, rax
0x180052972  test    rax, rax
0x180052975  jz      short loc_180052995
0x180052977  mov     rax, [rax]
0x18005297a  mov     edx, 7F0h
0x18005297f  mov     rax, [rax+8]
0x180052983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052988  test    eax, eax
0x18005298a  jz      short loc_180052995
0x18005298c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052993  jmp     short loc_1800529A3
0x180052995  lea     rcx, qword_18006EB20; this
0x18005299c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800529a3  cmp     byte ptr [rcx+8], 0
0x1800529a7  jz      short loc_1800529CA
0x1800529a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800529ae  cmp     [rax+7CCh], ebx
0x1800529b4  jz      short loc_1800529CA
0x1800529b6  mov     r9d, ebx; int
0x1800529b9  mov     r8d, 0BDh; int
0x1800529bf  mov     rdx, r12; char *
0x1800529c2  mov     rcx, rax; this
0x1800529c5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800529ca  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800529cf  cmp     al, 1
0x1800529d1  jb      loc_180052C37
0x1800529d7  mov     edx, 17h
0x1800529dc  jmp     loc_180052C19
0x1800529e1  movups  xmm0, cs:MF_MD_SHELLMULTI
0x1800529e8  lea     rax, [rsp+88h+var_58]
0x1800529ed  mov     r8, r14; struct tagPROPVARIANT *
0x1800529f0  movups  xmm1, cs:MF_MD_SHELLTYPE
0x1800529f7  lea     r9, [rsp+88h+var_48]; struct _GUID
0x1800529fc  mov     [rsp+88h+var_68], rax; struct _GUID
0x180052a01  mov     rdx, rbp; struct tagPROPVARIANT *
0x180052a04  mov     rcx, rsi; this
0x180052a07  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x180052a0d  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x180052a13  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x180052a18  mov     ebx, eax
0x180052a1a  test    eax, eax
0x180052a1c  jns     loc_180052C37
0x180052a22  cmp     word ptr [rdi], 41h ; 'A'
0x180052a26  jnz     loc_180052B97
0x180052a2c  mov     edx, [rdi+8]; cbMax
0x180052a2f  test    edx, edx
0x180052a31  jz      loc_180052B97
0x180052a37  cmp     edx, 8
0x180052a3a  jb      short loc_180052A53
0x180052a3c  mov     rcx, [rdi+10h]; pprop
0x180052a40  mov     r8, r14; ppropvar
0x180052a43  call    cs:__imp_StgDeserializePropVariant
0x180052a49  mov     ebx, eax
0x180052a4b  test    eax, eax
0x180052a4d  jns     loc_180052C37
0x180052a53  cmp     ebx, 8007000Eh
0x180052a59  jz      loc_180052B0C
0x180052a5f  cmp     ebx, 80030005h
0x180052a65  jz      loc_180052B0C
0x180052a6b  mov     rdx, rdi; pvarSrc
0x180052a6e  mov     rcx, r14; pvarDest
0x180052a71  call    cs:__imp_PropVariantCopy
0x180052a77  mov     ebx, eax
0x180052a79  test    eax, eax
0x180052a7b  jns     loc_180052C37
0x180052a81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052a88  test    rcx, rcx
0x180052a8b  jnz     short loc_180052ACE
0x180052a8d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052a93  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052a9a  mov     rcx, rax
0x180052a9d  test    rax, rax
0x180052aa0  jz      short loc_180052AC0
0x180052aa2  mov     rax, [rax]
0x180052aa5  mov     edx, 7F0h
0x180052aaa  mov     rax, [rax+8]
0x180052aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ab3  test    eax, eax
0x180052ab5  jz      short loc_180052AC0
0x180052ab7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052abe  jmp     short loc_180052ACE
0x180052ac0  lea     rcx, qword_18006EB20; this
0x180052ac7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ace  cmp     byte ptr [rcx+8], 0
0x180052ad2  jz      short loc_180052AF5
0x180052ad4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052ad9  cmp     [rax+7CCh], ebx
0x180052adf  jz      short loc_180052AF5
0x180052ae1  mov     r9d, ebx; int
0x180052ae4  mov     r8d, 0AFh; int
0x180052aea  mov     rdx, r12; char *
0x180052aed  mov     rcx, rax; this
0x180052af0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052af5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180052afa  cmp     al, 1
0x180052afc  jb      loc_180052C37
0x180052b02  mov     edx, 14h
0x180052b07  jmp     loc_180052C19
0x180052b0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052b13  test    rcx, rcx
0x180052b16  jnz     short loc_180052B59
0x180052b18  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052b1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052b25  mov     rcx, rax
0x180052b28  test    rax, rax
0x180052b2b  jz      short loc_180052B4B
0x180052b2d  mov     rax, [rax]
0x180052b30  mov     edx, 7F0h
0x180052b35  mov     rax, [rax+8]
0x180052b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b3e  test    eax, eax
0x180052b40  jz      short loc_180052B4B
0x180052b42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052b49  jmp     short loc_180052B59
0x180052b4b  lea     rcx, qword_18006EB20; this
0x180052b52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052b59  cmp     byte ptr [rcx+8], 0
0x180052b5d  jz      short loc_180052B80
0x180052b5f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052b64  cmp     [rax+7CCh], ebx
0x180052b6a  jz      short loc_180052B80
0x180052b6c  mov     r9d, ebx; int
0x180052b6f  mov     r8d, 0B1h; int
0x180052b75  mov     rdx, r12; char *
0x180052b78  mov     rcx, rax; this
0x180052b7b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052b80  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180052b85  cmp     al, 1
0x180052b87  jb      loc_180052C37
0x180052b8d  mov     edx, 15h
0x180052b92  jmp     loc_180052C19
0x180052b97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052b9e  test    rcx, rcx
0x180052ba1  jnz     short loc_180052BE4
0x180052ba3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052ba9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052bb0  mov     rcx, rax
0x180052bb3  test    rax, rax
0x180052bb6  jz      short loc_180052BD6
0x180052bb8  mov     rax, [rax]
0x180052bbb  mov     edx, 7F0h
0x180052bc0  mov     rax, [rax+8]
0x180052bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
