# CRolling420FrameStitcherMFTDataHandler::CreateShaderOutputView(IMFSample *,ID3D11RenderTargetView * *)

- ea: `0x1800b6ed8`
- end: `0x1800b72b5`
- name: `?CreateShaderOutputView@CRolling420FrameStitcherMFTDataHandler@@IEAAJPEAUIMFSample@@PEAPEAUID3D11RenderTargetView@@@Z`
- size: `989`
- prototype: `__int64 __fastcall(CRolling420FrameStitcherMFTDataHandler *__hidden this, struct IMFSample *, struct ID3D11RenderTargetView **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180043a90`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180054140`
- `0x1800b6ed8`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6f81`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b703f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b70fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b71d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6f81`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b703f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b70fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b71d8`

## string_xrefs

- `0x1800b6f22`: `CRolling420FrameStitcherMFTDataHandler::CreateShaderOutputView`

## pseudocode

```c
__int64 __fastcall CRolling420FrameStitcherMFTDataHandler::CreateShaderOutputView(
        CRolling420FrameStitcherMFTDataHandler *this,
        struct IMFSample *a2,
        struct ID3D11RenderTargetView **a3)
{
  HRESULT (__stdcall *GetBufferByIndex)(IMFSample *, DWORD, IMFMediaBuffer **); // rbx
  int v7; // ebx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, GUID *, __int64 *); // rbx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rcx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v27[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v28; // [rsp+38h] [rbp-31h] BYREF
  __int64 v29; // [rsp+40h] [rbp-29h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-21h] BYREF
  int v31; // [rsp+50h] [rbp-19h] BYREF
  __int64 v32; // [rsp+54h] [rbp-15h]
  __int64 v33; // [rsp+5Ch] [rbp-Dh]
  _OWORD v34[3]; // [rsp+68h] [rbp-1h] BYREF

  v30 = 0;
  v29 = 0;
  v28 = 0;
  memset(v34, 0, 44);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v27,
    "CRolling420FrameStitcherMFTDataHandler::CreateShaderOutputView",
    469);
  GetBufferByIndex = a2->lpVtbl->GetBufferByIndex;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  v7 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD, _QWORD))GetBufferByIndex)(a2, 0, &v30);
  if ( v7 >= 0 )
  {
    v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v30;
    v13 = **v30;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v7 = v13(v12, &GUID_e7174cfa_1c9e_48b1_8866_626226bfc258, &v29);
    if ( v7 >= 0 )
    {
      v17 = v29;
      v18 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v29 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      v7 = v18(v17, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v28);
      if ( v7 >= 0 )
      {
        (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v28 + 80LL))(v28, v34);
        v22 = *((_QWORD *)this + 7);
        v31 = v34[1];
        v33 = 0;
        v32 = 4;
        v7 = (*(__int64 (__fastcall **)(__int64, __int64, int *, struct ID3D11RenderTargetView **))(*(_QWORD *)v22 + 72LL))(
               v22,
               v28,
               &v31,
               a3);
        if ( v7 < 0 )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
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
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CRolling420FrameStitcherMFTDataHandler::CreateShaderOutputView",
                480,
                v7);
          }
          if ( g_wppLevels )
          {
            v11 = 75;
            goto LABEL_45;
          }
        }
      }
      else
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)v21 + 499) != v7 )
            CallStackContext::TraceFailure(
              v21,
              "CRolling420FrameStitcherMFTDataHandler::CreateShaderOutputView",
              471,
              v7);
        }
        if ( g_wppLevels )
        {
          v11 = 74;
          goto LABEL_45;
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
        if ( *((_DWORD *)v16 + 499) != v7 )
          CallStackContext::TraceFailure(v16, "CRolling420FrameStitcherMFTDataHandler::CreateShaderOutputView", 470, v7);
      }
      if ( g_wppLevels )
      {
        v11 = 73;
        goto LABEL_45;
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
      if ( *((_DWORD *)v10 + 499) != v7 )
        CallStackContext::TraceFailure(v10, "CRolling420FrameStitcherMFTDataHandler::CreateShaderOutputView", 469, v7);
    }
    if ( g_wppLevels )
    {
      v11 = 72;
LABEL_45:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids, this, v7);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v27);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800b6ed8  mov     [rsp-8+arg_18], rbx
0x1800b6edd  push    rbp
0x1800b6ede  push    rsi
0x1800b6edf  push    rdi
0x1800b6ee0  push    r12
0x1800b6ee2  push    r14
0x1800b6ee4  lea     rbp, [rsp-37h]
0x1800b6ee9  sub     rsp, 0A0h
0x1800b6ef0  mov     rax, cs:__security_cookie
0x1800b6ef7  xor     rax, rsp
0x1800b6efa  mov     [rbp+57h+var_28], rax
0x1800b6efe  xorps   xmm0, xmm0
0x1800b6f01  mov     [rbp+57h+var_78], 0
0x1800b6f09  mov     r14, r8
0x1800b6f0c  mov     [rbp+57h+var_80], 0
0x1800b6f14  mov     rdi, rdx
0x1800b6f17  mov     [rbp+57h+var_88], 0
0x1800b6f1f  mov     rsi, rcx
0x1800b6f22  lea     r12, aCrolling420fra_7; "CRolling420FrameStitcherMFTDataHandler:"...
0x1800b6f29  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x1800b6f2d  mov     rdx, r12; char *
0x1800b6f30  lea     rcx, [rbp+57h+var_90]; this
0x1800b6f34  mov     r8d, 1D5h; int
0x1800b6f3a  movups  xmmword ptr [rbp+57h+var_48+0Ch], xmm0
0x1800b6f3e  movups  [rbp+57h+var_58], xmm0
0x1800b6f42  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b6f47  mov     rax, [rdi]
0x1800b6f4a  lea     rcx, [rbp+57h+var_78]
0x1800b6f4e  mov     rbx, [rax+140h]
0x1800b6f55  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b6f5a  lea     r8, [rbp+57h+var_78]
0x1800b6f5e  xor     edx, edx
0x1800b6f60  mov     rcx, rdi
0x1800b6f63  mov     rax, rbx
0x1800b6f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6f6b  mov     ebx, eax
0x1800b6f6d  test    eax, eax
0x1800b6f6f  jns     loc_1800B7000
0x1800b6f75  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6f7c  test    rcx, rcx
0x1800b6f7f  jnz     short loc_1800B6FC2
0x1800b6f81  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b6f87  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6f8e  mov     rcx, rax
0x1800b6f91  test    rax, rax
0x1800b6f94  jz      short loc_1800B6FB4
0x1800b6f96  mov     rax, [rax]
0x1800b6f99  mov     edx, 7F0h
0x1800b6f9e  mov     rax, [rax+8]
0x1800b6fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6fa7  test    eax, eax
0x1800b6fa9  jz      short loc_1800B6FB4
0x1800b6fab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6fb2  jmp     short loc_1800B6FC2
0x1800b6fb4  lea     rcx, qword_180153440; this
0x1800b6fbb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6fc2  cmp     byte ptr [rcx+8], 0
0x1800b6fc6  jz      short loc_1800B6FE9
0x1800b6fc8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b6fcd  cmp     [rax+7CCh], ebx
0x1800b6fd3  jz      short loc_1800B6FE9
0x1800b6fd5  mov     r9d, ebx; int
0x1800b6fd8  mov     r8d, 1D5h; int
0x1800b6fde  mov     rdx, r12; char *
0x1800b6fe1  mov     rcx, rax; this
0x1800b6fe4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b6fe9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6ff0  jb      loc_1800B726C
0x1800b6ff6  mov     edx, 48h ; 'H'
0x1800b6ffb  jmp     loc_1800B724E
0x1800b7000  mov     rdi, [rbp+57h+var_78]
0x1800b7004  lea     rcx, [rbp+57h+var_80]
0x1800b7008  mov     rax, [rdi]
0x1800b700b  mov     rbx, [rax]
0x1800b700e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7013  lea     r8, [rbp+57h+var_80]
0x1800b7017  mov     rcx, rdi
0x1800b701a  lea     rdx, _GUID_e7174cfa_1c9e_48b1_8866_626226bfc258
0x1800b7021  mov     rax, rbx
0x1800b7024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7029  mov     ebx, eax
0x1800b702b  test    eax, eax
0x1800b702d  jns     loc_1800B70BE
0x1800b7033  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b703a  test    rcx, rcx
0x1800b703d  jnz     short loc_1800B7080
0x1800b703f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7045  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b704c  mov     rcx, rax
0x1800b704f  test    rax, rax
0x1800b7052  jz      short loc_1800B7072
0x1800b7054  mov     rax, [rax]
0x1800b7057  mov     edx, 7F0h
0x1800b705c  mov     rax, [rax+8]
0x1800b7060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7065  test    eax, eax
0x1800b7067  jz      short loc_1800B7072
0x1800b7069  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7070  jmp     short loc_1800B7080
0x1800b7072  lea     rcx, qword_180153440; this
0x1800b7079  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7080  cmp     byte ptr [rcx+8], 0
0x1800b7084  jz      short loc_1800B70A7
0x1800b7086  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b708b  cmp     [rax+7CCh], ebx
0x1800b7091  jz      short loc_1800B70A7
0x1800b7093  mov     r9d, ebx; int
0x1800b7096  mov     r8d, 1D6h; int
0x1800b709c  mov     rdx, r12; char *
0x1800b709f  mov     rcx, rax; this
0x1800b70a2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b70a7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b70ae  jb      loc_1800B726C
0x1800b70b4  mov     edx, 49h ; 'I'
0x1800b70b9  jmp     loc_1800B724E
0x1800b70be  mov     rdi, [rbp+57h+var_80]
0x1800b70c2  lea     rcx, [rbp+57h+var_88]
0x1800b70c6  mov     rax, [rdi]
0x1800b70c9  mov     rbx, [rax+18h]
0x1800b70cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b70d2  lea     r8, [rbp+57h+var_88]
0x1800b70d6  mov     rcx, rdi
0x1800b70d9  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x1800b70e0  mov     rax, rbx
0x1800b70e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b70e8  mov     ebx, eax
0x1800b70ea  test    eax, eax
0x1800b70ec  jns     loc_1800B717D
0x1800b70f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b70f9  test    rcx, rcx
0x1800b70fc  jnz     short loc_1800B713F
0x1800b70fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7104  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b710b  mov     rcx, rax
0x1800b710e  test    rax, rax
0x1800b7111  jz      short loc_1800B7131
0x1800b7113  mov     rax, [rax]
0x1800b7116  mov     edx, 7F0h
0x1800b711b  mov     rax, [rax+8]
0x1800b711f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7124  test    eax, eax
0x1800b7126  jz      short loc_1800B7131
0x1800b7128  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b712f  jmp     short loc_1800B713F
0x1800b7131  lea     rcx, qword_180153440; this
0x1800b7138  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b713f  cmp     byte ptr [rcx+8], 0
0x1800b7143  jz      short loc_1800B7166
0x1800b7145  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b714a  cmp     [rax+7CCh], ebx
0x1800b7150  jz      short loc_1800B7166
0x1800b7152  mov     r9d, ebx; int
0x1800b7155  mov     r8d, 1D7h; int
0x1800b715b  mov     rdx, r12; char *
0x1800b715e  mov     rcx, rax; this
0x1800b7161  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7166  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b716d  jb      loc_1800B726C
0x1800b7173  mov     edx, 4Ah ; 'J'
0x1800b7178  jmp     loc_1800B724E
0x1800b717d  mov     rcx, [rbp+57h+var_88]
0x1800b7181  lea     rdx, [rbp+57h+var_58]
0x1800b7185  mov     rax, [rcx]
0x1800b7188  mov     rax, [rax+50h]
0x1800b718c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7191  mov     eax, dword ptr [rbp+57h+var_48]
0x1800b7194  lea     r8, [rbp+57h+var_70]
0x1800b7198  mov     rcx, [rsi+38h]
0x1800b719c  mov     r9, r14
0x1800b719f  mov     rdx, [rbp+57h+var_88]
0x1800b71a3  mov     [rbp+57h+var_70], eax
0x1800b71a6  mov     [rbp+57h+var_64], 0
0x1800b71ae  mov     [rbp+57h+var_6C], 4
0x1800b71b6  mov     rax, [rcx]
0x1800b71b9  mov     rax, [rax+48h]
0x1800b71bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b71c2  mov     ebx, eax
0x1800b71c4  test    eax, eax
0x1800b71c6  jns     loc_1800B726C
0x1800b71cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b71d3  test    rcx, rcx
0x1800b71d6  jnz     short loc_1800B7219
0x1800b71d8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b71de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b71e5  mov     rcx, rax
0x1800b71e8  test    rax, rax
0x1800b71eb  jz      short loc_1800B720B
0x1800b71ed  mov     rax, [rax]
0x1800b71f0  mov     edx, 7F0h
0x1800b71f5  mov     rax, [rax+8]
0x1800b71f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b71fe  test    eax, eax
0x1800b7200  jz      short loc_1800B720B
0x1800b7202  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7209  jmp     short loc_1800B7219
0x1800b720b  lea     rcx, qword_180153440; this
0x1800b7212  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7219  cmp     byte ptr [rcx+8], 0
0x1800b721d  jz      short loc_1800B7240
0x1800b721f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b7224  cmp     [rax+7CCh], ebx
0x1800b722a  jz      short loc_1800B7240
0x1800b722c  mov     r9d, ebx; int
0x1800b722f  mov     r8d, 1E0h; int
0x1800b7235  mov     rdx, r12; char *
0x1800b7238  mov     rcx, rax; this
0x1800b723b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7240  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b7247  jb      short loc_1800B726C
0x1800b7249  mov     edx, 4Bh ; 'K'
0x1800b724e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7255  lea     r8, WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids
0x1800b725c  mov     r9, rsi
0x1800b725f  mov     [rsp+0C0h+var_A0], ebx
0x1800b7263  mov     rcx, [rcx+10h]
0x1800b7267  call    WPP_SF_qD
0x1800b726c  lea     rcx, [rbp+57h+var_90]; this
0x1800b7270  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b7275  lea     rcx, [rbp+57h+var_88]
0x1800b7279  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b727e  lea     rcx, [rbp+57h+var_80]
0x1800b7282  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7287  lea     rcx, [rbp+57h+var_78]
0x1800b728b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7290  mov     eax, ebx
0x1800b7292  mov     rcx, [rbp+57h+var_28]
0x1800b7296  xor     rcx, rsp; StackCookie
0x1800b7299  call    __security_check_cookie
0x1800b729e  mov     rbx, [rsp+0C0h+arg_18]
0x1800b72a6  add     rsp, 0A0h
0x1800b72ad  pop     r14
0x1800b72af  pop     r12
0x1800b72b1  pop     rdi
0x1800b72b2  pop     rsi
0x1800b72b3  pop     rbp
0x1800b72b4  retn
```
