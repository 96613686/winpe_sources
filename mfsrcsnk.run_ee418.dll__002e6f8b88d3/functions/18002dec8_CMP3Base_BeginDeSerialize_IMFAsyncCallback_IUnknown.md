# CMP3Base::BeginDeSerialize(IMFAsyncCallback *,IUnknown *)

- ea: `0x18002dec8`
- end: `0x18002e468`
- name: `?BeginDeSerialize@CMP3Base@@QEAAJPEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `1440`
- prototype: `__int64 __fastcall(CMP3Base *__hidden this, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800924b4`
- `0x1800c5f3c`

## callees

- `0x180010190`
- `0x18001303c`
- `0x18002dec8`
- `0x18002f904`
- `0x18004c264`
- `0x180071a44`
- `0x180073b14`
- `0x1801095a8`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002df25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e02b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e0bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e15d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002df25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e02b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e0bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e15d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e0a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e13e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e28a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e0a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e13e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e28a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e086`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e086`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e065`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e065`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e105`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e1a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e105`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e1a3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002df11`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e017`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e0ab`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e149`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002df11`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e017`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e0ab`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e149`
- `MFPlat!MFLockPlatform` at `0x18002df94`
- `MFPlat!MFLockPlatform` at `0x18002df94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e1f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e33a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e1f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e33a`

## string_xrefs

- `0x18002def2`: `CMP3Base::BeginDeSerialize`
- `0x18002e042`: `CByteStreamCacheReaderEx::GetCurrentPosition`

## pseudocode

```c
__int64 __fastcall CMP3Base::BeginDeSerialize(CMP3Base *this, struct IMFAsyncCallback *a2, struct IUnknown *a3)
{
  CallStackTracing *v3; // rdi
  char *v6; // rbx
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  tagMFASYNCRESULT *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  tagMFASYNCRESULT *v15; // rbx
  __int64 v16; // rcx
  CallStackTracing *v17; // rdi
  char *v18; // r15
  __int64 v19; // rsi
  char *v20; // rbx
  DWORD v21; // ebp
  char *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  CallStackTracing *v26; // rdi
  GUID *v27; // rbx
  DWORD v28; // esi
  GUID *v29; // rax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  int v33; // edi
  __int64 v34; // r8
  __int64 v35; // r9
  CallStackTracing *v36; // rsi
  GUID *v37; // rbx
  DWORD v38; // ebp
  GUID *v39; // rax
  int v40; // eax
  int v41; // eax
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  CallStackTracing *v45; // rcx
  __int64 v46; // rax
  CallStackTracing *v47; // rcx
  __int64 v48; // rax
  CallStackTracing *v49; // rcx
  __int64 v50; // rax
  CallStackTracing *v51; // rcx
  __int64 v52; // rax
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  struct CallStackContext *ThreadRelativeContext; // rax

  v3 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    v6 = (char *)v3 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v3 + 3));
    if ( Value )
    {
      v6 = Value;
    }
    else if ( !GetLastError() )
    {
      v45 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v45 = CallStackTracing::s_wpInstance;
      }
      v46 = (**(__int64 (__fastcall ***)(CallStackTracing *))v45)(v45);
      if ( v46 )
        v6 = (char *)v46;
    }
    SetLastError(LastError);
    v9 = *((unsigned int *)v6 + 497);
    if ( (unsigned int)v9 < *((_DWORD *)v6 + 498) )
    {
      v10 = 2 * v9;
      *(_QWORD *)&v6[8 * v10] = "CMP3Base::BeginDeSerialize";
      *(_DWORD *)&v6[8 * v10 + 8] = 129;
    }
    ++*((_DWORD *)v6 + 497);
  }
  v11 = (tagMFASYNCRESULT *)operator new(0x68u);
  v15 = v11;
  if ( !v11 )
  {
    v43 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
      CallStackTracing::s_wpInstance = v44;
      if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
      {
        v43 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v43 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    v33 = -2147024882;
    if ( *((_BYTE *)v43 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3Base::BeginDeSerialize", 137, -2147024882);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_d18bbb785de430394c1967457ee8924f_Traceguids,
        this,
        -2147024882);
    v18 = (char *)this + 48;
    goto LABEL_75;
  }
  tagMFASYNCRESULT::tagMFASYNCRESULT(v11);
  *(_QWORD *)(v16 + 64) = &CMFRefCounted::`vftable';
  *(_DWORD *)(v16 + 72) = 0;
  *(_QWORD *)v16 = &CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'};
  *(_QWORD *)(v16 + 64) = &CAsyncResult::`vftable'{for `CMFRefCounted'};
  *(_DWORD *)(v16 + 96) = 0;
  MFLockPlatform();
  HIDWORD(v15[1].overlapped.hEvent) = 0;
  v15->hrStatusResult = 0;
  v15->hEvent = 0;
  v15[1].overlapped.InternalHigh = 0;
  v15[1].overlapped.Pointer = 0;
  v15->pCallback = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IMFAsyncCallback *))a2->lpVtbl->AddRef)(a2);
  *(_OWORD *)&v15->overlapped.Internal = 0;
  *(_OWORD *)&v15->overlapped.Offset = 0;
  v15->dwBytesTransferred = 0;
  ((void (__fastcall *)(tagMFASYNCRESULT *))v15->AsyncResult.lpVtbl->AddRef)(v15);
  v17 = CallStackTracing::s_wpInstance;
  v18 = (char *)this + 48;
  v19 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 6) = v15;
  if ( !v17 )
  {
    CallStackTracing::InitInstance();
    v17 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v20 = (char *)v17 + 208;
    v21 = GetLastError();
    v22 = (char *)TlsGetValue(*((_DWORD *)v17 + 3));
    if ( v22 )
    {
      v20 = v22;
    }
    else if ( !GetLastError() )
    {
      v47 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v47 = CallStackTracing::s_wpInstance;
      }
      v48 = (**(__int64 (__fastcall ***)(CallStackTracing *))v47)(v47);
      if ( v48 )
        v20 = (char *)v48;
    }
    SetLastError(v21);
    v23 = *((unsigned int *)v20 + 497);
    if ( (unsigned int)v23 < *((_DWORD *)v20 + 498) )
    {
      v24 = 2 * v23;
      *(_QWORD *)&v20[8 * v24] = "CByteStreamCacheReaderEx::GetCurrentPosition";
      *(_DWORD *)&v20[8 * v24 + 8] = 439;
    }
    ++*((_DWORD *)v20 + 497);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 568));
  v25 = *(_QWORD *)(v19 + 512);
  if ( v25 == -1 )
    v25 = *(_QWORD *)(v19 + 504);
  *((_QWORD *)this + 3) = v25;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 568));
  v26 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v27 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v28 = GetLastError();
    v29 = (GUID *)TlsGetValue(*((_DWORD *)v26 + 3));
    if ( v29 )
    {
      v27 = v29;
    }
    else if ( !GetLastError() )
    {
      v49 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v49 = CallStackTracing::s_wpInstance;
      }
      v50 = (**(__int64 (__fastcall ***)(CallStackTracing *))v49)(v49);
      if ( v50 )
        v27 = (GUID *)v50;
    }
    SetLastError(v28);
    v30 = *(_DWORD *)&v27[124].Data2;
    if ( v30 )
    {
      v31 = v30 - 1;
      *(_DWORD *)&v27[124].Data2 = v31;
      if ( !v31 )
      {
        *(_DWORD *)&v27[124].Data2 = 0;
        *(_QWORD *)&v27[126].Data1 = 0;
        *(_DWORD *)&v27[124].Data4[4] = 0;
        v27[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v27[126].Data4 = 0;
        v27[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  v33 = (*(__int64 (__fastcall **)(CMP3Base *))(*(_QWORD *)this + 48LL))(this);
  if ( v33 < 0 )
  {
    v53 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v34, v35);
      CallStackTracing::s_wpInstance = v54;
      if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
      {
        v53 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v53 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v53 + 8) )
    {
      v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
      if ( *((_DWORD *)v55 + 499) != v33 )
        CallStackContext::TraceFailure(v55, "CMP3Base::BeginDeSerialize", 145, v33);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_d18bbb785de430394c1967457ee8924f_Traceguids, this, v33);
LABEL_75:
    ComSmartPtr<CBaseStreamSink>::operator=(v18);
  }
  v36 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v37 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v38 = GetLastError();
    v39 = (GUID *)TlsGetValue(*((_DWORD *)v36 + 3));
    if ( v39 )
    {
      v37 = v39;
    }
    else if ( !GetLastError() )
    {
      v51 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v51 = CallStackTracing::s_wpInstance;
      }
      v52 = (**(__int64 (__fastcall ***)(CallStackTracing *))v51)(v51);
      if ( v52 )
        v37 = (GUID *)v52;
    }
    SetLastError(v38);
    v40 = *(_DWORD *)&v37[124].Data2;
    if ( v40 )
    {
      v41 = v40 - 1;
      *(_DWORD *)&v37[124].Data2 = v41;
      if ( !v41 )
      {
        *(_DWORD *)&v37[124].Data2 = 0;
        *(_QWORD *)&v37[126].Data1 = 0;
        *(_DWORD *)&v37[124].Data4[4] = 0;
        v37[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v37[126].Data4 = 0;
        v37[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x18002dec8  push    rbx
0x18002deca  push    rbp
0x18002decb  push    rsi
0x18002decc  push    rdi
0x18002decd  push    r12
0x18002decf  push    r13
0x18002ded1  push    r14
0x18002ded3  push    r15
0x18002ded5  sub     rsp, 38h
0x18002ded9  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002dee0  xor     r12d, r12d
0x18002dee3  mov     rsi, rdx
0x18002dee6  mov     r14, rcx
0x18002dee9  test    rdi, rdi
0x18002deec  jz      loc_18002E1C2
0x18002def2  lea     r13, aCmp3baseBegind; "CMP3Base::BeginDeSerialize"
0x18002def9  cmp     [rdi+8], r12b
0x18002defd  jz      short loc_18002DF4E
0x18002deff  lea     rbx, [rdi+0D0h]
0x18002df06  call    cs:__imp_GetLastError
0x18002df0c  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002df0f  mov     ebp, eax
0x18002df11  call    cs:__imp_TlsGetValue
0x18002df17  test    rax, rax
0x18002df1a  jz      loc_18002E220
0x18002df20  mov     rbx, rax
0x18002df23  mov     ecx, ebp; dwErrCode
0x18002df25  call    cs:__imp_SetLastError
0x18002df2b  mov     eax, [rbx+7C4h]
0x18002df31  cmp     eax, [rbx+7C8h]
0x18002df37  jnb     short loc_18002DF48
0x18002df39  add     rax, rax
0x18002df3c  mov     [rbx+rax*8], r13
0x18002df40  mov     dword ptr [rbx+rax*8+8], 81h
0x18002df48  inc     dword ptr [rbx+7C4h]
0x18002df4e  mov     ecx, 68h ; 'h'; Size
0x18002df53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002df58  mov     rbx, rax
0x18002df5b  test    rax, rax
0x18002df5e  jz      loc_18002E1E4
0x18002df64  mov     rcx, rax; this
0x18002df67  call    ??0tagMFASYNCRESULT@@QEAA@XZ; tagMFASYNCRESULT::tagMFASYNCRESULT(void)
0x18002df6c  lea     rax, ??_7CMFRefCounted@@6B@; const CMFRefCounted::`vftable'
0x18002df73  mov     [rcx+40h], rax
0x18002df77  lea     rax, ??_7CMP3ByteStreamPluginResult@@6BtagMFASYNCRESULT@@@; const CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'}
0x18002df7e  mov     [rcx+48h], r12d
0x18002df82  mov     [rcx], rax
0x18002df85  lea     rax, ??_7CAsyncResult@@6BCMFRefCounted@@@; const CAsyncResult::`vftable'{for `CMFRefCounted'}
0x18002df8c  mov     [rcx+40h], rax
0x18002df90  mov     [rcx+60h], r12d
0x18002df94  call    cs:__imp_MFLockPlatform
0x18002df9a  mov     [rbx+64h], r12d
0x18002df9e  mov     [rbx+30h], r12d
0x18002dfa2  mov     [rbx+38h], r12
0x18002dfa6  mov     [rbx+50h], r12
0x18002dfaa  mov     [rbx+58h], r12
0x18002dfae  mov     [rbx+28h], rsi
0x18002dfb2  test    rsi, rsi
0x18002dfb5  jz      short loc_18002DFC6
0x18002dfb7  mov     rax, [rsi]
0x18002dfba  mov     rcx, rsi
0x18002dfbd  mov     rax, [rax+8]
0x18002dfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfc6  xorps   xmm0, xmm0
0x18002dfc9  mov     rcx, rbx
0x18002dfcc  movups  xmmword ptr [rbx+8], xmm0
0x18002dfd0  movups  xmmword ptr [rbx+18h], xmm0
0x18002dfd4  mov     [rbx+34h], r12d
0x18002dfd8  mov     rax, [rbx]
0x18002dfdb  mov     rax, [rax+8]
0x18002dfdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfe4  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002dfeb  lea     r15, [r14+30h]
0x18002dfef  mov     rsi, [r14+28h]
0x18002dff3  mov     [r15], rbx
0x18002dff6  test    rdi, rdi
0x18002dff9  jz      loc_18002E1D3
0x18002dfff  cmp     [rdi+8], r12b
0x18002e003  jz      short loc_18002E05B
0x18002e005  lea     rbx, [rdi+0D0h]
0x18002e00c  call    cs:__imp_GetLastError
0x18002e012  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002e015  mov     ebp, eax
0x18002e017  call    cs:__imp_TlsGetValue
0x18002e01d  test    rax, rax
0x18002e020  jz      loc_18002E255
0x18002e026  mov     rbx, rax
0x18002e029  mov     ecx, ebp; dwErrCode
0x18002e02b  call    cs:__imp_SetLastError
0x18002e031  mov     eax, [rbx+7C4h]
0x18002e037  cmp     eax, [rbx+7C8h]
0x18002e03d  jnb     short loc_18002E055
0x18002e03f  add     rax, rax
0x18002e042  lea     rcx, aCbytestreamcac_21; "CByteStreamCacheReaderEx::GetCurrentPos"...
0x18002e049  mov     [rbx+rax*8], rcx
0x18002e04d  mov     dword ptr [rbx+rax*8+8], 1B7h
0x18002e055  inc     dword ptr [rbx+7C4h]
0x18002e05b  lea     rbx, [rsi+238h]
0x18002e062  mov     rcx, rbx; lpCriticalSection
0x18002e065  call    cs:__imp_EnterCriticalSection
0x18002e06b  mov     rax, [rsi+200h]
0x18002e072  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e076  jnz     short loc_18002E07F
0x18002e078  mov     rax, [rsi+1F8h]
0x18002e07f  mov     rcx, rbx; lpCriticalSection
0x18002e082  mov     [r14+18h], rax
0x18002e086  call    cs:__imp_LeaveCriticalSection
0x18002e08c  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e093  cmp     [rdi+8], r12b
0x18002e097  jz      short loc_18002E111
0x18002e099  lea     rbx, [rdi+0D0h]
0x18002e0a0  call    cs:__imp_GetLastError
0x18002e0a6  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002e0a9  mov     esi, eax
0x18002e0ab  call    cs:__imp_TlsGetValue
0x18002e0b1  test    rax, rax
0x18002e0b4  jz      loc_18002E28A
0x18002e0ba  mov     rbx, rax
0x18002e0bd  mov     ecx, esi; dwErrCode
0x18002e0bf  call    cs:__imp_SetLastError
0x18002e0c5  mov     eax, [rbx+7C4h]
0x18002e0cb  test    eax, eax
0x18002e0cd  jz      short loc_18002E111
0x18002e0cf  sub     eax, 1
0x18002e0d2  mov     [rbx+7C4h], eax
0x18002e0d8  jnz     short loc_18002E111
0x18002e0da  mov     [rbx+7C4h], r12d
0x18002e0e1  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002e0e8  mov     [rbx+7E0h], r12
0x18002e0ef  mov     [rbx+7CCh], r12d
0x18002e0f6  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x18002e0fe  mov     [rbx+7E8h], r12d
0x18002e105  call    cs:__imp_GetCurrentThreadId
0x18002e10b  mov     [rbx+7C0h], eax
0x18002e111  mov     rax, [r14]
0x18002e114  mov     rcx, r14
0x18002e117  mov     rax, [rax+30h]
0x18002e11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e120  mov     edi, eax
0x18002e122  test    eax, eax
0x18002e124  js      loc_18002E32A
0x18002e12a  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e131  cmp     [rsi+8], r12b
0x18002e135  jz      short loc_18002E1AF
0x18002e137  lea     rbx, [rsi+0D0h]
0x18002e13e  call    cs:__imp_GetLastError
0x18002e144  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18002e147  mov     ebp, eax
0x18002e149  call    cs:__imp_TlsGetValue
0x18002e14f  test    rax, rax
0x18002e152  jz      loc_18002E2BB
0x18002e158  mov     rbx, rax
0x18002e15b  mov     ecx, ebp; dwErrCode
0x18002e15d  call    cs:__imp_SetLastError
0x18002e163  mov     eax, [rbx+7C4h]
0x18002e169  test    eax, eax
0x18002e16b  jz      short loc_18002E1AF
0x18002e16d  sub     eax, 1
0x18002e170  mov     [rbx+7C4h], eax
0x18002e176  jnz     short loc_18002E1AF
0x18002e178  mov     [rbx+7C4h], r12d
0x18002e17f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002e186  mov     [rbx+7E0h], r12
0x18002e18d  mov     [rbx+7CCh], r12d
0x18002e194  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x18002e19c  mov     [rbx+7E8h], r12d
0x18002e1a3  call    cs:__imp_GetCurrentThreadId
0x18002e1a9  mov     [rbx+7C0h], eax
0x18002e1af  mov     eax, edi
0x18002e1b1  add     rsp, 38h
0x18002e1b5  pop     r15
0x18002e1b7  pop     r14
0x18002e1b9  pop     r13
0x18002e1bb  pop     r12
0x18002e1bd  pop     rdi
0x18002e1be  pop     rsi
0x18002e1bf  pop     rbp
0x18002e1c0  pop     rbx
0x18002e1c1  retn
0x18002e1c2  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e1c7  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e1ce  jmp     loc_18002DEF2
0x18002e1d3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e1d8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e1df  jmp     loc_18002DFFF
0x18002e1e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e1eb  test    rcx, rcx
0x18002e1ee  jnz     loc_18002E427
0x18002e1f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e1fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e201  mov     rcx, rax
0x18002e204  test    rax, rax
0x18002e207  jnz     loc_18002E407
0x18002e20d  lea     rcx, qword_1801B07E0
0x18002e214  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e21b  jmp     loc_18002E427
0x18002e220  call    cs:__imp_GetLastError
0x18002e226  test    eax, eax
0x18002e228  jnz     loc_18002DF23
0x18002e22e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e235  test    rcx, rcx
0x18002e238  jz      loc_18002E2EC
0x18002e23e  mov     rax, [rcx]
0x18002e241  mov     rax, [rax]
0x18002e244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e249  test    rax, rax
0x18002e24c  cmovnz  rbx, rax
0x18002e250  jmp     loc_18002DF23
0x18002e255  call    cs:__imp_GetLastError
0x18002e25b  test    eax, eax
0x18002e25d  jnz     loc_18002E029
0x18002e263  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e26a  test    rcx, rcx
0x18002e26d  jz      loc_18002E2FD
0x18002e273  mov     rax, [rcx]
0x18002e276  mov     rax, [rax]
0x18002e279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e27e  test    rax, rax
0x18002e281  cmovnz  rbx, rax
0x18002e285  jmp     loc_18002E029
0x18002e28a  call    cs:__imp_GetLastError
0x18002e290  test    eax, eax
0x18002e292  jnz     loc_18002E0BD
0x18002e298  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e29f  test    rcx, rcx
0x18002e2a2  jz      short loc_18002E30E
0x18002e2a4  mov     rax, [rcx]
0x18002e2a7  mov     rax, [rax]
0x18002e2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2af  test    rax, rax
0x18002e2b2  cmovnz  rbx, rax
0x18002e2b6  jmp     loc_18002E0BD
0x18002e2bb  call    cs:__imp_GetLastError
0x18002e2c1  test    eax, eax
0x18002e2c3  jnz     loc_18002E15B
0x18002e2c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e2d0  test    rcx, rcx
0x18002e2d3  jz      short loc_18002E31C
0x18002e2d5  mov     rax, [rcx]
0x18002e2d8  mov     rax, [rax]
0x18002e2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2e0  test    rax, rax
0x18002e2e3  cmovnz  rbx, rax
0x18002e2e7  jmp     loc_18002E15B
0x18002e2ec  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e2f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e2f8  jmp     loc_18002E23E
0x18002e2fd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e302  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e309  jmp     loc_18002E273
0x18002e30e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e313  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e31a  jmp     short loc_18002E2A4
0x18002e31c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e321  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e328  jmp     short loc_18002E2D5
0x18002e32a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e331  test    rcx, rcx
0x18002e334  jnz     loc_18002E3C8
0x18002e33a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e340  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e347  mov     rcx, rax
0x18002e34a  test    rax, rax
0x18002e34d  jnz     short loc_18002E3AC
0x18002e34f  lea     rcx, qword_1801B07E0
0x18002e356  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e35d  jmp     short loc_18002E3C8
0x18002e35f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e364  cmp     [rax+7CCh], edi
0x18002e36a  jz      short loc_18002E3CE
0x18002e36c  mov     r9d, edi; int
0x18002e36f  mov     r8d, 91h; int
0x18002e375  mov     rdx, r13; char *
0x18002e378  mov     rcx, rax; this
0x18002e37b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e380  jmp     short loc_18002E3CE
0x18002e382  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e387  cmp     [rax+7CCh], edi
0x18002e38d  jz      loc_18002E436
0x18002e393  mov     r9d, edi; int
0x18002e396  mov     r8d, 89h; int
0x18002e39c  mov     rdx, r13; char *
0x18002e39f  mov     rcx, rax; this
0x18002e3a2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e3a7  jmp     loc_18002E436
0x18002e3ac  mov     rax, [rax]
0x18002e3af  mov     edx, 7F0h
0x18002e3b4  mov     rax, [rax+8]
0x18002e3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3bd  test    eax, eax
0x18002e3bf  jz      short loc_18002E34F
0x18002e3c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e3c8  cmp     [rcx+8], r12b
0x18002e3cc  jnz     short loc_18002E35F
0x18002e3ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e3d5  jb      short loc_18002E3FA
0x18002e3d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3de  lea     r8, WPP_d18bbb785de430394c1967457ee8924f_Traceguids
0x18002e3e5  mov     edx, 11h
0x18002e3ea  mov     [rsp+78h+var_58], edi
  ... truncated ...
```
