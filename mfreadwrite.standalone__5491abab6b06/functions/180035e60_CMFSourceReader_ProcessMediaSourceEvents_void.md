# CMFSourceReader::ProcessMediaSourceEvents(void)

- ea: `0x180035e60`
- end: `0x180036429`
- name: `?ProcessMediaSourceEvents@CMFSourceReader@@AEAAJXZ`
- size: `1481`
- prototype: `__int64 __fastcall(CMFSourceReader *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180033400`
- `0x180034a60`
- `0x180035a50`

## callees

- `0x180006bd4`
- `0x180012640`
- `0x180014a14`
- `0x180035e60`
- `0x180037594`
- `0x180065e80`
- `0x1800db3a0`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035ecf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035fb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036063`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003631d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800363e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035ecf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035fb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036063`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003631d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800363e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035eb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003612f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003638a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035eb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003612f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003638a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003601b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003601b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180035ebb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180035fa1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003604f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800362c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003637f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180035ebb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180035fa1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003604f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800362c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003637f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036243`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800362e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800363a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036243`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800362e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800363a0`

## string_xrefs

- `0x180035e98`: `CMFSourceReader::ProcessMediaSourceEvents`

## pseudocode

```c
__int64 __fastcall CMFSourceReader::ProcessMediaSourceEvents(CMFSourceReader *this)
{
  CallStackTracing *v1; // rbx
  char *v3; // rdi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v6; // rax
  CallStackTracing *v7; // rbx
  __int64 v8; // rax
  struct IMFMediaEvent *v9; // rcx
  int v10; // edi
  CallStackTracing *v11; // rbx
  GUID *v12; // rsi
  DWORD v13; // ebp
  GUID *v14; // rax
  int v15; // eax
  int v16; // eax
  char *v18; // rdi
  DWORD v19; // ebp
  char *v20; // rax
  int v21; // ebx
  __int128 v22; // xmm0
  CallStackTracing *v23; // rcx
  __int64 v24; // rax
  CallStackTracing *v25; // rcx
  __int64 v26; // rax
  CallStackTracing *v27; // rcx
  __int64 v28; // rax
  CallStackTracing *v29; // rbx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rcx
  CallStackTracing *v33; // rbp
  CallStackTracing *v34; // rax
  CallStackContext *v35; // r14
  DWORD v36; // r15d
  CallStackContext *v37; // rax
  __int64 v38; // rdx
  CallStackTracing *v39; // rcx
  CallStackTracing *v40; // rax
  __int64 v41; // rax
  CallStackContext *v42; // rbp
  DWORD v43; // r14d
  CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rcx
  CallStackTracing *v47; // rbx
  CallStackTracing *v48; // rax
  __int64 v49; // rax
  struct IMFMediaEvent *i; // [rsp+30h] [rbp-48h] BYREF
  char v51[16]; // [rsp+38h] [rbp-40h] BYREF

  v1 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v1 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v1 + 8) )
  {
    v3 = (char *)v1 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v1 + 3));
    if ( Value )
    {
      v3 = Value;
    }
    else if ( !GetLastError() )
    {
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v23 = CallStackTracing::s_wpInstance;
      }
      v24 = (**(__int64 (__fastcall ***)(CallStackTracing *))v23)(v23);
      if ( v24 )
        v3 = (char *)v24;
    }
    SetLastError(LastError);
    v6 = *((unsigned int *)v3 + 497);
    v7 = CallStackTracing::s_wpInstance;
    if ( (unsigned int)v6 < *((_DWORD *)v3 + 498) )
    {
      v8 = 2 * v6;
      *(_QWORD *)&v3[8 * v8] = "CMFSourceReader::ProcessMediaSourceEvents";
      *(_DWORD *)&v3[8 * v8 + 8] = 3525;
    }
    ++*((_DWORD *)v3 + 497);
    if ( *((_BYTE *)v7 + 8) && *((_QWORD *)this + 71) )
    {
      v18 = (char *)v7 + 208;
      if ( *((_BYTE *)v7 + 8) )
      {
        v19 = GetLastError();
        v20 = (char *)TlsGetValue(*((_DWORD *)v7 + 3));
        if ( v20 )
        {
          v18 = v20;
        }
        else if ( !GetLastError() )
        {
          v27 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v27 = CallStackTracing::s_wpInstance;
          }
          v28 = (**(__int64 (__fastcall ***)(CallStackTracing *))v27)(v27);
          if ( v28 )
            v18 = (char *)v28;
        }
        SetLastError(v19);
      }
      v21 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 71) + 296LL))(*((_QWORD *)this + 71));
      v22 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 71) + 280LL))(
                         *((_QWORD *)this + 71),
                         v51);
      *((_DWORD *)v18 + 504) = v21;
      *((_OWORD *)v18 + 125) = v22;
    }
  }
  v9 = 0;
  for ( i = 0; ; v9 = i )
  {
    if ( v9 )
    {
      ((void (__fastcall *)(struct IMFMediaEvent *))v9->lpVtbl->Release)(v9);
      i = 0;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFMediaEvent **))(**((_QWORD **)this + 22) + 24LL))(
            *((_QWORD *)this + 22),
            0,
            &i);
    if ( v10 == -1072873856 )
    {
      v10 = 0;
      goto LABEL_14;
    }
    if ( v10 < 0 )
    {
      v29 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v29 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v42 = (CallStackTracing *)((char *)v29 + 208);
        v43 = GetLastError();
        v44 = (CallStackContext *)TlsGetValue(*((_DWORD *)v29 + 3));
        if ( v44 )
        {
          v42 = v44;
        }
        else if ( !GetLastError() )
        {
          v47 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v46, v45);
            CallStackTracing::s_wpInstance = v48;
            if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
            {
              v47 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v47 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v49 = (**(__int64 (__fastcall ***)(CallStackTracing *))v47)(v47);
          if ( v49 )
            v42 = (CallStackContext *)v49;
        }
        SetLastError(v43);
        if ( *((_DWORD *)v42 + 499) != v10 )
          CallStackContext::TraceFailure(v42, "CMFSourceReader::ProcessMediaSourceEvents", 3544, v10);
      }
      if ( g_wppLevels )
      {
        v30 = 310;
LABEL_53:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_549ec7c0105c354ac25ef526ec668427_Traceguids, this, v10);
        goto LABEL_54;
      }
      goto LABEL_54;
    }
    v10 = CMFSourceReader::OnMediaSourceEvent(this, i);
    if ( v10 < 0 )
      break;
  }
  v33 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v32, v31);
    CallStackTracing::s_wpInstance = v34;
    if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
    {
      v33 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v33 = (CallStackTracing *)&qword_18010C230;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
    }
  }
  if ( *((_BYTE *)v33 + 8) )
  {
    v35 = (CallStackTracing *)((char *)v33 + 208);
    v36 = GetLastError();
    v37 = (CallStackContext *)TlsGetValue(*((_DWORD *)v33 + 3));
    if ( v37 )
    {
      v35 = v37;
    }
    else if ( !GetLastError() )
    {
      v39 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      v41 = (**(__int64 (__fastcall ***)(CallStackTracing *))v39)(v39);
      if ( v41 )
        v35 = (CallStackContext *)v41;
    }
    SetLastError(v36);
    if ( *((_DWORD *)v35 + 499) != v10 )
      CallStackContext::TraceFailure(v35, "CMFSourceReader::ProcessMediaSourceEvents", 3546, v10);
  }
  if ( g_wppLevels )
  {
    v30 = 311;
    goto LABEL_53;
  }
LABEL_54:
  if ( v10 == -2147467260 && *((int *)this + 116) < 0 )
    v10 = *((_DWORD *)this + 116);
  CMFSourceReader::SetMediaSourceState(this, 0xFFFFFFFFLL, (unsigned int)v10);
LABEL_14:
  if ( i )
    ((void (__fastcall *)(struct IMFMediaEvent *))i->lpVtbl->Release)(i);
  v11 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v12 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v13 = GetLastError();
    v14 = (GUID *)TlsGetValue(*((_DWORD *)v11 + 3));
    if ( v14 )
    {
      v12 = v14;
    }
    else if ( !GetLastError() )
    {
      v25 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v25 = CallStackTracing::s_wpInstance;
      }
      v26 = (**(__int64 (__fastcall ***)(CallStackTracing *))v25)(v25);
      if ( v26 )
        v12 = (GUID *)v26;
    }
    SetLastError(v13);
    v15 = *(_DWORD *)&v12[124].Data2;
    if ( v15 )
    {
      v16 = v15 - 1;
      *(_DWORD *)&v12[124].Data2 = v16;
      if ( !v16 )
      {
        *(_DWORD *)&v12[124].Data2 = 0;
        *(_QWORD *)&v12[126].Data1 = 0;
        *(_DWORD *)&v12[124].Data4[4] = 0;
        v12[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v12[126].Data4 = 0;
        v12[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180035e60  push    rbx
0x180035e62  push    rsi
0x180035e63  push    rdi
0x180035e64  push    r12
0x180035e66  sub     rsp, 58h
0x180035e6a  mov     rax, cs:__security_cookie
0x180035e71  xor     rax, rsp
0x180035e74  mov     [rsp+78h+var_30], rax
0x180035e79  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035e80  mov     rsi, rcx
0x180035e83  mov     [rsp+78h+arg_10], r13
0x180035e8b  test    rbx, rbx
0x180035e8e  jz      loc_1800360B4
0x180035e94  cmp     byte ptr [rbx+8], 0
0x180035e98  lea     r13, aCmfsourcereade_183; "CMFSourceReader::ProcessMediaSourceEven"...
0x180035e9f  mov     [rsp+78h+arg_8], rbp
0x180035ea7  jz      short loc_180035F09
0x180035ea9  lea     rdi, [rbx+0D0h]
0x180035eb0  call    cs:__imp_GetLastError
0x180035eb6  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180035eb9  mov     ebp, eax
0x180035ebb  call    cs:__imp_TlsGetValue
0x180035ec1  test    rax, rax
0x180035ec4  jz      loc_1800360C5
0x180035eca  mov     rdi, rax
0x180035ecd  mov     ecx, ebp; dwErrCode
0x180035ecf  call    cs:__imp_SetLastError
0x180035ed5  mov     eax, [rdi+7C4h]
0x180035edb  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035ee2  cmp     eax, [rdi+7C8h]
0x180035ee8  jnb     short loc_180035EF9
0x180035eea  add     rax, rax
0x180035eed  mov     [rdi+rax*8], r13
0x180035ef1  mov     dword ptr [rdi+rax*8+8], 0DC5h
0x180035ef9  inc     dword ptr [rdi+7C4h]
0x180035eff  cmp     byte ptr [rbx+8], 0
0x180035f03  jnz     loc_180036029
0x180035f09  xor     r12d, r12d
0x180035f0c  mov     [rsp+78h+arg_18], r14
0x180035f14  mov     ecx, r12d
0x180035f17  mov     [rsp+78h+var_48], rcx
0x180035f1c  test    rcx, rcx
0x180035f1f  jz      short loc_180035F32
0x180035f21  mov     rax, [rcx]
0x180035f24  mov     rax, [rax+10h]
0x180035f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f2d  mov     [rsp+78h+var_48], r12
0x180035f32  mov     rcx, [rsi+0B0h]
0x180035f39  lea     r8, [rsp+78h+var_48]
0x180035f3e  xor     edx, edx
0x180035f40  mov     rax, [rcx]
0x180035f43  mov     rax, [rax+18h]
0x180035f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f4c  mov     edi, eax
0x180035f4e  cmp     eax, 0C00D3E80h
0x180035f53  jnz     loc_180036164
0x180035f59  mov     edi, r12d
0x180035f5c  mov     rcx, [rsp+78h+var_48]
0x180035f61  mov     r14, [rsp+78h+arg_18]
0x180035f69  mov     r13, [rsp+78h+arg_10]
0x180035f71  test    rcx, rcx
0x180035f74  jz      short loc_180035F82
0x180035f76  mov     rax, [rcx]
0x180035f79  mov     rax, [rax+10h]
0x180035f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f82  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035f89  cmp     [rbx+8], r12b
0x180035f8d  jz      short loc_180035FD0
0x180035f8f  lea     rsi, [rbx+0D0h]
0x180035f96  call    cs:__imp_GetLastError
0x180035f9c  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180035f9f  mov     ebp, eax
0x180035fa1  call    cs:__imp_TlsGetValue
0x180035fa7  test    rax, rax
0x180035faa  jz      loc_1800360FA
0x180035fb0  mov     rsi, rax
0x180035fb3  mov     ecx, ebp; dwErrCode
0x180035fb5  call    cs:__imp_SetLastError
0x180035fbb  mov     eax, [rsi+7C4h]
0x180035fc1  test    eax, eax
0x180035fc3  jz      short loc_180035FD0
0x180035fc5  sub     eax, 1
0x180035fc8  mov     [rsi+7C4h], eax
0x180035fce  jz      short loc_180035FF1
0x180035fd0  mov     rbp, [rsp+78h+arg_8]
0x180035fd8  mov     eax, edi
0x180035fda  mov     rcx, [rsp+78h+var_30]
0x180035fdf  xor     rcx, rsp; StackCookie
0x180035fe2  call    __security_check_cookie
0x180035fe7  add     rsp, 58h
0x180035feb  pop     r12
0x180035fed  pop     rdi
0x180035fee  pop     rsi
0x180035fef  pop     rbx
0x180035ff0  retn
0x180035ff1  mov     [rsi+7C4h], r12d
0x180035ff8  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180035fff  mov     [rsi+7E0h], r12
0x180036006  mov     [rsi+7CCh], r12d
0x18003600d  movups  xmmword ptr [rsi+7D0h], xmm0
0x180036014  mov     [rsi+7E8h], r12d
0x18003601b  call    cs:__imp_GetCurrentThreadId
0x180036021  mov     [rsi+7C0h], eax
0x180036027  jmp     short loc_180035FD0
0x180036029  cmp     qword ptr [rsi+238h], 0
0x180036031  jz      loc_180035F09
0x180036037  cmp     byte ptr [rbx+8], 0
0x18003603b  lea     rdi, [rbx+0D0h]
0x180036042  jz      short loc_180036069
0x180036044  call    cs:__imp_GetLastError
0x18003604a  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003604d  mov     ebp, eax
0x18003604f  call    cs:__imp_TlsGetValue
0x180036055  test    rax, rax
0x180036058  jz      loc_18003612F
0x18003605e  mov     rdi, rax
0x180036061  mov     ecx, ebp; dwErrCode
0x180036063  call    cs:__imp_SetLastError
0x180036069  mov     rcx, [rsi+238h]
0x180036070  mov     rax, [rcx]
0x180036073  mov     rax, [rax+128h]
0x18003607a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003607f  mov     r8, [rsi+238h]
0x180036086  lea     rdx, [rsp+78h+var_40]
0x18003608b  mov     ebx, eax
0x18003608d  mov     rcx, [r8]
0x180036090  mov     rax, [rcx+118h]
0x180036097  mov     rcx, r8
0x18003609a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003609f  movups  xmm0, xmmword ptr [rax]
0x1800360a2  mov     [rdi+7E0h], ebx
0x1800360a8  movups  xmmword ptr [rdi+7D0h], xmm0
0x1800360af  jmp     loc_180035F09
0x1800360b4  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800360b9  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800360c0  jmp     loc_180035E94
0x1800360c5  call    cs:__imp_GetLastError
0x1800360cb  test    eax, eax
0x1800360cd  jnz     loc_180035ECD
0x1800360d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800360da  test    rcx, rcx
0x1800360dd  jz      loc_1800361F3
0x1800360e3  mov     rax, [rcx]
0x1800360e6  mov     rax, [rax]
0x1800360e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360ee  test    rax, rax
0x1800360f1  cmovnz  rdi, rax
0x1800360f5  jmp     loc_180035ECD
0x1800360fa  call    cs:__imp_GetLastError
0x180036100  test    eax, eax
0x180036102  jnz     loc_180035FB3
0x180036108  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003610f  test    rcx, rcx
0x180036112  jz      loc_180036204
0x180036118  mov     rax, [rcx]
0x18003611b  mov     rax, [rax]
0x18003611e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036123  test    rax, rax
0x180036126  cmovnz  rsi, rax
0x18003612a  jmp     loc_180035FB3
0x18003612f  call    cs:__imp_GetLastError
0x180036135  test    eax, eax
0x180036137  jnz     loc_180036061
0x18003613d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036144  test    rcx, rcx
0x180036147  jz      loc_180036226
0x18003614d  mov     rax, [rcx]
0x180036150  mov     rax, [rax]
0x180036153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036158  test    rax, rax
0x18003615b  cmovnz  rdi, rax
0x18003615f  jmp     loc_180036061
0x180036164  test    edi, edi
0x180036166  jns     short loc_1800361D6
0x180036168  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003616f  test    rbx, rbx
0x180036172  jz      loc_180036215
0x180036178  cmp     [rbx+8], r12b
0x18003617c  jnz     loc_18003636C
0x180036182  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180036189  jb      short loc_1800361AE
0x18003618b  mov     edx, 136h
0x180036190  mov     rcx, cs:WPP_GLOBAL_Control
0x180036197  lea     r8, WPP_549ec7c0105c354ac25ef526ec668427_Traceguids
0x18003619e  mov     r9, rsi
0x1800361a1  mov     [rsp+78h+var_58], edi
0x1800361a5  mov     rcx, [rcx+10h]
0x1800361a9  call    WPP_SF_qD
0x1800361ae  cmp     edi, 80004004h
0x1800361b4  jnz     short loc_1800361C1
0x1800361b6  mov     eax, [rsi+1D0h]
0x1800361bc  test    eax, eax
0x1800361be  cmovs   edi, eax
0x1800361c1  mov     r8d, edi
0x1800361c4  mov     edx, 0FFFFFFFFh
0x1800361c9  mov     rcx, rsi
0x1800361cc  call    ?SetMediaSourceState@CMFSourceReader@@AEAAXW4MediaSourceState@1@J@Z; CMFSourceReader::SetMediaSourceState(CMFSourceReader::MediaSourceState,long)
0x1800361d1  jmp     loc_180035F5C
0x1800361d6  mov     rdx, [rsp+78h+var_48]; struct IMFMediaEvent *
0x1800361db  mov     rcx, rsi; this
0x1800361de  call    ?OnMediaSourceEvent@CMFSourceReader@@AEAAJPEAUIMFMediaEvent@@@Z; CMFSourceReader::OnMediaSourceEvent(IMFMediaEvent *)
0x1800361e3  mov     edi, eax
0x1800361e5  test    eax, eax
0x1800361e7  js      short loc_180036237
0x1800361e9  mov     rcx, [rsp+78h+var_48]
0x1800361ee  jmp     loc_180035F1C
0x1800361f3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800361f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800361ff  jmp     loc_1800360E3
0x180036204  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180036209  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036210  jmp     loc_180036118
0x180036215  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003621a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036221  jmp     loc_180036178
0x180036226  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003622b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036232  jmp     loc_18003614D
0x180036237  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003623e  test    rbp, rbp
0x180036241  jnz     short loc_180036274
0x180036243  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036249  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036250  mov     rcx, rax
0x180036253  test    rax, rax
0x180036256  jz      short loc_180036298
0x180036258  mov     rax, [rax]
0x18003625b  mov     edx, 7F0h
0x180036260  mov     rax, [rax+8]
0x180036264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036269  test    eax, eax
0x18003626b  jz      short loc_180036298
0x18003626d  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036274  lea     rbx, qword_18010C230
0x18003627b  cmp     [rbp+8], r12b
0x18003627f  jnz     short loc_1800362AB
0x180036281  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180036288  jb      loc_1800361AE
0x18003628e  mov     edx, 137h
0x180036293  jmp     loc_180036190
0x180036298  lea     rbx, qword_18010C230
0x18003629f  mov     rbp, rbx
0x1800362a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800362a9  jmp     short loc_18003627B
0x1800362ab  lea     r14, [rbp+0D0h]
0x1800362b2  mov     [rsp+78h+var_28], r15
0x1800362b7  call    cs:__imp_GetLastError
0x1800362bd  mov     ecx, [rbp+0Ch]; dwTlsIndex
0x1800362c0  mov     r15d, eax
0x1800362c3  call    cs:__imp_TlsGetValue
0x1800362c9  test    rax, rax
0x1800362cc  jnz     short loc_180036317
0x1800362ce  call    cs:__imp_GetLastError
0x1800362d4  test    eax, eax
0x1800362d6  jnz     short loc_18003631A
0x1800362d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800362df  test    rcx, rcx
0x1800362e2  jnz     short loc_180036303
0x1800362e4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800362ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800362f1  mov     rcx, rax
0x1800362f4  test    rax, rax
0x1800362f7  jnz     short loc_18003634E
0x1800362f9  mov     rcx, rbx
0x1800362fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036303  mov     rax, [rcx]
0x180036306  mov     rax, [rax]
0x180036309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003630e  test    rax, rax
0x180036311  cmovnz  r14, rax
0x180036315  jmp     short loc_18003631A
0x180036317  mov     r14, rax
0x18003631a  mov     ecx, r15d; dwErrCode
0x18003631d  call    cs:__imp_SetLastError
0x180036323  mov     r15, [rsp+78h+var_28]
0x180036328  cmp     [r14+7CCh], edi
0x18003632f  jz      loc_180036281
0x180036335  mov     r9d, edi; int
0x180036338  mov     r8d, 0DDAh; int
0x18003633e  mov     rdx, r13; char *
0x180036341  mov     rcx, r14; this
0x180036344  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180036349  jmp     loc_180036281
0x18003634e  mov     rax, [rax]
0x180036351  mov     edx, 7F0h
0x180036356  mov     rax, [rax+8]
0x18003635a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003635f  test    eax, eax
0x180036361  jz      short loc_1800362F9
0x180036363  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003636a  jmp     short loc_180036303
0x18003636c  lea     rbp, [rbx+0D0h]
0x180036373  call    cs:__imp_GetLastError
0x180036379  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003637c  mov     r14d, eax
0x18003637f  call    cs:__imp_TlsGetValue
0x180036385  test    rax, rax
0x180036388  jnz     short loc_1800363DA
0x18003638a  call    cs:__imp_GetLastError
0x180036390  test    eax, eax
  ... truncated ...
```
