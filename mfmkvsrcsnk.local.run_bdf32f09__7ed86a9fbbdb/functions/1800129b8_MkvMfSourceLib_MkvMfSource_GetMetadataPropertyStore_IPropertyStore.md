# MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore(IPropertyStore * *)

- ea: `0x1800129b8`
- end: `0x180012f8a`
- name: `?GetMetadataPropertyStore@MkvMfSource@MkvMfSourceLib@@AEAAJPEAPEAUIPropertyStore@@@Z`
- size: `1490`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800135f0`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18000fe50`
- `0x1800129b8`
- `0x180020d84`
- `0x180043aa4`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012c84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012f2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012c84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012f2e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180012caa`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180012caa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012add`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012bd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012ce2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012dc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012e8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012add`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012bd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012ce2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012dc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012e8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore(
        MkvMfSourceLib::MkvMfSource *this,
        struct IPropertyStore **a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  _QWORD *v6; // r14
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  unsigned int v13; // ebx
  __int64 (__fastcall *v14)(char *, const IID *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 (__fastcall ***v34)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v35)(_QWORD, GUID *, char *); // rdi
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  int OnlyPropertyStore; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v44[4]; // [rsp+34h] [rbp-4Ch] BYREF
  LPVOID pv; // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall ***v46)(_QWORD, GUID *, char *); // [rsp+40h] [rbp-40h] BYREF
  IStream *ppstm; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v48; // [rsp+50h] [rbp-30h] BYREF
  MkvMfSourceLib::MkvMfSource *v49; // [rsp+58h] [rbp-28h]
  int *v50; // [rsp+60h] [rbp-20h]
  LPVOID *p_pv; // [rsp+68h] [rbp-18h] BYREF
  char v52; // [rsp+70h] [rbp-10h]

  OnlyPropertyStore = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v44,
    "MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore",
    1044);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 86) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 86) + 296LL))(*((_QWORD *)this + 86));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, LPVOID **))(**((_QWORD **)this + 86) + 280LL))(
                                                            *((_QWORD *)this + 86),
                                                            &p_pv);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
  }
  v49 = this;
  v50 = &OnlyPropertyStore;
  v6 = (_QWORD *)((char *)this + 696);
  if ( *((_QWORD *)this + 87) )
    goto LABEL_75;
  pv = 0;
  v48 = 0;
  p_pv = &pv;
  v52 = 1;
  if ( (int)MkvReader::GetByteStreamOriginName(
              (MkvMfSourceLib::MkvMfSource *)((char *)this + 184),
              (unsigned __int16 **)&pv,
              &v48) < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 696);
    OnlyPropertyStore = MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore(
                          this,
                          (struct IPropertyStore **)this + 87);
    if ( OnlyPropertyStore < 0 )
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8, v9);
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( OnlyPropertyStore < 0 && *((_DWORD *)v12 + 499) != OnlyPropertyStore )
          CallStackContext::TraceFailure(
            v12,
            "MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore",
            1058,
            OnlyPropertyStore);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          116,
          &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
          this,
          OnlyPropertyStore);
      v13 = OnlyPropertyStore;
      goto LABEL_33;
    }
    goto LABEL_74;
  }
  v46 = 0;
  v14 = *(__int64 (__fastcall **)(char *, const IID *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*((_QWORD *)this + 4) + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  OnlyPropertyStore = v14(
                        (char *)this + 32,
                        &MF_PROPERTY_HANDLER_SERVICE,
                        &GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f,
                        (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v46);
  if ( OnlyPropertyStore < 0 )
  {
    v18 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( OnlyPropertyStore < 0 && *((_DWORD *)v20 + 499) != OnlyPropertyStore )
        CallStackContext::TraceFailure(
          v20,
          "MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore",
          1064,
          OnlyPropertyStore);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        117,
        &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
        this,
        OnlyPropertyStore);
    v13 = OnlyPropertyStore;
    goto LABEL_32;
  }
  ppstm = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
  if ( SHCreateStreamOnFileW((LPCWSTR)pv, 0, &ppstm) >= 0 )
  {
    OnlyPropertyStore = (*v46)[3](v46, (GUID *)ppstm, 0);
    if ( OnlyPropertyStore < 0 )
    {
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( OnlyPropertyStore < 0 && *((_DWORD *)v33 + 499) != OnlyPropertyStore )
          CallStackContext::TraceFailure(
            v33,
            "MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore",
            1074,
            OnlyPropertyStore);
      }
      if ( !g_wppLevels )
        goto LABEL_48;
      v27 = 119;
      goto LABEL_47;
    }
    v34 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v46;
    v35 = **v46;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 696);
    OnlyPropertyStore = v35(v34, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (char *)this + 696);
    if ( OnlyPropertyStore < 0 )
    {
      v39 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v39 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( OnlyPropertyStore < 0 && *((_DWORD *)v41 + 499) != OnlyPropertyStore )
          CallStackContext::TraceFailure(
            v41,
            "MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore",
            1076,
            OnlyPropertyStore);
      }
      if ( !g_wppLevels )
        goto LABEL_48;
      v27 = 120;
      goto LABEL_47;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 696);
    OnlyPropertyStore = MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore(
                          this,
                          (struct IPropertyStore **)this + 87);
    if ( OnlyPropertyStore < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( OnlyPropertyStore < 0 && *((_DWORD *)v26 + 499) != OnlyPropertyStore )
          CallStackContext::TraceFailure(
            v26,
            "MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore",
            1070,
            OnlyPropertyStore);
      }
      if ( !g_wppLevels )
        goto LABEL_48;
      v27 = 118;
LABEL_47:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v27,
        &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
        this,
        OnlyPropertyStore);
LABEL_48:
      v13 = OnlyPropertyStore;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
LABEL_32:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
LABEL_33:
      CoTaskMemFree(pv);
      pv = 0;
      goto LABEL_78;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
LABEL_74:
  CoTaskMemFree(pv);
LABEL_75:
  if ( *v6 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
  *a2 = (struct IPropertyStore *)*v6;
  OnlyPropertyStore = 0;
  v13 = 0;
LABEL_78:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
  return v13;
}

```

## disassembly

```asm
0x1800129b8  mov     [rsp-28h+arg_10], rbx
0x1800129bd  mov     [rsp-28h+arg_18], rsi
0x1800129c2  push    rbp
0x1800129c3  push    rdi
0x1800129c4  push    r12
0x1800129c6  push    r14
0x1800129c8  push    r15
0x1800129ca  mov     rbp, rsp
0x1800129cd  sub     rsp, 80h
0x1800129d4  mov     rax, cs:__security_cookie
0x1800129db  xor     rax, rsp
0x1800129de  mov     [rbp+var_8], rax
0x1800129e2  mov     r15, rdx
0x1800129e5  mov     rsi, rcx
0x1800129e8  xor     r12d, r12d
0x1800129eb  mov     [rbp+var_50], r12d
0x1800129ef  mov     r8d, 414h; int
0x1800129f5  lea     rdx, aMkvmfsourcelib_135; "MkvMfSourceLib::MkvMfSource::GetMetadat"...
0x1800129fc  lea     rcx, [rbp+var_4C]; this
0x180012a00  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180012a05  nop
0x180012a06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180012a0d  cmp     [rcx+8], r12b
0x180012a11  jz      short loc_180012A67
0x180012a13  cmp     [rsi+2B0h], r12
0x180012a1a  jz      short loc_180012A67
0x180012a1c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012a21  mov     rdi, rax
0x180012a24  mov     rcx, [rsi+2B0h]
0x180012a2b  mov     rdx, [rcx]
0x180012a2e  mov     rax, [rdx+128h]
0x180012a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a3a  mov     ebx, eax
0x180012a3c  mov     rcx, [rsi+2B0h]
0x180012a43  mov     rdx, [rcx]
0x180012a46  mov     rax, [rdx+118h]
0x180012a4d  lea     rdx, [rbp+var_18]
0x180012a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a56  movups  xmm0, xmmword ptr [rax]
0x180012a59  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180012a61  mov     [rdi+7E0h], ebx
0x180012a67  mov     [rbp+var_28], rsi
0x180012a6b  lea     rax, [rbp+var_50]
0x180012a6f  mov     [rbp+var_20], rax
0x180012a73  lea     r14, [rsi+2B8h]
0x180012a7a  cmp     [r14], r12
0x180012a7d  jnz     loc_180012F35
0x180012a83  mov     [rbp+pv], r12
0x180012a87  mov     [rbp+var_30], r12d
0x180012a8b  lea     rax, [rbp+pv]
0x180012a8f  mov     [rbp+var_18], rax
0x180012a93  mov     [rbp+var_10], 1
0x180012a97  lea     rcx, [rsi+0B8h]; this
0x180012a9e  lea     r8, [rbp+var_30]; unsigned int *
0x180012aa2  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180012aa6  call    ?GetByteStreamOriginName@MkvReader@@QEAAJPEAPEAGPEAI@Z; MkvReader::GetByteStreamOriginName(ushort * *,uint *)
0x180012aab  test    eax, eax
0x180012aad  jns     loc_180012B87
0x180012ab3  mov     rcx, r14
0x180012ab6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012abb  mov     rdx, r14; struct IPropertyStore **
0x180012abe  mov     rcx, rsi; this
0x180012ac1  call    ?CreateReadOnlyPropertyStore@MkvMfSource@MkvMfSourceLib@@AEAAJPEAPEAUIPropertyStore@@@Z; MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore(IPropertyStore * *)
0x180012ac6  mov     [rbp+var_50], eax
0x180012ac9  test    eax, eax
0x180012acb  jns     loc_180012F2A
0x180012ad1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012ad8  test    rcx, rcx
0x180012adb  jnz     short loc_180012B1E
0x180012add  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012ae3  mov     rcx, rax
0x180012ae6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012aed  test    rax, rax
0x180012af0  jz      short loc_180012B10
0x180012af2  mov     rax, [rax]
0x180012af5  mov     edx, 7F0h
0x180012afa  mov     rax, [rax+8]
0x180012afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b03  test    eax, eax
0x180012b05  jz      short loc_180012B10
0x180012b07  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012b0e  jmp     short loc_180012B1E
0x180012b10  lea     rcx, qword_1800D6F70; this
0x180012b17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012b1e  cmp     [rcx+8], r12b
0x180012b22  jz      short loc_180012B50
0x180012b24  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012b29  mov     r9d, [rbp+var_50]; int
0x180012b2d  test    r9d, r9d
0x180012b30  jns     short loc_180012B50
0x180012b32  cmp     [rax+7CCh], r9d
0x180012b39  jz      short loc_180012B50
0x180012b3b  mov     r8d, 422h; int
0x180012b41  lea     rdx, aMkvmfsourcelib_135; "MkvMfSourceLib::MkvMfSource::GetMetadat"...
0x180012b48  mov     rcx, rax; this
0x180012b4b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012b50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012b57  jb      short loc_180012B7F
0x180012b59  mov     edx, 74h ; 't'
0x180012b5e  mov     eax, [rbp+var_50]
0x180012b61  mov     [rsp+80h+var_60], eax
0x180012b65  mov     r9, rsi
0x180012b68  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180012b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b76  mov     rcx, [rcx+10h]
0x180012b7a  call    WPP_SF_qD
0x180012b7f  mov     ebx, [rbp+var_50]
0x180012b82  jmp     loc_180012C80
0x180012b87  mov     [rbp+var_40], r12
0x180012b8b  mov     rax, [rsi+20h]
0x180012b8f  mov     rbx, [rax+18h]
0x180012b93  lea     rcx, [rbp+var_40]
0x180012b97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012b9c  lea     r9, [rbp+var_40]
0x180012ba0  lea     r8, _GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f
0x180012ba7  lea     rdx, MF_PROPERTY_HANDLER_SERVICE
0x180012bae  lea     rcx, [rsi+20h]
0x180012bb2  mov     rax, rbx
0x180012bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bba  mov     [rbp+var_50], eax
0x180012bbd  test    eax, eax
0x180012bbf  jns     loc_180012C93
0x180012bc5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012bcc  test    rcx, rcx
0x180012bcf  jnz     short loc_180012C12
0x180012bd1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012bd7  mov     rcx, rax
0x180012bda  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012be1  test    rax, rax
0x180012be4  jz      short loc_180012C04
0x180012be6  mov     rax, [rax]
0x180012be9  mov     edx, 7F0h
0x180012bee  mov     rax, [rax+8]
0x180012bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bf7  test    eax, eax
0x180012bf9  jz      short loc_180012C04
0x180012bfb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012c02  jmp     short loc_180012C12
0x180012c04  lea     rcx, qword_1800D6F70; this
0x180012c0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012c12  cmp     [rcx+8], r12b
0x180012c16  jz      short loc_180012C44
0x180012c18  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012c1d  mov     r9d, [rbp+var_50]; int
0x180012c21  test    r9d, r9d
0x180012c24  jns     short loc_180012C44
0x180012c26  cmp     [rax+7CCh], r9d
0x180012c2d  jz      short loc_180012C44
0x180012c2f  mov     r8d, 428h; int
0x180012c35  lea     rdx, aMkvmfsourcelib_135; "MkvMfSourceLib::MkvMfSource::GetMetadat"...
0x180012c3c  mov     rcx, rax; this
0x180012c3f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012c44  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012c4b  jb      short loc_180012C73
0x180012c4d  mov     edx, 75h ; 'u'
0x180012c52  mov     eax, [rbp+var_50]
0x180012c55  mov     [rsp+80h+var_60], eax
0x180012c59  mov     r9, rsi
0x180012c5c  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180012c63  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c6a  mov     rcx, [rcx+10h]
0x180012c6e  call    WPP_SF_qD
0x180012c73  mov     ebx, [rbp+var_50]
0x180012c76  lea     rcx, [rbp+var_40]
0x180012c7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012c7f  nop
0x180012c80  mov     rcx, [rbp+pv]; pv
0x180012c84  call    cs:__imp_CoTaskMemFree
0x180012c8a  mov     [rbp+pv], r12
0x180012c8e  jmp     loc_180012F57
0x180012c93  mov     [rbp+ppstm], r12
0x180012c97  lea     rcx, [rbp+ppstm]
0x180012c9b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012ca0  lea     r8, [rbp+ppstm]; ppstm
0x180012ca4  xor     edx, edx; grfMode
0x180012ca6  mov     rcx, [rbp+pv]; pszFile
0x180012caa  call    cs:__imp_SHCreateStreamOnFileW
0x180012cb0  test    eax, eax
0x180012cb2  jns     loc_180012D95
0x180012cb8  mov     rcx, r14
0x180012cbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012cc0  mov     rdx, r14; struct IPropertyStore **
0x180012cc3  mov     rcx, rsi; this
0x180012cc6  call    ?CreateReadOnlyPropertyStore@MkvMfSource@MkvMfSourceLib@@AEAAJPEAPEAUIPropertyStore@@@Z; MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore(IPropertyStore * *)
0x180012ccb  mov     [rbp+var_50], eax
0x180012cce  test    eax, eax
0x180012cd0  jns     loc_180012F16
0x180012cd6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012cdd  test    rcx, rcx
0x180012ce0  jnz     short loc_180012D23
0x180012ce2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012ce8  mov     rcx, rax
0x180012ceb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012cf2  test    rax, rax
0x180012cf5  jz      short loc_180012D15
0x180012cf7  mov     rax, [rax]
0x180012cfa  mov     edx, 7F0h
0x180012cff  mov     rax, [rax+8]
0x180012d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d08  test    eax, eax
0x180012d0a  jz      short loc_180012D15
0x180012d0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d13  jmp     short loc_180012D23
0x180012d15  lea     rcx, qword_1800D6F70; this
0x180012d1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d23  cmp     [rcx+8], r12b
0x180012d27  jz      short loc_180012D55
0x180012d29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012d2e  mov     r9d, [rbp+var_50]; int
0x180012d32  test    r9d, r9d
0x180012d35  jns     short loc_180012D55
0x180012d37  cmp     [rax+7CCh], r9d
0x180012d3e  jz      short loc_180012D55
0x180012d40  mov     r8d, 42Eh; int
0x180012d46  lea     rdx, aMkvmfsourcelib_135; "MkvMfSourceLib::MkvMfSource::GetMetadat"...
0x180012d4d  mov     rcx, rax; this
0x180012d50  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012d55  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012d5c  jb      short loc_180012D84
0x180012d5e  mov     edx, 76h ; 'v'
0x180012d63  mov     eax, [rbp+var_50]
0x180012d66  mov     [rsp+80h+var_60], eax
0x180012d6a  mov     r9, rsi
0x180012d6d  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180012d74  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d7b  mov     rcx, [rcx+10h]
0x180012d7f  call    WPP_SF_qD
0x180012d84  mov     ebx, [rbp+var_50]
0x180012d87  lea     rcx, [rbp+ppstm]
0x180012d8b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012d90  jmp     loc_180012C76
0x180012d95  mov     rcx, [rbp+var_40]
0x180012d99  mov     rax, [rcx]
0x180012d9c  xor     r8d, r8d
0x180012d9f  mov     rdx, [rbp+ppstm]
0x180012da3  mov     rax, [rax+18h]
0x180012da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dac  mov     [rbp+var_50], eax
0x180012daf  test    eax, eax
0x180012db1  jns     loc_180012E4D
0x180012db7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012dbe  test    rcx, rcx
0x180012dc1  jnz     short loc_180012E04
0x180012dc3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012dc9  mov     rcx, rax
0x180012dcc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012dd3  test    rax, rax
0x180012dd6  jz      short loc_180012DF6
0x180012dd8  mov     rax, [rax]
0x180012ddb  mov     edx, 7F0h
0x180012de0  mov     rax, [rax+8]
0x180012de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012de9  test    eax, eax
0x180012deb  jz      short loc_180012DF6
0x180012ded  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012df4  jmp     short loc_180012E04
0x180012df6  lea     rcx, qword_1800D6F70; this
0x180012dfd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012e04  cmp     [rcx+8], r12b
0x180012e08  jz      short loc_180012E36
0x180012e0a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012e0f  mov     r9d, [rbp+var_50]; int
0x180012e13  test    r9d, r9d
0x180012e16  jns     short loc_180012E36
0x180012e18  cmp     [rax+7CCh], r9d
0x180012e1f  jz      short loc_180012E36
0x180012e21  mov     r8d, 432h; int
0x180012e27  lea     rdx, aMkvmfsourcelib_135; "MkvMfSourceLib::MkvMfSource::GetMetadat"...
0x180012e2e  mov     rcx, rax; this
0x180012e31  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012e36  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012e3d  jb      loc_180012D84
0x180012e43  mov     edx, 77h ; 'w'
0x180012e48  jmp     loc_180012D63
0x180012e4d  mov     rbx, [rbp+var_40]
0x180012e51  mov     rax, [rbx]
0x180012e54  mov     rdi, [rax]
0x180012e57  mov     rcx, r14
0x180012e5a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012e5f  mov     r8, r14
0x180012e62  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180012e69  mov     rcx, rbx
0x180012e6c  mov     rax, rdi
0x180012e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e74  nop
0x180012e75  mov     [rbp+var_50], eax
0x180012e78  test    eax, eax
0x180012e7a  jns     loc_180012F16
0x180012e80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012e87  test    rcx, rcx
0x180012e8a  jnz     short loc_180012ECD
0x180012e8c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012e92  mov     rcx, rax
0x180012e95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012e9c  test    rax, rax
0x180012e9f  jz      short loc_180012EBF
0x180012ea1  mov     rax, [rax]
0x180012ea4  mov     edx, 7F0h
0x180012ea9  mov     rax, [rax+8]
0x180012ead  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
