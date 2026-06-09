# MFD3D12Sync::SignalResourceRelease(ID3D11DeviceContext4 *)

- ea: `0x1800ce600`
- end: `0x1800cebbb`
- name: `?SignalResourceRelease@MFD3D12Sync@@UEAAJPEAUID3D11DeviceContext4@@@Z`
- size: `1467`
- prototype: `__int64 __fastcall(MFD3D12Sync *__hidden this, struct ID3D11DeviceContext4 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180061e00`
- `0x1800a09f0`
- `0x1800cacd4`
- `0x1800cded8`
- `0x1800ce600`
- `0x1800cf1a0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ce61d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ce61d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ce9a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ce9a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ceba3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ceba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce9b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce9b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ceb6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ceb6c`

## pseudocode

```c
__int64 __fastcall MFD3D12Sync::SignalResourceRelease(MFD3D12Sync *this, struct ID3D11DeviceContext4 *a2)
{
  char *v4; // r14
  CallStackTracing *v5; // rcx
  signed int v6; // ebx
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64, GUID *, __int64); // rbx
  __int64 v11; // rax
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  void (__stdcall *GetDevice)(ID3D11DeviceContext4 *, ID3D11Device **); // rbx
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HANDLE, GUID *, struct ID3D11Fence **); // rbx
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  struct CallStackContext *v24; // rax
  void *v25; // rdi
  signed int LastError; // eax
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v33; // rax
  __int64 v34; // r8
  HANDLE hObject; // [rsp+40h] [rbp-10h] BYREF
  __int64 v37; // [rsp+48h] [rbp-8h] BYREF
  void *EventW; // [rsp+90h] [rbp+40h] BYREF
  struct ID3D11Fence *v39; // [rsp+98h] [rbp+48h] BYREF
  __int64 v40; // [rsp+A0h] [rbp+50h] BYREF
  struct ID3D12Fence *v41; // [rsp+A8h] [rbp+58h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v41 = 0;
  v39 = 0;
  v40 = 0;
  v37 = 0;
  hObject = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&EventW, "MFD3D12Sync::SignalResourceRelease", 522);
  v4 = (char *)this - 24;
  if ( a2 )
  {
    v9 = *((_QWORD *)v4 + 15);
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, GUID *, __int64))(*(_QWORD *)v9 + 288LL);
    v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ID3D12Fence>>(&v41);
    v6 = v10(v9, 0, 1, &GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76, v11);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _QWORD, HANDLE *))(**((_QWORD **)v4 + 15) + 248LL))(
             *((_QWORD *)v4 + 15),
             *((_QWORD *)this + 13),
             0,
             0x10000000,
             0,
             &hObject);
      if ( v6 >= 0 )
      {
        GetDevice = a2->lpVtbl->GetDevice;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
        ((void (__fastcall *)(struct ID3D11DeviceContext4 *, __int64 *))GetDevice)(a2, &v40);
        v6 = Microsoft::WRL::ComPtr<ID3D11Device>::As<ID3D11Device5>(&v40, &v37);
        if ( v6 >= 0 )
        {
          v19 = v37;
          v20 = *(__int64 (__fastcall **)(__int64, HANDLE, GUID *, struct ID3D11Fence **))(*(_QWORD *)v37 + 536LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
          v6 = v20(v19, hObject, &GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80, &v39);
          if ( v6 >= 0 )
          {
            v6 = ((__int64 (__fastcall *)(struct ID3D11DeviceContext4 *, struct ID3D11Fence *, _QWORD))a2->lpVtbl->Signal)(
                   a2,
                   v39,
                   *((_QWORD *)v4 + 20));
            if ( v6 >= 0 )
            {
              EventW = CreateEventW(0, 1, 0, 0);
              v25 = EventW;
              if ( EventW )
                goto LABEL_61;
              LastError = GetLastError();
              v6 = LastError;
              if ( LastError > 0 )
                v6 = (unsigned __int16)LastError | 0x80070000;
              if ( v6 >= 0 )
              {
LABEL_61:
                v6 = ((__int64 (__fastcall *)(struct ID3D12Fence *, _QWORD, void *))v41->lpVtbl->SetEventOnCompletion)(
                       v41,
                       *((_QWORD *)this + 17),
                       v25);
                if ( v6 >= 0 )
                {
                  v6 = MFD3D12Sync::ScheduleFreeWait((MFD3D12Sync *)((char *)this - 24), &EventW, v41, v39);
                  if ( v6 >= 0 )
                  {
                    if ( g_wppLevels >= 0x20u )
                    {
                      v33 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 64LL))(*((_QWORD *)this + 13));
                      WPP_SF_qdII(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        104,
                        v34,
                        (char *)this - 24,
                        *((_DWORD *)this + 41),
                        *((_QWORD *)this + 17),
                        v33);
                    }
                  }
                  else
                  {
                    v31 = CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      CallStackTracing::InitInstance();
                      v31 = CallStackTracing::s_wpInstance;
                    }
                    if ( *((_BYTE *)v31 + 8) )
                    {
                      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v31);
                      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
                        CallStackContext::TraceFailure(
                          ThreadRelativeContext,
                          "MFD3D12Sync::SignalResourceRelease",
                          539,
                          v6);
                    }
                    if ( g_wppLevels )
                    {
                      v8 = 103;
                      goto LABEL_9;
                    }
                  }
                }
                else
                {
                  v29 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::InitInstance();
                    v29 = CallStackTracing::s_wpInstance;
                  }
                  if ( *((_BYTE *)v29 + 8) )
                  {
                    v30 = CallStackTracing::GetThreadRelativeContext(v29);
                    if ( *((_DWORD *)v30 + 499) != v6 )
                      CallStackContext::TraceFailure(v30, "MFD3D12Sync::SignalResourceRelease", 538, v6);
                  }
                  if ( g_wppLevels )
                  {
                    v8 = 102;
                    goto LABEL_9;
                  }
                }
              }
              else
              {
                v27 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::InitInstance();
                  v27 = CallStackTracing::s_wpInstance;
                }
                if ( *((_BYTE *)v27 + 8) )
                {
                  v28 = CallStackTracing::GetThreadRelativeContext(v27);
                  if ( *((_DWORD *)v28 + 499) != v6 )
                    CallStackContext::TraceFailure(v28, "MFD3D12Sync::SignalResourceRelease", 536, v6);
                }
                if ( g_wppLevels )
                {
                  v8 = 101;
                  goto LABEL_9;
                }
              }
            }
            else
            {
              v23 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v23 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v23 + 8) )
              {
                v24 = CallStackTracing::GetThreadRelativeContext(v23);
                if ( *((_DWORD *)v24 + 499) != v6 )
                  CallStackContext::TraceFailure(v24, "MFD3D12Sync::SignalResourceRelease", 531, v6);
              }
              if ( g_wppLevels )
              {
                v8 = 100;
                goto LABEL_9;
              }
            }
          }
          else
          {
            v21 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v21 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v21 + 8) )
            {
              v22 = CallStackTracing::GetThreadRelativeContext(v21);
              if ( *((_DWORD *)v22 + 499) != v6 )
                CallStackContext::TraceFailure(v22, "MFD3D12Sync::SignalResourceRelease", 529, v6);
            }
            if ( g_wppLevels )
            {
              v8 = 99;
              goto LABEL_9;
            }
          }
        }
        else
        {
          v17 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v17 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v17 + 8) )
          {
            v18 = CallStackTracing::GetThreadRelativeContext(v17);
            if ( *((_DWORD *)v18 + 499) != v6 )
              CallStackContext::TraceFailure(v18, "MFD3D12Sync::SignalResourceRelease", 528, v6);
          }
          if ( g_wppLevels )
          {
            v8 = 98;
            goto LABEL_9;
          }
        }
      }
      else
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
          if ( *((_DWORD *)v15 + 499) != v6 )
            CallStackContext::TraceFailure(v15, "MFD3D12Sync::SignalResourceRelease", 526, v6);
        }
        if ( g_wppLevels )
        {
          v8 = 97;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v12 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v12 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext(v12);
        if ( *((_DWORD *)v13 + 499) != v6 )
          CallStackContext::TraceFailure(v13, "MFD3D12Sync::SignalResourceRelease", 523, v6);
      }
      if ( g_wppLevels )
      {
        v8 = 96;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v5 = CallStackTracing::s_wpInstance;
    v6 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v5 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext(v5);
      if ( *((_DWORD *)v7 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v7, "MFD3D12Sync::SignalResourceRelease", 522, -2147024809);
    }
    if ( g_wppLevels )
    {
      v8 = 95;
LABEL_9:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids,
        (char *)this - 24,
        v6);
    }
  }
  if ( hObject )
    CloseHandle(hObject);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&EventW);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(&v41);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ce600  push    rbp
0x1800ce602  push    rbx
0x1800ce603  push    rdi
0x1800ce604  push    r12
0x1800ce606  push    r13
0x1800ce608  push    r14
0x1800ce60a  push    r15
0x1800ce60c  mov     rbp, rsp
0x1800ce60f  sub     rsp, 50h
0x1800ce613  mov     r15, rcx
0x1800ce616  mov     r12, rdx
0x1800ce619  add     rcx, 38h ; '8'; lpCriticalSection
0x1800ce61d  call    cs:__imp_EnterCriticalSection
0x1800ce623  xor     edi, edi
0x1800ce625  lea     rdx, aMfd3d12syncSig_1; "MFD3D12Sync::SignalResourceRelease"
0x1800ce62c  mov     r8d, 20Ah; int
0x1800ce632  mov     [rbp+arg_18], rdi
0x1800ce636  lea     rcx, [rbp+arg_0]; this
0x1800ce63a  mov     [rbp+arg_8], rdi
0x1800ce63e  mov     [rbp+arg_10], rdi
0x1800ce642  mov     [rbp+var_8], rdi
0x1800ce646  mov     [rbp+hObject], rdi
0x1800ce64a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ce64f  lea     r14, [r15-18h]
0x1800ce653  test    r12, r12
0x1800ce656  jnz     short loc_1800CE6D5
0x1800ce658  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce65f  mov     ebx, 80070057h
0x1800ce664  test    rcx, rcx
0x1800ce667  jnz     short loc_1800CE675
0x1800ce669  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800ce66e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce675  cmp     [rcx+8], dil
0x1800ce679  jz      short loc_1800CE6A0
0x1800ce67b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce680  cmp     [rax+7CCh], ebx
0x1800ce686  jz      short loc_1800CE6A0
0x1800ce688  mov     r9d, ebx; int
0x1800ce68b  lea     rdx, aMfd3d12syncSig_1; "MFD3D12Sync::SignalResourceRelease"
0x1800ce692  mov     r8d, 20Ah; int
0x1800ce698  mov     rcx, rax; this
0x1800ce69b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce6a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce6a7  jb      loc_1800CEB63
0x1800ce6ad  mov     edx, 5Fh ; '_'
0x1800ce6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce6b9  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1800ce6c0  mov     r9, r14
0x1800ce6c3  mov     dword ptr [rsp+50h+var_30], ebx
0x1800ce6c7  mov     rcx, [rcx+10h]
0x1800ce6cb  call    WPP_SF_qD
0x1800ce6d0  jmp     loc_1800CEB63
0x1800ce6d5  mov     rdi, [r14+78h]
0x1800ce6d9  lea     rcx, [rbp+arg_18]
0x1800ce6dd  mov     rax, [rdi]
0x1800ce6e0  mov     rbx, [rax+120h]
0x1800ce6e7  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UID3D12Fence@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UID3D12Fence@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ID3D12Fence>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ID3D12Fence>>)
0x1800ce6ec  xor     edx, edx
0x1800ce6ee  mov     [rsp+50h+var_30], rax
0x1800ce6f3  lea     r9, _GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76
0x1800ce6fa  mov     rcx, rdi
0x1800ce6fd  mov     rax, rbx
0x1800ce700  lea     r8d, [rdx+1]
0x1800ce704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce709  xor     edi, edi
0x1800ce70b  mov     ebx, eax
0x1800ce70d  test    eax, eax
0x1800ce70f  jns     short loc_1800CE76B
0x1800ce711  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce718  test    rcx, rcx
0x1800ce71b  jnz     short loc_1800CE729
0x1800ce71d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800ce722  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce729  cmp     [rcx+8], dil
0x1800ce72d  jz      short loc_1800CE754
0x1800ce72f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce734  cmp     [rax+7CCh], ebx
0x1800ce73a  jz      short loc_1800CE754
0x1800ce73c  mov     r9d, ebx; int
0x1800ce73f  lea     rdx, aMfd3d12syncSig_1; "MFD3D12Sync::SignalResourceRelease"
0x1800ce746  mov     r8d, 20Bh; int
0x1800ce74c  mov     rcx, rax; this
0x1800ce74f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce754  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce75b  jb      loc_1800CEB63
0x1800ce761  mov     edx, 60h ; '`'
0x1800ce766  jmp     loc_1800CE6B2
0x1800ce76b  mov     rcx, [r14+78h]
0x1800ce76f  lea     rdx, [rbp+hObject]
0x1800ce773  mov     [rsp+50h+var_28], rdx
0x1800ce778  mov     r9d, 10000000h
0x1800ce77e  mov     rdx, [r15+68h]
0x1800ce782  xor     r8d, r8d
0x1800ce785  mov     [rsp+50h+var_30], rdi
0x1800ce78a  mov     rax, [rcx]
0x1800ce78d  mov     rax, [rax+0F8h]
0x1800ce794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce799  mov     ebx, eax
0x1800ce79b  test    eax, eax
0x1800ce79d  jns     short loc_1800CE7F9
0x1800ce79f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce7a6  test    rcx, rcx
0x1800ce7a9  jnz     short loc_1800CE7B7
0x1800ce7ab  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800ce7b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce7b7  cmp     [rcx+8], dil
0x1800ce7bb  jz      short loc_1800CE7E2
0x1800ce7bd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce7c2  cmp     [rax+7CCh], ebx
0x1800ce7c8  jz      short loc_1800CE7E2
0x1800ce7ca  mov     r9d, ebx; int
0x1800ce7cd  lea     rdx, aMfd3d12syncSig_1; "MFD3D12Sync::SignalResourceRelease"
0x1800ce7d4  mov     r8d, 20Eh; int
0x1800ce7da  mov     rcx, rax; this
0x1800ce7dd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce7e2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce7e9  jb      loc_1800CEB63
0x1800ce7ef  mov     edx, 61h ; 'a'
0x1800ce7f4  jmp     loc_1800CE6B2
0x1800ce7f9  mov     rax, [r12]
0x1800ce7fd  lea     rcx, [rbp+arg_10]
0x1800ce801  mov     rbx, [rax+18h]
0x1800ce805  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ce80a  lea     rdx, [rbp+arg_10]
0x1800ce80e  mov     rcx, r12
0x1800ce811  mov     rax, rbx
0x1800ce814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce819  lea     rdx, [rbp+var_8]
0x1800ce81d  lea     rcx, [rbp+arg_10]
0x1800ce821  call    ??$As@UID3D11Device5@@@?$ComPtr@UID3D11Device@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UID3D11Device5@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Device>::As<ID3D11Device5>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ID3D11Device5>>)
0x1800ce826  mov     ebx, eax
0x1800ce828  test    eax, eax
0x1800ce82a  jns     short loc_1800CE886
0x1800ce82c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce833  test    rcx, rcx
0x1800ce836  jnz     short loc_1800CE844
0x1800ce838  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800ce83d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce844  cmp     [rcx+8], dil
0x1800ce848  jz      short loc_1800CE86F
0x1800ce84a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce84f  cmp     [rax+7CCh], ebx
0x1800ce855  jz      short loc_1800CE86F
0x1800ce857  mov     r9d, ebx; int
0x1800ce85a  lea     rdx, aMfd3d12syncSig_1; "MFD3D12Sync::SignalResourceRelease"
0x1800ce861  mov     r8d, 210h; int
0x1800ce867  mov     rcx, rax; this
0x1800ce86a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce86f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce876  jb      loc_1800CEB63
0x1800ce87c  mov     edx, 62h ; 'b'
0x1800ce881  jmp     loc_1800CE6B2
0x1800ce886  mov     rdi, [rbp+var_8]
0x1800ce88a  lea     rcx, [rbp+arg_8]
0x1800ce88e  mov     rax, [rdi]
0x1800ce891  mov     rbx, [rax+218h]
0x1800ce898  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ce89d  mov     rdx, [rbp+hObject]
0x1800ce8a1  lea     r9, [rbp+arg_8]
0x1800ce8a5  lea     r8, _GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80
0x1800ce8ac  mov     rcx, rdi
0x1800ce8af  mov     rax, rbx
0x1800ce8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce8b7  xor     edi, edi
0x1800ce8b9  mov     ebx, eax
0x1800ce8bb  test    eax, eax
0x1800ce8bd  jns     short loc_1800CE919
0x1800ce8bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce8c6  test    rcx, rcx
0x1800ce8c9  jnz     short loc_1800CE8D7
0x1800ce8cb  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800ce8d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce8d7  cmp     [rcx+8], dil
0x1800ce8db  jz      short loc_1800CE902
0x1800ce8dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce8e2  cmp     [rax+7CCh], ebx
0x1800ce8e8  jz      short loc_1800CE902
0x1800ce8ea  mov     r9d, ebx; int
0x1800ce8ed  lea     rdx, aMfd3d12syncSig_1; "MFD3D12Sync::SignalResourceRelease"
0x1800ce8f4  mov     r8d, 211h; int
0x1800ce8fa  mov     rcx, rax; this
0x1800ce8fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce902  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce909  jb      loc_1800CEB63
0x1800ce90f  mov     edx, 63h ; 'c'
0x1800ce914  jmp     loc_1800CE6B2
0x1800ce919  mov     rax, [r12]
0x1800ce91d  mov     rcx, r12
0x1800ce920  mov     r8, [r14+0A0h]
0x1800ce927  mov     rdx, [rbp+arg_8]
0x1800ce92b  mov     rax, [rax+498h]
0x1800ce932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce937  mov     ebx, eax
0x1800ce939  test    eax, eax
0x1800ce93b  jns     short loc_1800CE997
0x1800ce93d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce944  test    rcx, rcx
0x1800ce947  jnz     short loc_1800CE955
0x1800ce949  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800ce94e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce955  cmp     [rcx+8], dil
0x1800ce959  jz      short loc_1800CE980
0x1800ce95b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce960  cmp     [rax+7CCh], ebx
0x1800ce966  jz      short loc_1800CE980
0x1800ce968  mov     r9d, ebx; int
0x1800ce96b  lea     rdx, aMfd3d12syncSig_1; "MFD3D12Sync::SignalResourceRelease"
0x1800ce972  mov     r8d, 213h; int
0x1800ce978  mov     rcx, rax; this
0x1800ce97b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce980  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce987  jb      loc_1800CEB63
0x1800ce98d  mov     edx, 64h ; 'd'
0x1800ce992  jmp     loc_1800CE6B2
0x1800ce997  xor     r9d, r9d; lpName
0x1800ce99a  xor     r8d, r8d; bInitialState
0x1800ce99d  xor     ecx, ecx; lpEventAttributes
0x1800ce99f  lea     edx, [r9+1]; bManualReset
0x1800ce9a3  call    cs:__imp_CreateEventW
0x1800ce9a9  mov     [rbp+arg_0], rax
0x1800ce9ad  mov     rdi, rax
0x1800ce9b0  test    rax, rax
0x1800ce9b3  jnz     short loc_1800CEA2A
0x1800ce9b5  call    cs:__imp_GetLastError
0x1800ce9bb  mov     ebx, eax
0x1800ce9bd  test    eax, eax
0x1800ce9bf  jle     short loc_1800CE9CA
0x1800ce9c1  movzx   ebx, ax
0x1800ce9c4  or      ebx, 80070000h
0x1800ce9ca  test    ebx, ebx
0x1800ce9cc  jns     short loc_1800CEA2A
0x1800ce9ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce9d5  xor     edi, edi
0x1800ce9d7  test    rcx, rcx
0x1800ce9da  jnz     short loc_1800CE9E8
0x1800ce9dc  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800ce9e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce9e8  cmp     [rcx+8], dil
0x1800ce9ec  jz      short loc_1800CEA13
0x1800ce9ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce9f3  cmp     [rax+7CCh], ebx
0x1800ce9f9  jz      short loc_1800CEA13
0x1800ce9fb  mov     r9d, ebx; int
0x1800ce9fe  lea     rdx, aMfd3d12syncSig_1; "MFD3D12Sync::SignalResourceRelease"
0x1800cea05  mov     r8d, 218h; int
0x1800cea0b  mov     rcx, rax; this
0x1800cea0e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cea13  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cea1a  jb      loc_1800CEB63
0x1800cea20  mov     edx, 65h ; 'e'
0x1800cea25  jmp     loc_1800CE6B2
0x1800cea2a  mov     rcx, [rbp+arg_18]
0x1800cea2e  mov     r8, rdi
0x1800cea31  mov     rdx, [r15+88h]
0x1800cea38  mov     rax, [rcx]
0x1800cea3b  mov     rax, [rax+48h]
0x1800cea3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cea44  xor     edi, edi
0x1800cea46  mov     ebx, eax
0x1800cea48  test    eax, eax
0x1800cea4a  jns     short loc_1800CEAA6
0x1800cea4c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cea53  test    rcx, rcx
0x1800cea56  jnz     short loc_1800CEA64
0x1800cea58  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cea5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cea64  cmp     [rcx+8], dil
0x1800cea68  jz      short loc_1800CEA8F
0x1800cea6a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cea6f  cmp     [rax+7CCh], ebx
0x1800cea75  jz      short loc_1800CEA8F
0x1800cea77  mov     r9d, ebx; int
0x1800cea7a  lea     rdx, aMfd3d12syncSig_1; "MFD3D12Sync::SignalResourceRelease"
0x1800cea81  mov     r8d, 21Ah; int
0x1800cea87  mov     rcx, rax; this
0x1800cea8a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cea8f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cea96  jb      loc_1800CEB63
0x1800cea9c  mov     edx, 66h ; 'f'
0x1800ceaa1  jmp     loc_1800CE6B2
0x1800ceaa6  mov     r9, [rbp+arg_8]; struct ID3D11Fence *
0x1800ceaaa  lea     rdx, [rbp+arg_0]; void **
0x1800ceaae  mov     r8, [rbp+arg_18]; struct ID3D12Fence *
0x1800ceab2  mov     rcx, r14; this
0x1800ceab5  call    ?ScheduleFreeWait@MFD3D12Sync@@IEAAJAEAPEAXPEAUID3D12Fence@@PEAUID3D11Fence@@@Z; MFD3D12Sync::ScheduleFreeWait(void * &,ID3D12Fence *,ID3D11Fence *)
0x1800ceaba  mov     ebx, eax
0x1800ceabc  test    eax, eax
0x1800ceabe  jns     short loc_1800CEB16
0x1800ceac0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ceac7  test    rcx, rcx
0x1800ceaca  jnz     short loc_1800CEAD8
0x1800ceacc  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cead1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cead8  cmp     [rcx+8], dil
0x1800ceadc  jz      short loc_1800CEB03
0x1800ceade  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ceae3  cmp     [rax+7CCh], ebx
0x1800ceae9  jz      short loc_1800CEB03
0x1800ceaeb  mov     r9d, ebx; int
0x1800ceaee  lea     rdx, aMfd3d12syncSig_1; "MFD3D12Sync::SignalResourceRelease"
  ... truncated ...
```
