# CDSSampleSinkInputPin::ReceiveConnection(IPin *,_AMMediaType const *)

- ea: `0x18000eb90`
- end: `0x18000f2d3`
- name: `?ReceiveConnection@CDSSampleSinkInputPin@@UEAAJPEAUIPin@@PEBU_AMMediaType@@@Z`
- size: `1859`
- prototype: `__int64 __fastcall(CDSSampleSinkInputPin *__hidden this, struct IPin *, const struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x18000e584`
- `0x18000eb90`
- `0x18000f2e0`
- `0x18000f6a8`
- `0x180010350`
- `0x1800140b0`
- `0x1800227e0`
- `0x18002329c`
- `0x180023af8`
- `0x1800242e0`
- `0x1800320b0`
- `0x180032a50`
- `0x18004b498`
- `0x18004bba8`
- `0x18004c0d0`
- `0x180051ce4`
- `0x180071dbc`
- `0x180074160`
- `0x18007c8e8`
- `0x18007ead0`
- `0x180083500`
- `0x1800c4a68`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f293`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f293`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ebe8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ebe8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f278`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f278`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ec85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ed36`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ede9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ee91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ef50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000effe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ec85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ed36`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ede9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ee91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ef50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000effe`

## pseudocode

```c
__int64 __fastcall CDSSampleSinkInputPin::ReceiveConnection(
        CDSSampleSinkInputPin *this,
        struct IPin *a2,
        const struct _AMMediaType *a3)
{
  CDSSampleSinkInputPin *v6; // rsi
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  struct _GUID *v8; // r9
  int v9; // edi
  CallStackTracing *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  CallStackTracing *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  _QWORD *v23; // rcx
  CallStackTracing *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  CallStackTracing *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IPinVtbl *lpVtbl; // rax
  int *v31; // r8
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  _BYTE v35[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v36; // [rsp+34h] [rbp-CCh] BYREF
  struct _AMMediaType *pv; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v38; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v39; // [rsp+48h] [rbp-B8h] BYREF
  IPin v40[2]; // [rsp+58h] [rbp-A8h] BYREF
  _AMMediaType v41; // [rsp+70h] [rbp-90h] BYREF
  __int128 v42; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID v43; // [rsp+E0h] [rbp-20h] BYREF
  struct _AMMediaType v44; // [rsp+F0h] [rbp-10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v35, "CDSSampleSinkInputPin::ReceiveConnection", 1187);
  v6 = (CDSSampleSinkInputPin *)((char *)this - 24);
  v7 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 5);
  EnterCriticalSection(v7);
  CopyMediaType(&v41, a3);
  *(_OWORD *)&v40[0].lpVtbl = 0;
  v43 = 0;
  v39 = 0;
  v42 = 0;
  if ( *((struct IPin **)this + 3) == a2 && a2 )
  {
    if ( (unsigned __int8)byte_1800EACCB >= 8u )
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 17), 103, &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids, v6, a2);
    v9 = CDSSampleSinkInputPin::CheckMediaType(v6, (const struct CMediaType *)&v41);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD *))(**((_QWORD **)v6 + 28) + 48LL))(*((_QWORD **)v6 + 28));
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *))(**((_QWORD **)v6 + 28) + 32LL))(
               *((_QWORD **)v6 + 28),
               &v39);
        if ( v9 >= 0 )
        {
          v9 = CDSSampleSinkInputPin::SetMediaType(v6, &v41);
          if ( v9 >= 0 )
          {
            v23 = (_QWORD *)*((_QWORD *)v6 + 28);
            DWORD1(v39) = a3->lSampleSize;
            v9 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int128 *))(*v23 + 24LL))(v23, &v39, &v42);
            if ( v9 >= 0 )
            {
              v9 = (*(__int64 (__fastcall **)(_QWORD *))(**((_QWORD **)v6 + 28) + 40LL))(*((_QWORD **)v6 + 28));
              if ( v9 < 0 )
              {
                v27 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                  CallStackTracing::s_wpInstance = v28;
                  if ( v28
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
                  {
                    v27 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v27 = (CallStackTracing *)&qword_1800EB130;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                  }
                }
                if ( *((_BYTE *)v27 + 8) )
                {
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v27);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
                    CallStackContext::TraceFailure(
                      ThreadRelativeContext,
                      "CDSSampleSinkInputPin::ReceiveConnection",
                      1223,
                      v9);
                }
                if ( g_wppLevels )
                {
                  v13 = 109;
                  goto LABEL_96;
                }
              }
            }
            else
            {
              v24 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                CallStackTracing::s_wpInstance = v25;
                if ( v25
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
                {
                  v24 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v24 = (CallStackTracing *)&qword_1800EB130;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                }
              }
              if ( *((_BYTE *)v24 + 8) )
              {
                v26 = CallStackTracing::GetThreadRelativeContext(v24);
                if ( *((_DWORD *)v26 + 499) != v9 )
                  CallStackContext::TraceFailure(v26, "CDSSampleSinkInputPin::ReceiveConnection", 1221, v9);
              }
              if ( g_wppLevels )
              {
                v13 = 108;
                goto LABEL_96;
              }
            }
          }
          else
          {
            v20 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v21;
              if ( v21
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
              {
                v20 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v20 = (CallStackTracing *)&qword_1800EB130;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
              }
            }
            if ( *((_BYTE *)v20 + 8) )
            {
              v22 = CallStackTracing::GetThreadRelativeContext(v20);
              if ( *((_DWORD *)v22 + 499) != v9 )
                CallStackContext::TraceFailure(v22, "CDSSampleSinkInputPin::ReceiveConnection", 1218, v9);
            }
            if ( g_wppLevels )
            {
              v13 = 107;
              goto LABEL_96;
            }
          }
        }
        else
        {
          v17 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v18;
            if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
            {
              v17 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v17 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v17 + 8) )
          {
            v19 = CallStackTracing::GetThreadRelativeContext(v17);
            if ( *((_DWORD *)v19 + 499) != v9 )
              CallStackContext::TraceFailure(v19, "CDSSampleSinkInputPin::ReceiveConnection", 1209, v9);
          }
          if ( g_wppLevels )
          {
            v13 = 106;
            goto LABEL_96;
          }
        }
      }
      else
      {
        v14 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          v16 = CallStackTracing::GetThreadRelativeContext(v14);
          if ( *((_DWORD *)v16 + 499) != v9 )
            CallStackContext::TraceFailure(v16, "CDSSampleSinkInputPin::ReceiveConnection", 1207, v9);
        }
        if ( g_wppLevels )
        {
          v13 = 105;
          goto LABEL_96;
        }
      }
    }
    else
    {
      v10 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext(v10);
        if ( *((_DWORD *)v12 + 499) != v9 )
          CallStackContext::TraceFailure(v12, "CDSSampleSinkInputPin::ReceiveConnection", 1202, v9);
      }
      if ( g_wppLevels )
      {
        v13 = 104;
LABEL_96:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids, v6, v9);
      }
    }
  }
  else
  {
    if ( (unsigned int)(*((_DWORD *)this + 78) - 2) <= 2 )
    {
      MFDSUtils::GetAMediaType((MFDSUtils *)a2, v40, &v43, v8);
      if ( (unsigned __int8)_(v40, (char *)this + 316) )
      {
        if ( (unsigned int)CDSSampleSinkInputPin::IsAcceptableVideoType(
                             (CDSSampleSinkInputPin *)((char *)this - 24),
                             (const struct CMediaType *)&v41) )
        {
          lpVtbl = a2->lpVtbl;
          v38 = 0;
          if ( ((int (__fastcall *)(struct IPin *, __int64 *))lpVtbl->EnumMediaTypes)(a2, &v38) >= 0 )
          {
            pv = 0;
            v36 = 0;
            while ( !(*(unsigned int (__fastcall **)(__int64, __int64, struct _AMMediaType **, int *))(*(_QWORD *)v38 + 24LL))(
                       v38,
                       1,
                       &pv,
                       &v36) )
            {
              CMediaType::CMediaType((CMediaType *)&v44, pv, v31);
              if ( (unsigned int)CMediaType::operator!=(&v44, &v41)
                && (unsigned int)CDSSampleSinkInputPin::IsAcceptableVideoType(
                                   (CDSSampleSinkInputPin *)((char *)this - 24),
                                   (const struct CMediaType *)&v44)
                && !(unsigned int)CDSSampleSinkInputPin::FindDSMediaType(
                                    (CDSSampleSinkInputPin *)((char *)this - 24),
                                    (struct CMediaType *)&v44)
                && !((unsigned int (__fastcall *)(struct IPin *, struct _AMMediaType *))a2->lpVtbl->QueryAccept)(
                      a2,
                      &v44) )
              {
                CDSSampleSinkInputPin::AddMediaTypePair((CDSSampleSinkInputPin *)((char *)this - 24), &v44, 0);
              }
              DeleteMediaType(pv);
              FreeMediaType(&v44);
            }
          }
          ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v38);
        }
        if ( (!*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 36) + 24LL) + 472LL)
           || (unsigned int)CDSSampleSinkInputPin::IsAcceptedDVDUncompressedType((const struct CMediaType *)&v41))
          && !(unsigned int)CDSSampleSinkInputPin::FindDSMediaType(
                              (CDSSampleSinkInputPin *)((char *)this - 24),
                              (struct CMediaType *)&v41) )
        {
          CDSSampleSinkInputPin::AddMediaTypePair((CDSSampleSinkInputPin *)((char *)this - 24), &v41, 0);
        }
      }
    }
    v9 = CBasePin::ReceiveConnection(this, a2, a3);
    if ( v9 < 0 )
    {
      v32 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v32 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext(v32);
        if ( *((_DWORD *)v33 + 499) != v9 )
          CallStackContext::TraceFailure(v33, "CDSSampleSinkInputPin::ReceiveConnection", 1282, v9);
      }
      if ( g_wppLevels )
      {
        v13 = 110;
        goto LABEL_96;
      }
    }
  }
  if ( v41.cbFormat )
  {
    CoTaskMemFree(v41.pbFormat);
    v41.cbFormat = 0;
    v41.pbFormat = 0;
  }
  v41.pUnk = 0;
  LeaveCriticalSection(v7);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v35);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000eb90  mov     [rsp-8+arg_18], rbx
0x18000eb95  push    rbp
0x18000eb96  push    rsi
0x18000eb97  push    rdi
0x18000eb98  push    r12
0x18000eb9a  push    r13
0x18000eb9c  push    r14
0x18000eb9e  push    r15
0x18000eba0  lea     rbp, [rsp-60h]
0x18000eba5  sub     rsp, 160h
0x18000ebac  mov     rax, cs:__security_cookie
0x18000ebb3  xor     rax, rsp
0x18000ebb6  mov     [rbp+90h+var_40], rax
0x18000ebba  mov     r15, r8
0x18000ebbd  lea     r13, aCdssamplesinki_4; "CDSSampleSinkInputPin::ReceiveConnectio"...
0x18000ebc4  mov     rdi, rdx
0x18000ebc7  mov     r14, rcx
0x18000ebca  mov     rdx, r13; char *
0x18000ebcd  lea     rcx, [rsp+190h+var_160]; this
0x18000ebd2  mov     r8d, 4A3h; int
0x18000ebd8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000ebdd  lea     rsi, [r14-18h]
0x18000ebe1  mov     rbx, [rsi+40h]
0x18000ebe5  mov     rcx, rbx; lpCriticalSection
0x18000ebe8  call    cs:__imp_EnterCriticalSection
0x18000ebef  nop     dword ptr [rax+rax+00h]
0x18000ebf4  mov     rdx, r15; struct _AMMediaType *
0x18000ebf7  lea     rcx, [rsp+190h+var_120]; struct _AMMediaType *
0x18000ebfc  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x18000ec01  xorps   xmm0, xmm0
0x18000ec04  xorps   xmm1, xmm1
0x18000ec07  xor     r12d, r12d
0x18000ec0a  movups  xmmword ptr [rsp+190h+var_138.lpVtbl], xmm0
0x18000ec0f  movups  xmmword ptr [rbp+90h+var_B0.Data1], xmm1
0x18000ec13  movups  [rsp+190h+var_148], xmm0
0x18000ec18  movups  [rbp+90h+var_C0], xmm1
0x18000ec1c  cmp     [r14+18h], rdi
0x18000ec20  jnz     loc_18000F083
0x18000ec26  test    rdi, rdi
0x18000ec29  jz      loc_18000F083
0x18000ec2f  cmp     cs:byte_1800EACCB, 8
0x18000ec36  lea     r14, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x18000ec3d  jb      short loc_18000EC62
0x18000ec3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec46  lea     edx, [r12+67h]
0x18000ec4b  mov     r9, rsi
0x18000ec4e  mov     [rsp+190h+var_170], rdi
0x18000ec53  mov     r8, r14
0x18000ec56  mov     rcx, [rcx+88h]
0x18000ec5d  call    WPP_SF_qq
0x18000ec62  lea     rdx, [rsp+190h+var_120]; struct CMediaType *
0x18000ec67  mov     rcx, rsi; this
0x18000ec6a  call    ?CheckMediaType@CDSSampleSinkInputPin@@UEAAJPEBVCMediaType@@@Z; CDSSampleSinkInputPin::CheckMediaType(CMediaType const *)
0x18000ec6f  mov     edi, eax
0x18000ec71  test    eax, eax
0x18000ec73  jns     loc_18000ED0D
0x18000ec79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ec80  test    rcx, rcx
0x18000ec83  jnz     short loc_18000ECCC
0x18000ec85  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000ec8c  nop     dword ptr [rax+rax+00h]
0x18000ec91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ec98  mov     rcx, rax
0x18000ec9b  test    rax, rax
0x18000ec9e  jz      short loc_18000ECBE
0x18000eca0  mov     rax, [rax]
0x18000eca3  mov     edx, 7F0h
0x18000eca8  mov     rax, [rax+8]
0x18000ecac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecb1  test    eax, eax
0x18000ecb3  jz      short loc_18000ECBE
0x18000ecb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ecbc  jmp     short loc_18000ECCC
0x18000ecbe  lea     rcx, qword_1800EB130; this
0x18000ecc5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000eccc  cmp     [rcx+8], r12b
0x18000ecd0  jz      short loc_18000ECF3
0x18000ecd2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000ecd7  cmp     [rax+7CCh], edi
0x18000ecdd  jz      short loc_18000ECF3
0x18000ecdf  mov     r9d, edi; int
0x18000ece2  mov     r8d, 4B2h; int
0x18000ece8  mov     rdx, r13; char *
0x18000eceb  mov     rcx, rax; this
0x18000ecee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000ecf3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000ecfa  jb      loc_18000F26E
0x18000ed00  mov     edx, 68h ; 'h'
0x18000ed05  mov     r8, r14
0x18000ed08  jmp     loc_18000F257
0x18000ed0d  mov     rcx, [rsi+0E0h]
0x18000ed14  mov     rax, [rcx]
0x18000ed17  mov     rax, [rax+30h]
0x18000ed1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed20  mov     edi, eax
0x18000ed22  test    eax, eax
0x18000ed24  jns     loc_18000EDBB
0x18000ed2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ed31  test    rcx, rcx
0x18000ed34  jnz     short loc_18000ED7D
0x18000ed36  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000ed3d  nop     dword ptr [rax+rax+00h]
0x18000ed42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ed49  mov     rcx, rax
0x18000ed4c  test    rax, rax
0x18000ed4f  jz      short loc_18000ED6F
0x18000ed51  mov     rax, [rax]
0x18000ed54  mov     edx, 7F0h
0x18000ed59  mov     rax, [rax+8]
0x18000ed5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed62  test    eax, eax
0x18000ed64  jz      short loc_18000ED6F
0x18000ed66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ed6d  jmp     short loc_18000ED7D
0x18000ed6f  lea     rcx, qword_1800EB130; this
0x18000ed76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ed7d  cmp     [rcx+8], r12b
0x18000ed81  jz      short loc_18000EDA4
0x18000ed83  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000ed88  cmp     [rax+7CCh], edi
0x18000ed8e  jz      short loc_18000EDA4
0x18000ed90  mov     r9d, edi; int
0x18000ed93  mov     r8d, 4B7h; int
0x18000ed99  mov     rdx, r13; char *
0x18000ed9c  mov     rcx, rax; this
0x18000ed9f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000eda4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000edab  jb      loc_18000F26E
0x18000edb1  mov     edx, 69h ; 'i'
0x18000edb6  jmp     loc_18000ED05
0x18000edbb  mov     rcx, [rsi+0E0h]
0x18000edc2  lea     rdx, [rsp+190h+var_148]
0x18000edc7  mov     rax, [rcx]
0x18000edca  mov     rax, [rax+20h]
0x18000edce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edd3  mov     edi, eax
0x18000edd5  test    eax, eax
0x18000edd7  jns     loc_18000EE6E
0x18000eddd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ede4  test    rcx, rcx
0x18000ede7  jnz     short loc_18000EE30
0x18000ede9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000edf0  nop     dword ptr [rax+rax+00h]
0x18000edf5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000edfc  mov     rcx, rax
0x18000edff  test    rax, rax
0x18000ee02  jz      short loc_18000EE22
0x18000ee04  mov     rax, [rax]
0x18000ee07  mov     edx, 7F0h
0x18000ee0c  mov     rax, [rax+8]
0x18000ee10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee15  test    eax, eax
0x18000ee17  jz      short loc_18000EE22
0x18000ee19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ee20  jmp     short loc_18000EE30
0x18000ee22  lea     rcx, qword_1800EB130; this
0x18000ee29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ee30  cmp     [rcx+8], r12b
0x18000ee34  jz      short loc_18000EE57
0x18000ee36  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000ee3b  cmp     [rax+7CCh], edi
0x18000ee41  jz      short loc_18000EE57
0x18000ee43  mov     r9d, edi; int
0x18000ee46  mov     r8d, 4B9h; int
0x18000ee4c  mov     rdx, r13; char *
0x18000ee4f  mov     rcx, rax; this
0x18000ee52  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000ee57  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000ee5e  jb      loc_18000F26E
0x18000ee64  mov     edx, 6Ah ; 'j'
0x18000ee69  jmp     loc_18000ED05
0x18000ee6e  lea     rdx, [rsp+190h+var_120]; struct _AMMediaType *
0x18000ee73  mov     rcx, rsi; this
0x18000ee76  call    ?SetMediaType@CDSSampleSinkInputPin@@UEAAJPEBVCMediaType@@@Z; CDSSampleSinkInputPin::SetMediaType(CMediaType const *)
0x18000ee7b  mov     edi, eax
0x18000ee7d  test    eax, eax
0x18000ee7f  jns     loc_18000EF16
0x18000ee85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ee8c  test    rcx, rcx
0x18000ee8f  jnz     short loc_18000EED8
0x18000ee91  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000ee98  nop     dword ptr [rax+rax+00h]
0x18000ee9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000eea4  mov     rcx, rax
0x18000eea7  test    rax, rax
0x18000eeaa  jz      short loc_18000EECA
0x18000eeac  mov     rax, [rax]
0x18000eeaf  mov     edx, 7F0h
0x18000eeb4  mov     rax, [rax+8]
0x18000eeb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eebd  test    eax, eax
0x18000eebf  jz      short loc_18000EECA
0x18000eec1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000eec8  jmp     short loc_18000EED8
0x18000eeca  lea     rcx, qword_1800EB130; this
0x18000eed1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000eed8  cmp     [rcx+8], r12b
0x18000eedc  jz      short loc_18000EEFF
0x18000eede  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000eee3  cmp     [rax+7CCh], edi
0x18000eee9  jz      short loc_18000EEFF
0x18000eeeb  mov     r9d, edi; int
0x18000eeee  mov     r8d, 4C2h; int
0x18000eef4  mov     rdx, r13; char *
0x18000eef7  mov     rcx, rax; this
0x18000eefa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000eeff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000ef06  jb      loc_18000F26E
0x18000ef0c  mov     edx, 6Bh ; 'k'
0x18000ef11  jmp     loc_18000ED05
0x18000ef16  mov     eax, [r15+28h]
0x18000ef1a  lea     r8, [rbp+90h+var_C0]
0x18000ef1e  mov     rcx, [rsi+0E0h]
0x18000ef25  lea     rdx, [rsp+190h+var_148]
0x18000ef2a  mov     dword ptr [rsp+190h+var_148+4], eax
0x18000ef2e  mov     rax, [rcx]
0x18000ef31  mov     rax, [rax+18h]
0x18000ef35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef3a  mov     edi, eax
0x18000ef3c  test    eax, eax
0x18000ef3e  jns     loc_18000EFD5
0x18000ef44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ef4b  test    rcx, rcx
0x18000ef4e  jnz     short loc_18000EF97
0x18000ef50  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000ef57  nop     dword ptr [rax+rax+00h]
0x18000ef5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ef63  mov     rcx, rax
0x18000ef66  test    rax, rax
0x18000ef69  jz      short loc_18000EF89
0x18000ef6b  mov     rax, [rax]
0x18000ef6e  mov     edx, 7F0h
0x18000ef73  mov     rax, [rax+8]
0x18000ef77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef7c  test    eax, eax
0x18000ef7e  jz      short loc_18000EF89
0x18000ef80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ef87  jmp     short loc_18000EF97
0x18000ef89  lea     rcx, qword_1800EB130; this
0x18000ef90  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ef97  cmp     [rcx+8], r12b
0x18000ef9b  jz      short loc_18000EFBE
0x18000ef9d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000efa2  cmp     [rax+7CCh], edi
0x18000efa8  jz      short loc_18000EFBE
0x18000efaa  mov     r9d, edi; int
0x18000efad  mov     r8d, 4C5h; int
0x18000efb3  mov     rdx, r13; char *
0x18000efb6  mov     rcx, rax; this
0x18000efb9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000efbe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000efc5  jb      loc_18000F26E
0x18000efcb  mov     edx, 6Ch ; 'l'
0x18000efd0  jmp     loc_18000ED05
0x18000efd5  mov     rcx, [rsi+0E0h]
0x18000efdc  mov     rax, [rcx]
0x18000efdf  mov     rax, [rax+28h]
0x18000efe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efe8  mov     edi, eax
0x18000efea  test    eax, eax
0x18000efec  jns     loc_18000F26E
0x18000eff2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000eff9  test    rcx, rcx
0x18000effc  jnz     short loc_18000F045
0x18000effe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000f005  nop     dword ptr [rax+rax+00h]
0x18000f00a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f011  mov     rcx, rax
0x18000f014  test    rax, rax
0x18000f017  jz      short loc_18000F037
0x18000f019  mov     rax, [rax]
0x18000f01c  mov     edx, 7F0h
0x18000f021  mov     rax, [rax+8]
0x18000f025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f02a  test    eax, eax
0x18000f02c  jz      short loc_18000F037
0x18000f02e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f035  jmp     short loc_18000F045
0x18000f037  lea     rcx, qword_1800EB130; this
0x18000f03e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f045  cmp     [rcx+8], r12b
0x18000f049  jz      short loc_18000F06C
0x18000f04b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000f050  cmp     [rax+7CCh], edi
0x18000f056  jz      short loc_18000F06C
0x18000f058  mov     r9d, edi; int
0x18000f05b  mov     r8d, 4C7h; int
0x18000f061  mov     rdx, r13; char *
0x18000f064  mov     rcx, rax; this
0x18000f067  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000f06c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f073  jb      loc_18000F26E
0x18000f079  mov     edx, 6Dh ; 'm'
0x18000f07e  jmp     loc_18000ED05
0x18000f083  mov     eax, [r14+138h]
0x18000f08a  sub     eax, 2
0x18000f08d  cmp     eax, 2
0x18000f090  ja      loc_18000F1EF
0x18000f096  lea     r8, [rbp+90h+var_B0]; struct _GUID *
0x18000f09a  mov     rcx, rdi; this
  ... truncated ...
```
