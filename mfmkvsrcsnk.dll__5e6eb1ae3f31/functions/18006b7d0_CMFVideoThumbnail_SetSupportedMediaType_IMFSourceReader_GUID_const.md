# CMFVideoThumbnail::SetSupportedMediaType(IMFSourceReader *,_GUID const &)

- ea: `0x18006b7d0`
- end: `0x18006bb93`
- name: `?SetSupportedMediaType@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@AEBU_GUID@@@Z`
- size: `963`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFSourceReader *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006860c`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18006b7d0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006b8af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006b966`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ba19`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006bac8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006b8af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006b966`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ba19`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006bac8`
- `MFPlat!MFCreateMediaType` at `0x18006b893`
- `MFPlat!MFCreateMediaType` at `0x18006b893`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::SetSupportedMediaType(
        CMFVideoThumbnail *this,
        struct IMFSourceReader *a2,
        const struct _GUID *a3)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v7; // ebx
  __int128 v8; // xmm0
  __int64 v9; // rdx
  HRESULT v10; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  _BYTE v36[8]; // [rsp+30h] [rbp-58h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v38[16]; // [rsp+40h] [rbp-48h] BYREF

  ppMFType = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v36, "CMFVideoThumbnail::SetSupportedMediaType", 1978);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                      *((_QWORD *)this + 50),
                      v38);
    *((_DWORD *)ThreadRelativeContext + 504) = v7;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
  v10 = MFCreateMediaType(&ppMFType);
  if ( v10 >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
            ppMFType,
            &MF_MT_MAJOR_TYPE,
            &MFMediaType_Video);
    if ( v10 >= 0 )
    {
      v10 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const struct _GUID *))ppMFType->lpVtbl->SetGUID)(
              ppMFType,
              &MF_MT_SUBTYPE,
              a3);
      if ( v10 >= 0 )
      {
        v10 = ((__int64 (__fastcall *)(struct IMFSourceReader *, _QWORD, _QWORD, IMFMediaType *))a2->lpVtbl->SetCurrentMediaType)(
                a2,
                *((unsigned int *)this + 6),
                0,
                ppMFType);
        if ( v10 < 0 )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
            CallStackTracing::s_wpInstance = v33;
            if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              v32 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v32 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v32 + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
            if ( *((_DWORD *)v34 + 499) != v10 )
              CallStackContext::TraceFailure(v34, "CMFVideoThumbnail::SetSupportedMediaType", 1987, v10);
          }
          if ( g_wppLevels )
          {
            v16 = 206;
            goto LABEL_48;
          }
        }
      }
      else
      {
        v26 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
          CallStackTracing::s_wpInstance = v27;
          if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
          {
            v26 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v26 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v26 + 8) )
        {
          v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
          if ( *((_DWORD *)v28 + 499) != v10 )
            CallStackContext::TraceFailure(v28, "CMFVideoThumbnail::SetSupportedMediaType", 1981, v10);
        }
        if ( g_wppLevels )
        {
          v16 = 205;
          goto LABEL_48;
        }
      }
    }
    else
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != v10 )
          CallStackContext::TraceFailure(v22, "CMFVideoThumbnail::SetSupportedMediaType", 1980, v10);
      }
      if ( g_wppLevels )
      {
        v16 = 204;
        goto LABEL_48;
      }
    }
  }
  else
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v11, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != v10 )
        CallStackContext::TraceFailure(v15, "CMFVideoThumbnail::SetSupportedMediaType", 1978, v10);
    }
    if ( g_wppLevels )
    {
      v16 = 203;
LABEL_48:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v10);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v36);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18006b7d0  mov     [rsp+arg_18], rbx
0x18006b7d5  push    rbp
0x18006b7d6  push    rsi
0x18006b7d7  push    rdi
0x18006b7d8  push    r12
0x18006b7da  push    r14
0x18006b7dc  sub     rsp, 60h
0x18006b7e0  mov     rax, cs:__security_cookie
0x18006b7e7  xor     rax, rsp
0x18006b7ea  mov     [rsp+88h+var_38], rax
0x18006b7ef  mov     rbp, r8
0x18006b7f2  mov     [rsp+88h+ppMFType], 0
0x18006b7fb  mov     r14, rdx
0x18006b7fe  lea     r12, aCmfvideothumbn_13; "CMFVideoThumbnail::SetSupportedMediaTyp"...
0x18006b805  mov     rsi, rcx
0x18006b808  mov     rdx, r12; char *
0x18006b80b  mov     r8d, 7BAh; int
0x18006b811  lea     rcx, [rsp+88h+var_58]; this
0x18006b816  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006b81b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006b822  cmp     byte ptr [rcx+8], 0
0x18006b826  jz      short loc_18006B884
0x18006b828  cmp     qword ptr [rsi+190h], 0
0x18006b830  jz      short loc_18006B884
0x18006b832  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006b837  mov     rdx, [rsi+190h]
0x18006b83e  mov     rdi, rax
0x18006b841  mov     rcx, [rdx]
0x18006b844  mov     rax, [rcx+128h]
0x18006b84b  mov     rcx, rdx
0x18006b84e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b853  mov     r8, [rsi+190h]
0x18006b85a  lea     rdx, [rsp+88h+var_48]
0x18006b85f  mov     ebx, eax
0x18006b861  mov     rcx, [r8]
0x18006b864  mov     rax, [rcx+118h]
0x18006b86b  mov     rcx, r8
0x18006b86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b873  movups  xmm0, xmmword ptr [rax]
0x18006b876  mov     [rdi+7E0h], ebx
0x18006b87c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006b884  lea     rcx, [rsp+88h+ppMFType]
0x18006b889  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006b88e  lea     rcx, [rsp+88h+ppMFType]; ppMFType
0x18006b893  call    cs:__imp_MFCreateMediaType
0x18006b899  mov     ebx, eax
0x18006b89b  test    eax, eax
0x18006b89d  jns     loc_18006B92E
0x18006b8a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b8aa  test    rcx, rcx
0x18006b8ad  jnz     short loc_18006B8F0
0x18006b8af  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006b8b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b8bc  mov     rcx, rax
0x18006b8bf  test    rax, rax
0x18006b8c2  jz      short loc_18006B8E2
0x18006b8c4  mov     rax, [rax]
0x18006b8c7  mov     edx, 7F0h
0x18006b8cc  mov     rax, [rax+8]
0x18006b8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b8d5  test    eax, eax
0x18006b8d7  jz      short loc_18006B8E2
0x18006b8d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b8e0  jmp     short loc_18006B8F0
0x18006b8e2  lea     rcx, qword_1800D6F70; this
0x18006b8e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b8f0  cmp     byte ptr [rcx+8], 0
0x18006b8f4  jz      short loc_18006B917
0x18006b8f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006b8fb  cmp     [rax+7CCh], ebx
0x18006b901  jz      short loc_18006B917
0x18006b903  mov     r9d, ebx; int
0x18006b906  mov     r8d, 7BAh; int
0x18006b90c  mov     rdx, r12; char *
0x18006b90f  mov     rcx, rax; this
0x18006b912  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006b917  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006b91e  jb      loc_18006BB5C
0x18006b924  mov     edx, 0CBh
0x18006b929  jmp     loc_18006BB3E
0x18006b92e  mov     rcx, [rsp+88h+ppMFType]
0x18006b933  lea     r8, MFMediaType_Video
0x18006b93a  lea     rdx, MF_MT_MAJOR_TYPE
0x18006b941  mov     rax, [rcx]
0x18006b944  mov     rax, [rax+0C0h]
0x18006b94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b950  mov     ebx, eax
0x18006b952  test    eax, eax
0x18006b954  jns     loc_18006B9E5
0x18006b95a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b961  test    rcx, rcx
0x18006b964  jnz     short loc_18006B9A7
0x18006b966  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006b96c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b973  mov     rcx, rax
0x18006b976  test    rax, rax
0x18006b979  jz      short loc_18006B999
0x18006b97b  mov     rax, [rax]
0x18006b97e  mov     edx, 7F0h
0x18006b983  mov     rax, [rax+8]
0x18006b987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b98c  test    eax, eax
0x18006b98e  jz      short loc_18006B999
0x18006b990  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b997  jmp     short loc_18006B9A7
0x18006b999  lea     rcx, qword_1800D6F70; this
0x18006b9a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b9a7  cmp     byte ptr [rcx+8], 0
0x18006b9ab  jz      short loc_18006B9CE
0x18006b9ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006b9b2  cmp     [rax+7CCh], ebx
0x18006b9b8  jz      short loc_18006B9CE
0x18006b9ba  mov     r9d, ebx; int
0x18006b9bd  mov     r8d, 7BCh; int
0x18006b9c3  mov     rdx, r12; char *
0x18006b9c6  mov     rcx, rax; this
0x18006b9c9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006b9ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006b9d5  jb      loc_18006BB5C
0x18006b9db  mov     edx, 0CCh
0x18006b9e0  jmp     loc_18006BB3E
0x18006b9e5  mov     rcx, [rsp+88h+ppMFType]
0x18006b9ea  lea     rdx, MF_MT_SUBTYPE
0x18006b9f1  mov     r8, rbp
0x18006b9f4  mov     rax, [rcx]
0x18006b9f7  mov     rax, [rax+0C0h]
0x18006b9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba03  mov     ebx, eax
0x18006ba05  test    eax, eax
0x18006ba07  jns     loc_18006BA98
0x18006ba0d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ba14  test    rcx, rcx
0x18006ba17  jnz     short loc_18006BA5A
0x18006ba19  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ba1f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ba26  mov     rcx, rax
0x18006ba29  test    rax, rax
0x18006ba2c  jz      short loc_18006BA4C
0x18006ba2e  mov     rax, [rax]
0x18006ba31  mov     edx, 7F0h
0x18006ba36  mov     rax, [rax+8]
0x18006ba3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba3f  test    eax, eax
0x18006ba41  jz      short loc_18006BA4C
0x18006ba43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ba4a  jmp     short loc_18006BA5A
0x18006ba4c  lea     rcx, qword_1800D6F70; this
0x18006ba53  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ba5a  cmp     byte ptr [rcx+8], 0
0x18006ba5e  jz      short loc_18006BA81
0x18006ba60  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006ba65  cmp     [rax+7CCh], ebx
0x18006ba6b  jz      short loc_18006BA81
0x18006ba6d  mov     r9d, ebx; int
0x18006ba70  mov     r8d, 7BDh; int
0x18006ba76  mov     rdx, r12; char *
0x18006ba79  mov     rcx, rax; this
0x18006ba7c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006ba81  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ba88  jb      loc_18006BB5C
0x18006ba8e  mov     edx, 0CDh
0x18006ba93  jmp     loc_18006BB3E
0x18006ba98  mov     rax, [r14]
0x18006ba9b  xor     r8d, r8d
0x18006ba9e  mov     r9, [rsp+88h+ppMFType]
0x18006baa3  mov     rcx, r14
0x18006baa6  mov     edx, [rsi+18h]
0x18006baa9  mov     rax, [rax+38h]
0x18006baad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bab2  mov     ebx, eax
0x18006bab4  test    eax, eax
0x18006bab6  jns     loc_18006BB5C
0x18006babc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bac3  test    rcx, rcx
0x18006bac6  jnz     short loc_18006BB09
0x18006bac8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006bace  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bad5  mov     rcx, rax
0x18006bad8  test    rax, rax
0x18006badb  jz      short loc_18006BAFB
0x18006badd  mov     rax, [rax]
0x18006bae0  mov     edx, 7F0h
0x18006bae5  mov     rax, [rax+8]
0x18006bae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006baee  test    eax, eax
0x18006baf0  jz      short loc_18006BAFB
0x18006baf2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006baf9  jmp     short loc_18006BB09
0x18006bafb  lea     rcx, qword_1800D6F70; this
0x18006bb02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006bb09  cmp     byte ptr [rcx+8], 0
0x18006bb0d  jz      short loc_18006BB30
0x18006bb0f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006bb14  cmp     [rax+7CCh], ebx
0x18006bb1a  jz      short loc_18006BB30
0x18006bb1c  mov     r9d, ebx; int
0x18006bb1f  mov     r8d, 7C3h; int
0x18006bb25  mov     rdx, r12; char *
0x18006bb28  mov     rcx, rax; this
0x18006bb2b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006bb30  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006bb37  jb      short loc_18006BB5C
0x18006bb39  mov     edx, 0CEh
0x18006bb3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bb45  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18006bb4c  mov     r9, rsi
0x18006bb4f  mov     [rsp+88h+var_68], ebx
0x18006bb53  mov     rcx, [rcx+10h]
0x18006bb57  call    WPP_SF_qD
0x18006bb5c  lea     rcx, [rsp+88h+var_58]; this
0x18006bb61  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006bb66  lea     rcx, [rsp+88h+ppMFType]
0x18006bb6b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006bb70  mov     eax, ebx
0x18006bb72  mov     rcx, [rsp+88h+var_38]
0x18006bb77  xor     rcx, rsp; StackCookie
0x18006bb7a  call    __security_check_cookie
0x18006bb7f  mov     rbx, [rsp+88h+arg_18]
0x18006bb87  add     rsp, 60h
0x18006bb8b  pop     r14
0x18006bb8d  pop     r12
0x18006bb8f  pop     rdi
0x18006bb90  pop     rsi
0x18006bb91  pop     rbp
0x18006bb92  retn
```
