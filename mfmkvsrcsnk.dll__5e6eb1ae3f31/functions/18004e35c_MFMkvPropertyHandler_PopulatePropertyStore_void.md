# MFMkvPropertyHandler::PopulatePropertyStore(void)

- ea: `0x18004e35c`
- end: `0x18004e9e6`
- name: `?PopulatePropertyStore@MFMkvPropertyHandler@@AEAAJXZ`
- size: `1674`
- prototype: `__int64 __fastcall(MFMkvPropertyHandler *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004d920`

## callees

- `0x180001fd0`
- `0x1800036c5`
- `0x180005ab8`
- `0x1800097f0`
- `0x1800098b8`
- `0x18000cf78`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x1800144f4`
- `0x1800203f0`
- `0x180020b54`
- `0x18004cd78`
- `0x18004e35c`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e68e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e68e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004e759`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004e8c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004e759`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004e8c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e3c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e485`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e595`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e617`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e6ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e7fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e848`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e3c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e485`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e595`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e617`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e6ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e7fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e848`

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
        v6 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v15 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v46 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v26 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v30 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v37 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v44 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18004e35c  mov     rax, rsp
0x18004e35f  push    rbx
0x18004e360  push    rsi
0x18004e361  push    rdi
0x18004e362  push    r12
0x18004e364  push    r13
0x18004e366  push    r14
0x18004e368  push    r15
0x18004e36a  sub     rsp, 70h
0x18004e36e  mov     r14, rcx
0x18004e371  mov     r8d, 0F4h; int
0x18004e377  lea     r13, aMfmkvpropertyh_1; "MFMkvPropertyHandler::PopulatePropertyS"...
0x18004e37e  mov     rdx, r13; char *
0x18004e381  lea     rcx, [rax+8]; this
0x18004e385  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004e38a  nop
0x18004e38b  xor     edi, edi
0x18004e38d  mov     [rsp+0A8h+arg_10], rdi
0x18004e395  mov     rcx, [r14+7D8h]
0x18004e39c  mov     rax, [rcx]
0x18004e39f  lea     rdx, [rsp+0A8h+arg_10]
0x18004e3a7  mov     rax, [rax+40h]
0x18004e3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3b0  mov     ebx, eax
0x18004e3b2  test    eax, eax
0x18004e3b4  jns     loc_18004E451
0x18004e3ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e3c1  test    rcx, rcx
0x18004e3c4  jnz     short loc_18004E407
0x18004e3c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e3cc  mov     rcx, rax
0x18004e3cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e3d6  test    rax, rax
0x18004e3d9  jz      short loc_18004E3F9
0x18004e3db  mov     rax, [rax]
0x18004e3de  mov     edx, 7F0h
0x18004e3e3  mov     rax, [rax+8]
0x18004e3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3ec  test    eax, eax
0x18004e3ee  jz      short loc_18004E3F9
0x18004e3f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e3f7  jmp     short loc_18004E407
0x18004e3f9  lea     rcx, qword_1800D6F70; this
0x18004e400  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e407  cmp     [rcx+8], dil
0x18004e40b  jz      short loc_18004E42F
0x18004e40d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e412  cmp     [rax+7CCh], ebx
0x18004e418  jz      short loc_18004E42F
0x18004e41a  mov     r9d, ebx; int
0x18004e41d  mov     r8d, 0F9h; int
0x18004e423  mov     rdx, r13; char *
0x18004e426  mov     rcx, rax; this
0x18004e429  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e42e  nop
0x18004e42f  lea     rcx, [rsp+0A8h+arg_10]
0x18004e437  call    ??1?$CComPtrBase@UIMFPresentationDescriptor@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFPresentationDescriptor>::~CComPtrBase<IMFPresentationDescriptor>(void)
0x18004e43c  nop
0x18004e43d  lea     rcx, [rsp+0A8h+cb]; this
0x18004e445  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004e44a  mov     eax, ebx
0x18004e44c  jmp     loc_18004E9D6
0x18004e451  lea     r15, [r14+20h]
0x18004e455  mov     rax, [r15]
0x18004e458  mov     rdx, [rsp+0A8h+arg_10]
0x18004e460  mov     rcx, r15
0x18004e463  mov     rax, [rax+0D8h]
0x18004e46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e46f  mov     esi, eax
0x18004e471  test    eax, eax
0x18004e473  jns     loc_18004E4FA
0x18004e479  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e480  test    rcx, rcx
0x18004e483  jnz     short loc_18004E4C6
0x18004e485  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e48b  mov     rcx, rax
0x18004e48e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e495  test    rax, rax
0x18004e498  jz      short loc_18004E4B8
0x18004e49a  mov     rax, [rax]
0x18004e49d  mov     edx, 7F0h
0x18004e4a2  mov     rax, [rax+8]
0x18004e4a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4ab  test    eax, eax
0x18004e4ad  jz      short loc_18004E4B8
0x18004e4af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e4b6  jmp     short loc_18004E4C6
0x18004e4b8  lea     rcx, qword_1800D6F70; this
0x18004e4bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e4c6  cmp     [rcx+8], dil
0x18004e4ca  jz      loc_18004E8D6
0x18004e4d0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e4d5  cmp     [rax+7CCh], esi
0x18004e4db  jz      loc_18004E8D6
0x18004e4e1  mov     r9d, esi; int
0x18004e4e4  mov     r8d, 0FAh; int
0x18004e4ea  mov     rdx, r13; char *
0x18004e4ed  mov     rcx, rax; this
0x18004e4f0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e4f5  jmp     loc_18004E8D6
0x18004e4fa  mov     rcx, [r14+7D8h]; this
0x18004e501  call    ?GetTitle@MkvMfSource@MkvMfSourceLib@@QEAAPEAGXZ; MkvMfSourceLib::MkvMfSource::GetTitle(void)
0x18004e506  mov     rcx, rax
0x18004e509  mov     [rsp+0A8h+Src], rax
0x18004e511  lea     rbx, [rsp+0A8h+Src]
0x18004e519  mov     [rsp+0A8h+var_78], rbx
0x18004e51e  mov     [rsp+0A8h+var_70], 1
0x18004e523  test    rax, rax
0x18004e526  jz      loc_18004E760
0x18004e52c  xorps   xmm0, xmm0
0x18004e52f  xor     eax, eax
0x18004e531  movups  xmmword ptr [rsp+0A8h+pvar], xmm0
0x18004e536  mov     qword ptr [rsp+0A8h+pvar+10h], rax
0x18004e53b  lea     rax, [rsp+0A8h+pvar]
0x18004e540  mov     [rsp+0A8h+var_68], rax
0x18004e545  mov     [rsp+0A8h+var_60], 1
0x18004e54a  mov     eax, 1Fh
0x18004e54f  mov     word ptr [rsp+0A8h+pvar], ax
0x18004e554  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004e558  inc     rax
0x18004e55b  cmp     [rcx+rax*2], di
0x18004e55f  jnz     short loc_18004E558
0x18004e561  lea     rcx, [rax+1]; unsigned __int64
0x18004e565  cmp     rcx, rax
0x18004e568  jb      loc_18004E83C
0x18004e56e  mov     [rsp+0A8h+cb], rcx
0x18004e576  lea     r8, [rsp+0A8h+cb]; unsigned __int64 *
0x18004e57e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004e583  mov     esi, eax
0x18004e585  test    eax, eax
0x18004e587  jns     short loc_18004E5FC
0x18004e589  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e590  test    rcx, rcx
0x18004e593  jnz     short loc_18004E5D6
0x18004e595  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e59b  mov     rcx, rax
0x18004e59e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e5a5  test    rax, rax
0x18004e5a8  jz      short loc_18004E5C8
0x18004e5aa  mov     rax, [rax]
0x18004e5ad  mov     edx, 7F0h
0x18004e5b2  mov     rax, [rax+8]
0x18004e5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5bb  test    eax, eax
0x18004e5bd  jz      short loc_18004E5C8
0x18004e5bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e5c6  jmp     short loc_18004E5D6
0x18004e5c8  lea     rcx, qword_1800D6F70; this
0x18004e5cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e5d6  cmp     [rcx+8], dil
0x18004e5da  jz      loc_18004E8BC
0x18004e5e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e5e5  cmp     [rax+7CCh], esi
0x18004e5eb  jz      loc_18004E8BC
0x18004e5f1  mov     r8d, 110h
0x18004e5f7  jmp     loc_18004E8A7
0x18004e5fc  mov     eax, 0FFFFFFFFh
0x18004e601  cmp     [rsp+0A8h+cb], rax
0x18004e609  jbe     short loc_18004E683
0x18004e60b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e612  test    rcx, rcx
0x18004e615  jnz     short loc_18004E658
0x18004e617  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e61d  mov     rcx, rax
0x18004e620  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e627  test    rax, rax
0x18004e62a  jz      short loc_18004E64A
0x18004e62c  mov     rax, [rax]
0x18004e62f  mov     edx, 7F0h
0x18004e634  mov     rax, [rax+8]
0x18004e638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e63d  test    eax, eax
0x18004e63f  jz      short loc_18004E64A
0x18004e641  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e648  jmp     short loc_18004E658
0x18004e64a  lea     rcx, qword_1800D6F70; this
0x18004e651  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e658  cmp     [rcx+8], dil
0x18004e65c  jz      loc_18004E8B7
0x18004e662  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e667  mov     esi, 80070216h
0x18004e66c  cmp     [rax+7CCh], esi
0x18004e672  jz      loc_18004E8BC
0x18004e678  mov     r8d, 114h
0x18004e67e  jmp     loc_18004E8A7
0x18004e683  mov     r12d, dword ptr [rsp+0A8h+cb]
0x18004e68b  mov     ecx, r12d; cb
0x18004e68e  call    cs:__imp_CoTaskMemAlloc
0x18004e694  mov     qword ptr [rsp+0A8h+pvar+8], rax
0x18004e699  test    rax, rax
0x18004e69c  jz      loc_18004E754
0x18004e6a2  mov     r8d, r12d; Size
0x18004e6a5  mov     rdx, [rsp+0A8h+Src]; Src
0x18004e6ad  mov     rcx, rax; void *
0x18004e6b0  call    memcpy_0
0x18004e6b5  mov     rax, [r15]
0x18004e6b8  mov     [rsp+0A8h+var_88], 1
0x18004e6c0  xor     r9d, r9d
0x18004e6c3  lea     r8, [rsp+0A8h+pvar]
0x18004e6c8  lea     rdx, PKEY_Title
0x18004e6cf  mov     rcx, r15
0x18004e6d2  mov     rax, [rax+28h]
0x18004e6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6db  mov     esi, eax
0x18004e6dd  test    eax, eax
0x18004e6df  jns     short loc_18004E754
0x18004e6e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e6e8  test    rcx, rcx
0x18004e6eb  jnz     short loc_18004E72E
0x18004e6ed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e6f3  mov     rcx, rax
0x18004e6f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e6fd  test    rax, rax
0x18004e700  jz      short loc_18004E720
0x18004e702  mov     rax, [rax]
0x18004e705  mov     edx, 7F0h
0x18004e70a  mov     rax, [rax+8]
0x18004e70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e713  test    eax, eax
0x18004e715  jz      short loc_18004E720
0x18004e717  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e71e  jmp     short loc_18004E72E
0x18004e720  lea     rcx, qword_1800D6F70; this
0x18004e727  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e72e  cmp     [rcx+8], dil
0x18004e732  jz      loc_18004E8BC
0x18004e738  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e73d  cmp     [rax+7CCh], esi
0x18004e743  jz      loc_18004E8BC
0x18004e749  mov     r8d, 11Dh
0x18004e74f  jmp     loc_18004E8A7
0x18004e754  lea     rcx, [rsp+0A8h+pvar]; pvar
0x18004e759  call    cs:__imp_PropVariantClear
0x18004e75f  nop
0x18004e760  mov     rax, [r14+7D8h]
0x18004e767  mov     r14, [rax+2C0h]
0x18004e76e  mov     [rsp+0A8h+cb], r14
0x18004e776  lea     rcx, [rsp+0A8h+cb]
0x18004e77e  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x18004e783  nop
0x18004e784  test    r14, r14
0x18004e787  jz      loc_18004E987
0x18004e78d  lea     rdx, [r14+18h]
0x18004e791  lea     rcx, [rsp+0A8h+pvar]
0x18004e796  call    ??0?$vector@V?$shared_ptr@VMkvMetadataTag@MkvMfSourceLib@@@std@@V?$allocator@V?$shared_ptr@VMkvMetadataTag@MkvMfSourceLib@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>>(std::vector<std::shared_ptr<MkvMfSourceLib::MkvMetadataTag>> const &)
0x18004e79b  nop
0x18004e79c  mov     r14, rdi
0x18004e79f  mov     rax, qword ptr [rsp+0A8h+pvar+8]
0x18004e7a4  mov     rdx, qword ptr [rsp+0A8h+pvar]
0x18004e7a9  sub     rax, rdx
0x18004e7ac  sar     rax, 4
0x18004e7b0  cmp     r14, rax
0x18004e7b3  jnb     loc_18004E97C
0x18004e7b9  mov     rax, r14
0x18004e7bc  add     rax, rax
0x18004e7bf  mov     rdx, [rdx+rax*8]
0x18004e7c3  mov     rax, [r15]
0x18004e7c6  mov     [rsp+0A8h+var_88], 1
0x18004e7ce  xor     r9d, r9d
0x18004e7d1  mov     r8, [rdx+8]
0x18004e7d5  mov     rdx, [rdx]
0x18004e7d8  mov     rcx, r15
0x18004e7db  mov     rax, [rax+28h]
0x18004e7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7e4  mov     esi, eax
0x18004e7e6  test    eax, eax
0x18004e7e8  jns     loc_18004E974
0x18004e7ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e7f5  test    rcx, rcx
0x18004e7f8  jnz     loc_18004E906
0x18004e7fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e804  mov     rcx, rax
0x18004e807  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e80e  test    rax, rax
0x18004e811  jz      loc_18004E8F8
0x18004e817  mov     rax, [rax]
0x18004e81a  mov     edx, 7F0h
0x18004e81f  mov     rax, [rax+8]
0x18004e823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e828  test    eax, eax
0x18004e82a  jz      loc_18004E8F8
0x18004e830  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e837  jmp     loc_18004E906
0x18004e83c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e843  test    rcx, rcx
0x18004e846  jnz     short loc_18004E889
0x18004e848  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e84e  mov     rcx, rax
0x18004e851  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e858  test    rax, rax
0x18004e85b  jz      short loc_18004E87B
0x18004e85d  mov     rax, [rax]
0x18004e860  mov     edx, 7F0h
0x18004e865  mov     rax, [rax+8]
0x18004e869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e86e  test    eax, eax
0x18004e870  jz      short loc_18004E87B
0x18004e872  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e879  jmp     short loc_18004E889
0x18004e87b  lea     rcx, qword_1800D6F70; this
  ... truncated ...
```
