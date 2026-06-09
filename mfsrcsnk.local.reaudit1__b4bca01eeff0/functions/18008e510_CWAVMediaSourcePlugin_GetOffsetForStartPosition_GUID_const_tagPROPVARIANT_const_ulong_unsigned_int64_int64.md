# CWAVMediaSourcePlugin::GetOffsetForStartPosition(_GUID const *,tagPROPVARIANT const *,ulong,unsigned __int64 *,__int64 *)

- ea: `0x18008e510`
- end: `0x18008eb84`
- name: `?GetOffsetForStartPosition@CWAVMediaSourcePlugin@@UEAAJPEBU_GUID@@PEBUtagPROPVARIANT@@KPEA_KPEA_J@Z`
- size: `1652`
- prototype: `int(CWAVMediaSourcePlugin *__hidden this, const struct _GUID *, const struct tagPROPVARIANT *, unsigned int, unsigned __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cf4`
- `0x180008890`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x18008e510`
- `0x1800b1dc8`
- `0x1800e25cc`
- `0x1800e9794`
- `0x180110ed0`
- `0x1801487d8`
- `0x18015df78`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008e5af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008e681`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008e75c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008e821`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008e8df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008e9c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008eaa7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008e5af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008e681`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008e75c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008e821`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008e8df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008e9c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008eaa7`

## string_xrefs

- `0x18008e553`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008e60c`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008e6de`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008e7b9`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008e87e`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008e93c`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008ea26`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008eb07`: `CWAVMediaSourcePlugin::GetOffsetForStartPosition`

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
        v39 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v11 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v27 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          if ( (unsigned __int8)byte_1801BA109 >= 4u )
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
              v36 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        else if ( (unsigned __int8)byte_1801BA109 >= 8u )
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
            v31 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v23 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v17 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x18008e510  mov     [rsp-38h+arg_18], rbx
0x18008e515  push    rbp
0x18008e516  push    rsi
0x18008e517  push    rdi
0x18008e518  push    r12
0x18008e51a  push    r13
0x18008e51c  push    r14
0x18008e51e  push    r15
0x18008e520  mov     rbp, rsp
0x18008e523  sub     rsp, 80h
0x18008e52a  mov     rax, cs:__security_cookie
0x18008e531  xor     rax, rsp
0x18008e534  mov     [rbp+var_10], rax
0x18008e538  mov     r14, [rbp+arg_28]
0x18008e53c  mov     rsi, r8
0x18008e53f  mov     r12, [rbp+arg_20]
0x18008e543  mov     r15, rdx
0x18008e546  mov     r13, rcx
0x18008e549  mov     [rbp+var_28], r14
0x18008e54d  mov     r8d, 24Eh; int
0x18008e553  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x18008e55a  lea     rcx, [rbp+var_40]; this
0x18008e55e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008e563  xor     edx, edx
0x18008e565  lea     rdi, [r13-18h]
0x18008e569  mov     [rbp+var_30], rdx
0x18008e56d  mov     [rbp+var_38], rdx
0x18008e571  mov     [rbp+var_20], edx
0x18008e574  mov     [rbp+var_18], rdx
0x18008e578  cmp     [rdi+30h], rdx
0x18008e57c  jz      loc_18008EA96
0x18008e582  cmp     [rsi], dx
0x18008e585  jz      loc_18008EA96
0x18008e58b  mov     r8, rsi; struct tagPROPVARIANT *
0x18008e58e  mov     rdx, r15; struct _GUID *
0x18008e591  mov     rcx, rdi; this
0x18008e594  call    ?CheckForValidStartPosition@CWAVMediaSourcePlugin@@AEAAJPEBU_GUID@@PEBUtagPROPVARIANT@@@Z; CWAVMediaSourcePlugin::CheckForValidStartPosition(_GUID const *,tagPROPVARIANT const *)
0x18008e599  mov     ebx, eax
0x18008e59b  test    eax, eax
0x18008e59d  jns     loc_18008E638
0x18008e5a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e5aa  test    rcx, rcx
0x18008e5ad  jnz     short loc_18008E5F6
0x18008e5af  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008e5b6  nop     dword ptr [rax+rax+00h]
0x18008e5bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e5c2  mov     rcx, rax
0x18008e5c5  test    rax, rax
0x18008e5c8  jz      short loc_18008E5E8
0x18008e5ca  mov     rax, [rax]
0x18008e5cd  mov     edx, 7F0h
0x18008e5d2  mov     rax, [rax+8]
0x18008e5d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e5db  test    eax, eax
0x18008e5dd  jz      short loc_18008E5E8
0x18008e5df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e5e6  jmp     short loc_18008E5F6
0x18008e5e8  lea     rcx, qword_1801B97E0; this
0x18008e5ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e5f6  cmp     byte ptr [rcx+8], 0
0x18008e5fa  jz      short loc_18008E621
0x18008e5fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008e601  cmp     [rax+7CCh], ebx
0x18008e607  jz      short loc_18008E621
0x18008e609  mov     r9d, ebx; int
0x18008e60c  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x18008e613  mov     r8d, 25Bh; int
0x18008e619  mov     rcx, rax; this
0x18008e61c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008e621  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008e628  jb      loc_18008EB48
0x18008e62e  mov     edx, 46h ; 'F'
0x18008e633  jmp     loc_18008EB2A
0x18008e638  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008e63c  lea     r9, [rbp+var_18]
0x18008e640  mov     [r12], rax
0x18008e644  lea     r8, [rbp+var_20]
0x18008e648  mov     [r14], rax
0x18008e64b  xor     edx, edx
0x18008e64d  mov     rax, [rdi+38h]
0x18008e651  mov     rcx, [r13+18h]
0x18008e655  mov     r14, [rax+1D8h]
0x18008e65c  mov     rax, [rcx]
0x18008e65f  mov     rax, [rax+110h]
0x18008e666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e66b  mov     ebx, eax
0x18008e66d  test    eax, eax
0x18008e66f  jns     loc_18008E70A
0x18008e675  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e67c  test    rcx, rcx
0x18008e67f  jnz     short loc_18008E6C8
0x18008e681  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008e688  nop     dword ptr [rax+rax+00h]
0x18008e68d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e694  mov     rcx, rax
0x18008e697  test    rax, rax
0x18008e69a  jz      short loc_18008E6BA
0x18008e69c  mov     rax, [rax]
0x18008e69f  mov     edx, 7F0h
0x18008e6a4  mov     rax, [rax+8]
0x18008e6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e6ad  test    eax, eax
0x18008e6af  jz      short loc_18008E6BA
0x18008e6b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e6b8  jmp     short loc_18008E6C8
0x18008e6ba  lea     rcx, qword_1801B97E0; this
0x18008e6c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e6c8  cmp     byte ptr [rcx+8], 0
0x18008e6cc  jz      short loc_18008E6F3
0x18008e6ce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008e6d3  cmp     [rax+7CCh], ebx
0x18008e6d9  jz      short loc_18008E6F3
0x18008e6db  mov     r9d, ebx; int
0x18008e6de  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x18008e6e5  mov     r8d, 262h; int
0x18008e6eb  mov     rcx, rax; this
0x18008e6ee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008e6f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008e6fa  jb      loc_18008EB48
0x18008e700  mov     edx, 47h ; 'G'
0x18008e705  jmp     loc_18008EB2A
0x18008e70a  mov     rax, cs:MF_TIME_FORMAT_BYTESTREAM_OFFSET
0x18008e711  sub     rax, [r15]
0x18008e714  jnz     short loc_18008E721
0x18008e716  mov     rax, cs:qword_180192B60
0x18008e71d  sub     rax, [r15+8]
0x18008e721  mov     rdx, [rsi+8]; __int64
0x18008e725  xor     r15d, r15d
0x18008e728  test    rax, rax
0x18008e72b  setz    al
0x18008e72e  test    al, al
0x18008e730  jz      loc_18008E7E5
0x18008e736  lea     r9, [rbp+var_38]; __int64 *
0x18008e73a  mov     rcx, r14; this
0x18008e73d  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18008e741  call    ?GetOffsetForStartBytePosition@CAudioStreamParser@@QEAAJ_KPEA_KPEA_J@Z; CAudioStreamParser::GetOffsetForStartBytePosition(unsigned __int64,unsigned __int64 *,__int64 *)
0x18008e746  mov     ebx, eax
0x18008e748  test    eax, eax
0x18008e74a  jns     loc_18008E968
0x18008e750  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e757  test    rcx, rcx
0x18008e75a  jnz     short loc_18008E7A3
0x18008e75c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008e763  nop     dword ptr [rax+rax+00h]
0x18008e768  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e76f  mov     rcx, rax
0x18008e772  test    rax, rax
0x18008e775  jz      short loc_18008E795
0x18008e777  mov     rax, [rax]
0x18008e77a  mov     edx, 7F0h
0x18008e77f  mov     rax, [rax+8]
0x18008e783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e788  test    eax, eax
0x18008e78a  jz      short loc_18008E795
0x18008e78c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e793  jmp     short loc_18008E7A3
0x18008e795  lea     rcx, qword_1801B97E0; this
0x18008e79c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e7a3  cmp     [rcx+8], r15b
0x18008e7a7  jz      short loc_18008E7CE
0x18008e7a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008e7ae  cmp     [rax+7CCh], ebx
0x18008e7b4  jz      short loc_18008E7CE
0x18008e7b6  mov     r9d, ebx; int
0x18008e7b9  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x18008e7c0  mov     r8d, 26Bh; int
0x18008e7c6  mov     rcx, rax; this
0x18008e7c9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008e7ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008e7d5  jb      loc_18008EB48
0x18008e7db  mov     edx, 48h ; 'H'
0x18008e7e0  jmp     loc_18008EB2A
0x18008e7e5  mov     rax, [r13+220h]
0x18008e7ec  cmp     rax, rdx
0x18008e7ef  jnz     loc_18008E8B9
0x18008e7f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008e7f9  jz      loc_18008E8B9
0x18008e7ff  lea     rdx, [rbp+var_38]; __int64 *
0x18008e803  mov     rcx, r14; this
0x18008e806  call    ?GetCurrentTimePosition@CAudioStreamParser@@QEAAJPEA_J@Z; CAudioStreamParser::GetCurrentTimePosition(__int64 *)
0x18008e80b  mov     ebx, eax
0x18008e80d  test    eax, eax
0x18008e80f  jns     loc_18008E8AA
0x18008e815  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e81c  test    rcx, rcx
0x18008e81f  jnz     short loc_18008E868
0x18008e821  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008e828  nop     dword ptr [rax+rax+00h]
0x18008e82d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e834  mov     rcx, rax
0x18008e837  test    rax, rax
0x18008e83a  jz      short loc_18008E85A
0x18008e83c  mov     rax, [rax]
0x18008e83f  mov     edx, 7F0h
0x18008e844  mov     rax, [rax+8]
0x18008e848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e84d  test    eax, eax
0x18008e84f  jz      short loc_18008E85A
0x18008e851  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e858  jmp     short loc_18008E868
0x18008e85a  lea     rcx, qword_1801B97E0; this
0x18008e861  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e868  cmp     [rcx+8], r15b
0x18008e86c  jz      short loc_18008E893
0x18008e86e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008e873  cmp     [rax+7CCh], ebx
0x18008e879  jz      short loc_18008E893
0x18008e87b  mov     r9d, ebx; int
0x18008e87e  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x18008e885  mov     r8d, 275h; int
0x18008e88b  mov     rcx, rax; this
0x18008e88e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008e893  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008e89a  jb      loc_18008EB48
0x18008e8a0  mov     edx, 49h ; 'I'
0x18008e8a5  jmp     loc_18008EB2A
0x18008e8aa  mov     rax, [r14+1D0h]
0x18008e8b1  mov     ebx, r15d
0x18008e8b4  jmp     loc_18008E96C
0x18008e8b9  lea     r9, [rbp+var_38]; __int64 *
0x18008e8bd  mov     rcx, r14; this
0x18008e8c0  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18008e8c4  call    ?GetOffsetForStartTimePosition@CAudioStreamParser@@QEAAJ_JPEA_KPEA_J@Z; CAudioStreamParser::GetOffsetForStartTimePosition(__int64,unsigned __int64 *,__int64 *)
0x18008e8c9  mov     ebx, eax
0x18008e8cb  test    eax, eax
0x18008e8cd  jns     loc_18008E968
0x18008e8d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e8da  test    rcx, rcx
0x18008e8dd  jnz     short loc_18008E926
0x18008e8df  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008e8e6  nop     dword ptr [rax+rax+00h]
0x18008e8eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e8f2  mov     rcx, rax
0x18008e8f5  test    rax, rax
0x18008e8f8  jz      short loc_18008E918
0x18008e8fa  mov     rax, [rax]
0x18008e8fd  mov     edx, 7F0h
0x18008e902  mov     rax, [rax+8]
0x18008e906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e90b  test    eax, eax
0x18008e90d  jz      short loc_18008E918
0x18008e90f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e916  jmp     short loc_18008E926
0x18008e918  lea     rcx, qword_1801B97E0; this
0x18008e91f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e926  cmp     [rcx+8], r15b
0x18008e92a  jz      short loc_18008E951
0x18008e92c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008e931  cmp     [rax+7CCh], ebx
0x18008e937  jz      short loc_18008E951
0x18008e939  mov     r9d, ebx; int
0x18008e93c  lea     rdx, aCwavmediasourc_0; "CWAVMediaSourcePlugin::GetOffsetForStar"...
0x18008e943  mov     r8d, 27Ch; int
0x18008e949  mov     rcx, rax; this
0x18008e94c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008e951  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008e958  jb      loc_18008EB48
0x18008e95e  mov     edx, 4Bh ; 'K'
0x18008e963  jmp     loc_18008EB2A
0x18008e968  mov     rax, [rbp+var_30]
0x18008e96c  mov     rcx, [rbp+var_28]
0x18008e970  mov     [r12], rax
0x18008e974  mov     rax, [rbp+var_38]
0x18008e978  mov     [rcx], rax
0x18008e97b  mov     rcx, [r12]
0x18008e97f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008e983  jnz     loc_18008EA52
0x18008e989  cmp     cs:byte_1801BA109, 4
0x18008e990  jb      short loc_18008E9B8
0x18008e992  mov     rax, [rsi+8]
0x18008e996  lea     edx, [rcx+4Dh]
0x18008e999  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e9a0  lea     r8, WPP_b9c73e557172350cc31d2d464215ca3e_Traceguids
0x18008e9a7  mov     r9, rdi
0x18008e9aa  mov     [rsp+80h+var_60], rax
0x18008e9af  mov     rcx, [rcx+38h]
0x18008e9b3  call    WPP_SF_qI
0x18008e9b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e9bf  mov     ebx, 0C00D36E5h
0x18008e9c4  test    rcx, rcx
0x18008e9c7  jnz     short loc_18008EA10
0x18008e9c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008e9d0  nop     dword ptr [rax+rax+00h]
0x18008e9d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008e9dc  mov     rcx, rax
0x18008e9df  test    rax, rax
0x18008e9e2  jz      short loc_18008EA02
0x18008e9e4  mov     rax, [rax]
0x18008e9e7  mov     edx, 7F0h
0x18008e9ec  mov     rax, [rax+8]
0x18008e9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e9f5  test    eax, eax
0x18008e9f7  jz      short loc_18008EA02
0x18008e9f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008ea00  jmp     short loc_18008EA10
0x18008ea02  lea     rcx, qword_1801B97E0; this
0x18008ea09  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008ea10  cmp     [rcx+8], r15b
0x18008ea14  jz      short loc_18008EA3B
0x18008ea16  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
  ... truncated ...
```
