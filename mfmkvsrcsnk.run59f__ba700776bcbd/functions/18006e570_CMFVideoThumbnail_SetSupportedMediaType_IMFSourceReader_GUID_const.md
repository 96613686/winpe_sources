# CMFVideoThumbnail::SetSupportedMediaType(IMFSourceReader *,_GUID const &)

- ea: `0x18006e570`
- end: `0x18006e952`
- name: `?SetSupportedMediaType@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@AEBU_GUID@@@Z`
- size: `994`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFSourceReader *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006b2cc`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18006e570`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e655`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e712`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e7cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e880`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e655`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e712`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e7cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e880`
- `MFPlat!MFCreateMediaType` at `0x18006e633`
- `MFPlat!MFCreateMediaType` at `0x18006e633`

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
              v32 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v26 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v20 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v13 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18006e570  mov     [rsp+arg_18], rbx
0x18006e575  push    rbp
0x18006e576  push    rsi
0x18006e577  push    rdi
0x18006e578  push    r12
0x18006e57a  push    r14
0x18006e57c  sub     rsp, 60h
0x18006e580  mov     rax, cs:__security_cookie
0x18006e587  xor     rax, rsp
0x18006e58a  mov     [rsp+88h+var_38], rax
0x18006e58f  mov     rbp, r8
0x18006e592  mov     [rsp+88h+ppMFType], 0
0x18006e59b  mov     r14, rdx
0x18006e59e  lea     r12, aCmfvideothumbn_13; "CMFVideoThumbnail::SetSupportedMediaTyp"...
0x18006e5a5  mov     rsi, rcx
0x18006e5a8  mov     rdx, r12; char *
0x18006e5ab  mov     r8d, 7BAh; int
0x18006e5b1  lea     rcx, [rsp+88h+var_58]; this
0x18006e5b6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006e5bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006e5c2  cmp     byte ptr [rcx+8], 0
0x18006e5c6  jz      short loc_18006E624
0x18006e5c8  cmp     qword ptr [rsi+190h], 0
0x18006e5d0  jz      short loc_18006E624
0x18006e5d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e5d7  mov     rdx, [rsi+190h]
0x18006e5de  mov     rdi, rax
0x18006e5e1  mov     rcx, [rdx]
0x18006e5e4  mov     rax, [rcx+128h]
0x18006e5eb  mov     rcx, rdx
0x18006e5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5f3  mov     r8, [rsi+190h]
0x18006e5fa  lea     rdx, [rsp+88h+var_48]
0x18006e5ff  mov     ebx, eax
0x18006e601  mov     rcx, [r8]
0x18006e604  mov     rax, [rcx+118h]
0x18006e60b  mov     rcx, r8
0x18006e60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e613  movups  xmm0, xmmword ptr [rax]
0x18006e616  mov     [rdi+7E0h], ebx
0x18006e61c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006e624  lea     rcx, [rsp+88h+ppMFType]
0x18006e629  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e62e  lea     rcx, [rsp+88h+ppMFType]; ppMFType
0x18006e633  call    cs:__imp_MFCreateMediaType
0x18006e63a  nop     dword ptr [rax+rax+00h]
0x18006e63f  mov     ebx, eax
0x18006e641  test    eax, eax
0x18006e643  jns     loc_18006E6DA
0x18006e649  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e650  test    rcx, rcx
0x18006e653  jnz     short loc_18006E69C
0x18006e655  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e65c  nop     dword ptr [rax+rax+00h]
0x18006e661  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e668  mov     rcx, rax
0x18006e66b  test    rax, rax
0x18006e66e  jz      short loc_18006E68E
0x18006e670  mov     rax, [rax]
0x18006e673  mov     edx, 7F0h
0x18006e678  mov     rax, [rax+8]
0x18006e67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e681  test    eax, eax
0x18006e683  jz      short loc_18006E68E
0x18006e685  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e68c  jmp     short loc_18006E69C
0x18006e68e  lea     rcx, qword_1800DBF70; this
0x18006e695  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e69c  cmp     byte ptr [rcx+8], 0
0x18006e6a0  jz      short loc_18006E6C3
0x18006e6a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e6a7  cmp     [rax+7CCh], ebx
0x18006e6ad  jz      short loc_18006E6C3
0x18006e6af  mov     r9d, ebx; int
0x18006e6b2  mov     r8d, 7BAh; int
0x18006e6b8  mov     rdx, r12; char *
0x18006e6bb  mov     rcx, rax; this
0x18006e6be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e6c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e6ca  jb      loc_18006E91A
0x18006e6d0  mov     edx, 0CBh
0x18006e6d5  jmp     loc_18006E8FC
0x18006e6da  mov     rcx, [rsp+88h+ppMFType]
0x18006e6df  lea     r8, MFMediaType_Video
0x18006e6e6  lea     rdx, MF_MT_MAJOR_TYPE
0x18006e6ed  mov     rax, [rcx]
0x18006e6f0  mov     rax, [rax+0C0h]
0x18006e6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e6fc  mov     ebx, eax
0x18006e6fe  test    eax, eax
0x18006e700  jns     loc_18006E797
0x18006e706  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e70d  test    rcx, rcx
0x18006e710  jnz     short loc_18006E759
0x18006e712  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e719  nop     dword ptr [rax+rax+00h]
0x18006e71e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e725  mov     rcx, rax
0x18006e728  test    rax, rax
0x18006e72b  jz      short loc_18006E74B
0x18006e72d  mov     rax, [rax]
0x18006e730  mov     edx, 7F0h
0x18006e735  mov     rax, [rax+8]
0x18006e739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e73e  test    eax, eax
0x18006e740  jz      short loc_18006E74B
0x18006e742  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e749  jmp     short loc_18006E759
0x18006e74b  lea     rcx, qword_1800DBF70; this
0x18006e752  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e759  cmp     byte ptr [rcx+8], 0
0x18006e75d  jz      short loc_18006E780
0x18006e75f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e764  cmp     [rax+7CCh], ebx
0x18006e76a  jz      short loc_18006E780
0x18006e76c  mov     r9d, ebx; int
0x18006e76f  mov     r8d, 7BCh; int
0x18006e775  mov     rdx, r12; char *
0x18006e778  mov     rcx, rax; this
0x18006e77b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e780  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e787  jb      loc_18006E91A
0x18006e78d  mov     edx, 0CCh
0x18006e792  jmp     loc_18006E8FC
0x18006e797  mov     rcx, [rsp+88h+ppMFType]
0x18006e79c  lea     rdx, MF_MT_SUBTYPE
0x18006e7a3  mov     r8, rbp
0x18006e7a6  mov     rax, [rcx]
0x18006e7a9  mov     rax, [rax+0C0h]
0x18006e7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e7b5  mov     ebx, eax
0x18006e7b7  test    eax, eax
0x18006e7b9  jns     loc_18006E850
0x18006e7bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e7c6  test    rcx, rcx
0x18006e7c9  jnz     short loc_18006E812
0x18006e7cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e7d2  nop     dword ptr [rax+rax+00h]
0x18006e7d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e7de  mov     rcx, rax
0x18006e7e1  test    rax, rax
0x18006e7e4  jz      short loc_18006E804
0x18006e7e6  mov     rax, [rax]
0x18006e7e9  mov     edx, 7F0h
0x18006e7ee  mov     rax, [rax+8]
0x18006e7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e7f7  test    eax, eax
0x18006e7f9  jz      short loc_18006E804
0x18006e7fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e802  jmp     short loc_18006E812
0x18006e804  lea     rcx, qword_1800DBF70; this
0x18006e80b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e812  cmp     byte ptr [rcx+8], 0
0x18006e816  jz      short loc_18006E839
0x18006e818  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e81d  cmp     [rax+7CCh], ebx
0x18006e823  jz      short loc_18006E839
0x18006e825  mov     r9d, ebx; int
0x18006e828  mov     r8d, 7BDh; int
0x18006e82e  mov     rdx, r12; char *
0x18006e831  mov     rcx, rax; this
0x18006e834  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e839  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e840  jb      loc_18006E91A
0x18006e846  mov     edx, 0CDh
0x18006e84b  jmp     loc_18006E8FC
0x18006e850  mov     rax, [r14]
0x18006e853  xor     r8d, r8d
0x18006e856  mov     r9, [rsp+88h+ppMFType]
0x18006e85b  mov     rcx, r14
0x18006e85e  mov     edx, [rsi+18h]
0x18006e861  mov     rax, [rax+38h]
0x18006e865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e86a  mov     ebx, eax
0x18006e86c  test    eax, eax
0x18006e86e  jns     loc_18006E91A
0x18006e874  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e87b  test    rcx, rcx
0x18006e87e  jnz     short loc_18006E8C7
0x18006e880  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e887  nop     dword ptr [rax+rax+00h]
0x18006e88c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e893  mov     rcx, rax
0x18006e896  test    rax, rax
0x18006e899  jz      short loc_18006E8B9
0x18006e89b  mov     rax, [rax]
0x18006e89e  mov     edx, 7F0h
0x18006e8a3  mov     rax, [rax+8]
0x18006e8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e8ac  test    eax, eax
0x18006e8ae  jz      short loc_18006E8B9
0x18006e8b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e8b7  jmp     short loc_18006E8C7
0x18006e8b9  lea     rcx, qword_1800DBF70; this
0x18006e8c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e8c7  cmp     byte ptr [rcx+8], 0
0x18006e8cb  jz      short loc_18006E8EE
0x18006e8cd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e8d2  cmp     [rax+7CCh], ebx
0x18006e8d8  jz      short loc_18006E8EE
0x18006e8da  mov     r9d, ebx; int
0x18006e8dd  mov     r8d, 7C3h; int
0x18006e8e3  mov     rdx, r12; char *
0x18006e8e6  mov     rcx, rax; this
0x18006e8e9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e8ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e8f5  jb      short loc_18006E91A
0x18006e8f7  mov     edx, 0CEh
0x18006e8fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e903  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18006e90a  mov     r9, rsi
0x18006e90d  mov     [rsp+88h+var_68], ebx
0x18006e911  mov     rcx, [rcx+10h]
0x18006e915  call    WPP_SF_qD
0x18006e91a  lea     rcx, [rsp+88h+var_58]; this
0x18006e91f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006e924  lea     rcx, [rsp+88h+ppMFType]
0x18006e929  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e92e  mov     eax, ebx
0x18006e930  mov     rcx, [rsp+88h+var_38]
0x18006e935  xor     rcx, rsp; StackCookie
0x18006e938  call    __security_check_cookie
0x18006e93d  mov     rbx, [rsp+88h+arg_18]
0x18006e945  add     rsp, 60h
0x18006e949  pop     r14
0x18006e94b  pop     r12
0x18006e94d  pop     rdi
0x18006e94e  pop     rsi
0x18006e94f  pop     rbp
0x18006e950  retn
```
