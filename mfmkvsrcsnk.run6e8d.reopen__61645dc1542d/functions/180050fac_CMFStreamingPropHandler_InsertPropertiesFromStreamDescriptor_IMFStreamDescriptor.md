# CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor(IMFStreamDescriptor *)

- ea: `0x180050fac`
- end: `0x1800515e3`
- name: `?InsertPropertiesFromStreamDescriptor@CMFStreamingPropHandler@@AEAAJPEAUIMFStreamDescriptor@@@Z`
- size: `1591`
- prototype: `__int64 __fastcall(CMFStreamingPropHandler *__hidden this, struct IMFStreamDescriptor *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800507a8`

## callees

- `0x1800023e0`
- `0x1800036b9`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18004f47c`
- `0x18004f524`
- `0x18004fbe0`
- `0x180050fac`
- `0x1800515ec`
- `0x180071330`
- `0x180071524`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005102a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800510e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051173`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051245`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800512d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051374`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005140a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051499`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051535`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005102a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800510e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051173`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051245`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800512d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051374`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005140a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051499`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051535`

## string_xrefs

- `0x180050fd0`: `CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor`

## pseudocode

```c
__int64 __fastcall CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor(
        CMFStreamingPropHandler *this,
        struct IMFStreamDescriptor *a2)
{
  struct IMFStreamDescriptorVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetMediaTypeHandler)(IMFStreamDescriptor *, IMFMediaTypeHandler **); // rax
  __int64 v6; // rdx
  int inserted; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v13; // r8d
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  int v30; // r8d
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  _BYTE v57[4]; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v58; // [rsp+24h] [rbp-4Ch] BYREF
  struct IMFMediaType *v59; // [rsp+28h] [rbp-48h] BYREF
  PROPVARIANT pvar; // [rsp+30h] [rbp-40h] BYREF
  __int64 v61; // [rsp+48h] [rbp-28h] BYREF
  __int128 Buf2; // [rsp+50h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v57,
    "CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor",
    187);
  lpVtbl = a2->lpVtbl;
  v61 = 0;
  v59 = 0;
  GetMediaTypeHandler = lpVtbl->GetMediaTypeHandler;
  Buf2 = 0;
  inserted = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))GetMediaTypeHandler)(a2, &v61);
  if ( inserted < 0 )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
      {
        v13 = 195;
LABEL_10:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor",
          v13,
          inserted);
        goto LABEL_88;
      }
    }
    goto LABEL_88;
  }
  if ( (*(int (__fastcall **)(__int64, struct IMFMediaType **))(*(_QWORD *)v61 + 56LL))(v61, &v59) >= 0
    || (inserted = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMFMediaType **))(*(_QWORD *)v61 + 40LL))(
                     v61,
                     0,
                     &v59),
        inserted >= 0) )
  {
    inserted = ((__int64 (__fastcall *)(struct IMFMediaType *, __int128 *))v59->lpVtbl->GetMajorType)(v59, &Buf2);
    if ( inserted < 0 )
    {
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
        {
          v13 = 203;
          goto LABEL_10;
        }
      }
      goto LABEL_88;
    }
    if ( !memcmp_0(&MFMediaType_Audio, &Buf2, 0x10u) )
    {
      v58 = 0;
      memset(&pvar, 0, sizeof(pvar));
      inserted = CMFStreamingPropHandler::AddAudioMediaTypeProperties(this, v59);
      if ( inserted >= 0 )
      {
        inserted = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, unsigned int *))a2->lpVtbl->GetStreamIdentifier)(
                     a2,
                     &v58);
        if ( inserted >= 0 )
        {
          pvar.vt = 18;
          pvar.hVal.QuadPart = v58;
          inserted = CMFStreamingPropHandler::InsertProperty(this, &PKEY_Audio_StreamNumber, &pvar);
          if ( inserted >= 0 )
            goto LABEL_87;
          v54 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
            CallStackTracing::s_wpInstance = v55;
            if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
            {
              v54 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v54 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( !*((_BYTE *)v54 + 8) )
            goto LABEL_87;
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v29 + 499) == inserted )
            goto LABEL_87;
          v30 = 214;
        }
        else
        {
          v49 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
            CallStackTracing::s_wpInstance = v50;
            if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
            {
              v49 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v49 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( !*((_BYTE *)v49 + 8) )
            goto LABEL_87;
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
          if ( *((_DWORD *)v29 + 499) == inserted )
            goto LABEL_87;
          v30 = 212;
        }
      }
      else
      {
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
        if ( !*((_BYTE *)v44 + 8) )
          goto LABEL_87;
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v29 + 499) == inserted )
          goto LABEL_87;
        v30 = 209;
      }
    }
    else
    {
      if ( memcmp_0(&MFMediaType_Video, &Buf2, 0x10u) )
        goto LABEL_88;
      v58 = 0;
      memset(&pvar, 0, sizeof(pvar));
      inserted = CMFStreamingPropHandler::AddVideoMediaTypeProperties(this, v59);
      if ( inserted >= 0 )
      {
        inserted = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, unsigned int *))a2->lpVtbl->GetStreamIdentifier)(
                     a2,
                     &v58);
        if ( inserted >= 0 )
        {
          pvar.vt = 18;
          pvar.hVal.QuadPart = v58;
          inserted = CMFStreamingPropHandler::InsertProperty(this, &PKEY_Video_StreamNumber, &pvar);
          if ( inserted >= 0 )
            goto LABEL_87;
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
          if ( !*((_BYTE *)v39 + 8) )
            goto LABEL_87;
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
          if ( *((_DWORD *)v29 + 499) == inserted )
            goto LABEL_87;
          v30 = 225;
        }
        else
        {
          v34 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
            CallStackTracing::s_wpInstance = v35;
            if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
            {
              v34 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v34 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( !*((_BYTE *)v34 + 8) )
            goto LABEL_87;
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v29 + 499) == inserted )
            goto LABEL_87;
          v30 = 223;
        }
      }
      else
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
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
        if ( !*((_BYTE *)v27 + 8) )
          goto LABEL_87;
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) == inserted )
          goto LABEL_87;
        v30 = 220;
      }
    }
    CallStackContext::TraceFailure(v29, "CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor", v30, inserted);
LABEL_87:
    CMFPropVariant::Clear(&pvar);
    goto LABEL_88;
  }
  v17 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
    {
      v13 = 200;
      goto LABEL_10;
    }
  }
LABEL_88:
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v59);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v61);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v57);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180050fac  mov     [rsp-28h+arg_10], rbx
0x180050fb1  push    rbp
0x180050fb2  push    rsi
0x180050fb3  push    rdi
0x180050fb4  push    r14
0x180050fb6  push    r15
0x180050fb8  mov     rbp, rsp
0x180050fbb  sub     rsp, 70h
0x180050fbf  mov     rax, cs:__security_cookie
0x180050fc6  xor     rax, rsp
0x180050fc9  mov     [rbp+var_10], rax
0x180050fcd  mov     rdi, rdx
0x180050fd0  lea     r15, aCmfstreamingpr_4; "CMFStreamingPropHandler::InsertProperti"...
0x180050fd7  mov     rsi, rcx
0x180050fda  mov     rdx, r15; char *
0x180050fdd  mov     r8d, 0BBh; int
0x180050fe3  lea     rcx, [rbp+var_50]; this
0x180050fe7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180050fec  mov     rax, [rdi]
0x180050fef  lea     rdx, [rbp+var_28]
0x180050ff3  xor     r14d, r14d
0x180050ff6  xorps   xmm0, xmm0
0x180050ff9  mov     rcx, rdi
0x180050ffc  mov     [rbp+var_28], r14
0x180051000  mov     [rbp+var_48], r14
0x180051004  mov     rax, [rax+110h]
0x18005100b  movups  [rbp+Buf2], xmm0
0x18005100f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051014  mov     ebx, eax
0x180051016  test    eax, eax
0x180051018  jns     loc_18005109F
0x18005101e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051025  test    rcx, rcx
0x180051028  jnz     short loc_18005106B
0x18005102a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051030  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180051037  mov     rcx, rax
0x18005103a  test    rax, rax
0x18005103d  jz      short loc_18005105D
0x18005103f  mov     rax, [rax]
0x180051042  mov     edx, 7F0h
0x180051047  mov     rax, [rax+8]
0x18005104b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051050  test    eax, eax
0x180051052  jz      short loc_18005105D
0x180051054  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005105b  jmp     short loc_18005106B
0x18005105d  lea     rcx, qword_1800D6F70; this
0x180051064  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005106b  cmp     [rcx+8], r14b
0x18005106f  jz      loc_1800515A6
0x180051075  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005107a  cmp     [rax+7CCh], ebx
0x180051080  jz      loc_1800515A6
0x180051086  mov     r8d, 0C3h; int
0x18005108c  mov     r9d, ebx; int
0x18005108f  mov     rdx, r15; char *
0x180051092  mov     rcx, rax; this
0x180051095  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005109a  jmp     loc_1800515A6
0x18005109f  mov     rcx, [rbp+var_28]
0x1800510a3  lea     rdx, [rbp+var_48]
0x1800510a7  mov     rax, [rcx]
0x1800510aa  mov     rax, [rax+38h]
0x1800510ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510b3  test    eax, eax
0x1800510b5  jns     loc_18005114A
0x1800510bb  mov     rcx, [rbp+var_28]
0x1800510bf  lea     r8, [rbp+var_48]
0x1800510c3  xor     edx, edx
0x1800510c5  mov     rax, [rcx]
0x1800510c8  mov     rax, [rax+28h]
0x1800510cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510d1  mov     ebx, eax
0x1800510d3  test    eax, eax
0x1800510d5  jns     short loc_18005114A
0x1800510d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800510de  test    rcx, rcx
0x1800510e1  jnz     short loc_180051124
0x1800510e3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800510e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800510f0  mov     rcx, rax
0x1800510f3  test    rax, rax
0x1800510f6  jz      short loc_180051116
0x1800510f8  mov     rax, [rax]
0x1800510fb  mov     edx, 7F0h
0x180051100  mov     rax, [rax+8]
0x180051104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051109  test    eax, eax
0x18005110b  jz      short loc_180051116
0x18005110d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051114  jmp     short loc_180051124
0x180051116  lea     rcx, qword_1800D6F70; this
0x18005111d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051124  cmp     [rcx+8], r14b
0x180051128  jz      loc_1800515A6
0x18005112e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051133  cmp     [rax+7CCh], ebx
0x180051139  jz      loc_1800515A6
0x18005113f  mov     r8d, 0C8h
0x180051145  jmp     loc_18005108C
0x18005114a  mov     rcx, [rbp+var_48]
0x18005114e  lea     rdx, [rbp+Buf2]
0x180051152  mov     rax, [rcx]
0x180051155  mov     rax, [rax+108h]
0x18005115c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051161  mov     ebx, eax
0x180051163  test    eax, eax
0x180051165  jns     short loc_1800511DA
0x180051167  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005116e  test    rcx, rcx
0x180051171  jnz     short loc_1800511B4
0x180051173  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051179  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180051180  mov     rcx, rax
0x180051183  test    rax, rax
0x180051186  jz      short loc_1800511A6
0x180051188  mov     rax, [rax]
0x18005118b  mov     edx, 7F0h
0x180051190  mov     rax, [rax+8]
0x180051194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051199  test    eax, eax
0x18005119b  jz      short loc_1800511A6
0x18005119d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800511a4  jmp     short loc_1800511B4
0x1800511a6  lea     rcx, qword_1800D6F70; this
0x1800511ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800511b4  cmp     [rcx+8], r14b
0x1800511b8  jz      loc_1800515A6
0x1800511be  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800511c3  cmp     [rax+7CCh], ebx
0x1800511c9  jz      loc_1800515A6
0x1800511cf  mov     r8d, 0CBh
0x1800511d5  jmp     loc_18005108C
0x1800511da  mov     r8d, 10h; Size
0x1800511e0  lea     rdx, [rbp+Buf2]; Buf2
0x1800511e4  lea     rcx, MFMediaType_Audio; Buf1
0x1800511eb  call    memcmp_0
0x1800511f0  test    eax, eax
0x1800511f2  jz      loc_1800513DB
0x1800511f8  mov     r8d, 10h; Size
0x1800511fe  lea     rdx, [rbp+Buf2]; Buf2
0x180051202  lea     rcx, MFMediaType_Video; Buf1
0x180051209  call    memcmp_0
0x18005120e  test    eax, eax
0x180051210  jnz     loc_1800515A6
0x180051216  mov     rdx, [rbp+var_48]; struct IMFMediaType *
0x18005121a  xorps   xmm0, xmm0
0x18005121d  xor     eax, eax
0x18005121f  mov     [rbp+var_4C], r14d
0x180051223  mov     rcx, rsi; this
0x180051226  mov     qword ptr [rbp+pvar+10h], rax
0x18005122a  movups  xmmword ptr [rbp+pvar], xmm0
0x18005122e  call    ?AddVideoMediaTypeProperties@CMFStreamingPropHandler@@AEAAJPEAUIMFMediaType@@@Z; CMFStreamingPropHandler::AddVideoMediaTypeProperties(IMFMediaType *)
0x180051233  mov     ebx, eax
0x180051235  test    eax, eax
0x180051237  jns     short loc_1800512AC
0x180051239  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051240  test    rcx, rcx
0x180051243  jnz     short loc_180051286
0x180051245  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005124b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180051252  mov     rcx, rax
0x180051255  test    rax, rax
0x180051258  jz      short loc_180051278
0x18005125a  mov     rax, [rax]
0x18005125d  mov     edx, 7F0h
0x180051262  mov     rax, [rax+8]
0x180051266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005126b  test    eax, eax
0x18005126d  jz      short loc_180051278
0x18005126f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051276  jmp     short loc_180051286
0x180051278  lea     rcx, qword_1800D6F70; this
0x18005127f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051286  cmp     [rcx+8], r14b
0x18005128a  jz      loc_18005159D
0x180051290  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051295  cmp     [rax+7CCh], ebx
0x18005129b  jz      loc_18005159D
0x1800512a1  mov     r8d, 0DCh
0x1800512a7  jmp     loc_18005158F
0x1800512ac  mov     rax, [rdi]
0x1800512af  lea     rdx, [rbp+var_4C]
0x1800512b3  mov     rcx, rdi
0x1800512b6  mov     rax, [rax+108h]
0x1800512bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512c2  mov     ebx, eax
0x1800512c4  test    eax, eax
0x1800512c6  jns     short loc_18005133B
0x1800512c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800512cf  test    rcx, rcx
0x1800512d2  jnz     short loc_180051315
0x1800512d4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800512da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800512e1  mov     rcx, rax
0x1800512e4  test    rax, rax
0x1800512e7  jz      short loc_180051307
0x1800512e9  mov     rax, [rax]
0x1800512ec  mov     edx, 7F0h
0x1800512f1  mov     rax, [rax+8]
0x1800512f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512fa  test    eax, eax
0x1800512fc  jz      short loc_180051307
0x1800512fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051305  jmp     short loc_180051315
0x180051307  lea     rcx, qword_1800D6F70; this
0x18005130e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051315  cmp     [rcx+8], r14b
0x180051319  jz      loc_18005159D
0x18005131f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051324  cmp     [rax+7CCh], ebx
0x18005132a  jz      loc_18005159D
0x180051330  mov     r8d, 0DFh
0x180051336  jmp     loc_18005158F
0x18005133b  mov     eax, 12h
0x180051340  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180051344  mov     word ptr [rbp+pvar], ax
0x180051348  lea     rdx, PKEY_Video_StreamNumber; struct _tagpropertykey *
0x18005134f  mov     eax, [rbp+var_4C]
0x180051352  mov     rcx, rsi; this
0x180051355  mov     qword ptr [rbp+pvar+8], rax
0x180051359  call    ?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)
0x18005135e  mov     ebx, eax
0x180051360  test    eax, eax
0x180051362  jns     loc_18005159D
0x180051368  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005136f  test    rcx, rcx
0x180051372  jnz     short loc_1800513B5
0x180051374  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005137a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180051381  mov     rcx, rax
0x180051384  test    rax, rax
0x180051387  jz      short loc_1800513A7
0x180051389  mov     rax, [rax]
0x18005138c  mov     edx, 7F0h
0x180051391  mov     rax, [rax+8]
0x180051395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005139a  test    eax, eax
0x18005139c  jz      short loc_1800513A7
0x18005139e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800513a5  jmp     short loc_1800513B5
0x1800513a7  lea     rcx, qword_1800D6F70; this
0x1800513ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800513b5  cmp     [rcx+8], r14b
0x1800513b9  jz      loc_18005159D
0x1800513bf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800513c4  cmp     [rax+7CCh], ebx
0x1800513ca  jz      loc_18005159D
0x1800513d0  mov     r8d, 0E1h
0x1800513d6  jmp     loc_18005158F
0x1800513db  mov     rdx, [rbp+var_48]; struct IMFMediaType *
0x1800513df  xorps   xmm0, xmm0
0x1800513e2  xor     eax, eax
0x1800513e4  mov     [rbp+var_4C], r14d
0x1800513e8  mov     rcx, rsi; this
0x1800513eb  mov     qword ptr [rbp+pvar+10h], rax
0x1800513ef  movups  xmmword ptr [rbp+pvar], xmm0
0x1800513f3  call    ?AddAudioMediaTypeProperties@CMFStreamingPropHandler@@AEAAJPEAUIMFMediaType@@@Z; CMFStreamingPropHandler::AddAudioMediaTypeProperties(IMFMediaType *)
0x1800513f8  mov     ebx, eax
0x1800513fa  test    eax, eax
0x1800513fc  jns     short loc_180051471
0x1800513fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051405  test    rcx, rcx
0x180051408  jnz     short loc_18005144B
0x18005140a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051410  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180051417  mov     rcx, rax
0x18005141a  test    rax, rax
0x18005141d  jz      short loc_18005143D
0x18005141f  mov     rax, [rax]
0x180051422  mov     edx, 7F0h
0x180051427  mov     rax, [rax+8]
0x18005142b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051430  test    eax, eax
0x180051432  jz      short loc_18005143D
0x180051434  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005143b  jmp     short loc_18005144B
0x18005143d  lea     rcx, qword_1800D6F70; this
0x180051444  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005144b  cmp     [rcx+8], r14b
0x18005144f  jz      loc_18005159D
0x180051455  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005145a  cmp     [rax+7CCh], ebx
0x180051460  jz      loc_18005159D
0x180051466  mov     r8d, 0D1h
0x18005146c  jmp     loc_18005158F
0x180051471  mov     rax, [rdi]
0x180051474  lea     rdx, [rbp+var_4C]
0x180051478  mov     rcx, rdi
0x18005147b  mov     rax, [rax+108h]
0x180051482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051487  mov     ebx, eax
0x180051489  test    eax, eax
0x18005148b  jns     short loc_180051500
0x18005148d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051494  test    rcx, rcx
0x180051497  jnz     short loc_1800514DA
0x180051499  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005149f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
