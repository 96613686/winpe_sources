# MFD3D12Sync::WaitForResourceReady(ID3D11DeviceContext4 *)

- ea: `0x18006c880`
- end: `0x18006cc52`
- name: `?WaitForResourceReady@MFD3D12Sync@@UEAAJPEAUID3D11DeviceContext4@@@Z`
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
- `0x18006c880`
- `0x18006dc78`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c94a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ca24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cb70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cbe1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c94a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ca24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cb70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cbe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c8f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c9d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c9ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cb1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cb37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c8f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c9d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c9ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cb1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cb37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cba9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006c901`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006c9dc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006cabd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006cb27`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006c901`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006c9dc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006cabd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006cb27`

## string_xrefs

- `0x18006c89e`: `MFD3D12Sync::WaitForResourceReady`

## pseudocode

```c
__int64 __fastcall MFD3D12Sync::WaitForResourceReady(MFD3D12Sync *this, struct ID3D11DeviceContext4 *a2)
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
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v35, "MFD3D12Sync::WaitForResourceReady", 496);
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
        CallStackContext::TraceFailure(v7, "MFD3D12Sync::WaitForResourceReady", 496, -2147024809);
    }
    if ( g_wppLevels )
    {
      v12 = 91;
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
          CallStackContext::TraceFailure(v14, "MFD3D12Sync::WaitForResourceReady", 500, ReadyFence11);
      }
      if ( !g_wppLevels )
        goto LABEL_65;
      v19 = 92;
      goto LABEL_64;
    }
    v20 = (_QWORD *)((char *)this + 112);
LABEL_34:
    ReadyFence11 = ((__int64 (__fastcall *)(struct ID3D11DeviceContext4 *, _QWORD, _QWORD))a2->lpVtbl->Wait)(
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
        CallStackContext::TraceFailure(v22, "MFD3D12Sync::WaitForResourceReady", 507, ReadyFence11);
    }
    if ( !g_wppLevels )
      goto LABEL_65;
    v19 = 94;
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
      CallStackContext::TraceFailure(v26, "MFD3D12Sync::WaitForResourceReady", 504, -2147024809);
  }
  if ( g_wppLevels )
  {
    v12 = 93;
    goto LABEL_16;
  }
LABEL_65:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v35);
  return (unsigned int)ReadyFence11;
}

```

## disassembly

```asm
0x18006c880  mov     rax, rsp
0x18006c883  mov     [rax+8], rbx
0x18006c887  mov     [rax+20h], rbp
0x18006c88b  mov     [rax+10h], rdx
0x18006c88f  push    rsi
0x18006c890  push    rdi
0x18006c891  push    r13
0x18006c893  push    r14
0x18006c895  push    r15
0x18006c897  sub     rsp, 30h
0x18006c89b  mov     rdi, rdx
0x18006c89e  lea     r13, aMfd3d12syncWai; "MFD3D12Sync::WaitForResourceReady"
0x18006c8a5  mov     rsi, rcx
0x18006c8a8  mov     rdx, r13; char *
0x18006c8ab  mov     r8d, 1F0h; int
0x18006c8b1  lea     rcx, [rax+18h]; this
0x18006c8b5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006c8ba  lea     r14, [rsi-18h]
0x18006c8be  test    rdi, rdi
0x18006c8c1  jnz     loc_18006C987
0x18006c8c7  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c8ce  mov     edi, 80070057h
0x18006c8d3  mov     ebx, edi
0x18006c8d5  test    rsi, rsi
0x18006c8d8  jnz     short loc_18006C8E8
0x18006c8da  lea     rsi, qword_18009CF60
0x18006c8e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c8e8  cmp     byte ptr [rsi+8], 0
0x18006c8ec  jz      short loc_18006C96C
0x18006c8ee  lea     rbp, [rsi+0D0h]
0x18006c8f5  call    cs:__imp_GetLastError
0x18006c8fb  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18006c8fe  mov     r15d, eax
0x18006c901  call    cs:__imp_TlsGetValue
0x18006c907  test    rax, rax
0x18006c90a  jz      short loc_18006C911
0x18006c90c  mov     rbp, rax
0x18006c90f  jmp     short loc_18006C947
0x18006c911  call    cs:__imp_GetLastError
0x18006c917  test    eax, eax
0x18006c919  jnz     short loc_18006C947
0x18006c91b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c922  test    rcx, rcx
0x18006c925  jnz     short loc_18006C935
0x18006c927  lea     rcx, qword_18009CF60
0x18006c92e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c935  mov     rax, [rcx]
0x18006c938  mov     rax, [rax]
0x18006c93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c940  test    rax, rax
0x18006c943  cmovnz  rbp, rax
0x18006c947  mov     ecx, r15d; dwErrCode
0x18006c94a  call    cs:__imp_SetLastError
0x18006c950  cmp     [rbp+7CCh], edi
0x18006c956  jz      short loc_18006C96C
0x18006c958  mov     r9d, edi; int
0x18006c95b  mov     r8d, 1F0h; int
0x18006c961  mov     rdx, r13; char *
0x18006c964  mov     rcx, rbp; this
0x18006c967  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006c96c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c973  jb      loc_18006CC2F
0x18006c979  mov     edx, 5Bh ; '['
0x18006c97e  mov     [rsp+58h+var_38], edi
0x18006c982  jmp     loc_18006CC15
0x18006c987  cmp     qword ptr [r14+88h], 0
0x18006c98f  jnz     loc_18006CAD4
0x18006c995  mov     rdx, rdi; struct ID3D11DeviceContext4 *
0x18006c998  mov     rcx, r14; this
0x18006c99b  call    ?CreateReadyFence11@MFD3D12Sync@@IEAAJPEAUID3D11DeviceContext4@@@Z; MFD3D12Sync::CreateReadyFence11(ID3D11DeviceContext4 *)
0x18006c9a0  mov     ebx, eax
0x18006c9a2  test    eax, eax
0x18006c9a4  jns     loc_18006CA5D
0x18006c9aa  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c9b1  test    rdi, rdi
0x18006c9b4  jnz     short loc_18006C9C4
0x18006c9b6  lea     rdi, qword_18009CF60
0x18006c9bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c9c4  cmp     byte ptr [rdi+8], 0
0x18006c9c8  jz      short loc_18006CA46
0x18006c9ca  lea     rsi, [rdi+0D0h]
0x18006c9d1  call    cs:__imp_GetLastError
0x18006c9d7  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18006c9da  mov     ebp, eax
0x18006c9dc  call    cs:__imp_TlsGetValue
0x18006c9e2  test    rax, rax
0x18006c9e5  jz      short loc_18006C9EC
0x18006c9e7  mov     rsi, rax
0x18006c9ea  jmp     short loc_18006CA22
0x18006c9ec  call    cs:__imp_GetLastError
0x18006c9f2  test    eax, eax
0x18006c9f4  jnz     short loc_18006CA22
0x18006c9f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c9fd  test    rcx, rcx
0x18006ca00  jnz     short loc_18006CA10
0x18006ca02  lea     rcx, qword_18009CF60
0x18006ca09  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ca10  mov     rax, [rcx]
0x18006ca13  mov     rax, [rax]
0x18006ca16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca1b  test    rax, rax
0x18006ca1e  cmovnz  rsi, rax
0x18006ca22  mov     ecx, ebp; dwErrCode
0x18006ca24  call    cs:__imp_SetLastError
0x18006ca2a  cmp     [rsi+7CCh], ebx
0x18006ca30  jz      short loc_18006CA46
0x18006ca32  mov     r9d, ebx; int
0x18006ca35  mov     r8d, 1F4h; int
0x18006ca3b  mov     rdx, r13; char *
0x18006ca3e  mov     rcx, rsi; this
0x18006ca41  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006ca46  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ca4d  jb      loc_18006CC2F
0x18006ca53  mov     edx, 5Ch ; '\'
0x18006ca58  jmp     loc_18006CC11
0x18006ca5d  lea     rbx, [rsi+70h]
0x18006ca61  mov     rax, [rdi]
0x18006ca64  mov     rcx, rdi
0x18006ca67  mov     r8, [rsi+88h]
0x18006ca6e  mov     rdx, [rbx]
0x18006ca71  mov     rax, [rax+4A0h]
0x18006ca78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca7d  mov     ebx, eax
0x18006ca7f  test    eax, eax
0x18006ca81  jns     loc_18006CC2F
0x18006ca87  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ca8e  test    rdi, rdi
0x18006ca91  jnz     short loc_18006CAA1
0x18006ca93  lea     rdi, qword_18009CF60
0x18006ca9a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006caa1  cmp     byte ptr [rdi+8], 0
0x18006caa5  jz      loc_18006CC03
0x18006caab  lea     rsi, [rdi+0D0h]
0x18006cab2  call    cs:__imp_GetLastError
0x18006cab8  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18006cabb  mov     ebp, eax
0x18006cabd  call    cs:__imp_TlsGetValue
0x18006cac3  test    rax, rax
0x18006cac6  jz      loc_18006CBA9
0x18006cacc  mov     rsi, rax
0x18006cacf  jmp     loc_18006CBDF
0x18006cad4  lea     rbx, [rsi+70h]
0x18006cad8  mov     rdx, rbx
0x18006cadb  lea     rcx, [rsp+58h+arg_8]
0x18006cae0  call    ??$CheckD3D11DeviceMatch@PEAUID3D11DeviceContext4@@V?$ComPtr@UID3D11Fence@@@WRL@Microsoft@@@@YA_NAEAPEAUID3D11DeviceContext4@@AEAV?$ComPtr@UID3D11Fence@@@WRL@Microsoft@@@Z; CheckD3D11DeviceMatch<ID3D11DeviceContext4 *,Microsoft::WRL::ComPtr<ID3D11Fence>>(ID3D11DeviceContext4 * &,Microsoft::WRL::ComPtr<ID3D11Fence> &)
0x18006cae5  test    al, al
0x18006cae7  jnz     loc_18006CA61
0x18006caed  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006caf4  mov     edi, 80070057h
0x18006caf9  mov     ebx, edi
0x18006cafb  test    rsi, rsi
0x18006cafe  jnz     short loc_18006CB0E
0x18006cb00  lea     rsi, qword_18009CF60
0x18006cb07  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cb0e  cmp     byte ptr [rsi+8], 0
0x18006cb12  jz      short loc_18006CB92
0x18006cb14  lea     rbp, [rsi+0D0h]
0x18006cb1b  call    cs:__imp_GetLastError
0x18006cb21  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18006cb24  mov     r15d, eax
0x18006cb27  call    cs:__imp_TlsGetValue
0x18006cb2d  test    rax, rax
0x18006cb30  jz      short loc_18006CB37
0x18006cb32  mov     rbp, rax
0x18006cb35  jmp     short loc_18006CB6D
0x18006cb37  call    cs:__imp_GetLastError
0x18006cb3d  test    eax, eax
0x18006cb3f  jnz     short loc_18006CB6D
0x18006cb41  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cb48  test    rcx, rcx
0x18006cb4b  jnz     short loc_18006CB5B
0x18006cb4d  lea     rcx, qword_18009CF60
0x18006cb54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cb5b  mov     rax, [rcx]
0x18006cb5e  mov     rax, [rax]
0x18006cb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cb66  test    rax, rax
0x18006cb69  cmovnz  rbp, rax
0x18006cb6d  mov     ecx, r15d; dwErrCode
0x18006cb70  call    cs:__imp_SetLastError
0x18006cb76  cmp     [rbp+7CCh], edi
0x18006cb7c  jz      short loc_18006CB92
0x18006cb7e  mov     r9d, edi; int
0x18006cb81  mov     r8d, 1F8h; int
0x18006cb87  mov     rdx, r13; char *
0x18006cb8a  mov     rcx, rbp; this
0x18006cb8d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006cb92  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006cb99  jb      loc_18006CC2F
0x18006cb9f  mov     edx, 5Dh ; ']'
0x18006cba4  jmp     loc_18006C97E
0x18006cba9  call    cs:__imp_GetLastError
0x18006cbaf  test    eax, eax
0x18006cbb1  jnz     short loc_18006CBDF
0x18006cbb3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cbba  test    rcx, rcx
0x18006cbbd  jnz     short loc_18006CBCD
0x18006cbbf  lea     rcx, qword_18009CF60
0x18006cbc6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cbcd  mov     rax, [rcx]
0x18006cbd0  mov     rax, [rax]
0x18006cbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cbd8  test    rax, rax
0x18006cbdb  cmovnz  rsi, rax
0x18006cbdf  mov     ecx, ebp; dwErrCode
0x18006cbe1  call    cs:__imp_SetLastError
0x18006cbe7  cmp     [rsi+7CCh], ebx
0x18006cbed  jz      short loc_18006CC03
0x18006cbef  mov     r9d, ebx; int
0x18006cbf2  mov     r8d, 1FBh; int
0x18006cbf8  mov     rdx, r13; char *
0x18006cbfb  mov     rcx, rsi; this
0x18006cbfe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006cc03  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006cc0a  jb      short loc_18006CC2F
0x18006cc0c  mov     edx, 5Eh ; '^'
0x18006cc11  mov     [rsp+58h+var_38], ebx
0x18006cc15  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cc1c  lea     r8, WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids
0x18006cc23  mov     r9, r14
0x18006cc26  mov     rcx, [rcx+10h]
0x18006cc2a  call    WPP_SF_qd
0x18006cc2f  lea     rcx, [rsp+58h+arg_10]; this
0x18006cc34  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006cc39  mov     rbp, [rsp+58h+arg_18]
0x18006cc3e  mov     eax, ebx
0x18006cc40  mov     rbx, [rsp+58h+arg_0]
0x18006cc45  add     rsp, 30h
0x18006cc49  pop     r15
0x18006cc4b  pop     r14
0x18006cc4d  pop     r13
0x18006cc4f  pop     rdi
0x18006cc50  pop     rsi
0x18006cc51  retn
```
