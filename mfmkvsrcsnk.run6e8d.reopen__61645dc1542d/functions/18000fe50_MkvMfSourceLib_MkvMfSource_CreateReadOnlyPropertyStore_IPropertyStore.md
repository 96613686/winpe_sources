# MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore(IPropertyStore * *)

- ea: `0x18000fe50`
- end: `0x180010653`
- name: `?CreateReadOnlyPropertyStore@MkvMfSource@MkvMfSourceLib@@AEAAJPEAPEAUIPropertyStore@@@Z`
- size: `2051`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800129b8`

## callees

- `0x180001fd0`
- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cf78`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18000fe50`
- `0x1800144f4`
- `0x180020b54`
- `0x180020d84`
- `0x1800505c0`
- `0x1800507a8`
- `0x1800515ec`
- `0x180071330`
- `0x180071524`
- `0x1800739f0`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ff35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010055`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010164`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800102be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800103f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010537`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ff35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010055`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010164`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800102be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800103f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010537`

## string_xrefs

- `0x18000fe9d`: `MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore`
- `0x18001031c`: `MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore`
- `0x1800103c1`: `MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore(
        MkvMfSourceLib::MkvMfSource *this,
        struct IPropertyStore **a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  const char *v6; // rdx
  int Instance; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  unsigned __int16 *Title; // rax
  __int64 v15; // rdx
  int String; // edi
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  CMFStreamingPropHandler *v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  int inserted; // r15d
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  unsigned __int64 i; // r12
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  int v35; // r15d
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  _BYTE v51[8]; // [rsp+30h] [rbp-88h] BYREF
  struct IMFPresentationDescriptor *v52; // [rsp+38h] [rbp-80h] BYREF
  struct CMFStreamingPropHandler *v53; // [rsp+40h] [rbp-78h] BYREF
  void *Block; // [rsp+48h] [rbp-70h] BYREF
  PROPVARIANT pvar; // [rsp+50h] [rbp-68h] BYREF
  MkvMfSourceLib::MkvMfSource *v56; // [rsp+68h] [rbp-50h]
  void **p_Block; // [rsp+70h] [rbp-48h] BYREF
  char v58; // [rsp+78h] [rbp-40h]

  v56 = this;
  v53 = 0;
  v52 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v51,
    "MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore",
    1091);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 86) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 86) + 296LL))(*((_QWORD *)this + 86));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, void ***))(**((_QWORD **)this + 86) + 280LL))(
                                                            *((_QWORD *)this + 86),
                                                            &p_Block);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
  }
  Instance = CMFStreamingPropHandler::CreateInstance((void ***)&v53);
  if ( Instance < 0 )
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
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
      if ( *((_DWORD *)v12 + 499) != Instance )
        CallStackContext::TraceFailure(v12, "MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore", 1091, Instance);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        122,
        &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
        this,
        Instance);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
    if ( v53 )
      (*(void (__fastcall **)(struct CMFStreamingPropHandler *))(*(_QWORD *)v53 + 16LL))(v53);
    return (unsigned int)Instance;
  }
  Title = MkvMfSourceLib::MkvMfSource::GetTitle(this, v6);
  Block = Title;
  p_Block = &Block;
  v58 = 1;
  if ( Title )
  {
    memset(&pvar, 0, sizeof(pvar));
    String = CMFPropVariant::CreateString((CMFPropVariant *)&pvar, 31, (const CHAR *)Title);
    if ( String < 0 )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v17, v18);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != String )
          CallStackContext::TraceFailure(v21, "MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore", 1103, String);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          123,
          &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
          this,
          String);
      CMFPropVariant::Clear(&pvar);
      operator delete(Block);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
      if ( v53 )
        (*(void (__fastcall **)(struct CMFStreamingPropHandler *))(*(_QWORD *)v53 + 16LL))(v53);
      return (unsigned int)String;
    }
    v22 = v53;
    inserted = CMFStreamingPropHandler::InsertProperty(v53, &PKEY_Title, &pvar);
    if ( inserted < 0 )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != inserted )
          CallStackContext::TraceFailure(
            v29,
            "MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore",
            1104,
            inserted);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          124,
          &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
          this,
          inserted);
      CMFPropVariant::Clear(&pvar);
      operator delete(Block);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
      if ( v22 )
        (*(void (__fastcall **)(CMFStreamingPropHandler *))(*(_QWORD *)v22 + 16LL))(v22);
      return (unsigned int)inserted;
    }
    CMFPropVariant::Clear(&pvar);
  }
  else
  {
    v22 = v53;
  }
  v30 = *((_QWORD *)this + 88);
  if ( !v30 )
  {
LABEL_68:
    inserted = (*(__int64 (__fastcall **)(MkvMfSourceLib::MkvMfSource *, struct IMFPresentationDescriptor **))(*(_QWORD *)this + 64LL))(
                 this,
                 &v52);
    if ( inserted >= 0 )
    {
      inserted = CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor(v22, v52);
      if ( inserted >= 0 )
      {
        *a2 = (struct IPropertyStore *)v22;
        operator delete(Block);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
      }
      else
      {
        v48 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
          CallStackTracing::s_wpInstance = v49;
          if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
          {
            v48 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v48 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v48 + 8) )
        {
          v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
          if ( *((_DWORD *)v50 + 499) != inserted )
            CallStackContext::TraceFailure(
              v50,
              "MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore",
              1124,
              inserted);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            128,
            &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
            this,
            inserted);
        operator delete(Block);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
        if ( v22 )
          (*(void (__fastcall **)(CMFStreamingPropHandler *))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    else
    {
      v42 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v42 + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
        if ( *((_DWORD *)v44 + 499) != inserted )
          CallStackContext::TraceFailure(
            v44,
            "MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore",
            1123,
            inserted);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          127,
          &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
          this,
          inserted);
      operator delete(Block);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
      if ( v22 )
        (*(void (__fastcall **)(CMFStreamingPropHandler *))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return (unsigned int)inserted;
  }
  std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>(
    &pvar,
    v30 + 24);
  for ( i = 0; ; ++i )
  {
    if ( i >= (pvar.hVal.QuadPart - *(_QWORD *)&pvar.vt) >> 4 )
    {
      std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>::_Tidy(&pvar);
      goto LABEL_68;
    }
    v35 = CMFStreamingPropHandler::InsertProperty(
            v22,
            **(const struct _tagpropertykey ***)(*(_QWORD *)&pvar.vt + 16 * i),
            *(struct tagPROPVARIANT **)(*(_QWORD *)(*(_QWORD *)&pvar.vt + 16 * i) + 8LL));
    if ( v35 < 0 )
      break;
  }
  v36 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
    CallStackTracing::s_wpInstance = v37;
    if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
    {
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v36 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v36 + 8) )
  {
    v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
    if ( *((_DWORD *)v38 + 499) != v35 )
      CallStackContext::TraceFailure(v38, "MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore", 1115, v35);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v35);
  std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>::_Tidy(&pvar);
  v58 = 0;
  operator delete(Block);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  if ( v22 )
  {
    v53 = 0;
    (*(void (__fastcall **)(CMFStreamingPropHandler *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return (unsigned int)v35;
}

```

## disassembly

```asm
0x18000fe50  mov     [rsp+arg_10], rbx
0x18000fe55  push    rdi
0x18000fe56  push    r12
0x18000fe58  push    r13
0x18000fe5a  push    r14
0x18000fe5c  push    r15
0x18000fe5e  sub     rsp, 90h
0x18000fe65  mov     rax, cs:__security_cookie
0x18000fe6c  xor     rax, rsp
0x18000fe6f  mov     [rsp+0B8h+var_38], rax
0x18000fe77  mov     r13, rdx
0x18000fe7a  mov     r14, rcx
0x18000fe7d  mov     [rsp+0B8h+var_50], rcx
0x18000fe82  mov     [rsp+0B8h+var_78], 0
0x18000fe8b  mov     [rsp+0B8h+var_80], 0
0x18000fe94  mov     r15d, 443h
0x18000fe9a  mov     r8d, r15d; int
0x18000fe9d  lea     r12, aMkvmfsourcelib_34; "MkvMfSourceLib::MkvMfSource::CreateRead"...
0x18000fea4  mov     rdx, r12; char *
0x18000fea7  lea     rcx, [rsp+0B8h+var_88]; this
0x18000feac  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000feb1  nop
0x18000feb2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000feb9  cmp     byte ptr [rcx+8], 0
0x18000febd  jz      short loc_18000FF15
0x18000febf  cmp     qword ptr [r14+2B0h], 0
0x18000fec7  jz      short loc_18000FF15
0x18000fec9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000fece  mov     rdi, rax
0x18000fed1  mov     rcx, [r14+2B0h]
0x18000fed8  mov     rdx, [rcx]
0x18000fedb  mov     rax, [rdx+128h]
0x18000fee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fee7  mov     ebx, eax
0x18000fee9  mov     rcx, [r14+2B0h]
0x18000fef0  mov     rdx, [rcx]
0x18000fef3  mov     rax, [rdx+118h]
0x18000fefa  lea     rdx, [rsp+0B8h+var_48]
0x18000feff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff04  movups  xmm0, xmmword ptr [rax]
0x18000ff07  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18000ff0f  mov     [rdi+7E0h], ebx
0x18000ff15  lea     rcx, [rsp+0B8h+var_78]; struct CMFStreamingPropHandler **
0x18000ff1a  call    ?CreateInstance@CMFStreamingPropHandler@@SAJPEAPEAV1@@Z; CMFStreamingPropHandler::CreateInstance(CMFStreamingPropHandler * *)
0x18000ff1f  mov     ebx, eax
0x18000ff21  test    eax, eax
0x18000ff23  jns     loc_18000FFFB
0x18000ff29  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ff30  test    rcx, rcx
0x18000ff33  jnz     short loc_18000FF76
0x18000ff35  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000ff3b  mov     rcx, rax
0x18000ff3e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ff45  test    rax, rax
0x18000ff48  jz      short loc_18000FF68
0x18000ff4a  mov     rax, [rax]
0x18000ff4d  mov     edx, 7F0h
0x18000ff52  mov     rax, [rax+8]
0x18000ff56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff5b  test    eax, eax
0x18000ff5d  jz      short loc_18000FF68
0x18000ff5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ff66  jmp     short loc_18000FF76
0x18000ff68  lea     rcx, qword_1800D6F70; this
0x18000ff6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ff76  cmp     byte ptr [rcx+8], 0
0x18000ff7a  jz      short loc_18000FF9A
0x18000ff7c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000ff81  cmp     [rax+7CCh], ebx
0x18000ff87  jz      short loc_18000FF9A
0x18000ff89  mov     r9d, ebx; int
0x18000ff8c  mov     r8d, r15d; int
0x18000ff8f  mov     rdx, r12; char *
0x18000ff92  mov     rcx, rax; this
0x18000ff95  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000ff9a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000ffa1  jb      short loc_18000FFC7
0x18000ffa3  mov     edx, 7Ah ; 'z'
0x18000ffa8  mov     [rsp+0B8h+var_98], ebx
0x18000ffac  mov     r9, r14
0x18000ffaf  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18000ffb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffbd  mov     rcx, [rcx+10h]
0x18000ffc1  call    WPP_SF_qD
0x18000ffc6  nop
0x18000ffc7  lea     rcx, [rsp+0B8h+var_88]; this
0x18000ffcc  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000ffd1  nop
0x18000ffd2  lea     rcx, [rsp+0B8h+var_80]
0x18000ffd7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ffdc  nop
0x18000ffdd  mov     rcx, [rsp+0B8h+var_78]
0x18000ffe2  test    rcx, rcx
0x18000ffe5  jz      short loc_18000FFF4
0x18000ffe7  mov     rax, [rcx]
0x18000ffea  mov     rax, [rax+10h]
0x18000ffee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fff3  nop
0x18000fff4  mov     eax, ebx
0x18000fff6  jmp     loc_18001062A
0x18000fffb  mov     rcx, r14; this
0x18000fffe  call    ?GetTitle@MkvMfSource@MkvMfSourceLib@@QEAAPEAGXZ; MkvMfSourceLib::MkvMfSource::GetTitle(void)
0x180010003  mov     [rsp+0B8h+Block], rax
0x180010008  lea     rbx, [rsp+0B8h+Block]
0x18001000d  mov     [rsp+0B8h+var_48], rbx
0x180010012  mov     [rsp+0B8h+var_40], 1
0x180010017  test    rax, rax
0x18001001a  jz      loc_18001024D
0x180010020  xorps   xmm0, xmm0
0x180010023  xor     ecx, ecx
0x180010025  movups  xmmword ptr [rsp+0B8h+pvar], xmm0
0x18001002a  mov     qword ptr [rsp+0B8h+pvar+10h], rcx
0x18001002f  lea     edx, [rcx+1Fh]; unsigned __int16
0x180010032  mov     r8, rax; void *
0x180010035  lea     rcx, [rsp+0B8h+pvar]; this
0x18001003a  call    ?CreateString@CMFPropVariant@@QEAAJGPEBX@Z; CMFPropVariant::CreateString(ushort,void const *)
0x18001003f  mov     edi, eax
0x180010041  test    eax, eax
0x180010043  jns     loc_180010134
0x180010049  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010050  test    rcx, rcx
0x180010053  jnz     short loc_180010096
0x180010055  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001005b  mov     rcx, rax
0x18001005e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010065  test    rax, rax
0x180010068  jz      short loc_180010088
0x18001006a  mov     rax, [rax]
0x18001006d  mov     edx, 7F0h
0x180010072  mov     rax, [rax+8]
0x180010076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001007b  test    eax, eax
0x18001007d  jz      short loc_180010088
0x18001007f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010086  jmp     short loc_180010096
0x180010088  lea     rcx, qword_1800D6F70; this
0x18001008f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010096  cmp     byte ptr [rcx+8], 0
0x18001009a  jz      short loc_1800100BD
0x18001009c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800100a1  cmp     [rax+7CCh], edi
0x1800100a7  jz      short loc_1800100BD
0x1800100a9  mov     r9d, edi; int
0x1800100ac  mov     r8d, 44Fh; int
0x1800100b2  mov     rdx, r12; char *
0x1800100b5  mov     rcx, rax; this
0x1800100b8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800100bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800100c4  jb      short loc_1800100EA
0x1800100c6  mov     edx, 7Bh ; '{'
0x1800100cb  mov     [rsp+0B8h+var_98], edi
0x1800100cf  mov     r9, r14
0x1800100d2  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800100d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100e0  mov     rcx, [rcx+10h]
0x1800100e4  call    WPP_SF_qD
0x1800100e9  nop
0x1800100ea  lea     rcx, [rsp+0B8h+pvar]; pvar
0x1800100ef  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800100f4  nop
0x1800100f5  mov     rcx, [rsp+0B8h+Block]; Block
0x1800100fa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800100ff  nop
0x180010100  lea     rcx, [rsp+0B8h+var_88]; this
0x180010105  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001010a  nop
0x18001010b  lea     rcx, [rsp+0B8h+var_80]
0x180010110  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010115  nop
0x180010116  mov     rcx, [rsp+0B8h+var_78]
0x18001011b  test    rcx, rcx
0x18001011e  jz      short loc_18001012D
0x180010120  mov     rax, [rcx]
0x180010123  mov     rax, [rax+10h]
0x180010127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001012c  nop
0x18001012d  mov     eax, edi
0x18001012f  jmp     loc_18001062A
0x180010134  lea     r8, [rsp+0B8h+pvar]; struct tagPROPVARIANT *
0x180010139  lea     rdx, PKEY_Title; struct _tagpropertykey *
0x180010140  mov     rdi, [rsp+0B8h+var_78]
0x180010145  mov     rcx, rdi; this
0x180010148  call    ?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)
0x18001014d  mov     r15d, eax
0x180010150  test    eax, eax
0x180010152  jns     loc_180010241
0x180010158  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001015f  test    rcx, rcx
0x180010162  jnz     short loc_1800101A5
0x180010164  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001016a  mov     rcx, rax
0x18001016d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010174  test    rax, rax
0x180010177  jz      short loc_180010197
0x180010179  mov     rax, [rax]
0x18001017c  mov     edx, 7F0h
0x180010181  mov     rax, [rax+8]
0x180010185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001018a  test    eax, eax
0x18001018c  jz      short loc_180010197
0x18001018e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010195  jmp     short loc_1800101A5
0x180010197  lea     rcx, qword_1800D6F70; this
0x18001019e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800101a5  cmp     byte ptr [rcx+8], 0
0x1800101a9  jz      short loc_1800101CD
0x1800101ab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800101b0  cmp     [rax+7CCh], r15d
0x1800101b7  jz      short loc_1800101CD
0x1800101b9  mov     r9d, r15d; int
0x1800101bc  mov     r8d, 450h; int
0x1800101c2  mov     rdx, r12; char *
0x1800101c5  mov     rcx, rax; this
0x1800101c8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800101cd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800101d4  jb      short loc_1800101FB
0x1800101d6  mov     edx, 7Ch ; '|'
0x1800101db  mov     [rsp+0B8h+var_98], r15d
0x1800101e0  mov     r9, r14
0x1800101e3  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800101ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101f1  mov     rcx, [rcx+10h]
0x1800101f5  call    WPP_SF_qD
0x1800101fa  nop
0x1800101fb  lea     rcx, [rsp+0B8h+pvar]; pvar
0x180010200  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180010205  nop
0x180010206  mov     rcx, [rsp+0B8h+Block]; Block
0x18001020b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010210  nop
0x180010211  lea     rcx, [rsp+0B8h+var_88]; this
0x180010216  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001021b  nop
0x18001021c  lea     rcx, [rsp+0B8h+var_80]
0x180010221  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010226  nop
0x180010227  test    rdi, rdi
0x18001022a  jz      short loc_18001023C
0x18001022c  mov     rax, [rdi]
0x18001022f  mov     rcx, rdi
0x180010232  mov     rax, [rax+10h]
0x180010236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001023b  nop
0x18001023c  jmp     loc_180010627
0x180010241  lea     rcx, [rsp+0B8h+pvar]; pvar
0x180010246  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18001024b  jmp     short loc_180010252
0x18001024d  mov     rdi, [rsp+0B8h+var_78]
0x180010252  mov     rdx, [r14+2C0h]
0x180010259  test    rdx, rdx
0x18001025c  jz      loc_1800103C8
0x180010262  add     rdx, 18h
0x180010266  lea     rcx, [rsp+0B8h+pvar]
0x18001026b  call    ??0?$vector@V?$shared_ptr@VMkvMetadataTag@MkvMfSourceLib@@@std@@V?$allocator@V?$shared_ptr@VMkvMetadataTag@MkvMfSourceLib@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>(std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>> const &)
0x180010270  nop
0x180010271  xor     r12d, r12d
0x180010274  mov     rax, qword ptr [rsp+0B8h+pvar+8]
0x180010279  mov     rdx, qword ptr [rsp+0B8h+pvar]
0x18001027e  sub     rax, rdx
0x180010281  sar     rax, 4
0x180010285  cmp     r12, rax
0x180010288  jnb     loc_1800103B6
0x18001028e  mov     rax, r12
0x180010291  add     rax, rax
0x180010294  mov     rdx, [rdx+rax*8]
0x180010298  mov     r8, [rdx+8]; struct tagPROPVARIANT *
0x18001029c  mov     rdx, [rdx]; struct _tagpropertykey *
0x18001029f  mov     rcx, rdi; this
0x1800102a2  call    ?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)
0x1800102a7  mov     r15d, eax
0x1800102aa  test    eax, eax
0x1800102ac  jns     loc_1800103AE
0x1800102b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800102b9  test    rcx, rcx
0x1800102bc  jnz     short loc_1800102FF
0x1800102be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800102c4  mov     rcx, rax
0x1800102c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800102ce  test    rax, rax
0x1800102d1  jz      short loc_1800102F1
0x1800102d3  mov     rax, [rax]
0x1800102d6  mov     edx, 7F0h
0x1800102db  mov     rax, [rax+8]
0x1800102df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102e4  test    eax, eax
0x1800102e6  jz      short loc_1800102F1
0x1800102e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800102ef  jmp     short loc_1800102FF
0x1800102f1  lea     rcx, qword_1800D6F70; this
0x1800102f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800102ff  cmp     byte ptr [rcx+8], 0
0x180010303  jz      short loc_18001032B
0x180010305  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001030a  cmp     [rax+7CCh], r15d
0x180010311  jz      short loc_18001032B
0x180010313  mov     r9d, r15d; int
0x180010316  mov     r8d, 45Bh; int
0x18001031c  lea     rdx, aMkvmfsourcelib_34; "MkvMfSourceLib::MkvMfSource::CreateRead"...
0x180010323  mov     rcx, rax; this
0x180010326  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
