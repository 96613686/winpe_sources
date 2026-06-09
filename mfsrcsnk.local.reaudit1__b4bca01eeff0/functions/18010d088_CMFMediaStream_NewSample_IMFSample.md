# CMFMediaStream::NewSample(IMFSample *)

- ea: `0x18010d088`
- end: `0x18010d8b5`
- name: `?NewSample@CMFMediaStream@@QEAAJPEAUIMFSample@@@Z`
- size: `2093`
- prototype: `__int64 __fastcall(CMFMediaStream *__hidden this, struct IMFSample *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800382c0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180039b04`
- `0x18003bd18`
- `0x180079680`
- `0x18010d088`
- `0x180140204`
- `0x180151658`
- `0x180153604`
- `0x180153694`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010d883`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010d883`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010d10c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010d10c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010d136`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010d1da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010d2ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010d365`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010d512`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010d7d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010d136`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010d1da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010d2ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010d365`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010d512`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18010d7d2`
- `MFPlat!MFCreateMediaEvent` at `0x18010d28b`
- `MFPlat!MFCreateMediaEvent` at `0x18010d28b`
- `MFPlat!DestroyPropVariant` at `0x18010d874`
- `MFPlat!DestroyPropVariant` at `0x18010d874`

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
        v5 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v14 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v20 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        if ( (unsigned __int8)byte_1801BA10B >= 8u )
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
    if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
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
            v26 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v39 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          if ( (unsigned __int8)byte_1801BA10B >= 8u )
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
          if ( (unsigned __int8)byte_1801BA10B >= 8u )
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
      v10 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x18010d088  push    rbp
0x18010d08a  push    rbx
0x18010d08b  push    rsi
0x18010d08c  push    rdi
0x18010d08d  push    r12
0x18010d08f  push    r13
0x18010d091  push    r14
0x18010d093  push    r15
0x18010d095  mov     rbp, rsp
0x18010d098  sub     rsp, 68h
0x18010d09c  mov     r14, rdx
0x18010d09f  lea     rsi, aCmfmediastream_16; "CMFMediaStream::NewSample"
0x18010d0a6  mov     rbx, rcx
0x18010d0a9  mov     rdx, rsi; char *
0x18010d0ac  mov     r8d, 683h; int
0x18010d0b2  lea     rcx, [rbp+arg_0]; this
0x18010d0b6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18010d0bb  xor     r12d, r12d
0x18010d0be  xor     eax, eax
0x18010d0c0  mov     qword ptr [rbp+pvValue+10h], rax
0x18010d0c4  xorps   xmm0, xmm0
0x18010d0c7  mov     [rbp+arg_18], r12
0x18010d0cb  mov     r13, 7FFFFFFFFFFFFFFFh
0x18010d0d5  mov     [rbp+arg_10], r13
0x18010d0d9  mov     [rbp+arg_8], r12d
0x18010d0dd  lea     eax, [r12+0Dh]
0x18010d0e2  movups  xmmword ptr [rbp+pvValue], xmm0
0x18010d0e6  mov     word ptr [rbp+pvValue], ax
0x18010d0ea  mov     qword ptr [rbp+pvValue+8], r14
0x18010d0ee  test    r14, r14
0x18010d0f1  jz      short loc_18010D102
0x18010d0f3  mov     rax, [r14]
0x18010d0f6  mov     rcx, r14
0x18010d0f9  mov     rax, [rax+8]
0x18010d0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d102  lea     r15, [rbx+90h]
0x18010d109  mov     rcx, r15; lpCriticalSection
0x18010d10c  call    cs:__imp_EnterCriticalSection
0x18010d113  nop     dword ptr [rax+rax+00h]
0x18010d118  cmp     [rbx+0C0h], r12d
0x18010d11f  jz      loc_18010D1C0
0x18010d125  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d12c  mov     edi, 0C00D3E85h
0x18010d131  test    rcx, rcx
0x18010d134  jnz     short loc_18010D17D
0x18010d136  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18010d13d  nop     dword ptr [rax+rax+00h]
0x18010d142  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d149  mov     rcx, rax
0x18010d14c  test    rax, rax
0x18010d14f  jz      short loc_18010D16F
0x18010d151  mov     rax, [rax]
0x18010d154  mov     edx, 7F0h
0x18010d159  mov     rax, [rax+8]
0x18010d15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d162  test    eax, eax
0x18010d164  jz      short loc_18010D16F
0x18010d166  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d16d  jmp     short loc_18010D17D
0x18010d16f  lea     rcx, qword_1801B97E0; this
0x18010d176  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d17d  cmp     [rcx+8], r12b
0x18010d181  jz      short loc_18010D1A4
0x18010d183  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010d188  cmp     [rax+7CCh], edi
0x18010d18e  jz      short loc_18010D1A4
0x18010d190  mov     r9d, edi; int
0x18010d193  mov     r8d, 692h; int
0x18010d199  mov     rdx, rsi; char *
0x18010d19c  mov     rcx, rax; this
0x18010d19f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010d1a4  mov     esi, 1
0x18010d1a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18010d1b0  jb      loc_18010D870
0x18010d1b6  mov     edx, 99h
0x18010d1bb  jmp     loc_18010D852
0x18010d1c0  test    r14, r14
0x18010d1c3  jnz     loc_18010D264
0x18010d1c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d1d0  mov     edi, 80004003h
0x18010d1d5  test    rcx, rcx
0x18010d1d8  jnz     short loc_18010D221
0x18010d1da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18010d1e1  nop     dword ptr [rax+rax+00h]
0x18010d1e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d1ed  mov     rcx, rax
0x18010d1f0  test    rax, rax
0x18010d1f3  jz      short loc_18010D213
0x18010d1f5  mov     rax, [rax]
0x18010d1f8  mov     edx, 7F0h
0x18010d1fd  mov     rax, [rax+8]
0x18010d201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d206  test    eax, eax
0x18010d208  jz      short loc_18010D213
0x18010d20a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d211  jmp     short loc_18010D221
0x18010d213  lea     rcx, qword_1801B97E0; this
0x18010d21a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d221  cmp     [rcx+8], r12b
0x18010d225  jz      short loc_18010D248
0x18010d227  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010d22c  cmp     [rax+7CCh], edi
0x18010d232  jz      short loc_18010D248
0x18010d234  mov     r9d, edi; int
0x18010d237  mov     r8d, 697h; int
0x18010d23d  mov     rdx, rsi; char *
0x18010d240  mov     rcx, rax; this
0x18010d243  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010d248  mov     esi, 1
0x18010d24d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18010d254  jb      loc_18010D870
0x18010d25a  mov     edx, 9Ah
0x18010d25f  jmp     loc_18010D852
0x18010d264  mov     rdx, r14; struct IMFSample *
0x18010d267  mov     rcx, rbx; this
0x18010d26a  call    ?AdjustSampleTime@CMFMediaStream@@IEAAXPEAUIMFSample@@@Z; CMFMediaStream::AdjustSampleTime(IMFSample *)
0x18010d26f  lea     rax, [rbp+arg_18]
0x18010d273  xor     r8d, r8d; hrStatus
0x18010d276  lea     r9, [rbp+pvValue]; pvValue
0x18010d27a  mov     [rsp+68h+ppEvent], rax; ppEvent
0x18010d27f  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x18010d286  mov     ecx, 0D5h; met
0x18010d28b  call    cs:__imp_MFCreateMediaEvent
0x18010d292  nop     dword ptr [rax+rax+00h]
0x18010d297  mov     edi, eax
0x18010d299  test    eax, eax
0x18010d29b  jns     loc_18010D337
0x18010d2a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d2a8  test    rcx, rcx
0x18010d2ab  jnz     short loc_18010D2F4
0x18010d2ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18010d2b4  nop     dword ptr [rax+rax+00h]
0x18010d2b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d2c0  mov     rcx, rax
0x18010d2c3  test    rax, rax
0x18010d2c6  jz      short loc_18010D2E6
0x18010d2c8  mov     rax, [rax]
0x18010d2cb  mov     edx, 7F0h
0x18010d2d0  mov     rax, [rax+8]
0x18010d2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d2d9  test    eax, eax
0x18010d2db  jz      short loc_18010D2E6
0x18010d2dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d2e4  jmp     short loc_18010D2F4
0x18010d2e6  lea     rcx, qword_1801B97E0; this
0x18010d2ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d2f4  cmp     [rcx+8], r12b
0x18010d2f8  jz      short loc_18010D31B
0x18010d2fa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010d2ff  cmp     [rax+7CCh], edi
0x18010d305  jz      short loc_18010D31B
0x18010d307  mov     r9d, edi; int
0x18010d30a  mov     r8d, 69Bh; int
0x18010d310  mov     rdx, rsi; char *
0x18010d313  mov     rcx, rax; this
0x18010d316  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010d31b  mov     esi, 1
0x18010d320  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18010d327  jb      loc_18010D870
0x18010d32d  mov     edx, 9Bh
0x18010d332  jmp     loc_18010D852
0x18010d337  mov     rdx, [rbp+arg_18]; struct IMFMediaEvent *
0x18010d33b  lea     rcx, [rbx+378h]; this
0x18010d342  mov     [rbp+arg_18], r12
0x18010d346  call    ?Add@CStreamEventQueue@@QEAAPEAXPEAUIMFMediaEvent@@@Z; CStreamEventQueue::Add(IMFMediaEvent *)
0x18010d34b  test    rax, rax
0x18010d34e  jnz     loc_18010D3EF
0x18010d354  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d35b  mov     edi, 8007000Eh
0x18010d360  test    rcx, rcx
0x18010d363  jnz     short loc_18010D3AC
0x18010d365  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18010d36c  nop     dword ptr [rax+rax+00h]
0x18010d371  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d378  mov     rcx, rax
0x18010d37b  test    rax, rax
0x18010d37e  jz      short loc_18010D39E
0x18010d380  mov     rax, [rax]
0x18010d383  mov     edx, 7F0h
0x18010d388  mov     rax, [rax+8]
0x18010d38c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d391  test    eax, eax
0x18010d393  jz      short loc_18010D39E
0x18010d395  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d39c  jmp     short loc_18010D3AC
0x18010d39e  lea     rcx, qword_1801B97E0; this
0x18010d3a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d3ac  cmp     [rcx+8], r12b
0x18010d3b0  jz      short loc_18010D3D3
0x18010d3b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010d3b7  cmp     [rax+7CCh], edi
0x18010d3bd  jz      short loc_18010D3D3
0x18010d3bf  mov     r9d, edi; int
0x18010d3c2  mov     r8d, 69Dh; int
0x18010d3c8  mov     rdx, rsi; char *
0x18010d3cb  mov     rcx, rax; this
0x18010d3ce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010d3d3  mov     esi, 1
0x18010d3d8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18010d3df  jb      loc_18010D870
0x18010d3e5  mov     edx, 9Ch
0x18010d3ea  jmp     loc_18010D852
0x18010d3ef  mov     rcx, [rbx+190h]
0x18010d3f6  mov     r8b, 3
0x18010d3f9  mov     rdx, r14
0x18010d3fc  mov     rax, [rcx]
0x18010d3ff  mov     rax, [rax+40h]
0x18010d403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d408  mov     rax, [r14]
0x18010d40b  lea     r8, [rbp+arg_8]
0x18010d40f  lea     rdx, MFSampleExtension_CleanPoint
0x18010d416  mov     rcx, r14
0x18010d419  mov     rax, [rax+38h]
0x18010d41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d422  mov     esi, 1
0x18010d427  test    eax, eax
0x18010d429  js      short loc_18010D46C
0x18010d42b  cmp     [rbp+arg_8], r12d
0x18010d42f  jz      short loc_18010D46C
0x18010d431  add     [rbx+548h], esi
0x18010d437  mov     eax, [rbx+548h]
0x18010d43d  cmp     cs:byte_1801BA10B, 8
0x18010d444  jb      short loc_18010D46C
0x18010d446  mov     rcx, cs:WPP_GLOBAL_Control
0x18010d44d  lea     r8, WPP_fc8c5d8c44273bdd34ec62b5fce42adb_Traceguids
0x18010d454  mov     edx, 9Dh
0x18010d459  mov     dword ptr [rsp+68h+ppEvent], eax
0x18010d45d  mov     r9, rbx
0x18010d460  mov     rcx, [rcx+88h]
0x18010d467  call    WPP_SF_qD
0x18010d46c  mov     rax, [r14]
0x18010d46f  lea     rdx, [rbp+arg_10]
0x18010d473  mov     rcx, r14
0x18010d476  mov     rax, [rax+118h]
0x18010d47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d482  mov     rax, [rbp+arg_10]
0x18010d486  mov     [rbx+0E0h], rax
0x18010d48d  cmp     cs:byte_1801BA10B, 10h
0x18010d494  jb      short loc_18010D4C7
0x18010d496  mov     rcx, cs:WPP_GLOBAL_Control
0x18010d49d  lea     r8, WPP_fc8c5d8c44273bdd34ec62b5fce42adb_Traceguids
0x18010d4a4  mov     [rsp+68h+var_40], rax
0x18010d4a9  mov     edx, 9Eh
0x18010d4ae  mov     eax, [rbx+1B0h]
0x18010d4b4  mov     r9, rbx
0x18010d4b7  mov     dword ptr [rsp+68h+ppEvent], eax
0x18010d4bb  mov     rcx, [rcx+88h]
0x18010d4c2  call    WPP_SF_qdi
0x18010d4c7  mov     rcx, [rbx+190h]
0x18010d4ce  mov     rax, [rcx]
0x18010d4d1  mov     rax, [rax+38h]
0x18010d4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d4da  test    eax, eax
0x18010d4dc  jz      loc_18010D5A1
0x18010d4e2  mov     rax, [r14]
0x18010d4e5  lea     rdx, [rbp+arg_0]
0x18010d4e9  mov     rcx, r14
0x18010d4ec  mov     [rbp+arg_0], r12d
0x18010d4f0  mov     rax, [rax+168h]
0x18010d4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d4fc  mov     edi, eax
0x18010d4fe  test    eax, eax
0x18010d500  jns     loc_18010D59B
0x18010d506  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d50d  test    rcx, rcx
0x18010d510  jnz     short loc_18010D559
0x18010d512  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18010d519  nop     dword ptr [rax+rax+00h]
0x18010d51e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d525  mov     rcx, rax
0x18010d528  test    rax, rax
0x18010d52b  jz      short loc_18010D54B
0x18010d52d  mov     rax, [rax]
0x18010d530  mov     edx, 7F0h
0x18010d535  mov     rax, [rax+8]
0x18010d539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d53e  test    eax, eax
0x18010d540  jz      short loc_18010D54B
0x18010d542  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d549  jmp     short loc_18010D559
0x18010d54b  lea     rcx, qword_1801B97E0; this
0x18010d552  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010d559  cmp     [rcx+8], r12b
0x18010d55d  jz      short loc_18010D584
0x18010d55f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010d564  cmp     [rax+7CCh], edi
0x18010d56a  jz      short loc_18010D584
0x18010d56c  mov     r9d, edi; int
0x18010d56f  lea     rdx, aCmfmediastream_16; "CMFMediaStream::NewSample"
0x18010d576  mov     r8d, 6B2h; int
0x18010d57c  mov     rcx, rax; this
0x18010d57f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010d584  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18010d58b  jb      loc_18010D870
0x18010d591  mov     edx, 9Fh
0x18010d596  jmp     loc_18010D852
0x18010d59b  mov     eax, [rbp+arg_0]
0x18010d59e  add     [rbx+30h], eax
0x18010d5a1  cmp     [rbx+0D0h], r12d
0x18010d5a8  jz      short loc_18010D5BC
  ... truncated ...
```
