# CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator(void)

- ea: `0x1800b72bc`
- end: `0x1800b7b01`
- name: `?CreateVideoSampleAllocator@CRolling420FrameStitcherMFTDataHandler@@IEAAJXZ`
- size: `2117`
- prototype: `__int64 __fastcall(CRolling420FrameStitcherMFTDataHandler *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003f6c0`
- `0x18004e3a0`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180014be0`
- `0x18003639c`
- `0x18004e280`
- `0x18007355c`
- `0x1800b72bc`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x1800b7311`
- `MFPlat!MFCreateAttributes` at `0x1800b7311`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b732d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b73fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b74af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7561`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7613`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7710`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b77ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b78ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7954`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7a13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b732d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b73fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b74af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7561`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7613`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7710`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b77ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b78ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7954`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7a13`

## string_xrefs

- `0x1800b72d2`: `CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator`

## pseudocode

```c
__int64 __fastcall CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator(
        CRolling420FrameStitcherMFTDataHandler *this)
{
  HRESULT v2; // edi
  __int64 *v3; // rcx
  CallStackTracing *v4; // rax
  struct CallStackContext *v5; // rax
  __int64 v6; // rdx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  unsigned int v19; // ebx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v27)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v37; // rbx
  __int64 v39; // [rsp+30h] [rbp-10h] BYREF
  struct IMFAttributes *v40; // [rsp+38h] [rbp-8h] BYREF
  __int64 v41; // [rsp+78h] [rbp+38h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+80h] [rbp+40h] BYREF
  __int64 v43; // [rsp+88h] [rbp+48h] BYREF

  ppMFAttributes = 0;
  v40 = 0;
  v43 = 0;
  v39 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v41,
    "CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator",
    398);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
  v2 = MFCreateAttributes(&ppMFAttributes, 5u);
  if ( v2 >= 0 )
  {
    v2 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
           ppMFAttributes,
           MF_SA_D3D11_USAGE,
           0);
    if ( v2 >= 0 )
    {
      v2 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
             ppMFAttributes,
             MF_SA_D3D11_BINDFLAGS,
             40);
      if ( v2 >= 0 )
      {
        v2 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
               ppMFAttributes,
               MF_SA_D3D11_SHARED,
               0);
        if ( v2 >= 0 )
        {
          v2 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
                 ppMFAttributes,
                 MF_SA_D3D11_SHARED_WITHOUT_MUTEX,
                 0);
          if ( v2 >= 0 )
          {
            v19 = MFGetAttributeUINT32(*(_QWORD *)(*((_QWORD *)this + 1) + 80LL), MF_MT_SECURE, 0);
            if ( !v19 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
              if ( (int)CRolling420FrameStitcherMFTDataHandler::GetAttributes(this, &v40) >= 0 )
                v19 = MFGetAttributeUINT32(v40, MFT_USING_HARDWARE_DRM, 0);
            }
            v2 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
                   ppMFAttributes,
                   MF_SA_D3D11_HW_PROTECTED,
                   v19);
            if ( v2 >= 0 )
            {
              if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 42),
                  58,
                  &WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids,
                  this,
                  v19);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
              v2 = dlMFCreateVideoSampleAllocatorEx(&GUID_545b3a48_3283_4f62_866f_a62d8f598f9f, &v43);
              if ( v2 >= 0 )
              {
                v26 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
                v27 = **v26;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
                v2 = v27(v26, &GUID_00000000_0000_0000_c000_000000000046, &v39);
                if ( v2 >= 0 )
                {
                  v2 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, v39);
                  if ( v2 >= 0 )
                  {
                    v2 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, IMFAttributes *, _QWORD))(*(_QWORD *)v43 + 56LL))(
                           v43,
                           1,
                           10,
                           ppMFAttributes,
                           *(_QWORD *)(*((_QWORD *)this + 1) + 80LL));
                    if ( v2 >= 0 )
                    {
                      v37 = v43;
                      if ( *((_QWORD *)this + 15) != v43 )
                      {
                        if ( v43 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
                        v41 = *((_QWORD *)this + 15);
                        *((_QWORD *)this + 15) = v37;
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
                      }
                    }
                    else
                    {
                      v34 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                        CallStackTracing::s_wpInstance = v35;
                        if ( v35
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(
                               v35,
                               2032) )
                        {
                          v34 = (__int64 *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v34 = &qword_180153440;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                        }
                      }
                      if ( *((_BYTE *)v34 + 8) )
                      {
                        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
                        if ( *((_DWORD *)ThreadRelativeContext + 499) != v2 )
                          CallStackContext::TraceFailure(
                            ThreadRelativeContext,
                            "CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator",
                            415,
                            v2);
                      }
                      if ( g_wppLevels )
                      {
                        v6 = 62;
                        goto LABEL_12;
                      }
                    }
                  }
                  else
                  {
                    v31 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                      CallStackTracing::s_wpInstance = v32;
                      if ( v32
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(
                             v32,
                             2032) )
                      {
                        v31 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v31 = &qword_180153440;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                      }
                    }
                    if ( *((_BYTE *)v31 + 8) )
                    {
                      v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
                      if ( *((_DWORD *)v33 + 499) != v2 )
                        CallStackContext::TraceFailure(
                          v33,
                          "CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator",
                          414,
                          v2);
                    }
                    if ( g_wppLevels )
                    {
                      v6 = 61;
                      goto LABEL_12;
                    }
                  }
                }
                else
                {
                  v28 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                    CallStackTracing::s_wpInstance = v29;
                    if ( v29
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
                    {
                      v28 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v28 = &qword_180153440;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                    }
                  }
                  if ( *((_BYTE *)v28 + 8) )
                  {
                    v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
                    if ( *((_DWORD *)v30 + 499) != v2 )
                      CallStackContext::TraceFailure(
                        v30,
                        "CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator",
                        413,
                        v2);
                  }
                  if ( g_wppLevels )
                  {
                    v6 = 60;
                    goto LABEL_12;
                  }
                }
              }
              else
              {
                v23 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v24;
                  if ( v24
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
                  {
                    v23 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v23 = &qword_180153440;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                  }
                }
                if ( *((_BYTE *)v23 + 8) )
                {
                  v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
                  if ( *((_DWORD *)v25 + 499) != v2 )
                    CallStackContext::TraceFailure(
                      v25,
                      "CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator",
                      412,
                      v2);
                }
                if ( g_wppLevels )
                {
                  v6 = 59;
                  goto LABEL_12;
                }
              }
            }
            else
            {
              v20 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v21;
                if ( v21
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
                {
                  v20 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v20 = &qword_180153440;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                }
              }
              if ( *((_BYTE *)v20 + 8) )
              {
                v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
                if ( *((_DWORD *)v22 + 499) != v2 )
                  CallStackContext::TraceFailure(
                    v22,
                    "CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator",
                    409,
                    v2);
              }
              if ( g_wppLevels )
              {
                v6 = 57;
                goto LABEL_12;
              }
            }
          }
          else
          {
            v16 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v17;
              if ( v17
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
              {
                v16 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v16 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v16 + 8) )
            {
              v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
              if ( *((_DWORD *)v18 + 499) != v2 )
                CallStackContext::TraceFailure(
                  v18,
                  "CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator",
                  402,
                  v2);
            }
            if ( g_wppLevels )
            {
              v6 = 56;
              goto LABEL_12;
            }
          }
        }
        else
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v14;
            if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
            {
              v13 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v13 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v13 + 8) )
          {
            v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
            if ( *((_DWORD *)v15 + 499) != v2 )
              CallStackContext::TraceFailure(
                v15,
                "CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator",
                401,
                v2);
          }
          if ( g_wppLevels )
          {
            v6 = 55;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v11;
          if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
          {
            v10 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v10 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v10 + 8) )
        {
          v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
          if ( *((_DWORD *)v12 + 499) != v2 )
            CallStackContext::TraceFailure(
              v12,
              "CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator",
              400,
              v2);
        }
        if ( g_wppLevels )
        {
          v6 = 54;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v7 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        {
          v7 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v7 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
        if ( *((_DWORD *)v9 + 499) != v2 )
          CallStackContext::TraceFailure(
            v9,
            "CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator",
            399,
            v2);
      }
      if ( g_wppLevels )
      {
        v6 = 53;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v3 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v4 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v4;
      if ( v4 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v4 + 8LL))(v4, 2032) )
      {
        v3 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v3 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v3 + 8) )
    {
      v5 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
      if ( *((_DWORD *)v5 + 499) != v2 )
        CallStackContext::TraceFailure(
          v5,
          "CRolling420FrameStitcherMFTDataHandler::CreateVideoSampleAllocator",
          398,
          v2);
    }
    if ( g_wppLevels )
    {
      v6 = 52;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids, this, v2);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800b72bc  mov     [rsp-28h+arg_0], rbx
0x1800b72c1  push    rbp
0x1800b72c2  push    rsi
0x1800b72c3  push    rdi
0x1800b72c4  push    r14
0x1800b72c6  push    r15
0x1800b72c8  mov     rbp, rsp
0x1800b72cb  sub     rsp, 40h
0x1800b72cf  xor     r14d, r14d
0x1800b72d2  lea     r15, aCrolling420fra_5; "CRolling420FrameStitcherMFTDataHandler:"...
0x1800b72d9  mov     rsi, rcx
0x1800b72dc  mov     [rbp+ppMFAttributes], r14
0x1800b72e0  mov     ebx, 18Eh
0x1800b72e5  mov     [rbp+var_8], r14
0x1800b72e9  mov     r8d, ebx; int
0x1800b72ec  mov     [rbp+arg_18], r14
0x1800b72f0  mov     rdx, r15; char *
0x1800b72f3  mov     [rbp+var_10], r14
0x1800b72f7  lea     rcx, [rbp+arg_8]; this
0x1800b72fb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b7300  lea     rcx, [rbp+ppMFAttributes]
0x1800b7304  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7309  lea     edx, [r14+5]; cInitialSize
0x1800b730d  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x1800b7311  call    cs:__imp_MFCreateAttributes
0x1800b7317  mov     edi, eax
0x1800b7319  test    eax, eax
0x1800b731b  jns     loc_1800B73C7
0x1800b7321  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7328  test    rcx, rcx
0x1800b732b  jnz     short loc_1800B736E
0x1800b732d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7333  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b733a  mov     rcx, rax
0x1800b733d  test    rax, rax
0x1800b7340  jz      short loc_1800B7360
0x1800b7342  mov     rax, [rax]
0x1800b7345  mov     edx, 7F0h
0x1800b734a  mov     rax, [rax+8]
0x1800b734e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7353  test    eax, eax
0x1800b7355  jz      short loc_1800B7360
0x1800b7357  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b735e  jmp     short loc_1800B736E
0x1800b7360  lea     rcx, qword_180153440; this
0x1800b7367  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b736e  cmp     [rcx+8], r14b
0x1800b7372  jz      short loc_1800B7392
0x1800b7374  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b7379  cmp     [rax+7CCh], edi
0x1800b737f  jz      short loc_1800B7392
0x1800b7381  mov     r9d, edi; int
0x1800b7384  mov     r8d, ebx; int
0x1800b7387  mov     rdx, r15; char *
0x1800b738a  mov     rcx, rax; this
0x1800b738d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7392  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b7399  jb      loc_1800B7AC1
0x1800b739f  mov     edx, 34h ; '4'
0x1800b73a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b73ab  lea     r8, WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids
0x1800b73b2  mov     r9, rsi
0x1800b73b5  mov     dword ptr [rsp+40h+var_20], edi
0x1800b73b9  mov     rcx, [rcx+10h]
0x1800b73bd  call    WPP_SF_qD
0x1800b73c2  jmp     loc_1800B7AC1
0x1800b73c7  mov     rcx, [rbp+ppMFAttributes]
0x1800b73cb  lea     rdx, MF_SA_D3D11_USAGE
0x1800b73d2  xor     r8d, r8d
0x1800b73d5  mov     rax, [rcx]
0x1800b73d8  mov     rax, [rax+0A8h]
0x1800b73df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b73e4  mov     edi, eax
0x1800b73e6  test    eax, eax
0x1800b73e8  jns     loc_1800B7479
0x1800b73ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b73f5  test    rcx, rcx
0x1800b73f8  jnz     short loc_1800B743B
0x1800b73fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7400  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7407  mov     rcx, rax
0x1800b740a  test    rax, rax
0x1800b740d  jz      short loc_1800B742D
0x1800b740f  mov     rax, [rax]
0x1800b7412  mov     edx, 7F0h
0x1800b7417  mov     rax, [rax+8]
0x1800b741b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7420  test    eax, eax
0x1800b7422  jz      short loc_1800B742D
0x1800b7424  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b742b  jmp     short loc_1800B743B
0x1800b742d  lea     rcx, qword_180153440; this
0x1800b7434  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b743b  cmp     [rcx+8], r14b
0x1800b743f  jz      short loc_1800B7462
0x1800b7441  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b7446  cmp     [rax+7CCh], edi
0x1800b744c  jz      short loc_1800B7462
0x1800b744e  mov     r9d, edi; int
0x1800b7451  mov     r8d, 18Fh; int
0x1800b7457  mov     rdx, r15; char *
0x1800b745a  mov     rcx, rax; this
0x1800b745d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7462  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b7469  jb      loc_1800B7AC1
0x1800b746f  mov     edx, 35h ; '5'
0x1800b7474  jmp     loc_1800B73A4
0x1800b7479  mov     rcx, [rbp+ppMFAttributes]
0x1800b747d  lea     rdx, MF_SA_D3D11_BINDFLAGS
0x1800b7484  mov     r8d, 28h ; '('
0x1800b748a  mov     rax, [rcx]
0x1800b748d  mov     rax, [rax+0A8h]
0x1800b7494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7499  mov     edi, eax
0x1800b749b  test    eax, eax
0x1800b749d  jns     loc_1800B752E
0x1800b74a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b74aa  test    rcx, rcx
0x1800b74ad  jnz     short loc_1800B74F0
0x1800b74af  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b74b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b74bc  mov     rcx, rax
0x1800b74bf  test    rax, rax
0x1800b74c2  jz      short loc_1800B74E2
0x1800b74c4  mov     rax, [rax]
0x1800b74c7  mov     edx, 7F0h
0x1800b74cc  mov     rax, [rax+8]
0x1800b74d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b74d5  test    eax, eax
0x1800b74d7  jz      short loc_1800B74E2
0x1800b74d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b74e0  jmp     short loc_1800B74F0
0x1800b74e2  lea     rcx, qword_180153440; this
0x1800b74e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b74f0  cmp     [rcx+8], r14b
0x1800b74f4  jz      short loc_1800B7517
0x1800b74f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b74fb  cmp     [rax+7CCh], edi
0x1800b7501  jz      short loc_1800B7517
0x1800b7503  mov     r9d, edi; int
0x1800b7506  mov     r8d, 190h; int
0x1800b750c  mov     rdx, r15; char *
0x1800b750f  mov     rcx, rax; this
0x1800b7512  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7517  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b751e  jb      loc_1800B7AC1
0x1800b7524  mov     edx, 36h ; '6'
0x1800b7529  jmp     loc_1800B73A4
0x1800b752e  mov     rcx, [rbp+ppMFAttributes]
0x1800b7532  lea     rdx, MF_SA_D3D11_SHARED
0x1800b7539  xor     r8d, r8d
0x1800b753c  mov     rax, [rcx]
0x1800b753f  mov     rax, [rax+0A8h]
0x1800b7546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b754b  mov     edi, eax
0x1800b754d  test    eax, eax
0x1800b754f  jns     loc_1800B75E0
0x1800b7555  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b755c  test    rcx, rcx
0x1800b755f  jnz     short loc_1800B75A2
0x1800b7561  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7567  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b756e  mov     rcx, rax
0x1800b7571  test    rax, rax
0x1800b7574  jz      short loc_1800B7594
0x1800b7576  mov     rax, [rax]
0x1800b7579  mov     edx, 7F0h
0x1800b757e  mov     rax, [rax+8]
0x1800b7582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7587  test    eax, eax
0x1800b7589  jz      short loc_1800B7594
0x1800b758b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7592  jmp     short loc_1800B75A2
0x1800b7594  lea     rcx, qword_180153440; this
0x1800b759b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b75a2  cmp     [rcx+8], r14b
0x1800b75a6  jz      short loc_1800B75C9
0x1800b75a8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b75ad  cmp     [rax+7CCh], edi
0x1800b75b3  jz      short loc_1800B75C9
0x1800b75b5  mov     r9d, edi; int
0x1800b75b8  mov     r8d, 191h; int
0x1800b75be  mov     rdx, r15; char *
0x1800b75c1  mov     rcx, rax; this
0x1800b75c4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b75c9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b75d0  jb      loc_1800B7AC1
0x1800b75d6  mov     edx, 37h ; '7'
0x1800b75db  jmp     loc_1800B73A4
0x1800b75e0  mov     rcx, [rbp+ppMFAttributes]
0x1800b75e4  lea     rdx, MF_SA_D3D11_SHARED_WITHOUT_MUTEX
0x1800b75eb  xor     r8d, r8d
0x1800b75ee  mov     rax, [rcx]
0x1800b75f1  mov     rax, [rax+0A8h]
0x1800b75f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b75fd  mov     edi, eax
0x1800b75ff  test    eax, eax
0x1800b7601  jns     loc_1800B7692
0x1800b7607  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b760e  test    rcx, rcx
0x1800b7611  jnz     short loc_1800B7654
0x1800b7613  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7619  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7620  mov     rcx, rax
0x1800b7623  test    rax, rax
0x1800b7626  jz      short loc_1800B7646
0x1800b7628  mov     rax, [rax]
0x1800b762b  mov     edx, 7F0h
0x1800b7630  mov     rax, [rax+8]
0x1800b7634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7639  test    eax, eax
0x1800b763b  jz      short loc_1800B7646
0x1800b763d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7644  jmp     short loc_1800B7654
0x1800b7646  lea     rcx, qword_180153440; this
0x1800b764d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7654  cmp     [rcx+8], r14b
0x1800b7658  jz      short loc_1800B767B
0x1800b765a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b765f  cmp     [rax+7CCh], edi
0x1800b7665  jz      short loc_1800B767B
0x1800b7667  mov     r9d, edi; int
0x1800b766a  mov     r8d, 192h; int
0x1800b7670  mov     rdx, r15; char *
0x1800b7673  mov     rcx, rax; this
0x1800b7676  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b767b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b7682  jb      loc_1800B7AC1
0x1800b7688  mov     edx, 38h ; '8'
0x1800b768d  jmp     loc_1800B73A4
0x1800b7692  mov     rcx, [rsi+8]
0x1800b7696  lea     rdx, MF_MT_SECURE
0x1800b769d  xor     r8d, r8d
0x1800b76a0  mov     rcx, [rcx+50h]
0x1800b76a4  call    MFGetAttributeUINT32
0x1800b76a9  mov     ebx, eax
0x1800b76ab  test    eax, eax
0x1800b76ad  jnz     short loc_1800B76DD
0x1800b76af  lea     rcx, [rbp+var_8]
0x1800b76b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b76b8  lea     rdx, [rbp+var_8]; struct IMFAttributes **
0x1800b76bc  mov     rcx, rsi; this
0x1800b76bf  call    ?GetAttributes@CRolling420FrameStitcherMFTDataHandler@@UEAAJPEAPEAUIMFAttributes@@@Z; CRolling420FrameStitcherMFTDataHandler::GetAttributes(IMFAttributes * *)
0x1800b76c4  test    eax, eax
0x1800b76c6  js      short loc_1800B76DD
0x1800b76c8  mov     rcx, [rbp+var_8]
0x1800b76cc  lea     rdx, MFT_USING_HARDWARE_DRM
0x1800b76d3  xor     r8d, r8d
0x1800b76d6  call    MFGetAttributeUINT32
0x1800b76db  mov     ebx, eax
0x1800b76dd  mov     rcx, [rbp+ppMFAttributes]
0x1800b76e1  lea     rdx, MF_SA_D3D11_HW_PROTECTED
0x1800b76e8  mov     r8d, ebx
0x1800b76eb  mov     rax, [rcx]
0x1800b76ee  mov     rax, [rax+0A8h]
0x1800b76f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b76fa  mov     edi, eax
0x1800b76fc  test    eax, eax
0x1800b76fe  jns     loc_1800B778F
0x1800b7704  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b770b  test    rcx, rcx
0x1800b770e  jnz     short loc_1800B7751
0x1800b7710  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7716  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b771d  mov     rcx, rax
0x1800b7720  test    rax, rax
0x1800b7723  jz      short loc_1800B7743
0x1800b7725  mov     rax, [rax]
0x1800b7728  mov     edx, 7F0h
0x1800b772d  mov     rax, [rax+8]
0x1800b7731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7736  test    eax, eax
0x1800b7738  jz      short loc_1800B7743
0x1800b773a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7741  jmp     short loc_1800B7751
0x1800b7743  lea     rcx, qword_180153440; this
0x1800b774a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7751  cmp     [rcx+8], r14b
0x1800b7755  jz      short loc_1800B7778
0x1800b7757  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b775c  cmp     [rax+7CCh], edi
0x1800b7762  jz      short loc_1800B7778
0x1800b7764  mov     r9d, edi; int
0x1800b7767  mov     r8d, 199h; int
0x1800b776d  mov     rdx, r15; char *
0x1800b7770  mov     rcx, rax; this
0x1800b7773  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7778  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b777f  jb      loc_1800B7AC1
0x1800b7785  mov     edx, 39h ; '9'
0x1800b778a  jmp     loc_1800B73A4
0x1800b778f  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800b7796  jb      short loc_1800B77BE
0x1800b7798  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b779f  lea     r8, WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids
0x1800b77a6  mov     edx, 3Ah ; ':'
0x1800b77ab  mov     dword ptr [rsp+40h+var_20], ebx
0x1800b77af  mov     r9, rsi
0x1800b77b2  mov     rcx, [rcx+150h]
0x1800b77b9  call    WPP_SF_qD
  ... truncated ...
```
