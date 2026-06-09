# CMFReadWriteTransformFactory::EnumTransformsByLuid(_GUID,uint,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFActivate * * *,uint *)

- ea: `0x1800d7614`
- end: `0x1800d7ad3`
- name: `?EnumTransformsByLuid@CMFReadWriteTransformFactory@@AEAAJU_GUID@@IPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAPEAPEAUIMFActivate@@PEAI@Z`
- size: `1215`
- prototype: `__int64 __usercall@<rax>(CMFReadWriteTransformFactory *__hidden this@<rcx>, struct _GUID *__struct_ptr@<rdx>, unsigned int@<r8d>, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *@<r9>, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, struct IMFActivate ***, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800ef46c`

## callees

- `0x18000517c`
- `0x180006bd4`
- `0x18000e590`
- `0x180012640`
- `0x1800252a0`
- `0x1800a5a1c`
- `0x1800d7614`
- `0x1800efde0`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d7776`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d78c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d7a2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d7776`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d78c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d7a2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d76f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d770c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d785f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d79a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d79c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d76f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d770c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d785f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d79a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d79c1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d76fc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d784f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d79b1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d76fc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d784f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d79b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d76a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7722`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d77f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7875`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7955`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d79d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d76a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7722`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d77f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7875`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7955`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d79d7`
- `MFPlat!MFTEnum2` at `0x1800d7933`
- `MFPlat!MFTEnum2` at `0x1800d7933`
- `MFPlat!MFCreateAttributes` at `0x1800d767e`
- `MFPlat!MFCreateAttributes` at `0x1800d767e`

## string_xrefs

- `0x1800d7631`: `CMFReadWriteTransformFactory::EnumTransformsByLuid`
- `0x1800d7787`: `CMFReadWriteTransformFactory::EnumTransformsByLuid`
- `0x1800d78da`: `CMFReadWriteTransformFactory::EnumTransformsByLuid`
- `0x1800d7a3c`: `CMFReadWriteTransformFactory::EnumTransformsByLuid`

## pseudocode

```c
__int64 __fastcall CMFReadWriteTransformFactory::EnumTransformsByLuid(
        CMFReadWriteTransformFactory *this,
        struct _GUID *a2,
        unsigned int a3,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a4,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a5,
        struct IMFActivate ***a6,
        unsigned int *a7)
{
  __int64 v11; // rdx
  __int64 v12; // r8
  HRESULT v13; // ebx
  __int64 v14; // rcx
  CallStackTracing *v15; // rdi
  CallStackTracing *v16; // rax
  CallStackContext *v17; // rsi
  DWORD v18; // r15d
  CallStackContext *v19; // rax
  __int64 v20; // rdx
  CallStackTracing *v21; // rcx
  CallStackTracing *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  CallStackTracing *v26; // rdi
  CallStackTracing *v27; // rax
  CallStackContext *v28; // rsi
  DWORD v29; // r15d
  CallStackContext *v30; // rax
  __int64 v31; // rdx
  CallStackTracing *v32; // rcx
  CallStackTracing *v33; // rax
  __int64 v34; // rax
  __int64 v35; // rcx
  CallStackTracing *v36; // rdi
  CallStackTracing *v37; // rax
  CallStackContext *v38; // rsi
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  __int64 v41; // rdx
  CallStackTracing *v42; // rcx
  CallStackTracing *v43; // rax
  __int64 v44; // rax
  char v46[8]; // [rsp+40h] [rbp-38h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int64 v48[2]; // [rsp+50h] [rbp-28h] BYREF
  __int128 v49; // [rsp+60h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v46,
    "CMFReadWriteTransformFactory::EnumTransformsByLuid",
    545);
  ppMFAttributes = 0;
  v48[0] = 0;
  *a7 = 0;
  if ( CMFReadWriteTransformFactory::GetD3DDeviceLUID(this, v48) )
  {
    v13 = 0;
    goto LABEL_67;
  }
  v13 = MFCreateAttributes(&ppMFAttributes, 1u);
  if ( v13 >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(IMFAttributes *, void *, unsigned __int64 *, __int64))ppMFAttributes->lpVtbl->SetBlob)(
            ppMFAttributes,
            &MFT_ENUM_ADAPTER_LUID,
            v48,
            8);
    if ( v13 >= 0 )
    {
      v49 = (__int128)*a2;
      v13 = MFTEnum2(&v49, a3, a4, a5, ppMFAttributes, a6, a7);
      if ( v13 < 0 )
      {
        v36 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v35, v11);
          CallStackTracing::s_wpInstance = v37;
          if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
          {
            v36 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v36 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        if ( *((_BYTE *)v36 + 8) )
        {
          v38 = (CallStackTracing *)((char *)v36 + 208);
          LastError = GetLastError();
          Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v36 + 3));
          if ( Value )
          {
            v38 = Value;
          }
          else if ( !GetLastError() )
          {
            v42 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
              CallStackTracing::s_wpInstance = v43;
              if ( v43
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
              {
                v42 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v42 = (CallStackTracing *)&qword_18010C230;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
              }
            }
            v44 = (**(__int64 (__fastcall ***)(CallStackTracing *))v42)(v42);
            if ( v44 )
              v38 = (CallStackContext *)v44;
          }
          SetLastError(LastError);
          if ( *((_DWORD *)v38 + 499) != v13 )
            CallStackContext::TraceFailure(v38, "CMFReadWriteTransformFactory::EnumTransformsByLuid", 568, v13);
        }
        if ( g_wppLevels )
        {
          v24 = 46;
          goto LABEL_66;
        }
      }
    }
    else
    {
      v26 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v25, v11);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = (CallStackTracing *)((char *)v26 + 208);
        v29 = GetLastError();
        v30 = (CallStackContext *)TlsGetValue(*((_DWORD *)v26 + 3));
        if ( v30 )
        {
          v28 = v30;
        }
        else if ( !GetLastError() )
        {
          v32 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
            CallStackTracing::s_wpInstance = v33;
            if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              v32 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v32 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v34 = (**(__int64 (__fastcall ***)(CallStackTracing *))v32)(v32);
          if ( v34 )
            v28 = (CallStackContext *)v34;
        }
        SetLastError(v29);
        if ( *((_DWORD *)v28 + 499) != v13 )
          CallStackContext::TraceFailure(v28, "CMFReadWriteTransformFactory::EnumTransformsByLuid", 565, v13);
      }
      if ( g_wppLevels )
      {
        v24 = 45;
        goto LABEL_66;
      }
    }
  }
  else
  {
    v15 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v14, v11);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = (CallStackTracing *)&qword_18010C230;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = (CallStackTracing *)((char *)v15 + 208);
      v18 = GetLastError();
      v19 = (CallStackContext *)TlsGetValue(*((_DWORD *)v15 + 3));
      if ( v19 )
      {
        v17 = v19;
      }
      else if ( !GetLastError() )
      {
        v21 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v23 = (**(__int64 (__fastcall ***)(CallStackTracing *))v21)(v21);
        if ( v23 )
          v17 = (CallStackContext *)v23;
      }
      SetLastError(v18);
      if ( *((_DWORD *)v17 + 499) != v13 )
        CallStackContext::TraceFailure(v17, "CMFReadWriteTransformFactory::EnumTransformsByLuid", 564, v13);
    }
    if ( g_wppLevels )
    {
      v24 = 44;
LABEL_66:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids, this, v13);
    }
  }
LABEL_67:
  if ( (unsigned __int8)byte_18010CAF1 >= 0x10u )
    WPP_SF_qdiD(*((_QWORD *)WPP_GLOBAL_Control + 7), v11, v12, this, *a7, v48[0], v13);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFAttributes);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v46);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800d7614  push    rbp
0x1800d7616  push    rbx
0x1800d7617  push    rsi
0x1800d7618  push    rdi
0x1800d7619  push    r12
0x1800d761b  push    r13
0x1800d761d  push    r14
0x1800d761f  push    r15
0x1800d7621  mov     rbp, rsp
0x1800d7624  sub     rsp, 78h
0x1800d7628  mov     esi, r8d
0x1800d762b  mov     r14, rdx
0x1800d762e  mov     r12, rcx
0x1800d7631  lea     rdx, aCmfreadwritetr_54; "CMFReadWriteTransformFactory::EnumTrans"...
0x1800d7638  mov     r8d, 221h; int
0x1800d763e  lea     rcx, [rbp+var_38]; this
0x1800d7642  mov     rdi, r9
0x1800d7645  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800d764a  mov     r13, [rbp+arg_30]
0x1800d764e  lea     rdx, [rbp+var_28]; unsigned __int64 *
0x1800d7652  xor     r15d, r15d
0x1800d7655  mov     rcx, r12; this
0x1800d7658  mov     [rbp+ppMFAttributes], r15
0x1800d765c  mov     [rbp+var_28], r15
0x1800d7660  mov     [r13+0], r15d
0x1800d7664  call    ?GetD3DDeviceLUID@CMFReadWriteTransformFactory@@AEAAJPEA_K@Z; CMFReadWriteTransformFactory::GetD3DDeviceLUID(unsigned __int64 *)
0x1800d7669  test    eax, eax
0x1800d766b  jz      short loc_1800D7675
0x1800d766d  mov     ebx, r15d
0x1800d7670  jmp     loc_1800D7A7D
0x1800d7675  mov     edx, 1; cInitialSize
0x1800d767a  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x1800d767e  call    cs:__imp_MFCreateAttributes
0x1800d7684  mov     ebx, eax
0x1800d7686  test    eax, eax
0x1800d7688  jns     loc_1800D77B3
0x1800d768e  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7695  mov     r14d, 7F0h
0x1800d769b  test    rdi, rdi
0x1800d769e  jnz     short loc_1800D76DF
0x1800d76a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d76a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d76ad  mov     rcx, rax
0x1800d76b0  test    rax, rax
0x1800d76b3  jz      short loc_1800D76D1
0x1800d76b5  mov     rax, [rax]
0x1800d76b8  mov     edx, r14d
0x1800d76bb  mov     rax, [rax+8]
0x1800d76bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d76c4  test    eax, eax
0x1800d76c6  jz      short loc_1800D76D1
0x1800d76c8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d76cf  jmp     short loc_1800D76DF
0x1800d76d1  lea     rdi, qword_18010C230
0x1800d76d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d76df  cmp     [rdi+8], r15b
0x1800d76e3  jz      loc_1800D779C
0x1800d76e9  lea     rsi, [rdi+0D0h]
0x1800d76f0  call    cs:__imp_GetLastError
0x1800d76f6  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800d76f9  mov     r15d, eax
0x1800d76fc  call    cs:__imp_TlsGetValue
0x1800d7702  test    rax, rax
0x1800d7705  jz      short loc_1800D770C
0x1800d7707  mov     rsi, rax
0x1800d770a  jmp     short loc_1800D7773
0x1800d770c  call    cs:__imp_GetLastError
0x1800d7712  test    eax, eax
0x1800d7714  jnz     short loc_1800D7773
0x1800d7716  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d771d  test    rcx, rcx
0x1800d7720  jnz     short loc_1800D7761
0x1800d7722  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d7728  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d772f  mov     rcx, rax
0x1800d7732  test    rax, rax
0x1800d7735  jz      short loc_1800D7753
0x1800d7737  mov     rax, [rax]
0x1800d773a  mov     edx, r14d
0x1800d773d  mov     rax, [rax+8]
0x1800d7741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7746  test    eax, eax
0x1800d7748  jz      short loc_1800D7753
0x1800d774a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7751  jmp     short loc_1800D7761
0x1800d7753  lea     rcx, qword_18010C230
0x1800d775a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7761  mov     rax, [rcx]
0x1800d7764  mov     rax, [rax]
0x1800d7767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d776c  test    rax, rax
0x1800d776f  cmovnz  rsi, rax
0x1800d7773  mov     ecx, r15d; dwErrCode
0x1800d7776  call    cs:__imp_SetLastError
0x1800d777c  cmp     [rsi+7CCh], ebx
0x1800d7782  jz      short loc_1800D779C
0x1800d7784  mov     r9d, ebx; int
0x1800d7787  lea     rdx, aCmfreadwritetr_54; "CMFReadWriteTransformFactory::EnumTrans"...
0x1800d778e  mov     r8d, 234h; int
0x1800d7794  mov     rcx, rsi; this
0x1800d7797  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d779c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d77a3  jb      loc_1800D7A7D
0x1800d77a9  mov     edx, 2Ch ; ','
0x1800d77ae  jmp     loc_1800D7A5F
0x1800d77b3  mov     rcx, [rbp+ppMFAttributes]
0x1800d77b7  lea     r8, [rbp+var_28]
0x1800d77bb  mov     r9d, 8
0x1800d77c1  lea     rdx, MFT_ENUM_ADAPTER_LUID
0x1800d77c8  mov     rax, [rcx]
0x1800d77cb  mov     rax, [rax+0D0h]
0x1800d77d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d77d7  mov     ebx, eax
0x1800d77d9  test    eax, eax
0x1800d77db  jns     loc_1800D7906
0x1800d77e1  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d77e8  mov     r14d, 7F0h
0x1800d77ee  test    rdi, rdi
0x1800d77f1  jnz     short loc_1800D7832
0x1800d77f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d77f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7800  mov     rcx, rax
0x1800d7803  test    rax, rax
0x1800d7806  jz      short loc_1800D7824
0x1800d7808  mov     rax, [rax]
0x1800d780b  mov     edx, r14d
0x1800d780e  mov     rax, [rax+8]
0x1800d7812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7817  test    eax, eax
0x1800d7819  jz      short loc_1800D7824
0x1800d781b  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7822  jmp     short loc_1800D7832
0x1800d7824  lea     rdi, qword_18010C230
0x1800d782b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7832  cmp     [rdi+8], r15b
0x1800d7836  jz      loc_1800D78EF
0x1800d783c  lea     rsi, [rdi+0D0h]
0x1800d7843  call    cs:__imp_GetLastError
0x1800d7849  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800d784c  mov     r15d, eax
0x1800d784f  call    cs:__imp_TlsGetValue
0x1800d7855  test    rax, rax
0x1800d7858  jz      short loc_1800D785F
0x1800d785a  mov     rsi, rax
0x1800d785d  jmp     short loc_1800D78C6
0x1800d785f  call    cs:__imp_GetLastError
0x1800d7865  test    eax, eax
0x1800d7867  jnz     short loc_1800D78C6
0x1800d7869  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7870  test    rcx, rcx
0x1800d7873  jnz     short loc_1800D78B4
0x1800d7875  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d787b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7882  mov     rcx, rax
0x1800d7885  test    rax, rax
0x1800d7888  jz      short loc_1800D78A6
0x1800d788a  mov     rax, [rax]
0x1800d788d  mov     edx, r14d
0x1800d7890  mov     rax, [rax+8]
0x1800d7894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7899  test    eax, eax
0x1800d789b  jz      short loc_1800D78A6
0x1800d789d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d78a4  jmp     short loc_1800D78B4
0x1800d78a6  lea     rcx, qword_18010C230
0x1800d78ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d78b4  mov     rax, [rcx]
0x1800d78b7  mov     rax, [rax]
0x1800d78ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d78bf  test    rax, rax
0x1800d78c2  cmovnz  rsi, rax
0x1800d78c6  mov     ecx, r15d; dwErrCode
0x1800d78c9  call    cs:__imp_SetLastError
0x1800d78cf  cmp     [rsi+7CCh], ebx
0x1800d78d5  jz      short loc_1800D78EF
0x1800d78d7  mov     r9d, ebx; int
0x1800d78da  lea     rdx, aCmfreadwritetr_54; "CMFReadWriteTransformFactory::EnumTrans"...
0x1800d78e1  mov     r8d, 235h; int
0x1800d78e7  mov     rcx, rsi; this
0x1800d78ea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d78ef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d78f6  jb      loc_1800D7A7D
0x1800d78fc  mov     edx, 2Dh ; '-'
0x1800d7901  jmp     loc_1800D7A5F
0x1800d7906  mov     rcx, [rbp+ppMFAttributes]
0x1800d790a  mov     r8, rdi
0x1800d790d  mov     rax, [rbp+arg_28]
0x1800d7911  mov     edx, esi
0x1800d7913  movaps  xmm0, xmmword ptr [r14]
0x1800d7917  mov     r9, [rbp+arg_20]
0x1800d791b  mov     [rsp+78h+var_48], r13
0x1800d7920  mov     [rsp+78h+var_50], rax
0x1800d7925  mov     [rsp+78h+var_58], rcx
0x1800d792a  lea     rcx, [rbp+var_18]
0x1800d792e  movdqa  [rbp+var_18], xmm0
0x1800d7933  call    cs:__imp_MFTEnum2
0x1800d7939  mov     ebx, eax
0x1800d793b  test    eax, eax
0x1800d793d  jns     loc_1800D7A7D
0x1800d7943  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d794a  mov     r14d, 7F0h
0x1800d7950  test    rdi, rdi
0x1800d7953  jnz     short loc_1800D7994
0x1800d7955  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d795b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7962  mov     rcx, rax
0x1800d7965  test    rax, rax
0x1800d7968  jz      short loc_1800D7986
0x1800d796a  mov     rax, [rax]
0x1800d796d  mov     edx, r14d
0x1800d7970  mov     rax, [rax+8]
0x1800d7974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7979  test    eax, eax
0x1800d797b  jz      short loc_1800D7986
0x1800d797d  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7984  jmp     short loc_1800D7994
0x1800d7986  lea     rdi, qword_18010C230
0x1800d798d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7994  cmp     [rdi+8], r15b
0x1800d7998  jz      loc_1800D7A51
0x1800d799e  lea     rsi, [rdi+0D0h]
0x1800d79a5  call    cs:__imp_GetLastError
0x1800d79ab  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800d79ae  mov     r15d, eax
0x1800d79b1  call    cs:__imp_TlsGetValue
0x1800d79b7  test    rax, rax
0x1800d79ba  jz      short loc_1800D79C1
0x1800d79bc  mov     rsi, rax
0x1800d79bf  jmp     short loc_1800D7A28
0x1800d79c1  call    cs:__imp_GetLastError
0x1800d79c7  test    eax, eax
0x1800d79c9  jnz     short loc_1800D7A28
0x1800d79cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d79d2  test    rcx, rcx
0x1800d79d5  jnz     short loc_1800D7A16
0x1800d79d7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d79dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d79e4  mov     rcx, rax
0x1800d79e7  test    rax, rax
0x1800d79ea  jz      short loc_1800D7A08
0x1800d79ec  mov     rax, [rax]
0x1800d79ef  mov     edx, r14d
0x1800d79f2  mov     rax, [rax+8]
0x1800d79f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d79fb  test    eax, eax
0x1800d79fd  jz      short loc_1800D7A08
0x1800d79ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7a06  jmp     short loc_1800D7A16
0x1800d7a08  lea     rcx, qword_18010C230
0x1800d7a0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7a16  mov     rax, [rcx]
0x1800d7a19  mov     rax, [rax]
0x1800d7a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7a21  test    rax, rax
0x1800d7a24  cmovnz  rsi, rax
0x1800d7a28  mov     ecx, r15d; dwErrCode
0x1800d7a2b  call    cs:__imp_SetLastError
0x1800d7a31  cmp     [rsi+7CCh], ebx
0x1800d7a37  jz      short loc_1800D7A51
0x1800d7a39  mov     r9d, ebx; int
0x1800d7a3c  lea     rdx, aCmfreadwritetr_54; "CMFReadWriteTransformFactory::EnumTrans"...
0x1800d7a43  mov     r8d, 238h; int
0x1800d7a49  mov     rcx, rsi; this
0x1800d7a4c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d7a51  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d7a58  jb      short loc_1800D7A7D
0x1800d7a5a  mov     edx, 2Eh ; '.'
0x1800d7a5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7a66  lea     r8, WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids
0x1800d7a6d  mov     r9, r12
0x1800d7a70  mov     dword ptr [rsp+78h+var_58], ebx
0x1800d7a74  mov     rcx, [rcx+10h]
0x1800d7a78  call    WPP_SF_qD
0x1800d7a7d  cmp     cs:byte_18010CAF1, 10h
0x1800d7a84  jb      short loc_1800D7AAE
0x1800d7a86  mov     rax, [rbp+var_28]
0x1800d7a8a  mov     r9, r12
0x1800d7a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7a94  mov     dword ptr [rsp+78h+var_48], ebx
0x1800d7a98  mov     [rsp+78h+var_50], rax
0x1800d7a9d  mov     eax, [r13+0]
0x1800d7aa1  mov     rcx, [rcx+38h]
0x1800d7aa5  mov     dword ptr [rsp+78h+var_58], eax
0x1800d7aa9  call    WPP_SF_qdiD
0x1800d7aae  lea     rcx, [rbp+ppMFAttributes]
0x1800d7ab2  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800d7ab7  lea     rcx, [rbp+var_38]; this
0x1800d7abb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800d7ac0  mov     eax, ebx
0x1800d7ac2  add     rsp, 78h
0x1800d7ac6  pop     r15
0x1800d7ac8  pop     r14
0x1800d7aca  pop     r13
0x1800d7acc  pop     r12
0x1800d7ace  pop     rdi
0x1800d7acf  pop     rsi
0x1800d7ad0  pop     rbx
0x1800d7ad1  pop     rbp
0x1800d7ad2  retn
```
