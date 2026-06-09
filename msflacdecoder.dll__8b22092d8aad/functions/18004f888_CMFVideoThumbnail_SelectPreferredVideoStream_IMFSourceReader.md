# CMFVideoThumbnail::SelectPreferredVideoStream(IMFSourceReader *)

- ea: `0x18004f888`
- end: `0x18004fdb8`
- name: `?SelectPreferredVideoStream@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@@Z`
- size: `1328`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFSourceReader *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18004cc48`

## callees

- `0x180001e80`
- `0x180016b18`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180048710`
- `0x18004f888`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fa52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fae1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fb70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fc39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fd07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fa52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fae1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fb70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fc39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fd07`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::SelectPreferredVideoStream(CMFVideoThumbnail *this, struct IMFSourceReader *a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int128 v6; // xmm0
  unsigned int v7; // edi
  unsigned int v8; // r14d
  int v9; // r12d
  unsigned int v10; // r13d
  struct IMFSourceReaderVtbl *lpVtbl; // rax
  int v12; // eax
  __int64 v13; // rdx
  int v14; // ebx
  HRESULT (__stdcall *GetNativeMediaType)(IMFSourceReader *, DWORD, DWORD, IMFMediaType **); // rbx
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v18; // ecx
  unsigned int v19; // eax
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  _BYTE v40[4]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v41; // [rsp+34h] [rbp-2Ch] BYREF
  _QWORD v42[2]; // [rsp+38h] [rbp-28h] BYREF
  GUID Buf2; // [rsp+48h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v40,
    "CMFVideoThumbnail::SelectPreferredVideoStream",
    1873);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v6 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 50) + 280LL))(
                      *((_QWORD *)this + 50),
                      v42);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
    *((_OWORD *)ThreadRelativeContext + 125) = v6;
  }
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v41 = 0;
  Buf2 = GUID_00000000_0000_0000_0000_000000000000;
  v10 = 0;
  while ( 1 )
  {
    lpVtbl = a2->lpVtbl;
    v42[0] = 0;
    v12 = ((__int64 (__fastcall *)(struct IMFSourceReader *, _QWORD, _QWORD))lpVtbl->SetStreamSelection)(a2, v8, 0);
    v14 = v12;
    if ( v12 == -1072875853 )
      break;
    if ( v12 < 0 )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != v14 )
          CallStackContext::TraceFailure(v29, "CMFVideoThumbnail::SelectPreferredVideoStream", 1905, v14);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_50;
      v23 = 198;
LABEL_49:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v14);
      goto LABEL_50;
    }
    GetNativeMediaType = a2->lpVtbl->GetNativeMediaType;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v42);
    v14 = ((__int64 (__fastcall *)(struct IMFSourceReader *, _QWORD, _QWORD, _QWORD *))GetNativeMediaType)(
            a2,
            v8,
            0,
            v42);
    if ( v14 < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
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
        if ( *((_DWORD *)v26 + 499) != v14 )
          CallStackContext::TraceFailure(v26, "CMFVideoThumbnail::SelectPreferredVideoStream", 1911, v14);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_50;
      v23 = 199;
      goto LABEL_49;
    }
    v14 = (*(__int64 (__fastcall **)(_QWORD, const GUID *, GUID *))(*(_QWORD *)v42[0] + 80LL))(
            v42[0],
            &MF_MT_MAJOR_TYPE,
            &Buf2);
    if ( v14 < 0 )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
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
        if ( *((_DWORD *)v22 + 499) != v14 )
          CallStackContext::TraceFailure(v22, "CMFVideoThumbnail::SelectPreferredVideoStream", 1913, v14);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v23 = 200;
        goto LABEL_49;
      }
LABEL_50:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v42);
      goto LABEL_75;
    }
    if ( memcmp_0(&MFMediaType_Video, &Buf2, 0x10u) )
      goto LABEL_16;
    v18 = v9;
    v19 = v8;
    if ( !v9 )
      v9 = 1;
    if ( v18 )
      v19 = v7;
    v7 = v19;
    if ( (*(int (__fastcall **)(_QWORD, const GUID *, unsigned int *))(*(_QWORD *)v42[0] + 56LL))(
           v42[0],
           &MF_MT_AVG_BITRATE,
           &v41) < 0 )
    {
      v41 = 0;
    }
    else
    {
LABEL_16:
      if ( v41 > v10 )
      {
        v10 = v41;
        v7 = v8;
      }
    }
    ++v8;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v42);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v42);
  if ( v9 )
  {
    v14 = ((__int64 (__fastcall *)(struct IMFSourceReader *, _QWORD, __int64))a2->lpVtbl->SetStreamSelection)(a2, v7, 1);
    if ( v14 >= 0 )
    {
      *((_DWORD *)this + 6) = v7;
      goto LABEL_75;
    }
    v36 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
      CallStackTracing::s_wpInstance = v37;
      if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
      {
        v36 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v36 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v36 + 8) )
    {
      v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
      if ( *((_DWORD *)v38 + 499) != v14 )
        CallStackContext::TraceFailure(v38, "CMFVideoThumbnail::SelectPreferredVideoStream", 1961, v14);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v34 = 202;
      goto LABEL_62;
    }
  }
  else
  {
    v31 = (__int64 *)CallStackTracing::s_wpInstance;
    v14 = -1072875819;
    if ( !CallStackTracing::s_wpInstance )
    {
      v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
      CallStackTracing::s_wpInstance = v32;
      if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
      {
        v31 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v31 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v31 + 8) )
    {
      v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
      if ( *((_DWORD *)v33 + 499) != -1072875819 )
        CallStackContext::TraceFailure(v33, "CMFVideoThumbnail::SelectPreferredVideoStream", 1953, -1072875819);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v34 = 201;
LABEL_62:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v14);
    }
  }
LABEL_75:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v40);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18004f888  mov     [rsp-38h+arg_10], rbx
0x18004f88d  push    rbp
0x18004f88e  push    rsi
0x18004f88f  push    rdi
0x18004f890  push    r12
0x18004f892  push    r13
0x18004f894  push    r14
0x18004f896  push    r15
0x18004f898  mov     rbp, rsp
0x18004f89b  sub     rsp, 60h
0x18004f89f  mov     rax, cs:__security_cookie
0x18004f8a6  xor     rax, rsp
0x18004f8a9  mov     [rbp+var_8], rax
0x18004f8ad  mov     r15, rdx
0x18004f8b0  mov     rsi, rcx
0x18004f8b3  lea     rdx, aCmfvideothumbn_16; "CMFVideoThumbnail::SelectPreferredVideo"...
0x18004f8ba  mov     r8d, 751h; int
0x18004f8c0  lea     rcx, [rbp+var_30]; this
0x18004f8c4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004f8c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004f8d0  cmp     byte ptr [rcx+8], 0
0x18004f8d4  jz      short loc_18004F931
0x18004f8d6  cmp     qword ptr [rsi+190h], 0
0x18004f8de  jz      short loc_18004F931
0x18004f8e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004f8e5  mov     rdx, [rsi+190h]
0x18004f8ec  mov     rdi, rax
0x18004f8ef  mov     rcx, [rdx]
0x18004f8f2  mov     rax, [rcx+128h]
0x18004f8f9  mov     rcx, rdx
0x18004f8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f901  mov     r8, [rsi+190h]
0x18004f908  lea     rdx, [rbp+var_28]
0x18004f90c  mov     ebx, eax
0x18004f90e  mov     rcx, [r8]
0x18004f911  mov     rax, [rcx+118h]
0x18004f918  mov     rcx, r8
0x18004f91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f920  movups  xmm0, xmmword ptr [rax]
0x18004f923  mov     [rdi+7E0h], ebx
0x18004f929  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004f931  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004f938  xor     edi, edi
0x18004f93a  xor     r14d, r14d
0x18004f93d  xor     r12d, r12d
0x18004f940  mov     [rbp+var_2C], edi
0x18004f943  movdqu  [rbp+Buf2], xmm0
0x18004f948  xor     r13d, r13d
0x18004f94b  mov     rax, [r15]
0x18004f94e  xor     r8d, r8d
0x18004f951  mov     edx, r14d
0x18004f954  mov     [rbp+var_28], 0
0x18004f95c  mov     rcx, r15
0x18004f95f  mov     rax, [rax+20h]
0x18004f963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f968  mov     ebx, eax
0x18004f96a  cmp     eax, 0C00D36B3h
0x18004f96f  jz      loc_18004FC16
0x18004f975  test    eax, eax
0x18004f977  js      loc_18004FB64
0x18004f97d  mov     rax, [r15]
0x18004f980  lea     rcx, [rbp+var_28]
0x18004f984  mov     rbx, [rax+28h]
0x18004f988  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f98d  lea     r9, [rbp+var_28]
0x18004f991  xor     r8d, r8d
0x18004f994  mov     edx, r14d
0x18004f997  mov     rcx, r15
0x18004f99a  mov     rax, rbx
0x18004f99d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f9a2  mov     ebx, eax
0x18004f9a4  test    eax, eax
0x18004f9a6  js      loc_18004FAD5
0x18004f9ac  mov     rcx, [rbp+var_28]
0x18004f9b0  lea     r8, [rbp+Buf2]
0x18004f9b4  lea     rdx, MF_MT_MAJOR_TYPE
0x18004f9bb  mov     rax, [rcx]
0x18004f9be  mov     rax, [rax+50h]
0x18004f9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f9c7  mov     ebx, eax
0x18004f9c9  test    eax, eax
0x18004f9cb  js      short loc_18004FA46
0x18004f9cd  mov     r8d, 10h; Size
0x18004f9d3  lea     rdx, [rbp+Buf2]; Buf2
0x18004f9d7  lea     rcx, MFMediaType_Video; Buf1
0x18004f9de  call    memcmp_0
0x18004f9e3  mov     ebx, 1
0x18004f9e8  test    eax, eax
0x18004f9ea  jnz     short loc_18004FA28
0x18004f9ec  mov     ecx, r12d
0x18004f9ef  lea     r8, [rbp+var_2C]
0x18004f9f3  test    r12d, r12d
0x18004f9f6  lea     rdx, MF_MT_AVG_BITRATE
0x18004f9fd  mov     eax, r14d
0x18004fa00  cmovz   r12d, ebx
0x18004fa04  test    ecx, ecx
0x18004fa06  mov     rcx, [rbp+var_28]
0x18004fa0a  cmovnz  eax, edi
0x18004fa0d  mov     edi, eax
0x18004fa0f  mov     rax, [rcx]
0x18004fa12  mov     rax, [rax+38h]
0x18004fa16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa1b  test    eax, eax
0x18004fa1d  jns     short loc_18004FA28
0x18004fa1f  mov     [rbp+var_2C], 0
0x18004fa26  jmp     short loc_18004FA35
0x18004fa28  cmp     [rbp+var_2C], r13d
0x18004fa2c  jbe     short loc_18004FA35
0x18004fa2e  mov     r13d, [rbp+var_2C]
0x18004fa32  mov     edi, r14d
0x18004fa35  add     r14d, ebx
0x18004fa38  lea     rcx, [rbp+var_28]
0x18004fa3c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fa41  jmp     loc_18004F94B
0x18004fa46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fa4d  test    rcx, rcx
0x18004fa50  jnz     short loc_18004FA93
0x18004fa52  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fa58  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fa5f  mov     rcx, rax
0x18004fa62  test    rax, rax
0x18004fa65  jz      short loc_18004FA85
0x18004fa67  mov     rax, [rax]
0x18004fa6a  mov     edx, 7F0h
0x18004fa6f  mov     rax, [rax+8]
0x18004fa73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa78  test    eax, eax
0x18004fa7a  jz      short loc_18004FA85
0x18004fa7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fa83  jmp     short loc_18004FA93
0x18004fa85  lea     rcx, qword_18006EB20; this
0x18004fa8c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fa93  cmp     byte ptr [rcx+8], 0
0x18004fa97  jz      short loc_18004FABE
0x18004fa99  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fa9e  cmp     [rax+7CCh], ebx
0x18004faa4  jz      short loc_18004FABE
0x18004faa6  mov     r9d, ebx; int
0x18004faa9  lea     rdx, aCmfvideothumbn_16; "CMFVideoThumbnail::SelectPreferredVideo"...
0x18004fab0  mov     r8d, 779h; int
0x18004fab6  mov     rcx, rax; this
0x18004fab9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004fabe  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004fac3  cmp     al, 1
0x18004fac5  jb      loc_18004FC08
0x18004facb  mov     edx, 0C8h
0x18004fad0  jmp     loc_18004FBEA
0x18004fad5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fadc  test    rcx, rcx
0x18004fadf  jnz     short loc_18004FB22
0x18004fae1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fae7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004faee  mov     rcx, rax
0x18004faf1  test    rax, rax
0x18004faf4  jz      short loc_18004FB14
0x18004faf6  mov     rax, [rax]
0x18004faf9  mov     edx, 7F0h
0x18004fafe  mov     rax, [rax+8]
0x18004fb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb07  test    eax, eax
0x18004fb09  jz      short loc_18004FB14
0x18004fb0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fb12  jmp     short loc_18004FB22
0x18004fb14  lea     rcx, qword_18006EB20; this
0x18004fb1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fb22  cmp     byte ptr [rcx+8], 0
0x18004fb26  jz      short loc_18004FB4D
0x18004fb28  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fb2d  cmp     [rax+7CCh], ebx
0x18004fb33  jz      short loc_18004FB4D
0x18004fb35  mov     r9d, ebx; int
0x18004fb38  lea     rdx, aCmfvideothumbn_16; "CMFVideoThumbnail::SelectPreferredVideo"...
0x18004fb3f  mov     r8d, 777h; int
0x18004fb45  mov     rcx, rax; this
0x18004fb48  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004fb4d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004fb52  cmp     al, 1
0x18004fb54  jb      loc_18004FC08
0x18004fb5a  mov     edx, 0C7h
0x18004fb5f  jmp     loc_18004FBEA
0x18004fb64  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fb6b  test    rcx, rcx
0x18004fb6e  jnz     short loc_18004FBB1
0x18004fb70  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fb76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fb7d  mov     rcx, rax
0x18004fb80  test    rax, rax
0x18004fb83  jz      short loc_18004FBA3
0x18004fb85  mov     rax, [rax]
0x18004fb88  mov     edx, 7F0h
0x18004fb8d  mov     rax, [rax+8]
0x18004fb91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb96  test    eax, eax
0x18004fb98  jz      short loc_18004FBA3
0x18004fb9a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fba1  jmp     short loc_18004FBB1
0x18004fba3  lea     rcx, qword_18006EB20; this
0x18004fbaa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fbb1  cmp     byte ptr [rcx+8], 0
0x18004fbb5  jz      short loc_18004FBDC
0x18004fbb7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fbbc  cmp     [rax+7CCh], ebx
0x18004fbc2  jz      short loc_18004FBDC
0x18004fbc4  mov     r9d, ebx; int
0x18004fbc7  lea     rdx, aCmfvideothumbn_16; "CMFVideoThumbnail::SelectPreferredVideo"...
0x18004fbce  mov     r8d, 771h; int
0x18004fbd4  mov     rcx, rax; this
0x18004fbd7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004fbdc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004fbe1  cmp     al, 1
0x18004fbe3  jb      short loc_18004FC08
0x18004fbe5  mov     edx, 0C6h
0x18004fbea  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fbf1  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004fbf8  mov     r9, rsi
0x18004fbfb  mov     [rsp+60h+var_40], ebx
0x18004fbff  mov     rcx, [rcx+10h]
0x18004fc03  call    WPP_SF_qd
0x18004fc08  lea     rcx, [rbp+var_28]
0x18004fc0c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fc11  jmp     loc_18004FD89
0x18004fc16  lea     rcx, [rbp+var_28]
0x18004fc1a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fc1f  test    r12d, r12d
0x18004fc22  jnz     loc_18004FCDA
0x18004fc28  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fc2f  mov     ebx, 0C00D36D5h
0x18004fc34  test    rcx, rcx
0x18004fc37  jnz     short loc_18004FC7A
0x18004fc39  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fc3f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fc46  mov     rcx, rax
0x18004fc49  test    rax, rax
0x18004fc4c  jz      short loc_18004FC6C
0x18004fc4e  mov     rax, [rax]
0x18004fc51  mov     edx, 7F0h
0x18004fc56  mov     rax, [rax+8]
0x18004fc5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc5f  test    eax, eax
0x18004fc61  jz      short loc_18004FC6C
0x18004fc63  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fc6a  jmp     short loc_18004FC7A
0x18004fc6c  lea     rcx, qword_18006EB20; this
0x18004fc73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fc7a  cmp     byte ptr [rcx+8], 0
0x18004fc7e  jz      short loc_18004FCA5
0x18004fc80  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fc85  cmp     [rax+7CCh], ebx
0x18004fc8b  jz      short loc_18004FCA5
0x18004fc8d  mov     r9d, ebx; int
0x18004fc90  lea     rdx, aCmfvideothumbn_16; "CMFVideoThumbnail::SelectPreferredVideo"...
0x18004fc97  mov     r8d, 7A1h; int
0x18004fc9d  mov     rcx, rax; this
0x18004fca0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004fca5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004fcaa  cmp     al, 1
0x18004fcac  jb      loc_18004FD89
0x18004fcb2  mov     edx, 0C9h
0x18004fcb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fcbe  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004fcc5  mov     r9, rsi
0x18004fcc8  mov     [rsp+60h+var_40], ebx
0x18004fccc  mov     rcx, [rcx+10h]
0x18004fcd0  call    WPP_SF_qd
0x18004fcd5  jmp     loc_18004FD89
0x18004fcda  mov     rax, [r15]
0x18004fcdd  mov     r8d, 1
0x18004fce3  mov     edx, edi
0x18004fce5  mov     rcx, r15
0x18004fce8  mov     rax, [rax+20h]
0x18004fcec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fcf1  mov     ebx, eax
0x18004fcf3  test    eax, eax
0x18004fcf5  jns     loc_18004FD86
0x18004fcfb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fd02  test    rcx, rcx
0x18004fd05  jnz     short loc_18004FD48
0x18004fd07  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fd0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fd14  mov     rcx, rax
0x18004fd17  test    rax, rax
0x18004fd1a  jz      short loc_18004FD3A
0x18004fd1c  mov     rax, [rax]
0x18004fd1f  mov     edx, 7F0h
0x18004fd24  mov     rax, [rax+8]
0x18004fd28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd2d  test    eax, eax
0x18004fd2f  jz      short loc_18004FD3A
0x18004fd31  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fd38  jmp     short loc_18004FD48
0x18004fd3a  lea     rcx, qword_18006EB20; this
0x18004fd41  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fd48  cmp     byte ptr [rcx+8], 0
0x18004fd4c  jz      short loc_18004FD73
0x18004fd4e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fd53  cmp     [rax+7CCh], ebx
0x18004fd59  jz      short loc_18004FD73
0x18004fd5b  mov     r9d, ebx; int
0x18004fd5e  lea     rdx, aCmfvideothumbn_16; "CMFVideoThumbnail::SelectPreferredVideo"...
0x18004fd65  mov     r8d, 7A9h; int
  ... truncated ...
```
