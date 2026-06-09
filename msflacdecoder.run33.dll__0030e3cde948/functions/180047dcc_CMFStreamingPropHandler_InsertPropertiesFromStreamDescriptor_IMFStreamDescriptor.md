# CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor(IMFStreamDescriptor *)

- ea: `0x180047dcc`
- end: `0x180048405`
- name: `?InsertPropertiesFromStreamDescriptor@CMFStreamingPropHandler@@AEAAJPEAUIMFStreamDescriptor@@@Z`
- size: `1593`
- prototype: `__int64 __fastcall(CMFStreamingPropHandler *__hidden this, struct IMFStreamDescriptor *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800475c8`

## callees

- `0x180001e80`
- `0x180016b18`
- `0x180016e48`
- `0x18002a100`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180034a04`
- `0x180039e60`
- `0x180046384`
- `0x180046a04`
- `0x180047dcc`
- `0x18004840c`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047e4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047f03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047f93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048065`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800480f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048194`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004822a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800482b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048355`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047e4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047f03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047f93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048065`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800480f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048194`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004822a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800482b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048355`

## string_xrefs

- `0x180047df9`: `CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor(
        CMFStreamingPropHandler *this,
        struct IMFStreamDescriptor *a2)
{
  __int64 v4; // rdx
  int inserted; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v9; // r8d
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  int v20; // r8d
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  __int64 v33; // rdx
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  _BYTE v37[4]; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v38; // [rsp+24h] [rbp-4Ch] BYREF
  struct IMFMediaType *v39; // [rsp+28h] [rbp-48h] BYREF
  PROPVARIANT pvar; // [rsp+30h] [rbp-40h] BYREF
  __int64 v41; // [rsp+48h] [rbp-28h] BYREF
  __int128 Buf2; // [rsp+50h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v37,
    "CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor",
    187);
  v41 = 0;
  v39 = 0;
  Buf2 = 0;
  inserted = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))a2->lpVtbl->GetMediaTypeHandler)(
               a2,
               &v41);
  if ( inserted < 0 )
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
      {
        v9 = 195;
LABEL_10:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor",
          v9,
          inserted);
        goto LABEL_88;
      }
    }
    goto LABEL_88;
  }
  if ( (*(int (__fastcall **)(__int64, struct IMFMediaType **))(*(_QWORD *)v41 + 56LL))(v41, &v39) >= 0
    || (inserted = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMFMediaType **))(*(_QWORD *)v41 + 40LL))(
                     v41,
                     0,
                     &v39),
        inserted >= 0) )
  {
    inserted = ((__int64 (__fastcall *)(struct IMFMediaType *, __int128 *))v39->lpVtbl->GetMajorType)(v39, &Buf2);
    if ( inserted < 0 )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
        {
          v9 = 203;
          goto LABEL_10;
        }
      }
      goto LABEL_88;
    }
    if ( !memcmp_0(&MFMediaType_Audio, &Buf2, 0x10u) )
    {
      memset(&pvar, 0, sizeof(pvar));
      v38 = 0;
      inserted = CMFStreamingPropHandler::AddAudioMediaTypeProperties(this, v39);
      if ( inserted >= 0 )
      {
        inserted = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, unsigned int *))a2->lpVtbl->GetStreamIdentifier)(
                     a2,
                     &v38);
        if ( inserted >= 0 )
        {
          pvar.vt = 18;
          pvar.hVal.QuadPart = v38;
          inserted = CMFStreamingPropHandler::InsertProperty(this, &PKEY_Audio_StreamNumber, &pvar);
          if ( inserted >= 0 )
            goto LABEL_87;
          v34 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
            CallStackTracing::s_wpInstance = v35;
            if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
            {
              v34 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v34 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( !*((_BYTE *)v34 + 8) )
            goto LABEL_87;
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v19 + 499) == inserted )
            goto LABEL_87;
          v20 = 214;
        }
        else
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
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
          if ( !*((_BYTE *)v31 + 8) )
            goto LABEL_87;
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
          if ( *((_DWORD *)v19 + 499) == inserted )
            goto LABEL_87;
          v20 = 212;
        }
      }
      else
      {
        v28 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( !*((_BYTE *)v28 + 8) )
          goto LABEL_87;
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v19 + 499) == inserted )
          goto LABEL_87;
        v20 = 209;
      }
    }
    else
    {
      if ( memcmp_0(&MFMediaType_Video, &Buf2, 0x10u) )
        goto LABEL_88;
      memset(&pvar, 0, sizeof(pvar));
      v38 = 0;
      inserted = CMFStreamingPropHandler::AddVideoMediaTypeProperties(this, v39);
      if ( inserted >= 0 )
      {
        inserted = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, unsigned int *))a2->lpVtbl->GetStreamIdentifier)(
                     a2,
                     &v38);
        if ( inserted >= 0 )
        {
          pvar.vt = 18;
          pvar.hVal.QuadPart = v38;
          inserted = CMFStreamingPropHandler::InsertProperty(this, &PKEY_Video_StreamNumber, &pvar);
          if ( inserted >= 0 )
            goto LABEL_87;
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
            {
              v25 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v25 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( !*((_BYTE *)v25 + 8) )
            goto LABEL_87;
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v19 + 499) == inserted )
            goto LABEL_87;
          v20 = 225;
        }
        else
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v22 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( !*((_BYTE *)v22 + 8) )
            goto LABEL_87;
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
          if ( *((_DWORD *)v19 + 499) == inserted )
            goto LABEL_87;
          v20 = 223;
        }
      }
      else
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( !*((_BYTE *)v17 + 8) )
          goto LABEL_87;
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) == inserted )
          goto LABEL_87;
        v20 = 220;
      }
    }
    CallStackContext::TraceFailure(v19, "CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor", v20, inserted);
LABEL_87:
    CMFPropVariant::Clear(&pvar);
    goto LABEL_88;
  }
  v11 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
    {
      v9 = 200;
      goto LABEL_10;
    }
  }
LABEL_88:
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v39);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v41);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v37);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180047dcc  mov     [rsp-28h+arg_10], rbx
0x180047dd1  push    rbp
0x180047dd2  push    rsi
0x180047dd3  push    rdi
0x180047dd4  push    r14
0x180047dd6  push    r15
0x180047dd8  mov     rbp, rsp
0x180047ddb  sub     rsp, 70h
0x180047ddf  mov     rax, cs:__security_cookie
0x180047de6  xor     rax, rsp
0x180047de9  mov     [rbp+var_10], rax
0x180047ded  mov     rdi, rdx
0x180047df0  mov     rsi, rcx
0x180047df3  mov     r8d, 0BBh; int
0x180047df9  lea     r15, aCmfstreamingpr_4; "CMFStreamingPropHandler::InsertProperti"...
0x180047e00  mov     rdx, r15; char *
0x180047e03  lea     rcx, [rbp+var_50]; this
0x180047e07  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180047e0c  xor     r14d, r14d
0x180047e0f  mov     [rbp+var_28], r14
0x180047e13  mov     [rbp+var_48], r14
0x180047e17  xorps   xmm0, xmm0
0x180047e1a  movups  [rbp+Buf2], xmm0
0x180047e1e  mov     rax, [rdi]
0x180047e21  lea     rdx, [rbp+var_28]
0x180047e25  mov     rcx, rdi
0x180047e28  mov     rax, [rax+110h]
0x180047e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e34  mov     ebx, eax
0x180047e36  test    eax, eax
0x180047e38  jns     loc_180047EBF
0x180047e3e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047e45  test    rcx, rcx
0x180047e48  jnz     short loc_180047E8B
0x180047e4a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180047e50  mov     rcx, rax
0x180047e53  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180047e5a  test    rax, rax
0x180047e5d  jz      short loc_180047E7D
0x180047e5f  mov     rax, [rax]
0x180047e62  mov     edx, 7F0h
0x180047e67  mov     rax, [rax+8]
0x180047e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e70  test    eax, eax
0x180047e72  jz      short loc_180047E7D
0x180047e74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047e7b  jmp     short loc_180047E8B
0x180047e7d  lea     rcx, qword_18006EB20; this
0x180047e84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047e8b  cmp     [rcx+8], r14b
0x180047e8f  jz      loc_1800483C7
0x180047e95  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047e9a  cmp     [rax+7CCh], ebx
0x180047ea0  jz      loc_1800483C7
0x180047ea6  mov     r8d, 0C3h; int
0x180047eac  mov     r9d, ebx; int
0x180047eaf  mov     rdx, r15; char *
0x180047eb2  mov     rcx, rax; this
0x180047eb5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180047eba  jmp     loc_1800483C7
0x180047ebf  mov     rcx, [rbp+var_28]
0x180047ec3  mov     rax, [rcx]
0x180047ec6  lea     rdx, [rbp+var_48]
0x180047eca  mov     rax, [rax+38h]
0x180047ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ed3  test    eax, eax
0x180047ed5  jns     loc_180047F6A
0x180047edb  mov     rcx, [rbp+var_28]
0x180047edf  mov     rax, [rcx]
0x180047ee2  lea     r8, [rbp+var_48]
0x180047ee6  xor     edx, edx
0x180047ee8  mov     rax, [rax+28h]
0x180047eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ef1  mov     ebx, eax
0x180047ef3  test    eax, eax
0x180047ef5  jns     short loc_180047F6A
0x180047ef7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047efe  test    rcx, rcx
0x180047f01  jnz     short loc_180047F44
0x180047f03  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180047f09  mov     rcx, rax
0x180047f0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180047f13  test    rax, rax
0x180047f16  jz      short loc_180047F36
0x180047f18  mov     rax, [rax]
0x180047f1b  mov     edx, 7F0h
0x180047f20  mov     rax, [rax+8]
0x180047f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f29  test    eax, eax
0x180047f2b  jz      short loc_180047F36
0x180047f2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047f34  jmp     short loc_180047F44
0x180047f36  lea     rcx, qword_18006EB20; this
0x180047f3d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047f44  cmp     [rcx+8], r14b
0x180047f48  jz      loc_1800483C7
0x180047f4e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047f53  cmp     [rax+7CCh], ebx
0x180047f59  jz      loc_1800483C7
0x180047f5f  mov     r8d, 0C8h
0x180047f65  jmp     loc_180047EAC
0x180047f6a  mov     rcx, [rbp+var_48]
0x180047f6e  mov     rax, [rcx]
0x180047f71  lea     rdx, [rbp+Buf2]
0x180047f75  mov     rax, [rax+108h]
0x180047f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f81  mov     ebx, eax
0x180047f83  test    eax, eax
0x180047f85  jns     short loc_180047FFA
0x180047f87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047f8e  test    rcx, rcx
0x180047f91  jnz     short loc_180047FD4
0x180047f93  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180047f99  mov     rcx, rax
0x180047f9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180047fa3  test    rax, rax
0x180047fa6  jz      short loc_180047FC6
0x180047fa8  mov     rax, [rax]
0x180047fab  mov     edx, 7F0h
0x180047fb0  mov     rax, [rax+8]
0x180047fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fb9  test    eax, eax
0x180047fbb  jz      short loc_180047FC6
0x180047fbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047fc4  jmp     short loc_180047FD4
0x180047fc6  lea     rcx, qword_18006EB20; this
0x180047fcd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047fd4  cmp     [rcx+8], r14b
0x180047fd8  jz      loc_1800483C7
0x180047fde  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047fe3  cmp     [rax+7CCh], ebx
0x180047fe9  jz      loc_1800483C7
0x180047fef  mov     r8d, 0CBh
0x180047ff5  jmp     loc_180047EAC
0x180047ffa  mov     r8d, 10h; Size
0x180048000  lea     rdx, [rbp+Buf2]; Buf2
0x180048004  lea     rcx, MFMediaType_Audio; Buf1
0x18004800b  call    memcmp_0
0x180048010  test    eax, eax
0x180048012  jz      loc_1800481FB
0x180048018  mov     r8d, 10h; Size
0x18004801e  lea     rdx, [rbp+Buf2]; Buf2
0x180048022  lea     rcx, MFMediaType_Video; Buf1
0x180048029  call    memcmp_0
0x18004802e  test    eax, eax
0x180048030  jnz     loc_1800483C7
0x180048036  xorps   xmm0, xmm0
0x180048039  xor     eax, eax
0x18004803b  movups  xmmword ptr [rbp+pvar], xmm0
0x18004803f  mov     qword ptr [rbp+pvar+10h], rax
0x180048043  mov     [rbp+var_4C], r14d
0x180048047  mov     rdx, [rbp+var_48]; struct IMFMediaType *
0x18004804b  mov     rcx, rsi; this
0x18004804e  call    ?AddVideoMediaTypeProperties@CMFStreamingPropHandler@@AEAAJPEAUIMFMediaType@@@Z; CMFStreamingPropHandler::AddVideoMediaTypeProperties(IMFMediaType *)
0x180048053  mov     ebx, eax
0x180048055  test    eax, eax
0x180048057  jns     short loc_1800480CC
0x180048059  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048060  test    rcx, rcx
0x180048063  jnz     short loc_1800480A6
0x180048065  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004806b  mov     rcx, rax
0x18004806e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180048075  test    rax, rax
0x180048078  jz      short loc_180048098
0x18004807a  mov     rax, [rax]
0x18004807d  mov     edx, 7F0h
0x180048082  mov     rax, [rax+8]
0x180048086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004808b  test    eax, eax
0x18004808d  jz      short loc_180048098
0x18004808f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048096  jmp     short loc_1800480A6
0x180048098  lea     rcx, qword_18006EB20; this
0x18004809f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800480a6  cmp     [rcx+8], r14b
0x1800480aa  jz      loc_1800483BD
0x1800480b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800480b5  cmp     [rax+7CCh], ebx
0x1800480bb  jz      loc_1800483BD
0x1800480c1  mov     r8d, 0DCh
0x1800480c7  jmp     loc_1800483AF
0x1800480cc  mov     rax, [rdi]
0x1800480cf  lea     rdx, [rbp+var_4C]
0x1800480d3  mov     rcx, rdi
0x1800480d6  mov     rax, [rax+108h]
0x1800480dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480e2  mov     ebx, eax
0x1800480e4  test    eax, eax
0x1800480e6  jns     short loc_18004815B
0x1800480e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800480ef  test    rcx, rcx
0x1800480f2  jnz     short loc_180048135
0x1800480f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800480fa  mov     rcx, rax
0x1800480fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180048104  test    rax, rax
0x180048107  jz      short loc_180048127
0x180048109  mov     rax, [rax]
0x18004810c  mov     edx, 7F0h
0x180048111  mov     rax, [rax+8]
0x180048115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004811a  test    eax, eax
0x18004811c  jz      short loc_180048127
0x18004811e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048125  jmp     short loc_180048135
0x180048127  lea     rcx, qword_18006EB20; this
0x18004812e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180048135  cmp     [rcx+8], r14b
0x180048139  jz      loc_1800483BD
0x18004813f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180048144  cmp     [rax+7CCh], ebx
0x18004814a  jz      loc_1800483BD
0x180048150  mov     r8d, 0DFh
0x180048156  jmp     loc_1800483AF
0x18004815b  mov     eax, 12h
0x180048160  mov     word ptr [rbp+pvar], ax
0x180048164  mov     eax, [rbp+var_4C]
0x180048167  mov     qword ptr [rbp+pvar+8], rax
0x18004816b  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x18004816f  lea     rdx, PKEY_Video_StreamNumber; struct _tagpropertykey *
0x180048176  mov     rcx, rsi; this
0x180048179  call    ?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)
0x18004817e  mov     ebx, eax
0x180048180  test    eax, eax
0x180048182  jns     loc_1800483BD
0x180048188  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004818f  test    rcx, rcx
0x180048192  jnz     short loc_1800481D5
0x180048194  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004819a  mov     rcx, rax
0x18004819d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800481a4  test    rax, rax
0x1800481a7  jz      short loc_1800481C7
0x1800481a9  mov     rax, [rax]
0x1800481ac  mov     edx, 7F0h
0x1800481b1  mov     rax, [rax+8]
0x1800481b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481ba  test    eax, eax
0x1800481bc  jz      short loc_1800481C7
0x1800481be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800481c5  jmp     short loc_1800481D5
0x1800481c7  lea     rcx, qword_18006EB20; this
0x1800481ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800481d5  cmp     [rcx+8], r14b
0x1800481d9  jz      loc_1800483BD
0x1800481df  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800481e4  cmp     [rax+7CCh], ebx
0x1800481ea  jz      loc_1800483BD
0x1800481f0  mov     r8d, 0E1h
0x1800481f6  jmp     loc_1800483AF
0x1800481fb  xorps   xmm0, xmm0
0x1800481fe  xor     eax, eax
0x180048200  movups  xmmword ptr [rbp+pvar], xmm0
0x180048204  mov     qword ptr [rbp+pvar+10h], rax
0x180048208  mov     [rbp+var_4C], r14d
0x18004820c  mov     rdx, [rbp+var_48]; struct IMFMediaType *
0x180048210  mov     rcx, rsi; this
0x180048213  call    ?AddAudioMediaTypeProperties@CMFStreamingPropHandler@@AEAAJPEAUIMFMediaType@@@Z; CMFStreamingPropHandler::AddAudioMediaTypeProperties(IMFMediaType *)
0x180048218  mov     ebx, eax
0x18004821a  test    eax, eax
0x18004821c  jns     short loc_180048291
0x18004821e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048225  test    rcx, rcx
0x180048228  jnz     short loc_18004826B
0x18004822a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180048230  mov     rcx, rax
0x180048233  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004823a  test    rax, rax
0x18004823d  jz      short loc_18004825D
0x18004823f  mov     rax, [rax]
0x180048242  mov     edx, 7F0h
0x180048247  mov     rax, [rax+8]
0x18004824b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048250  test    eax, eax
0x180048252  jz      short loc_18004825D
0x180048254  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004825b  jmp     short loc_18004826B
0x18004825d  lea     rcx, qword_18006EB20; this
0x180048264  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004826b  cmp     [rcx+8], r14b
0x18004826f  jz      loc_1800483BD
0x180048275  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004827a  cmp     [rax+7CCh], ebx
0x180048280  jz      loc_1800483BD
0x180048286  mov     r8d, 0D1h
0x18004828c  jmp     loc_1800483AF
0x180048291  mov     rax, [rdi]
0x180048294  lea     rdx, [rbp+var_4C]
0x180048298  mov     rcx, rdi
0x18004829b  mov     rax, [rax+108h]
0x1800482a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482a7  mov     ebx, eax
0x1800482a9  test    eax, eax
0x1800482ab  jns     short loc_180048320
0x1800482ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800482b4  test    rcx, rcx
0x1800482b7  jnz     short loc_1800482FA
0x1800482b9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800482bf  mov     rcx, rax
  ... truncated ...
```
