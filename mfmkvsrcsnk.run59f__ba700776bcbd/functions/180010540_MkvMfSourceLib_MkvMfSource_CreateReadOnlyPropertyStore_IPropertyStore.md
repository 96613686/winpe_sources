# MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore(IPropertyStore * *)

- ea: `0x180010540`
- end: `0x180010d68`
- name: `?CreateReadOnlyPropertyStore@MkvMfSource@MkvMfSourceLib@@AEAAJPEAPEAUIPropertyStore@@@Z`
- size: `2088`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180013248`

## callees

- `0x180001ff0`
- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x18000d518`
- `0x18000d554`
- `0x18000ddc0`
- `0x180010540`
- `0x180014e54`
- `0x1800219f0`
- `0x180021b9c`
- `0x180052850`
- `0x180052a48`
- `0x180053900`
- `0x1800744d8`
- `0x1800746f8`
- `0x180076d04`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010625`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001074b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010860`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800109c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010aff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010c45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010625`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001074b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010860`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800109c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010aff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010c45`

## string_xrefs

- `0x18001058d`: `MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore`
- `0x180010a24`: `MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore`
- `0x180010ac9`: `MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore(
        MkvMfSourceLib::MkvMfSource *this,
        struct IPropertyStore **a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int64 v6; // rdx
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
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
  Title = MkvMfSourceLib::MkvMfSource::GetTitle(this);
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
          v19 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v27 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v48 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v42 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v36 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180010540  mov     [rsp+arg_10], rbx
0x180010545  push    rdi
0x180010546  push    r12
0x180010548  push    r13
0x18001054a  push    r14
0x18001054c  push    r15
0x18001054e  sub     rsp, 90h
0x180010555  mov     rax, cs:__security_cookie
0x18001055c  xor     rax, rsp
0x18001055f  mov     [rsp+0B8h+var_38], rax
0x180010567  mov     r13, rdx
0x18001056a  mov     r14, rcx
0x18001056d  mov     [rsp+0B8h+var_50], rcx
0x180010572  mov     [rsp+0B8h+var_78], 0
0x18001057b  mov     [rsp+0B8h+var_80], 0
0x180010584  mov     r15d, 443h
0x18001058a  mov     r8d, r15d; int
0x18001058d  lea     r12, aMkvmfsourcelib_34; "MkvMfSourceLib::MkvMfSource::CreateRead"...
0x180010594  mov     rdx, r12; char *
0x180010597  lea     rcx, [rsp+0B8h+var_88]; this
0x18001059c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800105a1  nop
0x1800105a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800105a9  cmp     byte ptr [rcx+8], 0
0x1800105ad  jz      short loc_180010605
0x1800105af  cmp     qword ptr [r14+2B0h], 0
0x1800105b7  jz      short loc_180010605
0x1800105b9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800105be  mov     rdi, rax
0x1800105c1  mov     rcx, [r14+2B0h]
0x1800105c8  mov     rdx, [rcx]
0x1800105cb  mov     rax, [rdx+128h]
0x1800105d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105d7  mov     ebx, eax
0x1800105d9  mov     rcx, [r14+2B0h]
0x1800105e0  mov     rdx, [rcx]
0x1800105e3  mov     rax, [rdx+118h]
0x1800105ea  lea     rdx, [rsp+0B8h+var_48]
0x1800105ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105f4  movups  xmm0, xmmword ptr [rax]
0x1800105f7  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800105ff  mov     [rdi+7E0h], ebx
0x180010605  lea     rcx, [rsp+0B8h+var_78]; struct CMFStreamingPropHandler **
0x18001060a  call    ?CreateInstance@CMFStreamingPropHandler@@SAJPEAPEAV1@@Z; CMFStreamingPropHandler::CreateInstance(CMFStreamingPropHandler * *)
0x18001060f  mov     ebx, eax
0x180010611  test    eax, eax
0x180010613  jns     loc_1800106F1
0x180010619  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010620  test    rcx, rcx
0x180010623  jnz     short loc_18001066C
0x180010625  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001062c  nop     dword ptr [rax+rax+00h]
0x180010631  mov     rcx, rax
0x180010634  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001063b  test    rax, rax
0x18001063e  jz      short loc_18001065E
0x180010640  mov     rax, [rax]
0x180010643  mov     edx, 7F0h
0x180010648  mov     rax, [rax+8]
0x18001064c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010651  test    eax, eax
0x180010653  jz      short loc_18001065E
0x180010655  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001065c  jmp     short loc_18001066C
0x18001065e  lea     rcx, qword_1800DBF70; this
0x180010665  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001066c  cmp     byte ptr [rcx+8], 0
0x180010670  jz      short loc_180010690
0x180010672  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010677  cmp     [rax+7CCh], ebx
0x18001067d  jz      short loc_180010690
0x18001067f  mov     r9d, ebx; int
0x180010682  mov     r8d, r15d; int
0x180010685  mov     rdx, r12; char *
0x180010688  mov     rcx, rax; this
0x18001068b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180010690  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010697  jb      short loc_1800106BD
0x180010699  mov     edx, 7Ah ; 'z'
0x18001069e  mov     [rsp+0B8h+var_98], ebx
0x1800106a2  mov     r9, r14
0x1800106a5  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800106ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106b3  mov     rcx, [rcx+10h]
0x1800106b7  call    WPP_SF_qD
0x1800106bc  nop
0x1800106bd  lea     rcx, [rsp+0B8h+var_88]; this
0x1800106c2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800106c7  nop
0x1800106c8  lea     rcx, [rsp+0B8h+var_80]
0x1800106cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800106d2  nop
0x1800106d3  mov     rcx, [rsp+0B8h+var_78]
0x1800106d8  test    rcx, rcx
0x1800106db  jz      short loc_1800106EA
0x1800106dd  mov     rax, [rcx]
0x1800106e0  mov     rax, [rax+10h]
0x1800106e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106e9  nop
0x1800106ea  mov     eax, ebx
0x1800106ec  jmp     loc_180010D3E
0x1800106f1  mov     rcx, r14; this
0x1800106f4  call    ?GetTitle@MkvMfSource@MkvMfSourceLib@@QEAAPEAGXZ; MkvMfSourceLib::MkvMfSource::GetTitle(void)
0x1800106f9  mov     [rsp+0B8h+Block], rax
0x1800106fe  lea     rbx, [rsp+0B8h+Block]
0x180010703  mov     [rsp+0B8h+var_48], rbx
0x180010708  mov     [rsp+0B8h+var_40], 1
0x18001070d  test    rax, rax
0x180010710  jz      loc_18001094F
0x180010716  xorps   xmm0, xmm0
0x180010719  xor     ecx, ecx
0x18001071b  movups  xmmword ptr [rsp+0B8h+pvar], xmm0
0x180010720  mov     qword ptr [rsp+0B8h+pvar+10h], rcx
0x180010725  lea     edx, [rcx+1Fh]; unsigned __int16
0x180010728  mov     r8, rax; void *
0x18001072b  lea     rcx, [rsp+0B8h+pvar]; this
0x180010730  call    ?CreateString@CMFPropVariant@@QEAAJGPEBX@Z; CMFPropVariant::CreateString(ushort,void const *)
0x180010735  mov     edi, eax
0x180010737  test    eax, eax
0x180010739  jns     loc_180010830
0x18001073f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010746  test    rcx, rcx
0x180010749  jnz     short loc_180010792
0x18001074b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010752  nop     dword ptr [rax+rax+00h]
0x180010757  mov     rcx, rax
0x18001075a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010761  test    rax, rax
0x180010764  jz      short loc_180010784
0x180010766  mov     rax, [rax]
0x180010769  mov     edx, 7F0h
0x18001076e  mov     rax, [rax+8]
0x180010772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010777  test    eax, eax
0x180010779  jz      short loc_180010784
0x18001077b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010782  jmp     short loc_180010792
0x180010784  lea     rcx, qword_1800DBF70; this
0x18001078b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010792  cmp     byte ptr [rcx+8], 0
0x180010796  jz      short loc_1800107B9
0x180010798  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001079d  cmp     [rax+7CCh], edi
0x1800107a3  jz      short loc_1800107B9
0x1800107a5  mov     r9d, edi; int
0x1800107a8  mov     r8d, 44Fh; int
0x1800107ae  mov     rdx, r12; char *
0x1800107b1  mov     rcx, rax; this
0x1800107b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800107b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800107c0  jb      short loc_1800107E6
0x1800107c2  mov     edx, 7Bh ; '{'
0x1800107c7  mov     [rsp+0B8h+var_98], edi
0x1800107cb  mov     r9, r14
0x1800107ce  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800107d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107dc  mov     rcx, [rcx+10h]
0x1800107e0  call    WPP_SF_qD
0x1800107e5  nop
0x1800107e6  lea     rcx, [rsp+0B8h+pvar]; pvar
0x1800107eb  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800107f0  nop
0x1800107f1  mov     rcx, [rsp+0B8h+Block]; Block
0x1800107f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800107fb  nop
0x1800107fc  lea     rcx, [rsp+0B8h+var_88]; this
0x180010801  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180010806  nop
0x180010807  lea     rcx, [rsp+0B8h+var_80]
0x18001080c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010811  nop
0x180010812  mov     rcx, [rsp+0B8h+var_78]
0x180010817  test    rcx, rcx
0x18001081a  jz      short loc_180010829
0x18001081c  mov     rax, [rcx]
0x18001081f  mov     rax, [rax+10h]
0x180010823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010828  nop
0x180010829  mov     eax, edi
0x18001082b  jmp     loc_180010D3E
0x180010830  lea     r8, [rsp+0B8h+pvar]; struct tagPROPVARIANT *
0x180010835  lea     rdx, PKEY_Title; struct _tagpropertykey *
0x18001083c  mov     rdi, [rsp+0B8h+var_78]
0x180010841  mov     rcx, rdi; this
0x180010844  call    ?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)
0x180010849  mov     r15d, eax
0x18001084c  test    eax, eax
0x18001084e  jns     loc_180010943
0x180010854  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001085b  test    rcx, rcx
0x18001085e  jnz     short loc_1800108A7
0x180010860  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010867  nop     dword ptr [rax+rax+00h]
0x18001086c  mov     rcx, rax
0x18001086f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010876  test    rax, rax
0x180010879  jz      short loc_180010899
0x18001087b  mov     rax, [rax]
0x18001087e  mov     edx, 7F0h
0x180010883  mov     rax, [rax+8]
0x180010887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001088c  test    eax, eax
0x18001088e  jz      short loc_180010899
0x180010890  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010897  jmp     short loc_1800108A7
0x180010899  lea     rcx, qword_1800DBF70; this
0x1800108a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800108a7  cmp     byte ptr [rcx+8], 0
0x1800108ab  jz      short loc_1800108CF
0x1800108ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800108b2  cmp     [rax+7CCh], r15d
0x1800108b9  jz      short loc_1800108CF
0x1800108bb  mov     r9d, r15d; int
0x1800108be  mov     r8d, 450h; int
0x1800108c4  mov     rdx, r12; char *
0x1800108c7  mov     rcx, rax; this
0x1800108ca  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800108cf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800108d6  jb      short loc_1800108FD
0x1800108d8  mov     edx, 7Ch ; '|'
0x1800108dd  mov     [rsp+0B8h+var_98], r15d
0x1800108e2  mov     r9, r14
0x1800108e5  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800108ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108f3  mov     rcx, [rcx+10h]
0x1800108f7  call    WPP_SF_qD
0x1800108fc  nop
0x1800108fd  lea     rcx, [rsp+0B8h+pvar]; pvar
0x180010902  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180010907  nop
0x180010908  mov     rcx, [rsp+0B8h+Block]; Block
0x18001090d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010912  nop
0x180010913  lea     rcx, [rsp+0B8h+var_88]; this
0x180010918  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001091d  nop
0x18001091e  lea     rcx, [rsp+0B8h+var_80]
0x180010923  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010928  nop
0x180010929  test    rdi, rdi
0x18001092c  jz      short loc_18001093E
0x18001092e  mov     rax, [rdi]
0x180010931  mov     rcx, rdi
0x180010934  mov     rax, [rax+10h]
0x180010938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001093d  nop
0x18001093e  jmp     loc_180010D3B
0x180010943  lea     rcx, [rsp+0B8h+pvar]; pvar
0x180010948  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18001094d  jmp     short loc_180010954
0x18001094f  mov     rdi, [rsp+0B8h+var_78]
0x180010954  mov     rdx, [r14+2C0h]
0x18001095b  test    rdx, rdx
0x18001095e  jz      loc_180010AD0
0x180010964  add     rdx, 18h
0x180010968  lea     rcx, [rsp+0B8h+pvar]
0x18001096d  call    ??0?$vector@V?$shared_ptr@VMkvMetadataTag@MkvMfSourceLib@@@std@@V?$allocator@V?$shared_ptr@VMkvMetadataTag@MkvMfSourceLib@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>(std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>> const &)
0x180010972  nop
0x180010973  xor     r12d, r12d
0x180010976  mov     rax, qword ptr [rsp+0B8h+pvar+8]
0x18001097b  mov     rdx, qword ptr [rsp+0B8h+pvar]
0x180010980  sub     rax, rdx
0x180010983  sar     rax, 4
0x180010987  cmp     r12, rax
0x18001098a  jnb     loc_180010ABE
0x180010990  mov     rax, r12
0x180010993  add     rax, rax
0x180010996  mov     rdx, [rdx+rax*8]
0x18001099a  mov     r8, [rdx+8]; struct tagPROPVARIANT *
0x18001099e  mov     rdx, [rdx]; struct _tagpropertykey *
0x1800109a1  mov     rcx, rdi; this
0x1800109a4  call    ?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)
0x1800109a9  mov     r15d, eax
0x1800109ac  test    eax, eax
0x1800109ae  jns     loc_180010AB6
0x1800109b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800109bb  test    rcx, rcx
0x1800109be  jnz     short loc_180010A07
0x1800109c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800109c7  nop     dword ptr [rax+rax+00h]
0x1800109cc  mov     rcx, rax
0x1800109cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800109d6  test    rax, rax
0x1800109d9  jz      short loc_1800109F9
0x1800109db  mov     rax, [rax]
0x1800109de  mov     edx, 7F0h
0x1800109e3  mov     rax, [rax+8]
0x1800109e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ec  test    eax, eax
0x1800109ee  jz      short loc_1800109F9
0x1800109f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800109f7  jmp     short loc_180010A07
0x1800109f9  lea     rcx, qword_1800DBF70; this
0x180010a00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010a07  cmp     byte ptr [rcx+8], 0
0x180010a0b  jz      short loc_180010A33
0x180010a0d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010a12  cmp     [rax+7CCh], r15d
0x180010a19  jz      short loc_180010A33
0x180010a1b  mov     r9d, r15d; int
  ... truncated ...
```
