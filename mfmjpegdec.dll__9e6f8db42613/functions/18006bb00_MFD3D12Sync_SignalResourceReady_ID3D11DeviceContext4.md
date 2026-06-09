# MFD3D12Sync::SignalResourceReady(ID3D11DeviceContext4 *)

- ea: `0x18006bb00`
- end: `0x18006bed2`
- name: `?SignalResourceReady@MFD3D12Sync@@UEAAJPEAUID3D11DeviceContext4@@@Z`
- size: `978`
- prototype: `int(MFD3D12Sync *__hidden this, struct ID3D11DeviceContext4 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18002312c`
- `0x180045060`
- `0x180056638`
- `0x180066c80`
- `0x180067564`
- `0x18006bb00`
- `0x18006dc78`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006bbca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006bca4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006bdf0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006be61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006bbca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006bca4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006bdf0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006be61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bb75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bb91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bc51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bc6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bd32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bd9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bdb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bb75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bb91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bc51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bc6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bd32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bd9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bdb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be29`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006bb81`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006bc5c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006bd3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006bda7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006bb81`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006bc5c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006bd3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006bda7`

## string_xrefs

- `0x18006bb1e`: `MFD3D12Sync::SignalResourceReady`

## pseudocode

```c
__int64 __fastcall MFD3D12Sync::SignalResourceReady(MFD3D12Sync *this, struct ID3D11DeviceContext4 *a2)
{
  char *v4; // r14
  CallStackTracing *v5; // rsi
  int ReadyFence11; // ebx
  CallStackContext *v7; // rbp
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  CallStackTracing *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  CallStackTracing *v13; // rdi
  CallStackContext *v14; // rsi
  DWORD v15; // ebp
  CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  _QWORD *v20; // rbx
  CallStackTracing *v21; // rdi
  CallStackContext *v22; // rsi
  DWORD v23; // ebp
  CallStackContext *v24; // rax
  CallStackTracing *v25; // rsi
  CallStackContext *v26; // rbp
  DWORD v27; // r15d
  CallStackContext *v28; // rax
  CallStackTracing *v29; // rcx
  __int64 v30; // rax
  CallStackTracing *v31; // rcx
  __int64 v32; // rax
  struct ID3D11DeviceContext4 *v34; // [rsp+68h] [rbp+10h] BYREF
  char v35; // [rsp+70h] [rbp+18h] BYREF

  v34 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v35, "MFD3D12Sync::SignalResourceReady", 476);
  v4 = (char *)this - 24;
  if ( !a2 )
  {
    v5 = CallStackTracing::s_wpInstance;
    ReadyFence11 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)&qword_18009CF60;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = (CallStackTracing *)((char *)v5 + 208);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v5 + 3));
      if ( Value )
      {
        v7 = Value;
      }
      else if ( !GetLastError() )
      {
        v10 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v10 = (CallStackTracing *)&qword_18009CF60;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
        }
        v11 = (**(__int64 (__fastcall ***)(CallStackTracing *))v10)(v10);
        if ( v11 )
          v7 = (CallStackContext *)v11;
      }
      SetLastError(LastError);
      if ( *((_DWORD *)v7 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v7, "MFD3D12Sync::SignalResourceReady", 476, -2147024809);
    }
    if ( g_wppLevels )
    {
      v12 = 87;
LABEL_16:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids,
        v4,
        -2147024809);
      goto LABEL_65;
    }
    goto LABEL_65;
  }
  if ( !*((_QWORD *)v4 + 17) )
  {
    ReadyFence11 = MFD3D12Sync::CreateReadyFence11((struct _RTL_CRITICAL_SECTION *)((char *)this - 24), a2);
    if ( ReadyFence11 < 0 )
    {
      v13 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v14 = (CallStackTracing *)((char *)v13 + 208);
        v15 = GetLastError();
        v16 = (CallStackContext *)TlsGetValue(*((_DWORD *)v13 + 3));
        if ( v16 )
        {
          v14 = v16;
        }
        else if ( !GetLastError() )
        {
          v17 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v17 = (CallStackTracing *)&qword_18009CF60;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
          }
          v18 = (**(__int64 (__fastcall ***)(CallStackTracing *))v17)(v17);
          if ( v18 )
            v14 = (CallStackContext *)v18;
        }
        SetLastError(v15);
        if ( *((_DWORD *)v14 + 499) != ReadyFence11 )
          CallStackContext::TraceFailure(v14, "MFD3D12Sync::SignalResourceReady", 480, ReadyFence11);
      }
      if ( !g_wppLevels )
        goto LABEL_65;
      v19 = 88;
      goto LABEL_64;
    }
    v20 = (_QWORD *)((char *)this + 112);
LABEL_34:
    ReadyFence11 = ((__int64 (__fastcall *)(struct ID3D11DeviceContext4 *, _QWORD, _QWORD))a2->lpVtbl->Signal)(
                     a2,
                     *v20,
                     *((_QWORD *)this + 17));
    if ( ReadyFence11 >= 0 )
      goto LABEL_65;
    v21 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)&qword_18009CF60;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v22 = (CallStackTracing *)((char *)v21 + 208);
      v23 = GetLastError();
      v24 = (CallStackContext *)TlsGetValue(*((_DWORD *)v21 + 3));
      if ( v24 )
      {
        v22 = v24;
      }
      else if ( !GetLastError() )
      {
        v31 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)&qword_18009CF60;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
        }
        v32 = (**(__int64 (__fastcall ***)(CallStackTracing *))v31)(v31);
        if ( v32 )
          v22 = (CallStackContext *)v32;
      }
      SetLastError(v23);
      if ( *((_DWORD *)v22 + 499) != ReadyFence11 )
        CallStackContext::TraceFailure(v22, "MFD3D12Sync::SignalResourceReady", 487, ReadyFence11);
    }
    if ( !g_wppLevels )
      goto LABEL_65;
    v19 = 90;
LABEL_64:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      &WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids,
      v4,
      ReadyFence11);
    goto LABEL_65;
  }
  v20 = (_QWORD *)((char *)this + 112);
  if ( (unsigned __int8)CheckD3D11DeviceMatch<ID3D11DeviceContext4 *,Microsoft::WRL::ComPtr<ID3D11Fence>>(
                          &v34,
                          (char *)this + 112) )
    goto LABEL_34;
  v25 = CallStackTracing::s_wpInstance;
  ReadyFence11 = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    v25 = (CallStackTracing *)&qword_18009CF60;
    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
  }
  if ( *((_BYTE *)v25 + 8) )
  {
    v26 = (CallStackTracing *)((char *)v25 + 208);
    v27 = GetLastError();
    v28 = (CallStackContext *)TlsGetValue(*((_DWORD *)v25 + 3));
    if ( v28 )
    {
      v26 = v28;
    }
    else if ( !GetLastError() )
    {
      v29 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      v30 = (**(__int64 (__fastcall ***)(CallStackTracing *))v29)(v29);
      if ( v30 )
        v26 = (CallStackContext *)v30;
    }
    SetLastError(v27);
    if ( *((_DWORD *)v26 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v26, "MFD3D12Sync::SignalResourceReady", 484, -2147024809);
  }
  if ( g_wppLevels )
  {
    v12 = 89;
    goto LABEL_16;
  }
LABEL_65:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v35);
  return (unsigned int)ReadyFence11;
}

```

## disassembly

```asm
0x18006bb00  mov     rax, rsp
0x18006bb03  mov     [rax+8], rbx
0x18006bb07  mov     [rax+20h], rbp
0x18006bb0b  mov     [rax+10h], rdx
0x18006bb0f  push    rsi
0x18006bb10  push    rdi
0x18006bb11  push    r13
0x18006bb13  push    r14
0x18006bb15  push    r15
0x18006bb17  sub     rsp, 30h
0x18006bb1b  mov     rdi, rdx
0x18006bb1e  lea     r13, aMfd3d12syncSig_2; "MFD3D12Sync::SignalResourceReady"
0x18006bb25  mov     rsi, rcx
0x18006bb28  mov     rdx, r13; char *
0x18006bb2b  mov     r8d, 1DCh; int
0x18006bb31  lea     rcx, [rax+18h]; this
0x18006bb35  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006bb3a  lea     r14, [rsi-18h]
0x18006bb3e  test    rdi, rdi
0x18006bb41  jnz     loc_18006BC07
0x18006bb47  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bb4e  mov     edi, 80070057h
0x18006bb53  mov     ebx, edi
0x18006bb55  test    rsi, rsi
0x18006bb58  jnz     short loc_18006BB68
0x18006bb5a  lea     rsi, qword_18009CF60
0x18006bb61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bb68  cmp     byte ptr [rsi+8], 0
0x18006bb6c  jz      short loc_18006BBEC
0x18006bb6e  lea     rbp, [rsi+0D0h]
0x18006bb75  call    cs:__imp_GetLastError
0x18006bb7b  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18006bb7e  mov     r15d, eax
0x18006bb81  call    cs:__imp_TlsGetValue
0x18006bb87  test    rax, rax
0x18006bb8a  jz      short loc_18006BB91
0x18006bb8c  mov     rbp, rax
0x18006bb8f  jmp     short loc_18006BBC7
0x18006bb91  call    cs:__imp_GetLastError
0x18006bb97  test    eax, eax
0x18006bb99  jnz     short loc_18006BBC7
0x18006bb9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bba2  test    rcx, rcx
0x18006bba5  jnz     short loc_18006BBB5
0x18006bba7  lea     rcx, qword_18009CF60
0x18006bbae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bbb5  mov     rax, [rcx]
0x18006bbb8  mov     rax, [rax]
0x18006bbbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bbc0  test    rax, rax
0x18006bbc3  cmovnz  rbp, rax
0x18006bbc7  mov     ecx, r15d; dwErrCode
0x18006bbca  call    cs:__imp_SetLastError
0x18006bbd0  cmp     [rbp+7CCh], edi
0x18006bbd6  jz      short loc_18006BBEC
0x18006bbd8  mov     r9d, edi; int
0x18006bbdb  mov     r8d, 1DCh; int
0x18006bbe1  mov     rdx, r13; char *
0x18006bbe4  mov     rcx, rbp; this
0x18006bbe7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006bbec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006bbf3  jb      loc_18006BEAF
0x18006bbf9  mov     edx, 57h ; 'W'
0x18006bbfe  mov     [rsp+58h+var_38], edi
0x18006bc02  jmp     loc_18006BE95
0x18006bc07  cmp     qword ptr [r14+88h], 0
0x18006bc0f  jnz     loc_18006BD54
0x18006bc15  mov     rdx, rdi; struct ID3D11DeviceContext4 *
0x18006bc18  mov     rcx, r14; this
0x18006bc1b  call    ?CreateReadyFence11@MFD3D12Sync@@IEAAJPEAUID3D11DeviceContext4@@@Z; MFD3D12Sync::CreateReadyFence11(ID3D11DeviceContext4 *)
0x18006bc20  mov     ebx, eax
0x18006bc22  test    eax, eax
0x18006bc24  jns     loc_18006BCDD
0x18006bc2a  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bc31  test    rdi, rdi
0x18006bc34  jnz     short loc_18006BC44
0x18006bc36  lea     rdi, qword_18009CF60
0x18006bc3d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bc44  cmp     byte ptr [rdi+8], 0
0x18006bc48  jz      short loc_18006BCC6
0x18006bc4a  lea     rsi, [rdi+0D0h]
0x18006bc51  call    cs:__imp_GetLastError
0x18006bc57  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18006bc5a  mov     ebp, eax
0x18006bc5c  call    cs:__imp_TlsGetValue
0x18006bc62  test    rax, rax
0x18006bc65  jz      short loc_18006BC6C
0x18006bc67  mov     rsi, rax
0x18006bc6a  jmp     short loc_18006BCA2
0x18006bc6c  call    cs:__imp_GetLastError
0x18006bc72  test    eax, eax
0x18006bc74  jnz     short loc_18006BCA2
0x18006bc76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bc7d  test    rcx, rcx
0x18006bc80  jnz     short loc_18006BC90
0x18006bc82  lea     rcx, qword_18009CF60
0x18006bc89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bc90  mov     rax, [rcx]
0x18006bc93  mov     rax, [rax]
0x18006bc96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bc9b  test    rax, rax
0x18006bc9e  cmovnz  rsi, rax
0x18006bca2  mov     ecx, ebp; dwErrCode
0x18006bca4  call    cs:__imp_SetLastError
0x18006bcaa  cmp     [rsi+7CCh], ebx
0x18006bcb0  jz      short loc_18006BCC6
0x18006bcb2  mov     r9d, ebx; int
0x18006bcb5  mov     r8d, 1E0h; int
0x18006bcbb  mov     rdx, r13; char *
0x18006bcbe  mov     rcx, rsi; this
0x18006bcc1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006bcc6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006bccd  jb      loc_18006BEAF
0x18006bcd3  mov     edx, 58h ; 'X'
0x18006bcd8  jmp     loc_18006BE91
0x18006bcdd  lea     rbx, [rsi+70h]
0x18006bce1  mov     rax, [rdi]
0x18006bce4  mov     rcx, rdi
0x18006bce7  mov     r8, [rsi+88h]
0x18006bcee  mov     rdx, [rbx]
0x18006bcf1  mov     rax, [rax+498h]
0x18006bcf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bcfd  mov     ebx, eax
0x18006bcff  test    eax, eax
0x18006bd01  jns     loc_18006BEAF
0x18006bd07  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bd0e  test    rdi, rdi
0x18006bd11  jnz     short loc_18006BD21
0x18006bd13  lea     rdi, qword_18009CF60
0x18006bd1a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bd21  cmp     byte ptr [rdi+8], 0
0x18006bd25  jz      loc_18006BE83
0x18006bd2b  lea     rsi, [rdi+0D0h]
0x18006bd32  call    cs:__imp_GetLastError
0x18006bd38  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18006bd3b  mov     ebp, eax
0x18006bd3d  call    cs:__imp_TlsGetValue
0x18006bd43  test    rax, rax
0x18006bd46  jz      loc_18006BE29
0x18006bd4c  mov     rsi, rax
0x18006bd4f  jmp     loc_18006BE5F
0x18006bd54  lea     rbx, [rsi+70h]
0x18006bd58  mov     rdx, rbx
0x18006bd5b  lea     rcx, [rsp+58h+arg_8]
0x18006bd60  call    ??$CheckD3D11DeviceMatch@PEAUID3D11DeviceContext4@@V?$ComPtr@UID3D11Fence@@@WRL@Microsoft@@@@YA_NAEAPEAUID3D11DeviceContext4@@AEAV?$ComPtr@UID3D11Fence@@@WRL@Microsoft@@@Z; CheckD3D11DeviceMatch<ID3D11DeviceContext4 *,Microsoft::WRL::ComPtr<ID3D11Fence>>(ID3D11DeviceContext4 * &,Microsoft::WRL::ComPtr<ID3D11Fence> &)
0x18006bd65  test    al, al
0x18006bd67  jnz     loc_18006BCE1
0x18006bd6d  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bd74  mov     edi, 80070057h
0x18006bd79  mov     ebx, edi
0x18006bd7b  test    rsi, rsi
0x18006bd7e  jnz     short loc_18006BD8E
0x18006bd80  lea     rsi, qword_18009CF60
0x18006bd87  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bd8e  cmp     byte ptr [rsi+8], 0
0x18006bd92  jz      short loc_18006BE12
0x18006bd94  lea     rbp, [rsi+0D0h]
0x18006bd9b  call    cs:__imp_GetLastError
0x18006bda1  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18006bda4  mov     r15d, eax
0x18006bda7  call    cs:__imp_TlsGetValue
0x18006bdad  test    rax, rax
0x18006bdb0  jz      short loc_18006BDB7
0x18006bdb2  mov     rbp, rax
0x18006bdb5  jmp     short loc_18006BDED
0x18006bdb7  call    cs:__imp_GetLastError
0x18006bdbd  test    eax, eax
0x18006bdbf  jnz     short loc_18006BDED
0x18006bdc1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bdc8  test    rcx, rcx
0x18006bdcb  jnz     short loc_18006BDDB
0x18006bdcd  lea     rcx, qword_18009CF60
0x18006bdd4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bddb  mov     rax, [rcx]
0x18006bdde  mov     rax, [rax]
0x18006bde1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bde6  test    rax, rax
0x18006bde9  cmovnz  rbp, rax
0x18006bded  mov     ecx, r15d; dwErrCode
0x18006bdf0  call    cs:__imp_SetLastError
0x18006bdf6  cmp     [rbp+7CCh], edi
0x18006bdfc  jz      short loc_18006BE12
0x18006bdfe  mov     r9d, edi; int
0x18006be01  mov     r8d, 1E4h; int
0x18006be07  mov     rdx, r13; char *
0x18006be0a  mov     rcx, rbp; this
0x18006be0d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006be12  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006be19  jb      loc_18006BEAF
0x18006be1f  mov     edx, 59h ; 'Y'
0x18006be24  jmp     loc_18006BBFE
0x18006be29  call    cs:__imp_GetLastError
0x18006be2f  test    eax, eax
0x18006be31  jnz     short loc_18006BE5F
0x18006be33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006be3a  test    rcx, rcx
0x18006be3d  jnz     short loc_18006BE4D
0x18006be3f  lea     rcx, qword_18009CF60
0x18006be46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006be4d  mov     rax, [rcx]
0x18006be50  mov     rax, [rax]
0x18006be53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be58  test    rax, rax
0x18006be5b  cmovnz  rsi, rax
0x18006be5f  mov     ecx, ebp; dwErrCode
0x18006be61  call    cs:__imp_SetLastError
0x18006be67  cmp     [rsi+7CCh], ebx
0x18006be6d  jz      short loc_18006BE83
0x18006be6f  mov     r9d, ebx; int
0x18006be72  mov     r8d, 1E7h; int
0x18006be78  mov     rdx, r13; char *
0x18006be7b  mov     rcx, rsi; this
0x18006be7e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006be83  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006be8a  jb      short loc_18006BEAF
0x18006be8c  mov     edx, 5Ah ; 'Z'
0x18006be91  mov     [rsp+58h+var_38], ebx
0x18006be95  mov     rcx, cs:WPP_GLOBAL_Control
0x18006be9c  lea     r8, WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids
0x18006bea3  mov     r9, r14
0x18006bea6  mov     rcx, [rcx+10h]
0x18006beaa  call    WPP_SF_qd
0x18006beaf  lea     rcx, [rsp+58h+arg_10]; this
0x18006beb4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006beb9  mov     rbp, [rsp+58h+arg_18]
0x18006bebe  mov     eax, ebx
0x18006bec0  mov     rbx, [rsp+58h+arg_0]
0x18006bec5  add     rsp, 30h
0x18006bec9  pop     r15
0x18006becb  pop     r14
0x18006becd  pop     r13
0x18006becf  pop     rdi
0x18006bed0  pop     rsi
0x18006bed1  retn
```
