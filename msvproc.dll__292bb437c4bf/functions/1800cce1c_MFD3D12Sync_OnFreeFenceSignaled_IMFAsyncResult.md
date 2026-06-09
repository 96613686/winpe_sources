# MFD3D12Sync::OnFreeFenceSignaled(IMFAsyncResult *)

- ea: `0x1800cce1c`
- end: `0x1800cd3a5`
- name: `?OnFreeFenceSignaled@MFD3D12Sync@@IEAAJPEAUIMFAsyncResult@@@Z`
- size: `1417`
- prototype: `__int64 __fastcall(MFD3D12Sync *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800cce00`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180026db8`
- `0x18003639c`
- `0x180061e00`
- `0x1800cad24`
- `0x1800cb3fc`
- `0x1800cc488`
- `0x1800ccb68`
- `0x1800cce1c`
- `0x1800cda00`
- `0x1800cf210`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cce56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cce56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cced7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cd383`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cced7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cd383`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800cd193`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800cd193`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x1800cd280`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x1800cd280`

## pseudocode

```c
__int64 __fastcall MFD3D12Sync::OnFreeFenceSignaled(MFD3D12Sync *this, struct IMFAsyncResult *a2)
{
  CallStackTracing *v4; // rcx
  HRESULT v5; // edi
  struct CallStackContext *v6; // rax
  struct IMFAsyncResultVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetObjectA)(IMFAsyncResult *, IUnknown **); // rbx
  CallStackTracing *v9; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v13)(_QWORD, GUID *, IUnknown **); // rdi
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  IUnknown *v16; // rbx
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  volatile int *v24; // rdx
  void *v25; // rcx
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  __int64 (__fastcall ***v34)(_QWORD, GUID *, IUnknown **); // [rsp+40h] [rbp-28h] BYREF
  _OWORD v35[2]; // [rsp+48h] [rbp-20h] BYREF
  IRtwqAsyncResult *asyncResult; // [rsp+B0h] [rbp+48h] BYREF
  IUnknown *v37; // [rsp+B8h] [rbp+50h] BYREF
  IUnknown *appObject; // [rsp+C0h] [rbp+58h] BYREF
  MFD3D12Sync *v39; // [rsp+C8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&asyncResult, "MFD3D12Sync::OnFreeFenceSignaled", 283);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    v37 = 0;
    v34 = 0;
    GetObjectA = lpVtbl->GetObjectA;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    v5 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, __int64 (__fastcall ****)(_QWORD, GUID *, IUnknown **)))GetObjectA)(
           a2,
           &v34);
    if ( v5 < 0 )
    {
      v9 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v9 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v9);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MFD3D12Sync::OnFreeFenceSignaled", 289, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_79;
      v11 = 63;
      goto LABEL_78;
    }
    v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v34;
    v13 = **v34;
    Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(&v37);
    v5 = v13(v12, &GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76, &v37);
    if ( v5 < 0 )
    {
      v14 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v14 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext(v14);
        if ( *((_DWORD *)v15 + 499) != v5 )
          CallStackContext::TraceFailure(v15, "MFD3D12Sync::OnFreeFenceSignaled", 290, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_79;
      v11 = 64;
      goto LABEL_78;
    }
    v16 = v37;
    asyncResult = 0;
    appObject = v37;
    if ( !(unsigned int)CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::Find(
                          (char *)this + 176,
                          &appObject,
                          &asyncResult,
                          v35) )
    {
      v17 = CallStackTracing::s_wpInstance;
      v5 = -1072875819;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v17 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext(v17);
        if ( *((_DWORD *)v18 + 499) != -1072875819 )
          CallStackContext::TraceFailure(v18, "MFD3D12Sync::OnFreeFenceSignaled", 295, -1072875819);
      }
      if ( !g_wppLevels )
        goto LABEL_79;
      v11 = 65;
      goto LABEL_78;
    }
    if ( g_wppLevels >= 0x20u )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 64LL))(*((_QWORD *)this + 16));
      WPP_SF_qqdII(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        v21,
        this,
        v37,
        *((_DWORD *)this + 47),
        *((_QWORD *)this + 20),
        v19);
      v16 = v37;
    }
    if ( !asyncResult )
    {
      v22 = CallStackTracing::s_wpInstance;
      v5 = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v22 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext(v22);
        if ( *((_DWORD *)v23 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v23, "MFD3D12Sync::OnFreeFenceSignaled", 299, -2147467261);
      }
      if ( !g_wppLevels )
        goto LABEL_79;
      v11 = 67;
      goto LABEL_78;
    }
    appObject = v16;
    v35[0] = 0;
    if ( !(unsigned int)CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::Find(
                          (char *)this + 176,
                          &appObject,
                          &asyncResult,
                          v35)
      || (appObject = 0,
          !(unsigned int)CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::Remove(
                           (char *)this + 176,
                           v35,
                           &appObject,
                           &asyncResult)) )
    {
      v31 = CallStackTracing::s_wpInstance;
      v5 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v31 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext(v31);
        if ( *((_DWORD *)v32 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v32, "MFD3D12Sync::OnFreeFenceSignaled", 302, -2147418113);
      }
      if ( !g_wppLevels )
        goto LABEL_79;
      v11 = 68;
LABEL_78:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids, this, v5);
      goto LABEL_79;
    }
    if ( asyncResult )
      MFD3D12Sync::QueuedFreeWait::`scalar deleting destructor'(
        (MFD3D12Sync::QueuedFreeWait *)asyncResult,
        (unsigned int)v24);
    if ( !*((_DWORD *)this + 47) )
    {
      v25 = (void *)*((_QWORD *)this + 19);
      if ( v25 != (void *)-1LL )
      {
        SetEvent(v25);
        *((_QWORD *)this + 19) = -1;
      }
    }
    if ( !*((_QWORD *)this + 18) )
      goto LABEL_79;
    asyncResult = 0;
    appObject = 0;
    v39 = this;
    Microsoft::WRL::Details::SafeUnknownIncrementReference((MFD3D12Sync *)((char *)this + 68), v24);
    v5 = Microsoft::WRL::ComPtr<MFD3D12Sync>::As<IUnknown>(&v39, &appObject);
    if ( v5 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&asyncResult);
      v5 = RtwqCreateAsyncResult(appObject, (IRtwqAsyncCallback *)this + 3, 0, &asyncResult);
      if ( v5 >= 0 )
      {
        (*(void (__fastcall **)(_QWORD, IRtwqAsyncResult *))(**((_QWORD **)this + 18) + 32LL))(
          *((_QWORD *)this + 18),
          asyncResult);
        goto LABEL_61;
      }
      v29 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v29 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v30 = CallStackTracing::GetThreadRelativeContext(v29);
        if ( *((_DWORD *)v30 + 499) != v5 )
          CallStackContext::TraceFailure(v30, "MFD3D12Sync::OnFreeFenceSignaled", 319, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_61;
      v28 = 70;
    }
    else
    {
      v26 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v26 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext(v26);
        if ( *((_DWORD *)v27 + 499) != v5 )
          CallStackContext::TraceFailure(v27, "MFD3D12Sync::OnFreeFenceSignaled", 318, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_61;
      v28 = 69;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids, this, v5);
LABEL_61:
    Microsoft::WRL::ComPtr<MFD3D12Sync>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&appObject);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&asyncResult);
LABEL_79:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(&v37);
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
    goto LABEL_80;
  }
  v4 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v4 = CallStackTracing::s_wpInstance;
  }
  v5 = -2147024809;
  if ( *((_BYTE *)v4 + 8) )
  {
    v6 = CallStackTracing::GetThreadRelativeContext(v4);
    if ( *((_DWORD *)v6 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v6, "MFD3D12Sync::OnFreeFenceSignaled", 286, -2147024809);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids,
      this,
      -2147024809);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
LABEL_80:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&asyncResult);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800cce1c  push    rbp
0x1800cce1e  push    rbx
0x1800cce1f  push    rsi
0x1800cce20  push    rdi
0x1800cce21  push    r12
0x1800cce23  push    r13
0x1800cce25  push    r14
0x1800cce27  push    r15
0x1800cce29  mov     rbp, rsp
0x1800cce2c  sub     rsp, 68h
0x1800cce30  mov     rdi, rdx
0x1800cce33  lea     r13, aMfd3d12syncOnf; "MFD3D12Sync::OnFreeFenceSignaled"
0x1800cce3a  mov     rsi, rcx
0x1800cce3d  mov     rdx, r13; char *
0x1800cce40  mov     r8d, 11Bh; int
0x1800cce46  lea     rcx, [rbp+asyncResult]; this
0x1800cce4a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cce4f  lea     r15, [rsi+50h]
0x1800cce53  mov     rcx, r15; lpCriticalSection
0x1800cce56  call    cs:__imp_EnterCriticalSection
0x1800cce5c  xor     r12d, r12d
0x1800cce5f  test    rdi, rdi
0x1800cce62  jnz     short loc_1800CCEE2
0x1800cce64  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cce6b  test    rcx, rcx
0x1800cce6e  jnz     short loc_1800CCE7C
0x1800cce70  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cce75  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cce7c  mov     edi, 80070057h
0x1800cce81  cmp     [rcx+8], r12b
0x1800cce85  jz      short loc_1800CCEA8
0x1800cce87  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cce8c  cmp     [rax+7CCh], edi
0x1800cce92  jz      short loc_1800CCEA8
0x1800cce94  mov     r9d, edi; int
0x1800cce97  mov     r8d, 11Eh; int
0x1800cce9d  mov     rdx, r13; char *
0x1800ccea0  mov     rcx, rax; this
0x1800ccea3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ccea8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cceaf  jb      short loc_1800CCED4
0x1800cceb1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cceb8  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1800ccebf  mov     edx, 3Eh ; '>'
0x1800ccec4  mov     dword ptr [rsp+68h+var_48], edi
0x1800ccec8  mov     r9, rsi
0x1800ccecb  mov     rcx, [rcx+10h]
0x1800ccecf  call    WPP_SF_qD
0x1800cced4  mov     rcx, r15; lpCriticalSection
0x1800cced7  call    cs:__imp_LeaveCriticalSection
0x1800ccedd  jmp     loc_1800CD389
0x1800ccee2  mov     rax, [rdi]
0x1800ccee5  lea     rcx, [rbp+var_28]
0x1800ccee9  mov     [rbp+arg_8], r12
0x1800cceed  mov     [rbp+var_28], r12
0x1800ccef1  mov     rbx, [rax+30h]
0x1800ccef5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ccefa  lea     rdx, [rbp+var_28]
0x1800ccefe  mov     rcx, rdi
0x1800ccf01  mov     rax, rbx
0x1800ccf04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccf09  mov     edi, eax
0x1800ccf0b  test    eax, eax
0x1800ccf0d  jns     short loc_1800CCF65
0x1800ccf0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ccf16  test    rcx, rcx
0x1800ccf19  jnz     short loc_1800CCF27
0x1800ccf1b  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800ccf20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ccf27  cmp     [rcx+8], r12b
0x1800ccf2b  jz      short loc_1800CCF4E
0x1800ccf2d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ccf32  cmp     [rax+7CCh], edi
0x1800ccf38  jz      short loc_1800CCF4E
0x1800ccf3a  mov     r9d, edi; int
0x1800ccf3d  mov     r8d, 121h; int
0x1800ccf43  mov     rdx, r13; char *
0x1800ccf46  mov     rcx, rax; this
0x1800ccf49  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ccf4e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ccf55  jb      loc_1800CD36E
0x1800ccf5b  mov     edx, 3Fh ; '?'
0x1800ccf60  jmp     loc_1800CD350
0x1800ccf65  mov     rbx, [rbp+var_28]
0x1800ccf69  lea     rcx, [rbp+arg_8]
0x1800ccf6d  mov     rax, [rbx]
0x1800ccf70  mov     rdi, [rax]
0x1800ccf73  call    ?InternalRelease@?$ComPtr@UIMFDXGISchedulerRegistration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(void)
0x1800ccf78  lea     r8, [rbp+arg_8]
0x1800ccf7c  mov     rcx, rbx
0x1800ccf7f  lea     rdx, _GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76
0x1800ccf86  mov     rax, rdi
0x1800ccf89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccf8e  mov     edi, eax
0x1800ccf90  test    eax, eax
0x1800ccf92  jns     short loc_1800CCFEA
0x1800ccf94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ccf9b  test    rcx, rcx
0x1800ccf9e  jnz     short loc_1800CCFAC
0x1800ccfa0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800ccfa5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ccfac  cmp     [rcx+8], r12b
0x1800ccfb0  jz      short loc_1800CCFD3
0x1800ccfb2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ccfb7  cmp     [rax+7CCh], edi
0x1800ccfbd  jz      short loc_1800CCFD3
0x1800ccfbf  mov     r9d, edi; int
0x1800ccfc2  mov     r8d, 122h; int
0x1800ccfc8  mov     rdx, r13; char *
0x1800ccfcb  mov     rcx, rax; this
0x1800ccfce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ccfd3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ccfda  jb      loc_1800CD36E
0x1800ccfe0  mov     edx, 40h ; '@'
0x1800ccfe5  jmp     loc_1800CD350
0x1800ccfea  mov     rbx, [rbp+arg_8]
0x1800ccfee  lea     r14, [rsi+0B0h]
0x1800ccff5  mov     rcx, r14
0x1800ccff8  mov     [rbp+asyncResult], r12
0x1800ccffc  lea     r9, [rbp+var_20]
0x1800cd000  mov     [rbp+appObject], rbx
0x1800cd004  lea     r8, [rbp+asyncResult]
0x1800cd008  lea     rdx, [rbp+appObject]
0x1800cd00c  call    ?Find@?$CTBucketHash@PEAUID3D12Fence@@PEAVQueuedFreeWait@MFD3D12Sync@@@@QEAAHAEBQEAUID3D12Fence@@AEAPEAVQueuedFreeWait@MFD3D12Sync@@AEAU_POSITION@1@@Z; CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::Find(ID3D12Fence * const &,MFD3D12Sync::QueuedFreeWait * &,CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::_POSITION &)
0x1800cd011  test    eax, eax
0x1800cd013  jnz     short loc_1800CD070
0x1800cd015  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd01c  mov     edi, 0C00D36D5h
0x1800cd021  test    rcx, rcx
0x1800cd024  jnz     short loc_1800CD032
0x1800cd026  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cd02b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cd032  cmp     [rcx+8], r12b
0x1800cd036  jz      short loc_1800CD059
0x1800cd038  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cd03d  cmp     [rax+7CCh], edi
0x1800cd043  jz      short loc_1800CD059
0x1800cd045  mov     r9d, edi; int
0x1800cd048  mov     r8d, 127h; int
0x1800cd04e  mov     rdx, r13; char *
0x1800cd051  mov     rcx, rax; this
0x1800cd054  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cd059  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cd060  jb      loc_1800CD36E
0x1800cd066  mov     edx, 41h ; 'A'
0x1800cd06b  jmp     loc_1800CD350
0x1800cd070  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800cd077  jb      short loc_1800CD0C7
0x1800cd079  mov     rcx, [rsi+80h]
0x1800cd080  mov     rax, [rcx]
0x1800cd083  mov     rax, [rax+40h]
0x1800cd087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd08c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cd093  mov     r9, rsi
0x1800cd096  mov     [rsp+68h+var_30], rax
0x1800cd09b  mov     rax, [rsi+0A0h]
0x1800cd0a2  mov     [rsp+68h+var_38], rax
0x1800cd0a7  mov     eax, [rsi+0BCh]
0x1800cd0ad  mov     rcx, [rcx+10h]
0x1800cd0b1  mov     [rsp+68h+var_40], eax
0x1800cd0b5  mov     rax, [rbp+arg_8]
0x1800cd0b9  mov     [rsp+68h+var_48], rax
0x1800cd0be  call    WPP_SF_qqdII
0x1800cd0c3  mov     rbx, [rbp+arg_8]
0x1800cd0c7  cmp     [rbp+asyncResult], r12
0x1800cd0cb  jnz     short loc_1800CD128
0x1800cd0cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd0d4  mov     edi, 80004003h
0x1800cd0d9  test    rcx, rcx
0x1800cd0dc  jnz     short loc_1800CD0EA
0x1800cd0de  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cd0e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cd0ea  cmp     [rcx+8], r12b
0x1800cd0ee  jz      short loc_1800CD111
0x1800cd0f0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cd0f5  cmp     [rax+7CCh], edi
0x1800cd0fb  jz      short loc_1800CD111
0x1800cd0fd  mov     r9d, edi; int
0x1800cd100  mov     r8d, 12Bh; int
0x1800cd106  mov     rdx, r13; char *
0x1800cd109  mov     rcx, rax; this
0x1800cd10c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cd111  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cd118  jb      loc_1800CD36E
0x1800cd11e  mov     edx, 43h ; 'C'
0x1800cd123  jmp     loc_1800CD350
0x1800cd128  xorps   xmm0, xmm0
0x1800cd12b  mov     [rbp+appObject], rbx
0x1800cd12f  lea     r9, [rbp+var_20]
0x1800cd133  mov     rcx, r14
0x1800cd136  lea     r8, [rbp+asyncResult]
0x1800cd13a  lea     rdx, [rbp+appObject]
0x1800cd13e  movups  [rbp+var_20], xmm0
0x1800cd142  call    ?Find@?$CTBucketHash@PEAUID3D12Fence@@PEAVQueuedFreeWait@MFD3D12Sync@@@@QEAAHAEBQEAUID3D12Fence@@AEAPEAVQueuedFreeWait@MFD3D12Sync@@AEAU_POSITION@1@@Z; CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::Find(ID3D12Fence * const &,MFD3D12Sync::QueuedFreeWait * &,CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::_POSITION &)
0x1800cd147  test    eax, eax
0x1800cd149  jz      loc_1800CD2FE
0x1800cd14f  lea     r9, [rbp+asyncResult]
0x1800cd153  mov     [rbp+appObject], r12
0x1800cd157  lea     r8, [rbp+appObject]
0x1800cd15b  mov     rcx, r14
0x1800cd15e  lea     rdx, [rbp+var_20]
0x1800cd162  call    ?Remove@?$CTBucketHash@PEAUID3D12Fence@@PEAVQueuedFreeWait@MFD3D12Sync@@@@QEAAHAEAU_POSITION@1@AEAPEAUID3D12Fence@@AEAPEAVQueuedFreeWait@MFD3D12Sync@@@Z; CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::Remove(CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::_POSITION &,ID3D12Fence * &,MFD3D12Sync::QueuedFreeWait * &)
0x1800cd167  test    eax, eax
0x1800cd169  jz      loc_1800CD2FE
0x1800cd16f  mov     rcx, [rbp+asyncResult]; this
0x1800cd173  test    rcx, rcx
0x1800cd176  jz      short loc_1800CD17D
0x1800cd178  call    ??_GQueuedFreeWait@MFD3D12Sync@@QEAAPEAXI@Z; MFD3D12Sync::QueuedFreeWait::`scalar deleting destructor'(uint)
0x1800cd17d  cmp     [rsi+0BCh], r12d
0x1800cd184  jnz     short loc_1800CD1A4
0x1800cd186  mov     rcx, [rsi+98h]; hEvent
0x1800cd18d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800cd191  jz      short loc_1800CD1A4
0x1800cd193  call    cs:__imp_SetEvent
0x1800cd199  mov     qword ptr [rsi+98h], 0FFFFFFFFFFFFFFFFh
0x1800cd1a4  cmp     [rsi+90h], r12
0x1800cd1ab  jz      loc_1800CD36E
0x1800cd1b1  lea     rcx, [rsi+44h]; this
0x1800cd1b5  mov     [rbp+asyncResult], r12
0x1800cd1b9  mov     [rbp+appObject], r12
0x1800cd1bd  mov     [rbp+arg_18], rsi
0x1800cd1c1  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x1800cd1c6  lea     rdx, [rbp+appObject]
0x1800cd1ca  lea     rcx, [rbp+arg_18]
0x1800cd1ce  call    ??$As@UIUnknown@@@?$ComPtr@VMFD3D12Sync@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<MFD3D12Sync>::As<IUnknown>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>)
0x1800cd1d3  mov     edi, eax
0x1800cd1d5  test    eax, eax
0x1800cd1d7  jns     loc_1800CD268
0x1800cd1dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd1e4  test    rcx, rcx
0x1800cd1e7  jnz     short loc_1800CD1F5
0x1800cd1e9  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cd1ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cd1f5  cmp     [rcx+8], r12b
0x1800cd1f9  jz      short loc_1800CD21C
0x1800cd1fb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cd200  cmp     [rax+7CCh], edi
0x1800cd206  jz      short loc_1800CD21C
0x1800cd208  mov     r9d, edi; int
0x1800cd20b  mov     r8d, 13Eh; int
0x1800cd211  mov     rdx, r13; char *
0x1800cd214  mov     rcx, rax; this
0x1800cd217  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cd21c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cd223  jb      short loc_1800CD248
0x1800cd225  mov     edx, 45h ; 'E'
0x1800cd22a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cd231  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1800cd238  mov     r9, rsi
0x1800cd23b  mov     dword ptr [rsp+68h+var_48], edi
0x1800cd23f  mov     rcx, [rcx+10h]
0x1800cd243  call    WPP_SF_qD
0x1800cd248  lea     rcx, [rbp+arg_18]
0x1800cd24c  call    ?InternalRelease@?$ComPtr@VMFD3D12Sync@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<MFD3D12Sync>::InternalRelease(void)
0x1800cd251  lea     rcx, [rbp+appObject]
0x1800cd255  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd25a  lea     rcx, [rbp+asyncResult]
0x1800cd25e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd263  jmp     loc_1800CD36E
0x1800cd268  lea     rcx, [rbp+asyncResult]
0x1800cd26c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd271  mov     rcx, [rbp+appObject]; appObject
0x1800cd275  lea     rdx, [rsi+48h]; callback
0x1800cd279  lea     r9, [rbp+asyncResult]; asyncResult
0x1800cd27d  xor     r8d, r8d; appState
0x1800cd280  call    cs:__imp_RtwqCreateAsyncResult
0x1800cd286  mov     edi, eax
0x1800cd288  test    eax, eax
0x1800cd28a  jns     short loc_1800CD2E2
0x1800cd28c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd293  test    rcx, rcx
0x1800cd296  jnz     short loc_1800CD2A4
0x1800cd298  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cd29d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cd2a4  cmp     [rcx+8], r12b
0x1800cd2a8  jz      short loc_1800CD2CB
0x1800cd2aa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cd2af  cmp     [rax+7CCh], edi
0x1800cd2b5  jz      short loc_1800CD2CB
0x1800cd2b7  mov     r9d, edi; int
0x1800cd2ba  mov     r8d, 13Fh; int
0x1800cd2c0  mov     rdx, r13; char *
0x1800cd2c3  mov     rcx, rax; this
0x1800cd2c6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cd2cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cd2d2  jb      loc_1800CD248
0x1800cd2d8  mov     edx, 46h ; 'F'
0x1800cd2dd  jmp     loc_1800CD22A
0x1800cd2e2  mov     rcx, [rsi+90h]
0x1800cd2e9  mov     rdx, [rbp+asyncResult]
0x1800cd2ed  mov     rax, [rcx]
0x1800cd2f0  mov     rax, [rax+20h]
0x1800cd2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd2f9  jmp     loc_1800CD248
0x1800cd2fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd305  mov     edi, 8000FFFFh
0x1800cd30a  test    rcx, rcx
0x1800cd30d  jnz     short loc_1800CD31B
0x1800cd30f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cd314  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
  ... truncated ...
```
