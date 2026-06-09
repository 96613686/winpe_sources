# CBytewiseMediaStream::FillRequests(void)

- ea: `0x1800425a0`
- end: `0x180042b13`
- name: `?FillRequests@CBytewiseMediaStream@@UEAAJXZ`
- size: `1395`
- prototype: `__int64 __fastcall(CBytewiseMediaStream *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x1800245b4`
- `0x180036c30`
- `0x18003b32c`
- `0x18003cbec`
- `0x1800425a0`
- `0x180042b1c`
- `0x180042d78`
- `0x180077708`
- `0x180079680`
- `0x1800d73f0`
- `0x180121750`
- `0x1801534a0`
- `0x1801780cc`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042613`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800425e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800427e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800425e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800427e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042690`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042690`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042650`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042650`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800426f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800426f1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800425f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800425f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004283d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042885`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800428c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004283d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042885`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800428c7`

## pseudocode

```c
__int64 __fastcall CBytewiseMediaStream::FillRequests(CBytewiseMediaStream *this)
{
  CallStackTracing *v1; // rdi
  int v3; // r14d
  char *v4; // rbx
  DWORD LastError; // r15d
  char *Value; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  struct CallStackContext *v9; // rbx
  int v10; // eax
  int v11; // eax
  __int64 v13; // rdx
  struct IMFSample *v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  CallStackTracing *v17; // rcx
  __int64 v18; // rax
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  void *v30; // [rsp+70h] [rbp+30h] BYREF
  struct IMFSample *v31; // [rsp+78h] [rbp+38h] BYREF

  v1 = CallStackTracing::s_wpInstance;
  v3 = 0;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v1 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v1 + 8) )
  {
    v4 = (char *)v1 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v1 + 3));
    if ( Value )
    {
      v4 = Value;
    }
    else if ( !GetLastError() )
    {
      v17 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v17 = CallStackTracing::s_wpInstance;
      }
      v18 = (**(__int64 (__fastcall ***)(CallStackTracing *))v17)(v17);
      if ( v18 )
        v4 = (char *)v18;
    }
    SetLastError(LastError);
    v7 = *((unsigned int *)v4 + 497);
    if ( (unsigned int)v7 < *((_DWORD *)v4 + 498) )
    {
      v8 = 2 * v7;
      *(_QWORD *)&v4[8 * v8] = "CBytewiseMediaStream::FillRequests";
      *(_DWORD *)&v4[8 * v8 + 8] = 638;
    }
    ++*((_DWORD *)v4 + 497);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (unsigned __int8)byte_1801BA10B >= 8u )
    WPP_SF_sqddd(*((_QWORD *)WPP_GLOBAL_Control + 17), 47);
  while ( (unsigned int)CBytewiseMediaStream::HasOutstandingRequests(this)
       && (unsigned int)CBytewiseMediaStream::HasUnprocessedSamples(this) )
  {
    v31 = 0;
    v30 = 0;
    CVPtrList::RemoveHead((CBytewiseMediaStream *)((char *)this + 272), &v30);
    CVPtrList::RemoveHead((CBytewiseMediaStream *)((char *)this + 720), (void **)&v31);
    v14 = v31;
    if ( !v31 )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      v3 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CBytewiseMediaStream::FillRequests", 664, -2147418113);
      }
      if ( g_wppLevels )
      {
        v28 = 48;
LABEL_55:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids, this, v3);
      }
LABEL_56:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v30);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v31);
      break;
    }
    ((void (__fastcall *)(struct IMFSample *, const GUID *, void *))v31->lpVtbl->SetUnknown)(
      v31,
      &MFSampleExtension_Token,
      v30);
    v3 = CBytewiseMediaStream::SendSampleEvent(this, v14);
    if ( v3 < 0 )
    {
      v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v25 + 499) != v3 )
          CallStackContext::TraceFailure(v25, "CBytewiseMediaStream::FillRequests", 669, v3);
      }
      if ( g_wppLevels )
      {
        v28 = 49;
        goto LABEL_55;
      }
      goto LABEL_56;
    }
    if ( (byte_1801B9501 & 2) != 0 )
      McTemplateU0pp_EventWriteTransfer(v16, SrcStreamRequestSample_Stop, this, v30);
    CAudioBurstBufferStream::NeedMoreSamplesForBuffer((CBytewiseMediaStream *)((char *)this + 128));
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v30);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v31);
  }
  if ( *((_DWORD *)this + 66) == 1 && !(unsigned int)CBytewiseMediaStream::HasUnprocessedSamples(this) )
  {
    if ( (unsigned __int8)byte_1801BA10B >= 4u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 50, &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids, this);
    v3 = CBytewiseMediaStream::DoEOS(this);
    if ( v3 < 0 )
    {
      v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
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
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v27 + 499) != v3 )
          CallStackContext::TraceFailure(v27, "CBytewiseMediaStream::FillRequests", 688, v3);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids, this, v3);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v9 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = *((_DWORD *)v9 + 497);
    if ( v10 )
    {
      v11 = v10 - 1;
      *((_DWORD *)v9 + 497) = v11;
      if ( !v11 )
      {
        *((_DWORD *)v9 + 497) = 0;
        *((_QWORD *)v9 + 252) = 0;
        *((_DWORD *)v9 + 499) = 0;
        *((GUID *)v9 + 125) = GUID_00000000_0000_0000_0000_000000000000;
        *((_DWORD *)v9 + 506) = 0;
        *((_DWORD *)v9 + 496) = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800425a0  mov     [rsp-28h+arg_10], rbx
0x1800425a5  mov     [rsp-28h+arg_18], rsi
0x1800425aa  push    rbp
0x1800425ab  push    rdi
0x1800425ac  push    r12
0x1800425ae  push    r14
0x1800425b0  push    r15
0x1800425b2  mov     rbp, rsp
0x1800425b5  sub     rsp, 40h
0x1800425b9  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800425c0  xor     r12d, r12d
0x1800425c3  mov     rsi, rcx
0x1800425c6  mov     r14d, r12d
0x1800425c9  test    rdi, rdi
0x1800425cc  jz      loc_180042720
0x1800425d2  lea     rcx, aCbytewisemedia_16; "CBytewiseMediaStream::FillRequests"
0x1800425d9  cmp     [rdi+8], r12b
0x1800425dd  jz      short loc_180042649
0x1800425df  lea     rbx, [rdi+0D0h]
0x1800425e6  call    cs:__imp_GetLastError
0x1800425ed  nop     dword ptr [rax+rax+00h]
0x1800425f2  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800425f5  mov     r15d, eax
0x1800425f8  call    cs:__imp_TlsGetValue
0x1800425ff  nop     dword ptr [rax+rax+00h]
0x180042604  test    rax, rax
0x180042607  jz      loc_1800427E8
0x18004260d  mov     rbx, rax
0x180042610  mov     ecx, r15d; dwErrCode
0x180042613  call    cs:__imp_SetLastError
0x18004261a  nop     dword ptr [rax+rax+00h]
0x18004261f  mov     eax, [rbx+7C4h]
0x180042625  lea     rcx, aCbytewisemedia_16; "CBytewiseMediaStream::FillRequests"
0x18004262c  cmp     eax, [rbx+7C8h]
0x180042632  jnb     short loc_180042643
0x180042634  add     rax, rax
0x180042637  mov     [rbx+rax*8], rcx
0x18004263b  mov     dword ptr [rbx+rax*8+8], 27Eh
0x180042643  inc     dword ptr [rbx+7C4h]
0x180042649  lea     rdi, [rsi+10h]
0x18004264d  mov     rcx, rdi; lpCriticalSection
0x180042650  call    cs:__imp_EnterCriticalSection
0x180042657  nop     dword ptr [rax+rax+00h]
0x18004265c  cmp     cs:byte_1801BA10B, 8
0x180042663  jnb     loc_180042986
0x180042669  mov     rcx, rsi; this
0x18004266c  call    ?HasOutstandingRequests@CBytewiseMediaStream@@QEAAHXZ; CBytewiseMediaStream::HasOutstandingRequests(void)
0x180042671  lea     r15, WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids
0x180042678  test    eax, eax
0x18004267a  jnz     loc_180042731
0x180042680  cmp     dword ptr [rsi+108h], 1
0x180042687  jz      loc_180042A6A
0x18004268d  mov     rcx, rdi; lpCriticalSection
0x180042690  call    cs:__imp_LeaveCriticalSection
0x180042697  nop     dword ptr [rax+rax+00h]
0x18004269c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800426a3  cmp     [rcx+8], r12b
0x1800426a7  jz      short loc_180042703
0x1800426a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800426ae  mov     rbx, rax
0x1800426b1  mov     eax, [rax+7C4h]
0x1800426b7  test    eax, eax
0x1800426b9  jz      short loc_180042703
0x1800426bb  sub     eax, 1
0x1800426be  mov     [rbx+7C4h], eax
0x1800426c4  jnz     short loc_180042703
0x1800426c6  mov     [rbx+7C4h], r12d
0x1800426cd  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800426d4  mov     [rbx+7E0h], r12
0x1800426db  mov     [rbx+7CCh], r12d
0x1800426e2  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x1800426ea  mov     [rbx+7E8h], r12d
0x1800426f1  call    cs:__imp_GetCurrentThreadId
0x1800426f8  nop     dword ptr [rax+rax+00h]
0x1800426fd  mov     [rbx+7C0h], eax
0x180042703  lea     r11, [rsp+40h+var_s0]
0x180042708  mov     eax, r14d
0x18004270b  mov     rbx, [r11+40h]
0x18004270f  mov     rsi, [r11+48h]
0x180042713  mov     rsp, r11
0x180042716  pop     r15
0x180042718  pop     r14
0x18004271a  pop     r12
0x18004271c  pop     rdi
0x18004271d  pop     rbp
0x18004271e  retn
0x180042720  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180042725  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004272c  jmp     loc_1800425D2
0x180042731  mov     rcx, rsi; this
0x180042734  call    ?HasUnprocessedSamples@CBytewiseMediaStream@@QEAAHXZ; CBytewiseMediaStream::HasUnprocessedSamples(void)
0x180042739  test    eax, eax
0x18004273b  jz      loc_180042680
0x180042741  lea     rcx, [rsi+110h]; this
0x180042748  mov     [rbp+arg_8], r12
0x18004274c  lea     rdx, [rbp+arg_0]; void **
0x180042750  mov     [rbp+arg_0], r12
0x180042754  call    ?RemoveHead@CVPtrList@@QEAAHPEAPEAX@Z; CVPtrList::RemoveHead(void * *)
0x180042759  lea     rcx, [rsi+2D0h]; this
0x180042760  lea     rdx, [rbp+arg_8]; void **
0x180042764  call    ?RemoveHead@CVPtrList@@QEAAHPEAPEAX@Z; CVPtrList::RemoveHead(void * *)
0x180042769  mov     rbx, [rbp+arg_8]
0x18004276d  test    rbx, rbx
0x180042770  jz      loc_18004286F
0x180042776  mov     rax, [rbx]
0x180042779  lea     rdx, MFSampleExtension_Token
0x180042780  mov     r8, [rbp+arg_0]
0x180042784  mov     rcx, rbx
0x180042787  mov     rax, [rax+0D8h]
0x18004278e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042793  mov     rdx, rbx; struct IMFSample *
0x180042796  mov     rcx, rsi; this
0x180042799  call    ?SendSampleEvent@CBytewiseMediaStream@@QEAAJPEAUIMFSample@@@Z; CBytewiseMediaStream::SendSampleEvent(IMFSample *)
0x18004279e  mov     r14d, eax
0x1800427a1  test    eax, eax
0x1800427a3  js      loc_18004282D
0x1800427a9  test    cs:byte_1801B9501, 2
0x1800427b0  jz      short loc_1800427C5
0x1800427b2  mov     r9, [rbp+arg_0]
0x1800427b6  lea     rdx, SrcStreamRequestSample_Stop
0x1800427bd  mov     r8, rsi
0x1800427c0  call    McTemplateU0pp_EventWriteTransfer
0x1800427c5  lea     rcx, [rsi+80h]; this
0x1800427cc  call    ?NeedMoreSamplesForBuffer@CAudioBurstBufferStream@@QEAAHXZ; CAudioBurstBufferStream::NeedMoreSamplesForBuffer(void)
0x1800427d1  lea     rcx, [rbp+arg_0]; void *
0x1800427d5  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800427da  lea     rcx, [rbp+arg_8]; void *
0x1800427de  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800427e3  jmp     loc_180042669
0x1800427e8  call    cs:__imp_GetLastError
0x1800427ef  nop     dword ptr [rax+rax+00h]
0x1800427f4  test    eax, eax
0x1800427f6  jnz     loc_180042610
0x1800427fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042803  test    rcx, rcx
0x180042806  jz      short loc_18004281F
0x180042808  mov     rax, [rcx]
0x18004280b  mov     rax, [rax]
0x18004280e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042813  test    rax, rax
0x180042816  cmovnz  rbx, rax
0x18004281a  jmp     loc_180042610
0x18004281f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180042824  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004282b  jmp     short loc_180042808
0x18004282d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042834  test    rcx, rcx
0x180042837  jnz     loc_1800429E6
0x18004283d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042844  nop     dword ptr [rax+rax+00h]
0x180042849  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042850  mov     rcx, rax
0x180042853  test    rax, rax
0x180042856  jnz     loc_1800429C6
0x18004285c  lea     rcx, qword_1801B97E0
0x180042863  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004286a  jmp     loc_1800429E6
0x18004286f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042876  mov     r14d, 8000FFFFh
0x18004287c  test    rcx, rcx
0x18004287f  jnz     loc_180042A20
0x180042885  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004288c  nop     dword ptr [rax+rax+00h]
0x180042891  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042898  mov     rcx, rax
0x18004289b  test    rax, rax
0x18004289e  jnz     loc_180042A00
0x1800428a4  lea     rcx, qword_1801B97E0
0x1800428ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800428b2  jmp     loc_180042A20
0x1800428b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800428be  test    rcx, rcx
0x1800428c1  jnz     loc_180042AD7
0x1800428c7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800428ce  nop     dword ptr [rax+rax+00h]
0x1800428d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800428da  mov     rcx, rax
0x1800428dd  test    rax, rax
0x1800428e0  jnz     loc_180042AB7
0x1800428e6  lea     rcx, qword_1801B97E0
0x1800428ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800428f4  jmp     loc_180042AD7
0x1800428f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800428fe  cmp     [rax+7CCh], r14d
0x180042905  jz      loc_1800429F0
0x18004290b  mov     r9d, r14d; int
0x18004290e  lea     rdx, aCbytewisemedia_16; "CBytewiseMediaStream::FillRequests"
0x180042915  mov     r8d, 29Dh; int
0x18004291b  mov     rcx, rax; this
0x18004291e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042923  jmp     loc_1800429F0
0x180042928  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004292d  cmp     [rax+7CCh], r14d
0x180042934  jz      loc_180042A2A
0x18004293a  mov     r9d, r14d; int
0x18004293d  lea     rdx, aCbytewisemedia_16; "CBytewiseMediaStream::FillRequests"
0x180042944  mov     r8d, 298h; int
0x18004294a  mov     rcx, rax; this
0x18004294d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042952  jmp     loc_180042A2A
0x180042957  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004295c  cmp     [rax+7CCh], r14d
0x180042963  jz      loc_180042AE1
0x180042969  mov     r9d, r14d; int
0x18004296c  lea     rdx, aCbytewisemedia_16; "CBytewiseMediaStream::FillRequests"
0x180042973  mov     r8d, 2B0h; int
0x180042979  mov     rcx, rax; this
0x18004297c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042981  jmp     loc_180042AE1
0x180042986  mov     eax, [rsi+488h]
0x18004298c  mov     edx, 2Fh ; '/'
0x180042991  mov     rcx, cs:WPP_GLOBAL_Control
0x180042998  mov     [rsp+40h+var_8], eax
0x18004299c  mov     eax, [rsi+2C8h]
0x1800429a2  mov     [rsp+40h+var_10], eax
0x1800429a6  mov     eax, [rsi+0F0h]
0x1800429ac  mov     rcx, [rcx+88h]
0x1800429b3  mov     [rsp+40h+var_18], eax
0x1800429b7  mov     [rsp+40h+var_20], rsi
0x1800429bc  call    WPP_SF_sqddd
0x1800429c1  jmp     loc_180042669
0x1800429c6  mov     rax, [rax]
0x1800429c9  mov     edx, 7F0h
0x1800429ce  mov     rax, [rax+8]
0x1800429d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429d7  test    eax, eax
0x1800429d9  jz      loc_18004285C
0x1800429df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800429e6  cmp     [rcx+8], r12b
0x1800429ea  jnz     loc_1800428F9
0x1800429f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800429f7  jb      short loc_180042A53
0x1800429f9  mov     edx, 31h ; '1'
0x1800429fe  jmp     short loc_180042A38
0x180042a00  mov     rax, [rax]
0x180042a03  mov     edx, 7F0h
0x180042a08  mov     rax, [rax+8]
0x180042a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a11  test    eax, eax
0x180042a13  jz      loc_1800428A4
0x180042a19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180042a20  cmp     [rcx+8], r12b
0x180042a24  jnz     loc_180042928
0x180042a2a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042a31  jb      short loc_180042A53
0x180042a33  mov     edx, 30h ; '0'
0x180042a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a3f  mov     r9, rsi
0x180042a42  mov     r8, r15
0x180042a45  mov     dword ptr [rsp+40h+var_20], r14d
0x180042a4a  mov     rcx, [rcx+10h]
0x180042a4e  call    WPP_SF_qD
0x180042a53  lea     rcx, [rbp+arg_0]; void *
0x180042a57  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180042a5c  lea     rcx, [rbp+arg_8]; void *
0x180042a60  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180042a65  jmp     loc_180042680
0x180042a6a  mov     rcx, rsi; this
0x180042a6d  call    ?HasUnprocessedSamples@CBytewiseMediaStream@@QEAAHXZ; CBytewiseMediaStream::HasUnprocessedSamples(void)
0x180042a72  test    eax, eax
0x180042a74  jnz     loc_18004268D
0x180042a7a  cmp     cs:byte_1801BA10B, 4
0x180042a81  jb      short loc_180042A9F
0x180042a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a8a  lea     edx, [rax+32h]
0x180042a8d  mov     r9, rsi
0x180042a90  mov     r8, r15
0x180042a93  mov     rcx, [rcx+88h]
0x180042a9a  call    WPP_SF_q
0x180042a9f  mov     rcx, rsi; this
0x180042aa2  call    ?DoEOS@CBytewiseMediaStream@@IEAAJXZ; CBytewiseMediaStream::DoEOS(void)
0x180042aa7  mov     r14d, eax
0x180042aaa  test    eax, eax
0x180042aac  jns     loc_18004268D
0x180042ab2  jmp     loc_1800428B7
0x180042ab7  mov     rax, [rax]
0x180042aba  mov     edx, 7F0h
0x180042abf  mov     rax, [rax+8]
0x180042ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ac8  test    eax, eax
0x180042aca  jz      loc_1800428E6
0x180042ad0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180042ad7  cmp     [rcx+8], r12b
0x180042adb  jnz     loc_180042957
0x180042ae1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042ae8  jb      loc_18004268D
0x180042aee  mov     rcx, cs:WPP_GLOBAL_Control
0x180042af5  mov     edx, 33h ; '3'
0x180042afa  mov     r9, rsi
0x180042afd  mov     dword ptr [rsp+40h+var_20], r14d
0x180042b02  mov     r8, r15
0x180042b05  mov     rcx, [rcx+10h]
0x180042b09  call    WPP_SF_qD
0x180042b0e  jmp     loc_18004268D
```
