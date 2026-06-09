# MFMkvPropertyHandler::PopulatePropertyStore(void)

- ea: `0x180050458`
- end: `0x180050b1f`
- name: `?PopulatePropertyStore@MFMkvPropertyHandler@@AEAAJXZ`
- size: `1735`
- prototype: `__int64 __fastcall(MFMkvPropertyHandler *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004f970`

## callees

- `0x180001ff0`
- `0x180003705`
- `0x180005c68`
- `0x180009b04`
- `0x180009bec`
- `0x18000d518`
- `0x18000d554`
- `0x18000ddc0`
- `0x180014e54`
- `0x180021240`
- `0x1800219f0`
- `0x18004ed48`
- `0x180050458`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800507a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800507a2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180050879`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800509f3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180050879`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800509f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800504c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050587`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005069d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050725`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050807`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050924`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050974`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800504c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050587`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005069d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050725`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050807`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050924`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050974`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall MFMkvPropertyHandler::PopulatePropertyStore(MFMkvPropertyHandler *this)
{
  __int64 v2; // rdx
  int v3; // ebx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char *v10; // r15
  __int64 v11; // rdx
  int v12; // esi
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  unsigned __int64 v18; // rdx
  unsigned __int16 *Title; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  int v29; // r8d
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  unsigned int v32; // r12d
  void *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  SIZE_T v39; // r14
  unsigned __int64 i; // r14
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  void *v48; // rcx
  struct CallStackContext *v49; // rax
  PROPVARIANT pvar; // [rsp+50h] [rbp-58h] BYREF
  SIZE_T cb; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v52; // [rsp+C0h] [rbp+18h] BYREF
  void *Src; // [rsp+C8h] [rbp+20h]

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&cb,
    "MFMkvPropertyHandler::PopulatePropertyStore",
    244);
  v52 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 251) + 64LL))(*((_QWORD *)this + 251), &v52);
  if ( v3 < 0 )
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2, v4, v5);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFMkvPropertyHandler::PopulatePropertyStore", 249, v3);
    }
    ATL::CComPtrBase<IMFPresentationDescriptor>::~CComPtrBase<IMFPresentationDescriptor>(&v52);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
    return (unsigned int)v3;
  }
  v10 = (char *)this + 32;
  v12 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this + 4) + 216LL))((char *)this + 32, v52);
  if ( v12 < 0 )
  {
    v15 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v13, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != v12 )
        CallStackContext::TraceFailure(v17, "MFMkvPropertyHandler::PopulatePropertyStore", 250, v12);
    }
    goto LABEL_73;
  }
  Title = MkvMfSourceLib::MkvMfSource::GetTitle(*((MkvMfSourceLib::MkvMfSource **)this + 251));
  Src = Title;
  if ( Title )
  {
    memset(&pvar, 0, sizeof(pvar));
    pvar.vt = 31;
    v22 = -1;
    do
      ++v22;
    while ( Title[v22] );
    if ( v22 + 1 < v22 )
    {
      v46 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v20, v21);
        CallStackTracing::s_wpInstance = v47;
        if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
        {
          v46 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v46 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v46 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
        v12 = -2147024362;
        if ( *((_DWORD *)v28 + 499) != -2147024362 )
        {
          v29 = 271;
          goto LABEL_69;
        }
LABEL_71:
        PropVariantClear(&pvar);
        v48 = Src;
LABEL_72:
        operator delete(v48);
LABEL_73:
        ATL::CComPtrBase<IMFPresentationDescriptor>::~CComPtrBase<IMFPresentationDescriptor>(&v52);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
        return (unsigned int)v12;
      }
LABEL_70:
      v12 = -2147024362;
      goto LABEL_71;
    }
    cb = v22 + 1;
    v12 = ULongLongMult(v22 + 1, v18, &cb);
    if ( v12 < 0 )
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
      if ( !*((_BYTE *)v26 + 8) )
        goto LABEL_71;
      v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
      if ( *((_DWORD *)v28 + 499) == v12 )
        goto LABEL_71;
      v29 = 272;
      goto LABEL_69;
    }
    if ( cb > 0xFFFFFFFF )
    {
      v30 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        v12 = -2147024362;
        if ( *((_DWORD *)v28 + 499) != -2147024362 )
        {
          v29 = 276;
LABEL_69:
          CallStackContext::TraceFailure(v28, "MFMkvPropertyHandler::PopulatePropertyStore", v29, v12);
          goto LABEL_71;
        }
        goto LABEL_71;
      }
      goto LABEL_70;
    }
    v32 = cb;
    v33 = CoTaskMemAlloc((unsigned int)cb);
    pvar.hVal.QuadPart = (LONGLONG)v33;
    if ( v33 )
    {
      memcpy_0(v33, Src, v32);
      v12 = (*(__int64 (__fastcall **)(char *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)v10 + 40LL))(
              (char *)this + 32,
              &PKEY_Title,
              &pvar,
              0,
              1);
      if ( v12 < 0 )
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( !*((_BYTE *)v37 + 8) )
          goto LABEL_71;
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)v28 + 499) == v12 )
          goto LABEL_71;
        v29 = 285;
        goto LABEL_69;
      }
    }
    PropVariantClear(&pvar);
  }
  v39 = *(_QWORD *)(*((_QWORD *)this + 251) + 704LL);
  cb = v39;
  Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(&cb);
  if ( !v39 )
  {
LABEL_81:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&cb);
    v48 = Src;
    goto LABEL_72;
  }
  std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>(
    &pvar,
    v39 + 24);
  for ( i = 0; ; ++i )
  {
    if ( i >= (pvar.hVal.QuadPart - *(_QWORD *)&pvar.vt) >> 4 )
    {
      std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>::_Tidy(&pvar);
      goto LABEL_81;
    }
    v12 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)v10 + 40LL))(
            v10,
            **(_QWORD **)(*(_QWORD *)&pvar.vt + 16 * i),
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&pvar.vt + 16 * i) + 8LL),
            0,
            1);
    if ( v12 < 0 )
      break;
  }
  v44 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
    CallStackTracing::s_wpInstance = v45;
    if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
    {
      v44 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v44 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v44 + 8) )
  {
    v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
    if ( *((_DWORD *)v49 + 499) != v12 )
      CallStackContext::TraceFailure(v49, "MFMkvPropertyHandler::PopulatePropertyStore", 301, v12);
  }
  std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>::_Tidy(&pvar);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&cb);
  operator delete(Src);
  ATL::CComPtrBase<IMFPresentationDescriptor>::~CComPtrBase<IMFPresentationDescriptor>(&v52);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180050458  mov     rax, rsp
0x18005045b  push    rbx
0x18005045c  push    rsi
0x18005045d  push    rdi
0x18005045e  push    r12
0x180050460  push    r13
0x180050462  push    r14
0x180050464  push    r15
0x180050466  sub     rsp, 70h
0x18005046a  mov     r14, rcx
0x18005046d  mov     r8d, 0F4h; int
0x180050473  lea     r13, aMfmkvpropertyh_1; "MFMkvPropertyHandler::PopulatePropertyS"...
0x18005047a  mov     rdx, r13; char *
0x18005047d  lea     rcx, [rax+8]; this
0x180050481  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180050486  nop
0x180050487  xor     edi, edi
0x180050489  mov     [rsp+0A8h+arg_10], rdi
0x180050491  mov     rcx, [r14+7D8h]
0x180050498  mov     rax, [rcx]
0x18005049b  lea     rdx, [rsp+0A8h+arg_10]
0x1800504a3  mov     rax, [rax+40h]
0x1800504a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504ac  mov     ebx, eax
0x1800504ae  test    eax, eax
0x1800504b0  jns     loc_180050553
0x1800504b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800504bd  test    rcx, rcx
0x1800504c0  jnz     short loc_180050509
0x1800504c2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800504c9  nop     dword ptr [rax+rax+00h]
0x1800504ce  mov     rcx, rax
0x1800504d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800504d8  test    rax, rax
0x1800504db  jz      short loc_1800504FB
0x1800504dd  mov     rax, [rax]
0x1800504e0  mov     edx, 7F0h
0x1800504e5  mov     rax, [rax+8]
0x1800504e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504ee  test    eax, eax
0x1800504f0  jz      short loc_1800504FB
0x1800504f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800504f9  jmp     short loc_180050509
0x1800504fb  lea     rcx, qword_1800DBF70; this
0x180050502  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050509  cmp     [rcx+8], dil
0x18005050d  jz      short loc_180050531
0x18005050f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050514  cmp     [rax+7CCh], ebx
0x18005051a  jz      short loc_180050531
0x18005051c  mov     r9d, ebx; int
0x18005051f  mov     r8d, 0F9h; int
0x180050525  mov     rdx, r13; char *
0x180050528  mov     rcx, rax; this
0x18005052b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050530  nop
0x180050531  lea     rcx, [rsp+0A8h+arg_10]
0x180050539  call    ??1?$CComPtrBase@UIMFPresentationDescriptor@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFPresentationDescriptor>::~CComPtrBase<IMFPresentationDescriptor>(void)
0x18005053e  nop
0x18005053f  lea     rcx, [rsp+0A8h+cb]; this
0x180050547  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005054c  mov     eax, ebx
0x18005054e  jmp     loc_180050B0E
0x180050553  lea     r15, [r14+20h]
0x180050557  mov     rax, [r15]
0x18005055a  mov     rdx, [rsp+0A8h+arg_10]
0x180050562  mov     rcx, r15
0x180050565  mov     rax, [rax+0D8h]
0x18005056c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050571  mov     esi, eax
0x180050573  test    eax, eax
0x180050575  jns     loc_180050602
0x18005057b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050582  test    rcx, rcx
0x180050585  jnz     short loc_1800505CE
0x180050587  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005058e  nop     dword ptr [rax+rax+00h]
0x180050593  mov     rcx, rax
0x180050596  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005059d  test    rax, rax
0x1800505a0  jz      short loc_1800505C0
0x1800505a2  mov     rax, [rax]
0x1800505a5  mov     edx, 7F0h
0x1800505aa  mov     rax, [rax+8]
0x1800505ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505b3  test    eax, eax
0x1800505b5  jz      short loc_1800505C0
0x1800505b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800505be  jmp     short loc_1800505CE
0x1800505c0  lea     rcx, qword_1800DBF70; this
0x1800505c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800505ce  cmp     [rcx+8], dil
0x1800505d2  jz      loc_180050A0E
0x1800505d8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800505dd  cmp     [rax+7CCh], esi
0x1800505e3  jz      loc_180050A0E
0x1800505e9  mov     r9d, esi; int
0x1800505ec  mov     r8d, 0FAh; int
0x1800505f2  mov     rdx, r13; char *
0x1800505f5  mov     rcx, rax; this
0x1800505f8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800505fd  jmp     loc_180050A0E
0x180050602  mov     rcx, [r14+7D8h]; this
0x180050609  call    ?GetTitle@MkvMfSource@MkvMfSourceLib@@QEAAPEAGXZ; MkvMfSourceLib::MkvMfSource::GetTitle(void)
0x18005060e  mov     rcx, rax
0x180050611  mov     [rsp+0A8h+Src], rax
0x180050619  lea     rbx, [rsp+0A8h+Src]
0x180050621  mov     [rsp+0A8h+var_78], rbx
0x180050626  mov     [rsp+0A8h+var_70], 1
0x18005062b  test    rax, rax
0x18005062e  jz      loc_180050886
0x180050634  xorps   xmm0, xmm0
0x180050637  xor     eax, eax
0x180050639  movups  xmmword ptr [rsp+0A8h+pvar], xmm0
0x18005063e  mov     qword ptr [rsp+0A8h+pvar+10h], rax
0x180050643  lea     rax, [rsp+0A8h+pvar]
0x180050648  mov     [rsp+0A8h+var_68], rax
0x18005064d  mov     [rsp+0A8h+var_60], 1
0x180050652  mov     eax, 1Fh
0x180050657  mov     word ptr [rsp+0A8h+pvar], ax
0x18005065c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180050660  inc     rax
0x180050663  cmp     [rcx+rax*2], di
0x180050667  jnz     short loc_180050660
0x180050669  lea     rcx, [rax+1]; unsigned __int64
0x18005066d  cmp     rcx, rax
0x180050670  jb      loc_180050968
0x180050676  mov     [rsp+0A8h+cb], rcx
0x18005067e  lea     r8, [rsp+0A8h+cb]; unsigned __int64 *
0x180050686  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18005068b  mov     esi, eax
0x18005068d  test    eax, eax
0x18005068f  jns     short loc_18005070A
0x180050691  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050698  test    rcx, rcx
0x18005069b  jnz     short loc_1800506E4
0x18005069d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800506a4  nop     dword ptr [rax+rax+00h]
0x1800506a9  mov     rcx, rax
0x1800506ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800506b3  test    rax, rax
0x1800506b6  jz      short loc_1800506D6
0x1800506b8  mov     rax, [rax]
0x1800506bb  mov     edx, 7F0h
0x1800506c0  mov     rax, [rax+8]
0x1800506c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506c9  test    eax, eax
0x1800506cb  jz      short loc_1800506D6
0x1800506cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800506d4  jmp     short loc_1800506E4
0x1800506d6  lea     rcx, qword_1800DBF70; this
0x1800506dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800506e4  cmp     [rcx+8], dil
0x1800506e8  jz      loc_1800509EE
0x1800506ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800506f3  cmp     [rax+7CCh], esi
0x1800506f9  jz      loc_1800509EE
0x1800506ff  mov     r8d, 110h
0x180050705  jmp     loc_1800509D9
0x18005070a  mov     eax, 0FFFFFFFFh
0x18005070f  cmp     [rsp+0A8h+cb], rax
0x180050717  jbe     short loc_180050797
0x180050719  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050720  test    rcx, rcx
0x180050723  jnz     short loc_18005076C
0x180050725  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005072c  nop     dword ptr [rax+rax+00h]
0x180050731  mov     rcx, rax
0x180050734  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005073b  test    rax, rax
0x18005073e  jz      short loc_18005075E
0x180050740  mov     rax, [rax]
0x180050743  mov     edx, 7F0h
0x180050748  mov     rax, [rax+8]
0x18005074c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050751  test    eax, eax
0x180050753  jz      short loc_18005075E
0x180050755  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005075c  jmp     short loc_18005076C
0x18005075e  lea     rcx, qword_1800DBF70; this
0x180050765  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005076c  cmp     [rcx+8], dil
0x180050770  jz      loc_1800509E9
0x180050776  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005077b  mov     esi, 80070216h
0x180050780  cmp     [rax+7CCh], esi
0x180050786  jz      loc_1800509EE
0x18005078c  mov     r8d, 114h
0x180050792  jmp     loc_1800509D9
0x180050797  mov     r12d, dword ptr [rsp+0A8h+cb]
0x18005079f  mov     ecx, r12d; cb
0x1800507a2  call    cs:__imp_CoTaskMemAlloc
0x1800507a9  nop     dword ptr [rax+rax+00h]
0x1800507ae  mov     qword ptr [rsp+0A8h+pvar+8], rax
0x1800507b3  test    rax, rax
0x1800507b6  jz      loc_180050874
0x1800507bc  mov     r8d, r12d; Size
0x1800507bf  mov     rdx, [rsp+0A8h+Src]; Src
0x1800507c7  mov     rcx, rax; void *
0x1800507ca  call    memcpy_0
0x1800507cf  mov     rax, [r15]
0x1800507d2  mov     [rsp+0A8h+var_88], 1
0x1800507da  xor     r9d, r9d
0x1800507dd  lea     r8, [rsp+0A8h+pvar]
0x1800507e2  lea     rdx, PKEY_Title
0x1800507e9  mov     rcx, r15
0x1800507ec  mov     rax, [rax+28h]
0x1800507f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507f5  mov     esi, eax
0x1800507f7  test    eax, eax
0x1800507f9  jns     short loc_180050874
0x1800507fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050802  test    rcx, rcx
0x180050805  jnz     short loc_18005084E
0x180050807  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005080e  nop     dword ptr [rax+rax+00h]
0x180050813  mov     rcx, rax
0x180050816  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005081d  test    rax, rax
0x180050820  jz      short loc_180050840
0x180050822  mov     rax, [rax]
0x180050825  mov     edx, 7F0h
0x18005082a  mov     rax, [rax+8]
0x18005082e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050833  test    eax, eax
0x180050835  jz      short loc_180050840
0x180050837  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005083e  jmp     short loc_18005084E
0x180050840  lea     rcx, qword_1800DBF70; this
0x180050847  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005084e  cmp     [rcx+8], dil
0x180050852  jz      loc_1800509EE
0x180050858  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005085d  cmp     [rax+7CCh], esi
0x180050863  jz      loc_1800509EE
0x180050869  mov     r8d, 11Dh
0x18005086f  jmp     loc_1800509D9
0x180050874  lea     rcx, [rsp+0A8h+pvar]; pvar
0x180050879  call    cs:__imp_PropVariantClear
0x180050880  nop     dword ptr [rax+rax+00h]
0x180050885  nop
0x180050886  mov     rax, [r14+7D8h]
0x18005088d  mov     r14, [rax+2C0h]
0x180050894  mov     [rsp+0A8h+cb], r14
0x18005089c  lea     rcx, [rsp+0A8h+cb]
0x1800508a4  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x1800508a9  nop
0x1800508aa  test    r14, r14
0x1800508ad  jz      loc_180050ABF
0x1800508b3  lea     rdx, [r14+18h]
0x1800508b7  lea     rcx, [rsp+0A8h+pvar]
0x1800508bc  call    ??0?$vector@V?$shared_ptr@VMkvMetadataTag@MkvMfSourceLib@@@std@@V?$allocator@V?$shared_ptr@VMkvMetadataTag@MkvMfSourceLib@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>(std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>> const &)
0x1800508c1  nop
0x1800508c2  mov     r14, rdi
0x1800508c5  mov     rax, qword ptr [rsp+0A8h+pvar+8]
0x1800508ca  mov     rdx, qword ptr [rsp+0A8h+pvar]
0x1800508cf  sub     rax, rdx
0x1800508d2  sar     rax, 4
0x1800508d6  cmp     r14, rax
0x1800508d9  jnb     loc_180050AB4
0x1800508df  mov     rax, r14
0x1800508e2  add     rax, rax
0x1800508e5  mov     rdx, [rdx+rax*8]
0x1800508e9  mov     rax, [r15]
0x1800508ec  mov     [rsp+0A8h+var_88], 1
0x1800508f4  xor     r9d, r9d
0x1800508f7  mov     r8, [rdx+8]
0x1800508fb  mov     rdx, [rdx]
0x1800508fe  mov     rcx, r15
0x180050901  mov     rax, [rax+28h]
0x180050905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005090a  mov     esi, eax
0x18005090c  test    eax, eax
0x18005090e  jns     loc_180050AAC
0x180050914  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005091b  test    rcx, rcx
0x18005091e  jnz     loc_180050A3E
0x180050924  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005092b  nop     dword ptr [rax+rax+00h]
0x180050930  mov     rcx, rax
0x180050933  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005093a  test    rax, rax
0x18005093d  jz      loc_180050A30
0x180050943  mov     rax, [rax]
0x180050946  mov     edx, 7F0h
0x18005094b  mov     rax, [rax+8]
0x18005094f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050954  test    eax, eax
0x180050956  jz      loc_180050A30
0x18005095c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050963  jmp     loc_180050A3E
0x180050968  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005096f  test    rcx, rcx
0x180050972  jnz     short loc_1800509BB
0x180050974  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005097b  nop     dword ptr [rax+rax+00h]
0x180050980  mov     rcx, rax
0x180050983  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005098a  test    rax, rax
0x18005098d  jz      short loc_1800509AD
  ... truncated ...
```
