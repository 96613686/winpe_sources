# CDShowSBEWrapper::FireEx(_GUID,ulong,ulong,ulong,ulong)

- ea: `0x180061b00`
- end: `0x1800621de`
- name: `?FireEx@CDShowSBEWrapper@@UEAAJU_GUID@@KKKK@Z`
- size: `1758`
- prototype: `int(CDShowSBEWrapper *__hidden this, struct _GUID *__struct_ptr, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032a50`
- `0x18003e7e8`
- `0x180051ce4`
- `0x180053dc0`
- `0x1800595c0`
- `0x180061b00`
- `0x180073d4c`
- `0x180073d58`
- `0x180074160`
- `0x180074a06`
- `0x180074a12`
- `0x180074aba`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180061bf4`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x180061bf4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180061f7e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006206f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180061f7e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006206f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180061ea2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180061ea2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18006219d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18006219d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180061ebc`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180061ebc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180061fac`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180062089`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180061fac`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180062089`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061c54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061d1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061e03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061ede`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062021`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800620a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061c54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061d1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061e03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061ede`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062021`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800620a1`

## pseudocode

```c
__int64 __fastcall CDShowSBEWrapper::FireEx(
        CDShowSBEWrapper *this,
        struct _GUID *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  unsigned int v9; // edi
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v11; // ebx
  __int128 v12; // xmm0
  void (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rcx
  int v14; // ebx
  CallStackTracing *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  void *v19; // rax
  void *v20; // r12
  CallStackTracing *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  HRESULT v24; // ebx
  CallStackTracing *v25; // rcx
  SAFEARRAY *v26; // rdi
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  SAFEARRAY *v30; // rax
  CallStackTracing *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rcx
  CallStackTracing *v35; // rcx
  CallStackTracing *v36; // rax
  CallStackTracing *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  struct CallStackContext *v40; // rax
  _BYTE v42[4]; // [rsp+50h] [rbp-59h] BYREF
  ULONG Size; // [rsp+54h] [rbp-55h] BYREF
  int Size_4; // [rsp+58h] [rbp-51h] BYREF
  __int64 v45; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v46; // [rsp+68h] [rbp-41h]
  SAFEARRAYBOUND rgsabound; // [rsp+70h] [rbp-39h] BYREF
  void *ppvData; // [rsp+78h] [rbp-31h] BYREF
  struct tagPROPVARIANT v49; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v50[16]; // [rsp+98h] [rbp-11h] BYREF

  v46 = a4;
  v9 = a4;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v42, "CDShowSBEWrapper::FireEx", 483);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this - 2) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this - 2) + 296LL))(*((_QWORD *)this - 2));
    v12 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this - 2) + 280LL))(
                       *((_QWORD *)this - 2),
                       v50);
    *((_DWORD *)ThreadRelativeContext + 504) = v11;
    *((_OWORD *)ThreadRelativeContext + 125) = v12;
    v9 = v46;
  }
  Size_4 = 0;
  v13 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this - 54);
  v45 = 0;
  if ( v13 )
    (**v13)(v13, &GUID_caede759_b6b1_11db_a578_0018f3fa24c6, &v45);
  Size = 0;
  memset(&v49, 0, sizeof(v49));
  memset(&v49, 0, sizeof(v49));
  v14 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, _QWORD, _QWORD, unsigned int, unsigned int, int *, ULONG *, _QWORD))(*(_QWORD *)v45 + 24LL))(
          v45,
          a2,
          a3,
          v9,
          a5,
          a6,
          &Size_4,
          &Size,
          0);
  if ( v14 < 0 )
  {
    v15 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext(v15);
      if ( *((_DWORD *)v17 + 499) != v14 )
        CallStackContext::TraceFailure(v17, "CDShowSBEWrapper::FireEx", 496, v14);
    }
    if ( g_wppLevels )
    {
      v18 = 57;
LABEL_17:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        WPP_37ff27b5f7033090a0d8eec054f7c30c_Traceguids,
        (char *)this - 496,
        v14);
      goto LABEL_81;
    }
    goto LABEL_81;
  }
  v19 = operator new[](Size);
  v20 = v19;
  if ( v19 )
  {
    v24 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, _QWORD, _QWORD, unsigned int, unsigned int, int *, ULONG *, void *))(*(_QWORD *)v45 + 24LL))(
            v45,
            a2,
            a3,
            v9,
            a5,
            a6,
            &Size_4,
            &Size,
            v19);
    if ( v24 < 0 )
    {
      v25 = CallStackTracing::s_wpInstance;
      v26 = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v25 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v25 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext(v25);
        if ( *((_DWORD *)v28 + 499) != v24 )
          CallStackContext::TraceFailure(v28, "CDShowSBEWrapper::FireEx", 503, v24);
      }
      if ( !g_wppLevels )
        goto LABEL_79;
      v29 = 59;
LABEL_78:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v29,
        WPP_37ff27b5f7033090a0d8eec054f7c30c_Traceguids,
        (char *)this - 496,
        v24);
LABEL_79:
      operator delete(v20);
      if ( v26 )
        SafeArrayDestroy(v26);
      goto LABEL_81;
    }
    rgsabound.cElements = Size;
    rgsabound.lLbound = 0;
    v30 = SafeArrayCreate(0x11u, 1u, &rgsabound);
    ppvData = 0;
    v26 = v30;
    v24 = SafeArrayAccessData(v30, &ppvData);
    if ( v24 < 0 )
    {
      v31 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext(v31);
        if ( *((_DWORD *)v33 + 499) != v24 )
          CallStackContext::TraceFailure(v33, "CDShowSBEWrapper::FireEx", 512, v24);
      }
      if ( !g_wppLevels )
        goto LABEL_79;
      v29 = 60;
      goto LABEL_78;
    }
    if ( ppvData && Size )
    {
      if ( v26->rgsabound[0].cElements < (unsigned __int64)Size )
      {
        memset_0(ppvData, 0, v26->rgsabound[0].cElements);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
        SafeArrayUnaccessData(v26);
        v37 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        v24 = -2147467259;
        if ( *((_BYTE *)v37 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext(v37);
          if ( *((_DWORD *)v39 + 499) != -2147467259 )
            CallStackContext::TraceFailure(v39, "CDShowSBEWrapper::FireEx", 523, -2147467259);
        }
        if ( !g_wppLevels )
          goto LABEL_79;
        v29 = 61;
        goto LABEL_78;
      }
      memcpy_0(ppvData, v20, Size);
    }
    SafeArrayUnaccessData(v26);
    v49.hVal.QuadPart = (LONGLONG)v26;
    v49.vt = 0x2000;
    CMFSRWLock::LockExclusive((PSRWLOCK)this + 32);
    v34 = *((_QWORD *)this - 61);
    if ( v34 )
      v24 = CDSSourceObjectBase::_QueueEvent((CDSSourceObjectBase *)(v34 + 32), 2u, a2, 0, &v49);
    CMFSRWLock::UnlockExclusive((CDShowSBEWrapper *)((char *)this + 256));
    if ( v24 >= 0 )
      goto LABEL_79;
    v35 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v36;
      if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
      {
        v35 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v35 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v35 + 8) )
    {
      v40 = CallStackTracing::GetThreadRelativeContext(v35);
      if ( *((_DWORD *)v40 + 499) != v24 )
        CallStackContext::TraceFailure(v40, "CDShowSBEWrapper::FireEx", 539, v24);
    }
    if ( !g_wppLevels )
      goto LABEL_79;
    v29 = 62;
    goto LABEL_78;
  }
  v21 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
    CallStackTracing::s_wpInstance = v22;
    if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
    {
      v21 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v21 = (CallStackTracing *)&qword_1800EB130;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
    }
  }
  v14 = -2147024882;
  if ( *((_BYTE *)v21 + 8) )
  {
    v23 = CallStackTracing::GetThreadRelativeContext(v21);
    if ( *((_DWORD *)v23 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v23, "CDShowSBEWrapper::FireEx", 500, -2147024882);
  }
  if ( g_wppLevels )
  {
    v18 = 58;
    goto LABEL_17;
  }
LABEL_81:
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v45);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v42);
  return 0;
}

```

## disassembly

```asm
0x180061b00  push    rbp
0x180061b02  push    rbx
0x180061b03  push    rsi
0x180061b04  push    rdi
0x180061b05  push    r12
0x180061b07  push    r13
0x180061b09  push    r14
0x180061b0b  push    r15
0x180061b0d  lea     rbp, [rsp-0Fh]
0x180061b12  sub     rsp, 0B8h
0x180061b19  mov     rax, cs:__security_cookie
0x180061b20  xor     rax, rsp
0x180061b23  mov     [rbp+47h+var_48], rax
0x180061b27  mov     r15d, r8d
0x180061b2a  mov     [rbp+47h+var_88], r9d
0x180061b2e  mov     r13, rdx
0x180061b31  mov     r14, rcx
0x180061b34  mov     r8d, 1E3h; int
0x180061b3a  lea     rdx, aCdshowsbewrapp_11; "CDShowSBEWrapper::FireEx"
0x180061b41  lea     rcx, [rbp+47h+var_A0]; this
0x180061b45  mov     edi, r9d
0x180061b48  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180061b4d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180061b54  xor     r12d, r12d
0x180061b57  cmp     [rcx+8], r12b
0x180061b5b  jz      short loc_180061BAB
0x180061b5d  cmp     [r14-10h], r12
0x180061b61  jz      short loc_180061BAB
0x180061b63  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061b68  mov     rcx, [r14-10h]
0x180061b6c  mov     rdi, rax
0x180061b6f  mov     rdx, [rcx]
0x180061b72  mov     rax, [rdx+128h]
0x180061b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b7e  mov     rcx, [r14-10h]
0x180061b82  mov     ebx, eax
0x180061b84  mov     rdx, [rcx]
0x180061b87  mov     rax, [rdx+118h]
0x180061b8e  lea     rdx, [rbp+47h+var_58]
0x180061b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b97  movups  xmm0, xmmword ptr [rax]
0x180061b9a  mov     [rdi+7E0h], ebx
0x180061ba0  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180061ba8  mov     edi, [rbp+47h+var_88]
0x180061bab  lea     rsi, [r14-1F0h]
0x180061bb2  mov     dword ptr [rbp+47h+Size+4], r12d
0x180061bb6  mov     rcx, [rsi+40h]
0x180061bba  mov     [rbp+47h+var_90], r12
0x180061bbe  test    rcx, rcx
0x180061bc1  jz      short loc_180061BD9
0x180061bc3  mov     rax, [rcx]
0x180061bc6  lea     r8, [rbp+47h+var_90]
0x180061bca  lea     rdx, _GUID_caede759_b6b1_11db_a578_0018f3fa24c6
0x180061bd1  mov     rax, [rax]
0x180061bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bd9  xor     eax, eax
0x180061bdb  mov     dword ptr [rbp+47h+Size], r12d
0x180061bdf  xorps   xmm0, xmm0
0x180061be2  mov     qword ptr [rbp+47h+var_70+10h], rax
0x180061be6  xor     edx, edx; Val
0x180061be8  lea     rcx, [rbp+47h+var_70]; void *
0x180061bec  movups  xmmword ptr [rbp+47h+var_70], xmm0
0x180061bf0  lea     r8d, [rax+18h]; Size
0x180061bf4  call    cs:__imp_memset
0x180061bfb  nop     dword ptr [rax+rax+00h]
0x180061c00  mov     rcx, [rbp+47h+var_90]
0x180061c04  lea     rdx, [rbp+47h+Size]
0x180061c08  mov     [rsp+0F0h+var_B0], r12
0x180061c0d  mov     r9d, edi
0x180061c10  mov     [rsp+0F0h+var_B8], rdx
0x180061c15  mov     r8d, r15d
0x180061c18  lea     rdx, [rbp+47h+Size+4]
0x180061c1c  mov     rax, [rcx]
0x180061c1f  mov     [rsp+0F0h+var_C0], rdx
0x180061c24  mov     edx, [rbp+47h+arg_28]
0x180061c27  mov     [rsp+0F0h+var_C8], edx
0x180061c2b  mov     edx, [rbp+47h+arg_20]
0x180061c2e  mov     rax, [rax+18h]
0x180061c32  mov     dword ptr [rsp+0F0h+var_D0], edx
0x180061c36  mov     rdx, r13
0x180061c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c3e  mov     ebx, eax
0x180061c40  test    eax, eax
0x180061c42  jns     loc_180061CFB
0x180061c48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061c4f  test    rcx, rcx
0x180061c52  jnz     short loc_180061C9B
0x180061c54  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061c5b  nop     dword ptr [rax+rax+00h]
0x180061c60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061c67  mov     rcx, rax
0x180061c6a  test    rax, rax
0x180061c6d  jz      short loc_180061C8D
0x180061c6f  mov     rax, [rax]
0x180061c72  mov     edx, 7F0h
0x180061c77  mov     rax, [rax+8]
0x180061c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c80  test    eax, eax
0x180061c82  jz      short loc_180061C8D
0x180061c84  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061c8b  jmp     short loc_180061C9B
0x180061c8d  lea     rcx, qword_1800EB130; this
0x180061c94  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061c9b  cmp     [rcx+8], r12b
0x180061c9f  jz      short loc_180061CC6
0x180061ca1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061ca6  cmp     [rax+7CCh], ebx
0x180061cac  jz      short loc_180061CC6
0x180061cae  mov     r9d, ebx; int
0x180061cb1  lea     rdx, aCdshowsbewrapp_11; "CDShowSBEWrapper::FireEx"
0x180061cb8  mov     r8d, 1F0h; int
0x180061cbe  mov     rcx, rax; this
0x180061cc1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061cc6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061ccd  jb      loc_1800621A9
0x180061cd3  mov     edx, 39h ; '9'
0x180061cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180061cdf  lea     r8, WPP_37ff27b5f7033090a0d8eec054f7c30c_Traceguids
0x180061ce6  mov     r9, rsi
0x180061ce9  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180061ced  mov     rcx, [rcx+10h]
0x180061cf1  call    WPP_SF_qD
0x180061cf6  jmp     loc_1800621A9
0x180061cfb  mov     ecx, dword ptr [rbp+47h+Size]; unsigned __int64
0x180061cfe  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180061d03  mov     r12, rax
0x180061d06  test    rax, rax
0x180061d09  jnz     loc_180061DA9
0x180061d0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061d16  test    rcx, rcx
0x180061d19  jnz     short loc_180061D62
0x180061d1b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061d22  nop     dword ptr [rax+rax+00h]
0x180061d27  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061d2e  mov     rcx, rax
0x180061d31  test    rax, rax
0x180061d34  jz      short loc_180061D54
0x180061d36  mov     rax, [rax]
0x180061d39  mov     edx, 7F0h
0x180061d3e  mov     rax, [rax+8]
0x180061d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061d47  test    eax, eax
0x180061d49  jz      short loc_180061D54
0x180061d4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061d52  jmp     short loc_180061D62
0x180061d54  lea     rcx, qword_1800EB130; this
0x180061d5b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061d62  cmp     byte ptr [rcx+8], 0
0x180061d66  mov     ebx, 8007000Eh
0x180061d6b  jz      short loc_180061D92
0x180061d6d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061d72  cmp     [rax+7CCh], ebx
0x180061d78  jz      short loc_180061D92
0x180061d7a  mov     r9d, ebx; int
0x180061d7d  lea     rdx, aCdshowsbewrapp_11; "CDShowSBEWrapper::FireEx"
0x180061d84  mov     r8d, 1F4h; int
0x180061d8a  mov     rcx, rax; this
0x180061d8d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061d92  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061d99  jb      loc_1800621A9
0x180061d9f  mov     edx, 3Ah ; ':'
0x180061da4  jmp     loc_180061CD8
0x180061da9  mov     rcx, [rbp+47h+var_90]
0x180061dad  lea     rdx, [rbp+47h+Size]
0x180061db1  mov     [rsp+0F0h+var_B0], r12
0x180061db6  mov     r9d, edi
0x180061db9  mov     [rsp+0F0h+var_B8], rdx
0x180061dbe  mov     r8d, r15d
0x180061dc1  lea     rdx, [rbp+47h+Size+4]
0x180061dc5  mov     rax, [rcx]
0x180061dc8  mov     [rsp+0F0h+var_C0], rdx
0x180061dcd  mov     edx, [rbp+47h+arg_28]
0x180061dd0  mov     [rsp+0F0h+var_C8], edx
0x180061dd4  mov     edx, [rbp+47h+arg_20]
0x180061dd7  mov     rax, [rax+18h]
0x180061ddb  mov     dword ptr [rsp+0F0h+var_D0], edx
0x180061ddf  mov     rdx, r13
0x180061de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061de7  xor     r15d, r15d
0x180061dea  mov     ebx, eax
0x180061dec  test    eax, eax
0x180061dee  jns     loc_180061E8C
0x180061df4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061dfb  mov     edi, r15d
0x180061dfe  test    rcx, rcx
0x180061e01  jnz     short loc_180061E4A
0x180061e03  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061e0a  nop     dword ptr [rax+rax+00h]
0x180061e0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061e16  mov     rcx, rax
0x180061e19  test    rax, rax
0x180061e1c  jz      short loc_180061E3C
0x180061e1e  mov     rax, [rax]
0x180061e21  mov     edx, 7F0h
0x180061e26  mov     rax, [rax+8]
0x180061e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061e2f  test    eax, eax
0x180061e31  jz      short loc_180061E3C
0x180061e33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061e3a  jmp     short loc_180061E4A
0x180061e3c  lea     rcx, qword_1800EB130; this
0x180061e43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061e4a  cmp     [rcx+8], r15b
0x180061e4e  jz      short loc_180061E75
0x180061e50  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061e55  cmp     [rax+7CCh], ebx
0x180061e5b  jz      short loc_180061E75
0x180061e5d  mov     r9d, ebx; int
0x180061e60  lea     rdx, aCdshowsbewrapp_11; "CDShowSBEWrapper::FireEx"
0x180061e67  mov     r8d, 1F7h; int
0x180061e6d  mov     rcx, rax; this
0x180061e70  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061e75  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061e7c  jb      loc_18006218D
0x180061e82  mov     edx, 3Bh ; ';'
0x180061e87  jmp     loc_18006216F
0x180061e8c  mov     eax, dword ptr [rbp+47h+Size]
0x180061e8f  lea     r8, [rbp+47h+rgsabound]; rgsabound
0x180061e93  mov     ecx, 11h; vt
0x180061e98  mov     [rbp+47h+rgsabound.cElements], eax
0x180061e9b  mov     [rbp+47h+rgsabound.lLbound], r15d
0x180061e9f  lea     edx, [rcx-10h]; cDims
0x180061ea2  call    cs:__imp_SafeArrayCreate
0x180061ea9  nop     dword ptr [rax+rax+00h]
0x180061eae  lea     rdx, [rbp+47h+ppvData]; ppvData
0x180061eb2  mov     [rbp+47h+ppvData], r15
0x180061eb6  mov     rcx, rax; psa
0x180061eb9  mov     rdi, rax
0x180061ebc  call    cs:__imp_SafeArrayAccessData
0x180061ec3  nop     dword ptr [rax+rax+00h]
0x180061ec8  mov     ebx, eax
0x180061eca  test    eax, eax
0x180061ecc  jns     loc_180061F67
0x180061ed2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061ed9  test    rcx, rcx
0x180061edc  jnz     short loc_180061F25
0x180061ede  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061ee5  nop     dword ptr [rax+rax+00h]
0x180061eea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061ef1  mov     rcx, rax
0x180061ef4  test    rax, rax
0x180061ef7  jz      short loc_180061F17
0x180061ef9  mov     rax, [rax]
0x180061efc  mov     edx, 7F0h
0x180061f01  mov     rax, [rax+8]
0x180061f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f0a  test    eax, eax
0x180061f0c  jz      short loc_180061F17
0x180061f0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061f15  jmp     short loc_180061F25
0x180061f17  lea     rcx, qword_1800EB130; this
0x180061f1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061f25  cmp     [rcx+8], r15b
0x180061f29  jz      short loc_180061F50
0x180061f2b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061f30  cmp     [rax+7CCh], ebx
0x180061f36  jz      short loc_180061F50
0x180061f38  mov     r9d, ebx; int
0x180061f3b  lea     rdx, aCdshowsbewrapp_11; "CDShowSBEWrapper::FireEx"
0x180061f42  mov     r8d, 200h; int
0x180061f48  mov     rcx, rax; this
0x180061f4b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061f50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061f57  jb      loc_18006218D
0x180061f5d  mov     edx, 3Ch ; '<'
0x180061f62  jmp     loc_18006216F
0x180061f67  mov     rcx, [rbp+47h+ppvData]; void *
0x180061f6b  test    rcx, rcx
0x180061f6e  jz      short loc_180061FA9
0x180061f70  mov     r8d, dword ptr [rbp+47h+Size]; Size
0x180061f74  test    r8, r8
0x180061f77  jz      short loc_180061FA9
0x180061f79  test    rcx, rcx
0x180061f7c  jnz     short loc_180061F95
0x180061f7e  call    cs:__imp__o__errno
0x180061f85  nop     dword ptr [rax+rax+00h]
0x180061f8a  mov     dword ptr [rax], 16h
0x180061f90  jmp     loc_180062081
0x180061f95  mov     eax, [rdi+18h]
0x180061f98  cmp     rax, r8
0x180061f9b  jb      loc_180062065
0x180061fa1  mov     rdx, r12; Src
0x180061fa4  call    memcpy_0
0x180061fa9  mov     rcx, rdi; psa
0x180061fac  call    cs:__imp_SafeArrayUnaccessData
0x180061fb3  nop     dword ptr [rax+rax+00h]
0x180061fb8  mov     eax, 2000h
0x180061fbd  mov     qword ptr [rbp+47h+var_70+8], rdi
0x180061fc1  lea     r15, [r14+100h]
0x180061fc8  mov     word ptr [rbp+47h+var_70], ax
0x180061fcc  mov     rcx, r15; SRWLock
0x180061fcf  call    ?LockExclusive@CMFSRWLock@@QEAAXXZ; CMFSRWLock::LockExclusive(void)
0x180061fd4  mov     rcx, [r14-1E8h]
0x180061fdb  test    rcx, rcx
0x180061fde  jz      short loc_180061FFE
0x180061fe0  xor     r9d, r9d; int
0x180061fe3  lea     rax, [rbp+47h+var_70]
0x180061fe7  add     rcx, 20h ; ' '; this
0x180061feb  mov     [rsp+0F0h+var_D0], rax; struct tagPROPVARIANT *
0x180061ff0  mov     r8, r13; struct _GUID *
  ... truncated ...
```
