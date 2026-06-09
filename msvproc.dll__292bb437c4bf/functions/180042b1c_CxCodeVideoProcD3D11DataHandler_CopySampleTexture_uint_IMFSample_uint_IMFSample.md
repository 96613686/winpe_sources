# CxCodeVideoProcD3D11DataHandler::CopySampleTexture(uint,IMFSample *,uint,IMFSample *)

- ea: `0x180042b1c`
- end: `0x180042fd8`
- name: `?CopySampleTexture@CxCodeVideoProcD3D11DataHandler@@AEAAJIPEAUIMFSample@@I0@Z`
- size: `1212`
- prototype: `int(CxCodeVideoProcD3D11DataHandler *__hidden this, unsigned int, struct IMFSample *, unsigned int, struct IMFSample *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006eb24`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180042b1c`
- `0x1800669a4`
- `0x1800724b0`
- `0x1800c0704`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042bbc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042c9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042d4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042dfb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042ebe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042bbc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042c9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042d4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042dfb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042ebe`

## string_xrefs

- `0x180042b7f`: `CxCodeVideoProcD3D11DataHandler::CopySampleTexture`
- `0x180042c13`: `CxCodeVideoProcD3D11DataHandler::CopySampleTexture`
- `0x180042cf4`: `CxCodeVideoProcD3D11DataHandler::CopySampleTexture`
- `0x180042da1`: `CxCodeVideoProcD3D11DataHandler::CopySampleTexture`
- `0x180042e52`: `CxCodeVideoProcD3D11DataHandler::CopySampleTexture`
- `0x180042f15`: `CxCodeVideoProcD3D11DataHandler::CopySampleTexture`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::CopySampleTexture(
        CxCodeVideoProcD3D11DataHandler *this,
        unsigned int a2,
        struct IMFSample *a3,
        unsigned int a4,
        struct IMFSample *a5)
{
  struct IMFDXGIBuffer **v9; // r9
  int v10; // ebx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, GUID *, __int64 *); // rbx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  struct IMFDXGIBuffer **v21; // r9
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, GUID *, __int64 *); // rbx
  CallStackTracing *v26; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v29[4]; // [rsp+50h] [rbp-30h] BYREF
  int v30; // [rsp+54h] [rbp-2Ch] BYREF
  unsigned int v31[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v32; // [rsp+60h] [rbp-20h] BYREF
  __int64 v33; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v34[2]; // [rsp+70h] [rbp-10h] BYREF

  v30 = 0;
  *(_QWORD *)v31 = 0;
  *(_QWORD *)v34 = 0;
  v33 = 0;
  v32 = 0;
  if ( (Microsoft_Windows_MediaFoundation_MSVProcEnableBits & 1) != 0 )
    McTemplateU0ppqpq_EventWriteTransfer((_DWORD)this, a2, (_DWORD)this, (_DWORD)a3, a2, (char)a5, a4);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v29,
    "CxCodeVideoProcD3D11DataHandler::CopySampleTexture",
    4199);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
  v10 = MFD3D::DXGIBufferFromSample((MFD3D *)a3, (struct IMFSample *)a2, (unsigned int)v31, v9);
  if ( v10 >= 0 )
  {
    v15 = *(_QWORD *)v31;
    v16 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(**(_QWORD **)v31 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v10 = v16(v15, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v33);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v31 + 32LL))(*(_QWORD *)v31, &v30);
      if ( v10 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
        v10 = MFD3D::DXGIBufferFromSample((MFD3D *)a5, (struct IMFSample *)a4, (unsigned int)v34, v21);
        if ( v10 >= 0 )
        {
          v24 = *(_QWORD *)v34;
          v25 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(**(_QWORD **)v34 + 24LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          v10 = v25(v24, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v32);
          if ( v10 >= 0 )
          {
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, _DWORD, __int64, int, _QWORD))(**((_QWORD **)this + 286) + 368LL))(
              *((_QWORD *)this + 286),
              v32,
              0,
              0,
              0,
              0,
              v33,
              v30,
              0);
          }
          else
          {
            v11 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v26;
              if ( v26
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
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
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CxCodeVideoProcD3D11DataHandler::CopySampleTexture",
                  4204,
                  v10);
            }
            if ( g_wppLevels )
            {
              v14 = 250;
              goto LABEL_14;
            }
          }
        }
        else
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v22;
            if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
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
            v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
            if ( *((_DWORD *)v23 + 499) != v10 )
              CallStackContext::TraceFailure(v23, "CxCodeVideoProcD3D11DataHandler::CopySampleTexture", 4203, v10);
          }
          if ( g_wppLevels )
          {
            v14 = 249;
            goto LABEL_14;
          }
        }
      }
      else
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
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
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( *((_DWORD *)v20 + 499) != v10 )
            CallStackContext::TraceFailure(v20, "CxCodeVideoProcD3D11DataHandler::CopySampleTexture", 4201, v10);
        }
        if ( g_wppLevels )
        {
          v14 = 248;
          goto LABEL_14;
        }
      }
    }
    else
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
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
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v18 + 499) != v10 )
          CallStackContext::TraceFailure(v18, "CxCodeVideoProcD3D11DataHandler::CopySampleTexture", 4200, v10);
      }
      if ( g_wppLevels )
      {
        v14 = 247;
        goto LABEL_14;
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
      if ( *((_DWORD *)v13 + 499) != v10 )
        CallStackContext::TraceFailure(v13, "CxCodeVideoProcD3D11DataHandler::CopySampleTexture", 4199, v10);
    }
    if ( g_wppLevels )
    {
      v14 = 246;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this, v10);
    }
  }
  if ( (Microsoft_Windows_MediaFoundation_MSVProcEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(v11, MSVProc_CopySampleTexture_Stop, this, (unsigned int)v10);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v29);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180042b1c  push    rbp
0x180042b1e  push    rbx
0x180042b1f  push    rsi
0x180042b20  push    rdi
0x180042b21  push    r12
0x180042b23  push    r14
0x180042b25  push    r15
0x180042b27  mov     rbp, rsp
0x180042b2a  sub     rsp, 80h
0x180042b31  mov     r15, [rbp+arg_20]
0x180042b35  xor     r12d, r12d
0x180042b38  test    byte ptr cs:Microsoft_Windows_MediaFoundation_MSVProcEnableBits, 1
0x180042b3f  mov     r14d, r9d
0x180042b42  mov     rbx, r8
0x180042b45  mov     [rbp+var_2C], r12d
0x180042b49  mov     edi, edx
0x180042b4b  mov     qword ptr [rbp+var_28], r12
0x180042b4f  mov     rsi, rcx
0x180042b52  mov     qword ptr [rbp+var_10], r12
0x180042b56  mov     [rbp+var_18], r12
0x180042b5a  mov     [rbp+var_20], r12
0x180042b5e  jz      short loc_180042B79
0x180042b60  mov     dword ptr [rsp+80h+var_50], r9d
0x180042b65  mov     r8, rcx
0x180042b68  mov     [rsp+80h+var_58], r15
0x180042b6d  mov     r9, rbx
0x180042b70  mov     [rsp+80h+var_60], edx
0x180042b74  call    McTemplateU0ppqpq_EventWriteTransfer
0x180042b79  mov     r8d, 1067h; int
0x180042b7f  lea     rdx, aCxcodevideopro_12; "CxCodeVideoProcD3D11DataHandler::CopySa"...
0x180042b86  lea     rcx, [rbp+var_30]; this
0x180042b8a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180042b8f  lea     rcx, [rbp+var_28]
0x180042b93  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042b98  lea     r8, [rbp+var_28]; unsigned int
0x180042b9c  mov     edx, edi; struct IMFSample *
0x180042b9e  mov     rcx, rbx; this
0x180042ba1  call    ?DXGIBufferFromSample@MFD3D@@YAJPEAUIMFSample@@KPEAPEAUIMFDXGIBuffer@@@Z; MFD3D::DXGIBufferFromSample(IMFSample *,ulong,IMFDXGIBuffer * *)
0x180042ba6  mov     ebx, eax
0x180042ba8  test    eax, eax
0x180042baa  jns     loc_180042C5D
0x180042bb0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042bb7  test    rcx, rcx
0x180042bba  jnz     short loc_180042BFD
0x180042bbc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042bc2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042bc9  mov     rcx, rax
0x180042bcc  test    rax, rax
0x180042bcf  jz      short loc_180042BEF
0x180042bd1  mov     rax, [rax]
0x180042bd4  mov     edx, 7F0h
0x180042bd9  mov     rax, [rax+8]
0x180042bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042be2  test    eax, eax
0x180042be4  jz      short loc_180042BEF
0x180042be6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042bed  jmp     short loc_180042BFD
0x180042bef  lea     rcx, qword_180153440; this
0x180042bf6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042bfd  cmp     [rcx+8], r12b
0x180042c01  jz      short loc_180042C28
0x180042c03  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042c08  cmp     [rax+7CCh], ebx
0x180042c0e  jz      short loc_180042C28
0x180042c10  mov     r9d, ebx; int
0x180042c13  lea     rdx, aCxcodevideopro_12; "CxCodeVideoProcD3D11DataHandler::CopySa"...
0x180042c1a  mov     r8d, 1067h; int
0x180042c20  mov     rcx, rax; this
0x180042c23  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042c28  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042c2f  jb      loc_180042F7C
0x180042c35  mov     edx, 0F6h
0x180042c3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c41  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x180042c48  mov     r9, rsi
0x180042c4b  mov     [rsp+80h+var_60], ebx
0x180042c4f  mov     rcx, [rcx+10h]
0x180042c53  call    WPP_SF_qD
0x180042c58  jmp     loc_180042F7C
0x180042c5d  mov     rdi, qword ptr [rbp+var_28]
0x180042c61  lea     rcx, [rbp+var_18]
0x180042c65  mov     rax, [rdi]
0x180042c68  mov     rbx, [rax+18h]
0x180042c6c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042c71  lea     r8, [rbp+var_18]
0x180042c75  mov     rcx, rdi
0x180042c78  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x180042c7f  mov     rax, rbx
0x180042c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c87  mov     ebx, eax
0x180042c89  test    eax, eax
0x180042c8b  jns     loc_180042D20
0x180042c91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042c98  test    rcx, rcx
0x180042c9b  jnz     short loc_180042CDE
0x180042c9d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042ca3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042caa  mov     rcx, rax
0x180042cad  test    rax, rax
0x180042cb0  jz      short loc_180042CD0
0x180042cb2  mov     rax, [rax]
0x180042cb5  mov     edx, 7F0h
0x180042cba  mov     rax, [rax+8]
0x180042cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cc3  test    eax, eax
0x180042cc5  jz      short loc_180042CD0
0x180042cc7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042cce  jmp     short loc_180042CDE
0x180042cd0  lea     rcx, qword_180153440; this
0x180042cd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042cde  cmp     [rcx+8], r12b
0x180042ce2  jz      short loc_180042D09
0x180042ce4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042ce9  cmp     [rax+7CCh], ebx
0x180042cef  jz      short loc_180042D09
0x180042cf1  mov     r9d, ebx; int
0x180042cf4  lea     rdx, aCxcodevideopro_12; "CxCodeVideoProcD3D11DataHandler::CopySa"...
0x180042cfb  mov     r8d, 1068h; int
0x180042d01  mov     rcx, rax; this
0x180042d04  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042d09  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042d10  jb      loc_180042F7C
0x180042d16  mov     edx, 0F7h
0x180042d1b  jmp     loc_180042C3A
0x180042d20  mov     rcx, qword ptr [rbp+var_28]
0x180042d24  lea     rdx, [rbp+var_2C]
0x180042d28  mov     rax, [rcx]
0x180042d2b  mov     rax, [rax+20h]
0x180042d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d34  mov     ebx, eax
0x180042d36  test    eax, eax
0x180042d38  jns     loc_180042DCD
0x180042d3e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042d45  test    rcx, rcx
0x180042d48  jnz     short loc_180042D8B
0x180042d4a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042d50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042d57  mov     rcx, rax
0x180042d5a  test    rax, rax
0x180042d5d  jz      short loc_180042D7D
0x180042d5f  mov     rax, [rax]
0x180042d62  mov     edx, 7F0h
0x180042d67  mov     rax, [rax+8]
0x180042d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d70  test    eax, eax
0x180042d72  jz      short loc_180042D7D
0x180042d74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042d7b  jmp     short loc_180042D8B
0x180042d7d  lea     rcx, qword_180153440; this
0x180042d84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042d8b  cmp     [rcx+8], r12b
0x180042d8f  jz      short loc_180042DB6
0x180042d91  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042d96  cmp     [rax+7CCh], ebx
0x180042d9c  jz      short loc_180042DB6
0x180042d9e  mov     r9d, ebx; int
0x180042da1  lea     rdx, aCxcodevideopro_12; "CxCodeVideoProcD3D11DataHandler::CopySa"...
0x180042da8  mov     r8d, 1069h; int
0x180042dae  mov     rcx, rax; this
0x180042db1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042db6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042dbd  jb      loc_180042F7C
0x180042dc3  mov     edx, 0F8h
0x180042dc8  jmp     loc_180042C3A
0x180042dcd  lea     rcx, [rbp+var_10]
0x180042dd1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042dd6  lea     r8, [rbp+var_10]; unsigned int
0x180042dda  mov     edx, r14d; struct IMFSample *
0x180042ddd  mov     rcx, r15; this
0x180042de0  call    ?DXGIBufferFromSample@MFD3D@@YAJPEAUIMFSample@@KPEAPEAUIMFDXGIBuffer@@@Z; MFD3D::DXGIBufferFromSample(IMFSample *,ulong,IMFDXGIBuffer * *)
0x180042de5  mov     ebx, eax
0x180042de7  test    eax, eax
0x180042de9  jns     loc_180042E7E
0x180042def  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042df6  test    rcx, rcx
0x180042df9  jnz     short loc_180042E3C
0x180042dfb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042e01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042e08  mov     rcx, rax
0x180042e0b  test    rax, rax
0x180042e0e  jz      short loc_180042E2E
0x180042e10  mov     rax, [rax]
0x180042e13  mov     edx, 7F0h
0x180042e18  mov     rax, [rax+8]
0x180042e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e21  test    eax, eax
0x180042e23  jz      short loc_180042E2E
0x180042e25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042e2c  jmp     short loc_180042E3C
0x180042e2e  lea     rcx, qword_180153440; this
0x180042e35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042e3c  cmp     [rcx+8], r12b
0x180042e40  jz      short loc_180042E67
0x180042e42  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042e47  cmp     [rax+7CCh], ebx
0x180042e4d  jz      short loc_180042E67
0x180042e4f  mov     r9d, ebx; int
0x180042e52  lea     rdx, aCxcodevideopro_12; "CxCodeVideoProcD3D11DataHandler::CopySa"...
0x180042e59  mov     r8d, 106Bh; int
0x180042e5f  mov     rcx, rax; this
0x180042e62  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042e67  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042e6e  jb      loc_180042F7C
0x180042e74  mov     edx, 0F9h
0x180042e79  jmp     loc_180042C3A
0x180042e7e  mov     rdi, qword ptr [rbp+var_10]
0x180042e82  lea     rcx, [rbp+var_20]
0x180042e86  mov     rax, [rdi]
0x180042e89  mov     rbx, [rax+18h]
0x180042e8d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042e92  lea     r8, [rbp+var_20]
0x180042e96  mov     rcx, rdi
0x180042e99  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x180042ea0  mov     rax, rbx
0x180042ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ea8  mov     ebx, eax
0x180042eaa  test    eax, eax
0x180042eac  jns     loc_180042F3D
0x180042eb2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042eb9  test    rcx, rcx
0x180042ebc  jnz     short loc_180042EFF
0x180042ebe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042ec4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ecb  mov     rcx, rax
0x180042ece  test    rax, rax
0x180042ed1  jz      short loc_180042EF1
0x180042ed3  mov     rax, [rax]
0x180042ed6  mov     edx, 7F0h
0x180042edb  mov     rax, [rax+8]
0x180042edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ee4  test    eax, eax
0x180042ee6  jz      short loc_180042EF1
0x180042ee8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042eef  jmp     short loc_180042EFF
0x180042ef1  lea     rcx, qword_180153440; this
0x180042ef8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042eff  cmp     [rcx+8], r12b
0x180042f03  jz      short loc_180042F2A
0x180042f05  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042f0a  cmp     [rax+7CCh], ebx
0x180042f10  jz      short loc_180042F2A
0x180042f12  mov     r9d, ebx; int
0x180042f15  lea     rdx, aCxcodevideopro_12; "CxCodeVideoProcD3D11DataHandler::CopySa"...
0x180042f1c  mov     r8d, 106Ch; int
0x180042f22  mov     rcx, rax; this
0x180042f25  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042f2a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042f31  jb      short loc_180042F7C
0x180042f33  mov     edx, 0FAh
0x180042f38  jmp     loc_180042C3A
0x180042f3d  mov     edx, [rbp+var_2C]
0x180042f40  xor     r9d, r9d
0x180042f43  mov     rcx, [rsi+8F0h]
0x180042f4a  xor     r8d, r8d
0x180042f4d  mov     [rsp+80h+var_40], r12
0x180042f52  mov     [rsp+80h+var_48], edx
0x180042f56  mov     rdx, [rbp+var_18]
0x180042f5a  mov     rax, [rcx]
0x180042f5d  mov     [rsp+80h+var_50], rdx
0x180042f62  mov     rdx, [rbp+var_20]
0x180042f66  mov     dword ptr [rsp+80h+var_58], r12d
0x180042f6b  mov     rax, [rax+170h]
0x180042f72  mov     [rsp+80h+var_60], r12d
0x180042f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f7c  test    byte ptr cs:Microsoft_Windows_MediaFoundation_MSVProcEnableBits, 1
0x180042f83  jz      short loc_180042F97
0x180042f85  mov     r9d, ebx
0x180042f88  lea     rdx, MSVProc_CopySampleTexture_Stop
0x180042f8f  mov     r8, rsi
0x180042f92  call    McTemplateU0pq_EventWriteTransfer
0x180042f97  lea     rcx, [rbp+var_30]; this
0x180042f9b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180042fa0  lea     rcx, [rbp+var_20]
0x180042fa4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042fa9  lea     rcx, [rbp+var_18]
0x180042fad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042fb2  lea     rcx, [rbp+var_10]
0x180042fb6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042fbb  lea     rcx, [rbp+var_28]
0x180042fbf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042fc4  mov     eax, ebx
0x180042fc6  add     rsp, 80h
0x180042fcd  pop     r15
0x180042fcf  pop     r14
0x180042fd1  pop     r12
0x180042fd3  pop     rdi
0x180042fd4  pop     rsi
0x180042fd5  pop     rbx
0x180042fd6  pop     rbp
0x180042fd7  retn
```
