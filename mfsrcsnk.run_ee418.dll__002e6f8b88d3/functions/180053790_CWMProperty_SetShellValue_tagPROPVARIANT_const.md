# CWMProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x180053790`
- end: `0x180053cf3`
- name: `?SetShellValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1379`
- prototype: `__int64 __fastcall(CWMProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180099d80`
- `0x1800d84c0`
- `0x1800f8910`
- `0x1800fda70`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180026f50`
- `0x180053790`
- `0x180071a44`
- `0x180073b14`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005387a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005391b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053a06`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053ac4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053b77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053c43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005387a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005391b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053a06`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053ac4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053b77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053c43`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800538ff`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180053b5b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800538ff`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180053b5b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800537f8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005385e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800537f8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005385e`
- `PROPSYS!StgSerializePropVariant` at `0x1800539ea`
- `PROPSYS!StgSerializePropVariant` at `0x1800539ea`

## pseudocode

```c
__int64 __fastcall CWMProperty::SetShellValue(CWMProperty *this, PROPVARIANT *pvarSrc)
{
  CallStackTracing *v4; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // ebx
  CallStackTracing *v9; // rcx
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  struct _GUID v52; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v53; // [rsp+40h] [rbp-48h] BYREF
  int v54; // [rsp+90h] [rbp+8h] BYREF

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
      *((_QWORD *)ThreadRelativeContext + v7) = "CWMProperty::SetShellValue";
      *((_DWORD *)ThreadRelativeContext + 2 * v7 + 2) = 89;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  v8 = PropVariantClear((PROPVARIANT *)this + 4);
  if ( v8 >= 0 )
  {
    v8 = PropVariantClear((PROPVARIANT *)this + 5);
    if ( v8 >= 0 )
    {
      v8 = PropVariantCopy((PROPVARIANT *)this + 4, pvarSrc);
      if ( v8 >= 0 )
      {
        v24 = *(_QWORD *)this;
        v54 = 0;
        if ( (*(int (__fastcall **)(CWMProperty *, void *, int *))(v24 + 56))(this, &MF_MD_EXTENDEDPROP, &v54) >= 0 )
          v25 = v54;
        else
          v25 = 0;
        if ( v25 )
        {
          *((_WORD *)this + 60) = 65;
          v8 = StgSerializePropVariant(pvarSrc, (SERIALIZEDPROPERTYVALUE **)this + 17, (ULONG *)this + 32);
          if ( v8 < 0 )
          {
            v29 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
              CallStackTracing::s_wpInstance = v30;
              if ( v30
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
              {
                v29 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v29 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v29 + 8) )
            {
              v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
              if ( *((_DWORD *)v31 + 499) != v8 )
                CallStackContext::TraceFailure(v31, "CWMProperty::SetShellValue", 108, v8);
            }
            if ( g_wppLevels )
            {
              v11 = 13;
              goto LABEL_86;
            }
          }
        }
        else
        {
          v32 = *(_QWORD *)this;
          v54 = 0;
          v8 = (*(__int64 (__fastcall **)(CWMProperty *, __int128 *, int *))(v32 + 56))(this, &MF_MD_FSDKTYPE, &v54);
          if ( v8 >= 0 )
          {
            if ( pvarSrc->vt == (_WORD)v54 )
            {
              v8 = PropVariantCopy((PROPVARIANT *)this + 5, pvarSrc);
              if ( v8 < 0 )
              {
                v42 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
                  CallStackTracing::s_wpInstance = v43;
                  if ( v43
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
                  {
                    v42 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v42 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v42 + 8) )
                {
                  v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
                  if ( *((_DWORD *)v44 + 499) != v8 )
                    CallStackContext::TraceFailure(v44, "CWMProperty::SetShellValue", 127, v8);
                }
                if ( g_wppLevels )
                {
                  v11 = 15;
                  goto LABEL_86;
                }
              }
            }
            else
            {
              v52 = (struct _GUID)MF_MD_FSDKMULTI;
              v53 = (struct _GUID)MF_MD_FSDKTYPE;
              v8 = CWMProperty::TranslateValue(
                     this,
                     (struct tagPROPVARIANT *)this + 4,
                     (struct tagPROPVARIANT *)this + 5,
                     &v53,
                     &v52);
              if ( v8 < 0 )
              {
                v48 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
                  CallStackTracing::s_wpInstance = v49;
                  if ( v49
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
                  {
                    v48 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v48 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v48 + 8) )
                {
                  v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
                  if ( *((_DWORD *)v50 + 499) != v8 )
                    CallStackContext::TraceFailure(v50, "CWMProperty::SetShellValue", 131, v8);
                }
                if ( g_wppLevels )
                {
                  v11 = 16;
                  goto LABEL_86;
                }
              }
            }
          }
          else
          {
            v36 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
              CallStackTracing::s_wpInstance = v37;
              if ( v37
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
              {
                v36 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v36 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v36 + 8) )
            {
              v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
              if ( *((_DWORD *)v38 + 499) != v8 )
                CallStackContext::TraceFailure(v38, "CWMProperty::SetShellValue", 120, v8);
            }
            if ( g_wppLevels )
            {
              v11 = 14;
              goto LABEL_86;
            }
          }
        }
      }
      else
      {
        v21 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != v8 )
            CallStackContext::TraceFailure(v23, "CWMProperty::SetShellValue", 92, v8);
        }
        if ( g_wppLevels )
        {
          v11 = 12;
          goto LABEL_86;
        }
      }
    }
    else
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != v8 )
          CallStackContext::TraceFailure(v17, "CWMProperty::SetShellValue", 90, v8);
      }
      if ( g_wppLevels )
      {
        v11 = 11;
        goto LABEL_86;
      }
    }
  }
  else
  {
    v9 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v9 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext(v9);
      if ( *((_DWORD *)v10 + 499) != v8 )
        CallStackContext::TraceFailure(v10, "CWMProperty::SetShellValue", 89, v8);
    }
    if ( g_wppLevels )
    {
      v11 = 10;
LABEL_86:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v8);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v54);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180053790  push    rbx
0x180053792  push    rbp
0x180053793  push    rsi
0x180053794  push    rdi
0x180053795  push    r13
0x180053797  push    r14
0x180053799  sub     rsp, 58h
0x18005379d  mov     rdi, rcx
0x1800537a0  mov     rbp, rdx
0x1800537a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800537aa  test    rcx, rcx
0x1800537ad  jnz     short loc_1800537BB
0x1800537af  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800537b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800537bb  cmp     byte ptr [rcx+8], 0
0x1800537bf  lea     r13, aCwmpropertySet_0; "CWMProperty::SetShellValue"
0x1800537c6  mov     esi, 59h ; 'Y'
0x1800537cb  jz      short loc_1800537F1
0x1800537cd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800537d2  mov     ecx, [rax+7C4h]
0x1800537d8  cmp     ecx, [rax+7C8h]
0x1800537de  jnb     short loc_1800537EB
0x1800537e0  add     rcx, rcx
0x1800537e3  mov     [rax+rcx*8], r13
0x1800537e7  mov     [rax+rcx*8+8], esi
0x1800537eb  inc     dword ptr [rax+7C4h]
0x1800537f1  lea     r14, [rdi+60h]
0x1800537f5  mov     rcx, r14; pvar
0x1800537f8  call    cs:__imp_PropVariantClear
0x1800537fe  mov     ebx, eax
0x180053800  test    eax, eax
0x180053802  jns     short loc_180053857
0x180053804  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005380b  test    rcx, rcx
0x18005380e  jnz     short loc_18005381C
0x180053810  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180053815  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005381c  cmp     byte ptr [rcx+8], 0
0x180053820  jz      short loc_180053840
0x180053822  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053827  cmp     [rax+7CCh], ebx
0x18005382d  jz      short loc_180053840
0x18005382f  mov     r9d, ebx; int
0x180053832  mov     r8d, esi; int
0x180053835  mov     rdx, r13; char *
0x180053838  mov     rcx, rax; this
0x18005383b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053840  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180053847  jb      loc_180053CD7
0x18005384d  mov     edx, 0Ah
0x180053852  jmp     loc_180053CB9
0x180053857  lea     rsi, [rdi+78h]
0x18005385b  mov     rcx, rsi; pvar
0x18005385e  call    cs:__imp_PropVariantClear
0x180053864  mov     ebx, eax
0x180053866  test    eax, eax
0x180053868  jns     loc_1800538F9
0x18005386e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053875  test    rcx, rcx
0x180053878  jnz     short loc_1800538BB
0x18005387a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053880  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053887  mov     rcx, rax
0x18005388a  test    rax, rax
0x18005388d  jz      short loc_1800538AD
0x18005388f  mov     rax, [rax]
0x180053892  mov     edx, 7F0h
0x180053897  mov     rax, [rax+8]
0x18005389b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538a0  test    eax, eax
0x1800538a2  jz      short loc_1800538AD
0x1800538a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800538ab  jmp     short loc_1800538BB
0x1800538ad  lea     rcx, qword_1801B07E0; this
0x1800538b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800538bb  cmp     byte ptr [rcx+8], 0
0x1800538bf  jz      short loc_1800538E2
0x1800538c1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800538c6  cmp     [rax+7CCh], ebx
0x1800538cc  jz      short loc_1800538E2
0x1800538ce  mov     r9d, ebx; int
0x1800538d1  mov     r8d, 5Ah ; 'Z'; int
0x1800538d7  mov     rdx, r13; char *
0x1800538da  mov     rcx, rax; this
0x1800538dd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800538e2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800538e9  jb      loc_180053CD7
0x1800538ef  mov     edx, 0Bh
0x1800538f4  jmp     loc_180053CB9
0x1800538f9  mov     rdx, rbp; pvarSrc
0x1800538fc  mov     rcx, r14; pvarDest
0x1800538ff  call    cs:__imp_PropVariantCopy
0x180053905  mov     ebx, eax
0x180053907  test    eax, eax
0x180053909  jns     loc_18005399A
0x18005390f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053916  test    rcx, rcx
0x180053919  jnz     short loc_18005395C
0x18005391b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053921  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053928  mov     rcx, rax
0x18005392b  test    rax, rax
0x18005392e  jz      short loc_18005394E
0x180053930  mov     rax, [rax]
0x180053933  mov     edx, 7F0h
0x180053938  mov     rax, [rax+8]
0x18005393c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053941  test    eax, eax
0x180053943  jz      short loc_18005394E
0x180053945  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005394c  jmp     short loc_18005395C
0x18005394e  lea     rcx, qword_1801B07E0; this
0x180053955  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005395c  cmp     byte ptr [rcx+8], 0
0x180053960  jz      short loc_180053983
0x180053962  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053967  cmp     [rax+7CCh], ebx
0x18005396d  jz      short loc_180053983
0x18005396f  mov     r9d, ebx; int
0x180053972  mov     r8d, 5Ch ; '\'; int
0x180053978  mov     rdx, r13; char *
0x18005397b  mov     rcx, rax; this
0x18005397e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053983  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005398a  jb      loc_180053CD7
0x180053990  mov     edx, 0Ch
0x180053995  jmp     loc_180053CB9
0x18005399a  mov     rax, [rdi]
0x18005399d  lea     r8, [rsp+88h+arg_0]
0x1800539a5  lea     rdx, MF_MD_EXTENDEDPROP
0x1800539ac  mov     [rsp+88h+arg_0], 0
0x1800539b7  mov     rcx, rdi
0x1800539ba  mov     rax, [rax+38h]
0x1800539be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800539c3  test    eax, eax
0x1800539c5  jns     short loc_1800539CB
0x1800539c7  xor     eax, eax
0x1800539c9  jmp     short loc_1800539D2
0x1800539cb  mov     eax, [rsp+88h+arg_0]
0x1800539d2  test    eax, eax
0x1800539d4  jz      loc_180053A85
0x1800539da  lea     r8, [rsi+8]; pcb
0x1800539de  mov     word ptr [rsi], 41h ; 'A'
0x1800539e3  lea     rdx, [r8+8]; ppProp
0x1800539e7  mov     rcx, rbp; ppropvar
0x1800539ea  call    cs:__imp_StgSerializePropVariant
0x1800539f0  mov     ebx, eax
0x1800539f2  test    eax, eax
0x1800539f4  jns     loc_180053CD7
0x1800539fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053a01  test    rcx, rcx
0x180053a04  jnz     short loc_180053A47
0x180053a06  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053a0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053a13  mov     rcx, rax
0x180053a16  test    rax, rax
0x180053a19  jz      short loc_180053A39
0x180053a1b  mov     rax, [rax]
0x180053a1e  mov     edx, 7F0h
0x180053a23  mov     rax, [rax+8]
0x180053a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a2c  test    eax, eax
0x180053a2e  jz      short loc_180053A39
0x180053a30  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053a37  jmp     short loc_180053A47
0x180053a39  lea     rcx, qword_1801B07E0; this
0x180053a40  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053a47  cmp     byte ptr [rcx+8], 0
0x180053a4b  jz      short loc_180053A6E
0x180053a4d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053a52  cmp     [rax+7CCh], ebx
0x180053a58  jz      short loc_180053A6E
0x180053a5a  mov     r9d, ebx; int
0x180053a5d  mov     r8d, 6Ch ; 'l'; int
0x180053a63  mov     rdx, r13; char *
0x180053a66  mov     rcx, rax; this
0x180053a69  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053a6e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180053a75  jb      loc_180053CD7
0x180053a7b  mov     edx, 0Dh
0x180053a80  jmp     loc_180053CB9
0x180053a85  mov     rax, [rdi]
0x180053a88  lea     r8, [rsp+88h+arg_0]
0x180053a90  lea     rdx, MF_MD_FSDKTYPE
0x180053a97  mov     [rsp+88h+arg_0], 0
0x180053aa2  mov     rcx, rdi
0x180053aa5  mov     rax, [rax+38h]
0x180053aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053aae  mov     ebx, eax
0x180053ab0  test    eax, eax
0x180053ab2  jns     loc_180053B43
0x180053ab8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053abf  test    rcx, rcx
0x180053ac2  jnz     short loc_180053B05
0x180053ac4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053aca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053ad1  mov     rcx, rax
0x180053ad4  test    rax, rax
0x180053ad7  jz      short loc_180053AF7
0x180053ad9  mov     rax, [rax]
0x180053adc  mov     edx, 7F0h
0x180053ae1  mov     rax, [rax+8]
0x180053ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053aea  test    eax, eax
0x180053aec  jz      short loc_180053AF7
0x180053aee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053af5  jmp     short loc_180053B05
0x180053af7  lea     rcx, qword_1801B07E0; this
0x180053afe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053b05  cmp     byte ptr [rcx+8], 0
0x180053b09  jz      short loc_180053B2C
0x180053b0b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053b10  cmp     [rax+7CCh], ebx
0x180053b16  jz      short loc_180053B2C
0x180053b18  mov     r9d, ebx; int
0x180053b1b  mov     r8d, 78h ; 'x'; int
0x180053b21  mov     rdx, r13; char *
0x180053b24  mov     rcx, rax; this
0x180053b27  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053b2c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180053b33  jb      loc_180053CD7
0x180053b39  mov     edx, 0Eh
0x180053b3e  jmp     loc_180053CB9
0x180053b43  movzx   eax, word ptr [rsp+88h+arg_0]
0x180053b4b  cmp     [rbp+0], ax
0x180053b4f  jnz     loc_180053BF6
0x180053b55  mov     rdx, rbp; pvarSrc
0x180053b58  mov     rcx, rsi; pvarDest
0x180053b5b  call    cs:__imp_PropVariantCopy
0x180053b61  mov     ebx, eax
0x180053b63  test    eax, eax
0x180053b65  jns     loc_180053CD7
0x180053b6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053b72  test    rcx, rcx
0x180053b75  jnz     short loc_180053BB8
0x180053b77  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053b7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053b84  mov     rcx, rax
0x180053b87  test    rax, rax
0x180053b8a  jz      short loc_180053BAA
0x180053b8c  mov     rax, [rax]
0x180053b8f  mov     edx, 7F0h
0x180053b94  mov     rax, [rax+8]
0x180053b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b9d  test    eax, eax
0x180053b9f  jz      short loc_180053BAA
0x180053ba1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053ba8  jmp     short loc_180053BB8
0x180053baa  lea     rcx, qword_1801B07E0; this
0x180053bb1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053bb8  cmp     byte ptr [rcx+8], 0
0x180053bbc  jz      short loc_180053BDF
0x180053bbe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053bc3  cmp     [rax+7CCh], ebx
0x180053bc9  jz      short loc_180053BDF
0x180053bcb  mov     r9d, ebx; int
0x180053bce  mov     r8d, 7Fh; int
0x180053bd4  mov     rdx, r13; char *
0x180053bd7  mov     rcx, rax; this
0x180053bda  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053bdf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180053be6  jb      loc_180053CD7
0x180053bec  mov     edx, 0Fh
0x180053bf1  jmp     loc_180053CB9
0x180053bf6  movups  xmm0, cs:MF_MD_FSDKMULTI
0x180053bfd  lea     rax, [rsp+88h+var_58]
0x180053c02  mov     r8, rsi; struct tagPROPVARIANT *
0x180053c05  movups  xmm1, cs:MF_MD_FSDKTYPE
0x180053c0c  lea     r9, [rsp+88h+var_48]; struct _GUID
0x180053c11  mov     [rsp+88h+var_68], rax; struct _GUID
0x180053c16  mov     rdx, r14; struct tagPROPVARIANT *
0x180053c19  mov     rcx, rdi; this
0x180053c1c  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x180053c22  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x180053c28  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x180053c2d  mov     ebx, eax
0x180053c2f  test    eax, eax
0x180053c31  jns     loc_180053CD7
0x180053c37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053c3e  test    rcx, rcx
0x180053c41  jnz     short loc_180053C84
0x180053c43  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053c49  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053c50  mov     rcx, rax
0x180053c53  test    rax, rax
0x180053c56  jz      short loc_180053C76
0x180053c58  mov     rax, [rax]
0x180053c5b  mov     edx, 7F0h
0x180053c60  mov     rax, [rax+8]
0x180053c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c69  test    eax, eax
0x180053c6b  jz      short loc_180053C76
0x180053c6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053c74  jmp     short loc_180053C84
0x180053c76  lea     rcx, qword_1801B07E0; this
0x180053c7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053c84  cmp     byte ptr [rcx+8], 0
0x180053c88  jz      short loc_180053CAB
0x180053c8a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053c8f  cmp     [rax+7CCh], ebx
  ... truncated ...
```
