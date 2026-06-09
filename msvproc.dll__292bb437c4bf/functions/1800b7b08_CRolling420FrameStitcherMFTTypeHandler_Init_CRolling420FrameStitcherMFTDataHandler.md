# CRolling420FrameStitcherMFTTypeHandler::Init(CRolling420FrameStitcherMFTDataHandler *)

- ea: `0x1800b7b08`
- end: `0x1800b8076`
- name: `?Init@CRolling420FrameStitcherMFTTypeHandler@@QEAAJPEAVCRolling420FrameStitcherMFTDataHandler@@@Z`
- size: `1390`
- prototype: `__int64 __fastcall(CRolling420FrameStitcherMFTTypeHandler *__hidden this, struct CRolling420FrameStitcherMFTDataHandler *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b8518`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001bcd8`
- `0x18001ca80`
- `0x18003639c`
- `0x1800b7b08`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800b7c15`
- `MFPlat!MFCreateMediaType` at `0x1800b7e37`
- `MFPlat!MFCreateMediaType` at `0x1800b7c15`
- `MFPlat!MFCreateMediaType` at `0x1800b7e37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7b6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7c31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7ce7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7d9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7e53`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7f09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7fbf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7b6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7c31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7ce7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7d9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7e53`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7f09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7fbf`

## pseudocode

```c
__int64 __fastcall CRolling420FrameStitcherMFTTypeHandler::Init(
        CRolling420FrameStitcherMFTTypeHandler *this,
        struct CRolling420FrameStitcherMFTDataHandler *a2)
{
  HRESULT inited; // ebx
  __int64 *v4; // rcx
  CallStackTracing *v5; // rax
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v27; // [rsp+50h] [rbp+20h] BYREF
  IMFMediaType *v28; // [rsp+58h] [rbp+28h] BYREF
  IMFMediaType *ppMFType; // [rsp+60h] [rbp+30h] BYREF

  *((_QWORD *)this + 1) = a2;
  ppMFType = 0;
  v28 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v27,
    "CRolling420FrameStitcherMFTTypeHandler::Init",
    84);
  inited = CMFTSimpleTypeHandler::InitAvailableInputTypeArray(this, 2u);
  if ( inited >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
    inited = MFCreateMediaType(&ppMFType);
    if ( inited >= 0 )
    {
      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                 ppMFType,
                 &MF_MT_MAJOR_TYPE,
                 &MFMediaType_Video);
      if ( inited >= 0 )
      {
        inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                   ppMFType,
                   &MF_MT_SUBTYPE,
                   &MFVideoFormat_ARGB32);
        if ( inited >= 0 )
        {
          CMFTSimpleTypeHandler::SetAvailableInputType(this, 0, ppMFType);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
          inited = MFCreateMediaType(&v28);
          if ( inited >= 0 )
          {
            inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))v28->lpVtbl->SetGUID)(
                       v28,
                       &MF_MT_MAJOR_TYPE,
                       &MFMediaType_Video);
            if ( inited >= 0 )
            {
              inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))v28->lpVtbl->SetGUID)(
                         v28,
                         &MF_MT_SUBTYPE,
                         &MFVideoFormat_RGB32);
              if ( inited >= 0 )
              {
                CMFTSimpleTypeHandler::SetAvailableInputType(this, 1u, v28);
                goto LABEL_80;
              }
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
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != inited )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CRolling420FrameStitcherMFTTypeHandler::Init",
                    93,
                    inited);
              }
              if ( g_wppLevels )
              {
                v7 = 21;
                goto LABEL_12;
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
                if ( *((_DWORD *)v22 + 499) != inited )
                  CallStackContext::TraceFailure(v22, "CRolling420FrameStitcherMFTTypeHandler::Init", 92, inited);
              }
              if ( g_wppLevels )
              {
                v7 = 20;
                goto LABEL_12;
              }
            }
          }
          else
          {
            v17 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v18;
              if ( v18
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
              {
                v17 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v17 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v17 + 8) )
            {
              v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
              if ( *((_DWORD *)v19 + 499) != inited )
                CallStackContext::TraceFailure(v19, "CRolling420FrameStitcherMFTTypeHandler::Init", 91, inited);
            }
            if ( g_wppLevels )
            {
              v7 = 19;
              goto LABEL_12;
            }
          }
        }
        else
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v15;
            if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
            {
              v14 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v14 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v14 + 8) )
          {
            v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
            if ( *((_DWORD *)v16 + 499) != inited )
              CallStackContext::TraceFailure(v16, "CRolling420FrameStitcherMFTTypeHandler::Init", 88, inited);
          }
          if ( g_wppLevels )
          {
            v7 = 18;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v12;
          if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
          {
            v11 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( *((_DWORD *)v13 + 499) != inited )
            CallStackContext::TraceFailure(v13, "CRolling420FrameStitcherMFTTypeHandler::Init", 87, inited);
        }
        if ( g_wppLevels )
        {
          v7 = 17;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)v10 + 499) != inited )
          CallStackContext::TraceFailure(v10, "CRolling420FrameStitcherMFTTypeHandler::Init", 86, inited);
      }
      if ( g_wppLevels )
      {
        v7 = 16;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v4 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v5;
      if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
      {
        v4 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v6 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)v6 + 499) != inited )
        CallStackContext::TraceFailure(v6, "CRolling420FrameStitcherMFTTypeHandler::Init", 84, inited);
    }
    if ( g_wppLevels )
    {
      v7 = 15;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids, this, inited);
    }
  }
LABEL_80:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v27);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800b7b08  mov     [rsp-18h+arg_18], rbx
0x1800b7b0d  push    rbp
0x1800b7b0e  push    rdi
0x1800b7b0f  push    r14
0x1800b7b11  mov     rbp, rsp
0x1800b7b14  sub     rsp, 30h
0x1800b7b18  mov     [rcx+8], rdx
0x1800b7b1c  lea     r14, aCrolling420fra_15; "CRolling420FrameStitcherMFTTypeHandler:"...
0x1800b7b23  mov     rdi, rcx
0x1800b7b26  mov     [rbp+ppMFType], 0
0x1800b7b2e  mov     rdx, r14; char *
0x1800b7b31  mov     [rbp+arg_8], 0
0x1800b7b39  mov     r8d, 54h ; 'T'; int
0x1800b7b3f  lea     rcx, [rbp+arg_0]; this
0x1800b7b43  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b7b48  mov     edx, 2; unsigned int
0x1800b7b4d  mov     rcx, rdi; this
0x1800b7b50  call    ?InitAvailableInputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z; CMFTSimpleTypeHandler::InitAvailableInputTypeArray(ulong)
0x1800b7b55  mov     ebx, eax
0x1800b7b57  test    eax, eax
0x1800b7b59  jns     loc_1800B7C08
0x1800b7b5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7b66  test    rcx, rcx
0x1800b7b69  jnz     short loc_1800B7BAC
0x1800b7b6b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7b71  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7b78  mov     rcx, rax
0x1800b7b7b  test    rax, rax
0x1800b7b7e  jz      short loc_1800B7B9E
0x1800b7b80  mov     rax, [rax]
0x1800b7b83  mov     edx, 7F0h
0x1800b7b88  mov     rax, [rax+8]
0x1800b7b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7b91  test    eax, eax
0x1800b7b93  jz      short loc_1800B7B9E
0x1800b7b95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7b9c  jmp     short loc_1800B7BAC
0x1800b7b9e  lea     rcx, qword_180153440; this
0x1800b7ba5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7bac  cmp     byte ptr [rcx+8], 0
0x1800b7bb0  jz      short loc_1800B7BD3
0x1800b7bb2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b7bb7  cmp     [rax+7CCh], ebx
0x1800b7bbd  jz      short loc_1800B7BD3
0x1800b7bbf  mov     r9d, ebx; int
0x1800b7bc2  mov     r8d, 54h ; 'T'; int
0x1800b7bc8  mov     rdx, r14; char *
0x1800b7bcb  mov     rcx, rax; this
0x1800b7bce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7bd3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b7bda  jb      loc_1800B804B
0x1800b7be0  mov     edx, 0Fh
0x1800b7be5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7bec  lea     r8, WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids
0x1800b7bf3  mov     r9, rdi
0x1800b7bf6  mov     [rsp+30h+var_10], ebx
0x1800b7bfa  mov     rcx, [rcx+10h]
0x1800b7bfe  call    WPP_SF_qD
0x1800b7c03  jmp     loc_1800B804B
0x1800b7c08  lea     rcx, [rbp+ppMFType]
0x1800b7c0c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7c11  lea     rcx, [rbp+ppMFType]; ppMFType
0x1800b7c15  call    cs:__imp_MFCreateMediaType
0x1800b7c1b  mov     ebx, eax
0x1800b7c1d  test    eax, eax
0x1800b7c1f  jns     loc_1800B7CB0
0x1800b7c25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7c2c  test    rcx, rcx
0x1800b7c2f  jnz     short loc_1800B7C72
0x1800b7c31  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7c37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7c3e  mov     rcx, rax
0x1800b7c41  test    rax, rax
0x1800b7c44  jz      short loc_1800B7C64
0x1800b7c46  mov     rax, [rax]
0x1800b7c49  mov     edx, 7F0h
0x1800b7c4e  mov     rax, [rax+8]
0x1800b7c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7c57  test    eax, eax
0x1800b7c59  jz      short loc_1800B7C64
0x1800b7c5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7c62  jmp     short loc_1800B7C72
0x1800b7c64  lea     rcx, qword_180153440; this
0x1800b7c6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7c72  cmp     byte ptr [rcx+8], 0
0x1800b7c76  jz      short loc_1800B7C99
0x1800b7c78  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b7c7d  cmp     [rax+7CCh], ebx
0x1800b7c83  jz      short loc_1800B7C99
0x1800b7c85  mov     r9d, ebx; int
0x1800b7c88  mov     r8d, 56h ; 'V'; int
0x1800b7c8e  mov     rdx, r14; char *
0x1800b7c91  mov     rcx, rax; this
0x1800b7c94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7c99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b7ca0  jb      loc_1800B804B
0x1800b7ca6  mov     edx, 10h
0x1800b7cab  jmp     loc_1800B7BE5
0x1800b7cb0  mov     rcx, [rbp+ppMFType]
0x1800b7cb4  lea     r8, MFMediaType_Video
0x1800b7cbb  lea     rdx, MF_MT_MAJOR_TYPE
0x1800b7cc2  mov     rax, [rcx]
0x1800b7cc5  mov     rax, [rax+0C0h]
0x1800b7ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7cd1  mov     ebx, eax
0x1800b7cd3  test    eax, eax
0x1800b7cd5  jns     loc_1800B7D66
0x1800b7cdb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7ce2  test    rcx, rcx
0x1800b7ce5  jnz     short loc_1800B7D28
0x1800b7ce7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7ced  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7cf4  mov     rcx, rax
0x1800b7cf7  test    rax, rax
0x1800b7cfa  jz      short loc_1800B7D1A
0x1800b7cfc  mov     rax, [rax]
0x1800b7cff  mov     edx, 7F0h
0x1800b7d04  mov     rax, [rax+8]
0x1800b7d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7d0d  test    eax, eax
0x1800b7d0f  jz      short loc_1800B7D1A
0x1800b7d11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7d18  jmp     short loc_1800B7D28
0x1800b7d1a  lea     rcx, qword_180153440; this
0x1800b7d21  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7d28  cmp     byte ptr [rcx+8], 0
0x1800b7d2c  jz      short loc_1800B7D4F
0x1800b7d2e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b7d33  cmp     [rax+7CCh], ebx
0x1800b7d39  jz      short loc_1800B7D4F
0x1800b7d3b  mov     r9d, ebx; int
0x1800b7d3e  mov     r8d, 57h ; 'W'; int
0x1800b7d44  mov     rdx, r14; char *
0x1800b7d47  mov     rcx, rax; this
0x1800b7d4a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7d4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b7d56  jb      loc_1800B804B
0x1800b7d5c  mov     edx, 11h
0x1800b7d61  jmp     loc_1800B7BE5
0x1800b7d66  mov     rcx, [rbp+ppMFType]
0x1800b7d6a  lea     r8, MFVideoFormat_ARGB32
0x1800b7d71  lea     rdx, MF_MT_SUBTYPE
0x1800b7d78  mov     rax, [rcx]
0x1800b7d7b  mov     rax, [rax+0C0h]
0x1800b7d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7d87  mov     ebx, eax
0x1800b7d89  test    eax, eax
0x1800b7d8b  jns     loc_1800B7E1C
0x1800b7d91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7d98  test    rcx, rcx
0x1800b7d9b  jnz     short loc_1800B7DDE
0x1800b7d9d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7da3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7daa  mov     rcx, rax
0x1800b7dad  test    rax, rax
0x1800b7db0  jz      short loc_1800B7DD0
0x1800b7db2  mov     rax, [rax]
0x1800b7db5  mov     edx, 7F0h
0x1800b7dba  mov     rax, [rax+8]
0x1800b7dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7dc3  test    eax, eax
0x1800b7dc5  jz      short loc_1800B7DD0
0x1800b7dc7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7dce  jmp     short loc_1800B7DDE
0x1800b7dd0  lea     rcx, qword_180153440; this
0x1800b7dd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7dde  cmp     byte ptr [rcx+8], 0
0x1800b7de2  jz      short loc_1800B7E05
0x1800b7de4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b7de9  cmp     [rax+7CCh], ebx
0x1800b7def  jz      short loc_1800B7E05
0x1800b7df1  mov     r9d, ebx; int
0x1800b7df4  mov     r8d, 58h ; 'X'; int
0x1800b7dfa  mov     rdx, r14; char *
0x1800b7dfd  mov     rcx, rax; this
0x1800b7e00  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7e05  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b7e0c  jb      loc_1800B804B
0x1800b7e12  mov     edx, 12h
0x1800b7e17  jmp     loc_1800B7BE5
0x1800b7e1c  mov     r8, [rbp+ppMFType]; struct IMFMediaType *
0x1800b7e20  xor     edx, edx; unsigned int
0x1800b7e22  mov     rcx, rdi; this
0x1800b7e25  call    ?SetAvailableInputType@CMFTSimpleTypeHandler@@QEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleTypeHandler::SetAvailableInputType(ulong,IMFMediaType *)
0x1800b7e2a  lea     rcx, [rbp+arg_8]
0x1800b7e2e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7e33  lea     rcx, [rbp+arg_8]; ppMFType
0x1800b7e37  call    cs:__imp_MFCreateMediaType
0x1800b7e3d  mov     ebx, eax
0x1800b7e3f  test    eax, eax
0x1800b7e41  jns     loc_1800B7ED2
0x1800b7e47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7e4e  test    rcx, rcx
0x1800b7e51  jnz     short loc_1800B7E94
0x1800b7e53  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7e59  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7e60  mov     rcx, rax
0x1800b7e63  test    rax, rax
0x1800b7e66  jz      short loc_1800B7E86
0x1800b7e68  mov     rax, [rax]
0x1800b7e6b  mov     edx, 7F0h
0x1800b7e70  mov     rax, [rax+8]
0x1800b7e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7e79  test    eax, eax
0x1800b7e7b  jz      short loc_1800B7E86
0x1800b7e7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7e84  jmp     short loc_1800B7E94
0x1800b7e86  lea     rcx, qword_180153440; this
0x1800b7e8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7e94  cmp     byte ptr [rcx+8], 0
0x1800b7e98  jz      short loc_1800B7EBB
0x1800b7e9a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b7e9f  cmp     [rax+7CCh], ebx
0x1800b7ea5  jz      short loc_1800B7EBB
0x1800b7ea7  mov     r9d, ebx; int
0x1800b7eaa  mov     r8d, 5Bh ; '['; int
0x1800b7eb0  mov     rdx, r14; char *
0x1800b7eb3  mov     rcx, rax; this
0x1800b7eb6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7ebb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b7ec2  jb      loc_1800B804B
0x1800b7ec8  mov     edx, 13h
0x1800b7ecd  jmp     loc_1800B7BE5
0x1800b7ed2  mov     rcx, [rbp+arg_8]
0x1800b7ed6  lea     r8, MFMediaType_Video
0x1800b7edd  lea     rdx, MF_MT_MAJOR_TYPE
0x1800b7ee4  mov     rax, [rcx]
0x1800b7ee7  mov     rax, [rax+0C0h]
0x1800b7eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7ef3  mov     ebx, eax
0x1800b7ef5  test    eax, eax
0x1800b7ef7  jns     loc_1800B7F88
0x1800b7efd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7f04  test    rcx, rcx
0x1800b7f07  jnz     short loc_1800B7F4A
0x1800b7f09  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7f0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7f16  mov     rcx, rax
0x1800b7f19  test    rax, rax
0x1800b7f1c  jz      short loc_1800B7F3C
0x1800b7f1e  mov     rax, [rax]
0x1800b7f21  mov     edx, 7F0h
0x1800b7f26  mov     rax, [rax+8]
0x1800b7f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7f2f  test    eax, eax
0x1800b7f31  jz      short loc_1800B7F3C
0x1800b7f33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7f3a  jmp     short loc_1800B7F4A
0x1800b7f3c  lea     rcx, qword_180153440; this
0x1800b7f43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7f4a  cmp     byte ptr [rcx+8], 0
0x1800b7f4e  jz      short loc_1800B7F71
0x1800b7f50  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b7f55  cmp     [rax+7CCh], ebx
0x1800b7f5b  jz      short loc_1800B7F71
0x1800b7f5d  mov     r9d, ebx; int
0x1800b7f60  mov     r8d, 5Ch ; '\'; int
0x1800b7f66  mov     rdx, r14; char *
0x1800b7f69  mov     rcx, rax; this
0x1800b7f6c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7f71  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b7f78  jb      loc_1800B804B
0x1800b7f7e  mov     edx, 14h
0x1800b7f83  jmp     loc_1800B7BE5
0x1800b7f88  mov     rcx, [rbp+arg_8]
0x1800b7f8c  lea     r8, MFVideoFormat_RGB32
0x1800b7f93  lea     rdx, MF_MT_SUBTYPE
0x1800b7f9a  mov     rax, [rcx]
0x1800b7f9d  mov     rax, [rax+0C0h]
0x1800b7fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7fa9  mov     ebx, eax
0x1800b7fab  test    eax, eax
0x1800b7fad  jns     loc_1800B803A
0x1800b7fb3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7fba  test    rcx, rcx
0x1800b7fbd  jnz     short loc_1800B8000
0x1800b7fbf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7fc5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7fcc  mov     rcx, rax
0x1800b7fcf  test    rax, rax
0x1800b7fd2  jz      short loc_1800B7FF2
0x1800b7fd4  mov     rax, [rax]
0x1800b7fd7  mov     edx, 7F0h
0x1800b7fdc  mov     rax, [rax+8]
0x1800b7fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7fe5  test    eax, eax
0x1800b7fe7  jz      short loc_1800B7FF2
0x1800b7fe9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7ff0  jmp     short loc_1800B8000
0x1800b7ff2  lea     rcx, qword_180153440; this
0x1800b7ff9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8000  cmp     byte ptr [rcx+8], 0
0x1800b8004  jz      short loc_1800B8027
0x1800b8006  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b800b  cmp     [rax+7CCh], ebx
0x1800b8011  jz      short loc_1800B8027
0x1800b8013  mov     r9d, ebx; int
0x1800b8016  mov     r8d, 5Dh ; ']'; int
0x1800b801c  mov     rdx, r14; char *
0x1800b801f  mov     rcx, rax; this
  ... truncated ...
```
