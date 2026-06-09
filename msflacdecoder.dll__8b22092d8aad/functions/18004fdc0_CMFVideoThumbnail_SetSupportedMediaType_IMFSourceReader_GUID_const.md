# CMFVideoThumbnail::SetSupportedMediaType(IMFSourceReader *,_GUID const &)

- ea: `0x18004fdc0`
- end: `0x180050183`
- name: `?SetSupportedMediaType@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@AEBU_GUID@@@Z`
- size: `963`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFSourceReader *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18004cc48`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180048710`
- `0x18004fdc0`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18004fe83`
- `MFPlat!MFCreateMediaType` at `0x18004fe83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fe9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ff56`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050009`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800500b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fe9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ff56`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050009`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800500b8`

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
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  _BYTE v28[8]; // [rsp+30h] [rbp-58h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v30[16]; // [rsp+40h] [rbp-48h] BYREF

  ppMFType = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v28, "CMFVideoThumbnail::SetSupportedMediaType", 1978);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                      *((_QWORD *)this + 50),
                      v30);
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
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
            CallStackTracing::s_wpInstance = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
            if ( *((_DWORD *)v26 + 499) != v10 )
              CallStackContext::TraceFailure(v26, "CMFVideoThumbnail::SetSupportedMediaType", 1987, v10);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v14 = 206;
            goto LABEL_48;
          }
        }
      }
      else
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( *((_DWORD *)v22 + 499) != v10 )
            CallStackContext::TraceFailure(v22, "CMFVideoThumbnail::SetSupportedMediaType", 1981, v10);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v14 = 205;
          goto LABEL_48;
        }
      }
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != v10 )
          CallStackContext::TraceFailure(v18, "CMFVideoThumbnail::SetSupportedMediaType", 1980, v10);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 204;
        goto LABEL_48;
      }
    }
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != v10 )
        CallStackContext::TraceFailure(v13, "CMFVideoThumbnail::SetSupportedMediaType", 1978, v10);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 203;
LABEL_48:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v10);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004fdc0  mov     [rsp+arg_18], rbx
0x18004fdc5  push    rbp
0x18004fdc6  push    rsi
0x18004fdc7  push    rdi
0x18004fdc8  push    r12
0x18004fdca  push    r14
0x18004fdcc  sub     rsp, 60h
0x18004fdd0  mov     rax, cs:__security_cookie
0x18004fdd7  xor     rax, rsp
0x18004fdda  mov     [rsp+88h+var_38], rax
0x18004fddf  mov     rbp, r8
0x18004fde2  mov     [rsp+88h+ppMFType], 0
0x18004fdeb  mov     r14, rdx
0x18004fdee  lea     r12, aCmfvideothumbn_13; "CMFVideoThumbnail::SetSupportedMediaTyp"...
0x18004fdf5  mov     rsi, rcx
0x18004fdf8  mov     rdx, r12; char *
0x18004fdfb  mov     r8d, 7BAh; int
0x18004fe01  lea     rcx, [rsp+88h+var_58]; this
0x18004fe06  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004fe0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004fe12  cmp     byte ptr [rcx+8], 0
0x18004fe16  jz      short loc_18004FE74
0x18004fe18  cmp     qword ptr [rsi+190h], 0
0x18004fe20  jz      short loc_18004FE74
0x18004fe22  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fe27  mov     rdx, [rsi+190h]
0x18004fe2e  mov     rdi, rax
0x18004fe31  mov     rcx, [rdx]
0x18004fe34  mov     rax, [rcx+128h]
0x18004fe3b  mov     rcx, rdx
0x18004fe3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe43  mov     r8, [rsi+190h]
0x18004fe4a  lea     rdx, [rsp+88h+var_48]
0x18004fe4f  mov     ebx, eax
0x18004fe51  mov     rcx, [r8]
0x18004fe54  mov     rax, [rcx+118h]
0x18004fe5b  mov     rcx, r8
0x18004fe5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe63  movups  xmm0, xmmword ptr [rax]
0x18004fe66  mov     [rdi+7E0h], ebx
0x18004fe6c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004fe74  lea     rcx, [rsp+88h+ppMFType]
0x18004fe79  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fe7e  lea     rcx, [rsp+88h+ppMFType]; ppMFType
0x18004fe83  call    cs:__imp_MFCreateMediaType
0x18004fe89  mov     ebx, eax
0x18004fe8b  test    eax, eax
0x18004fe8d  jns     loc_18004FF1E
0x18004fe93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fe9a  test    rcx, rcx
0x18004fe9d  jnz     short loc_18004FEE0
0x18004fe9f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fea5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004feac  mov     rcx, rax
0x18004feaf  test    rax, rax
0x18004feb2  jz      short loc_18004FED2
0x18004feb4  mov     rax, [rax]
0x18004feb7  mov     edx, 7F0h
0x18004febc  mov     rax, [rax+8]
0x18004fec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fec5  test    eax, eax
0x18004fec7  jz      short loc_18004FED2
0x18004fec9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fed0  jmp     short loc_18004FEE0
0x18004fed2  lea     rcx, qword_18006EB20; this
0x18004fed9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fee0  cmp     byte ptr [rcx+8], 0
0x18004fee4  jz      short loc_18004FF07
0x18004fee6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004feeb  cmp     [rax+7CCh], ebx
0x18004fef1  jz      short loc_18004FF07
0x18004fef3  mov     r9d, ebx; int
0x18004fef6  mov     r8d, 7BAh; int
0x18004fefc  mov     rdx, r12; char *
0x18004feff  mov     rcx, rax; this
0x18004ff02  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ff07  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004ff0c  cmp     al, 1
0x18004ff0e  jb      loc_18005014C
0x18004ff14  mov     edx, 0CBh
0x18004ff19  jmp     loc_18005012E
0x18004ff1e  mov     rcx, [rsp+88h+ppMFType]
0x18004ff23  lea     r8, MFMediaType_Video
0x18004ff2a  lea     rdx, MF_MT_MAJOR_TYPE
0x18004ff31  mov     rax, [rcx]
0x18004ff34  mov     rax, [rax+0C0h]
0x18004ff3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff40  mov     ebx, eax
0x18004ff42  test    eax, eax
0x18004ff44  jns     loc_18004FFD5
0x18004ff4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff51  test    rcx, rcx
0x18004ff54  jnz     short loc_18004FF97
0x18004ff56  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ff5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff63  mov     rcx, rax
0x18004ff66  test    rax, rax
0x18004ff69  jz      short loc_18004FF89
0x18004ff6b  mov     rax, [rax]
0x18004ff6e  mov     edx, 7F0h
0x18004ff73  mov     rax, [rax+8]
0x18004ff77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff7c  test    eax, eax
0x18004ff7e  jz      short loc_18004FF89
0x18004ff80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff87  jmp     short loc_18004FF97
0x18004ff89  lea     rcx, qword_18006EB20; this
0x18004ff90  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff97  cmp     byte ptr [rcx+8], 0
0x18004ff9b  jz      short loc_18004FFBE
0x18004ff9d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ffa2  cmp     [rax+7CCh], ebx
0x18004ffa8  jz      short loc_18004FFBE
0x18004ffaa  mov     r9d, ebx; int
0x18004ffad  mov     r8d, 7BCh; int
0x18004ffb3  mov     rdx, r12; char *
0x18004ffb6  mov     rcx, rax; this
0x18004ffb9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ffbe  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004ffc3  cmp     al, 1
0x18004ffc5  jb      loc_18005014C
0x18004ffcb  mov     edx, 0CCh
0x18004ffd0  jmp     loc_18005012E
0x18004ffd5  mov     rcx, [rsp+88h+ppMFType]
0x18004ffda  lea     rdx, MF_MT_SUBTYPE
0x18004ffe1  mov     r8, rbp
0x18004ffe4  mov     rax, [rcx]
0x18004ffe7  mov     rax, [rax+0C0h]
0x18004ffee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fff3  mov     ebx, eax
0x18004fff5  test    eax, eax
0x18004fff7  jns     loc_180050088
0x18004fffd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050004  test    rcx, rcx
0x180050007  jnz     short loc_18005004A
0x180050009  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005000f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050016  mov     rcx, rax
0x180050019  test    rax, rax
0x18005001c  jz      short loc_18005003C
0x18005001e  mov     rax, [rax]
0x180050021  mov     edx, 7F0h
0x180050026  mov     rax, [rax+8]
0x18005002a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005002f  test    eax, eax
0x180050031  jz      short loc_18005003C
0x180050033  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005003a  jmp     short loc_18005004A
0x18005003c  lea     rcx, qword_18006EB20; this
0x180050043  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005004a  cmp     byte ptr [rcx+8], 0
0x18005004e  jz      short loc_180050071
0x180050050  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050055  cmp     [rax+7CCh], ebx
0x18005005b  jz      short loc_180050071
0x18005005d  mov     r9d, ebx; int
0x180050060  mov     r8d, 7BDh; int
0x180050066  mov     rdx, r12; char *
0x180050069  mov     rcx, rax; this
0x18005006c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050071  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050076  cmp     al, 1
0x180050078  jb      loc_18005014C
0x18005007e  mov     edx, 0CDh
0x180050083  jmp     loc_18005012E
0x180050088  mov     rax, [r14]
0x18005008b  xor     r8d, r8d
0x18005008e  mov     r9, [rsp+88h+ppMFType]
0x180050093  mov     rcx, r14
0x180050096  mov     edx, [rsi+18h]
0x180050099  mov     rax, [rax+38h]
0x18005009d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500a2  mov     ebx, eax
0x1800500a4  test    eax, eax
0x1800500a6  jns     loc_18005014C
0x1800500ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800500b3  test    rcx, rcx
0x1800500b6  jnz     short loc_1800500F9
0x1800500b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800500be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800500c5  mov     rcx, rax
0x1800500c8  test    rax, rax
0x1800500cb  jz      short loc_1800500EB
0x1800500cd  mov     rax, [rax]
0x1800500d0  mov     edx, 7F0h
0x1800500d5  mov     rax, [rax+8]
0x1800500d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500de  test    eax, eax
0x1800500e0  jz      short loc_1800500EB
0x1800500e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800500e9  jmp     short loc_1800500F9
0x1800500eb  lea     rcx, qword_18006EB20; this
0x1800500f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800500f9  cmp     byte ptr [rcx+8], 0
0x1800500fd  jz      short loc_180050120
0x1800500ff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050104  cmp     [rax+7CCh], ebx
0x18005010a  jz      short loc_180050120
0x18005010c  mov     r9d, ebx; int
0x18005010f  mov     r8d, 7C3h; int
0x180050115  mov     rdx, r12; char *
0x180050118  mov     rcx, rax; this
0x18005011b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050120  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050125  cmp     al, 1
0x180050127  jb      short loc_18005014C
0x180050129  mov     edx, 0CEh
0x18005012e  mov     rcx, cs:WPP_GLOBAL_Control
0x180050135  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18005013c  mov     r9, rsi
0x18005013f  mov     [rsp+88h+var_68], ebx
0x180050143  mov     rcx, [rcx+10h]
0x180050147  call    WPP_SF_qd
0x18005014c  lea     rcx, [rsp+88h+var_58]; this
0x180050151  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180050156  lea     rcx, [rsp+88h+ppMFType]
0x18005015b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050160  mov     eax, ebx
0x180050162  mov     rcx, [rsp+88h+var_38]
0x180050167  xor     rcx, rsp; StackCookie
0x18005016a  call    __security_check_cookie
0x18005016f  mov     rbx, [rsp+88h+arg_18]
0x180050177  add     rsp, 60h
0x18005017b  pop     r14
0x18005017d  pop     r12
0x18005017f  pop     rdi
0x180050180  pop     rsi
0x180050181  pop     rbp
0x180050182  retn
```
