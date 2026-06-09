# CRolling420FrameStitcherMFTDataHandler::CreateD3DBuffer(void)

- ea: `0x18003aefc`
- end: `0x18003b22f`
- name: `?CreateD3DBuffer@CRolling420FrameStitcherMFTDataHandler@@IEAAJXZ`
- size: `819`
- prototype: `__int64 __fastcall(CRolling420FrameStitcherMFTDataHandler *__hidden this)`
- caller_count: `2`
- callee_count: `9`
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
- `0x18003639c`
- `0x18003aefc`
- `0x180054140`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003afc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b0f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003afc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b0f9`

## string_xrefs

- `0x18003af4f`: `CRolling420FrameStitcherMFTDataHandler::CreateD3DBuffer`
- `0x18003b019`: `CRolling420FrameStitcherMFTDataHandler::CreateD3DBuffer`
- `0x18003b092`: `CRolling420FrameStitcherMFTDataHandler::CreateD3DBuffer`
- `0x18003b150`: `CRolling420FrameStitcherMFTDataHandler::CreateD3DBuffer`

## pseudocode

```c
__int64 __fastcall CRolling420FrameStitcherMFTDataHandler::CreateD3DBuffer(
        CRolling420FrameStitcherMFTDataHandler *this)
{
  char *v1; // r14
  int v3; // ebx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, int *, __int128 *, char *); // rbx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  _QWORD *v10; // r14
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, int *, _QWORD, char *); // rbx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  _BYTE v17[8]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v18; // [rsp+48h] [rbp-38h] BYREF
  int v19; // [rsp+58h] [rbp-28h] BYREF
  int v20; // [rsp+5Ch] [rbp-24h]
  int v21; // [rsp+60h] [rbp-20h]
  int v22; // [rsp+64h] [rbp-1Ch]
  __int64 v23; // [rsp+68h] [rbp-18h]

  v1 = (char *)this + 96;
  if ( *((_QWORD *)this + 12) )
  {
    v3 = 0;
  }
  else
  {
    v23 = 0;
    *(_QWORD *)&v18 = &CRolling420FrameStitcherMFTDataHandler::_svDefault;
    v20 = 2;
    v21 = 1;
    v22 = 0x10000;
    v19 = 96;
    *((_QWORD *)&v18 + 1) = 0;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v17,
      "CRolling420FrameStitcherMFTDataHandler::CreateD3DBuffer",
      504);
    v4 = *((_QWORD *)this + 7);
    v5 = *(__int64 (__fastcall **)(__int64, int *, __int128 *, char *))(*(_QWORD *)v4 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v1);
    v3 = v5(v4, &v19, &v18, v1);
    if ( v3 < 0 )
    {
      v6 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v7;
        if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
        {
          v6 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v6 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v6 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CRolling420FrameStitcherMFTDataHandler::CreateD3DBuffer",
            504,
            v3);
      }
      if ( !g_wppLevels )
        goto LABEL_30;
      v9 = 76;
      goto LABEL_14;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v17);
  }
  v10 = (_QWORD *)((char *)this + 104);
  if ( !*((_QWORD *)this + 13) )
  {
    v23 = 0;
    v19 = 64;
    v20 = 2;
    v21 = 4;
    v18 = 0;
    v22 = 0x10000;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v17,
      "CRolling420FrameStitcherMFTDataHandler::CreateD3DBuffer",
      518);
    v11 = *((_QWORD *)this + 7);
    v12 = *(__int64 (__fastcall **)(__int64, int *, _QWORD, char *))(*(_QWORD *)v11 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 104);
    v3 = v12(v11, &v19, 0, (char *)this + 104);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, __int128 *))(**((_QWORD **)this + 8)
                                                                                          + 112LL))(
             *((_QWORD *)this + 8),
             *v10,
             0,
             4,
             0,
             &v18);
      if ( v3 >= 0 )
      {
        *(_OWORD *)v18 = DirectX::g_XMIdentityR0;
        *(_OWORD *)(v18 + 16) = DirectX::g_XMIdentityR1;
        *(_OWORD *)(v18 + 32) = DirectX::g_XMIdentityR2;
        *(_OWORD *)(v18 + 48) = DirectX::g_XMIdentityR3;
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 120LL))(
          *((_QWORD *)this + 8),
          *v10,
          0);
      }
      goto LABEL_30;
    }
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
      if ( *((_DWORD *)v15 + 499) != v3 )
        CallStackContext::TraceFailure(v15, "CRolling420FrameStitcherMFTDataHandler::CreateD3DBuffer", 518, v3);
    }
    if ( !g_wppLevels )
    {
LABEL_30:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v17);
      return (unsigned int)v3;
    }
    v9 = 77;
LABEL_14:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids, this, v3);
    goto LABEL_30;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003aefc  mov     [rsp-18h+arg_8], rbx
0x18003af01  mov     [rsp-18h+arg_10], rsi
0x18003af06  push    rbp
0x18003af07  push    rdi
0x18003af08  push    r14
0x18003af0a  mov     rbp, rsp
0x18003af0d  sub     rsp, 80h
0x18003af14  mov     rax, cs:__security_cookie
0x18003af1b  xor     rax, rsp
0x18003af1e  mov     [rbp+var_10], rax
0x18003af22  lea     r14, [rcx+60h]
0x18003af26  mov     rsi, rcx
0x18003af29  cmp     qword ptr [r14], 0
0x18003af2d  jz      short loc_18003AF36
0x18003af2f  xor     ebx, ebx
0x18003af31  jmp     loc_18003B06C
0x18003af36  lea     rax, ?_svDefault@CRolling420FrameStitcherMFTDataHandler@@0QBUScreenVertex@@B; ScreenVertex const near * const CRolling420FrameStitcherMFTDataHandler::_svDefault
0x18003af3d  mov     [rbp+var_18], 0
0x18003af45  mov     r8d, 1F8h; int
0x18003af4b  mov     qword ptr [rbp+var_38], rax
0x18003af4f  lea     rdx, aCrolling420fra_10; "CRolling420FrameStitcherMFTDataHandler:"...
0x18003af56  mov     [rbp+var_24], 2
0x18003af5d  lea     rcx, [rbp+var_40]; this
0x18003af61  mov     [rbp+var_20], 1
0x18003af68  mov     [rbp+var_1C], 10000h
0x18003af6f  mov     [rbp+var_28], 60h ; '`'
0x18003af76  mov     qword ptr [rbp+var_38+8], 0
0x18003af7e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003af83  mov     rdi, [rsi+38h]
0x18003af87  mov     rcx, r14
0x18003af8a  mov     rax, [rdi]
0x18003af8d  mov     rbx, [rax+18h]
0x18003af91  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003af96  mov     r9, r14
0x18003af99  lea     r8, [rbp+var_38]
0x18003af9d  lea     rdx, [rbp+var_28]
0x18003afa1  mov     rcx, rdi
0x18003afa4  mov     rax, rbx
0x18003afa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afac  mov     ebx, eax
0x18003afae  test    eax, eax
0x18003afb0  jns     loc_18003B063
0x18003afb6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003afbd  test    rcx, rcx
0x18003afc0  jnz     short loc_18003B003
0x18003afc2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003afc8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003afcf  mov     rcx, rax
0x18003afd2  test    rax, rax
0x18003afd5  jz      short loc_18003AFF5
0x18003afd7  mov     rax, [rax]
0x18003afda  mov     edx, 7F0h
0x18003afdf  mov     rax, [rax+8]
0x18003afe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afe8  test    eax, eax
0x18003afea  jz      short loc_18003AFF5
0x18003afec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003aff3  jmp     short loc_18003B003
0x18003aff5  lea     rcx, qword_180153440; this
0x18003affc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b003  cmp     byte ptr [rcx+8], 0
0x18003b007  jz      short loc_18003B02E
0x18003b009  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b00e  cmp     [rax+7CCh], ebx
0x18003b014  jz      short loc_18003B02E
0x18003b016  mov     r9d, ebx; int
0x18003b019  lea     rdx, aCrolling420fra_10; "CRolling420FrameStitcherMFTDataHandler:"...
0x18003b020  mov     r8d, 1F8h; int
0x18003b026  mov     rcx, rax; this
0x18003b029  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b02e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003b035  jb      loc_18003B200
0x18003b03b  mov     edx, 4Ch ; 'L'
0x18003b040  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b047  lea     r8, WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids
0x18003b04e  mov     r9, rsi
0x18003b051  mov     [rsp+80h+var_60], ebx
0x18003b055  mov     rcx, [rcx+10h]
0x18003b059  call    WPP_SF_qD
0x18003b05e  jmp     loc_18003B200
0x18003b063  lea     rcx, [rbp+var_40]; this
0x18003b067  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003b06c  lea     r14, [rsi+68h]
0x18003b070  cmp     qword ptr [r14], 0
0x18003b074  jnz     loc_18003B209
0x18003b07a  xorps   xmm0, xmm0
0x18003b07d  mov     [rbp+var_18], 0
0x18003b085  mov     r8d, 206h; int
0x18003b08b  mov     [rbp+var_28], 40h ; '@'
0x18003b092  lea     rdx, aCrolling420fra_10; "CRolling420FrameStitcherMFTDataHandler:"...
0x18003b099  mov     [rbp+var_24], 2
0x18003b0a0  lea     rcx, [rbp+var_40]; this
0x18003b0a4  mov     [rbp+var_20], 4
0x18003b0ab  movups  [rbp+var_38], xmm0
0x18003b0af  mov     [rbp+var_1C], 10000h
0x18003b0b6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b0bb  mov     rdi, [rsi+38h]
0x18003b0bf  mov     rcx, r14
0x18003b0c2  mov     rax, [rdi]
0x18003b0c5  mov     rbx, [rax+18h]
0x18003b0c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b0ce  mov     r9, r14
0x18003b0d1  lea     rdx, [rbp+var_28]
0x18003b0d5  xor     r8d, r8d
0x18003b0d8  mov     rcx, rdi
0x18003b0db  mov     rax, rbx
0x18003b0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0e3  mov     ebx, eax
0x18003b0e5  test    eax, eax
0x18003b0e7  jns     loc_18003B17C
0x18003b0ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b0f4  test    rcx, rcx
0x18003b0f7  jnz     short loc_18003B13A
0x18003b0f9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b0ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b106  mov     rcx, rax
0x18003b109  test    rax, rax
0x18003b10c  jz      short loc_18003B12C
0x18003b10e  mov     rax, [rax]
0x18003b111  mov     edx, 7F0h
0x18003b116  mov     rax, [rax+8]
0x18003b11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b11f  test    eax, eax
0x18003b121  jz      short loc_18003B12C
0x18003b123  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b12a  jmp     short loc_18003B13A
0x18003b12c  lea     rcx, qword_180153440; this
0x18003b133  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b13a  cmp     byte ptr [rcx+8], 0
0x18003b13e  jz      short loc_18003B165
0x18003b140  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b145  cmp     [rax+7CCh], ebx
0x18003b14b  jz      short loc_18003B165
0x18003b14d  mov     r9d, ebx; int
0x18003b150  lea     rdx, aCrolling420fra_10; "CRolling420FrameStitcherMFTDataHandler:"...
0x18003b157  mov     r8d, 206h; int
0x18003b15d  mov     rcx, rax; this
0x18003b160  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b165  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003b16c  jb      loc_18003B200
0x18003b172  mov     edx, 4Dh ; 'M'
0x18003b177  jmp     loc_18003B040
0x18003b17c  mov     rcx, [rsi+40h]
0x18003b180  lea     rdx, [rbp+var_38]
0x18003b184  mov     [rsp+80h+var_58], rdx
0x18003b189  mov     r9d, 4
0x18003b18f  mov     rdx, [r14]
0x18003b192  xor     r8d, r8d
0x18003b195  mov     [rsp+80h+var_60], 0
0x18003b19d  mov     rax, [rcx]
0x18003b1a0  mov     rax, [rax+70h]
0x18003b1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1a9  mov     ebx, eax
0x18003b1ab  test    eax, eax
0x18003b1ad  js      short loc_18003B200
0x18003b1af  mov     rax, qword ptr [rbp+var_38]
0x18003b1b3  xor     r8d, r8d
0x18003b1b6  movaps  xmm0, cs:?g_XMIdentityR0@DirectX@@3UXMVECTORF32@1@B; DirectX::XMVECTORF32 const DirectX::g_XMIdentityR0
0x18003b1bd  movaps  xmm1, cs:?g_XMIdentityR1@DirectX@@3UXMVECTORF32@1@B; DirectX::XMVECTORF32 const DirectX::g_XMIdentityR1
0x18003b1c4  movaps  xmm2, cs:?g_XMIdentityR2@DirectX@@3UXMVECTORF32@1@B; DirectX::XMVECTORF32 const DirectX::g_XMIdentityR2
0x18003b1cb  movaps  xmm3, cs:?g_XMIdentityR3@DirectX@@3UXMVECTORF32@1@B; DirectX::XMVECTORF32 const DirectX::g_XMIdentityR3
0x18003b1d2  movups  xmmword ptr [rax], xmm0
0x18003b1d5  mov     rax, qword ptr [rbp+var_38]
0x18003b1d9  movups  xmmword ptr [rax+10h], xmm1
0x18003b1dd  mov     rax, qword ptr [rbp+var_38]
0x18003b1e1  movups  xmmword ptr [rax+20h], xmm2
0x18003b1e5  mov     rax, qword ptr [rbp+var_38]
0x18003b1e9  movups  xmmword ptr [rax+30h], xmm3
0x18003b1ed  mov     rcx, [rsi+40h]
0x18003b1f1  mov     rdx, [r14]
0x18003b1f4  mov     rax, [rcx]
0x18003b1f7  mov     rax, [rax+78h]
0x18003b1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b200  lea     rcx, [rbp+var_40]; this
0x18003b204  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003b209  mov     eax, ebx
0x18003b20b  mov     rcx, [rbp+var_10]
0x18003b20f  xor     rcx, rsp; StackCookie
0x18003b212  call    __security_check_cookie
0x18003b217  lea     r11, [rsp+80h+var_s0]
0x18003b21f  mov     rbx, [r11+28h]
0x18003b223  mov     rsi, [r11+30h]
0x18003b227  mov     rsp, r11
0x18003b22a  pop     r14
0x18003b22c  pop     rdi
0x18003b22d  pop     rbp
0x18003b22e  retn
```
