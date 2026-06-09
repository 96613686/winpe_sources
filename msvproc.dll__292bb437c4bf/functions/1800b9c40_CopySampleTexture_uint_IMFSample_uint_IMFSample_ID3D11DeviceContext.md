# CopySampleTexture(uint,IMFSample *,uint,IMFSample *,ID3D11DeviceContext *)

- ea: `0x1800b9c40`
- end: `0x1800ba0a8`
- name: `?CopySampleTexture@@YAJIPEAUIMFSample@@I0PEAUID3D11DeviceContext@@@Z`
- size: `1128`
- prototype: `int(unsigned int, struct IMFSample *, unsigned int, struct IMFSample *, struct ID3D11DeviceContext *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800bb808`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800b9c40`
- `0x1800c0704`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9cbf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9d99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9e42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9eee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9fad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9cbf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9d99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9e42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9eee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9fad`

## string_xrefs

- `0x1800b9c7e`: `CopySampleTexture`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CopySampleTexture(
        __int64 a1,
        struct IMFSample *a2,
        __int64 a3,
        struct IMFSample *a4,
        struct ID3D11DeviceContext *a5)
{
  struct IMFDXGIBuffer **v7; // r9
  int v8; // ebx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, GUID *, __int64 *); // rbx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  struct IMFDXGIBuffer **v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, GUID *, __int64 *); // rbx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v31[8]; // [rsp+50h] [rbp-11h] BYREF
  unsigned int v32[2]; // [rsp+58h] [rbp-9h] BYREF
  __int64 v33; // [rsp+60h] [rbp-1h] BYREF
  __int64 v34; // [rsp+68h] [rbp+7h] BYREF
  unsigned int v35[2]; // [rsp+70h] [rbp+Fh] BYREF
  int v36; // [rsp+D0h] [rbp+6Fh] BYREF

  v36 = 0;
  *(_QWORD *)v32 = 0;
  *(_QWORD *)v35 = 0;
  v34 = 0;
  v33 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v31, "CopySampleTexture", 596);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v32);
  v8 = MFD3D::DXGIBufferFromSample((MFD3D *)a2, 0, (unsigned int)v32, v7);
  if ( v8 >= 0 )
  {
    v13 = *(_QWORD *)v32;
    v14 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(**(_QWORD **)v32 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    v8 = v14(v13, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v34);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v32 + 32LL))(*(_QWORD *)v32, &v36);
      if ( v8 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
        v8 = MFD3D::DXGIBufferFromSample((MFD3D *)a4, 0, (unsigned int)v35, v21);
        if ( v8 >= 0 )
        {
          v25 = *(_QWORD *)v35;
          v26 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(**(_QWORD **)v35 + 24LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
          v8 = v26(v25, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v33);
          if ( v8 >= 0 )
          {
            ((void (__fastcall *)(struct ID3D11DeviceContext *, __int64, _QWORD, _QWORD, _DWORD, _DWORD, __int64, int, _QWORD))a5->lpVtbl->CopySubresourceRegion)(
              a5,
              v33,
              0,
              0,
              0,
              0,
              v34,
              v36,
              0);
            goto LABEL_58;
          }
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v28;
            if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
            {
              v27 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v27 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v27 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CopySampleTexture", 600, v8);
          }
          if ( g_wppLevels )
          {
            v12 = 24;
            goto LABEL_12;
          }
        }
        else
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v22 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)v24 + 499) != v8 )
              CallStackContext::TraceFailure(v24, "CopySampleTexture", 599, v8);
          }
          if ( g_wppLevels )
          {
            v12 = 23;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v20 + 499) != v8 )
            CallStackContext::TraceFailure(v20, "CopySampleTexture", 598, v8);
        }
        if ( g_wppLevels )
        {
          v12 = 22;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != v8 )
          CallStackContext::TraceFailure(v17, "CopySampleTexture", 597, v8);
      }
      if ( g_wppLevels )
      {
        v12 = 21;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != v8 )
        CallStackContext::TraceFailure(v11, "CopySampleTexture", 596, v8);
    }
    if ( g_wppLevels )
    {
      v12 = 20;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_30d13c7481f9330926eccd3bdf8c4cd0_Traceguids, 0, v8);
    }
  }
LABEL_58:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v32);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800b9c40  mov     [rsp-8+arg_10], r8d
0x1800b9c45  push    rbp
0x1800b9c46  push    rbx
0x1800b9c47  push    rsi
0x1800b9c48  push    rdi
0x1800b9c49  push    r14
0x1800b9c4b  push    r15
0x1800b9c4d  lea     rbp, [rsp-27h]
0x1800b9c52  sub     rsp, 88h
0x1800b9c59  mov     rsi, r9
0x1800b9c5c  mov     rbx, rdx
0x1800b9c5f  xor     r14d, r14d
0x1800b9c62  mov     [rbp+4Fh+arg_10], r14d
0x1800b9c66  mov     qword ptr [rbp+4Fh+var_58], r14
0x1800b9c6a  mov     qword ptr [rbp+4Fh+var_40], r14
0x1800b9c6e  mov     [rbp+4Fh+var_48], r14
0x1800b9c72  mov     [rbp+4Fh+var_50], r14
0x1800b9c76  mov     edi, 254h
0x1800b9c7b  mov     r8d, edi; int
0x1800b9c7e  lea     r15, aCopysampletext; "CopySampleTexture"
0x1800b9c85  mov     rdx, r15; char *
0x1800b9c88  lea     rcx, [rbp+4Fh+var_60]; this
0x1800b9c8c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b9c91  nop
0x1800b9c92  lea     rcx, [rbp+4Fh+var_58]
0x1800b9c96  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b9c9b  lea     r8, [rbp+4Fh+var_58]; unsigned int
0x1800b9c9f  xor     edx, edx; struct IMFSample *
0x1800b9ca1  mov     rcx, rbx; this
0x1800b9ca4  call    ?DXGIBufferFromSample@MFD3D@@YAJPEAUIMFSample@@KPEAPEAUIMFDXGIBuffer@@@Z; MFD3D::DXGIBufferFromSample(IMFSample *,ulong,IMFDXGIBuffer * *)
0x1800b9ca9  mov     ebx, eax
0x1800b9cab  test    eax, eax
0x1800b9cad  jns     loc_1800B9D59
0x1800b9cb3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9cba  test    rcx, rcx
0x1800b9cbd  jnz     short loc_1800B9D00
0x1800b9cbf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b9cc5  mov     rcx, rax
0x1800b9cc8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9ccf  test    rax, rax
0x1800b9cd2  jz      short loc_1800B9CF2
0x1800b9cd4  mov     rax, [rax]
0x1800b9cd7  mov     edx, 7F0h
0x1800b9cdc  mov     rax, [rax+8]
0x1800b9ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9ce5  test    eax, eax
0x1800b9ce7  jz      short loc_1800B9CF2
0x1800b9ce9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9cf0  jmp     short loc_1800B9D00
0x1800b9cf2  lea     rcx, qword_180153440; this
0x1800b9cf9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9d00  cmp     [rcx+8], r14b
0x1800b9d04  jz      short loc_1800B9D24
0x1800b9d06  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b9d0b  cmp     [rax+7CCh], ebx
0x1800b9d11  jz      short loc_1800B9D24
0x1800b9d13  mov     r9d, ebx; int
0x1800b9d16  mov     r8d, edi; int
0x1800b9d19  mov     rdx, r15; char *
0x1800b9d1c  mov     rcx, rax; this
0x1800b9d1f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b9d24  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b9d2b  jb      loc_1800BA065
0x1800b9d31  mov     edx, 14h
0x1800b9d36  mov     [rsp+0B0h+var_90], ebx
0x1800b9d3a  xor     r9d, r9d
0x1800b9d3d  lea     r8, WPP_30d13c7481f9330926eccd3bdf8c4cd0_Traceguids
0x1800b9d44  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9d4b  mov     rcx, [rcx+10h]
0x1800b9d4f  call    WPP_SF_qD
0x1800b9d54  jmp     loc_1800BA065
0x1800b9d59  mov     rdi, qword ptr [rbp+4Fh+var_58]
0x1800b9d5d  mov     rax, [rdi]
0x1800b9d60  mov     rbx, [rax+18h]
0x1800b9d64  lea     rcx, [rbp+4Fh+var_48]
0x1800b9d68  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b9d6d  lea     r8, [rbp+4Fh+var_48]
0x1800b9d71  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x1800b9d78  mov     rcx, rdi
0x1800b9d7b  mov     rax, rbx
0x1800b9d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9d83  mov     ebx, eax
0x1800b9d85  test    eax, eax
0x1800b9d87  jns     loc_1800B9E18
0x1800b9d8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9d94  test    rcx, rcx
0x1800b9d97  jnz     short loc_1800B9DDA
0x1800b9d99  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b9d9f  mov     rcx, rax
0x1800b9da2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9da9  test    rax, rax
0x1800b9dac  jz      short loc_1800B9DCC
0x1800b9dae  mov     rax, [rax]
0x1800b9db1  mov     edx, 7F0h
0x1800b9db6  mov     rax, [rax+8]
0x1800b9dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9dbf  test    eax, eax
0x1800b9dc1  jz      short loc_1800B9DCC
0x1800b9dc3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9dca  jmp     short loc_1800B9DDA
0x1800b9dcc  lea     rcx, qword_180153440; this
0x1800b9dd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9dda  cmp     [rcx+8], r14b
0x1800b9dde  jz      short loc_1800B9E01
0x1800b9de0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b9de5  cmp     [rax+7CCh], ebx
0x1800b9deb  jz      short loc_1800B9E01
0x1800b9ded  mov     r9d, ebx; int
0x1800b9df0  mov     r8d, 255h; int
0x1800b9df6  mov     rdx, r15; char *
0x1800b9df9  mov     rcx, rax; this
0x1800b9dfc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b9e01  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b9e08  jb      loc_1800BA065
0x1800b9e0e  mov     edx, 15h
0x1800b9e13  jmp     loc_1800B9D36
0x1800b9e18  mov     rcx, qword ptr [rbp+4Fh+var_58]
0x1800b9e1c  mov     rax, [rcx]
0x1800b9e1f  lea     rdx, [rbp+4Fh+arg_10]
0x1800b9e23  mov     rax, [rax+20h]
0x1800b9e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9e2c  mov     ebx, eax
0x1800b9e2e  test    eax, eax
0x1800b9e30  jns     loc_1800B9EC1
0x1800b9e36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9e3d  test    rcx, rcx
0x1800b9e40  jnz     short loc_1800B9E83
0x1800b9e42  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b9e48  mov     rcx, rax
0x1800b9e4b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9e52  test    rax, rax
0x1800b9e55  jz      short loc_1800B9E75
0x1800b9e57  mov     rax, [rax]
0x1800b9e5a  mov     edx, 7F0h
0x1800b9e5f  mov     rax, [rax+8]
0x1800b9e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9e68  test    eax, eax
0x1800b9e6a  jz      short loc_1800B9E75
0x1800b9e6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9e73  jmp     short loc_1800B9E83
0x1800b9e75  lea     rcx, qword_180153440; this
0x1800b9e7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9e83  cmp     [rcx+8], r14b
0x1800b9e87  jz      short loc_1800B9EAA
0x1800b9e89  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b9e8e  cmp     [rax+7CCh], ebx
0x1800b9e94  jz      short loc_1800B9EAA
0x1800b9e96  mov     r9d, ebx; int
0x1800b9e99  mov     r8d, 256h; int
0x1800b9e9f  mov     rdx, r15; char *
0x1800b9ea2  mov     rcx, rax; this
0x1800b9ea5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b9eaa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b9eb1  jb      loc_1800BA065
0x1800b9eb7  mov     edx, 16h
0x1800b9ebc  jmp     loc_1800B9D36
0x1800b9ec1  lea     rcx, [rbp+4Fh+var_40]
0x1800b9ec5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b9eca  lea     r8, [rbp+4Fh+var_40]; unsigned int
0x1800b9ece  xor     edx, edx; struct IMFSample *
0x1800b9ed0  mov     rcx, rsi; this
0x1800b9ed3  call    ?DXGIBufferFromSample@MFD3D@@YAJPEAUIMFSample@@KPEAPEAUIMFDXGIBuffer@@@Z; MFD3D::DXGIBufferFromSample(IMFSample *,ulong,IMFDXGIBuffer * *)
0x1800b9ed8  mov     ebx, eax
0x1800b9eda  test    eax, eax
0x1800b9edc  jns     loc_1800B9F6D
0x1800b9ee2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9ee9  test    rcx, rcx
0x1800b9eec  jnz     short loc_1800B9F2F
0x1800b9eee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b9ef4  mov     rcx, rax
0x1800b9ef7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9efe  test    rax, rax
0x1800b9f01  jz      short loc_1800B9F21
0x1800b9f03  mov     rax, [rax]
0x1800b9f06  mov     edx, 7F0h
0x1800b9f0b  mov     rax, [rax+8]
0x1800b9f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9f14  test    eax, eax
0x1800b9f16  jz      short loc_1800B9F21
0x1800b9f18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9f1f  jmp     short loc_1800B9F2F
0x1800b9f21  lea     rcx, qword_180153440; this
0x1800b9f28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9f2f  cmp     [rcx+8], r14b
0x1800b9f33  jz      short loc_1800B9F56
0x1800b9f35  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b9f3a  cmp     [rax+7CCh], ebx
0x1800b9f40  jz      short loc_1800B9F56
0x1800b9f42  mov     r9d, ebx; int
0x1800b9f45  mov     r8d, 257h; int
0x1800b9f4b  mov     rdx, r15; char *
0x1800b9f4e  mov     rcx, rax; this
0x1800b9f51  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b9f56  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b9f5d  jb      loc_1800BA065
0x1800b9f63  mov     edx, 17h
0x1800b9f68  jmp     loc_1800B9D36
0x1800b9f6d  mov     rdi, qword ptr [rbp+4Fh+var_40]
0x1800b9f71  mov     rax, [rdi]
0x1800b9f74  mov     rbx, [rax+18h]
0x1800b9f78  lea     rcx, [rbp+4Fh+var_50]
0x1800b9f7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b9f81  lea     r8, [rbp+4Fh+var_50]
0x1800b9f85  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x1800b9f8c  mov     rcx, rdi
0x1800b9f8f  mov     rax, rbx
0x1800b9f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9f97  mov     ebx, eax
0x1800b9f99  test    eax, eax
0x1800b9f9b  jns     loc_1800BA028
0x1800b9fa1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9fa8  test    rcx, rcx
0x1800b9fab  jnz     short loc_1800B9FEE
0x1800b9fad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b9fb3  mov     rcx, rax
0x1800b9fb6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9fbd  test    rax, rax
0x1800b9fc0  jz      short loc_1800B9FE0
0x1800b9fc2  mov     rax, [rax]
0x1800b9fc5  mov     edx, 7F0h
0x1800b9fca  mov     rax, [rax+8]
0x1800b9fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9fd3  test    eax, eax
0x1800b9fd5  jz      short loc_1800B9FE0
0x1800b9fd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9fde  jmp     short loc_1800B9FEE
0x1800b9fe0  lea     rcx, qword_180153440; this
0x1800b9fe7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9fee  cmp     [rcx+8], r14b
0x1800b9ff2  jz      short loc_1800BA015
0x1800b9ff4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b9ff9  cmp     [rax+7CCh], ebx
0x1800b9fff  jz      short loc_1800BA015
0x1800ba001  mov     r9d, ebx; int
0x1800ba004  mov     r8d, 258h; int
0x1800ba00a  mov     rdx, r15; char *
0x1800ba00d  mov     rcx, rax; this
0x1800ba010  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ba015  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ba01c  jb      short loc_1800BA065
0x1800ba01e  mov     edx, 18h
0x1800ba023  jmp     loc_1800B9D36
0x1800ba028  mov     rcx, [rbp+4Fh+arg_20]
0x1800ba02c  mov     rax, [rcx]
0x1800ba02f  mov     [rsp+0B0h+var_70], r14
0x1800ba034  mov     edx, [rbp+4Fh+arg_10]
0x1800ba037  mov     [rsp+0B0h+var_78], edx
0x1800ba03b  mov     rdx, [rbp+4Fh+var_48]
0x1800ba03f  mov     [rsp+0B0h+var_80], rdx
0x1800ba044  mov     [rsp+0B0h+var_88], r14d
0x1800ba049  mov     [rsp+0B0h+var_90], r14d
0x1800ba04e  xor     r9d, r9d
0x1800ba051  xor     r8d, r8d
0x1800ba054  mov     rdx, [rbp+4Fh+var_50]
0x1800ba058  mov     rax, [rax+170h]
0x1800ba05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba064  nop
0x1800ba065  lea     rcx, [rbp+4Fh+var_60]; this
0x1800ba069  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ba06e  nop
0x1800ba06f  lea     rcx, [rbp+4Fh+var_50]
0x1800ba073  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ba078  nop
0x1800ba079  lea     rcx, [rbp+4Fh+var_48]
0x1800ba07d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ba082  nop
0x1800ba083  lea     rcx, [rbp+4Fh+var_40]
0x1800ba087  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ba08c  nop
0x1800ba08d  lea     rcx, [rbp+4Fh+var_58]
0x1800ba091  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ba096  mov     eax, ebx
0x1800ba098  add     rsp, 88h
0x1800ba09f  pop     r15
0x1800ba0a1  pop     r14
0x1800ba0a3  pop     rdi
0x1800ba0a4  pop     rsi
0x1800ba0a5  pop     rbx
0x1800ba0a6  pop     rbp
0x1800ba0a7  retn
```
