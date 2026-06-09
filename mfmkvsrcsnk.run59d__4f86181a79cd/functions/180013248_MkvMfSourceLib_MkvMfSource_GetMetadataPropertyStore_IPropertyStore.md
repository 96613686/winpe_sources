# MkvMfSourceLib::MkvMfSource::GetMetadataPropertyStore(IPropertyStore * *)

- ea: `0x180013248`
- end: `0x18001384b`
- name: `?GetMetadataPropertyStore@MkvMfSource@MkvMfSourceLib@@AEAAJPEAPEAUIPropertyStore@@@Z`
- size: `1539`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013ed0`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180010540`
- `0x180013248`
- `0x180021b9c`
- `0x1800458ac`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800137e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800137e8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001354c`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18001354c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001336d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013467`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001358a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013671`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013740`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001336d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013467`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001358a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013671`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013740`

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
          v10 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v18 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v31 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v39 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v24 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180013248  mov     [rsp-28h+arg_10], rbx
0x18001324d  mov     [rsp-28h+arg_18], rsi
0x180013252  push    rbp
0x180013253  push    rdi
0x180013254  push    r12
0x180013256  push    r14
0x180013258  push    r15
0x18001325a  mov     rbp, rsp
0x18001325d  sub     rsp, 80h
0x180013264  mov     rax, cs:__security_cookie
0x18001326b  xor     rax, rsp
0x18001326e  mov     [rbp+var_8], rax
0x180013272  mov     r15, rdx
0x180013275  mov     rsi, rcx
0x180013278  xor     r12d, r12d
0x18001327b  mov     [rbp+var_50], r12d
0x18001327f  mov     r8d, 414h; int
0x180013285  lea     rdx, aMkvmfsourcelib_135; "MkvMfSourceLib::MkvMfSource::GetMetadat"...
0x18001328c  lea     rcx, [rbp+var_4C]; this
0x180013290  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180013295  nop
0x180013296  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001329d  cmp     [rcx+8], r12b
0x1800132a1  jz      short loc_1800132F7
0x1800132a3  cmp     [rsi+2B0h], r12
0x1800132aa  jz      short loc_1800132F7
0x1800132ac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800132b1  mov     rdi, rax
0x1800132b4  mov     rcx, [rsi+2B0h]
0x1800132bb  mov     rdx, [rcx]
0x1800132be  mov     rax, [rdx+128h]
0x1800132c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132ca  mov     ebx, eax
0x1800132cc  mov     rcx, [rsi+2B0h]
0x1800132d3  mov     rdx, [rcx]
0x1800132d6  mov     rax, [rdx+118h]
0x1800132dd  lea     rdx, [rbp+var_18]
0x1800132e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132e6  movups  xmm0, xmmword ptr [rax]
0x1800132e9  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800132f1  mov     [rdi+7E0h], ebx
0x1800132f7  mov     [rbp+var_28], rsi
0x1800132fb  lea     rax, [rbp+var_50]
0x1800132ff  mov     [rbp+var_20], rax
0x180013303  lea     r14, [rsi+2B8h]
0x18001330a  cmp     [r14], r12
0x18001330d  jnz     loc_1800137F5
0x180013313  mov     [rbp+pv], r12
0x180013317  mov     [rbp+var_30], r12d
0x18001331b  lea     rax, [rbp+pv]
0x18001331f  mov     [rbp+var_18], rax
0x180013323  mov     [rbp+var_10], 1
0x180013327  lea     rcx, [rsi+0B8h]; this
0x18001332e  lea     r8, [rbp+var_30]; unsigned int *
0x180013332  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180013336  call    ?GetByteStreamOriginName@MkvReader@@QEAAJPEAPEAGPEAI@Z; MkvReader::GetByteStreamOriginName(ushort * *,uint *)
0x18001333b  test    eax, eax
0x18001333d  jns     loc_18001341D
0x180013343  mov     rcx, r14
0x180013346  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001334b  mov     rdx, r14; struct IPropertyStore **
0x18001334e  mov     rcx, rsi; this
0x180013351  call    ?CreateReadOnlyPropertyStore@MkvMfSource@MkvMfSourceLib@@AEAAJPEAPEAUIPropertyStore@@@Z; MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore(IPropertyStore * *)
0x180013356  mov     [rbp+var_50], eax
0x180013359  test    eax, eax
0x18001335b  jns     loc_1800137E4
0x180013361  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013368  test    rcx, rcx
0x18001336b  jnz     short loc_1800133B4
0x18001336d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013374  nop     dword ptr [rax+rax+00h]
0x180013379  mov     rcx, rax
0x18001337c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013383  test    rax, rax
0x180013386  jz      short loc_1800133A6
0x180013388  mov     rax, [rax]
0x18001338b  mov     edx, 7F0h
0x180013390  mov     rax, [rax+8]
0x180013394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013399  test    eax, eax
0x18001339b  jz      short loc_1800133A6
0x18001339d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800133a4  jmp     short loc_1800133B4
0x1800133a6  lea     rcx, qword_1800DBF70; this
0x1800133ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800133b4  cmp     [rcx+8], r12b
0x1800133b8  jz      short loc_1800133E6
0x1800133ba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800133bf  mov     r9d, [rbp+var_50]; int
0x1800133c3  test    r9d, r9d
0x1800133c6  jns     short loc_1800133E6
0x1800133c8  cmp     [rax+7CCh], r9d
0x1800133cf  jz      short loc_1800133E6
0x1800133d1  mov     r8d, 422h; int
0x1800133d7  lea     rdx, aMkvmfsourcelib_135; "MkvMfSourceLib::MkvMfSource::GetMetadat"...
0x1800133de  mov     rcx, rax; this
0x1800133e1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800133e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800133ed  jb      short loc_180013415
0x1800133ef  mov     edx, 74h ; 't'
0x1800133f4  mov     eax, [rbp+var_50]
0x1800133f7  mov     [rsp+80h+var_60], eax
0x1800133fb  mov     r9, rsi
0x1800133fe  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180013405  mov     rcx, cs:WPP_GLOBAL_Control
0x18001340c  mov     rcx, [rcx+10h]
0x180013410  call    WPP_SF_qD
0x180013415  mov     ebx, [rbp+var_50]
0x180013418  jmp     loc_18001351C
0x18001341d  mov     [rbp+var_40], r12
0x180013421  mov     rax, [rsi+20h]
0x180013425  mov     rbx, [rax+18h]
0x180013429  lea     rcx, [rbp+var_40]
0x18001342d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013432  lea     r9, [rbp+var_40]
0x180013436  lea     r8, _GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f
0x18001343d  lea     rdx, MF_PROPERTY_HANDLER_SERVICE
0x180013444  lea     rcx, [rsi+20h]
0x180013448  mov     rax, rbx
0x18001344b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013450  mov     [rbp+var_50], eax
0x180013453  test    eax, eax
0x180013455  jns     loc_180013535
0x18001345b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013462  test    rcx, rcx
0x180013465  jnz     short loc_1800134AE
0x180013467  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001346e  nop     dword ptr [rax+rax+00h]
0x180013473  mov     rcx, rax
0x180013476  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001347d  test    rax, rax
0x180013480  jz      short loc_1800134A0
0x180013482  mov     rax, [rax]
0x180013485  mov     edx, 7F0h
0x18001348a  mov     rax, [rax+8]
0x18001348e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013493  test    eax, eax
0x180013495  jz      short loc_1800134A0
0x180013497  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001349e  jmp     short loc_1800134AE
0x1800134a0  lea     rcx, qword_1800DBF70; this
0x1800134a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800134ae  cmp     [rcx+8], r12b
0x1800134b2  jz      short loc_1800134E0
0x1800134b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800134b9  mov     r9d, [rbp+var_50]; int
0x1800134bd  test    r9d, r9d
0x1800134c0  jns     short loc_1800134E0
0x1800134c2  cmp     [rax+7CCh], r9d
0x1800134c9  jz      short loc_1800134E0
0x1800134cb  mov     r8d, 428h; int
0x1800134d1  lea     rdx, aMkvmfsourcelib_135; "MkvMfSourceLib::MkvMfSource::GetMetadat"...
0x1800134d8  mov     rcx, rax; this
0x1800134db  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800134e0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800134e7  jb      short loc_18001350F
0x1800134e9  mov     edx, 75h ; 'u'
0x1800134ee  mov     eax, [rbp+var_50]
0x1800134f1  mov     [rsp+80h+var_60], eax
0x1800134f5  mov     r9, rsi
0x1800134f8  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800134ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180013506  mov     rcx, [rcx+10h]
0x18001350a  call    WPP_SF_qD
0x18001350f  mov     ebx, [rbp+var_50]
0x180013512  lea     rcx, [rbp+var_40]
0x180013516  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001351b  nop
0x18001351c  mov     rcx, [rbp+pv]; pv
0x180013520  call    cs:__imp_CoTaskMemFree
0x180013527  nop     dword ptr [rax+rax+00h]
0x18001352c  mov     [rbp+pv], r12
0x180013530  jmp     loc_180013817
0x180013535  mov     [rbp+ppstm], r12
0x180013539  lea     rcx, [rbp+ppstm]
0x18001353d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013542  lea     r8, [rbp+ppstm]; ppstm
0x180013546  xor     edx, edx; grfMode
0x180013548  mov     rcx, [rbp+pv]; pszFile
0x18001354c  call    cs:__imp_SHCreateStreamOnFileW
0x180013553  nop     dword ptr [rax+rax+00h]
0x180013558  test    eax, eax
0x18001355a  jns     loc_180013643
0x180013560  mov     rcx, r14
0x180013563  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013568  mov     rdx, r14; struct IPropertyStore **
0x18001356b  mov     rcx, rsi; this
0x18001356e  call    ?CreateReadOnlyPropertyStore@MkvMfSource@MkvMfSourceLib@@AEAAJPEAPEAUIPropertyStore@@@Z; MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore(IPropertyStore * *)
0x180013573  mov     [rbp+var_50], eax
0x180013576  test    eax, eax
0x180013578  jns     loc_1800137D0
0x18001357e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013585  test    rcx, rcx
0x180013588  jnz     short loc_1800135D1
0x18001358a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013591  nop     dword ptr [rax+rax+00h]
0x180013596  mov     rcx, rax
0x180013599  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800135a0  test    rax, rax
0x1800135a3  jz      short loc_1800135C3
0x1800135a5  mov     rax, [rax]
0x1800135a8  mov     edx, 7F0h
0x1800135ad  mov     rax, [rax+8]
0x1800135b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135b6  test    eax, eax
0x1800135b8  jz      short loc_1800135C3
0x1800135ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800135c1  jmp     short loc_1800135D1
0x1800135c3  lea     rcx, qword_1800DBF70; this
0x1800135ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800135d1  cmp     [rcx+8], r12b
0x1800135d5  jz      short loc_180013603
0x1800135d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800135dc  mov     r9d, [rbp+var_50]; int
0x1800135e0  test    r9d, r9d
0x1800135e3  jns     short loc_180013603
0x1800135e5  cmp     [rax+7CCh], r9d
0x1800135ec  jz      short loc_180013603
0x1800135ee  mov     r8d, 42Eh; int
0x1800135f4  lea     rdx, aMkvmfsourcelib_135; "MkvMfSourceLib::MkvMfSource::GetMetadat"...
0x1800135fb  mov     rcx, rax; this
0x1800135fe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013603  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001360a  jb      short loc_180013632
0x18001360c  mov     edx, 76h ; 'v'
0x180013611  mov     eax, [rbp+var_50]
0x180013614  mov     [rsp+80h+var_60], eax
0x180013618  mov     r9, rsi
0x18001361b  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180013622  mov     rcx, cs:WPP_GLOBAL_Control
0x180013629  mov     rcx, [rcx+10h]
0x18001362d  call    WPP_SF_qD
0x180013632  mov     ebx, [rbp+var_50]
0x180013635  lea     rcx, [rbp+ppstm]
0x180013639  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001363e  jmp     loc_180013512
0x180013643  mov     rcx, [rbp+var_40]
0x180013647  mov     rax, [rcx]
0x18001364a  xor     r8d, r8d
0x18001364d  mov     rdx, [rbp+ppstm]
0x180013651  mov     rax, [rax+18h]
0x180013655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001365a  mov     [rbp+var_50], eax
0x18001365d  test    eax, eax
0x18001365f  jns     loc_180013701
0x180013665  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001366c  test    rcx, rcx
0x18001366f  jnz     short loc_1800136B8
0x180013671  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013678  nop     dword ptr [rax+rax+00h]
0x18001367d  mov     rcx, rax
0x180013680  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013687  test    rax, rax
0x18001368a  jz      short loc_1800136AA
0x18001368c  mov     rax, [rax]
0x18001368f  mov     edx, 7F0h
0x180013694  mov     rax, [rax+8]
0x180013698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001369d  test    eax, eax
0x18001369f  jz      short loc_1800136AA
0x1800136a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800136a8  jmp     short loc_1800136B8
0x1800136aa  lea     rcx, qword_1800DBF70; this
0x1800136b1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800136b8  cmp     [rcx+8], r12b
0x1800136bc  jz      short loc_1800136EA
0x1800136be  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800136c3  mov     r9d, [rbp+var_50]; int
0x1800136c7  test    r9d, r9d
0x1800136ca  jns     short loc_1800136EA
0x1800136cc  cmp     [rax+7CCh], r9d
0x1800136d3  jz      short loc_1800136EA
0x1800136d5  mov     r8d, 432h; int
0x1800136db  lea     rdx, aMkvmfsourcelib_135; "MkvMfSourceLib::MkvMfSource::GetMetadat"...
0x1800136e2  mov     rcx, rax; this
0x1800136e5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800136ea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800136f1  jb      loc_180013632
0x1800136f7  mov     edx, 77h ; 'w'
0x1800136fc  jmp     loc_180013611
0x180013701  mov     rbx, [rbp+var_40]
0x180013705  mov     rax, [rbx]
0x180013708  mov     rdi, [rax]
0x18001370b  mov     rcx, r14
0x18001370e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013713  mov     r8, r14
0x180013716  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18001371d  mov     rcx, rbx
0x180013720  mov     rax, rdi
0x180013723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013728  nop
0x180013729  mov     [rbp+var_50], eax
0x18001372c  test    eax, eax
0x18001372e  jns     loc_1800137D0
0x180013734  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001373b  test    rcx, rcx
0x18001373e  jnz     short loc_180013787
0x180013740  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013747  nop     dword ptr [rax+rax+00h]
0x18001374c  mov     rcx, rax
  ... truncated ...
```
