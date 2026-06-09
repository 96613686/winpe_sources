# CWAVMediaSourcePlugin::GetOffsetForStartPosition(_GUID const *,tagPROPVARIANT const *,ulong,unsigned __int64 *,__int64 *)

- ea: `0x1800896e0`
- end: `0x180089d29`
- name: `?GetOffsetForStartPosition@CWAVMediaSourcePlugin@@UEAAJPEBU_GUID@@PEBUtagPROPVARIANT@@KPEA_KPEA_J@Z`
- size: `1609`
- prototype: `int(CWAVMediaSourcePlugin *__hidden this, const struct _GUID *, const struct tagPROPVARIANT *, unsigned int, unsigned __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005eb8`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x1800896e0`
- `0x1800aca10`
- `0x1800dc0f8`
- `0x1800e2f60`
- `0x1801099f0`
- `0x180140abc`
- `0x180155748`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008977f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008984b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089920`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800899df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089a97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089b7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089c53`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008977f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008984b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089920`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800899df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089a97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089b7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089c53`

## string_xrefs

- `0x180089723`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x1800897d6`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x1800898a2`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x180089977`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x180089a36`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x180089aee`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x180089bd2`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x180089cad`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`

## pseudocode

```c
__int64 __fastcall CWAVMediaSourcePlugin::GetOffsetForStartPosition(
        CWAVMediaSourcePlugin *this,
        const struct _GUID *a2,
        const struct tagPROPVARIANT *a3,
        __int64 a4,
        unsigned __int64 *a5,
        __int64 *a6)
{
  __int64 v9; // rdx
  int CurrentTimePosition; // ebx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  CAudioStreamParser *v15; // r14
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rax
  LARGE_INTEGER hVal; // rdx
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rax
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  unsigned __int64 v30; // rax
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 *v34; // rcx
  __int64 v35; // rax
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v43[8]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v44; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int64 v45; // [rsp+50h] [rbp-30h] BYREF
  __int64 *v46; // [rsp+58h] [rbp-28h]
  int v47; // [rsp+60h] [rbp-20h] BYREF
  __int64 v48; // [rsp+68h] [rbp-18h] BYREF

  v46 = a6;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v43,
    "CWAVMediaSourcePlugin::GetOffsetForStartPosition",
    590);
  v45 = 0;
  v44 = 0;
  v47 = 0;
  v48 = 0;
  if ( !*((_QWORD *)this + 3) || !a3->vt )
  {
    v39 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentTimePosition = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0);
      CallStackTracing::s_wpInstance = v40;
      if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
      {
        v39 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v39 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v39 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWAVMediaSourcePlugin::GetOffsetForStartPosition",
          600,
          -1072875854);
    }
    if ( g_wppLevels )
    {
      v14 = 69;
      goto LABEL_90;
    }
    goto LABEL_91;
  }
  CurrentTimePosition = CWAVMediaSourcePlugin::CheckForValidStartPosition(
                          (CWAVMediaSourcePlugin *)((char *)this - 24),
                          a2,
                          a3);
  if ( CurrentTimePosition < 0 )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != CurrentTimePosition )
        CallStackContext::TraceFailure(
          v13,
          "CWAVMediaSourcePlugin::GetOffsetForStartPosition",
          603,
          CurrentTimePosition);
    }
    if ( g_wppLevels )
    {
      v14 = 70;
LABEL_90:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        WPP_b9c73e557172350cc31d2d464215ca3e_Traceguids,
        (char *)this - 24,
        CurrentTimePosition);
      goto LABEL_91;
    }
    goto LABEL_91;
  }
  *a5 = -1;
  *a6 = -1;
  v15 = *(CAudioStreamParser **)(*((_QWORD *)this + 4) + 472LL);
  CurrentTimePosition = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, __int64 *))(**((_QWORD **)this + 3) + 272LL))(
                          *((_QWORD *)this + 3),
                          0,
                          &v47,
                          &v48);
  if ( CurrentTimePosition >= 0 )
  {
    v20 = MF_TIME_FORMAT_BYTESTREAM_OFFSET - *(_QWORD *)&a2->Data1;
    if ( MF_TIME_FORMAT_BYTESTREAM_OFFSET == *(_QWORD *)&a2->Data1 )
      v20 = 0xCA572657DBDF638CuLL - *(_QWORD *)a2->Data4;
    hVal = a3->hVal;
    if ( v20 )
    {
      v26 = *((_QWORD *)this + 68);
      if ( v26 == hVal.QuadPart && v26 != -1 )
      {
        CurrentTimePosition = CAudioStreamParser::GetCurrentTimePosition(v15, &v44);
        if ( CurrentTimePosition < 0 )
        {
          v27 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
            CallStackTracing::s_wpInstance = v28;
            if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
            {
              v27 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v27 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v27 + 8) )
          {
            v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
            if ( *((_DWORD *)v29 + 499) != CurrentTimePosition )
              CallStackContext::TraceFailure(
                v29,
                "CWAVMediaSourcePlugin::GetOffsetForStartPosition",
                629,
                CurrentTimePosition);
          }
          if ( g_wppLevels )
          {
            v14 = 73;
            goto LABEL_90;
          }
          goto LABEL_91;
        }
        v30 = *((_QWORD *)v15 + 58);
        CurrentTimePosition = 0;
LABEL_65:
        v34 = v46;
        *a5 = v30;
        v35 = v44;
        *v34 = v44;
        if ( *a5 == -1 )
        {
          if ( (unsigned __int8)byte_1801B1109 >= 4u )
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qI)(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              76,
              WPP_b9c73e557172350cc31d2d464215ca3e_Traceguids,
              (char *)this - 24,
              (LARGE_INTEGER)a3->hVal.QuadPart);
          v36 = (wchar_t *)CallStackTracing::s_wpInstance;
          CurrentTimePosition = -1072875803;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
            CallStackTracing::s_wpInstance = v37;
            if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
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
            if ( *((_DWORD *)v38 + 499) != -1072875803 )
              CallStackContext::TraceFailure(v38, "CWAVMediaSourcePlugin::GetOffsetForStartPosition", 646, -1072875803);
          }
          if ( g_wppLevels )
          {
            v14 = 77;
            goto LABEL_90;
          }
        }
        else if ( (unsigned __int8)byte_1801B1109 >= 8u )
        {
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qIII)(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            78,
            WPP_b9c73e557172350cc31d2d464215ca3e_Traceguids,
            (char *)this - 24,
            (LARGE_INTEGER)a3->hVal.QuadPart,
            *a5,
            v35);
        }
        goto LABEL_91;
      }
      CurrentTimePosition = CAudioStreamParser::GetOffsetForStartTimePosition(v15, hVal.QuadPart, &v45, &v44);
      if ( CurrentTimePosition < 0 )
      {
        v31 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v31 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v31 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v31 + 8) )
        {
          v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
          if ( *((_DWORD *)v33 + 499) != CurrentTimePosition )
            CallStackContext::TraceFailure(
              v33,
              "CWAVMediaSourcePlugin::GetOffsetForStartPosition",
              636,
              CurrentTimePosition);
        }
        if ( g_wppLevels )
        {
          v14 = 75;
          goto LABEL_90;
        }
        goto LABEL_91;
      }
    }
    else
    {
      CurrentTimePosition = CAudioStreamParser::GetOffsetForStartBytePosition(v15, hVal.QuadPart, &v45, &v44);
      if ( CurrentTimePosition < 0 )
      {
        v23 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != CurrentTimePosition )
            CallStackContext::TraceFailure(
              v25,
              "CWAVMediaSourcePlugin::GetOffsetForStartPosition",
              619,
              CurrentTimePosition);
        }
        if ( g_wppLevels )
        {
          v14 = 72;
          goto LABEL_90;
        }
        goto LABEL_91;
      }
    }
    v30 = v45;
    goto LABEL_65;
  }
  v17 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
    if ( *((_DWORD *)v19 + 499) != CurrentTimePosition )
      CallStackContext::TraceFailure(v19, "CWAVMediaSourcePlugin::GetOffsetForStartPosition", 610, CurrentTimePosition);
  }
  if ( g_wppLevels )
  {
    v14 = 71;
    goto LABEL_90;
  }
LABEL_91:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v48);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v43);
  return (unsigned int)CurrentTimePosition;
}

```

## disassembly

```asm
0x1800896e0  mov     [rsp-38h+arg_18], rbx
0x1800896e5  push    rbp
0x1800896e6  push    rsi
0x1800896e7  push    rdi
0x1800896e8  push    r12
0x1800896ea  push    r13
0x1800896ec  push    r14
0x1800896ee  push    r15
0x1800896f0  mov     rbp, rsp
0x1800896f3  sub     rsp, 80h
0x1800896fa  mov     rax, cs:__security_cookie
0x180089701  xor     rax, rsp
0x180089704  mov     [rbp+var_10], rax
0x180089708  mov     r14, [rbp+arg_28]
0x18008970c  mov     rsi, r8
0x18008970f  mov     r12, [rbp+arg_20]
0x180089713  mov     r15, rdx
0x180089716  mov     r13, rcx
0x180089719  mov     [rbp+var_28], r14
0x18008971d  mov     r8d, 24Eh; int
0x180089723  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x18008972a  lea     rcx, [rbp+var_40]; this
0x18008972e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180089733  xor     edx, edx
0x180089735  lea     rdi, [r13-18h]
0x180089739  mov     [rbp+var_30], rdx
0x18008973d  mov     [rbp+var_38], rdx
0x180089741  mov     [rbp+var_20], edx
0x180089744  mov     [rbp+var_18], rdx
0x180089748  cmp     [rdi+30h], rdx
0x18008974c  jz      loc_180089C42
0x180089752  cmp     [rsi], dx
0x180089755  jz      loc_180089C42
0x18008975b  mov     r8, rsi; struct tagPROPVARIANT *
0x18008975e  mov     rdx, r15; struct _GUID *
0x180089761  mov     rcx, rdi; this
0x180089764  call    ?CheckForValidStartPosition@CWAVMediaSourcePlugin@@AEAAJPEBU_GUID@@PEBUtagPROPVARIANT@@@Z; CWAVMediaSourcePlugin::CheckForValidStartPosition(_GUID const *,tagPROPVARIANT const *)
0x180089769  mov     ebx, eax
0x18008976b  test    eax, eax
0x18008976d  jns     loc_180089802
0x180089773  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008977a  test    rcx, rcx
0x18008977d  jnz     short loc_1800897C0
0x18008977f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089785  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008978c  mov     rcx, rax
0x18008978f  test    rax, rax
0x180089792  jz      short loc_1800897B2
0x180089794  mov     rax, [rax]
0x180089797  mov     edx, 7F0h
0x18008979c  mov     rax, [rax+8]
0x1800897a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800897a5  test    eax, eax
0x1800897a7  jz      short loc_1800897B2
0x1800897a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800897b0  jmp     short loc_1800897C0
0x1800897b2  lea     rcx, qword_1801B07E0; this
0x1800897b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800897c0  cmp     byte ptr [rcx+8], 0
0x1800897c4  jz      short loc_1800897EB
0x1800897c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800897cb  cmp     [rax+7CCh], ebx
0x1800897d1  jz      short loc_1800897EB
0x1800897d3  mov     r9d, ebx; int
0x1800897d6  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x1800897dd  mov     r8d, 25Bh; int
0x1800897e3  mov     rcx, rax; this
0x1800897e6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800897eb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800897f2  jb      loc_180089CEE
0x1800897f8  mov     edx, 46h ; 'F'
0x1800897fd  jmp     loc_180089CD0
0x180089802  or      rax, 0FFFFFFFFFFFFFFFFh
0x180089806  lea     r9, [rbp+var_18]
0x18008980a  mov     [r12], rax
0x18008980e  lea     r8, [rbp+var_20]
0x180089812  mov     [r14], rax
0x180089815  xor     edx, edx
0x180089817  mov     rax, [rdi+38h]
0x18008981b  mov     rcx, [r13+18h]
0x18008981f  mov     r14, [rax+1D8h]
0x180089826  mov     rax, [rcx]
0x180089829  mov     rax, [rax+110h]
0x180089830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089835  mov     ebx, eax
0x180089837  test    eax, eax
0x180089839  jns     loc_1800898CE
0x18008983f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089846  test    rcx, rcx
0x180089849  jnz     short loc_18008988C
0x18008984b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089851  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089858  mov     rcx, rax
0x18008985b  test    rax, rax
0x18008985e  jz      short loc_18008987E
0x180089860  mov     rax, [rax]
0x180089863  mov     edx, 7F0h
0x180089868  mov     rax, [rax+8]
0x18008986c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089871  test    eax, eax
0x180089873  jz      short loc_18008987E
0x180089875  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008987c  jmp     short loc_18008988C
0x18008987e  lea     rcx, qword_1801B07E0; this
0x180089885  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008988c  cmp     byte ptr [rcx+8], 0
0x180089890  jz      short loc_1800898B7
0x180089892  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089897  cmp     [rax+7CCh], ebx
0x18008989d  jz      short loc_1800898B7
0x18008989f  mov     r9d, ebx; int
0x1800898a2  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x1800898a9  mov     r8d, 262h; int
0x1800898af  mov     rcx, rax; this
0x1800898b2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800898b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800898be  jb      loc_180089CEE
0x1800898c4  mov     edx, 47h ; 'G'
0x1800898c9  jmp     loc_180089CD0
0x1800898ce  mov     rax, cs:MF_TIME_FORMAT_BYTESTREAM_OFFSET
0x1800898d5  sub     rax, [r15]
0x1800898d8  jnz     short loc_1800898E5
0x1800898da  mov     rax, cs:qword_180189AC8
0x1800898e1  sub     rax, [r15+8]
0x1800898e5  mov     rdx, [rsi+8]; __int64
0x1800898e9  xor     r15d, r15d
0x1800898ec  test    rax, rax
0x1800898ef  setz    al
0x1800898f2  test    al, al
0x1800898f4  jz      loc_1800899A3
0x1800898fa  lea     r9, [rbp+var_38]; __int64 *
0x1800898fe  mov     rcx, r14; this
0x180089901  lea     r8, [rbp+var_30]; unsigned __int64 *
0x180089905  call    ?GetOffsetForStartBytePosition@CAudioStreamParser@@QEAAJ_KPEA_KPEA_J@Z; CAudioStreamParser::GetOffsetForStartBytePosition(unsigned __int64,unsigned __int64 *,__int64 *)
0x18008990a  mov     ebx, eax
0x18008990c  test    eax, eax
0x18008990e  jns     loc_180089B1A
0x180089914  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008991b  test    rcx, rcx
0x18008991e  jnz     short loc_180089961
0x180089920  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089926  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008992d  mov     rcx, rax
0x180089930  test    rax, rax
0x180089933  jz      short loc_180089953
0x180089935  mov     rax, [rax]
0x180089938  mov     edx, 7F0h
0x18008993d  mov     rax, [rax+8]
0x180089941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089946  test    eax, eax
0x180089948  jz      short loc_180089953
0x18008994a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089951  jmp     short loc_180089961
0x180089953  lea     rcx, qword_1801B07E0; this
0x18008995a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089961  cmp     [rcx+8], r15b
0x180089965  jz      short loc_18008998C
0x180089967  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008996c  cmp     [rax+7CCh], ebx
0x180089972  jz      short loc_18008998C
0x180089974  mov     r9d, ebx; int
0x180089977  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x18008997e  mov     r8d, 26Bh; int
0x180089984  mov     rcx, rax; this
0x180089987  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008998c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089993  jb      loc_180089CEE
0x180089999  mov     edx, 48h ; 'H'
0x18008999e  jmp     loc_180089CD0
0x1800899a3  mov     rax, [r13+220h]
0x1800899aa  cmp     rax, rdx
0x1800899ad  jnz     loc_180089A71
0x1800899b3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800899b7  jz      loc_180089A71
0x1800899bd  lea     rdx, [rbp+var_38]; __int64 *
0x1800899c1  mov     rcx, r14; this
0x1800899c4  call    ?GetCurrentTimePosition@CAudioStreamParser@@QEAAJPEA_J@Z; CAudioStreamParser::GetCurrentTimePosition(__int64 *)
0x1800899c9  mov     ebx, eax
0x1800899cb  test    eax, eax
0x1800899cd  jns     loc_180089A62
0x1800899d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800899da  test    rcx, rcx
0x1800899dd  jnz     short loc_180089A20
0x1800899df  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800899e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800899ec  mov     rcx, rax
0x1800899ef  test    rax, rax
0x1800899f2  jz      short loc_180089A12
0x1800899f4  mov     rax, [rax]
0x1800899f7  mov     edx, 7F0h
0x1800899fc  mov     rax, [rax+8]
0x180089a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089a05  test    eax, eax
0x180089a07  jz      short loc_180089A12
0x180089a09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089a10  jmp     short loc_180089A20
0x180089a12  lea     rcx, qword_1801B07E0; this
0x180089a19  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089a20  cmp     [rcx+8], r15b
0x180089a24  jz      short loc_180089A4B
0x180089a26  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089a2b  cmp     [rax+7CCh], ebx
0x180089a31  jz      short loc_180089A4B
0x180089a33  mov     r9d, ebx; int
0x180089a36  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x180089a3d  mov     r8d, 275h; int
0x180089a43  mov     rcx, rax; this
0x180089a46  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089a4b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089a52  jb      loc_180089CEE
0x180089a58  mov     edx, 49h ; 'I'
0x180089a5d  jmp     loc_180089CD0
0x180089a62  mov     rax, [r14+1D0h]
0x180089a69  mov     ebx, r15d
0x180089a6c  jmp     loc_180089B1E
0x180089a71  lea     r9, [rbp+var_38]; __int64 *
0x180089a75  mov     rcx, r14; this
0x180089a78  lea     r8, [rbp+var_30]; unsigned __int64 *
0x180089a7c  call    ?GetOffsetForStartTimePosition@CAudioStreamParser@@QEAAJ_JPEA_KPEA_J@Z; CAudioStreamParser::GetOffsetForStartTimePosition(__int64,unsigned __int64 *,__int64 *)
0x180089a81  mov     ebx, eax
0x180089a83  test    eax, eax
0x180089a85  jns     loc_180089B1A
0x180089a8b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089a92  test    rcx, rcx
0x180089a95  jnz     short loc_180089AD8
0x180089a97  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089a9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089aa4  mov     rcx, rax
0x180089aa7  test    rax, rax
0x180089aaa  jz      short loc_180089ACA
0x180089aac  mov     rax, [rax]
0x180089aaf  mov     edx, 7F0h
0x180089ab4  mov     rax, [rax+8]
0x180089ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089abd  test    eax, eax
0x180089abf  jz      short loc_180089ACA
0x180089ac1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089ac8  jmp     short loc_180089AD8
0x180089aca  lea     rcx, qword_1801B07E0; this
0x180089ad1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089ad8  cmp     [rcx+8], r15b
0x180089adc  jz      short loc_180089B03
0x180089ade  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089ae3  cmp     [rax+7CCh], ebx
0x180089ae9  jz      short loc_180089B03
0x180089aeb  mov     r9d, ebx; int
0x180089aee  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x180089af5  mov     r8d, 27Ch; int
0x180089afb  mov     rcx, rax; this
0x180089afe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089b03  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089b0a  jb      loc_180089CEE
0x180089b10  mov     edx, 4Bh ; 'K'
0x180089b15  jmp     loc_180089CD0
0x180089b1a  mov     rax, [rbp+var_30]
0x180089b1e  mov     rcx, [rbp+var_28]
0x180089b22  mov     [r12], rax
0x180089b26  mov     rax, [rbp+var_38]
0x180089b2a  mov     [rcx], rax
0x180089b2d  mov     rcx, [r12]
0x180089b31  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180089b35  jnz     loc_180089BFE
0x180089b3b  cmp     cs:byte_1801B1109, 4
0x180089b42  jb      short loc_180089B6A
0x180089b44  mov     rax, [rsi+8]
0x180089b48  lea     edx, [rcx+4Dh]
0x180089b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180089b52  lea     r8, WPP_b9c73e557172350cc31d2d464215ca3e_Traceguids
0x180089b59  mov     r9, rdi
0x180089b5c  mov     [rsp+80h+var_60], rax
0x180089b61  mov     rcx, [rcx+38h]
0x180089b65  call    WPP_SF_qI
0x180089b6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089b71  mov     ebx, 0C00D36E5h
0x180089b76  test    rcx, rcx
0x180089b79  jnz     short loc_180089BBC
0x180089b7b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089b81  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089b88  mov     rcx, rax
0x180089b8b  test    rax, rax
0x180089b8e  jz      short loc_180089BAE
0x180089b90  mov     rax, [rax]
0x180089b93  mov     edx, 7F0h
0x180089b98  mov     rax, [rax+8]
0x180089b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089ba1  test    eax, eax
0x180089ba3  jz      short loc_180089BAE
0x180089ba5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089bac  jmp     short loc_180089BBC
0x180089bae  lea     rcx, qword_1801B07E0; this
0x180089bb5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089bbc  cmp     [rcx+8], r15b
0x180089bc0  jz      short loc_180089BE7
0x180089bc2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089bc7  cmp     [rax+7CCh], ebx
0x180089bcd  jz      short loc_180089BE7
0x180089bcf  mov     r9d, ebx; int
0x180089bd2  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x180089bd9  mov     r8d, 286h; int
0x180089bdf  mov     rcx, rax; this
  ... truncated ...
```
