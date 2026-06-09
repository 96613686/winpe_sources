# RendererEffectWrapper::CheckOutputTypeSupported(IMFMediaType *)

- ea: `0x1800b3710`
- end: `0x1800b3a96`
- name: `?CheckOutputTypeSupported@RendererEffectWrapper@@QEAAJPEAUIMFMediaType@@@Z`
- size: `902`
- prototype: `__int64 __fastcall(RendererEffectWrapper *__hidden this, struct IMFMediaType *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18005e9c0`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180066a98`
- `0x1800b3710`
- `0x1800b3a9c`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800b375f`
- `MFPlat!MFCreateMediaType` at `0x1800b375f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3782`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b382d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b38ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b39b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3782`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b382d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b38ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b39b1`

## pseudocode

```c
__int64 __fastcall RendererEffectWrapper::CheckOutputTypeSupported(
        RendererEffectWrapper *this,
        struct IMFMediaType *a2)
{
  HRESULT v4; // ebx
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, struct IMFMediaType **); // rbx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFMediaType *v21[2]; // [rsp+30h] [rbp-10h] BYREF
  char v22; // [rsp+80h] [rbp+40h] BYREF
  IMFMediaType *ppMFType; // [rsp+88h] [rbp+48h] BYREF

  ppMFType = 0;
  v21[0] = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v22,
    "RendererEffectWrapper::CheckOutputTypeSupported",
    532);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
  v4 = MFCreateMediaType(&ppMFType);
  if ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))a2->lpVtbl->CopyAllItems)(a2, ppMFType);
    if ( v4 >= 0 )
    {
      v12 = *((_QWORD *)this + 19);
      v13 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IMFMediaType **))(*(_QWORD *)v12 + 136LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
      v4 = v13(v12, 0, v21);
      if ( v4 >= 0 )
      {
        CopyScalingAttributes(v21[0], ppMFType);
        v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, IMFMediaType *, __int64))(**((_QWORD **)this + 19) + 128LL))(
               *((_QWORD *)this + 19),
               0,
               ppMFType,
               1);
        if ( v4 < 0 )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v18;
            if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
            {
              v17 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v17 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v17 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "RendererEffectWrapper::CheckOutputTypeSupported",
                536,
                v4);
          }
          if ( g_wppLevels )
          {
            v8 = 56;
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
          if ( *((_DWORD *)v16 + 499) != v4 )
            CallStackContext::TraceFailure(v16, "RendererEffectWrapper::CheckOutputTypeSupported", 534, v4);
        }
        if ( g_wppLevels )
        {
          v8 = 55;
          goto LABEL_45;
        }
      }
    }
    else
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)v11 + 499) != v4 )
          CallStackContext::TraceFailure(v11, "RendererEffectWrapper::CheckOutputTypeSupported", 533, v4);
      }
      if ( g_wppLevels )
      {
        v8 = 54;
        goto LABEL_45;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v7 + 499) != v4 )
        CallStackContext::TraceFailure(v7, "RendererEffectWrapper::CheckOutputTypeSupported", 532, v4);
    }
    if ( g_wppLevels )
    {
      v8 = 53;
LABEL_45:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids, this, v4);
    }
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      57,
      &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
      (unsigned int)v4);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800b3710  mov     [rsp-28h+arg_0], rbx
0x1800b3715  push    rbp
0x1800b3716  push    rsi
0x1800b3717  push    rdi
0x1800b3718  push    r12
0x1800b371a  push    r15
0x1800b371c  mov     rbp, rsp
0x1800b371f  sub     rsp, 40h
0x1800b3723  mov     rdi, rdx
0x1800b3726  mov     [rbp+ppMFType], 0
0x1800b372e  mov     rsi, rcx
0x1800b3731  mov     [rbp+var_10], 0
0x1800b3739  lea     r12, aRenderereffect_10; "RendererEffectWrapper::CheckOutputTypeS"...
0x1800b3740  mov     r8d, 214h; int
0x1800b3746  mov     rdx, r12; char *
0x1800b3749  lea     rcx, [rbp+arg_10]; this
0x1800b374d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b3752  lea     rcx, [rbp+ppMFType]
0x1800b3756  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b375b  lea     rcx, [rbp+ppMFType]; ppMFType
0x1800b375f  call    cs:__imp_MFCreateMediaType
0x1800b3765  lea     r15, WPP_e7b63f7618733801a471ab74d0df161d_Traceguids
0x1800b376c  mov     ebx, eax
0x1800b376e  test    eax, eax
0x1800b3770  jns     loc_1800B3801
0x1800b3776  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b377d  test    rcx, rcx
0x1800b3780  jnz     short loc_1800B37C3
0x1800b3782  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b3788  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b378f  mov     rcx, rax
0x1800b3792  test    rax, rax
0x1800b3795  jz      short loc_1800B37B5
0x1800b3797  mov     rax, [rax]
0x1800b379a  mov     edx, 7F0h
0x1800b379f  mov     rax, [rax+8]
0x1800b37a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b37a8  test    eax, eax
0x1800b37aa  jz      short loc_1800B37B5
0x1800b37ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b37b3  jmp     short loc_1800B37C3
0x1800b37b5  lea     rcx, qword_180153440; this
0x1800b37bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b37c3  cmp     byte ptr [rcx+8], 0
0x1800b37c7  jz      short loc_1800B37EA
0x1800b37c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b37ce  cmp     [rax+7CCh], ebx
0x1800b37d4  jz      short loc_1800B37EA
0x1800b37d6  mov     r9d, ebx; int
0x1800b37d9  mov     r8d, 214h; int
0x1800b37df  mov     rdx, r12; char *
0x1800b37e2  mov     rcx, rax; this
0x1800b37e5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b37ea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b37f1  jb      loc_1800B3A41
0x1800b37f7  mov     edx, 35h ; '5'
0x1800b37fc  jmp     loc_1800B3A27
0x1800b3801  mov     rax, [rdi]
0x1800b3804  mov     rcx, rdi
0x1800b3807  mov     rdx, [rbp+ppMFType]
0x1800b380b  mov     rax, [rax+100h]
0x1800b3812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3817  mov     ebx, eax
0x1800b3819  test    eax, eax
0x1800b381b  jns     loc_1800B38AC
0x1800b3821  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3828  test    rcx, rcx
0x1800b382b  jnz     short loc_1800B386E
0x1800b382d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b3833  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b383a  mov     rcx, rax
0x1800b383d  test    rax, rax
0x1800b3840  jz      short loc_1800B3860
0x1800b3842  mov     rax, [rax]
0x1800b3845  mov     edx, 7F0h
0x1800b384a  mov     rax, [rax+8]
0x1800b384e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3853  test    eax, eax
0x1800b3855  jz      short loc_1800B3860
0x1800b3857  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b385e  jmp     short loc_1800B386E
0x1800b3860  lea     rcx, qword_180153440; this
0x1800b3867  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b386e  cmp     byte ptr [rcx+8], 0
0x1800b3872  jz      short loc_1800B3895
0x1800b3874  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b3879  cmp     [rax+7CCh], ebx
0x1800b387f  jz      short loc_1800B3895
0x1800b3881  mov     r9d, ebx; int
0x1800b3884  mov     r8d, 215h; int
0x1800b388a  mov     rdx, r12; char *
0x1800b388d  mov     rcx, rax; this
0x1800b3890  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b3895  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b389c  jb      loc_1800B3A41
0x1800b38a2  mov     edx, 36h ; '6'
0x1800b38a7  jmp     loc_1800B3A27
0x1800b38ac  mov     rdi, [rsi+98h]
0x1800b38b3  lea     rcx, [rbp+var_10]
0x1800b38b7  mov     rax, [rdi]
0x1800b38ba  mov     rbx, [rax+88h]
0x1800b38c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b38c6  lea     r8, [rbp+var_10]
0x1800b38ca  xor     edx, edx
0x1800b38cc  mov     rcx, rdi
0x1800b38cf  mov     rax, rbx
0x1800b38d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b38d7  mov     ebx, eax
0x1800b38d9  test    eax, eax
0x1800b38db  jns     loc_1800B396C
0x1800b38e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b38e8  test    rcx, rcx
0x1800b38eb  jnz     short loc_1800B392E
0x1800b38ed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b38f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b38fa  mov     rcx, rax
0x1800b38fd  test    rax, rax
0x1800b3900  jz      short loc_1800B3920
0x1800b3902  mov     rax, [rax]
0x1800b3905  mov     edx, 7F0h
0x1800b390a  mov     rax, [rax+8]
0x1800b390e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3913  test    eax, eax
0x1800b3915  jz      short loc_1800B3920
0x1800b3917  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b391e  jmp     short loc_1800B392E
0x1800b3920  lea     rcx, qword_180153440; this
0x1800b3927  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b392e  cmp     byte ptr [rcx+8], 0
0x1800b3932  jz      short loc_1800B3955
0x1800b3934  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b3939  cmp     [rax+7CCh], ebx
0x1800b393f  jz      short loc_1800B3955
0x1800b3941  mov     r9d, ebx; int
0x1800b3944  mov     r8d, 216h; int
0x1800b394a  mov     rdx, r12; char *
0x1800b394d  mov     rcx, rax; this
0x1800b3950  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b3955  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b395c  jb      loc_1800B3A41
0x1800b3962  mov     edx, 37h ; '7'
0x1800b3967  jmp     loc_1800B3A27
0x1800b396c  mov     rdx, [rbp+ppMFType]; struct IMFMediaType *
0x1800b3970  mov     rcx, [rbp+var_10]; struct IMFMediaType *
0x1800b3974  call    ?CopyScalingAttributes@@YAJPEAUIMFMediaType@@0@Z; CopyScalingAttributes(IMFMediaType *,IMFMediaType *)
0x1800b3979  mov     rcx, [rsi+98h]
0x1800b3980  mov     r9d, 1
0x1800b3986  mov     r8, [rbp+ppMFType]
0x1800b398a  xor     edx, edx
0x1800b398c  mov     rax, [rcx]
0x1800b398f  mov     rax, [rax+80h]
0x1800b3996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b399b  mov     ebx, eax
0x1800b399d  test    eax, eax
0x1800b399f  jns     loc_1800B3A41
0x1800b39a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b39ac  test    rcx, rcx
0x1800b39af  jnz     short loc_1800B39F2
0x1800b39b1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b39b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b39be  mov     rcx, rax
0x1800b39c1  test    rax, rax
0x1800b39c4  jz      short loc_1800B39E4
0x1800b39c6  mov     rax, [rax]
0x1800b39c9  mov     edx, 7F0h
0x1800b39ce  mov     rax, [rax+8]
0x1800b39d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b39d7  test    eax, eax
0x1800b39d9  jz      short loc_1800B39E4
0x1800b39db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b39e2  jmp     short loc_1800B39F2
0x1800b39e4  lea     rcx, qword_180153440; this
0x1800b39eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b39f2  cmp     byte ptr [rcx+8], 0
0x1800b39f6  jz      short loc_1800B3A19
0x1800b39f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b39fd  cmp     [rax+7CCh], ebx
0x1800b3a03  jz      short loc_1800B3A19
0x1800b3a05  mov     r9d, ebx; int
0x1800b3a08  mov     r8d, 218h; int
0x1800b3a0e  mov     rdx, r12; char *
0x1800b3a11  mov     rcx, rax; this
0x1800b3a14  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b3a19  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3a20  jb      short loc_1800B3A41
0x1800b3a22  mov     edx, 38h ; '8'
0x1800b3a27  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3a2e  mov     r9, rsi
0x1800b3a31  mov     r8, r15
0x1800b3a34  mov     [rsp+40h+var_20], ebx
0x1800b3a38  mov     rcx, [rcx+10h]
0x1800b3a3c  call    WPP_SF_qD
0x1800b3a41  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800b3a48  jb      short loc_1800B3A68
0x1800b3a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3a51  mov     edx, 39h ; '9'
0x1800b3a56  mov     r9d, ebx
0x1800b3a59  mov     r8, r15
0x1800b3a5c  mov     rcx, [rcx+150h]
0x1800b3a63  call    WPP_SF_d
0x1800b3a68  lea     rcx, [rbp+arg_10]; this
0x1800b3a6c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b3a71  lea     rcx, [rbp+var_10]
0x1800b3a75  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b3a7a  lea     rcx, [rbp+ppMFType]
0x1800b3a7e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b3a83  mov     eax, ebx
0x1800b3a85  mov     rbx, [rsp+40h+arg_0]
0x1800b3a8a  add     rsp, 40h
0x1800b3a8e  pop     r15
0x1800b3a90  pop     r12
0x1800b3a92  pop     rdi
0x1800b3a93  pop     rsi
0x1800b3a94  pop     rbp
0x1800b3a95  retn
```
