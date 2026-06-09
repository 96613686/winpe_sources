# CMFMediaStream::NewSample(IMFSample *)

- ea: `0x180105d4c`
- end: `0x18010653c`
- name: `?NewSample@CMFMediaStream@@QEAAJPEAUIMFSample@@@Z`
- size: `2032`
- prototype: `__int64 __fastcall(CMFMediaStream *__hidden this, struct IMFSample *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005e320`

## callees

- `0x1800063a8`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180069e4c`
- `0x180073b14`
- `0x180105d4c`
- `0x18013891c`
- `0x180149438`
- `0x18014b2b0`
- `0x18014b33c`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180106511`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180106511`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180105dd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180105dd0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180105df4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180105e92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180105f59`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010600b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801061b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010646c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180105df4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180105e92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180105f59`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010600b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801061b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010646c`
- `MFPlat!MFCreateMediaEvent` at `0x180105f3d`
- `MFPlat!MFCreateMediaEvent` at `0x180105f3d`
- `MFPlat!DestroyPropVariant` at `0x180106508`
- `MFPlat!DestroyPropVariant` at `0x180106508`

## pseudocode

```c
__int64 __fastcall CMFMediaStream::NewSample(CMFMediaStream *this, struct IMFSample *a2)
{
  __int64 v4; // rdx
  wchar_t *v5; // rcx
  HRESULT v6; // edi
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  wchar_t *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  struct IMFMediaEvent *v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rax
  struct IMFSampleVtbl *lpVtbl; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // ecx
  float v31; // xmm0_4
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rax
  double v35; // xmm0_8
  __int64 v36; // rax
  int v37; // ecx
  __int64 v38; // rdx
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  PROPVARIANT pvValue; // [rsp+40h] [rbp-28h] BYREF
  int v44; // [rsp+B0h] [rbp+48h] BYREF
  int v45; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v46; // [rsp+C0h] [rbp+58h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+C8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "CMFMediaStream::NewSample", 1667);
  ppEvent = 0;
  v46 = 0x7FFFFFFFFFFFFFFFLL;
  v45 = 0;
  *(_QWORD *)&pvValue.vt = 13;
  *(_OWORD *)&pvValue.decVal.Lo32 = (unsigned __int64)a2;
  if ( a2 )
    ((void (__fastcall *)(struct IMFSample *))a2->lpVtbl->AddRef)(a2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  if ( *((_DWORD *)this + 48) )
  {
    v5 = (wchar_t *)CallStackTracing::s_wpInstance;
    v6 = -1072873851;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072873851 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFMediaStream::NewSample", 1682, -1072873851);
    }
    if ( g_wppLevels )
    {
      v9 = 153;
LABEL_112:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_fc8c5d8c44273bdd34ec62b5fce42adb_Traceguids, this, v6);
      goto LABEL_113;
    }
    goto LABEL_113;
  }
  if ( a2 )
  {
    CMFMediaStream::AdjustSampleTime(this, a2);
    v6 = MFCreateMediaEvent(0xD5u, &GUID_00000000_0000_0000_0000_000000000000, 0, &pvValue, &ppEvent);
    if ( v6 < 0 )
    {
      v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != v6 )
          CallStackContext::TraceFailure(v16, "CMFMediaStream::NewSample", 1691, v6);
      }
      if ( g_wppLevels )
      {
        v9 = 155;
        goto LABEL_112;
      }
      goto LABEL_113;
    }
    v17 = ppEvent;
    ppEvent = 0;
    if ( !CStreamEventQueue::Add((CMFMediaStream *)((char *)this + 888), v17) )
    {
      v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      v6 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v22, "CMFMediaStream::NewSample", 1693, -2147024882);
      }
      if ( g_wppLevels )
      {
        v9 = 156;
        goto LABEL_112;
      }
      goto LABEL_113;
    }
    LOBYTE(v19) = 3;
    (*(void (__fastcall **)(_QWORD, struct IMFSample *, __int64))(**((_QWORD **)this + 50) + 64LL))(
      *((_QWORD *)this + 50),
      a2,
      v19);
    if ( ((int (__fastcall *)(struct IMFSample *, const GUID *, int *))a2->lpVtbl->GetUINT32)(
           a2,
           &MFSampleExtension_CleanPoint,
           &v45) >= 0 )
    {
      if ( v45 )
      {
        ++*((_DWORD *)this + 338);
        if ( (unsigned __int8)byte_1801B110B >= 8u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            157,
            &WPP_fc8c5d8c44273bdd34ec62b5fce42adb_Traceguids,
            this,
            *((_DWORD *)this + 338));
      }
    }
    ((void (__fastcall *)(struct IMFSample *, __int64 *))a2->lpVtbl->GetSampleTime)(a2, &v46);
    v23 = v46;
    *((_QWORD *)this + 28) = v46;
    if ( (unsigned __int8)byte_1801B110B >= 0x10u )
      WPP_SF_qdi(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        158,
        &WPP_fc8c5d8c44273bdd34ec62b5fce42adb_Traceguids,
        this,
        *((_DWORD *)this + 108),
        v23);
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 56LL))(*((_QWORD *)this + 50)) )
    {
      lpVtbl = a2->lpVtbl;
      v44 = 0;
      v6 = ((__int64 (__fastcall *)(struct IMFSample *, int *))lpVtbl->GetTotalLength)(a2, &v44);
      if ( v6 < 0 )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
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
          v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
          if ( *((_DWORD *)v28 + 499) != v6 )
            CallStackContext::TraceFailure(v28, "CMFMediaStream::NewSample", 1714, v6);
        }
        if ( g_wppLevels )
        {
          v9 = 159;
          goto LABEL_112;
        }
        goto LABEL_113;
      }
      *((_DWORD *)this + 12) += v44;
    }
    if ( *((_DWORD *)this + 52) )
    {
      *((_QWORD *)this + 27) = v46;
      *((_DWORD *)this + 52) = 0;
    }
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 56LL))(*((_QWORD *)this + 50))
      || *((_DWORD *)this + 51) )
    {
LABEL_100:
      if ( !*((_DWORD *)this + 49) )
      {
        v6 = CMFMediaStream::FillRequests(this);
        if ( v6 < 0 )
        {
          v39 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
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
            v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
            if ( *((_DWORD *)v41 + 499) != v6 )
              CallStackContext::TraceFailure(v41, "CMFMediaStream::NewSample", 1834, v6);
          }
          if ( g_wppLevels )
          {
            v9 = 162;
            goto LABEL_112;
          }
        }
      }
      goto LABEL_113;
    }
    v29 = v46;
    if ( v46 == 0x7FFFFFFFFFFFFFFFLL )
    {
      v30 = *((_DWORD *)this + 68);
      *((_DWORD *)this + 68) = v30 + 1;
      if ( v30 > 0xA
        && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 40LL))(*((_QWORD *)this + 50)) )
      {
        *((_DWORD *)this + 51) = 1;
      }
      goto LABEL_96;
    }
    v31 = *((float *)this + 343);
    *((_DWORD *)this + 68) = 0;
    if ( v31 <= 0.0 )
    {
      *((_DWORD *)this + 51) = 1;
    }
    else
    {
      v32 = *((_QWORD *)this + 27);
      if ( v32 == 0x7FFFFFFFFFFFFFFFLL )
      {
        if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 40LL))(*((_QWORD *)this + 50)) )
        {
          *((_DWORD *)this + 51) = 1;
          LODWORD(v33) = 1;
        }
        else
        {
          LODWORD(v33) = *((_DWORD *)this + 51);
        }
        v29 = v46;
      }
      else
      {
        v33 = 0;
        if ( v29 >= *((_QWORD *)this + 29) + v32 )
        {
          if ( (unsigned __int8)byte_1801B110B >= 8u )
          {
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qDiii)(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              v32,
              0,
              this,
              *((_DWORD *)this + 108),
              v29,
              v32,
              *((_QWORD *)this + 29),
              *(_QWORD *)&pvValue.vt,
              (LARGE_INTEGER)pvValue.hVal.QuadPart,
              pvValue.bstrblobVal.pData);
            v32 = *((_QWORD *)this + 27);
            v29 = v46;
          }
          *((_DWORD *)this + 51) = 1;
          v33 = 1;
        }
        if ( v29 + 50000000 < v32 )
        {
          if ( (unsigned __int8)byte_1801B110B >= 8u )
          {
            WPP_SF_qDiid(*((_QWORD *)WPP_GLOBAL_Control + 17), v32, v33, this, *((_DWORD *)this + 108), v29, v32);
            v29 = v46;
          }
          *((_DWORD *)this + 51) = 1;
          LODWORD(v33) = 1;
        }
      }
      if ( !(_DWORD)v33 )
        goto LABEL_89;
    }
    v36 = *((_QWORD *)this + 29);
    if ( v36 > 0 )
    {
      v35 = (double)(int)v36;
      goto LABEL_91;
    }
LABEL_89:
    v34 = *((_QWORD *)this + 27);
    if ( v29 <= v34 )
    {
      *((_DWORD *)this + 67) = 0;
      goto LABEL_96;
    }
    v35 = (double)((int)v29 - (int)v34);
LABEL_91:
    *((_DWORD *)this + 67) = (int)(v35 / 10000.0);
LABEL_96:
    if ( !*((_DWORD *)this + 51) )
      goto LABEL_113;
    v37 = 4;
    if ( *((_DWORD *)this + 334) > 4u )
      v37 = *((_DWORD *)this + 334);
    *((_DWORD *)this + 66) = v37;
    goto LABEL_100;
  }
  v10 = (wchar_t *)CallStackTracing::s_wpInstance;
  v6 = -2147467261;
  if ( !CallStackTracing::s_wpInstance )
  {
    v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
    CallStackTracing::s_wpInstance = v11;
    if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
    {
      v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v10 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v10 + 8) )
  {
    v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
    if ( *((_DWORD *)v12 + 499) != -2147467261 )
      CallStackContext::TraceFailure(v12, "CMFMediaStream::NewSample", 1687, -2147467261);
  }
  if ( g_wppLevels )
  {
    v9 = 154;
    goto LABEL_112;
  }
LABEL_113:
  DestroyPropVariant(&pvValue);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppEvent);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180105d4c  push    rbp
0x180105d4e  push    rbx
0x180105d4f  push    rsi
0x180105d50  push    rdi
0x180105d51  push    r12
0x180105d53  push    r13
0x180105d55  push    r14
0x180105d57  push    r15
0x180105d59  mov     rbp, rsp
0x180105d5c  sub     rsp, 68h
0x180105d60  mov     r14, rdx
0x180105d63  lea     rsi, aCmfmediastream_16; "CMFMediaStream::NewSample"
0x180105d6a  mov     rbx, rcx
0x180105d6d  mov     rdx, rsi; char *
0x180105d70  mov     r8d, 683h; int
0x180105d76  lea     rcx, [rbp+arg_0]; this
0x180105d7a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180105d7f  xor     r12d, r12d
0x180105d82  xor     eax, eax
0x180105d84  mov     qword ptr [rbp+pvValue+10h], rax
0x180105d88  xorps   xmm0, xmm0
0x180105d8b  mov     [rbp+arg_18], r12
0x180105d8f  mov     r13, 7FFFFFFFFFFFFFFFh
0x180105d99  mov     [rbp+arg_10], r13
0x180105d9d  mov     [rbp+arg_8], r12d
0x180105da1  lea     eax, [r12+0Dh]
0x180105da6  movups  xmmword ptr [rbp+pvValue], xmm0
0x180105daa  mov     word ptr [rbp+pvValue], ax
0x180105dae  mov     qword ptr [rbp+pvValue+8], r14
0x180105db2  test    r14, r14
0x180105db5  jz      short loc_180105DC6
0x180105db7  mov     rax, [r14]
0x180105dba  mov     rcx, r14
0x180105dbd  mov     rax, [rax+8]
0x180105dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105dc6  lea     r15, [rbx+90h]
0x180105dcd  mov     rcx, r15; lpCriticalSection
0x180105dd0  call    cs:__imp_EnterCriticalSection
0x180105dd6  cmp     [rbx+0C0h], r12d
0x180105ddd  jz      loc_180105E78
0x180105de3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180105dea  mov     edi, 0C00D3E85h
0x180105def  test    rcx, rcx
0x180105df2  jnz     short loc_180105E35
0x180105df4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180105dfa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180105e01  mov     rcx, rax
0x180105e04  test    rax, rax
0x180105e07  jz      short loc_180105E27
0x180105e09  mov     rax, [rax]
0x180105e0c  mov     edx, 7F0h
0x180105e11  mov     rax, [rax+8]
0x180105e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105e1a  test    eax, eax
0x180105e1c  jz      short loc_180105E27
0x180105e1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180105e25  jmp     short loc_180105E35
0x180105e27  lea     rcx, qword_1801B07E0; this
0x180105e2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180105e35  cmp     [rcx+8], r12b
0x180105e39  jz      short loc_180105E5C
0x180105e3b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180105e40  cmp     [rax+7CCh], edi
0x180105e46  jz      short loc_180105E5C
0x180105e48  mov     r9d, edi; int
0x180105e4b  mov     r8d, 692h; int
0x180105e51  mov     rdx, rsi; char *
0x180105e54  mov     rcx, rax; this
0x180105e57  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180105e5c  mov     esi, 1
0x180105e61  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180105e68  jb      loc_180106504
0x180105e6e  mov     edx, 99h
0x180105e73  jmp     loc_1801064E6
0x180105e78  test    r14, r14
0x180105e7b  jnz     loc_180105F16
0x180105e81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180105e88  mov     edi, 80004003h
0x180105e8d  test    rcx, rcx
0x180105e90  jnz     short loc_180105ED3
0x180105e92  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180105e98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180105e9f  mov     rcx, rax
0x180105ea2  test    rax, rax
0x180105ea5  jz      short loc_180105EC5
0x180105ea7  mov     rax, [rax]
0x180105eaa  mov     edx, 7F0h
0x180105eaf  mov     rax, [rax+8]
0x180105eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105eb8  test    eax, eax
0x180105eba  jz      short loc_180105EC5
0x180105ebc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180105ec3  jmp     short loc_180105ED3
0x180105ec5  lea     rcx, qword_1801B07E0; this
0x180105ecc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180105ed3  cmp     [rcx+8], r12b
0x180105ed7  jz      short loc_180105EFA
0x180105ed9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180105ede  cmp     [rax+7CCh], edi
0x180105ee4  jz      short loc_180105EFA
0x180105ee6  mov     r9d, edi; int
0x180105ee9  mov     r8d, 697h; int
0x180105eef  mov     rdx, rsi; char *
0x180105ef2  mov     rcx, rax; this
0x180105ef5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180105efa  mov     esi, 1
0x180105eff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180105f06  jb      loc_180106504
0x180105f0c  mov     edx, 9Ah
0x180105f11  jmp     loc_1801064E6
0x180105f16  mov     rdx, r14; struct IMFSample *
0x180105f19  mov     rcx, rbx; this
0x180105f1c  call    ?AdjustSampleTime@CMFMediaStream@@IEAAXPEAUIMFSample@@@Z; CMFMediaStream::AdjustSampleTime(IMFSample *)
0x180105f21  lea     rax, [rbp+arg_18]
0x180105f25  xor     r8d, r8d; hrStatus
0x180105f28  lea     r9, [rbp+pvValue]; pvValue
0x180105f2c  mov     [rsp+68h+ppEvent], rax; ppEvent
0x180105f31  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x180105f38  mov     ecx, 0D5h; met
0x180105f3d  call    cs:__imp_MFCreateMediaEvent
0x180105f43  mov     edi, eax
0x180105f45  test    eax, eax
0x180105f47  jns     loc_180105FDD
0x180105f4d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180105f54  test    rcx, rcx
0x180105f57  jnz     short loc_180105F9A
0x180105f59  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180105f5f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180105f66  mov     rcx, rax
0x180105f69  test    rax, rax
0x180105f6c  jz      short loc_180105F8C
0x180105f6e  mov     rax, [rax]
0x180105f71  mov     edx, 7F0h
0x180105f76  mov     rax, [rax+8]
0x180105f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105f7f  test    eax, eax
0x180105f81  jz      short loc_180105F8C
0x180105f83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180105f8a  jmp     short loc_180105F9A
0x180105f8c  lea     rcx, qword_1801B07E0; this
0x180105f93  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180105f9a  cmp     [rcx+8], r12b
0x180105f9e  jz      short loc_180105FC1
0x180105fa0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180105fa5  cmp     [rax+7CCh], edi
0x180105fab  jz      short loc_180105FC1
0x180105fad  mov     r9d, edi; int
0x180105fb0  mov     r8d, 69Bh; int
0x180105fb6  mov     rdx, rsi; char *
0x180105fb9  mov     rcx, rax; this
0x180105fbc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180105fc1  mov     esi, 1
0x180105fc6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180105fcd  jb      loc_180106504
0x180105fd3  mov     edx, 9Bh
0x180105fd8  jmp     loc_1801064E6
0x180105fdd  mov     rdx, [rbp+arg_18]; struct IMFMediaEvent *
0x180105fe1  lea     rcx, [rbx+378h]; this
0x180105fe8  mov     [rbp+arg_18], r12
0x180105fec  call    ?Add@CStreamEventQueue@@QEAAPEAXPEAUIMFMediaEvent@@@Z; CStreamEventQueue::Add(IMFMediaEvent *)
0x180105ff1  test    rax, rax
0x180105ff4  jnz     loc_18010608F
0x180105ffa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180106001  mov     edi, 8007000Eh
0x180106006  test    rcx, rcx
0x180106009  jnz     short loc_18010604C
0x18010600b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180106011  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180106018  mov     rcx, rax
0x18010601b  test    rax, rax
0x18010601e  jz      short loc_18010603E
0x180106020  mov     rax, [rax]
0x180106023  mov     edx, 7F0h
0x180106028  mov     rax, [rax+8]
0x18010602c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106031  test    eax, eax
0x180106033  jz      short loc_18010603E
0x180106035  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010603c  jmp     short loc_18010604C
0x18010603e  lea     rcx, qword_1801B07E0; this
0x180106045  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010604c  cmp     [rcx+8], r12b
0x180106050  jz      short loc_180106073
0x180106052  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180106057  cmp     [rax+7CCh], edi
0x18010605d  jz      short loc_180106073
0x18010605f  mov     r9d, edi; int
0x180106062  mov     r8d, 69Dh; int
0x180106068  mov     rdx, rsi; char *
0x18010606b  mov     rcx, rax; this
0x18010606e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180106073  mov     esi, 1
0x180106078  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18010607f  jb      loc_180106504
0x180106085  mov     edx, 9Ch
0x18010608a  jmp     loc_1801064E6
0x18010608f  mov     rcx, [rbx+190h]
0x180106096  mov     r8b, 3
0x180106099  mov     rdx, r14
0x18010609c  mov     rax, [rcx]
0x18010609f  mov     rax, [rax+40h]
0x1801060a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801060a8  mov     rax, [r14]
0x1801060ab  lea     r8, [rbp+arg_8]
0x1801060af  lea     rdx, MFSampleExtension_CleanPoint
0x1801060b6  mov     rcx, r14
0x1801060b9  mov     rax, [rax+38h]
0x1801060bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801060c2  mov     esi, 1
0x1801060c7  test    eax, eax
0x1801060c9  js      short loc_18010610C
0x1801060cb  cmp     [rbp+arg_8], r12d
0x1801060cf  jz      short loc_18010610C
0x1801060d1  add     [rbx+548h], esi
0x1801060d7  mov     eax, [rbx+548h]
0x1801060dd  cmp     cs:byte_1801B110B, 8
0x1801060e4  jb      short loc_18010610C
0x1801060e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801060ed  lea     r8, WPP_fc8c5d8c44273bdd34ec62b5fce42adb_Traceguids
0x1801060f4  mov     edx, 9Dh
0x1801060f9  mov     dword ptr [rsp+68h+ppEvent], eax
0x1801060fd  mov     r9, rbx
0x180106100  mov     rcx, [rcx+88h]
0x180106107  call    WPP_SF_qD
0x18010610c  mov     rax, [r14]
0x18010610f  lea     rdx, [rbp+arg_10]
0x180106113  mov     rcx, r14
0x180106116  mov     rax, [rax+118h]
0x18010611d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106122  mov     rax, [rbp+arg_10]
0x180106126  mov     [rbx+0E0h], rax
0x18010612d  cmp     cs:byte_1801B110B, 10h
0x180106134  jb      short loc_180106167
0x180106136  mov     rcx, cs:WPP_GLOBAL_Control
0x18010613d  lea     r8, WPP_fc8c5d8c44273bdd34ec62b5fce42adb_Traceguids
0x180106144  mov     [rsp+68h+var_40], rax
0x180106149  mov     edx, 9Eh
0x18010614e  mov     eax, [rbx+1B0h]
0x180106154  mov     r9, rbx
0x180106157  mov     dword ptr [rsp+68h+ppEvent], eax
0x18010615b  mov     rcx, [rcx+88h]
0x180106162  call    WPP_SF_qdi
0x180106167  mov     rcx, [rbx+190h]
0x18010616e  mov     rax, [rcx]
0x180106171  mov     rax, [rax+38h]
0x180106175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010617a  test    eax, eax
0x18010617c  jz      loc_18010623B
0x180106182  mov     rax, [r14]
0x180106185  lea     rdx, [rbp+arg_0]
0x180106189  mov     rcx, r14
0x18010618c  mov     [rbp+arg_0], r12d
0x180106190  mov     rax, [rax+168h]
0x180106197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010619c  mov     edi, eax
0x18010619e  test    eax, eax
0x1801061a0  jns     loc_180106235
0x1801061a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801061ad  test    rcx, rcx
0x1801061b0  jnz     short loc_1801061F3
0x1801061b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801061b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801061bf  mov     rcx, rax
0x1801061c2  test    rax, rax
0x1801061c5  jz      short loc_1801061E5
0x1801061c7  mov     rax, [rax]
0x1801061ca  mov     edx, 7F0h
0x1801061cf  mov     rax, [rax+8]
0x1801061d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801061d8  test    eax, eax
0x1801061da  jz      short loc_1801061E5
0x1801061dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801061e3  jmp     short loc_1801061F3
0x1801061e5  lea     rcx, qword_1801B07E0; this
0x1801061ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801061f3  cmp     [rcx+8], r12b
0x1801061f7  jz      short loc_18010621E
0x1801061f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801061fe  cmp     [rax+7CCh], edi
0x180106204  jz      short loc_18010621E
0x180106206  mov     r9d, edi; int
0x180106209  lea     rdx, aCmfmediastream_16; "CMFMediaStream::NewSample"
0x180106210  mov     r8d, 6B2h; int
0x180106216  mov     rcx, rax; this
0x180106219  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010621e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180106225  jb      loc_180106504
0x18010622b  mov     edx, 9Fh
0x180106230  jmp     loc_1801064E6
0x180106235  mov     eax, [rbp+arg_0]
0x180106238  add     [rbx+30h], eax
0x18010623b  cmp     [rbx+0D0h], r12d
0x180106242  jz      short loc_180106256
0x180106244  mov     rax, [rbp+arg_10]
0x180106248  mov     [rbx+0D8h], rax
0x18010624f  mov     [rbx+0D0h], r12d
0x180106256  mov     rcx, [rbx+190h]
0x18010625d  mov     rax, [rcx]
0x180106260  mov     rax, [rax+38h]
0x180106264  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
