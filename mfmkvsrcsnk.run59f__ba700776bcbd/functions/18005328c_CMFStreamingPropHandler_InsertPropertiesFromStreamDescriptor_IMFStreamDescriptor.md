# CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor(IMFStreamDescriptor *)

- ea: `0x18005328c`
- end: `0x1800538fa`
- name: `?InsertPropertiesFromStreamDescriptor@CMFStreamingPropHandler@@AEAAJPEAUIMFStreamDescriptor@@@Z`
- size: `1646`
- prototype: `__int64 __fastcall(CMFStreamingPropHandler *__hidden this, struct IMFStreamDescriptor *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180052a48`

## callees

- `0x180002400`
- `0x1800036f9`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x1800516a4`
- `0x180051754`
- `0x180051e30`
- `0x18005328c`
- `0x180053900`
- `0x1800744d8`
- `0x1800746f8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005330a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800533c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005345f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053537`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800535cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053672`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005370e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800537a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053845`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005330a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800533c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005345f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053537`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800535cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053672`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005370e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800537a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053845`

## string_xrefs

- `0x1800532b0`: `CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor`

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
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v22 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v54 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v49 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v44 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v39 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v34 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v27 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v17 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18005328c  mov     [rsp-28h+arg_10], rbx
0x180053291  push    rbp
0x180053292  push    rsi
0x180053293  push    rdi
0x180053294  push    r14
0x180053296  push    r15
0x180053298  mov     rbp, rsp
0x18005329b  sub     rsp, 70h
0x18005329f  mov     rax, cs:__security_cookie
0x1800532a6  xor     rax, rsp
0x1800532a9  mov     [rbp+var_10], rax
0x1800532ad  mov     rdi, rdx
0x1800532b0  lea     r15, aCmfstreamingpr_4; "CMFStreamingPropHandler::InsertProperti"...
0x1800532b7  mov     rsi, rcx
0x1800532ba  mov     rdx, r15; char *
0x1800532bd  mov     r8d, 0BBh; int
0x1800532c3  lea     rcx, [rbp+var_50]; this
0x1800532c7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800532cc  mov     rax, [rdi]
0x1800532cf  lea     rdx, [rbp+var_28]
0x1800532d3  xor     r14d, r14d
0x1800532d6  xorps   xmm0, xmm0
0x1800532d9  mov     rcx, rdi
0x1800532dc  mov     [rbp+var_28], r14
0x1800532e0  mov     [rbp+var_48], r14
0x1800532e4  mov     rax, [rax+110h]
0x1800532eb  movups  [rbp+Buf2], xmm0
0x1800532ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532f4  mov     ebx, eax
0x1800532f6  test    eax, eax
0x1800532f8  jns     loc_180053385
0x1800532fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053305  test    rcx, rcx
0x180053308  jnz     short loc_180053351
0x18005330a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053311  nop     dword ptr [rax+rax+00h]
0x180053316  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005331d  mov     rcx, rax
0x180053320  test    rax, rax
0x180053323  jz      short loc_180053343
0x180053325  mov     rax, [rax]
0x180053328  mov     edx, 7F0h
0x18005332d  mov     rax, [rax+8]
0x180053331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053336  test    eax, eax
0x180053338  jz      short loc_180053343
0x18005333a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053341  jmp     short loc_180053351
0x180053343  lea     rcx, qword_1800DBF70; this
0x18005334a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053351  cmp     [rcx+8], r14b
0x180053355  jz      loc_1800538BC
0x18005335b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053360  cmp     [rax+7CCh], ebx
0x180053366  jz      loc_1800538BC
0x18005336c  mov     r8d, 0C3h; int
0x180053372  mov     r9d, ebx; int
0x180053375  mov     rdx, r15; char *
0x180053378  mov     rcx, rax; this
0x18005337b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053380  jmp     loc_1800538BC
0x180053385  mov     rcx, [rbp+var_28]
0x180053389  lea     rdx, [rbp+var_48]
0x18005338d  mov     rax, [rcx]
0x180053390  mov     rax, [rax+38h]
0x180053394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053399  test    eax, eax
0x18005339b  jns     loc_180053436
0x1800533a1  mov     rcx, [rbp+var_28]
0x1800533a5  lea     r8, [rbp+var_48]
0x1800533a9  xor     edx, edx
0x1800533ab  mov     rax, [rcx]
0x1800533ae  mov     rax, [rax+28h]
0x1800533b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533b7  mov     ebx, eax
0x1800533b9  test    eax, eax
0x1800533bb  jns     short loc_180053436
0x1800533bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800533c4  test    rcx, rcx
0x1800533c7  jnz     short loc_180053410
0x1800533c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800533d0  nop     dword ptr [rax+rax+00h]
0x1800533d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800533dc  mov     rcx, rax
0x1800533df  test    rax, rax
0x1800533e2  jz      short loc_180053402
0x1800533e4  mov     rax, [rax]
0x1800533e7  mov     edx, 7F0h
0x1800533ec  mov     rax, [rax+8]
0x1800533f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533f5  test    eax, eax
0x1800533f7  jz      short loc_180053402
0x1800533f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053400  jmp     short loc_180053410
0x180053402  lea     rcx, qword_1800DBF70; this
0x180053409  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053410  cmp     [rcx+8], r14b
0x180053414  jz      loc_1800538BC
0x18005341a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005341f  cmp     [rax+7CCh], ebx
0x180053425  jz      loc_1800538BC
0x18005342b  mov     r8d, 0C8h
0x180053431  jmp     loc_180053372
0x180053436  mov     rcx, [rbp+var_48]
0x18005343a  lea     rdx, [rbp+Buf2]
0x18005343e  mov     rax, [rcx]
0x180053441  mov     rax, [rax+108h]
0x180053448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005344d  mov     ebx, eax
0x18005344f  test    eax, eax
0x180053451  jns     short loc_1800534CC
0x180053453  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005345a  test    rcx, rcx
0x18005345d  jnz     short loc_1800534A6
0x18005345f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053466  nop     dword ptr [rax+rax+00h]
0x18005346b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053472  mov     rcx, rax
0x180053475  test    rax, rax
0x180053478  jz      short loc_180053498
0x18005347a  mov     rax, [rax]
0x18005347d  mov     edx, 7F0h
0x180053482  mov     rax, [rax+8]
0x180053486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005348b  test    eax, eax
0x18005348d  jz      short loc_180053498
0x18005348f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053496  jmp     short loc_1800534A6
0x180053498  lea     rcx, qword_1800DBF70; this
0x18005349f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800534a6  cmp     [rcx+8], r14b
0x1800534aa  jz      loc_1800538BC
0x1800534b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800534b5  cmp     [rax+7CCh], ebx
0x1800534bb  jz      loc_1800538BC
0x1800534c1  mov     r8d, 0CBh
0x1800534c7  jmp     loc_180053372
0x1800534cc  mov     r8d, 10h; Size
0x1800534d2  lea     rdx, [rbp+Buf2]; Buf2
0x1800534d6  lea     rcx, MFMediaType_Audio; Buf1
0x1800534dd  call    memcmp_0
0x1800534e2  test    eax, eax
0x1800534e4  jz      loc_1800536DF
0x1800534ea  mov     r8d, 10h; Size
0x1800534f0  lea     rdx, [rbp+Buf2]; Buf2
0x1800534f4  lea     rcx, MFMediaType_Video; Buf1
0x1800534fb  call    memcmp_0
0x180053500  test    eax, eax
0x180053502  jnz     loc_1800538BC
0x180053508  mov     rdx, [rbp+var_48]; struct IMFMediaType *
0x18005350c  xorps   xmm0, xmm0
0x18005350f  xor     eax, eax
0x180053511  mov     [rbp+var_4C], r14d
0x180053515  mov     rcx, rsi; this
0x180053518  mov     qword ptr [rbp+pvar+10h], rax
0x18005351c  movups  xmmword ptr [rbp+pvar], xmm0
0x180053520  call    ?AddVideoMediaTypeProperties@CMFStreamingPropHandler@@AEAAJPEAUIMFMediaType@@@Z; CMFStreamingPropHandler::AddVideoMediaTypeProperties(IMFMediaType *)
0x180053525  mov     ebx, eax
0x180053527  test    eax, eax
0x180053529  jns     short loc_1800535A4
0x18005352b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053532  test    rcx, rcx
0x180053535  jnz     short loc_18005357E
0x180053537  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005353e  nop     dword ptr [rax+rax+00h]
0x180053543  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005354a  mov     rcx, rax
0x18005354d  test    rax, rax
0x180053550  jz      short loc_180053570
0x180053552  mov     rax, [rax]
0x180053555  mov     edx, 7F0h
0x18005355a  mov     rax, [rax+8]
0x18005355e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053563  test    eax, eax
0x180053565  jz      short loc_180053570
0x180053567  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005356e  jmp     short loc_18005357E
0x180053570  lea     rcx, qword_1800DBF70; this
0x180053577  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005357e  cmp     [rcx+8], r14b
0x180053582  jz      loc_1800538B3
0x180053588  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005358d  cmp     [rax+7CCh], ebx
0x180053593  jz      loc_1800538B3
0x180053599  mov     r8d, 0DCh
0x18005359f  jmp     loc_1800538A5
0x1800535a4  mov     rax, [rdi]
0x1800535a7  lea     rdx, [rbp+var_4C]
0x1800535ab  mov     rcx, rdi
0x1800535ae  mov     rax, [rax+108h]
0x1800535b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800535ba  mov     ebx, eax
0x1800535bc  test    eax, eax
0x1800535be  jns     short loc_180053639
0x1800535c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800535c7  test    rcx, rcx
0x1800535ca  jnz     short loc_180053613
0x1800535cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800535d3  nop     dword ptr [rax+rax+00h]
0x1800535d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800535df  mov     rcx, rax
0x1800535e2  test    rax, rax
0x1800535e5  jz      short loc_180053605
0x1800535e7  mov     rax, [rax]
0x1800535ea  mov     edx, 7F0h
0x1800535ef  mov     rax, [rax+8]
0x1800535f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800535f8  test    eax, eax
0x1800535fa  jz      short loc_180053605
0x1800535fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053603  jmp     short loc_180053613
0x180053605  lea     rcx, qword_1800DBF70; this
0x18005360c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053613  cmp     [rcx+8], r14b
0x180053617  jz      loc_1800538B3
0x18005361d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053622  cmp     [rax+7CCh], ebx
0x180053628  jz      loc_1800538B3
0x18005362e  mov     r8d, 0DFh
0x180053634  jmp     loc_1800538A5
0x180053639  mov     eax, 12h
0x18005363e  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180053642  mov     word ptr [rbp+pvar], ax
0x180053646  lea     rdx, PKEY_Video_StreamNumber; struct _tagpropertykey *
0x18005364d  mov     eax, [rbp+var_4C]
0x180053650  mov     rcx, rsi; this
0x180053653  mov     qword ptr [rbp+pvar+8], rax
0x180053657  call    ?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)
0x18005365c  mov     ebx, eax
0x18005365e  test    eax, eax
0x180053660  jns     loc_1800538B3
0x180053666  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005366d  test    rcx, rcx
0x180053670  jnz     short loc_1800536B9
0x180053672  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053679  nop     dword ptr [rax+rax+00h]
0x18005367e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053685  mov     rcx, rax
0x180053688  test    rax, rax
0x18005368b  jz      short loc_1800536AB
0x18005368d  mov     rax, [rax]
0x180053690  mov     edx, 7F0h
0x180053695  mov     rax, [rax+8]
0x180053699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005369e  test    eax, eax
0x1800536a0  jz      short loc_1800536AB
0x1800536a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800536a9  jmp     short loc_1800536B9
0x1800536ab  lea     rcx, qword_1800DBF70; this
0x1800536b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800536b9  cmp     [rcx+8], r14b
0x1800536bd  jz      loc_1800538B3
0x1800536c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800536c8  cmp     [rax+7CCh], ebx
0x1800536ce  jz      loc_1800538B3
0x1800536d4  mov     r8d, 0E1h
0x1800536da  jmp     loc_1800538A5
0x1800536df  mov     rdx, [rbp+var_48]; struct IMFMediaType *
0x1800536e3  xorps   xmm0, xmm0
0x1800536e6  xor     eax, eax
0x1800536e8  mov     [rbp+var_4C], r14d
0x1800536ec  mov     rcx, rsi; this
0x1800536ef  mov     qword ptr [rbp+pvar+10h], rax
0x1800536f3  movups  xmmword ptr [rbp+pvar], xmm0
0x1800536f7  call    ?AddAudioMediaTypeProperties@CMFStreamingPropHandler@@AEAAJPEAUIMFMediaType@@@Z; CMFStreamingPropHandler::AddAudioMediaTypeProperties(IMFMediaType *)
0x1800536fc  mov     ebx, eax
0x1800536fe  test    eax, eax
0x180053700  jns     short loc_18005377B
0x180053702  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053709  test    rcx, rcx
0x18005370c  jnz     short loc_180053755
0x18005370e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053715  nop     dword ptr [rax+rax+00h]
0x18005371a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053721  mov     rcx, rax
0x180053724  test    rax, rax
0x180053727  jz      short loc_180053747
0x180053729  mov     rax, [rax]
0x18005372c  mov     edx, 7F0h
0x180053731  mov     rax, [rax+8]
0x180053735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005373a  test    eax, eax
0x18005373c  jz      short loc_180053747
0x18005373e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053745  jmp     short loc_180053755
0x180053747  lea     rcx, qword_1800DBF70; this
0x18005374e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053755  cmp     [rcx+8], r14b
0x180053759  jz      loc_1800538B3
0x18005375f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053764  cmp     [rax+7CCh], ebx
0x18005376a  jz      loc_1800538B3
0x180053770  mov     r8d, 0D1h
0x180053776  jmp     loc_1800538A5
0x18005377b  mov     rax, [rdi]
0x18005377e  lea     rdx, [rbp+var_4C]
0x180053782  mov     rcx, rdi
0x180053785  mov     rax, [rax+108h]
0x18005378c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053791  mov     ebx, eax
  ... truncated ...
```
