# CRolling420FrameStitcherMFTDataHandler::CreateShaderInputView(ID3D11ShaderResourceView * *,ulong)

- ea: `0x1800b6798`
- end: `0x1800b6ed0`
- name: `?CreateShaderInputView@CRolling420FrameStitcherMFTDataHandler@@IEAAJPEAPEAUID3D11ShaderResourceView@@K@Z`
- size: `1848`
- prototype: `__int64 __fastcall(CRolling420FrameStitcherMFTDataHandler *__hidden this, struct ID3D11ShaderResourceView **, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180043a90`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001bdb0`
- `0x18001e060`
- `0x18003639c`
- `0x180054140`
- `0x1800b6798`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6879`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6937`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b69f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6ab6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6b74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6c33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6d14`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6dc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6879`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6937`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b69f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6ab6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6b74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6c33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6d14`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6dc5`

## string_xrefs

- `0x1800b67c7`: `CRolling420FrameStitcherMFTDataHandler::CreateShaderInputView`

## pseudocode

```c
__int64 __fastcall CRolling420FrameStitcherMFTDataHandler::CreateShaderInputView(
        CRolling420FrameStitcherMFTDataHandler *this,
        struct ID3D11ShaderResourceView **a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, _QWORD); // rbx
  int v6; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, GUID *, __int64 *); // rbx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, _QWORD); // rbx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v27)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, GUID *, __int64 *); // rbx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rcx
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v44[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v45; // [rsp+38h] [rbp-51h] BYREF
  __int64 v46; // [rsp+40h] [rbp-49h] BYREF
  __int64 v47; // [rsp+48h] [rbp-41h] BYREF
  __int64 v48; // [rsp+50h] [rbp-39h] BYREF
  __int64 (__fastcall ***v49)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-31h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-29h] BYREF
  int v51; // [rsp+68h] [rbp-21h] BYREF
  __int64 v52; // [rsp+6Ch] [rbp-1Dh]
  int v53; // [rsp+74h] [rbp-15h]
  __int64 v54; // [rsp+78h] [rbp-11h]
  _OWORD v55[3]; // [rsp+80h] [rbp-9h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v44,
    "CRolling420FrameStitcherMFTDataHandler::CreateShaderInputView",
    425);
  `vector constructor iterator'(&v49, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::ComPtr<ID3D11ComputeShader>);
  `vector constructor iterator'(&v47, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::ComPtr<ID3D11ComputeShader>);
  `vector constructor iterator'(&v45, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::ComPtr<ID3D11ComputeShader>);
  v4 = *((_QWORD *)this + 2);
  memset(v55, 0, 44);
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v4 + 320LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  v6 = v5(v4, 0, &v49);
  if ( v6 >= 0 )
  {
    v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
    v12 = **v49;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    v6 = v12(v11, &GUID_e7174cfa_1c9e_48b1_8866_626226bfc258, &v47);
    if ( v6 >= 0 )
    {
      v16 = v47;
      v17 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v47 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      v6 = v17(v16, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v45);
      if ( v6 >= 0 )
      {
        v21 = *((_QWORD *)this + 17);
        v22 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v21 + 320LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        v6 = v22(v21, 0, &v50);
        if ( v6 >= 0 )
        {
          v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
          v27 = **v50;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
          v6 = v27(v26, &GUID_e7174cfa_1c9e_48b1_8866_626226bfc258, &v48);
          if ( v6 >= 0 )
          {
            v31 = v48;
            v32 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v48 + 24LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
            v6 = v32(v31, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v46);
            if ( v6 >= 0 )
            {
              (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v45 + 80LL))(v45, v55);
              v36 = *((_QWORD *)this + 7);
              v51 = v55[1];
              v54 = 0;
              v52 = 4;
              v53 = 1;
              v6 = (*(__int64 (__fastcall **)(__int64, __int64, int *, struct ID3D11ShaderResourceView **))(*(_QWORD *)v36 + 56LL))(
                     v36,
                     v45,
                     &v51,
                     a2);
              if ( v6 >= 0 )
              {
                v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, struct ID3D11ShaderResourceView **))(**((_QWORD **)this + 7) + 56LL))(
                       *((_QWORD *)this + 7),
                       v46,
                       &v51,
                       a2 + 1);
                if ( v6 < 0 )
                {
                  v40 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                    CallStackTracing::s_wpInstance = v41;
                    if ( v41
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
                    {
                      v40 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v40 = &qword_180153440;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                    }
                  }
                  if ( *((_BYTE *)v40 + 8) )
                  {
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
                      CallStackContext::TraceFailure(
                        ThreadRelativeContext,
                        "CRolling420FrameStitcherMFTDataHandler::CreateShaderInputView",
                        455,
                        v6);
                  }
                  if ( g_wppLevels )
                  {
                    v10 = 71;
                    goto LABEL_89;
                  }
                }
              }
              else
              {
                v37 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v38;
                  if ( v38
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
                  {
                    v37 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v37 = &qword_180153440;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                  }
                }
                if ( *((_BYTE *)v37 + 8) )
                {
                  v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                  if ( *((_DWORD *)v39 + 499) != v6 )
                    CallStackContext::TraceFailure(
                      v39,
                      "CRolling420FrameStitcherMFTDataHandler::CreateShaderInputView",
                      454,
                      v6);
                }
                if ( g_wppLevels )
                {
                  v10 = 70;
                  goto LABEL_89;
                }
              }
            }
            else
            {
              v33 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v34;
                if ( v34
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
                {
                  v33 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v33 = &qword_180153440;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                }
              }
              if ( *((_BYTE *)v33 + 8) )
              {
                v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                if ( *((_DWORD *)v35 + 499) != v6 )
                  CallStackContext::TraceFailure(
                    v35,
                    "CRolling420FrameStitcherMFTDataHandler::CreateShaderInputView",
                    444,
                    v6);
              }
              if ( g_wppLevels )
              {
                v10 = 69;
                goto LABEL_89;
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
              if ( *((_DWORD *)v30 + 499) != v6 )
                CallStackContext::TraceFailure(
                  v30,
                  "CRolling420FrameStitcherMFTDataHandler::CreateShaderInputView",
                  443,
                  v6);
            }
            if ( g_wppLevels )
            {
              v10 = 68;
              goto LABEL_89;
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
            v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v25 + 499) != v6 )
              CallStackContext::TraceFailure(
                v25,
                "CRolling420FrameStitcherMFTDataHandler::CreateShaderInputView",
                442,
                v6);
          }
          if ( g_wppLevels )
          {
            v10 = 67;
            goto LABEL_89;
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
          if ( *((_DWORD *)v20 + 499) != v6 )
            CallStackContext::TraceFailure(
              v20,
              "CRolling420FrameStitcherMFTDataHandler::CreateShaderInputView",
              440,
              v6);
        }
        if ( g_wppLevels )
        {
          v10 = 66;
          goto LABEL_89;
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
        if ( *((_DWORD *)v15 + 499) != v6 )
          CallStackContext::TraceFailure(v15, "CRolling420FrameStitcherMFTDataHandler::CreateShaderInputView", 439, v6);
      }
      if ( g_wppLevels )
      {
        v10 = 65;
        goto LABEL_89;
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
      if ( *((_DWORD *)v9 + 499) != v6 )
        CallStackContext::TraceFailure(v9, "CRolling420FrameStitcherMFTDataHandler::CreateShaderInputView", 438, v6);
    }
    if ( g_wppLevels )
    {
      v10 = 64;
LABEL_89:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids, this, v6);
    }
  }
  `vector destructor iterator'(&v45, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::~ComPtr<ID3D11ComputeShader>);
  `vector destructor iterator'(&v47, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::~ComPtr<ID3D11ComputeShader>);
  `vector destructor iterator'(&v49, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::~ComPtr<ID3D11ComputeShader>);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b6798  mov     [rsp-8+arg_10], rbx
0x1800b679d  mov     [rsp-8+arg_18], rsi
0x1800b67a2  push    rbp
0x1800b67a3  push    rdi
0x1800b67a4  push    r12
0x1800b67a6  push    r13
0x1800b67a8  push    r14
0x1800b67aa  lea     rbp, [rsp-37h]
0x1800b67af  sub     rsp, 0C0h
0x1800b67b6  mov     rax, cs:__security_cookie
0x1800b67bd  xor     rax, rsp
0x1800b67c0  mov     [rbp+57h+var_30], rax
0x1800b67c4  mov     r14, rdx
0x1800b67c7  lea     r12, aCrolling420fra_8; "CRolling420FrameStitcherMFTDataHandler:"...
0x1800b67ce  mov     rsi, rcx
0x1800b67d1  mov     rdx, r12; char *
0x1800b67d4  mov     r8d, 1A9h; int
0x1800b67da  lea     rcx, [rbp+57h+var_B0]; this
0x1800b67de  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b67e3  mov     r13d, 2
0x1800b67e9  lea     r9, ??0?$ComPtr@UID3D11ComputeShader@@@WRL@Microsoft@@QEAA@XZ; void *(*)(void *)
0x1800b67f0  mov     r8d, r13d; unsigned __int64
0x1800b67f3  lea     rcx, [rbp+57h+var_88]; void *
0x1800b67f7  lea     ebx, [r13+6]
0x1800b67fb  mov     edx, ebx; unsigned __int64
0x1800b67fd  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800b6802  lea     r9, ??0?$ComPtr@UID3D11ComputeShader@@@WRL@Microsoft@@QEAA@XZ; void *(*)(void *)
0x1800b6809  mov     r8d, r13d; unsigned __int64
0x1800b680c  mov     edx, ebx; unsigned __int64
0x1800b680e  lea     rcx, [rbp+57h+var_98]; void *
0x1800b6812  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800b6817  lea     r9, ??0?$ComPtr@UID3D11ComputeShader@@@WRL@Microsoft@@QEAA@XZ; void *(*)(void *)
0x1800b681e  mov     r8d, r13d; unsigned __int64
0x1800b6821  mov     edx, ebx; unsigned __int64
0x1800b6823  lea     rcx, [rbp+57h+var_A8]; void *
0x1800b6827  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800b682c  mov     rdi, [rsi+10h]
0x1800b6830  lea     rcx, [rbp+57h+var_88]
0x1800b6834  xorps   xmm0, xmm0
0x1800b6837  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1800b683b  movups  xmmword ptr [rbp+57h+var_50+0Ch], xmm0
0x1800b683f  movups  [rbp+57h+var_60], xmm0
0x1800b6843  mov     rax, [rdi]
0x1800b6846  mov     rbx, [rax+140h]
0x1800b684d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b6852  lea     r8, [rbp+57h+var_88]
0x1800b6856  xor     edx, edx
0x1800b6858  mov     rcx, rdi
0x1800b685b  mov     rax, rbx
0x1800b685e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6863  mov     ebx, eax
0x1800b6865  test    eax, eax
0x1800b6867  jns     loc_1800B68F8
0x1800b686d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6874  test    rcx, rcx
0x1800b6877  jnz     short loc_1800B68BA
0x1800b6879  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b687f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6886  mov     rcx, rax
0x1800b6889  test    rax, rax
0x1800b688c  jz      short loc_1800B68AC
0x1800b688e  mov     rax, [rax]
0x1800b6891  mov     edx, 7F0h
0x1800b6896  mov     rax, [rax+8]
0x1800b689a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b689f  test    eax, eax
0x1800b68a1  jz      short loc_1800B68AC
0x1800b68a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b68aa  jmp     short loc_1800B68BA
0x1800b68ac  lea     rcx, qword_180153440; this
0x1800b68b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b68ba  cmp     byte ptr [rcx+8], 0
0x1800b68be  jz      short loc_1800B68E1
0x1800b68c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b68c5  cmp     [rax+7CCh], ebx
0x1800b68cb  jz      short loc_1800B68E1
0x1800b68cd  mov     r9d, ebx; int
0x1800b68d0  mov     r8d, 1B6h; int
0x1800b68d6  mov     rdx, r12; char *
0x1800b68d9  mov     rcx, rax; this
0x1800b68dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b68e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b68e8  jb      loc_1800B6E59
0x1800b68ee  mov     edx, 40h ; '@'
0x1800b68f3  jmp     loc_1800B6E3B
0x1800b68f8  mov     rdi, [rbp+57h+var_88]
0x1800b68fc  lea     rcx, [rbp+57h+var_98]
0x1800b6900  mov     rax, [rdi]
0x1800b6903  mov     rbx, [rax]
0x1800b6906  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b690b  lea     r8, [rbp+57h+var_98]
0x1800b690f  mov     rcx, rdi
0x1800b6912  lea     rdx, _GUID_e7174cfa_1c9e_48b1_8866_626226bfc258
0x1800b6919  mov     rax, rbx
0x1800b691c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6921  mov     ebx, eax
0x1800b6923  test    eax, eax
0x1800b6925  jns     loc_1800B69B6
0x1800b692b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6932  test    rcx, rcx
0x1800b6935  jnz     short loc_1800B6978
0x1800b6937  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b693d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6944  mov     rcx, rax
0x1800b6947  test    rax, rax
0x1800b694a  jz      short loc_1800B696A
0x1800b694c  mov     rax, [rax]
0x1800b694f  mov     edx, 7F0h
0x1800b6954  mov     rax, [rax+8]
0x1800b6958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b695d  test    eax, eax
0x1800b695f  jz      short loc_1800B696A
0x1800b6961  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6968  jmp     short loc_1800B6978
0x1800b696a  lea     rcx, qword_180153440; this
0x1800b6971  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6978  cmp     byte ptr [rcx+8], 0
0x1800b697c  jz      short loc_1800B699F
0x1800b697e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b6983  cmp     [rax+7CCh], ebx
0x1800b6989  jz      short loc_1800B699F
0x1800b698b  mov     r9d, ebx; int
0x1800b698e  mov     r8d, 1B7h; int
0x1800b6994  mov     rdx, r12; char *
0x1800b6997  mov     rcx, rax; this
0x1800b699a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b699f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b69a6  jb      loc_1800B6E59
0x1800b69ac  mov     edx, 41h ; 'A'
0x1800b69b1  jmp     loc_1800B6E3B
0x1800b69b6  mov     rdi, [rbp+57h+var_98]
0x1800b69ba  lea     rcx, [rbp+57h+var_A8]
0x1800b69be  mov     rax, [rdi]
0x1800b69c1  mov     rbx, [rax+18h]
0x1800b69c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b69ca  lea     r8, [rbp+57h+var_A8]
0x1800b69ce  mov     rcx, rdi
0x1800b69d1  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x1800b69d8  mov     rax, rbx
0x1800b69db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b69e0  mov     ebx, eax
0x1800b69e2  test    eax, eax
0x1800b69e4  jns     loc_1800B6A75
0x1800b69ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b69f1  test    rcx, rcx
0x1800b69f4  jnz     short loc_1800B6A37
0x1800b69f6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b69fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6a03  mov     rcx, rax
0x1800b6a06  test    rax, rax
0x1800b6a09  jz      short loc_1800B6A29
0x1800b6a0b  mov     rax, [rax]
0x1800b6a0e  mov     edx, 7F0h
0x1800b6a13  mov     rax, [rax+8]
0x1800b6a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6a1c  test    eax, eax
0x1800b6a1e  jz      short loc_1800B6A29
0x1800b6a20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6a27  jmp     short loc_1800B6A37
0x1800b6a29  lea     rcx, qword_180153440; this
0x1800b6a30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6a37  cmp     byte ptr [rcx+8], 0
0x1800b6a3b  jz      short loc_1800B6A5E
0x1800b6a3d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b6a42  cmp     [rax+7CCh], ebx
0x1800b6a48  jz      short loc_1800B6A5E
0x1800b6a4a  mov     r9d, ebx; int
0x1800b6a4d  mov     r8d, 1B8h; int
0x1800b6a53  mov     rdx, r12; char *
0x1800b6a56  mov     rcx, rax; this
0x1800b6a59  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b6a5e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6a65  jb      loc_1800B6E59
0x1800b6a6b  mov     edx, 42h ; 'B'
0x1800b6a70  jmp     loc_1800B6E3B
0x1800b6a75  mov     rdi, [rsi+88h]
0x1800b6a7c  lea     rcx, [rbp+57h+var_80]
0x1800b6a80  mov     rax, [rdi]
0x1800b6a83  mov     rbx, [rax+140h]
0x1800b6a8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b6a8f  lea     r8, [rbp+57h+var_80]
0x1800b6a93  xor     edx, edx
0x1800b6a95  mov     rcx, rdi
0x1800b6a98  mov     rax, rbx
0x1800b6a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6aa0  mov     ebx, eax
0x1800b6aa2  test    eax, eax
0x1800b6aa4  jns     loc_1800B6B35
0x1800b6aaa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6ab1  test    rcx, rcx
0x1800b6ab4  jnz     short loc_1800B6AF7
0x1800b6ab6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b6abc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6ac3  mov     rcx, rax
0x1800b6ac6  test    rax, rax
0x1800b6ac9  jz      short loc_1800B6AE9
0x1800b6acb  mov     rax, [rax]
0x1800b6ace  mov     edx, 7F0h
0x1800b6ad3  mov     rax, [rax+8]
0x1800b6ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6adc  test    eax, eax
0x1800b6ade  jz      short loc_1800B6AE9
0x1800b6ae0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6ae7  jmp     short loc_1800B6AF7
0x1800b6ae9  lea     rcx, qword_180153440; this
0x1800b6af0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6af7  cmp     byte ptr [rcx+8], 0
0x1800b6afb  jz      short loc_1800B6B1E
0x1800b6afd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b6b02  cmp     [rax+7CCh], ebx
0x1800b6b08  jz      short loc_1800B6B1E
0x1800b6b0a  mov     r9d, ebx; int
0x1800b6b0d  mov     r8d, 1BAh; int
0x1800b6b13  mov     rdx, r12; char *
0x1800b6b16  mov     rcx, rax; this
0x1800b6b19  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b6b1e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6b25  jb      loc_1800B6E59
0x1800b6b2b  mov     edx, 43h ; 'C'
0x1800b6b30  jmp     loc_1800B6E3B
0x1800b6b35  mov     rdi, [rbp+57h+var_80]
0x1800b6b39  lea     rcx, [rbp+57h+var_90]
0x1800b6b3d  mov     rax, [rdi]
0x1800b6b40  mov     rbx, [rax]
0x1800b6b43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b6b48  lea     r8, [rbp+57h+var_90]
0x1800b6b4c  mov     rcx, rdi
0x1800b6b4f  lea     rdx, _GUID_e7174cfa_1c9e_48b1_8866_626226bfc258
0x1800b6b56  mov     rax, rbx
0x1800b6b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6b5e  mov     ebx, eax
0x1800b6b60  test    eax, eax
0x1800b6b62  jns     loc_1800B6BF3
0x1800b6b68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6b6f  test    rcx, rcx
0x1800b6b72  jnz     short loc_1800B6BB5
0x1800b6b74  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b6b7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6b81  mov     rcx, rax
0x1800b6b84  test    rax, rax
0x1800b6b87  jz      short loc_1800B6BA7
0x1800b6b89  mov     rax, [rax]
0x1800b6b8c  mov     edx, 7F0h
0x1800b6b91  mov     rax, [rax+8]
0x1800b6b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6b9a  test    eax, eax
0x1800b6b9c  jz      short loc_1800B6BA7
0x1800b6b9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6ba5  jmp     short loc_1800B6BB5
0x1800b6ba7  lea     rcx, qword_180153440; this
0x1800b6bae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6bb5  cmp     byte ptr [rcx+8], 0
0x1800b6bb9  jz      short loc_1800B6BDC
0x1800b6bbb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b6bc0  cmp     [rax+7CCh], ebx
0x1800b6bc6  jz      short loc_1800B6BDC
0x1800b6bc8  mov     r9d, ebx; int
0x1800b6bcb  mov     r8d, 1BBh; int
0x1800b6bd1  mov     rdx, r12; char *
0x1800b6bd4  mov     rcx, rax; this
0x1800b6bd7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b6bdc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6be3  jb      loc_1800B6E59
0x1800b6be9  mov     edx, 44h ; 'D'
0x1800b6bee  jmp     loc_1800B6E3B
0x1800b6bf3  mov     rdi, [rbp+57h+var_90]
0x1800b6bf7  lea     rcx, [rbp+57h+var_A0]
0x1800b6bfb  mov     rax, [rdi]
0x1800b6bfe  mov     rbx, [rax+18h]
0x1800b6c02  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b6c07  lea     r8, [rbp+57h+var_A0]
0x1800b6c0b  mov     rcx, rdi
0x1800b6c0e  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x1800b6c15  mov     rax, rbx
0x1800b6c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6c1d  mov     ebx, eax
0x1800b6c1f  test    eax, eax
0x1800b6c21  jns     loc_1800B6CB2
0x1800b6c27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6c2e  test    rcx, rcx
0x1800b6c31  jnz     short loc_1800B6C74
0x1800b6c33  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b6c39  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6c40  mov     rcx, rax
0x1800b6c43  test    rax, rax
0x1800b6c46  jz      short loc_1800B6C66
0x1800b6c48  mov     rax, [rax]
0x1800b6c4b  mov     edx, 7F0h
0x1800b6c50  mov     rax, [rax+8]
0x1800b6c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6c59  test    eax, eax
0x1800b6c5b  jz      short loc_1800B6C66
0x1800b6c5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6c64  jmp     short loc_1800B6C74
0x1800b6c66  lea     rcx, qword_180153440; this
0x1800b6c6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6c74  cmp     byte ptr [rcx+8], 0
0x1800b6c78  jz      short loc_1800B6C9B
0x1800b6c7a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b6c7f  cmp     [rax+7CCh], ebx
  ... truncated ...
```
