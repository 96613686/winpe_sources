# CWMProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x18006e500`
- end: `0x18006ea63`
- name: `?SetNativeValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1379`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006ddb0`
- `0x18006ea70`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18006e500`
- `0x18007064c`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006e677`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006e881`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006e677`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006e881`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006e537`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006e5d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006e537`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006e5d6`
- `PROPSYS!StgDeserializePropVariant` at `0x18006e853`
- `PROPSYS!StgDeserializePropVariant` at `0x18006e853`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e553`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e5f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e693`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e772`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e89d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e928`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e9b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e553`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e5f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e693`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e772`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e89d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e928`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e9b3`

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
                      v36 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v33 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v39 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v24 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v21 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v15 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18006e500  mov     rax, rsp
0x18006e503  push    rbx
0x18006e504  push    rbp
0x18006e505  push    rsi
0x18006e506  push    rdi
0x18006e507  push    r12
0x18006e509  push    r14
0x18006e50b  sub     rsp, 58h
0x18006e50f  mov     rdi, rdx
0x18006e512  lea     r12, aCwmpropertySet; "CWMProperty::SetNativeValue"
0x18006e519  mov     rsi, rcx
0x18006e51c  mov     ebp, 91h
0x18006e521  mov     r8d, ebp; int
0x18006e524  lea     rcx, [rax+8]; this
0x18006e528  mov     rdx, r12; char *
0x18006e52b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006e530  lea     r14, [rsi+60h]
0x18006e534  mov     rcx, r14; pvar
0x18006e537  call    cs:__imp_PropVariantClear
0x18006e53d  mov     ebx, eax
0x18006e53f  test    eax, eax
0x18006e541  jns     loc_18006E5CF
0x18006e547  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e54e  test    rcx, rcx
0x18006e551  jnz     short loc_18006E594
0x18006e553  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e559  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e560  mov     rcx, rax
0x18006e563  test    rax, rax
0x18006e566  jz      short loc_18006E586
0x18006e568  mov     rax, [rax]
0x18006e56b  mov     edx, 7F0h
0x18006e570  mov     rax, [rax+8]
0x18006e574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e579  test    eax, eax
0x18006e57b  jz      short loc_18006E586
0x18006e57d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e584  jmp     short loc_18006E594
0x18006e586  lea     rcx, qword_1800D6F70; this
0x18006e58d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e594  cmp     byte ptr [rcx+8], 0
0x18006e598  jz      short loc_18006E5B8
0x18006e59a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e59f  cmp     [rax+7CCh], ebx
0x18006e5a5  jz      short loc_18006E5B8
0x18006e5a7  mov     r9d, ebx; int
0x18006e5aa  mov     r8d, ebp; int
0x18006e5ad  mov     rdx, r12; char *
0x18006e5b0  mov     rcx, rax; this
0x18006e5b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e5b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e5bf  jb      loc_18006EA47
0x18006e5c5  mov     edx, 11h
0x18006e5ca  jmp     loc_18006EA29
0x18006e5cf  lea     rbp, [rsi+78h]
0x18006e5d3  mov     rcx, rbp; pvar
0x18006e5d6  call    cs:__imp_PropVariantClear
0x18006e5dc  mov     ebx, eax
0x18006e5de  test    eax, eax
0x18006e5e0  jns     loc_18006E671
0x18006e5e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e5ed  test    rcx, rcx
0x18006e5f0  jnz     short loc_18006E633
0x18006e5f2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e5f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e5ff  mov     rcx, rax
0x18006e602  test    rax, rax
0x18006e605  jz      short loc_18006E625
0x18006e607  mov     rax, [rax]
0x18006e60a  mov     edx, 7F0h
0x18006e60f  mov     rax, [rax+8]
0x18006e613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e618  test    eax, eax
0x18006e61a  jz      short loc_18006E625
0x18006e61c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e623  jmp     short loc_18006E633
0x18006e625  lea     rcx, qword_1800D6F70; this
0x18006e62c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e633  cmp     byte ptr [rcx+8], 0
0x18006e637  jz      short loc_18006E65A
0x18006e639  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e63e  cmp     [rax+7CCh], ebx
0x18006e644  jz      short loc_18006E65A
0x18006e646  mov     r9d, ebx; int
0x18006e649  mov     r8d, 92h; int
0x18006e64f  mov     rdx, r12; char *
0x18006e652  mov     rcx, rax; this
0x18006e655  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e65a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e661  jb      loc_18006EA47
0x18006e667  mov     edx, 12h
0x18006e66c  jmp     loc_18006EA29
0x18006e671  mov     rdx, rdi; pvarSrc
0x18006e674  mov     rcx, rbp; pvarDest
0x18006e677  call    cs:__imp_PropVariantCopy
0x18006e67d  mov     ebx, eax
0x18006e67f  test    eax, eax
0x18006e681  jns     loc_18006E712
0x18006e687  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e68e  test    rcx, rcx
0x18006e691  jnz     short loc_18006E6D4
0x18006e693  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e699  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e6a0  mov     rcx, rax
0x18006e6a3  test    rax, rax
0x18006e6a6  jz      short loc_18006E6C6
0x18006e6a8  mov     rax, [rax]
0x18006e6ab  mov     edx, 7F0h
0x18006e6b0  mov     rax, [rax+8]
0x18006e6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e6b9  test    eax, eax
0x18006e6bb  jz      short loc_18006E6C6
0x18006e6bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e6c4  jmp     short loc_18006E6D4
0x18006e6c6  lea     rcx, qword_1800D6F70; this
0x18006e6cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e6d4  cmp     byte ptr [rcx+8], 0
0x18006e6d8  jz      short loc_18006E6FB
0x18006e6da  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e6df  cmp     [rax+7CCh], ebx
0x18006e6e5  jz      short loc_18006E6FB
0x18006e6e7  mov     r9d, ebx; int
0x18006e6ea  mov     r8d, 94h; int
0x18006e6f0  mov     rdx, r12; char *
0x18006e6f3  mov     rcx, rax; this
0x18006e6f6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e6fb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e702  jb      loc_18006EA47
0x18006e708  mov     edx, 13h
0x18006e70d  jmp     loc_18006EA29
0x18006e712  movzx   ecx, word ptr [rdi]
0x18006e715  btr     ecx, 0Ch
0x18006e719  sub     ecx, 8
0x18006e71c  jz      loc_18006E7F1
0x18006e722  sub     ecx, 3
0x18006e725  jz      loc_18006E7F1
0x18006e72b  sub     ecx, 7
0x18006e72e  jz      loc_18006E7F1
0x18006e734  sub     ecx, 1
0x18006e737  jz      loc_18006E7F1
0x18006e73d  sub     ecx, 2
0x18006e740  jz      loc_18006E7F1
0x18006e746  sub     ecx, 0Ah
0x18006e749  jz      loc_18006E7F1
0x18006e74f  sub     ecx, 22h ; '"'
0x18006e752  jz      loc_18006E7F1
0x18006e758  cmp     ecx, 7
0x18006e75b  jz      loc_18006E7F1
0x18006e761  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e768  mov     ebx, 8000FFFFh
0x18006e76d  test    rcx, rcx
0x18006e770  jnz     short loc_18006E7B3
0x18006e772  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e778  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e77f  mov     rcx, rax
0x18006e782  test    rax, rax
0x18006e785  jz      short loc_18006E7A5
0x18006e787  mov     rax, [rax]
0x18006e78a  mov     edx, 7F0h
0x18006e78f  mov     rax, [rax+8]
0x18006e793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e798  test    eax, eax
0x18006e79a  jz      short loc_18006E7A5
0x18006e79c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e7a3  jmp     short loc_18006E7B3
0x18006e7a5  lea     rcx, qword_1800D6F70; this
0x18006e7ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e7b3  cmp     byte ptr [rcx+8], 0
0x18006e7b7  jz      short loc_18006E7DA
0x18006e7b9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e7be  cmp     [rax+7CCh], ebx
0x18006e7c4  jz      short loc_18006E7DA
0x18006e7c6  mov     r9d, ebx; int
0x18006e7c9  mov     r8d, 0BDh; int
0x18006e7cf  mov     rdx, r12; char *
0x18006e7d2  mov     rcx, rax; this
0x18006e7d5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e7da  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e7e1  jb      loc_18006EA47
0x18006e7e7  mov     edx, 17h
0x18006e7ec  jmp     loc_18006EA29
0x18006e7f1  movups  xmm0, cs:MF_MD_SHELLMULTI
0x18006e7f8  lea     rax, [rsp+88h+var_58]
0x18006e7fd  mov     r8, r14; struct tagPROPVARIANT *
0x18006e800  movups  xmm1, cs:MF_MD_SHELLTYPE
0x18006e807  lea     r9, [rsp+88h+var_48]; struct _GUID
0x18006e80c  mov     [rsp+88h+var_68], rax; struct _GUID
0x18006e811  mov     rdx, rbp; struct tagPROPVARIANT *
0x18006e814  mov     rcx, rsi; this
0x18006e817  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x18006e81d  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x18006e823  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x18006e828  mov     ebx, eax
0x18006e82a  test    eax, eax
0x18006e82c  jns     loc_18006EA47
0x18006e832  cmp     word ptr [rdi], 41h ; 'A'
0x18006e836  jnz     loc_18006E9A7
0x18006e83c  mov     edx, [rdi+8]; cbMax
0x18006e83f  test    edx, edx
0x18006e841  jz      loc_18006E9A7
0x18006e847  cmp     edx, 8
0x18006e84a  jb      short loc_18006E863
0x18006e84c  mov     rcx, [rdi+10h]; pprop
0x18006e850  mov     r8, r14; ppropvar
0x18006e853  call    cs:__imp_StgDeserializePropVariant
0x18006e859  mov     ebx, eax
0x18006e85b  test    eax, eax
0x18006e85d  jns     loc_18006EA47
0x18006e863  cmp     ebx, 8007000Eh
0x18006e869  jz      loc_18006E91C
0x18006e86f  cmp     ebx, 80030005h
0x18006e875  jz      loc_18006E91C
0x18006e87b  mov     rdx, rdi; pvarSrc
0x18006e87e  mov     rcx, r14; pvarDest
0x18006e881  call    cs:__imp_PropVariantCopy
0x18006e887  mov     ebx, eax
0x18006e889  test    eax, eax
0x18006e88b  jns     loc_18006EA47
0x18006e891  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e898  test    rcx, rcx
0x18006e89b  jnz     short loc_18006E8DE
0x18006e89d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e8a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e8aa  mov     rcx, rax
0x18006e8ad  test    rax, rax
0x18006e8b0  jz      short loc_18006E8D0
0x18006e8b2  mov     rax, [rax]
0x18006e8b5  mov     edx, 7F0h
0x18006e8ba  mov     rax, [rax+8]
0x18006e8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e8c3  test    eax, eax
0x18006e8c5  jz      short loc_18006E8D0
0x18006e8c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e8ce  jmp     short loc_18006E8DE
0x18006e8d0  lea     rcx, qword_1800D6F70; this
0x18006e8d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e8de  cmp     byte ptr [rcx+8], 0
0x18006e8e2  jz      short loc_18006E905
0x18006e8e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e8e9  cmp     [rax+7CCh], ebx
0x18006e8ef  jz      short loc_18006E905
0x18006e8f1  mov     r9d, ebx; int
0x18006e8f4  mov     r8d, 0AFh; int
0x18006e8fa  mov     rdx, r12; char *
0x18006e8fd  mov     rcx, rax; this
0x18006e900  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e905  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e90c  jb      loc_18006EA47
0x18006e912  mov     edx, 14h
0x18006e917  jmp     loc_18006EA29
0x18006e91c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e923  test    rcx, rcx
0x18006e926  jnz     short loc_18006E969
0x18006e928  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e92e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e935  mov     rcx, rax
0x18006e938  test    rax, rax
0x18006e93b  jz      short loc_18006E95B
0x18006e93d  mov     rax, [rax]
0x18006e940  mov     edx, 7F0h
0x18006e945  mov     rax, [rax+8]
0x18006e949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e94e  test    eax, eax
0x18006e950  jz      short loc_18006E95B
0x18006e952  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e959  jmp     short loc_18006E969
0x18006e95b  lea     rcx, qword_1800D6F70; this
0x18006e962  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e969  cmp     byte ptr [rcx+8], 0
0x18006e96d  jz      short loc_18006E990
0x18006e96f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e974  cmp     [rax+7CCh], ebx
0x18006e97a  jz      short loc_18006E990
0x18006e97c  mov     r9d, ebx; int
0x18006e97f  mov     r8d, 0B1h; int
0x18006e985  mov     rdx, r12; char *
0x18006e988  mov     rcx, rax; this
0x18006e98b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e990  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e997  jb      loc_18006EA47
0x18006e99d  mov     edx, 15h
0x18006e9a2  jmp     loc_18006EA29
0x18006e9a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e9ae  test    rcx, rcx
0x18006e9b1  jnz     short loc_18006E9F4
0x18006e9b3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e9b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e9c0  mov     rcx, rax
0x18006e9c3  test    rax, rax
0x18006e9c6  jz      short loc_18006E9E6
0x18006e9c8  mov     rax, [rax]
0x18006e9cb  mov     edx, 7F0h
0x18006e9d0  mov     rax, [rax+8]
0x18006e9d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e9d9  test    eax, eax
0x18006e9db  jz      short loc_18006E9E6
0x18006e9dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e9e4  jmp     short loc_18006E9F4
0x18006e9e6  lea     rcx, qword_1800D6F70; this
0x18006e9ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
