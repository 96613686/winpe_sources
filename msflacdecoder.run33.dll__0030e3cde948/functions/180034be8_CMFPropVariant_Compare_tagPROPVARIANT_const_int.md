# CMFPropVariant::Compare(tagPROPVARIANT const *,int *)

- ea: `0x180034be8`
- end: `0x18003513f`
- name: `?Compare@CMFPropVariant@@QEBAJPEBUtagPROPVARIANT@@PEAH@Z`
- size: `1367`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this, const struct tagPROPVARIANT *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180039270`

## callees

- `0x180002834`
- `0x180002840`
- `0x180016b18`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180034be8`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034c37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034ce3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034d7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034fee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035090`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034c37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034ce3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034d7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034fee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035090`

## string_xrefs

- `0x180034bfb`: `CMFPropVariant::Compare`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Compare(const void **this, const struct tagPROPVARIANT *a2, int *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // ebx
  __int64 *v9; // rdi
  unsigned int v10; // ebp
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 *v15; // rdi
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 *v18; // rdi
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  double dblVal; // xmm1_8
  double v27; // xmm0_8
  bool v28; // zf
  float v29; // xmm0_4
  float fltVal; // xmm1_4
  LONG lVal; // eax
  bool v32; // zf
  bool v33; // sf
  bool v34; // of
  bool v35; // cc
  SHORT iVal; // ax
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  bool v41; // cf
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  LARGE_INTEGER hVal; // rax
  unsigned int ulVal; // eax
  bool v48; // cf
  bool v49; // cc
  unsigned __int16 uiVal; // ax
  unsigned __int8 bVal; // al
  int v52; // ebx
  CHAR cVal; // al
  LARGE_INTEGER v54; // rax
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  int v59; // eax
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 v63; // rdx
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  _BYTE v68[56]; // [rsp+30h] [rbp-38h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v68, "CMFPropVariant::Compare", 1414);
  v8 = 0;
  if ( this == (const void **)a2 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    v10 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v7, v6);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::Compare", 1423, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 86;
LABEL_112:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, this, v10);
      goto LABEL_113;
    }
    goto LABEL_113;
  }
  *a3 = 0;
  v14 = *(unsigned __int16 *)this;
  if ( (v14 & 0x1000) == 0 )
  {
    if ( a2->vt != (_WORD)v14 )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      v10 = -1072875801;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v14, 4096);
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
        if ( *((_DWORD *)v20 + 499) != -1072875801 )
          CallStackContext::TraceFailure(v20, "CMFPropVariant::Compare", 1444, -1072875801);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v13 = 88;
        goto LABEL_112;
      }
      goto LABEL_113;
    }
    v21 = v14 & 0xFFF;
    if ( v21 > 0x48 )
      goto LABEL_92;
    v10 = 0;
    if ( v21 == 72 )
    {
      v41 = memcmp_0(a2->puuid, this[1], 0x10u) != 0;
      goto LABEL_91;
    }
    if ( v21 <= 0xD )
    {
      if ( v21 == 13 )
      {
LABEL_59:
        v41 = this[1] != a2->puuid;
LABEL_91:
        v59 = -v41;
        goto LABEL_89;
      }
      if ( v21 <= 6 )
      {
        if ( v21 != 6 )
        {
          if ( !v21 )
            goto LABEL_113;
          v22 = v21 - 1;
          if ( !v22 )
            goto LABEL_113;
          v23 = v22 - 1;
          if ( v23 )
          {
            v24 = v23 - 1;
            if ( v24 )
            {
              v25 = v24 - 1;
              if ( !v25 )
              {
                v29 = *((float *)this + 2);
                fltVal = a2->fltVal;
                if ( v29 <= fltVal )
                {
                  v28 = fltVal == v29;
                  goto LABEL_50;
                }
                goto LABEL_76;
              }
              if ( v25 == 1 )
                goto LABEL_46;
LABEL_92:
              v60 = (__int64 *)CallStackTracing::s_wpInstance;
              v10 = -1072875800;
              if ( !CallStackTracing::s_wpInstance )
              {
                v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 4096);
                CallStackTracing::s_wpInstance = v61;
                if ( v61
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
                {
                  v60 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v60 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v60 + 8) )
              {
                v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
                if ( *((_DWORD *)v62 + 499) != -1072875800 )
                  CallStackContext::TraceFailure(v62, "CMFPropVariant::Compare", 1483, -1072875800);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                WPP_SF_qd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  89,
                  &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                  this,
                  -1072875800);
                v64 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              if ( !v64 )
              {
                v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63);
                CallStackTracing::s_wpInstance = v65;
                if ( v65
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
                {
                  v64 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v64 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v64 + 8) )
              {
                v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
                if ( *((_DWORD *)v66 + 499) != -1072875800 )
                  CallStackContext::TraceFailure(v66, "CMFPropVariant::Compare", 1486, -1072875800);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v13 = 90;
                goto LABEL_112;
              }
              goto LABEL_113;
            }
            goto LABEL_51;
          }
          iVal = a2->iVal;
          v34 = __OFSUB__(iVal, *((_WORD *)this + 4));
          v32 = iVal == *((_WORD *)this + 4);
          v33 = (__int16)(iVal - *((_WORD *)this + 4)) < 0;
          v35 = iVal < *((_WORD *)this + 4);
LABEL_75:
          if ( !v35 )
          {
            LOBYTE(v8) = v33 ^ v34 | v32;
            goto LABEL_78;
          }
          goto LABEL_76;
        }
LABEL_67:
        hVal = a2->hVal;
        v34 = __OFSUB__(hVal.QuadPart, this[1]);
        v32 = hVal.QuadPart == (_QWORD)this[1];
        v33 = hVal.QuadPart - (__int64)this[1] < 0;
        v35 = hVal.QuadPart < (__int64)this[1];
        goto LABEL_75;
      }
      v37 = v21 - 7;
      if ( !v37 )
      {
LABEL_46:
        dblVal = a2->dblVal;
        v27 = *((double *)this + 1);
        if ( v27 <= dblVal )
        {
          v28 = dblVal == v27;
LABEL_50:
          LOBYTE(v8) = v28;
LABEL_78:
          v52 = v8 - 1;
          goto LABEL_79;
        }
        goto LABEL_76;
      }
      v38 = v37 - 1;
      if ( v38 )
      {
        v39 = v38 - 1;
        if ( v39 )
        {
          v40 = v39 - 1;
          if ( v40 )
          {
            if ( v40 != 1 )
              goto LABEL_92;
            v41 = *((_WORD *)this + 4) != a2->iVal;
            goto LABEL_91;
          }
LABEL_51:
          lVal = a2->lVal;
          v34 = __OFSUB__(lVal, *((_DWORD *)this + 2));
          v32 = lVal == *((_DWORD *)this + 2);
          v33 = lVal - *((_DWORD *)this + 2) < 0;
          v35 = lVal < *((_DWORD *)this + 2);
          goto LABEL_75;
        }
        goto LABEL_59;
      }
      goto LABEL_87;
    }
    if ( v21 <= 0x15 )
    {
      if ( v21 == 21 )
      {
        v54 = a2->hVal;
        v48 = (unsigned __int64)this[1] < v54.QuadPart;
        v49 = (unsigned __int64)this[1] <= v54.QuadPart;
      }
      else
      {
        v42 = v21 - 16;
        if ( !v42 )
        {
          cVal = a2->cVal;
          v34 = __OFSUB__(cVal, *((_BYTE *)this + 8));
          v32 = cVal == *((_BYTE *)this + 8);
          v33 = (char)(cVal - *((_BYTE *)this + 8)) < 0;
          v35 = cVal < *((_BYTE *)this + 8);
          goto LABEL_75;
        }
        v43 = v42 - 1;
        if ( !v43 )
        {
          bVal = a2->bVal;
          v48 = *((_BYTE *)this + 8) < bVal;
          if ( *((_BYTE *)this + 8) > bVal )
          {
LABEL_76:
            v52 = -1;
            goto LABEL_79;
          }
LABEL_73:
          v52 = -v48;
LABEL_79:
          *a3 = v52;
          goto LABEL_113;
        }
        v44 = v43 - 1;
        if ( v44 )
        {
          v45 = v44 - 1;
          if ( v45 )
          {
            if ( v45 != 1 )
              goto LABEL_92;
            goto LABEL_67;
          }
LABEL_68:
          ulVal = a2->ulVal;
          v48 = *((_DWORD *)this + 2) < ulVal;
          v49 = *((_DWORD *)this + 2) <= ulVal;
          goto LABEL_70;
        }
        uiVal = a2->uiVal;
        v48 = *((_WORD *)this + 4) < uiVal;
        v49 = *((_WORD *)this + 4) <= uiVal;
      }
LABEL_70:
      if ( !v49 )
        goto LABEL_76;
      goto LABEL_73;
    }
    v55 = v21 - 22;
    if ( !v55 )
      goto LABEL_51;
    v56 = v55 - 1;
    if ( v56 )
    {
      v57 = v56 - 7;
      if ( !v57 )
      {
        v59 = ((__int64 (__fastcall *)(_QWORD, _QWORD))o__stricmp_0)((LARGE_INTEGER)a2->hVal.QuadPart, this[1]);
        goto LABEL_89;
      }
      v58 = v57 - 1;
      if ( v58 )
      {
        if ( v58 != 33 )
          goto LABEL_92;
        v59 = memcmp_0(&a2->decVal.8, this + 1, 8u);
LABEL_89:
        *a3 = v59;
        goto LABEL_113;
      }
LABEL_87:
      v59 = wcsicmp(a2->bstrVal, (const wchar_t *)this[1]);
      goto LABEL_89;
    }
    goto LABEL_68;
  }
  v15 = (__int64 *)CallStackTracing::s_wpInstance;
  v10 = -1072875797;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v14, 4096);
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
    if ( *((_DWORD *)v17 + 499) != -1072875797 )
      CallStackContext::TraceFailure(v17, "CMFPropVariant::Compare", 1436, -1072875797);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v13 = 87;
    goto LABEL_112;
  }
LABEL_113:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v68);
  return v10;
}

```

## disassembly

```asm
0x180034be8  mov     [rsp+arg_18], rbx
0x180034bed  push    rbp
0x180034bee  push    rsi
0x180034bef  push    rdi
0x180034bf0  push    r14
0x180034bf2  push    r15
0x180034bf4  sub     rsp, 40h
0x180034bf8  mov     rsi, r8
0x180034bfb  lea     r15, aCmfpropvariant_2; "CMFPropVariant::Compare"
0x180034c02  mov     rdi, rdx
0x180034c05  mov     r14, rcx
0x180034c08  mov     rdx, r15; char *
0x180034c0b  lea     rcx, [rsp+68h+var_38]; this
0x180034c10  mov     r8d, 586h; int
0x180034c16  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180034c1b  xor     ebx, ebx
0x180034c1d  cmp     r14, rdi
0x180034c20  jnz     loc_180034CB8
0x180034c26  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034c2d  mov     ebp, 80004003h
0x180034c32  test    rdi, rdi
0x180034c35  jnz     short loc_180034C78
0x180034c37  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180034c3d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180034c44  mov     rcx, rax
0x180034c47  test    rax, rax
0x180034c4a  jz      short loc_180034C6A
0x180034c4c  mov     rax, [rax]
0x180034c4f  mov     edx, 7F0h
0x180034c54  mov     rax, [rax+8]
0x180034c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c5d  test    eax, eax
0x180034c5f  jz      short loc_180034C6A
0x180034c61  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034c68  jmp     short loc_180034C78
0x180034c6a  lea     rdi, qword_18006EB20
0x180034c71  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180034c78  cmp     [rdi+8], bl
0x180034c7b  jz      short loc_180034CA1
0x180034c7d  mov     rcx, rdi; this
0x180034c80  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180034c85  cmp     [rax+7CCh], ebp
0x180034c8b  jz      short loc_180034CA1
0x180034c8d  mov     r9d, ebp; int
0x180034c90  mov     r8d, 58Fh; int
0x180034c96  mov     rdx, r15; char *
0x180034c99  mov     rcx, rax; this
0x180034c9c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180034ca1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180034ca6  cmp     al, 1
0x180034ca8  jb      loc_18003511F
0x180034cae  mov     edx, 56h ; 'V'
0x180034cb3  jmp     loc_180035101
0x180034cb8  mov     [rsi], ebx
0x180034cba  mov     edx, 1000h
0x180034cbf  movzx   ecx, word ptr [r14]
0x180034cc3  movzx   eax, cx
0x180034cc6  and     ax, dx
0x180034cc9  cmp     bx, ax
0x180034ccc  jz      loc_180034D64
0x180034cd2  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034cd9  mov     ebp, 0C00D36EBh
0x180034cde  test    rdi, rdi
0x180034ce1  jnz     short loc_180034D24
0x180034ce3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180034ce9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180034cf0  mov     rcx, rax
0x180034cf3  test    rax, rax
0x180034cf6  jz      short loc_180034D16
0x180034cf8  mov     rax, [rax]
0x180034cfb  mov     edx, 7F0h
0x180034d00  mov     rax, [rax+8]
0x180034d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d09  test    eax, eax
0x180034d0b  jz      short loc_180034D16
0x180034d0d  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034d14  jmp     short loc_180034D24
0x180034d16  lea     rdi, qword_18006EB20
0x180034d1d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180034d24  cmp     [rdi+8], bl
0x180034d27  jz      short loc_180034D4D
0x180034d29  mov     rcx, rdi; this
0x180034d2c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180034d31  cmp     [rax+7CCh], ebp
0x180034d37  jz      short loc_180034D4D
0x180034d39  mov     r9d, ebp; int
0x180034d3c  mov     r8d, 59Ch; int
0x180034d42  mov     rdx, r15; char *
0x180034d45  mov     rcx, rax; this
0x180034d48  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180034d4d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180034d52  cmp     al, 1
0x180034d54  jb      loc_18003511F
0x180034d5a  mov     edx, 57h ; 'W'
0x180034d5f  jmp     loc_180035101
0x180034d64  cmp     [rdi], cx
0x180034d67  jz      loc_180034DFF
0x180034d6d  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034d74  mov     ebp, 0C00D36E7h
0x180034d79  test    rdi, rdi
0x180034d7c  jnz     short loc_180034DBF
0x180034d7e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180034d84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180034d8b  mov     rcx, rax
0x180034d8e  test    rax, rax
0x180034d91  jz      short loc_180034DB1
0x180034d93  mov     rax, [rax]
0x180034d96  mov     edx, 7F0h
0x180034d9b  mov     rax, [rax+8]
0x180034d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034da4  test    eax, eax
0x180034da6  jz      short loc_180034DB1
0x180034da8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034daf  jmp     short loc_180034DBF
0x180034db1  lea     rdi, qword_18006EB20
0x180034db8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180034dbf  cmp     [rdi+8], bl
0x180034dc2  jz      short loc_180034DE8
0x180034dc4  mov     rcx, rdi; this
0x180034dc7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180034dcc  cmp     [rax+7CCh], ebp
0x180034dd2  jz      short loc_180034DE8
0x180034dd4  mov     r9d, ebp; int
0x180034dd7  mov     r8d, 5A4h; int
0x180034ddd  mov     rdx, r15; char *
0x180034de0  mov     rcx, rax; this
0x180034de3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180034de8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180034ded  cmp     al, 1
0x180034def  jb      loc_18003511F
0x180034df5  mov     edx, 58h ; 'X'
0x180034dfa  jmp     loc_180035101
0x180034dff  and     ecx, 0FFFh
0x180034e05  cmp     ecx, 48h ; 'H'
0x180034e08  ja      loc_180034FD6
0x180034e0e  mov     ebp, ebx
0x180034e10  jz      loc_180034FBD
0x180034e16  cmp     ecx, 0Dh
0x180034e19  ja      loc_180034EF3
0x180034e1f  jz      loc_180034EE3
0x180034e25  cmp     ecx, 6
0x180034e28  ja      loc_180034EB1
0x180034e2e  jz      loc_180034F17
0x180034e34  test    ecx, ecx
0x180034e36  jz      loc_18003511F
0x180034e3c  sub     ecx, 1
0x180034e3f  jz      loc_18003511F
0x180034e45  sub     ecx, 1
0x180034e48  jz      short loc_180034EA3
0x180034e4a  sub     ecx, 1
0x180034e4d  jz      short loc_180034E97
0x180034e4f  sub     ecx, 1
0x180034e52  jz      short loc_180034E78
0x180034e54  cmp     ecx, 1
0x180034e57  jnz     loc_180034FD6
0x180034e5d  movsd   xmm1, qword ptr [rdi+8]
0x180034e62  movsd   xmm0, qword ptr [r14+8]
0x180034e68  comisd  xmm0, xmm1
0x180034e6c  ja      loc_180034F4D
0x180034e72  comisd  xmm1, xmm0
0x180034e76  jmp     short loc_180034E8F
0x180034e78  movss   xmm0, dword ptr [r14+8]
0x180034e7e  movss   xmm1, dword ptr [rdi+8]
0x180034e83  comiss  xmm0, xmm1
0x180034e86  ja      loc_180034F4D
0x180034e8c  comiss  xmm1, xmm0
0x180034e8f  setbe   bl
0x180034e92  jmp     loc_180034F55
0x180034e97  mov     eax, [rdi+8]
0x180034e9a  cmp     eax, [r14+8]
0x180034e9e  jmp     loc_180034F4B
0x180034ea3  movzx   eax, word ptr [rdi+8]
0x180034ea7  cmp     ax, [r14+8]
0x180034eac  jmp     loc_180034F4B
0x180034eb1  sub     ecx, 7
0x180034eb4  jz      short loc_180034E5D
0x180034eb6  sub     ecx, 1
0x180034eb9  jz      loc_180034F9A
0x180034ebf  sub     ecx, 1
0x180034ec2  jz      short loc_180034EE3
0x180034ec4  sub     ecx, 1
0x180034ec7  jz      short loc_180034E97
0x180034ec9  cmp     ecx, 1
0x180034ecc  jnz     loc_180034FD6
0x180034ed2  movzx   eax, word ptr [rdi+8]
0x180034ed6  sub     ax, [r14+8]
0x180034edb  neg     ax
0x180034ede  jmp     loc_180034FD2
0x180034ee3  mov     rax, [rdi+8]
0x180034ee7  sub     rax, [r14+8]
0x180034eeb  neg     rax
0x180034eee  jmp     loc_180034FD2
0x180034ef3  cmp     ecx, 15h
0x180034ef6  ja      short loc_180034F68
0x180034ef8  jz      short loc_180034F5E
0x180034efa  sub     ecx, 10h
0x180034efd  jz      short loc_180034F44
0x180034eff  sub     ecx, 1
0x180034f02  jz      short loc_180034F37
0x180034f04  sub     ecx, 1
0x180034f07  jz      short loc_180034F2A
0x180034f09  sub     ecx, 1
0x180034f0c  jz      short loc_180034F21
0x180034f0e  cmp     ecx, 1
0x180034f11  jnz     loc_180034FD6
0x180034f17  mov     rax, [rdi+8]
0x180034f1b  cmp     rax, [r14+8]
0x180034f1f  jmp     short loc_180034F4B
0x180034f21  mov     eax, [rdi+8]
0x180034f24  cmp     [r14+8], eax
0x180034f28  jmp     short loc_180034F33
0x180034f2a  movzx   eax, word ptr [rdi+8]
0x180034f2e  cmp     [r14+8], ax
0x180034f33  jbe     short loc_180034F40
0x180034f35  jmp     short loc_180034F4D
0x180034f37  mov     al, [rdi+8]
0x180034f3a  cmp     [r14+8], al
0x180034f3e  ja      short loc_180034F4D
0x180034f40  sbb     ebx, ebx
0x180034f42  jmp     short loc_180034F57
0x180034f44  mov     al, [rdi+8]
0x180034f47  cmp     al, [r14+8]
0x180034f4b  jge     short loc_180034F52
0x180034f4d  or      ebx, 0FFFFFFFFh
0x180034f50  jmp     short loc_180034F57
0x180034f52  setle   bl
0x180034f55  dec     ebx
0x180034f57  mov     [rsi], ebx
0x180034f59  jmp     loc_18003511F
0x180034f5e  mov     rax, [rdi+8]
0x180034f62  cmp     [r14+8], rax
0x180034f66  jmp     short loc_180034F33
0x180034f68  sub     ecx, 16h
0x180034f6b  jz      loc_180034E97
0x180034f71  sub     ecx, 1
0x180034f74  jz      short loc_180034F21
0x180034f76  sub     ecx, 7
0x180034f79  jz      short loc_180034FA9
0x180034f7b  sub     ecx, 1
0x180034f7e  jz      short loc_180034F9A
0x180034f80  cmp     ecx, 21h ; '!'
0x180034f83  jnz     short loc_180034FD6
0x180034f85  lea     rdx, [r14+8]; Buf2
0x180034f89  mov     r8d, 8; Size
0x180034f8f  lea     rcx, [rdi+8]; Buf1
0x180034f93  call    memcmp_0
0x180034f98  jmp     short loc_180034FB6
0x180034f9a  mov     rdx, [r14+8]; String2
0x180034f9e  mov     rcx, [rdi+8]; String1
0x180034fa2  call    _wcsicmp
0x180034fa7  jmp     short loc_180034FB6
0x180034fa9  mov     rdx, [r14+8]
0x180034fad  mov     rcx, [rdi+8]
0x180034fb1  call    _o__stricmp_0
0x180034fb6  mov     [rsi], eax
0x180034fb8  jmp     loc_18003511F
0x180034fbd  mov     rdx, [r14+8]; Buf2
0x180034fc1  mov     r8d, 10h; Size
0x180034fc7  mov     rcx, [rdi+8]; Buf1
0x180034fcb  call    memcmp_0
0x180034fd0  neg     eax
0x180034fd2  sbb     eax, eax
0x180034fd4  jmp     short loc_180034FB6
0x180034fd6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034fdd  lea     rdi, qword_18006EB20
0x180034fe4  mov     ebp, 0C00D36E8h
0x180034fe9  test    rcx, rcx
0x180034fec  jnz     short loc_18003502B
0x180034fee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180034ff4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180034ffb  mov     rcx, rax
0x180034ffe  test    rax, rax
0x180035001  jz      short loc_180035021
0x180035003  mov     rax, [rax]
0x180035006  mov     edx, 7F0h
0x18003500b  mov     rax, [rax+8]
0x18003500f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035014  test    eax, eax
0x180035016  jz      short loc_180035021
0x180035018  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003501f  jmp     short loc_18003502B
0x180035021  mov     rcx, rdi; this
0x180035024  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003502b  cmp     [rcx+8], bl
0x18003502e  jz      short loc_180035058
0x180035030  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035035  cmp     [rax+7CCh], ebp
0x18003503b  jz      short loc_180035051
0x18003503d  mov     r9d, ebp; int
0x180035040  mov     r8d, 5CBh; int
0x180035046  mov     rdx, r15; char *
0x180035049  mov     rcx, rax; this
0x18003504c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035051  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035058  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003505d  cmp     al, 1
0x18003505f  jb      short loc_18003508B
0x180035061  mov     rcx, cs:WPP_GLOBAL_Control
0x180035068  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18003506f  mov     edx, 59h ; 'Y'
  ... truncated ...
```
